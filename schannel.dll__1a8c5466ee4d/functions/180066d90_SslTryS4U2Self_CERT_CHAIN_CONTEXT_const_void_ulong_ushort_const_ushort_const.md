# SslTryS4U2Self(_CERT_CHAIN_CONTEXT const *,void * *,ulong,ushort const *,ushort const *)

- ea: `0x180066d90`
- end: `0x1800670de`
- name: `?SslTryS4U2Self@@YAJPEBU_CERT_CHAIN_CONTEXT@@PEAPEAXKPEBG2@Z`
- size: `846`
- prototype: `int(const struct _CERT_CHAIN_CONTEXT *, void **, unsigned int, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x180064bc8`
- `0x1800661d8`

## callees

- `0x180057cb4`
- `0x1800597b0`
- `0x180064848`
- `0x180066d90`
- `0x180088a54`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006709f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800670af`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006709f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800670af`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180066ed4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180066ed4`
- `SspiCli!LsaLogonUser` at `0x180067067`
- `SspiCli!LsaLogonUser` at `0x180067067`
- `SspiCli!LsaFreeReturnBuffer` at `0x180067091`
- `SspiCli!LsaFreeReturnBuffer` at `0x180067091`
- `LSASRV!LsaISetTokenDacl` at `0x18006707d`
- `LSASRV!LsaISetTokenDacl` at `0x18006707d`

## pseudocode

```c
__int64 __fastcall SslTryS4U2Self(
        const struct _CERT_CHAIN_CONTEXT *a1,
        void **a2,
        int a3,
        const unsigned __int16 *a4,
        const unsigned __int16 *Src)
{
  int v5; // r14d
  bool v6; // zf
  __int64 result; // rax
  PCCERT_CONTEXT pCertContext; // rsi
  _DWORD *AuthenticationInformation; // rdi
  ULONG AuthenticationInformationLength; // esi
  __int64 v13; // rcx
  unsigned __int16 v14; // r13
  __int64 v15; // rax
  int v16; // edx
  _DWORD *v17; // rax
  NTSTATUS v18; // ebx
  _DWORD *v19; // r15
  char *v20; // rbx
  PCCERT_CONTEXT v21; // rdx
  PHANDLE v22; // r14
  int SubStatus; // [rsp+70h] [rbp-51h] BYREF
  HLOCAL hMem; // [rsp+78h] [rbp-49h] BYREF
  int v25; // [rsp+80h] [rbp-41h] BYREF
  ULONG ProfileBufferLength; // [rsp+84h] [rbp-3Dh] BYREF
  PVOID Buffer; // [rsp+88h] [rbp-39h] BYREF
  PCCERT_CONTEXT v28; // [rsp+90h] [rbp-31h]
  PHANDLE Token; // [rsp+98h] [rbp-29h]
  struct _LUID LogonId; // [rsp+A0h] [rbp-21h] BYREF
  struct _QUOTA_LIMITS Quotas; // [rsp+A8h] [rbp-19h] BYREF

  LOWORD(v5) = 0;
  v6 = g_SslS4U2SelfInitialized == 0;
  Token = a2;
  SubStatus = 0;
  v25 = 0;
  hMem = 0;
  Buffer = 0;
  ProfileBufferLength = 0;
  LogonId = 0;
  *(_OWORD *)&Quotas.PagedPoolLimit = 0;
  *a2 = 0;
  memset(&Quotas.MinimumWorkingSetSize, 0, 32);
  if ( v6 )
    return 3221225659LL;
  pCertContext = (*(*a1->rgpChain)->rgpElement)->pCertContext;
  v28 = pCertContext;
  result = SslGetNameFromCertificate(pCertContext, (unsigned __int16 **)&hMem, &v25);
  if ( (int)result >= 0 )
  {
    AuthenticationInformation = 0;
    if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_e1738149d20f31dfe7380947af7f2303_Traceguids, hMem);
    AuthenticationInformationLength = pCertContext->cbCertEncoded + 56;
    if ( AuthenticationInformationLength >= 0x38 )
    {
      v13 = -1;
      v14 = 0;
      if ( !a4 )
      {
LABEL_13:
        if ( !Src )
          goto LABEL_17;
        do
          ++v13;
        while ( Src[v13] );
        v5 = (unsigned __int16)(2 * (v13 + 1));
        if ( v5 + AuthenticationInformationLength >= AuthenticationInformationLength )
        {
          AuthenticationInformationLength += v5;
LABEL_17:
          v17 = LocalAlloc(0x40u, AuthenticationInformationLength);
          AuthenticationInformation = v17;
          if ( v17 )
          {
            *v17 = 14;
            v17[1] = a3 | 2;
            v19 = v17 + 14;
            if ( a4 )
            {
              if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control
                && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
              {
                WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_e1738149d20f31dfe7380947af7f2303_Traceguids, a4);
              }
              *((_WORD *)AuthenticationInformation + 4) = v14 - 2;
              *((_QWORD *)AuthenticationInformation + 2) = v19;
              *((_WORD *)AuthenticationInformation + 5) = v14;
              memcpy_0(AuthenticationInformation + 14, a4, v14);
              v20 = (char *)v19 + *((unsigned __int16 *)AuthenticationInformation + 5);
            }
            else
            {
              v20 = (char *)(v17 + 14);
            }
            if ( Src )
            {
              if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control
                && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
              {
                WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_e1738149d20f31dfe7380947af7f2303_Traceguids, Src);
              }
              *((_WORD *)AuthenticationInformation + 12) = v5 - 2;
              *((_QWORD *)AuthenticationInformation + 4) = v20;
              *((_WORD *)AuthenticationInformation + 13) = v5;
              memcpy_0(v20, Src, (unsigned __int16)v5);
              v20 += *((unsigned __int16 *)AuthenticationInformation + 13);
            }
            v21 = v28;
            AuthenticationInformation[10] = v28->cbCertEncoded;
            *((_QWORD *)AuthenticationInformation + 6) = v20;
            memcpy_0(v20, v21->pbCertEncoded, v21->cbCertEncoded);
            v22 = Token;
            v18 = LsaLogonUser(
                    SslLogonHandle,
                    &SslPackageNameA,
                    Network,
                    SslKerberosPackageId,
                    AuthenticationInformation,
                    AuthenticationInformationLength,
                    SslPackageSid,
                    &SslTokenSource,
                    &Buffer,
                    &ProfileBufferLength,
                    &LogonId,
                    Token,
                    &Quotas,
                    &SubStatus);
            if ( v18 >= 0 )
            {
              v18 = SubStatus;
              if ( SubStatus >= 0 )
                v18 = LsaISetTokenDacl(*v22);
            }
          }
          else
          {
            v18 = -1073741801;
          }
          goto LABEL_35;
        }
        v18 = -1073741675;
LABEL_35:
        if ( Buffer )
          LsaFreeReturnBuffer(Buffer);
        if ( AuthenticationInformation )
          LocalFree(AuthenticationInformation);
        if ( hMem )
          LocalFree(hMem);
        return (unsigned int)v18;
      }
      v15 = -1;
      do
        ++v15;
      while ( a4[v15] );
      v16 = (unsigned __int16)(2 * (v15 + 1));
      if ( v16 + AuthenticationInformationLength >= AuthenticationInformationLength )
      {
        v14 = 2 * (v15 + 1);
        AuthenticationInformationLength += v16;
        goto LABEL_13;
      }
    }
    v18 = -1073741675;
    goto LABEL_35;
  }
  return result;
}

