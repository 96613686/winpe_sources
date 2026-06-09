# CDataLinkDialog_Connect::GetOpenFileNameW(uint,ushort const *,ushort * &,uint,uint)

- ea: `0x3839dcd70`
- end: `0x3839dd1aa`
- name: `?GetOpenFileNameW@CDataLinkDialog_Connect@@AEAAJIPEBGAEAPEAGII@Z`
- size: `1082`
- prototype: `__int64 __fastcall(CDataLinkDialog_Connect *__hidden this, unsigned int, const unsigned __int16 *, unsigned __int16 **, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x3839da120`

## callees

- `0x3838434c0`
- `0x3838435e0`
- `0x383844d50`
- `0x383893160`
- `0x38391aed0`
- `0x3839dcd70`

## import_xrefs

- `MSVCR100!_wsplitpath_s` at `0x3839dcedc`
- `MSVCR100!_wsplitpath_s` at `0x3839dcedc`
- `MSVCR100!wcschr` at `0x3839dcdf7`
- `MSVCR100!wcschr` at `0x3839dce0f`
- `MSVCR100!wcschr` at `0x3839dcdf7`
- `MSVCR100!wcschr` at `0x3839dce0f`
- `KERNEL32!lstrlenW` at `0x3839dce3d`
- `KERNEL32!lstrlenW` at `0x3839dce3d`
- `USER32!LoadStringW` at `0x3839dcde6`
- `USER32!LoadStringW` at `0x3839dd071`
- `USER32!LoadStringW` at `0x3839dd0a2`
- `USER32!LoadStringW` at `0x3839dcde6`
- `USER32!LoadStringW` at `0x3839dd071`
- `USER32!LoadStringW` at `0x3839dd0a2`
- `COMDLG32!CommDlgExtendedError` at `0x3839dd0e3`
- `COMDLG32!CommDlgExtendedError` at `0x3839dd0e3`
- `COMDLG32!GetOpenFileNameW` at `0x3839dd0b7`
- `COMDLG32!GetOpenFileNameW` at `0x3839dd0b7`

## pseudocode

