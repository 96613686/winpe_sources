# BuildInstanceNameInit(void)

- ea: `0x100419fd0`
- end: `0x10041a394`
- name: `?BuildInstanceNameInit@@YAXXZ`
- size: `964`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1004115f0`
- `0x100416770`

## callees

- `0x100401580`
- `0x100419fd0`
- `0x10041d230`
- `0x10041eac0`
- `0x10044aad0`

## import_xrefs

- `KERNEL32!GetComputerNameExW` at `0x10041a237`
- `KERNEL32!GetComputerNameExW` at `0x10041a237`
- `KERNEL32!GetLastError` at `0x10041a2cb`
- `KERNEL32!GetLastError` at `0x10041a2cb`
- `sqlmin!?SetWin32ExitCode@@YAXK@Z` at `0x10041a07a`
- `sqlmin!?SetWin32ExitCode@@YAXK@Z` at `0x10041a11f`
- `sqlmin!?SetWin32ExitCode@@YAXK@Z` at `0x10041a1dc`
- `sqlmin!?SetWin32ExitCode@@YAXK@Z` at `0x10041a2e9`
- `sqlmin!?SetWin32ExitCode@@YAXK@Z` at `0x10041a07a`
- `sqlmin!?SetWin32ExitCode@@YAXK@Z` at `0x10041a11f`
- `sqlmin!?SetWin32ExitCode@@YAXK@Z` at `0x10041a1dc`
- `sqlmin!?SetWin32ExitCode@@YAXK@Z` at `0x10041a2e9`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x10041a080`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x10041a125`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x10041a1e2`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x10041a253`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x10041a2ef`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x10041a080`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x10041a125`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x10041a1e2`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x10041a253`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x10041a2ef`
- `api-ms-win-crt-string-l1-1-0!wcsncpy_s` at `0x10041a352`
- `api-ms-win-crt-string-l1-1-0!wcsncpy_s` at `0x10041a352`

## string_xrefs

- `0x10041a091`: `String copy failure (build server name)`
- `0x10041a136`: `String copy failure (build instance ID)`
- `0x10041a300`: `GetComputerNameEx() initialization failed. Aborting Initilialization`
- `0x10041a1e8`: `String copy failure (build instance name)`

## pseudocode

```c
void BuildInstanceNameInit(void)
{
  _WORD *v0; // rcx
  __int64 v1; // rdx
  signed __int64 v2; // r8
  __int16 v3; // ax
  _WORD *v4; // rax
  unsigned int v5; // ebp
  unsigned int v6; // edi
  struct __crt_locale_pointers *DefaultLocale; // rax
  int v8; // eax
  char *v9; // rcx
  _WORD *v10; // rcx
  __int64 v11; // rdx
  __int16 v12; // ax
  _WORD *v13; // rax
  unsigned int v14; // edi
  struct __crt_locale_pointers *v15; // rax
  int v16; // eax
  char *v17; // rcx
  __int64 v18; // rsi
  __int64 v19; // rax
  __int64 v20; // rdx
  _WORD *v21; // rcx
  signed __int64 v22; // rbx
  __int16 v23; // ax
  _WORD *v24; // rax
  struct __crt_locale_pointers *v25; // rax
  int v26; // eax
  char *v27; // rcx
  RESOURCE *v28; // rbx
  char *v29; // rdi
  __crt_locale_pointers *Locale; // rax
  char *v31; // rcx
  signed int LastError; // eax
  int v33; // ebx
  struct __crt_locale_pointers *v34; // rax
  int v35; // eax
  char *v36; // rcx
  __int64 v37; // [rsp+28h] [rbp-960h]
  unsigned int v38; // [rsp+28h] [rbp-960h]
  DWORD nSize[4]; // [rsp+40h] [rbp-948h] BYREF
  WCHAR Buffer[136]; // [rsp+50h] [rbp-938h] BYREF
  char v41[512]; // [rsp+160h] [rbp-828h] BYREF
  char v42[512]; // [rsp+360h] [rbp-628h] BYREF
  char v43[512]; // [rsp+560h] [rbp-428h] BYREF
  char v44[512]; // [rsp+760h] [rbp-228h] BYREF

  v0 = (_WORD *)((char *)qword_10049F360 + 43256);
  nSize[0] = 130;
  v1 = 261;
  v2 = (char *)L"MKMASTR" - ((char *)qword_10049F360 + 43256);
  do
  {
    if ( v1 == -2147483385 )
      break;
    v3 = *(_WORD *)((char *)v0 + v2);
    if ( !v3 )
      break;
    *v0++ = v3;
    --v1;
  }
  while ( v1 );
  v4 = v0 - 1;
  v5 = -2147024774;
  if ( v1 )
    v4 = v0;
  v6 = -2147024774;
  if ( v1 )
    v6 = 0;
  *v4 = 0;
  if ( !v1 )
  {
    _mm_lfence();
    SetWin32ExitCode(v6);
    DefaultLocale = GetDefaultLocale();
    v38 = v6;
    v8 = StringCchPrintf_lA(
           v41,
           0x200u,
           "%hs (HRESULT 0x%x)",
           DefaultLocale,
           "String copy failure (build server name)",
           v38);
    v9 = "String copy failure (build server name)";
    if ( v8 >= 0 )
      v9 = v41;
    FailAndExit(v9);
  }
  v10 = &GlobalInstanceId;
  v11 = 39;
  do
  {
    if ( v11 == -2147483607 )
      break;
    v12 = *(_WORD *)((char *)v10 + (char *)L"MKMASTR" - (char *)&GlobalInstanceId);
    if ( !v12 )
      break;
    *v10++ = v12;
    --v11;
  }
  while ( v11 );
  v13 = v10 - 1;
  v14 = -2147024774;
  if ( v11 )
  {
    v13 = v10;
    v14 = 0;
  }
  *v13 = 0;
  if ( !v11 )
  {
    _mm_lfence();
    SetWin32ExitCode(v14);
    v15 = GetDefaultLocale();
    LODWORD(v37) = v14;
    v16 = StringCchPrintf_lA(v42, 0x200u, "%hs (HRESULT 0x%x)", v15, "String copy failure (build instance ID)", v37);
    v17 = "String copy failure (build instance ID)";
    if ( v16 >= 0 )
      v17 = v42;
    FailAndExit(v17);
  }
  v18 = -1;
  v19 = -1;
  do
    ++v19;
  while ( *((_WORD *)&GlobalInstanceId + v19) );
  v20 = 261;
  v21 = (_WORD *)((char *)qword_10049F360 + 43778);
  dword_1004A3830 = v19;
  v22 = (char *)L"MKMASTR" - ((char *)qword_10049F360 + 43778);
  do
  {
    if ( v20 == -2147483385 )
      break;
    v23 = *(_WORD *)((char *)v21 + v22);
    if ( !v23 )
      break;
    *v21++ = v23;
    --v20;
  }
  while ( v20 );
  v24 = v21 - 1;
  if ( v20 )
  {
    v24 = v21;
    v5 = 0;
  }
  *v24 = 0;
  if ( !v20 )
  {
    _mm_lfence();
    SetWin32ExitCode(v5);
    v25 = GetDefaultLocale();
    LODWORD(v37) = v5;
    v26 = StringCchPrintf_lA(v43, 0x200u, "%hs (HRESULT 0x%x)", v25, "String copy failure (build instance name)", v37);
    v27 = "String copy failure (build instance name)";
    if ( v26 >= 0 )
      v27 = v43;
    FailAndExit(v27);
  }
  if ( GetComputerNameExW(ComputerNameDnsHostname, Buffer, nSize) )
  {
    v28 = qword_10049F360;
    v29 = (char *)qword_10049F360 + 43778;
    Locale = GetDefaultLocale();
    snwprintf_s_l((wchar_t *const)v28 + 22672, 0x105u, 0x105u, L"%ls\\%ls", Locale, Buffer, v29);
    *((_WORD *)qword_10049F360 + 22932) = 0;
    v31 = (char *)qword_10049F360 + 45344;
    *((_QWORD *)qword_10049F360 + 1466) = (char *)qword_10049F360 + 45344;
    do
      ++v18;
    while ( *(_WORD *)&v31[2 * v18] );
    *((_DWORD *)qword_10049F360 + 2934) = 2 * v18;
  }
  else
  {
    LastError = GetLastError();
    v33 = LastError;
    if ( LastError > 0 )
      v33 = (unsigned __int16)LastError | 0x80070000;
    if ( v33 < 0 )
    {
      _mm_lfence();
      SetWin32ExitCode(v33);
      v34 = GetDefaultLocale();
      LODWORD(v37) = v33;
      v35 = StringCchPrintf_lA(
              v44,
              0x200u,
              "%hs (HRESULT 0x%x)",
              v34,
              "GetComputerNameEx() initialization failed. Aborting Initilialization",
              v37);
      v36 = "GetComputerNameEx() initialization failed. Aborting Initilialization";
      if ( v35 >= 0 )
        v36 = v44;
      FailAndExit(v36);
    }
  }
  wcsncpy_s((wchar_t *)qword_10049F360 + 23194, 0x105u, (const wchar_t *)qword_10049F360 + 21889, 0x105u);
  *((_WORD *)qword_10049F360 + 23454) = 0;
}

