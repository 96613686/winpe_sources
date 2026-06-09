# SrConvertSppGroupToSrRpProp(_SR_RESTORE_SOURCE,_SPP_GROUP_PROP const *,_SR_RP_PROP *)

- ea: `0x14000d688`
- end: `0x14000de50`
- name: `?SrConvertSppGroupToSrRpProp@@YAJW4_SR_RESTORE_SOURCE@@PEBU_SPP_GROUP_PROP@@PEAU_SR_RP_PROP@@@Z`
- size: `1992`
- prototype: `__int64 __fastcall(__int64, __int64, _OWORD *)`
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, service_task`

## callers

- `0x1400047e4`

## callees

- `0x1400011d4`
- `0x1400011e0`
- `0x140002e1c`
- `0x140006c40`
- `0x14000d168`
- `0x14000d1a4`
- `0x14000d2a4`
- `0x14000d350`
- `0x14000d3b4`
- `0x14000d414`
- `0x14000d478`
- `0x14000d56c`
- `0x14000d688`
- `0x14000e324`
- `0x14000e41c`
- `0x14001094e`
- `0x140010980`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x14000dc7d`
- `ole32!CoTaskMemFree` at `0x14000ddaa`
- `ole32!CoTaskMemFree` at `0x14000dc7d`
- `ole32!CoTaskMemFree` at `0x14000ddaa`
- `ole32!CoTaskMemRealloc` at `0x14000dc58`
- `ole32!CoTaskMemRealloc` at `0x14000dc58`

## pseudocode

