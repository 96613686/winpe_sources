# CVRoots::Init(void)

- ea: `0x18002d240`
- end: `0x18002d57f`
- name: `?Init@CVRoots@@AEAAHXZ`
- size: `831`
- prototype: `__int64 __fastcall(CVRoots *__hidden this)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180014580`

## callees

- `0x18001bbc0`
- `0x18002d240`
- `0x18002d588`
- `0x18002d5cc`
- `0x180031718`
- `0x180034bec`
- `0x1800350b4`
- `0x18003a33c`
- `0x18003a42c`
- `0x18003af3c`
- `0x18003bb6c`
- `0x18003cb60`
- `0x18003d4b0`
- `0x180051cdc`
- `0x180051f20`
- `0x180051ff0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18002d26c`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18002d26c`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18002d43b`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18002d43b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002d2df`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002d36b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002d2df`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002d36b`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18002d3be`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18002d3be`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18002d477`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18002d477`

## pseudocode

```c
__int64 __fastcall CVRoots::Init(struct _RTL_CRITICAL_SECTION *this)
{
  const unsigned __int16 *v2; // rdi
  HKEY v3; // rdx
  void *v4; // rdx
  DWORD v5; // eax
  void *v6; // rax
  int i; // edi
  DWORD v8; // edx
  unsigned int v9; // r9d
  int v10; // eax
  const unsigned __int16 *v11; // rdx
  __int64 v12; // rsi
  CVRoots *v13; // rcx
  unsigned int v14; // eax
  CVRoots *v15; // rcx
  DWORD cSubKeys; // [rsp+60h] [rbp-A0h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-98h] BYREF
  DWORD dwIndex; // [rsp+70h] [rbp-90h]
  __int64 v20; // [rsp+78h] [rbp-88h]
  HKEY v21; // [rsp+80h] [rbp-80h] BYREF
  int v22; // [rsp+88h] [rbp-78h]
  __int64 v23; // [rsp+90h] [rbp-70h]
  HKEY phkResult; // [rsp+98h] [rbp-68h] BYREF
  int v25; // [rsp+A0h] [rbp-60h]
  __int64 v26; // [rsp+A8h] [rbp-58h]
  unsigned __int16 v27[264]; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR Name[264]; // [rsp+2C0h] [rbp+1C0h] BYREF
  unsigned __int16 v29[272]; // [rsp+4D0h] [rbp+3D0h] BYREF
  unsigned __int16 v30[264]; // [rsp+6F0h] [rbp+5F0h] BYREF

  InitializeCriticalSection(this);
  memset_0(v29, 0, 0x214u);
  v30[0] = 0;
  Name[0] = 0;
  hKey = 0;
  dwIndex = 0;
  v20 = 0;
  phkResult = 0;
  v25 = 0;
  v26 = 0;
  RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\MICROSOFT\\UPnP Device Host", 0, 0x20019u, &phkResult);
  v2 = CReg::ValueSZ((CReg *)&phkResult, L"RedirectionKey");
  if ( v2 )
  {
    memset_0(v27, 0, 0x20Au);
    StringCbCopyW(v27, 0x20Au, v2);
    StringCbCatW(v27, 0x20Au, L"\\HTTP Server\\VROOTS");
    if ( !CReg::Create((CReg *)&hKey, v3, v27) )
      goto LABEL_17;
  }
  else if ( RegOpenKeyExW(
              HKEY_LOCAL_MACHINE,
              L"SOFTWARE\\MICROSOFT\\UPnP Device Host\\HTTP Server\\VROOTS",
              0,
              0x20019u,
              &hKey) )
  {
    goto LABEL_17;
  }
  cSubKeys = 0;
  RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
  v5 = cSubKeys;
  LODWORD(this[1].DebugInfo) = cSubKeys;
  if ( v5 )
  {
    v6 = svsutil_AllocZ(56 * v5, v4);
    *(_QWORD *)&this[1].LockCount = v6;
    if ( v6 )
    {
      for ( i = 0; i < SLODWORD(this[1].DebugInfo); ++i )
      {
        cSubKeys = 261;
        if ( !hKey )
          break;
        v8 = dwIndex++;
        if ( RegEnumKeyExW(hKey, v8, Name, &cSubKeys, 0, 0, 0, 0) )
          break;
        v21 = 0;
        v22 = 0;
        v23 = 0;
        CReg::Open(&v21, hKey, Name, v9);
        v10 = lstrlenW(L"\\\\?\\");
        if ( CReg::ValueSZ((CReg *)&v21, v11, v30, 261 - v10) )
        {
          StringCbCopyW(v29, 0x214u, L"\\\\?\\");
          StringCbCatW(v29, 0x214u, v30);
          v12 = 56LL * i;
          if ( !CVRoots::FillVRoot(v13, (struct VROOTINFO *)(v12 + *(_QWORD *)&this[1].LockCount), Name, v29) )
          {
            CReg::~CReg((CReg *)&v21);
            goto LABEL_17;
          }
          v14 = CReg::ValueDW((CReg *)&v21, L"p", 0x205u);
          v15 = *(CVRoots **)&this[1].LockCount;
          *(_DWORD *)((char *)v15 + v12 + 32) = v14;
          CVRoots::LoadExtensionMap(v15, (struct VROOTINFO *)(v12 + *(_QWORD *)&this[1].LockCount), v21);
        }
        CReg::Reset((CReg *)&v21);
        CReg::~CReg((CReg *)&v21);
      }
      CVRoots::Sort((CVRoots *)this);
    }
  }
LABEL_17:
  CReg::~CReg((CReg *)&phkResult);
  CReg::~CReg((CReg *)&hKey);
  return 1;
}

