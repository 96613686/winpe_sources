# CDidlLiteObjectWriter::WriteInnerResAttributes(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> &,_WMCResElement const *,CDidlLiteObjectWriter::CdsElement *)

- ea: `0x1400124d0`
- end: `0x140012b24`
- name: `?WriteInnerResAttributes@CDidlLiteObjectWriter@@IEAAJAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@PEBU_WMCResElement@@PEAVCdsElement@1@@Z`
- size: `1620`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `17`
- tags: `loader_planting, service_task`

## callers

- `0x140011d70`

## callees

- `0x140011714`
- `0x1400124d0`
- `0x140012b30`
- `0x140013570`
- `0x140015230`
- `0x140023eb0`
- `0x1400396dc`
- `0x140046c32`
- `0x140046d00`
- `0x140047798`
- `0x14004a500`
- `0x14004a834`
- `0x140054490`
- `0x1400907d4`
- `0x14009a294`
- `0x14009ad10`
- `0x14009e010`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x14001268e`
- `KERNEL32!GetProcessHeap` at `0x14001268e`
- `KERNEL32!HeapFree` at `0x14001269c`
- `KERNEL32!HeapFree` at `0x14001269c`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140012622`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14001292b`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140012a06`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140012a29`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140012622`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14001292b`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140012a06`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140012a29`
- `ole32!CoTaskMemFree` at `0x140012a5e`
- `ole32!CoTaskMemFree` at `0x140012a5e`

## pseudocode

```c
__int64 __fastcall CDidlLiteObjectWriter::WriteInnerResAttributes(__int64 a1, _QWORD *a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rsi
  __int64 v7; // rdx
  __int64 v8; // rbp
  unsigned int v9; // r15d
  __int64 v10; // r8
  _QWORD *i; // rax
  __int64 v12; // rdi
  _QWORD *v13; // r12
  __int64 v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // r8
  void *v17; // rsi
  int v18; // r13d
  const wchar_t *v19; // r14
  unsigned __int64 v20; // rbp
  unsigned __int64 v21; // r15
  int v22; // esi
  __int64 v23; // rcx
  wchar_t *v24; // rcx
  int v25; // eax
  HANDLE ProcessHeap; // rax
  int v27; // r14d
  PVOID *v28; // r10
  unsigned int v29; // r15d
  __int64 v31; // rdx
  const void *v32; // rbp
  unsigned __int64 v33; // r14
  __int64 v34; // r15
  unsigned __int64 v35; // rsi
  int v36; // edi
  __int64 v37; // rcx
  size_t v38; // r8
  void *v39; // rcx
  const wchar_t *v40; // r14
  __int64 v41; // rdx
  unsigned __int64 v42; // rsi
  unsigned __int64 v43; // rbp
  int v44; // edi
  __int64 v45; // rcx
  _DWORD *v46; // rcx
  int *v47; // r8
  __int64 v48; // rdx
  const wchar_t *v49; // rsi
  unsigned __int64 v50; // rbp
  unsigned __int64 v51; // r14
  int v52; // edi
  __int64 v53; // rcx
  wchar_t *v54; // rcx
  unsigned int v55; // [rsp+38h] [rbp-60h] BYREF
  __int64 v56; // [rsp+3Ch] [rbp-5Ch]
  int v57; // [rsp+44h] [rbp-54h]
  LPVOID lpMem; // [rsp+48h] [rbp-50h]
  unsigned int v60; // [rsp+A8h] [rbp+10h]
  unsigned int v62; // [rsp+B8h] [rbp+20h]

  v4 = a3;
  v7 = *a2;
  v8 = a1;
  v9 = *(_DWORD *)(v7 - 16);
  v60 = v9;
  v10 = v9 - 10;
  if ( v9 <= 0xA )
    v10 = 0;
  v62 = v10;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_Sqq(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      99,
      (unsigned int)&WPP_478ffc6658c23ee89d991dcff0807d2d_Traceguids,
      v7 + 2 * v10,
      v4,
      a4);
  }
  for ( i = *(_QWORD **)(a4 + 16); ; i = v13 )
  {
    if ( !i )
    {
      v27 = 0;
      goto LABEL_34;
    }
    v12 = i[2];
    v13 = (_QWORD *)*i;
    if ( (*(unsigned __int8 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(v8 + 24) + 8LL))(
           *(_QWORD *)(v8 + 24),
           *(unsigned int *)(v12 + 8))
      || (*(unsigned __int8 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(v8 + 24) + 16LL))(
           *(_QWORD *)(v8 + 24),
           *(unsigned int *)(v12 + 8)) )
    {
      break;
    }
LABEL_27:
    ;
  }
  v14 = *(unsigned int *)(v12 + 8);
  v55 &= 0xFFFFFFF8;
  v56 = 0;
  lpMem = 0;
  v57 = 0;
  CDidlLiteObjectWriter::GetResElementValue(v14, v4, &v55);
  v17 = lpMem;
  if ( (int)v56 >= 0 )
  {
    v18 = HIDWORD(v56);
    if ( HIDWORD(v56) )
    {
      v19 = L" ";
      v20 = ((__int64)L" " - *a2) >> 1;
      v21 = *(unsigned int *)(*a2 - 16LL);
      v22 = v21 + 1;
      if ( (((*(_DWORD *)(*a2 - 12LL) - (v21 + 1)) | (1 - *(_DWORD *)(*a2 - 8LL))) & 0x80000000) != 0LL )
        ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(a2, (unsigned int)v22);
      v23 = *a2;
      if ( v20 <= v21 )
        v19 = (const wchar_t *)(v23 + 2 * v20);
      v24 = (wchar_t *)(v23 + 2 * v21);
      if ( v24 )
      {
        if ( v19 )
        {
          *v24 = *v19;
          goto LABEL_46;
        }
        *v24 = 0;
      }
      *(_DWORD *)_o__errno(v24, v15, v16) = 22;
      invalid_parameter_noinfo();
LABEL_46:
      if ( v22 < 0 || v22 > *(_DWORD *)(*a2 - 12LL) )
LABEL_90:
        ATL::AtlThrowImpl(-2147024809);
      *(_DWORD *)(*a2 - 16LL) = v22;
      v31 = v22;
      *(_WORD *)(*a2 + 2LL * v22) = 0;
      v32 = *(const void **)v12;
      v33 = *(unsigned int *)(*a2 - 16LL);
      v34 = *(int *)(*(_QWORD *)v12 - 16LL);
      v35 = (__int64)(*(_QWORD *)v12 - *a2) >> 1;
      v36 = v34 + v33;
      if ( (((*(_DWORD *)(*a2 - 12LL) - (v34 + v33)) | (1 - *(_DWORD *)(*a2 - 8LL))) & 0x80000000) != 0LL )
        ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(a2, (unsigned int)v36);
      v37 = *a2;
      if ( v35 <= v33 )
        v32 = (const void *)(v37 + 2 * v35);
      v38 = 2 * v34;
      if ( 2 * v34 )
      {
        v39 = (void *)(v37 + 2 * v33);
        if ( v39 )
        {
          if ( v32 )
          {
            memcpy_0(v39, v32, v38);
            goto LABEL_56;
          }
          memset_0(v39, 0, v38);
        }
        *(_DWORD *)_o__errno(v39, v31, v38) = 22;
        invalid_parameter_noinfo();
      }
LABEL_56:
      if ( v36 < 0 || v36 > *(_DWORD *)(*a2 - 12LL) )
        goto LABEL_90;
      *(_DWORD *)(*a2 - 16LL) = v36;
      v40 = L"=\"";
      v41 = v36;
      *(_WORD *)(*a2 + 2LL * v36) = 0;
      v42 = ((__int64)L"=\"" - *a2) >> 1;
      v43 = *(unsigned int *)(*a2 - 16LL);
      v44 = v43 + 2;
      if ( (((*(_DWORD *)(*a2 - 12LL) - (v43 + 2)) | (1 - *(_DWORD *)(*a2 - 8LL))) & 0x80000000) != 0LL )
        ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(a2, (unsigned int)v44);
      v45 = *a2;
      if ( v42 <= v43 )
        v40 = (const wchar_t *)(v45 + 2 * v42);
      v46 = (_DWORD *)(v45 + 2 * v43);
      if ( v46 )
      {
        if ( v40 )
        {
          *v46 = *(_DWORD *)v40;
LABEL_65:
          if ( v44 < 0 || v44 > *(_DWORD *)(*a2 - 12LL) )
            goto LABEL_90;
          v47 = (int *)lpMem;
          *(_DWORD *)(*a2 - 16LL) = v44;
          if ( !v18 )
            v47 = &CMFBaseStringT<unsigned short>::m_EmptyString;
          *(_WORD *)(*a2 + 2LL * v44) = 0;
          CDidlLiteObjectWriter::WriteEscapedAttributeValue(a2, v62, v47);
          v49 = L"\"";
          v50 = ((__int64)L"\"" - *a2) >> 1;
          v51 = *(unsigned int *)(*a2 - 16LL);
          v52 = v51 + 1;
          if ( (((*(_DWORD *)(*a2 - 12LL) - (v51 + 1)) | (1 - *(_DWORD *)(*a2 - 8LL))) & 0x80000000) != 0LL )
            ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(a2, (unsigned int)v52);
          v53 = *a2;
          if ( v50 <= v51 )
            v49 = (const wchar_t *)(v53 + 2 * v50);
          v54 = (wchar_t *)(v53 + 2 * v51);
          if ( v54 )
          {
            if ( v49 )
            {
              *v54 = *v49;
              goto LABEL_19;
            }
            *v54 = 0;
          }
          *(_DWORD *)_o__errno(v54, v48, v10) = 22;
          invalid_parameter_noinfo();
LABEL_19:
          if ( v52 < 0 || v52 > *(_DWORD *)(*a2 - 12LL) )
            goto LABEL_90;
          v17 = lpMem;
          v8 = a1;
          *(_DWORD *)(*a2 - 16LL) = v52;
          v7 = v52;
          *(_WORD *)(*a2 + 2LL * v52) = 0;
          goto LABEL_22;
        }
        *v46 = 0;
      }
      *(_DWORD *)_o__errno(v46, v41, v38) = 22;
      invalid_parameter_noinfo();
      goto LABEL_65;
    }
  }
  if ( !(*(unsigned __int8 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(v8 + 24) + 16LL))(
          *(_QWORD *)(v8 + 24),
          *(unsigned int *)(v12 + 8)) )
  {
LABEL_22:
    if ( v17 && (v55 & 1) == 0 )
    {
      v25 = (v55 >> 1) & 3;
      if ( v25 )
      {
        if ( v25 == 1 )
          CoTaskMemFree(v17);
      }
      else
      {
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v17);
      }
    }
    v4 = a3;
    goto LABEL_27;
  }
  v27 = -2147024883;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_Dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      100,
      &WPP_478ffc6658c23ee89d991dcff0807d2d_Traceguids,
      *(unsigned int *)(v12 + 8));
  }
  CMFBaseStringT<unsigned short>::~CMFBaseStringT<unsigned short>((__int64)&v55);
