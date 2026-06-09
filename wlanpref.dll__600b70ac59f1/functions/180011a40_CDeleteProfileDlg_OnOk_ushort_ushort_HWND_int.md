# CDeleteProfileDlg::OnOk(ushort,ushort,HWND__ *,int &)

- ea: `0x180011a40`
- end: `0x180011b06`
- name: `?OnOk@CDeleteProfileDlg@@QEAA_JGGPEAUHWND__@@AEAH@Z`
- size: `198`
- prototype: `__int64 __fastcall(CDeleteProfileDlg *__hidden this, unsigned __int16, unsigned __int16, HWND, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180011b10`

## callees

- `0x1800036ac`
- `0x180008484`
- `0x180011a40`
- `0x180030010`

## import_xrefs

- `USER32!MessageBoxW` at `0x180011ac8`
- `USER32!MessageBoxW` at `0x180011ac8`
- `USER32!EndDialog` at `0x180011af8`
- `USER32!EndDialog` at `0x180011af8`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CDeleteProfileDlg::OnOk(CDeleteProfileDlg *this, __int64 a2, __int64 a3, const WCHAR *a4)
{
  __int64 v4; // rdx
  HWND *v5; // rbx
  __int64 v6; // rax
  int v7; // eax
  LPCWSTR lpCaption; // [rsp+30h] [rbp+8h] BYREF
  LPCWSTR lpText; // [rsp+48h] [rbp+20h] BYREF

  lpText = a4;
  v4 = *((_QWORD *)this + 9);
  v5 = (HWND *)((char *)this + 8);
  v6 = *(_QWORD *)CSingletonPtr<CWlanProfileStore>::s_pInstance;
  if ( *(_BYTE *)(v4 + 83) )
    v7 = (*(__int64 (**)(void))(v6 + 168))();
  else
    v7 = (*(__int64 (__fastcall **)(__int64, __int64, HWND))(v6 + 248))(
           CSingletonPtr<CWlanProfileStore>::s_pInstance,
           v4,
           *v5);
  if ( v7 == -2147024156 )
  {
    lpCaption = WTL::_atltmpPchNil;
    lpText = WTL::_atltmpPchNil;
    WTL::CString::LoadStringW((WTL::CString *)&lpCaption, 0x4E21u);
    WTL::CString::LoadStringW((WTL::CString *)&lpText, 0x4E6Du);
    MessageBoxW(*v5, lpText, lpCaption, 0x30u);
    WTL::CString::~CString((WTL::CString *)&lpText);
    WTL::CString::~CString((WTL::CString *)&lpCaption);
  }
  else if ( v7 != -2147023673 )
  {
    EndDialog(*v5, (unsigned __int64)(unsigned int)~v7 >> 31);
  }
  return 0;
}

```

## disassembly

```asm
0x180011a40  mov     [rsp+lpText], r9
0x180011a45  push    rbx
0x180011a46  sub     rsp, 20h
0x180011a4a  mov     rdx, [rcx+48h]
0x180011a4e  lea     rbx, [rcx+8]
0x180011a52  mov     rcx, cs:?s_pInstance@?$CSingletonPtr@VCWlanProfileStore@@@@0PEAVCWlanProfileStore@@EA; CWlanProfileStore * CSingletonPtr<CWlanProfileStore>::s_pInstance
0x180011a59  mov     rax, [rcx]
0x180011a5c  cmp     byte ptr [rdx+53h], 0
0x180011a60  jnz     short loc_180011A73
0x180011a62  mov     r8, [rbx]
0x180011a65  mov     rax, [rax+0F8h]
0x180011a6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011a71  jmp     short loc_180011A7F
0x180011a73  mov     rax, [rax+0A8h]
0x180011a7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011a7f  cmp     eax, 800702E4h
0x180011a84  jnz     short loc_180011AE6
0x180011a86  mov     rax, cs:?_atltmpPchNil@WTL@@3PEBGEB; ushort const * const WTL::_atltmpPchNil
0x180011a8d  mov     [rsp+28h+lpCaption], rax
0x180011a92  mov     [rsp+28h+lpText], rax
0x180011a97  mov     edx, 4E21h; uID
0x180011a9c  lea     rcx, [rsp+28h+lpCaption]; this
0x180011aa1  call    ?LoadStringW@CString@WTL@@QEAAHI@Z; WTL::CString::LoadStringW(uint)
0x180011aa6  mov     edx, 4E6Dh; uID
0x180011aab  lea     rcx, [rsp+28h+lpText]; this
0x180011ab0  call    ?LoadStringW@CString@WTL@@QEAAHI@Z; WTL::CString::LoadStringW(uint)
0x180011ab5  mov     r9d, 30h ; '0'; uType
0x180011abb  mov     r8, [rsp+28h+lpCaption]; lpCaption
0x180011ac0  mov     rdx, [rsp+28h+lpText]; lpText
0x180011ac5  mov     rcx, [rbx]; hWnd
0x180011ac8  call    cs:__imp_MessageBoxW
0x180011ace  nop
0x180011acf  lea     rcx, [rsp+28h+lpText]; this
0x180011ad4  call    ??1CString@WTL@@QEAA@XZ; WTL::CString::~CString(void)
0x180011ad9  nop
0x180011ada  lea     rcx, [rsp+28h+lpCaption]; this
0x180011adf  call    ??1CString@WTL@@QEAA@XZ; WTL::CString::~CString(void)
0x180011ae4  jmp     short loc_180011AFE
0x180011ae6  cmp     eax, 800704C7h
0x180011aeb  jz      short loc_180011AFE
0x180011aed  not     eax
0x180011aef  mov     edx, eax
0x180011af1  shr     rdx, 1Fh; nResult
0x180011af5  mov     rcx, [rbx]; hDlg
0x180011af8  call    cs:__imp_EndDialog
0x180011afe  xor     eax, eax
0x180011b00  add     rsp, 20h
0x180011b04  pop     rbx
0x180011b05  retn
```
