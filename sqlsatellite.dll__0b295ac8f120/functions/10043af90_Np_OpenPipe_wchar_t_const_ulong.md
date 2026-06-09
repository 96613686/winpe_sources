# Np::OpenPipe(wchar_t const *,ulong)

- ea: `0x10043af90`
- end: `0x10043b4fb`
- name: `?OpenPipe@Np@@AEAAKPEB_WK@Z`
- size: `1387`
- prototype: `unsigned int(Np *__hidden this, const wchar_t *, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x10043b510`

## callees

- `0x10042b7f0`
- `0x10042b9b0`
- `0x10042c270`
- `0x10042c430`
- `0x1004349f0`
- `0x10043af90`

## import_xrefs

- `KERNEL32!SetNamedPipeHandleState` at `0x10043b273`
- `KERNEL32!SetNamedPipeHandleState` at `0x10043b273`
- `KERNEL32!WaitNamedPipeW` at `0x10043b203`
- `KERNEL32!WaitNamedPipeW` at `0x10043b203`
- `KERNEL32!GetTickCount` at `0x10043b1aa`
- `KERNEL32!GetTickCount` at `0x10043b211`
- `KERNEL32!GetTickCount` at `0x10043b1aa`
- `KERNEL32!GetTickCount` at `0x10043b211`
- `KERNEL32!CloseHandle` at `0x10043b2d2`
- `KERNEL32!CloseHandle` at `0x10043b2d2`
- `KERNEL32!GetLastError` at `0x10043b1e8`
- `KERNEL32!GetLastError` at `0x10043b281`
- `KERNEL32!GetLastError` at `0x10043b398`
- `KERNEL32!GetLastError` at `0x10043b1e8`
- `KERNEL32!GetLastError` at `0x10043b281`
- `KERNEL32!GetLastError` at `0x10043b398`
- `KERNEL32!CreateFileW` at `0x10043b1d8`
- `KERNEL32!CreateFileW` at `0x10043b247`
- `KERNEL32!CreateFileW` at `0x10043b1d8`
- `KERNEL32!CreateFileW` at `0x10043b247`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x10043b137`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x10043b15a`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x10043b137`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x10043b15a`
- `api-ms-win-crt-string-l1-1-0!_wcsnicmp_l` at `0x10043b150`
- `api-ms-win-crt-string-l1-1-0!_wcsnicmp_l` at `0x10043b173`
- `api-ms-win-crt-string-l1-1-0!_wcsnicmp_l` at `0x10043b150`
- `api-ms-win-crt-string-l1-1-0!_wcsnicmp_l` at `0x10043b173`
- `USER32!CharNextW` at `0x10043b0f3`
- `USER32!CharNextW` at `0x10043b0f3`

## string_xrefs

