# _OSDeploymentRemote::RemoteUHOSDeploymentProcessHost::CreateDeploymentSession_::_1_::dtor$4

- ea: `0x140021843`
- end: `0x14002184f`
- name: `_OSDeploymentRemote::RemoteUHOSDeploymentProcessHost::CreateDeploymentSession_::_1_::dtor$4`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140011b1c`

## pseudocode

```c
_QWORD *__fastcall OSDeploymentRemote::RemoteUHOSDeploymentProcessHost::CreateDeploymentSession_::_1_::dtor_4(
        __int64 a1,
        __int64 a2)
{
  return Microsoft::WRL::ComPtr<OSDeploymentRemote::RemoteDeploymentSession>::~ComPtr<OSDeploymentRemote::RemoteDeploymentSession>((_QWORD *)(a2 + 48));
}

```

## disassembly

```asm
0x140021843  lea     rcx, [rdx+30h]
0x14002184a  jmp     ??1?$ComPtr@VRemoteDeploymentSession@OSDeploymentRemote@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<OSDeploymentRemote::RemoteDeploymentSession>::~ComPtr<OSDeploymentRemote::RemoteDeploymentSession>(void)
```
