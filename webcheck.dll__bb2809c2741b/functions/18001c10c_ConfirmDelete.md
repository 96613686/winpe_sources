# ConfirmDelete

- ea: `0x18001c10c`
- end: `0x18001c37e`
- name: `ConfirmDelete`
- size: `626`
- prototype: `__int64 __fastcall(HWND hWnd)`
- caller_count: `3`
- callee_count: `9`
- tags: ``

## callers

- `0x18000a7fc`
- `0x18000f2c0`
- `0x1800173f0`

## callees

- `0x180004adc`
- `0x18000e110`
- `0x18001be60`
- `0x18001c10c`
- `0x180027d70`
- `0x180027de0`
- `0x1800280ac`
- `0x18002924e`
- `0x180029280`

## import_xrefs

- `IEFRAME!__imp_SHRestricted2W` at `0x18001c166`
- `IEFRAME!__imp_SHRestricted2W` at `0x18001c190`
- `IEFRAME!__imp_SHRestricted2W` at `0x18001c166`
- `IEFRAME!__imp_SHRestricted2W` at `0x18001c190`
- `USER32!IsWindow` at `0x18001c1a1`
- `USER32!IsWindow` at `0x18001c1c7`
- `USER32!IsWindow` at `0x18001c1a1`
- `USER32!IsWindow` at `0x18001c1c7`
- `USER32!MessageBoxIndirectW` at `0x18001c325`
- `USER32!MessageBoxIndirectW` at `0x18001c325`
- `USER32!LoadStringW` at `0x18001c262`
- `USER32!LoadStringW` at `0x18001c291`
- `USER32!LoadStringW` at `0x18001c262`
- `USER32!LoadStringW` at `0x18001c291`

## pseudocode