LABEL_34:
  v28 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    v29 = v60;
    if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_qdd(*((_QWORD *)WPP_GLOBAL_Control + 2), v7, v10, *a2, v60, v27);
      v28 = (PVOID *)WPP_GLOBAL_Control;
    }
  }
  else
  {
    v29 = v60;
  }
  if ( v27 >= 0 || *(_DWORD *)(*a2 - 16LL) <= v29 )
  {
LABEL_38:
    if ( v28 != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)v28 + 28) & 2) != 0 )
      {
        WPP_SF_(v28[2], 39, &WPP_478ffc6658c23ee89d991dcff0807d2d_Traceguids);
        v28 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v28 != &WPP_GLOBAL_Control
        && (*((_BYTE *)v28 + 28) & 2) != 0
        && *((unsigned __int8 *)v28 + 25) >= ((v27 >> 31) & 0xFFFFFFFD) + 5 )
      {
        WPP_SF_dS(
          (unsigned int)v28[2],
          101,
          (unsigned int)&WPP_478ffc6658c23ee89d991dcff0807d2d_Traceguids,
          v27,
          *a2 + 2LL * v62);
      }
    }
  }
  else
  {
    ATL::CSimpleStringT<unsigned short,0>::SetLength(a2, v29);
    v28 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_DDd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          38,
          &WPP_478ffc6658c23ee89d991dcff0807d2d_Traceguids,
          *(unsigned int *)(*a2 - 16LL),
          v29,
          v27);
        v28 = (PVOID *)WPP_GLOBAL_Control;
      }
      goto LABEL_38;
    }
  }
  return (unsigned int)v27;
}

