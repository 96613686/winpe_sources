# CProfMgr::CreateUserProfileList(void)

- ea: `0x180016674`
- end: `0x180016c63`
- name: `?CreateUserProfileList@CProfMgr@@AEAAJXZ`
- size: `1519`
- prototype: `__int64 __fastcall(CProfMgr *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1800314c0`

## callees

- `0x180003f30`
- `0x180004e00`
- `0x180016674`
- `0x180016c6c`
- `0x18001a280`
- `0x18001ad14`
- `0x18001ad5c`
- `0x180031b7c`
- `0x180032864`
- `0x180043c58`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800166eb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800166eb`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800167d2`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180016820`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180016950`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800169a4`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180016a19`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180016a81`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180016aeb`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800167d2`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180016820`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180016950`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800169a4`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180016a19`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180016a81`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180016aeb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180016c38`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180016c38`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180016b1a`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180016b1a`
- `api-ms-win-core-registry-l2-1-0!RegEnumKeyW` at `0x180016749`
- `api-ms-win-core-registry-l2-1-0!RegEnumKeyW` at `0x1800168e6`
- `api-ms-win-core-registry-l2-1-0!RegEnumKeyW` at `0x180016749`
- `api-ms-win-core-registry-l2-1-0!RegEnumKeyW` at `0x1800168e6`

## string_xrefs

- `0x18001670e`: `CProfMgr::CreateUserProfileList`
- `0x180016704`: `RegOpenKeyEx failed: 0x%x in %s`
- `0x180016aad`: `ProfileImagePath`
- `0x180016b2c`: `%ws is an invalid Profile Image Path.`

## pseudocode

