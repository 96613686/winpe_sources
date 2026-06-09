# _OSDeploymentRemote::RemoteUHOSDeploymentProcessHost::CreateDeploymentSession_::_1_::dtor$2

- ea: `0x140021831`
- end: `0x14002183d`
- name: `_OSDeploymentRemote::RemoteUHOSDeploymentProcessHost::CreateDeploymentSession_::_1_::dtor$2`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x14001192c`

## pseudocode

```c
__int64 __fastcall OSDeploymentRemote::RemoteUHOSDeploymentProcessHost::CreateDeploymentSession_::_1_::dtor_2(
        __int64 a1,
        __int64 a2)
{
  return Microsoft::WRL::Details::MakeAllocator<OSDeploymentRemote::RemoteDeploymentSession>::~MakeAllocator<OSDeploymentRemote::RemoteDeploymentSession>(a2 + 56);
}

```

## disassembly

```asm
0x140021831  lea     rcx, [rdx+38h]
0x140021838  jmp     ??1?$MakeAllocator@VRemoteDeploymentSession@OSDeploymentRemote@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<OSDeploymentRemote::RemoteDeploymentSession>::~MakeAllocator<OSDeploymentRemote::RemoteDeploymentSession>(void)
```
