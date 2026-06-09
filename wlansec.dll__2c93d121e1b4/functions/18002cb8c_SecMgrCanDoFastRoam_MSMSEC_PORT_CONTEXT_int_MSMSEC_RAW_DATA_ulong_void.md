# SecMgrCanDoFastRoam(MSMSEC_PORT_CONTEXT *,int *,MSMSEC_RAW_DATA *,ulong *,void * *)

- ea: `0x18002cb8c`
- end: `0x18002d131`
- name: `?SecMgrCanDoFastRoam@@YAKPEAUMSMSEC_PORT_CONTEXT@@PEAHPEAUMSMSEC_RAW_DATA@@PEAKPEAPEAX@Z`
- size: `1445`
- prototype: `unsigned int __usercall@<eax>(struct MSMSEC_PORT_CONTEXT *@<rcx>, int *@<rdx>, struct MSMSEC_RAW_DATA *@<r8>, unsigned int *@<r9>, void **)`
- caller_count: `1`
- callee_count: `17`
- tags: ``

## callers

- `0x18002ca20`

## callees

- `0x1800083bc`
- `0x18000892c`
- `0x180008998`
- `0x18000bde0`
- `0x18000d5e4`
- `0x18001057c`
- `0x1800169c0`
- `0x18001f29c`
- `0x18002cb8c`
- `0x18002d138`
- `0x18002d25c`
- `0x18002d79c`
- `0x18002ddd4`
- `0x18003e5bc`
- `0x18004456c`
- `0x180062824`
- `0x180071050`

## import_xrefs

- `OneX!OneXFreeAuthParams` at `0x18002ce5e`
- `OneX!OneXFreeAuthParams` at `0x18002ce5e`
- `MobileNetworking!ReleaseWriteLock` at `0x18002d0e8`
- `MobileNetworking!ReleaseWriteLock` at `0x18002d0e8`
- `MobileNetworking!AcquireWriteLock` at `0x18002cf87`
- `MobileNetworking!AcquireWriteLock` at `0x18002cf87`

## pseudocode

