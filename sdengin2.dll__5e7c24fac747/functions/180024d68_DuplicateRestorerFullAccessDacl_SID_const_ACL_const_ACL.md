# DuplicateRestorerFullAccessDacl(_SID const *,_ACL * const,_ACL * *)

- ea: `0x180024d68`
- end: `0x180024ff6`
- name: `?DuplicateRestorerFullAccessDacl@@YAJPEBU_SID@@QEAU_ACL@@PEAPEAU2@@Z`
- size: `654`
- prototype: `__int64 __fastcall(PSID pSid, PACL pAcl, struct _ACL **)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180022c34`

## callees

- `0x1800081d8`
- `0x180024d68`
- `0x180026a90`
- `0x18006fe84`
- `0x18006ff8c`
- `0x18008f5d0`
- `0x1800c9830`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180024f03`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180024f03`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x180024ec8`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x180024ec8`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x180024e16`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x180024e16`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x180024f4d`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x180024f4d`
- `ole32!CoTaskMemFree` at `0x180024fc4`
- `ole32!CoTaskMemFree` at `0x180024fc4`
- `ole32!CoTaskMemAlloc` at `0x180024e4c`
- `ole32!CoTaskMemAlloc` at `0x180024e4c`

## string_xrefs

- `0x180024da2`: `DuplicateRestorerFullAccessDacl`

## pseudocode

```c
__int64 __fastcall DuplicateRestorerFullAccessDacl(PSID pSid, PACL pAcl, struct _ACL **a3)
{
  struct _ACL *v6; // rbx
  __int16 v7; // ax
  __int64 v8; // rcx
  DWORD v9; // edi
  __int64 v10; // rcx
  __int64 v11; // rcx
  DWORD i; // edi
  __int64 v13; // rcx
  unsigned int v14; // ebx
  int LastFailureAsHRESULT; // [rsp+30h] [rbp-39h] BYREF
  __int16 v17; // [rsp+34h] [rbp-35h]
  __int16 v18; // [rsp+36h] [rbp-33h]
  LPVOID pAce; // [rsp+68h] [rbp-1h] BYREF
  __int64 pAclInformation; // [rsp+70h] [rbp+7h] BYREF
  int v21; // [rsp+78h] [rbp+Fh]

  CSxFunctionTracer::CSxFunctionTracer(
    (CSxFunctionTracer *)&LastFailureAsHRESULT,
    "DuplicateRestorerFullAccessDacl",
    712,
    1);
  pAclInformation = 0;
  v21 = 0;
  v6 = 0;
  pAce = 0;
  if ( a3 )
    *a3 = 0;
  v7 = 724;
  if ( !pSid || (v17 = 724, v7 = 725, !pAcl) || (v17 = 725, v7 = 726, !a3) )
  {
    LastFailureAsHRESULT = -2147024809;
    goto LABEL_28;
  }
  LastFailureAsHRESULT = 0;
  v17 = 726;
  if ( !GetAclInformation(pAcl, &pAclInformation, 0xCu, AclSizeInformation) )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v8);
    v7 = 728;
LABEL_28:
    v18 = v7;
    goto LABEL_29;
  }
  LastFailureAsHRESULT = 0;
  v17 = 728;
  v9 = 80 * pAclInformation + 88;
  v6 = (struct _ACL *)CoTaskMemAlloc(v9);
  v7 = 735;
  if ( !v6 )
  {
    LastFailureAsHRESULT = -2147024882;
    goto LABEL_28;
  }
  LastFailureAsHRESULT = 0;
  v17 = 735;
  if ( v9 <= 0xFFFC )
  {
    if ( !InitializeAcl(v6, v9, 2u) )
    {
      LastFailureAsHRESULT = GetLastFailureAsHRESULT(v10);
      v7 = 748;
      goto LABEL_28;
    }
    LastFailureAsHRESULT = 0;
    v17 = 748;
    if ( !AddAccessAllowedAce(v6, 2u, 0x1F01FFu, pSid) )
    {
      LastFailureAsHRESULT = GetLastFailureAsHRESULT(v11);
      v7 = 751;
      goto LABEL_28;
    }
    LastFailureAsHRESULT = 0;
    v17 = 751;
    v6->AceCount = 1;
    for ( i = 0; i < (unsigned int)pAclInformation; ++i )
    {
      if ( !GetAce(pAcl, i, &pAce) )
      {
        LastFailureAsHRESULT = GetLastFailureAsHRESULT(v13);
        v18 = 756;
        goto LABEL_29;
      }
      LastFailureAsHRESULT = 0;
      v17 = 756;
      LastFailureAsHRESULT = SxAddKnownAce(
                               v6,
                               *((_BYTE *)pAce + 1),
                               *((_DWORD *)pAce + 1),
                               (char *)pAce + 8,
                               *(_BYTE *)pAce);
      if ( LastFailureAsHRESULT < 0 )
      {
        v18 = 758;
        goto LABEL_29;
      }
      v17 = 758;
    }
    *a3 = v6;
    v6 = 0;
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, &WPP_052bc5b66f273e09fada3dec80af9ee3_Traceguids);
    *a3 = 0;
    LastFailureAsHRESULT = 1;
    v17 = 745;
  }
LABEL_29:
  CoTaskMemFree(v6);
  v14 = LastFailureAsHRESULT;
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&LastFailureAsHRESULT);
  return v14;
}

```

