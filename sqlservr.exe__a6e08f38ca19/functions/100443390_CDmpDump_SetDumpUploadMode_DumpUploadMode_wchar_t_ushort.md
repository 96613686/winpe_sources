# CDmpDump::SetDumpUploadMode(DumpUploadMode,wchar_t *,ushort)

- ea: `0x100443390`
- end: `0x100443633`
- name: `?SetDumpUploadMode@CDmpDump@@UEAAJW4DumpUploadMode@@PEA_WG@Z`
- size: `675`
- prototype: `int __high(enum DumpUploadMode, wchar_t *, unsigned __int16)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, registry_config`

## callees

- `0x100401580`
- `0x100404a30`
- `0x100443390`
- `0x100444610`
- `0x100444870`
- `0x1004534f8`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1004435c1`
- `KERNEL32!GetLastError` at `0x1004435c1`
- `api-ms-win-crt-convert-l1-1-0!_itow_s` at `0x100443568`
- `api-ms-win-crt-convert-l1-1-0!_itow_s` at `0x100443568`
- `SHLWAPI!PathFileExistsW` at `0x100443535`
- `SHLWAPI!PathFileExistsW` at `0x100443535`

## string_xrefs

- `0x1004435e6`: `StringCchCatW failed to construct dumper configuration file. Dumper dir path: %ls`
- `0x1004434df`: `sqldumper.exe.config.xml`
- `0x1004435ff`: `StringCchCatW failed to copy dumper dir path. : %ls`

## pseudocode

```c
signed int __fastcall CDmpDump::SetDumpUploadMode(__int64 a1, int a2, wchar_t *a3, unsigned __int16 a4)
{
  unsigned __int64 v5; // rbp
  WCHAR *v8; // rax
  __int64 v9; // r11
  __int64 v10; // rcx
  int v11; // edi
  __int64 v12; // rax
  int v13; // ebx
  WCHAR *v14; // rcx
  __int64 v15; // r9
  __int64 v16; // rdx
  __int64 v17; // rax
  __int64 v18; // r10
  WCHAR v19; // r8
  WCHAR *v20; // rax
  __int64 v21; // rcx
  WCHAR *v22; // rax
  __int64 v23; // rax
  WCHAR *v24; // rcx
  __int64 v25; // rdx
  char *v26; // r8
  WCHAR v27; // ax
  WCHAR *v28; // rax
  char ConfigFile; // al
  signed int result; // eax
  bool v31; // sf
  wchar_t Buffer[8]; // [rsp+40h] [rbp-298h] BYREF
  __int128 v33; // [rsp+50h] [rbp-288h]
  __int128 v34; // [rsp+60h] [rbp-278h]
  __int128 v35; // [rsp+70h] [rbp-268h]
  wchar_t pszPath[264]; // [rsp+80h] [rbp-258h] BYREF

  v5 = a4;
  memset_0(pszPath, 0, 0x208u);
  v8 = pszPath;
  v9 = *(_QWORD *)(a1 + 16) + 6680LL;
  *(_DWORD *)(a1 + 5032) = a2;
  v10 = 260;
  do
  {
    if ( !*v8 )
      break;
    ++v8;
    --v10;
  }
  while ( v10 );
  v11 = -2147024809;
  v12 = 260 - v10;
  v13 = -2147024809;
  if ( !v10 )
    goto LABEL_35;
  v14 = &pszPath[v12];
  v15 = 2147483646;
  v16 = 260 - v12;
  if ( v12 != 260 )
  {
    v17 = 2147483646;
    v18 = v9 - (_QWORD)v14;
    do
    {
      if ( !v17 )
        break;
      v19 = *(WCHAR *)((char *)v14 + v18);
      if ( !v19 )
        break;
      *v14 = v19;
      --v17;
      ++v14;
      --v16;
    }
    while ( v16 );
  }
  v20 = v14 - 1;
  v13 = -2147024774;
  if ( v16 )
  {
    v20 = v14;
    v13 = 0;
  }
  *v20 = 0;
  if ( v16 )
  {
    v21 = 260;
    v22 = pszPath;
    do
    {
      if ( !*v22 )
        break;
      ++v22;
      --v21;
    }
    while ( v21 );
    v23 = 260 - v21;
    if ( !v21 )
      goto LABEL_34;
    v24 = &pszPath[v23];
    v25 = 260 - v23;
    if ( v23 != 260 )
    {
      v26 = (char *)((char *)L"sqldumper.exe.config.xml" - (char *)v24);
      do
      {
        if ( !v15 )
          break;
        v27 = *(WCHAR *)((char *)v24 + (_QWORD)v26);
        if ( !v27 )
          break;
        *v24 = v27;
        --v15;
        ++v24;
        --v25;
      }
      while ( v25 );
    }
    v28 = v24 - 1;
    v11 = -2147024774;
    if ( v25 )
    {
      v28 = v24;
      v11 = 0;
    }
    *v28 = 0;
    if ( v25 )
    {
      if ( PathFileExistsW(pszPath) )
      {
        *(_OWORD *)Buffer = 0;
        v33 = 0;
        v34 = 0;
        v35 = 0;
        _itow_s(a2, Buffer, 0x20u, 10);
        ConfigFile = DumperConfig::XmlElementReadOrModify(pszPath, L"DumpUploadMode", Buffer, 0x104u, a3, v5, 1);
      }
      else
      {
        ConfigFile = DumperConfig::CreateConfigFile(pszPath, L"DumpUploadMode", a2, a3, v5);
      }
      if ( ConfigFile )
      {
        return 0;
      }
      else
      {
        result = GetLastError();
        v31 = result < 0;
        if ( result > 0 )
        {
          result = (unsigned __int16)result | 0x80070000;
          v31 = result < 0;
        }
        if ( !v31 )
          return -2147467259;
      }
    }
    else
    {
LABEL_34:
      StringCchPrintfW(a3, v5, L"StringCchCatW failed to construct dumper configuration file. Dumper dir path: %ls", v9);
      return v11;
    }
  }
  else
  {
LABEL_35:
    StringCchPrintfW(a3, v5, L"StringCchCatW failed to copy dumper dir path. : %ls", v9);
    return v13;
  }
  return result;
}

