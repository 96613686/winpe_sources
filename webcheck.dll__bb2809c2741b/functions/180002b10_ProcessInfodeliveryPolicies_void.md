# ProcessInfodeliveryPolicies(void)

- ea: `0x180002b10`
- end: `0x180002e25`
- name: `?ProcessInfodeliveryPolicies@@YAJXZ`
- size: `789`
- prototype: `__int64(void)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800024dc`
- `0x1800024f4`
- `0x180002520`
- `0x180002570`
- `0x1800026e4`
- `0x18000272c`
- `0x18000279c`
- `0x180002b10`
- `0x180002f20`
- `0x180029280`
- `0x18002a010`

## import_xrefs

- `KERNEL32!GetSystemTime` at `0x180002d50`
- `KERNEL32!GetSystemTime` at `0x180002d50`
- `KERNEL32!SystemTimeToFileTime` at `0x180002d5f`
- `KERNEL32!SystemTimeToFileTime` at `0x180002d5f`
- `SHLWAPI!StrCmpIW` at `0x180002c7a`
- `SHLWAPI!StrCmpIW` at `0x180002c7a`
- `SHLWAPI!SHDeleteKeyW` at `0x180002db0`
- `SHLWAPI!SHDeleteKeyW` at `0x180002db0`
- `iertutil!__imp_DPA_GetPtr` at `0x180002d00`
- `iertutil!__imp_DPA_GetPtr` at `0x180002d00`
- `ADVAPI32!RegCreateKeyExW` at `0x180002bb8`
- `ADVAPI32!RegCreateKeyExW` at `0x180002bb8`
- `ADVAPI32!RegSetValueExW` at `0x180002d8a`
- `ADVAPI32!RegSetValueExW` at `0x180002d8a`
- `ole32!CoUninitialize` at `0x180002db6`
- `ole32!CoUninitialize` at `0x180002db6`
- `ole32!CoInitialize` at `0x180002bc8`
- `ole32!CoInitialize` at `0x180002bc8`

## string_xrefs

- `0x180002b93`: `Software\Policies\Microsoft\Internet Explorer\Infodelivery\CompletedModifications`

## pseudocode

