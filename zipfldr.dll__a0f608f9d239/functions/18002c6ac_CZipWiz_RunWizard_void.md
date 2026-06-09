# CZipWiz::RunWizard(void)

- ea: `0x18002c6ac`
- end: `0x18002c8e2`
- name: `?RunWizard@CZipWiz@@QEAAHXZ`
- size: `566`
- prototype: `__int64 __fastcall(CZipWiz *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, loader_planting`

## callers

- `0x18002a2e0`

## callees

- `0x18002c6ac`
- `0x180031e94`
- `0x180036f50`
- `0x180037958`
- `0x1800421a4`
- `0x1800423c4`
- `0x180042628`
- `0x180042d08`
- `0x18006daa0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002c720`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002c720`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002c711`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002c711`
- `USER32!SetThreadDpiAwarenessContext` at `0x18002c6dd`
- `USER32!SetThreadDpiAwarenessContext` at `0x18002c8ba`
- `USER32!SetThreadDpiAwarenessContext` at `0x18002c6dd`
- `USER32!SetThreadDpiAwarenessContext` at `0x18002c8ba`

## pseudocode

```c
__int64 __fastcall CZipWiz::RunWizard(WCHAR *this)
{
  HANDLE FileW; // rax
  UINT v3; // edi
  signed int i; // esi
  __int64 v5; // r12
  __int64 v6; // rbx
  const WCHAR *pszTemplate; // r14
  HINSTANCE v8; // rbx
  unsigned int TextScaleFactor; // eax
  int v10; // eax
  struct _PROPSHEETHEADERW_V2 *v11; // rdx
  unsigned int v12; // eax
  __int64 v13; // r13
  unsigned __int16 *v14; // rcx
  unsigned int v15; // ebx
  __int64 v16; // rdx
  DWORD dwCreationDisposition; // [rsp+20h] [rbp-E0h]
  const WCHAR *v19; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v20; // [rsp+48h] [rbp-B8h]
  PROPSHEETPAGEW_V4 constPropSheetPagePointer; // [rsp+50h] [rbp-B0h] BYREF
  PROPSHEETHEADERW_V2 v22; // [rsp+C0h] [rbp-40h] BYREF
  _OWORD v23[2]; // [rsp+120h] [rbp+20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+198h] [rbp+98h]

  v20 = SetThreadDpiAwarenessContext(-2);
  FileW = CreateFileW(this + 6, 0x80000000, 1u, 0, 3u, 0, 0);
  if ( FileW == (HANDLE)-1LL )
  {
    v3 = 2;
  }
  else
  {
    CloseHandle(FileW);
    v3 = CZipWiz::_SourceHasFiles((CZipWiz *)this, this + 6) == 0;
  }
  memset(v23, 0, sizeof(v23));
  for ( i = 0; (unsigned int)i < 4; ++i )
  {
    constPropSheetPagePointer.dwSize = 104;
    memset_0(&constPropSheetPagePointer.dwFlags, 0, 0x64u);
    constPropSheetPagePointer.hInstance = g_hmodThisDll;
    v5 = i;
    constPropSheetPagePointer.lParam = (LPARAM)this;
    v6 = 4LL * i;
    constPropSheetPagePointer.dwFlags = 4096;
    constPropSheetPagePointer.pszTemplate = (LPCWSTR)qword_180074450[v6];
    if ( (unsigned int)anonymous_namespace_::GetTextScaleFactor() <= 0x7D )
    {
      pszTemplate = constPropSheetPagePointer.pszTemplate;
    }
    else
    {
      pszTemplate = (const WCHAR *)qword_180074450[v6 + 3];
      constPropSheetPagePointer.pszTemplate = pszTemplate;
    }
    constPropSheetPagePointer.pfnDlgProc = (DLGPROC)*(&off_180074458 + 4 * i);
    v8 = g_hmodThisDll;
    constPropSheetPagePointer.pszHeaderTitle = (LPCWSTR)qword_180074460[4 * i];
    v19 = 0;
    TextScaleFactor = anonymous_namespace_::GetTextScaleFactor();
    v10 = anonymous_namespace_::ScaleDialogTemplate(v8, pszTemplate, TextScaleFactor, &v19);
    if ( v10 >= 0 )
    {
      constPropSheetPagePointer.dwFlags |= 1u;
      constPropSheetPagePointer.pszTemplate = v19;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA2,
        (unsigned int)"onecore\\internal\\shell\\inc\\private\\ShCore-Win32DialogResourceHelpers.h",
        (const char *)(unsigned int)v10,
        dwCreationDisposition);
    }
    *((_QWORD *)v23 + v5) = CreatePropertySheetPageW(&constPropSheetPagePointer);
  }
  v22.dwSize = 96;
  memset_0(&v22.dwFlags, 0, 0x5Cu);
  v22.hInstance = g_hmodThisDll;
  v22.ppsp = (LPCPROPSHEETPAGEW)v23;
  v22.dwFlags = 16388;
  v22.nPages = 4;
  v22.nStartPage = v3;
  v22.pszCaption = (LPCWSTR)10135;
  v22.hIcon = (HICON)123;
  v12 = AccessibilityHelpers::DoPropertySheetWithScaling(&v22, v11);
  v13 = v20;
  v14 = &word_18008BAB8;
  v15 = v12;
  v16 = 130;
  do
  {
    *(_BYTE *)v14 = 0;
    v14 = (unsigned __int16 *)((char *)v14 + 1);
    --v16;
  }
  while ( v16 );
  SetThreadDpiAwarenessContext(v13);
  return v15;
}