```

## disassembly

```asm
0x100419fd0  mov     [rsp+arg_0], rbx
0x100419fd5  mov     [rsp+arg_8], rbp
0x100419fda  mov     [rsp+arg_10], rsi
0x100419fdf  push    rdi
0x100419fe0  push    r14
0x100419fe2  push    r15
0x100419fe4  sub     rsp, 970h
0x100419feb  mov     rax, cs:__security_cookie
0x100419ff2  xor     rax, rsp
0x100419ff5  mov     [rsp+988h+var_28], rax
0x100419ffd  mov     rcx, cs:qword_10049F360
0x10041a004  lea     rbx, aMkmastr; "MKMASTR"
0x10041a00b  add     rcx, 0A8F8h
0x10041a012  mov     [rsp+988h+nSize], 82h
0x10041a01a  mov     r8, rbx
0x10041a01d  mov     edx, 105h
0x10041a022  sub     r8, rcx
0x10041a025  nop     word ptr [rax+rax+00000000h]
0x10041a030  lea     rax, [rdx+7FFFFEF9h]
0x10041a037  test    rax, rax
0x10041a03a  jz      short loc_10041A053
0x10041a03c  movzx   eax, word ptr [r8+rcx]
0x10041a041  test    ax, ax
0x10041a044  jz      short loc_10041A053
0x10041a046  mov     [rcx], ax
0x10041a049  add     rcx, 2
0x10041a04d  sub     rdx, 1
0x10041a051  jnz     short loc_10041A030
0x10041a053  test    rdx, rdx
0x10041a056  lea     rax, [rcx-2]
0x10041a05a  mov     ebp, 8007007Ah
0x10041a05f  cmovnz  rax, rcx
0x10041a063  mov     edi, ebp
0x10041a065  xor     r15d, r15d
0x10041a068  test    rdx, rdx
0x10041a06b  cmovnz  edi, r15d
0x10041a06f  mov     [rax], r15w
0x10041a073  jnz     short loc_10041A0C6
0x10041a075  lfence
0x10041a078  mov     ecx, edi
0x10041a07a  call    cs:__imp_?SetWin32ExitCode@@YAXK@Z; SetWin32ExitCode(ulong)
0x10041a080  call    cs:__imp_?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ; GetDefaultLocale(void)
0x10041a086  mov     dword ptr [rsp+988h+var_960], edi
0x10041a08a  lea     r8, aHsHresult0xX; "%hs (HRESULT 0x%x)"
0x10041a091  lea     rdi, aStringCopyFail_5; "String copy failure (build server name)"
0x10041a098  mov     r9, rax; struct __crt_locale_pointers *
0x10041a09b  mov     edx, 200h; unsigned __int64
0x10041a0a0  mov     [rsp+988h+Locale], rdi
0x10041a0a5  lea     rcx, [rsp+988h+var_828]; Buffer
0x10041a0ad  call    ?StringCchPrintf_lA@@YAJPEAD_KPEBDPEAU__crt_locale_pointers@@ZZ; StringCchPrintf_lA(char *,unsigned __int64,char const *,__crt_locale_pointers *,...)
0x10041a0b2  mov     rcx, rdi
0x10041a0b5  test    eax, eax
0x10041a0b7  js      short loc_10041A0C1
0x10041a0b9  lea     rcx, [rsp+988h+var_828]; char *
0x10041a0c1  call    ?FailAndExit@@YAXPEBD@Z; FailAndExit(char const *)
0x10041a0c6  lea     r14, ?GlobalInstanceId@@3U_INST_ID@@A; _INST_ID GlobalInstanceId
0x10041a0cd  mov     r8, rbx
0x10041a0d0  mov     rcx, r14
0x10041a0d3  sub     r8, r14
0x10041a0d6  mov     edx, 27h ; '''
0x10041a0db  nop     dword ptr [rax+rax+00h]
0x10041a0e0  lea     rax, [rdx+7FFFFFD7h]
0x10041a0e7  test    rax, rax
0x10041a0ea  jz      short loc_10041A103
0x10041a0ec  movzx   eax, word ptr [r8+rcx]
0x10041a0f1  test    ax, ax
0x10041a0f4  jz      short loc_10041A103
0x10041a0f6  mov     [rcx], ax
0x10041a0f9  add     rcx, 2
0x10041a0fd  sub     rdx, 1
0x10041a101  jnz     short loc_10041A0E0
0x10041a103  test    rdx, rdx
0x10041a106  lea     rax, [rcx-2]
0x10041a10a  mov     edi, ebp
0x10041a10c  cmovnz  rax, rcx
0x10041a110  cmovnz  edi, r15d
0x10041a114  mov     [rax], r15w
0x10041a118  jnz     short loc_10041A16B
0x10041a11a  lfence
0x10041a11d  mov     ecx, edi
0x10041a11f  call    cs:__imp_?SetWin32ExitCode@@YAXK@Z; SetWin32ExitCode(ulong)
0x10041a125  call    cs:__imp_?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ; GetDefaultLocale(void)
0x10041a12b  mov     dword ptr [rsp+988h+var_960], edi
0x10041a12f  lea     r8, aHsHresult0xX; "%hs (HRESULT 0x%x)"
0x10041a136  lea     rdi, aStringCopyFail_2; "String copy failure (build instance ID)"
0x10041a13d  mov     r9, rax; struct __crt_locale_pointers *
0x10041a140  mov     edx, 200h; unsigned __int64
0x10041a145  mov     [rsp+988h+Locale], rdi
0x10041a14a  lea     rcx, [rsp+988h+var_628]; Buffer
0x10041a152  call    ?StringCchPrintf_lA@@YAJPEAD_KPEBDPEAU__crt_locale_pointers@@ZZ; StringCchPrintf_lA(char *,unsigned __int64,char const *,__crt_locale_pointers *,...)
0x10041a157  mov     rcx, rdi
0x10041a15a  test    eax, eax
0x10041a15c  js      short loc_10041A166
0x10041a15e  lea     rcx, [rsp+988h+var_628]; char *
0x10041a166  call    ?FailAndExit@@YAXPEBD@Z; FailAndExit(char const *)
0x10041a16b  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x10041a172  mov     rax, rsi
0x10041a175  inc     rax
0x10041a178  cmp     [r14+rax*2], r15w
0x10041a17d  jnz     short loc_10041A175
0x10041a17f  mov     rcx, cs:qword_10049F360
0x10041a186  mov     edx, 105h
0x10041a18b  add     rcx, 0AB02h
0x10041a192  mov     cs:dword_1004A3830, eax
0x10041a198  sub     rbx, rcx
0x10041a19b  nop     dword ptr [rax+rax+00h]
0x10041a1a0  lea     rax, [rdx+7FFFFEF9h]
0x10041a1a7  test    rax, rax
0x10041a1aa  jz      short loc_10041A1C2
0x10041a1ac  movzx   eax, word ptr [rbx+rcx]
0x10041a1b0  test    ax, ax
0x10041a1b3  jz      short loc_10041A1C2
0x10041a1b5  mov     [rcx], ax
0x10041a1b8  add     rcx, 2
0x10041a1bc  sub     rdx, 1
0x10041a1c0  jnz     short loc_10041A1A0
0x10041a1c2  test    rdx, rdx
0x10041a1c5  lea     rax, [rcx-2]
0x10041a1c9  cmovnz  rax, rcx
0x10041a1cd  cmovnz  ebp, r15d
0x10041a1d1  mov     [rax], r15w
0x10041a1d5  jnz     short loc_10041A228
0x10041a1d7  lfence
0x10041a1da  mov     ecx, ebp
0x10041a1dc  call    cs:__imp_?SetWin32ExitCode@@YAXK@Z; SetWin32ExitCode(ulong)
0x10041a1e2  call    cs:__imp_?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ; GetDefaultLocale(void)
0x10041a1e8  lea     rbx, aStringCopyFail_3; "String copy failure (build instance nam"...
0x10041a1ef  mov     dword ptr [rsp+988h+var_960], ebp
0x10041a1f3  mov     r9, rax; struct __crt_locale_pointers *
0x10041a1f6  mov     [rsp+988h+Locale], rbx
0x10041a1fb  lea     r8, aHsHresult0xX; "%hs (HRESULT 0x%x)"
0x10041a202  mov     edx, 200h; unsigned __int64
0x10041a207  lea     rcx, [rsp+988h+var_428]; Buffer
0x10041a20f  call    ?StringCchPrintf_lA@@YAJPEAD_KPEBDPEAU__crt_locale_pointers@@ZZ; StringCchPrintf_lA(char *,unsigned __int64,char const *,__crt_locale_pointers *,...)
0x10041a214  mov     rcx, rbx
0x10041a217  test    eax, eax
0x10041a219  js      short loc_10041A223
0x10041a21b  lea     rcx, [rsp+988h+var_428]; char *
0x10041a223  call    ?FailAndExit@@YAXPEBD@Z; FailAndExit(char const *)
0x10041a228  lea     r8, [rsp+988h+nSize]; nSize
0x10041a22d  mov     ecx, 1; NameType
0x10041a232  lea     rdx, [rsp+988h+Buffer]; lpBuffer
0x10041a237  call    cs:__imp_GetComputerNameExW
0x10041a23d  test    eax, eax
0x10041a23f  jz      loc_10041A2CB
0x10041a245  mov     rbx, cs:qword_10049F360
0x10041a24c  lea     rdi, [rbx+0AB02h]
0x10041a253  call    cs:__imp_?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ; GetDefaultLocale(void)
0x10041a259  lea     rdx, [rsp+988h+Buffer]
0x10041a25e  mov     [rsp+988h+var_958], rdi
0x10041a263  mov     [rsp+988h+var_960], rdx
0x10041a268  lea     rcx, [rbx+0B120h]; Buffer
0x10041a26f  mov     edx, 105h; BufferCount
0x10041a274  mov     [rsp+988h+Locale], rax; Locale
0x10041a279  mov     r8d, edx; MaxCount
0x10041a27c  lea     r9, aLsLs_1; "%ls\\%ls"
0x10041a283  call    _snwprintf_s_l
0x10041a288  mov     rax, cs:qword_10049F360
0x10041a28f  mov     [rax+0B328h], r15w
0x10041a297  mov     rax, cs:qword_10049F360
0x10041a29e  lea     rcx, [rax+0B120h]
0x10041a2a5  mov     [rax+2DD0h], rcx
0x10041a2ac  nop     dword ptr [rax+00h]
0x10041a2b0  inc     rsi
0x10041a2b3  cmp     [rcx+rsi*2], r15w
0x10041a2b8  jnz     short loc_10041A2B0
0x10041a2ba  mov     rax, cs:qword_10049F360
0x10041a2c1  add     esi, esi
0x10041a2c3  mov     [rax+2DD8h], esi
0x10041a2c9  jmp     short loc_10041A335
0x10041a2cb  call    cs:__imp_GetLastError
0x10041a2d1  mov     ebx, eax
0x10041a2d3  test    eax, eax
0x10041a2d5  jle     short loc_10041A2E0
0x10041a2d7  movzx   ebx, ax
0x10041a2da  or      ebx, 80070000h
0x10041a2e0  test    ebx, ebx
0x10041a2e2  jns     short loc_10041A335
0x10041a2e4  lfence
0x10041a2e7  mov     ecx, ebx
0x10041a2e9  call    cs:__imp_?SetWin32ExitCode@@YAXK@Z; SetWin32ExitCode(ulong)
0x10041a2ef  call    cs:__imp_?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ; GetDefaultLocale(void)
0x10041a2f5  mov     dword ptr [rsp+988h+var_960], ebx
0x10041a2f9  lea     r8, aHsHresult0xX; "%hs (HRESULT 0x%x)"
0x10041a300  lea     rbx, aGetcomputernam_0; "GetComputerNameEx() initialization fail"...
0x10041a307  mov     r9, rax; struct __crt_locale_pointers *
0x10041a30a  mov     edx, 200h; unsigned __int64
0x10041a30f  mov     [rsp+988h+Locale], rbx
0x10041a314  lea     rcx, [rsp+988h+var_228]; Buffer
0x10041a31c  call    ?StringCchPrintf_lA@@YAJPEAD_KPEBDPEAU__crt_locale_pointers@@ZZ; StringCchPrintf_lA(char *,unsigned __int64,char const *,__crt_locale_pointers *,...)
0x10041a321  mov     rcx, rbx
0x10041a324  test    eax, eax
0x10041a326  js      short loc_10041A330
0x10041a328  lea     rcx, [rsp+988h+var_228]; char *
0x10041a330  call    ?FailAndExit@@YAXPEBD@Z; FailAndExit(char const *)
0x10041a335  mov     rcx, cs:qword_10049F360
0x10041a33c  mov     edx, 105h; SizeInWords
0x10041a341  mov     r9d, edx; MaxCount
0x10041a344  lea     r8, [rcx+0AB02h]; Source
0x10041a34b  add     rcx, 0B534h; Destination
0x10041a352  call    cs:__imp_wcsncpy_s
0x10041a358  mov     rax, cs:qword_10049F360
0x10041a35f  mov     [rax+0B73Ch], r15w
0x10041a367  mov     rcx, [rsp+988h+var_28]
0x10041a36f  xor     rcx, rsp; StackCookie
0x10041a372  call    __security_check_cookie
0x10041a377  lea     r11, [rsp+988h+var_18]
0x10041a37f  mov     rbx, [r11+20h]
0x10041a383  mov     rbp, [r11+28h]
0x10041a387  mov     rsi, [r11+30h]
0x10041a38b  mov     rsp, r11
0x10041a38e  pop     r15
0x10041a390  pop     r14
0x10041a392  pop     rdi
0x10041a393  retn
```
