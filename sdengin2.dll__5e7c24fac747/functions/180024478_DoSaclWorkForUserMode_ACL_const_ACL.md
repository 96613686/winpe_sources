# DoSaclWorkForUserMode(_ACL * const,_ACL * *)

- ea: `0x180024478`
- end: `0x18002471d`
- name: `?DoSaclWorkForUserMode@@YAJQEAU_ACL@@PEAPEAU1@@Z`
- size: `677`
- prototype: `__int64 __fastcall(PACL pAcl, struct _ACL **)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180022c34`

## callees

- `0x1800081d8`
- `0x180024478`
- `0x18002631c`
- `0x180026a90`
- `0x18006fe84`
- `0x18006ff8c`
- `0x18008f5d0`
- `0x1800c9830`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x1800245cc`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x1800245cc`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x18002451e`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x18002451e`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18002461d`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18002461d`
- `ole32!CoTaskMemFree` at `0x1800245ea`
- `ole32!CoTaskMemFree` at `0x1800245ea`
- `ole32!CoTaskMemAlloc` at `0x1800245a5`
- `ole32!CoTaskMemAlloc` at `0x1800245a5`

## string_xrefs

- `0x1800244b6`: `DoSaclWorkForUserMode`

## pseudocode

```c
__int64 __fastcall DoSaclWorkForUserMode(PACL pAcl, struct _ACL **a2)
{
  DWORD v4; // r14d
  __int16 v5; // ax
  __int64 v6; // rcx
  int LastFailureAsHRESULT; // ebx
  DWORD v8; // r15d
  DWORD v9; // ebx
  struct _ACL *v10; // rsi
  __int64 v11; // rcx
  __int16 v12; // ax
  int v13; // r13d
  __int64 v14; // rcx
  BYTE v16; // [rsp+30h] [rbp-49h]
  int v17; // [rsp+34h] [rbp-45h] BYREF
  int v18; // [rsp+38h] [rbp-41h] BYREF
  __int16 v19; // [rsp+3Ch] [rbp-3Dh]
  __int16 v20; // [rsp+3Eh] [rbp-3Bh]
  LPVOID pAce; // [rsp+70h] [rbp-9h] BYREF
  _BYTE *v22; // [rsp+78h] [rbp-1h]
  __int64 pAclInformation; // [rsp+80h] [rbp+7h] BYREF
  int v24; // [rsp+88h] [rbp+Fh]

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v18, "DoSaclWorkForUserMode", 425, 1);
  pAclInformation = 0;
  v24 = 0;
  v4 = 0;
  pAce = 0;
  v17 = 0;
  if ( a2 )
    *a2 = 0;
  v5 = 441;
  if ( !pAcl || (v19 = 441, v5 = 442, !a2) )
  {
    LastFailureAsHRESULT = -2147024809;
    goto LABEL_30;
  }
  v18 = 0;
  v19 = 442;
  if ( !GetAclInformation(pAcl, &pAclInformation, 0xCu, AclSizeInformation) )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v6);
    v18 = LastFailureAsHRESULT;
    v5 = 444;
LABEL_31:
    v20 = v5;
    goto LABEL_32;
  }
  v18 = 0;
  v19 = 444;
  v8 = pAclInformation;
  v9 = 80 * pAclInformation + 8;
  if ( v9 > 0xFFFC )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_052bc5b66f273e09fada3dec80af9ee3_Traceguids);
    *a2 = 0;
    LastFailureAsHRESULT = 1;
    v18 = 1;
    v19 = 457;
    goto LABEL_32;
  }
  v10 = (struct _ACL *)CoTaskMemAlloc(v9);
  v5 = 461;
  if ( !v10 )
  {
    LastFailureAsHRESULT = -2147024882;
LABEL_30:
    v18 = LastFailureAsHRESULT;
    goto LABEL_31;
  }
  v18 = 0;
  v19 = 461;
  if ( InitializeAcl(v10, v9, 2u) )
  {
    v13 = 0;
    LastFailureAsHRESULT = 0;
    v18 = 0;
    v19 = 464;
    while ( v4 < v8 )
    {
      if ( !GetAce(pAcl, v4, &pAce) )
      {
        v18 = GetLastFailureAsHRESULT(v14);
        v12 = 469;
        goto LABEL_15;
      }
      v18 = 0;
      v19 = 469;
      v22 = pAce;
      v16 = *(_BYTE *)pAce;
      LastFailureAsHRESULT = IsSaclAceInteresting(pAce, *(_BYTE *)pAce, &v17);
      v18 = LastFailureAsHRESULT;
      v12 = 472;
      if ( LastFailureAsHRESULT < 0 )
        goto LABEL_15;
      v19 = 472;
      if ( v17 )
      {
        LastFailureAsHRESULT = SxAddKnownAce(v10, v22[1], *((_DWORD *)pAce + 1), (char *)pAce + 8, v16);
        v18 = LastFailureAsHRESULT;
        v12 = 475;
        if ( LastFailureAsHRESULT < 0 )
          goto LABEL_15;
        v19 = 475;
        v13 = 1;
      }
      ++v4;
    }
    if ( v13 )
    {
      *a2 = v10;
      goto LABEL_32;
    }
  }
  else
  {
    v18 = GetLastFailureAsHRESULT(v11);
    v12 = 464;
LABEL_15:
    v20 = v12;
  }
  CoTaskMemFree(v10);
  LastFailureAsHRESULT = v18;
LABEL_32:
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v18);
  return (unsigned int)LastFailureAsHRESULT;
}

```

