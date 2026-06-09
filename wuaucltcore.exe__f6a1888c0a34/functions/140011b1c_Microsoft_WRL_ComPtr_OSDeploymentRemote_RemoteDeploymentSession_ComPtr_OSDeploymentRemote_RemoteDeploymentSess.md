# Microsoft::WRL::ComPtr<OSDeploymentRemote::RemoteDeploymentSession>::~ComPtr<OSDeploymentRemote::RemoteDeploymentSession>(void)

- ea: `0x140011b1c`
- end: `0x140011b44`
- name: `??1?$ComPtr@VRemoteDeploymentSession@OSDeploymentRemote@@@WRL@Microsoft@@QEAA@XZ`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140021843`

## callees

- `0x140011b1c`
- `0x1400206e0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall Microsoft::WRL::ComPtr<OSDeploymentRemote::RemoteDeploymentSession>::~ComPtr<OSDeploymentRemote::RemoteDeploymentSession>(
        _QWORD *a1)
{
  _QWORD *result; // rax
  __int64 v2; // rcx

  result = a1;
  v2 = *a1;
  if ( v2 )
  {
    *result = 0;
    return (_QWORD *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  }
  return result;
}

```

## disassembly

```asm
0x140011b1c  sub     rsp, 28h
0x140011b20  mov     rax, rcx
0x140011b23  mov     rcx, [rcx]
0x140011b26  test    rcx, rcx
0x140011b29  jz      short loc_140011B3F
0x140011b2b  mov     qword ptr [rax], 0
0x140011b32  mov     rax, [rcx]
0x140011b35  mov     rax, [rax+10h]
0x140011b39  call    _guard_dispatch_icall
0x140011b3e  nop
0x140011b3f  add     rsp, 28h
0x140011b43  retn
```