```c
__int64 __fastcall SrConvertSppGroupToSrRpProp(__int64 a1, __int64 a2, _OWORD *a3)
{
  unsigned int v5; // r13d
  __int64 v6; // rbx
  __int64 v7; // rsi
  __int64 v8; // rdi
  __int64 v9; // rcx
  _BYTE *v10; // rax
  __int16 v11; // ax
  _QWORD *v12; // rax
  _QWORD *v13; // rax
  _QWORD *v14; // rax
  __int64 v15; // xmm0_8
  const unsigned __int16 *v16; // rcx
  __int128 v17; // xmm0
  const unsigned __int16 *v18; // rcx
  const unsigned __int16 *v19; // rcx
  const unsigned __int16 *v20; // rcx
  __int64 v21; // rax
  __int64 v22; // r12
  __int64 v23; // r15
  unsigned __int16 *v24; // xmm0_8
  const unsigned __int16 *v25; // rcx
  int v26; // eax
  __int64 v27; // rcx
  unsigned int v28; // r15d
  int v29; // eax
  __int64 v30; // rcx
  int v31; // eax
  __int64 v32; // r12
  unsigned int v33; // ecx
  __int64 v34; // r15
  __int64 v35; // rax
  int v36; // ecx
  unsigned int v37; // eax
  __int64 v38; // r15
  __int64 v39; // rcx
  unsigned int v40; // eax
  unsigned int v41; // r13d
  int v42; // r12d
  unsigned int v43; // r15d
  int v44; // eax
  LPVOID v45; // rax
  __int64 v46; // rcx
  __int128 v47; // xmm0
  __int64 v48; // rax
  int v49; // eax
  __int64 v50; // rcx
  __int128 v51; // xmm0
  __int128 v52; // xmm1
  _OWORD *v53; // rax
  __int128 v54; // xmm0
  __int128 v55; // xmm1
  __int128 v56; // xmm0
  __int128 v57; // xmm1
  __int128 v58; // xmm0
  __int128 v59; // xmm1
  __int128 v60; // xmm0
  __int64 v61; // rdx
  __int64 v62; // r8
  unsigned int v63; // r14d
  int v65; // [rsp+20h] [rbp-E0h]
  unsigned int i; // [rsp+20h] [rbp-E0h]
  int v67; // [rsp+28h] [rbp-D8h] BYREF
  __int16 v68; // [rsp+2Ch] [rbp-D4h]
  __int16 v69; // [rsp+2Eh] [rbp-D2h]
  LPVOID pv; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 *v71[2]; // [rsp+68h] [rbp-98h] BYREF
  _OWORD *v72; // [rsp+78h] [rbp-88h]
  int v73; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int16 *v74[2]; // [rsp+8Ch] [rbp-74h] BYREF
  unsigned __int16 *v75[4]; // [rsp+9Ch] [rbp-64h] BYREF
  __int128 v76; // [rsp+C0h] [rbp-40h] BYREF
  __int128 v77; // [rsp+D0h] [rbp-30h]
  unsigned __int16 *v78[2]; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v79; // [rsp+F0h] [rbp-10h]
  unsigned __int16 *v80[2]; // [rsp+100h] [rbp+0h] BYREF
  unsigned __int16 *v81[2]; // [rsp+110h] [rbp+10h] BYREF
  __int128 v82; // [rsp+120h] [rbp+20h]
  __int128 v83; // [rsp+130h] [rbp+30h]
  __int128 v84; // [rsp+140h] [rbp+40h]
  __int64 v85; // [rsp+150h] [rbp+50h]

  v72 = a3;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_356ece2e4ded3d022f22f9fb8e9950d0_Traceguids);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v67, "SrConvertSppGroupToSrRpProp", 46, 1);
  v5 = 0;
  memset(v75, 0, 28);
  v73 = 0;
  LODWORD(v76) = 0;
  *(_OWORD *)v74 = 0;
  memset_0((char *)&v76 + 4, 0, 0x94u);
  pv = 0;
  v6 = 0;
  v7 = 0;
  v8 = 0;
  *(_OWORD *)v71 = 0;
  if ( a3 )
  {
    v9 = 152;
    v10 = a3;
    do
    {
      *v10++ = 0;
      --v9;
    }
    while ( v9 );
  }
  v11 = 63;
  if ( !a2 || (v68 = 63, v11 = 64, !a3) )
  {
    v67 = -2147024809;
LABEL_69:
    v69 = v11;
    goto LABEL_70;
  }
  v67 = 0;
  v68 = 64;
  v12 = operator new(0x18u);
  v6 = (__int64)v12;
  if ( !v12 )
  {
    v6 = 0;
    v11 = 66;
    goto LABEL_68;
  }
  *(_DWORD *)v12 = 1;
  v12[1] = 0;
  v12[2] = 0;
  v67 = 0;
  v68 = 66;
  v13 = operator new(0x18u);
  v7 = (__int64)v13;
  if ( !v13 )
  {
    v7 = 0;
    v11 = 67;
    goto LABEL_68;
  }
  *(_DWORD *)v13 = 1;
  v13[1] = 0;
  v13[2] = 0;
  v67 = 0;
  v68 = 67;
  v14 = operator new(0x18u);
  v8 = (__int64)v14;
  if ( !v14 )
  {
    v8 = 0;
    v11 = 68;
LABEL_68:
    v67 = -2147024882;
    goto LABEL_69;
  }
  *(_DWORD *)v14 = 1;
  v14[1] = 0;
  v14[2] = 0;
  v15 = *(_QWORD *)(a2 + 4);
  v16 = *(const unsigned __int16 **)(a2 + 32);
  v68 = 68;
  LODWORD(v76) = *(_DWORD *)a2;
  HIDWORD(v76) = *(_DWORD *)(a2 + 12);
  *(_QWORD *)&v77 = *(_QWORD *)(a2 + 16);
  DWORD2(v77) = *(_DWORD *)(a2 + 24);
  LODWORD(v78[0]) = *(_DWORD *)(a2 + 28);
  v67 = 0;
  *(_QWORD *)((char *)&v76 + 4) = v15;
  HIDWORD(v77) = 1;
  v67 = SxCopyString(v16, &v78[1]);
  v11 = 75;
  if ( v67 < 0 )
    goto LABEL_69;
  v17 = *(_OWORD *)(a2 + 40);
  v18 = *(const unsigned __int16 **)(a2 + 56);
  v68 = 75;
  v79 = v17;
  v67 = SxCopyString(v18, v80);
  v11 = 77;
  if ( v67 < 0 )
    goto LABEL_69;
  v19 = *(const unsigned __int16 **)(a2 + 64);
  v68 = 77;
  v67 = SxCopyString(v19, &v80[1]);
  v11 = 78;
  if ( v67 < 0 )
    goto LABEL_69;
  v20 = *(const unsigned __int16 **)(a2 + 72);
  v68 = 78;
  v67 = SxCopyString(v20, v81);
  v11 = 79;
  if ( v67 < 0 )
    goto LABEL_69;
  v68 = 79;
  v21 = 0;
  v65 = 0;
  while ( (unsigned int)v21 < *(_DWORD *)(a2 + 80) )
  {
    v22 = *(_QWORD *)(a2 + 88);
    v23 = 56 * v21;
    v24 = *(unsigned __int16 **)(56 * v21 + v22 + 4);
    v25 = *(const unsigned __int16 **)(56 * v21 + v22 + 16);
    v73 = *(_DWORD *)(56 * v21 + v22);
    LODWORD(v74[1]) = *(_DWORD *)(56 * v21 + v22 + 12);
    v74[0] = v24;
    v67 = SxCopyString(v25, (unsigned __int16 **)((char *)&v74[1] + 4));
    v11 = 86;
    if ( v67 < 0 )
      goto LABEL_69;
    v68 = 86;
    v67 = SxCopyString(*(const unsigned __int16 **)(v23 + v22 + 24), (unsigned __int16 **)((char *)v75 + 4));
    v11 = 87;
    if ( v67 < 0 )
      goto LABEL_69;
    v68 = 87;
    if ( *(_DWORD *)(v23 + v22 + 32) )
    {
      do
      {
        v67 = SxCopyString(
                *(const unsigned __int16 **)(*(_QWORD *)(v23 + v22 + 40) + 8LL * v5),
                (unsigned __int16 **)&pv);
        v11 = 91;
        if ( v67 < 0 )
          goto LABEL_69;
        v68 = 91;
        v67 = CSxArrayBuilder<unsigned short *,&void Free_String(unsigned short * *),&void SxDefaultInit<unsigned short *>(unsigned short * *),&void SxDefaultTransfer<unsigned short *>(unsigned short * *,unsigned short * *)>::Append(
                v6,
                &pv);
        v11 = 92;
        if ( v67 < 0 )
          goto LABEL_69;
        ++v5;
        v68 = 92;
      }
      while ( v5 < *(_DWORD *)(v23 + v22 + 32) );
    }
    v26 = *(_DWORD *)(v6 + 16);
    v5 = 0;
    *(unsigned __int16 **)((char *)&v75[2] + 4) = *(unsigned __int16 **)(v6 + 8);
    *(_QWORD *)(v6 + 8) = 0;
    *(_QWORD *)(v6 + 16) = 0;
    HIDWORD(v75[1]) = v26;
    v67 = CSxArrayBuilder<_SR_VOLUME_PROP,&void Free_SR_VOLUME_PROP(_SR_VOLUME_PROP *),&void SxDefaultInit<_SR_VOLUME_PROP>(_SR_VOLUME_PROP *),&void SxDefaultTransfer<_SR_VOLUME_PROP>(_SR_VOLUME_PROP *,_SR_VOLUME_PROP *)>::Append(
            v7,
            &v73);
    v11 = 96;
    if ( v67 < 0 )
      goto LABEL_69;
    v68 = 96;
    v21 = (unsigned int)(v65 + 1);
    v65 = v21;
  }
  v27 = *(_QWORD *)(v7 + 8);
  v28 = 0;
  v29 = *(_DWORD *)(v7 + 16);
  *(_QWORD *)(v7 + 8) = 0;
  *(_QWORD *)(v7 + 16) = 0;
  *(_QWORD *)&v82 = v27;
  for ( LODWORD(v81[1]) = v29; v28 < *(_DWORD *)(a2 + 112); v68 = 104 )
  {
    v67 = SxCopyString(*(const unsigned __int16 **)(*(_QWORD *)(a2 + 120) + 8LL * v28), (unsigned __int16 **)&pv);
    v11 = 103;
    if ( v67 < 0 )
      goto LABEL_69;
    v68 = 103;
    v67 = CSxArrayBuilder<unsigned short *,&void Free_String(unsigned short * *),&void SxDefaultInit<unsigned short *>(unsigned short * *),&void SxDefaultTransfer<unsigned short *>(unsigned short * *,unsigned short * *)>::Append(
            v6,
            &pv);
    v11 = 104;
    if ( v67 < 0 )
      goto LABEL_69;
    ++v28;
  }
  v30 = *(_QWORD *)(v6 + 8);
  v31 = *(_DWORD *)(v6 + 16);
  *(_QWORD *)(v6 + 8) = 0;
  *(_QWORD *)(v6 + 16) = 0;
  *(_QWORD *)&v83 = v30;
  DWORD2(v82) = v31;
  if ( *(_DWORD *)(a2 + 96) )
  {
    v32 = *(_QWORD *)(a2 + 104);
    v33 = 0;
    while ( 1 )
    {
      v34 = 6LL * v33;
      if ( *(_QWORD *)(v32 + 48LL * v33) == 0x4180294E09F7EDC5LL
        && *(_QWORD *)(v32 + 48LL * v33 + 8) == 0x13950E6A0EFB6AAFLL )
      {
        break;
      }
      if ( ++v33 >= *(_DWORD *)(a2 + 96) )
        goto LABEL_41;
    }
    if ( *(_DWORD *)(v32 + 48LL * v33 + 24) )
    {
      do
      {
        v67 = SxCopyString(
                *(const unsigned __int16 **)(*(_QWORD *)(v32 + 8 * v34 + 32) + 8LL * v5),
                (unsigned __int16 **)&pv);
        v11 = 118;
        if ( v67 < 0 )
          goto LABEL_69;
        v68 = 118;
        v67 = CSxArrayBuilder<unsigned short *,&void Free_String(unsigned short * *),&void SxDefaultInit<unsigned short *>(unsigned short * *),&void SxDefaultTransfer<unsigned short *>(unsigned short * *,unsigned short * *)>::Append(
                v6,
                &pv);
        v11 = 119;
        if ( v67 < 0 )
          goto LABEL_69;
        ++v5;
        v68 = 119;
      }
      while ( v5 < *(_DWORD *)(v32 + 8 * v34 + 24) );
    }
    v35 = *(_QWORD *)(v6 + 8);
    v36 = *(_DWORD *)(v6 + 16);
    *(_QWORD *)(v6 + 8) = 0;
    *(_QWORD *)(v6 + 16) = 0;
    *(_QWORD *)&v84 = v35;
    DWORD2(v83) = v36;
  }
LABEL_41:
  v37 = 0;
  for ( i = 0; v37 < *(_DWORD *)(a2 + 128); i = v37 )
  {
    v38 = 2LL * v37;
    v67 = SxCopyString(*(const unsigned __int16 **)(*(_QWORD *)(a2 + 136) + 16LL * v37), v71);
    v11 = 129;
    if ( v67 < 0 )
      goto LABEL_69;
    v39 = *(_QWORD *)(a2 + 136);
    v68 = 129;
    v67 = SxCopyString(*(const unsigned __int16 **)(v39 + 8 * v38 + 8), &v71[1]);
    if ( v67 < 0 )
    {
      v69 = 130;
      goto LABEL_70;
    }
    v68 = 130;
    v40 = *(_DWORD *)(v8 + 16);
    v41 = v40 + 1;
    if ( v40 + 1 >= v40 )
    {
      v42 = 0;
      if ( v41 > *(_DWORD *)(v8 + 20) )
      {
        if ( v41 > 0x40 )
        {
          v44 = 256;
          if ( v41 > 0x100 && (v44 = 1024, v41 > 0x400) && (v44 = 4096, v41 > 0x1000) && (v44 = 0x4000, v41 > 0x4000) )
          {
            v43 = (v41 + 0xFFFF) & 0xFFFF0000;
            if ( v43 < v41 )
              v43 = v41;
          }
          else
          {
            v43 = v44;
          }
        }
        else
        {
          v43 = 64;
        }
        if ( is_mul_ok(v43, 0x10u) )
        {
          v45 = CoTaskMemRealloc(*(LPVOID *)(v8 + 8), 16LL * v43);
          if ( v45 )
          {
            *(_QWORD *)(v8 + 8) = v45;
            *(_DWORD *)(v8 + 20) = v43;
          }
          else
          {
            v42 = -2147024882;
          }
        }
        else
        {
          v42 = -2147024362;
        }
      }
      CoTaskMemFree(0);
      if ( v42 >= 0 )
      {
        v46 = *(unsigned int *)(v8 + 16);
        v47 = *(_OWORD *)v71;
        v48 = *(_QWORD *)(v8 + 8);
        *(_OWORD *)v71 = 0;
        *(_OWORD *)(v48 + 16 * v46) = v47;
        *(_DWORD *)(v8 + 16) = v41;
      }
    }
    Free_SR_ENVIRONMENT_PROP((LPVOID *)v71);
    v37 = i + 1;
  }
  v49 = *(_DWORD *)(v8 + 16);
  v50 = *(_QWORD *)(v8 + 8);
  v51 = v76;
  v52 = v77;
  *(_QWORD *)(v8 + 8) = 0;
  *(_QWORD *)(v8 + 16) = 0;
  DWORD2(v84) = v49;
  v53 = v72;
  v85 = v50;
  *v72 = v51;
  v54 = *(_OWORD *)v78;
  v53[1] = v52;
  v55 = v79;
  v53[2] = v54;
  v56 = *(_OWORD *)v80;
  v53[3] = v55;
  v57 = *(_OWORD *)v81;
  v53[4] = v56;
  v58 = v82;
  v53[5] = v57;
  v59 = v83;
  v53[6] = v58;
  v60 = v84;
  v53[7] = v59;
  v53[8] = v60;
  *((_QWORD *)v53 + 18) = v50;
  memset_0(&v76, 0, 0x98u);
LABEL_70:
  Free_SR_RP_PROP((struct _SR_RP_PROP *)&v76);
  Free_SR_VOLUME_PROP((struct _SR_VOLUME_PROP *)&v73);
  Free_SR_ENVIRONMENT_PROP((LPVOID *)v71);
  CoTaskMemFree(pv);
  v63 = v67;
  if ( v8 && _InterlockedExchangeAdd((volatile signed __int32 *)v8, 0xFFFFFFFF) == 1 )
  {
    CSxArrayBuilder<_SR_ENVIRONMENT_PROP,&void Free_SR_ENVIRONMENT_PROP(_SR_ENVIRONMENT_PROP *),&void SxDefaultInit<_SR_ENVIRONMENT_PROP>(_SR_ENVIRONMENT_PROP *),&void SxDefaultTransfer<_SR_ENVIRONMENT_PROP>(_SR_ENVIRONMENT_PROP *,_SR_ENVIRONMENT_PROP *)>::~CSxArrayBuilder<_SR_ENVIRONMENT_PROP,&void Free_SR_ENVIRONMENT_PROP(_SR_ENVIRONMENT_PROP *),&void SxDefaultInit<_SR_ENVIRONMENT_PROP>(_SR_ENVIRONMENT_PROP *),&void SxDefaultTransfer<_SR_ENVIRONMENT_PROP>(_SR_ENVIRONMENT_PROP *,_SR_ENVIRONMENT_PROP *)>(v8);
    operator delete((void *)v8);
  }
  if ( v7 && _InterlockedExchangeAdd((volatile signed __int32 *)v7, 0xFFFFFFFF) == 1 )
  {
    CSxArrayBuilder<_SR_VOLUME_PROP,&void Free_SR_VOLUME_PROP(_SR_VOLUME_PROP *),&void SxDefaultInit<_SR_VOLUME_PROP>(_SR_VOLUME_PROP *),&void SxDefaultTransfer<_SR_VOLUME_PROP>(_SR_VOLUME_PROP *,_SR_VOLUME_PROP *)>::~CSxArrayBuilder<_SR_VOLUME_PROP,&void Free_SR_VOLUME_PROP(_SR_VOLUME_PROP *),&void SxDefaultInit<_SR_VOLUME_PROP>(_SR_VOLUME_PROP *),&void SxDefaultTransfer<_SR_VOLUME_PROP>(_SR_VOLUME_PROP *,_SR_VOLUME_PROP *)>(v7);
    operator delete((void *)v7);
  }
  if ( v6 && _InterlockedExchangeAdd((volatile signed __int32 *)v6, 0xFFFFFFFF) == 1 )
  {
    CSxArrayBuilder<unsigned short *,&void Free_String(unsigned short * *),&void SxDefaultInit<unsigned short *>(unsigned short * *),&void SxDefaultTransfer<unsigned short *>(unsigned short * *,unsigned short * *)>::~CSxArrayBuilder<unsigned short *,&void Free_String(unsigned short * *),&void SxDefaultInit<unsigned short *>(unsigned short * *),&void SxDefaultTransfer<unsigned short *>(unsigned short * *,unsigned short * *)>(v6);
    operator delete((void *)v6);
  }
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v67, v61, v62);
  return v63;
}

```

