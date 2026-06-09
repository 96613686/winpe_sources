# CHttpPolicyExtensionEntry::Initialize(void)

- ea: `0x18006e73c`
- end: `0x18006ebb6`
- name: `?Initialize@CHttpPolicyExtensionEntry@@QEAAHXZ`
- size: `1146`
- prototype: `__int64 __fastcall(CHttpPolicyExtensionEntry *__hidden this)`
- caller_count: `2`
- callee_count: `16`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18006e610`
- `0x18006e6d0`

## callees

- `0x18006e73c`
- `0x18006ebbc`
- `0x18006ede4`
- `0x1800a1d10`
- `0x1800a2660`
- `0x1800ab418`
- `0x1800ab48c`
- `0x1800c82d0`
- `0x1800c830c`
- `0x1800cf008`
- `0x1800cf4c4`
- `0x1800d06a4`
- `0x1800d06fc`
- `0x1800db6b0`
- `0x1800db704`
- `0x1800de010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18006e9b7`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18006e9b7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18006e9f6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18006ea2e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18006e9f6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18006ea2e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006e94a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006ea13`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006ea4e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006eb1e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006e94a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006ea13`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006ea4e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006eb1e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006eb82`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006eb82`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18006e929`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18006e929`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18006e9a3`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18006e9a3`

## string_xrefs

- `0x18006e9eb`: `HttpPolicyExtensionInit`
- `0x18006ea23`: `HttpPolicyExtensionShutdown`

## pseudocode

```c
__int64 __fastcall CHttpPolicyExtensionEntry::Initialize(CHttpPolicyExtensionEntry *this)
{
  __int64 FileW; // rbx
  size_t v3; // r9
  unsigned int v4; // r11d
  __int64 v5; // rcx
  HRESULT v6; // esi
  size_t *v7; // r8
  bool v8; // sf
  DWORD LastError; // eax
  __int64 v10; // rdx
  __int64 v11; // r9
  int v12; // eax
  signed int v13; // esi
  HMODULE LibraryW; // rax
  HMODULE v15; // rcx
  DWORD dwCreationDisposition[2]; // [rsp+20h] [rbp-2B8h]
  DWORD dwCreationDispositiona[2]; // [rsp+20h] [rbp-2B8h]
  unsigned int v19; // [rsp+40h] [rbp-298h]
  size_t pcchDestLength; // [rsp+50h] [rbp-288h] BYREF
  unsigned int v21; // [rsp+58h] [rbp-280h]
  signed int v22; // [rsp+60h] [rbp-278h]
  int v23; // [rsp+64h] [rbp-274h]
  FARPROC ProcAddress; // [rsp+68h] [rbp-270h]
  int v25; // [rsp+70h] [rbp-268h]
  __int64 v26; // [rsp+78h] [rbp-260h]
  CHttpPolicyExtensionEntry *v27; // [rsp+80h] [rbp-258h]
  FARPROC v28; // [rsp+88h] [rbp-250h]
  _DWORD v29[4]; // [rsp+90h] [rbp-248h] BYREF
  wchar_t pszDest[37]; // [rsp+A0h] [rbp-238h] BYREF
  _BYTE v31[454]; // [rsp+EAh] [rbp-1EEh] BYREF

  v27 = this;
  v23 = 0;
  FileW = -1;
  wcscpy(pszDest, L"SOFTWARE\\Policies\\Microsofindows\\");
  memset_0(v31, 0, 0x1BEu);
  v29[0] = 0;
  if ( (BYTE1(xmmword_180107A60) & 0x40) != 0 )
    WPP_SF_(1038, 11, WPP_70a6ea6fbc8b32957ec072c0c9e35dfc_Traceguids);
  if ( !**((_DWORD **)this + 3) )
  {
    v19 = 0;
    pcchDestLength = 0;
    v6 = StringValidateDestAndLengthW(pszDest, 0x104u, &pcchDestLength, v3);
    if ( v6 >= 0 )
      v6 = StringCopyWorkerW(
             &pszDest[pcchDestLength],
             260 - pcchDestLength,
             v7,
             *((STRSAFE_PCNZWCH *)this + 6),
             *(size_t *)dwCreationDisposition);
    v8 = v6 < 0;
    if ( v6 > 0 )
      v8 = 1;
    if ( v8 )
    {
      v23 = 99;
      goto LABEL_47;
    }
    if ( (int)WxRegValuesExist(v5, pszDest, v29) < 0 || !v29[0] )
    {
      if ( (BYTE1(xmmword_180107A60) & 0x40) != 0 )
        WPP_SF_SS(
          1038,
          13,
          (unsigned int)WPP_70a6ea6fbc8b32957ec072c0c9e35dfc_Traceguids,
          *((_QWORD *)this + 6),
          *((_QWORD *)this + 4));
      goto LABEL_46;
    }
    v19 = 1;
    v25 = 1;
    if ( (BYTE1(xmmword_180107A60) & 0x40) != 0 )
      WPP_SF_S(1038, 14, WPP_70a6ea6fbc8b32957ec072c0c9e35dfc_Traceguids, *((_QWORD *)this + 4));
    pcchDestLength = (size_t)this + 32;
    FileW = (__int64)CreateFileW(*((LPCWSTR *)this + 4), 0x80000000, 1u, 0, 3u, 0, 0);
    v26 = FileW;
    if ( FileW == -1 )
    {
      if ( (BYTE1(xmmword_180107A60) & 0x40) != 0 )
      {
        LastError = GetLastError();
        v10 = 15;
LABEL_20:
        v11 = LastError;
LABEL_21:
        WPP_SF_d(1038, v10, WPP_70a6ea6fbc8b32957ec072c0c9e35dfc_Traceguids, v11, *(_QWORD *)dwCreationDispositiona);
      }
    }
    else
    {
      v12 = WxVerifyMicrosoftSignedEx(*(_QWORD *)pcchDestLength, *((_DWORD *)this + 4));
      v13 = v12;
      if ( v12 > 0 )
        v13 = (unsigned __int16)v12 | 0x80070000;
      v22 = v13;
      if ( v13 < 0 )
      {
        v23 = 145;
        goto LABEL_46;
      }
      LibraryW = LoadLibraryW(*(LPCWSTR *)pcchDestLength);
      ProcAddress = (FARPROC)LibraryW;
      v15 = (HMODULE)*((_QWORD *)this + 8);
      if ( v15 )
      {
        FreeLibrary(v15);
        LibraryW = (HMODULE)ProcAddress;
      }
      *((_QWORD *)this + 8) = LibraryW;
      if ( !LibraryW )
      {
        if ( (BYTE1(xmmword_180107A60) & 0x40) == 0 )
          goto LABEL_46;
        LastError = GetLastError();
        v10 = 16;
        goto LABEL_20;
      }
      if ( (BYTE1(xmmword_180107A60) & 0x40) != 0 )
        WPP_SF_q(1038, 17, WPP_70a6ea6fbc8b32957ec072c0c9e35dfc_Traceguids);
      ProcAddress = GetProcAddress(*((HMODULE *)this + 8), "HttpPolicyExtensionInit");
      if ( !ProcAddress )
      {
        if ( (BYTE1(xmmword_180107A60) & 0x40) == 0 )
          goto LABEL_46;
        LastError = GetLastError();
        v10 = 18;
        goto LABEL_20;
      }
      v28 = GetProcAddress(*((HMODULE *)this + 8), "HttpPolicyExtensionShutdown");
      if ( !v28 )
      {
        if ( (BYTE1(xmmword_180107A60) & 0x40) == 0 )
          goto LABEL_46;
        LastError = GetLastError();
        v10 = 19;
        goto LABEL_20;
      }
      v21 = 0;
      v21 = ((__int64 (__fastcall *)(__int64, _QWORD, _QWORD, _QWORD))ProcAddress)(1, *((unsigned int *)this + 5), 0, 0);
      v11 = v21;
      if ( !v21 )
      {
        *((_QWORD *)this + 9) = ProcAddress;
        *((_QWORD *)this + 10) = v28;
        if ( (BYTE1(xmmword_180107A60) & 0x40) != 0 )
          WPP_SF_S(1038, 21, WPP_70a6ea6fbc8b32957ec072c0c9e35dfc_Traceguids, *(_QWORD *)pcchDestLength);
        goto LABEL_46;
      }
      if ( (BYTE1(xmmword_180107A60) & 0x40) != 0 )
      {
        v10 = 20;
        goto LABEL_21;
      }
    }
LABEL_46:
    v4 = v19;
    goto LABEL_47;
  }
  if ( (BYTE1(xmmword_180107A60) & 0x40) != 0 )
    WPP_SF_S(1038, 12, WPP_70a6ea6fbc8b32957ec072c0c9e35dfc_Traceguids, *((_QWORD *)this + 4));
  v4 = 1;
  v19 = 1;
LABEL_47:
  if ( (BYTE1(xmmword_180107A60) & 0x40) != 0 )
    WPP_SF_Dd(1038, 22, WPP_70a6ea6fbc8b32957ec072c0c9e35dfc_Traceguids, v4);
  if ( FileW != -1 )
    CloseHandle((HANDLE)FileW);
  return v19;
}

