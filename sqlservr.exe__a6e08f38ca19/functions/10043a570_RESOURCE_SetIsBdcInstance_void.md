# RESOURCE::SetIsBdcInstance(void)

- ea: `0x10043a570`
- end: `0x10043a837`
- name: `?SetIsBdcInstance@RESOURCE@@QEAAXXZ`
- size: `711`
- prototype: `void __fastcall(RESOURCE *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x100416770`

## callees

- `0x100401580`
- `0x10043a570`

## import_xrefs

- `KERNEL32!GetEnvironmentVariableW` at `0x10043a5a4`
- `KERNEL32!GetEnvironmentVariableW` at `0x10043a790`
- `KERNEL32!GetEnvironmentVariableW` at `0x10043a7b7`
- `KERNEL32!GetEnvironmentVariableW` at `0x10043a5a4`
- `KERNEL32!GetEnvironmentVariableW` at `0x10043a790`
- `KERNEL32!GetEnvironmentVariableW` at `0x10043a7b7`
- `sqlTsEs!?CompareStringWEnglishNoCase@@YAHKEPEFB_WH0H@Z` at `0x10043a5f2`
- `sqlTsEs!?CompareStringWEnglishNoCase@@YAHKEPEFB_WH0H@Z` at `0x10043a642`
- `sqlTsEs!?CompareStringWEnglishNoCase@@YAHKEPEFB_WH0H@Z` at `0x10043a692`
- `sqlTsEs!?CompareStringWEnglishNoCase@@YAHKEPEFB_WH0H@Z` at `0x10043a6e2`
- `sqlTsEs!?CompareStringWEnglishNoCase@@YAHKEPEFB_WH0H@Z` at `0x10043a731`
- `sqlTsEs!?CompareStringWEnglishNoCase@@YAHKEPEFB_WH0H@Z` at `0x10043a804`
- `sqlTsEs!?CompareStringWEnglishNoCase@@YAHKEPEFB_WH0H@Z` at `0x10043a5f2`
- `sqlTsEs!?CompareStringWEnglishNoCase@@YAHKEPEFB_WH0H@Z` at `0x10043a642`
- `sqlTsEs!?CompareStringWEnglishNoCase@@YAHKEPEFB_WH0H@Z` at `0x10043a692`
- `sqlTsEs!?CompareStringWEnglishNoCase@@YAHKEPEFB_WH0H@Z` at `0x10043a6e2`
- `sqlTsEs!?CompareStringWEnglishNoCase@@YAHKEPEFB_WH0H@Z` at `0x10043a731`
- `sqlTsEs!?CompareStringWEnglishNoCase@@YAHKEPEFB_WH0H@Z` at `0x10043a804`
- `sqldk!?IsLinux@OsInfo@@QEBA?B_NXZ` at `0x10043a74a`
- `sqldk!?IsLinux@OsInfo@@QEBA?B_NXZ` at `0x10043a74a`
- `sqldk!?SOS_OS_OsInfo@@3VOsInfo@@A` at `0x10043a743`

## string_xrefs

- `0x10043a66b`: `compute`

## pseudocode

