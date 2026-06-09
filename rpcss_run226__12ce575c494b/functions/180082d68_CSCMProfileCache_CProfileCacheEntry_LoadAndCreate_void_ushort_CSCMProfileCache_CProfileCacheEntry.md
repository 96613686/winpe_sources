# CSCMProfileCache::CProfileCacheEntry::LoadAndCreate(void *,ushort *,CSCMProfileCache::CProfileCacheEntry * *)

- ea: `0x180082d68`
- end: `0x180082f3e`
- name: `?LoadAndCreate@CProfileCacheEntry@CSCMProfileCache@@SAJPEAXPEAGPEAPEAV12@@Z`
- size: `470`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, unsigned __int16 *, struct CSCMProfileCache::CProfileCacheEntry **)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180081d3c`

## callees

- `0x180034540`
- `0x18006cb10`
- `0x18007e3d4`
- `0x1800818cc`
- `0x180082d68`

## import_xrefs

- `RPCRT4!UuidCreate` at `0x180082dd2`
- `RPCRT4!UuidCreate` at `0x180082dd2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180082dfd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180082e82`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180082dfd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180082e82`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180082d95`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180082d95`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x180082df3`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x180082df3`
- `profapi!__imp_CreateEnvBlock` at `0x180082ecf`
- `profapi!__imp_CreateEnvBlock` at `0x180082ecf`
- `USERENV!LoadUserProfileW` at `0x180082e78`
- `USERENV!LoadUserProfileW` at `0x180082e78`

## string_xrefs

- `0x180082f16`: `onecore\com\combase\rpcss\olescm\profiles.cxx`
- `0x180082f0f`: `CSCMProfileCache::CProfileCacheEntry::LoadAndCreate`

## pseudocode

```c
__int64 __fastcall CSCMProfileCache::CProfileCacheEntry::LoadAndCreate(
        HANDLE TokenHandle,
        unsigned __int16 *a2,
        struct CSCMProfileCache::CProfileCacheEntry **a3)
{
  unsigned int EnvBlock; // ebx
  char *v7; // rax
  char *v8; // rdi
  HANDLE *v9; // rbx
  signed int v10; // eax
  unsigned int v11; // edx
  int v12; // r8d
  signed int LastError; // eax
  HANDLE v14; // rdx
  _PROFILEINFOW ProfileInfo; // [rsp+30h] [rbp-68h] BYREF

  *a3 = 0;
  EnvBlock = -2147024882;
  v7 = (char *)HeapAlloc(g_hHeap, 0, 0x48u);
  v8 = v7;
  if ( v7 )
  {
    *((_DWORD *)v7 + 4) = 1;
    *((_QWORD *)v7 + 3) = 0;
    *((_QWORD *)v7 + 4) = 0;
    *((_QWORD *)v7 + 5) = 0;
    *((_QWORD *)v7 + 6) = 0;
    UuidCreate((UUID *)(v7 + 56));
    v9 = (HANDLE *)(v8 + 32);
    *((_QWORD *)v8 + 6) = GetUserSid(TokenHandle);
    if ( DuplicateToken(TokenHandle, SecurityImpersonation, (PHANDLE)v8 + 4) )
    {
      ProfileInfo.dwSize = 56;
      ProfileInfo.dwFlags = 1;
      ProfileInfo.lpUserName = a2;
      memset(&ProfileInfo.lpProfilePath, 0, 40);
      if ( LoadUserProfileW(*v9, &ProfileInfo) )
      {
        v14 = *v9;
        *((_QWORD *)v8 + 3) = ProfileInfo.hProfile;
        EnvBlock = CreateEnvBlock(v8 + 40, v14, 0);
        if ( (EnvBlock & 0x80000000) == 0 )
        {
          EnvBlock = 0;
          *a3 = (struct CSCMProfileCache::CProfileCacheEntry *)v8;
          return EnvBlock;
        }
        if ( !dword_18014E4B8
          && (!gfEnableTracing || !(unsigned __int8)IsWppLevelEnabled((unsigned int)dword_18014E4B8)) )
        {
          goto LABEL_22;
        }
        v12 = 357;
      }
      else
      {
        LastError = GetLastError();
        EnvBlock = LastError;
        if ( LastError > 0 )
          EnvBlock = (unsigned __int16)LastError | 0x80070000;
        if ( !dword_18014E4B8 && (!gfEnableTracing || !(unsigned __int8)IsWppLevelEnabled(0)) )
          goto LABEL_22;
        v12 = 344;
      }
    }
    else
    {
      v10 = GetLastError();
      EnvBlock = v10;
      if ( v10 > 0 )
        EnvBlock = (unsigned __int16)v10 | 0x80070000;
      if ( !dword_18014E4B8 && (!gfEnableTracing || !(unsigned __int8)IsWppLevelEnabled(0)) )
        goto LABEL_22;
      v12 = 330;
    }
    ComTraceMessageT<long>(
      (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\profiles.cxx",
      (unsigned int)"CSCMProfileCache::CProfileCacheEntry::LoadAndCreate",
      v12,
      0,
      (__int64)L"%!HRESULT!",
      EnvBlock);
LABEL_22:
    CSCMProfileCache::CProfileCacheEntry::`scalar deleting destructor'((CSCMProfileCache::CProfileCacheEntry *)v8, v11);
  }
  return EnvBlock;
}

