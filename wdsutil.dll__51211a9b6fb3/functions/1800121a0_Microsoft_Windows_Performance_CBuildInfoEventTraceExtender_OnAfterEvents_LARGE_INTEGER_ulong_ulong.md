# Microsoft::Windows::Performance::CBuildInfoEventTraceExtender::OnAfterEvents(_LARGE_INTEGER,ulong,ulong)

- ea: `0x1800121a0`
- end: `0x18001281c`
- name: `?OnAfterEvents@CBuildInfoEventTraceExtender@Performance@Windows@Microsoft@@UEAAJT_LARGE_INTEGER@@KK@Z`
- size: `1660`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CBuildInfoEventTraceExtender *__hidden this, union _LARGE_INTEGER, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800121a0`
- `0x180012848`
- `0x180012cbc`
- `0x180012dcc`
- `0x1800319ae`
- `0x1800319f0`
- `0x180034010`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x180012579`
- `msvcrt!wcsncpy_s` at `0x1800125a6`
- `msvcrt!wcsncpy_s` at `0x180012579`
- `msvcrt!wcsncpy_s` at `0x1800125a6`
- `msvcrt!_ultow_s` at `0x1800124da`
- `msvcrt!_ultow_s` at `0x1800124da`
- `msvcrt!_gmtime64` at `0x1800122e5`
- `msvcrt!_gmtime64` at `0x1800122e5`
- `msvcrt!wcsnlen` at `0x1800124f0`
- `msvcrt!wcsnlen` at `0x1800124f0`
- `msvcrt!_errno` at `0x1800122d2`
- `msvcrt!_errno` at `0x1800122fd`
- `msvcrt!_errno` at `0x1800122d2`
- `msvcrt!_errno` at `0x1800122fd`
- `msvcrt!??3@YAXPEAX@Z` at `0x180012467`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800124a8`
- `msvcrt!??3@YAXPEAX@Z` at `0x180012525`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800125c4`
- `msvcrt!??3@YAXPEAX@Z` at `0x180012467`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800124a8`
- `msvcrt!??3@YAXPEAX@Z` at `0x180012525`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800125c4`
- `KERNEL32!SystemTimeToFileTime` at `0x180012369`
- `KERNEL32!SystemTimeToFileTime` at `0x180012369`
- `KERNEL32!GetProcAddress` at `0x180012692`
- `KERNEL32!GetProcAddress` at `0x180012692`
- `KERNEL32!LoadLibraryExW` at `0x180012677`
- `KERNEL32!LoadLibraryExW` at `0x180012677`
- `ADVAPI32!RegCloseKey` at `0x180012549`
- `ADVAPI32!RegCloseKey` at `0x1800126c1`
- `ADVAPI32!RegCloseKey` at `0x180012738`
- `ADVAPI32!RegCloseKey` at `0x1800127b2`
- `ADVAPI32!RegCloseKey` at `0x1800127c9`
- `ADVAPI32!RegCloseKey` at `0x180012549`
- `ADVAPI32!RegCloseKey` at `0x1800126c1`
- `ADVAPI32!RegCloseKey` at `0x180012738`
- `ADVAPI32!RegCloseKey` at `0x1800127b2`
- `ADVAPI32!RegCloseKey` at `0x1800127c9`
- `ADVAPI32!RegOpenKeyExW` at `0x180012248`
- `ADVAPI32!RegOpenKeyExW` at `0x180012248`
- `ADVAPI32!RegQueryValueExW` at `0x1800122a2`
- `ADVAPI32!RegQueryValueExW` at `0x1800123ea`
- `ADVAPI32!RegQueryValueExW` at `0x1800122a2`
- `ADVAPI32!RegQueryValueExW` at `0x1800123ea`

## string_xrefs

