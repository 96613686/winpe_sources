# SamLookupIdsInDomain

- ea: `0x18000f5c0`
- end: `0x18000fec4`
- name: `SamLookupIdsInDomain`
- size: `2308`
- prototype: `__int64 __fastcall(void *, unsigned int, unsigned int *, struct _UNICODE_STRING **, enum _SID_NAME_USE **)`
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180003220`
- `0x180006ec2`
- `0x1800078c0`
- `0x18000807c`
- `0x18000ad50`
- `0x18000ba10`
- `0x18000c070`
- `0x18000f5c0`
- `0x180014a50`
- `0x180014a90`
- `0x1800160d8`
- `0x180017935`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f634`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000fcb2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000fd69`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000fd85`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000fda1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000fdbd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000fde3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000fdfd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000fe22`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000fe37`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f634`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000fcb2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000fd69`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000fd85`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000fda1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000fdbd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000fde3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000fdfd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000fe22`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000fe37`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000f7c0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000f7e7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000f80e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000f83d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000f867`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000f88e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000faa6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000fbf4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000f7c0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000f7e7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000f80e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000f83d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000f867`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000f88e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000faa6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000fbf4`

## pseudocode

```c
__int64 __fastcall SamLookupIdsInDomain(
        void **a1,
        unsigned int a2,
        unsigned int *a3,
        struct _UNICODE_STRING **a4,
        enum _SID_NAME_USE **a5)
{
  unsigned int *v6; // rbx
  unsigned int v7; // r12d
  unsigned __int16 *CallingProcessInfo; // rax
  int v10; // ecx
  unsigned __int16 *v11; // rbx
  const wchar_t *v12; // rdx
  __int64 v13; // rcx
  unsigned int v14; // ebx
  unsigned int v16; // eax
  PVOID v17; // rcx
  struct _UNICODE_STRING **v18; // r15
  int v19; // edi
  __int64 v20; // rax
  __int64 v21; // rbp
  size_t v22; // rbx
  _DWORD *v23; // rax
  _DWORD *v24; // rax
  _DWORD *v25; // rax
  struct _UNICODE_STRING **v26; // rax
  enum _SID_NAME_USE **v27; // rax
  _QWORD *v28; // rax
  unsigned int v29; // r13d
  _QWORD *v30; // rcx
  unsigned int v31; // edx
  int v32; // eax
  unsigned int i; // r14d
  unsigned int v34; // edx
  unsigned int v35; // eax
  __int64 v36; // rdx
  __int64 v37; // r9
  unsigned int v38; // ecx
  unsigned int v39; // r8d
  unsigned int v40; // r9d
  __int64 v41; // rax
  unsigned int v42; // ebx
  struct _UNICODE_STRING *v43; // rax
  struct _UNICODE_STRING *v44; // r14
  unsigned int v45; // esi
  struct _UNICODE_STRING *v46; // r13
  _DWORD *v47; // rax
  struct _UNICODE_STRING *v48; // rdx
  unsigned int v49; // ebx
  unsigned int v50; // r14d
  struct _UNICODE_STRING *v51; // r12
  unsigned int v52; // r15d
  struct _UNICODE_STRING **v53; // rax
  struct _UNICODE_STRING *v54; // rcx
  unsigned int MaximumLength; // r9d
  PWSTR Buffer; // rdx
  __int64 v57; // rbx
  enum _SID_NAME_USE *v58; // rax
  enum _SID_NAME_USE *v59; // rsi
  enum _SID_NAME_USE *v60; // r14
  unsigned int v61; // edi
  _DWORD *v62; // rax
  size_t v63; // rbx
  __int64 v64; // r9
  _QWORD *v65; // rcx
  __int64 v66; // rdx
  enum _SID_NAME_USE **v67; // r12
  struct _UNICODE_STRING **v68; // rsi
  void *v69; // rax
  enum _SID_NAME_USE **v70; // r14
  unsigned int v71; // ebx
  struct _UNICODE_STRING *v72; // rcx
  unsigned int j; // ebx
  enum _SID_NAME_USE *v74; // rcx
  unsigned int v75; // [rsp+30h] [rbp-98h]
  _DWORD *v76; // [rsp+38h] [rbp-90h]
  int v77; // [rsp+40h] [rbp-88h]
  unsigned int v78; // [rsp+48h] [rbp-80h]
  unsigned int v79; // [rsp+4Ch] [rbp-7Ch]
  enum _SID_NAME_USE **v80; // [rsp+50h] [rbp-78h]
  _DWORD *v81; // [rsp+58h] [rbp-70h]
  struct _UNICODE_STRING **v82; // [rsp+60h] [rbp-68h]
  _DWORD *hMem; // [rsp+68h] [rbp-60h]
  _QWORD *v84; // [rsp+70h] [rbp-58h]
  struct _UNICODE_STRING *v85; // [rsp+78h] [rbp-50h]
  void *v86; // [rsp+80h] [rbp-48h] BYREF

  v6 = a3;
  v7 = a2;
  if ( (Microsoft_Windows_SAMLIBEnableBits & 1) != 0 )
  {
    CallingProcessInfo = SampQueryCallingProcessInfo();
    v11 = CallingProcessInfo;
    if ( (Microsoft_Windows_SAMLIBEnableBits & 1) != 0 )
    {
      v12 = L"<unknown>";
      if ( CallingProcessInfo )
        v12 = CallingProcessInfo;
      McTemplateU0pqz_EventWriteTransfer(v10, (unsigned int)SamLookupIdsInDomainEntry, (_DWORD)a1, v7, (__int64)v12);
    }
    LocalFree(v11);
    v6 = a3;
  }
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 107, &WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids, a1, v7);
  if ( !(unsigned __int8)SampIsValidClientHandle(a1, &v86) )
  {
    v14 = -1073741816;
    if ( (Microsoft_Windows_SAMLIBEnableBits & 1) != 0 )
      McTemplateU0d_EventWriteTransfer(v13, SamLookupIdsInDomainExit, 3221225480LL);
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 108, &WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids, a1);
    return v14;
  }
  if ( v7 <= 0x3E8 )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 109, &WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids);
    v16 = SampLookupIdsInDomain(a1, v7, v6, a4, a5);
    v14 = v16;
    v17 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 110, &WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids, v16);
    if ( (Microsoft_Windows_SAMLIBEnableBits & 1) != 0 )
      McTemplateU0d_EventWriteTransfer(v17, SamLookupIdsInDomainExit, v14);
    return v14;
  }
  v84 = 0;
  v18 = 0;
  v76 = 0;
  v82 = 0;
  v80 = 0;
  v19 = -1073741801;
  v20 = (v7 >> 9) + 1;
  if ( (v7 & 0x1FF) == 0 )
    v20 = v7 >> 9;
  v21 = (unsigned int)v20;
  v86 = (void *)(unsigned int)v20;
  v22 = 4 * v20;
  v23 = LocalAlloc(0x40u, 4 * v20);
  hMem = v23;
  if ( !v23 )
  {
    v81 = 0;
    goto LABEL_107;
  }
  memset_0(v23, 0, v22);
  v24 = LocalAlloc(0x40u, v22);
  v81 = v24;
  if ( !v24 )
    goto LABEL_107;
  memset_0(v24, 0, v22);
  v25 = LocalAlloc(0x40u, v22);
  v76 = v25;
  if ( !v25 )
    goto LABEL_107;
  memset_0(v25, 0, v22);
  v26 = (struct _UNICODE_STRING **)LocalAlloc(0x40u, 8 * v21);
  v82 = v26;
  v18 = v26;
  if ( !v26 )
    goto LABEL_107;
  memset_0(v26, 0, 8 * v21);
  v27 = (enum _SID_NAME_USE **)LocalAlloc(0x40u, 8 * v21);
  v80 = v27;
  if ( !v27 )
    goto LABEL_107;
  memset_0(v27, 0, 8 * v21);
  v28 = LocalAlloc(0x40u, 8 * v21);
  v84 = v28;
  if ( !v28 )
    goto LABEL_107;
  v78 = 0;
  v75 = 0;
  v29 = 0;
  memset_0(v28, 0, 8 * v21);
  v30 = WPP_GLOBAL_Control;
  v31 = 0;
  v77 = 0;
  v32 = 0;
  for ( i = 0; i < (unsigned int)v21; ++i )
  {
    if ( (*((_BYTE *)v30 + 28) & 2) != 0 && *((_BYTE *)v30 + 25) >= 4u )
    {
      WPP_SF_D(v30[2], 111, &WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids, i);
      v32 = v77;
    }
    v34 = v7 - v32;
    if ( v7 - v32 > 0x200 )
      v34 = 512;
    hMem[i] = v32;
    v79 = v34;
    v81[i] = v34;
    v19 = SampLookupIdsInDomain(a1, v34, &a3[hMem[i]], &v18[i], &v80[i]);
    v76[i] = v19;
    if ( v19 == 263 )
    {
      v35 = ++v78;
      v30 = WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        v36 = 112;
        v37 = v35;
        goto LABEL_45;
      }
      goto LABEL_46;
    }
    if ( v19 == -1073741709 )
    {
      ++v29;
      v31 = 0;
      v75 = v29;
      v30 = WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        v36 = 113;
        v37 = v29;
LABEL_45:
        WPP_SF_D(v30[2], v36, &WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids, v37);
        v30 = WPP_GLOBAL_Control;
LABEL_46:
        v31 = 0;
      }
    }
    else
    {
      v31 = 0;
      if ( v19 < 0 )
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          WPP_SF_D(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            114,
            &WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids,
            (unsigned int)v19);
        goto LABEL_107;
      }
      v30 = WPP_GLOBAL_Control;
    }
    v32 = v79 + v77;
    v77 += v79;
  }
  v38 = 0;
  v39 = 16 * v7;
  if ( (_DWORD)v21 )
  {
    do
    {
      if ( v76[v38] != -1073741709 )
      {
        v40 = v81[v38];
        if ( v40 )
        {
          do
          {
            v41 = v31++;
            v39 += v18[v38][v41].MaximumLength;
          }
          while ( v31 < v40 );
          v31 = 0;
        }
      }
      ++v38;
    }
    while ( v38 < (unsigned int)v21 );
  }
  else
  {
    v75 = v29;
  }
  v19 = -1073741670;
  v42 = v39;
  v43 = (struct _UNICODE_STRING *)LocalAlloc(0x40u, v39);
  v85 = v43;
  v44 = v43;
  if ( !v43 )
  {
LABEL_107:
    *a4 = 0;
    if ( a5 )
      *a5 = 0;
LABEL_109:
    v65 = WPP_GLOBAL_Control;
    goto LABEL_110;
  }
  memset_0(v43, 0, v42);
  v45 = 0;
  if ( (_DWORD)v21 )
  {
    v46 = v44;
    v47 = v76;
    do
    {
      if ( v47[v45] != -1073741709 )
      {
        v48 = v18[v45];
        v49 = 16 * v81[v45];
        v84[v45] = (char *)v46 - (char *)v48;
        memmove_0(v46, v48, v49);
        v47 = v76;
        v46 = (struct _UNICODE_STRING *)((char *)v46 + v49);
      }
      ++v45;
    }
    while ( v45 < (unsigned int)v21 );
    v19 = -1073741670;
    v50 = 0;
    v51 = v46;
    do
    {
      if ( v47[v50] != -1073741709 )
      {
        v52 = 0;
        if ( v81[v50] )
        {
          v53 = v82;
          do
          {
            v54 = v53[v50];
            MaximumLength = v54[v52].MaximumLength;
            if ( (_WORD)MaximumLength )
            {
              Buffer = v54[v52].Buffer;
              v57 = v54[v52].MaximumLength;
              *(PWSTR *)((char *)&v54[v52].Buffer + v84[v50]) = &v51->Length;
              memmove_0(v51, Buffer, MaximumLength);
              v53 = v82;
              v51 = (struct _UNICODE_STRING *)((char *)v51 + v57);
            }
            ++v52;
          }
          while ( v52 < v81[v50] );
          LODWORD(v21) = (_DWORD)v86;
          v47 = v76;
        }
      }
      ++v50;
    }
    while ( v50 < (unsigned int)v21 );
    v7 = a2;
    v29 = v75;
    v18 = v82;
    v44 = v85;
  }
  if ( a5 )
  {
    v58 = (enum _SID_NAME_USE *)LocalAlloc(0x40u, 4 * v7);
    v59 = v58;
    if ( !v58 )
    {
      LocalFree(v44);
      goto LABEL_107;
    }
    memset_0(v58, 0, 4 * v7);
    v60 = v59;
    v61 = 0;
    if ( (_DWORD)v21 )
    {
      v62 = v76;
      do
      {
        if ( v62[v61] != -1073741709 )
        {
          v63 = (unsigned int)(4 * v81[v61]);
          memmove_0(v60, v80[v61], v63);
          v62 = v76;
          v60 = (enum _SID_NAME_USE *)((char *)v60 + v63);
        }
        ++v61;
      }
      while ( v61 < (unsigned int)v21 );
      v29 = v75;
      v18 = v82;
    }
    *a5 = v59;
  }
  v64 = v78;
  *a4 = v85;
  if ( v78 )
  {
    v19 = 263;
    v65 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v66 = 115;
      goto LABEL_100;
    }
    goto LABEL_101;
  }
  if ( v29 == (_DWORD)v21 )
  {
    v19 = -1073741709;
    v65 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
      goto LABEL_101;
    v66 = 116;
    goto LABEL_99;
  }
  v19 = 0;
  if ( !v29 )
    goto LABEL_109;
  v19 = 263;
  v65 = WPP_GLOBAL_Control;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    v66 = 117;
LABEL_99:
    v64 = v29;
LABEL_100:
    WPP_SF_D(v65[2], v66, &WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids, v64);
LABEL_101:
    v67 = v80;
    v68 = v18;
    v69 = hMem;
    v70 = v80;
    goto LABEL_111;
  }
LABEL_110:
  v69 = hMem;
  v68 = v18;
  v67 = v80;
  v70 = v80;
  if ( hMem )
  {
LABEL_111:
    LocalFree(v69);
    v65 = WPP_GLOBAL_Control;
  }
  if ( v81 )
  {
    LocalFree(v81);
    v65 = WPP_GLOBAL_Control;
  }
  if ( v76 )
  {
    LocalFree(v76);
    v65 = WPP_GLOBAL_Control;
  }
  if ( v84 )
  {
    LocalFree(v84);
    v65 = WPP_GLOBAL_Control;
  }
  if ( v18 )
  {
    v71 = 0;
    if ( (_DWORD)v21 )
    {
      do
      {
        v72 = v68[v71];
        if ( v72 )
        {
          LocalFree(v72);
          v68[v71] = 0;
        }
        ++v71;
      }
      while ( v71 < (unsigned int)v21 );
      v18 = v82;
    }
    LocalFree(v18);
    v65 = WPP_GLOBAL_Control;
  }
  if ( v67 )
  {
    for ( j = 0; j < (unsigned int)v21; ++j )
    {
      v74 = v70[j];
      if ( v74 )
      {
        LocalFree(v74);
        v70[j] = 0;
      }
    }
    LocalFree(v67);
    v65 = WPP_GLOBAL_Control;
  }
  if ( v19 < 0 )
  {
    if ( (*((_BYTE *)v65 + 28) & 2) != 0 && *((_BYTE *)v65 + 25) >= 2u )
      WPP_SF_D(v65[2], 119, &WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids, (unsigned int)v19);
  }
  else if ( (*((_BYTE *)v65 + 28) & 2) != 0 && *((_BYTE *)v65 + 25) >= 4u )
  {
    WPP_SF_(v65[2], 118, &WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids);
  }
  if ( (Microsoft_Windows_SAMLIBEnableBits & 1) != 0 )
    McTemplateU0d_EventWriteTransfer(v65, SamLookupIdsInDomainExit, (unsigned int)v19);
  return (unsigned int)v19;
}

```

