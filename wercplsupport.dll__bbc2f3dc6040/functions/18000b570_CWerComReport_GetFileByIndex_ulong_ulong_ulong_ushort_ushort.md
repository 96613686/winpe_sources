# CWerComReport::GetFileByIndex(ulong,ulong *,ulong *,ushort * *,ushort * *)

- ea: `0x18000b570`
- end: `0x18000b5e2`
- name: `?GetFileByIndex@CWerComReport@@UEAAJKPEAK0PEAPEAG1@Z`
- size: `114`
- prototype: `__int64 __fastcall(CWerComReport *this, unsigned int, unsigned int *, unsigned int *, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180007d20`
- `0x180007fe0`
- `0x18000b570`
- `0x18000f7f8`

## pseudocode

```c
__int64 __fastcall CWerComReport::GetFileByIndex(
        CWerComReport *this,
        unsigned int a2,
        unsigned int *a3,
        unsigned int *a4,
        unsigned __int16 **a5,
        unsigned __int16 **a6)
{
  int FileByIndex; // ebx
  _DWORD v12[14]; // [rsp+30h] [rbp-38h] BYREF

  v12[0] = 2;
  FileByIndex = CAutoImpersonate::ImpersonateUserHighestPrivs((CAutoImpersonate *)v12);
  if ( FileByIndex >= 0 )
    FileByIndex = CWerComReport::_GetFileByIndex((CWerComReport *)((char *)this - 24), a2, a3, a4, a5, a6);
  CAutoImpersonate::~CAutoImpersonate((CAutoImpersonate *)v12);
  return (unsigned int)FileByIndex;
}

```

## disassembly

```asm
0x18000b570  push    rbx
0x18000b572  push    rbp
0x18000b573  push    rsi
0x18000b574  push    rdi
0x18000b575  push    r14
0x18000b577  sub     rsp, 40h
0x18000b57b  mov     r14, rcx
0x18000b57e  mov     [rsp+68h+var_38], 2
0x18000b586  lea     rcx, [rsp+68h+var_38]; this
0x18000b58b  mov     rdi, r9
0x18000b58e  mov     rsi, r8
0x18000b591  mov     ebp, edx
0x18000b593  call    ?ImpersonateUserHighestPrivs@CAutoImpersonate@@QEAAJXZ; CAutoImpersonate::ImpersonateUserHighestPrivs(void)
0x18000b598  mov     ebx, eax
0x18000b59a  test    eax, eax
0x18000b59c  js      short loc_18000B5CB
0x18000b59e  mov     rax, [rsp+68h+arg_28]
0x18000b5a6  lea     rcx, [r14-18h]; this
0x18000b5aa  mov     [rsp+68h+var_40], rax; unsigned __int16 **
0x18000b5af  mov     r9, rdi; unsigned int *
0x18000b5b2  mov     rax, [rsp+68h+arg_20]
0x18000b5ba  mov     r8, rsi; unsigned int *
0x18000b5bd  mov     edx, ebp; unsigned int
0x18000b5bf  mov     [rsp+68h+var_48], rax; unsigned __int16 **
0x18000b5c4  call    ?_GetFileByIndex@CWerComReport@@QEAAJKPEAK0PEAPEAG1@Z; CWerComReport::_GetFileByIndex(ulong,ulong *,ulong *,ushort * *,ushort * *)
0x18000b5c9  mov     ebx, eax
0x18000b5cb  lea     rcx, [rsp+68h+var_38]; this
0x18000b5d0  call    ??1CAutoImpersonate@@QEAA@XZ; CAutoImpersonate::~CAutoImpersonate(void)
0x18000b5d5  mov     eax, ebx
0x18000b5d7  add     rsp, 40h
0x18000b5db  pop     r14
0x18000b5dd  pop     rdi
0x18000b5de  pop     rsi
0x18000b5df  pop     rbp
0x18000b5e0  pop     rbx
0x18000b5e1  retn
```
