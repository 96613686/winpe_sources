# CWerComReport::get_UIParameters(IWerStringList * *)

- ea: `0x180011b60`
- end: `0x180011bb6`
- name: `?get_UIParameters@CWerComReport@@UEAAJPEAPEAUIWerStringList@@@Z`
- size: `86`
- prototype: `int(CWerComReport *__hidden this, struct IWerStringList **)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180007d20`
- `0x180007fe0`
- `0x180010e50`
- `0x180011b60`

## pseudocode

```c
__int64 __fastcall CWerComReport::get_UIParameters(CWerComReport *this, struct IWerStringList **a2)
{
  int UIParameters; // ebx
  int v6; // [rsp+40h] [rbp+18h] BYREF

  v6 = 2;
  UIParameters = CAutoImpersonate::ImpersonateUserHighestPrivs((CAutoImpersonate *)&v6);
  if ( UIParameters >= 0 )
    UIParameters = CWerComReport::_get_UIParameters((CWerComReport *)((char *)this - 24), a2);
  CAutoImpersonate::~CAutoImpersonate((CAutoImpersonate *)&v6);
  return (unsigned int)UIParameters;
}

```

## disassembly

```asm
0x180011b60  mov     rax, rsp
0x180011b63  mov     [rax+8], rbx
0x180011b67  mov     [rax+10h], rsi
0x180011b6b  push    rdi
0x180011b6c  sub     rsp, 20h
0x180011b70  mov     rsi, rcx
0x180011b73  mov     dword ptr [rax+18h], 2
0x180011b7a  lea     rcx, [rax+18h]; this
0x180011b7e  mov     rdi, rdx
0x180011b81  call    ?ImpersonateUserHighestPrivs@CAutoImpersonate@@QEAAJXZ; CAutoImpersonate::ImpersonateUserHighestPrivs(void)
0x180011b86  mov     ebx, eax
0x180011b88  test    eax, eax
0x180011b8a  js      short loc_180011B9A
0x180011b8c  lea     rcx, [rsi-18h]; this
0x180011b90  mov     rdx, rdi; struct IWerStringList **
0x180011b93  call    ?_get_UIParameters@CWerComReport@@QEAAJPEAPEAUIWerStringList@@@Z; CWerComReport::_get_UIParameters(IWerStringList * *)
0x180011b98  mov     ebx, eax
0x180011b9a  lea     rcx, [rsp+28h+arg_10]; this
0x180011b9f  call    ??1CAutoImpersonate@@QEAA@XZ; CAutoImpersonate::~CAutoImpersonate(void)
0x180011ba4  mov     rsi, [rsp+28h+arg_8]
0x180011ba9  mov     eax, ebx
0x180011bab  mov     rbx, [rsp+28h+arg_0]
0x180011bb0  add     rsp, 20h
0x180011bb4  pop     rdi
0x180011bb5  retn
```