- `0x180012298`: `InstallDate`
- `0x180012670`: `ntdll.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Microsoft::Windows::Performance::CBuildInfoEventTraceExtender::OnAfterEvents(
        Microsoft::Windows::Performance::CBuildInfoEventTraceExtender *this,
        union _LARGE_INTEGER a2,
        unsigned int a3,
        unsigned int a4)
{
  unsigned int v4; // r13d
  unsigned int v5; // r12d
  Microsoft::Windows::Performance::CBuildInfoEventTraceExtender *v7; // r15
  unsigned __int16 *p_Src; // rdi
  HKEY v9; // r14
  unsigned int v10; // esi
  LSTATUS v11; // eax
  WORD *v12; // rdi
  WORD v13; // r11
  WORD v14; // r10
  WORD v15; // r9
  WORD v16; // r8
  WORD v17; // dx
  BOOL v18; // eax
  HKEY v19; // rcx
  DWORD v20; // esi
  LSTATUS v21; // eax
  __int64 v22; // r8
  __int64 v23; // rdx
  __int64 first_of; // rax
  __int64 v25; // rdx
  __int64 v26; // rsi
  __int64 v27; // r15
  size_t v28; // rax
  size_t v29; // r12
  rsize_t v30; // r13
  wchar_t *v32; // rdi
  unsigned int v33; // esi
  wchar_t *v34; // rdi
  unsigned int v35; // esi
  SYSTEMTIME *p_SystemTime; // rax
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  int v39; // edi
  __int64 v40; // rcx
  DWORD Type; // [rsp+30h] [rbp-D0h] BYREF
  HKEY phkResult; // [rsp+38h] [rbp-C8h] BYREF
  DWORD cbData[2]; // [rsp+40h] [rbp-C0h] BYREF
  BYTE Data[4]; // [rsp+48h] [rbp-B8h] BYREF
  DWORD v45; // [rsp+4Ch] [rbp-B4h] BYREF
  unsigned int v46; // [rsp+50h] [rbp-B0h]
  unsigned int v47; // [rsp+54h] [rbp-ACh]
  _QWORD v48[3]; // [rsp+58h] [rbp-A8h] BYREF
  Microsoft::Windows::Performance::CBuildInfoEventTraceExtender *v49; // [rsp+70h] [rbp-90h]
  __int64 v50; // [rsp+78h] [rbp-88h]
  _WORD v51[2]; // [rsp+80h] [rbp-80h] BYREF
  char v52; // [rsp+84h] [rbp-7Ch]
  union _LARGE_INTEGER v53; // [rsp+90h] [rbp-70h]
  __int128 v54; // [rsp+98h] [rbp-68h]
  HKEY *v55; // [rsp+C8h] [rbp-38h]
  unsigned int v56; // [rsp+D0h] [rbp-30h]
  unsigned int v57; // [rsp+D4h] [rbp-2Ch]
  _WORD v58[2]; // [rsp+E0h] [rbp-20h] BYREF
  char v59; // [rsp+E4h] [rbp-1Ch]
  union _LARGE_INTEGER v60; // [rsp+F0h] [rbp-10h]
  __int128 v61; // [rsp+F8h] [rbp-8h] BYREF
  __int128 *v62; // [rsp+128h] [rbp+28h]
  int v63; // [rsp+130h] [rbp+30h]
  unsigned int v64; // [rsp+134h] [rbp+34h]
  SYSTEMTIME SystemTime; // [rsp+140h] [rbp+40h] BYREF
  __int64 v66; // [rsp+150h] [rbp+50h]
  unsigned __int64 v67; // [rsp+158h] [rbp+58h]
  __int128 v68; // [rsp+160h] [rbp+60h] BYREF
  HKEY v69; // [rsp+170h] [rbp+70h] BYREF
  unsigned __int16 Src; // [rsp+178h] [rbp+78h] BYREF
  char v71; // [rsp+17Ah] [rbp+7Ah] BYREF
  wchar_t Buffer[16]; // [rsp+980h] [rbp+880h] BYREF

  v50 = -2;
  v4 = a4;
  v47 = a4;
  v5 = a3;
  v46 = a3;
  v7 = this;
  v49 = this;
  memset_0(&v69, 0, 0x80Cu);
  p_Src = &Src;
  v68 = 0;
  v9 = 0;
  memset(v48, 0, sizeof(v48));
  phkResult = 0;
  v10 = 1;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion", 0, 1u, &phkResult) )
  {
    v9 = phkResult;
    v48[0] = phkResult;
    *(_DWORD *)Data = 0;
    Type = 0;
    cbData[0] = 4;
    v11 = RegQueryValueExW(phkResult, L"InstallDate", 0, &Type, Data, cbData);
    if ( !v11 )
      v11 = Type != 4 ? 0xD : 0;
    if ( !v11 )
    {
      *(_QWORD *)cbData = *(int *)Data;
      *_errno() = 0;
      v12 = (WORD *)_gmtime64((const __time64_t *)cbData);
      if ( v12 )
      {
        if ( !*_errno() )
        {
          v13 = *v12;
          v14 = v12[2];
          v15 = v12[4];
          v16 = v12[6];
          v17 = v12[12];
          SystemTime.wYear = v12[10] + 1900;
          SystemTime.wMonth = v12[8] + 1;
          SystemTime.wDayOfWeek = v17;
          SystemTime.wDay = v16;
          SystemTime.wHour = v15;
          SystemTime.wMinute = v14;
          SystemTime.wSecond = v13;
          SystemTime.wMilliseconds = 0;
          phkResult = 0;
          v18 = SystemTimeToFileTime(&SystemTime, (LPFILETIME)&phkResult);
          v19 = v69;
          if ( v18 )
            v19 = phkResult;
          v69 = v19;
        }
      }
    }
    v20 = 1025;
    Type = 1025;
    if ( (unsigned int)ATL::CRegKey::QueryStringValue((ATL::CRegKey *)v48, L"BuildLabEx", &Src, &Type) )
    {
      Type = 1025;
      if ( (unsigned int)ATL::CRegKey::QueryStringValue((ATL::CRegKey *)v48, L"BuildLab", &Src, &Type) )
      {
        Src = 0;
        p_Src = (unsigned __int16 *)&v71;
        goto LABEL_40;
      }
    }
    else
    {
      cbData[0] = 0;
      v45 = 0;
      LODWORD(phkResult) = 4;
      v21 = RegQueryValueExW(v9, L"UBR", 0, &v45, (LPBYTE)cbData, (LPDWORD)&phkResult);
      if ( !v21 )
        v21 = v45 != 4 ? 0xD : 0;
      if ( !v21 )
      {
        v67 = 7;
        v66 = 0;
        SystemTime.wYear = 0;
        if ( Src )
        {
          v22 = -1;
          do
            ++v22;
          while ( *(&Src + v22) );
        }
        std::wstring::assign(&SystemTime, &Src);
        first_of = std::wstring::find_first_of(&SystemTime, v23, 0);
        if ( first_of == -1 )
        {
          if ( v67 >= 8 )
            operator delete(*(void **)&SystemTime.wYear);
          v67 = 7;
          v66 = 0;
          SystemTime.wYear = 0;
LABEL_29:
          if ( v9 )
            RegCloseKey(v9);
          return 2147500037LL;
        }
        v26 = first_of + 1;
        v27 = std::wstring::find_first_of(&SystemTime, v25, first_of + 1);
        if ( v27 == -1 )
        {
          if ( v67 >= 8 )
            operator delete(*(void **)&SystemTime.wYear);
          v67 = 7;
          v66 = 0;
          SystemTime.wYear = 0;
          goto LABEL_29;
        }
        _ultow_s(cbData[0], Buffer, 0x10u, 10);
        v28 = wcsnlen(Buffer, 0x10u);
        v29 = v28;
        v30 = v66 - v27 + 1;
        if ( v28 + v26 + v30 > 0x402 )
        {
          if ( v67 >= 8 )
            operator delete(*(void **)&SystemTime.wYear);
          v67 = 7;
          v66 = 0;
          SystemTime.wYear = 0;
          goto LABEL_29;
        }
        v32 = &Src + v26;
        v33 = 1026 - v26;
        wcsncpy_s(v32, v33, Buffer, v28);
        v34 = &v32[v29];
        v35 = v33 - v29;
        p_SystemTime = &SystemTime;
        if ( v67 >= 8 )
          p_SystemTime = *(SYSTEMTIME **)&SystemTime.wYear;
        wcsncpy_s(v34, v35, (const wchar_t *)&p_SystemTime->wYear + v27, v30);
        p_Src = &v34[v30];
        v20 = v35 - v30;
        if ( v67 >= 8 )
          operator delete(*(void **)&SystemTime.wYear);
        v67 = 7;
        v66 = 0;
        SystemTime.wYear = 0;
        v7 = v49;
        v5 = v46;
        v4 = v47;
        goto LABEL_40;
      }
    }
    p_Src = &Src + Type;
    v20 = 1026 - Type;
LABEL_40:
    Type = v20;
    if ( (unsigned int)ATL::CRegKey::QueryStringValue((ATL::CRegKey *)v48, L"ProductName", p_Src, &Type) )
    {
      *p_Src = 0;
      LODWORD(p_Src) = (_DWORD)p_Src + 2;
    }
    else
    {
      LODWORD(p_Src) = (_DWORD)p_Src + 2 * Type;
    }
    Library = LoadLibraryExW(L"ntdll.dll", 0, 0x800u);
    if ( Library )
    {
      ProcAddress = GetProcAddress(Library, "RtlGetDeviceFamilyInfoEnum");
      if ( ProcAddress )
        ((void (__fastcall *)(__int128 *, char *, char *))ProcAddress)(&v68, (char *)&v68 + 8, (char *)&v68 + 12);
    }
    v10 = 1;
  }
  if ( v9 )
    RegCloseKey(v9);
  memset_0(v51, 0, 0x58u);
  v51[0] = v4;
  v53 = a2;
  v54 = SystemConfigExGuid;
  v52 = 32;
  v55 = &v69;
  v56 = (_DWORD)p_Src - ((unsigned int)&v61 + 8 + 112);
  v57 = v5;
  v39 = (*(__int64 (__fastcall **)(_QWORD, _WORD *, _QWORD, _QWORD))(**((_QWORD **)v7 + 2) + 192LL))(
          *((_QWORD *)v7 + 2),
          v51,
          0,
          0);
  if ( v39 < 0 )
    return (unsigned int)v39;
  memset_0(v58, 0, 0x58u);
  v58[0] = v4;
  v60 = a2;
  v61 = SystemConfigExGuid;
  v59 = 37;
  v62 = &v68;
  v63 = 16;
  v64 = v5;
  v39 = (*(__int64 (__fastcall **)(_QWORD, _WORD *, _QWORD, _QWORD))(**((_QWORD **)v7 + 2) + 192LL))(
          *((_QWORD *)v7 + 2),
          v58,
          0,
          0);
  if ( v39 < 0 )
    return (unsigned int)v39;
  v40 = *((_QWORD *)v7 + 1);
  if ( v40 )
    return (*(unsigned int (__fastcall **)(__int64, union _LARGE_INTEGER, _QWORD, _QWORD))(*(_QWORD *)v40 + 96LL))(
             v40,
             a2,
             v5,
             v4);
  return v10;
}

```