```c
__int64 ProcessInfodeliveryPolicies(void)
{
  HRESULT v0; // edi
  __int64 v1; // rsi
  HDPA *v3; // rbx
  __int64 v4; // r14
  unsigned int i; // ebx
  __int64 v6; // r14
  unsigned int j; // r14d
  int v8; // eax
  int v9; // r12d
  void (__fastcall *v10)(PVOID); // rbx
  PVOID Ptr; // rax
  CRegKeyDPA *v12; // rbx
  DWORD dwDisposition; // [rsp+50h] [rbp-B0h] BYREF
  HKEY v14; // [rsp+58h] [rbp-A8h] BYREF
  int v15; // [rsp+60h] [rbp-A0h]
  struct _FILETIME FileTime; // [rsp+68h] [rbp-98h] BYREF
  int v17; // [rsp+70h] [rbp-90h]
  HKEY hKey; // [rsp+78h] [rbp-88h] BYREF
  int v19; // [rsp+80h] [rbp-80h]
  _SYSTEMTIME SystemTime; // [rsp+88h] [rbp-78h] BYREF
  HDPA hdpa[6]; // [rsp+98h] [rbp-68h] BYREF
  char v22; // [rsp+C8h] [rbp-38h] BYREF
  WCHAR ValueName[264]; // [rsp+D0h] [rbp-30h] BYREF
  WCHAR psz2[264]; // [rsp+2E0h] [rbp+1E0h] BYREF

  v14 = 0;
  v15 = 0;
  if ( (int)CRegKey::OpenForRead(
              &v14,
              HKEY_CURRENT_USER,
              L"Software\\Policies\\Microsoft\\Internet Explorer\\Infodelivery\\Modifications") < 0 )
  {
    v0 = 1;
LABEL_6:
    CRegKey::~CRegKey((CRegKey *)&v14);
    return (unsigned int)v0;
  }
  hKey = 0;
  v19 = 0;
  v1 = 3;
  dwDisposition = 0;
  if ( RegCreateKeyExW(
         HKEY_CURRENT_USER,
         L"Software\\Policies\\Microsoft\\Internet Explorer\\Infodelivery\\CompletedModifications",
         0,
         (LPWSTR)&Default,
         0,
         3u,
         0,
         &hKey,
         &dwDisposition) )
  {
    CRegKey::~CRegKey((CRegKey *)&hKey);
    CRegKey::~CRegKey((CRegKey *)&v14);
    return 2147500037LL;
  }
  else
  {
    v0 = CoInitialize(0);
    if ( v0 < 0 )
    {
      CRegKey::~CRegKey((CRegKey *)&hKey);
      goto LABEL_6;
    }
    v3 = hdpa;
    v4 = 3;
    do
    {
      CRegKeyDPA::CRegKeyDPA((CRegKeyDPA *)v3);
      v3 += 2;
      --v4;
    }
    while ( v4 );
    while ( !CRegKey::Next((CRegKey *)&v14, ValueName) )
    {
      dwDisposition = 0;
      if ( (int)CRegKey::GetValue((CRegKey *)&hKey, ValueName, &dwDisposition) < 0 )
      {
        FileTime = 0;
        v17 = 0;
        CRegKey::OpenForRead((PHKEY)&FileTime, v14, ValueName);
LABEL_17:
        while ( !CRegKey::Next((CRegKey *)&FileTime, psz2) )
        {
          for ( i = 0; i < 3; ++i )
          {
            v6 = 2LL * (int)i;
            if ( !StrCmpIW(*(PCWSTR *)((char *)&rgActionTable + v6 * 8), psz2) )
            {
              CRegKeyDPA::Add((CRegKeyDPA *)&hdpa[v6], *(HKEY *)&FileTime, psz2);
              goto LABEL_17;
            }
          }
        }
        CRegKey::~CRegKey((CRegKey *)&FileTime);
      }
    }
    for ( j = 0; j < 3; ++j )
    {
      v8 = (int)hdpa[2 * (int)j + 1];
      if ( v8 )
      {
        v9 = 0;
        if ( v8 > 0 )
        {
          do
          {
            v10 = (void (__fastcall *)(PVOID))*(&funcs_180002D0C + 2 * (int)j);
            Ptr = DPA_GetPtr(hdpa[2 * (int)j], v9);
            v10(Ptr);
            ++v9;
          }
          while ( v9 < SLODWORD(hdpa[2 * (int)j + 1]) );
        }
      }
    }
    v15 = 0;
    while ( !CRegKey::Next((CRegKey *)&v14, ValueName) )
    {
      FileTime = 0;
      SystemTime = 0;
      GetSystemTime(&SystemTime);
      SystemTimeToFileTime(&SystemTime, &FileTime);
      dwDisposition = FileTime.dwHighDateTime;
      RegSetValueExW(hKey, ValueName, 0, 4u, (const BYTE *)&dwDisposition, 4u);
    }
    SHDeleteKeyW(HKEY_CURRENT_USER, L"Software\\Policies\\Microsoft\\Internet Explorer\\Infodelivery\\Modifications");
    CoUninitialize();
    v12 = (CRegKeyDPA *)&v22;
    do
    {
      v12 = (CRegKeyDPA *)((char *)v12 - 16);
      CRegKeyDPA::~CRegKeyDPA(v12);
      --v1;
    }
    while ( v1 );
    CRegKey::~CRegKey((CRegKey *)&hKey);
    CRegKey::~CRegKey((CRegKey *)&v14);
    return 0;
  }
}

```

## disassembly

