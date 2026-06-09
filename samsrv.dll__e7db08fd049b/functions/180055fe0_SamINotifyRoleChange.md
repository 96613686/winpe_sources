# SamINotifyRoleChange

- ea: `0x180055fe0`
- end: `0x180056263`
- name: `SamINotifyRoleChange`
- size: `643`
- prototype: `__int64 __fastcall(PSID Sid2)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800243e0`
- `0x1800270e0`
- `0x180027e24`
- `0x18002cd80`
- `0x180037284`
- `0x180055fe0`
- `0x180065b60`
- `0x1800b03d0`

## import_xrefs

- `ntdll!RtlEqualSid` at `0x180056070`
- `ntdll!RtlEqualSid` at `0x180056070`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x1800561bc`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x1800561bc`
- `LSASRV!LsaINotifyChangeNotification` at `0x180056200`
- `LSASRV!LsaINotifyChangeNotification` at `0x180056200`
- `LSASRV!LsaIRegisterNotification` at `0x180056188`
- `LSASRV!LsaIRegisterNotification` at `0x180056188`
- `NETLOGON!I_NetNotifyRole` at `0x180056191`
- `NETLOGON!I_NetNotifyRole` at `0x180056191`

## pseudocode

```c
__int64 __fastcall SamINotifyRoleChange(PSID Sid2, int a2)
{
  unsigned int v4; // ebx
  unsigned int v5; // r12d
  unsigned int PrimaryDomainStart; // edi
  char v7; // r15
  __int64 v8; // r14
  struct _PSAMP_DEFINED_DOMAINS *v9; // rdx
  int v10; // eax
  PUNICODE_STRING v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // rax
  __int64 v14; // r9
  DWORD nSize; // [rsp+40h] [rbp-19h] BYREF
  __int16 v17; // [rsp+48h] [rbp-11h] BYREF
  int v18; // [rsp+4Ah] [rbp-Fh]
  __int16 v19; // [rsp+4Eh] [rbp-Bh]
  WCHAR *v20; // [rsp+50h] [rbp-9h]
  WCHAR Buffer[8]; // [rsp+58h] [rbp-1h] BYREF
  __int128 v22; // [rsp+68h] [rbp+Fh]
  __int16 v23; // [rsp+78h] [rbp+1Fh]

  nSize = 0;
  if ( a2 == 2 )
  {
    v5 = 2;
  }
  else
  {
    if ( a2 != 3 )
    {
LABEL_3:
      v4 = -1073741811;
      goto LABEL_30;
    }
    v5 = 3;
  }
  PrimaryDomainStart = SampDsGetPrimaryDomainStart();
  if ( PrimaryDomainStart >= SampDefinedDomainsCount )
    goto LABEL_29;
  v7 = 1;
  do
  {
    if ( RtlEqualSid(*((PSID *)SampDefinedDomains + 170 * PrimaryDomainStart + 1), Sid2) )
      break;
    ++PrimaryDomainStart;
  }
  while ( PrimaryDomainStart < SampDefinedDomainsCount );
  if ( PrimaryDomainStart >= SampDefinedDomainsCount )
  {
LABEL_29:
    v4 = -1073741601;
    goto LABEL_30;
  }
  v8 = 1360LL * PrimaryDomainStart;
  if ( *((_BYTE *)SampDefinedDomains + v8 + 1296) )
    goto LABEL_3;
  v4 = 0;
  SampAcquireWriteLock(*(_QWORD *)((char *)SampDefinedDomains + v8));
  v9 = SampDefinedDomains;
  v10 = *(_DWORD *)((char *)SampDefinedDomains + v8 + 1308);
  if ( v10 == 2 && a2 == 3 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20) == 0 || HIBYTE(WPP_GLOBAL_Control[4].Length) < 4u )
      goto LABEL_23;
    v12 = 25;
  }
  else
  {
    v7 = 0;
    if ( v10 != 3 )
      goto LABEL_23;
    if ( a2 != 2 )
      goto LABEL_23;
    v11 = WPP_GLOBAL_Control;
    if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20) == 0 || HIBYTE(WPP_GLOBAL_Control[4].Length) < 4u )
      goto LABEL_23;
    v12 = 26;
  }
  WPP_SF_(v11[3].Buffer, v12, &WPP_24d3cb53f35333e5462bba9dfbf11e25_Traceguids);
  v9 = SampDefinedDomains;
LABEL_23:
  *(_DWORD *)((char *)v9 + v8 + 1308) = a2;
  v13 = 1360LL * (PrimaryDomainStart - 1);
  *(_DWORD *)((char *)v9 + v8 + 220) = a2;
  *(_DWORD *)((char *)v9 + v8 + 588) = a2;
  *(_DWORD *)((char *)v9 + v13 + 1308) = a2;
  *(_DWORD *)((char *)v9 + v13 + 220) = a2;
  *(_DWORD *)((char *)v9 + v13 + 588) = a2;
  SampReleaseWriteLock(0);
  if ( v7 )
    LsaIRegisterNotification(SampDoAccountsUpgradeDuringPDCTransfer, 0, 16, 0, 2, 0, 0);
  I_NetNotifyRole(v5);
  if ( a2 == 3 )
  {
    nSize = 17;
    v23 = 0;
    *(_OWORD *)Buffer = 0;
    v22 = 0;
    if ( GetComputerNameW(Buffer, &nSize) )
    {
      v19 = 0;
      v20 = Buffer;
      v18 = (unsigned __int16)(2 * nSize);
      v17 = 2 * nSize;
      SampWriteEventLog(SAMMSG_PROMOTED_TO_PDC, L"u", &v17, v14);
    }
  }
  LsaINotifyChangeNotification(3);
LABEL_30:
  if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
    WPP_SF_Dd(WPP_GLOBAL_Control[3].Buffer, 27, &WPP_24d3cb53f35333e5462bba9dfbf11e25_Traceguids, v4, v4);
  return v4;
}

```