```c
void __fastcall RESOURCE::SetIsBdcInstance(RESOURCE *this)
{
  __int64 v2; // rbx
  __int64 v3; // rax
  __int64 v4; // rax
  __int64 v5; // rax
  __int64 v6; // rax
  __int64 v7; // rax
  bool v8; // al
  wchar_t Buffer[264]; // [rsp+30h] [rbp-438h] BYREF
  wchar_t v10[264]; // [rsp+240h] [rbp-228h] BYREF

  v2 = -1;
  if ( GetEnvironmentVariableW(L"MSSQL_POD_TYPE", Buffer, 0x105u) )
  {
    v3 = -1;
    do
      ++v3;
    while ( Buffer[v3] );
    if ( CompareStringWEnglishNoCase(1u, 0, Buffer, (unsigned __int64)(2 * (int)v3) >> 1, L"master", 6) == 2 )
    {
      *((_BYTE *)this + 48772) = 1;
    }
    else
    {
      v4 = -1;
      do
        ++v4;
      while ( Buffer[v4] );
      if ( CompareStringWEnglishNoCase(1u, 0, Buffer, (unsigned __int64)(2 * (int)v4) >> 1, L"storage", 7) == 2 )
      {
        *((_BYTE *)this + 48769) = 1;
      }
      else
      {
        v5 = -1;
        do
          ++v5;
        while ( Buffer[v5] );
        if ( CompareStringWEnglishNoCase(1u, 0, Buffer, (unsigned __int64)(2 * (int)v5) >> 1, L"compute", 7) == 2 )
        {
          *((_BYTE *)this + 48773) = 1;
        }
        else
        {
          v6 = -1;
          do
            ++v6;
          while ( Buffer[v6] );
          if ( CompareStringWEnglishNoCase(1u, 0, Buffer, (unsigned __int64)(2 * (int)v6) >> 1, L"data", 4) == 2 )
          {
            *((_BYTE *)this + 48774) = 1;
          }
          else
          {
            v7 = -1;
            do
              ++v7;
            while ( Buffer[v7] );
            if ( CompareStringWEnglishNoCase(1u, 0, Buffer, (unsigned __int64)(2 * (int)v7) >> 1, L"miaa", 4) == 2 )
              *((_BYTE *)this + 48775) = 1;
          }
        }
      }
    }
  }
  v8 = OsInfo::IsLinux(SOS_OS_OsInfo)
    && (*((_BYTE *)this + 48772) || *((_BYTE *)this + 48769) || *((_BYTE *)this + 48773) || *((_BYTE *)this + 48774));
  *((_BYTE *)this + 48768) = v8;
  if ( GetEnvironmentVariableW(L"MSSQL_DOMAIN", 0, 0) > 1 )
    *((_BYTE *)this + 48777) = 1;
  if ( GetEnvironmentVariableW(L"MSSQL_KERBEROS_DELEGATION_MODE", v10, 0x105u) )
  {
    do
      ++v2;
    while ( v10[v2] );
    if ( CompareStringWEnglishNoCase(1u, 0, v10, (unsigned __int64)(2 * (int)v2) >> 1, L"None", 4) != 2 )
      *((_BYTE *)this + 48778) = 1;
  }
}

```

## disassembly

