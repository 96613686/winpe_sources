# xxxDlgDirListHelper(tagWND *,ushort *,uchar *,int,int,uint,int)

- ea: `0x180085ab4`
- end: `0x180085fa5`
- name: `?xxxDlgDirListHelper@@YAHPEAUtagWND@@PEAGPEAEHHIH@Z`
- size: `1265`
- prototype: `__int64 __usercall@<rax>(struct tagWND *@<rcx>, LPARAM lParam@<rdx>, unsigned __int8 *@<r8>, int@<r9d>, int nIDDlgItem, unsigned int, int)`
- caller_count: `4`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x180076540`
- `0x180076630`
- `0x180086310`
- `0x180086400`

## callees

- `0x18000cf20`
- `0x180020990`
- `0x18002aac8`
- `0x18003b4a0`
- `0x180043b70`
- `0x18004ba70`
- `0x18008560c`
- `0x180085ab4`
- `0x180096c24`
- `0x180096e00`

## import_xrefs

- `win32u!NtUserInvalidateRect` at `0x180085f76`
- `win32u!NtUserInvalidateRect` at `0x180085f76`
- `ntdll!RtlSetLastWin32Error` at `0x180085b16`
- `ntdll!RtlSetLastWin32Error` at `0x180085bd7`
- `ntdll!RtlSetLastWin32Error` at `0x180085b16`
- `ntdll!RtlSetLastWin32Error` at `0x180085bd7`
- `api-ms-win-core-string-l2-1-0!CharUpperW` at `0x180085c3e`
- `api-ms-win-core-string-l2-1-0!CharUpperW` at `0x180085c3e`
- `api-ms-win-core-string-l2-1-0!CharLowerW` at `0x180085de4`
- `api-ms-win-core-string-l2-1-0!CharLowerW` at `0x180085de4`
- `api-ms-win-core-processenvironment-l1-1-0!GetCurrentDirectoryW` at `0x180085dd4`
- `api-ms-win-core-processenvironment-l1-1-0!GetCurrentDirectoryW` at `0x180085dd4`
- `api-ms-win-core-processenvironment-l1-1-0!SetCurrentDirectoryW` at `0x180085c91`
- `api-ms-win-core-processenvironment-l1-1-0!SetCurrentDirectoryW` at `0x180085d4e`
- `api-ms-win-core-processenvironment-l1-1-0!SetCurrentDirectoryW` at `0x180085c91`
- `api-ms-win-core-processenvironment-l1-1-0!SetCurrentDirectoryW` at `0x180085d4e`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180085c07`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180085c07`

## pseudocode

```c
__int64 __fastcall xxxDlgDirListHelper(
        struct tagWND *a1,
        WCHAR *lParam,
        unsigned __int8 *a3,
        int a4,
        int nIDDlgItem,
        unsigned int a6,
        int a7)
{
  int v7; // r15d
  int v8; // edi
  unsigned __int8 *v9; // rbp
  ULONG v11; // ecx
  unsigned int v13; // esi
  struct tagWND *DlgItem; // rax
  __int64 v15; // r8
  HWND *v16; // rbx
  __int16 v17; // cx
  __int64 **v18; // rax
  int v19; // r12d
  int v20; // eax
  bool v21; // zf
  char near **v22; // rax
  int v23; // r10d
  WCHAR *v24; // rbx
  __int64 v25; // rdi
  int CharPosition; // eax
  int v27; // r11d
  unsigned int v28; // r8d
  BOOL v29; // eax
  int v30; // r12d
  int v31; // edx
  int v32; // eax
  WCHAR *v33; // rcx
  unsigned __int64 v34; // rax
  __int64 v35; // r8
  WCHAR *v36; // rdi
  WCHAR v37; // bp
  BOOL v38; // eax
  WCHAR *v39; // rdx
  WCHAR v40; // ax
  HWND *v41; // rbp
  const WCHAR *v42; // rax
  HWND v43; // rbx
  int v44; // ebp
  int v45; // edi
  UINT v46; // edi
  unsigned int v47; // eax
  unsigned __int16 v48; // si
  WPARAM v49; // r8
  LPARAM v50; // r14
  WPARAM v51; // r8
  unsigned __int8 *lParama; // [rsp+38h] [rbp-2B0h]
  __int64 v54; // [rsp+48h] [rbp-2A0h]
  unsigned __int8 *v55; // [rsp+50h] [rbp-298h] BYREF
  struct tagWND *v56; // [rsp+58h] [rbp-290h]
  struct tagWND *v57; // [rsp+60h] [rbp-288h]
  unsigned __int16 v58[7]; // [rsp+70h] [rbp-278h] BYREF
  WCHAR Buffer[265]; // [rsp+7Eh] [rbp-26Ah] BYREF

  v7 = nIDDlgItem;
  v8 = a4;
  v9 = a3;
  v57 = a1;
  lParama = a3;
  v55 = a3;
  if ( (a6 & 0xFFFF1FC8) != 0 )
  {
    v11 = 1004;
LABEL_3:
    RtlSetLastWin32Error(v11);
    return 0;
  }
  v13 = a6 & 0xFFFFEFFF;
  if ( (a6 & 0x1000) == 0 )
    v13 = a6;
  if ( !a1 && nIDDlgItem )
  {
    v11 = 87;
    goto LABEL_3;
  }
  v54 = 0;
  DlgItem = _GetDlgItem(a1, a4);
  v16 = (HWND *)DlgItem;
  v56 = DlgItem;
  if ( !DlgItem )
  {
    if ( !v8 )
      goto LABEL_22;
LABEL_21:
    RtlSetLastWin32Error(0x588u);
    v15 = 0;
    goto LABEL_22;
  }
  v17 = *((_WORD *)DlgItem + 21) & 0x2FFF;
  if ( (v17 != 678 || !a7) && (v17 != 674 || a7) && (v17 != 675 || !a7) )
    goto LABEL_21;
  v18 = (__int64 **)((char *)DlgItem + 296);
  if ( !a7 )
    v18 = (__int64 **)(*(_QWORD *)(**v18 + 72) + 296LL);
  v15 = **v18;
  v54 = v15;
LABEL_22:
  if ( nIDDlgItem < 0 && v15 )
    v7 = 0;
  v19 = v13 & 0x2000;
  if ( lParam )
  {
    v20 = lstrlenW(lParam);
    if ( !v20 )
    {
      v21 = v9 == (unsigned __int8 *)lParam;
      v22 = &achSlashStar;
      lParam = (WCHAR *)&awchSlashStar;
      if ( v21 )
        v22 = (char near **)v9;
      lParama = (unsigned __int8 *)v22;
      goto LABEL_69;
    }
    if ( v20 > 260 )
      return 0;
    CharUpperW(lParam);
    v23 = 0;
    v24 = (WCHAR *)&szSLASHSTARDOTSTAR + 1;
    if ( !*lParam )
      goto LABEL_63;
    v25 = -1;
    do
      ++v25;
    while ( lParam[v25] );
    CharPosition = FindCharPosition(lParam, 42);
    v28 = v27 + 21;
    if ( CharPosition == (_DWORD)v25 )
    {
      if ( (unsigned int)FindCharPosition(lParam, v28) == (_DWORD)v25 )
      {
        v29 = SetCurrentDirectoryW(lParam);
        v23 = 0;
        if ( v29 )
        {
LABEL_62:
          v8 = a4;
LABEL_63:
          if ( v19 && v9 != (unsigned __int8 *)lParam )
          {
            WCSToMBEx(0, v24, 0xFFFFFFFFLL, &v55, 0x7FFFFFFF, v23);
            lParama = v55;
          }
          v39 = lParam;
          do
          {
            v40 = *v24++;
            *v39++ = v40;
          }
          while ( v40 );
          v16 = (HWND *)v56;
          goto LABEL_69;
        }
        LOWORD(v27) = 42;
      }
      LOWORD(v28) = 63;
    }
    v31 = v23;
    v30 = v23;
    v24 = &lParam[(int)v25];
    LOBYTE(v31) = *(v24 - 1) == 92;
    while ( 1 )
    {
      v32 = v25;
      LODWORD(v25) = v25 - 1;
      if ( !v32 )
        break;
      v33 = v24 - 1;
      if ( *(v24 - 1) == (_WORD)v27 || *v33 == (_WORD)v28 )
        v31 = 1;
      v34 = *v33;
      LOWORD(v34) = v34 - 47;
      if ( (unsigned __int16)v34 <= 0x2Du )
      {
        v35 = 0x200000000801LL;
        if ( _bittest64(&v35, v34) )
        {
          if ( !(_DWORD)v25 || *(v24 - 2) == 58 || *v33 == 58 )
            v30 = 1;
          break;
        }
      }
      --v24;
      LOWORD(v28) = 63;
    }
    if ( !v31 )
    {
      v11 = 1417;
      goto LABEL_3;
    }
    if ( v30 )
    {
      ++v24;
    }
    else if ( (int)v25 < 0 )
    {
LABEL_61:
      v19 = v13 & 0x2000;
      goto LABEL_62;
    }
    v36 = v24 - 1;
    v37 = *(v24 - 1);
    *(v24 - 1) = v23;
    if ( *lParam != (_WORD)v23 )
    {
      v38 = SetCurrentDirectoryW(lParam);
      v23 = 0;
      if ( !v38 )
      {
        *v36 = v37;
        return 0;
      }
    }
    *v36 = v37;
    v9 = lParama;
    if ( v30 )
      --v24;
    goto LABEL_61;
  }
LABEL_69:
  GetCurrentDirectoryW(0x104u, Buffer);
  if ( v7 )
  {
    CharLowerW(Buffer);
    v41 = (HWND *)v57;
    v42 = ChopText(v57, v7, v58);
    SetDlgItemTextW(*v41, v7, v42);
  }
  if ( !v8 || !v16 )
    return 1;
  v43 = *v16;
  v44 = 0;
  v45 = a7 != 0 ? 0x39 : 0;
  if ( v19 )
  {
    PostMessageW(v43, v45 + 331, 0, 0);
  }
  else
  {
    if ( v54 && (*(_BYTE *)(v54 + 92) & 4) != 0 && (unsigned int)IsVisible(*(_QWORD *)(v54 + 8)) )
    {
      v44 = 1;
      SendMessageW(v43, 0xBu, 0, 0);
    }
    SendMessageW(v43, v45 + 331, 0, 0);
  }
  v46 = a7 != 0 ? 397 : 325;
  if ( v13 == 0x4000 )
    v13 = 49152;
  v47 = v13 | 0x1000;
  if ( (v13 & 0x8000) == 0 || (v13 & 0x4010) == 0 )
    v47 = v13;
  v48 = v47;
  if ( (v47 & 0x1000) != 0 )
  {
    v50 = (LPARAM)lParama;
  }
  else
  {
    v49 = v47 & 0xFFFFBFEF;
    if ( v19 )
    {
      v50 = (LPARAM)lParama;
      PostMessageW(v43, v46, v49, (LPARAM)lParama);
    }
    else
    {
      SendMessageW(v43, v46, v49, (LPARAM)lParam);
      v50 = (LPARAM)lParama;
    }
    v47 = v48 & (v48 & 0x27 | 0x6010) | 0x1000;
  }
  if ( (v47 & 0x6010) == 0 )
  {
    if ( v19 )
      return 1;
LABEL_95:
    if ( v44 )
    {
      SendMessageW(v43, 0xBu, 1u, 0);
      NtUserInvalidateRect(v43, 0, 1);
    }
    return 1;
  }
  v51 = v47 | 0x8000LL;
  if ( !v19 )
  {
    SendMessageW(v43, v46, v51, (LPARAM)&szSLASHSTARDOTSTAR + 2);
    goto LABEL_95;
  }
  PostMessageW(v43, v46, v51, v50);
  return 1;
}

