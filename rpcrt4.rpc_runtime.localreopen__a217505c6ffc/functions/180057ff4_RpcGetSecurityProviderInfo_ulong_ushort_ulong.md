# RpcGetSecurityProviderInfo(ulong,ushort * *,ulong *)

- ea: `0x180057ff4`
- end: `0x180058226`
- name: `?RpcGetSecurityProviderInfo@@YAJKPEAPEAGPEAK@Z`
- size: `562`
- prototype: `__int64 __fastcall(unsigned int, unsigned __int16 **, unsigned int *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180057b70`
- `0x1800b5e40`

## callees

- `0x18002e750`
- `0x180057ff4`
- `0x1800b69ec`
- `0x1800ceda0`

## import_xrefs

- `ntdll!_itoa_s` at `0x180058065`
- `ntdll!_itoa_s` at `0x180058065`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180058092`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180058092`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180058192`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800581d5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180058213`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180058192`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800581d5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180058213`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18005817f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18005817f`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyA` at `0x180058106`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyA` at `0x180058106`

## string_xrefs

- `0x180058084`: `Software\Microsoft\Rpc\SecurityService`

## pseudocode

```c
__int64 __fastcall RpcGetSecurityProviderInfo(int a1, unsigned __int16 **a2, unsigned int *a3)
{
  __int64 i; // rcx
  unsigned int ValueW; // ebx
  const unsigned __int16 *v7; // rcx
  unsigned __int16 *v8; // rax
  DWORD cSubKeys; // [rsp+60h] [rbp-A0h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-98h] BYREF
  DWORD cValues; // [rsp+70h] [rbp-90h] BYREF
  DWORD pcbData; // [rsp+74h] [rbp-8Ch] BYREF
  DWORD cbMaxValueLen; // [rsp+78h] [rbp-88h] BYREF
  DWORD cchClass; // [rsp+7Ch] [rbp-84h] BYREF
  struct _FILETIME ftLastWriteTime; // [rsp+80h] [rbp-80h] BYREF
  char Buffer[16]; // [rsp+88h] [rbp-78h] BYREF
  WCHAR Value[12]; // [rsp+98h] [rbp-68h] BYREF
  CHAR Class[64]; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int16 pvData[136]; // [rsp+F0h] [rbp-10h] BYREF

  cSubKeys = 0;
  cValues = 0;
  cbMaxValueLen = 0;
  pcbData = 129;
  cchClass = 64;
  ftLastWriteTime = 0;
  hKey = 0;
  _itoa_s(a1, Buffer, 0xCu, 10);
  if ( RegOpenKeyExA(HKEY_LOCAL_MACHINE, "Software\\Microsoft\\Rpc\\SecurityService", 0, 0x20019u, &hKey) )
    return 1747;
  if ( RegQueryInfoKeyA(
         hKey,
         Class,
         &cchClass,
         0,
         &cSubKeys,
         &cSubKeys,
         &cSubKeys,
         &cValues,
         &cSubKeys,
         &cbMaxValueLen,
         &cSubKeys,
         &ftLastWriteTime)
    || cValues < 2 )
  {
    RegCloseKey(hKey);
    return 1747;
  }
  if ( cValues <= 0xFFFF )
  {
    *a3 = cValues - 2;
    for ( i = 0; i != 12; ++i )
      Value[i] = Buffer[i];
    Value[11] = 0;
    ValueW = RegGetValueW(hKey, 0, Value, 2u, 0, pvData, &pcbData);
    RegCloseKey(hKey);
    v7 = pvData;
    if ( ValueW )
    {
      ValueW = GetDefaultSecurityDll(pvData, pcbData);
      if ( ValueW )
        return 1747;
      v7 = DefaultSecurityDLL;
    }
    v8 = DuplicateString(v7);
    *a2 = v8;
    if ( !v8 )
      return 14;
    return ValueW;
  }
  RegCloseKey(hKey);
  return 14;
}

