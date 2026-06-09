# CWerComStoreFactory::GetAdminQueue(IWerStore * *)

- ea: `0x18000b050`
- end: `0x18000b096`
- name: `?GetAdminQueue@CWerComStoreFactory@@UEAAJPEAPEAUIWerStore@@@Z`
- size: `70`
- prototype: `__int64 __fastcall(CWerComStoreFactory *__hidden this, struct IWerStore **)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180007d20`
- `0x180007fe0`
- `0x180008420`
- `0x18000b050`

## pseudocode

```c
__int64 __fastcall CWerComStoreFactory::GetAdminQueue(CWerComStoreFactory *this, struct IWerStore **a2)
{
  int v3; // ebx
  int v5; // [rsp+40h] [rbp+18h] BYREF

  v5 = 2;
  v3 = CAutoImpersonate::ImpersonateUserHighestPrivs((CAutoImpersonate *)&v5);
  if ( v3 >= 0 )
    v3 = OpenWerStore<&long WerpOpenMachineQueue(void * *)>((__int64)a2);
  CAutoImpersonate::~CAutoImpersonate((CAutoImpersonate *)&v5);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18000b050  mov     [rsp+arg_0], rbx
0x18000b055  push    rdi
0x18000b056  sub     rsp, 20h
0x18000b05a  lea     rcx, [rsp+28h+arg_10]; this
0x18000b05f  mov     [rsp+28h+arg_10], 2
0x18000b067  mov     rdi, rdx
0x18000b06a  call    ?ImpersonateUserHighestPrivs@CAutoImpersonate@@QEAAJXZ; CAutoImpersonate::ImpersonateUserHighestPrivs(void)
0x18000b06f  mov     ebx, eax
0x18000b071  test    eax, eax
0x18000b073  js      short loc_18000B07F
0x18000b075  mov     rcx, rdi
0x18000b078  call    ??$OpenWerStore@$1?WerpOpenMachineQueue@@YAJPEAPEAX@Z@@YAJPEAPEAUIWerStore@@@Z; OpenWerStore<&WerpOpenMachineQueue(void * *)>(IWerStore * *)
0x18000b07d  mov     ebx, eax
0x18000b07f  lea     rcx, [rsp+28h+arg_10]; this
0x18000b084  call    ??1CAutoImpersonate@@QEAA@XZ; CAutoImpersonate::~CAutoImpersonate(void)
0x18000b089  mov     eax, ebx
0x18000b08b  mov     rbx, [rsp+28h+arg_0]
0x18000b090  add     rsp, 20h
0x18000b094  pop     rdi
0x18000b095  retn
```
