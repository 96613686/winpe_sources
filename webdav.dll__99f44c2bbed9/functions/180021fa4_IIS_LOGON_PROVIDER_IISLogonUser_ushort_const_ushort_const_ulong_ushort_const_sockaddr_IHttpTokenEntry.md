# IIS_LOGON_PROVIDER::IISLogonUser(ushort const *,ushort const *,ulong,ushort const *,sockaddr *,IHttpTokenEntry * *)

- ea: `0x180021fa4`
- end: `0x1800222fe`
- name: `?IISLogonUser@IIS_LOGON_PROVIDER@@QEAAJPEBG0K0PEAUsockaddr@@PEAPEAVIHttpTokenEntry@@@Z`
- size: `858`
- prototype: `__int64 __fastcall(IIS_LOGON_PROVIDER *__hidden this, const unsigned __int16 *, const unsigned __int16 *, unsigned int, const unsigned __int16 *, struct sockaddr *, struct IHttpTokenEntry **)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180019bc4`

## callees

- `0x1800011d4`
- `0x1800213d8`
- `0x1800214a4`
- `0x180021fa4`
- `0x1800224c2`
- `0x180022520`
- `0x180023010`

## import_xrefs

- `msvcrt!wcschr` at `0x1800220a8`
- `msvcrt!wcschr` at `0x1800220a8`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002224c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002224c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022149`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022168`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022256`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022149`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022168`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022256`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800222af`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800222af`
- `iisutil!??0STRU@@QEAA@XZ` at `0x1800221d0`
- `iisutil!??0STRU@@QEAA@XZ` at `0x1800221dd`
- `iisutil!??0STRU@@QEAA@XZ` at `0x1800221d0`
- `iisutil!??0STRU@@QEAA@XZ` at `0x1800221dd`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800222c9`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800222d3`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800222c9`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800222d3`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180022021`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180022046`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180022021`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180022046`
- `SspiCli!LsaFreeReturnBuffer` at `0x1800222bf`
- `SspiCli!LsaFreeReturnBuffer` at `0x1800222bf`
- `ADVAPI32!LogonUserExW` at `0x18002213f`
- `ADVAPI32!LogonUserExW` at `0x18002213f`

## pseudocode

