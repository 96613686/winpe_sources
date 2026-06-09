# CConsentUI::Static_ShowUpSellUI(HWND__ *,int *)

- ea: `0x18000a70c`
- end: `0x18000a872`
- name: `?Static_ShowUpSellUI@CConsentUI@@SAJPEAUHWND__@@PEAH@Z`
- size: `358`
- prototype: `__int64 __fastcall(HWND, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180003d00`

## callees

- `0x1800035dc`
- `0x180003604`
- `0x180009944`
- `0x180009a98`
- `0x180009ab8`
- `0x180009b74`
- `0x18000a70c`
- `0x18000ab00`

## import_xrefs

- `wer!WerReportCreate` at `0x18000a74f`
- `wer!WerReportCreate` at `0x18000a74f`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CConsentUI::Static_ShowUpSellUI(HWND a1, int *a2)
{
  int v4; // ebx
  _QWORD *v5; // rcx
  __int64 v6; // rdx
  HWND v8[44]; // [rsp+40h] [rbp-168h] BYREF
  HREPORT phReportHandle; // [rsp+1C0h] [rbp+18h] BYREF

  CConsentUI::CConsentUI((CConsentUI *)v8);
  phReportHandle = 0;
  v4 = WerReportCreate(L"Temp", WerReportNonCritical, 0, &phReportHandle);
  if ( v4 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_fea2387d138a3e728ec0a3daac89d932_Traceguids);
    goto LABEL_15;
  }
  v4 = CConsentUI::Initialize((CConsentUI *)v8, phReportHandle, a1, 0, 0, 0, 0, 0);
  if ( v4 < 0 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_15;
    v6 = 21;
LABEL_9:
    WPP_SF_d(v5[2], v6, WPP_fea2387d138a3e728ec0a3daac89d932_Traceguids, (unsigned int)v4);
    goto LABEL_15;
  }
  v4 = CConsentUI::UpSellShowUI(v8, a2, 0);
  if ( v4 >= 0 )
  {
    v4 = 0;
    goto LABEL_15;
  }
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v6 = 22;
    goto LABEL_9;
  }
LABEL_15:
  tlx::unique_any<tlx::handle_traits<void *,long (void *),&long WerReportCloseHandle(void *),0>>::~unique_any<tlx::handle_traits<void *,long (void *),&long WerReportCloseHandle(void *),0>>(&phReportHandle);
  CConsentUI::~CConsentUI((CConsentUI *)v8);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000a70c  mov     [rsp+arg_0], rbx
