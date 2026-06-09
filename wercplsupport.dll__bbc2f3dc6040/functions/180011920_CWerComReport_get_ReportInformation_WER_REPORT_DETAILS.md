# CWerComReport::get_ReportInformation(_WER_REPORT_DETAILS *)

- ea: `0x180011920`
- end: `0x180011976`
- name: `?get_ReportInformation@CWerComReport@@UEAAJPEAU_WER_REPORT_DETAILS@@@Z`
- size: `86`
- prototype: `int(CWerComReport *__hidden this, struct _WER_REPORT_DETAILS *)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180007d20`
- `0x180007fe0`
- `0x1800108f4`
- `0x180011920`

## pseudocode

```c
__int64 __fastcall CWerComReport::get_ReportInformation(CWerComReport *this, struct _WER_REPORT_DETAILS *a2)
{
  int ReportInformation; // ebx
  int v6; // [rsp+40h] [rbp+18h] BYREF

  v6 = 2;
  ReportInformation = CAutoImpersonate::ImpersonateUserHighestPrivs((CAutoImpersonate *)&v6);
  if ( ReportInformation >= 0 )
    ReportInformation = CWerComReport::_get_ReportInformation((CWerComReport *)((char *)this - 24), a2);
  CAutoImpersonate::~CAutoImpersonate((CAutoImpersonate *)&v6);
  return (unsigned int)ReportInformation;
}

```

## disassembly

```asm
0x180011920  mov     rax, rsp
0x180011923  mov     [rax+8], rbx
0x180011927  mov     [rax+10h], rsi
0x18001192b  push    rdi
0x18001192c  sub     rsp, 20h
0x180011930  mov     rsi, rcx
0x180011933  mov     dword ptr [rax+18h], 2
0x18001193a  lea     rcx, [rax+18h]; this
0x18001193e  mov     rdi, rdx
0x180011941  call    ?ImpersonateUserHighestPrivs@CAutoImpersonate@@QEAAJXZ; CAutoImpersonate::ImpersonateUserHighestPrivs(void)
0x180011946  mov     ebx, eax
0x180011948  test    eax, eax
0x18001194a  js      short loc_18001195A
0x18001194c  lea     rcx, [rsi-18h]; this
0x180011950  mov     rdx, rdi; struct _WER_REPORT_DETAILS *
0x180011953  call    ?_get_ReportInformation@CWerComReport@@QEAAJPEAU_WER_REPORT_DETAILS@@@Z; CWerComReport::_get_ReportInformation(_WER_REPORT_DETAILS *)
0x180011958  mov     ebx, eax
0x18001195a  lea     rcx, [rsp+28h+arg_10]; this
0x18001195f  call    ??1CAutoImpersonate@@QEAA@XZ; CAutoImpersonate::~CAutoImpersonate(void)
0x180011964  mov     rsi, [rsp+28h+arg_8]
0x180011969  mov     eax, ebx
0x18001196b  mov     rbx, [rsp+28h+arg_0]
0x180011970  add     rsp, 20h
0x180011974  pop     rdi
0x180011975  retn
```