```

## disassembly

```asm
0x18002d240  push    rbp
0x18002d242  push    rbx
0x18002d243  push    rsi
0x18002d244  push    rdi
0x18002d245  push    r12
0x18002d247  push    r14
0x18002d249  lea     rbp, [rsp-818h]
0x18002d251  sub     rsp, 918h
0x18002d258  mov     rax, cs:__security_cookie
0x18002d25f  xor     rax, rsp
0x18002d262  mov     [rbp+840h+var_40], rax
0x18002d269  mov     rbx, rcx
0x18002d26c  call    cs:__imp_InitializeCriticalSection
0x18002d273  nop     dword ptr [rax+rax+00h]
0x18002d278  mov     r12d, 214h
0x18002d27e  lea     rcx, [rbp+840h+var_470]; void *
0x18002d285  mov     r8d, r12d; Size
0x18002d288  xor     edx, edx; Val
0x18002d28a  call    memset_0
0x18002d28f  xor     r14d, r14d
0x18002d292  lea     rax, [rbp+840h+var_8A8]
0x18002d296  mov     esi, 20019h
0x18002d29b  mov     [rsp+940h+phkResult], rax; phkResult
0x18002d2a0  mov     r9d, esi; samDesired
0x18002d2a3  mov     [rbp+840h+var_250], r14w
0x18002d2ab  xor     r8d, r8d; ulOptions
0x18002d2ae  mov     [rbp+840h+Name], r14w
0x18002d2b6  lea     rdx, aSoftwareMicros; "SOFTWARE\\MICROSOFT\\UPnP Device Host"
0x18002d2bd  mov     [rsp+940h+hKey], r14
0x18002d2c2  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002d2c9  mov     [rsp+940h+dwIndex], r14d
0x18002d2ce  mov     [rsp+940h+var_8C8], r14
0x18002d2d3  mov     [rbp+840h+var_8A8], r14
0x18002d2d7  mov     [rbp+840h+var_8A0], r14d
0x18002d2db  mov     [rbp+840h+var_898], r14
0x18002d2df  call    cs:__imp_RegOpenKeyExW
0x18002d2e6  nop     dword ptr [rax+rax+00h]
0x18002d2eb  lea     rdx, aRedirectionkey; "RedirectionKey"
0x18002d2f2  lea     rcx, [rbp+840h+var_8A8]; this
0x18002d2f6  call    ?ValueSZ@CReg@@QEAAPEBGPEBG@Z; CReg::ValueSZ(ushort const *)
0x18002d2fb  mov     rdi, rax
0x18002d2fe  test    rax, rax
0x18002d301  jz      short loc_18002D34D
0x18002d303  lea     esi, [r12-0Ah]
0x18002d308  xor     edx, edx; Val
0x18002d30a  mov     r8d, esi; Size
0x18002d30d  lea     rcx, [rbp+840h+var_890]; void *
0x18002d311  call    memset_0
0x18002d316  mov     r8, rdi; unsigned __int16 *
0x18002d319  lea     rcx, [rbp+840h+var_890]; unsigned __int16 *
0x18002d31d  mov     edx, esi; unsigned __int64
0x18002d31f  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x18002d324  lea     r8, aHttpServerVroo; "\\HTTP Server\\VROOTS"
0x18002d32b  mov     edx, esi; unsigned __int64
0x18002d32d  lea     rcx, [rbp+840h+var_890]; unsigned __int16 *
0x18002d331  call    ?StringCbCatW@@YAJPEAG_KPEBG@Z; StringCbCatW(ushort *,unsigned __int64,ushort const *)
0x18002d336  lea     r8, [rbp+840h+var_890]; unsigned __int16 *
0x18002d33a  lea     rcx, [rsp+940h+hKey]; this
0x18002d33f  call    ?Create@CReg@@QEAAHPEAUHKEY__@@PEBG@Z; CReg::Create(HKEY__ *,ushort const *)
0x18002d344  test    eax, eax
0x18002d346  jnz     short loc_18002D37F
0x18002d348  jmp     loc_18002D547
0x18002d34d  lea     rax, [rsp+940h+hKey]
0x18002d352  mov     r9d, esi; samDesired
0x18002d355  xor     r8d, r8d; ulOptions
0x18002d358  mov     [rsp+940h+phkResult], rax; phkResult
0x18002d35d  lea     rdx, aSoftwareMicros_3; "SOFTWARE\\MICROSOFT\\UPnP Device Host\\"...
0x18002d364  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002d36b  call    cs:__imp_RegOpenKeyExW
0x18002d372  nop     dword ptr [rax+rax+00h]
0x18002d377  test    eax, eax
0x18002d379  jnz     loc_18002D547
0x18002d37f  mov     rcx, [rsp+940h+hKey]; hKey
0x18002d384  lea     rax, [rsp+940h+cSubKeys]
0x18002d389  mov     [rsp+940h+lpftLastWriteTime], r14; lpftLastWriteTime
0x18002d38e  xor     r9d, r9d; lpReserved
0x18002d391  mov     [rsp+940h+lpcbSecurityDescriptor], r14; lpcbSecurityDescriptor
0x18002d396  xor     r8d, r8d; lpcchClass
0x18002d399  mov     [rsp+940h+lpcbMaxValueLen], r14; lpcbMaxValueLen
0x18002d39e  xor     edx, edx; lpClass
0x18002d3a0  mov     [rsp+940h+lpcbMaxValueNameLen], r14; lpcbMaxValueNameLen
0x18002d3a5  mov     [rsp+940h+lpcValues], r14; lpcValues
0x18002d3aa  mov     [rsp+940h+lpcbMaxClassLen], r14; lpcbMaxClassLen
0x18002d3af  mov     [rsp+940h+lpcbMaxSubKeyLen], r14; lpcbMaxSubKeyLen
0x18002d3b4  mov     [rsp+940h+phkResult], rax; lpcSubKeys
0x18002d3b9  mov     [rsp+940h+cSubKeys], r14d
0x18002d3be  call    cs:__imp_RegQueryInfoKeyW
0x18002d3c5  nop     dword ptr [rax+rax+00h]
0x18002d3ca  mov     eax, [rsp+940h+cSubKeys]
0x18002d3ce  mov     [rbx+28h], eax
0x18002d3d1  test    eax, eax
0x18002d3d3  jz      loc_18002D547
0x18002d3d9  imul    ecx, eax, 38h ; '8'; Size
0x18002d3dc  call    ?svsutil_AllocZ@@YAPEAXKPEAX@Z; svsutil_AllocZ(ulong,void *)
0x18002d3e1  mov     [rbx+30h], rax
0x18002d3e5  test    rax, rax
0x18002d3e8  jz      loc_18002D547
0x18002d3ee  mov     edi, r14d
0x18002d3f1  cmp     edi, [rbx+28h]
0x18002d3f4  jge     loc_18002D53F
0x18002d3fa  mov     rcx, [rsp+940h+hKey]; hKey
0x18002d3ff  mov     [rsp+940h+cSubKeys], 105h
0x18002d407  test    rcx, rcx
0x18002d40a  jz      loc_18002D53F
0x18002d410  mov     edx, [rsp+940h+dwIndex]; dwIndex
0x18002d414  lea     r9, [rsp+940h+cSubKeys]; lpcchName
0x18002d419  mov     [rsp+940h+lpcValues], r14; lpftLastWriteTime
0x18002d41e  lea     r8, [rbp+840h+Name]; lpName
0x18002d425  mov     [rsp+940h+lpcbMaxClassLen], r14; lpcchClass
0x18002d42a  mov     [rsp+940h+lpcbMaxSubKeyLen], r14; lpClass
0x18002d42f  lea     eax, [rdx+1]
0x18002d432  mov     [rsp+940h+phkResult], r14; lpReserved
0x18002d437  mov     [rsp+940h+dwIndex], eax
0x18002d43b  call    cs:__imp_RegEnumKeyExW
0x18002d442  nop     dword ptr [rax+rax+00h]
0x18002d447  test    eax, eax
0x18002d449  jnz     loc_18002D53F
0x18002d44f  mov     rdx, [rsp+940h+hKey]; hKey
0x18002d454  lea     r8, [rbp+840h+Name]; lpSubKey
0x18002d45b  lea     rcx, [rbp+840h+var_8C0]; phkResult
0x18002d45f  mov     [rbp+840h+var_8C0], r14
0x18002d463  mov     [rbp+840h+var_8B8], r14d
0x18002d467  mov     [rbp+840h+var_8B0], r14
0x18002d46b  call    ?Open@CReg@@QEAAHPEAUHKEY__@@PEBGK@Z; CReg::Open(HKEY__ *,ushort const *,ulong)
0x18002d470  lea     rcx, asc_18006A080; "\\\\?\\"
0x18002d477  call    cs:__imp_lstrlenW
0x18002d47e  nop     dword ptr [rax+rax+00h]
0x18002d483  mov     r9d, 105h
0x18002d489  lea     r8, [rbp+840h+var_250]; unsigned __int16 *
0x18002d490  sub     r9d, eax; unsigned int
0x18002d493  lea     rcx, [rbp+840h+var_8C0]; this
0x18002d497  call    ?ValueSZ@CReg@@QEAAHPEBGPEAGK@Z; CReg::ValueSZ(ushort const *,ushort *,ulong)
0x18002d49c  test    eax, eax
0x18002d49e  jz      short loc_18002D51F
0x18002d4a0  lea     r8, asc_18006A080; "\\\\?\\"
0x18002d4a7  mov     rdx, r12; unsigned __int64
0x18002d4aa  lea     rcx, [rbp+840h+var_470]; unsigned __int16 *
0x18002d4b1  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x18002d4b6  lea     r8, [rbp+840h+var_250]; unsigned __int16 *
0x18002d4bd  mov     rdx, r12; unsigned __int64
0x18002d4c0  lea     rcx, [rbp+840h+var_470]; unsigned __int16 *
0x18002d4c7  call    ?StringCbCatW@@YAJPEAG_KPEBG@Z; StringCbCatW(ushort *,unsigned __int64,ushort const *)
0x18002d4cc  mov     rdx, [rbx+30h]
0x18002d4d0  lea     r9, [rbp+840h+var_470]; unsigned __int16 *
0x18002d4d7  movsxd  rax, edi
0x18002d4da  lea     r8, [rbp+840h+Name]; unsigned __int16 *
0x18002d4e1  imul    rsi, rax, 38h ; '8'
0x18002d4e5  add     rdx, rsi; struct VROOTINFO *
0x18002d4e8  call    ?FillVRoot@CVRoots@@AEAAHPEAUVROOTINFO@@PEAG1@Z; CVRoots::FillVRoot(VROOTINFO *,ushort *,ushort *)
0x18002d4ed  lea     rcx, [rbp+840h+var_8C0]; this
0x18002d4f1  test    eax, eax
0x18002d4f3  jz      short loc_18002D538
0x18002d4f5  mov     r8d, 205h; unsigned int
0x18002d4fb  lea     rdx, aP; "p"
0x18002d502  call    ?ValueDW@CReg@@QEAAKPEBGK@Z; CReg::ValueDW(ushort const *,ulong)
0x18002d507  mov     rcx, [rbx+30h]; this
0x18002d50b  mov     [rcx+rsi+20h], eax
0x18002d50f  mov     rdx, [rbx+30h]
0x18002d513  mov     r8, [rbp+840h+var_8C0]; HKEY
0x18002d517  add     rdx, rsi; struct VROOTINFO *
0x18002d51a  call    ?LoadExtensionMap@CVRoots@@AEAAHPEAUVROOTINFO@@PEAUHKEY__@@@Z; CVRoots::LoadExtensionMap(VROOTINFO *,HKEY__ *)
0x18002d51f  lea     rcx, [rbp+840h+var_8C0]; this
0x18002d523  call    ?Reset@CReg@@QEAAXXZ; CReg::Reset(void)
0x18002d528  lea     rcx, [rbp+840h+var_8C0]; this
0x18002d52c  call    ??1CReg@@QEAA@XZ; CReg::~CReg(void)
0x18002d531  inc     edi
0x18002d533  jmp     loc_18002D3F1
0x18002d538  call    ??1CReg@@QEAA@XZ; CReg::~CReg(void)
0x18002d53d  jmp     short loc_18002D547
0x18002d53f  mov     rcx, rbx; this
0x18002d542  call    ?Sort@CVRoots@@AEAAXXZ; CVRoots::Sort(void)
0x18002d547  lea     rcx, [rbp+840h+var_8A8]; this
0x18002d54b  call    ??1CReg@@QEAA@XZ; CReg::~CReg(void)
0x18002d550  lea     rcx, [rsp+940h+hKey]; this
0x18002d555  call    ??1CReg@@QEAA@XZ; CReg::~CReg(void)
0x18002d55a  mov     eax, 1
0x18002d55f  mov     rcx, [rbp+840h+var_40]
0x18002d566  xor     rcx, rsp; StackCookie
0x18002d569  call    __security_check_cookie
0x18002d56e  add     rsp, 918h
0x18002d575  pop     r14
0x18002d577  pop     r12
0x18002d579  pop     rdi
0x18002d57a  pop     rsi
0x18002d57b  pop     rbx
0x18002d57c  pop     rbp
0x18002d57d  retn
```
