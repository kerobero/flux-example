# Flux CD Example Project

This project demonstrates a basic setup for using Flux CD to manage Kubernetes resources through GitOps principles. It includes the necessary configurations to deploy an Nginx application within a specified namespace.

## Project Structure

```
fluxcd-example
├── clusters
│   └── my-cluster
│       ├── kustomization.yaml          # Kustomization for the cluster
│       ├── apps
│       │   └── nginx
│       │       ├── kustomization.yaml  # Kustomization for the Nginx app
│       │       └── deployment.yaml     # Deployment manifest for Nginx
│       └── infrastructure
│           └── namespace.yaml          # Namespace definition
├── apps
│   └── nginx
│       ├── kustomization.yaml          # Higher-level Kustomization for Nginx
│       └── deployment.yaml             # Duplicate Deployment manifest for local testing
├── flux
│   └── flux-system
│       ├── gotk-components.yaml        # Flux components for GitOps
│       ├── gotk-sync.yaml              # Sync configuration for Flux
│       └── kustomization.yaml          # Kustomization for Flux components
├── .gitignore                           # Git ignore file
└── README.md                            # Project documentation
```

## Getting Started

1. **Prerequisites**: Ensure you have a Kubernetes cluster running and `kubectl` configured to interact with it.

2. **Install Flux**: Follow the official Flux documentation to install Flux CLI and bootstrap your Git repository.

3. **Deploy the Application**:
   - Navigate to the `clusters/my-cluster` directory.
   - Apply the Kustomization to deploy the Nginx application and the necessary infrastructure:
     ```
     kubectl apply -k .
     ```

4. **Verify Deployment**: Check the status of the Nginx deployment:
   ```
   kubectl get deployments -n <your-namespace>
   ```

## Contributing

Feel free to submit issues or pull requests to improve this example project. 

## License

This project is licensed under the MIT License.