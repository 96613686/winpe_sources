# CWerComReport::get_IntegratorId(ushort * *)

- ea: `0x1800115c0`
- end: `0x180011616`
- name: `?get_IntegratorId@CWerComReport@@UEAAJPEAPEAG@Z`
- size: `86`
- prototype: `int(CWerComReport *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180007d20`
- `0x180007fe0`
- `0x180010508`
- `0x1800115c0`

## pseudocode

```c
__int64 __fastcall CWerComReport::get_IntegratorId(CWerComReport *this, unsigned __int16 **a2)
{
  int IntegratorId; // ebx
  int v6; // [rsp+40h] [rbp+18h] BYREF

  v6 = 2;
  IntegratorId = CAutoImpersonate::ImpersonateUserHighestPrivs((CAutoImpersonate *)&v6);
  if ( IntegratorId >= 0 )
    IntegratorId = CWerComReport::_get_IntegratorId((CWerComReport *)((char *)this - 24), a2);
  CAutoImpersonate::~CAutoImpersonate((CAutoImpersonate *)&v6);
  return (unsigned int)IntegratorId;
}

```

## disassembly

```asm
0x1800115c0  mov     rax, rsp
0x1800115c3  mov     [rax+8], rbx
0x1800115c7  mov     [rax+10h], rsi
0x1800115cb  push    rdi
0x1800115cc  sub     rsp, 20h
0x1800115d0  mov     rsi, rcx
0x1800115d3  mov     dword ptr [rax+18h], 2
0x1800115da  lea     rcx, [rax+18h]; this
0x1800115de  mov     rdi, rdx
0x1800115e1  call    ?ImpersonateUserHighestPrivs@CAutoImpersonate@@QEAAJXZ; CAutoImpersonate::ImpersonateUserHighestPrivs(void)
0x1800115e6  mov     ebx, eax
0x1800115e8  test    eax, eax
0x1800115ea  js      short loc_1800115FA
0x1800115ec  lea     rcx, [rsi-18h]; this
0x1800115f0  mov     rdx, rdi; unsigned __int16 **
0x1800115f3  call    ?_get_IntegratorId@CWerComReport@@QEAAJPEAPEAG@Z; CWerComReport::_get_IntegratorId(ushort * *)
0x1800115f8  mov     ebx, eax
0x1800115fa  lea     rcx, [rsp+28h+arg_10]; this
0x1800115ff  call    ??1CAutoImpersonate@@QEAA@XZ; CAutoImpersonate::~CAutoImpersonate(void)
0x180011604  mov     rsi, [rsp+28h+arg_8]
0x180011609  mov     eax, ebx
0x18001160b  mov     rbx, [rsp+28h+arg_0]
0x180011610  add     rsp, 20h
0x180011614  pop     rdi
0x180011615  retn
```
