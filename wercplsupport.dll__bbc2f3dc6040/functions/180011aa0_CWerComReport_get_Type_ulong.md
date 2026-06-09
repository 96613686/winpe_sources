# CWerComReport::get_Type(ulong *)

- ea: `0x180011aa0`
- end: `0x180011b56`
- name: `?get_Type@CWerComReport@@UEAAJPEAK@Z`
- size: `182`
- prototype: `__int64 __fastcall(CWerComReport *__hidden this, unsigned int *)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180006c9c`
- `0x180007d20`
- `0x180007fe0`
- `0x18000e35c`
- `0x180011aa0`

## import_xrefs

- `wer!WerpGetReportType` at `0x180011b23`
- `wer!WerpGetReportType` at `0x180011b23`

## pseudocode

```c
__int64 __fastcall CWerComReport::get_Type(CWerComReport *this, unsigned int *a2)
{
  int WerApiLock; // ebx
  int v6; // [rsp+40h] [rbp+18h] BYREF
  __int64 v7; // [rsp+48h] [rbp+20h] BYREF

  v6 = 2;
  WerApiLock = CAutoImpersonate::ImpersonateUserHighestPrivs((CAutoImpersonate *)&v6);
  if ( WerApiLock >= 0 )
  {
    v7 = 0;
    WerApiLock = CWerApiAutoLock::TryGetWerApiLock((CWerApiAutoLock *)&v7, (CWerComReport *)((char *)this - 24));
    if ( WerApiLock >= 0 )
    {
      WerApiLock = WerpGetReportType(*((_QWORD *)this + 1), a2);
    }
    else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        55,
        WPP_132f0e6ae0033c985ddb49c0ccaaa1a1_Traceguids,
        (unsigned int)WerApiLock);
    }
    if ( v7 )
      _InterlockedExchange((volatile __int32 *)(v7 + 48), 0);
  }
  CAutoImpersonate::~CAutoImpersonate((CAutoImpersonate *)&v6);
  return (unsigned int)WerApiLock;
}

```

## disassembly

```asm
0x180011aa0  mov     rax, rsp
0x180011aa3  mov     [rax+8], rbx
0x180011aa7  mov     [rax+10h], rsi
0x180011aab  push    rdi
0x180011aac  sub     rsp, 20h
0x180011ab0  mov     rdi, rcx
0x180011ab3  mov     dword ptr [rax+18h], 2
0x180011aba  lea     rcx, [rax+18h]; this
0x180011abe  mov     rsi, rdx
0x180011ac1  call    ?ImpersonateUserHighestPrivs@CAutoImpersonate@@QEAAJXZ; CAutoImpersonate::ImpersonateUserHighestPrivs(void)
0x180011ac6  mov     ebx, eax
0x180011ac8  test    eax, eax
0x180011aca  js      short loc_180011B3A
0x180011acc  lea     rdx, [rdi-18h]; struct CWerComReport *
0x180011ad0  mov     [rsp+28h+arg_18], 0
0x180011ad9  lea     rcx, [rsp+28h+arg_18]; this
0x180011ade  call    ?TryGetWerApiLock@CWerApiAutoLock@@QEAAJPEAVCWerComReport@@@Z; CWerApiAutoLock::TryGetWerApiLock(CWerComReport *)
0x180011ae3  mov     ebx, eax
0x180011ae5  test    eax, eax
0x180011ae7  jns     short loc_180011B1C
0x180011ae9  mov     rcx, cs:WPP_GLOBAL_Control
0x180011af0  lea     rax, WPP_GLOBAL_Control
0x180011af7  cmp     rcx, rax
0x180011afa  jz      short loc_180011B2B
0x180011afc  test    byte ptr [rcx+1Ch], 1
0x180011b00  jz      short loc_180011B2B
0x180011b02  mov     rcx, [rcx+10h]
0x180011b06  lea     r8, WPP_132f0e6ae0033c985ddb49c0ccaaa1a1_Traceguids
0x180011b0d  mov     edx, 37h ; '7'
0x180011b12  mov     r9d, ebx
0x180011b15  call    WPP_SF_d
0x180011b1a  jmp     short loc_180011B2B
0x180011b1c  mov     rcx, [rdi+8]
0x180011b20  mov     rdx, rsi
0x180011b23  call    cs:__imp_WerpGetReportType
0x180011b29  mov     ebx, eax
0x180011b2b  mov     rax, [rsp+28h+arg_18]
0x180011b30  test    rax, rax
0x180011b33  jz      short loc_180011B3A
0x180011b35  xor     ecx, ecx
0x180011b37  xchg    ecx, [rax+30h]
0x180011b3a  lea     rcx, [rsp+28h+arg_10]; this
0x180011b3f  call    ??1CAutoImpersonate@@QEAA@XZ; CAutoImpersonate::~CAutoImpersonate(void)
0x180011b44  mov     rsi, [rsp+28h+arg_8]
0x180011b49  mov     eax, ebx
0x180011b4b  mov     rbx, [rsp+28h+arg_0]
0x180011b50  add     rsp, 20h
0x180011b54  pop     rdi
0x180011b55  retn
```