## disassembly

```asm
0x180055fe0  mov     [rsp-8+arg_8], rbx
0x180055fe5  mov     [rsp-8+arg_10], rsi
0x180055fea  push    rbp
0x180055feb  push    rdi
0x180055fec  push    r12
0x180055fee  push    r14
0x180055ff0  push    r15
0x180055ff2  lea     rbp, [rsp-37h]
0x180055ff7  sub     rsp, 90h
0x180055ffe  mov     rax, cs:__security_cookie
0x180056005  xor     rax, rsp
0x180056008  mov     [rbp+57h+var_30], rax
0x18005600c  mov     r8d, edx
0x18005600f  mov     [rbp+57h+nSize], 0
0x180056016  mov     esi, edx
0x180056018  mov     rbx, rcx
0x18005601b  sub     r8d, 2
0x18005601f  jz      short loc_180056039
0x180056021  cmp     r8d, 1
0x180056025  jz      short loc_180056031
0x180056027  mov     ebx, 0C000000Dh
0x18005602c  jmp     loc_18005620D
0x180056031  mov     r12d, 3
0x180056037  jmp     short loc_18005603F
0x180056039  mov     r12d, 2
0x18005603f  call    SampDsGetPrimaryDomainStart
0x180056044  cmp     eax, cs:?SampDefinedDomainsCount@@3KA; ulong SampDefinedDomainsCount
0x18005604a  mov     edi, eax
0x18005604c  jnb     loc_180056208
0x180056052  mov     r15d, 1
0x180056058  mov     rcx, cs:?SampDefinedDomains@@3PEAU_PSAMP_DEFINED_DOMAINS@@EA; _PSAMP_DEFINED_DOMAINS * SampDefinedDomains
0x18005605f  mov     rdx, rbx; Sid2
0x180056062  mov     eax, edi
0x180056064  imul    r8, rax, 550h
0x18005606b  mov     rcx, [r8+rcx+8]; Sid1
0x180056070  call    cs:__imp_RtlEqualSid
0x180056076  mov     ecx, cs:?SampDefinedDomainsCount@@3KA; ulong SampDefinedDomainsCount
0x18005607c  test    al, al
0x18005607e  jnz     short loc_180056087
0x180056080  add     edi, r15d
0x180056083  cmp     edi, ecx
0x180056085  jb      short loc_180056058
0x180056087  cmp     edi, ecx
0x180056089  jnb     loc_180056208
0x18005608f  mov     rcx, cs:?SampDefinedDomains@@3PEAU_PSAMP_DEFINED_DOMAINS@@EA; _PSAMP_DEFINED_DOMAINS * SampDefinedDomains
0x180056096  mov     eax, edi
0x180056098  imul    r14, rax, 550h
0x18005609f  cmp     byte ptr [r14+rcx+510h], 0
0x1800560a8  jnz     loc_180056027
0x1800560ae  mov     rcx, [r14+rcx]
0x1800560b2  xor     ebx, ebx
0x1800560b4  call    SampAcquireWriteLock
0x1800560b9  mov     rdx, cs:?SampDefinedDomains@@3PEAU_PSAMP_DEFINED_DOMAINS@@EA; _PSAMP_DEFINED_DOMAINS * SampDefinedDomains
0x1800560c0  mov     eax, [r14+rdx+51Ch]
0x1800560c8  cmp     eax, 2
0x1800560cb  jnz     short loc_1800560EA
0x1800560cd  cmp     esi, 3
0x1800560d0  jnz     short loc_1800560EA
0x1800560d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800560d9  test    byte ptr [rcx+44h], 20h
0x1800560dd  jz      short loc_180056124
0x1800560df  cmp     byte ptr [rcx+41h], 4
0x1800560e3  jb      short loc_180056124
0x1800560e5  lea     edx, [rbx+19h]
0x1800560e8  jmp     short loc_18005610D
0x1800560ea  xor     r15b, r15b
0x1800560ed  cmp     eax, 3
0x1800560f0  jnz     short loc_180056124
0x1800560f2  cmp     esi, 2
0x1800560f5  jnz     short loc_180056124
0x1800560f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800560fe  test    byte ptr [rcx+44h], 20h
0x180056102  jz      short loc_180056124
0x180056104  cmp     byte ptr [rcx+41h], 4
0x180056108  jb      short loc_180056124
0x18005610a  lea     edx, [rax+17h]
0x18005610d  mov     rcx, [rcx+38h]
0x180056111  lea     r8, WPP_24d3cb53f35333e5462bba9dfbf11e25_Traceguids
0x180056118  call    WPP_SF_
0x18005611d  mov     rdx, cs:?SampDefinedDomains@@3PEAU_PSAMP_DEFINED_DOMAINS@@EA; _PSAMP_DEFINED_DOMAINS * SampDefinedDomains
0x180056124  lea     ecx, [rdi-1]
0x180056127  mov     [r14+rdx+51Ch], esi
0x18005612f  imul    rax, rcx, 550h
0x180056136  xor     ecx, ecx
0x180056138  mov     [r14+rdx+0DCh], esi
0x180056140  mov     [r14+rdx+24Ch], esi
0x180056148  mov     [rax+rdx+51Ch], esi
0x18005614f  mov     [rax+rdx+0DCh], esi
0x180056156  mov     [rax+rdx+24Ch], esi
0x18005615d  call    SampReleaseWriteLock
0x180056162  test    r15b, r15b
0x180056165  jz      short loc_18005618E
0x180056167  xor     r9d, r9d
0x18005616a  mov     [rsp+0B0h+var_80], rbx
0x18005616f  mov     [rsp+0B0h+var_88], ebx
0x180056173  lea     rcx, ?SampDoAccountsUpgradeDuringPDCTransfer@@YAJPEAX@Z; SampDoAccountsUpgradeDuringPDCTransfer(void *)
0x18005617a  xor     edx, edx
0x18005617c  mov     [rsp+0B0h+var_90], 2
0x180056184  lea     r8d, [r9+10h]
0x180056188  call    cs:__imp_LsaIRegisterNotification
0x18005618e  mov     ecx, r12d
0x180056191  call    cs:__imp_I_NetNotifyRole
0x180056197  cmp     esi, 3
0x18005619a  jnz     short loc_1800561FB
0x18005619c  xorps   xmm0, xmm0
0x18005619f  mov     [rbp+57h+nSize], 11h
0x1800561a6  xor     eax, eax
0x1800561a8  lea     rdx, [rbp+57h+nSize]; nSize
0x1800561ac  lea     rcx, [rbp+57h+Buffer]; lpBuffer
0x1800561b0  mov     [rbp+57h+var_38], ax
0x1800561b4  movups  xmmword ptr [rbp+57h+Buffer], xmm0
0x1800561b8  movups  [rbp+57h+var_48], xmm0
0x1800561bc  call    cs:__imp_GetComputerNameW
0x1800561c2  test    eax, eax
0x1800561c4  jz      short loc_1800561FB
0x1800561c6  lea     rax, [rbp+57h+Buffer]
0x1800561ca  xorps   xmm0, xmm0
0x1800561cd  movups  [rbp+57h+var_68], xmm0
0x1800561d1  mov     qword ptr [rbp+57h+var_68+8], rax
0x1800561d5  lea     r8, [rbp+57h+var_68]
0x1800561d9  movzx   eax, word ptr [rbp+57h+nSize]
0x1800561dd  lea     rdx, aU; "u"
0x1800561e4  add     ax, ax
0x1800561e7  lea     rcx, SAMMSG_PROMOTED_TO_PDC
0x1800561ee  mov     word ptr [rbp+57h+var_68+2], ax
0x1800561f2  mov     word ptr [rbp+57h+var_68], ax
0x1800561f6  call    SampWriteEventLog
0x1800561fb  mov     ecx, 3
0x180056200  call    cs:__imp_LsaINotifyChangeNotification
0x180056206  jmp     short loc_18005620D
0x180056208  mov     ebx, 0C00000DFh
0x18005620d  mov     rcx, cs:WPP_GLOBAL_Control
0x180056214  test    dword ptr [rcx+44h], 20000h
0x18005621b  jz      short loc_180056239
0x18005621d  mov     rcx, [rcx+38h]
0x180056221  lea     r8, WPP_24d3cb53f35333e5462bba9dfbf11e25_Traceguids
0x180056228  mov     edx, 1Bh
0x18005622d  mov     [rsp+0B0h+var_90], ebx
0x180056231  mov     r9d, ebx
0x180056234  call    WPP_SF_Dd
0x180056239  mov     eax, ebx
0x18005623b  mov     rcx, [rbp+57h+var_30]
0x18005623f  xor     rcx, rsp; StackCookie
0x180056242  call    __security_check_cookie
0x180056247  lea     r11, [rsp+0B0h+var_20]
0x18005624f  mov     rbx, [r11+38h]
0x180056253  mov     rsi, [r11+40h]
0x180056257  mov     rsp, r11
0x18005625a  pop     r15
0x18005625c  pop     r14
0x18005625e  pop     r12
0x180056260  pop     rdi
0x180056261  pop     rbp
0x180056262  retn
```