```

## disassembly

```asm
0x180085ab4  push    rbx
0x180085ab6  push    rbp
0x180085ab7  push    rsi
0x180085ab8  push    rdi
0x180085ab9  push    r12
0x180085abb  push    r13
0x180085abd  push    r14
0x180085abf  push    r15
0x180085ac1  sub     rsp, 2A8h
0x180085ac8  mov     rax, cs:__security_cookie
0x180085acf  xor     rax, rsp
0x180085ad2  mov     [rsp+2E8h+var_58], rax
0x180085ada  mov     r15d, [rsp+2E8h+nIDDlgItem]
0x180085ae2  mov     edi, r9d
0x180085ae5  mov     [rsp+2E8h+var_2B8], r9d
0x180085aea  mov     rbp, r8
0x180085aed  mov     r9, rcx
0x180085af0  mov     [rsp+2E8h+var_288], rcx
0x180085af5  mov     ecx, [rsp+2E8h+arg_28]
0x180085afc  mov     r14, rdx
0x180085aff  mov     [rsp+2E8h+lParam], r8
0x180085b04  mov     [rsp+2E8h+var_298], r8
0x180085b09  test    ecx, 0FFFF1FC8h
0x180085b0f  jz      short loc_180085B23
0x180085b11  mov     ecx, 3ECh; LastError
0x180085b16  call    cs:__imp_RtlSetLastWin32Error
0x180085b1c  xor     eax, eax
0x180085b1e  jmp     loc_180085F81
0x180085b23  xor     r12d, r12d
0x180085b26  mov     esi, ecx
0x180085b28  btr     esi, 0Ch
0x180085b2c  bt      ecx, 0Ch
0x180085b30  cmovnb  esi, ecx
0x180085b33  test    r9, r9
0x180085b36  jnz     short loc_180085B48
0x180085b38  test    r15d, r15d
0x180085b3b  jnz     short loc_180085B41
0x180085b3d  test    edi, edi
0x180085b3f  jz      short loc_180085B48
0x180085b41  mov     ecx, 57h ; 'W'
0x180085b46  jmp     short loc_180085B16
0x180085b48  mov     edx, edi; int
0x180085b4a  mov     [rsp+2E8h+var_2A0], r12
0x180085b4f  mov     rcx, r9; struct tagWND *
0x180085b52  mov     r8, r12
0x180085b55  call    ?_GetDlgItem@@YAPEAUtagWND@@PEAU1@H@Z; _GetDlgItem(tagWND *,int)
0x180085b5a  mov     r13d, [rsp+2E8h+arg_30]
0x180085b62  mov     rbx, rax
0x180085b65  mov     [rsp+2E8h+var_290], rax
0x180085b6a  test    rax, rax
0x180085b6d  jz      short loc_180085BCE
0x180085b6f  mov     ecx, 2FFFh
0x180085b74  and     cx, [rax+2Ah]
0x180085b78  mov     eax, 2A6h
0x180085b7d  cmp     cx, ax
0x180085b80  jnz     short loc_180085B87
0x180085b82  test    r13d, r13d
0x180085b85  jnz     short loc_180085BA5
0x180085b87  mov     eax, 2A2h
0x180085b8c  cmp     cx, ax
0x180085b8f  jnz     short loc_180085B96
0x180085b91  test    r13d, r13d
0x180085b94  jz      short loc_180085BA5
0x180085b96  mov     eax, 2A3h
0x180085b9b  cmp     cx, ax
0x180085b9e  jnz     short loc_180085BD2
0x180085ba0  test    r13d, r13d
0x180085ba3  jz      short loc_180085BD2
0x180085ba5  lea     rax, [rbx+128h]
0x180085bac  test    r13d, r13d
0x180085baf  jnz     short loc_180085BC1
0x180085bb1  mov     rax, [rax]
0x180085bb4  mov     rcx, [rax]
0x180085bb7  mov     rax, [rcx+48h]
0x180085bbb  add     rax, 128h
0x180085bc1  mov     rax, [rax]
0x180085bc4  mov     r8, [rax]
0x180085bc7  mov     [rsp+2E8h+var_2A0], r8
0x180085bcc  jmp     short loc_180085BE0
0x180085bce  test    edi, edi
0x180085bd0  jz      short loc_180085BE0
0x180085bd2  mov     ecx, 588h; LastError
0x180085bd7  call    cs:__imp_RtlSetLastWin32Error
0x180085bdd  mov     r8, r12
0x180085be0  test    r15d, r15d
0x180085be3  jns     short loc_180085BEC
0x180085be5  test    r8, r8
0x180085be8  cmovnz  r15d, r12d
0x180085bec  mov     r12d, esi
0x180085bef  and     r12d, 2000h
0x180085bf6  mov     [rsp+2E8h+var_2A8], r12d
0x180085bfb  test    r14, r14
0x180085bfe  jz      loc_180085DCA
0x180085c04  mov     rcx, r14; lpString
0x180085c07  call    cs:__imp_lstrlenW
0x180085c0d  test    eax, eax
0x180085c0f  jnz     short loc_180085C30
0x180085c11  cmp     rbp, r14
0x180085c14  lea     rax, ?achSlashStar@@3PADA; "\\*"
0x180085c1b  lea     r14, ?awchSlashStar@@3PAGA; "\\*"
0x180085c22  cmovz   rax, rbp
0x180085c26  mov     [rsp+2E8h+lParam], rax
0x180085c2b  jmp     loc_180085DCA
0x180085c30  cmp     eax, 104h
0x180085c35  jg      loc_180085B1C
0x180085c3b  mov     rcx, r14; lpsz
0x180085c3e  call    cs:__imp_CharUpperW
0x180085c44  xor     r10d, r10d
0x180085c47  lea     rbx, ?szSLASHSTARDOTSTAR@@3PAGA+2; "*"
0x180085c4e  cmp     [r14], r10w
0x180085c52  jz      loc_180085D7B
0x180085c58  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180085c5c  inc     rdi
0x180085c5f  cmp     [r14+rdi*2], r10w
0x180085c64  jnz     short loc_180085C5C
0x180085c66  mov     r11d, 2Ah ; '*'
0x180085c6c  mov     rcx, r14
0x180085c6f  mov     edx, r11d
0x180085c72  call    FindCharPosition
0x180085c77  lea     r8d, [r11+15h]
0x180085c7b  cmp     eax, edi
0x180085c7d  jnz     short loc_180085CAC
0x180085c7f  mov     edx, r8d
0x180085c82  mov     rcx, r14
0x180085c85  call    FindCharPosition
0x180085c8a  cmp     eax, edi
0x180085c8c  jnz     short loc_180085CA6
0x180085c8e  mov     rcx, r14; lpPathName
0x180085c91  call    cs:__imp_SetCurrentDirectoryW
0x180085c97  xor     r10d, r10d
0x180085c9a  test    eax, eax
0x180085c9c  jnz     loc_180085D77
0x180085ca2  lea     r11d, [r10+2Ah]
0x180085ca6  mov     r8d, 3Fh ; '?'
0x180085cac  movsxd  rax, edi
0x180085caf  mov     edx, r10d
0x180085cb2  mov     r12d, r10d
0x180085cb5  lea     rbx, [r14+rax*2]
0x180085cb9  cmp     word ptr [rbx-2], 5Ch ; '\'
0x180085cbe  setz    dl
0x180085cc1  mov     eax, edi
0x180085cc3  dec     edi
0x180085cc5  test    eax, eax
0x180085cc7  jz      short loc_180085D1D
0x180085cc9  lea     rcx, [rbx-2]
0x180085ccd  cmp     [rcx], r11w
0x180085cd1  jz      short loc_180085CD9
0x180085cd3  cmp     [rcx], r8w
0x180085cd7  jnz     short loc_180085CDE
0x180085cd9  mov     edx, 1
0x180085cde  movzx   eax, word ptr [rcx]
0x180085ce1  sub     ax, 2Fh ; '/'
0x180085ce5  cmp     ax, 2Dh ; '-'
0x180085ce9  ja      short loc_180085CFB
0x180085ceb  mov     r8, 200000000801h
0x180085cf5  bt      r8, rax
0x180085cf9  jb      short loc_180085D06
0x180085cfb  mov     rbx, rcx
0x180085cfe  mov     r8d, 3Fh ; '?'
0x180085d04  jmp     short loc_180085CC1
0x180085d06  test    edi, edi
0x180085d08  jz      short loc_180085D17
0x180085d0a  cmp     word ptr [rbx-4], 3Ah ; ':'
0x180085d0f  jz      short loc_180085D17
0x180085d11  cmp     word ptr [rcx], 3Ah ; ':'
0x180085d15  jnz     short loc_180085D1D
0x180085d17  mov     r12d, 1
0x180085d1d  test    edx, edx
0x180085d1f  jnz     short loc_180085D2B
0x180085d21  mov     ecx, 589h
0x180085d26  jmp     loc_180085B16
0x180085d2b  test    r12d, r12d
0x180085d2e  jz      short loc_180085D36
0x180085d30  add     rbx, 2
0x180085d34  jmp     short loc_180085D3A
0x180085d36  test    edi, edi
0x180085d38  js      short loc_180085D72
0x180085d3a  lea     rdi, [rbx-2]
0x180085d3e  movzx   ebp, word ptr [rdi]
0x180085d41  mov     [rdi], r10w
0x180085d45  cmp     [r14], r10w
0x180085d49  jz      short loc_180085D63
0x180085d4b  mov     rcx, r14; lpPathName
0x180085d4e  call    cs:__imp_SetCurrentDirectoryW
0x180085d54  xor     r10d, r10d
0x180085d57  test    eax, eax
0x180085d59  jnz     short loc_180085D63
0x180085d5b  mov     [rdi], bp
0x180085d5e  jmp     loc_180085B1C
0x180085d63  test    r12d, r12d
0x180085d66  mov     [rdi], bp
0x180085d69  mov     rbp, [rsp+2E8h+lParam]
0x180085d6e  cmovnz  rbx, rdi
0x180085d72  mov     r12d, [rsp+2E8h+var_2A8]
0x180085d77  mov     edi, [rsp+2E8h+var_2B8]
0x180085d7b  test    r12d, r12d
0x180085d7e  jz      short loc_180085DAF
0x180085d80  cmp     rbp, r14
0x180085d83  jz      short loc_180085DAF
0x180085d85  mov     [rsp+2E8h+var_2C0], r10d
0x180085d8a  lea     r9, [rsp+2E8h+var_298]
0x180085d8f  xor     ecx, ecx
0x180085d91  mov     [rsp+2E8h+var_2C8], 7FFFFFFFh
0x180085d99  or      r8d, 0FFFFFFFFh
0x180085d9d  mov     rdx, rbx
0x180085da0  call    WCSToMBEx
0x180085da5  mov     rax, [rsp+2E8h+var_298]
0x180085daa  mov     [rsp+2E8h+lParam], rax
0x180085daf  mov     rdx, r14
0x180085db2  movzx   eax, word ptr [rbx]
0x180085db5  lea     rbx, [rbx+2]
0x180085db9  mov     [rdx], ax
0x180085dbc  lea     rdx, [rdx+2]
0x180085dc0  test    ax, ax
0x180085dc3  jnz     short loc_180085DB2
0x180085dc5  mov     rbx, [rsp+2E8h+var_290]
0x180085dca  lea     rdx, [rsp+2E8h+Buffer]; lpBuffer
0x180085dcf  mov     ecx, 104h; nBufferLength
0x180085dd4  call    cs:__imp_GetCurrentDirectoryW
0x180085dda  test    r15d, r15d
0x180085ddd  jz      short loc_180085E0E
0x180085ddf  lea     rcx, [rsp+2E8h+Buffer]; lpsz
0x180085de4  call    cs:__imp_CharLowerW
0x180085dea  mov     rbp, [rsp+2E8h+var_288]
0x180085def  lea     r8, [rsp+2E8h+var_278]; unsigned __int16 *
0x180085df4  mov     rcx, rbp; struct tagWND *
0x180085df7  mov     edx, r15d; int
0x180085dfa  call    ?ChopText@@YAPEAGPEAUtagWND@@HPEAG@Z; ChopText(tagWND *,int,ushort *)
0x180085dff  mov     rcx, [rbp+0]; hDlg
0x180085e03  mov     r8, rax; lpString
0x180085e06  mov     edx, r15d; nIDDlgItem
0x180085e09  call    SetDlgItemTextW
0x180085e0e  xor     r15d, r15d
0x180085e11  test    edi, edi
0x180085e13  jz      loc_180085F7C
0x180085e19  test    rbx, rbx
0x180085e1c  jz      loc_180085F7C
0x180085e22  mov     rbx, [rbx]
0x180085e25  mov     eax, r13d
0x180085e28  neg     eax
0x180085e2a  mov     ebp, r15d
0x180085e2d  sbb     edi, edi
0x180085e2f  and     edi, 39h
0x180085e32  test    r12d, r12d
0x180085e35  jz      short loc_180085E4D
0x180085e37  xor     r9d, r9d; lParam
0x180085e3a  lea     edx, [rdi+14Bh]; Msg
0x180085e40  xor     r8d, r8d; wParam
0x180085e43  mov     rcx, rbx; hWnd
0x180085e46  call    PostMessageW
0x180085e4b  jmp     short loc_180085E94
0x180085e4d  mov     rcx, [rsp+2E8h+var_2A0]
0x180085e52  test    rcx, rcx
0x180085e55  jz      short loc_180085E80
0x180085e57  test    byte ptr [rcx+5Ch], 4
0x180085e5b  jz      short loc_180085E80
0x180085e5d  mov     rcx, [rcx+8]
0x180085e61  call    IsVisible
0x180085e66  test    eax, eax
0x180085e68  jz      short loc_180085E80
0x180085e6a  mov     ebp, 1
0x180085e6f  xor     r9d, r9d; lParam
0x180085e72  xor     r8d, r8d; wParam
0x180085e75  mov     rcx, rbx; hWnd
0x180085e78  lea     edx, [rbp+0Ah]; Msg
0x180085e7b  call    SendMessageW
0x180085e80  xor     r9d, r9d; lParam
0x180085e83  lea     edx, [rdi+14Bh]; Msg
0x180085e89  xor     r8d, r8d; wParam
0x180085e8c  mov     rcx, rbx; hWnd
0x180085e8f  call    SendMessageW
0x180085e94  neg     r13d
0x180085e97  mov     r13d, 8000h
0x180085e9d  sbb     edi, edi
0x180085e9f  and     edi, 48h
0x180085ea2  add     edi, 145h
0x180085ea8  cmp     esi, 4000h
0x180085eae  jnz     short loc_180085EB3
0x180085eb0  or      esi, r13d
0x180085eb3  test    esi, 4010h
0x180085eb9  mov     edx, 1000h
0x180085ebe  setnz   cl
0x180085ec1  bt      esi, 0Fh
0x180085ec5  setb    al
0x180085ec8  and     cl, al
0x180085eca  mov     eax, esi
0x180085ecc  or      eax, edx
0x180085ece  test    cl, cl
0x180085ed0  cmovz   eax, esi
0x180085ed3  mov     esi, eax
0x180085ed5  test    edx, eax
0x180085ed7  jnz     short loc_180085F1C
0x180085ed9  mov     r8d, esi
0x180085edc  mov     eax, 0FFFFBFEFh
0x180085ee1  and     r8, rax; wParam
0x180085ee4  mov     edx, edi; Msg
0x180085ee6  mov     rcx, rbx; hWnd
0x180085ee9  test    r12d, r12d
0x180085eec  jz      short loc_180085EFD
0x180085eee  mov     r14, [rsp+2E8h+lParam]
  ... truncated ...
```