0x18000a711  mov     [rsp+arg_8], rsi
0x18000a716  push    rdi
0x18000a717  sub     rsp, 1A0h
0x18000a71e  mov     rdi, rdx
0x18000a721  mov     rsi, rcx
0x18000a724  lea     rcx, [rsp+1A8h+var_168]; this
0x18000a729  call    ??0CConsentUI@@QEAA@XZ; CConsentUI::CConsentUI(void)
0x18000a72e  nop
0x18000a72f  mov     [rsp+1A8h+phReportHandle], 0
0x18000a73b  lea     r9, [rsp+1A8h+phReportHandle]; phReportHandle
0x18000a743  xor     r8d, r8d; pReportInformation
0x18000a746  xor     edx, edx; repType
0x18000a748  lea     rcx, pwzEventType; "Temp"
0x18000a74f  call    cs:__imp_WerReportCreate
0x18000a755  mov     ebx, eax
0x18000a757  test    eax, eax
0x18000a759  jns     short loc_18000A796
0x18000a75b  lea     rax, WPP_GLOBAL_Control
0x18000a762  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a769  cmp     rcx, rax
0x18000a76c  jz      loc_18000A843
0x18000a772  test    byte ptr [rcx+1Ch], 1
0x18000a776  jz      loc_18000A843
0x18000a77c  mov     edx, 14h
0x18000a781  lea     r8, WPP_fea2387d138a3e728ec0a3daac89d932_Traceguids
0x18000a788  mov     rcx, [rcx+10h]
0x18000a78c  call    WPP_SF_
0x18000a791  jmp     loc_18000A843
0x18000a796  mov     [rsp+1A8h+var_170], 0; void *
0x18000a79f  mov     [rsp+1A8h+var_178], 0; int (*)(void *, struct _WER_UI_CALLBACK_INPUT *const)
0x18000a7a8  mov     [rsp+1A8h+var_180], 0; void *
0x18000a7b1  mov     [rsp+1A8h+var_188], 0; struct _WER_USER_PROMPT_INPUT *
0x18000a7ba  xor     r9d, r9d; struct tagPOINT *
0x18000a7bd  mov     r8, rsi; HWND
0x18000a7c0  mov     rdx, [rsp+1A8h+phReportHandle]; void *
0x18000a7c8  lea     rcx, [rsp+1A8h+var_168]; this
0x18000a7cd  call    ?Initialize@CConsentUI@@QEAAJPEAXPEAUHWND__@@PEAUtagPOINT@@PEAU_WER_USER_PROMPT_INPUT@@0P6AH0QEAU_WER_UI_CALLBACK_INPUT@@@Z0@Z; CConsentUI::Initialize(void *,HWND__ *,tagPOINT *,_WER_USER_PROMPT_INPUT *,void *,int (*)(void *,_WER_UI_CALLBACK_INPUT * const),void *)
0x18000a7d2  mov     ebx, eax
0x18000a7d4  test    eax, eax
0x18000a7d6  jns     short loc_18000A80B
0x18000a7d8  lea     rax, WPP_GLOBAL_Control
0x18000a7df  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a7e6  cmp     rcx, rax
0x18000a7e9  jz      short loc_18000A843
0x18000a7eb  test    byte ptr [rcx+1Ch], 1
0x18000a7ef  jz      short loc_18000A843
0x18000a7f1  mov     edx, 15h
0x18000a7f6  mov     r9d, ebx
0x18000a7f9  lea     r8, WPP_fea2387d138a3e728ec0a3daac89d932_Traceguids
0x18000a800  mov     rcx, [rcx+10h]
0x18000a804  call    WPP_SF_d
0x18000a809  jmp     short loc_18000A843
0x18000a80b  xor     r8d, r8d; int
0x18000a80e  mov     rdx, rdi; int *
0x18000a811  lea     rcx, [rsp+1A8h+var_168]; this
0x18000a816  call    ?UpSellShowUI@CConsentUI@@AEAAJPEAHH@Z; CConsentUI::UpSellShowUI(int *,int)
0x18000a81b  mov     ebx, eax
0x18000a81d  test    eax, eax
0x18000a81f  jns     short loc_18000A841
0x18000a821  lea     rax, WPP_GLOBAL_Control
0x18000a828  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a82f  cmp     rcx, rax
0x18000a832  jz      short loc_18000A843
0x18000a834  test    byte ptr [rcx+1Ch], 1
0x18000a838  jz      short loc_18000A843
0x18000a83a  mov     edx, 16h
0x18000a83f  jmp     short loc_18000A7F6
0x18000a841  xor     ebx, ebx
0x18000a843  lea     rcx, [rsp+1A8h+phReportHandle]
0x18000a84b  call    ??1?$unique_any@U?$handle_traits@PEAX$$A6AJPEAX@Z$1?WerReportCloseHandle@@YAJ0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<void *,long (void *),&WerReportCloseHandle(void *),0>>::~unique_any<tlx::handle_traits<void *,long (void *),&WerReportCloseHandle(void *),0>>(void)
0x18000a850  nop
0x18000a851  lea     rcx, [rsp+1A8h+var_168]; this
0x18000a856  call    ??1CConsentUI@@QEAA@XZ; CConsentUI::~CConsentUI(void)
0x18000a85b  mov     eax, ebx
0x18000a85d  lea     r11, [rsp+1A8h+var_8]
0x18000a865  mov     rbx, [r11+10h]
0x18000a869  mov     rsi, [r11+18h]
0x18000a86d  mov     rsp, r11
0x18000a870  pop     rdi
0x18000a871  retn
```