```c
__int64 __fastcall CDataLinkDialog_Connect::GetOpenFileNameW(
        CDataLinkDialog_Connect *this,
        const WCHAR *a2,
        unsigned __int16 *a3,
        unsigned __int16 **a4)
{
  wchar_t *i; // rax
  DWORD nMaxFile; // ecx
  DWORD v9; // eax
  __int64 v10; // rbx
  __int64 v11; // rdx
  WCHAR *v12; // rax
  __int64 v13; // rax
  unsigned __int64 v14; // rdx
  unsigned __int64 v15; // rcx
  unsigned __int64 v16; // rcx
  void *v17; // rsp
  void *v18; // rsp
  wchar_t v19; // ax
  wchar_t *v20; // r11
  wchar_t v21; // ax
  wchar_t *v22; // rcx
  DWORD v24; // eax
  unsigned int v25; // ebx
  __int64 v26; // [rsp+0h] [rbp-50h] BYREF
  size_t DirCount; // [rsp+20h] [rbp-30h]
  struct tagOFNW v28; // [rsp+50h] [rbp+0h] BYREF
  wchar_t Drive[8]; // [rsp+F0h] [rbp+A0h] BYREF
  wchar_t Filename[256]; // [rsp+100h] [rbp+B0h] BYREF
  wchar_t Ext[256]; // [rsp+300h] [rbp+2B0h] BYREF
  wchar_t Dir[256]; // [rsp+500h] [rbp+4B0h] BYREF
  WCHAR Buffer[512]; // [rsp+700h] [rbp+6B0h] BYREF
  WCHAR v34[512]; // [rsp+B00h] [rbp+AB0h] BYREF
  WCHAR v35[512]; // [rsp+F00h] [rbp+EB0h] BYREF

  *(_QWORD *)a3 = 0;
  v28.lStructSize = 152;
  memset(&v28.hwndOwner, 0, 0x90u);
  v28.hwndOwner = (HWND)*((_QWORD *)this + 2);
  v28.hInstance = g_hinstance_language;
  LoadStringW(g_hinstance_language, 0x9C7Eu, Buffer, 512);
  for ( i = wcschr(Buffer, 0x7Cu); i; i = wcschr(i + 1, 0x7Cu) )
    *i = 0;
  nMaxFile = 260;
  v28.lpstrCustomFilter = 0;
  v28.nFilterIndex = 0;
  v28.lpstrFilter = Buffer;
  v28.nMaxFile = 260;
  if ( a2 )
  {
    v9 = lstrlenW(a2);
    nMaxFile = v28.nMaxFile;
    if ( v9 > v28.nMaxFile )
      nMaxFile = v9;
    v28.nMaxFile = nMaxFile;
  }
  v10 = -1;
  v11 = 2LL * (nMaxFile + 1);
  if ( !is_mul_ok(nMaxFile + 1, 2u) )
    v11 = -1;
  v12 = (WCHAR *)((__int64 (__fastcall *)(struct IMalloc *, __int64))g_pMO->lpVtbl[1].Free)(g_pMO, v11);
  *(_QWORD *)a3 = v12;
  if ( !v12 )
    return 2147942414LL;
  v28.lpstrFile = v12;
  *v12 = 0;
  v28.lpstrInitialDir = 0;
  if ( !a2 )
    goto LABEL_38;
  _wsplitpath_s(a2, Drive, 3u, Dir, 0x100u, Filename, 0x100u, Ext, 0x100u);
  v13 = -1;
  do
    ++v13;
  while ( Drive[v13] );
  do
    ++v10;
  while ( Dir[v10] );
  v14 = v10 + v13 + 1;
  v15 = 2 * v14 + 15;
  if ( v15 <= 2 * v14 )
    v15 = 0xFFFFFFFFFFFFFF0LL;
  v16 = v15 & 0xFFFFFFFFFFFFFFF0uLL;
  v17 = alloca(v16);
  v18 = alloca(v16);
  v28.lpstrInitialDir = (LPCWSTR)&v28;
  if ( &v26 == (__int64 *)-80LL )
    return 2147942414LL;
  StringCchPrintfW((unsigned __int16 *)&v28, v14, L"%ls%ls", Drive, Dir);
  v19 = Filename[0];
  v20 = Filename;
  if ( Filename[0] )
  {
    while ( v19 != 92 && v19 != 47 && v19 != 58 && v19 != 42 && v19 != 63 && v19 != 60 && v19 != 62 && v19 != 124 )
    {
      v19 = v20[1];
      ++v20;
      if ( !v19 )
        goto LABEL_27;
    }
  }
  else
  {
LABEL_27:
    v21 = Ext[0];
    v22 = Ext;
    if ( Ext[0] )
    {
      while ( v21 != 92 && v21 != 47 && v21 != 58 && v21 != 42 && v21 != 63 && v21 != 60 && v21 != 62 && v21 != 124 )
      {
        v21 = v22[1];
        ++v22;
        if ( !v21 )
          goto LABEL_37;
      }
    }
    else
    {
LABEL_37:
      StringCchPrintfW(v28.lpstrFile, v28.nMaxFile, L"%ls%ls", Filename, Ext);
    }
  }
LABEL_38:
  v28.lpstrFileTitle = 0;
  LoadStringW(g_hinstance_language, 0x9C7Fu, v34, 512);
  v28.lpstrTitle = v34;
  v28.Flags = 6148;
  LoadStringW(g_hinstance_language, 0x9C80u, v35, 512);
  v28.lpstrDefExt = v35;
  if ( GetOpenFileNameW(&v28) )
    return 0;
  if ( *(_QWORD *)a3 )
    ((void (__fastcall *)(struct IMalloc *))g_pMO->lpVtbl[1].DidAlloc)(g_pMO);
  *(_QWORD *)a3 = 0;
  v24 = CommDlgExtendedError();
  v25 = v24;
  if ( v24 )
  {
    if ( (bidGblFlags & 2) != 0 && off_383B496F0[0] )
      bidTraceW(off_383B432A8[0], 3510272, off_383B496F0[0], v24);
    if ( v25 != 2 && (v25 <= 8 || v25 > 0xA && v25 != 12 && v25 != 12289) )
      return 2147500037LL;
    if ( (bidGblFlags & 2) != 0 )
    {
      if ( off_383B49128[0] )
      {
        LODWORD(DirCount) = 3436;
        bidTraceW(off_383B432A8[0], 3518505, off_383B49128[0], 2147942414LL);
      }
    }
    return 2147942414LL;
  }
  return 1;
}

```