```

## disassembly

```asm
0x100443390  push    rbx
0x100443392  push    rbp
0x100443393  push    rsi
0x100443394  push    rdi
0x100443395  push    r14
0x100443397  push    r15
0x100443399  sub     rsp, 2A8h
0x1004433a0  mov     rax, cs:__security_cookie
0x1004433a7  xor     rax, rsp
0x1004433aa  mov     [rsp+2D8h+var_48], rax
0x1004433b2  mov     rsi, r8
0x1004433b5  movzx   ebp, r9w
0x1004433b9  mov     r14d, edx
0x1004433bc  mov     rbx, rcx
0x1004433bf  xor     edx, edx; Val
0x1004433c1  lea     rcx, [rsp+2D8h+pszPath]; void *
0x1004433c9  mov     r8d, 208h; Size
0x1004433cf  xor     r15d, r15d
0x1004433d2  call    memset_0
0x1004433d7  mov     r11, [rbx+10h]
0x1004433db  lea     rax, [rsp+2D8h+pszPath]
0x1004433e3  add     r11, 1A18h
0x1004433ea  mov     [rbx+13A8h], r14d
0x1004433f1  mov     ecx, 104h
0x1004433f6  cmp     [rax], r15w
0x1004433fa  jz      short loc_100443406
0x1004433fc  add     rax, 2
0x100443400  sub     rcx, 1
0x100443404  jnz     short loc_1004433F6
0x100443406  mov     eax, 104h
0x10044340b  mov     edi, 80070057h
0x100443410  sub     rax, rcx
0x100443413  mov     ebx, edi
0x100443415  test    rcx, rcx
0x100443418  cmovz   rax, r15
0x10044341c  cmovnz  ebx, r15d
0x100443420  jz      loc_1004435FC
0x100443426  mov     edx, 104h
0x10044342b  lea     rcx, [rsp+2D8h+pszPath]
0x100443433  lea     rcx, [rcx+rax*2]
0x100443437  mov     r9d, 7FFFFFFEh
0x10044343d  sub     rdx, rax
0x100443440  jz      short loc_100443471
0x100443442  mov     r10, r11
0x100443445  mov     eax, r9d
0x100443448  sub     r10, rcx
0x10044344b  nop     dword ptr [rax+rax+00h]
0x100443450  test    rax, rax
0x100443453  jz      short loc_100443471
0x100443455  movzx   r8d, word ptr [r10+rcx]
0x10044345a  test    r8w, r8w
0x10044345e  jz      short loc_100443471
0x100443460  mov     [rcx], r8w
0x100443464  dec     rax
0x100443467  add     rcx, 2
0x10044346b  sub     rdx, 1
0x10044346f  jnz     short loc_100443450
0x100443471  test    rdx, rdx
0x100443474  lea     rax, [rcx-2]
0x100443478  mov     ebx, 8007007Ah
0x10044347d  cmovnz  rax, rcx
0x100443481  cmovnz  ebx, r15d
0x100443485  mov     [rax], r15w
0x100443489  jz      loc_1004435FC
0x10044348f  mov     ecx, 104h
0x100443494  lea     rax, [rsp+2D8h+pszPath]
0x10044349c  nop     dword ptr [rax+00h]
0x1004434a0  cmp     [rax], r15w
0x1004434a4  jz      short loc_1004434B0
0x1004434a6  add     rax, 2
0x1004434aa  sub     rcx, 1
0x1004434ae  jnz     short loc_1004434A0
0x1004434b0  mov     eax, 104h
0x1004434b5  sub     rax, rcx
0x1004434b8  test    rcx, rcx
0x1004434bb  cmovz   rax, r15
0x1004434bf  cmovnz  edi, r15d
0x1004434c3  jz      loc_1004435E3
0x1004434c9  mov     edx, 104h
0x1004434ce  lea     rcx, [rsp+2D8h+pszPath]
0x1004434d6  lea     rcx, [rcx+rax*2]
0x1004434da  sub     rdx, rax
0x1004434dd  jz      short loc_10044350F
0x1004434df  lea     r8, aSqldumperExeCo; "sqldumper.exe.config.xml"
0x1004434e6  sub     r8, rcx
0x1004434e9  nop     dword ptr [rax+00000000h]
0x1004434f0  test    r9, r9
0x1004434f3  jz      short loc_10044350F
0x1004434f5  movzx   eax, word ptr [r8+rcx]
0x1004434fa  test    ax, ax
0x1004434fd  jz      short loc_10044350F
0x1004434ff  mov     [rcx], ax
0x100443502  dec     r9
0x100443505  add     rcx, 2
0x100443509  sub     rdx, 1
0x10044350d  jnz     short loc_1004434F0
0x10044350f  test    rdx, rdx
0x100443512  lea     rax, [rcx-2]
0x100443516  mov     edi, 8007007Ah
0x10044351b  cmovnz  rax, rcx
0x10044351f  cmovnz  edi, r15d
0x100443523  mov     [rax], r15w
0x100443527  jz      loc_1004435E3
0x10044352d  lea     rcx, [rsp+2D8h+pszPath]; pszPath
0x100443535  call    cs:__imp_PathFileExistsW
0x10044353b  test    eax, eax
0x10044353d  jz      short loc_10044359E
0x10044353f  xorps   xmm0, xmm0
0x100443542  lea     rdx, [rsp+2D8h+Buffer]; Buffer
0x100443547  mov     r9d, 0Ah; Radix
0x10044354d  mov     ecx, r14d; Value
0x100443550  movups  xmmword ptr [rsp+2D8h+Buffer], xmm0
0x100443555  movups  [rsp+2D8h+var_288], xmm0
0x10044355a  lea     r8d, [r9+16h]; BufferCount
0x10044355e  movups  [rsp+2D8h+var_278], xmm0
0x100443563  movups  [rsp+2D8h+var_268], xmm0
0x100443568  call    cs:__imp__itow_s
0x10044356e  mov     [rsp+2D8h+var_2A8], 1; bool
0x100443573  lea     r8, [rsp+2D8h+Buffer]; wchar_t *
0x100443578  mov     r9d, 104h; unsigned __int16
0x10044357e  mov     [rsp+2D8h+var_2B0], bp; unsigned __int16
0x100443583  lea     rdx, aDumpuploadmode; "DumpUploadMode"
0x10044358a  mov     [rsp+2D8h+var_2B8], rsi; wchar_t *
0x10044358f  lea     rcx, [rsp+2D8h+pszPath]; psz
0x100443597  call    ?XmlElementReadOrModify@DumperConfig@@CA_NPEB_W0PEA_WG1G_N@Z; DumperConfig::XmlElementReadOrModify(wchar_t const *,wchar_t const *,wchar_t *,ushort,wchar_t *,ushort,bool)
0x10044359c  jmp     short loc_1004435BD
0x10044359e  mov     r9, rsi; wchar_t *
0x1004435a1  mov     word ptr [rsp+2D8h+var_2B8], bp; unsigned __int16
0x1004435a6  mov     r8d, r14d; int
0x1004435a9  lea     rdx, aDumpuploadmode; "DumpUploadMode"
0x1004435b0  lea     rcx, [rsp+2D8h+pszPath]; lpFileName
0x1004435b8  call    ?CreateConfigFile@DumperConfig@@SA_NPEB_W0HPEA_WG@Z; DumperConfig::CreateConfigFile(wchar_t const *,wchar_t const *,int,wchar_t *,ushort)
0x1004435bd  test    al, al
0x1004435bf  jnz     short loc_1004435DE
0x1004435c1  call    cs:__imp_GetLastError
0x1004435c7  test    eax, eax
0x1004435c9  jle     short loc_1004435D5
0x1004435cb  movzx   eax, ax
0x1004435ce  or      eax, 80070000h
0x1004435d3  test    eax, eax
0x1004435d5  js      short loc_100443613
0x1004435d7  mov     eax, 80004005h
0x1004435dc  jmp     short loc_100443613
0x1004435de  mov     eax, r15d
0x1004435e1  jmp     short loc_100443613
0x1004435e3  mov     rdx, rbp; unsigned __int64
0x1004435e6  lea     r8, aStringcchcatwF_0; "StringCchCatW failed to construct dumpe"...
0x1004435ed  mov     r9, r11
0x1004435f0  mov     rcx, rsi; Buffer
0x1004435f3  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1004435f8  mov     eax, edi
0x1004435fa  jmp     short loc_100443613
0x1004435fc  mov     rdx, rbp; unsigned __int64
0x1004435ff  lea     r8, aStringcchcatwF; "StringCchCatW failed to copy dumper dir"...
0x100443606  mov     r9, r11
0x100443609  mov     rcx, rsi; Buffer
0x10044360c  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x100443611  mov     eax, ebx
0x100443613  mov     rcx, [rsp+2D8h+var_48]
0x10044361b  xor     rcx, rsp; StackCookie
0x10044361e  call    __security_check_cookie
0x100443623  add     rsp, 2A8h
0x10044362a  pop     r15
0x10044362c  pop     r14
0x10044362e  pop     rdi
0x10044362f  pop     rsi
0x100443630  pop     rbp
0x100443631  pop     rbx
0x100443632  retn
```