```

## disassembly

```asm
0x180082d68  push    rbx
0x180082d6a  push    rbp
0x180082d6b  push    rsi
0x180082d6c  push    rdi
0x180082d6d  push    r14
0x180082d6f  sub     rsp, 70h
0x180082d73  mov     r14, rdx
0x180082d76  mov     qword ptr [r8], 0
0x180082d7d  xor     edx, edx; dwFlags
0x180082d7f  mov     rsi, r8
0x180082d82  mov     rbp, rcx
0x180082d85  mov     ebx, 8007000Eh
0x180082d8a  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x180082d91  lea     r8d, [rdx+48h]; dwBytes
0x180082d95  call    cs:__imp_HeapAlloc
0x180082d9b  mov     rdi, rax
0x180082d9e  test    rax, rax
0x180082da1  jz      loc_180082F31
0x180082da7  lea     rcx, [rax+38h]; Uuid
0x180082dab  mov     dword ptr [rax+10h], 1
0x180082db2  mov     qword ptr [rax+18h], 0
0x180082dba  mov     qword ptr [rax+20h], 0
0x180082dc2  mov     qword ptr [rax+28h], 0
0x180082dca  mov     qword ptr [rax+30h], 0
0x180082dd2  call    cs:__imp_UuidCreate
0x180082dd8  mov     rcx, rbp; TokenHandle
0x180082ddb  call    ?GetUserSid@@YAPEAXPEAX@Z; GetUserSid(void *)
0x180082de0  lea     rbx, [rdi+20h]
0x180082de4  mov     [rdi+30h], rax
0x180082de8  mov     r8, rbx; DuplicateTokenHandle
0x180082deb  mov     edx, 2; ImpersonationLevel
0x180082df0  mov     rcx, rbp; ExistingTokenHandle
0x180082df3  call    cs:__imp_DuplicateToken
0x180082df9  test    eax, eax
0x180082dfb  jnz     short loc_180082E42
0x180082dfd  call    cs:__imp_GetLastError
0x180082e03  mov     ebx, eax
0x180082e05  test    eax, eax
0x180082e07  jle     short loc_180082E12
0x180082e09  movzx   ebx, ax
0x180082e0c  or      ebx, 80070000h
0x180082e12  mov     eax, cs:dword_18014E4B8
0x180082e18  test    eax, eax
0x180082e1a  jnz     short loc_180082E37
0x180082e1c  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x180082e22  jz      loc_180082F22
0x180082e28  xor     ecx, ecx
0x180082e2a  call    IsWppLevelEnabled
0x180082e2f  test    al, al
0x180082e31  jz      loc_180082F22
0x180082e37  mov     r8d, 14Ah
0x180082e3d  jmp     loc_180082EFC
0x180082e42  xorps   xmm0, xmm0
0x180082e45  lea     rdx, [rsp+98h+ProfileInfo]; lpProfileInfo
0x180082e4a  movups  xmmword ptr [rsp+98h+ProfileInfo.dwSize], xmm0
0x180082e4f  xor     eax, eax
0x180082e51  mov     [rsp+98h+ProfileInfo.dwSize], 38h ; '8'
0x180082e59  mov     [rsp+98h+ProfileInfo.dwFlags], 1
0x180082e61  mov     [rsp+98h+ProfileInfo.lpUserName], r14
0x180082e66  movups  xmmword ptr [rsp+98h+ProfileInfo.lpProfilePath], xmm0
0x180082e6b  mov     [rsp+98h+ProfileInfo.hProfile], rax
0x180082e70  movups  xmmword ptr [rsp+98h+ProfileInfo.lpServerName], xmm0
0x180082e75  mov     rcx, [rbx]; hToken
0x180082e78  call    cs:__imp_LoadUserProfileW
0x180082e7e  test    eax, eax
0x180082e80  jnz     short loc_180082EBC
0x180082e82  call    cs:__imp_GetLastError
0x180082e88  mov     ebx, eax
0x180082e8a  test    eax, eax
0x180082e8c  jle     short loc_180082E97
0x180082e8e  movzx   ebx, ax
0x180082e91  or      ebx, 80070000h
0x180082e97  mov     eax, cs:dword_18014E4B8
0x180082e9d  test    eax, eax
0x180082e9f  jnz     short loc_180082EB4
0x180082ea1  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x180082ea7  jz      short loc_180082F22
0x180082ea9  xor     ecx, ecx
0x180082eab  call    IsWppLevelEnabled
0x180082eb0  test    al, al
0x180082eb2  jz      short loc_180082F22
0x180082eb4  mov     r8d, 158h
0x180082eba  jmp     short loc_180082EFC
0x180082ebc  mov     rax, [rsp+98h+ProfileInfo.hProfile]
0x180082ec1  lea     rcx, [rdi+28h]
0x180082ec5  mov     rdx, [rbx]
0x180082ec8  xor     r8d, r8d
0x180082ecb  mov     [rdi+18h], rax
0x180082ecf  call    cs:__imp_CreateEnvBlock
0x180082ed5  mov     ebx, eax
0x180082ed7  test    eax, eax
0x180082ed9  jns     short loc_180082F2C
0x180082edb  mov     ecx, cs:dword_18014E4B8
0x180082ee1  test    ecx, ecx
0x180082ee3  jnz     short loc_180082EF6
0x180082ee5  cmp     cs:?gfEnableTracing@@3HA, ecx; int gfEnableTracing
0x180082eeb  jz      short loc_180082F22
0x180082eed  call    IsWppLevelEnabled
0x180082ef2  test    al, al
0x180082ef4  jz      short loc_180082F22
0x180082ef6  mov     r8d, 165h
0x180082efc  lea     rax, aHresult; "%!HRESULT!"
0x180082f03  mov     [rsp+98h+var_70], ebx
0x180082f07  xor     r9d, r9d
0x180082f0a  mov     [rsp+98h+var_78], rax
0x180082f0f  lea     rdx, aCscmprofilecac_4; "CSCMProfileCache::CProfileCacheEntry::L"...
0x180082f16  lea     rcx, aOnecoreComComb_110; "onecore\\com\\combase\\rpcss\\olescm\\p"...
0x180082f1d  call    ??$ComTraceMessageT@J@@YAXPEBD0HW4TraceLevel@@PEBGJ@Z; ComTraceMessageT<long>(char const *,char const *,int,TraceLevel,ushort const *,long)
0x180082f22  mov     rcx, rdi; this
0x180082f25  call    ??_GCProfileCacheEntry@CSCMProfileCache@@QEAAPEAXI@Z; CSCMProfileCache::CProfileCacheEntry::`scalar deleting destructor'(uint)
0x180082f2a  jmp     short loc_180082F31
0x180082f2c  xor     ebx, ebx
0x180082f2e  mov     [rsi], rdi
0x180082f31  mov     eax, ebx
0x180082f33  add     rsp, 70h
0x180082f37  pop     r14
0x180082f39  pop     rdi
0x180082f3a  pop     rsi
0x180082f3b  pop     rbp
0x180082f3c  pop     rbx
0x180082f3d  retn
```