## disassembly

```asm
0x180024d68  push    rbp
0x180024d6a  push    rbx
0x180024d6b  push    rsi
0x180024d6c  push    rdi
0x180024d6d  push    r13
0x180024d6f  push    r14
0x180024d71  push    r15
0x180024d73  lea     rbp, [rsp-27h]
0x180024d78  sub     rsp, 90h
0x180024d7f  mov     rax, cs:__security_cookie
0x180024d86  xor     rax, rsp
0x180024d89  mov     [rbp+57h+var_40], rax
0x180024d8d  mov     rsi, r8
0x180024d90  mov     r15, rdx
0x180024d93  mov     r14, rcx
0x180024d96  mov     r9d, 1; unsigned __int16
0x180024d9c  mov     r8d, 2C8h; unsigned __int16
0x180024da2  lea     rdx, aDuplicateresto; "DuplicateRestorerFullAccessDacl"
0x180024da9  lea     rcx, [rbp+57h+var_90]; this
0x180024dad  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180024db2  xor     eax, eax
0x180024db4  mov     [rbp+57h+pAclInformation], rax
0x180024db8  mov     [rbp+57h+var_48], eax
0x180024dbb  xor     ebx, ebx
0x180024dbd  mov     [rbp+57h+pAce], rax
0x180024dc1  test    rsi, rsi
0x180024dc4  jz      short loc_180024DC9
0x180024dc6  mov     [rsi], rax
0x180024dc9  mov     eax, 2D4h
0x180024dce  test    r14, r14
0x180024dd1  jz      loc_180024FB6
0x180024dd7  mov     [rbp+57h+var_8C], ax
0x180024ddb  mov     eax, 2D5h
0x180024de0  test    r15, r15
0x180024de3  jz      loc_180024FB6
0x180024de9  mov     [rbp+57h+var_8C], ax
0x180024ded  mov     eax, 2D6h
0x180024df2  test    rsi, rsi
0x180024df5  jz      loc_180024FB6
0x180024dfb  mov     [rbp+57h+var_90], ebx
0x180024dfe  mov     [rbp+57h+var_8C], ax
0x180024e02  mov     r13d, 2
0x180024e08  mov     r9d, r13d; dwAclInformationClass
0x180024e0b  lea     r8d, [r13+0Ah]; nAclInformationLength
0x180024e0f  lea     rdx, [rbp+57h+pAclInformation]; pAclInformation
0x180024e13  mov     rcx, r15; pAcl
0x180024e16  call    cs:__imp_GetAclInformation
0x180024e1c  test    eax, eax
0x180024e1e  jnz     short loc_180024E32
0x180024e20  call    GetLastFailureAsHRESULT
0x180024e25  mov     [rbp+57h+var_90], eax
0x180024e28  mov     eax, 2D8h
0x180024e2d  jmp     loc_180024FBD
0x180024e32  mov     [rbp+57h+var_90], ebx
0x180024e35  mov     eax, 2D8h
0x180024e3a  mov     [rbp+57h+var_8C], ax
0x180024e3e  mov     eax, dword ptr [rbp+57h+pAclInformation]
0x180024e41  lea     edi, [rax+rax*4]
0x180024e44  shl     edi, 4
0x180024e47  add     edi, 58h ; 'X'
0x180024e4a  mov     ecx, edi; cb
0x180024e4c  call    cs:__imp_CoTaskMemAlloc
0x180024e52  mov     rbx, rax
0x180024e55  test    rax, rax
0x180024e58  mov     eax, 2DFh
0x180024e5d  jz      loc_180024FAD
0x180024e63  mov     [rbp+57h+var_90], 0
0x180024e6a  mov     [rbp+57h+var_8C], ax
0x180024e6e  cmp     edi, 0FFFCh
0x180024e74  jbe     short loc_180024EC0
0x180024e76  lea     rax, WPP_GLOBAL_Control
0x180024e7d  mov     rcx, cs:WPP_GLOBAL_Control
0x180024e84  cmp     rcx, rax
0x180024e87  jz      short loc_180024EA4
0x180024e89  test    [rcx+1Ch], r13b
0x180024e8d  jz      short loc_180024EA4
0x180024e8f  mov     edx, 16h
0x180024e94  lea     r8, WPP_052bc5b66f273e09fada3dec80af9ee3_Traceguids
0x180024e9b  mov     rcx, [rcx+10h]
0x180024e9f  call    WPP_SF_
0x180024ea4  mov     qword ptr [rsi], 0
0x180024eab  mov     [rbp+57h+var_90], 1
0x180024eb2  mov     eax, 2E9h
0x180024eb7  mov     [rbp+57h+var_8C], ax
0x180024ebb  jmp     loc_180024FC1
0x180024ec0  mov     r8d, r13d; dwAclRevision
0x180024ec3  mov     edx, edi; nAclLength
0x180024ec5  mov     rcx, rbx; pAcl
0x180024ec8  call    cs:__imp_InitializeAcl
0x180024ece  test    eax, eax
0x180024ed0  jnz     short loc_180024EE4
0x180024ed2  call    GetLastFailureAsHRESULT
0x180024ed7  mov     [rbp+57h+var_90], eax
0x180024eda  mov     eax, 2ECh
0x180024edf  jmp     loc_180024FBD
0x180024ee4  mov     [rbp+57h+var_90], 0
0x180024eeb  mov     eax, 2ECh
0x180024ef0  mov     [rbp+57h+var_8C], ax
0x180024ef4  mov     r9, r14; pSid
0x180024ef7  mov     r8d, 1F01FFh; AccessMask
0x180024efd  mov     edx, r13d; dwAceRevision
0x180024f00  mov     rcx, rbx; pAcl
0x180024f03  call    cs:__imp_AddAccessAllowedAce
0x180024f09  test    eax, eax
0x180024f0b  jnz     short loc_180024F1F
0x180024f0d  call    GetLastFailureAsHRESULT
0x180024f12  mov     [rbp+57h+var_90], eax
0x180024f15  mov     eax, 2EFh
0x180024f1a  jmp     loc_180024FBD
0x180024f1f  mov     [rbp+57h+var_90], 0
0x180024f26  mov     eax, 2EFh
0x180024f2b  mov     [rbp+57h+var_8C], ax
0x180024f2f  mov     word ptr [rbx+4], 1
0x180024f35  xor     edi, edi
0x180024f37  lea     r13d, [rax+5]
0x180024f3b  lea     r14d, [rax+7]
0x180024f3f  cmp     edi, dword ptr [rbp+57h+pAclInformation]
0x180024f42  jnb     short loc_180024FA6
0x180024f44  lea     r8, [rbp+57h+pAce]; pAce
0x180024f48  mov     edx, edi; dwAceIndex
0x180024f4a  mov     rcx, r15; pAcl
0x180024f4d  call    cs:__imp_GetAce
0x180024f53  test    eax, eax
0x180024f55  jz      short loc_180024F97
0x180024f57  mov     [rbp+57h+var_90], 0
0x180024f5e  mov     [rbp+57h+var_8C], r13w
0x180024f63  mov     rdx, [rbp+57h+pAce]
0x180024f67  lea     r9, [rdx+8]; void *
0x180024f6b  mov     al, [rdx]
0x180024f6d  mov     [rsp+0C0h+var_A0], al; unsigned __int8
0x180024f71  mov     r8d, [rdx+4]; unsigned int
0x180024f75  mov     dl, [rdx+1]; unsigned __int8
0x180024f78  mov     rcx, rbx; pAcl
0x180024f7b  call    ?SxAddKnownAce@@YAJPEAU_ACL@@EKQEAXE@Z; SxAddKnownAce(_ACL *,uchar,ulong,void * const,uchar)
0x180024f80  mov     [rbp+57h+var_90], eax
0x180024f83  test    eax, eax
0x180024f85  js      short loc_180024F90
0x180024f87  mov     [rbp+57h+var_8C], r14w
0x180024f8c  inc     edi
0x180024f8e  jmp     short loc_180024F3F
0x180024f90  mov     [rbp+57h+var_8A], r14w
0x180024f95  jmp     short loc_180024FC1
0x180024f97  call    GetLastFailureAsHRESULT
0x180024f9c  mov     [rbp+57h+var_90], eax
0x180024f9f  mov     [rbp+57h+var_8A], r13w
0x180024fa4  jmp     short loc_180024FC1
0x180024fa6  mov     [rsi], rbx
0x180024fa9  xor     ebx, ebx
0x180024fab  jmp     short loc_180024FC1
0x180024fad  mov     [rbp+57h+var_90], 8007000Eh
0x180024fb4  jmp     short loc_180024FBD
0x180024fb6  mov     [rbp+57h+var_90], 80070057h
0x180024fbd  mov     [rbp+57h+var_8A], ax
0x180024fc1  mov     rcx, rbx; pv
0x180024fc4  call    cs:__imp_CoTaskMemFree
0x180024fca  mov     ebx, [rbp+57h+var_90]
0x180024fcd  lea     rcx, [rbp+57h+var_90]; this
0x180024fd1  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180024fd6  mov     eax, ebx
0x180024fd8  mov     rcx, [rbp+57h+var_40]
0x180024fdc  xor     rcx, rsp; StackCookie
0x180024fdf  call    __security_check_cookie
0x180024fe4  add     rsp, 90h
0x180024feb  pop     r15
0x180024fed  pop     r14
0x180024fef  pop     r13
0x180024ff1  pop     rdi
0x180024ff2  pop     rsi
0x180024ff3  pop     rbx
0x180024ff4  pop     rbp
0x180024ff5  retn
```