## disassembly

```asm
0x3839dcd70  push    rbp
0x3839dcd72  push    rbx
0x3839dcd73  push    rsi
0x3839dcd74  push    rdi
0x3839dcd75  push    r14
0x3839dcd77  mov     eax, 1310h
0x3839dcd7c  call    _alloca_probe
0x3839dcd81  sub     rsp, rax
0x3839dcd84  lea     rbp, [rsp+50h]
0x3839dcd89  mov     rax, cs:__security_cookie
0x3839dcd90  xor     rax, rbp
0x3839dcd93  mov     [rbp+12E0h+var_30], rax
0x3839dcd9a  mov     rbx, rcx
0x3839dcd9d  mov     rsi, r8
0x3839dcda0  mov     rdi, rdx
0x3839dcda3  xor     r14d, r14d
0x3839dcda6  lea     rcx, [rbp+12E0h+var_12E0.hwndOwner]; void *
0x3839dcdaa  xor     edx, edx; Val
0x3839dcdac  mov     [r8], r14
0x3839dcdaf  mov     r8d, 90h; Size
0x3839dcdb5  mov     [rbp+12E0h+var_12E0.lStructSize], 98h
0x3839dcdbc  call    memset
0x3839dcdc1  mov     r11, [rbx+10h]
0x3839dcdc5  mov     rcx, cs:?g_hinstance_language@@3PEAUHINSTANCE__@@EA; hInstance
0x3839dcdcc  lea     r8, [rbp+12E0h+Buffer]; lpBuffer
0x3839dcdd3  mov     r9d, 200h; cchBufferMax
0x3839dcdd9  mov     edx, 9C7Eh; uID
0x3839dcdde  mov     [rbp+12E0h+var_12E0.hwndOwner], r11
0x3839dcde2  mov     [rbp+12E0h+var_12E0.hInstance], rcx
0x3839dcde6  call    cs:__imp_LoadStringW
0x3839dcdec  lea     edx, [r14+7Ch]; Ch
0x3839dcdf0  lea     rcx, [rbp+12E0h+Buffer]; Str
0x3839dcdf7  call    cs:__imp_wcschr
0x3839dcdfd  test    rax, rax
0x3839dce00  jz      short loc_3839DCE1A
0x3839dce02  lea     rcx, [rax+2]; Str
0x3839dce06  mov     edx, 7Ch ; '|'; Ch
0x3839dce0b  mov     [rax], r14w
0x3839dce0f  call    cs:__imp_wcschr
0x3839dce15  test    rax, rax
0x3839dce18  jnz     short loc_3839DCE02
0x3839dce1a  lea     rax, [rbp+12E0h+Buffer]
0x3839dce21  mov     ecx, 104h
0x3839dce26  mov     [rbp+12E0h+var_12E0.lpstrCustomFilter], r14
0x3839dce2a  mov     [rbp+12E0h+var_12E0.nFilterIndex], r14d
0x3839dce2e  mov     [rbp+12E0h+var_12E0.lpstrFilter], rax
0x3839dce32  mov     [rbp+12E0h+var_12E0.nMaxFile], ecx
0x3839dce35  test    rdi, rdi
0x3839dce38  jz      short loc_3839DCE4E
0x3839dce3a  mov     rcx, rdi; lpString
0x3839dce3d  call    cs:__imp_lstrlenW
0x3839dce43  mov     ecx, [rbp+12E0h+var_12E0.nMaxFile]
0x3839dce46  cmp     eax, ecx
0x3839dce48  cmova   ecx, eax
0x3839dce4b  mov     [rbp+12E0h+var_12E0.nMaxFile], ecx
0x3839dce4e  inc     ecx
0x3839dce50  mov     eax, 2
0x3839dce55  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x3839dce5c  mul     rcx
0x3839dce5f  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x3839dce66  mov     rdx, rax
0x3839dce69  mov     rax, [rcx]
0x3839dce6c  cmovo   rdx, rbx
0x3839dce70  call    qword ptr [rax+70h]
0x3839dce73  mov     [rsi], rax
0x3839dce76  test    rax, rax
0x3839dce79  jz      loc_3839DD181
0x3839dce7f  mov     [rbp+12E0h+var_12E0.lpstrFile], rax
0x3839dce83  mov     [rax], r14w
0x3839dce87  mov     [rbp+12E0h+var_12E0.lpstrInitialDir], r14
0x3839dce8b  test    rdi, rdi
0x3839dce8e  jz      loc_3839DD054
0x3839dce94  mov     [rsp+1330h+ExtCount], 100h; ExtCount
0x3839dce9d  lea     rax, [rbp+12E0h+var_1030]
0x3839dcea4  lea     r9, [rbp+12E0h+Dir]; Dir
0x3839dceab  mov     [rsp+1330h+Ext], rax; Ext
0x3839dceb0  lea     rax, [rbp+12E0h+var_1230]
0x3839dceb7  mov     [rsp+1330h+FilenameCount], 100h; FilenameCount
0x3839dcec0  mov     [rsp+1330h+Filename], rax; Filename
0x3839dcec5  lea     r8d, [rbx+4]; DriveCount
0x3839dcec9  lea     rdx, [rbp+12E0h+Drive]; Drive
0x3839dced0  mov     rcx, rdi; FullPath
0x3839dced3  mov     [rsp+1330h+DirCount], 100h; DirCount
0x3839dcedc  call    cs:__imp__wsplitpath_s
0x3839dcee2  lea     r11, [rbp+12E0h+Drive]
0x3839dcee9  mov     rax, rbx
0x3839dceec  nop     dword ptr [rax+00h]
0x3839dcef0  inc     rax
0x3839dcef3  cmp     [r11+rax*2], r14w
0x3839dcef8  jnz     short loc_3839DCEF0
0x3839dcefa  lea     rcx, [rbp+12E0h+Dir]
0x3839dcf01  inc     rbx
0x3839dcf04  cmp     [rcx+rbx*2], r14w
0x3839dcf09  jnz     short loc_3839DCF01
0x3839dcf0b  lea     rdx, [rax+1]
0x3839dcf0f  add     rdx, rbx
0x3839dcf12  lea     rax, [rdx+rdx]
0x3839dcf16  lea     rcx, [rax+0Fh]
0x3839dcf1a  cmp     rcx, rax
0x3839dcf1d  ja      short loc_3839DCF29
0x3839dcf1f  mov     rcx, 0FFFFFFFFFFFFFF0h
0x3839dcf29  and     rcx, 0FFFFFFFFFFFFFFF0h
0x3839dcf2d  mov     rax, rcx
0x3839dcf30  call    _alloca_probe
0x3839dcf35  sub     rsp, rcx
0x3839dcf38  lea     rcx, [rsp+1330h+var_12E0]; unsigned __int16 *
0x3839dcf3d  mov     [rbp+12E0h+var_12E0.lpstrInitialDir], rcx
0x3839dcf41  test    rcx, rcx
0x3839dcf44  jz      loc_3839DD181
0x3839dcf4a  lea     rax, [rbp+12E0h+Dir]
0x3839dcf51  lea     r9, [rbp+12E0h+Drive]
0x3839dcf58  lea     r8, aLsLs_2; "%ls%ls"
0x3839dcf5f  mov     [rsp+1330h+DirCount], rax
0x3839dcf64  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x3839dcf69  movzx   eax, [rbp+12E0h+var_1230]
0x3839dcf70  lea     r11, [rbp+12E0h+var_1230]
0x3839dcf77  test    ax, ax
0x3839dcf7a  jz      short loc_3839DCFDE
0x3839dcf7c  nop     dword ptr [rax+00h]
0x3839dcf80  cmp     ax, 5Ch ; '\'
0x3839dcf84  jz      loc_3839DD054
0x3839dcf8a  cmp     ax, 2Fh ; '/'
0x3839dcf8e  jz      loc_3839DD054
0x3839dcf94  cmp     ax, 3Ah ; ':'
0x3839dcf98  jz      loc_3839DD054
0x3839dcf9e  cmp     ax, 2Ah ; '*'
0x3839dcfa2  jz      loc_3839DD054
0x3839dcfa8  cmp     ax, 3Fh ; '?'
0x3839dcfac  jz      loc_3839DD054
0x3839dcfb2  cmp     ax, 3Ch ; '<'
0x3839dcfb6  jz      loc_3839DD054
0x3839dcfbc  cmp     ax, 3Eh ; '>'
0x3839dcfc0  jz      loc_3839DD054
0x3839dcfc6  cmp     ax, 7Ch ; '|'
0x3839dcfca  jz      loc_3839DD054
0x3839dcfd0  movzx   eax, word ptr [r11+2]
0x3839dcfd5  add     r11, 2
0x3839dcfd9  test    ax, ax
0x3839dcfdc  jnz     short loc_3839DCF80
0x3839dcfde  movzx   eax, [rbp+12E0h+var_1030]
0x3839dcfe5  lea     rcx, [rbp+12E0h+var_1030]
0x3839dcfec  test    ax, ax
0x3839dcfef  jz      short loc_3839DD02E
0x3839dcff1  cmp     ax, 5Ch ; '\'
0x3839dcff5  jz      short loc_3839DD054
0x3839dcff7  cmp     ax, 2Fh ; '/'
0x3839dcffb  jz      short loc_3839DD054
0x3839dcffd  cmp     ax, 3Ah ; ':'
0x3839dd001  jz      short loc_3839DD054
0x3839dd003  cmp     ax, 2Ah ; '*'
0x3839dd007  jz      short loc_3839DD054
0x3839dd009  cmp     ax, 3Fh ; '?'
0x3839dd00d  jz      short loc_3839DD054
0x3839dd00f  cmp     ax, 3Ch ; '<'
0x3839dd013  jz      short loc_3839DD054
0x3839dd015  cmp     ax, 3Eh ; '>'
0x3839dd019  jz      short loc_3839DD054
0x3839dd01b  cmp     ax, 7Ch ; '|'
0x3839dd01f  jz      short loc_3839DD054
0x3839dd021  movzx   eax, word ptr [rcx+2]
0x3839dd025  add     rcx, 2
0x3839dd029  test    ax, ax
0x3839dd02c  jnz     short loc_3839DCFF1
0x3839dd02e  mov     edx, [rbp+12E0h+var_12E0.nMaxFile]; unsigned __int64
0x3839dd031  mov     rcx, [rbp+12E0h+var_12E0.lpstrFile]; unsigned __int16 *
0x3839dd035  lea     rax, [rbp+12E0h+var_1030]
0x3839dd03c  lea     r9, [rbp+12E0h+var_1230]
0x3839dd043  lea     r8, aLsLs_2; "%ls%ls"
0x3839dd04a  mov     [rsp+1330h+DirCount], rax
0x3839dd04f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x3839dd054  mov     rcx, cs:?g_hinstance_language@@3PEAUHINSTANCE__@@EA; hInstance
0x3839dd05b  lea     r8, [rbp+12E0h+var_830]; lpBuffer
0x3839dd062  mov     r9d, 200h; cchBufferMax
0x3839dd068  mov     edx, 9C7Fh; uID
0x3839dd06d  mov     [rbp+12E0h+var_12E0.lpstrFileTitle], r14
0x3839dd071  call    cs:__imp_LoadStringW
0x3839dd077  mov     rcx, cs:?g_hinstance_language@@3PEAUHINSTANCE__@@EA; hInstance
0x3839dd07e  lea     r11, [rbp+12E0h+var_830]
0x3839dd085  lea     r8, [rbp+12E0h+var_430]; lpBuffer
0x3839dd08c  mov     r9d, 200h; cchBufferMax
0x3839dd092  mov     edx, 9C80h; uID
0x3839dd097  mov     [rbp+12E0h+var_12E0.lpstrTitle], r11
0x3839dd09b  mov     [rbp+12E0h+var_12E0.Flags], 1804h
0x3839dd0a2  call    cs:__imp_LoadStringW
0x3839dd0a8  lea     r11, [rbp+12E0h+var_430]
0x3839dd0af  lea     rcx, [rbp+12E0h+var_12E0]; LPOPENFILENAMEW
0x3839dd0b3  mov     [rbp+12E0h+var_12E0.lpstrDefExt], r11
0x3839dd0b7  call    cs:__imp_GetOpenFileNameW
0x3839dd0bd  test    eax, eax
0x3839dd0bf  jz      short loc_3839DD0C8
0x3839dd0c1  xor     eax, eax
0x3839dd0c3  jmp     loc_3839DD18D
0x3839dd0c8  mov     rdx, [rsi]
0x3839dd0cb  test    rdx, rdx
0x3839dd0ce  jz      short loc_3839DD0E0
0x3839dd0d0  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x3839dd0d7  mov     rax, [rcx]
0x3839dd0da  call    qword ptr [rax+80h]
0x3839dd0e0  mov     [rsi], r14
0x3839dd0e3  call    cs:__imp_CommDlgExtendedError
0x3839dd0e9  mov     ebx, eax
0x3839dd0eb  test    eax, eax
0x3839dd0ed  jz      loc_3839DD188
0x3839dd0f3  test    byte ptr cs:_bidGblFlags, 2
0x3839dd0fa  jz      short loc_3839DD123
0x3839dd0fc  mov     rcx, cs:off_383B496F0; "<CDataLinkDialog_Connect::GetOpenFileNa"...
0x3839dd103  test    rcx, rcx
0x3839dd106  jz      short loc_3839DD123
0x3839dd108  mov     r8, cs:off_383B496F0; "<CDataLinkDialog_Connect::GetOpenFileNa"...
0x3839dd10f  mov     rcx, cs:off_383B432A8; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x3839dd116  mov     r9d, eax
0x3839dd119  mov     edx, 359000h
0x3839dd11e  call    _bidTraceW
0x3839dd123  cmp     ebx, 2
0x3839dd126  jz      short loc_3839DD146
0x3839dd128  cmp     ebx, 8
0x3839dd12b  jbe     short loc_3839DD13F
0x3839dd12d  cmp     ebx, 0Ah
0x3839dd130  jbe     short loc_3839DD146
0x3839dd132  cmp     ebx, 0Ch
0x3839dd135  jz      short loc_3839DD146
0x3839dd137  cmp     ebx, 3001h
0x3839dd13d  jz      short loc_3839DD146
0x3839dd13f  mov     eax, 80004005h
0x3839dd144  jmp     short loc_3839DD18D
0x3839dd146  test    byte ptr cs:_bidGblFlags, 2
0x3839dd14d  jz      short loc_3839DD181
0x3839dd14f  mov     rcx, cs:off_383B432A8; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x3839dd156  mov     rax, cs:off_383B49128; "<Trace|HR> 0x%08X{HRESULT} line %d\n"
0x3839dd15d  test    rax, rax
0x3839dd160  jz      short loc_3839DD181
0x3839dd162  mov     r8, cs:off_383B49128; "<Trace|HR> 0x%08X{HRESULT} line %d\n"
0x3839dd169  mov     r9d, 8007000Eh
0x3839dd16f  mov     edx, 35B029h
0x3839dd174  mov     dword ptr [rsp+1330h+DirCount], 0D6Ch
0x3839dd17c  call    _bidTraceW
0x3839dd181  mov     eax, 8007000Eh
0x3839dd186  jmp     short loc_3839DD18D
0x3839dd188  mov     eax, 1
0x3839dd18d  mov     rcx, [rbp+12E0h+var_30]
0x3839dd194  xor     rcx, rbp; StackCookie
0x3839dd197  call    __security_check_cookie
0x3839dd19c  lea     rsp, [rbp+12C0h]
0x3839dd1a3  pop     r14
0x3839dd1a5  pop     rdi
0x3839dd1a6  pop     rsi
0x3839dd1a7  pop     rbx
0x3839dd1a8  pop     rbp
0x3839dd1a9  retn
```