```c
__int64 __fastcall IIS_LOGON_PROVIDER::IISLogonUser(
        IIS_LOGON_PROVIDER *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned int a4,
        const unsigned __int16 *a5,
        struct sockaddr *a6,
        struct IHttpTokenEntry **a7)
{
  const unsigned __int16 *v11; // r8
  int CacheKey; // ebx
  int v13; // esi
  const WCHAR *v14; // rdx
  unsigned int v15; // edi
  unsigned int i; // ebx
  signed int v17; // eax
  signed int v18; // eax
  _QWORD *v19; // rax
  struct IHttpTokenEntry *v20; // rdi
  HANDLE v21; // rcx
  int v22; // eax
  signed int LastError; // eax
  DWORD ReturnLength; // [rsp+50h] [rbp-B0h] BYREF
  DWORD pdwProfileLength; // [rsp+54h] [rbp-ACh] BYREF
  HANDLE TokenHandle; // [rsp+58h] [rbp-A8h] BYREF
  LPCWSTR lpszDomain; // [rsp+60h] [rbp-A0h]
  const WCHAR *v29; // [rsp+68h] [rbp-98h]
  PVOID Buffer; // [rsp+70h] [rbp-90h] BYREF
  struct IHttpTokenEntry **v31; // [rsp+78h] [rbp-88h]
  _BYTE v32[32]; // [rsp+80h] [rbp-80h] BYREF
  const WCHAR *v33; // [rsp+A0h] [rbp-60h]
  _BYTE v34[32]; // [rsp+B8h] [rbp-48h] BYREF
  wchar_t *Str; // [rsp+D8h] [rbp-28h]
  unsigned __int16 v36[256]; // [rsp+F0h] [rbp-10h] BYREF
  unsigned __int16 v37[256]; // [rsp+2F0h] [rbp+1F0h] BYREF

  v31 = a7;
  TokenHandle = 0;
  Buffer = 0;
  pdwProfileLength = 0;
  v29 = 0;
  memset_0(v36, 0, sizeof(v36));
  STRU::STRU((STRU *)v34, v36, 0x100u);
  memset_0(v37, 0, sizeof(v37));
  STRU::STRU((STRU *)v32, v37, 0x100u);
  ReturnLength = 0;
  if ( !a7 )
  {
    CacheKey = -2147024809;
    goto LABEL_41;
  }
  CacheKey = IIS_LOGON_PROVIDER::DetermineUserAndDomain(
               this,
               a2,
               v11,
               (struct STRU *)v34,
               (struct STRU *)v32,
               (int *)&ReturnLength);
  if ( CacheKey >= 0 )
  {
    v13 = 2;
    if ( !ReturnLength )
    {
      v14 = v33;
      if ( !*v33 )
      {
LABEL_11:
        v15 = 1;
        lpszDomain = (LPCWSTR)((unsigned __int64)v14 & -(__int64)(*v14 != 0));
        goto LABEL_12;
      }
      if ( wcschr(Str, 0x40u) )
      {
        v15 = 2;
        if ( *((_DWORD *)this + 641) )
        {
          lpszDomain = v33;
          v29 = 0;
        }
        else
        {
          v29 = v33;
          lpszDomain = 0;
        }
LABEL_12:
        for ( i = 0; i < v15; ++i )
        {
          if ( LogonUserExW(Str, (&lpszDomain)[i], a3, a4, 0, &TokenHandle, 0, &Buffer, &pdwProfileLength, 0) )
          {
            v19 = operator new(0x108u);
            v20 = (struct IHttpTokenEntry *)v19;
            if ( !v19 )
            {
              CacheKey = -2147024888;
              goto LABEL_37;
            }
            v19[2] = 0;
            *v19 = &TOKEN_ENTRY::`vftable';
            v19[3] = 0;
            v19[15] = &TOKEN_KEY::`vftable';
            *((_DWORD *)v19 + 3) = 1;
            *((_DWORD *)v19 + 29) = 0;
            STRU::STRU((STRU *)(v19 + 16));
            STRU::STRU((struct IHttpTokenEntry *)((char *)v20 + 184));
            *((_DWORD *)v20 + 65) &= 0xFFFFFFFC;
            *((_DWORD *)v20 + 62) = 0;
            *((_DWORD *)v20 + 63) = 0;
            *((_DWORD *)v20 + 64) = 2;
            *((_DWORD *)v20 + 2) = 1313558356;
            v21 = TokenHandle;
            if ( a4 == 3 || (v22 = 0, a4 == 8) )
              v22 = 1;
            if ( v22 )
            {
              *((_QWORD *)v20 + 2) = TokenHandle;
              v13 = 1;
            }
            else
            {
              *((_QWORD *)v20 + 3) = TokenHandle;
            }
            *((_DWORD *)v20 + 65) |= v13;
            ReturnLength = 84;
            if ( GetTokenInformation(v21, TokenUser, (char *)v20 + 32, 0x54u, &ReturnLength) )
            {
              CacheKey = TOKEN_KEY::CreateCacheKey((struct IHttpTokenEntry *)((char *)v20 + 120), a2, a3, a4);
            }
            else
            {
              LastError = GetLastError();
              CacheKey = LastError;
              if ( LastError > 0 )
                CacheKey = (unsigned __int16)LastError | 0x80070000;
            }
            if ( CacheKey < 0 )
            {
              (*(void (__fastcall **)(struct IHttpTokenEntry *))(*(_QWORD *)v20 + 16LL))(v20);
              goto LABEL_37;
            }
            *v31 = v20;
            goto LABEL_39;
          }
          v17 = GetLastError();
          if ( v17 > 0 )
            v17 = (unsigned __int16)v17 | 0x80070000;
          if ( v17 != -2147023570 )
            break;
        }
        v18 = GetLastError();
        CacheKey = v18;
        if ( v18 > 0 )
          CacheKey = (unsigned __int16)v18 | 0x80070000;
        if ( CacheKey >= 0 )
          goto LABEL_39;
        goto LABEL_37;
      }
    }
    v14 = v33;
    goto LABEL_11;
  }
LABEL_37:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
LABEL_39:
  if ( Buffer )
    LsaFreeReturnBuffer(Buffer);
LABEL_41:
  STRU::~STRU((STRU *)v32);
  STRU::~STRU((STRU *)v34);
  return (unsigned int)CacheKey;
}

```

