# CWerComStoreFactory::GetAdminArchive(IWerStore * *)

- ea: `0x18000b000`
- end: `0x18000b046`
- name: `?GetAdminArchive@CWerComStoreFactory@@UEAAJPEAPEAUIWerStore@@@Z`
- size: `70`
- prototype: `__int64 __fastcall(CWerComStoreFactory *__hidden this, struct IWerStore **)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180007d20`
- `0x180007fe0`
- `0x180008208`
- `0x18000b000`

## pseudocode

```c
__int64 __fastcall CWerComStoreFactory::GetAdminArchive(CWerComStoreFactory *this, struct IWerStore **a2)
{
  int v3; // ebx
  int v5; // [rsp+40h] [rbp+18h] BYREF

  v5 = 2;
  v3 = CAutoImpersonate::ImpersonateUserHighestPrivs((CAutoImpersonate *)&v5);
  if ( v3 >= 0 )
    v3 = OpenWerStore<&long WerpOpenMachineArchive(void * *)>((__int64)a2);
  CAutoImpersonate::~CAutoImpersonate((CAutoImpersonate *)&v5);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18000b000  mov     [rsp+arg_0], rbx
0x18000b005  push    rdi
0x18000b006  sub     rsp, 20h
0x18000b00a  lea     rcx, [rsp+28h+arg_10]; this
0x18000b00f  mov     [rsp+28h+arg_10], 2
0x18000b017  mov     rdi, rdx
0x18000b01a  call    ?ImpersonateUserHighestPrivs@CAutoImpersonate@@QEAAJXZ; CAutoImpersonate::ImpersonateUserHighestPrivs(void)
0x18000b01f  mov     ebx, eax
0x18000b021  test    eax, eax
0x18000b023  js      short loc_18000B02F
0x18000b025  mov     rcx, rdi
0x18000b028  call    ??$OpenWerStore@$1?WerpOpenMachineArchive@@YAJPEAPEAX@Z@@YAJPEAPEAUIWerStore@@@Z; OpenWerStore<&WerpOpenMachineArchive(void * *)>(IWerStore * *)
0x18000b02d  mov     ebx, eax
0x18000b02f  lea     rcx, [rsp+28h+arg_10]; this
0x18000b034  call    ??1CAutoImpersonate@@QEAA@XZ; CAutoImpersonate::~CAutoImpersonate(void)
0x18000b039  mov     eax, ebx
0x18000b03b  mov     rbx, [rsp+28h+arg_0]
0x18000b040  add     rsp, 20h
0x18000b044  pop     rdi
0x18000b045  retn
```
