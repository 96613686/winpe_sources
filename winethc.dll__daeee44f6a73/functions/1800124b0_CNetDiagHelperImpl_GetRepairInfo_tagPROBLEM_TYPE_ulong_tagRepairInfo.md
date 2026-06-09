# CNetDiagHelperImpl::GetRepairInfo(tagPROBLEM_TYPE,ulong *,tagRepairInfo * *)

- ea: `0x1800124b0`
- end: `0x18001250a`
- name: `?GetRepairInfo@CNetDiagHelperImpl@@UEAAJW4tagPROBLEM_TYPE@@PEAKPEAPEAUtagRepairInfo@@@Z`
- size: `90`
- prototype: `__int64 __fastcall(CNetDiagHelperImpl *__hidden this, enum tagPROBLEM_TYPE, unsigned int *, struct tagRepairInfo **)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1800124b0`
- `0x180012ca0`

## pseudocode

```c
__int64 __fastcall CNetDiagHelperImpl::GetRepairInfo(
        CNetDiagHelperImpl *this,
        enum tagPROBLEM_TYPE a2,
        unsigned int *a3,
        struct tagRepairInfo **a4)
{
  __int64 result; // rax

  if ( !a3 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( !a4 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( *((_DWORD *)this + 4) != 1 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  result = 2147500033LL;
  *a4 = 0;
  *a3 = 0;
  return result;
}

```

## disassembly

```asm
0x1800124b0  mov     [rsp+arg_0], rbx
0x1800124b5  mov     [rsp+arg_8], rsi
0x1800124ba  push    rdi
0x1800124bb  sub     rsp, 20h
0x1800124bf  mov     rbx, r9
0x1800124c2  mov     rdi, r8
0x1800124c5  mov     rsi, rcx
0x1800124c8  test    r8, r8
0x1800124cb  jnz     short loc_1800124D2
0x1800124cd  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800124d2  test    rbx, rbx
0x1800124d5  jnz     short loc_1800124DC
0x1800124d7  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800124dc  cmp     dword ptr [rsi+10h], 1
0x1800124e0  jz      short loc_1800124E7
0x1800124e2  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800124e7  mov     rsi, [rsp+28h+arg_8]
0x1800124ec  mov     eax, 80004001h
0x1800124f1  mov     qword ptr [rbx], 0
0x1800124f8  mov     rbx, [rsp+28h+arg_0]
0x1800124fd  mov     dword ptr [rdi], 0
0x180012503  add     rsp, 20h
0x180012507  pop     rdi
0x180012508  retn
```