```

## disassembly

```asm
0x180066d90  mov     [rsp-8+arg_10], rbx
0x180066d95  push    rbp
0x180066d96  push    rsi
0x180066d97  push    rdi
0x180066d98  push    r12
0x180066d9a  push    r13
0x180066d9c  push    r14
0x180066d9e  push    r15
0x180066da0  lea     rbp, [rsp-1Fh]
0x180066da5  sub     rsp, 0E0h
0x180066dac  mov     rax, cs:__security_cookie
0x180066db3  xor     rax, rsp
0x180066db6  mov     [rbp+4Fh+var_38], rax
0x180066dba  mov     r12, [rbp+4Fh+Src]
0x180066dbe  xor     r14d, r14d
0x180066dc1  cmp     cs:?g_SslS4U2SelfInitialized@@3HA, r14d; int g_SslS4U2SelfInitialized
0x180066dc8  xorps   xmm0, xmm0
0x180066dcb  mov     rbx, r9
0x180066dce  mov     [rbp+4Fh+var_78], rdx
0x180066dd2  mov     r15d, r8d
0x180066dd5  mov     [rbp+4Fh+var_A0], r14d
0x180066dd9  mov     [rbp+4Fh+var_90], r14d
0x180066ddd  mov     [rbp+4Fh+hMem], r14
0x180066de1  mov     [rbp+4Fh+Buffer], r14
0x180066de5  mov     [rbp+4Fh+var_8C], r14d
0x180066de9  mov     qword ptr [rbp+4Fh+var_70.LowPart], r14
0x180066ded  movups  xmmword ptr [rbp+4Fh+var_68.PagedPoolLimit], xmm0
0x180066df1  mov     [rdx], r14
0x180066df4  movups  xmmword ptr [rbp+4Fh+var_68.MinimumWorkingSetSize], xmm0
0x180066df8  movups  xmmword ptr [rbp+4Fh+var_68.PagefileLimit], xmm0
0x180066dfc  jnz     short loc_180066E08
0x180066dfe  mov     eax, 0C00000BBh
0x180066e03  jmp     loc_1800670B7
0x180066e08  mov     rax, [rcx+10h]
0x180066e0c  lea     r8, [rbp+4Fh+var_90]; int *
0x180066e10  lea     rdx, [rbp+4Fh+hMem]; unsigned __int16 **
0x180066e14  mov     rcx, [rax]
0x180066e17  mov     rax, [rcx+10h]
0x180066e1b  mov     rcx, [rax]
0x180066e1e  mov     rsi, [rcx+8]
0x180066e22  mov     rcx, rsi; pCertContext
0x180066e25  mov     [rbp+4Fh+var_80], rsi
0x180066e29  call    ?SslGetNameFromCertificate@@YAJPEBU_CERT_CONTEXT@@PEAPEAGPEAH@Z; SslGetNameFromCertificate(_CERT_CONTEXT const *,ushort * *,int *)
0x180066e2e  test    eax, eax
0x180066e30  js      loc_1800670B7
0x180066e36  mov     rcx, cs:WPP_GLOBAL_Control
0x180066e3d  lea     rax, WPP_GLOBAL_Control
0x180066e44  mov     rdi, r14
0x180066e47  cmp     rcx, rax
0x180066e4a  jz      short loc_180066E6E
0x180066e4c  test    dword ptr [rcx+1Ch], 100h
0x180066e53  jz      short loc_180066E6E
0x180066e55  mov     r9, [rbp+4Fh+hMem]
0x180066e59  lea     r8, WPP_e1738149d20f31dfe7380947af7f2303_Traceguids
0x180066e60  mov     rcx, [rcx+10h]
0x180066e64  mov     edx, 0Ah
0x180066e69  call    WPP_SF_S
0x180066e6e  mov     esi, [rsi+10h]
0x180066e71  add     esi, 38h ; '8'
0x180066e74  cmp     esi, 38h ; '8'
0x180066e77  jb      short loc_180066EEC
0x180066e79  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180066e7d  mov     r13d, r14d
0x180066e80  test    rbx, rbx
0x180066e83  jz      short loc_180066EA8
0x180066e85  mov     rax, rcx
0x180066e88  inc     rax
0x180066e8b  cmp     [rbx+rax*2], r14w
0x180066e90  jnz     short loc_180066E88
0x180066e92  inc     ax
0x180066e95  add     ax, ax
0x180066e98  movzx   edx, ax
0x180066e9b  lea     eax, [rdx+rsi]
0x180066e9e  cmp     eax, esi
0x180066ea0  jb      short loc_180066EEC
0x180066ea2  movzx   r13d, dx
0x180066ea6  mov     esi, eax
0x180066ea8  xor     eax, eax
0x180066eaa  test    r12, r12
0x180066ead  jz      short loc_180066ECD
0x180066eaf  inc     rcx
0x180066eb2  cmp     [r12+rcx*2], ax
0x180066eb7  jnz     short loc_180066EAF
0x180066eb9  inc     cx
0x180066ebc  add     cx, cx
0x180066ebf  movzx   r14d, cx
0x180066ec3  lea     eax, [r14+rsi]
0x180066ec7  cmp     eax, esi
0x180066ec9  jb      short loc_180066EF6
0x180066ecb  mov     esi, eax
0x180066ecd  mov     edx, esi; uBytes
0x180066ecf  mov     ecx, 40h ; '@'; uFlags
0x180066ed4  call    cs:__imp_LocalAlloc
0x180066eda  mov     rdi, rax
0x180066edd  test    rax, rax
0x180066ee0  jnz     short loc_180066F00
0x180066ee2  mov     ebx, 0C0000017h
0x180066ee7  jmp     loc_180067085
0x180066eec  mov     ebx, 0C0000095h
0x180066ef1  jmp     loc_180067088
0x180066ef6  mov     ebx, 0C0000095h
0x180066efb  jmp     loc_180067085
0x180066f00  or      r15d, 2
0x180066f04  mov     dword ptr [rdi], 0Eh
0x180066f0a  mov     [rdi+4], r15d
0x180066f0e  lea     r15, [rdi+38h]
0x180066f12  test    rbx, rbx
0x180066f15  jz      short loc_180066F74
0x180066f17  mov     rcx, cs:WPP_GLOBAL_Control
0x180066f1e  lea     rax, WPP_GLOBAL_Control
0x180066f25  cmp     rcx, rax
0x180066f28  jz      short loc_180066F4B
0x180066f2a  test    dword ptr [rcx+1Ch], 100h
0x180066f31  jz      short loc_180066F4B
0x180066f33  mov     rcx, [rcx+10h]
0x180066f37  lea     r8, WPP_e1738149d20f31dfe7380947af7f2303_Traceguids
0x180066f3e  mov     edx, 0Bh
0x180066f43  mov     r9, rbx
0x180066f46  call    WPP_SF_S
0x180066f4b  lea     eax, [r13-2]
0x180066f4f  movzx   r8d, r13w; Size
0x180066f53  mov     rdx, rbx; Src
0x180066f56  mov     [rdi+8], ax
0x180066f5a  mov     rcx, r15; void *
0x180066f5d  mov     [rdi+10h], r15
0x180066f61  mov     [rdi+0Ah], r13w
0x180066f66  call    memcpy_0
0x180066f6b  movzx   ebx, word ptr [rdi+0Ah]
0x180066f6f  add     rbx, r15
0x180066f72  jmp     short loc_180066F77
0x180066f74  mov     rbx, r15
0x180066f77  test    r12, r12
0x180066f7a  jz      short loc_180066FD7
0x180066f7c  mov     rcx, cs:WPP_GLOBAL_Control
0x180066f83  lea     rax, WPP_GLOBAL_Control
0x180066f8a  cmp     rcx, rax
0x180066f8d  jz      short loc_180066FB0
0x180066f8f  test    dword ptr [rcx+1Ch], 100h
0x180066f96  jz      short loc_180066FB0
0x180066f98  mov     rcx, [rcx+10h]
0x180066f9c  lea     r8, WPP_e1738149d20f31dfe7380947af7f2303_Traceguids
0x180066fa3  mov     edx, 0Ch
0x180066fa8  mov     r9, r12
0x180066fab  call    WPP_SF_S
0x180066fb0  lea     eax, [r14-2]
0x180066fb4  movzx   r8d, r14w; Size
0x180066fb8  mov     rdx, r12; Src
0x180066fbb  mov     [rdi+18h], ax
0x180066fbf  mov     rcx, rbx; void *
0x180066fc2  mov     [rdi+20h], rbx
0x180066fc6  mov     [rdi+1Ah], r14w
0x180066fcb  call    memcpy_0
0x180066fd0  movzx   eax, word ptr [rdi+1Ah]
0x180066fd4  add     rbx, rax
0x180066fd7  mov     rdx, [rbp+4Fh+var_80]
0x180066fdb  mov     rcx, rbx; void *
0x180066fde  mov     eax, [rdx+10h]
0x180066fe1  mov     [rdi+28h], eax
0x180066fe4  mov     [rdi+30h], rbx
0x180066fe8  mov     r8d, [rdx+10h]; Size
0x180066fec  mov     rdx, [rdx+8]; Src
0x180066ff0  call    memcpy_0
0x180066ff5  mov     r14, [rbp+4Fh+var_78]
0x180066ff9  lea     rax, [rbp+4Fh+var_A0]
0x180066ffd  mov     r9d, cs:?SslKerberosPackageId@@3KA; AuthenticationPackage
0x180067004  lea     rdx, ?SslPackageNameA@@3U_STRING@@A; OriginName
0x18006700b  mov     rcx, cs:?SslLogonHandle@@3PEAXEA; LsaHandle
0x180067012  mov     r8d, 3; LogonType
0x180067018  mov     [rsp+110h+SubStatus], rax; SubStatus
0x18006701d  lea     rax, [rbp+4Fh+var_68]
0x180067021  mov     [rsp+110h+Quotas], rax; Quotas
0x180067026  lea     rax, [rbp+4Fh+var_70]
0x18006702a  mov     [rsp+110h+Token], r14; Token
0x18006702f  mov     [rsp+110h+LogonId], rax; LogonId
0x180067034  lea     rax, [rbp+4Fh+var_8C]
0x180067038  mov     [rsp+110h+ProfileBufferLength], rax; ProfileBufferLength
0x18006703d  lea     rax, [rbp+4Fh+Buffer]
0x180067041  mov     [rsp+110h+ProfileBuffer], rax; ProfileBuffer
0x180067046  lea     rax, ?SslTokenSource@@3U_TOKEN_SOURCE@@A; _TOKEN_SOURCE SslTokenSource
0x18006704d  mov     [rsp+110h+SourceContext], rax; SourceContext
0x180067052  mov     rax, cs:?SslPackageSid@@3PEAU_TOKEN_GROUPS@@EA; _TOKEN_GROUPS * SslPackageSid
0x180067059  mov     [rsp+110h+LocalGroups], rax; LocalGroups
0x18006705e  mov     [rsp+110h+AuthenticationInformationLength], esi; AuthenticationInformationLength
0x180067062  mov     [rsp+110h+AuthenticationInformation], rdi; AuthenticationInformation
0x180067067  call    cs:__imp_LsaLogonUser
0x18006706d  mov     ebx, eax
0x18006706f  test    eax, eax
0x180067071  js      short loc_180067085
0x180067073  mov     ebx, [rbp+4Fh+var_A0]
0x180067076  test    ebx, ebx
0x180067078  js      short loc_180067085
0x18006707a  mov     rcx, [r14]
0x18006707d  call    cs:__imp_LsaISetTokenDacl
0x180067083  mov     ebx, eax
0x180067085  xor     r14d, r14d
0x180067088  mov     rcx, [rbp+4Fh+Buffer]; Buffer
0x18006708c  test    rcx, rcx
0x18006708f  jz      short loc_180067097
0x180067091  call    cs:__imp_LsaFreeReturnBuffer
0x180067097  test    rdi, rdi
0x18006709a  jz      short loc_1800670A5
0x18006709c  mov     rcx, rdi; hMem
0x18006709f  call    cs:__imp_LocalFree
0x1800670a5  cmp     [rbp+4Fh+hMem], r14
0x1800670a9  jz      short loc_1800670B5
0x1800670ab  mov     rcx, [rbp+4Fh+hMem]; hMem
0x1800670af  call    cs:__imp_LocalFree
0x1800670b5  mov     eax, ebx
0x1800670b7  mov     rcx, [rbp+4Fh+var_38]
0x1800670bb  xor     rcx, rsp; StackCookie
0x1800670be  call    __security_check_cookie
0x1800670c3  mov     rbx, [rsp+110h+arg_10]
0x1800670cb  add     rsp, 0E0h
0x1800670d2  pop     r15
0x1800670d4  pop     r14
0x1800670d6  pop     r13
0x1800670d8  pop     r12
0x1800670da  pop     rdi
0x1800670db  pop     rsi
0x1800670dc  pop     rbp
0x1800670dd  retn
```
