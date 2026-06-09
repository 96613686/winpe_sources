# CVRoots::Init(void)

- ea: `0x18002bb38`
- end: `0x18002be52`
- name: `?Init@CVRoots@@AEAAHXZ`
- size: `794`
- prototype: `__int64 __fastcall(CVRoots *__hidden this)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001f41c`

## callees

- `0x180006f10`
- `0x18002bb38`
- `0x18002be58`
- `0x18002be90`
- `0x1800300e4`
- `0x180032d48`
- `0x1800331ac`
- `0x180037f28`
- `0x180037fdc`
- `0x180038a88`
- `0x1800395c0`
- `0x18003a560`
- `0x18003ae80`
- `0x18004e7b0`
- `0x18004e9e4`
- `0x18004eaa0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18002bb64`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18002bb64`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18002bd1b`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18002bd1b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002bbd1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002bc57`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002bbd1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002bc57`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18002bca4`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18002bca4`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18002bd51`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18002bd51`

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
    if ( !CReg::Create(&hKey, v3, v27) )
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
0x18002bb38  push    rbp
0x18002bb3a  push    rbx
0x18002bb3b  push    rsi
0x18002bb3c  push    rdi
0x18002bb3d  push    r12
0x18002bb3f  push    r14
0x18002bb41  lea     rbp, [rsp-818h]
0x18002bb49  sub     rsp, 918h
0x18002bb50  mov     rax, cs:__security_cookie
0x18002bb57  xor     rax, rsp
0x18002bb5a  mov     [rbp+840h+var_40], rax
0x18002bb61  mov     rbx, rcx
0x18002bb64  call    cs:__imp_InitializeCriticalSection
0x18002bb6a  mov     r12d, 214h
0x18002bb70  lea     rcx, [rbp+840h+var_470]; void *
0x18002bb77  mov     r8d, r12d; Size
0x18002bb7a  xor     edx, edx; Val
0x18002bb7c  call    memset_0
0x18002bb81  xor     r14d, r14d
0x18002bb84  lea     rax, [rbp+840h+var_8A8]
0x18002bb88  mov     esi, 20019h
0x18002bb8d  mov     [rsp+940h+phkResult], rax; phkResult
0x18002bb92  mov     r9d, esi; samDesired
0x18002bb95  mov     [rbp+840h+var_250], r14w
0x18002bb9d  xor     r8d, r8d; ulOptions
0x18002bba0  mov     [rbp+840h+Name], r14w
0x18002bba8  lea     rdx, aSoftwareMicros; "SOFTWARE\\MICROSOFT\\UPnP Device Host"
0x18002bbaf  mov     [rsp+940h+hKey], r14
0x18002bbb4  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002bbbb  mov     [rsp+940h+dwIndex], r14d
0x18002bbc0  mov     [rsp+940h+var_8C8], r14
0x18002bbc5  mov     [rbp+840h+var_8A8], r14
0x18002bbc9  mov     [rbp+840h+var_8A0], r14d
0x18002bbcd  mov     [rbp+840h+var_898], r14
0x18002bbd1  call    cs:__imp_RegOpenKeyExW
0x18002bbd7  lea     rdx, aRedirectionkey; "RedirectionKey"
0x18002bbde  lea     rcx, [rbp+840h+var_8A8]; this
0x18002bbe2  call    ?ValueSZ@CReg@@QEAAPEBGPEBG@Z; CReg::ValueSZ(ushort const *)
0x18002bbe7  mov     rdi, rax
0x18002bbea  test    rax, rax
0x18002bbed  jz      short loc_18002BC39
0x18002bbef  lea     esi, [r12-0Ah]
0x18002bbf4  xor     edx, edx; Val
0x18002bbf6  mov     r8d, esi; Size
0x18002bbf9  lea     rcx, [rbp+840h+var_890]; void *
0x18002bbfd  call    memset_0
0x18002bc02  mov     r8, rdi; unsigned __int16 *
0x18002bc05  lea     rcx, [rbp+840h+var_890]; unsigned __int16 *
0x18002bc09  mov     edx, esi; unsigned __int64
0x18002bc0b  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x18002bc10  lea     r8, aHttpServerVroo; "\\HTTP Server\\VROOTS"
0x18002bc17  mov     edx, esi; unsigned __int64
0x18002bc19  lea     rcx, [rbp+840h+var_890]; unsigned __int16 *
0x18002bc1d  call    ?StringCbCatW@@YAJPEAG_KPEBG@Z; StringCbCatW(ushort *,unsigned __int64,ushort const *)
0x18002bc22  lea     r8, [rbp+840h+var_890]; unsigned __int16 *
0x18002bc26  lea     rcx, [rsp+940h+hKey]; this
0x18002bc2b  call    ?Create@CReg@@QEAAHPEAUHKEY__@@PEBG@Z; CReg::Create(HKEY__ *,ushort const *)
0x18002bc30  test    eax, eax
0x18002bc32  jnz     short loc_18002BC65
0x18002bc34  jmp     loc_18002BE1B
0x18002bc39  lea     rax, [rsp+940h+hKey]
0x18002bc3e  mov     r9d, esi; samDesired
0x18002bc41  xor     r8d, r8d; ulOptions
0x18002bc44  mov     [rsp+940h+phkResult], rax; phkResult
0x18002bc49  lea     rdx, aSoftwareMicros_3; "SOFTWARE\\MICROSOFT\\UPnP Device Host\\"...
0x18002bc50  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002bc57  call    cs:__imp_RegOpenKeyExW
0x18002bc5d  test    eax, eax
0x18002bc5f  jnz     loc_18002BE1B
0x18002bc65  mov     rcx, [rsp+940h+hKey]; hKey
0x18002bc6a  lea     rax, [rsp+940h+cSubKeys]
0x18002bc6f  mov     [rsp+940h+lpftLastWriteTime], r14; lpftLastWriteTime
0x18002bc74  xor     r9d, r9d; lpReserved
0x18002bc77  mov     [rsp+940h+lpcbSecurityDescriptor], r14; lpcbSecurityDescriptor
0x18002bc7c  xor     r8d, r8d; lpcchClass
0x18002bc7f  mov     [rsp+940h+lpcbMaxValueLen], r14; lpcbMaxValueLen
0x18002bc84  xor     edx, edx; lpClass
0x18002bc86  mov     [rsp+940h+lpcbMaxValueNameLen], r14; lpcbMaxValueNameLen
0x18002bc8b  mov     [rsp+940h+lpcValues], r14; lpcValues
0x18002bc90  mov     [rsp+940h+lpcbMaxClassLen], r14; lpcbMaxClassLen
0x18002bc95  mov     [rsp+940h+lpcbMaxSubKeyLen], r14; lpcbMaxSubKeyLen
0x18002bc9a  mov     [rsp+940h+phkResult], rax; lpcSubKeys
0x18002bc9f  mov     [rsp+940h+cSubKeys], r14d
0x18002bca4  call    cs:__imp_RegQueryInfoKeyW
0x18002bcaa  mov     eax, [rsp+940h+cSubKeys]
0x18002bcae  mov     [rbx+28h], eax
0x18002bcb1  test    eax, eax
0x18002bcb3  jz      loc_18002BE1B
0x18002bcb9  imul    ecx, eax, 38h ; '8'; Size
0x18002bcbc  call    ?svsutil_AllocZ@@YAPEAXKPEAX@Z; svsutil_AllocZ(ulong,void *)
0x18002bcc1  mov     [rbx+30h], rax
0x18002bcc5  test    rax, rax
0x18002bcc8  jz      loc_18002BE1B
0x18002bcce  mov     edi, r14d
0x18002bcd1  cmp     edi, [rbx+28h]
0x18002bcd4  jge     loc_18002BE13
0x18002bcda  mov     rcx, [rsp+940h+hKey]; hKey
0x18002bcdf  mov     [rsp+940h+cSubKeys], 105h
0x18002bce7  test    rcx, rcx
0x18002bcea  jz      loc_18002BE13
0x18002bcf0  mov     edx, [rsp+940h+dwIndex]; dwIndex
0x18002bcf4  lea     r9, [rsp+940h+cSubKeys]; lpcchName
0x18002bcf9  mov     [rsp+940h+lpcValues], r14; lpftLastWriteTime
0x18002bcfe  lea     r8, [rbp+840h+Name]; lpName
0x18002bd05  mov     [rsp+940h+lpcbMaxClassLen], r14; lpcchClass
0x18002bd0a  mov     [rsp+940h+lpcbMaxSubKeyLen], r14; lpClass
0x18002bd0f  lea     eax, [rdx+1]
0x18002bd12  mov     [rsp+940h+phkResult], r14; lpReserved
0x18002bd17  mov     [rsp+940h+dwIndex], eax
0x18002bd1b  call    cs:__imp_RegEnumKeyExW
0x18002bd21  test    eax, eax
0x18002bd23  jnz     loc_18002BE13
0x18002bd29  mov     rdx, [rsp+940h+hKey]; hKey
0x18002bd2e  lea     r8, [rbp+840h+Name]; lpSubKey
0x18002bd35  lea     rcx, [rbp+840h+var_8C0]; phkResult
0x18002bd39  mov     [rbp+840h+var_8C0], r14
0x18002bd3d  mov     [rbp+840h+var_8B8], r14d
0x18002bd41  mov     [rbp+840h+var_8B0], r14
0x18002bd45  call    ?Open@CReg@@QEAAHPEAUHKEY__@@PEBGK@Z; CReg::Open(HKEY__ *,ushort const *,ulong)
0x18002bd4a  lea     rcx, asc_1800660B8; "\\\\?\\"
0x18002bd51  call    cs:__imp_lstrlenW
0x18002bd57  mov     r9d, 105h
0x18002bd5d  lea     r8, [rbp+840h+var_250]; unsigned __int16 *
0x18002bd64  sub     r9d, eax; unsigned int
0x18002bd67  lea     rcx, [rbp+840h+var_8C0]; this
0x18002bd6b  call    ?ValueSZ@CReg@@QEAAHPEBGPEAGK@Z; CReg::ValueSZ(ushort const *,ushort *,ulong)
0x18002bd70  test    eax, eax
0x18002bd72  jz      short loc_18002BDF3
0x18002bd74  lea     r8, asc_1800660B8; "\\\\?\\"
0x18002bd7b  mov     rdx, r12; unsigned __int64
0x18002bd7e  lea     rcx, [rbp+840h+var_470]; unsigned __int16 *
0x18002bd85  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x18002bd8a  lea     r8, [rbp+840h+var_250]; unsigned __int16 *
0x18002bd91  mov     rdx, r12; unsigned __int64
0x18002bd94  lea     rcx, [rbp+840h+var_470]; unsigned __int16 *
0x18002bd9b  call    ?StringCbCatW@@YAJPEAG_KPEBG@Z; StringCbCatW(ushort *,unsigned __int64,ushort const *)
0x18002bda0  mov     rdx, [rbx+30h]
0x18002bda4  lea     r9, [rbp+840h+var_470]; unsigned __int16 *
0x18002bdab  movsxd  rax, edi
0x18002bdae  lea     r8, [rbp+840h+Name]; unsigned __int16 *
0x18002bdb5  imul    rsi, rax, 38h ; '8'
0x18002bdb9  add     rdx, rsi; struct VROOTINFO *
0x18002bdbc  call    ?FillVRoot@CVRoots@@AEAAHPEAUVROOTINFO@@PEAG1@Z; CVRoots::FillVRoot(VROOTINFO *,ushort *,ushort *)
0x18002bdc1  lea     rcx, [rbp+840h+var_8C0]; this
0x18002bdc5  test    eax, eax
0x18002bdc7  jz      short loc_18002BE0C
0x18002bdc9  mov     r8d, 205h; unsigned int
0x18002bdcf  lea     rdx, aP; "p"
0x18002bdd6  call    ?ValueDW@CReg@@QEAAKPEBGK@Z; CReg::ValueDW(ushort const *,ulong)
0x18002bddb  mov     rcx, [rbx+30h]; this
0x18002bddf  mov     [rcx+rsi+20h], eax
0x18002bde3  mov     rdx, [rbx+30h]
0x18002bde7  mov     r8, [rbp+840h+var_8C0]; HKEY
0x18002bdeb  add     rdx, rsi; struct VROOTINFO *
0x18002bdee  call    ?LoadExtensionMap@CVRoots@@AEAAHPEAUVROOTINFO@@PEAUHKEY__@@@Z; CVRoots::LoadExtensionMap(VROOTINFO *,HKEY__ *)
0x18002bdf3  lea     rcx, [rbp+840h+var_8C0]; this
0x18002bdf7  call    ?Reset@CReg@@QEAAXXZ; CReg::Reset(void)
0x18002bdfc  lea     rcx, [rbp+840h+var_8C0]; this
0x18002be00  call    ??1CReg@@QEAA@XZ; CReg::~CReg(void)
0x18002be05  inc     edi
0x18002be07  jmp     loc_18002BCD1
0x18002be0c  call    ??1CReg@@QEAA@XZ; CReg::~CReg(void)
0x18002be11  jmp     short loc_18002BE1B
0x18002be13  mov     rcx, rbx; this
0x18002be16  call    ?Sort@CVRoots@@AEAAXXZ; CVRoots::Sort(void)
0x18002be1b  lea     rcx, [rbp+840h+var_8A8]; this
0x18002be1f  call    ??1CReg@@QEAA@XZ; CReg::~CReg(void)
0x18002be24  lea     rcx, [rsp+940h+hKey]; this
0x18002be29  call    ??1CReg@@QEAA@XZ; CReg::~CReg(void)
0x18002be2e  mov     eax, 1
0x18002be33  mov     rcx, [rbp+840h+var_40]
0x18002be3a  xor     rcx, rsp; StackCookie
0x18002be3d  call    __security_check_cookie
0x18002be42  add     rsp, 918h
0x18002be49  pop     r14
0x18002be4b  pop     r12
0x18002be4d  pop     rdi
0x18002be4e  pop     rsi
0x18002be4f  pop     rbx
0x18002be50  pop     rbp
0x18002be51  retn
```
