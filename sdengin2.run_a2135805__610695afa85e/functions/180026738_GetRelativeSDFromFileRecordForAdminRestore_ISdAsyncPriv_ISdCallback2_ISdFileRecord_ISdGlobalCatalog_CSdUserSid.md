# GetRelativeSDFromFileRecordForAdminRestore(ISdAsyncPriv *,ISdCallback2 *,ISdFileRecord *,ISdGlobalCatalog *,CSdUserSidList *,uchar * *,ulong *)

- ea: `0x180026738`
- end: `0x180026b65`
- name: `?GetRelativeSDFromFileRecordForAdminRestore@@YAJPEAUISdAsyncPriv@@PEAUISdCallback2@@PEAUISdFileRecord@@PEAUISdGlobalCatalog@@PEAVCSdUserSidList@@PEAPEAEPEAK@Z`
- size: `1069`
- prototype: `__int64 __usercall@<rax>(struct ISdAsyncPriv *@<rcx>, struct ISdCallback2 *@<rdx>, struct ISdFileRecord *@<r8>, struct ISdGlobalCatalog *@<r9>, struct CSdUserSidList *, unsigned __int8 **, unsigned int *)`
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180007588`
- `0x18002e620`

## callees

- `0x1800083e4`
- `0x180009d0c`
- `0x180023224`
- `0x180026738`
- `0x180032d38`
- `0x180072e08`
- `0x180072f14`
- `0x1800935fc`
- `0x1800d1010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x18002689a`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x180026a07`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x18002689a`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x180026a07`
- `ole32!CoTaskMemFree` at `0x180026b0e`
- `ole32!CoTaskMemFree` at `0x180026b26`
- `ole32!CoTaskMemFree` at `0x180026b0e`
- `ole32!CoTaskMemFree` at `0x180026b26`

## pseudocode

