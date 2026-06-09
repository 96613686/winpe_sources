# DuplicateRestorerFullAccessDacl(_SID const *,_ACL * const,_ACL * *)

- ea: `0x180025c68`
- end: `0x180025f1b`
- name: `?DuplicateRestorerFullAccessDacl@@YAJPEBU_SID@@QEAU_ACL@@PEAPEAU2@@Z`
- size: `691`
- prototype: `__int64 __fastcall(PSID pSid, PACL pAcl, struct _ACL **)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180023978`

## callees

- `0x180008370`
- `0x180025c68`
- `0x180027a9c`
- `0x180072e08`
- `0x180072f14`
- `0x1800935fc`
- `0x1800cf5c0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180025e15`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180025e15`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x180025dd4`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x180025dd4`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x180025d16`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x180025d16`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x180025e65`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x180025e65`
- `ole32!CoTaskMemFree` at `0x180025ee2`
- `ole32!CoTaskMemFree` at `0x180025ee2`
- `ole32!CoTaskMemAlloc` at `0x180025d52`
- `ole32!CoTaskMemAlloc` at `0x180025d52`

## string_xrefs

- `0x180025ca2`: `DuplicateRestorerFullAccessDacl`

## pseudocode

```c
__int64 __fastcall DuplicateRestorerFullAccessDacl(PSID pSid, PACL pAcl, struct _ACL **a3)
{
  struct _ACL *v6; // rbx
  __int16 v7; // ax
  __int64 v8; // rcx
  DWORD v9; // edi
  __int64 v10; // r9
  __int64 v11; // rcx
  __int64 v12; // rcx
  DWORD i; // edi
  __int64 v14; // rcx
  unsigned int v15; // ebx
  int LastFailureAsHRESULT; // [rsp+30h] [rbp-39h] BYREF
  __int16 v18; // [rsp+34h] [rbp-35h]
  __int16 v19; // [rsp+36h] [rbp-33h]
  LPVOID pAce; // [rsp+68h] [rbp-1h] BYREF
  __int64 pAclInformation; // [rsp+70h] [rbp+7h] BYREF
  int v22; // [rsp+78h] [rbp+Fh]

  CSxFunctionTracer::CSxFunctionTracer(
    (CSxFunctionTracer *)&LastFailureAsHRESULT,
    "DuplicateRestorerFullAccessDacl",
    0x2C8u,
    1u);
  pAclInformation = 0;
  v22 = 0;
  v6 = 0;
  pAce = 0;
  if ( a3 )
    *a3 = 0;
  v7 = 724;
  if ( !pSid || (v18 = 724, v7 = 725, !pAcl) || (v18 = 725, v7 = 726, !a3) )
  {
    LastFailureAsHRESULT = -2147024809;
    goto LABEL_28;
  }
  LastFailureAsHRESULT = 0;
  v18 = 726;
  if ( !GetAclInformation(pAcl, &pAclInformation, 0xCu, AclSizeInformation) )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v8);
    v7 = 728;
LABEL_28:
    v19 = v7;
    goto LABEL_29;
  }
  LastFailureAsHRESULT = 0;
  v18 = 728;
  v9 = 80 * pAclInformation + 88;
  v6 = (struct _ACL *)CoTaskMemAlloc(v9);
  v7 = 735;
  if ( !v6 )
  {
    LastFailureAsHRESULT = -2147024882;
    goto LABEL_28;
  }
  LastFailureAsHRESULT = 0;
  v18 = 735;
  if ( v9 <= 0xFFFC )
  {
    if ( !InitializeAcl(v6, v9, 2u) )
    {
      LastFailureAsHRESULT = GetLastFailureAsHRESULT(v11);
      v7 = 748;
      goto LABEL_28;
    }
    LastFailureAsHRESULT = 0;
    v18 = 748;
    if ( !AddAccessAllowedAce(v6, 2u, 0x1F01FFu, pSid) )
    {
      LastFailureAsHRESULT = GetLastFailureAsHRESULT(v12);
      v7 = 751;
      goto LABEL_28;
    }
    LastFailureAsHRESULT = 0;
    v18 = 751;
    v6->AceCount = 1;
    for ( i = 0; i < (unsigned int)pAclInformation; ++i )
    {
      if ( !GetAce(pAcl, i, &pAce) )
      {
        LastFailureAsHRESULT = GetLastFailureAsHRESULT(v14);
        v19 = 756;
        goto LABEL_29;
      }
      LastFailureAsHRESULT = 0;
      v18 = 756;
      LastFailureAsHRESULT = SxAddKnownAce(
                               v6,
                               *((_BYTE *)pAce + 1),
                               *((_DWORD *)pAce + 1),
                               (char *)pAce + 8,
                               *(_BYTE *)pAce);
      if ( LastFailureAsHRESULT < 0 )
      {
        v19 = 758;
        goto LABEL_29;
      }
      v18 = 758;
    }
    *a3 = v6;
    v6 = 0;
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, &WPP_052bc5b66f273e09fada3dec80af9ee3_Traceguids, v10);
    *a3 = 0;
    LastFailureAsHRESULT = 1;
    v18 = 745;
  }
