# CRenameProfileDlg::OnOk(ushort,ushort,HWND__ *,int &)

- ea: `0x180011c5c`
- end: `0x180011d29`
- name: `?OnOk@CRenameProfileDlg@@QEAA_JGGPEAUHWND__@@AEAH@Z`
- size: `205`
- prototype: `__int64 __fastcall(CRenameProfileDlg *__hidden this, unsigned __int16, unsigned __int16, HWND, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180011d30`

## callees

- `0x1800036ac`
- `0x180008484`
- `0x180011c5c`
- `0x180030010`

## import_xrefs

- `USER32!MessageBoxW` at `0x180011ceb`
- `USER32!MessageBoxW` at `0x180011ceb`
- `USER32!EndDialog` at `0x180011d1b`
- `USER32!EndDialog` at `0x180011d1b`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CRenameProfileDlg::OnOk(CRenameProfileDlg *this, __int64 a2, __int64 a3, const WCHAR *a4)
{
  __int64 v4; // rdx
  HWND *v5; // rbx
  __int64 v6; // r8
  __int64 v7; // rax
  int v8; // eax
  LPCWSTR lpCaption; // [rsp+40h] [rbp+8h] BYREF
  LPCWSTR lpText; // [rsp+58h] [rbp+20h] BYREF

  lpText = a4;
  v4 = *((_QWORD *)this + 9);
  v5 = (HWND *)((char *)this + 8);
  v6 = *((_QWORD *)this + 10);
  v7 = *(_QWORD *)CSingletonPtr<CWlanProfileStore>::s_pInstance;
  if ( *(_BYTE *)(v4 + 83) )
    v8 = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(v7 + 176))(
           CSingletonPtr<CWlanProfileStore>::s_pInstance,
           v4,
           v6);
  else
    v8 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, HWND))(v7 + 256))(
           CSingletonPtr<CWlanProfileStore>::s_pInstance,
           v4,
           v6,
           *v5);
  if ( v8 == -2147024156 )
  {
    lpCaption = WTL::_atltmpPchNil;
    lpText = WTL::_atltmpPchNil;
    WTL::CString::LoadStringW((WTL::CString *)&lpCaption, 0x4E21u);
    WTL::CString::LoadStringW((WTL::CString *)&lpText, 0x4E6Du);
    MessageBoxW(*v5, lpText, lpCaption, 0x30u);
    WTL::CString::~CString((WTL::CString *)&lpText);
    WTL::CString::~CString((WTL::CString *)&lpCaption);
  }
  else if ( v8 != -2147023673 )
  {
    EndDialog(*v5, (unsigned __int64)(unsigned int)~v8 >> 31);
  }
  return 0;
}

```

## disassembly

```asm
0x180011c5c  mov     [rsp+lpText], r9
0x180011c61  push    rbx
0x180011c62  sub     rsp, 30h
0x180011c66  mov     r8, rcx
0x180011c69  mov     rdx, [rcx+48h]
0x180011c6d  lea     rbx, [rcx+8]
0x180011c71  mov     rcx, cs:?s_pInstance@?$CSingletonPtr@VCWlanProfileStore@@@@0PEAVCWlanProfileStore@@EA; CWlanProfileStore * CSingletonPtr<CWlanProfileStore>::s_pInstance
0x180011c78  mov     r8, [r8+50h]
0x180011c7c  mov     rax, [rcx]
0x180011c7f  cmp     byte ptr [rdx+53h], 0
0x180011c83  jnz     short loc_180011C96
0x180011c85  mov     r9, [rbx]
0x180011c88  mov     rax, [rax+100h]
0x180011c8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011c94  jmp     short loc_180011CA2
0x180011c96  mov     rax, [rax+0B0h]
0x180011c9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011ca2  cmp     eax, 800702E4h
0x180011ca7  jnz     short loc_180011D09
0x180011ca9  mov     rax, cs:?_atltmpPchNil@WTL@@3PEBGEB; ushort const * const WTL::_atltmpPchNil
0x180011cb0  mov     [rsp+38h+lpCaption], rax
0x180011cb5  mov     [rsp+38h+lpText], rax
0x180011cba  mov     edx, 4E21h; uID
0x180011cbf  lea     rcx, [rsp+38h+lpCaption]; this
0x180011cc4  call    ?LoadStringW@CString@WTL@@QEAAHI@Z; WTL::CString::LoadStringW(uint)
0x180011cc9  mov     edx, 4E6Dh; uID
0x180011cce  lea     rcx, [rsp+38h+lpText]; this
0x180011cd3  call    ?LoadStringW@CString@WTL@@QEAAHI@Z; WTL::CString::LoadStringW(uint)
0x180011cd8  mov     r9d, 30h ; '0'; uType
0x180011cde  mov     r8, [rsp+38h+lpCaption]; lpCaption
0x180011ce3  mov     rdx, [rsp+38h+lpText]; lpText
0x180011ce8  mov     rcx, [rbx]; hWnd
0x180011ceb  call    cs:__imp_MessageBoxW
0x180011cf1  nop
0x180011cf2  lea     rcx, [rsp+38h+lpText]; this
0x180011cf7  call    ??1CString@WTL@@QEAA@XZ; WTL::CString::~CString(void)
0x180011cfc  nop
0x180011cfd  lea     rcx, [rsp+38h+lpCaption]; this
0x180011d02  call    ??1CString@WTL@@QEAA@XZ; WTL::CString::~CString(void)
0x180011d07  jmp     short loc_180011D21
0x180011d09  cmp     eax, 800704C7h
0x180011d0e  jz      short loc_180011D21
0x180011d10  not     eax
0x180011d12  mov     edx, eax
0x180011d14  shr     rdx, 1Fh; nResult
0x180011d18  mov     rcx, [rbx]; hDlg
0x180011d1b  call    cs:__imp_EndDialog
0x180011d21  xor     eax, eax
0x180011d23  add     rsp, 30h
0x180011d27  pop     rbx
0x180011d28  retn
```