```

## disassembly

```asm
0x18006e73c  mov     [rsp+arg_8], rbx
0x18006e741  mov     [rsp+arg_10], rsi
0x18006e746  push    r12
0x18006e748  push    r14
0x18006e74a  push    r15
0x18006e74c  sub     rsp, 2C0h
0x18006e753  mov     rax, cs:__security_cookie
0x18006e75a  xor     rax, rsp
0x18006e75d  mov     [rsp+2D8h+var_28], rax
0x18006e765  mov     r14, rcx
0x18006e768  mov     [rsp+2D8h+var_258], rcx
0x18006e770  xor     esi, esi
0x18006e772  mov     [rsp+2D8h+var_274], esi
0x18006e776  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18006e77a  movaps  xmm0, xmmword ptr cs:aSoftwarePolici_3; "SOFTWARE\\Policies\\Microsoft\\Windows"...
0x18006e781  movaps  xmmword ptr [rsp+2D8h+pszDest], xmm0
0x18006e789  movaps  xmm1, xmmword ptr cs:aSoftwarePolici_3+10h; "\\Policies\\Microsoft\\Windows\\"
0x18006e790  movaps  [rsp+2D8h+var_228], xmm1
0x18006e798  movaps  xmm0, xmmword ptr cs:aSoftwarePolici_3+20h; "s\\Microsoft\\Windows\\"
0x18006e79f  movaps  [rsp+2D8h+var_218], xmm0
0x18006e7a7  movaps  xmm1, xmmword ptr cs:aSoftwarePolici_3+30h; "oft\\Windows\\"
0x18006e7ae  movaps  [rsp+2D8h+var_208], xmm1
0x18006e7b6  movups  xmm0, xmmword ptr cs:aSoftwarePolici_3+3Ah; "indows\\"
0x18006e7bd  movups  [rsp+2D8h+var_208+0Ah], xmm0
0x18006e7c5  xor     edx, edx; Val
0x18006e7c7  mov     r8d, 1BEh; Size
0x18006e7cd  lea     rcx, [rsp+2D8h+var_1EE]; void *
0x18006e7d5  call    memset_0
0x18006e7da  mov     [rsp+2D8h+var_248], esi
0x18006e7e1  mov     r15d, 40Eh
0x18006e7e7  lea     r12, WPP_70a6ea6fbc8b32957ec072c0c9e35dfc_Traceguids
0x18006e7ee  test    byte ptr cs:xmmword_180107A60+1, 40h
0x18006e7f5  jz      short loc_18006E805
0x18006e7f7  lea     edx, [rsi+0Bh]
0x18006e7fa  mov     ecx, r15d
0x18006e7fd  mov     r8, r12
0x18006e800  call    WPP_SF_
0x18006e805  mov     rax, [r14+18h]
0x18006e809  cmp     [rax], esi
0x18006e80b  jz      short loc_18006E83A
0x18006e80d  test    byte ptr cs:xmmword_180107A60+1, 40h
0x18006e814  jz      short loc_18006E82A
0x18006e816  mov     edx, 0Ch
0x18006e81b  mov     ecx, r15d
0x18006e81e  mov     r9, [r14+20h]
0x18006e822  mov     r8, r12
0x18006e825  call    WPP_SF_S
0x18006e82a  mov     r11d, 1
0x18006e830  mov     [rsp+2D8h+var_298], r11d
0x18006e835  jmp     loc_18006EB59
0x18006e83a  xor     r11d, r11d
0x18006e83d  mov     [rsp+2D8h+var_298], r11d
0x18006e842  mov     [rsp+2D8h+pcchDestLength], rsi
0x18006e847  lea     r8, [rsp+2D8h+pcchDestLength]; pcchDestLength
0x18006e84c  mov     edx, 104h; cchDest
0x18006e851  lea     rcx, [rsp+2D8h+pszDest]; pszDest
0x18006e859  call    StringValidateDestAndLengthW
0x18006e85e  mov     esi, eax
0x18006e860  test    eax, eax
0x18006e862  js      short loc_18006E888
0x18006e864  mov     rax, [rsp+2D8h+pcchDestLength]
0x18006e869  mov     edx, 104h
0x18006e86e  sub     rdx, rax; cchDest
0x18006e871  lea     rcx, [rsp+2D8h+pszDest]
0x18006e879  lea     rcx, [rcx+rax*2]; pszDest
0x18006e87d  mov     r9, [r14+30h]; pszSrc
0x18006e881  call    StringCopyWorkerW
0x18006e886  mov     esi, eax
0x18006e888  test    esi, esi
0x18006e88a  jle     short loc_18006E897
0x18006e88c  movzx   esi, si
0x18006e88f  or      esi, 80070000h
0x18006e895  test    esi, esi
0x18006e897  jns     short loc_18006E8A6
0x18006e899  mov     [rsp+2D8h+var_274], 63h ; 'c'
0x18006e8a1  jmp     loc_18006EB59
0x18006e8a6  lea     r8, [rsp+2D8h+var_248]
0x18006e8ae  lea     rdx, [rsp+2D8h+pszDest]
0x18006e8b6  call    WxRegValuesExist
0x18006e8bb  test    eax, eax
0x18006e8bd  js      loc_18006EB2E
0x18006e8c3  cmp     [rsp+2D8h+var_248], 0
0x18006e8cb  jz      loc_18006EB2E
0x18006e8d1  mov     ebx, 1
0x18006e8d6  mov     [rsp+2D8h+var_298], ebx
0x18006e8da  mov     [rsp+2D8h+var_268], ebx
0x18006e8de  test    byte ptr cs:xmmword_180107A60+1, 40h
0x18006e8e5  jz      short loc_18006E8F9
0x18006e8e7  lea     edx, [rbx+0Dh]
0x18006e8ea  mov     ecx, r15d
0x18006e8ed  mov     r9, [r14+20h]
0x18006e8f1  mov     r8, r12
0x18006e8f4  call    WPP_SF_S
0x18006e8f9  lea     rax, [r14+20h]
0x18006e8fd  mov     [rsp+2D8h+pcchDestLength], rax
0x18006e902  mov     [rsp+2D8h+hTemplateFile], 0; hTemplateFile
0x18006e90b  mov     [rsp+2D8h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x18006e913  mov     [rsp+2D8h+dwCreationDisposition], 3; dwCreationDisposition
0x18006e91b  xor     r9d, r9d; lpSecurityAttributes
0x18006e91e  mov     r8d, ebx; dwShareMode
0x18006e921  mov     edx, 80000000h; dwDesiredAccess
0x18006e926  mov     rcx, [rax]; lpFileName
0x18006e929  call    cs:__imp_CreateFileW
0x18006e92f  mov     rbx, rax
0x18006e932  mov     [rsp+2D8h+var_260], rax
0x18006e937  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18006e93b  jnz     short loc_18006E966
0x18006e93d  test    byte ptr cs:xmmword_180107A60+1, 40h
0x18006e944  jz      loc_18006EB54
0x18006e94a  call    cs:__imp_GetLastError
0x18006e950  lea     edx, [rbx+10h]
0x18006e953  mov     r9d, eax
0x18006e956  mov     ecx, r15d
0x18006e959  mov     r8, r12
0x18006e95c  call    WPP_SF_d
0x18006e961  jmp     loc_18006EB54
0x18006e966  mov     edx, [r14+10h]
0x18006e96a  mov     rcx, [rsp+2D8h+pcchDestLength]
0x18006e96f  mov     rcx, [rcx]
0x18006e972  call    WxVerifyMicrosoftSignedEx
0x18006e977  mov     esi, eax
0x18006e979  test    eax, eax
0x18006e97b  jle     short loc_18006E986
0x18006e97d  movzx   esi, ax
0x18006e980  or      esi, 80070000h
0x18006e986  mov     [rsp+2D8h+var_278], esi
0x18006e98a  test    esi, esi
0x18006e98c  jns     short loc_18006E99B
0x18006e98e  mov     [rsp+2D8h+var_274], 91h
0x18006e996  jmp     loc_18006EB54
0x18006e99b  mov     rax, [rsp+2D8h+pcchDestLength]
0x18006e9a0  mov     rcx, [rax]; lpLibFileName
0x18006e9a3  call    cs:__imp_LoadLibraryW
0x18006e9a9  mov     [rsp+2D8h+var_270], rax
0x18006e9ae  mov     rcx, [r14+40h]; hLibModule
0x18006e9b2  test    rcx, rcx
0x18006e9b5  jz      short loc_18006E9C2
0x18006e9b7  call    cs:__imp_FreeLibrary
0x18006e9bd  mov     rax, [rsp+2D8h+var_270]
0x18006e9c2  mov     [r14+40h], rax
0x18006e9c6  test    rax, rax
0x18006e9c9  jz      loc_18006EB15
0x18006e9cf  test    byte ptr cs:xmmword_180107A60+1, 40h
0x18006e9d6  jz      short loc_18006E9EB
0x18006e9d8  mov     edx, 11h
0x18006e9dd  mov     ecx, r15d
0x18006e9e0  mov     r9, rax
0x18006e9e3  mov     r8, r12
0x18006e9e6  call    WPP_SF_q
0x18006e9eb  lea     rdx, ProcName; "HttpPolicyExtensionInit"
0x18006e9f2  mov     rcx, [r14+40h]; hModule
0x18006e9f6  call    cs:__imp_GetProcAddress
0x18006e9fc  mov     [rsp+2D8h+var_270], rax
0x18006ea01  test    rax, rax
0x18006ea04  jnz     short loc_18006EA23
0x18006ea06  test    byte ptr cs:xmmword_180107A60+1, 40h
0x18006ea0d  jz      loc_18006EB54
0x18006ea13  call    cs:__imp_GetLastError
0x18006ea19  mov     edx, 12h
0x18006ea1e  jmp     loc_18006E953
0x18006ea23  lea     rdx, aHttppolicyexte_0; "HttpPolicyExtensionShutdown"
0x18006ea2a  mov     rcx, [r14+40h]; hModule
0x18006ea2e  call    cs:__imp_GetProcAddress
0x18006ea34  mov     [rsp+2D8h+var_250], rax
0x18006ea3c  test    rax, rax
0x18006ea3f  jnz     short loc_18006EA5E
0x18006ea41  test    byte ptr cs:xmmword_180107A60+1, 40h
0x18006ea48  jz      loc_18006EB54
0x18006ea4e  call    cs:__imp_GetLastError
0x18006ea54  mov     edx, 13h
0x18006ea59  jmp     loc_18006E953
0x18006ea5e  mov     [rsp+2D8h+var_280], 0
0x18006ea66  mov     eax, [rsp+2D8h+var_298]
0x18006ea6a  mov     [rsp+2D8h+var_294], eax
0x18006ea6e  xor     r9d, r9d
0x18006ea71  xor     r8d, r8d
0x18006ea74  mov     edx, [r14+14h]
0x18006ea78  mov     ecx, eax
0x18006ea7a  mov     rax, [rsp+2D8h+var_270]
0x18006ea7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ea84  mov     [rsp+2D8h+var_280], eax
0x18006ea88  jmp     short loc_18006EAB0
0x18006ea8a  mov     r15d, 40Eh
0x18006ea90  lea     r12, WPP_70a6ea6fbc8b32957ec072c0c9e35dfc_Traceguids
0x18006ea97  mov     esi, [rsp+2D8h+var_278]
0x18006ea9b  mov     rbx, [rsp+2D8h+var_260]
0x18006eaa0  mov     eax, [rsp+2D8h+var_268]
0x18006eaa4  mov     [rsp+2D8h+var_298], eax
0x18006eaa8  mov     r14, [rsp+2D8h+var_258]
0x18006eab0  cmp     [rsp+2D8h+var_294], 0
0x18006eab5  jnz     short loc_18006EABC
0x18006eab7  call    WxReportSwallowedFatalException
0x18006eabc  mov     r9d, [rsp+2D8h+var_280]
0x18006eac1  test    r9d, r9d
0x18006eac4  jz      short loc_18006EADD
0x18006eac6  test    byte ptr cs:xmmword_180107A60+1, 40h
0x18006eacd  jz      loc_18006EB54
0x18006ead3  mov     edx, 14h
0x18006ead8  jmp     loc_18006E956
0x18006eadd  mov     rax, [rsp+2D8h+var_270]
0x18006eae2  mov     [r14+48h], rax
0x18006eae6  mov     rax, [rsp+2D8h+var_250]
0x18006eaee  mov     [r14+50h], rax
0x18006eaf2  test    byte ptr cs:xmmword_180107A60+1, 40h
0x18006eaf9  jz      short loc_18006EB54
0x18006eafb  mov     edx, 15h
0x18006eb00  mov     ecx, r15d
0x18006eb03  mov     rax, [rsp+2D8h+pcchDestLength]
0x18006eb08  mov     r9, [rax]
0x18006eb0b  mov     r8, r12
0x18006eb0e  call    WPP_SF_S
0x18006eb13  jmp     short loc_18006EB54
0x18006eb15  test    byte ptr cs:xmmword_180107A60+1, 40h
0x18006eb1c  jz      short loc_18006EB54
0x18006eb1e  call    cs:__imp_GetLastError
0x18006eb24  mov     edx, 10h
0x18006eb29  jmp     loc_18006E953
0x18006eb2e  test    byte ptr cs:xmmword_180107A60+1, 40h
0x18006eb35  jz      short loc_18006EB54
0x18006eb37  mov     edx, 0Dh
0x18006eb3c  mov     ecx, r15d
0x18006eb3f  mov     rax, [r14+20h]
0x18006eb43  mov     qword ptr [rsp+2D8h+dwCreationDisposition], rax
0x18006eb48  mov     r9, [r14+30h]
0x18006eb4c  mov     r8, r12
0x18006eb4f  call    WPP_SF_SS
0x18006eb54  mov     r11d, [rsp+2D8h+var_298]
0x18006eb59  test    byte ptr cs:xmmword_180107A60+1, 40h
0x18006eb60  jz      short loc_18006EB79
0x18006eb62  mov     edx, 16h
0x18006eb67  mov     ecx, r15d
0x18006eb6a  mov     [rsp+2D8h+dwCreationDisposition], esi
0x18006eb6e  mov     r9d, r11d
0x18006eb71  mov     r8, r12
0x18006eb74  call    WPP_SF_Dd
0x18006eb79  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18006eb7d  jz      short loc_18006EB88
0x18006eb7f  mov     rcx, rbx; hObject
0x18006eb82  call    cs:__imp_CloseHandle
0x18006eb88  mov     eax, [rsp+2D8h+var_298]
0x18006eb8c  mov     rcx, [rsp+2D8h+var_28]
0x18006eb94  xor     rcx, rsp; StackCookie
0x18006eb97  call    __security_check_cookie
0x18006eb9c  lea     r11, [rsp+2D8h+var_18]
0x18006eba4  mov     rbx, [r11+28h]
0x18006eba8  mov     rsi, [r11+30h]
0x18006ebac  mov     rsp, r11
0x18006ebaf  pop     r15
0x18006ebb1  pop     r14
0x18006ebb3  pop     r12
0x18006ebb5  retn
0x1800ce49e  push    rbp
0x1800ce4a0  sub     rsp, 40h
0x1800ce4a4  mov     rbp, rdx
0x1800ce4a7  call    WxSaveExceptionFilter
0x1800ce4ac  mov     [rbp+44h], eax
0x1800ce4af  mov     eax, [rbp+44h]
0x1800ce4b2  add     rsp, 40h
0x1800ce4b6  pop     rbp
0x1800ce4b7  retn
0x1800ce4b9  push    rbp
0x1800ce4bb  sub     rsp, 40h
0x1800ce4bf  mov     rbp, rdx
0x1800ce4c2  cmp     dword ptr [rbp+44h], 0
0x1800ce4c6  jnz     short loc_1800CE4CE
0x1800ce4c8  call    WxReportSwallowedFatalException
0x1800ce4ce  add     rsp, 40h
0x1800ce4d2  pop     rbp
0x1800ce4d3  retn
```