## disassembly

```asm
0x1800121a0  push    rbp
0x1800121a2  push    rbx
0x1800121a3  push    rsi
0x1800121a4  push    rdi
0x1800121a5  push    r12
0x1800121a7  push    r13
0x1800121a9  push    r14
0x1800121ab  push    r15
0x1800121ad  lea     rbp, [rsp-8B8h]
0x1800121b5  sub     rsp, 9B8h
0x1800121bc  mov     [rsp+9F0h+var_978], 0FFFFFFFFFFFFFFFEh
0x1800121c5  mov     rax, cs:__security_cookie
0x1800121cc  xor     rax, rsp
0x1800121cf  mov     [rbp+8F0h+var_50], rax
0x1800121d6  mov     r13d, r9d
0x1800121d9  mov     [rsp+9F0h+var_99C], r9d
0x1800121de  mov     r12d, r8d
0x1800121e1  mov     [rsp+9F0h+var_9A0], r8d
0x1800121e6  mov     rbx, rdx
0x1800121e9  mov     r15, rcx
0x1800121ec  mov     [rsp+9F0h+var_980], rcx
0x1800121f1  xor     edx, edx; Val
0x1800121f3  mov     r8d, 80Ch; Size
0x1800121f9  lea     rcx, [rbp+8F0h+var_880]; void *
0x1800121fd  call    memset_0
0x180012202  lea     rdi, [rbp+8F0h+Src]
0x180012206  xorps   xmm0, xmm0
0x180012209  movups  [rbp+8F0h+var_890], xmm0
0x18001220d  xor     eax, eax
0x18001220f  mov     r14d, eax
0x180012212  mov     [rsp+9F0h+var_998], rax
0x180012217  mov     [rsp+9F0h+var_990], rax
0x18001221c  mov     [rsp+9F0h+var_988], rax
0x180012221  mov     [rsp+9F0h+var_9B8], rax
0x180012226  lea     rax, [rsp+9F0h+var_9B8]
0x18001222b  mov     [rsp+9F0h+phkResult], rax; phkResult
0x180012230  lea     esi, [r14+1]
0x180012234  mov     r9d, esi; samDesired
0x180012237  xor     r8d, r8d; ulOptions
0x18001223a  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180012241  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180012248  call    cs:__imp_RegOpenKeyExW
0x18001224f  nop     dword ptr [rax+rax+00h]
0x180012254  test    eax, eax
0x180012256  jnz     short loc_180012262
0x180012258  mov     r14, [rsp+9F0h+var_9B8]
0x18001225d  mov     [rsp+9F0h+var_998], r14
0x180012262  test    eax, eax
0x180012264  jnz     loc_1800126B9
0x18001226a  xor     edi, edi
0x18001226c  mov     dword ptr [rsp+9F0h+Data], edi
0x180012270  mov     [rsp+9F0h+Type], edi
0x180012274  mov     [rsp+9F0h+cbData], 4
0x18001227c  lea     rax, [rsp+9F0h+cbData]
0x180012281  mov     [rsp+9F0h+lpcbData], rax; lpcbData
0x180012286  lea     rax, [rsp+9F0h+Data]
0x18001228b  mov     [rsp+9F0h+phkResult], rax; lpData
0x180012290  lea     r9, [rsp+9F0h+Type]; lpType
0x180012295  xor     r8d, r8d; lpReserved
0x180012298  lea     rdx, ValueName; "InstallDate"
0x18001229f  mov     rcx, r14; hKey
0x1800122a2  call    cs:__imp_RegQueryValueExW
0x1800122a9  nop     dword ptr [rax+rax+00h]
0x1800122ae  test    eax, eax
0x1800122b0  jnz     short loc_1800122C0
0x1800122b2  mov     eax, [rsp+9F0h+Type]
0x1800122b6  sub     eax, 4
0x1800122b9  neg     eax
0x1800122bb  sbb     eax, eax
0x1800122bd  and     eax, 0Dh
0x1800122c0  test    eax, eax
0x1800122c2  jnz     loc_180012389
0x1800122c8  movsxd  rax, dword ptr [rsp+9F0h+Data]
0x1800122cd  mov     qword ptr [rsp+9F0h+cbData], rax
0x1800122d2  call    cs:__imp__errno
0x1800122d9  nop     dword ptr [rax+rax+00h]
0x1800122de  mov     [rax], edi
0x1800122e0  lea     rcx, [rsp+9F0h+cbData]; Time
0x1800122e5  call    cs:__imp__gmtime64
0x1800122ec  nop     dword ptr [rax+rax+00h]
0x1800122f1  mov     rdi, rax
0x1800122f4  test    rax, rax
0x1800122f7  jz      loc_180012387
0x1800122fd  call    cs:__imp__errno
0x180012304  nop     dword ptr [rax+rax+00h]
0x180012309  cmp     dword ptr [rax], 0
0x18001230c  jnz     short loc_180012387
0x18001230e  movzx   r11d, word ptr [rdi]
0x180012312  movzx   r10d, word ptr [rdi+4]
0x180012317  movzx   r9d, word ptr [rdi+8]
0x18001231c  movzx   r8d, word ptr [rdi+0Ch]
0x180012321  movzx   edx, word ptr [rdi+18h]
0x180012325  mov     ecx, 76Ch
0x18001232a  add     cx, [rdi+14h]
0x18001232e  mov     [rbp+8F0h+SystemTime.wYear], cx
0x180012332  movzx   eax, word ptr [rdi+10h]
0x180012336  add     ax, si
0x180012339  mov     [rbp+8F0h+SystemTime.wMonth], ax
0x18001233d  mov     [rbp+8F0h+SystemTime.wDayOfWeek], dx
0x180012341  mov     [rbp+8F0h+SystemTime.wDay], r8w
0x180012346  mov     [rbp+8F0h+SystemTime.wHour], r9w
0x18001234b  mov     [rbp+8F0h+SystemTime.wMinute], r10w
0x180012350  mov     [rbp+8F0h+SystemTime.wSecond], r11w
0x180012355  xor     edi, edi
0x180012357  mov     [rbp+8F0h+SystemTime.wMilliseconds], di
0x18001235b  mov     [rsp+9F0h+var_9B8], rdi
0x180012360  lea     rdx, [rsp+9F0h+var_9B8]; lpFileTime
0x180012365  lea     rcx, [rbp+8F0h+SystemTime]; lpSystemTime
0x180012369  call    cs:__imp_SystemTimeToFileTime
0x180012370  nop     dword ptr [rax+rax+00h]
0x180012375  mov     rcx, [rbp+8F0h+var_880]
0x180012379  test    eax, eax
0x18001237b  cmovnz  rcx, [rsp+9F0h+var_9B8]
0x180012381  mov     [rbp+8F0h+var_880], rcx
0x180012385  jmp     short loc_180012389
0x180012387  xor     edi, edi
0x180012389  mov     esi, 401h
0x18001238e  mov     [rsp+9F0h+Type], esi
0x180012392  lea     r9, [rsp+9F0h+Type]; unsigned int *
0x180012397  lea     r8, [rbp+8F0h+Src]; unsigned __int16 *
0x18001239b  lea     rdx, aBuildlabex; "BuildLabEx"
0x1800123a2  lea     rcx, [rsp+9F0h+var_998]; this
0x1800123a7  call    ?QueryStringValue@CRegKey@ATL@@QEAAJPEBGPEAGPEAK@Z; ATL::CRegKey::QueryStringValue(ushort const *,ushort *,ulong *)
0x1800123ac  test    eax, eax
0x1800123ae  jnz     loc_1800125F3
0x1800123b4  mov     [rsp+9F0h+cbData], edi
0x1800123b8  mov     [rsp+9F0h+var_9A4], edi
0x1800123bc  mov     dword ptr [rsp+9F0h+var_9B8], 4
0x1800123c4  lea     rax, [rsp+9F0h+var_9B8]
0x1800123c9  mov     [rsp+9F0h+lpcbData], rax; lpcbData
0x1800123ce  lea     rax, [rsp+9F0h+cbData]
0x1800123d3  mov     [rsp+9F0h+phkResult], rax; lpData
0x1800123d8  lea     r9, [rsp+9F0h+var_9A4]; lpType
0x1800123dd  xor     r8d, r8d; lpReserved
0x1800123e0  lea     rdx, aUbr; "UBR"
0x1800123e7  mov     rcx, r14; hKey
0x1800123ea  call    cs:__imp_RegQueryValueExW
0x1800123f1  nop     dword ptr [rax+rax+00h]
0x1800123f6  test    eax, eax
0x1800123f8  jnz     short loc_180012408
0x1800123fa  mov     eax, [rsp+9F0h+var_9A4]
0x1800123fe  sub     eax, 4
0x180012401  neg     eax
0x180012403  sbb     eax, eax
0x180012405  and     eax, 0Dh
0x180012408  test    eax, eax
0x18001240a  jnz     loc_180012615
0x180012410  lea     r12d, [rax+7]
0x180012414  mov     [rbp+8F0h+var_898], r12
0x180012418  mov     [rbp+8F0h+var_8A0], rdi
0x18001241c  mov     [rbp+8F0h+SystemTime.wYear], di
0x180012420  cmp     [rbp+8F0h+Src], di
0x180012424  jnz     short loc_18001242B
0x180012426  mov     r8, rdi
0x180012429  jmp     short loc_18001243D
0x18001242b  lea     rax, [rbp+8F0h+Src]
0x18001242f  or      r8, 0FFFFFFFFFFFFFFFFh
0x180012433  inc     r8
0x180012436  cmp     [rax+r8*2], di
0x18001243b  jnz     short loc_180012433
0x18001243d  lea     rdx, [rbp+8F0h+Src]; Src
0x180012441  lea     rcx, [rbp+8F0h+SystemTime]; void *
0x180012445  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x18001244a  xor     r8d, r8d
0x18001244d  lea     rcx, [rbp+8F0h+SystemTime]
0x180012451  call    ?find_first_of@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KG_K@Z; std::wstring::find_first_of(ushort,unsigned __int64)
0x180012456  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001245a  jnz     short loc_180012484
0x18001245c  cmp     [rbp+8F0h+var_898], 8
0x180012461  jb      short loc_180012473
0x180012463  mov     rcx, qword ptr [rbp+8F0h+SystemTime.wYear]
0x180012467  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001246e  nop     dword ptr [rax+rax+00h]
0x180012473  mov     [rbp+8F0h+var_898], r12
0x180012477  mov     [rbp+8F0h+var_8A0], rdi
0x18001247b  mov     [rbp+8F0h+SystemTime.wYear], di
0x18001247f  jmp     loc_180012541
0x180012484  lea     rsi, [rax+1]
0x180012488  mov     r8, rsi
0x18001248b  lea     rcx, [rbp+8F0h+SystemTime]
0x18001248f  call    ?find_first_of@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KG_K@Z; std::wstring::find_first_of(ushort,unsigned __int64)
0x180012494  mov     r15, rax
0x180012497  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001249b  jnz     short loc_1800124C2
0x18001249d  cmp     [rbp+8F0h+var_898], 8
0x1800124a2  jb      short loc_1800124B4
0x1800124a4  mov     rcx, qword ptr [rbp+8F0h+SystemTime.wYear]
0x1800124a8  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800124af  nop     dword ptr [rax+rax+00h]
0x1800124b4  mov     [rbp+8F0h+var_898], r12
0x1800124b8  mov     [rbp+8F0h+var_8A0], rdi
0x1800124bc  mov     [rbp+8F0h+SystemTime.wYear], di
0x1800124c0  jmp     short loc_180012541
0x1800124c2  mov     r9d, 0Ah; Radix
0x1800124c8  lea     r12d, [r9+6]
0x1800124cc  mov     r8d, r12d; BufferCount
0x1800124cf  lea     rdx, [rbp+8F0h+Buffer]; Buffer
0x1800124d6  mov     ecx, [rsp+9F0h+cbData]; Value
0x1800124da  call    cs:__imp__ultow_s
0x1800124e1  nop     dword ptr [rax+rax+00h]
0x1800124e6  mov     edx, r12d; MaxCount
0x1800124e9  lea     rcx, [rbp+8F0h+Buffer]; Source
0x1800124f0  call    cs:__imp_wcsnlen
0x1800124f7  nop     dword ptr [rax+rax+00h]
0x1800124fc  mov     r12, rax
0x1800124ff  mov     r13, [rbp+8F0h+var_8A0]
0x180012503  sub     r13, r15
0x180012506  inc     r13
0x180012509  lea     rcx, [rsi+r13]
0x18001250d  add     rcx, rax
0x180012510  mov     edx, 402h
0x180012515  cmp     rcx, rdx
0x180012518  jbe     short loc_180012560
0x18001251a  cmp     [rbp+8F0h+var_898], 8
0x18001251f  jb      short loc_180012531
0x180012521  mov     rcx, qword ptr [rbp+8F0h+SystemTime.wYear]
0x180012525  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001252c  nop     dword ptr [rax+rax+00h]
0x180012531  mov     [rbp+8F0h+var_898], 7
0x180012539  mov     [rbp+8F0h+var_8A0], rdi
0x18001253d  mov     [rbp+8F0h+SystemTime.wYear], di
0x180012541  test    r14, r14
0x180012544  jz      short loc_180012556
0x180012546  mov     rcx, r14; hKey
0x180012549  call    cs:__imp_RegCloseKey
0x180012550  nop     dword ptr [rax+rax+00h]
0x180012555  nop
0x180012556  mov     eax, 80004005h
0x18001255b  jmp     loc_1800127F8
0x180012560  lea     rdi, [rbp+8F0h+Src]
0x180012564  lea     rdi, [rdi+rsi*2]
0x180012568  sub     edx, esi; SizeInWords
0x18001256a  mov     esi, edx
0x18001256c  mov     r9, r12; MaxCount
0x18001256f  lea     r8, [rbp+8F0h+Buffer]; Source
0x180012576  mov     rcx, rdi; Destination
0x180012579  call    cs:__imp_wcsncpy_s
0x180012580  nop     dword ptr [rax+rax+00h]
0x180012585  lea     rdi, [rdi+r12*2]
0x180012589  sub     esi, r12d
0x18001258c  lea     rax, [rbp+8F0h+SystemTime]
0x180012590  cmp     [rbp+8F0h+var_898], 8
0x180012595  cmovnb  rax, qword ptr [rbp+8F0h+SystemTime.wYear]
0x18001259a  lea     r8, [rax+r15*2]; Source
0x18001259e  mov     edx, esi; SizeInWords
0x1800125a0  mov     r9, r13; MaxCount
0x1800125a3  mov     rcx, rdi; Destination
0x1800125a6  call    cs:__imp_wcsncpy_s
0x1800125ad  nop     dword ptr [rax+rax+00h]
0x1800125b2  lea     rdi, [rdi+r13*2]
0x1800125b6  sub     esi, r13d
0x1800125b9  cmp     [rbp+8F0h+var_898], 8
0x1800125be  jb      short loc_1800125D0
0x1800125c0  mov     rcx, qword ptr [rbp+8F0h+SystemTime.wYear]
0x1800125c4  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800125cb  nop     dword ptr [rax+rax+00h]
0x1800125d0  mov     [rbp+8F0h+var_898], 7
0x1800125d8  xor     eax, eax
0x1800125da  mov     [rbp+8F0h+var_8A0], rax
0x1800125de  mov     [rbp+8F0h+SystemTime.wYear], ax
0x1800125e2  mov     r15, [rsp+9F0h+var_980]
0x1800125e7  mov     r12d, [rsp+9F0h+var_9A0]
0x1800125ec  mov     r13d, [rsp+9F0h+var_99C]
0x1800125f1  jmp     short loc_180012634
0x1800125f3  mov     [rsp+9F0h+Type], esi
0x1800125f7  lea     r9, [rsp+9F0h+Type]; unsigned int *
0x1800125fc  lea     r8, [rbp+8F0h+Src]; unsigned __int16 *
0x180012600  lea     rdx, aBuildlab; "BuildLab"
0x180012607  lea     rcx, [rsp+9F0h+var_998]; this
0x18001260c  call    ?QueryStringValue@CRegKey@ATL@@QEAAJPEBGPEAGPEAK@Z; ATL::CRegKey::QueryStringValue(ushort const *,ushort *,ulong *)
0x180012611  test    eax, eax
0x180012613  jnz     short loc_18001262C
0x180012615  mov     eax, [rsp+9F0h+Type]
0x180012619  lea     rdi, [rbp+8F0h+Src]
0x18001261d  lea     rdi, [rdi+rax*2]
0x180012621  mov     esi, 402h
0x180012626  sub     esi, [rsp+9F0h+Type]
0x18001262a  jmp     short loc_180012634
0x18001262c  mov     [rbp+8F0h+Src], di
0x180012630  lea     rdi, [rbp+8F0h+var_876]
0x180012634  mov     [rsp+9F0h+Type], esi
0x180012638  lea     r9, [rsp+9F0h+Type]; unsigned int *
0x18001263d  mov     r8, rdi; unsigned __int16 *
0x180012640  lea     rdx, aProductname; "ProductName"
0x180012647  lea     rcx, [rsp+9F0h+var_998]; this
0x18001264c  call    ?QueryStringValue@CRegKey@ATL@@QEAAJPEBGPEAGPEAK@Z; ATL::CRegKey::QueryStringValue(ushort const *,ushort *,ulong *)
0x180012651  xor     esi, esi
0x180012653  test    eax, eax
0x180012655  jnz     short loc_180012661
0x180012657  mov     eax, [rsp+9F0h+Type]
0x18001265b  lea     rdi, [rdi+rax*2]
0x18001265f  jmp     short loc_180012668
0x180012661  mov     [rdi], si
0x180012664  add     rdi, 2
0x180012668  xor     edx, edx; hFile
0x18001266a  mov     r8d, 800h; dwFlags
0x180012670  lea     rcx, LibFileName; "ntdll.dll"
0x180012677  call    cs:__imp_LoadLibraryExW
0x18001267e  nop     dword ptr [rax+rax+00h]
0x180012683  test    rax, rax
  ... truncated ...
```