LABEL_29:
  CoTaskMemFree(v6);
  v15 = LastFailureAsHRESULT;
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&LastFailureAsHRESULT);
  return v15;
}

```

## disassembly

```asm
0x180025c68  push    rbp
0x180025c6a  push    rbx
0x180025c6b  push    rsi
0x180025c6c  push    rdi
0x180025c6d  push    r13
0x180025c6f  push    r14
0x180025c71  push    r15
0x180025c73  lea     rbp, [rsp-27h]
0x180025c78  sub     rsp, 90h
0x180025c7f  mov     rax, cs:__security_cookie
0x180025c86  xor     rax, rsp
0x180025c89  mov     [rbp+57h+var_40], rax
0x180025c8d  mov     rsi, r8
0x180025c90  mov     r15, rdx
0x180025c93  mov     r14, rcx
0x180025c96  mov     r9d, 1; unsigned __int16
0x180025c9c  mov     r8d, 2C8h; unsigned __int16
0x180025ca2  lea     rdx, aDuplicateresto; "DuplicateRestorerFullAccessDacl"
0x180025ca9  lea     rcx, [rbp+57h+var_90]; this
0x180025cad  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180025cb2  xor     eax, eax
0x180025cb4  mov     [rbp+57h+pAclInformation], rax
0x180025cb8  mov     [rbp+57h+var_48], eax
0x180025cbb  xor     ebx, ebx
0x180025cbd  mov     [rbp+57h+pAce], rax
0x180025cc1  test    rsi, rsi
0x180025cc4  jz      short loc_180025CC9
0x180025cc6  mov     [rsi], rax
0x180025cc9  mov     eax, 2D4h
0x180025cce  test    r14, r14
0x180025cd1  jz      loc_180025ED4
0x180025cd7  mov     [rbp+57h+var_8C], ax
0x180025cdb  mov     eax, 2D5h
0x180025ce0  test    r15, r15
0x180025ce3  jz      loc_180025ED4
0x180025ce9  mov     [rbp+57h+var_8C], ax
0x180025ced  mov     eax, 2D6h
0x180025cf2  test    rsi, rsi
0x180025cf5  jz      loc_180025ED4
0x180025cfb  mov     [rbp+57h+var_90], ebx
0x180025cfe  mov     [rbp+57h+var_8C], ax
0x180025d02  mov     r13d, 2
0x180025d08  mov     r9d, r13d; dwAclInformationClass
0x180025d0b  lea     r8d, [r13+0Ah]; nAclInformationLength
0x180025d0f  lea     rdx, [rbp+57h+pAclInformation]; pAclInformation
0x180025d13  mov     rcx, r15; pAcl
0x180025d16  call    cs:__imp_GetAclInformation
0x180025d1d  nop     dword ptr [rax+rax+00h]
0x180025d22  test    eax, eax
0x180025d24  jnz     short loc_180025D38
0x180025d26  call    GetLastFailureAsHRESULT
0x180025d2b  mov     [rbp+57h+var_90], eax
0x180025d2e  mov     eax, 2D8h
0x180025d33  jmp     loc_180025EDB
0x180025d38  mov     [rbp+57h+var_90], ebx
0x180025d3b  mov     eax, 2D8h
0x180025d40  mov     [rbp+57h+var_8C], ax
0x180025d44  mov     eax, dword ptr [rbp+57h+pAclInformation]
0x180025d47  lea     edi, [rax+rax*4]
0x180025d4a  shl     edi, 4
0x180025d4d  add     edi, 58h ; 'X'
0x180025d50  mov     ecx, edi; cb
0x180025d52  call    cs:__imp_CoTaskMemAlloc
0x180025d59  nop     dword ptr [rax+rax+00h]
0x180025d5e  mov     rbx, rax
0x180025d61  test    rax, rax
0x180025d64  mov     eax, 2DFh
0x180025d69  jz      loc_180025ECB
0x180025d6f  mov     [rbp+57h+var_90], 0
0x180025d76  mov     [rbp+57h+var_8C], ax
0x180025d7a  cmp     edi, 0FFFCh
0x180025d80  jbe     short loc_180025DCC
0x180025d82  lea     rax, WPP_GLOBAL_Control
0x180025d89  mov     rcx, cs:WPP_GLOBAL_Control
0x180025d90  cmp     rcx, rax
0x180025d93  jz      short loc_180025DB0
0x180025d95  test    [rcx+1Ch], r13b
0x180025d99  jz      short loc_180025DB0
0x180025d9b  mov     edx, 16h
0x180025da0  lea     r8, WPP_052bc5b66f273e09fada3dec80af9ee3_Traceguids
0x180025da7  mov     rcx, [rcx+10h]
0x180025dab  call    WPP_SF_
0x180025db0  mov     qword ptr [rsi], 0
0x180025db7  mov     [rbp+57h+var_90], 1
0x180025dbe  mov     eax, 2E9h
0x180025dc3  mov     [rbp+57h+var_8C], ax
0x180025dc7  jmp     loc_180025EDF
0x180025dcc  mov     r8d, r13d; dwAclRevision
0x180025dcf  mov     edx, edi; nAclLength
0x180025dd1  mov     rcx, rbx; pAcl
0x180025dd4  call    cs:__imp_InitializeAcl
0x180025ddb  nop     dword ptr [rax+rax+00h]
0x180025de0  test    eax, eax
0x180025de2  jnz     short loc_180025DF6
0x180025de4  call    GetLastFailureAsHRESULT
0x180025de9  mov     [rbp+57h+var_90], eax
0x180025dec  mov     eax, 2ECh
0x180025df1  jmp     loc_180025EDB
0x180025df6  mov     [rbp+57h+var_90], 0
0x180025dfd  mov     eax, 2ECh
0x180025e02  mov     [rbp+57h+var_8C], ax
0x180025e06  mov     r9, r14; pSid
0x180025e09  mov     r8d, 1F01FFh; AccessMask
0x180025e0f  mov     edx, r13d; dwAceRevision
0x180025e12  mov     rcx, rbx; pAcl
0x180025e15  call    cs:__imp_AddAccessAllowedAce
0x180025e1c  nop     dword ptr [rax+rax+00h]
0x180025e21  test    eax, eax
0x180025e23  jnz     short loc_180025E37
0x180025e25  call    GetLastFailureAsHRESULT
0x180025e2a  mov     [rbp+57h+var_90], eax
0x180025e2d  mov     eax, 2EFh
0x180025e32  jmp     loc_180025EDB
0x180025e37  mov     [rbp+57h+var_90], 0
0x180025e3e  mov     eax, 2EFh
0x180025e43  mov     [rbp+57h+var_8C], ax
0x180025e47  mov     word ptr [rbx+4], 1
0x180025e4d  xor     edi, edi
0x180025e4f  lea     r13d, [rax+5]
0x180025e53  lea     r14d, [rax+7]
0x180025e57  cmp     edi, dword ptr [rbp+57h+pAclInformation]
0x180025e5a  jnb     short loc_180025EC4
0x180025e5c  lea     r8, [rbp+57h+pAce]; pAce
0x180025e60  mov     edx, edi; dwAceIndex
0x180025e62  mov     rcx, r15; pAcl
0x180025e65  call    cs:__imp_GetAce
0x180025e6c  nop     dword ptr [rax+rax+00h]
0x180025e71  test    eax, eax
0x180025e73  jz      short loc_180025EB5
0x180025e75  mov     [rbp+57h+var_90], 0
0x180025e7c  mov     [rbp+57h+var_8C], r13w
0x180025e81  mov     rdx, [rbp+57h+pAce]
0x180025e85  lea     r9, [rdx+8]; void *
0x180025e89  mov     al, [rdx]
0x180025e8b  mov     [rsp+0C0h+var_A0], al; unsigned __int8
0x180025e8f  mov     r8d, [rdx+4]; unsigned int
0x180025e93  mov     dl, [rdx+1]; unsigned __int8
0x180025e96  mov     rcx, rbx; pAcl
0x180025e99  call    ?SxAddKnownAce@@YAJPEAU_ACL@@EKQEAXE@Z; SxAddKnownAce(_ACL *,uchar,ulong,void * const,uchar)
0x180025e9e  mov     [rbp+57h+var_90], eax
0x180025ea1  test    eax, eax
0x180025ea3  js      short loc_180025EAE
0x180025ea5  mov     [rbp+57h+var_8C], r14w
0x180025eaa  inc     edi
0x180025eac  jmp     short loc_180025E57
0x180025eae  mov     [rbp+57h+var_8A], r14w
0x180025eb3  jmp     short loc_180025EDF
0x180025eb5  call    GetLastFailureAsHRESULT
0x180025eba  mov     [rbp+57h+var_90], eax
0x180025ebd  mov     [rbp+57h+var_8A], r13w
0x180025ec2  jmp     short loc_180025EDF
0x180025ec4  mov     [rsi], rbx
0x180025ec7  xor     ebx, ebx
0x180025ec9  jmp     short loc_180025EDF
0x180025ecb  mov     [rbp+57h+var_90], 8007000Eh
0x180025ed2  jmp     short loc_180025EDB
0x180025ed4  mov     [rbp+57h+var_90], 80070057h
0x180025edb  mov     [rbp+57h+var_8A], ax
0x180025edf  mov     rcx, rbx; pv
0x180025ee2  call    cs:__imp_CoTaskMemFree
0x180025ee9  nop     dword ptr [rax+rax+00h]
0x180025eee  mov     ebx, [rbp+57h+var_90]
0x180025ef1  lea     rcx, [rbp+57h+var_90]; this
0x180025ef5  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180025efa  mov     eax, ebx
0x180025efc  mov     rcx, [rbp+57h+var_40]
0x180025f00  xor     rcx, rsp; StackCookie
0x180025f03  call    __security_check_cookie
0x180025f08  add     rsp, 90h
0x180025f0f  pop     r15
0x180025f11  pop     r14
0x180025f13  pop     r13
0x180025f15  pop     rdi
0x180025f16  pop     rsi
0x180025f17  pop     rbx
0x180025f18  pop     rbp
0x180025f19  retn
```
