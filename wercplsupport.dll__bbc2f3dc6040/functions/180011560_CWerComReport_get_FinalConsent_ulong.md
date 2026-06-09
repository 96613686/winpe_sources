# CWerComReport::get_FinalConsent(ulong *)

- ea: `0x180011560`
- end: `0x1800115b7`
- name: `?get_FinalConsent@CWerComReport@@UEAAJPEAK@Z`
- size: `87`
- prototype: `__int64 __fastcall(CWerComReport *__hidden this, unsigned int *)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180007d20`
- `0x180007fe0`
- `0x180011560`

## import_xrefs

- `wer!WerpGetReportFinalConsent` at `0x180011593`
- `wer!WerpGetReportFinalConsent` at `0x180011593`

## pseudocode

```c
__int64 __fastcall CWerComReport::get_FinalConsent(CWerComReport *this, unsigned int *a2)
{
  int ReportFinalConsent; // ebx
  int v6; // [rsp+40h] [rbp+18h] BYREF

  v6 = 2;
  ReportFinalConsent = CAutoImpersonate::ImpersonateUserHighestPrivs((CAutoImpersonate *)&v6);
  if ( ReportFinalConsent >= 0 )
    ReportFinalConsent = WerpGetReportFinalConsent(*((_QWORD *)this + 1), a2);
  CAutoImpersonate::~CAutoImpersonate((CAutoImpersonate *)&v6);
  return (unsigned int)ReportFinalConsent;
}

```

## disassembly

```asm
0x180011560  mov     rax, rsp
0x180011563  mov     [rax+8], rbx
0x180011567  mov     [rax+10h], rsi
0x18001156b  push    rdi
0x18001156c  sub     rsp, 20h
0x180011570  mov     rsi, rcx
0x180011573  mov     dword ptr [rax+18h], 2
0x18001157a  lea     rcx, [rax+18h]; this
0x18001157e  mov     rdi, rdx
0x180011581  call    ?ImpersonateUserHighestPrivs@CAutoImpersonate@@QEAAJXZ; CAutoImpersonate::ImpersonateUserHighestPrivs(void)
0x180011586  mov     ebx, eax
0x180011588  test    eax, eax
0x18001158a  js      short loc_18001159B
0x18001158c  mov     rcx, [rsi+8]
0x180011590  mov     rdx, rdi
0x180011593  call    cs:__imp_WerpGetReportFinalConsent
0x180011599  mov     ebx, eax
0x18001159b  lea     rcx, [rsp+28h+arg_10]; this
0x1800115a0  call    ??1CAutoImpersonate@@QEAA@XZ; CAutoImpersonate::~CAutoImpersonate(void)
0x1800115a5  mov     rsi, [rsp+28h+arg_8]
0x1800115aa  mov     eax, ebx
0x1800115ac  mov     rbx, [rsp+28h+arg_0]
0x1800115b1  add     rsp, 20h
0x1800115b5  pop     rdi
0x1800115b6  retn
```
