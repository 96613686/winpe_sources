# GetRelativeSDFromFileRecordForAdminRestore(ISdAsyncPriv *,ISdCallback2 *,ISdFileRecord *,ISdGlobalCatalog *,CSdUserSidList *,uchar * *,ulong *)

- ea: `0x180025794`
- end: `0x180025ba8`
- name: `?GetRelativeSDFromFileRecordForAdminRestore@@YAJPEAUISdAsyncPriv@@PEAUISdCallback2@@PEAUISdFileRecord@@PEAUISdGlobalCatalog@@PEAVCSdUserSidList@@PEAPEAEPEAK@Z`
- size: `1044`
- prototype: `__int64 __usercall@<rax>(struct ISdAsyncPriv *@<rcx>, struct ISdCallback2 *@<rdx>, struct ISdFileRecord *@<r8>, struct ISdGlobalCatalog *@<r9>, struct CSdUserSidList *, unsigned __int8 **, unsigned int *)`
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180007438`
- `0x18002d470`

## callees

- `0x180008240`
- `0x180009a98`
- `0x180022564`
- `0x180025794`
- `0x180031a20`
- `0x18006fe84`
- `0x18006ff8c`
- `0x18008f5d0`
- `0x1800cb010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x1800258f6`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x180025a5d`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x1800258f6`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x180025a5d`
- `ole32!CoTaskMemFree` at `0x180025b5e`
- `ole32!CoTaskMemFree` at `0x180025b70`
- `ole32!CoTaskMemFree` at `0x180025b5e`
- `ole32!CoTaskMemFree` at `0x180025b70`

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
    151,
    1);
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
0x180025794  mov     [rsp-8+arg_8], rbx
0x180025799  mov     [rsp-8+arg_10], rsi
0x18002579e  push    rbp
0x18002579f  push    rdi
0x1800257a0  push    r12
0x1800257a2  push    r13
0x1800257a4  push    r15
0x1800257a6  lea     rbp, [rsp-1Fh]
0x1800257ab  sub     rsp, 0B0h
0x1800257b2  mov     r12, r9
0x1800257b5  mov     rbx, r8
0x1800257b8  mov     r13, rdx
0x1800257bb  mov     r15, rcx
0x1800257be  mov     r9d, 1; unsigned __int16
0x1800257c4  mov     r8d, 97h; unsigned __int16
0x1800257ca  lea     rdx, aGetrelativesdf; "GetRelativeSDFromFileRecordForAdminRest"...
0x1800257d1  lea     rcx, [rbp+3Fh+var_68]; this
0x1800257d5  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x1800257da  xor     ecx, ecx
0x1800257dc  mov     [rbp+3Fh+var_78], ecx
0x1800257df  mov     [rbp+3Fh+dwRevision], ecx
0x1800257e2  mov     [rbp+3Fh+var_28], rcx
0x1800257e6  mov     [rbp+3Fh+pControl], cx
0x1800257ea  mov     [rbp+3Fh+pSecurityDescriptor], rcx
0x1800257ee  mov     [rbp+3Fh+pv], rcx
0x1800257f2  mov     [rbp+3Fh+var_2C], ecx
0x1800257f5  mov     rsi, [rbp+3Fh+arg_28]
0x1800257f9  test    rsi, rsi
0x1800257fc  jz      short loc_180025801
0x1800257fe  mov     [rsi], rcx
0x180025801  mov     rdi, [rbp+3Fh+arg_30]
0x180025805  test    rdi, rdi
0x180025808  jz      short loc_18002580C
0x18002580a  mov     [rdi], ecx
0x18002580c  mov     eax, 0A3h
0x180025811  test    r15, r15
0x180025814  jnz     short loc_180025826
0x180025816  mov     [rbp+3Fh+var_68], 80070057h
0x18002581d  mov     [rbp+3Fh+var_62], ax
0x180025821  jmp     loc_180025B51
0x180025826  mov     [rbp+3Fh+var_64], ax
0x18002582a  mov     eax, 0A4h
0x18002582f  test    r13, r13
0x180025832  jz      short loc_180025816
0x180025834  mov     [rbp+3Fh+var_64], ax
0x180025838  mov     eax, 0A5h
0x18002583d  test    rbx, rbx
0x180025840  jz      short loc_180025816
0x180025842  mov     [rbp+3Fh+var_64], ax
0x180025846  mov     eax, 0A6h
0x18002584b  test    r12, r12
0x18002584e  jz      short loc_180025816
0x180025850  mov     [rbp+3Fh+var_64], ax
0x180025854  mov     eax, 0A7h
0x180025859  cmp     [rbp+3Fh+arg_20], rcx
0x18002585d  jz      short loc_180025816
0x18002585f  mov     [rbp+3Fh+var_64], ax
0x180025863  mov     eax, 0A8h
0x180025868  test    rsi, rsi
0x18002586b  jz      short loc_180025816
0x18002586d  mov     [rbp+3Fh+var_64], ax
0x180025871  mov     eax, 0A9h
0x180025876  test    rdi, rdi
0x180025879  jz      short loc_180025816
0x18002587b  mov     [rbp+3Fh+var_68], ecx
0x18002587e  mov     [rbp+3Fh+var_64], ax
0x180025882  mov     rax, [rbx]
0x180025885  lea     rdx, [rbp+3Fh+var_28]
0x180025889  mov     rcx, rbx
0x18002588c  mov     rax, [rax+20h]
0x180025890  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025895  mov     [rbp+3Fh+var_68], eax
0x180025898  test    eax, eax
0x18002589a  mov     eax, 0ABh
0x18002589f  js      loc_18002581D
0x1800258a5  mov     [rbp+3Fh+var_64], ax
0x1800258a9  mov     rax, [rbx]
0x1800258ac  lea     r8, [rbp+3Fh+var_78]
0x1800258b0  lea     rdx, [rbp+3Fh+pSecurityDescriptor]
0x1800258b4  mov     rcx, rbx
0x1800258b7  mov     rax, [rax+88h]
0x1800258be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800258c3  mov     [rbp+3Fh+var_68], eax
0x1800258c6  test    eax, eax
0x1800258c8  mov     eax, 0AEh
0x1800258cd  js      loc_18002581D
0x1800258d3  mov     [rbp+3Fh+var_64], ax
0x1800258d7  mov     rcx, [rbp+3Fh+pSecurityDescriptor]; pSecurityDescriptor
0x1800258db  test    rcx, rcx
0x1800258de  jz      loc_180025B41
0x1800258e4  cmp     [rbp+3Fh+var_78], 0
0x1800258e8  jz      loc_180025B41
0x1800258ee  lea     r8, [rbp+3Fh+dwRevision]; lpdwRevision
0x1800258f2  lea     rdx, [rbp+3Fh+pControl]; pControl
0x1800258f6  call    cs:__imp_GetSecurityDescriptorControl
0x1800258fc  test    eax, eax
0x1800258fe  jnz     short loc_180025912
0x180025900  call    GetLastFailureAsHRESULT
0x180025905  mov     [rbp+3Fh+var_68], eax
0x180025908  mov     eax, 0B8h
0x18002590d  jmp     loc_18002581D
0x180025912  mov     eax, 0B8h
0x180025917  mov     [rbp+3Fh+var_64], ax
0x18002591b  movzx   ecx, [rbp+3Fh+pControl]
0x18002591f  mov     eax, 0BDh
0x180025924  bt      cx, 0Fh
0x180025929  jb      short loc_180025937
0x18002592b  mov     [rbp+3Fh+var_68], 8007053Ah
0x180025932  jmp     loc_18002581D
0x180025937  mov     [rbp+3Fh+var_68], 0
0x18002593e  mov     [rbp+3Fh+var_64], ax
0x180025942  lea     rax, WPP_GLOBAL_Control
0x180025949  mov     bl, 2
0x18002594b  mov     r11, cs:WPP_GLOBAL_Control
0x180025952  cmp     r11, rax
0x180025955  jz      loc_1800259E1
0x18002595b  test    [r11+1Ch], bl
0x18002595f  jz      short loc_18002598C
0x180025961  mov     edx, 10h
0x180025966  mov     r9, [rbp+3Fh+var_28]
0x18002596a  lea     r8, WPP_052bc5b66f273e09fada3dec80af9ee3_Traceguids
0x180025971  mov     rcx, [r11+10h]
0x180025975  call    WPP_SF_S
0x18002597a  movzx   ecx, [rbp+3Fh+pControl]
0x18002597e  mov     r11, cs:WPP_GLOBAL_Control
0x180025985  lea     rax, WPP_GLOBAL_Control
0x18002598c  cmp     r11, rax
0x18002598f  jz      short loc_1800259E1
0x180025991  test    [r11+1Ch], bl
0x180025995  jz      short loc_1800259E1
0x180025997  mov     rcx, [rbp+3Fh+pSecurityDescriptor]
0x18002599b  movzx   r8d, word ptr [rcx+2]
0x1800259a0  movzx   r10d, byte ptr [rcx+1]
0x1800259a5  movzx   r9d, byte ptr [rcx]
0x1800259a9  mov     edx, 11h
0x1800259ae  mov     eax, [rcx+0Ch]
0x1800259b1  mov     [rsp+0D0h+var_88], eax
0x1800259b5  mov     eax, [rcx+10h]
0x1800259b8  mov     [rsp+0D0h+var_90], eax
0x1800259bc  mov     eax, [rcx+8]
0x1800259bf  mov     dword ptr [rsp+0D0h+var_98], eax
0x1800259c3  mov     eax, [rcx+4]
0x1800259c6  mov     dword ptr [rsp+0D0h+var_A0], eax
0x1800259ca  mov     [rsp+0D0h+SecurityDescriptorLength], r8d
0x1800259cf  mov     dword ptr [rsp+0D0h+SecurityDescriptorInput], r10d
0x1800259d4  mov     rcx, [r11+10h]
0x1800259d8  call    WPP_SF_DDDDDDD
0x1800259dd  movzx   ecx, [rbp+3Fh+pControl]
0x1800259e1  bt      cx, 0Ah
0x1800259e6  jnb     short loc_1800259F1
0x1800259e8  or      cx, 100h
0x1800259ed  mov     [rbp+3Fh+pControl], cx
0x1800259f1  bt      cx, 0Bh
0x1800259f6  jnb     short loc_180025A01
0x1800259f8  or      cx, 200h
0x1800259fd  mov     [rbp+3Fh+pControl], cx
0x180025a01  mov     rax, [rbp+3Fh+pSecurityDescriptor]
0x180025a05  mov     [rax+2], cx
0x180025a09  lea     rax, [rbp+3Fh+var_2C]
0x180025a0d  mov     [rsp+0D0h+var_98], rax; unsigned int *
0x180025a12  lea     rax, [rbp+3Fh+pv]
0x180025a16  mov     [rsp+0D0h+var_A0], rax; void **
0x180025a1b  mov     eax, [rbp+3Fh+var_78]
0x180025a1e  mov     [rsp+0D0h+SecurityDescriptorLength], eax; SecurityDescriptorLength
0x180025a22  mov     rax, [rbp+3Fh+pSecurityDescriptor]
0x180025a26  mov     [rsp+0D0h+SecurityDescriptorInput], rax; SecurityDescriptorInput
0x180025a2b  mov     r9, [rbp+3Fh+arg_20]; struct CSdUserSidList *
0x180025a2f  mov     r8, r12; struct ISdGlobalCatalog *
0x180025a32  mov     rdx, r13; struct ISdCallback2 *
0x180025a35  mov     rcx, r15; struct ISdAsyncPriv *
0x180025a38  call    ?AlterExistingSecurityDescriptor@@YAJPEAUISdAsyncPriv@@PEAUISdCallback2@@PEAUISdGlobalCatalog@@PEAVCSdUserSidList@@QEAXKPEAPEAXPEAK@Z; AlterExistingSecurityDescriptor(ISdAsyncPriv *,ISdCallback2 *,ISdGlobalCatalog *,CSdUserSidList *,void * const,ulong,void * *,ulong *)
0x180025a3d  mov     [rbp+3Fh+var_68], eax
0x180025a40  test    eax, eax
0x180025a42  mov     eax, 0D3h
0x180025a47  js      loc_18002581D
0x180025a4d  mov     [rbp+3Fh+var_64], ax
0x180025a51  lea     r8, [rbp+3Fh+dwRevision]; lpdwRevision
0x180025a55  lea     rdx, [rbp+3Fh+pControl]; pControl
0x180025a59  mov     rcx, [rbp+3Fh+pv]; pSecurityDescriptor
0x180025a5d  call    cs:__imp_GetSecurityDescriptorControl
0x180025a63  test    eax, eax
0x180025a65  jnz     short loc_180025A79
0x180025a67  call    GetLastFailureAsHRESULT
0x180025a6c  mov     [rbp+3Fh+var_68], eax
0x180025a6f  mov     eax, 0D7h
0x180025a74  jmp     loc_18002581D
0x180025a79  mov     eax, 0D7h
0x180025a7e  mov     [rbp+3Fh+var_64], ax
0x180025a82  movzx   ecx, [rbp+3Fh+pControl]
0x180025a86  mov     eax, 0D9h
0x180025a8b  bt      cx, 0Fh
0x180025a90  jnb     loc_18002592B
0x180025a96  mov     [rbp+3Fh+var_68], 0
0x180025a9d  mov     [rbp+3Fh+var_64], ax
0x180025aa1  bt      cx, 0Ah
0x180025aa6  jnb     short loc_180025AB1
0x180025aa8  or      cx, 100h
0x180025aad  mov     [rbp+3Fh+pControl], cx
0x180025ab1  bt      cx, 0Bh
0x180025ab6  jnb     short loc_180025AC1
0x180025ab8  or      cx, 200h
0x180025abd  mov     [rbp+3Fh+pControl], cx
0x180025ac1  mov     rax, [rbp+3Fh+pv]
0x180025ac5  mov     [rax+2], cx
0x180025ac9  mov     rcx, cs:WPP_GLOBAL_Control
0x180025ad0  lea     rax, WPP_GLOBAL_Control
0x180025ad7  cmp     rcx, rax
0x180025ada  jz      short loc_180025B2B
0x180025adc  test    [rcx+1Ch], bl
0x180025adf  jz      short loc_180025B2B
0x180025ae1  movzx   r11d, [rbp+3Fh+pControl]
0x180025ae6  mov     r8, [rbp+3Fh+pv]
0x180025aea  movzx   r10d, byte ptr [r8+1]
0x180025aef  movzx   r9d, byte ptr [r8]
0x180025af3  mov     edx, 12h
0x180025af8  mov     eax, [r8+0Ch]
0x180025afc  mov     [rsp+0D0h+var_88], eax
0x180025b00  mov     eax, [r8+10h]
0x180025b04  mov     [rsp+0D0h+var_90], eax
0x180025b08  mov     eax, [r8+8]
0x180025b0c  mov     dword ptr [rsp+0D0h+var_98], eax
0x180025b10  mov     eax, [r8+4]
0x180025b14  mov     dword ptr [rsp+0D0h+var_A0], eax
0x180025b18  mov     [rsp+0D0h+SecurityDescriptorLength], r11d
0x180025b1d  mov     dword ptr [rsp+0D0h+SecurityDescriptorInput], r10d
0x180025b22  mov     rcx, [rcx+10h]
0x180025b26  call    WPP_SF_DDDDDDD
0x180025b2b  mov     eax, [rbp+3Fh+var_2C]
0x180025b2e  mov     [rdi], eax
0x180025b30  mov     rax, [rbp+3Fh+pv]
0x180025b34  mov     [rsi], rax
0x180025b37  mov     [rbp+3Fh+pv], 0
0x180025b3f  jmp     short loc_180025B51
0x180025b41  mov     [rbp+3Fh+var_68], 1
0x180025b48  mov     eax, 0B3h
0x180025b4d  mov     [rbp+3Fh+var_64], ax
0x180025b51  lea     rcx, [rbp+3Fh+var_28]; unsigned __int16 **
0x180025b55  call    ?SdFreeString@@YAXPEAPEAG@Z; SdFreeString(ushort * *)
0x180025b5a  mov     rcx, [rbp+3Fh+pSecurityDescriptor]; pv
0x180025b5e  call    cs:__imp_CoTaskMemFree
0x180025b64  mov     [rbp+3Fh+pSecurityDescriptor], 0
0x180025b6c  mov     rcx, [rbp+3Fh+pv]; pv
0x180025b70  call    cs:__imp_CoTaskMemFree
0x180025b76  mov     [rbp+3Fh+pv], 0
0x180025b7e  mov     ebx, [rbp+3Fh+var_68]
0x180025b81  lea     rcx, [rbp+3Fh+var_68]; this
0x180025b85  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180025b8a  mov     eax, ebx
0x180025b8c  lea     r11, [rsp+0D0h+var_20]
0x180025b94  mov     rbx, [r11+38h]
0x180025b98  mov     rsi, [r11+40h]
0x180025b9c  mov     rsp, r11
0x180025b9f  pop     r15
0x180025ba1  pop     r13
0x180025ba3  pop     r12
0x180025ba5  pop     rdi
0x180025ba6  pop     rbp
0x180025ba7  retn
```