```c
__int64 __fastcall CProfMgr::CreateUserProfileList(CProfMgr *this)
{
  LSTATUS v2; // eax
  signed int v3; // ebx
  const char *v4; // rdx
  DWORD v5; // r12d
  DWORD i; // r14d
  LSTATUS v7; // eax
  bool v8; // di
  unsigned int v9; // eax
  size_t v10; // rdi
  void *v11; // rax
  unsigned int v12; // r15d
  DWORD j; // r14d
  LSTATUS v14; // eax
  const char *v15; // rdx
  LSTATUS ValueW; // eax
  LSTATUS v17; // eax
  LSTATUS v18; // eax
  CProfMgr *v19; // rcx
  char *v20; // rax
  char *v21; // rdi
  DWORD pvData; // [rsp+40h] [rbp-C0h] BYREF
  DWORD v24; // [rsp+44h] [rbp-BCh] BYREF
  DWORD pcbData; // [rsp+48h] [rbp-B8h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  int v27; // [rsp+58h] [rbp-A8h] BYREF
  struct _FILETIME v28; // [rsp+60h] [rbp-A0h]
  WCHAR Name[264]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR FileName[520]; // [rsp+280h] [rbp+180h] BYREF

  hKey = 0;
  pcbData = 0;
  pvData = 0;
  v24 = 0;
  v28 = 0;
  v27 = 0;
  CProfMgr::FreeUserProfileList(this);
  v2 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Windows NT\\CurrentVersion\\ProfileList",
         0,
         0x20019u,
         &hKey);
  v3 = v2;
  if ( v2 > 0 )
    v3 = (unsigned __int16)v2 | 0x80070000;
  if ( v3 < 0 )
  {
    v4 = "RegOpenKeyEx failed: 0x%x in %s";
    goto LABEL_5;
  }
  v5 = 0;
  for ( i = 0; ; ++i )
  {
    Name[0] = 0;
    v7 = RegEnumKeyW(hKey, i, Name, 0x104u);
    if ( v7 == 259 )
    {
      v9 = *((_DWORD *)this + 414);
      if ( !v9 )
      {
LABEL_63:
        v3 = 0;
        goto LABEL_64;
      }
      v10 = 8LL * v9;
      v11 = o_malloc_0(v10);
      *((_QWORD *)this + 206) = v11;
      if ( !v11 )
      {
LABEL_25:
        v3 = -2147024888;
        _DbgPrintMessage(8, "malloc failed: 0x%x in %s", 2147942408LL, "CProfMgr::CreateUserProfileList");
        goto LABEL_64;
      }
      memset_0(v11, 0, v10);
      v12 = 0;
      for ( j = 0; ; ++j )
      {
        if ( j >= v5 )
          goto LABEL_64;
        if ( v12 == *((_DWORD *)this + 414) )
          goto LABEL_63;
        Name[0] = 0;
        v14 = RegEnumKeyW(hKey, j, Name, 0x104u);
        v3 = v14;
        if ( v14 == 259 )
          goto LABEL_63;
        if ( v14 > 0 )
          v3 = (unsigned __int16)v14 | 0x80070000;
        if ( v3 < 0 )
          goto LABEL_13;
        pcbData = 1040;
        FileName[0] = 0;
        if ( !RegGetValueW(hKey, Name, L"CentralProfile", 0xFFFFu, 0, FileName, &pcbData) && FileName[0] )
        {
          v24 = 4;
          if ( RegGetValueW(hKey, Name, L"State", 0x10u, 0, &pvData, &v24) )
          {
            v15 = "Profile State of %ws RegGetValue call failed while creating UserProfileInfo.";
LABEL_37:
            _DbgPrintMessage(1, v15, Name);
            continue;
          }
          if ( (pvData & 1) == 0 && (pvData & 0x10) != 0 )
          {
            v28 = 0;
            v24 = 4;
            ValueW = RegGetValueW(hKey, Name, L"ProfileUnloadTimeHigh", 0x10u, 0, &pvData, &v24);
            if ( ValueW != 2 )
            {
              if ( ValueW > 0 )
                v3 = (unsigned __int16)ValueW | 0x80070000;
              else
                v3 = ValueW;
              if ( v3 < 0 )
              {
LABEL_62:
                v4 = "RegGetValue failed: 0x%x in %s";
                goto LABEL_5;
              }
              v28.dwHighDateTime = pvData;
              v24 = 4;
              v17 = RegGetValueW(hKey, Name, L"ProfileUnloadTimeLow", 0x10u, 0, &pvData, &v24);
              if ( v17 != 2 )
              {
                if ( v17 > 0 )
                  v3 = (unsigned __int16)v17 | 0x80070000;
                else
                  v3 = v17;
                if ( v3 < 0 )
                  goto LABEL_62;
                v28.dwLowDateTime = pvData;
                pcbData = 1040;
                v18 = RegGetValueW(hKey, Name, L"ProfileImagePath", 0xFFFFu, 0, FileName, &pcbData);
                if ( v18 != 2 )
                {
                  if ( v18 > 0 )
                    v3 = (unsigned __int16)v18 | 0x80070000;
                  else
                    v3 = v18;
                  if ( v3 < 0 )
                    goto LABEL_62;
                  if ( GetFileAttributesW(FileName) == -1 )
                  {
                    _DbgPrintMessage(1, "%ws is an invalid Profile Image Path.", FileName);
                  }
                  else
                  {
                    CProfMgr::IsFullyBackedUpRUP(v19, v28, FileName, &v27);
                    if ( !v27 )
                    {
                      v15 = "Profile %ws is not fully backedup.";
                      goto LABEL_37;
                    }
                    v20 = (char *)o_malloc_0(0x640u);
                    v21 = v20;
                    if ( !v20 )
                      goto LABEL_25;
                    memset_0(v20, 0, 0x334u);
                    UserProfileSize = 0;
                    LastModifiedTime = 0;
                    EnumerateDirectory(FileName, 0);
                    *((_QWORD *)v21 + 1) = v21 + 560;
                    *(_QWORD *)v21 = v21 + 40;
                    *((_DWORD *)v21 + 4) = (pvData & 1) == 0;
                    *((_DWORD *)v21 + 5) = (pvData >> 4) & 1;
                    *((_QWORD *)v21 + 3) = UserProfileSize;
                    *((FILETIME *)v21 + 4) = LastModifiedTime;
                    StringCchCopyW((unsigned __int16 *)v21 + 20, 0x104u, Name);
                    StringCchCopyW(*((unsigned __int16 **)v21 + 1), 0x208u, FileName);
                    CProfMgr::SortedInsertIntoUserProfileList(this, (struct _UPINFO *)v21, v12++);
                  }
                }
              }
            }
          }
        }
      }
    }
    if ( v7 == 234 )
      continue;
    if ( v7 )
      break;
    pcbData = 1040;
    ++v5;
    v8 = 0;
    FileName[0] = 0;
    if ( !RegGetValueW(hKey, Name, L"CentralProfile", 0xFFFFu, 0, FileName, &pcbData) )
      v8 = FileName[0] != 0;
    v24 = 4;
    if ( RegGetValueW(hKey, Name, L"State", 0x10u, 0, &pvData, &v24) )
    {
      _DbgPrintMessage(1, "Profile State of %ws RegGetValue call failed.", Name);
    }
    else if ( (pvData & 1) == 0 && v8 && (pvData & 0x10) != 0 )
    {
      ++*((_DWORD *)this + 414);
    }
  }
  if ( v7 > 0 )
    v3 = (unsigned __int16)v7 | 0x80070000;
  else
    v3 = v7;
LABEL_13:
  v4 = "RegEnumKey failed: 0x%x in %s";
LABEL_5:
  _DbgPrintMessage(8, v4, (unsigned int)v3, "CProfMgr::CreateUserProfileList");
LABEL_64:
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180016674  push    rbp
0x180016676  push    rbx
0x180016677  push    rsi
0x180016678  push    rdi
0x180016679  push    r12
0x18001667b  push    r13
0x18001667d  push    r14
0x18001667f  push    r15
0x180016681  lea     rbp, [rsp-5A8h]
0x180016689  sub     rsp, 6A8h
0x180016690  mov     rax, cs:__security_cookie
0x180016697  xor     rax, rsp
0x18001669a  mov     [rbp+5E0h+var_50], rax
0x1800166a1  xor     r13d, r13d
0x1800166a4  mov     rsi, rcx
0x1800166a7  mov     [rsp+6E0h+hKey], r13
0x1800166ac  mov     [rsp+6E0h+var_698], r13d
0x1800166b1  mov     [rsp+6E0h+var_6A0], r13d
0x1800166b6  mov     [rsp+6E0h+var_69C], r13d
0x1800166bb  mov     qword ptr [rsp+6E0h+var_680.dwLowDateTime], r13
0x1800166c0  mov     [rsp+6E0h+var_688], r13d
0x1800166c5  call    ?FreeUserProfileList@CProfMgr@@AEAAXXZ; CProfMgr::FreeUserProfileList(void)
0x1800166ca  lea     rax, [rsp+6E0h+hKey]
0x1800166cf  mov     r9d, 20019h; samDesired
0x1800166d5  xor     r8d, r8d; ulOptions
0x1800166d8  mov     [rsp+6E0h+phkResult], rax; phkResult
0x1800166dd  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Windows NT\\Curren"...
0x1800166e4  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800166eb  call    cs:__imp_RegOpenKeyExW
0x1800166f1  mov     ebx, eax
0x1800166f3  test    eax, eax
0x1800166f5  jle     short loc_180016700
0x1800166f7  movzx   ebx, ax
0x1800166fa  or      ebx, 80070000h
0x180016700  test    ebx, ebx
0x180016702  jns     short loc_180016724
0x180016704  lea     rdx, aRegopenkeyexFa_2; "RegOpenKeyEx failed: 0x%x in %s"
0x18001670b  mov     r8d, ebx
0x18001670e  lea     r9, aCprofmgrCreate; "CProfMgr::CreateUserProfileList"
0x180016715  mov     ecx, 8; int
0x18001671a  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18001671f  jmp     loc_180016C2E
0x180016724  mov     r12d, r13d
0x180016727  mov     r14d, r13d
0x18001672a  mov     r15d, 1
0x180016730  mov     rcx, [rsp+6E0h+hKey]; hKey
0x180016735  lea     r8, [rsp+6E0h+Name]; lpName
0x18001673a  mov     r9d, 104h; cchName
0x180016740  mov     [rsp+6E0h+Name], r13w
0x180016746  mov     edx, r14d; dwIndex
0x180016749  call    cs:__imp_RegEnumKeyW
0x18001674f  cmp     eax, 103h
0x180016754  jz      loc_180016862
0x18001675a  cmp     eax, 0EAh
0x18001675f  jz      loc_18001685A
0x180016765  test    eax, eax
0x180016767  jz      short loc_180016789
0x180016769  jg      short loc_18001676F
0x18001676b  mov     ebx, eax
0x18001676d  jmp     short loc_180016778
0x18001676f  movzx   ebx, ax
0x180016772  or      ebx, 80070000h
0x180016778  test    ebx, ebx
0x18001677a  jns     loc_18001685A
0x180016780  lea     rdx, aRegenumkeyFail; "RegEnumKey failed: 0x%x in %s"
0x180016787  jmp     short loc_18001670B
0x180016789  mov     rcx, [rsp+6E0h+hKey]; hkey
0x18001678e  lea     rax, [rsp+6E0h+var_698]
0x180016793  mov     [rsp+6E0h+pcbData], rax; pcbData
0x180016798  lea     r8, Value; "CentralProfile"
0x18001679f  lea     rax, [rbp+5E0h+FileName]
0x1800167a6  mov     [rsp+6E0h+var_698], 410h
0x1800167ae  mov     [rsp+6E0h+pvData], rax; pvData
0x1800167b3  lea     rdx, [rsp+6E0h+Name]; lpSubKey
0x1800167b8  mov     r9d, 0FFFFh; dwFlags
0x1800167be  mov     [rsp+6E0h+phkResult], r13; pdwType
0x1800167c3  add     r12d, r15d
0x1800167c6  movzx   edi, r13b
0x1800167ca  mov     [rbp+5E0h+FileName], r13w
0x1800167d2  call    cs:__imp_RegGetValueW
0x1800167d8  test    eax, eax
0x1800167da  jnz     short loc_1800167E8
0x1800167dc  cmp     [rbp+5E0h+FileName], r13w
0x1800167e4  cmovnz  edi, r15d
0x1800167e8  mov     rcx, [rsp+6E0h+hKey]; hkey
0x1800167ed  lea     rax, [rsp+6E0h+var_69C]
0x1800167f2  mov     [rsp+6E0h+pcbData], rax; pcbData
0x1800167f7  lea     r8, aState; "State"
0x1800167fe  lea     rax, [rsp+6E0h+var_6A0]
0x180016803  mov     [rsp+6E0h+var_69C], 4
0x18001680b  mov     [rsp+6E0h+pvData], rax; pvData
0x180016810  lea     rdx, [rsp+6E0h+Name]; lpSubKey
0x180016815  mov     r9d, 10h; dwFlags
0x18001681b  mov     [rsp+6E0h+phkResult], r13; pdwType
0x180016820  call    cs:__imp_RegGetValueW
0x180016826  test    eax, eax
0x180016828  jz      short loc_180016840
0x18001682a  lea     r8, [rsp+6E0h+Name]
0x18001682f  mov     ecx, r15d; int
0x180016832  lea     rdx, aProfileStateOf_0; "Profile State of %ws RegGetValue call f"...
0x180016839  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18001683e  jmp     short loc_18001685A
0x180016840  test    byte ptr [rsp+6E0h+var_6A0], r15b
0x180016845  jnz     short loc_18001685A
0x180016847  test    dil, dil
0x18001684a  jz      short loc_18001685A
0x18001684c  test    byte ptr [rsp+6E0h+var_6A0], 10h
0x180016851  jz      short loc_18001685A
0x180016853  add     [rsi+678h], r15d
0x18001685a  add     r14d, r15d
0x18001685d  jmp     loc_180016730
0x180016862  mov     eax, [rsi+678h]
0x180016868  test    eax, eax
0x18001686a  jz      loc_180016C2B
0x180016870  mov     edi, eax
0x180016872  shl     rdi, 3
0x180016876  mov     rcx, rdi; Size
0x180016879  call    _o_malloc_0
0x18001687e  mov     [rsi+670h], rax
0x180016885  test    rax, rax
0x180016888  jnz     short loc_18001689F
0x18001688a  mov     r8d, 80070008h
0x180016890  lea     rdx, aMallocFailed0x; "malloc failed: 0x%x in %s"
0x180016897  mov     ebx, r8d
0x18001689a  jmp     loc_18001670E
0x18001689f  mov     r8, rdi; Size
0x1800168a2  xor     edx, edx; Val
0x1800168a4  mov     rcx, rax; void *
0x1800168a7  call    memset_0
0x1800168ac  mov     r15d, r13d
0x1800168af  mov     r14d, r13d
0x1800168b2  mov     edi, 1
0x1800168b7  cmp     r14d, r12d
0x1800168ba  jnb     loc_180016C2E
0x1800168c0  cmp     r15d, [rsi+678h]
0x1800168c7  jz      loc_180016C2B
0x1800168cd  mov     rcx, [rsp+6E0h+hKey]; hKey
0x1800168d2  lea     r8, [rsp+6E0h+Name]; lpName
0x1800168d7  mov     r9d, 104h; cchName
0x1800168dd  mov     [rsp+6E0h+Name], r13w
0x1800168e3  mov     edx, r14d; dwIndex
0x1800168e6  call    cs:__imp_RegEnumKeyW
0x1800168ec  mov     ebx, eax
0x1800168ee  cmp     eax, 103h
0x1800168f3  jz      loc_180016C2B
0x1800168f9  test    eax, eax
0x1800168fb  jle     short loc_180016906
0x1800168fd  movzx   ebx, ax
0x180016900  or      ebx, 80070000h
0x180016906  test    ebx, ebx
0x180016908  js      loc_180016780
0x18001690e  mov     rcx, [rsp+6E0h+hKey]; hkey
0x180016913  lea     rax, [rsp+6E0h+var_698]
0x180016918  mov     [rsp+6E0h+pcbData], rax; pcbData
0x18001691d  lea     r8, Value; "CentralProfile"
0x180016924  lea     rax, [rbp+5E0h+FileName]
0x18001692b  mov     [rsp+6E0h+var_698], 410h
0x180016933  mov     [rsp+6E0h+pvData], rax; pvData
0x180016938  lea     rdx, [rsp+6E0h+Name]; lpSubKey
0x18001693d  mov     r9d, 0FFFFh; dwFlags
0x180016943  mov     [rsp+6E0h+phkResult], r13; pdwType
0x180016948  mov     [rbp+5E0h+FileName], r13w
0x180016950  call    cs:__imp_RegGetValueW
0x180016956  test    eax, eax
0x180016958  jnz     loc_180016C17
0x18001695e  cmp     [rbp+5E0h+FileName], r13w
0x180016966  jz      loc_180016C17
0x18001696c  mov     rcx, [rsp+6E0h+hKey]; hkey
0x180016971  lea     rax, [rsp+6E0h+var_69C]
0x180016976  mov     [rsp+6E0h+pcbData], rax; pcbData
0x18001697b  lea     r8, aState; "State"
0x180016982  lea     rax, [rsp+6E0h+var_6A0]
0x180016987  mov     [rsp+6E0h+var_69C], 4
0x18001698f  mov     [rsp+6E0h+pvData], rax; pvData
0x180016994  lea     rdx, [rsp+6E0h+Name]; lpSubKey
0x180016999  mov     r9d, 10h; dwFlags
0x18001699f  mov     [rsp+6E0h+phkResult], r13; pdwType
0x1800169a4  call    cs:__imp_RegGetValueW
0x1800169aa  test    eax, eax
0x1800169ac  jz      short loc_1800169C6
0x1800169ae  lea     rdx, aProfileStateOf; "Profile State of %ws RegGetValue call f"...
0x1800169b5  lea     r8, [rsp+6E0h+Name]
0x1800169ba  mov     ecx, edi; int
0x1800169bc  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800169c1  jmp     loc_180016C17
0x1800169c6  test    byte ptr [rsp+6E0h+var_6A0], dil
0x1800169cb  jnz     loc_180016C17
0x1800169d1  test    byte ptr [rsp+6E0h+var_6A0], 10h
0x1800169d6  jz      loc_180016C17
0x1800169dc  mov     rcx, [rsp+6E0h+hKey]; hkey
0x1800169e1  lea     rax, [rsp+6E0h+var_69C]
0x1800169e6  mov     [rsp+6E0h+pcbData], rax; pcbData
0x1800169eb  lea     r8, aProfileunloadt_0; "ProfileUnloadTimeHigh"
0x1800169f2  lea     rax, [rsp+6E0h+var_6A0]
0x1800169f7  mov     qword ptr [rsp+6E0h+var_680.dwLowDateTime], r13
0x1800169fc  mov     [rsp+6E0h+pvData], rax; pvData
0x180016a01  lea     rdx, [rsp+6E0h+Name]; lpSubKey
0x180016a06  mov     r9d, 10h; dwFlags
0x180016a0c  mov     [rsp+6E0h+phkResult], r13; pdwType
0x180016a11  mov     [rsp+6E0h+var_69C], 4
0x180016a19  call    cs:__imp_RegGetValueW
0x180016a1f  cmp     eax, 2
0x180016a22  jz      loc_180016C17
0x180016a28  test    eax, eax
0x180016a2a  jg      short loc_180016A30
0x180016a2c  mov     ebx, eax
0x180016a2e  jmp     short loc_180016A39
0x180016a30  movzx   ebx, ax
0x180016a33  or      ebx, 80070000h
0x180016a39  test    ebx, ebx
0x180016a3b  js      loc_180016C1F
0x180016a41  mov     eax, [rsp+6E0h+var_6A0]
0x180016a45  lea     r8, aProfileunloadt; "ProfileUnloadTimeLow"
0x180016a4c  mov     rcx, [rsp+6E0h+hKey]; hkey
0x180016a51  lea     rdx, [rsp+6E0h+Name]; lpSubKey
0x180016a56  mov     [rsp+6E0h+var_680.dwHighDateTime], eax
0x180016a5a  mov     r9d, 10h; dwFlags
0x180016a60  lea     rax, [rsp+6E0h+var_69C]
0x180016a65  mov     [rsp+6E0h+var_69C], 4
0x180016a6d  mov     [rsp+6E0h+pcbData], rax; pcbData
0x180016a72  lea     rax, [rsp+6E0h+var_6A0]
0x180016a77  mov     [rsp+6E0h+pvData], rax; pvData
0x180016a7c  mov     [rsp+6E0h+phkResult], r13; pdwType
0x180016a81  call    cs:__imp_RegGetValueW
0x180016a87  cmp     eax, 2
0x180016a8a  jz      loc_180016C17
0x180016a90  test    eax, eax
0x180016a92  jg      short loc_180016A98
0x180016a94  mov     ebx, eax
0x180016a96  jmp     short loc_180016AA1
0x180016a98  movzx   ebx, ax
0x180016a9b  or      ebx, 80070000h
0x180016aa1  test    ebx, ebx
0x180016aa3  js      loc_180016C1F
0x180016aa9  mov     eax, [rsp+6E0h+var_6A0]
0x180016aad  lea     r8, aProfileimagepa; "ProfileImagePath"
0x180016ab4  mov     rcx, [rsp+6E0h+hKey]; hkey
0x180016ab9  lea     rdx, [rsp+6E0h+Name]; lpSubKey
0x180016abe  mov     [rsp+6E0h+var_680.dwLowDateTime], eax
0x180016ac2  mov     r9d, 0FFFFh; dwFlags
0x180016ac8  lea     rax, [rsp+6E0h+var_698]
0x180016acd  mov     [rsp+6E0h+var_698], 410h
0x180016ad5  mov     [rsp+6E0h+pcbData], rax; pcbData
0x180016ada  lea     rax, [rbp+5E0h+FileName]
0x180016ae1  mov     [rsp+6E0h+pvData], rax; pvData
0x180016ae6  mov     [rsp+6E0h+phkResult], r13; pdwType
0x180016aeb  call    cs:__imp_RegGetValueW
0x180016af1  cmp     eax, 2
0x180016af4  jz      loc_180016C17
0x180016afa  test    eax, eax
0x180016afc  jg      short loc_180016B02
0x180016afe  mov     ebx, eax
0x180016b00  jmp     short loc_180016B0B
0x180016b02  movzx   ebx, ax
0x180016b05  or      ebx, 80070000h
0x180016b0b  test    ebx, ebx
0x180016b0d  js      loc_180016C1F
0x180016b13  lea     rcx, [rbp+5E0h+FileName]; lpFileName
0x180016b1a  call    cs:__imp_GetFileAttributesW
0x180016b20  lea     r8, [rbp+5E0h+FileName]; unsigned __int16 *
0x180016b27  cmp     eax, 0FFFFFFFFh
0x180016b2a  jnz     short loc_180016B38
0x180016b2c  lea     rdx, aWsIsAnInvalidP; "%ws is an invalid Profile Image Path."
0x180016b33  jmp     loc_1800169BA
0x180016b38  mov     rdx, qword ptr [rsp+6E0h+var_680.dwLowDateTime]; struct _FILETIME
0x180016b3d  lea     r9, [rsp+6E0h+var_688]; int *
0x180016b42  call    ?IsFullyBackedUpRUP@CProfMgr@@AEAAJU_FILETIME@@PEBGPEAH@Z; CProfMgr::IsFullyBackedUpRUP(_FILETIME,ushort const *,int *)
0x180016b47  cmp     [rsp+6E0h+var_688], r13d
0x180016b4c  jnz     short loc_180016B5A
0x180016b4e  lea     rdx, aProfileWsIsNot; "Profile %ws is not fully backedup."
0x180016b55  jmp     loc_1800169B5
0x180016b5a  mov     ecx, 640h; Size
0x180016b5f  call    _o_malloc_0
0x180016b64  mov     rdi, rax
0x180016b67  test    rax, rax
0x180016b6a  jz      loc_18001688A
0x180016b70  xor     edx, edx; Val
0x180016b72  mov     r8d, 334h; Size
0x180016b78  mov     rcx, rax; void *
0x180016b7b  call    memset_0
0x180016b80  xor     edx, edx; unsigned int
0x180016b82  mov     cs:?UserProfileSize@@3_KA, r13; unsigned __int64 UserProfileSize
0x180016b89  lea     rcx, [rbp+5E0h+FileName]; Source
0x180016b90  mov     qword ptr cs:?LastModifiedTime@@3U_FILETIME@@A.dwLowDateTime, r13; _FILETIME LastModifiedTime ...
0x180016b97  call    EnumerateDirectory
0x180016b9c  lea     rax, [rdi+230h]
0x180016ba3  mov     edx, 104h; unsigned __int64
0x180016ba8  mov     [rdi+8], rax
0x180016bac  lea     rcx, [rdi+28h]; unsigned __int16 *
0x180016bb0  mov     [rdi], rcx
0x180016bb3  lea     r8, [rsp+6E0h+Name]; unsigned __int16 *
0x180016bb8  mov     eax, [rsp+6E0h+var_6A0]
0x180016bbc  not     eax
0x180016bbe  and     eax, 1
0x180016bc1  mov     [rdi+10h], eax
0x180016bc4  mov     eax, [rsp+6E0h+var_6A0]
0x180016bc8  shr     eax, 4
0x180016bcb  and     eax, 1
0x180016bce  mov     [rdi+14h], eax
0x180016bd1  mov     rax, cs:?UserProfileSize@@3_KA; unsigned __int64 UserProfileSize
  ... truncated ...
```
