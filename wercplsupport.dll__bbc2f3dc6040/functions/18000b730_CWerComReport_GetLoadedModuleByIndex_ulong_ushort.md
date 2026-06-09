# CWerComReport::GetLoadedModuleByIndex(ulong,ushort * *)

- ea: `0x18000b730`
- end: `0x18000b77e`
- name: `?GetLoadedModuleByIndex@CWerComReport@@UEAAJKPEAPEAG@Z`
- size: `78`
- prototype: `int(CWerComReport *__hidden this, unsigned int, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180007d20`
- `0x180007fe0`
- `0x18000b730`
- `0x18000f9dc`

## pseudocode

```c
__int64 __fastcall CWerComReport::GetLoadedModuleByIndex(CWerComReport *this, unsigned int a2, unsigned __int16 **a3)
{
  int LoadedModuleByIndex; // ebx
  int v8; // [rsp+68h] [rbp+20h] BYREF

  v8 = 2;
  LoadedModuleByIndex = CAutoImpersonate::ImpersonateUserHighestPrivs((CAutoImpersonate *)&v8);
  if ( LoadedModuleByIndex >= 0 )
    LoadedModuleByIndex = CWerComReport::_GetLoadedModuleByIndex((CWerComReport *)((char *)this - 24), a2, a3);
  CAutoImpersonate::~CAutoImpersonate((CAutoImpersonate *)&v8);
  return (unsigned int)LoadedModuleByIndex;
}

```

## disassembly

```asm
0x18000b730  push    rbx
0x18000b732  push    rbp
0x18000b733  push    rsi
0x18000b734  push    rdi
0x18000b735  sub     rsp, 28h
0x18000b739  mov     rbp, rcx
0x18000b73c  mov     [rsp+48h+arg_18], 2
0x18000b744  lea     rcx, [rsp+48h+arg_18]; this
0x18000b749  mov     rdi, r8
0x18000b74c  mov     esi, edx
0x18000b74e  call    ?ImpersonateUserHighestPrivs@CAutoImpersonate@@QEAAJXZ; CAutoImpersonate::ImpersonateUserHighestPrivs(void)
0x18000b753  mov     ebx, eax
0x18000b755  test    eax, eax
0x18000b757  js      short loc_18000B769
0x18000b759  lea     rcx, [rbp-18h]; this
0x18000b75d  mov     r8, rdi; unsigned __int16 **
0x18000b760  mov     edx, esi; unsigned int
0x18000b762  call    ?_GetLoadedModuleByIndex@CWerComReport@@QEAAJKPEAPEAG@Z; CWerComReport::_GetLoadedModuleByIndex(ulong,ushort * *)
0x18000b767  mov     ebx, eax
0x18000b769  lea     rcx, [rsp+48h+arg_18]; this
0x18000b76e  call    ??1CAutoImpersonate@@QEAA@XZ; CAutoImpersonate::~CAutoImpersonate(void)
0x18000b773  mov     eax, ebx
0x18000b775  add     rsp, 28h
0x18000b779  pop     rdi
0x18000b77a  pop     rsi
0x18000b77b  pop     rbp
0x18000b77c  pop     rbx
0x18000b77d  retn
```