```

## disassembly

```asm
0x1400124d0  mov     [rsp+arg_10], r8
0x1400124d5  mov     [rsp+arg_0], rcx
0x1400124da  push    rbx
0x1400124db  push    rbp
0x1400124dc  push    rsi
0x1400124dd  push    rdi
0x1400124de  push    r13
0x1400124e0  push    r14
0x1400124e2  push    r15
0x1400124e4  sub     rsp, 60h
0x1400124e8  xor     eax, eax
0x1400124ea  mov     rsi, r8
0x1400124ed  mov     rbx, rdx
0x1400124f0  mov     rdi, r9
0x1400124f3  mov     rdx, [rdx]
0x1400124f6  mov     rbp, rcx
0x1400124f9  mov     r15d, [rdx-10h]
0x1400124fd  cmp     r15d, 0Ah
0x140012501  mov     [rsp+98h+arg_8], r15d
0x140012509  lea     r8d, [r15-0Ah]
0x14001250d  cmovbe  r8d, eax
0x140012511  mov     [rsp+98h+arg_18], r8d
0x140012519  mov     rcx, cs:WPP_GLOBAL_Control
0x140012520  lea     r13, WPP_GLOBAL_Control
0x140012527  cmp     rcx, r13
0x14001252a  jz      short loc_140012536
0x14001252c  test    byte ptr [rcx+1Ch], 2
0x140012530  jnz     loc_1400129B1
0x140012536  mov     rax, [rdi+10h]
0x14001253a  xor     r15d, r15d
0x14001253d  mov     [rsp+98h+var_68], r15d
0x140012542  mov     [rsp+98h+var_40], r12
0x140012547  test    rax, rax
0x14001254a  jz      loc_140012A74
0x140012550  mov     rdi, [rax+10h]
0x140012554  mov     r12, [rax]
0x140012557  mov     rcx, [rbp+18h]
0x14001255b  mov     edx, [rdi+8]
0x14001255e  mov     rax, [rcx]
0x140012561  mov     rax, [rax+8]
0x140012565  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001256a  test    al, al
0x14001256c  jnz     short loc_140012589
0x14001256e  mov     rcx, [rbp+18h]
0x140012572  mov     edx, [rdi+8]
0x140012575  mov     rax, [rcx]
0x140012578  mov     rax, [rax+10h]
0x14001257c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012581  test    al, al
0x140012583  jz      loc_1400126AA
0x140012589  mov     ecx, [rdi+8]
0x14001258c  lea     r8, [rsp+98h+var_60]
0x140012591  and     [rsp+98h+var_60], 0FFFFFFF8h
0x140012596  mov     rdx, rsi
0x140012599  mov     [rsp+98h+var_5C], 0
0x1400125a2  mov     [rsp+98h+lpMem], r15
0x1400125a7  mov     [rsp+98h+var_54], r15d
0x1400125ac  call    ?GetResElementValue@CDidlLiteObjectWriter@@KAJW4Value@CdsValue@@PEBU_WMCResElement@@AEAV?$CMFBaseStringT@G@@@Z; CDidlLiteObjectWriter::GetResElementValue(CdsValue::Value,_WMCResElement const *,CMFBaseStringT<ushort> &)
0x1400125b1  cmp     dword ptr [rsp+98h+var_5C], 0
0x1400125b6  mov     rsi, [rsp+98h+lpMem]
0x1400125bb  jl      loc_1400126B2
0x1400125c1  mov     r13d, dword ptr [rsp+98h+var_5C+4]
0x1400125c6  test    r13d, r13d
0x1400125c9  jz      loc_1400126B2
0x1400125cf  mov     rax, [rbx]
0x1400125d2  lea     rbp, asc_1400A3A60; " "
0x1400125d9  sub     rbp, rax
0x1400125dc  lea     r14, asc_1400A3A60; " "
0x1400125e3  mov     ecx, 1
0x1400125e8  sar     rbp, 1
0x1400125eb  mov     r15d, [rax-10h]
0x1400125ef  sub     ecx, [rax-8]
0x1400125f2  mov     eax, [rax-0Ch]
0x1400125f5  lea     esi, [r15+1]
0x1400125f9  sub     eax, esi
0x1400125fb  or      ecx, eax
0x1400125fd  jge     short loc_140012609
0x1400125ff  mov     edx, esi
0x140012601  mov     rcx, rbx
0x140012604  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x140012609  mov     rcx, [rbx]
0x14001260c  cmp     rbp, r15
0x14001260f  jbe     loc_1400129E3
0x140012615  lea     rcx, [rcx+r15*2]
0x140012619  test    rcx, rcx
0x14001261c  jnz     loc_140012775
0x140012622  call    cs:__imp__o__errno
0x140012628  mov     dword ptr [rax], 16h
0x14001262e  call    _invalid_parameter_noinfo
0x140012633  jmp     loc_140012785
0x140012638  test    rsi, rsi
0x14001263b  jz      loc_140012A48
0x140012641  movzx   eax, word ptr [rsi]
0x140012644  mov     [rcx], ax
0x140012647  test    edi, edi
0x140012649  js      loc_140012A69
0x14001264f  mov     rax, [rbx]
0x140012652  cmp     edi, [rax-0Ch]
0x140012655  jg      loc_140012A69
0x14001265b  mov     rsi, [rsp+98h+lpMem]
0x140012660  mov     rbp, [rsp+98h+arg_0]
0x140012668  mov     [rax-10h], edi
0x14001266b  mov     rcx, [rbx]
0x14001266e  movsxd  rdx, edi
0x140012671  mov     [rcx+rdx*2], r15w
0x140012676  test    rsi, rsi
0x140012679  jz      short loc_1400126A2
0x14001267b  mov     eax, [rsp+98h+var_60]
0x14001267f  test    al, 1
0x140012681  jnz     short loc_1400126A2
0x140012683  shr     eax, 1
0x140012685  and     eax, 3
0x140012688  jnz     loc_140012A52
0x14001268e  call    cs:__imp_GetProcessHeap
0x140012694  mov     r8, rsi; lpMem
0x140012697  xor     edx, edx; dwFlags
0x140012699  mov     rcx, rax; hHeap
0x14001269c  call    cs:__imp_HeapFree
0x1400126a2  mov     rsi, [rsp+98h+arg_10]
0x1400126aa  mov     rax, r12
0x1400126ad  jmp     loc_140012547
0x1400126b2  mov     rcx, [rbp+18h]
0x1400126b6  mov     edx, [rdi+8]
0x1400126b9  mov     rax, [rcx]
0x1400126bc  mov     rax, [rax+10h]
0x1400126c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400126c5  test    al, al
0x1400126c7  jz      short loc_140012676
0x1400126c9  mov     r14d, 8007000Dh
0x1400126cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1400126d6  lea     r13, WPP_GLOBAL_Control
0x1400126dd  cmp     rcx, r13
0x1400126e0  jz      short loc_14001270C
0x1400126e2  test    byte ptr [rcx+1Ch], 20h
0x1400126e6  jz      short loc_14001270C
0x1400126e8  cmp     byte ptr [rcx+19h], 4
0x1400126ec  jb      short loc_14001270C
0x1400126ee  mov     r9d, [rdi+8]
0x1400126f2  lea     r8, WPP_478ffc6658c23ee89d991dcff0807d2d_Traceguids
0x1400126f9  mov     rcx, [rcx+10h]
0x1400126fd  mov     edx, 64h ; 'd'
0x140012702  mov     dword ptr [rsp+98h+var_78], r14d
0x140012707  call    WPP_SF_Dd
0x14001270c  lea     rcx, [rsp+98h+var_60]
0x140012711  call    ??1?$CMFBaseStringT@G@@QEAA@XZ; CMFBaseStringT<ushort>::~CMFBaseStringT<ushort>(void)
0x140012716  mov     r10, cs:WPP_GLOBAL_Control
0x14001271d  cmp     r10, r13
0x140012720  jz      short loc_14001272D
0x140012722  test    byte ptr [r10+1Ch], 2
0x140012727  jnz     loc_140012A85
0x14001272d  mov     r15d, [rsp+98h+arg_8]
0x140012735  test    r14d, r14d
0x140012738  js      loc_140012941
0x14001273e  cmp     r10, r13
0x140012741  jz      short loc_14001275E
0x140012743  test    byte ptr [r10+1Ch], 2
0x140012748  jnz     loc_140012ABA
0x14001274e  cmp     r10, r13
0x140012751  jz      short loc_14001275E
0x140012753  test    byte ptr [r10+1Ch], 2
0x140012758  jnz     loc_140012ADB
0x14001275e  mov     r12, [rsp+98h+var_40]
0x140012763  mov     eax, r14d
0x140012766  add     rsp, 60h
0x14001276a  pop     r15
0x14001276c  pop     r14
0x14001276e  pop     r13
0x140012770  pop     rdi
0x140012771  pop     rsi
0x140012772  pop     rbp
0x140012773  pop     rbx
0x140012774  retn
0x140012775  test    r14, r14
0x140012778  jz      loc_1400129EC
0x14001277e  movzx   eax, word ptr [r14]
0x140012782  mov     [rcx], ax
0x140012785  test    esi, esi
0x140012787  js      loc_140012A69
0x14001278d  mov     rax, [rbx]
0x140012790  cmp     esi, [rax-0Ch]
0x140012793  jg      loc_140012A69
0x140012799  mov     [rax-10h], esi
0x14001279c  xor     eax, eax
0x14001279e  mov     rcx, [rbx]
0x1400127a1  movsxd  rdx, esi
0x1400127a4  mov     [rcx+rdx*2], ax
0x1400127a8  mov     ecx, 1
0x1400127ad  mov     rax, [rbx]
0x1400127b0  mov     rbp, [rdi]
0x1400127b3  mov     rsi, rbp
0x1400127b6  sub     rsi, rax
0x1400127b9  mov     r14d, [rax-10h]
0x1400127bd  sub     ecx, [rax-8]
0x1400127c0  movsxd  r15, dword ptr [rbp-10h]
0x1400127c4  mov     eax, [rax-0Ch]
0x1400127c7  sar     rsi, 1
0x1400127ca  lea     edi, [r15+r14]
0x1400127ce  sub     eax, edi
0x1400127d0  or      ecx, eax
0x1400127d2  jge     short loc_1400127DE
0x1400127d4  mov     edx, edi
0x1400127d6  mov     rcx, rbx
0x1400127d9  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x1400127de  mov     rcx, [rbx]
0x1400127e1  cmp     rsi, r14
0x1400127e4  jbe     loc_1400129F6
0x1400127ea  mov     r8, r15
0x1400127ed  add     r8, r8; Size
0x1400127f0  jz      short loc_140012810
0x1400127f2  lea     rcx, [rcx+r14*2]; void *
0x1400127f6  test    rcx, rcx
0x1400127f9  jz      loc_140012A06
0x1400127ff  test    rbp, rbp
0x140012802  jz      loc_1400129FF
0x140012808  mov     rdx, rbp; Src
0x14001280b  call    memcpy_0
0x140012810  test    edi, edi
0x140012812  js      loc_140012A69
0x140012818  mov     rax, [rbx]
0x14001281b  cmp     edi, [rax-0Ch]
0x14001281e  jg      loc_140012A69
0x140012824  mov     [rax-10h], edi
0x140012827  lea     rsi, asc_1400A3A64; "=\""
0x14001282e  mov     rcx, [rbx]
0x140012831  lea     r14, asc_1400A3A64; "=\""
0x140012838  movsxd  rdx, edi
0x14001283b  xor     r15d, r15d
0x14001283e  mov     [rcx+rdx*2], r15w
0x140012843  mov     ecx, 1
0x140012848  mov     rax, [rbx]
0x14001284b  sub     rsi, rax
0x14001284e  sar     rsi, 1
0x140012851  mov     ebp, [rax-10h]
0x140012854  sub     ecx, [rax-8]
0x140012857  mov     eax, [rax-0Ch]
0x14001285a  lea     edi, [rbp+2]
0x14001285d  sub     eax, edi
0x14001285f  or      ecx, eax
0x140012861  jge     short loc_14001286D
0x140012863  mov     edx, edi
0x140012865  mov     rcx, rbx
0x140012868  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x14001286d  mov     rcx, [rbx]
0x140012870  cmp     rsi, rbp
0x140012873  jbe     loc_140012A1C
0x140012879  lea     rcx, [rcx+rbp*2]
0x14001287d  test    rcx, rcx
0x140012880  jz      loc_140012A29
0x140012886  test    r14, r14
0x140012889  jz      loc_140012A25
0x14001288f  mov     eax, [r14]
0x140012892  mov     [rcx], eax
0x140012894  test    edi, edi
0x140012896  js      loc_140012A69
0x14001289c  mov     rax, [rbx]
0x14001289f  cmp     edi, [rax-0Ch]
0x1400128a2  jg      loc_140012A69
0x1400128a8  mov     r8, [rsp+98h+lpMem]
0x1400128ad  test    r13d, r13d
0x1400128b0  mov     [rax-10h], edi
0x1400128b3  lea     rax, ?m_EmptyString@?$CMFBaseStringT@G@@1QBGB; ushort const near * const CMFBaseStringT<ushort>::m_EmptyString
0x1400128ba  mov     rcx, [rbx]
0x1400128bd  cmovz   r8, rax
0x1400128c1  movsxd  rdx, edi
0x1400128c4  mov     [rcx+rdx*2], r15w
0x1400128c9  mov     rcx, rbx
0x1400128cc  mov     edx, [rsp+98h+arg_18]
0x1400128d3  call    ?WriteEscapedAttributeValue@CDidlLiteObjectWriter@@SAXAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@KPEBG@Z; CDidlLiteObjectWriter::WriteEscapedAttributeValue(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> &,ulong,ushort const *)
0x1400128d8  mov     rax, [rbx]
0x1400128db  lea     rbp, asc_1400A3A6C; "\""
0x1400128e2  sub     rbp, rax
0x1400128e5  lea     rsi, asc_1400A3A6C; "\""
0x1400128ec  mov     ecx, 1
0x1400128f1  sar     rbp, 1
0x1400128f4  mov     r14d, [rax-10h]
0x1400128f8  sub     ecx, [rax-8]
0x1400128fb  mov     eax, [rax-0Ch]
0x1400128fe  lea     edi, [r14+1]
0x140012902  sub     eax, edi
0x140012904  or      ecx, eax
0x140012906  jge     short loc_140012912
0x140012908  mov     edx, edi
0x14001290a  mov     rcx, rbx
0x14001290d  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x140012912  mov     rcx, [rbx]
0x140012915  cmp     rbp, r14
0x140012918  jbe     loc_140012A3F
0x14001291e  lea     rcx, [rcx+r14*2]
0x140012922  test    rcx, rcx
0x140012925  jnz     loc_140012638
0x14001292b  call    cs:__imp__o__errno
0x140012931  mov     dword ptr [rax], 16h
0x140012937  call    _invalid_parameter_noinfo
0x14001293c  jmp     loc_140012647
0x140012941  mov     rax, [rbx]
0x140012944  cmp     [rax-10h], r15d
0x140012948  jbe     loc_14001273E
0x14001294e  mov     edx, r15d
0x140012951  mov     rcx, rbx
0x140012954  call    ?SetLength@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::SetLength(int)
  ... truncated ...
```