```c
__int64 __fastcall GetRelativeSDFromFileRecordForAdminRestore(
        struct ISdAsyncPriv *a1,
        struct ISdCallback2 *a2,
        struct ISdFileRecord *a3,
        struct ISdGlobalCatalog *a4,
        struct CSdUserSidList *a5,
        unsigned __int8 **a6,
        unsigned int *a7)
{
  unsigned __int8 **v11; // rsi
  unsigned int *v12; // rdi
  __int16 v13; // ax
  __int64 v14; // rcx
  WORD v15; // cx
  PVOID *v16; // r11
  __int64 v17; // rcx
  WORD v18; // cx
  unsigned int v19; // ebx
  PSECURITY_DESCRIPTOR pv; // [rsp+50h] [rbp-41h] BYREF
  ULONG SecurityDescriptorLength; // [rsp+58h] [rbp-39h] BYREF
  PSECURITY_DESCRIPTOR pSecurityDescriptor; // [rsp+60h] [rbp-31h] BYREF
  int LastFailureAsHRESULT; // [rsp+68h] [rbp-29h] BYREF
  __int16 v25; // [rsp+6Ch] [rbp-25h]
  __int16 v26; // [rsp+6Eh] [rbp-23h]
  DWORD dwRevision; // [rsp+A0h] [rbp+Fh] BYREF
  unsigned int v28; // [rsp+A4h] [rbp+13h] BYREF
  unsigned __int16 *v29; // [rsp+A8h] [rbp+17h] BYREF
  WORD pControl; // [rsp+E0h] [rbp+4Fh] BYREF

  CSxFunctionTracer::CSxFunctionTracer(
    (CSxFunctionTracer *)&LastFailureAsHRESULT,
    "GetRelativeSDFromFileRecordForAdminRestore",
    0x97u,
    1u);
  SecurityDescriptorLength = 0;
  dwRevision = 0;
  v29 = 0;
  pControl = 0;
  pSecurityDescriptor = 0;
  pv = 0;
  v28 = 0;
  v11 = a6;
  if ( a6 )
    *a6 = 0;
  v12 = a7;
  if ( a7 )
    *a7 = 0;
  v13 = 163;
  if ( !a1 )
    goto LABEL_6;
  v25 = 163;
  v13 = 164;
  if ( !a2 )
    goto LABEL_6;
  v25 = 164;
  v13 = 165;
  if ( !a3 )
    goto LABEL_6;
  v25 = 165;
  v13 = 166;
  if ( !a4 || (v25 = 166, v13 = 167, !a5) || (v25 = 167, v13 = 168, !v11) || (v25 = 168, v13 = 169, !v12) )
  {
LABEL_6:
    LastFailureAsHRESULT = -2147024809;
LABEL_7:
    v26 = v13;
    goto LABEL_45;
  }
  LastFailureAsHRESULT = 0;
  v25 = 169;
  LastFailureAsHRESULT = (*(__int64 (__fastcall **)(struct ISdFileRecord *, unsigned __int16 **))(*(_QWORD *)a3 + 32LL))(
                           a3,
                           &v29);
  v13 = 171;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_7;
  v25 = 171;
  LastFailureAsHRESULT = (*(__int64 (__fastcall **)(struct ISdFileRecord *, PSECURITY_DESCRIPTOR *, ULONG *))(*(_QWORD *)a3 + 136LL))(
                           a3,
                           &pSecurityDescriptor,
                           &SecurityDescriptorLength);
  v13 = 174;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_7;
  v25 = 174;
  if ( !pSecurityDescriptor || !SecurityDescriptorLength )
  {
    LastFailureAsHRESULT = 1;
    v25 = 179;
    goto LABEL_45;
  }
  if ( !GetSecurityDescriptorControl(pSecurityDescriptor, &pControl, &dwRevision) )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v14);
    v13 = 184;
    goto LABEL_7;
  }
  v25 = 184;
  v15 = pControl;
  v13 = 189;
  if ( (pControl & 0x8000u) == 0 )
    goto LABEL_21;
  LastFailureAsHRESULT = 0;
  v25 = 189;
  v16 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_052bc5b66f273e09fada3dec80af9ee3_Traceguids, v29);
      v15 = pControl;
      v16 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v16 != &WPP_GLOBAL_Control && (*((_BYTE *)v16 + 28) & 2) != 0 )
    {
      WPP_SF_DDDDDDD(
        v16[2],
        17,
        *((unsigned __int16 *)pSecurityDescriptor + 1),
        *(unsigned __int8 *)pSecurityDescriptor,
        *((unsigned __int8 *)pSecurityDescriptor + 1),
        *((unsigned __int16 *)pSecurityDescriptor + 1),
        *((_DWORD *)pSecurityDescriptor + 1),
        *((_DWORD *)pSecurityDescriptor + 2),
        *((_DWORD *)pSecurityDescriptor + 4),
        *((_DWORD *)pSecurityDescriptor + 3));
      v15 = pControl;
    }
  }
  if ( (v15 & 0x400) != 0 )
  {
    v15 |= 0x100u;
    pControl = v15;
  }
  if ( (v15 & 0x800) != 0 )
  {
    v15 |= 0x200u;
    pControl = v15;
  }
  *((_WORD *)pSecurityDescriptor + 1) = v15;
  LastFailureAsHRESULT = AlterExistingSecurityDescriptor(
                           a1,
                           a2,
                           a4,
                           a5,
                           pSecurityDescriptor,
                           SecurityDescriptorLength,
                           &pv,
                           &v28);
  v13 = 211;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_7;
  v25 = 211;
  if ( !GetSecurityDescriptorControl(pv, &pControl, &dwRevision) )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v17);
    v13 = 215;
    goto LABEL_7;
  }
  v25 = 215;
  v18 = pControl;
  v13 = 217;
  if ( (pControl & 0x8000u) == 0 )
  {
LABEL_21:
    LastFailureAsHRESULT = -2147023558;
    goto LABEL_7;
  }
  LastFailureAsHRESULT = 0;
  v25 = 217;
  if ( (pControl & 0x400) != 0 )
  {
    v18 = pControl | 0x100;
    pControl |= 0x100u;
  }
  if ( (v18 & 0x800) != 0 )
  {
    v18 |= 0x200u;
    pControl = v18;
  }
  *((_WORD *)pv + 1) = v18;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_DDDDDDD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      18,
      pv,
      *(unsigned __int8 *)pv,
      *((unsigned __int8 *)pv + 1),
      pControl,
      *((_DWORD *)pv + 1),
      *((_DWORD *)pv + 2),
      *((_DWORD *)pv + 4),
      *((_DWORD *)pv + 3));
  *v12 = v28;
  *v11 = (unsigned __int8 *)pv;
  pv = 0;
LABEL_45:
  SdFreeString(&v29);
  CoTaskMemFree(pSecurityDescriptor);
  pSecurityDescriptor = 0;
  CoTaskMemFree(pv);
  pv = 0;
  v19 = LastFailureAsHRESULT;
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&LastFailureAsHRESULT);
  return v19;
}

```

