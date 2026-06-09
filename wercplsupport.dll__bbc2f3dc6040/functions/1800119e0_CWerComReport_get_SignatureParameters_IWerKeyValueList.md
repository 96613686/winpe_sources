# CWerComReport::get_SignatureParameters(IWerKeyValueList * *)

- ea: `0x1800119e0`
- end: `0x180011a36`
- name: `?get_SignatureParameters@CWerComReport@@UEAAJPEAPEAUIWerKeyValueList@@@Z`
- size: `86`
- prototype: `int(CWerComReport *__hidden this, struct IWerKeyValueList **)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180007d20`
- `0x180007fe0`
- `0x180010c08`
- `0x1800119e0`

## pseudocode

```c
__int64 __fastcall CWerComReport::get_SignatureParameters(CWerComReport *this, struct IWerKeyValueList **a2)
{
  int SignatureParameters; // ebx
  int v6; // [rsp+40h] [rbp+18h] BYREF

  v6 = 2;
  SignatureParameters = CAutoImpersonate::ImpersonateUserHighestPrivs((CAutoImpersonate *)&v6);
  if ( SignatureParameters >= 0 )
    SignatureParameters = CWerComReport::_get_SignatureParameters((CWerComReport *)((char *)this - 24), a2);
  CAutoImpersonate::~CAutoImpersonate((CAutoImpersonate *)&v6);
  return (unsigned int)SignatureParameters;
}

```

## disassembly

```asm
0x1800119e0  mov     rax, rsp
0x1800119e3  mov     [rax+8], rbx
0x1800119e7  mov     [rax+10h], rsi
0x1800119eb  push    rdi
0x1800119ec  sub     rsp, 20h
0x1800119f0  mov     rsi, rcx
0x1800119f3  mov     dword ptr [rax+18h], 2
0x1800119fa  lea     rcx, [rax+18h]; this
0x1800119fe  mov     rdi, rdx
0x180011a01  call    ?ImpersonateUserHighestPrivs@CAutoImpersonate@@QEAAJXZ; CAutoImpersonate::ImpersonateUserHighestPrivs(void)
0x180011a06  mov     ebx, eax
0x180011a08  test    eax, eax
0x180011a0a  js      short loc_180011A1A
0x180011a0c  lea     rcx, [rsi-18h]; this
0x180011a10  mov     rdx, rdi; struct IWerKeyValueList **
0x180011a13  call    ?_get_SignatureParameters@CWerComReport@@QEAAJPEAPEAUIWerKeyValueList@@@Z; CWerComReport::_get_SignatureParameters(IWerKeyValueList * *)
0x180011a18  mov     ebx, eax
0x180011a1a  lea     rcx, [rsp+28h+arg_10]; this
0x180011a1f  call    ??1CAutoImpersonate@@QEAA@XZ; CAutoImpersonate::~CAutoImpersonate(void)
0x180011a24  mov     rsi, [rsp+28h+arg_8]
0x180011a29  mov     eax, ebx
0x180011a2b  mov     rbx, [rsp+28h+arg_0]
0x180011a30  add     rsp, 20h
0x180011a34  pop     rdi
0x180011a35  retn
```
