# InitializeSidLookupTable

- ea: `0x180005730`
- end: `0x180005a94`
- name: `InitializeSidLookupTable`
- size: `868`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180004260`
- `0x180004f20`
- `0x180005d00`

## callees

- `0x180005730`
- `0x18000cbf8`
- `0x18004f902`
- `0x18004fa50`

## import_xrefs

- `ntdll!RtlInitializeSid` at `0x1800058e0`
- `ntdll!RtlInitializeSid` at `0x18000595d`
- `ntdll!RtlInitializeSid` at `0x180005a02`
- `ntdll!RtlInitializeSid` at `0x180005a2d`
- `ntdll!RtlInitializeSid` at `0x1800058e0`
- `ntdll!RtlInitializeSid` at `0x18000595d`
- `ntdll!RtlInitializeSid` at `0x180005a02`
- `ntdll!RtlInitializeSid` at `0x180005a2d`
- `ntdll!RtlSubAuthoritySid` at `0x1800058eb`
- `ntdll!RtlSubAuthoritySid` at `0x180005968`
- `ntdll!RtlSubAuthoritySid` at `0x180005a0d`
- `ntdll!RtlSubAuthoritySid` at `0x180005a38`
- `ntdll!RtlSubAuthoritySid` at `0x180005a4c`
- `ntdll!RtlSubAuthoritySid` at `0x1800058eb`
- `ntdll!RtlSubAuthoritySid` at `0x180005968`
- `ntdll!RtlSubAuthoritySid` at `0x180005a0d`
- `ntdll!RtlSubAuthoritySid` at `0x180005a38`
- `ntdll!RtlSubAuthoritySid` at `0x180005a4c`
- `ntdll!RtlSubAuthorityCountSid` at `0x180005942`
- `ntdll!RtlSubAuthorityCountSid` at `0x1800059b7`
- `ntdll!RtlSubAuthorityCountSid` at `0x180005942`
- `ntdll!RtlSubAuthorityCountSid` at `0x1800059b7`
- `ntdll!RtlLengthSid` at `0x18000591d`
- `ntdll!RtlLengthSid` at `0x180005992`
- `ntdll!RtlLengthSid` at `0x18000591d`
- `ntdll!RtlLengthSid` at `0x180005992`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800057d5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800057d5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800057ae`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800057ae`

## pseudocode

```c
char __fastcall InitializeSidLookupTable(unsigned __int8 a1)
{
  int v1; // ebx
  __int64 v2; // rdx
  __int64 v3; // rcx
  __int64 v4; // r8
  __int64 v5; // r9
  int v7; // edi
  __int64 i; // rdi
  __int64 v9; // rsi
  void **v10; // r14
  int v11; // eax
  struct _SID_IDENTIFIER_AUTHORITY *p_IdentifierAuthority; // rdx
  ULONG v13; // edx
  ULONG v14; // eax
  PULONG v15; // rax
  ULONG v16; // eax
  PULONG v17; // rax
  PULONG v18; // rax
  __int64 v19; // [rsp+20h] [rbp-40h] BYREF
  __int64 v20; // [rsp+28h] [rbp-38h] BYREF
  __int64 v21; // [rsp+30h] [rbp-30h] BYREF
  int v22; // [rsp+38h] [rbp-28h] BYREF
  __int16 v23; // [rsp+3Ch] [rbp-24h]
  int v24; // [rsp+40h] [rbp-20h] BYREF
  __int16 v25; // [rsp+44h] [rbp-1Ch]
  struct _SID_IDENTIFIER_AUTHORITY v26; // [rsp+48h] [rbp-18h] BYREF
  _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+50h] [rbp-10h] BYREF

  v1 = a1;
  LODWORD(v20) = 0;
  WORD2(v20) = 256;
  LODWORD(v21) = 0;
  WORD2(v21) = 512;
  v22 = 0;
  v23 = 768;
  LODWORD(v19) = 0;
  WORD2(v19) = 1280;
  v24 = 0;
  v25 = 4096;
  *(_DWORD *)v26.Value = 0;
  *(_WORD *)&v26.Value[4] = 3840;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  *(_WORD *)&IdentifierAuthority.Value[4] = 4608;
  EnterCriticalSection(&SddlSidLookupCritical);
  if ( v1 == 1 )
  {
    if ( (unsigned int)++dword_18007C620 > 1 || gbLookupTableInitialized == 1 )
      goto LABEL_3;
  }
  else if ( v1 == 2 )
  {
    if ( (unsigned int)dword_18007C620 <= 1 )
      v7 = 0;
    else
      v7 = dword_18007C620 - 1;
    dword_18007C620 = v7;
    goto LABEL_3;
  }
  CacheDomainAndDnsDomainSids(v3, v2, v4, v5, v19, v20, v21);
  for ( i = 0; i != 68; ++i )
  {
    v9 = 13 * i;
    if ( (_BYTE)v1 == 1 )
      LOBYTE(qword_180079EE0[v9]) = 0;
    v10 = (void **)&qword_180079EF0[v9];
    if ( LOBYTE(qword_180079EE0[v9]) != 1 || !*v10 )
    {
      v11 = HIDWORD(qword_180079EF8[v9]);
      *v10 = &qword_180079F00[v9];
      switch ( v11 )
      {
        case 0:
          if ( gbDnsDomainSidCached )
          {
            v14 = RtlLengthSid(Sid);
            memcpy_0(*v10, Sid, v14);
            ++*((_BYTE *)*v10 + 1);
            v13 = *RtlSubAuthorityCountSid(Sid);
            goto LABEL_21;
          }
          continue;
        case 1:
          p_IdentifierAuthority = (struct _SID_IDENTIFIER_AUTHORITY *)&v20;
          goto LABEL_20;
        case 2:
          p_IdentifierAuthority = (struct _SID_IDENTIFIER_AUTHORITY *)&v21;
          goto LABEL_20;
        case 3:
          if ( !gbDomainSidCached )
            continue;
          v16 = RtlLengthSid(Src);
          memcpy_0(*v10, Src, v16);
          ++*((_BYTE *)*v10 + 1);
          v13 = *RtlSubAuthorityCountSid(Src);
          goto LABEL_21;
        case 4:
          p_IdentifierAuthority = (struct _SID_IDENTIFIER_AUTHORITY *)&v22;
          goto LABEL_20;
        case 5:
          p_IdentifierAuthority = (struct _SID_IDENTIFIER_AUTHORITY *)&v19;
          goto LABEL_20;
        case 6:
          RtlInitializeSid(&qword_180079F00[v9], (PSID_IDENTIFIER_AUTHORITY)&v19, 2u);
          v15 = RtlSubAuthoritySid(*v10, 0);
          v13 = 1;
          *v15 = 32;
          goto LABEL_21;
        case 8:
          p_IdentifierAuthority = (struct _SID_IDENTIFIER_AUTHORITY *)&v24;
          goto LABEL_20;
        case 9:
          RtlInitializeSid(&qword_180079F00[v9], &v26, 2u);
          v17 = RtlSubAuthoritySid(*v10, 0);
          v13 = 1;
          *v17 = 2;
          goto LABEL_21;
        case 10:
          RtlInitializeSid(&qword_180079F00[v9], (PSID_IDENTIFIER_AUTHORITY)&v19, 6u);
          *RtlSubAuthoritySid(*v10, 0) = 84;
          v18 = RtlSubAuthoritySid(*v10, 1u);
          *(_OWORD *)v18 = 0;
          v18[4] = 0;
          goto LABEL_22;
        case 11:
          p_IdentifierAuthority = &IdentifierAuthority;
LABEL_20:
          RtlInitializeSid(&qword_180079F00[v9], p_IdentifierAuthority, 1u);
          v13 = 0;
LABEL_21:
          *RtlSubAuthoritySid(*v10, v13) = qword_180079EF8[v9];
LABEL_22:
          LOBYTE(qword_180079EE0[v9]) = 1;
          break;
        default:
          continue;
      }
    }
  }
  if ( gbLsaLookupSucceeded )
    gbLookupTableInitialized = 1;
