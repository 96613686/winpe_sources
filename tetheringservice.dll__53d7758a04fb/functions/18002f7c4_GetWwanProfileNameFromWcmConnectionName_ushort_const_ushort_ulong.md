# GetWwanProfileNameFromWcmConnectionName(ushort const *,ushort *,ulong)

- ea: `0x18002f7c4`
- end: `0x18002fb00`
- name: `?GetWwanProfileNameFromWcmConnectionName@@YAKPEBGPEAGK@Z`
- size: `828`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180022794`

## callees

- `0x180002590`
- `0x180003088`
- `0x18000fe0c`
- `0x18002f5f4`
- `0x18002f7c4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002f989`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002f989`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f87f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f90c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f87f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f90c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002f892`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002f91f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002f892`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002f91f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002f868`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002f88a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002f8e8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002f917`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002f9ef`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002faa1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002fab1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002fac5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002f868`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002f88a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002f8e8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002f917`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002f9ef`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002faa1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002fab1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002fac5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002f8c8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002f94a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002f8c8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002f94a`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18002f9cf`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18002fa2e`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18002f9cf`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18002fa2e`

## pseudocode

```c
__int64 __fastcall GetWwanProfileNameFromWcmConnectionName(const unsigned __int16 *a1, unsigned __int16 *a2)
{
  __int64 v4; // rdx
  __int64 v5; // rcx
  DWORD v6; // r15d
  unsigned int PersistentRegPathWstring; // ebx
  __int64 result; // rax
  const WCHAR *v9; // rdx
  unsigned int v10; // ebx
  DWORD i; // edx
  HKEY v12; // r14
  DWORD LastError; // ebx
  unsigned int v14; // ebx
  DWORD v15; // r14d
  DWORD j; // edx
  __int64 v17; // rax
  WCHAR *v18; // rdx
  __int64 v19; // rcx
  unsigned __int16 v20; // r8
  unsigned __int16 *v21; // rax
  HKEY hKey; // [rsp+40h] [rbp-478h] BYREF
  DWORD v23; // [rsp+48h] [rbp-470h] BYREF
  HKEY phkResult; // [rsp+50h] [rbp-468h] BYREF
  DWORD cchName; // [rsp+58h] [rbp-460h] BYREF
  LPCWSTR lpSubKey[2]; // [rsp+60h] [rbp-458h] BYREF
  __m128i si128; // [rsp+70h] [rbp-448h]
  WCHAR SubKey[256]; // [rsp+80h] [rbp-438h] BYREF
  WCHAR Name[256]; // [rsp+280h] [rbp-238h] BYREF

  hKey = 0;
  memset_0(SubKey, 0, sizeof(SubKey));
  v23 = 256;
  if ( !a1 || (v6 = 0, !a2) )
  {
    result = 87;
    goto LABEL_45;
  }
  *(_OWORD *)lpSubKey = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(lpSubKey[0]) = 0;
  PersistentRegPathWstring = GetPersistentRegPathWstring(v5, v4, (__int64)lpSubKey);
  if ( PersistentRegPathWstring )
  {
    std::wstring::~wstring((char **)lpSubKey);
    result = PersistentRegPathWstring;
    goto LABEL_45;
  }
  hKey = 0;
  v9 = (const WCHAR *)lpSubKey;
  if ( si128.m128i_i64[1] > 7uLL )
    v9 = lpSubKey[0];
  v10 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v9, 0, 0x20019u, &hKey);
  if ( v10 )
  {
    std::wstring::~wstring((char **)lpSubKey);
    if ( hKey )
      RegCloseKey(hKey);
    result = v10;
    goto LABEL_45;
  }
  std::wstring::~wstring((char **)lpSubKey);
  for ( i = 0; ; i = v6 )
  {
    phkResult = 0;
    v14 = RegEnumKeyExW(hKey, i, SubKey, &v23, 0, 0, 0, 0);
    if ( v14 )
      goto LABEL_36;
    v12 = phkResult;
    if ( phkResult )
    {
      LastError = GetLastError();
      RegCloseKey(v12);
      SetLastError(LastError);
    }
    phkResult = 0;
    v14 = RegOpenKeyExW(hKey, SubKey, 0, 0x20019u, &phkResult);
    if ( !v14 )
      break;
LABEL_20:
    v23 = 256;
    if ( phkResult )
      RegCloseKey(phkResult);
    if ( v14 )
      goto LABEL_38;
    ++v6;
  }
  memset_0(Name, 0, sizeof(Name));
  cchName = 256;
  v15 = 0;
  for ( j = 0; ; j = v15 )
  {
    v14 = RegEnumKeyExW(phkResult, j, Name, &cchName, 0, 0, 0, 0);
    if ( v14 )
    {
      v14 = 0;
      goto LABEL_20;
    }
    if ( !(unsigned int)_o__wcsicmp(Name, a1) )
      break;
    cchName = 256;
    ++v15;
  }
  v17 = v23;
  if ( v23 > 0x7FFFFFFEuLL )
  {
    *a2 = 0;
LABEL_35:
    v14 = 14;
    goto LABEL_36;
  }
  v18 = SubKey;
  v19 = 257;
  do
  {
    if ( !v17 )
      break;
    v20 = *v18;
    if ( !*v18 )
      break;
    ++v18;
    *a2++ = v20;
    --v17;
    --v19;
  }
  while ( v19 );
  v21 = a2 - 1;
  if ( v19 )
    v21 = a2;
  *v21 = 0;
  if ( !v19 )
    goto LABEL_35;