```c
__int64 __fastcall ConfirmDelete(HWND hWnd, unsigned int a2, __int64 *a3)
{
  __int64 i; // rdi
  __int64 v7; // rcx
  __int64 v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // rax
  ULONG_PTR v12; // rcx
  __int64 v13; // rbx
  ULONG_PTR ulCookie; // [rsp+30h] [rbp-D0h] BYREF
  ULONG_PTR v16; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v17; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v18; // [rsp+50h] [rbp-B0h]
  MSGBOXPARAMSW mbp; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR Buffer[200]; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int16 v21[216]; // [rsp+240h] [rbp+140h] BYREF

  for ( i = 0; (unsigned int)i < a2; i = (unsigned int)(i + 1) )
  {
    v7 = a3[i];
    if ( !*(_DWORD *)(v7 + 56) || !(unsigned int)SHRestricted2W(1342177284, v7 + *(_QWORD *)(v7 + 200) + 8LL, 0) )
    {
      v8 = a3[i];
      if ( *(_DWORD *)(v8 + 52) || !(unsigned int)SHRestricted2W(1342177287, v8 + *(_QWORD *)(v8 + 200) + 8LL, 0) )
        continue;
    }
    if ( IsWindow(hWnd) )
      SGMessageBox(hWnd, 0x1FBCu, 0);
    return 0;
  }
  if ( IsWindow(hWnd) )
  {
    v18 = 0;
    v17 = 0;
    LODWORD(v17) = a2;
    if ( a2 == 1 )
    {
      v9 = *a3;
      *((_QWORD *)&v17 + 1) = *(_QWORD *)(*a3 + 208) + *a3 + 8;
      v18 = *(_QWORD *)(v9 + 200) + v9 + 8;
      ulCookie = 0;
      SHActivateContext(&ulCookie);
      v11 = DialogBoxParam(v10, 6007, hWnd, ConfirmDeleteDlgProc, &v17);
      v12 = ulCookie;
      v13 = v11;
    }
    else
    {
      LoadStringW(g_hinstMUI, 0x1F6Eu, Buffer, 200);
      StringCchPrintfW(v21, 0xD3u, Buffer, a2);
      LoadStringW(g_hinstMUI, 0x2031u, Buffer, 200);
      memset_0(&mbp, 0, sizeof(mbp));
      mbp.hInstance = g_hInst;
      mbp.lpszText = v21;
      mbp.lpszCaption = Buffer;
      mbp.cbSize = 80;
      mbp.hwndOwner = hWnd;
      mbp.dwStyle = 132;
      mbp.lpszIcon = (LPCWSTR)402;
      v16 = 0;
      SHActivateContext(&v16);
      ulCookie = 0;
      if ( (unsigned int)SHActivateContext(&ulCookie) )
      {
        if ( g_hActCtx != (HANDLE)-3LL )
          DelayLoadCC();
        LODWORD(v13) = MessageBoxIndirectW(&mbp);
        SHDeactivateContext(ulCookie);
      }
      else
      {
        LODWORD(v13) = 0;
      }
      v12 = v16;
      v13 = (int)v13;
    }
    if ( v12 )
      SHDeactivateContext(v12);
    if ( v13 != 6 )
      return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x18001c10c  mov     [rsp-8+arg_18], rbx
0x18001c111  push    rbp
0x18001c112  push    rsi
0x18001c113  push    rdi
0x18001c114  push    r14
0x18001c116  push    r15
0x18001c118  lea     rbp, [rsp-300h]
0x18001c120  sub     rsp, 400h
0x18001c127  mov     rax, cs:__security_cookie
0x18001c12e  xor     rax, rsp
0x18001c131  mov     [rbp+320h+var_30], rax
0x18001c138  mov     r14, r8
0x18001c13b  mov     esi, edx
0x18001c13d  mov     rbx, rcx
0x18001c140  xor     edi, edi
0x18001c142  cmp     edi, esi
0x18001c144  jnb     short loc_18001C1C4
0x18001c146  mov     rcx, [r14+rdi*8]
0x18001c14a  cmp     dword ptr [rcx+38h], 0
0x18001c14e  jz      short loc_18001C170
0x18001c150  mov     rdx, [rcx+0C8h]
0x18001c157  xor     r8d, r8d
0x18001c15a  add     rdx, 8
0x18001c15e  add     rdx, rcx
0x18001c161  mov     ecx, 50000004h
0x18001c166  call    cs:__imp_SHRestricted2W
0x18001c16c  test    eax, eax
0x18001c16e  jnz     short loc_18001C19E
0x18001c170  mov     rcx, [r14+rdi*8]
0x18001c174  cmp     dword ptr [rcx+34h], 0
0x18001c178  jnz     short loc_18001C19A
0x18001c17a  mov     rdx, [rcx+0C8h]
0x18001c181  xor     r8d, r8d
0x18001c184  add     rdx, 8
0x18001c188  add     rdx, rcx
0x18001c18b  mov     ecx, 50000007h
0x18001c190  call    cs:__imp_SHRestricted2W
0x18001c196  test    eax, eax
0x18001c198  jnz     short loc_18001C19E
0x18001c19a  inc     edi
0x18001c19c  jmp     short loc_18001C142
0x18001c19e  mov     rcx, rbx; hWnd
0x18001c1a1  call    cs:__imp_IsWindow
0x18001c1a7  test    eax, eax
0x18001c1a9  jz      loc_18001C34F
0x18001c1af  xor     r8d, r8d; unsigned int
0x18001c1b2  mov     edx, 1FBCh; unsigned int
0x18001c1b7  mov     rcx, rbx; hWnd
0x18001c1ba  call    ?SGMessageBox@@YAHPEAUHWND__@@II@Z; SGMessageBox(HWND__ *,uint,uint)
0x18001c1bf  jmp     loc_18001C34F
0x18001c1c4  mov     rcx, rbx; hWnd
0x18001c1c7  call    cs:__imp_IsWindow
0x18001c1cd  test    eax, eax
0x18001c1cf  jz      loc_18001C353
0x18001c1d5  xor     eax, eax
0x18001c1d7  xorps   xmm0, xmm0
0x18001c1da  mov     [rsp+420h+var_3D0], rax
0x18001c1df  movups  [rsp+420h+var_3E0], xmm0
0x18001c1e4  mov     dword ptr [rsp+420h+var_3E0], esi
0x18001c1e8  cmp     esi, 1
0x18001c1eb  jnz     short loc_18001C24A
0x18001c1ed  mov     rdx, [r14]
0x18001c1f0  lea     rcx, [rdx+8]
0x18001c1f4  add     rcx, [rdx+0D0h]
0x18001c1fb  mov     qword ptr [rsp+420h+var_3E0+8], rcx
0x18001c200  lea     rcx, [rdx+8]
0x18001c204  add     rcx, [rdx+0C8h]
0x18001c20b  mov     [rsp+420h+var_3D0], rcx
0x18001c210  lea     rcx, [rsp+420h+ulCookie]
0x18001c215  mov     [rsp+420h+ulCookie], rax
0x18001c21a  call    SHActivateContext
0x18001c21f  lea     rax, [rsp+420h+var_3E0]
0x18001c224  mov     r8, rbx
0x18001c227  lea     r9, ?ConfirmDeleteDlgProc@@YA_JPEAUHWND__@@I_K_J@Z; ConfirmDeleteDlgProc(HWND__ *,uint,unsigned __int64,__int64)
0x18001c22e  mov     [rsp+420h+var_400], rax
0x18001c233  mov     edx, 1777h
0x18001c238  call    DialogBoxParam
0x18001c23d  mov     rcx, [rsp+420h+ulCookie]
0x18001c242  mov     rbx, rax
0x18001c245  jmp     loc_18001C33F
0x18001c24a  mov     rcx, cs:g_hinstMUI; hInstance
0x18001c251  lea     r8, [rbp+320h+Buffer]; lpBuffer
0x18001c255  mov     edi, 0C8h
0x18001c25a  mov     edx, 1F6Eh; uID
0x18001c25f  mov     r9d, edi; cchBufferMax
0x18001c262  call    cs:__imp_LoadStringW
0x18001c268  mov     r9d, esi
0x18001c26b  lea     r8, [rbp+320h+Buffer]; unsigned __int16 *
0x18001c26f  lea     edx, [rdi+0Bh]; unsigned __int64
0x18001c272  lea     rcx, [rbp+320h+var_1E0]; unsigned __int16 *
0x18001c279  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001c27e  mov     rcx, cs:g_hinstMUI; hInstance
0x18001c285  lea     r8, [rbp+320h+Buffer]; lpBuffer
0x18001c289  mov     r9d, edi; cchBufferMax
0x18001c28c  mov     edx, 2031h; uID
0x18001c291  call    cs:__imp_LoadStringW
0x18001c297  mov     edi, 50h ; 'P'
0x18001c29c  lea     rcx, [rsp+420h+mbp]; void *
0x18001c2a1  mov     r8d, edi; Size
0x18001c2a4  xor     edx, edx; Val
0x18001c2a6  call    memset_0
0x18001c2ab  mov     rax, cs:g_hInst
0x18001c2b2  lea     rcx, [rsp+420h+var_3E8]
0x18001c2b7  mov     [rsp+420h+mbp.hInstance], rax
0x18001c2bc  lea     rax, [rbp+320h+var_1E0]
0x18001c2c3  mov     [rsp+420h+mbp.lpszText], rax
0x18001c2c8  lea     rax, [rbp+320h+Buffer]
0x18001c2cc  mov     [rbp+320h+mbp.lpszCaption], rax
0x18001c2d0  mov     [rsp+420h+mbp.cbSize], edi
0x18001c2d4  mov     [rsp+420h+mbp.hwndOwner], rbx
0x18001c2d9  mov     [rbp+320h+mbp.dwStyle], 84h
0x18001c2e0  mov     [rbp+320h+mbp.lpszIcon], 192h
0x18001c2e8  mov     [rsp+420h+var_3E8], 0
0x18001c2f1  call    SHActivateContext
0x18001c2f6  lea     rcx, [rsp+420h+ulCookie]
0x18001c2fb  mov     [rsp+420h+ulCookie], 0
0x18001c304  call    SHActivateContext
0x18001c309  test    eax, eax
0x18001c30b  jnz     short loc_18001C311
0x18001c30d  xor     ebx, ebx
0x18001c30f  jmp     short loc_18001C337
0x18001c311  cmp     cs:g_hActCtx, 0FFFFFFFFFFFFFFFDh
0x18001c319  jz      short loc_18001C320
0x18001c31b  call    DelayLoadCC
0x18001c320  lea     rcx, [rsp+420h+mbp]; lpmbp
0x18001c325  call    cs:__imp_MessageBoxIndirectW
0x18001c32b  mov     rcx, [rsp+420h+ulCookie]; ulCookie
0x18001c330  mov     ebx, eax
0x18001c332  call    SHDeactivateContext
0x18001c337  mov     rcx, [rsp+420h+var_3E8]; ulCookie
0x18001c33c  movsxd  rbx, ebx
0x18001c33f  test    rcx, rcx
0x18001c342  jz      short loc_18001C349
0x18001c344  call    SHDeactivateContext
0x18001c349  cmp     rbx, 6
0x18001c34d  jz      short loc_18001C353
0x18001c34f  xor     eax, eax
0x18001c351  jmp     short loc_18001C358
0x18001c353  mov     eax, 1
0x18001c358  mov     rcx, [rbp+320h+var_30]
0x18001c35f  xor     rcx, rsp; StackCookie
0x18001c362  call    __security_check_cookie
0x18001c367  mov     rbx, [rsp+420h+arg_18]
0x18001c36f  add     rsp, 400h
0x18001c376  pop     r15
0x18001c378  pop     r14
0x18001c37a  pop     rdi
0x18001c37b  pop     rsi
0x18001c37c  pop     rbp
0x18001c37d  retn
```