## disassembly

```asm
0x180021fa4  push    rbp
0x180021fa6  push    rbx
0x180021fa7  push    rsi
0x180021fa8  push    rdi
0x180021fa9  push    r12
0x180021fab  push    r13
0x180021fad  push    r14
0x180021faf  push    r15
0x180021fb1  lea     rbp, [rsp-408h]
0x180021fb9  sub     rsp, 508h
0x180021fc0  mov     rax, cs:__security_cookie
0x180021fc7  xor     rax, rsp
0x180021fca  mov     [rbp+440h+var_50], rax
0x180021fd1  mov     rbx, [rbp+440h+arg_30]
0x180021fd8  xor     eax, eax
0x180021fda  mov     r13, r8
0x180021fdd  mov     [rsp+540h+var_4C8], rbx
0x180021fe2  mov     r12, rdx
0x180021fe5  mov     [rsp+540h+TokenHandle], rax
0x180021fea  mov     r14, rcx
0x180021fed  mov     [rsp+540h+Buffer], rax
0x180021ff2  mov     esi, 200h
0x180021ff7  mov     [rsp+540h+var_4EC], eax
0x180021ffb  mov     r8d, esi; Size
0x180021ffe  mov     [rsp+540h+var_4D8], rax
0x180022003  xor     edx, edx; Val
0x180022005  lea     rcx, [rbp+440h+var_450]; void *
0x180022009  mov     r15d, r9d
0x18002200c  call    memset_0
0x180022011  mov     edi, 100h
0x180022016  lea     rdx, [rbp+440h+var_450]
0x18002201a  mov     r8d, edi
0x18002201d  lea     rcx, [rbp+440h+var_488]
0x180022021  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180022027  mov     r8d, esi; Size
0x18002202a  lea     rcx, [rbp+440h+var_250]; void *
0x180022031  xor     edx, edx; Val
0x180022033  call    memset_0
0x180022038  mov     r8d, edi
0x18002203b  lea     rdx, [rbp+440h+var_250]
0x180022042  lea     rcx, [rbp+440h+var_4C0]
0x180022046  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18002204c  xor     edi, edi
0x18002204e  mov     [rsp+540h+ReturnLength], edi
0x180022052  test    rbx, rbx
0x180022055  jnz     short loc_180022061
0x180022057  mov     ebx, 80070057h
0x18002205c  jmp     loc_1800222C5
0x180022061  lea     rax, [rsp+540h+ReturnLength]
0x180022066  mov     rdx, r12; unsigned __int16 *
0x180022069  mov     [rsp+540h+phToken], rax; int *
0x18002206e  lea     r9, [rbp+440h+var_488]; struct STRU *
0x180022072  lea     rax, [rbp+440h+var_4C0]
0x180022076  mov     rcx, r14; this
0x180022079  mov     qword ptr [rsp+540h+dwLogonProvider], rax; struct STRU *
0x18002207e  call    ?DetermineUserAndDomain@IIS_LOGON_PROVIDER@@AEAAJPEBG0PEAVSTRU@@1PEAH@Z; IIS_LOGON_PROVIDER::DetermineUserAndDomain(ushort const *,ushort const *,STRU *,STRU *,int *)
0x180022083  mov     ebx, eax
0x180022085  test    eax, eax
0x180022087  js      loc_1800222A5
0x18002208d  mov     esi, 2
0x180022092  cmp     [rsp+540h+ReturnLength], edi
0x180022096  jnz     short loc_1800220E1
0x180022098  mov     rdx, [rbp+440h+var_4A0]
0x18002209c  cmp     [rdx], di
0x18002209f  jz      short loc_1800220E5
0x1800220a1  mov     rcx, [rbp+440h+Str]; Str
0x1800220a5  lea     edx, [rsi+3Eh]; Ch
0x1800220a8  call    cs:__imp_wcschr
0x1800220ae  test    rax, rax
0x1800220b1  jz      short loc_1800220E1
0x1800220b3  cmp     dword ptr [r14+0A04h], 0
0x1800220bb  mov     edi, esi
0x1800220bd  mov     rax, [rbp+440h+var_4A0]
0x1800220c1  jz      short loc_1800220D2
0x1800220c3  xor     r14d, r14d
0x1800220c6  mov     [rsp+540h+lpszDomain], rax
0x1800220cb  mov     [rsp+540h+var_4D8], r14
0x1800220d0  jmp     short loc_1800220FE
0x1800220d2  xor     r14d, r14d
0x1800220d5  mov     [rsp+540h+var_4D8], rax
0x1800220da  mov     [rsp+540h+lpszDomain], r14
0x1800220df  jmp     short loc_1800220FE
0x1800220e1  mov     rdx, [rbp+440h+var_4A0]
0x1800220e5  movzx   eax, word ptr [rdx]
0x1800220e8  mov     edi, 1
0x1800220ed  neg     ax
0x1800220f0  sbb     rcx, rcx
0x1800220f3  and     rcx, rdx
0x1800220f6  mov     [rsp+540h+lpszDomain], rcx
0x1800220fb  xor     r14d, r14d
0x1800220fe  mov     ebx, r14d
0x180022101  mov     rcx, [rbp+440h+Str]; lpszUsername
0x180022105  lea     rax, [rsp+540h+var_4EC]
0x18002210a  mov     [rsp+540h+pQuotaLimits], r14; pQuotaLimits
0x18002210f  mov     r9d, r15d; dwLogonType
0x180022112  mov     [rsp+540h+pdwProfileLength], rax; pdwProfileLength
0x180022117  mov     r8, r13; lpszPassword
0x18002211a  lea     rax, [rsp+540h+Buffer]
0x18002211f  mov     edx, ebx
0x180022121  mov     [rsp+540h+ppProfileBuffer], rax; ppProfileBuffer
0x180022126  lea     rax, [rsp+540h+TokenHandle]
0x18002212b  mov     [rsp+540h+ppLogonSid], r14; ppLogonSid
0x180022130  mov     [rsp+540h+phToken], rax; phToken
0x180022135  mov     rdx, [rsp+rdx*8+540h+lpszDomain]; lpszDomain
0x18002213a  mov     [rsp+540h+dwLogonProvider], r14d; dwLogonProvider
0x18002213f  call    cs:__imp_LogonUserExW
0x180022145  test    eax, eax
0x180022147  jnz     short loc_18002218A
0x180022149  call    cs:__imp_GetLastError
0x18002214f  test    eax, eax
0x180022151  jle     short loc_18002215B
0x180022153  movzx   eax, ax
0x180022156  or      eax, 80070000h
0x18002215b  cmp     eax, 8007052Eh
0x180022160  jnz     short loc_180022168
0x180022162  inc     ebx
0x180022164  cmp     ebx, edi
0x180022166  jb      short loc_180022101
0x180022168  call    cs:__imp_GetLastError
0x18002216e  mov     ebx, eax
0x180022170  test    eax, eax
0x180022172  jle     short loc_18002217D
0x180022174  movzx   ebx, ax
0x180022177  or      ebx, 80070000h
0x18002217d  test    ebx, ebx
0x18002217f  jns     loc_1800222B5
0x180022185  jmp     loc_1800222A5
0x18002218a  mov     ecx, 108h; Size
0x18002218f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180022194  mov     rdi, rax
0x180022197  test    rax, rax
0x18002219a  jz      loc_1800222A0
0x1800221a0  lea     rax, ??_7TOKEN_ENTRY@@6B@; const TOKEN_ENTRY::`vftable'
0x1800221a7  mov     [rdi+10h], r14
0x1800221ab  mov     [rdi], rax
0x1800221ae  lea     rcx, [rdi+80h]
0x1800221b5  lea     rax, ??_7TOKEN_KEY@@6B@; const TOKEN_KEY::`vftable'
0x1800221bc  mov     [rdi+18h], r14
0x1800221c0  mov     ebx, 1
0x1800221c5  mov     [rdi+78h], rax
0x1800221c9  mov     [rdi+0Ch], ebx
0x1800221cc  mov     [rdi+74h], r14d
0x1800221d0  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x1800221d6  lea     rcx, [rdi+0B8h]
0x1800221dd  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x1800221e3  and     dword ptr [rdi+104h], 0FFFFFFFCh
0x1800221ea  mov     [rdi+0F8h], r14d
0x1800221f1  mov     [rdi+0FCh], r14d
0x1800221f8  mov     [rdi+100h], esi
0x1800221fe  mov     dword ptr [rdi+8], 4E4B4F54h
0x180022205  mov     rcx, [rsp+540h+TokenHandle]; TokenHandle
0x18002220a  cmp     r15d, 3
0x18002220e  jz      short loc_180022219
0x180022210  mov     eax, r14d
0x180022213  cmp     r15d, 8
0x180022217  jnz     short loc_18002221B
0x180022219  mov     eax, ebx
0x18002221b  test    eax, eax
0x18002221d  jz      short loc_180022227
0x18002221f  mov     [rdi+10h], rcx
0x180022223  mov     esi, ebx
0x180022225  jmp     short loc_18002222B
0x180022227  mov     [rdi+18h], rcx
0x18002222b  or      [rdi+104h], esi
0x180022231  lea     rax, [rsp+540h+ReturnLength]
0x180022236  mov     r9d, 54h ; 'T'; TokenInformationLength
0x18002223c  mov     qword ptr [rsp+540h+dwLogonProvider], rax; ReturnLength
0x180022241  lea     r8, [rdi+20h]; TokenInformation
0x180022245  mov     [rsp+540h+ReturnLength], r9d
0x18002224a  mov     edx, ebx; TokenInformationClass
0x18002224c  call    cs:__imp_GetTokenInformation
0x180022252  test    eax, eax
0x180022254  jnz     short loc_18002226D
0x180022256  call    cs:__imp_GetLastError
0x18002225c  mov     ebx, eax
0x18002225e  test    eax, eax
0x180022260  jle     short loc_180022281
0x180022262  movzx   ebx, ax
0x180022265  or      ebx, 80070000h
0x18002226b  jmp     short loc_180022281
0x18002226d  lea     rcx, [rdi+78h]; this
0x180022271  mov     r9d, r15d; unsigned int
0x180022274  mov     r8, r13; unsigned __int16 *
0x180022277  mov     rdx, r12; unsigned __int16 *
0x18002227a  call    ?CreateCacheKey@TOKEN_KEY@@QEAAJPEBG0K@Z; TOKEN_KEY::CreateCacheKey(ushort const *,ushort const *,ulong)
0x18002227f  mov     ebx, eax
0x180022281  test    ebx, ebx
0x180022283  jns     short loc_180022296
0x180022285  mov     rax, [rdi]
0x180022288  mov     rcx, rdi
0x18002228b  mov     rax, [rax+10h]
0x18002228f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022294  jmp     short loc_1800222A5
0x180022296  mov     rax, [rsp+540h+var_4C8]
0x18002229b  mov     [rax], rdi
0x18002229e  jmp     short loc_1800222B5
0x1800222a0  mov     ebx, 80070008h
0x1800222a5  mov     rcx, [rsp+540h+TokenHandle]; hObject
0x1800222aa  test    rcx, rcx
0x1800222ad  jz      short loc_1800222B5
0x1800222af  call    cs:__imp_CloseHandle
0x1800222b5  mov     rcx, [rsp+540h+Buffer]; Buffer
0x1800222ba  test    rcx, rcx
0x1800222bd  jz      short loc_1800222C5
0x1800222bf  call    cs:__imp_LsaFreeReturnBuffer
0x1800222c5  lea     rcx, [rbp+440h+var_4C0]
0x1800222c9  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1800222cf  lea     rcx, [rbp+440h+var_488]
0x1800222d3  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1800222d9  mov     eax, ebx
0x1800222db  mov     rcx, [rbp+440h+var_50]
0x1800222e2  xor     rcx, rsp; StackCookie
0x1800222e5  call    __security_check_cookie
0x1800222ea  add     rsp, 508h
0x1800222f1  pop     r15
0x1800222f3  pop     r14
0x1800222f5  pop     r13
0x1800222f7  pop     r12
0x1800222f9  pop     rdi
0x1800222fa  pop     rsi
0x1800222fb  pop     rbx
0x1800222fc  pop     rbp
0x1800222fd  retn
```
