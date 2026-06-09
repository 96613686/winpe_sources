# CSCMProfileCache::CProfileCacheEntry::LoadAndCreate(void *,ushort *,CSCMProfileCache::CProfileCacheEntry * *)

- ea: `0x1800871cc`
- end: `0x1800873cd`
- name: `?LoadAndCreate@CProfileCacheEntry@CSCMProfileCache@@SAJPEAXPEAGPEAPEAV12@@Z`
- size: `513`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, unsigned __int16 *, struct CSCMProfileCache::CProfileCacheEntry **)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800861e8`

## callees

- `0x180034260`
- `0x1800710a4`
- `0x18008172c`
- `0x180085cf4`
- `0x1800871cc`

## import_xrefs

- `RPCRT4!UuidCreate` at `0x18008723c`
- `RPCRT4!UuidCreate` at `0x18008723c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180087273`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180087304`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180087273`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180087304`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800871f9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800871f9`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x180087263`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x180087263`
- `profapi!__imp_CreateEnvBlock` at `0x180087357`
- `profapi!__imp_CreateEnvBlock` at `0x180087357`
- `USERENV!LoadUserProfileW` at `0x1800872f4`
- `USERENV!LoadUserProfileW` at `0x1800872f4`

## string_xrefs

- `0x1800873a4`: `onecore\com\combase\rpcss\olescm\profiles.cxx`
- `0x18008739d`: `CSCMProfileCache::CProfileCacheEntry::LoadAndCreate`

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
        if ( !dword_1801574B8
          && (!gfEnableTracing || !(unsigned __int8)IsWppLevelEnabled((unsigned int)dword_1801574B8)) )
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
        if ( !dword_1801574B8 && (!gfEnableTracing || !(unsigned __int8)IsWppLevelEnabled(0)) )
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
      if ( !dword_1801574B8 && (!gfEnableTracing || !(unsigned __int8)IsWppLevelEnabled(0)) )
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
0x1800871cc  push    rbx
0x1800871ce  push    rbp
0x1800871cf  push    rsi
0x1800871d0  push    rdi
0x1800871d1  push    r14
0x1800871d3  sub     rsp, 70h
0x1800871d7  mov     r14, rdx
0x1800871da  mov     qword ptr [r8], 0
0x1800871e1  xor     edx, edx; dwFlags
0x1800871e3  mov     rsi, r8
0x1800871e6  mov     rbp, rcx
0x1800871e9  mov     ebx, 8007000Eh
0x1800871ee  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x1800871f5  lea     r8d, [rdx+48h]; dwBytes
0x1800871f9  call    cs:__imp_HeapAlloc
0x180087200  nop     dword ptr [rax+rax+00h]
0x180087205  mov     rdi, rax
0x180087208  test    rax, rax
0x18008720b  jz      loc_1800873BF
0x180087211  lea     rcx, [rax+38h]; Uuid
0x180087215  mov     dword ptr [rax+10h], 1
0x18008721c  mov     qword ptr [rax+18h], 0
0x180087224  mov     qword ptr [rax+20h], 0
0x18008722c  mov     qword ptr [rax+28h], 0
0x180087234  mov     qword ptr [rax+30h], 0
0x18008723c  call    cs:__imp_UuidCreate
0x180087243  nop     dword ptr [rax+rax+00h]
0x180087248  mov     rcx, rbp; TokenHandle
0x18008724b  call    ?GetUserSid@@YAPEAXPEAX@Z; GetUserSid(void *)
0x180087250  lea     rbx, [rdi+20h]
0x180087254  mov     [rdi+30h], rax
0x180087258  mov     r8, rbx; DuplicateTokenHandle
0x18008725b  mov     edx, 2; ImpersonationLevel
0x180087260  mov     rcx, rbp; ExistingTokenHandle
0x180087263  call    cs:__imp_DuplicateToken
0x18008726a  nop     dword ptr [rax+rax+00h]
0x18008726f  test    eax, eax
0x180087271  jnz     short loc_1800872BE
0x180087273  call    cs:__imp_GetLastError
0x18008727a  nop     dword ptr [rax+rax+00h]
0x18008727f  mov     ebx, eax
0x180087281  test    eax, eax
0x180087283  jle     short loc_18008728E
0x180087285  movzx   ebx, ax
0x180087288  or      ebx, 80070000h
0x18008728e  mov     eax, cs:dword_1801574B8
0x180087294  test    eax, eax
0x180087296  jnz     short loc_1800872B3
0x180087298  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x18008729e  jz      loc_1800873B0
0x1800872a4  xor     ecx, ecx
0x1800872a6  call    IsWppLevelEnabled
0x1800872ab  test    al, al
0x1800872ad  jz      loc_1800873B0
0x1800872b3  mov     r8d, 14Ah
0x1800872b9  jmp     loc_18008738A
0x1800872be  xorps   xmm0, xmm0
0x1800872c1  lea     rdx, [rsp+98h+ProfileInfo]; lpProfileInfo
0x1800872c6  movups  xmmword ptr [rsp+98h+ProfileInfo.dwSize], xmm0
0x1800872cb  xor     eax, eax
0x1800872cd  mov     [rsp+98h+ProfileInfo.dwSize], 38h ; '8'
0x1800872d5  mov     [rsp+98h+ProfileInfo.dwFlags], 1
0x1800872dd  mov     [rsp+98h+ProfileInfo.lpUserName], r14
0x1800872e2  movups  xmmword ptr [rsp+98h+ProfileInfo.lpProfilePath], xmm0
0x1800872e7  mov     [rsp+98h+ProfileInfo.hProfile], rax
0x1800872ec  movups  xmmword ptr [rsp+98h+ProfileInfo.lpServerName], xmm0
0x1800872f1  mov     rcx, [rbx]; hToken
0x1800872f4  call    cs:__imp_LoadUserProfileW
0x1800872fb  nop     dword ptr [rax+rax+00h]
0x180087300  test    eax, eax
0x180087302  jnz     short loc_180087344
0x180087304  call    cs:__imp_GetLastError
0x18008730b  nop     dword ptr [rax+rax+00h]
0x180087310  mov     ebx, eax
0x180087312  test    eax, eax
0x180087314  jle     short loc_18008731F
0x180087316  movzx   ebx, ax
0x180087319  or      ebx, 80070000h
0x18008731f  mov     eax, cs:dword_1801574B8
0x180087325  test    eax, eax
0x180087327  jnz     short loc_18008733C
0x180087329  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x18008732f  jz      short loc_1800873B0
0x180087331  xor     ecx, ecx
0x180087333  call    IsWppLevelEnabled
0x180087338  test    al, al
0x18008733a  jz      short loc_1800873B0
0x18008733c  mov     r8d, 158h
0x180087342  jmp     short loc_18008738A
0x180087344  mov     rax, [rsp+98h+ProfileInfo.hProfile]
0x180087349  lea     rcx, [rdi+28h]
0x18008734d  mov     rdx, [rbx]
0x180087350  xor     r8d, r8d
0x180087353  mov     [rdi+18h], rax
0x180087357  call    cs:__imp_CreateEnvBlock
0x18008735e  nop     dword ptr [rax+rax+00h]
0x180087363  mov     ebx, eax
0x180087365  test    eax, eax
0x180087367  jns     short loc_1800873BA
0x180087369  mov     ecx, cs:dword_1801574B8
0x18008736f  test    ecx, ecx
0x180087371  jnz     short loc_180087384
0x180087373  cmp     cs:?gfEnableTracing@@3HA, ecx; int gfEnableTracing
0x180087379  jz      short loc_1800873B0
0x18008737b  call    IsWppLevelEnabled
0x180087380  test    al, al
0x180087382  jz      short loc_1800873B0
0x180087384  mov     r8d, 165h
0x18008738a  lea     rax, aHresult; "%!HRESULT!"
0x180087391  mov     [rsp+98h+var_70], ebx
0x180087395  xor     r9d, r9d
0x180087398  mov     [rsp+98h+var_78], rax
0x18008739d  lea     rdx, aCscmprofilecac_4; "CSCMProfileCache::CProfileCacheEntry::L"...
0x1800873a4  lea     rcx, aOnecoreComComb_110; "onecore\\com\\combase\\rpcss\\olescm\\p"...
0x1800873ab  call    ??$ComTraceMessageT@J@@YAXPEBD0HW4TraceLevel@@PEBGJ@Z; ComTraceMessageT<long>(char const *,char const *,int,TraceLevel,ushort const *,long)
0x1800873b0  mov     rcx, rdi; this
0x1800873b3  call    ??_GCProfileCacheEntry@CSCMProfileCache@@QEAAPEAXI@Z; CSCMProfileCache::CProfileCacheEntry::`scalar deleting destructor'(uint)
0x1800873b8  jmp     short loc_1800873BF
0x1800873ba  xor     ebx, ebx
0x1800873bc  mov     [rsi], rdi
0x1800873bf  mov     eax, ebx
0x1800873c1  add     rsp, 70h
0x1800873c5  pop     r14
0x1800873c7  pop     rdi
0x1800873c8  pop     rsi
0x1800873c9  pop     rbp
0x1800873ca  pop     rbx
0x1800873cb  retn
```