## disassembly

```asm
0x180026738  mov     [rsp-8+arg_8], rbx
0x18002673d  mov     [rsp-8+arg_10], rsi
0x180026742  push    rbp
0x180026743  push    rdi
0x180026744  push    r12
0x180026746  push    r13
0x180026748  push    r15
0x18002674a  lea     rbp, [rsp-1Fh]
0x18002674f  sub     rsp, 0B0h
0x180026756  mov     r12, r9
0x180026759  mov     rbx, r8
0x18002675c  mov     r13, rdx
0x18002675f  mov     r15, rcx
0x180026762  mov     r9d, 1; unsigned __int16
0x180026768  mov     r8d, 97h; unsigned __int16
0x18002676e  lea     rdx, aGetrelativesdf; "GetRelativeSDFromFileRecordForAdminRest"...
0x180026775  lea     rcx, [rbp+3Fh+var_68]; this
0x180026779  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18002677e  xor     ecx, ecx
0x180026780  mov     [rbp+3Fh+var_78], ecx
0x180026783  mov     [rbp+3Fh+dwRevision], ecx
0x180026786  mov     [rbp+3Fh+var_28], rcx
0x18002678a  mov     [rbp+3Fh+pControl], cx
0x18002678e  mov     [rbp+3Fh+pSecurityDescriptor], rcx
0x180026792  mov     [rbp+3Fh+pv], rcx
0x180026796  mov     [rbp+3Fh+var_2C], ecx
0x180026799  mov     rsi, [rbp+3Fh+arg_28]
0x18002679d  test    rsi, rsi
0x1800267a0  jz      short loc_1800267A5
0x1800267a2  mov     [rsi], rcx
0x1800267a5  mov     rdi, [rbp+3Fh+arg_30]
0x1800267a9  test    rdi, rdi
0x1800267ac  jz      short loc_1800267B0
0x1800267ae  mov     [rdi], ecx
0x1800267b0  mov     eax, 0A3h
0x1800267b5  test    r15, r15
0x1800267b8  jnz     short loc_1800267CA
0x1800267ba  mov     [rbp+3Fh+var_68], 80070057h
0x1800267c1  mov     [rbp+3Fh+var_62], ax
0x1800267c5  jmp     loc_180026B01
0x1800267ca  mov     [rbp+3Fh+var_64], ax
0x1800267ce  mov     eax, 0A4h
0x1800267d3  test    r13, r13
0x1800267d6  jz      short loc_1800267BA
0x1800267d8  mov     [rbp+3Fh+var_64], ax
0x1800267dc  mov     eax, 0A5h
0x1800267e1  test    rbx, rbx
0x1800267e4  jz      short loc_1800267BA
0x1800267e6  mov     [rbp+3Fh+var_64], ax
0x1800267ea  mov     eax, 0A6h
0x1800267ef  test    r12, r12
0x1800267f2  jz      short loc_1800267BA
0x1800267f4  mov     [rbp+3Fh+var_64], ax
0x1800267f8  mov     eax, 0A7h
0x1800267fd  cmp     [rbp+3Fh+arg_20], rcx
0x180026801  jz      short loc_1800267BA
0x180026803  mov     [rbp+3Fh+var_64], ax
0x180026807  mov     eax, 0A8h
0x18002680c  test    rsi, rsi
0x18002680f  jz      short loc_1800267BA
0x180026811  mov     [rbp+3Fh+var_64], ax
0x180026815  mov     eax, 0A9h
0x18002681a  test    rdi, rdi
0x18002681d  jz      short loc_1800267BA
0x18002681f  mov     [rbp+3Fh+var_68], ecx
0x180026822  mov     [rbp+3Fh+var_64], ax
0x180026826  mov     rax, [rbx]
0x180026829  lea     rdx, [rbp+3Fh+var_28]
0x18002682d  mov     rcx, rbx
0x180026830  mov     rax, [rax+20h]
0x180026834  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026839  mov     [rbp+3Fh+var_68], eax
0x18002683c  test    eax, eax
0x18002683e  mov     eax, 0ABh
0x180026843  js      loc_1800267C1
0x180026849  mov     [rbp+3Fh+var_64], ax
0x18002684d  mov     rax, [rbx]
0x180026850  lea     r8, [rbp+3Fh+var_78]
0x180026854  lea     rdx, [rbp+3Fh+pSecurityDescriptor]
0x180026858  mov     rcx, rbx
0x18002685b  mov     rax, [rax+88h]
0x180026862  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026867  mov     [rbp+3Fh+var_68], eax
0x18002686a  test    eax, eax
0x18002686c  mov     eax, 0AEh
0x180026871  js      loc_1800267C1
0x180026877  mov     [rbp+3Fh+var_64], ax
0x18002687b  mov     rcx, [rbp+3Fh+pSecurityDescriptor]; pSecurityDescriptor
0x18002687f  test    rcx, rcx
0x180026882  jz      loc_180026AF1
0x180026888  cmp     [rbp+3Fh+var_78], 0
0x18002688c  jz      loc_180026AF1
0x180026892  lea     r8, [rbp+3Fh+dwRevision]; lpdwRevision
0x180026896  lea     rdx, [rbp+3Fh+pControl]; pControl
0x18002689a  call    cs:__imp_GetSecurityDescriptorControl
0x1800268a1  nop     dword ptr [rax+rax+00h]
0x1800268a6  test    eax, eax
0x1800268a8  jnz     short loc_1800268BC
0x1800268aa  call    GetLastFailureAsHRESULT
0x1800268af  mov     [rbp+3Fh+var_68], eax
0x1800268b2  mov     eax, 0B8h
0x1800268b7  jmp     loc_1800267C1
0x1800268bc  mov     eax, 0B8h
0x1800268c1  mov     [rbp+3Fh+var_64], ax
0x1800268c5  movzx   ecx, [rbp+3Fh+pControl]
0x1800268c9  mov     eax, 0BDh
0x1800268ce  bt      cx, 0Fh
0x1800268d3  jb      short loc_1800268E1
0x1800268d5  mov     [rbp+3Fh+var_68], 8007053Ah
0x1800268dc  jmp     loc_1800267C1
0x1800268e1  mov     [rbp+3Fh+var_68], 0
0x1800268e8  mov     [rbp+3Fh+var_64], ax
0x1800268ec  lea     rax, WPP_GLOBAL_Control
0x1800268f3  mov     bl, 2
0x1800268f5  mov     r11, cs:WPP_GLOBAL_Control
0x1800268fc  cmp     r11, rax
0x1800268ff  jz      loc_18002698B
0x180026905  test    [r11+1Ch], bl
0x180026909  jz      short loc_180026936
0x18002690b  mov     edx, 10h
0x180026910  mov     r9, [rbp+3Fh+var_28]
0x180026914  lea     r8, WPP_052bc5b66f273e09fada3dec80af9ee3_Traceguids
0x18002691b  mov     rcx, [r11+10h]
0x18002691f  call    WPP_SF_S
0x180026924  movzx   ecx, [rbp+3Fh+pControl]
0x180026928  mov     r11, cs:WPP_GLOBAL_Control
0x18002692f  lea     rax, WPP_GLOBAL_Control
0x180026936  cmp     r11, rax
0x180026939  jz      short loc_18002698B
0x18002693b  test    [r11+1Ch], bl
0x18002693f  jz      short loc_18002698B
0x180026941  mov     rcx, [rbp+3Fh+pSecurityDescriptor]
0x180026945  movzx   r8d, word ptr [rcx+2]
0x18002694a  movzx   r10d, byte ptr [rcx+1]
0x18002694f  movzx   r9d, byte ptr [rcx]
0x180026953  mov     edx, 11h
0x180026958  mov     eax, [rcx+0Ch]
0x18002695b  mov     [rsp+0D0h+var_88], eax
0x18002695f  mov     eax, [rcx+10h]
0x180026962  mov     [rsp+0D0h+var_90], eax
0x180026966  mov     eax, [rcx+8]
0x180026969  mov     dword ptr [rsp+0D0h+var_98], eax
0x18002696d  mov     eax, [rcx+4]
0x180026970  mov     dword ptr [rsp+0D0h+var_A0], eax
0x180026974  mov     [rsp+0D0h+SecurityDescriptorLength], r8d
0x180026979  mov     dword ptr [rsp+0D0h+SecurityDescriptorInput], r10d
0x18002697e  mov     rcx, [r11+10h]
0x180026982  call    WPP_SF_DDDDDDD
0x180026987  movzx   ecx, [rbp+3Fh+pControl]
0x18002698b  bt      cx, 0Ah
0x180026990  jnb     short loc_18002699B
0x180026992  or      cx, 100h
0x180026997  mov     [rbp+3Fh+pControl], cx
0x18002699b  bt      cx, 0Bh
0x1800269a0  jnb     short loc_1800269AB
0x1800269a2  or      cx, 200h
0x1800269a7  mov     [rbp+3Fh+pControl], cx
0x1800269ab  mov     rax, [rbp+3Fh+pSecurityDescriptor]
0x1800269af  mov     [rax+2], cx
0x1800269b3  lea     rax, [rbp+3Fh+var_2C]
0x1800269b7  mov     [rsp+0D0h+var_98], rax; unsigned int *
0x1800269bc  lea     rax, [rbp+3Fh+pv]
0x1800269c0  mov     [rsp+0D0h+var_A0], rax; void **
0x1800269c5  mov     eax, [rbp+3Fh+var_78]
0x1800269c8  mov     [rsp+0D0h+SecurityDescriptorLength], eax; SecurityDescriptorLength
0x1800269cc  mov     rax, [rbp+3Fh+pSecurityDescriptor]
0x1800269d0  mov     [rsp+0D0h+SecurityDescriptorInput], rax; SecurityDescriptorInput
0x1800269d5  mov     r9, [rbp+3Fh+arg_20]; struct CSdUserSidList *
0x1800269d9  mov     r8, r12; struct ISdGlobalCatalog *
0x1800269dc  mov     rdx, r13; struct ISdCallback2 *
0x1800269df  mov     rcx, r15; struct ISdAsyncPriv *
0x1800269e2  call    ?AlterExistingSecurityDescriptor@@YAJPEAUISdAsyncPriv@@PEAUISdCallback2@@PEAUISdGlobalCatalog@@PEAVCSdUserSidList@@QEAXKPEAPEAXPEAK@Z; AlterExistingSecurityDescriptor(ISdAsyncPriv *,ISdCallback2 *,ISdGlobalCatalog *,CSdUserSidList *,void * const,ulong,void * *,ulong *)
0x1800269e7  mov     [rbp+3Fh+var_68], eax
0x1800269ea  test    eax, eax
0x1800269ec  mov     eax, 0D3h
0x1800269f1  js      loc_1800267C1
0x1800269f7  mov     [rbp+3Fh+var_64], ax
0x1800269fb  lea     r8, [rbp+3Fh+dwRevision]; lpdwRevision
0x1800269ff  lea     rdx, [rbp+3Fh+pControl]; pControl
0x180026a03  mov     rcx, [rbp+3Fh+pv]; pSecurityDescriptor
0x180026a07  call    cs:__imp_GetSecurityDescriptorControl
0x180026a0e  nop     dword ptr [rax+rax+00h]
0x180026a13  test    eax, eax
0x180026a15  jnz     short loc_180026A29
0x180026a17  call    GetLastFailureAsHRESULT
0x180026a1c  mov     [rbp+3Fh+var_68], eax
0x180026a1f  mov     eax, 0D7h
0x180026a24  jmp     loc_1800267C1
0x180026a29  mov     eax, 0D7h
0x180026a2e  mov     [rbp+3Fh+var_64], ax
0x180026a32  movzx   ecx, [rbp+3Fh+pControl]
0x180026a36  mov     eax, 0D9h
0x180026a3b  bt      cx, 0Fh
0x180026a40  jnb     loc_1800268D5
0x180026a46  mov     [rbp+3Fh+var_68], 0
0x180026a4d  mov     [rbp+3Fh+var_64], ax
0x180026a51  bt      cx, 0Ah
0x180026a56  jnb     short loc_180026A61
0x180026a58  or      cx, 100h
0x180026a5d  mov     [rbp+3Fh+pControl], cx
0x180026a61  bt      cx, 0Bh
0x180026a66  jnb     short loc_180026A71
0x180026a68  or      cx, 200h
0x180026a6d  mov     [rbp+3Fh+pControl], cx
0x180026a71  mov     rax, [rbp+3Fh+pv]
0x180026a75  mov     [rax+2], cx
0x180026a79  mov     rcx, cs:WPP_GLOBAL_Control
0x180026a80  lea     rax, WPP_GLOBAL_Control
0x180026a87  cmp     rcx, rax
0x180026a8a  jz      short loc_180026ADB
0x180026a8c  test    [rcx+1Ch], bl
0x180026a8f  jz      short loc_180026ADB
0x180026a91  movzx   r11d, [rbp+3Fh+pControl]
0x180026a96  mov     r8, [rbp+3Fh+pv]
0x180026a9a  movzx   r10d, byte ptr [r8+1]
0x180026a9f  movzx   r9d, byte ptr [r8]
0x180026aa3  mov     edx, 12h
0x180026aa8  mov     eax, [r8+0Ch]
0x180026aac  mov     [rsp+0D0h+var_88], eax
0x180026ab0  mov     eax, [r8+10h]
0x180026ab4  mov     [rsp+0D0h+var_90], eax
0x180026ab8  mov     eax, [r8+8]
0x180026abc  mov     dword ptr [rsp+0D0h+var_98], eax
0x180026ac0  mov     eax, [r8+4]
0x180026ac4  mov     dword ptr [rsp+0D0h+var_A0], eax
0x180026ac8  mov     [rsp+0D0h+SecurityDescriptorLength], r11d
0x180026acd  mov     dword ptr [rsp+0D0h+SecurityDescriptorInput], r10d
0x180026ad2  mov     rcx, [rcx+10h]
0x180026ad6  call    WPP_SF_DDDDDDD
0x180026adb  mov     eax, [rbp+3Fh+var_2C]
0x180026ade  mov     [rdi], eax
0x180026ae0  mov     rax, [rbp+3Fh+pv]
0x180026ae4  mov     [rsi], rax
0x180026ae7  mov     [rbp+3Fh+pv], 0
0x180026aef  jmp     short loc_180026B01
0x180026af1  mov     [rbp+3Fh+var_68], 1
0x180026af8  mov     eax, 0B3h
0x180026afd  mov     [rbp+3Fh+var_64], ax
0x180026b01  lea     rcx, [rbp+3Fh+var_28]; unsigned __int16 **
0x180026b05  call    ?SdFreeString@@YAXPEAPEAG@Z; SdFreeString(ushort * *)
0x180026b0a  mov     rcx, [rbp+3Fh+pSecurityDescriptor]; pv
0x180026b0e  call    cs:__imp_CoTaskMemFree
0x180026b15  nop     dword ptr [rax+rax+00h]
0x180026b1a  mov     [rbp+3Fh+pSecurityDescriptor], 0
0x180026b22  mov     rcx, [rbp+3Fh+pv]; pv
0x180026b26  call    cs:__imp_CoTaskMemFree
0x180026b2d  nop     dword ptr [rax+rax+00h]
0x180026b32  mov     [rbp+3Fh+pv], 0
0x180026b3a  mov     ebx, [rbp+3Fh+var_68]
0x180026b3d  lea     rcx, [rbp+3Fh+var_68]; this
0x180026b41  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180026b46  mov     eax, ebx
0x180026b48  lea     r11, [rsp+0D0h+var_20]
0x180026b50  mov     rbx, [r11+38h]
0x180026b54  mov     rsi, [r11+40h]
0x180026b58  mov     rsp, r11
0x180026b5b  pop     r15
0x180026b5d  pop     r13
0x180026b5f  pop     r12
0x180026b61  pop     rdi
0x180026b62  pop     rbp
0x180026b63  retn
```