```c
__int64 __fastcall SecMgrCanDoFastRoam(
        struct MSMSEC_PORT_CONTEXT *a1,
        int *a2,
        struct MSMSEC_RAW_DATA *a3,
        unsigned int *a4,
        void **a5)
{
  int v7; // r13d
  void *v8; // r15
  unsigned int v9; // esi
  int v10; // edi
  PVOID *v11; // rcx
  __int64 v12; // rdx
  PVOID v14; // rcx
  const char *v15; // r9
  unsigned int v16; // eax
  unsigned __int16 v17; // cx
  int v18; // edi
  unsigned int v19; // esi
  struct DOT11_AUTH_AKM_SUITE *v20; // rdx
  unsigned int v21; // eax
  unsigned int v22; // edi
  unsigned int v23[2]; // [rsp+58h] [rbp-81h] BYREF
  unsigned int v24; // [rsp+60h] [rbp-79h] BYREF
  unsigned __int8 *v25; // [rsp+68h] [rbp-71h] BYREF
  unsigned __int8 *v26; // [rsp+70h] [rbp-69h] BYREF
  void *v27; // [rsp+78h] [rbp-61h] BYREF
  __int128 v28; // [rsp+80h] [rbp-59h] BYREF
  char v29[8]; // [rsp+98h] [rbp-41h] BYREF
  unsigned __int16 v30; // [rsp+A0h] [rbp-39h]
  __int64 v31; // [rsp+A8h] [rbp-31h]
  unsigned __int16 v32; // [rsp+B0h] [rbp-29h]
  struct DOT11_AUTH_AKM_SUITE *v33; // [rsp+B8h] [rbp-21h] BYREF
  unsigned __int16 v34; // [rsp+C2h] [rbp-17h]
  unsigned __int8 (*v35)[16]; // [rsp+C8h] [rbp-11h]
  unsigned int v36[16]; // [rsp+E8h] [rbp+Fh] BYREF

  v25 = 0;
  v26 = 0;
  v24 = 0;
  v7 = 0;
  memset_0(v29, 0, 0x48u);
  v23[1] = 0;
  v28 = 0;
  v8 = 0;
  v27 = 0;
  v23[0] = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 12, WPP_6b4468b8a73334dd0914b2db0c523d9b_Traceguids);
  if ( !(unsigned int)SecMgrProfileValidForFastRoam(a1) )
  {
    v9 = 0;
    v10 = 0;
    v11 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) == 0 )
      goto LABEL_13;
    v12 = 13;
    goto LABEL_12;
  }
  if ( QueryStationRSNIE(a1, &v25, v36) )
  {
    v9 = 0;
    v10 = 0;
    v11 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) == 0 )
      goto LABEL_13;
    v12 = 14;
LABEL_12:
    WPP_SF_(v11[7], v12, WPP_6b4468b8a73334dd0914b2db0c523d9b_Traceguids);
    v11 = (PVOID *)WPP_GLOBAL_Control;
LABEL_13:
    *a2 = 0;
    goto LABEL_14;
  }
  v16 = IEPRSNParseIE(v25 + 2, v25[1]);
  v9 = v16;
  if ( v16 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 15, WPP_6b4468b8a73334dd0914b2db0c523d9b_Traceguids, v16);
    goto LABEL_38;
  }
  v17 = v34;
  v18 = 0;
  if ( v34 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 17, WPP_6b4468b8a73334dd0914b2db0c523d9b_Traceguids, v34);
      v17 = v34;
    }
    v19 = 0;
    if ( v17 )
    {
      do
        MSMSecLogBuffer(L"Transmitted PMKID:", v35[v19++], 0x10u);
      while ( v19 < v34 );
    }
    v20 = (struct DOT11_AUTH_AKM_SUITE *)&v33;
    if ( v32 > 1u )
      v20 = v33;
    if ( IsFtAkmPresent(v32, v20) && !QueryStationMDDIE(a1, &v26, &v24) && v26 )
      v18 = 1;
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 16, WPP_6b4468b8a73334dd0914b2db0c523d9b_Traceguids);
  }
  TraceAdapterId(*(_DWORD *)(*((_QWORD *)a1 + 3) + 2496LL), ">>> Locking >>>");
  AcquireWriteLock(*((_QWORD *)a1 + 3), *((_QWORD *)a1 + 3) + 2512LL, "SecMgrCanDoFastRoam", 126);
  v21 = PmkCacheCheckFastRoam(
          (struct MSMSEC_PMKCACHE_CONTEXT *)(*((_QWORD *)a1 + 3) + 3000LL),
          (unsigned __int8 (*)[6])((char *)a1 + 302),
          v34,
          v35,
          v18,
          (struct MSMSEC_RAW_DATA *)&v28,
          v23,
          &v27);
  v8 = v27;
  v9 = v21;
  if ( !v21 && (v22 = v23[0]) != 0 && v27 && (unsigned int)RawDataIsNonEmpty(&v28) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), v9 + 18, WPP_6b4468b8a73334dd0914b2db0c523d9b_Traceguids);
    *a2 = 1;
    v7 = 1;
    *a4 = v22;
    v10 = 1;
    *a5 = v8;
    *((_QWORD *)a3 + 1) = *((_QWORD *)&v28 + 1);
    *(_DWORD *)a3 = v28;
    v11 = (PVOID *)WPP_GLOBAL_Control;
  }
  else
  {
    v9 = 0;
    v10 = 0;
    v7 = 1;
    v11 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) == 0 )
    {
      *a2 = 0;
    }
    else
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 19, WPP_6b4468b8a73334dd0914b2db0c523d9b_Traceguids);
      v11 = (PVOID *)WPP_GLOBAL_Control;
      *a2 = 0;
    }
  }
LABEL_14:
  if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 68) & 2) != 0 )
  {
    v14 = v11[7];
    v15 = "Enabled";
    if ( !v10 )
      v15 = "Disabled";
    WPP_SF_s(v14, 21, WPP_6b4468b8a73334dd0914b2db0c523d9b_Traceguids, v15);
    v11 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( (byte_1800AED45 & 1) != 0 )
  {
    McTemplateU0qjqqb6b6t_EventWriteTransfer(
      (_DWORD)a1 + 296,
      (unsigned int)"?R",
      *(_DWORD *)(*((_QWORD *)a1 + 3) + 2496LL),
      *((_QWORD *)a1 + 3) + 32,
      *((_DWORD *)a1 + 234),
      *((_DWORD *)a1 + 78),
      (__int64)a1 + 296,
      (__int64)a1 + 302,
      v10);
    v11 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !v10 )
  {
LABEL_38:
    FreeRawData(&v28);
    if ( v8 )
      OneXFreeAuthParams(v8);
    v11 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v7 )
  {
    TraceAdapterId(*(_DWORD *)(*((_QWORD *)a1 + 3) + 2496LL), "<<< Unlocking <<<");
    ReleaseWriteLock(*((_QWORD *)a1 + 3), *((_QWORD *)a1 + 3) + 2512LL, "SecMgrCanDoFastRoam", 188);
    v11 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v32 > 1u )
  {
    FreeWLMemory(v33);
    v11 = (PVOID *)WPP_GLOBAL_Control;
    v33 = 0;
  }
  v32 = 0;
  if ( v30 > 1u )
  {
    FreeWLMemory(v31);
    v11 = (PVOID *)WPP_GLOBAL_Control;
    v31 = 0;
  }
  v30 = 0;
  if ( v35 )
  {
    FreeWLMemory((unsigned __int8 *)v35);
    v11 = (PVOID *)WPP_GLOBAL_Control;
    v35 = 0;
  }
  v34 = 0;
  if ( v11 != &WPP_GLOBAL_Control && (*((_DWORD *)v11 + 17) & 0x100) != 0 )
    WPP_SF_d(v11[7], 22, WPP_6b4468b8a73334dd0914b2db0c523d9b_Traceguids, v9);
  return v9;
}

```

