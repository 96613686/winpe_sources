# DoSaclWorkForUserMode(_ACL * const,_ACL * *)

- ea: `0x1800252f0`
- end: `0x1800255b4`
- name: `?DoSaclWorkForUserMode@@YAJQEAU_ACL@@PEAPEAU1@@Z`
- size: `708`
- prototype: `__int64 __fastcall(PACL pAcl, struct _ACL **)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180023978`

## callees

- `0x180008370`
- `0x1800252f0`
- `0x1800272fc`
- `0x180027a9c`
- `0x180072e08`
- `0x180072f14`
- `0x1800935fc`
- `0x1800cf5c0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x180025450`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x180025450`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x180025396`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x180025396`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x1800254ad`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x1800254ad`
- `ole32!CoTaskMemFree` at `0x180025474`
- `ole32!CoTaskMemFree` at `0x180025474`
- `ole32!CoTaskMemAlloc` at `0x180025423`
- `ole32!CoTaskMemAlloc` at `0x180025423`

## string_xrefs

- `0x18002532e`: `DoSaclWorkForUserMode`

## pseudocode

```c
__int64 __fastcall DoSaclWorkForUserMode(PACL pAcl, struct _ACL **a2)
{
  DWORD v4; // r14d
  __int16 v5; // ax
  __int64 v6; // rcx
  __int64 v7; // r9
  int LastFailureAsHRESULT; // ebx
  DWORD v9; // r15d
  DWORD v10; // ebx
  struct _ACL *v11; // rsi
  __int64 v12; // rcx
  __int16 v13; // ax
  int v14; // r13d
  __int64 v15; // rcx
  BYTE v17; // [rsp+30h] [rbp-49h]
  int v18; // [rsp+34h] [rbp-45h] BYREF
  int v19; // [rsp+38h] [rbp-41h] BYREF
  __int16 v20; // [rsp+3Ch] [rbp-3Dh]
  __int16 v21; // [rsp+3Eh] [rbp-3Bh]
  LPVOID pAce; // [rsp+70h] [rbp-9h] BYREF
  _BYTE *v23; // [rsp+78h] [rbp-1h]
  __int64 pAclInformation; // [rsp+80h] [rbp+7h] BYREF
  int v25; // [rsp+88h] [rbp+Fh]

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v19, "DoSaclWorkForUserMode", 0x1A9u, 1u);
  pAclInformation = 0;
  v25 = 0;
  v4 = 0;
  pAce = 0;
  v18 = 0;
  if ( a2 )
    *a2 = 0;
  v5 = 441;
  if ( !pAcl || (v20 = 441, v5 = 442, !a2) )
  {
    LastFailureAsHRESULT = -2147024809;
    goto LABEL_30;
  }
  v19 = 0;
  v20 = 442;
  if ( !GetAclInformation(pAcl, &pAclInformation, 0xCu, AclSizeInformation) )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v6);
    v19 = LastFailureAsHRESULT;
    v5 = 444;
LABEL_31:
    v21 = v5;
    goto LABEL_32;
  }
  v19 = 0;
  v20 = 444;
  v9 = pAclInformation;
  v10 = 80 * pAclInformation + 8;
  if ( v10 > 0xFFFC )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_052bc5b66f273e09fada3dec80af9ee3_Traceguids, v7);
    *a2 = 0;
    LastFailureAsHRESULT = 1;
    v19 = 1;
    v20 = 457;
    goto LABEL_32;
  }
  v11 = (struct _ACL *)CoTaskMemAlloc(v10);
  v5 = 461;
  if ( !v11 )
  {
    LastFailureAsHRESULT = -2147024882;
LABEL_30:
    v19 = LastFailureAsHRESULT;
    goto LABEL_31;
  }
  v19 = 0;
  v20 = 461;
  if ( InitializeAcl(v11, v10, 2u) )
  {
    v14 = 0;
    LastFailureAsHRESULT = 0;
    v19 = 0;
    v20 = 464;
    while ( v4 < v9 )
    {
      if ( !GetAce(pAcl, v4, &pAce) )
      {
        v19 = GetLastFailureAsHRESULT(v15);
        v13 = 469;
        goto LABEL_15;
      }
      v19 = 0;
      v20 = 469;
      v23 = pAce;
      v17 = *(_BYTE *)pAce;
      LastFailureAsHRESULT = IsSaclAceInteresting(pAce, *(_BYTE *)pAce, &v18);
      v19 = LastFailureAsHRESULT;
      v13 = 472;
      if ( LastFailureAsHRESULT < 0 )
        goto LABEL_15;
      v20 = 472;
      if ( v18 )
      {
        LastFailureAsHRESULT = SxAddKnownAce(v11, v23[1], *((_DWORD *)pAce + 1), (char *)pAce + 8, v17);
        v19 = LastFailureAsHRESULT;
        v13 = 475;
        if ( LastFailureAsHRESULT < 0 )
          goto LABEL_15;
        v20 = 475;
        v14 = 1;
      }
      ++v4;
    }
    if ( v14 )
    {
      *a2 = v11;
      goto LABEL_32;
    }
  }
  else
  {
    v19 = GetLastFailureAsHRESULT(v12);
    v13 = 464;
LABEL_15:
    v21 = v13;
  }
  CoTaskMemFree(v11);
  LastFailureAsHRESULT = v19;
