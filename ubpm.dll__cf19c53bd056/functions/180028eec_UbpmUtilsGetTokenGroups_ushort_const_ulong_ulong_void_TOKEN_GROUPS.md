# UbpmUtilsGetTokenGroups(ushort const *,ulong,ulong,void * *,_TOKEN_GROUPS * *)

- ea: `0x180028eec`
- end: `0x1800291e8`
- name: `?UbpmUtilsGetTokenGroups@@YAKPEBGKKPEAPEAXPEAPEAU_TOKEN_GROUPS@@@Z`
- size: `764`
- prototype: `unsigned int __fastcall(const unsigned __int16 *, unsigned int, unsigned int, void **, struct _TOKEN_GROUPS **)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180019480`

## callees

- `0x18000f9a0`
- `0x180019d90`
- `0x180028eec`
- `0x180029398`
- `0x18003d810`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18002902a`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180029036`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800290ee`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18002902a`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180029036`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800290ee`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180029138`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180029147`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180029138`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180029147`
- `api-ms-win-security-base-l1-1-0!AllocateLocallyUniqueId` at `0x180028f84`
- `api-ms-win-security-base-l1-1-0!AllocateLocallyUniqueId` at `0x180028f84`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180029103`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180029199`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180029103`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180029199`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180028fcb`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18002900c`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180028fcb`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18002900c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800291a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800291a3`

## pseudocode

```c
__int64 __fastcall UbpmUtilsGetTokenGroups(
        const unsigned __int16 *a1,
        unsigned int a2,
        unsigned int a3,
        void **a4,
        struct _TOKEN_GROUPS **a5)
{
  struct _TOKEN_GROUPS *v6; // rsi
  void *v7; // r12
  DWORD v8; // edi
  DWORD LengthSid; // ebx
  DWORD v10; // ebx
  DWORD v11; // r14d
  struct _TOKEN_GROUPS *v12; // rax
  char *v13; // rbx
  unsigned int v14; // r14d
  char *v15; // r15
  void **v16; // r8
  __int64 v17; // rdx
  __int64 v18; // rcx
  void *v19; // rax
  unsigned int i; // r13d
  __int64 v21; // rdi
  void *v22; // rcx
  DWORD v23; // eax
  void *v24; // r8
  PSID Sid; // rdx
  DWORD LastError; // ebx
  DWORD ConsumerSid; // eax
  unsigned int v29; // [rsp+60h] [rbp-51h] BYREF
  PSID pSid; // [rsp+68h] [rbp-49h] BYREF
  void *v31; // [rsp+70h] [rbp-41h] BYREF
  struct _LUID Luid; // [rsp+78h] [rbp-39h] BYREF
  PSID v33; // [rsp+80h] [rbp-31h] BYREF
  void **v34; // [rsp+88h] [rbp-29h]
  struct _TOKEN_GROUPS **v35; // [rsp+90h] [rbp-21h]
  PSID pSourceSid; // [rsp+98h] [rbp-19h]
  _DWORD v37[2]; // [rsp+A0h] [rbp-11h]
  PSID v38; // [rsp+A8h] [rbp-9h]
  int v39; // [rsp+B0h] [rbp-1h]
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+B8h] [rbp+7h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY v41; // [rsp+C0h] [rbp+Fh] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  v35 = a5;
  v6 = 0;
  v34 = a4;
  v7 = 0;
  *(_DWORD *)v41.Value = 0;
  v8 = 0;
  *(_WORD *)&v41.Value[4] = 512;
  v37[0] = -1073741817;
  v39 = 7;
  pSid = 0;
  v31 = 0;
  v29 = 0;
  v33 = 0;
  Luid = 0;
  if ( a3 > 0x400 )
  {
    LastError = 1389;
    goto LABEL_20;
  }
  if ( !a4 )
  {
    ConsumerSid = UbpmUtilsGetConsumerSid(a1, a2, &v31, &v29);
    v7 = v31;
    LastError = ConsumerSid;
    if ( ConsumerSid )
      goto LABEL_16;
    v8 = v29;
  }
  if ( AllocateLocallyUniqueId(&Luid) )
  {
    if ( AllocateAndInitializeSid(&pIdentifierAuthority, 3u, 5u, Luid.HighPart, Luid.LowPart, 0, 0, 0, 0, 0, &pSid) )
    {
      if ( AllocateAndInitializeSid(&v41, 1u, 0, 0, 0, 0, 0, 0, 0, 0, &v33) )
      {
        pSourceSid = pSid;
        v38 = v33;
        LengthSid = GetLengthSid(v33);
        v10 = GetLengthSid(pSid) + LengthSid;
        v11 = v8 + v10 + 16 * ((v7 != 0) + a3) + 40;
        v12 = (struct _TOKEN_GROUPS *)UbpmAlloc(v11);
        v6 = v12;
        if ( v12 )
        {
          v13 = (char *)v12 + v11 - (unsigned __int64)(v10 + v8);
          v12->GroupCount = a3 + (v7 != 0) + 2;
          if ( !v7 )
          {
            v14 = 0;
            v15 = v13;
            if ( a3 )
            {
              v16 = v34;
              v17 = 0;
              do
              {
                ++v14;
                v18 = v17;
                v6->Groups[v18].Attributes = 14;
                v19 = v16[v17++];
                v6->Groups[v18].Sid = v19;
              }
              while ( v14 < a3 );
            }
LABEL_11:
            for ( i = 0; i < 2; ++i )
            {
              v21 = v14;
              v22 = *(void **)&v37[4 * i - 2];
              v6->Groups[v21].Attributes = v37[4 * i];
              v6->Groups[v21].Sid = v15;
              v23 = GetLengthSid(v22);
              v24 = *(void **)&v37[4 * i - 2];
              Sid = v6->Groups[v14].Sid;
              v29 = v23;
              if ( !CopySid(v23, Sid, v24) )
                goto LABEL_22;
              v15 += v29;
              ++v14;
            }
            LastError = 0;
            *v35 = v6;
            v6 = 0;
            goto LABEL_16;
          }
          v12->Groups[0].Attributes = 14;
          v12->Groups[0].Sid = v13;
          if ( CopySid(v8, v13, v7) )
          {
            v14 = 1;
            v15 = &v13[v8];
            goto LABEL_11;
          }
        }
      }
    }
  }
LABEL_22:
  LastError = GetLastError();
LABEL_16:
  if ( pSid )
    FreeSid(pSid);
  if ( v33 )
    FreeSid(v33);
LABEL_20:
  UBPM_MIDL_user_free(v6);
  UBPM_MIDL_user_free(v7);
  return LastError;
}

```

