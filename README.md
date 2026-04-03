cat > README.md << 'EOF'
# CD Project

## Branches
- **main** - Production
- **stage** - Staging/Testing
- **dev** - Development

## CI/CD Pipeline
- Jenkins Multibranch Pipeline
- Auto deploy on push

## Workflow
1. Push to `dev` → Auto deploy to Dev
2. Merge to `stage` → Auto deploy to Stage
3. Merge to `main` → Manual approval → Production
EOF