## disassembly

```asm
0x180024478  mov     [rsp-8+arg_10], rbx
0x18002447d  push    rbp
0x18002447e  push    rsi
0x18002447f  push    rdi
0x180024480  push    r12
0x180024482  push    r13
0x180024484  push    r14
0x180024486  push    r15
0x180024488  lea     rbp, [rsp-27h]
0x18002448d  sub     rsp, 0A0h
0x180024494  mov     rax, cs:__security_cookie
0x18002449b  xor     rax, rsp
0x18002449e  mov     [rbp+57h+var_40], rax
0x1800244a2  mov     rdi, rdx
0x1800244a5  mov     r12, rcx
0x1800244a8  mov     esi, 1
0x1800244ad  mov     r9d, esi; unsigned __int16
0x1800244b0  mov     r8d, 1A9h; unsigned __int16
0x1800244b6  lea     rdx, aDosaclworkforu; "DoSaclWorkForUserMode"
0x1800244bd  lea     rcx, [rbp+57h+var_98]; this
0x1800244c1  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x1800244c6  xor     eax, eax
0x1800244c8  mov     [rbp+57h+pAclInformation], rax
0x1800244cc  mov     [rbp+57h+var_48], eax
0x1800244cf  xor     r14d, r14d
0x1800244d2  mov     [rbp+57h+pAce], r14
0x1800244d6  mov     [rbp+57h+var_9C], r14d
0x1800244da  test    rdi, rdi
0x1800244dd  jz      short loc_1800244E2
0x1800244df  mov     [rdi], r14
0x1800244e2  mov     eax, 1B9h
0x1800244e7  test    r12, r12
0x1800244ea  jz      loc_1800246DF
0x1800244f0  mov     [rbp+57h+var_94], ax
0x1800244f4  mov     eax, 1BAh
0x1800244f9  test    rdi, rdi
0x1800244fc  jz      loc_1800246DF
0x180024502  mov     [rbp+57h+var_98], r14d
0x180024506  mov     [rbp+57h+var_94], ax
0x18002450a  mov     r13d, 2
0x180024510  mov     r9d, r13d; dwAclInformationClass
0x180024513  lea     r8d, [r13+0Ah]; nAclInformationLength
0x180024517  lea     rdx, [rbp+57h+pAclInformation]; pAclInformation
0x18002451b  mov     rcx, r12; pAcl
0x18002451e  call    cs:__imp_GetAclInformation
0x180024524  test    eax, eax
0x180024526  jnz     short loc_18002453C
0x180024528  call    GetLastFailureAsHRESULT
0x18002452d  mov     ebx, eax
0x18002452f  mov     [rbp+57h+var_98], eax
0x180024532  mov     eax, 1BCh
0x180024537  jmp     loc_1800246E7
0x18002453c  mov     [rbp+57h+var_98], r14d
0x180024540  mov     eax, 1BCh
0x180024545  mov     [rbp+57h+var_94], ax
0x180024549  mov     r15d, dword ptr [rbp+57h+pAclInformation]
0x18002454d  lea     ebx, [r15+r15*4]
0x180024551  shl     ebx, 4
0x180024554  add     ebx, 8
0x180024557  cmp     ebx, 0FFFCh
0x18002455d  jbe     short loc_1800245A3
0x18002455f  lea     rax, WPP_GLOBAL_Control
0x180024566  mov     rcx, cs:WPP_GLOBAL_Control
0x18002456d  cmp     rcx, rax
0x180024570  jz      short loc_18002458D
0x180024572  test    [rcx+1Ch], r13b
0x180024576  jz      short loc_18002458D
0x180024578  mov     edx, 13h
0x18002457d  lea     r8, WPP_052bc5b66f273e09fada3dec80af9ee3_Traceguids
0x180024584  mov     rcx, [rcx+10h]
0x180024588  call    WPP_SF_
0x18002458d  mov     [rdi], r14
0x180024590  mov     ebx, esi
0x180024592  mov     [rbp+57h+var_98], ebx
0x180024595  mov     eax, 1C9h
0x18002459a  mov     [rbp+57h+var_94], ax
0x18002459e  jmp     loc_1800246EB
0x1800245a3  mov     ecx, ebx; cb
0x1800245a5  call    cs:__imp_CoTaskMemAlloc
0x1800245ab  mov     rsi, rax
0x1800245ae  test    rax, rax
0x1800245b1  mov     eax, 1CDh
0x1800245b6  jz      loc_1800246D8
0x1800245bc  mov     [rbp+57h+var_98], r14d
0x1800245c0  mov     [rbp+57h+var_94], ax
0x1800245c4  mov     r8d, r13d; dwAclRevision
0x1800245c7  mov     edx, ebx; nAclLength
0x1800245c9  mov     rcx, rsi; pAcl
0x1800245cc  call    cs:__imp_InitializeAcl
0x1800245d2  test    eax, eax
0x1800245d4  jnz     short loc_1800245F8
0x1800245d6  call    GetLastFailureAsHRESULT
0x1800245db  mov     [rbp+57h+var_98], eax
0x1800245de  mov     eax, 1D0h
0x1800245e3  mov     [rbp+57h+var_92], ax
0x1800245e7  mov     rcx, rsi; pv
0x1800245ea  call    cs:__imp_CoTaskMemFree
0x1800245f0  mov     ebx, [rbp+57h+var_98]
0x1800245f3  jmp     loc_1800246EB
0x1800245f8  mov     r13d, r14d
0x1800245fb  mov     ebx, r14d
0x1800245fe  mov     [rbp+57h+var_98], ebx
0x180024601  mov     eax, 1D0h
0x180024606  mov     [rbp+57h+var_94], ax
0x18002460a  cmp     r14d, r15d
0x18002460d  jnb     loc_1800246CA
0x180024613  lea     r8, [rbp+57h+pAce]; pAce
0x180024617  mov     edx, r14d; dwAceIndex
0x18002461a  mov     rcx, r12; pAcl
0x18002461d  call    cs:__imp_GetAce
0x180024623  test    eax, eax
0x180024625  jz      loc_1800246B8
0x18002462b  mov     [rbp+57h+var_98], 0
0x180024632  mov     eax, 1D5h
0x180024637  mov     [rbp+57h+var_94], ax
0x18002463b  mov     rax, [rbp+57h+pAce]
0x18002463f  mov     [rbp+57h+var_58], rax
0x180024643  mov     cl, [rax]
0x180024645  mov     [rbp+57h+var_A0], cl
0x180024648  lea     r8, [rbp+57h+var_9C]; int *
0x18002464c  mov     dl, cl; unsigned __int8
0x18002464e  mov     rcx, rax; void *
0x180024651  call    ?IsSaclAceInteresting@@YAJPEAXEPEAH@Z; IsSaclAceInteresting(void *,uchar,int *)
0x180024656  mov     ebx, eax
0x180024658  mov     [rbp+57h+var_98], eax
0x18002465b  test    eax, eax
0x18002465d  mov     eax, 1D8h
0x180024662  js      loc_1800245E3
0x180024668  mov     [rbp+57h+var_94], ax
0x18002466c  cmp     [rbp+57h+var_9C], 0
0x180024670  jz      short loc_1800246B0
0x180024672  mov     r8, [rbp+57h+pAce]
0x180024676  lea     r9, [r8+8]; void *
0x18002467a  mov     al, [rbp+57h+var_A0]
0x18002467d  mov     [rsp+0D0h+var_B0], al; unsigned __int8
0x180024681  mov     r8d, [r8+4]; unsigned int
0x180024685  mov     rdx, [rbp+57h+var_58]
0x180024689  mov     dl, [rdx+1]; unsigned __int8
0x18002468c  mov     rcx, rsi; pAcl
0x18002468f  call    ?SxAddKnownAce@@YAJPEAU_ACL@@EKQEAXE@Z; SxAddKnownAce(_ACL *,uchar,ulong,void * const,uchar)
0x180024694  mov     ebx, eax
0x180024696  mov     [rbp+57h+var_98], eax
0x180024699  test    eax, eax
0x18002469b  mov     eax, 1DBh
0x1800246a0  js      loc_1800245E3
0x1800246a6  mov     [rbp+57h+var_94], ax
0x1800246aa  mov     r13d, 1
0x1800246b0  inc     r14d
0x1800246b3  jmp     loc_18002460A
0x1800246b8  call    GetLastFailureAsHRESULT
0x1800246bd  mov     [rbp+57h+var_98], eax
0x1800246c0  mov     eax, 1D5h
0x1800246c5  jmp     loc_1800245E3
0x1800246ca  test    r13d, r13d
0x1800246cd  jz      loc_1800245E7
0x1800246d3  mov     [rdi], rsi
0x1800246d6  jmp     short loc_1800246EB
0x1800246d8  mov     ebx, 8007000Eh
0x1800246dd  jmp     short loc_1800246E4
0x1800246df  mov     ebx, 80070057h
0x1800246e4  mov     [rbp+57h+var_98], ebx
0x1800246e7  mov     [rbp+57h+var_92], ax
0x1800246eb  lea     rcx, [rbp+57h+var_98]; this
0x1800246ef  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x1800246f4  mov     eax, ebx
0x1800246f6  mov     rcx, [rbp+57h+var_40]
0x1800246fa  xor     rcx, rsp; StackCookie
0x1800246fd  call    __security_check_cookie
0x180024702  mov     rbx, [rsp+0D0h+arg_10]
0x18002470a  add     rsp, 0A0h
0x180024711  pop     r15
0x180024713  pop     r14
0x180024715  pop     r13
0x180024717  pop     r12
0x180024719  pop     rdi
0x18002471a  pop     rsi
0x18002471b  pop     rbp
0x18002471c  retn
```
