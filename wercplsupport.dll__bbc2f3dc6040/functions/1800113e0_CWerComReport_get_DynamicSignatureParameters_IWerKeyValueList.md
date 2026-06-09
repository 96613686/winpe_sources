# CWerComReport::get_DynamicSignatureParameters(IWerKeyValueList * *)

- ea: `0x1800113e0`
- end: `0x180011436`
- name: `?get_DynamicSignatureParameters@CWerComReport@@UEAAJPEAPEAUIWerKeyValueList@@@Z`
- size: `86`
- prototype: `int(CWerComReport *__hidden this, struct IWerKeyValueList **)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180007d20`
- `0x180007fe0`
- `0x1800100b4`
- `0x1800113e0`

## pseudocode

```c
__int64 __fastcall CWerComReport::get_DynamicSignatureParameters(CWerComReport *this, struct IWerKeyValueList **a2)
{
  int DynamicSignatureParameters; // ebx
  int v6; // [rsp+40h] [rbp+18h] BYREF

  v6 = 2;
  DynamicSignatureParameters = CAutoImpersonate::ImpersonateUserHighestPrivs((CAutoImpersonate *)&v6);
  if ( DynamicSignatureParameters >= 0 )
    DynamicSignatureParameters = CWerComReport::_get_DynamicSignatureParameters(
                                   (CWerComReport *)((char *)this - 24),
                                   a2);
  CAutoImpersonate::~CAutoImpersonate((CAutoImpersonate *)&v6);
  return (unsigned int)DynamicSignatureParameters;
}

```

## disassembly

```asm
0x1800113e0  mov     rax, rsp
0x1800113e3  mov     [rax+8], rbx
0x1800113e7  mov     [rax+10h], rsi
0x1800113eb  push    rdi
0x1800113ec  sub     rsp, 20h
0x1800113f0  mov     rsi, rcx
0x1800113f3  mov     dword ptr [rax+18h], 2
0x1800113fa  lea     rcx, [rax+18h]; this
0x1800113fe  mov     rdi, rdx
0x180011401  call    ?ImpersonateUserHighestPrivs@CAutoImpersonate@@QEAAJXZ; CAutoImpersonate::ImpersonateUserHighestPrivs(void)
0x180011406  mov     ebx, eax
0x180011408  test    eax, eax
0x18001140a  js      short loc_18001141A
0x18001140c  lea     rcx, [rsi-18h]; this
0x180011410  mov     rdx, rdi; struct IWerKeyValueList **
0x180011413  call    ?_get_DynamicSignatureParameters@CWerComReport@@QEAAJPEAPEAUIWerKeyValueList@@@Z; CWerComReport::_get_DynamicSignatureParameters(IWerKeyValueList * *)
0x180011418  mov     ebx, eax
0x18001141a  lea     rcx, [rsp+28h+arg_10]; this
0x18001141f  call    ??1CAutoImpersonate@@QEAA@XZ; CAutoImpersonate::~CAutoImpersonate(void)
0x180011424  mov     rsi, [rsp+28h+arg_8]
0x180011429  mov     eax, ebx
0x18001142b  mov     rbx, [rsp+28h+arg_0]
0x180011430  add     rsp, 20h
0x180011434  pop     rdi
0x180011435  retn
```