LABEL_32:
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v19);
  return (unsigned int)LastFailureAsHRESULT;
}

```

## disassembly

```asm
0x1800252f0  mov     [rsp-8+arg_10], rbx
0x1800252f5  push    rbp
0x1800252f6  push    rsi
0x1800252f7  push    rdi
0x1800252f8  push    r12
0x1800252fa  push    r13
0x1800252fc  push    r14
0x1800252fe  push    r15
0x180025300  lea     rbp, [rsp-27h]
0x180025305  sub     rsp, 0A0h
0x18002530c  mov     rax, cs:__security_cookie
0x180025313  xor     rax, rsp
0x180025316  mov     [rbp+57h+var_40], rax
0x18002531a  mov     rdi, rdx
0x18002531d  mov     r12, rcx
0x180025320  mov     esi, 1
0x180025325  mov     r9d, esi; unsigned __int16
0x180025328  mov     r8d, 1A9h; unsigned __int16
0x18002532e  lea     rdx, aDosaclworkforu; "DoSaclWorkForUserMode"
0x180025335  lea     rcx, [rbp+57h+var_98]; this
0x180025339  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18002533e  xor     eax, eax
0x180025340  mov     [rbp+57h+pAclInformation], rax
0x180025344  mov     [rbp+57h+var_48], eax
0x180025347  xor     r14d, r14d
0x18002534a  mov     [rbp+57h+pAce], r14
0x18002534e  mov     [rbp+57h+var_9C], r14d
0x180025352  test    rdi, rdi
0x180025355  jz      short loc_18002535A
0x180025357  mov     [rdi], r14
0x18002535a  mov     eax, 1B9h
0x18002535f  test    r12, r12
0x180025362  jz      loc_180025575
0x180025368  mov     [rbp+57h+var_94], ax
0x18002536c  mov     eax, 1BAh
0x180025371  test    rdi, rdi
0x180025374  jz      loc_180025575
0x18002537a  mov     [rbp+57h+var_98], r14d
0x18002537e  mov     [rbp+57h+var_94], ax
0x180025382  mov     r13d, 2
0x180025388  mov     r9d, r13d; dwAclInformationClass
0x18002538b  lea     r8d, [r13+0Ah]; nAclInformationLength
0x18002538f  lea     rdx, [rbp+57h+pAclInformation]; pAclInformation
0x180025393  mov     rcx, r12; pAcl
0x180025396  call    cs:__imp_GetAclInformation
0x18002539d  nop     dword ptr [rax+rax+00h]
0x1800253a2  test    eax, eax
0x1800253a4  jnz     short loc_1800253BA
0x1800253a6  call    GetLastFailureAsHRESULT
0x1800253ab  mov     ebx, eax
0x1800253ad  mov     [rbp+57h+var_98], eax
0x1800253b0  mov     eax, 1BCh
0x1800253b5  jmp     loc_18002557D
0x1800253ba  mov     [rbp+57h+var_98], r14d
0x1800253be  mov     eax, 1BCh
0x1800253c3  mov     [rbp+57h+var_94], ax
0x1800253c7  mov     r15d, dword ptr [rbp+57h+pAclInformation]
0x1800253cb  lea     ebx, [r15+r15*4]
0x1800253cf  shl     ebx, 4
0x1800253d2  add     ebx, 8
0x1800253d5  cmp     ebx, 0FFFCh
0x1800253db  jbe     short loc_180025421
0x1800253dd  lea     rax, WPP_GLOBAL_Control
0x1800253e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800253eb  cmp     rcx, rax
0x1800253ee  jz      short loc_18002540B
0x1800253f0  test    [rcx+1Ch], r13b
0x1800253f4  jz      short loc_18002540B
0x1800253f6  mov     edx, 13h
0x1800253fb  lea     r8, WPP_052bc5b66f273e09fada3dec80af9ee3_Traceguids
0x180025402  mov     rcx, [rcx+10h]
0x180025406  call    WPP_SF_
0x18002540b  mov     [rdi], r14
0x18002540e  mov     ebx, esi
0x180025410  mov     [rbp+57h+var_98], ebx
0x180025413  mov     eax, 1C9h
0x180025418  mov     [rbp+57h+var_94], ax
0x18002541c  jmp     loc_180025581
0x180025421  mov     ecx, ebx; cb
0x180025423  call    cs:__imp_CoTaskMemAlloc
0x18002542a  nop     dword ptr [rax+rax+00h]
0x18002542f  mov     rsi, rax
0x180025432  test    rax, rax
0x180025435  mov     eax, 1CDh
0x18002543a  jz      loc_18002556E
0x180025440  mov     [rbp+57h+var_98], r14d
0x180025444  mov     [rbp+57h+var_94], ax
0x180025448  mov     r8d, r13d; dwAclRevision
0x18002544b  mov     edx, ebx; nAclLength
0x18002544d  mov     rcx, rsi; pAcl
0x180025450  call    cs:__imp_InitializeAcl
0x180025457  nop     dword ptr [rax+rax+00h]
0x18002545c  test    eax, eax
0x18002545e  jnz     short loc_180025488
0x180025460  call    GetLastFailureAsHRESULT
0x180025465  mov     [rbp+57h+var_98], eax
0x180025468  mov     eax, 1D0h
0x18002546d  mov     [rbp+57h+var_92], ax
0x180025471  mov     rcx, rsi; pv
0x180025474  call    cs:__imp_CoTaskMemFree
0x18002547b  nop     dword ptr [rax+rax+00h]
0x180025480  mov     ebx, [rbp+57h+var_98]
0x180025483  jmp     loc_180025581
0x180025488  mov     r13d, r14d
0x18002548b  mov     ebx, r14d
0x18002548e  mov     [rbp+57h+var_98], ebx
0x180025491  mov     eax, 1D0h
0x180025496  mov     [rbp+57h+var_94], ax
0x18002549a  cmp     r14d, r15d
0x18002549d  jnb     loc_180025560
0x1800254a3  lea     r8, [rbp+57h+pAce]; pAce
0x1800254a7  mov     edx, r14d; dwAceIndex
0x1800254aa  mov     rcx, r12; pAcl
0x1800254ad  call    cs:__imp_GetAce
0x1800254b4  nop     dword ptr [rax+rax+00h]
0x1800254b9  test    eax, eax
0x1800254bb  jz      loc_18002554E
0x1800254c1  mov     [rbp+57h+var_98], 0
0x1800254c8  mov     eax, 1D5h
0x1800254cd  mov     [rbp+57h+var_94], ax
0x1800254d1  mov     rax, [rbp+57h+pAce]
0x1800254d5  mov     [rbp+57h+var_58], rax
0x1800254d9  mov     cl, [rax]
0x1800254db  mov     [rbp+57h+var_A0], cl
0x1800254de  lea     r8, [rbp+57h+var_9C]; int *
0x1800254e2  mov     dl, cl; unsigned __int8
0x1800254e4  mov     rcx, rax; void *
0x1800254e7  call    ?IsSaclAceInteresting@@YAJPEAXEPEAH@Z; IsSaclAceInteresting(void *,uchar,int *)
0x1800254ec  mov     ebx, eax
0x1800254ee  mov     [rbp+57h+var_98], eax
0x1800254f1  test    eax, eax
0x1800254f3  mov     eax, 1D8h
0x1800254f8  js      loc_18002546D
0x1800254fe  mov     [rbp+57h+var_94], ax
0x180025502  cmp     [rbp+57h+var_9C], 0
0x180025506  jz      short loc_180025546
0x180025508  mov     r8, [rbp+57h+pAce]
0x18002550c  lea     r9, [r8+8]; void *
0x180025510  mov     al, [rbp+57h+var_A0]
0x180025513  mov     [rsp+0D0h+var_B0], al; unsigned __int8
0x180025517  mov     r8d, [r8+4]; unsigned int
0x18002551b  mov     rdx, [rbp+57h+var_58]
0x18002551f  mov     dl, [rdx+1]; unsigned __int8
0x180025522  mov     rcx, rsi; pAcl
0x180025525  call    ?SxAddKnownAce@@YAJPEAU_ACL@@EKQEAXE@Z; SxAddKnownAce(_ACL *,uchar,ulong,void * const,uchar)
0x18002552a  mov     ebx, eax
0x18002552c  mov     [rbp+57h+var_98], eax
0x18002552f  test    eax, eax
0x180025531  mov     eax, 1DBh
0x180025536  js      loc_18002546D
0x18002553c  mov     [rbp+57h+var_94], ax
0x180025540  mov     r13d, 1
0x180025546  inc     r14d
0x180025549  jmp     loc_18002549A
0x18002554e  call    GetLastFailureAsHRESULT
0x180025553  mov     [rbp+57h+var_98], eax
0x180025556  mov     eax, 1D5h
0x18002555b  jmp     loc_18002546D
0x180025560  test    r13d, r13d
0x180025563  jz      loc_180025471
0x180025569  mov     [rdi], rsi
0x18002556c  jmp     short loc_180025581
0x18002556e  mov     ebx, 8007000Eh
0x180025573  jmp     short loc_18002557A
0x180025575  mov     ebx, 80070057h
0x18002557a  mov     [rbp+57h+var_98], ebx
0x18002557d  mov     [rbp+57h+var_92], ax
0x180025581  lea     rcx, [rbp+57h+var_98]; this
0x180025585  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18002558a  mov     eax, ebx
0x18002558c  mov     rcx, [rbp+57h+var_40]
0x180025590  xor     rcx, rsp; StackCookie
0x180025593  call    __security_check_cookie
0x180025598  mov     rbx, [rsp+0D0h+arg_10]
0x1800255a0  add     rsp, 0A0h
0x1800255a7  pop     r15
0x1800255a9  pop     r14
0x1800255ab  pop     r13
0x1800255ad  pop     r12
0x1800255af  pop     rdi
0x1800255b0  pop     rsi
0x1800255b1  pop     rbp
0x1800255b2  retn
```