- `0x10043afbd`: `sql\common\dk\sni\src\np.cpp`
- `0x10043afc8`: `Np::OpenPipe`
- `0x10043b127`: `Np::OpenPipe`
- `0x10043b192`: `Np::OpenPipe`
- `0x10043b19e`: `Np::OpenPipe`
- `0x10043b2af`: `Np::OpenPipe`
- `0x10043b2fe`: `Np::OpenPipe`
- `0x10043b33f`: `Np::OpenPipe`
- `0x10043b37f`: `Np::OpenPipe`
- `0x10043b3c9`: `Np::OpenPipe`
- `0x10043b406`: `Np::OpenPipe`
- `0x10043b443`: `Np::OpenPipe`
- `0x10043b47c`: `Np::OpenPipe`
- `0x10043b48d`: `Np::OpenPipe`
- `0x10043b4cc`: `Np::OpenPipe`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Np::OpenPipe(Np *this, const wchar_t *a2, unsigned int a3)
{
  char v6; // al
  int v7; // r14d
  int v8; // r8d
  const wchar_t *v9; // r9
  const wchar_t *v10; // rbp
  __int64 v11; // rbx
  const wchar_t *v12; // rcx
  int v13; // esi
  LPWSTR v14; // rax
  __int64 v15; // rax
  const wchar_t *v16; // rbx
  __crt_locale_pointers *DefaultLocale; // rax
  __crt_locale_pointers *v18; // rax
  DWORD TickCount; // ebp
  DWORD v20; // esi
  HANDLE FileW; // rax
  DWORD LastError; // eax
  unsigned int v23; // ebx
  DWORD v24; // eax
  DWORD v25; // eax
  __int64 dwCreationDisposition; // [rsp+20h] [rbp-68h]
  __int64 dwFlagsAndAttributes; // [rsp+28h] [rbp-60h]
  __int64 dwFlagsAndAttributesa; // [rsp+28h] [rbp-60h]
  HANDLE hTemplateFile; // [rsp+30h] [rbp-58h]
  HANDLE hTemplateFilea; // [rsp+30h] [rbp-58h]
  DWORD Mode; // [rsp+98h] [rbp+10h] BYREF

  v6 = g_XeSniPkg_enabledBitmap;
  if ( (g_XeSniPkg_enabledBitmap & 0x40) != 0 )
  {
    SNIXE_SNI_ENTER_ON(
      "sql\\common\\dk\\sni\\src\\np.cpp",
      "Np::OpenPipe",
      1281,
      L"API|SNI%u#, szPipeName: '%s', dwTimeout: %d\n",
      *((_DWORD *)this + 11),
      a2,
      a3);
    v6 = g_XeSniPkg_enabledBitmap;
  }
  v7 = 0;
  if ( *a2 != 92 )
  {
    v7 = 87;
    if ( (v6 & 2) == 0 )
    {
LABEL_11:
      SNISetLastError(*((unsigned int *)this + 18), 87, 50105);
LABEL_51:
      if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
      {
        LODWORD(dwCreationDisposition) = v7;
        SNIXE_SNI_TRACE_ON(
          "sql\\common\\dk\\sni\\src\\np.cpp",
          "Np::OpenPipe",
          1422,
          L"RET|SNI%d{WINERR}\n",
          dwCreationDisposition);
      }
      v23 = v7;
      goto LABEL_54;
    }
    v8 = 1297;
LABEL_6:
    LODWORD(hTemplateFile) = 87;
    LODWORD(dwFlagsAndAttributes) = 5;
    LODWORD(dwCreationDisposition) = *((_DWORD *)this + 18);
    SNIXE_SNI_ERROR_ON(
      "sql\\common\\dk\\sni\\src\\np.cpp",
      "Np::OpenPipe",
      v8,
      L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
      dwCreationDisposition,
      dwFlagsAndAttributes,
      hTemplateFile);
    goto LABEL_11;
  }
  if ( a2[1] != 92 )
  {
    v7 = 87;
    if ( (v6 & 2) != 0 )
    {
      LODWORD(hTemplateFile) = 87;
      LODWORD(dwFlagsAndAttributes) = 5;
      LODWORD(dwCreationDisposition) = *((_DWORD *)this + 18);
      SNIXE_SNI_ERROR_ON(
        "sql\\common\\dk\\sni\\src\\np.cpp",
        "Np::OpenPipe",
        1306,
        L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
        dwCreationDisposition,
        dwFlagsAndAttributes,
        hTemplateFile);
    }
    goto LABEL_11;
  }
  v10 = a2 + 2;
  v11 = -1;
  do
    ++v11;
  while ( v10[v11] );
  v12 = a2 + 2;
  v13 = 0;
  if ( (int)v11 <= 0 )
  {
LABEL_21:
    v7 = 87;
    if ( (v6 & 2) == 0 )
      goto LABEL_11;
    v8 = 1319;
    goto LABEL_6;
  }
  while ( 1 )
  {
    if ( !*v12 )
    {
LABEL_20:
      v6 = g_XeSniPkg_enabledBitmap;
      goto LABEL_21;
    }
    if ( *v12 == 92 )
      break;
    v14 = CharNextW(v12);
    v12 = v14;
    if ( v14 )
    {
      v15 = v14 - v10;
      if ( (int)v15 > v13 )
      {
        v13 = v15;
        if ( (int)v15 < (int)v11 )
          continue;
      }
    }
    goto LABEL_20;
  }
  v16 = v12 + 1;
  DefaultLocale = GetDefaultLocale();
  if ( _wcsnicmp_l(L"pipe\\", v16, 5u, DefaultLocale) )
  {
    v18 = GetDefaultLocale();
    if ( _wcsnicmp_l(L"HostPipe\\", v16, 9u, v18) )
    {
      v7 = 87;
      if ( (g_XeSniPkg_enabledBitmap & 2) == 0 )
        goto LABEL_11;
      v8 = 1338;
      goto LABEL_6;
    }
  }
  TickCount = GetTickCount();
  v20 = 0;
  FileW = CreateFileW(a2, 0xC0000000, 0, 0, 3u, 0x40000080u, 0);
  *((_QWORD *)this + 8) = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    while ( 1 )
    {
      LastError = GetLastError();
      v23 = LastError;
      if ( LastError != 231 )
        break;
      if ( !WaitNamedPipeW(a2, a3 - v20) )
      {
        v25 = GetLastError();
        v23 = v25;
        if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
        {
          LODWORD(hTemplateFilea) = v25;
          LODWORD(dwFlagsAndAttributesa) = 40;
          LODWORD(dwCreationDisposition) = *((_DWORD *)this + 18);
          SNIXE_SNI_ERROR_ON(
            "sql\\common\\dk\\sni\\src\\np.cpp",
            "Np::OpenPipe",
            1377,
            L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
            dwCreationDisposition,
            dwFlagsAndAttributesa,
            hTemplateFilea);
        }
        SNISetLastError(*((unsigned int *)this + 18), v23, 50140);
        if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
        {
          LODWORD(dwCreationDisposition) = v23;
          SNIXE_SNI_TRACE_ON(
            "sql\\common\\dk\\sni\\src\\np.cpp",
            "Np::OpenPipe",
            1378,
            L"RET|SNI%d{WINERR}\n",
            dwCreationDisposition);
        }
        goto LABEL_54;
      }
      v20 = GetTickCount() - TickCount;
      if ( a3 < v20 )
      {
        if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
        {
          LODWORD(hTemplateFilea) = 231;
          LODWORD(dwFlagsAndAttributesa) = 40;
          LODWORD(dwCreationDisposition) = *((_DWORD *)this + 18);
          SNIXE_SNI_ERROR_ON(
            "sql\\common\\dk\\sni\\src\\np.cpp",
            "Np::OpenPipe",
            1386,
            L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
            dwCreationDisposition,
            dwFlagsAndAttributesa,
            hTemplateFilea);
        }
        SNISetLastError(*((unsigned int *)this + 18), 231, 50140);
        if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
        {
          LODWORD(dwCreationDisposition) = 231;
          SNIXE_SNI_TRACE_ON(
            "sql\\common\\dk\\sni\\src\\np.cpp",
            "Np::OpenPipe",
            1387,
            L"RET|SNI%d{WINERR}\n",
            dwCreationDisposition);
        }
        v23 = 1460;
        goto LABEL_54;
      }
      FileW = CreateFileW(a2, 0xC0000000, 0, 0, 3u, 0x40000080u, 0);
      *((_QWORD *)this + 8) = FileW;
      if ( FileW != (HANDLE)-1LL )
        goto LABEL_33;
    }
    if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
    {
      LODWORD(hTemplateFilea) = LastError;
      LODWORD(dwFlagsAndAttributesa) = 40;
      LODWORD(dwCreationDisposition) = *((_DWORD *)this + 18);
      SNIXE_SNI_ERROR_ON(
        "sql\\common\\dk\\sni\\src\\np.cpp",
        "Np::OpenPipe",
        1369,
        L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
        dwCreationDisposition,
        dwFlagsAndAttributesa,
        hTemplateFilea);
    }
    SNISetLastError(*((unsigned int *)this + 18), v23, 50140);
    if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
    {
      LODWORD(dwCreationDisposition) = v23;
      SNIXE_SNI_TRACE_ON(
        "sql\\common\\dk\\sni\\src\\np.cpp",
        "Np::OpenPipe",
        1370,
        L"RET|SNI%d{WINERR}\n",
        dwCreationDisposition);
    }
  }
  else
  {
LABEL_33:
    Mode = 2;
    if ( SetNamedPipeHandleState(FileW, &Mode, 0, 0) )
      goto LABEL_51;
    v24 = GetLastError();
    v23 = v24;
    if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
    {
      LODWORD(hTemplateFilea) = v24;
      LODWORD(dwFlagsAndAttributesa) = 0;
      LODWORD(dwCreationDisposition) = *((_DWORD *)this + 18);
      SNIXE_SNI_ERROR_ON(
        "sql\\common\\dk\\sni\\src\\np.cpp",
        "Np::OpenPipe",
        1410,
        L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
        dwCreationDisposition,
        dwFlagsAndAttributesa,
        hTemplateFilea);
    }
    SNISetLastError(*((unsigned int *)this + 18), v23, 50100);
    CloseHandle(*((HANDLE *)this + 8));
    *((_QWORD *)this + 8) = -1;
    if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
    {
      LODWORD(dwCreationDisposition) = v23;
      SNIXE_SNI_TRACE_ON(
        "sql\\common\\dk\\sni\\src\\np.cpp",
        "Np::OpenPipe",
        1416,
        L"RET|SNI%d{WINERR}\n",
        dwCreationDisposition);
    }
  }