## disassembly

```asm
0x18002cb8c  mov     rax, rsp
0x18002cb8f  mov     [rax+8], rbx
0x18002cb93  mov     [rax+20h], r9
0x18002cb97  mov     [rax+18h], r8
0x18002cb9b  push    rbp
0x18002cb9c  push    rsi
0x18002cb9d  push    rdi
0x18002cb9e  push    r12
0x18002cba0  push    r13
0x18002cba2  push    r14
0x18002cba4  push    r15
0x18002cba6  lea     rbp, [rax-57h]
0x18002cbaa  sub     rsp, 0F0h
0x18002cbb1  xor     ebx, ebx
0x18002cbb3  mov     r12, rdx
0x18002cbb6  mov     r14, rcx
0x18002cbb9  mov     [rbp+4Fh+var_C0], rbx
0x18002cbbd  xor     edx, edx; Val
0x18002cbbf  mov     [rbp+4Fh+var_B8], rbx
0x18002cbc3  lea     rcx, [rbp+4Fh+var_90]; void *
0x18002cbc7  mov     [rbp+4Fh+var_C8], ebx
0x18002cbca  lea     r8d, [rbx+48h]; Size
0x18002cbce  mov     r13d, ebx
0x18002cbd1  call    memset_0
0x18002cbd6  xorps   xmm0, xmm0
0x18002cbd9  mov     [rbp+4Fh+var_CC], ebx
0x18002cbdc  movups  [rbp+4Fh+var_A8], xmm0
0x18002cbe0  mov     r15d, ebx
0x18002cbe3  mov     [rbp+4Fh+var_B0], rbx
0x18002cbe7  mov     [rsp+120h+var_D0], ebx
0x18002cbeb  mov     rcx, cs:WPP_GLOBAL_Control
0x18002cbf2  lea     rdi, WPP_GLOBAL_Control
0x18002cbf9  cmp     rcx, rdi
0x18002cbfc  jz      short loc_18002CC0B
0x18002cbfe  test    dword ptr [rcx+44h], 100h
0x18002cc05  jnz     loc_18002CDE4
0x18002cc0b  mov     rcx, r14; struct MSMSEC_PORT_CONTEXT *
0x18002cc0e  call    ?SecMgrProfileValidForFastRoam@@YAHPEAUMSMSEC_PORT_CONTEXT@@@Z; SecMgrProfileValidForFastRoam(MSMSEC_PORT_CONTEXT *)
0x18002cc13  test    eax, eax
0x18002cc15  jz      short loc_18002CC54
0x18002cc17  lea     r8, [rbp+4Fh+var_40]; unsigned int *
0x18002cc1b  mov     rcx, r14; struct MSMSEC_PORT_CONTEXT *
0x18002cc1e  lea     rdx, [rbp+4Fh+var_C0]; unsigned __int8 **
0x18002cc22  call    ?QueryStationRSNIE@@YAKPEBUMSMSEC_PORT_CONTEXT@@PEAPEAEPEAK@Z; QueryStationRSNIE(MSMSEC_PORT_CONTEXT const *,uchar * *,ulong *)
0x18002cc27  test    eax, eax
0x18002cc29  jz      loc_18002CDFE
0x18002cc2f  mov     esi, ebx
0x18002cc31  mov     edi, ebx
0x18002cc33  mov     rcx, cs:WPP_GLOBAL_Control
0x18002cc3a  lea     rax, WPP_GLOBAL_Control
0x18002cc41  mov     bl, 2
0x18002cc43  cmp     rcx, rax
0x18002cc46  jz      short loc_18002CC8E
0x18002cc48  test    [rcx+44h], bl
0x18002cc4b  jz      short loc_18002CC8E
0x18002cc4d  mov     edx, 0Eh
0x18002cc52  jmp     short loc_18002CC77
0x18002cc54  mov     esi, ebx
0x18002cc56  mov     edi, ebx
0x18002cc58  mov     rcx, cs:WPP_GLOBAL_Control
0x18002cc5f  lea     rax, WPP_GLOBAL_Control
0x18002cc66  mov     bl, 2
0x18002cc68  cmp     rcx, rax
0x18002cc6b  jz      short loc_18002CC8E
0x18002cc6d  test    [rcx+44h], bl
0x18002cc70  jz      short loc_18002CC8E
0x18002cc72  mov     edx, 0Dh
0x18002cc77  mov     rcx, [rcx+38h]
0x18002cc7b  lea     r8, WPP_6b4468b8a73334dd0914b2db0c523d9b_Traceguids
0x18002cc82  call    WPP_SF_
0x18002cc87  mov     rcx, cs:WPP_GLOBAL_Control
0x18002cc8e  mov     [r12], esi
0x18002cc92  mov     r12d, 1
0x18002cc98  lea     rax, WPP_GLOBAL_Control
0x18002cc9f  cmp     rcx, rax
0x18002cca2  jnz     loc_18002CDA6
0x18002cca8  xor     ebx, ebx
0x18002ccaa  test    cs:byte_1800AED45, r12b
0x18002ccb1  jz      short loc_18002CD07
0x18002ccb3  mov     r8, [r14+18h]
0x18002ccb7  lea     rax, [r14+12Eh]
0x18002ccbe  mov     [rsp+40h], edi
0x18002ccc2  lea     rcx, [r14+128h]
0x18002ccc9  mov     [rsp+120h+var_E8], rax
0x18002ccce  lea     rdx, MsmSecFastRoamEnabled; "?R"
0x18002ccd5  mov     eax, [r14+138h]
0x18002ccdc  mov     [rsp+120h+var_F0], rcx
0x18002cce1  lea     r9, [r8+20h]
0x18002cce5  mov     r8d, [r8+9C0h]
0x18002ccec  mov     dword ptr [rsp+120h+var_F8], eax
0x18002ccf0  mov     eax, [r14+3A8h]
0x18002ccf7  mov     [rsp+120h+var_100], eax
0x18002ccfb  call    McTemplateU0qjqqb6b6t_EventWriteTransfer
0x18002cd00  mov     rcx, cs:WPP_GLOBAL_Control
0x18002cd07  test    edi, edi
0x18002cd09  jz      loc_18002CE4D
0x18002cd0f  test    r13d, r13d
0x18002cd12  jnz     loc_18002D0BA
0x18002cd18  cmp     [rbp+4Fh+var_78], r12w
0x18002cd1d  ja      loc_18002D100
0x18002cd23  mov     [rbp+4Fh+var_78], bx
0x18002cd27  cmp     [rbp+4Fh+var_88], r12w
0x18002cd2c  ja      short loc_18002CD6D
0x18002cd2e  mov     rax, [rbp+4Fh+var_60]
0x18002cd32  mov     [rbp+4Fh+var_88], bx
0x18002cd36  test    rax, rax
0x18002cd39  jnz     loc_18002D119
0x18002cd3f  mov     [rbp+4Fh+var_66], bx
0x18002cd43  lea     rax, WPP_GLOBAL_Control
0x18002cd4a  cmp     rcx, rax
0x18002cd4d  jnz     short loc_18002CD83
0x18002cd4f  mov     rbx, [rsp+120h+arg_0]
0x18002cd57  mov     eax, esi
0x18002cd59  add     rsp, 0F0h
0x18002cd60  pop     r15
0x18002cd62  pop     r14
0x18002cd64  pop     r13
0x18002cd66  pop     r12
0x18002cd68  pop     rdi
0x18002cd69  pop     rsi
0x18002cd6a  pop     rbp
0x18002cd6b  retn
0x18002cd6d  mov     rcx, [rbp+4Fh+var_80]
0x18002cd71  call    FreeWLMemory
0x18002cd76  mov     rcx, cs:WPP_GLOBAL_Control
0x18002cd7d  mov     [rbp+4Fh+var_80], rbx
0x18002cd81  jmp     short loc_18002CD2E
0x18002cd83  test    dword ptr [rcx+44h], 100h
0x18002cd8a  jz      short loc_18002CD4F
0x18002cd8c  mov     rcx, [rcx+38h]
0x18002cd90  lea     r8, WPP_6b4468b8a73334dd0914b2db0c523d9b_Traceguids
0x18002cd97  mov     edx, 16h
0x18002cd9c  mov     r9d, esi
0x18002cd9f  call    WPP_SF_d
0x18002cda4  jmp     short loc_18002CD4F
0x18002cda6  test    [rcx+44h], bl
0x18002cda9  jz      loc_18002CCA8
0x18002cdaf  mov     rcx, [rcx+38h]
0x18002cdb3  lea     rax, aDisabled_0; "Disabled"
0x18002cdba  xor     ebx, ebx
0x18002cdbc  lea     r9, aEnabled_2; "Enabled"
0x18002cdc3  test    edi, edi
0x18002cdc5  lea     r8, WPP_6b4468b8a73334dd0914b2db0c523d9b_Traceguids
0x18002cdcc  cmovz   r9, rax
0x18002cdd0  lea     edx, [rbx+15h]
0x18002cdd3  call    WPP_SF_s
0x18002cdd8  mov     rcx, cs:WPP_GLOBAL_Control
0x18002cddf  jmp     loc_18002CCAA
0x18002cde4  mov     rcx, [rcx+38h]
0x18002cde8  lea     r8, WPP_6b4468b8a73334dd0914b2db0c523d9b_Traceguids
0x18002cdef  mov     edx, 0Ch
0x18002cdf4  call    WPP_SF_
0x18002cdf9  jmp     loc_18002CC0B
0x18002cdfe  mov     rcx, [rbp+4Fh+var_C0]
0x18002ce02  lea     r9, [rbp+4Fh+var_90]
0x18002ce06  lea     r8, [rbp+4Fh+var_CC]
0x18002ce0a  movzx   edx, byte ptr [rcx+1]; int
0x18002ce0e  add     rcx, 2; unsigned __int8 *
0x18002ce12  call    IEPRSNParseIE
0x18002ce17  mov     esi, eax
0x18002ce19  test    eax, eax
0x18002ce1b  jz      short loc_18002CE76
0x18002ce1d  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ce24  mov     r12d, 1
0x18002ce2a  cmp     rcx, rdi
0x18002ce2d  jz      short loc_18002CE4D
0x18002ce2f  test    [rcx+44h], r12b
0x18002ce33  jz      short loc_18002CE4D
0x18002ce35  mov     rcx, [rcx+38h]
0x18002ce39  lea     edx, [r12+0Eh]
0x18002ce3e  mov     r9d, eax
0x18002ce41  lea     r8, WPP_6b4468b8a73334dd0914b2db0c523d9b_Traceguids
0x18002ce48  call    WPP_SF_d
0x18002ce4d  lea     rcx, [rbp+4Fh+var_A8]
0x18002ce51  call    FreeRawData
0x18002ce56  test    r15, r15
0x18002ce59  jz      short loc_18002CE6A
0x18002ce5b  mov     rcx, r15
0x18002ce5e  call    cs:__imp_OneXFreeAuthParams
0x18002ce65  nop     dword ptr [rax+rax+00h]
0x18002ce6a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ce71  jmp     loc_18002CD0F
0x18002ce76  movzx   ecx, [rbp+4Fh+var_66]
0x18002ce7a  mov     edi, ebx
0x18002ce7c  mov     bl, 2
0x18002ce7e  test    cx, cx
0x18002ce81  jnz     short loc_18002CEBD
0x18002ce83  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ce8a  lea     rax, WPP_GLOBAL_Control
0x18002ce91  cmp     rcx, rax
0x18002ce94  jz      loc_18002CF59
0x18002ce9a  test    [rcx+44h], bl
0x18002ce9d  jz      loc_18002CF59
0x18002cea3  mov     rcx, [rcx+38h]
0x18002cea7  lea     r8, WPP_6b4468b8a73334dd0914b2db0c523d9b_Traceguids
0x18002ceae  mov     edx, 10h
0x18002ceb3  call    WPP_SF_
0x18002ceb8  jmp     loc_18002CF59
0x18002cebd  mov     rax, cs:WPP_GLOBAL_Control
0x18002cec4  lea     rdx, WPP_GLOBAL_Control
0x18002cecb  cmp     rax, rdx
0x18002cece  jz      short loc_18002CEF1
0x18002ced0  test    [rax+44h], bl
0x18002ced3  jz      short loc_18002CEF1
0x18002ced5  mov     r9d, ecx
0x18002ced8  lea     r8, WPP_6b4468b8a73334dd0914b2db0c523d9b_Traceguids
0x18002cedf  mov     rcx, [rax+38h]
0x18002cee3  mov     edx, 11h
0x18002cee8  call    WPP_SF_d
0x18002ceed  movzx   ecx, [rbp+4Fh+var_66]
0x18002cef1  mov     esi, r13d
0x18002cef4  cmp     r13w, cx
0x18002cef8  jnb     short loc_18002CF20
0x18002cefa  mov     edx, esi
0x18002cefc  lea     rcx, aTransmittedPmk; "Transmitted PMKID:"
0x18002cf03  shl     rdx, 4
0x18002cf07  mov     r8d, 10h; unsigned int
0x18002cf0d  add     rdx, [rbp+4Fh+var_60]; unsigned __int8 *
0x18002cf11  call    ?MSMSecLogBuffer@@YAXPEBGPEAEK@Z; MSMSecLogBuffer(ushort const *,uchar *,ulong)
0x18002cf16  movzx   eax, [rbp+4Fh+var_66]
0x18002cf1a  inc     esi
0x18002cf1c  cmp     esi, eax
0x18002cf1e  jb      short loc_18002CEFA
0x18002cf20  movzx   ecx, [rbp+4Fh+var_78]; unsigned __int16
0x18002cf24  lea     rdx, [rbp+4Fh+var_70]
0x18002cf28  mov     esi, 1
0x18002cf2d  cmp     cx, si
0x18002cf30  cmova   rdx, [rbp+4Fh+var_70]; struct DOT11_AUTH_AKM_SUITE *
0x18002cf35  call    ?IsFtAkmPresent@@YA_NGPEAUDOT11_AUTH_AKM_SUITE@@@Z; IsFtAkmPresent(ushort,DOT11_AUTH_AKM_SUITE *)
0x18002cf3a  test    al, al
0x18002cf3c  jz      short loc_18002CF59
0x18002cf3e  lea     r8, [rbp+4Fh+var_C8]; unsigned int *
0x18002cf42  mov     rcx, r14; struct MSMSEC_PORT_CONTEXT *
0x18002cf45  lea     rdx, [rbp+4Fh+var_B8]; unsigned __int8 **
0x18002cf49  call    ?QueryStationMDDIE@@YAKPEAUMSMSEC_PORT_CONTEXT@@PEAPEAEPEAK@Z; QueryStationMDDIE(MSMSEC_PORT_CONTEXT *,uchar * *,ulong *)
0x18002cf4e  test    eax, eax
0x18002cf50  jnz     short loc_18002CF59
0x18002cf52  cmp     [rbp+4Fh+var_B8], r13
0x18002cf56  cmovnz  edi, esi
0x18002cf59  mov     rcx, [r14+18h]
0x18002cf5d  lea     rdx, aLocking; ">>> Locking >>>"
0x18002cf64  mov     ecx, [rcx+9C0h]; unsigned int
0x18002cf6a  call    ?TraceAdapterId@@YAXKPEBD@Z; TraceAdapterId(ulong,char const *)
0x18002cf6f  mov     rcx, [r14+18h]
0x18002cf73  lea     r8, aSecmgrcandofas; "SecMgrCanDoFastRoam"
0x18002cf7a  mov     r9d, 7Eh ; '~'
0x18002cf80  lea     rdx, [rcx+9D0h]
0x18002cf87  call    cs:__imp_AcquireWriteLock
0x18002cf8e  nop     dword ptr [rax+rax+00h]
0x18002cf93  mov     rcx, [r14+18h]
0x18002cf97  lea     rax, [rbp+4Fh+var_B0]
0x18002cf9b  movzx   r8d, [rbp+4Fh+var_66]; unsigned int
0x18002cfa0  lea     rdx, [r14+12Eh]; unsigned __int8 (*)[6]
0x18002cfa7  mov     r9, [rbp+4Fh+var_60]; unsigned __int8 (*)[16]
0x18002cfab  add     rcx, 0BB8h; struct MSMSEC_PMKCACHE_CONTEXT *
0x18002cfb2  mov     [rsp+120h+var_E8], rax; void **
0x18002cfb7  lea     rax, [rsp+120h+var_D0]
0x18002cfbc  mov     [rsp+120h+var_F0], rax; unsigned int *
0x18002cfc1  lea     rax, [rbp+4Fh+var_A8]
0x18002cfc5  mov     [rsp+120h+var_F8], rax; struct MSMSEC_RAW_DATA *
0x18002cfca  mov     [rsp+120h+var_100], edi; int
0x18002cfce  call    ?PmkCacheCheckFastRoam@@YAKPEAUMSMSEC_PMKCACHE_CONTEXT@@PEAY05EKPEAY0BA@EHPEAUMSMSEC_RAW_DATA@@PEAKPEAPEAX@Z; PmkCacheCheckFastRoam(MSMSEC_PMKCACHE_CONTEXT *,uchar (*)[6],ulong,uchar (*)[16],int,MSMSEC_RAW_DATA *,ulong *,void * *)
0x18002cfd3  mov     r15, [rbp+4Fh+var_B0]
0x18002cfd7  mov     esi, eax
0x18002cfd9  test    eax, eax
0x18002cfdb  jnz     loc_18002D064
0x18002cfe1  mov     edi, [rsp+120h+var_D0]
0x18002cfe5  test    edi, edi
0x18002cfe7  jz      short loc_18002D064
0x18002cfe9  test    r15, r15
0x18002cfec  jz      short loc_18002D064
0x18002cfee  lea     rcx, [rbp+4Fh+var_A8]
0x18002cff2  call    RawDataIsNonEmpty
0x18002cff7  test    eax, eax
0x18002cff9  jz      short loc_18002D064
0x18002cffb  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d002  lea     rax, WPP_GLOBAL_Control
0x18002d009  cmp     rcx, rax
0x18002d00c  jz      short loc_18002D026
0x18002d00e  test    [rcx+44h], bl
0x18002d011  jz      short loc_18002D026
0x18002d013  mov     rcx, [rcx+38h]
0x18002d017  lea     edx, [rsi+12h]
0x18002d01a  lea     r8, WPP_6b4468b8a73334dd0914b2db0c523d9b_Traceguids
0x18002d021  call    WPP_SF_
0x18002d026  mov     rcx, [rbp+4Fh+arg_10]
0x18002d02a  mov     rax, [rbp+4Fh+arg_18]
0x18002d02e  mov     dword ptr [r12], 1
0x18002d036  mov     r12d, 1
0x18002d03c  mov     r13d, r12d
0x18002d03f  mov     [rax], edi
0x18002d041  mov     edi, r12d
0x18002d044  mov     rax, [rbp+4Fh+arg_20]
0x18002d048  mov     [rax], r15
0x18002d04b  mov     rax, qword ptr [rbp+4Fh+var_A8+8]
0x18002d04f  mov     [rcx+8], rax
0x18002d053  mov     eax, dword ptr [rbp+4Fh+var_A8]
0x18002d056  mov     [rcx], eax
0x18002d058  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d05f  jmp     loc_18002CC98
  ... truncated ...
```