## disassembly

```asm
0x14000d688  mov     [rsp-8+arg_0], rbx
0x14000d68d  push    rbp
0x14000d68e  push    rsi
0x14000d68f  push    rdi
0x14000d690  push    r12
0x14000d692  push    r13
0x14000d694  push    r14
0x14000d696  push    r15
0x14000d698  lea     rbp, [rsp-70h]
0x14000d69d  sub     rsp, 170h
0x14000d6a4  mov     rax, cs:__security_cookie
0x14000d6ab  xor     rax, rsp
0x14000d6ae  mov     [rbp+0A0h+var_40], rax
0x14000d6b2  mov     r15, r8
0x14000d6b5  mov     [rsp+1A0h+var_128], r8
0x14000d6ba  mov     r14, rdx
0x14000d6bd  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d6c4  lea     rax, WPP_GLOBAL_Control
0x14000d6cb  cmp     rcx, rax
0x14000d6ce  jz      short loc_14000D6EE
0x14000d6d0  test    dword ptr [rcx+1Ch], 20000000h
0x14000d6d7  jz      short loc_14000D6EE
0x14000d6d9  mov     rcx, [rcx+10h]
0x14000d6dd  lea     r8, WPP_356ece2e4ded3d022f22f9fb8e9950d0_Traceguids
0x14000d6e4  mov     edx, 0Ah
0x14000d6e9  call    WPP_SF_
0x14000d6ee  mov     r12d, 1
0x14000d6f4  lea     rdx, aSrconvertsppgr; "SrConvertSppGroupToSrRpProp"
0x14000d6fb  mov     r9d, r12d; unsigned __int16
0x14000d6fe  lea     rcx, [rsp+1A0h+var_178]; this
0x14000d703  lea     r8d, [r12+2Dh]; unsigned __int16
0x14000d708  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x14000d70d  xorps   xmm0, xmm0
0x14000d710  lea     rcx, [rbp+0A0h+var_E0+4]; void *
0x14000d714  xor     r13d, r13d
0x14000d717  xor     edx, edx; Val
0x14000d719  movups  xmmword ptr [rbp+0A0h+var_104], xmm0
0x14000d71d  mov     r8d, 94h; Size
0x14000d723  mov     [rbp+0A0h+var_118], r13d
0x14000d727  movups  xmmword ptr [rbp+0A0h+var_104+0Ch], xmm0
0x14000d72b  mov     dword ptr [rbp+0A0h+var_E0], r13d
0x14000d72f  movups  xmmword ptr [rbp+0A0h+var_114], xmm0
0x14000d733  call    memset_0
0x14000d738  mov     [rsp+1A0h+pv], r13
0x14000d73d  xorps   xmm0, xmm0
0x14000d740  mov     ebx, r13d
0x14000d743  mov     esi, r13d
0x14000d746  mov     edi, r13d
0x14000d749  movups  xmmword ptr [rsp+1A0h+var_138], xmm0
0x14000d74e  test    r15, r15
0x14000d751  jz      short loc_14000D766
0x14000d753  mov     ecx, 98h
0x14000d758  mov     rax, r15
0x14000d75b  mov     [rax], r13b
0x14000d75e  add     rax, r12
0x14000d761  sub     rcx, r12
0x14000d764  jnz     short loc_14000D75B
0x14000d766  mov     eax, 3Fh ; '?'
0x14000d76b  test    r14, r14
0x14000d76e  jnz     short loc_14000D77D
0x14000d770  mov     [rsp+1A0h+var_178], 80070057h
0x14000d778  jmp     loc_14000DD84
0x14000d77d  mov     [rsp+1A0h+var_174], ax
0x14000d782  mov     eax, 40h ; '@'
0x14000d787  test    r15, r15
0x14000d78a  jz      short loc_14000D770
0x14000d78c  lea     r15d, [rax-28h]
0x14000d790  mov     [rsp+1A0h+var_178], r13d
0x14000d795  mov     ecx, r15d; Size
0x14000d798  mov     [rsp+1A0h+var_174], ax
0x14000d79d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000d7a2  mov     rbx, rax
0x14000d7a5  test    rax, rax
0x14000d7a8  jz      loc_14000DD74
0x14000d7ae  mov     [rax], r12d
0x14000d7b1  mov     [rax+8], r13
0x14000d7b5  mov     [rax+10h], r13
0x14000d7b9  lea     eax, [r15+2Ah]
0x14000d7bd  mov     [rsp+1A0h+var_178], r13d
0x14000d7c2  mov     ecx, r15d; Size
0x14000d7c5  mov     [rsp+1A0h+var_174], ax
0x14000d7ca  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000d7cf  mov     rsi, rax
0x14000d7d2  test    rax, rax
0x14000d7d5  jz      loc_14000DD6A
0x14000d7db  mov     [rax], r12d
0x14000d7de  mov     [rax+8], r13
0x14000d7e2  mov     [rax+10h], r13
0x14000d7e6  lea     eax, [r15+2Bh]
0x14000d7ea  mov     [rsp+1A0h+var_178], r13d
0x14000d7ef  mov     ecx, r15d; Size
0x14000d7f2  mov     [rsp+1A0h+var_174], ax
0x14000d7f7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000d7fc  mov     rdi, rax
0x14000d7ff  test    rax, rax
0x14000d802  jz      loc_14000DD60
0x14000d808  mov     [rax], r12d
0x14000d80b  mov     [rax+8], r13
0x14000d80f  mov     [rax+10h], r13
0x14000d813  movsd   xmm0, qword ptr [r14+4]
0x14000d819  lea     eax, [r15+2Ch]
0x14000d81d  mov     rcx, [r14+20h]; Src
0x14000d821  lea     rdx, [rbp+0A0h+var_C0+8]; unsigned __int16 **
0x14000d825  mov     [rsp+1A0h+var_174], ax
0x14000d82a  mov     eax, [r14]
0x14000d82d  mov     dword ptr [rbp+0A0h+var_E0], eax
0x14000d830  mov     eax, [r14+0Ch]
0x14000d834  mov     dword ptr [rbp+0A0h+var_E0+0Ch], eax
0x14000d837  mov     rax, [r14+10h]
0x14000d83b  mov     qword ptr [rbp+0A0h+var_D0], rax
0x14000d83f  mov     eax, [r14+18h]
0x14000d843  mov     dword ptr [rbp+0A0h+var_D0+8], eax
0x14000d846  mov     eax, [r14+1Ch]
0x14000d84a  mov     dword ptr [rbp+0A0h+var_C0], eax
0x14000d84d  mov     [rsp+1A0h+var_178], r13d
0x14000d852  movsd   qword ptr [rbp+0A0h+var_E0+4], xmm0
0x14000d857  mov     dword ptr [rbp+0A0h+var_D0+0Ch], r12d
0x14000d85b  call    ?SxCopyString@@YAJPEBGPEAPEAG@Z; SxCopyString(ushort const *,ushort * *)
0x14000d860  mov     [rsp+1A0h+var_178], eax
0x14000d864  test    eax, eax
0x14000d866  lea     eax, [r15+33h]
0x14000d86a  js      loc_14000DD84
0x14000d870  movups  xmm0, xmmword ptr [r14+28h]
0x14000d875  mov     rcx, [r14+38h]; Src
0x14000d879  lea     rdx, [rbp+0A0h+var_A0]; unsigned __int16 **
0x14000d87d  mov     [rsp+1A0h+var_174], ax
0x14000d882  movdqu  [rbp+0A0h+var_B0], xmm0
0x14000d887  call    ?SxCopyString@@YAJPEBGPEAPEAG@Z; SxCopyString(ushort const *,ushort * *)
0x14000d88c  mov     [rsp+1A0h+var_178], eax
0x14000d890  test    eax, eax
0x14000d892  lea     eax, [r15+35h]
0x14000d896  js      loc_14000DD84
0x14000d89c  mov     rcx, [r14+40h]; Src
0x14000d8a0  lea     rdx, [rbp+0A0h+var_A0+8]; unsigned __int16 **
0x14000d8a4  mov     [rsp+1A0h+var_174], ax
0x14000d8a9  call    ?SxCopyString@@YAJPEBGPEAPEAG@Z; SxCopyString(ushort const *,ushort * *)
0x14000d8ae  mov     [rsp+1A0h+var_178], eax
0x14000d8b2  test    eax, eax
0x14000d8b4  lea     eax, [r15+36h]
0x14000d8b8  js      loc_14000DD84
0x14000d8be  mov     rcx, [r14+48h]; Src
0x14000d8c2  lea     rdx, [rbp+0A0h+var_90]; unsigned __int16 **
0x14000d8c6  mov     [rsp+1A0h+var_174], ax
0x14000d8cb  call    ?SxCopyString@@YAJPEBGPEAPEAG@Z; SxCopyString(ushort const *,ushort * *)
0x14000d8d0  mov     [rsp+1A0h+var_178], eax
0x14000d8d4  test    eax, eax
0x14000d8d6  lea     eax, [r15+37h]
0x14000d8da  js      loc_14000DD84
0x14000d8e0  mov     [rsp+1A0h+var_174], ax
0x14000d8e5  mov     eax, r13d
0x14000d8e8  mov     [rsp+1A0h+var_180], eax
0x14000d8ec  cmp     [r14+50h], r13d
0x14000d8f0  jbe     loc_14000DA15
0x14000d8f6  mov     r12, [r14+58h]
0x14000d8fa  lea     rdx, [rbp+0A0h+var_114+0Ch]; unsigned __int16 **
0x14000d8fe  imul    r15, rax, 38h ; '8'
0x14000d902  mov     eax, [r15+r12]
0x14000d906  movsd   xmm0, qword ptr [r15+r12+4]
0x14000d90d  mov     rcx, [r15+r12+10h]; Src
0x14000d912  mov     [rbp+0A0h+var_118], eax
0x14000d915  mov     eax, [r15+r12+0Ch]
0x14000d91a  mov     dword ptr [rbp+0A0h+var_114+8], eax
0x14000d91d  movsd   [rbp+0A0h+var_114], xmm0
0x14000d922  call    ?SxCopyString@@YAJPEBGPEAPEAG@Z; SxCopyString(ushort const *,ushort * *)
0x14000d927  mov     [rsp+1A0h+var_178], eax
0x14000d92b  test    eax, eax
0x14000d92d  mov     eax, 56h ; 'V'
0x14000d932  js      loc_14000DD84
0x14000d938  mov     [rsp+1A0h+var_174], ax
0x14000d93d  lea     rdx, [rbp+0A0h+var_104+4]; unsigned __int16 **
0x14000d941  mov     rcx, [r15+r12+18h]; Src
0x14000d946  call    ?SxCopyString@@YAJPEBGPEAPEAG@Z; SxCopyString(ushort const *,ushort * *)
0x14000d94b  mov     [rsp+1A0h+var_178], eax
0x14000d94f  test    eax, eax
0x14000d951  mov     eax, 57h ; 'W'
0x14000d956  js      loc_14000DD84
0x14000d95c  mov     [rsp+1A0h+var_174], ax
0x14000d961  cmp     dword ptr [r15+r12+20h], 0
0x14000d967  jbe     short loc_14000D9C2
0x14000d969  mov     rcx, [r15+r12+28h]
0x14000d96e  lea     rdx, [rsp+1A0h+pv]; unsigned __int16 **
0x14000d973  mov     eax, r13d
0x14000d976  mov     rcx, [rcx+rax*8]; Src
0x14000d97a  call    ?SxCopyString@@YAJPEBGPEAPEAG@Z; SxCopyString(ushort const *,ushort * *)
0x14000d97f  mov     [rsp+1A0h+var_178], eax
0x14000d983  test    eax, eax
0x14000d985  mov     eax, 5Bh ; '['
0x14000d98a  js      loc_14000DD84
0x14000d990  lea     rdx, [rsp+1A0h+pv]
0x14000d995  mov     [rsp+1A0h+var_174], ax
0x14000d99a  mov     rcx, rbx
0x14000d99d  call    ?Append@?$CSxArrayBuilder@PEAG$1?Free_String@@YAXPEAPEAG@Z$1??$SxDefaultInit@PEAG@@YAX0@Z$1??$SxDefaultTransfer@PEAG@@YAX00@Z@@QEAAJPEAPEAG@Z; CSxArrayBuilder<ushort *,&Free_String(ushort * *),&SxDefaultInit<ushort *>(ushort * *),&SxDefaultTransfer<ushort *>(ushort * *,ushort * *)>::Append(ushort * *)
0x14000d9a2  mov     [rsp+1A0h+var_178], eax
0x14000d9a6  test    eax, eax
0x14000d9a8  mov     eax, 5Ch ; '\'
0x14000d9ad  js      loc_14000DD84
0x14000d9b3  inc     r13d
0x14000d9b6  mov     [rsp+1A0h+var_174], ax
0x14000d9bb  cmp     r13d, [r15+r12+20h]
0x14000d9c0  jb      short loc_14000D969
0x14000d9c2  mov     rcx, [rbx+8]
0x14000d9c6  lea     rdx, [rbp+0A0h+var_118]
0x14000d9ca  mov     eax, [rbx+10h]
0x14000d9cd  xor     r13d, r13d
0x14000d9d0  mov     [rbp+0A0h+var_F0], rcx
0x14000d9d4  mov     rcx, rsi
0x14000d9d7  mov     [rbx+8], r13
0x14000d9db  mov     [rbx+10h], r13
0x14000d9df  mov     dword ptr [rbp+0A0h+var_104+0Ch], eax
0x14000d9e2  call    ?Append@?$CSxArrayBuilder@U_SR_VOLUME_PROP@@$1?Free_SR_VOLUME_PROP@@YAXPEAU1@@Z$1??$SxDefaultInit@U_SR_VOLUME_PROP@@@@YAX0@Z$1??$SxDefaultTransfer@U_SR_VOLUME_PROP@@@@YAX00@Z@@QEAAJPEAU_SR_VOLUME_PROP@@@Z; CSxArrayBuilder<_SR_VOLUME_PROP,&Free_SR_VOLUME_PROP(_SR_VOLUME_PROP *),&SxDefaultInit<_SR_VOLUME_PROP>(_SR_VOLUME_PROP *),&SxDefaultTransfer<_SR_VOLUME_PROP>(_SR_VOLUME_PROP *,_SR_VOLUME_PROP *)>::Append(_SR_VOLUME_PROP *)
0x14000d9e7  mov     [rsp+1A0h+var_178], eax
0x14000d9eb  test    eax, eax
0x14000d9ed  lea     eax, [r13+60h]
0x14000d9f1  js      loc_14000DD84
0x14000d9f7  mov     [rsp+1A0h+var_174], ax
0x14000d9fc  lea     r12d, [r13+1]
0x14000da00  mov     eax, [rsp+1A0h+var_180]
0x14000da04  add     eax, r12d
0x14000da07  mov     [rsp+1A0h+var_180], eax
0x14000da0b  cmp     eax, [r14+50h]
0x14000da0f  jb      loc_14000D8F6
0x14000da15  mov     rcx, [rsi+8]
0x14000da19  mov     r15d, r13d
0x14000da1c  mov     eax, [rsi+10h]
0x14000da1f  mov     [rsi+8], r13
0x14000da23  mov     qword ptr [rsi+10h], 0
0x14000da2b  mov     qword ptr [rbp+0A0h+var_80], rcx
0x14000da2f  mov     dword ptr [rbp+0A0h+var_90+8], eax
0x14000da32  cmp     [r14+70h], r13d
0x14000da36  jbe     short loc_14000DA8F
0x14000da38  mov     rcx, [r14+78h]
0x14000da3c  lea     rdx, [rsp+1A0h+pv]; unsigned __int16 **
0x14000da41  mov     eax, r15d
0x14000da44  mov     rcx, [rcx+rax*8]; Src
0x14000da48  call    ?SxCopyString@@YAJPEBGPEAPEAG@Z; SxCopyString(ushort const *,ushort * *)
0x14000da4d  mov     [rsp+1A0h+var_178], eax
0x14000da51  test    eax, eax
0x14000da53  mov     eax, 67h ; 'g'
0x14000da58  js      loc_14000DD84
0x14000da5e  lea     rdx, [rsp+1A0h+pv]
0x14000da63  mov     [rsp+1A0h+var_174], ax
0x14000da68  mov     rcx, rbx
0x14000da6b  call    ?Append@?$CSxArrayBuilder@PEAG$1?Free_String@@YAXPEAPEAG@Z$1??$SxDefaultInit@PEAG@@YAX0@Z$1??$SxDefaultTransfer@PEAG@@YAX00@Z@@QEAAJPEAPEAG@Z; CSxArrayBuilder<ushort *,&Free_String(ushort * *),&SxDefaultInit<ushort *>(ushort * *),&SxDefaultTransfer<ushort *>(ushort * *,ushort * *)>::Append(ushort * *)
0x14000da70  mov     [rsp+1A0h+var_178], eax
0x14000da74  test    eax, eax
0x14000da76  mov     eax, 68h ; 'h'
0x14000da7b  js      loc_14000DD84
0x14000da81  add     r15d, r12d
0x14000da84  mov     [rsp+1A0h+var_174], ax
0x14000da89  cmp     r15d, [r14+70h]
0x14000da8d  jb      short loc_14000DA38
0x14000da8f  mov     rcx, [rbx+8]
0x14000da93  mov     eax, [rbx+10h]
0x14000da96  mov     [rbx+8], r13
0x14000da9a  mov     qword ptr [rbx+10h], 0
0x14000daa2  mov     qword ptr [rbp+0A0h+var_70], rcx
0x14000daa6  mov     dword ptr [rbp+0A0h+var_80+8], eax
0x14000daa9  cmp     [r14+60h], r13d
0x14000daad  jbe     loc_14000DB62
0x14000dab3  mov     r12, [r14+68h]
0x14000dab7  mov     ecx, r13d
0x14000daba  mov     rdx, cs:qword_140013780
0x14000dac1  mov     r8, cs:qword_140013778
0x14000dac8  mov     eax, ecx
0x14000daca  lea     r15, [rax+rax*2]
0x14000dace  add     r15, r15
0x14000dad1  cmp     [r12+r15*8], r8
0x14000dad5  jnz     short loc_14000DADE
0x14000dad7  cmp     [r12+r15*8+8], rdx
0x14000dadc  jz      short loc_14000DAE8
0x14000dade  inc     ecx
0x14000dae0  cmp     ecx, [r14+60h]
0x14000dae4  jb      short loc_14000DAC8
0x14000dae6  jmp     short loc_14000DB62
0x14000dae8  cmp     dword ptr [r12+r15*8+18h], 0
0x14000daee  jbe     short loc_14000DB49
0x14000daf0  mov     rcx, [r12+r15*8+20h]
0x14000daf5  lea     rdx, [rsp+1A0h+pv]; unsigned __int16 **
0x14000dafa  mov     eax, r13d
0x14000dafd  mov     rcx, [rcx+rax*8]; Src
0x14000db01  call    ?SxCopyString@@YAJPEBGPEAPEAG@Z; SxCopyString(ushort const *,ushort * *)
0x14000db06  mov     [rsp+1A0h+var_178], eax
0x14000db0a  test    eax, eax
0x14000db0c  mov     eax, 76h ; 'v'
0x14000db11  js      loc_14000DD84
0x14000db17  lea     rdx, [rsp+1A0h+pv]
0x14000db1c  mov     [rsp+1A0h+var_174], ax
0x14000db21  mov     rcx, rbx
0x14000db24  call    ?Append@?$CSxArrayBuilder@PEAG$1?Free_String@@YAXPEAPEAG@Z$1??$SxDefaultInit@PEAG@@YAX0@Z$1??$SxDefaultTransfer@PEAG@@YAX00@Z@@QEAAJPEAPEAG@Z; CSxArrayBuilder<ushort *,&Free_String(ushort * *),&SxDefaultInit<ushort *>(ushort * *),&SxDefaultTransfer<ushort *>(ushort * *,ushort * *)>::Append(ushort * *)
0x14000db29  mov     [rsp+1A0h+var_178], eax
0x14000db2d  test    eax, eax
0x14000db2f  mov     eax, 77h ; 'w'
0x14000db34  js      loc_14000DD84
0x14000db3a  inc     r13d
0x14000db3d  mov     [rsp+1A0h+var_174], ax
0x14000db42  cmp     r13d, [r12+r15*8+18h]
0x14000db47  jb      short loc_14000DAF0
0x14000db49  mov     rax, [rbx+8]
0x14000db4d  xor     r13d, r13d
0x14000db50  mov     ecx, [rbx+10h]
  ... truncated ...
```