## disassembly

```asm
0x180028eec  mov     [rsp-8+arg_18], rbx
0x180028ef1  push    rbp
0x180028ef2  push    rsi
0x180028ef3  push    rdi
0x180028ef4  push    r12
0x180028ef6  push    r13
0x180028ef8  push    r14
0x180028efa  push    r15
0x180028efc  lea     rbp, [rsp-1Fh]
0x180028f01  sub     rsp, 0D0h
0x180028f08  mov     rax, cs:__security_cookie
0x180028f0f  xor     rax, rsp
0x180028f12  mov     [rbp+4Fh+var_38], rax
0x180028f16  xor     r15d, r15d
0x180028f19  mov     word ptr [rbp+4Fh+pIdentifierAuthority.Value+4], 500h
0x180028f1f  mov     r13d, r8d
0x180028f22  mov     dword ptr [rbp+4Fh+pIdentifierAuthority.Value], r15d
0x180028f26  mov     r8, [rbp+4Fh+arg_20]
0x180028f2a  mov     rax, r9
0x180028f2d  mov     [rbp+4Fh+var_70], r8
0x180028f31  mov     esi, r15d
0x180028f34  mov     [rbp+4Fh+var_78], rax
0x180028f38  mov     r12d, r15d
0x180028f3b  mov     dword ptr [rbp+4Fh+var_40.Value], r15d
0x180028f3f  mov     edi, r15d
0x180028f42  mov     word ptr [rbp+4Fh+var_40.Value+4], 200h
0x180028f48  mov     [rbp+4Fh+var_60], 0C0000007h
0x180028f4f  mov     [rbp+4Fh+var_50], 7
0x180028f56  mov     [rbp+4Fh+var_98], r15
0x180028f5a  mov     [rbp+4Fh+var_90], r15
0x180028f5e  mov     [rbp+4Fh+var_A0], r15d
0x180028f62  mov     [rbp+4Fh+var_80], r15
0x180028f66  mov     qword ptr [rbp+4Fh+Luid.LowPart], r15
0x180028f6a  cmp     r13d, 400h
0x180028f71  ja      loc_1800291AD
0x180028f77  test    rax, rax
0x180028f7a  jz      loc_1800291B4
0x180028f80  lea     rcx, [rbp+4Fh+Luid]; Luid
0x180028f84  call    cs:__imp_AllocateLocallyUniqueId
0x180028f8a  test    eax, eax
0x180028f8c  jz      loc_1800291A3
0x180028f92  mov     r9d, [rbp+4Fh+Luid.HighPart]; nSubAuthority1
0x180028f96  lea     rax, [rbp+4Fh+var_98]
0x180028f9a  mov     [rsp+100h+pSid], rax; pSid
0x180028f9f  lea     rcx, [rbp+4Fh+pIdentifierAuthority]; pIdentifierAuthority
0x180028fa3  mov     eax, [rbp+4Fh+Luid.LowPart]
0x180028fa6  mov     r8d, 5; nSubAuthority0
0x180028fac  mov     [rsp+100h+nSubAuthority7], r15d; nSubAuthority7
0x180028fb1  mov     dl, 3; nSubAuthorityCount
0x180028fb3  mov     [rsp+100h+nSubAuthority6], r15d; nSubAuthority6
0x180028fb8  mov     [rsp+100h+nSubAuthority5], r15d; nSubAuthority5
0x180028fbd  mov     [rsp+100h+nSubAuthority4], r15d; nSubAuthority4
0x180028fc2  mov     [rsp+100h+nSubAuthority3], r15d; nSubAuthority3
0x180028fc7  mov     [rsp+100h+nSubAuthority2], eax; nSubAuthority2
0x180028fcb  call    cs:__imp_AllocateAndInitializeSid
0x180028fd1  test    eax, eax
0x180028fd3  jz      loc_1800291A3
0x180028fd9  lea     rax, [rbp+4Fh+var_80]
0x180028fdd  xor     r9d, r9d; nSubAuthority1
0x180028fe0  mov     [rsp+100h+pSid], rax; pSid
0x180028fe5  lea     rcx, [rbp+4Fh+var_40]; pIdentifierAuthority
0x180028fe9  mov     [rsp+100h+nSubAuthority7], r15d; nSubAuthority7
0x180028fee  xor     r8d, r8d; nSubAuthority0
0x180028ff1  mov     [rsp+100h+nSubAuthority6], r15d; nSubAuthority6
0x180028ff6  mov     dl, 1; nSubAuthorityCount
0x180028ff8  mov     [rsp+100h+nSubAuthority5], r15d; nSubAuthority5
0x180028ffd  mov     [rsp+100h+nSubAuthority4], r15d; nSubAuthority4
0x180029002  mov     [rsp+100h+nSubAuthority3], r15d; nSubAuthority3
0x180029007  mov     [rsp+100h+nSubAuthority2], r15d; nSubAuthority2
0x18002900c  call    cs:__imp_AllocateAndInitializeSid
0x180029012  test    eax, eax
0x180029014  jz      loc_1800291A3
0x18002901a  mov     rax, [rbp+4Fh+var_98]
0x18002901e  mov     rcx, [rbp+4Fh+var_80]; pSid
0x180029022  mov     [rbp+4Fh+pSourceSid], rax
0x180029026  mov     [rbp+4Fh+var_58], rcx
0x18002902a  call    cs:__imp_GetLengthSid
0x180029030  mov     rcx, [rbp+4Fh+var_98]; pSid
0x180029034  mov     ebx, eax
0x180029036  call    cs:__imp_GetLengthSid
0x18002903c  add     ebx, eax
0x18002903e  mov     eax, r15d
0x180029041  test    r12, r12
0x180029044  setnz   al
0x180029047  lea     r14d, [rax+r13]
0x18002904b  shl     r14d, 4
0x18002904f  add     r14d, 28h ; '('
0x180029053  add     r14d, ebx
0x180029056  add     r14d, edi
0x180029059  mov     ecx, r14d; Size
0x18002905c  call    ?UbpmAlloc@@YAPEAXK@Z; UbpmAlloc(ulong)
0x180029061  mov     rsi, rax
0x180029064  test    rax, rax
0x180029067  jz      loc_1800291A3
0x18002906d  lea     ecx, [rbx+rdi]
0x180029070  mov     ebx, r14d
0x180029073  sub     rbx, rcx
0x180029076  add     rbx, rax
0x180029079  mov     rax, r12
0x18002907c  neg     rax
0x18002907f  sbb     ecx, ecx
0x180029081  neg     ecx
0x180029083  lea     eax, [rcx+2]
0x180029086  add     eax, r13d
0x180029089  mov     [rsi], eax
0x18002908b  test    r12, r12
0x18002908e  jnz     loc_180029186
0x180029094  xor     r14d, r14d
0x180029097  mov     r15, rbx
0x18002909a  test    r13d, r13d
0x18002909d  jz      short loc_1800290C7
0x18002909f  mov     r8, [rbp+4Fh+var_78]
0x1800290a3  xor     edx, edx
0x1800290a5  mov     rcx, rdx
0x1800290a8  inc     r14d
0x1800290ab  add     rcx, rcx
0x1800290ae  mov     dword ptr [rsi+rcx*8+10h], 0Eh
0x1800290b6  mov     rax, [r8+rdx*8]
0x1800290ba  inc     rdx
0x1800290bd  mov     [rsi+rcx*8+8], rax
0x1800290c2  cmp     r14d, r13d
0x1800290c5  jb      short loc_1800290A5
0x1800290c7  xor     r13d, r13d
0x1800290ca  cmp     r13d, 2
0x1800290ce  jnb     short loc_18002911F
0x1800290d0  mov     ebx, r13d
0x1800290d3  add     rbx, rbx
0x1800290d6  mov     edi, r14d
0x1800290d9  add     rdi, rdi
0x1800290dc  mov     eax, [rbp+rbx*8+4Fh+var_60]
0x1800290e0  mov     rcx, [rbp+rbx*8+4Fh+pSourceSid]; pSid
0x1800290e5  mov     [rsi+rdi*8+10h], eax
0x1800290e9  mov     [rsi+rdi*8+8], r15
0x1800290ee  call    cs:__imp_GetLengthSid
0x1800290f4  mov     r8, [rbp+rbx*8+4Fh+pSourceSid]; pSourceSid
0x1800290f9  mov     ecx, eax; nDestinationSidLength
0x1800290fb  mov     rdx, [rsi+rdi*8+8]; pDestinationSid
0x180029100  mov     [rbp+4Fh+var_A0], eax
0x180029103  call    cs:__imp_CopySid
0x180029109  test    eax, eax
0x18002910b  jz      loc_1800291A3
0x180029111  mov     eax, [rbp+4Fh+var_A0]
0x180029114  inc     r13d
0x180029117  add     r15, rax
0x18002911a  inc     r14d
0x18002911d  jmp     short loc_1800290CA
0x18002911f  mov     rax, [rbp+4Fh+var_70]
0x180029123  xor     r15d, r15d
0x180029126  mov     ebx, r15d
0x180029129  mov     [rax], rsi
0x18002912c  mov     esi, r15d
0x18002912f  mov     rcx, [rbp+4Fh+var_98]; pSid
0x180029133  test    rcx, rcx
0x180029136  jz      short loc_18002913E
0x180029138  call    cs:__imp_FreeSid
0x18002913e  mov     rcx, [rbp+4Fh+var_80]; pSid
0x180029142  test    rcx, rcx
0x180029145  jz      short loc_18002914D
0x180029147  call    cs:__imp_FreeSid
0x18002914d  mov     rcx, rsi
0x180029150  call    UBPM_MIDL_user_free
0x180029155  mov     rcx, r12
0x180029158  call    UBPM_MIDL_user_free
0x18002915d  mov     eax, ebx
0x18002915f  mov     rcx, [rbp+4Fh+var_38]
0x180029163  xor     rcx, rsp; StackCookie
0x180029166  call    __security_check_cookie
0x18002916b  mov     rbx, [rsp+100h+arg_18]
0x180029173  add     rsp, 0D0h
0x18002917a  pop     r15
0x18002917c  pop     r14
0x18002917e  pop     r13
0x180029180  pop     r12
0x180029182  pop     rdi
0x180029183  pop     rsi
0x180029184  pop     rbp
0x180029185  retn
0x180029186  mov     r8, r12; pSourceSid
0x180029189  mov     dword ptr [rsi+10h], 0Eh
0x180029190  mov     rdx, rbx; pDestinationSid
0x180029193  mov     [rsi+8], rbx
0x180029197  mov     ecx, edi; nDestinationSidLength
0x180029199  call    cs:__imp_CopySid
0x18002919f  test    eax, eax
0x1800291a1  jnz     short loc_1800291D7
0x1800291a3  call    cs:__imp_GetLastError
0x1800291a9  mov     ebx, eax
0x1800291ab  jmp     short loc_18002912F
0x1800291ad  mov     ebx, 56Dh
0x1800291b2  jmp     short loc_18002914D
0x1800291b4  lea     r9, [rbp+4Fh+var_A0]; unsigned int *
0x1800291b8  lea     r8, [rbp+4Fh+var_90]; void **
0x1800291bc  call    ?UbpmUtilsGetConsumerSid@@YAKPEBGKPEAPEAXPEAK@Z; UbpmUtilsGetConsumerSid(ushort const *,ulong,void * *,ulong *)
0x1800291c1  mov     r12, [rbp+4Fh+var_90]
0x1800291c5  mov     ebx, eax
0x1800291c7  test    eax, eax
0x1800291c9  jnz     loc_18002912F
0x1800291cf  mov     edi, [rbp+4Fh+var_A0]
0x1800291d2  jmp     loc_180028F80
0x1800291d7  mov     r15d, edi
0x1800291da  mov     r14d, 1
0x1800291e0  add     r15, rbx
0x1800291e3  jmp     loc_1800290C7
```
