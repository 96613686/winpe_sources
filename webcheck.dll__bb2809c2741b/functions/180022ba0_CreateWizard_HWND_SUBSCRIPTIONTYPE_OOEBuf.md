# CreateWizard(HWND__ *,SUBSCRIPTIONTYPE,OOEBuf *)

- ea: `0x180022ba0`
- end: `0x180022dc0`
- name: `?CreateWizard@@YAJPEAUHWND__@@W4SUBSCRIPTIONTYPE@@PEAUOOEBuf@@@Z`
- size: `544`
- prototype: `__int64 __fastcall(HWND, enum SUBSCRIPTIONTYPE, struct OOEBuf *)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1800170c8`

## callees

- `0x180018934`
- `0x18001be14`
- `0x18001bf60`
- `0x180022ba0`
- `0x180028018`
- `0x1800280fc`
- `0x18002924e`
- `0x180029280`

## import_xrefs

- `IEFRAME!__imp_SHRestricted2W` at `0x180022c69`
- `IEFRAME!__imp_SHRestricted2W` at `0x180022c69`

## string_xrefs

- `0x180022c16`: `ShowWelcome`
- `0x180022d61`: `ShowWelcome`

## pseudocode

```c
__int64 __fastcall CreateWizard(HWND a1, unsigned int a2, struct OOEBuf *a3)
{
  int v6; // ebx
  const unsigned __int16 *v7; // rdx
  HKEY v8; // rcx
  unsigned int v9; // ecx
  int v10; // edi
  HPROPSHEETPAGE v11; // rax
  __int64 v12; // rax
  const unsigned __int16 *v13; // rdx
  HKEY v14; // rcx
  __int64 v15; // rdi
  BYTE v17[16]; // [rsp+30h] [rbp-D0h] BYREF
  _DWORD v18[2]; // [rsp+40h] [rbp-C0h] BYREF
  HWND v19; // [rsp+48h] [rbp-B8h]
  HINSTANCE v20; // [rsp+50h] [rbp-B0h]
  __int64 v21; // [rsp+60h] [rbp-A0h]
  unsigned int v22; // [rsp+68h] [rbp-98h]
  int v23; // [rsp+70h] [rbp-90h]
  HPROPSHEETPAGE *v24; // [rsp+78h] [rbp-88h]
  PROPSHEETPAGEW_V4 constPropSheetPagePointer; // [rsp+A0h] [rbp-60h] BYREF
  _QWORD v26[2]; // [rsp+110h] [rbp+10h] BYREF
  __int128 v27; // [rsp+120h] [rbp+20h]
  __int128 v28; // [rsp+130h] [rbp+30h]
  HPROPSHEETPAGE v29[2]; // [rsp+140h] [rbp+40h] BYREF
  __int128 v30; // [rsp+150h] [rbp+50h]
  __int64 v31; // [rsp+160h] [rbp+60h]

  v6 = 0;
  v31 = 0;
  *(_OWORD *)v29 = 0;
  v30 = 0;
  memset_0(&constPropSheetPagePointer, 0, sizeof(constPropSheetPagePointer));
  memset_0(v18, 0, 0x60u);
  *(_DWORD *)v17 = 1;
  v26[0] = a2;
  v27 = 0;
  v26[1] = a3;
  LODWORD(v27) = 0;
  v28 = 0;
  ReadRegValue(v8, v7, L"ShowWelcome", v17, 4u);
  *(_QWORD *)((char *)&v27 + 4) = *(unsigned int *)v17;
  if ( !*(_DWORD *)v17 )
    LODWORD(v27) = v27 | 1;
  if ( ((a2 - 2) & 0xFFFFFFFD) == 0 )
    LODWORD(v27) = v27 | 2;
  if ( *((_DWORD *)a3 + 11) && !*((_DWORD *)a3 + 15) || (unsigned int)SHRestricted2W(1342177305, 0, 0) )
    LODWORD(v27) = v27 | 4;
  v9 = 0;
  v20 = g_hinstMUI;
  constPropSheetPagePointer.hInstance = g_hinstMUI;
  v18[0] = 96;
  constPropSheetPagePointer.lParam = (LPARAM)v26;
  v10 = 0;
  v18[1] = 32;
  v19 = a1;
  v21 = 0;
  v22 = 0;
  v23 = 0;
  v24 = v29;
  *(_QWORD *)&constPropSheetPagePointer.dwSize = 104;
  constPropSheetPagePointer.hIcon = 0;
  constPropSheetPagePointer.pszTitle = 0;
  while ( v6 >= 0 )
  {
    if ( (qword_18002BD20[3 * v10 + 2] & (unsigned int)v27) != 0 )
    {
      v6 = 1;
    }
    else
    {
      constPropSheetPagePointer.pszTemplate = (LPCWSTR)LOWORD(qword_18002BD20[3 * v10]);
      constPropSheetPagePointer.pfnDlgProc = (DLGPROC)qword_18002BD20[3 * v10 + 1];
      v11 = CreatePropertySheetPageW(&constPropSheetPagePointer);
      if ( v11 )
      {
        v6 = 0;
        v24[v22] = v11;
        v9 = ++v22;
      }
      else
      {
        v9 = v22;
        v6 = -2147024882;
      }
    }
    if ( (unsigned int)++v10 >= 5 )
    {
      if ( v6 >= 0 )
      {
        v12 = PropertySheet(v18);
        if ( v12 <= 0 )
        {
          return (unsigned int)((v12 != 0) - 2147467260);
        }
        else
        {
          *(_DWORD *)v17 = DWORD1(v27);
          WriteRegValue(v14, v13, L"ShowWelcome", v17, 4u, 4u);
          return 0;
        }
      }
      break;
    }
  }
  v15 = 0;
  if ( v9 )
  {
    do
    {
      DestroyPropertySheetPage(v29[v15]);
      v15 = (unsigned int)(v15 + 1);
    }
    while ( (unsigned int)v15 < v22 );
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180022ba0  push    rbp
0x180022ba2  push    rbx
0x180022ba3  push    rsi
0x180022ba4  push    rdi
0x180022ba5  push    r14
0x180022ba7  lea     rbp, [rsp-70h]
0x180022bac  sub     rsp, 170h
0x180022bb3  mov     rax, cs:__security_cookie
0x180022bba  xor     rax, rsp
0x180022bbd  mov     [rbp+90h+var_28], rax
0x180022bc1  xorps   xmm0, xmm0
0x180022bc4  mov     rdi, r8
0x180022bc7  mov     esi, edx
0x180022bc9  mov     r14, rcx
0x180022bcc  xor     eax, eax
0x180022bce  lea     rcx, [rbp+90h+constPropSheetPagePointer]; void *
0x180022bd2  xor     ebx, ebx
0x180022bd4  mov     [rbp+90h+var_30], rax
0x180022bd8  xor     edx, edx; Val
0x180022bda  movups  xmmword ptr [rbp+90h+var_50], xmm0
0x180022bde  lea     r8d, [rbx+68h]; Size
0x180022be2  movups  [rbp+90h+var_40], xmm0
0x180022be6  call    memset_0
0x180022beb  xor     edx, edx; Val
0x180022bed  lea     r8d, [rbx+60h]; Size
0x180022bf1  lea     rcx, [rsp+190h+var_150]; void *
0x180022bf6  call    memset_0
0x180022bfb  xorps   xmm0, xmm0
0x180022bfe  mov     dword ptr [rsp+190h+var_160], 1
0x180022c06  movups  [rbp+90h+var_80], xmm0
0x180022c0a  lea     r9, [rsp+190h+var_160]; void *
0x180022c0f  mov     dword ptr [rbp+90h+var_80], esi
0x180022c12  movups  [rbp+90h+var_70], xmm0
0x180022c16  lea     r8, aShowwelcome; "ShowWelcome"
0x180022c1d  mov     qword ptr [rbp+90h+var_80+8], rdi
0x180022c21  mov     dword ptr [rbp+90h+var_70], ebx
0x180022c24  movups  [rbp+90h+var_60], xmm0
0x180022c28  mov     [rsp+190h+var_170], 4; unsigned int
0x180022c30  call    ?ReadRegValue@@YAHPEAUHKEY__@@PEBG1PEAXK@Z; ReadRegValue(HKEY__ *,ushort const *,ushort const *,void *,ulong)
0x180022c35  mov     eax, dword ptr [rsp+190h+var_160]
0x180022c39  mov     dword ptr [rbp+90h+var_70+4], eax
0x180022c3c  mov     dword ptr [rbp+90h+var_70+8], ebx
0x180022c3f  test    eax, eax
0x180022c41  jnz     short loc_180022C47
0x180022c43  or      dword ptr [rbp+90h+var_70], 1
0x180022c47  lea     eax, [rsi-2]
0x180022c4a  test    eax, 0FFFFFFFDh
0x180022c4f  jnz     short loc_180022C55
0x180022c51  or      dword ptr [rbp+90h+var_70], 2
0x180022c55  cmp     [rdi+2Ch], ebx
0x180022c58  jz      short loc_180022C5F
0x180022c5a  cmp     [rdi+3Ch], ebx
0x180022c5d  jz      short loc_180022C73
0x180022c5f  xor     r8d, r8d
0x180022c62  xor     edx, edx
0x180022c64  mov     ecx, 50000019h
0x180022c69  call    cs:__imp_SHRestricted2W
0x180022c6f  test    eax, eax
0x180022c71  jz      short loc_180022C77
0x180022c73  or      dword ptr [rbp+90h+var_70], 4
0x180022c77  mov     rax, cs:g_hinstMUI
0x180022c7e  lea     rdx, [rbp+90h+var_50]
0x180022c82  xor     ecx, ecx
0x180022c84  mov     [rsp+190h+var_140], rax
0x180022c89  mov     [rbp+90h+constPropSheetPagePointer.hInstance], rax
0x180022c8d  lea     rsi, qword_18002BD20
0x180022c94  lea     rax, [rbp+90h+var_80]
0x180022c98  mov     [rsp+190h+var_150], 60h ; '`'
0x180022ca0  mov     [rbp+90h+constPropSheetPagePointer.lParam], rax
0x180022ca4  xor     edi, edi
0x180022ca6  mov     [rsp+190h+var_14C], 20h ; ' '
0x180022cae  mov     [rsp+190h+var_148], r14
0x180022cb3  mov     [rsp+190h+var_130], rbx
0x180022cb8  mov     [rsp+190h+var_128], ecx
0x180022cbc  mov     [rsp+190h+var_120], ecx
0x180022cc0  mov     [rsp+190h+var_118], rdx
0x180022cc5  mov     qword ptr [rbp+90h+constPropSheetPagePointer.dwSize], 68h ; 'h'
0x180022ccd  mov     qword ptr [rbp+90h+constPropSheetPagePointer.18h], rcx
0x180022cd1  mov     [rbp+90h+constPropSheetPagePointer.pszTitle], rcx
0x180022cd5  test    ebx, ebx
0x180022cd7  js      loc_180022D8C
0x180022cdd  movsxd  rax, edi
0x180022ce0  lea     rdx, [rax+rax*2]
0x180022ce4  mov     eax, [rsi+rdx*8+10h]
0x180022ce8  test    dword ptr [rbp+90h+var_70], eax
0x180022ceb  jnz     short loc_180022D32
0x180022ced  movzx   eax, word ptr [rsi+rdx*8]
0x180022cf1  lea     rcx, [rbp+90h+constPropSheetPagePointer]; constPropSheetPagePointer
0x180022cf5  mov     qword ptr [rbp+90h+constPropSheetPagePointer.10h], rax
0x180022cf9  mov     rax, [rsi+rdx*8+8]
0x180022cfe  mov     [rbp+90h+constPropSheetPagePointer.pfnDlgProc], rax
0x180022d02  call    CreatePropertySheetPageW
0x180022d07  test    rax, rax
0x180022d0a  jz      short loc_180022D27
0x180022d0c  mov     edx, [rsp+190h+var_128]
0x180022d10  xor     ebx, ebx
0x180022d12  mov     rcx, [rsp+190h+var_118]
0x180022d17  mov     [rcx+rdx*8], rax
0x180022d1b  mov     ecx, [rsp+190h+var_128]
0x180022d1f  inc     ecx
0x180022d21  mov     [rsp+190h+var_128], ecx
0x180022d25  jmp     short loc_180022D37
0x180022d27  mov     ecx, [rsp+190h+var_128]
0x180022d2b  mov     ebx, 8007000Eh
0x180022d30  jmp     short loc_180022D37
0x180022d32  mov     ebx, 1
0x180022d37  inc     edi
0x180022d39  cmp     edi, 5
0x180022d3c  jb      short loc_180022CD5
0x180022d3e  test    ebx, ebx
0x180022d40  js      short loc_180022D8C
0x180022d42  lea     rcx, [rsp+190h+var_150]
0x180022d47  call    PropertySheet
0x180022d4c  test    rax, rax
0x180022d4f  jle     short loc_180022D7D
0x180022d51  mov     eax, dword ptr [rbp+90h+var_70+4]
0x180022d54  lea     r9, [rsp+190h+var_160]; void *
0x180022d59  mov     [rsp+190h+var_168], 4; unsigned int
0x180022d61  lea     r8, aShowwelcome; "ShowWelcome"
0x180022d68  mov     dword ptr [rsp+190h+var_160], eax
0x180022d6c  mov     [rsp+190h+var_170], 4; unsigned int
0x180022d74  call    ?WriteRegValue@@YAHPEAUHKEY__@@PEBG1PEAXKK@Z; WriteRegValue(HKEY__ *,ushort const *,ushort const *,void *,ulong,ulong)
0x180022d79  xor     ebx, ebx
0x180022d7b  jmp     short loc_180022DA4
0x180022d7d  neg     rax
0x180022d80  sbb     ebx, ebx
0x180022d82  neg     ebx
0x180022d84  add     ebx, 80004004h
0x180022d8a  jmp     short loc_180022DA4
0x180022d8c  xor     edi, edi
0x180022d8e  test    ecx, ecx
0x180022d90  jz      short loc_180022DA4
0x180022d92  mov     rcx, [rbp+rdi*8+90h+var_50]; HPROPSHEETPAGE
0x180022d97  call    DestroyPropertySheetPage
0x180022d9c  inc     edi
0x180022d9e  cmp     edi, [rsp+190h+var_128]
0x180022da2  jb      short loc_180022D92
0x180022da4  mov     eax, ebx
0x180022da6  mov     rcx, [rbp+90h+var_28]
0x180022daa  xor     rcx, rsp; StackCookie
0x180022dad  call    __security_check_cookie
0x180022db2  add     rsp, 170h
0x180022db9  pop     r14
0x180022dbb  pop     rdi
0x180022dbc  pop     rsi
0x180022dbd  pop     rbx
0x180022dbe  pop     rbp
0x180022dbf  retn
```
