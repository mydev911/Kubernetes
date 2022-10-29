## Rolling update = Application update = Roll-out

### Replication controller

```
- Only one lable can be select / number of selector is not avalible.
- Rolling update is avaliable But there is down time when its update.
- Roll back is not avaliable
```

### Replica set 
```
- Multi selector is avelable
- Rolling update is not avelable
```

### Deployment

- Service >> Deployment >> Replica-set
```
Rollback / Rolling update / multi selector is avelable
```
