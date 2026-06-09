# CRegAccount::CreateCompilationMutextNameKey(void * *,ulong)

- ea: `0x180022c1c`
- end: `0x180022e18`
- name: `?CreateCompilationMutextNameKey@CRegAccount@@CAJPEAPEAXK@Z`
- size: `508`
- prototype: `__int64 __fastcall(void **, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180023838`

## callees

- `0x18000d56c`
- `0x18001d3c0`
- `0x180022c1c`
- `0x180026634`
- `0x18004d030`
- `0x18004d754`
- `0x18004eaa8`
- `0x1800653c0`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180022dca`
- `ADVAPI32!RegCloseKey` at `0x180022dd9`
- `ADVAPI32!RegCloseKey` at `0x180022dca`
- `ADVAPI32!RegCloseKey` at `0x180022dd9`
- `ADVAPI32!RegOpenKeyExW` at `0x180022cfc`
- `ADVAPI32!RegOpenKeyExW` at `0x180022cfc`
- `ADVAPI32!RegSetValueW` at `0x180022cc2`
- `ADVAPI32!RegSetValueW` at `0x180022cc2`

## string_xrefs

- `0x180022cbb`: `CompilationMutexName`
- `0x180022cf5`: `CompilationMutexName`

## pseudocode

```c
__int64 __fastcall CRegAccount::CreateCompilationMutextNameKey(void **a1, unsigned int a2)
{
  unsigned int RandomString; // ebx
  LSTATUS v5; // eax
  unsigned int i; // edi
  void *lpMem; // [rsp+38h] [rbp-29h] BYREF
  HKEY phkResult; // [rsp+40h] [rbp-21h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-19h] BYREF
  WCHAR Data[32]; // [rsp+58h] [rbp-9h] BYREF

  hKey = 0;
  phkResult = 0;
  lpMem = 0;
  RandomString = CRegInfo::OpenCurrentVersionKey((DWORD)&hKey, 0x20006u, 1, 1);
  if ( !RandomString )
  {
    memset_0(Data, 0, sizeof(Data));
    RandomString = GenerateRandomString(Data, 31);
    if ( !RandomString )
    {
      v5 = RegSetValueW(hKey, L"CompilationMutexName", 1u, Data, 0x20u);
      if ( v5 || (v5 = RegOpenKeyExW(hKey, L"CompilationMutexName", 0, 0x60019u, &phkResult)) != 0 )
      {
        RandomString = (unsigned __int16)v5 | 0x80070000;
        if ( v5 <= 0 )
          RandomString = v5;
      }
      else
      {
        RandomString = GetPrincipalSID((char *)L"administrators", &lpMem);
        if ( !RandomString )
        {
          RandomString = CRegAccount::SetAccessToRegKey(lpMem, phkResult, 0xF003Fu, 0);
          if ( !RandomString )
          {
            MemFree(lpMem);
            lpMem = 0;
            RandomString = GetPrincipalSID((char *)L"system", &lpMem);
            if ( !RandomString )
            {
              RandomString = CRegAccount::SetAccessToRegKey(lpMem, phkResult, 0x20019u, 1);
              if ( !RandomString )
              {
                MemFree(lpMem);
                lpMem = 0;
                for ( i = 0; i < a2; ++a1 )
                {
                  if ( *a1 )
                  {
                    RandomString = CRegAccount::SetAccessToRegKey(*a1, phkResult, 0x20019u, 1);
                    if ( RandomString )
                      break;
                  }
                  ++i;
                }
              }
            }
          }
        }
      }
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( lpMem )
    MemFree(lpMem);
  return RandomString;
}

```

## disassembly

```asm
0x180022c1c  mov     rax, rsp
0x180022c1f  mov     [rax+10h], rbx
0x180022c23  mov     [rax+18h], rsi
0x180022c27  mov     [rax+20h], rdi
0x180022c2b  push    rbp
0x180022c2c  push    r12
0x180022c2e  push    r14
0x180022c30  lea     rbp, [rax-5Fh]
0x180022c34  sub     rsp, 0A0h
0x180022c3b  mov     rax, cs:__security_cookie
0x180022c42  xor     rax, rsp
0x180022c45  mov     [rbp+57h+var_20], rax
0x180022c49  and     [rbp+57h+hKey], 0
0x180022c4e  mov     r12d, 1
0x180022c54  and     [rbp+57h+phkResult], 0
0x180022c59  mov     r14d, edx
0x180022c5c  and     [rbp+57h+lpMem], 0
0x180022c61  mov     rsi, rcx
0x180022c64  mov     r9d, r12d; int
0x180022c67  lea     rcx, [rbp+57h+hKey]; dwOptions
0x180022c6b  mov     r8d, r12d; int
0x180022c6e  mov     edx, 20006h; samDesired
0x180022c73  call    ?OpenCurrentVersionKey@CRegInfo@@SAJPEAPEAUHKEY__@@KHH@Z; CRegInfo::OpenCurrentVersionKey(HKEY__ * *,ulong,int,int)
0x180022c78  mov     ebx, eax
0x180022c7a  test    eax, eax
0x180022c7c  jnz     loc_180022DC1
0x180022c82  xor     edx, edx; Val
0x180022c84  lea     r8d, [r12+3Fh]; Size
0x180022c89  lea     rcx, [rbp+57h+Data]; void *
0x180022c8d  call    memset_0
0x180022c92  lea     edx, [rbx+1Fh]; int
0x180022c95  lea     rcx, [rbp+57h+Data]; unsigned __int16 *
0x180022c99  call    ?GenerateRandomString@@YAJPEAGH@Z; GenerateRandomString(ushort *,int)
0x180022c9e  mov     ebx, eax
0x180022ca0  test    eax, eax
0x180022ca2  jnz     loc_180022DC1
0x180022ca8  mov     rcx, [rbp+57h+hKey]; hKey
0x180022cac  lea     r9, [rbp+57h+Data]; lpData
0x180022cb0  mov     r8d, r12d; dwType
0x180022cb3  mov     [rsp+0B0h+cbData], 20h ; ' '; cbData
0x180022cbb  lea     rdx, aCompilationmut; "CompilationMutexName"
0x180022cc2  call    cs:__imp_RegSetValueW
0x180022cc8  test    eax, eax
0x180022cca  jz      short loc_180022CDF
0x180022ccc  movzx   ebx, ax
0x180022ccf  or      ebx, 80070000h
0x180022cd5  test    eax, eax
0x180022cd7  cmovle  ebx, eax
0x180022cda  jmp     loc_180022DC1
0x180022cdf  mov     rcx, [rbp+57h+hKey]; hKey
0x180022ce3  lea     rax, [rbp+57h+phkResult]
0x180022ce7  mov     r9d, 60019h; samDesired
0x180022ced  mov     qword ptr [rsp+0B0h+cbData], rax; phkResult
0x180022cf2  xor     r8d, r8d; ulOptions
0x180022cf5  lea     rdx, aCompilationmut; "CompilationMutexName"
0x180022cfc  call    cs:__imp_RegOpenKeyExW
0x180022d02  test    eax, eax
0x180022d04  jnz     short loc_180022CCC
0x180022d06  lea     rdx, [rbp+57h+lpMem]; void **
0x180022d0a  lea     rcx, aAdministrators; "administrators"
0x180022d11  call    ?GetPrincipalSID@@YAJPEBGPEAPEAX@Z; GetPrincipalSID(ushort const *,void * *)
0x180022d16  mov     ebx, eax
0x180022d18  test    eax, eax
0x180022d1a  jnz     loc_180022DC1
0x180022d20  mov     rdx, [rbp+57h+phkResult]; HKEY
0x180022d24  xor     r9d, r9d; int
0x180022d27  mov     rcx, [rbp+57h+lpMem]; void *
0x180022d2b  mov     r8d, 0F003Fh; unsigned int
0x180022d31  call    ?SetAccessToRegKey@CRegAccount@@SAJPEAXPEAUHKEY__@@KH@Z; CRegAccount::SetAccessToRegKey(void *,HKEY__ *,ulong,int)
0x180022d36  mov     ebx, eax
0x180022d38  test    eax, eax
0x180022d3a  jnz     loc_180022DC1
0x180022d40  mov     rcx, [rbp+57h+lpMem]; lpMem
0x180022d44  call    ?MemFree@@YAXPEAX@Z; MemFree(void *)
0x180022d49  and     [rbp+57h+lpMem], 0
0x180022d4e  lea     rdx, [rbp+57h+lpMem]; void **
0x180022d52  lea     rcx, aSystem_0; "system"
0x180022d59  call    ?GetPrincipalSID@@YAJPEBGPEAPEAX@Z; GetPrincipalSID(ushort const *,void * *)
0x180022d5e  mov     ebx, eax
0x180022d60  test    eax, eax
0x180022d62  jnz     short loc_180022DC1
0x180022d64  mov     rdx, [rbp+57h+phkResult]; HKEY
0x180022d68  mov     r9d, r12d; int
0x180022d6b  mov     rcx, [rbp+57h+lpMem]; void *
0x180022d6f  mov     r8d, 20019h; unsigned int
0x180022d75  call    ?SetAccessToRegKey@CRegAccount@@SAJPEAXPEAUHKEY__@@KH@Z; CRegAccount::SetAccessToRegKey(void *,HKEY__ *,ulong,int)
0x180022d7a  mov     ebx, eax
0x180022d7c  test    eax, eax
0x180022d7e  jnz     short loc_180022DC1
0x180022d80  mov     rcx, [rbp+57h+lpMem]; lpMem
0x180022d84  call    ?MemFree@@YAXPEAX@Z; MemFree(void *)
0x180022d89  and     [rbp+57h+lpMem], 0
0x180022d8e  xor     edi, edi
0x180022d90  test    r14d, r14d
0x180022d93  jz      short loc_180022DC1
0x180022d95  mov     rcx, [rsi]; void *
0x180022d98  test    rcx, rcx
0x180022d9b  jz      short loc_180022DB5
0x180022d9d  mov     rdx, [rbp+57h+phkResult]; HKEY
0x180022da1  mov     r9d, r12d; int
0x180022da4  mov     r8d, 20019h; unsigned int
0x180022daa  call    ?SetAccessToRegKey@CRegAccount@@SAJPEAXPEAUHKEY__@@KH@Z; CRegAccount::SetAccessToRegKey(void *,HKEY__ *,ulong,int)
0x180022daf  mov     ebx, eax
0x180022db1  test    eax, eax
0x180022db3  jnz     short loc_180022DC1
0x180022db5  add     edi, r12d
0x180022db8  add     rsi, 8
0x180022dbc  cmp     edi, r14d
0x180022dbf  jb      short loc_180022D95
0x180022dc1  mov     rcx, [rbp+57h+hKey]; hKey
0x180022dc5  test    rcx, rcx
0x180022dc8  jz      short loc_180022DD0
0x180022dca  call    cs:__imp_RegCloseKey
0x180022dd0  mov     rcx, [rbp+57h+phkResult]; hKey
0x180022dd4  test    rcx, rcx
0x180022dd7  jz      short loc_180022DDF
0x180022dd9  call    cs:__imp_RegCloseKey
0x180022ddf  mov     rcx, [rbp+57h+lpMem]; lpMem
0x180022de3  test    rcx, rcx
0x180022de6  jz      short loc_180022DED
0x180022de8  call    ?MemFree@@YAXPEAX@Z; MemFree(void *)
0x180022ded  mov     eax, ebx
0x180022def  mov     rcx, [rbp+57h+var_20]
0x180022df3  xor     rcx, rsp; StackCookie
0x180022df6  call    __security_check_cookie
0x180022dfb  lea     r11, [rsp+0B0h+var_10]
0x180022e03  mov     rbx, [r11+28h]
0x180022e07  mov     rsi, [r11+30h]
0x180022e0b  mov     rdi, [r11+38h]
0x180022e0f  mov     rsp, r11
0x180022e12  pop     r14
0x180022e14  pop     r12
0x180022e16  pop     rbp
0x180022e17  retn
```