## disassembly

```asm
0x18000f5c0  mov     rax, rsp
0x18000f5c3  mov     [rax+8], rbx
0x18000f5c7  mov     [rax+20h], r9
0x18000f5cb  mov     [rax+18h], r8
0x18000f5cf  mov     [rax+10h], edx
0x18000f5d2  push    rbp
0x18000f5d3  push    rsi
0x18000f5d4  push    rdi
0x18000f5d5  push    r12
0x18000f5d7  push    r13
0x18000f5d9  push    r14
0x18000f5db  push    r15
0x18000f5dd  sub     rsp, 90h
0x18000f5e4  xor     ebp, ebp
0x18000f5e6  mov     rdi, r9
0x18000f5e9  test    byte ptr cs:Microsoft_Windows_SAMLIBEnableBits, 1
0x18000f5f0  mov     rbx, r8
0x18000f5f3  mov     r12d, edx
0x18000f5f6  mov     rsi, rcx
0x18000f5f9  jz      short loc_18000F642
0x18000f5fb  call    ?SampQueryCallingProcessInfo@@YAPEAGXZ; SampQueryCallingProcessInfo(void)
0x18000f600  test    byte ptr cs:Microsoft_Windows_SAMLIBEnableBits, 1
0x18000f607  mov     rbx, rax
0x18000f60a  jz      short loc_18000F631
0x18000f60c  test    rax, rax
0x18000f60f  lea     rdx, aUnknown; "<unknown>"
0x18000f616  mov     r9d, r12d
0x18000f619  mov     r8, rsi
0x18000f61c  cmovnz  rdx, rax
0x18000f620  mov     [rsp+0C8h+var_A8], rdx
0x18000f625  lea     rdx, SamLookupIdsInDomainEntry
0x18000f62c  call    McTemplateU0pqz_EventWriteTransfer
0x18000f631  mov     rcx, rbx; hMem
0x18000f634  call    cs:__imp_LocalFree
0x18000f63a  mov     rbx, [rsp+0C8h+arg_10]
0x18000f642  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f649  lea     r15, WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids
0x18000f650  mov     r14b, 2
0x18000f653  mov     r13b, 4
0x18000f656  test    [rcx+1Ch], r14b
0x18000f65a  jz      short loc_18000F67B
0x18000f65c  cmp     [rcx+19h], r13b
0x18000f660  jb      short loc_18000F67B
0x18000f662  mov     rcx, [rcx+10h]
0x18000f666  mov     edx, 6Bh ; 'k'
0x18000f66b  mov     r9, rsi
0x18000f66e  mov     dword ptr [rsp+0C8h+var_A8], r12d
0x18000f673  mov     r8, r15
0x18000f676  call    WPP_SF_qD
0x18000f67b  lea     rdx, [rsp+0C8h+var_48]; void **
0x18000f683  mov     rcx, rsi; void *
0x18000f686  call    ?SampIsValidClientHandle@@YAEPEAXPEAPEAX@Z; SampIsValidClientHandle(void *,void * *)
0x18000f68b  test    al, al
0x18000f68d  jnz     short loc_18000F6DA
0x18000f68f  test    byte ptr cs:Microsoft_Windows_SAMLIBEnableBits, 1
0x18000f696  mov     ebx, 0C0000008h
0x18000f69b  jz      short loc_18000F6AC
0x18000f69d  mov     r8d, ebx
0x18000f6a0  lea     rdx, SamLookupIdsInDomainExit
0x18000f6a7  call    McTemplateU0d_EventWriteTransfer
0x18000f6ac  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f6b3  test    [rcx+1Ch], r14b
0x18000f6b7  jz      short loc_18000F6D3
0x18000f6b9  cmp     [rcx+19h], r14b
0x18000f6bd  jb      short loc_18000F6D3
0x18000f6bf  mov     rcx, [rcx+10h]
0x18000f6c3  mov     edx, 6Ch ; 'l'
0x18000f6c8  mov     r9, rsi
0x18000f6cb  mov     r8, r15
0x18000f6ce  call    WPP_SF_q
0x18000f6d3  mov     eax, ebx
0x18000f6d5  jmp     loc_18000FEA9
0x18000f6da  cmp     r12d, 3E8h
0x18000f6e1  ja      loc_18000F773
0x18000f6e7  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f6ee  test    [rcx+1Ch], r14b
0x18000f6f2  jz      short loc_18000F70B
0x18000f6f4  cmp     [rcx+19h], r13b
0x18000f6f8  jb      short loc_18000F70B
0x18000f6fa  mov     rcx, [rcx+10h]
0x18000f6fe  mov     edx, 6Dh ; 'm'
0x18000f703  mov     r8, r15
0x18000f706  call    WPP_SF_
0x18000f70b  mov     rax, [rsp+0C8h+arg_20]
0x18000f713  mov     r9, rdi; struct _UNICODE_STRING **
0x18000f716  mov     r8, rbx; unsigned int *
0x18000f719  mov     [rsp+0C8h+var_A8], rax; enum _SID_NAME_USE **
0x18000f71e  mov     edx, r12d; unsigned int
0x18000f721  mov     rcx, rsi; void *
0x18000f724  call    ?SampLookupIdsInDomain@@YAJPEAXKPEAKPEAPEAU_UNICODE_STRING@@PEAPEAW4_SID_NAME_USE@@@Z; SampLookupIdsInDomain(void *,ulong,ulong *,_UNICODE_STRING * *,_SID_NAME_USE * *)
0x18000f729  mov     ebx, eax
0x18000f72b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f732  test    [rcx+1Ch], r14b
0x18000f736  jz      short loc_18000F752
0x18000f738  cmp     [rcx+19h], r13b
0x18000f73c  jb      short loc_18000F752
0x18000f73e  mov     rcx, [rcx+10h]
0x18000f742  mov     edx, 6Eh ; 'n'
0x18000f747  mov     r9d, eax
0x18000f74a  mov     r8, r15
0x18000f74d  call    WPP_SF_D
0x18000f752  test    byte ptr cs:Microsoft_Windows_SAMLIBEnableBits, 1
0x18000f759  jz      loc_18000F6D3
0x18000f75f  mov     r8d, ebx
0x18000f762  lea     rdx, SamLookupIdsInDomainExit
0x18000f769  call    McTemplateU0d_EventWriteTransfer
0x18000f76e  jmp     loc_18000F6D3
0x18000f773  mov     ecx, r12d
0x18000f776  mov     [rsp+0C8h+var_58], rbp
0x18000f77b  shr     ecx, 9
0x18000f77e  mov     r15, rbp
0x18000f781  test    r12d, 1FFh
0x18000f788  mov     [rsp+0C8h+var_90], rbp
0x18000f78d  mov     [rsp+0C8h+var_68], rbp
0x18000f792  mov     r13d, 40h ; '@'
0x18000f798  mov     [rsp+0C8h+var_78], rbp
0x18000f79d  mov     edi, 0C0000017h
0x18000f7a2  lea     eax, [rcx+1]
0x18000f7a5  cmovbe  eax, ecx
0x18000f7a8  mov     ecx, r13d; uFlags
0x18000f7ab  mov     ebp, eax
0x18000f7ad  mov     [rsp+0C8h+var_48], rbp
0x18000f7b5  lea     rbx, ds:0[rax*4]
0x18000f7bd  mov     rdx, rbx; uBytes
0x18000f7c0  call    cs:__imp_LocalAlloc
0x18000f7c6  xor     edx, edx; Val
0x18000f7c8  mov     [rsp+0C8h+hMem], rax
0x18000f7cd  test    rax, rax
0x18000f7d0  jz      loc_18000FD2A
0x18000f7d6  mov     r8, rbx; Size
0x18000f7d9  mov     rcx, rax; void *
0x18000f7dc  call    memset_0
0x18000f7e1  mov     rdx, rbx; uBytes
0x18000f7e4  mov     ecx, r13d; uFlags
0x18000f7e7  call    cs:__imp_LocalAlloc
0x18000f7ed  xor     edx, edx; Val
0x18000f7ef  mov     [rsp+0C8h+var_70], rax
0x18000f7f4  test    rax, rax
0x18000f7f7  jz      loc_18000FD2F
0x18000f7fd  mov     r8, rbx; Size
0x18000f800  mov     rcx, rax; void *
0x18000f803  call    memset_0
0x18000f808  mov     rdx, rbx; uBytes
0x18000f80b  mov     ecx, r13d; uFlags
0x18000f80e  call    cs:__imp_LocalAlloc
0x18000f814  xor     edx, edx; Val
0x18000f816  mov     [rsp+0C8h+var_90], rax
0x18000f81b  test    rax, rax
0x18000f81e  jz      loc_18000FD2F
0x18000f824  mov     r8, rbx; Size
0x18000f827  mov     rcx, rax; void *
0x18000f82a  call    memset_0
0x18000f82f  lea     rbx, ds:0[rbp*8]
0x18000f837  mov     ecx, r13d; uFlags
0x18000f83a  mov     rdx, rbx; uBytes
0x18000f83d  call    cs:__imp_LocalAlloc
0x18000f843  xor     edx, edx; Val
0x18000f845  mov     [rsp+0C8h+var_68], rax
0x18000f84a  mov     r15, rax
0x18000f84d  test    rax, rax
0x18000f850  jz      loc_18000FD2F
0x18000f856  mov     r8, rbx; Size
0x18000f859  mov     rcx, rax; void *
0x18000f85c  call    memset_0
0x18000f861  mov     rdx, rbx; uBytes
0x18000f864  mov     ecx, r13d; uFlags
0x18000f867  call    cs:__imp_LocalAlloc
0x18000f86d  xor     edx, edx; Val
0x18000f86f  mov     [rsp+0C8h+var_78], rax
0x18000f874  test    rax, rax
0x18000f877  jz      loc_18000FD2F
0x18000f87d  mov     r8, rbx; Size
0x18000f880  mov     rcx, rax; void *
0x18000f883  call    memset_0
0x18000f888  mov     rdx, rbx; uBytes
0x18000f88b  mov     ecx, r13d; uFlags
0x18000f88e  call    cs:__imp_LocalAlloc
0x18000f894  xor     edx, edx; Val
0x18000f896  mov     [rsp+0C8h+var_58], rax
0x18000f89b  test    rax, rax
0x18000f89e  jz      loc_18000FD2F
0x18000f8a4  mov     r8, rbx; Size
0x18000f8a7  mov     [rsp+0C8h+var_80], edx
0x18000f8ab  mov     rcx, rax; void *
0x18000f8ae  mov     [rsp+0C8h+var_98], edx
0x18000f8b2  mov     r13d, edx
0x18000f8b5  call    memset_0
0x18000f8ba  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f8c1  xor     edx, edx
0x18000f8c3  mov     edi, edx
0x18000f8c5  mov     dword ptr [rsp+0C8h+var_88], edx
0x18000f8c9  mov     eax, edx
0x18000f8cb  mov     r14d, edx
0x18000f8ce  mov     r9d, 200h
0x18000f8d4  cmp     r14d, ebp
0x18000f8d7  jnb     loc_18000FA37
0x18000f8dd  test    byte ptr [rcx+1Ch], 2
0x18000f8e1  jz      short loc_18000F90B
0x18000f8e3  cmp     byte ptr [rcx+19h], 4
0x18000f8e7  jb      short loc_18000F90B
0x18000f8e9  mov     rcx, [rcx+10h]
0x18000f8ed  lea     r8, WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids
0x18000f8f4  mov     edx, 6Fh ; 'o'
0x18000f8f9  mov     r9d, r14d
0x18000f8fc  call    WPP_SF_D
0x18000f901  mov     eax, dword ptr [rsp+0C8h+var_88]
0x18000f905  mov     r9d, 200h
0x18000f90b  mov     r8, [rsp+0C8h+hMem]
0x18000f910  mov     edx, r12d
0x18000f913  sub     edx, eax
0x18000f915  mov     ebx, r14d
0x18000f918  cmp     edx, r9d
0x18000f91b  cmova   edx, r9d; unsigned int
0x18000f91f  mov     [r8+rbx*4], eax
0x18000f923  lea     r9, [r15+rbx*8]; struct _UNICODE_STRING **
0x18000f927  mov     rax, [rsp+0C8h+var_70]
0x18000f92c  mov     [rsp+0C8h+var_7C], edx
0x18000f930  mov     [rax+rbx*4], edx
0x18000f933  mov     rax, [rsp+0C8h+var_78]
0x18000f938  lea     rcx, [rax+rbx*8]
0x18000f93c  mov     eax, [r8+rbx*4]
0x18000f940  mov     r8, [rsp+0C8h+arg_10]
0x18000f948  mov     [rsp+0C8h+var_A8], rcx; enum _SID_NAME_USE **
0x18000f94d  mov     rcx, rsi; void *
0x18000f950  lea     r8, [r8+rax*4]; unsigned int *
0x18000f954  call    ?SampLookupIdsInDomain@@YAJPEAXKPEAKPEAPEAU_UNICODE_STRING@@PEAPEAW4_SID_NAME_USE@@@Z; SampLookupIdsInDomain(void *,ulong,ulong *,_UNICODE_STRING * *,_SID_NAME_USE * *)
0x18000f959  mov     edi, eax
0x18000f95b  mov     rax, [rsp+0C8h+var_90]
0x18000f960  mov     [rax+rbx*4], edi
0x18000f963  cmp     edi, 107h
0x18000f969  jnz     short loc_18000F9BD
0x18000f96b  mov     eax, [rsp+0C8h+var_80]
0x18000f96f  inc     eax
0x18000f971  mov     [rsp+0C8h+var_80], eax
0x18000f975  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f97c  test    byte ptr [rcx+1Ch], 2
0x18000f980  jz      short loc_18000F9A7
0x18000f982  cmp     byte ptr [rcx+19h], 4
0x18000f986  jb      short loc_18000F9A7
0x18000f988  mov     edx, 70h ; 'p'
0x18000f98d  mov     r9d, eax
0x18000f990  mov     rcx, [rcx+10h]
0x18000f994  lea     r8, WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids
0x18000f99b  call    WPP_SF_D
0x18000f9a0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f9a7  xor     edx, edx
0x18000f9a9  mov     eax, dword ptr [rsp+0C8h+var_88]
0x18000f9ad  add     eax, [rsp+0C8h+var_7C]
0x18000f9b1  mov     dword ptr [rsp+0C8h+var_88], eax
0x18000f9b5  inc     r14d
0x18000f9b8  jmp     loc_18000F8CE
0x18000f9bd  cmp     edi, 0C0000073h
0x18000f9c3  jnz     short loc_18000F9EE
0x18000f9c5  inc     r13d
0x18000f9c8  xor     edx, edx
0x18000f9ca  mov     [rsp+0C8h+var_98], r13d
0x18000f9cf  mov     edi, edx
0x18000f9d1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f9d8  test    byte ptr [rcx+1Ch], 2
0x18000f9dc  jz      short loc_18000F9A9
0x18000f9de  cmp     byte ptr [rcx+19h], 4
0x18000f9e2  jb      short loc_18000F9A9
0x18000f9e4  mov     edx, 71h ; 'q'
0x18000f9e9  mov     r9d, r13d
0x18000f9ec  jmp     short loc_18000F990
0x18000f9ee  xor     edx, edx
0x18000f9f0  test    edi, edi
0x18000f9f2  js      short loc_18000F9FD
0x18000f9f4  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f9fb  jmp     short loc_18000F9A9
0x18000f9fd  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fa04  test    byte ptr [rcx+1Ch], 2
0x18000fa08  jz      loc_18000FD2F
0x18000fa0e  cmp     byte ptr [rcx+19h], 4
0x18000fa12  jb      loc_18000FD2F
0x18000fa18  mov     rcx, [rcx+10h]
0x18000fa1c  lea     r8, WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids
0x18000fa23  mov     edx, 72h ; 'r'
0x18000fa28  mov     r9d, edi
0x18000fa2b  call    WPP_SF_D
0x18000fa30  xor     edx, edx
0x18000fa32  jmp     loc_18000FD2F
0x18000fa37  test    edi, edi
0x18000fa39  js      loc_18000FD2F
0x18000fa3f  mov     r8d, r12d
0x18000fa42  mov     ecx, edx
0x18000fa44  shl     r8d, 4
0x18000fa48  test    ebp, ebp
0x18000fa4a  jz      short loc_18000FA8D
0x18000fa4c  mov     r11, [rsp+0C8h+var_70]
0x18000fa51  mov     rbx, [rsp+0C8h+var_90]
0x18000fa56  mov     eax, ecx
0x18000fa58  cmp     dword ptr [rbx+rax*4], 0C0000073h
0x18000fa5f  jz      short loc_18000FA85
0x18000fa61  mov     r9d, [r11+rax*4]
0x18000fa65  test    r9d, r9d
0x18000fa68  jz      short loc_18000FA85
0x18000fa6a  mov     r10, [r15+rax*8]
0x18000fa6e  mov     eax, edx
0x18000fa70  inc     edx
  ... truncated ...
```