LABEL_3:
  LeaveCriticalSection(&SddlSidLookupCritical);
  return 1;
}

```

## disassembly

```asm
0x180005730  push    rbp
0x180005732  push    rbx
0x180005733  push    rdi
0x180005734  mov     rbp, rsp
0x180005737  sub     rsp, 60h
0x18000573b  mov     rax, cs:__security_cookie
0x180005742  xor     rax, rsp
0x180005745  mov     [rbp+var_8], rax
0x180005749  movzx   ebx, cl
0x18000574c  lea     rcx, SddlSidLookupCritical; lpCriticalSection
0x180005753  mov     [rbp+var_38], 0
0x18000575a  mov     [rbp+var_34], 100h
0x180005760  mov     [rbp+var_30], 0
0x180005767  mov     [rbp+var_2C], 200h
0x18000576d  mov     [rbp+var_28], 0
0x180005774  mov     [rbp+var_24], 300h
0x18000577a  mov     dword ptr [rbp+var_40], 0
0x180005781  mov     word ptr [rbp+var_40+4], 500h
0x180005787  mov     [rbp+var_20], 0
0x18000578e  mov     [rbp+var_1C], 1000h
0x180005794  mov     dword ptr [rbp+var_18.Value], 0
0x18000579b  mov     word ptr [rbp+var_18.Value+4], 0F00h
0x1800057a1  mov     dword ptr [rbp+IdentifierAuthority.Value], 0
0x1800057a8  mov     word ptr [rbp+IdentifierAuthority.Value+4], 1200h
0x1800057ae  call    cs:__imp_EnterCriticalSection
0x1800057b4  mov     eax, ebx
0x1800057b6  sub     eax, 1
0x1800057b9  jnz     short loc_1800057F1
0x1800057bb  mov     eax, cs:dword_18007C620
0x1800057c1  inc     eax
0x1800057c3  mov     cs:dword_18007C620, eax
0x1800057c9  cmp     eax, 1
0x1800057cc  jbe     short loc_18000580E
0x1800057ce  lea     rcx, SddlSidLookupCritical; lpCriticalSection
0x1800057d5  call    cs:__imp_LeaveCriticalSection
0x1800057db  mov     al, 1
0x1800057dd  mov     rcx, [rbp+var_8]
0x1800057e1  xor     rcx, rsp; StackCookie
0x1800057e4  call    __security_check_cookie
0x1800057e9  add     rsp, 60h
0x1800057ed  pop     rdi
0x1800057ee  pop     rbx
0x1800057ef  pop     rbp
0x1800057f0  retn
0x1800057f1  cmp     eax, 1
0x1800057f4  jnz     short loc_180005817
0x1800057f6  mov     edi, cs:dword_18007C620
0x1800057fc  cmp     edi, eax
0x1800057fe  jbe     loc_1800058C2
0x180005804  dec     edi
0x180005806  mov     cs:dword_18007C620, edi
0x18000580c  jmp     short loc_1800057CE
0x18000580e  cmp     cs:gbLookupTableInitialized, 1
0x180005815  jz      short loc_1800057CE
0x180005817  mov     [rsp+60h+arg_0], rsi
0x18000581f  mov     [rsp+60h+arg_8], r14
0x180005827  mov     [rsp+60h+arg_10], r15
0x18000582f  call    CacheDomainAndDnsDomainSids
0x180005834  xor     edi, edi
0x180005836  lea     r15, __ImageBase
0x18000583d  nop     dword ptr [rax]
0x180005840  imul    rsi, rdi, 68h ; 'h'
0x180005844  cmp     bl, 1
0x180005847  jnz     short loc_180005852
0x180005849  mov     byte ptr [rsi+r15+79EE0h], 0
0x180005852  lea     r14, rva qword_180079EF0[r15]
0x180005859  add     r14, rsi
0x18000585c  cmp     byte ptr [rsi+r15+79EE0h], 1
0x180005865  jz      loc_1800059D7
0x18000586b  movsxd  rax, dword ptr [rsi+r15+79EFCh]
0x180005873  lea     r9, rva qword_180079F00[r15]
0x18000587a  add     r9, rsi
0x18000587d  mov     [r14], r9
0x180005880  cmp     eax, 0Bh; switch 12 cases
0x180005883  jbe     short loc_1800058C9
0x180005885  inc     rdi; jumptable 00000001800058D4 default case, case 7
0x180005888  cmp     rdi, 44h ; 'D'
0x18000588c  jnz     short loc_180005840
0x18000588e  cmp     cs:gbLsaLookupSucceeded, 0
0x180005895  mov     r15, [rsp+60h+arg_10]
0x18000589d  mov     r14, [rsp+60h+arg_8]
0x1800058a5  mov     rsi, [rsp+60h+arg_0]
0x1800058ad  jz      loc_1800057CE
0x1800058b3  mov     cs:gbLookupTableInitialized, 1
0x1800058bd  jmp     loc_1800057CE
0x1800058c2  xor     edi, edi
0x1800058c4  jmp     loc_180005806
0x1800058c9  mov     ecx, ds:(jpt_1800058D4 - 180000000h)[r15+rax*4]
0x1800058d1  add     rcx, r15
0x1800058d4  jmp     rcx; switch jump
0x1800058d6  lea     rdx, [rbp+IdentifierAuthority]; jumptable 00000001800058D4 case 11
0x1800058da  mov     r8b, 1; SubAuthorityCount
0x1800058dd  mov     rcx, r9; Sid
0x1800058e0  call    cs:__imp_RtlInitializeSid
0x1800058e6  xor     edx, edx; SubAuthority
0x1800058e8  mov     rcx, [r14]; Sid
0x1800058eb  call    cs:__imp_RtlSubAuthoritySid
0x1800058f1  mov     ecx, [rsi+r15+79EF8h]
0x1800058f9  mov     [rax], ecx
0x1800058fb  mov     byte ptr [rsi+r15+79EE0h], 1
0x180005904  jmp     def_1800058D4; jumptable 00000001800058D4 default case, case 7
0x180005909  cmp     cs:gbDnsDomainSidCached, 0; jumptable 00000001800058D4 case 0
0x180005910  jz      def_1800058D4; jumptable 00000001800058D4 default case, case 7
0x180005916  mov     rcx, cs:Sid; Sid
0x18000591d  call    cs:__imp_RtlLengthSid
0x180005923  mov     rdx, cs:Sid; Src
0x18000592a  mov     rcx, [r14]; void *
0x18000592d  mov     r8d, eax; Size
0x180005930  call    memcpy_0
0x180005935  mov     rax, [r14]
0x180005938  inc     byte ptr [rax+1]
0x18000593b  mov     rcx, cs:Sid; Sid
0x180005942  call    cs:__imp_RtlSubAuthorityCountSid
0x180005948  movzx   edx, byte ptr [rax]
0x18000594b  jmp     short loc_1800058E8
0x18000594d  lea     rdx, [rbp+var_38]; jumptable 00000001800058D4 case 1
0x180005951  jmp     short loc_1800058DA
0x180005953  mov     r8b, 2; jumptable 00000001800058D4 case 6
0x180005956  lea     rdx, [rbp+var_40]; IdentifierAuthority
0x18000595a  mov     rcx, r9; Sid
0x18000595d  call    cs:__imp_RtlInitializeSid
0x180005963  mov     rcx, [r14]; Sid
0x180005966  xor     edx, edx; SubAuthority
0x180005968  call    cs:__imp_RtlSubAuthoritySid
0x18000596e  mov     edx, 1
0x180005973  mov     dword ptr [rax], 20h ; ' '
0x180005979  jmp     loc_1800058E8
0x18000597e  cmp     cs:gbDomainSidCached, 0; jumptable 00000001800058D4 case 3
0x180005985  jz      def_1800058D4; jumptable 00000001800058D4 default case, case 7
0x18000598b  mov     rcx, cs:Src; Sid
0x180005992  call    cs:__imp_RtlLengthSid
0x180005998  mov     rdx, cs:Src; Src
0x18000599f  mov     rcx, [r14]; void *
0x1800059a2  mov     r8d, eax; Size
0x1800059a5  call    memcpy_0
0x1800059aa  mov     rax, [r14]
0x1800059ad  inc     byte ptr [rax+1]
0x1800059b0  mov     rcx, cs:Src; Sid
0x1800059b7  call    cs:__imp_RtlSubAuthorityCountSid
0x1800059bd  movzx   edx, byte ptr [rax]
0x1800059c0  jmp     loc_1800058E8
0x1800059c5  lea     rdx, [rbp+var_40]; jumptable 00000001800058D4 case 5
0x1800059c9  jmp     loc_1800058DA
0x1800059ce  lea     rdx, [rbp+var_20]; jumptable 00000001800058D4 case 8
0x1800059d2  jmp     loc_1800058DA
0x1800059d7  cmp     qword ptr [r14], 0
0x1800059db  jnz     def_1800058D4; jumptable 00000001800058D4 default case, case 7
0x1800059e1  jmp     loc_18000586B
0x1800059e6  lea     rdx, [rbp+var_30]; jumptable 00000001800058D4 case 2
0x1800059ea  jmp     loc_1800058DA
0x1800059ef  lea     rdx, [rbp+var_28]; jumptable 00000001800058D4 case 4
0x1800059f3  jmp     loc_1800058DA
0x1800059f8  mov     r8b, 2; jumptable 00000001800058D4 case 9
0x1800059fb  lea     rdx, [rbp+var_18]; IdentifierAuthority
0x1800059ff  mov     rcx, r9; Sid
0x180005a02  call    cs:__imp_RtlInitializeSid
0x180005a08  mov     rcx, [r14]; Sid
0x180005a0b  xor     edx, edx; SubAuthority
0x180005a0d  call    cs:__imp_RtlSubAuthoritySid
0x180005a13  mov     edx, 1
0x180005a18  mov     dword ptr [rax], 2
0x180005a1e  jmp     loc_1800058E8
0x180005a23  mov     r8b, 6; jumptable 00000001800058D4 case 10
0x180005a26  lea     rdx, [rbp+var_40]; IdentifierAuthority
0x180005a2a  mov     rcx, r9; Sid
0x180005a2d  call    cs:__imp_RtlInitializeSid
0x180005a33  mov     rcx, [r14]; Sid
0x180005a36  xor     edx, edx; SubAuthority
0x180005a38  call    cs:__imp_RtlSubAuthoritySid
0x180005a3e  mov     edx, 1; SubAuthority
0x180005a43  mov     dword ptr [rax], 54h ; 'T'
0x180005a49  mov     rcx, [r14]; Sid
0x180005a4c  call    cs:__imp_RtlSubAuthoritySid
0x180005a52  xorps   xmm0, xmm0
0x180005a55  xor     ecx, ecx
0x180005a57  movups  xmmword ptr [rax], xmm0
0x180005a5a  mov     [rax+10h], ecx
0x180005a5d  jmp     loc_1800058FB
```