```asm
0x180002b10  push    rbp
0x180002b12  push    rbx
0x180002b13  push    rsi
0x180002b14  push    rdi
0x180002b15  push    r12
0x180002b17  push    r13
0x180002b19  push    r14
0x180002b1b  push    r15
0x180002b1d  lea     rbp, [rsp-408h]
0x180002b25  sub     rsp, 508h
0x180002b2c  mov     rax, cs:__security_cookie
0x180002b33  xor     rax, rsp
0x180002b36  mov     [rbp+440h+var_50], rax
0x180002b3d  xor     r13d, r13d
0x180002b40  lea     r8, pszSubKey; "Software\\Policies\\Microsoft\\Internet"...
0x180002b47  mov     rbx, 0FFFFFFFF80000001h
0x180002b4e  mov     [rsp+540h+var_4E8], r13
0x180002b53  mov     rdx, rbx; hKey
0x180002b56  mov     [rsp+540h+var_4E0], r13d
0x180002b5b  lea     rcx, [rsp+540h+var_4E8]; phkResult
0x180002b60  call    ?OpenForRead@CRegKey@@QEAAJPEAUHKEY__@@PEBG@Z; CRegKey::OpenForRead(HKEY__ *,ushort const *)
0x180002b65  test    eax, eax
0x180002b67  jns     short loc_180002B6F
0x180002b69  lea     edi, [r13+1]
0x180002b6d  jmp     short loc_180002BDE
0x180002b6f  lea     rax, [rsp+540h+dwDisposition]
0x180002b74  mov     [rsp+540h+hKey], r13
0x180002b79  mov     [rsp+540h+lpdwDisposition], rax; lpdwDisposition
0x180002b7e  lea     r9, Default; lpClass
0x180002b85  lea     rax, [rsp+540h+hKey]
0x180002b8a  mov     [rbp+440h+var_4C0], r13d
0x180002b8e  mov     [rsp+540h+phkResult], rax; phkResult
0x180002b93  lea     rdx, SubKey; "Software\\Policies\\Microsoft\\Internet"...
0x180002b9a  mov     [rsp+540h+lpSecurityAttributes], r13; lpSecurityAttributes
0x180002b9f  mov     esi, 3
0x180002ba4  mov     [rsp+540h+samDesired], esi; samDesired
0x180002ba8  xor     r8d, r8d; Reserved
0x180002bab  mov     rcx, rbx; hKey
0x180002bae  mov     [rsp+540h+dwOptions], r13d; dwOptions
0x180002bb3  mov     [rsp+540h+dwDisposition], r13d
0x180002bb8  call    cs:__imp_RegCreateKeyExW
0x180002bbe  test    eax, eax
0x180002bc0  jnz     loc_180002DE9
0x180002bc6  xor     ecx, ecx; pvReserved
0x180002bc8  call    cs:__imp_CoInitialize
0x180002bce  mov     edi, eax
0x180002bd0  test    eax, eax
0x180002bd2  jns     short loc_180002BEF
0x180002bd4  lea     rcx, [rsp+540h+hKey]; this
0x180002bd9  call    ??1CRegKey@@QEAA@XZ; CRegKey::~CRegKey(void)
0x180002bde  lea     rcx, [rsp+540h+var_4E8]; this
0x180002be3  call    ??1CRegKey@@QEAA@XZ; CRegKey::~CRegKey(void)
0x180002be8  mov     eax, edi
0x180002bea  jmp     loc_180002E02
0x180002bef  lea     rbx, [rbp+440h+hdpa]
0x180002bf3  mov     r14, rsi
0x180002bf6  mov     edi, 1
0x180002bfb  mov     rcx, rbx; this
0x180002bfe  call    ??0CRegKeyDPA@@QEAA@XZ; CRegKeyDPA::CRegKeyDPA(void)
0x180002c03  add     rbx, 10h
0x180002c07  sub     r14, rdi
0x180002c0a  jnz     short loc_180002BFB
0x180002c0c  lea     rdx, [rbp+440h+ValueName]; unsigned __int16 *
0x180002c10  lea     rcx, [rsp+540h+var_4E8]; this
0x180002c15  call    ?Next@CRegKey@@QEAAJPEAG@Z; CRegKey::Next(ushort *)
0x180002c1a  lea     r15, ?rgActionTable@@3PAUACTIONTABLE@@A; ACTIONTABLE near * rgActionTable
0x180002c21  jmp     loc_180002CCD
0x180002c26  lea     r8, [rsp+540h+dwDisposition]; unsigned int *
0x180002c2b  mov     [rsp+540h+dwDisposition], r13d
0x180002c30  lea     rdx, [rbp+440h+ValueName]; unsigned __int16 *
0x180002c34  lea     rcx, [rsp+540h+hKey]; this
0x180002c39  call    ?GetValue@CRegKey@@QEAAJPEBGPEAK@Z; CRegKey::GetValue(ushort const *,ulong *)
0x180002c3e  test    eax, eax
0x180002c40  jns     short loc_180002CBF
0x180002c42  mov     rdx, [rsp+540h+var_4E8]; hKey
0x180002c47  lea     r8, [rbp+440h+ValueName]; lpSubKey
0x180002c4b  lea     rcx, [rsp+540h+FileTime]; phkResult
0x180002c50  mov     qword ptr [rsp+540h+FileTime.dwLowDateTime], r13
0x180002c55  mov     [rsp+540h+var_4D0], r13d
0x180002c5a  call    ?OpenForRead@CRegKey@@QEAAJPEAUHKEY__@@PEBG@Z; CRegKey::OpenForRead(HKEY__ *,ushort const *)
0x180002c5f  jmp     short loc_180002CA0
0x180002c61  mov     ebx, r13d
0x180002c64  cmp     ebx, esi
0x180002c66  jnb     short loc_180002CA0
0x180002c68  movsxd  r14, ebx
0x180002c6b  lea     rdx, [rbp+440h+psz2]; psz2
0x180002c72  shl     r14, 4
0x180002c76  mov     rcx, [r14+r15]; psz1
0x180002c7a  call    cs:__imp_StrCmpIW
0x180002c80  test    eax, eax
0x180002c82  jz      short loc_180002C88
0x180002c84  add     ebx, edi
0x180002c86  jmp     short loc_180002C64
0x180002c88  mov     rdx, qword ptr [rsp+540h+FileTime.dwLowDateTime]; HKEY
0x180002c8d  lea     rcx, [rbp+440h+hdpa]
0x180002c91  add     rcx, r14; this
0x180002c94  lea     r8, [rbp+440h+psz2]; unsigned __int16 *
0x180002c9b  call    ?Add@CRegKeyDPA@@QEAAJPEAUHKEY__@@PEBG@Z; CRegKeyDPA::Add(HKEY__ *,ushort const *)
0x180002ca0  lea     rdx, [rbp+440h+psz2]; unsigned __int16 *
0x180002ca7  lea     rcx, [rsp+540h+FileTime]; this
0x180002cac  call    ?Next@CRegKey@@QEAAJPEAG@Z; CRegKey::Next(ushort *)
0x180002cb1  test    eax, eax
0x180002cb3  jz      short loc_180002C61
0x180002cb5  lea     rcx, [rsp+540h+FileTime]; this
0x180002cba  call    ??1CRegKey@@QEAA@XZ; CRegKey::~CRegKey(void)
0x180002cbf  lea     rdx, [rbp+440h+ValueName]; unsigned __int16 *
0x180002cc3  lea     rcx, [rsp+540h+var_4E8]; this
0x180002cc8  call    ?Next@CRegKey@@QEAAJPEAG@Z; CRegKey::Next(ushort *)
0x180002ccd  test    eax, eax
0x180002ccf  jz      loc_180002C26
0x180002cd5  mov     r14d, r13d
0x180002cd8  movsxd  r15, r14d
0x180002cdb  add     r15, r15
0x180002cde  mov     eax, [rbp+r15*8+440h+var_4A0]
0x180002ce3  test    eax, eax
0x180002ce5  jz      short loc_180002D1E
0x180002ce7  mov     r12d, r13d
0x180002cea  jle     short loc_180002D1E
0x180002cec  lea     r13, ?rgActionTable@@3PAUACTIONTABLE@@A; ACTIONTABLE near * rgActionTable
0x180002cf3  mov     rcx, [rbp+r15*8+440h+hdpa]; hdpa
0x180002cf8  mov     rbx, (funcs_180002D0C - 180034000h)[r13+r15*8]
0x180002cfd  movsxd  rdx, r12d; i
0x180002d00  call    cs:__imp_DPA_GetPtr
0x180002d06  mov     rcx, rax; hKey
0x180002d09  mov     rax, rbx
0x180002d0c  call    _guard_dispatch_icall$thunk$10345483385596137414; ProcessRemoveSubscriptions(HKEY__ *) ...
0x180002d11  add     r12d, edi
0x180002d14  cmp     r12d, [rbp+r15*8+440h+var_4A0]
0x180002d19  jl      short loc_180002CF3
0x180002d1b  xor     r13d, r13d
0x180002d1e  add     r14d, edi
0x180002d21  cmp     r14d, esi
0x180002d24  jb      short loc_180002CD8
0x180002d26  lea     rdx, [rbp+440h+ValueName]; unsigned __int16 *
0x180002d2a  mov     [rsp+540h+var_4E0], r13d
0x180002d2f  lea     rcx, [rsp+540h+var_4E8]; this
0x180002d34  call    ?Next@CRegKey@@QEAAJPEAG@Z; CRegKey::Next(ushort *)
0x180002d39  test    eax, eax
0x180002d3b  jnz     short loc_180002DA2
0x180002d3d  lea     ebx, [rax+4]
0x180002d40  xorps   xmm0, xmm0
0x180002d43  mov     qword ptr [rsp+540h+FileTime.dwLowDateTime], r13
0x180002d48  lea     rcx, [rbp+440h+SystemTime]; lpSystemTime
0x180002d4c  movups  xmmword ptr [rbp+440h+SystemTime.wYear], xmm0
0x180002d50  call    cs:__imp_GetSystemTime
0x180002d56  lea     rdx, [rsp+540h+FileTime]; lpFileTime
0x180002d5b  lea     rcx, [rbp+440h+SystemTime]; lpSystemTime
0x180002d5f  call    cs:__imp_SystemTimeToFileTime
0x180002d65  mov     eax, [rsp+540h+FileTime.dwHighDateTime]
0x180002d69  lea     rdx, [rbp+440h+ValueName]; lpValueName
0x180002d6d  mov     rcx, [rsp+540h+hKey]; hKey
0x180002d72  mov     r9d, ebx; dwType
0x180002d75  mov     [rsp+540h+dwDisposition], eax
0x180002d79  xor     r8d, r8d; Reserved
0x180002d7c  lea     rax, [rsp+540h+dwDisposition]
0x180002d81  mov     [rsp+540h+samDesired], ebx; cbData
0x180002d85  mov     qword ptr [rsp+540h+dwOptions], rax; lpData
0x180002d8a  call    cs:__imp_RegSetValueExW
0x180002d90  lea     rdx, [rbp+440h+ValueName]; unsigned __int16 *
0x180002d94  lea     rcx, [rsp+540h+var_4E8]; this
0x180002d99  call    ?Next@CRegKey@@QEAAJPEAG@Z; CRegKey::Next(ushort *)
0x180002d9e  test    eax, eax
0x180002da0  jz      short loc_180002D40
0x180002da2  lea     rdx, pszSubKey; "Software\\Policies\\Microsoft\\Internet"...
0x180002da9  mov     rcx, 0FFFFFFFF80000001h; hkey
0x180002db0  call    cs:__imp_SHDeleteKeyW
0x180002db6  call    cs:__imp_CoUninitialize
0x180002dbc  lea     rbx, [rbp+440h+var_478]
0x180002dc0  sub     rbx, 10h
0x180002dc4  mov     rcx, rbx; this
0x180002dc7  call    ??1CRegKeyDPA@@QEAA@XZ; CRegKeyDPA::~CRegKeyDPA(void)
0x180002dcc  sub     rsi, rdi
0x180002dcf  jnz     short loc_180002DC0
0x180002dd1  lea     rcx, [rsp+540h+hKey]; this
0x180002dd6  call    ??1CRegKey@@QEAA@XZ; CRegKey::~CRegKey(void)
0x180002ddb  lea     rcx, [rsp+540h+var_4E8]; this
0x180002de0  call    ??1CRegKey@@QEAA@XZ; CRegKey::~CRegKey(void)
0x180002de5  xor     eax, eax
0x180002de7  jmp     short loc_180002E02
0x180002de9  lea     rcx, [rsp+540h+hKey]; this
0x180002dee  call    ??1CRegKey@@QEAA@XZ; CRegKey::~CRegKey(void)
0x180002df3  lea     rcx, [rsp+540h+var_4E8]; this
0x180002df8  call    ??1CRegKey@@QEAA@XZ; CRegKey::~CRegKey(void)
0x180002dfd  mov     eax, 80004005h
0x180002e02  mov     rcx, [rbp+440h+var_50]
0x180002e09  xor     rcx, rsp; StackCookie
0x180002e0c  call    __security_check_cookie
0x180002e11  add     rsp, 508h
0x180002e18  pop     r15
0x180002e1a  pop     r14
0x180002e1c  pop     r13
0x180002e1e  pop     r12
0x180002e20  pop     rdi
0x180002e21  pop     rsi
0x180002e22  pop     rbx
0x180002e23  pop     rbp
0x180002e24  retn
```