```

## disassembly

```asm
0x180057ff4  push    rbp
0x180057ff6  push    rbx
0x180057ff7  push    rdi
0x180057ff8  lea     rbp, [rsp-110h]
0x180058000  sub     rsp, 210h
0x180058007  mov     rax, cs:__security_cookie
0x18005800e  xor     rax, rsp
0x180058011  mov     [rbp+120h+var_20], rax
0x180058018  mov     r9d, 0Ah; Radix
0x18005801e  mov     [rsp+220h+cSubKeys], 0
0x180058026  mov     rbx, r8
0x180058029  mov     [rsp+220h+cValues], 0
0x180058031  mov     rdi, rdx
0x180058034  mov     [rsp+220h+cbMaxValueLen], 0
0x18005803c  lea     rdx, [rbp+120h+Buffer]; Buffer
0x180058040  mov     [rsp+220h+pcbData], 81h
0x180058048  lea     r8d, [r9+2]; BufferCount
0x18005804c  mov     [rsp+220h+cchClass], 40h ; '@'
0x180058054  mov     qword ptr [rbp+120h+ftLastWriteTime.dwLowDateTime], 0
0x18005805c  mov     [rsp+220h+hKey], 0
0x180058065  call    cs:__imp__itoa_s
0x18005806c  nop     dword ptr [rax+rax+00h]
0x180058071  lea     rax, [rsp+220h+hKey]
0x180058076  mov     r9d, 20019h; samDesired
0x18005807c  xor     r8d, r8d; ulOptions
0x18005807f  mov     [rsp+220h+phkResult], rax; phkResult
0x180058084  lea     rdx, SubKey; "Software\\Microsoft\\Rpc\\SecurityServi"...
0x18005808b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180058092  call    cs:__imp_RegOpenKeyExA
0x180058099  nop     dword ptr [rax+rax+00h]
0x18005809e  test    eax, eax
0x1800580a0  jnz     loc_18005821F
0x1800580a6  mov     rcx, [rsp+220h+hKey]; hKey
0x1800580ab  lea     rax, [rbp+120h+ftLastWriteTime]
0x1800580af  mov     [rsp+220h+lpftLastWriteTime], rax; lpftLastWriteTime
0x1800580b4  lea     r8, [rsp+220h+cchClass]; lpcchClass
0x1800580b9  lea     rax, [rsp+220h+cSubKeys]
0x1800580be  xor     r9d, r9d; lpReserved
0x1800580c1  mov     [rsp+220h+lpcbSecurityDescriptor], rax; lpcbSecurityDescriptor
0x1800580c6  lea     rdx, [rbp+120h+Class]; lpClass
0x1800580ca  lea     rax, [rsp+220h+cbMaxValueLen]
0x1800580cf  mov     [rsp+220h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x1800580d4  lea     rax, [rsp+220h+cSubKeys]
0x1800580d9  mov     [rsp+220h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x1800580de  lea     rax, [rsp+220h+cValues]
0x1800580e3  mov     [rsp+220h+lpcValues], rax; lpcValues
0x1800580e8  lea     rax, [rsp+220h+cSubKeys]
0x1800580ed  mov     [rsp+220h+lpcbMaxClassLen], rax; lpcbMaxClassLen
0x1800580f2  lea     rax, [rsp+220h+cSubKeys]
0x1800580f7  mov     [rsp+220h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x1800580fc  lea     rax, [rsp+220h+cSubKeys]
0x180058101  mov     [rsp+220h+phkResult], rax; lpcSubKeys
0x180058106  call    cs:__imp_RegQueryInfoKeyA
0x18005810d  nop     dword ptr [rax+rax+00h]
0x180058112  test    eax, eax
0x180058114  jnz     loc_18005820E
0x18005811a  mov     eax, [rsp+220h+cValues]
0x18005811e  mov     r9d, 2; dwFlags
0x180058124  cmp     eax, r9d
0x180058127  jb      loc_18005820E
0x18005812d  cmp     eax, 0FFFFh
0x180058132  ja      loc_1800581D0
0x180058138  add     eax, 0FFFFFFFEh
0x18005813b  mov     [rbx], eax
0x18005813d  xor     ecx, ecx
0x18005813f  movsx   eax, [rbp+rcx+120h+Buffer]
0x180058144  mov     [rbp+rcx*2+120h+Value], ax
0x180058149  inc     rcx
0x18005814c  cmp     rcx, 0Ch
0x180058150  jnz     short loc_18005813F
0x180058152  mov     rcx, [rsp+220h+hKey]; hkey
0x180058157  lea     r8, [rbp+120h+Value]; lpValue
0x18005815b  xor     eax, eax
0x18005815d  xor     edx, edx; lpSubKey
0x18005815f  mov     [rbp+120h+var_172], ax
0x180058163  lea     rax, [rsp+220h+pcbData]
0x180058168  mov     [rsp+220h+lpcbMaxClassLen], rax; pcbData
0x18005816d  lea     rax, [rbp+120h+pvData]
0x180058171  mov     [rsp+220h+lpcbMaxSubKeyLen], rax; pvData
0x180058176  mov     [rsp+220h+phkResult], 0; pdwType
0x18005817f  call    cs:__imp_RegGetValueW
0x180058186  nop     dword ptr [rax+rax+00h]
0x18005818b  mov     rcx, [rsp+220h+hKey]; hKey
0x180058190  mov     ebx, eax
0x180058192  call    cs:__imp_RegCloseKey
0x180058199  nop     dword ptr [rax+rax+00h]
0x18005819e  lea     rcx, [rbp+120h+pvData]; Src
0x1800581a2  test    ebx, ebx
0x1800581a4  jnz     short loc_1800581E8
0x1800581a6  call    ?DuplicateString@@YAPEAGPEBG@Z; DuplicateString(ushort const *)
0x1800581ab  mov     [rdi], rax
0x1800581ae  test    rax, rax
0x1800581b1  jz      short loc_180058207
0x1800581b3  mov     eax, ebx
0x1800581b5  mov     rcx, [rbp+120h+var_20]
0x1800581bc  xor     rcx, rsp; StackCookie
0x1800581bf  call    __security_check_cookie
0x1800581c4  add     rsp, 210h
0x1800581cb  pop     rdi
0x1800581cc  pop     rbx
0x1800581cd  pop     rbp
0x1800581ce  retn
0x1800581d0  mov     rcx, [rsp+220h+hKey]; hKey
0x1800581d5  call    cs:__imp_RegCloseKey
0x1800581dc  nop     dword ptr [rax+rax+00h]
0x1800581e1  mov     eax, 0Eh
0x1800581e6  jmp     short loc_1800581B5
0x1800581e8  mov     edx, [rsp+220h+pcbData]; unsigned int
0x1800581ec  call    ?GetDefaultSecurityDll@@YAJPEAGK@Z; GetDefaultSecurityDll(ushort *,ulong)
0x1800581f1  mov     ebx, eax
0x1800581f3  test    eax, eax
0x1800581f5  jnz     short loc_180058200
0x1800581f7  mov     rcx, cs:?DefaultSecurityDLL@@3PEAGEA; ushort * DefaultSecurityDLL
0x1800581fe  jmp     short loc_1800581A6
0x180058200  mov     ebx, 6D3h
0x180058205  jmp     short loc_1800581B3
0x180058207  mov     ebx, 0Eh
0x18005820c  jmp     short loc_1800581B3
0x18005820e  mov     rcx, [rsp+220h+hKey]; hKey
0x180058213  call    cs:__imp_RegCloseKey
0x18005821a  nop     dword ptr [rax+rax+00h]
0x18005821f  mov     eax, 6D3h
0x180058224  jmp     short loc_1800581B5
```