```

## disassembly

```asm
0x18002c6ac  push    rbp
0x18002c6ae  push    rbx
0x18002c6af  push    rsi
0x18002c6b0  push    rdi
0x18002c6b1  push    r12
0x18002c6b3  push    r13
0x18002c6b5  push    r14
0x18002c6b7  push    r15
0x18002c6b9  lea     rbp, [rsp-58h]
0x18002c6be  sub     rsp, 158h
0x18002c6c5  mov     rax, cs:__security_cookie
0x18002c6cc  xor     rax, rsp
0x18002c6cf  mov     [rbp+90h+var_50], rax
0x18002c6d3  mov     r15, rcx
0x18002c6d6  mov     rcx, 0FFFFFFFFFFFFFFFEh
0x18002c6dd  call    cs:__imp_SetThreadDpiAwarenessContext
0x18002c6e3  xor     r9d, r9d; lpSecurityAttributes
0x18002c6e6  mov     [rsp+190h+hTemplateFile], 0; hTemplateFile
0x18002c6ef  mov     [rsp+190h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x18002c6f7  lea     rcx, [r15+0Ch]; lpFileName
0x18002c6fb  mov     edx, 80000000h; dwDesiredAccess
0x18002c700  mov     [rsp+190h+var_148], rax
0x18002c705  mov     [rsp+190h+dwCreationDisposition], 3; int
0x18002c70d  lea     r8d, [r9+1]; dwShareMode
0x18002c711  call    cs:__imp_CreateFileW
0x18002c717  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002c71b  jz      short loc_18002C73D
0x18002c71d  mov     rcx, rax; hObject
0x18002c720  call    cs:__imp_CloseHandle
0x18002c726  lea     rdx, [r15+0Ch]; unsigned __int16 *
0x18002c72a  mov     rcx, r15; this
0x18002c72d  xor     edi, edi
0x18002c72f  call    ?_SourceHasFiles@CZipWiz@@AEAAHPEBG@Z; CZipWiz::_SourceHasFiles(ushort const *)
0x18002c734  test    eax, eax
0x18002c736  jnz     short loc_18002C742
0x18002c738  lea     edi, [rax+1]
0x18002c73b  jmp     short loc_18002C742
0x18002c73d  mov     edi, 2
0x18002c742  xorps   xmm0, xmm0
0x18002c745  lea     r13, qword_180074450
0x18002c74c  movups  [rbp+90h+var_70], xmm0
0x18002c750  xor     esi, esi
0x18002c752  movups  [rbp+90h+var_60], xmm0
0x18002c756  xor     edx, edx; Val
0x18002c758  mov     [rsp+190h+constPropSheetPagePointer.dwSize], 68h ; 'h'
0x18002c760  lea     rcx, [rsp+190h+constPropSheetPagePointer.dwFlags]; void *
0x18002c765  lea     r8d, [rdx+64h]; Size
0x18002c769  call    memset_0
0x18002c76e  mov     rax, cs:g_hmodThisDll
0x18002c775  mov     [rsp+190h+constPropSheetPagePointer.hInstance], rax
0x18002c77a  movsxd  r12, esi
0x18002c77d  mov     rbx, r12
0x18002c780  mov     [rbp+90h+constPropSheetPagePointer.lParam], r15
0x18002c784  shl     rbx, 5
0x18002c788  mov     [rsp+190h+constPropSheetPagePointer.dwFlags], 1000h
0x18002c790  mov     rax, [rbx+r13]
0x18002c794  mov     qword ptr [rsp+190h+constPropSheetPagePointer.10h], rax
0x18002c799  call    _anonymous_namespace___GetTextScaleFactor
0x18002c79e  cmp     eax, 7Dh ; '}'
0x18002c7a1  lea     rcx, qword_180074460
0x18002c7a8  lea     rax, off_180074458
0x18002c7af  jbe     short loc_18002C7BD
0x18002c7b1  mov     r14, [rbx+r13+18h]
0x18002c7b6  mov     qword ptr [rsp+190h+constPropSheetPagePointer.10h], r14
0x18002c7bb  jmp     short loc_18002C7C2
0x18002c7bd  mov     r14, qword ptr [rsp+190h+constPropSheetPagePointer.10h]
0x18002c7c2  mov     rax, [rax+rbx]
0x18002c7c6  mov     [rsp+190h+constPropSheetPagePointer.pfnDlgProc], rax
0x18002c7cb  mov     rax, [rcx+rbx]
0x18002c7cf  mov     rbx, cs:g_hmodThisDll
0x18002c7d6  mov     [rbp+90h+constPropSheetPagePointer.pszHeaderTitle], rax
0x18002c7da  mov     [rsp+190h+var_150], 0
0x18002c7e3  call    _anonymous_namespace___GetTextScaleFactor
0x18002c7e8  mov     r8d, eax
0x18002c7eb  lea     r9, [rsp+190h+var_150]
0x18002c7f0  mov     rdx, r14
0x18002c7f3  mov     rcx, rbx
0x18002c7f6  call    _anonymous_namespace___ScaleDialogTemplate
0x18002c7fb  test    eax, eax
0x18002c7fd  jns     short loc_18002C81C
0x18002c7ff  mov     rcx, [rbp+98h]; this
0x18002c806  lea     r8, aOnecoreInterna_5; "onecore\\internal\\shell\\inc\\private"...
0x18002c80d  mov     r9d, eax; char *
0x18002c810  mov     edx, 0A2h; void *
0x18002c815  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c81a  jmp     short loc_18002C82B
0x18002c81c  mov     rax, [rsp+190h+var_150]
0x18002c821  or      [rsp+190h+constPropSheetPagePointer.dwFlags], 1
0x18002c826  mov     qword ptr [rsp+190h+constPropSheetPagePointer.10h], rax
0x18002c82b  lea     rcx, [rsp+190h+constPropSheetPagePointer]; constPropSheetPagePointer
0x18002c830  call    CreatePropertySheetPageW
0x18002c835  inc     esi
0x18002c837  mov     qword ptr [rbp+r12*8+90h+var_70], rax
0x18002c83c  cmp     esi, 4
0x18002c83f  jb      loc_18002C756
0x18002c845  xor     edx, edx; Val
0x18002c847  mov     [rbp+90h+var_D0.dwSize], 60h ; '`'
0x18002c84e  lea     rcx, [rbp+90h+var_D0.dwFlags]; void *
0x18002c852  lea     r8d, [rdx+5Ch]; Size
0x18002c856  call    memset_0
0x18002c85b  mov     rax, cs:g_hmodThisDll
0x18002c862  lea     rcx, [rbp+90h+var_D0]; this
0x18002c866  mov     [rbp+90h+var_D0.hInstance], rax
0x18002c86a  lea     rax, [rbp+90h+var_70]
0x18002c86e  mov     qword ptr [rbp+90h+var_D0.38h], rax
0x18002c872  mov     [rbp+90h+var_D0.dwFlags], 4004h
0x18002c879  mov     [rbp+90h+var_D0.nPages], 4
0x18002c880  mov     dword ptr [rbp+90h+var_D0.30h], edi
0x18002c883  mov     [rbp+90h+var_D0.pszCaption], 2797h
0x18002c88b  mov     qword ptr [rbp+90h+var_D0.18h], 7Bh ; '{'
0x18002c893  call    ?DoPropertySheetWithScaling@AccessibilityHelpers@@YAHPEAU_PROPSHEETHEADERW_V2@@@Z; AccessibilityHelpers::DoPropertySheetWithScaling(_PROPSHEETHEADERW_V2 *)
0x18002c898  mov     r13, [rsp+190h+var_148]
0x18002c89d  lea     rcx, word_18008BAB8
0x18002c8a4  mov     ebx, eax
0x18002c8a6  mov     edx, 82h
0x18002c8ab  mov     byte ptr [rcx], 0
0x18002c8ae  inc     rcx
0x18002c8b1  sub     rdx, 1
0x18002c8b5  jnz     short loc_18002C8AB
0x18002c8b7  mov     rcx, r13
0x18002c8ba  call    cs:__imp_SetThreadDpiAwarenessContext
0x18002c8c0  mov     eax, ebx
0x18002c8c2  mov     rcx, [rbp+90h+var_50]
0x18002c8c6  xor     rcx, rsp; StackCookie
0x18002c8c9  call    __security_check_cookie
0x18002c8ce  add     rsp, 158h
0x18002c8d5  pop     r15
0x18002c8d7  pop     r14
0x18002c8d9  pop     r13
0x18002c8db  pop     r12
0x18002c8dd  pop     rdi
0x18002c8de  pop     rsi
0x18002c8df  pop     rbx
0x18002c8e0  pop     rbp
0x18002c8e1  retn
```
