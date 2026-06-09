# UpdatePolicyReader::ReadUXPolicy(tagUpdatePolicy,tagUpdatePolicyValue_V1 *)

- ea: `0x18001e25c`
- end: `0x18001e47a`
- name: `?ReadUXPolicy@UpdatePolicyReader@@CAJW4tagUpdatePolicy@@PEAUtagUpdatePolicyValue_V1@@@Z`
- size: `542`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x18001a320`

## callees

- `0x18000aac0`
- `0x18001e25c`
- `0x18001f4a8`
- `0x180026c78`
- `0x18002fda9`
- `0x18002ffd0`

## string_xrefs

- `0x18001e38d`: `AllowMUUpdateService`
- `0x18001e295`: `C:\__w\1\s\src\Client\policy\src\Update\PolicyReader.cpp`
- `0x18001e3ca`: `C:\__w\1\s\src\Client\policy\src\Update\PolicyReader.cpp`
- `0x18001e3de`: `C:\__w\1\s\src\Client\policy\src\Update\PolicyReader.cpp`
- `0x18001e364`: `WindowsUpdateUXRoot`

## pseudocode

```c
__int64 __fastcall UpdatePolicyReader::ReadUXPolicy(int a1, __int64 a2)
{
  unsigned int v3; // ebx
  __int64 v4; // rdx
  bool v6; // zf
  bool v7; // zf
  int v8; // ecx
  int v9; // ecx
  int v10; // ecx
  int v11; // ecx
  int v12; // ecx
  int v13; // ecx
  int v14; // ecx
  int v15; // ecx
  bool v16; // zf
  int v17; // ecx
  int v18; // ecx
  int RedirectedRegistryKeyName; // eax
  unsigned int PolicyDword; // edi
  __int64 v21; // rdx
  unsigned __int64 v22; // r9
  int v23; // ecx
  int v24; // ecx
  int v25; // ecx
  int v26; // ecx
  unsigned int v27; // [rsp+20h] [rbp-248h]
  unsigned int v28; // [rsp+20h] [rbp-248h]
  unsigned int v29[4]; // [rsp+30h] [rbp-238h] BYREF
  WCHAR SubKey[264]; // [rsp+40h] [rbp-228h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+0h]

  if ( !a2 )
  {
    v3 = -2147467261;
    v4 = 2971;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\policy\\src\\Update\\PolicyReader.cpp",
      (const char *)v3,
      v27);
    return v3;
  }
  *(_DWORD *)a2 = a1;
  if ( a1 > 24 )
  {
    if ( a1 > 34 )
    {
      v18 = a1 - 35;
      if ( !v18 )
        return 0;
    }
    else
    {
      if ( a1 == 34 )
        return 0;
      v18 = a1 - 25;
      if ( !v18 )
      {
        v29[0] = 0;
        memset_0(SubKey, 0, 0x208u);
        RedirectedRegistryKeyName = PolicyRegistryHelper::GetRedirectedRegistryKeyName(
                                      (wchar_t *)L"WindowsUpdateUXRoot",
                                      L"\\Settings",
                                      SubKey,
                                      (wchar_t **)0x104);
        PolicyDword = RedirectedRegistryKeyName;
        if ( RedirectedRegistryKeyName >= 0 )
        {
          PolicyDword = PolicyHelpers::ReadPolicyDword(SubKey, L"AllowMUUpdateService", 0, 0, 1u, v29);
          v22 = PolicyDword;
          if ( PolicyDword + 2147024894 <= 1 )
          {
            *(_QWORD *)(a2 + 4) = 0;
            return 0;
          }
          if ( (PolicyDword & 0x80000000) == 0 )
          {
            *(_DWORD *)(a2 + 24) = v29[0];
            *(_DWORD *)(a2 + 4) = 1;
            *(_WORD *)(a2 + 16) = 3;
            *(_DWORD *)(a2 + 8) = 4;
            return 0;
          }
          v21 = 3043;
        }
        else
        {
          v21 = 3030;
          v22 = (unsigned int)RedirectedRegistryKeyName;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v21,
          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\policy\\src\\Update\\PolicyReader.cpp",
          (const char *)v22,
          v27);
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xBA8,
          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\policy\\src\\Update\\PolicyReader.cpp",
          (const char *)PolicyDword,
          v28);
        return PolicyDword;
      }
    }
    v23 = v18 - 1;
    if ( !v23 )
      return 0;
    v24 = v23 - 1;
    if ( !v24 )
      return 0;
    v25 = v24 - 1;
    if ( !v25 )
      return 0;
    a1 = v25 - 1;
    v6 = a1 == 0;
    goto LABEL_37;
  }
  if ( a1 == 24 )
    return 0;
  if ( a1 <= 10 )
  {
    if ( a1 == 10 )
      return 0;
    if ( a1 > 5 )
    {
      v8 = a1 - 6;
      v7 = v8 == 0;
LABEL_39:
      if ( !v7 )
      {
        v26 = v8 - 1;
        if ( v26 )
        {
          v17 = v26 - 1;
          v16 = v17 == 0;
          goto LABEL_42;
        }
      }
      return 0;
    }
    if ( a1 == 5 )
      return 0;
    v6 = a1 == 0;
LABEL_37:
    if ( v6 )
      return 0;
    v8 = a1 - 1;
    v7 = v8 == 0;
    goto LABEL_39;
  }
  v9 = a1 - 11;
  if ( v9 )
  {
    v10 = v9 - 1;
    if ( v10 )
    {
      v11 = v10 - 1;
      if ( v11 )
      {
        v12 = v11 - 1;
        if ( v12 )
        {
          v13 = v12 - 1;
          if ( v13 )
          {
            v14 = v13 - 1;
            if ( v14 )
            {
              v15 = v14 - 2;
              if ( v15 )
              {
                v17 = v15 - 4;
                v16 = v17 == 0;
LABEL_42:
                if ( !v16 && v17 != 1 )
                {
                  v3 = -2147024809;
                  v4 = 2975;
                  goto LABEL_3;
                }
              }
            }
          }
        }
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18001e25c  mov     [rsp+arg_0], rbx
0x18001e261  push    rdi
0x18001e262  sub     rsp, 260h
0x18001e269  mov     rax, cs:__security_cookie
0x18001e270  xor     rax, rsp
0x18001e273  mov     [rsp+268h+var_18], rax
0x18001e27b  mov     rbx, rdx
0x18001e27e  test    rdx, rdx
0x18001e281  jnz     short loc_18001E2AB
0x18001e283  mov     ebx, 80004003h
0x18001e288  mov     edx, 0B9Bh; void *
0x18001e28d  mov     rcx, [rsp+268h]; this
0x18001e295  lea     r8, aCW1SSrcClientP_9; "C:\\__w\\1\\s\\src\\Client\\policy\\src"...
0x18001e29c  mov     r9d, ebx; char *
0x18001e29f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e2a4  mov     eax, ebx
0x18001e2a6  jmp     loc_18001E413
0x18001e2ab  mov     [rdx], ecx
0x18001e2ad  cmp     ecx, 18h
0x18001e2b0  jg      short loc_18001E324
0x18001e2b2  jz      loc_18001E411
0x18001e2b8  cmp     ecx, 0Ah
0x18001e2bb  jg      short loc_18001E2DD
0x18001e2bd  jz      loc_18001E411
0x18001e2c3  cmp     ecx, 5
0x18001e2c6  jg      short loc_18001E2D5
0x18001e2c8  jz      loc_18001E411
0x18001e2ce  test    ecx, ecx
0x18001e2d0  jmp     loc_18001E455
0x18001e2d5  sub     ecx, 6
0x18001e2d8  jmp     loc_18001E45A
0x18001e2dd  sub     ecx, 0Bh
0x18001e2e0  jz      loc_18001E411
0x18001e2e6  sub     ecx, 1
0x18001e2e9  jz      loc_18001E411
0x18001e2ef  sub     ecx, 1
0x18001e2f2  jz      loc_18001E411
0x18001e2f8  sub     ecx, 1
0x18001e2fb  jz      loc_18001E411
0x18001e301  sub     ecx, 1
0x18001e304  jz      loc_18001E411
0x18001e30a  sub     ecx, 1
0x18001e30d  jz      loc_18001E411
0x18001e313  sub     ecx, 2
0x18001e316  jz      loc_18001E411
0x18001e31c  sub     ecx, 4
0x18001e31f  jmp     loc_18001E464
0x18001e324  cmp     ecx, 22h ; '"'
0x18001e327  jg      loc_18001E43E
0x18001e32d  jz      loc_18001E411
0x18001e333  sub     ecx, 19h
0x18001e336  jnz     loc_18001E443
0x18001e33c  mov     [rsp+268h+var_238], ecx
0x18001e340  xor     edx, edx; Val
0x18001e342  lea     rcx, [rsp+268h+SubKey]; void *
0x18001e347  mov     r8d, 208h; Size
0x18001e34d  call    memset_0
0x18001e352  mov     r9d, 104h; unsigned __int64
0x18001e358  lea     r8, [rsp+268h+SubKey]; wchar_t *
0x18001e35d  lea     rdx, aSettings; "\\Settings"
0x18001e364  lea     rcx, aWindowsupdateu; "WindowsUpdateUXRoot"
0x18001e36b  call    ?GetRedirectedRegistryKeyName@PolicyRegistryHelper@@SAJPEB_W0PEA_W_K@Z; PolicyRegistryHelper::GetRedirectedRegistryKeyName(wchar_t const *,wchar_t const *,wchar_t *,unsigned __int64)
0x18001e370  mov     edi, eax
0x18001e372  test    eax, eax
0x18001e374  jns     short loc_18001E380
0x18001e376  mov     edx, 0BD6h
0x18001e37b  mov     r9d, eax
0x18001e37e  jmp     short loc_18001E3C2
0x18001e380  lea     rax, [rsp+268h+var_238]
0x18001e385  xor     r9d, r9d; unsigned int
0x18001e388  mov     [rsp+268h+var_240], rax; unsigned int *
0x18001e38d  lea     rdx, aAllowmuupdates; "AllowMUUpdateService"
0x18001e394  xor     r8d, r8d; unsigned int
0x18001e397  mov     [rsp+268h+var_248], 1; int
0x18001e39f  lea     rcx, [rsp+268h+SubKey]; lpSubKey
0x18001e3a4  call    ?ReadPolicyDword@PolicyHelpers@@SAJPEB_W0KKKPEAK@Z; PolicyHelpers::ReadPolicyDword(wchar_t const *,wchar_t const *,ulong,ulong,ulong,ulong *)
0x18001e3a9  mov     edi, eax
0x18001e3ab  mov     r9d, eax; char *
0x18001e3ae  add     eax, 7FF8FFFEh
0x18001e3b3  cmp     eax, 1
0x18001e3b6  jbe     short loc_18001E434
0x18001e3b8  test    r9d, r9d
0x18001e3bb  jns     short loc_18001E3F6
0x18001e3bd  mov     edx, 0BE3h; void *
0x18001e3c2  mov     rcx, [rsp+268h]; this
0x18001e3ca  lea     r8, aCW1SSrcClientP_9; "C:\\__w\\1\\s\\src\\Client\\policy\\src"...
0x18001e3d1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e3d6  mov     rcx, [rsp+268h]; this
0x18001e3de  lea     r8, aCW1SSrcClientP_9; "C:\\__w\\1\\s\\src\\Client\\policy\\src"...
0x18001e3e5  mov     r9d, edi; char *
0x18001e3e8  mov     edx, 0BA8h; void *
0x18001e3ed  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e3f2  mov     eax, edi
0x18001e3f4  jmp     short loc_18001E413
0x18001e3f6  mov     eax, [rsp+268h+var_238]
0x18001e3fa  mov     [rbx+18h], eax
0x18001e3fd  mov     dword ptr [rbx+4], 1
0x18001e404  mov     word ptr [rbx+10h], 3
0x18001e40a  mov     dword ptr [rbx+8], 4
0x18001e411  xor     eax, eax
0x18001e413  mov     rcx, [rsp+268h+var_18]
0x18001e41b  xor     rcx, rsp; StackCookie
0x18001e41e  call    __security_check_cookie
0x18001e423  mov     rbx, [rsp+268h+arg_0]
0x18001e42b  add     rsp, 260h
0x18001e432  pop     rdi
0x18001e433  retn
0x18001e434  mov     qword ptr [rbx+4], 0
0x18001e43c  jmp     short loc_18001E411
0x18001e43e  sub     ecx, 23h ; '#'
0x18001e441  jz      short loc_18001E411
0x18001e443  sub     ecx, 1
0x18001e446  jz      short loc_18001E411
0x18001e448  sub     ecx, 1
0x18001e44b  jz      short loc_18001E411
0x18001e44d  sub     ecx, 1
0x18001e450  jz      short loc_18001E411
0x18001e452  sub     ecx, 1
0x18001e455  jz      short loc_18001E411
0x18001e457  sub     ecx, 1
0x18001e45a  jz      short loc_18001E411
0x18001e45c  sub     ecx, 1
0x18001e45f  jz      short loc_18001E411
0x18001e461  sub     ecx, 1
0x18001e464  jz      short loc_18001E411
0x18001e466  cmp     ecx, 1
0x18001e469  jz      short loc_18001E411
0x18001e46b  mov     ebx, 80070057h
0x18001e470  mov     edx, 0B9Fh
0x18001e475  jmp     loc_18001E28D
```