LABEL_54:
  if ( (g_XeSniPkg_enabledBitmap & 0x80u) != 0 )
    SNIXE_SNI_LEAVE_ON("sql\\common\\dk\\sni\\src\\np.cpp", "Np::OpenPipe", 1281, v9);
  return v23;
}

```

## disassembly

```asm
0x10043af90  mov     r11, rsp
0x10043af93  push    rdi
0x10043af94  push    r12
0x10043af96  push    r13
0x10043af98  push    r14
0x10043af9a  push    r15
0x10043af9c  sub     rsp, 60h
0x10043afa0  mov     qword ptr [r11-48h], 0FFFFFFFFFFFFFFFEh
0x10043afa8  mov     [r11+8], rbx
0x10043afac  mov     [r11+18h], rbp
0x10043afb0  mov     [r11+20h], rsi
0x10043afb4  mov     r12d, r8d
0x10043afb7  mov     r15, rdx
0x10043afba  mov     rdi, rcx
0x10043afbd  lea     r13, aSqlCommonDkSni_22; "sql\\common\\dk\\sni\\src\\np.cpp"
0x10043afc4  mov     [r11-40h], r13
0x10043afc8  lea     rbx, aNpOpenpipe; "Np::OpenPipe"
0x10043afcf  mov     [r11-38h], rbx
0x10043afd3  mov     [rsp+88h+var_30], 501h
0x10043afdb  mov     eax, cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10043afe1  test    al, 40h
0x10043afe3  jz      short loc_10043B012
0x10043afe5  mov     [r11-58h], r8d
0x10043afe9  mov     [r11-60h], rdx
0x10043afed  mov     eax, [rcx+2Ch]
0x10043aff0  mov     dword ptr [rsp+88h+dwCreationDisposition], eax
0x10043aff4  lea     r9, aApiSniUSzpipen; "API|SNI%u#, szPipeName: '%s', dwTimeout"...
0x10043affb  mov     r8d, 501h; int
0x10043b001  mov     rdx, rbx; char *
0x10043b004  mov     rcx, r13; char *
0x10043b007  call    ?SNIXE_SNI_ENTER_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ENTER_ON(char const *,char const *,int,wchar_t const *,...)
0x10043b00c  mov     eax, cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10043b012  xor     r14d, r14d
0x10043b015  mov     ecx, 5Ch ; '\'
0x10043b01a  cmp     cx, [r15]
0x10043b01e  jz      short loc_10043B06A
0x10043b020  lea     r14d, [rcx-5]
0x10043b024  test    al, 2
0x10043b026  jz      short loc_10043B054
0x10043b028  mov     r8d, 511h; int
0x10043b02e  mov     dword ptr [rsp+88h+hTemplateFile], r14d
0x10043b033  mov     dword ptr [rsp+88h+dwFlagsAndAttributes], 5
0x10043b03b  mov     eax, [rdi+48h]
0x10043b03e  lea     r9, aErrSniprovider; "ERR|SNIProviderNum: %d{ProviderNum}, SN"...
0x10043b045  mov     dword ptr [rsp+88h+dwCreationDisposition], eax
0x10043b049  mov     rdx, rbx; char *
0x10043b04c  mov     rcx, r13; char *
0x10043b04f  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x10043b054  mov     edx, r14d
0x10043b057  mov     r8d, 0C3B9h
0x10043b05d  mov     ecx, [rdi+48h]
0x10043b060  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x10043b065  jmp     loc_10043B494
0x10043b06a  lea     rbp, [r15+2]
0x10043b06e  cmp     cx, [rbp+0]
0x10043b072  jz      short loc_10043B0C0
0x10043b074  mov     r14d, 57h ; 'W'
0x10043b07a  test    al, 2
0x10043b07c  jz      short loc_10043B0AA
0x10043b07e  mov     dword ptr [rsp+88h+hTemplateFile], r14d
0x10043b083  mov     dword ptr [rsp+88h+dwFlagsAndAttributes], 5
0x10043b08b  mov     eax, [rdi+48h]
0x10043b08e  mov     dword ptr [rsp+88h+dwCreationDisposition], eax
0x10043b092  lea     r9, aErrSniprovider; "ERR|SNIProviderNum: %d{ProviderNum}, SN"...
0x10043b099  mov     r8d, 51Ah; int
0x10043b09f  mov     rdx, rbx; char *
0x10043b0a2  mov     rcx, r13; char *
0x10043b0a5  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x10043b0aa  mov     edx, r14d
0x10043b0ad  mov     r8d, 0C3B9h
0x10043b0b3  mov     ecx, [rdi+48h]
0x10043b0b6  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x10043b0bb  jmp     loc_10043B494
0x10043b0c0  add     rbp, 2
0x10043b0c4  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x10043b0cb  nop     dword ptr [rax+rax+00h]
0x10043b0d0  inc     rbx
0x10043b0d3  cmp     [rbp+rbx*2+0], r14w
0x10043b0d9  jnz     short loc_10043B0D0
0x10043b0db  mov     rcx, rbp; lpsz
0x10043b0de  mov     esi, r14d
0x10043b0e1  test    ebx, ebx
0x10043b0e3  jle     short loc_10043B117
0x10043b0e5  movzx   eax, word ptr [rcx]
0x10043b0e8  test    ax, ax
0x10043b0eb  jz      short loc_10043B111
0x10043b0ed  cmp     ax, 5Ch ; '\'
0x10043b0f1  jz      short loc_10043B133
0x10043b0f3  call    cs:__imp_CharNextW
0x10043b0f9  mov     rcx, rax
0x10043b0fc  test    rax, rax
0x10043b0ff  jz      short loc_10043B111
0x10043b101  sub     rax, rbp
0x10043b104  sar     rax, 1
0x10043b107  cmp     eax, esi
0x10043b109  jle     short loc_10043B111
0x10043b10b  mov     esi, eax
0x10043b10d  cmp     eax, ebx
0x10043b10f  jl      short loc_10043B0E5
0x10043b111  mov     eax, cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10043b117  mov     r14d, 57h ; 'W'
0x10043b11d  test    al, 2
0x10043b11f  jz      short loc_10043B19E
0x10043b121  mov     r8d, 527h
0x10043b127  lea     rbx, aNpOpenpipe; "Np::OpenPipe"
0x10043b12e  jmp     loc_10043B02E
0x10043b133  lea     rbx, [rcx+2]
0x10043b137  call    cs:__imp_?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ; GetDefaultLocale(void)
0x10043b13d  mov     r9, rax; Locale
0x10043b140  mov     r8d, 5; MaxCount
0x10043b146  mov     rdx, rbx; String2
0x10043b149  lea     rcx, aPipe; "pipe\\"
0x10043b150  call    cs:__imp__wcsnicmp_l
0x10043b156  test    eax, eax
0x10043b158  jz      short loc_10043B1AA
0x10043b15a  call    cs:__imp_?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ; GetDefaultLocale(void)
0x10043b160  mov     r9, rax; Locale
0x10043b163  mov     r8d, 9; MaxCount
0x10043b169  mov     rdx, rbx; String2
0x10043b16c  lea     rcx, aHostpipe; "HostPipe\\"
0x10043b173  call    cs:__imp__wcsnicmp_l
0x10043b179  test    eax, eax
0x10043b17b  jz      short loc_10043B1AA
0x10043b17d  mov     r14d, 57h ; 'W'
0x10043b183  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10043b18a  jz      short loc_10043B19E
0x10043b18c  mov     r8d, 53Ah
0x10043b192  lea     rbx, aNpOpenpipe; "Np::OpenPipe"
0x10043b199  jmp     loc_10043B02E
0x10043b19e  lea     rbx, aNpOpenpipe; "Np::OpenPipe"
0x10043b1a5  jmp     loc_10043B054
0x10043b1aa  call    cs:__imp_GetTickCount
0x10043b1b0  mov     ebp, eax
0x10043b1b2  mov     esi, r14d
0x10043b1b5  mov     [rsp+88h+hTemplateFile], r14; hTemplateFile
0x10043b1ba  mov     dword ptr [rsp+88h+dwFlagsAndAttributes], 40000080h; dwFlagsAndAttributes
0x10043b1c2  mov     dword ptr [rsp+88h+dwCreationDisposition], 3; dwCreationDisposition
0x10043b1ca  xor     r9d, r9d; lpSecurityAttributes
0x10043b1cd  xor     r8d, r8d; dwShareMode
0x10043b1d0  mov     edx, 0C0000000h; dwDesiredAccess
0x10043b1d5  mov     rcx, r15; lpFileName
0x10043b1d8  call    cs:__imp_CreateFileW
0x10043b1de  mov     [rdi+40h], rax
0x10043b1e2  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x10043b1e6  jnz     short loc_10043B257
0x10043b1e8  call    cs:__imp_GetLastError
0x10043b1ee  mov     ebx, eax
0x10043b1f0  cmp     eax, 0E7h
0x10043b1f5  jnz     loc_10043B41A
0x10043b1fb  mov     edx, r12d
0x10043b1fe  sub     edx, esi; nTimeOut
0x10043b200  mov     rcx, r15; lpNamedPipeName
0x10043b203  call    cs:__imp_WaitNamedPipeW
0x10043b209  test    eax, eax
0x10043b20b  jz      loc_10043B398
0x10043b211  call    cs:__imp_GetTickCount
0x10043b217  mov     esi, eax
0x10043b219  sub     esi, ebp
0x10043b21b  cmp     r12d, esi
0x10043b21e  jb      loc_10043B312
0x10043b224  mov     [rsp+88h+hTemplateFile], r14; hTemplateFile
0x10043b229  mov     dword ptr [rsp+88h+dwFlagsAndAttributes], 40000080h; dwFlagsAndAttributes
0x10043b231  mov     dword ptr [rsp+88h+dwCreationDisposition], 3; dwCreationDisposition
0x10043b239  xor     r9d, r9d; lpSecurityAttributes
0x10043b23c  xor     r8d, r8d; dwShareMode
0x10043b23f  mov     edx, 0C0000000h; dwDesiredAccess
0x10043b244  mov     rcx, r15; lpFileName
0x10043b247  call    cs:__imp_CreateFileW
0x10043b24d  mov     [rdi+40h], rax
0x10043b251  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x10043b255  jz      short loc_10043B1E8
0x10043b257  mov     [rsp+88h+Mode], 2
0x10043b262  xor     r9d, r9d; lpCollectDataTimeout
0x10043b265  xor     r8d, r8d; lpMaxCollectionCount
0x10043b268  lea     rdx, [rsp+88h+Mode]; lpMode
0x10043b270  mov     rcx, rax; hNamedPipe
0x10043b273  call    cs:__imp_SetNamedPipeHandleState
0x10043b279  test    eax, eax
0x10043b27b  jnz     loc_10043B48D
0x10043b281  call    cs:__imp_GetLastError
0x10043b287  mov     ebx, eax
0x10043b289  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10043b290  jz      short loc_10043B2BE
0x10043b292  mov     dword ptr [rsp+88h+hTemplateFile], eax
0x10043b296  mov     dword ptr [rsp+88h+dwFlagsAndAttributes], r14d
0x10043b29b  mov     eax, [rdi+48h]
0x10043b29e  mov     dword ptr [rsp+88h+dwCreationDisposition], eax
0x10043b2a2  lea     r9, aErrSniprovider; "ERR|SNIProviderNum: %d{ProviderNum}, SN"...
0x10043b2a9  mov     r8d, 582h; int
0x10043b2af  lea     rdx, aNpOpenpipe; "Np::OpenPipe"
0x10043b2b6  mov     rcx, r13; char *
0x10043b2b9  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x10043b2be  mov     r8d, 0C3B4h
0x10043b2c4  mov     edx, ebx
0x10043b2c6  mov     ecx, [rdi+48h]
0x10043b2c9  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x10043b2ce  mov     rcx, [rdi+40h]; hObject
0x10043b2d2  call    cs:__imp_CloseHandle
0x10043b2d8  mov     qword ptr [rdi+40h], 0FFFFFFFFFFFFFFFFh
0x10043b2e0  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 1; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10043b2e7  jz      loc_10043B4BD
0x10043b2ed  mov     dword ptr [rsp+88h+dwCreationDisposition], ebx
0x10043b2f1  lea     r9, aRetSniDWinerr; "RET|SNI%d{WINERR}\n"
0x10043b2f8  mov     r8d, 588h; int
0x10043b2fe  lea     rdx, aNpOpenpipe; "Np::OpenPipe"
0x10043b305  mov     rcx, r13; char *
0x10043b308  call    ?SNIXE_SNI_TRACE_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_TRACE_ON(char const *,char const *,int,wchar_t const *,...)
0x10043b30d  jmp     loc_10043B4BD
0x10043b312  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10043b319  jz      short loc_10043B34E
0x10043b31b  mov     dword ptr [rsp+88h+hTemplateFile], 0E7h
0x10043b323  mov     dword ptr [rsp+88h+dwFlagsAndAttributes], 28h ; '('
0x10043b32b  mov     eax, [rdi+48h]
0x10043b32e  mov     dword ptr [rsp+88h+dwCreationDisposition], eax
0x10043b332  lea     r9, aErrSniprovider; "ERR|SNIProviderNum: %d{ProviderNum}, SN"...
0x10043b339  mov     r8d, 56Ah; int
0x10043b33f  lea     rdx, aNpOpenpipe; "Np::OpenPipe"
0x10043b346  mov     rcx, r13; char *
0x10043b349  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x10043b34e  mov     edx, 0E7h
0x10043b353  mov     r8d, 0C3DCh
0x10043b359  mov     ecx, [rdi+48h]
0x10043b35c  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x10043b361  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 1; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10043b368  jz      short loc_10043B38E
0x10043b36a  mov     dword ptr [rsp+88h+dwCreationDisposition], 0E7h
0x10043b372  lea     r9, aRetSniDWinerr; "RET|SNI%d{WINERR}\n"
0x10043b379  mov     r8d, 56Bh; int
0x10043b37f  lea     rdx, aNpOpenpipe; "Np::OpenPipe"
0x10043b386  mov     rcx, r13; char *
0x10043b389  call    ?SNIXE_SNI_TRACE_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_TRACE_ON(char const *,char const *,int,wchar_t const *,...)
0x10043b38e  mov     ebx, 5B4h
0x10043b393  jmp     loc_10043B4BD
0x10043b398  call    cs:__imp_GetLastError
0x10043b39e  mov     ebx, eax
0x10043b3a0  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10043b3a7  jz      short loc_10043B3D8
0x10043b3a9  mov     dword ptr [rsp+88h+hTemplateFile], eax
0x10043b3ad  mov     dword ptr [rsp+88h+dwFlagsAndAttributes], 28h ; '('
0x10043b3b5  mov     eax, [rdi+48h]
0x10043b3b8  mov     dword ptr [rsp+88h+dwCreationDisposition], eax
0x10043b3bc  lea     r9, aErrSniprovider; "ERR|SNIProviderNum: %d{ProviderNum}, SN"...
0x10043b3c3  mov     r8d, 561h; int
0x10043b3c9  lea     rdx, aNpOpenpipe; "Np::OpenPipe"
0x10043b3d0  mov     rcx, r13; char *
0x10043b3d3  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x10043b3d8  mov     r8d, 0C3DCh
0x10043b3de  mov     edx, ebx
0x10043b3e0  mov     ecx, [rdi+48h]
0x10043b3e3  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x10043b3e8  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 1; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10043b3ef  jz      loc_10043B4BD
0x10043b3f5  mov     dword ptr [rsp+88h+dwCreationDisposition], ebx
0x10043b3f9  lea     r9, aRetSniDWinerr; "RET|SNI%d{WINERR}\n"
0x10043b400  mov     r8d, 562h; int
0x10043b406  lea     rdx, aNpOpenpipe; "Np::OpenPipe"
0x10043b40d  mov     rcx, r13; char *
0x10043b410  call    ?SNIXE_SNI_TRACE_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_TRACE_ON(char const *,char const *,int,wchar_t const *,...)
0x10043b415  jmp     loc_10043B4BD
0x10043b41a  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10043b421  jz      short loc_10043B452
0x10043b423  mov     dword ptr [rsp+88h+hTemplateFile], ebx
0x10043b427  mov     dword ptr [rsp+88h+dwFlagsAndAttributes], 28h ; '('
0x10043b42f  mov     eax, [rdi+48h]
0x10043b432  mov     dword ptr [rsp+88h+dwCreationDisposition], eax
0x10043b436  lea     r9, aErrSniprovider; "ERR|SNIProviderNum: %d{ProviderNum}, SN"...
0x10043b43d  mov     r8d, 559h; int
0x10043b443  lea     rdx, aNpOpenpipe; "Np::OpenPipe"
0x10043b44a  mov     rcx, r13; char *
0x10043b44d  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x10043b452  mov     r8d, 0C3DCh
0x10043b458  mov     edx, ebx
0x10043b45a  mov     ecx, [rdi+48h]
0x10043b45d  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x10043b462  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 1; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10043b469  jz      short loc_10043B4BD
0x10043b46b  mov     dword ptr [rsp+88h+dwCreationDisposition], ebx
0x10043b46f  lea     r9, aRetSniDWinerr; "RET|SNI%d{WINERR}\n"
0x10043b476  mov     r8d, 55Ah; int
0x10043b47c  lea     rdx, aNpOpenpipe; "Np::OpenPipe"
0x10043b483  mov     rcx, r13; char *
0x10043b486  call    ?SNIXE_SNI_TRACE_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_TRACE_ON(char const *,char const *,int,wchar_t const *,...)
0x10043b48b  jmp     short loc_10043B4BD
0x10043b48d  lea     rbx, aNpOpenpipe; "Np::OpenPipe"
0x10043b494  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 1; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10043b49b  jz      short loc_10043B4BA
0x10043b49d  mov     dword ptr [rsp+88h+dwCreationDisposition], r14d
0x10043b4a2  lea     r9, aRetSniDWinerr; "RET|SNI%d{WINERR}\n"
0x10043b4a9  mov     r8d, 58Eh; int
0x10043b4af  mov     rdx, rbx; char *
0x10043b4b2  mov     rcx, r13; char *
0x10043b4b5  call    ?SNIXE_SNI_TRACE_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_TRACE_ON(char const *,char const *,int,wchar_t const *,...)
0x10043b4ba  mov     ebx, r14d
0x10043b4bd  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 80h; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10043b4c4  jz      short loc_10043B4DB
0x10043b4c6  mov     r8d, 501h; int
0x10043b4cc  lea     rdx, aNpOpenpipe; "Np::OpenPipe"
0x10043b4d3  mov     rcx, r13; char *
0x10043b4d6  call    ?SNIXE_SNI_LEAVE_ON@@YAXPEBD0HPEB_W@Z; SNIXE_SNI_LEAVE_ON(char const *,char const *,int,wchar_t const *)
0x10043b4db  mov     eax, ebx
  ... truncated ...
```
