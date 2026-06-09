# CWerComReport::get_IsWow64(int *)

- ea: `0x1800116e0`
- end: `0x180011736`
- name: `?get_IsWow64@CWerComReport@@UEAAJPEAH@Z`
- size: `86`
- prototype: `int(CWerComReport *__hidden this, int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180007d20`
- `0x180007fe0`
- `0x180010650`
- `0x1800116e0`

## pseudocode

```c
__int64 __fastcall CWerComReport::get_IsWow64(CWerComReport *this, int *a2)
{
  int IsWow64; // ebx
  int v6; // [rsp+40h] [rbp+18h] BYREF

  v6 = 2;
  IsWow64 = CAutoImpersonate::ImpersonateUserHighestPrivs((CAutoImpersonate *)&v6);
  if ( IsWow64 >= 0 )
    IsWow64 = CWerComReport::_get_IsWow64((CWerComReport *)((char *)this - 24), a2);
  CAutoImpersonate::~CAutoImpersonate((CAutoImpersonate *)&v6);
  return (unsigned int)IsWow64;
}

```

## disassembly

```asm
0x1800116e0  mov     rax, rsp
0x1800116e3  mov     [rax+8], rbx
0x1800116e7  mov     [rax+10h], rsi
0x1800116eb  push    rdi
0x1800116ec  sub     rsp, 20h
0x1800116f0  mov     rsi, rcx
0x1800116f3  mov     dword ptr [rax+18h], 2
0x1800116fa  lea     rcx, [rax+18h]; this
0x1800116fe  mov     rdi, rdx
0x180011701  call    ?ImpersonateUserHighestPrivs@CAutoImpersonate@@QEAAJXZ; CAutoImpersonate::ImpersonateUserHighestPrivs(void)
0x180011706  mov     ebx, eax
0x180011708  test    eax, eax
0x18001170a  js      short loc_18001171A
0x18001170c  lea     rcx, [rsi-18h]; this
0x180011710  mov     rdx, rdi; int *
0x180011713  call    ?_get_IsWow64@CWerComReport@@QEAAJPEAH@Z; CWerComReport::_get_IsWow64(int *)
0x180011718  mov     ebx, eax
0x18001171a  lea     rcx, [rsp+28h+arg_10]; this
0x18001171f  call    ??1CAutoImpersonate@@QEAA@XZ; CAutoImpersonate::~CAutoImpersonate(void)
0x180011724  mov     rsi, [rsp+28h+arg_8]
0x180011729  mov     eax, ebx
0x18001172b  mov     rbx, [rsp+28h+arg_0]
0x180011730  add     rsp, 20h
0x180011734  pop     rdi
0x180011735  retn
```