LABEL_36:
  if ( phkResult )
    RegCloseKey(phkResult);
LABEL_38:
  if ( hKey )
    RegCloseKey(hKey);
  result = v14;
LABEL_45:
  while ( 2 )
  {
    if ( __eh34_try(-1, 0) )
      __eh34_scope_strut(0);
    if ( __eh34_catch(0) )
    {
      if ( __eh34_catch_type(0, &std::exception `RTTI Type Descriptor', 0) )
      {
        __eh34_try_continuation(0, &std::exception `RTTI Type Descriptor', &loc_18002FABB);
        if ( hKey )
          RegCloseKey(hKey);
        result = 14;
        continue;
      }
    }
    break;
  }
  return result;
}

```

## disassembly

```asm
0x18002f7c4  mov     [rsp+arg_10], rbx
0x18002f7c9  push    rsi
0x18002f7ca  push    rdi
0x18002f7cb  push    r12
0x18002f7cd  push    r14
0x18002f7cf  push    r15
0x18002f7d1  sub     rsp, 490h
0x18002f7d8  mov     rax, cs:__security_cookie
0x18002f7df  xor     rax, rsp
0x18002f7e2  mov     [rsp+4B8h+var_38], rax
0x18002f7ea  mov     rsi, rdx
0x18002f7ed  mov     r12, rcx
0x18002f7f0  xor     edi, edi
0x18002f7f2  mov     [rsp+4B8h+hKey], rdi
0x18002f7f7  xor     edx, edx; Val
0x18002f7f9  mov     r8d, 200h; Size
0x18002f7ff  lea     rcx, [rsp+4B8h+SubKey]; void *
0x18002f807  call    memset_0
0x18002f80c  mov     [rsp+4B8h+var_470], 100h
0x18002f814  test    r12, r12
0x18002f817  jz      loc_18002FAD2
0x18002f81d  mov     r15d, edi
0x18002f820  test    rsi, rsi
0x18002f823  jz      loc_18002FAD2
0x18002f829  xorps   xmm0, xmm0
0x18002f82c  movups  xmmword ptr [rsp+4B8h+lpSubKey], xmm0
0x18002f831  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18002f839  movdqu  [rsp+4B8h+var_448], xmm1
0x18002f83f  mov     word ptr [rsp+4B8h+lpSubKey], di
0x18002f844  lea     r8, [rsp+4B8h+lpSubKey]
0x18002f849  call    ?GetPersistentRegPathWstring@@YAKW4_REG_ROOT_PATH@@PEBGPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; GetPersistentRegPathWstring(_REG_ROOT_PATH,ushort const *,std::wstring *)
0x18002f84e  mov     ebx, eax
0x18002f850  test    eax, eax
0x18002f852  jz      short loc_18002F875
0x18002f854  lea     rcx, [rsp+4B8h+lpSubKey]
0x18002f859  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002f85e  mov     rcx, [rsp+4B8h+hKey]; hKey
0x18002f863  test    rcx, rcx
0x18002f866  jz      short loc_18002F86E
0x18002f868  call    cs:__imp_RegCloseKey
0x18002f86e  mov     eax, ebx
0x18002f870  jmp     loc_18002FAD7
0x18002f875  mov     r14, [rsp+4B8h+hKey]
0x18002f87a  test    r14, r14
0x18002f87d  jz      short loc_18002F898
0x18002f87f  call    cs:__imp_GetLastError
0x18002f885  mov     ebx, eax
0x18002f887  mov     rcx, r14; hKey
0x18002f88a  call    cs:__imp_RegCloseKey
0x18002f890  mov     ecx, ebx; dwErrCode
0x18002f892  call    cs:__imp_SetLastError
0x18002f898  mov     [rsp+4B8h+hKey], rdi
0x18002f89d  lea     rdx, [rsp+4B8h+lpSubKey]
0x18002f8a2  cmp     qword ptr [rsp+4B8h+var_448+8], 7
0x18002f8a8  cmova   rdx, [rsp+4B8h+lpSubKey]; lpSubKey
0x18002f8ae  lea     rax, [rsp+4B8h+hKey]
0x18002f8b3  mov     [rsp+4B8h+phkResult], rax; phkResult
0x18002f8b8  mov     r9d, 20019h; samDesired
0x18002f8be  xor     r8d, r8d; ulOptions
0x18002f8c1  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002f8c8  call    cs:__imp_RegOpenKeyExW
0x18002f8ce  mov     ebx, eax
0x18002f8d0  lea     rcx, [rsp+4B8h+lpSubKey]
0x18002f8d5  test    eax, eax
0x18002f8d7  jz      short loc_18002F8F5
0x18002f8d9  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002f8de  mov     rcx, [rsp+4B8h+hKey]; hKey
0x18002f8e3  test    rcx, rcx
0x18002f8e6  jz      short loc_18002F8EE
0x18002f8e8  call    cs:__imp_RegCloseKey
0x18002f8ee  mov     eax, ebx
0x18002f8f0  jmp     loc_18002FAD7
0x18002f8f5  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002f8fa  nop
0x18002f8fb  xor     edx, edx
0x18002f8fd  jmp     loc_18002FA03
0x18002f902  mov     r14, [rsp+4B8h+var_468]
0x18002f907  test    r14, r14
0x18002f90a  jz      short loc_18002F925
0x18002f90c  call    cs:__imp_GetLastError
0x18002f912  mov     ebx, eax
0x18002f914  mov     rcx, r14; hKey
0x18002f917  call    cs:__imp_RegCloseKey
0x18002f91d  mov     ecx, ebx; dwErrCode
0x18002f91f  call    cs:__imp_SetLastError
0x18002f925  mov     [rsp+4B8h+var_468], rdi
0x18002f92a  lea     rax, [rsp+4B8h+var_468]
0x18002f92f  mov     [rsp+4B8h+phkResult], rax; phkResult
0x18002f934  mov     r9d, 20019h; samDesired
0x18002f93a  xor     r8d, r8d; ulOptions
0x18002f93d  lea     rdx, [rsp+4B8h+SubKey]; lpSubKey
0x18002f945  mov     rcx, [rsp+4B8h+hKey]; hKey
0x18002f94a  call    cs:__imp_RegOpenKeyExW
0x18002f950  mov     ebx, eax
0x18002f952  test    eax, eax
0x18002f954  jnz     loc_18002F9DD
0x18002f95a  xor     edx, edx; Val
0x18002f95c  mov     r8d, 200h; Size
0x18002f962  lea     rcx, [rsp+4B8h+Name]; void *
0x18002f96a  call    memset_0
0x18002f96f  mov     [rsp+4B8h+cchName], 100h
0x18002f977  mov     r14d, edi
0x18002f97a  xor     edx, edx
0x18002f97c  jmp     short loc_18002F9A9
0x18002f97e  mov     rdx, r12
0x18002f981  lea     rcx, [rsp+4B8h+Name]
0x18002f989  call    cs:__imp__o__wcsicmp
0x18002f98f  test    eax, eax
0x18002f991  jz      loc_18002FA40
0x18002f997  mov     [rsp+4B8h+cchName], 100h
0x18002f99f  test    ebx, ebx
0x18002f9a1  jnz     short loc_18002F9DD
0x18002f9a3  inc     r14d
0x18002f9a6  mov     edx, r14d; dwIndex
0x18002f9a9  mov     [rsp+4B8h+lpftLastWriteTime], rdi; lpftLastWriteTime
0x18002f9ae  mov     [rsp+4B8h+lpcchClass], rdi; lpcchClass
0x18002f9b3  mov     [rsp+4B8h+lpClass], rdi; lpClass
0x18002f9b8  mov     [rsp+4B8h+phkResult], rdi; lpReserved
0x18002f9bd  lea     r9, [rsp+4B8h+cchName]; lpcchName
0x18002f9c2  lea     r8, [rsp+4B8h+Name]; lpName
0x18002f9ca  mov     rcx, [rsp+4B8h+var_468]; hKey
0x18002f9cf  call    cs:__imp_RegEnumKeyExW
0x18002f9d5  test    eax, eax
0x18002f9d7  mov     ebx, eax
0x18002f9d9  jz      short loc_18002F97E
0x18002f9db  mov     ebx, edi
0x18002f9dd  mov     [rsp+4B8h+var_470], 100h
0x18002f9e5  mov     rcx, [rsp+4B8h+var_468]; hKey
0x18002f9ea  test    rcx, rcx
0x18002f9ed  jz      short loc_18002F9F5
0x18002f9ef  call    cs:__imp_RegCloseKey
0x18002f9f5  test    ebx, ebx
0x18002f9f7  jnz     loc_18002FAA7
0x18002f9fd  inc     r15d
0x18002fa00  mov     edx, r15d; dwIndex
0x18002fa03  mov     [rsp+4B8h+lpftLastWriteTime], rdi; lpftLastWriteTime
0x18002fa08  mov     [rsp+4B8h+lpcchClass], rdi; lpcchClass
0x18002fa0d  mov     [rsp+4B8h+lpClass], rdi; lpClass
0x18002fa12  mov     [rsp+4B8h+phkResult], rdi; lpReserved
0x18002fa17  mov     [rsp+4B8h+var_468], rdi
0x18002fa1c  lea     r9, [rsp+4B8h+var_470]; lpcchName
0x18002fa21  lea     r8, [rsp+4B8h+SubKey]; lpName
0x18002fa29  mov     rcx, [rsp+4B8h+hKey]; hKey
0x18002fa2e  call    cs:__imp_RegEnumKeyExW
0x18002fa34  test    eax, eax
0x18002fa36  mov     ebx, eax
0x18002fa38  jz      loc_18002F902
0x18002fa3e  jmp     short loc_18002FA97
0x18002fa40  mov     eax, [rsp+4B8h+var_470]
0x18002fa44  cmp     rax, 7FFFFFFEh
0x18002fa4a  jbe     short loc_18002FA51
0x18002fa4c  mov     [rsi], di
0x18002fa4f  jmp     short loc_18002FA92
0x18002fa51  lea     rdx, [rsp+4B8h+SubKey]
0x18002fa59  mov     ecx, 101h
0x18002fa5e  test    rax, rax
0x18002fa61  jz      short loc_18002FA82
0x18002fa63  movzx   r8d, word ptr [rdx]
0x18002fa67  test    r8w, r8w
0x18002fa6b  jz      short loc_18002FA82
0x18002fa6d  add     rdx, 2
0x18002fa71  mov     [rsi], r8w
0x18002fa75  add     rsi, 2
0x18002fa79  dec     rax
0x18002fa7c  sub     rcx, 1
0x18002fa80  jnz     short loc_18002FA5E
0x18002fa82  lea     rax, [rsi-2]
0x18002fa86  test    rcx, rcx
0x18002fa89  cmovnz  rax, rsi
0x18002fa8d  mov     [rax], di
0x18002fa90  jnz     short loc_18002FA97
0x18002fa92  mov     ebx, 0Eh
0x18002fa97  mov     rcx, [rsp+4B8h+var_468]; hKey
0x18002fa9c  test    rcx, rcx
0x18002fa9f  jz      short loc_18002FAA7
0x18002faa1  call    cs:__imp_RegCloseKey
0x18002faa7  mov     rcx, [rsp+4B8h+hKey]; hKey
0x18002faac  test    rcx, rcx
0x18002faaf  jz      short loc_18002FAB7
0x18002fab1  call    cs:__imp_RegCloseKey
0x18002fab7  mov     eax, ebx
0x18002fab9  jmp     short loc_18002FAD7
0x18002fabb  mov     rcx, [rsp+4B8h+hKey]; hKey
0x18002fac0  test    rcx, rcx
0x18002fac3  jz      short loc_18002FACB
0x18002fac5  call    cs:__imp_RegCloseKey
0x18002facb  mov     eax, 0Eh
0x18002fad0  jmp     short loc_18002FAD7
0x18002fad2  mov     eax, 57h ; 'W'
0x18002fad7  mov     rcx, [rsp+4B8h+var_38]
0x18002fadf  xor     rcx, rsp; StackCookie
0x18002fae2  call    __security_check_cookie
0x18002fae7  mov     rbx, [rsp+4B8h+arg_10]
0x18002faef  add     rsp, 490h
0x18002faf6  pop     r15
0x18002faf8  pop     r14
0x18002fafa  pop     r12
0x18002fafc  pop     rdi
0x18002fafd  pop     rsi
0x18002fafe  retn
```