```asm
0x10043a570  mov     [rsp+arg_8], rbx
0x10043a575  push    rdi
0x10043a576  sub     rsp, 460h
0x10043a57d  mov     rax, cs:__security_cookie
0x10043a584  xor     rax, rsp
0x10043a587  mov     [rsp+468h+var_18], rax
0x10043a58f  mov     rdi, rcx
0x10043a592  lea     rdx, [rsp+468h+Buffer]; lpBuffer
0x10043a597  lea     rcx, aMssqlPodType; "MSSQL_POD_TYPE"
0x10043a59e  mov     r8d, 105h; nSize
0x10043a5a4  call    cs:__imp_GetEnvironmentVariableW
0x10043a5aa  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x10043a5b1  test    eax, eax
0x10043a5b3  jz      loc_10043A743
0x10043a5b9  lea     rcx, [rsp+468h+Buffer]
0x10043a5be  mov     rax, rbx
0x10043a5c1  inc     rax
0x10043a5c4  cmp     word ptr [rcx+rax*2], 0
0x10043a5c9  jnz     short loc_10043A5C1
0x10043a5cb  lea     rcx, aMaster; "master"
0x10043a5d2  mov     [rsp+468h+var_440], 6
0x10043a5da  xor     edx, edx
0x10043a5dc  mov     [rsp+468h+var_448], rcx
0x10043a5e1  add     rax, rax
0x10043a5e4  lea     r8, [rsp+468h+Buffer]
0x10043a5e9  movsxd  r9, eax
0x10043a5ec  shr     r9, 1
0x10043a5ef  lea     ecx, [rdx+1]
0x10043a5f2  call    cs:__imp_?CompareStringWEnglishNoCase@@YAHKEPEFB_WH0H@Z; CompareStringWEnglishNoCase(ulong,uchar,wchar_t const *,int,wchar_t const *,int)
0x10043a5f8  cmp     eax, 2
0x10043a5fb  jnz     short loc_10043A609
0x10043a5fd  mov     byte ptr [rdi+0BE84h], 1
0x10043a604  jmp     loc_10043A743
0x10043a609  lea     rcx, [rsp+468h+Buffer]
0x10043a60e  mov     rax, rbx
0x10043a611  inc     rax
0x10043a614  cmp     word ptr [rcx+rax*2], 0
0x10043a619  jnz     short loc_10043A611
0x10043a61b  lea     rcx, aStorage; "storage"
0x10043a622  mov     [rsp+468h+var_440], 7
0x10043a62a  xor     edx, edx
0x10043a62c  mov     [rsp+468h+var_448], rcx
0x10043a631  add     rax, rax
0x10043a634  lea     r8, [rsp+468h+Buffer]
0x10043a639  movsxd  r9, eax
0x10043a63c  shr     r9, 1
0x10043a63f  lea     ecx, [rdx+1]
0x10043a642  call    cs:__imp_?CompareStringWEnglishNoCase@@YAHKEPEFB_WH0H@Z; CompareStringWEnglishNoCase(ulong,uchar,wchar_t const *,int,wchar_t const *,int)
0x10043a648  cmp     eax, 2
0x10043a64b  jnz     short loc_10043A659
0x10043a64d  mov     byte ptr [rdi+0BE81h], 1
0x10043a654  jmp     loc_10043A743
0x10043a659  lea     rcx, [rsp+468h+Buffer]
0x10043a65e  mov     rax, rbx
0x10043a661  inc     rax
0x10043a664  cmp     word ptr [rcx+rax*2], 0
0x10043a669  jnz     short loc_10043A661
0x10043a66b  lea     rcx, aCompute; "compute"
0x10043a672  mov     [rsp+468h+var_440], 7
0x10043a67a  xor     edx, edx
0x10043a67c  mov     [rsp+468h+var_448], rcx
0x10043a681  add     rax, rax
0x10043a684  lea     r8, [rsp+468h+Buffer]
0x10043a689  movsxd  r9, eax
0x10043a68c  shr     r9, 1
0x10043a68f  lea     ecx, [rdx+1]
0x10043a692  call    cs:__imp_?CompareStringWEnglishNoCase@@YAHKEPEFB_WH0H@Z; CompareStringWEnglishNoCase(ulong,uchar,wchar_t const *,int,wchar_t const *,int)
0x10043a698  cmp     eax, 2
0x10043a69b  jnz     short loc_10043A6A9
0x10043a69d  mov     byte ptr [rdi+0BE85h], 1
0x10043a6a4  jmp     loc_10043A743
0x10043a6a9  lea     rcx, [rsp+468h+Buffer]
0x10043a6ae  mov     rax, rbx
0x10043a6b1  inc     rax
0x10043a6b4  cmp     word ptr [rcx+rax*2], 0
0x10043a6b9  jnz     short loc_10043A6B1
0x10043a6bb  lea     rcx, aData; "data"
0x10043a6c2  mov     [rsp+468h+var_440], 4
0x10043a6ca  xor     edx, edx
0x10043a6cc  mov     [rsp+468h+var_448], rcx
0x10043a6d1  add     rax, rax
0x10043a6d4  lea     r8, [rsp+468h+Buffer]
0x10043a6d9  movsxd  r9, eax
0x10043a6dc  shr     r9, 1
0x10043a6df  lea     ecx, [rdx+1]
0x10043a6e2  call    cs:__imp_?CompareStringWEnglishNoCase@@YAHKEPEFB_WH0H@Z; CompareStringWEnglishNoCase(ulong,uchar,wchar_t const *,int,wchar_t const *,int)
0x10043a6e8  cmp     eax, 2
0x10043a6eb  jnz     short loc_10043A6F6
0x10043a6ed  mov     byte ptr [rdi+0BE86h], 1
0x10043a6f4  jmp     short loc_10043A743
0x10043a6f6  lea     rcx, [rsp+468h+Buffer]
0x10043a6fb  mov     rax, rbx
0x10043a6fe  xchg    ax, ax
0x10043a700  inc     rax
0x10043a703  cmp     word ptr [rcx+rax*2], 0
0x10043a708  jnz     short loc_10043A700
0x10043a70a  lea     rcx, aMiaa; "miaa"
0x10043a711  mov     [rsp+468h+var_440], 4
0x10043a719  xor     edx, edx
0x10043a71b  mov     [rsp+468h+var_448], rcx
0x10043a720  add     rax, rax
0x10043a723  lea     r8, [rsp+468h+Buffer]
0x10043a728  movsxd  r9, eax
0x10043a72b  shr     r9, 1
0x10043a72e  lea     ecx, [rdx+1]
0x10043a731  call    cs:__imp_?CompareStringWEnglishNoCase@@YAHKEPEFB_WH0H@Z; CompareStringWEnglishNoCase(ulong,uchar,wchar_t const *,int,wchar_t const *,int)
0x10043a737  cmp     eax, 2
0x10043a73a  jnz     short loc_10043A743
0x10043a73c  mov     byte ptr [rdi+0BE87h], 1
0x10043a743  mov     rcx, cs:__imp_?SOS_OS_OsInfo@@3VOsInfo@@A; OsInfo SOS_OS_OsInfo
0x10043a74a  call    cs:__imp_?IsLinux@OsInfo@@QEBA?B_NXZ; OsInfo::IsLinux(void)
0x10043a750  test    al, al
0x10043a752  jz      short loc_10043A77C
0x10043a754  cmp     byte ptr [rdi+0BE84h], 0
0x10043a75b  jnz     short loc_10043A778
0x10043a75d  cmp     byte ptr [rdi+0BE81h], 0
0x10043a764  jnz     short loc_10043A778
0x10043a766  cmp     byte ptr [rdi+0BE85h], 0
0x10043a76d  jnz     short loc_10043A778
0x10043a76f  cmp     byte ptr [rdi+0BE86h], 0
0x10043a776  jz      short loc_10043A77C
0x10043a778  mov     al, 1
0x10043a77a  jmp     short loc_10043A77E
0x10043a77c  xor     al, al
0x10043a77e  xor     r8d, r8d; nSize
0x10043a781  mov     [rdi+0BE80h], al
0x10043a787  xor     edx, edx; lpBuffer
0x10043a789  lea     rcx, aMssqlDomain; "MSSQL_DOMAIN"
0x10043a790  call    cs:__imp_GetEnvironmentVariableW
0x10043a796  cmp     eax, 1
0x10043a799  jbe     short loc_10043A7A2
0x10043a79b  mov     byte ptr [rdi+0BE89h], 1
0x10043a7a2  mov     r8d, 105h; nSize
0x10043a7a8  lea     rdx, [rsp+468h+var_228]; lpBuffer
0x10043a7b0  lea     rcx, aMssqlKerberosD; "MSSQL_KERBEROS_DELEGATION_MODE"
0x10043a7b7  call    cs:__imp_GetEnvironmentVariableW
0x10043a7bd  test    eax, eax
0x10043a7bf  jz      short loc_10043A816
0x10043a7c1  lea     rax, [rsp+468h+var_228]
0x10043a7c9  nop     dword ptr [rax+00000000h]
0x10043a7d0  inc     rbx
0x10043a7d3  cmp     word ptr [rax+rbx*2], 0
0x10043a7d8  jnz     short loc_10043A7D0
0x10043a7da  lea     rdx, aNone; "None"
0x10043a7e1  mov     [rsp+468h+var_440], 4
0x10043a7e9  mov     [rsp+468h+var_448], rdx
0x10043a7ee  lea     r8, [rsp+468h+var_228]
0x10043a7f6  xor     edx, edx
0x10043a7f8  add     rbx, rbx
0x10043a7fb  movsxd  r9, ebx
0x10043a7fe  shr     r9, 1
0x10043a801  lea     ecx, [rdx+1]
0x10043a804  call    cs:__imp_?CompareStringWEnglishNoCase@@YAHKEPEFB_WH0H@Z; CompareStringWEnglishNoCase(ulong,uchar,wchar_t const *,int,wchar_t const *,int)
0x10043a80a  cmp     eax, 2
0x10043a80d  jz      short loc_10043A816
0x10043a80f  mov     byte ptr [rdi+0BE8Ah], 1
0x10043a816  mov     rcx, [rsp+468h+var_18]
0x10043a81e  xor     rcx, rsp; StackCookie
0x10043a821  call    __security_check_cookie
0x10043a826  mov     rbx, [rsp+468h+arg_8]
0x10043a82e  add     rsp, 460h
0x10043a835  pop     rdi
0x10043a836  retn
```
