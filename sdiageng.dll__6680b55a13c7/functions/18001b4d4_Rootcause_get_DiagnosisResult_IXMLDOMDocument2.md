# Rootcause::get_DiagnosisResult(IXMLDOMDocument2 *)

- ea: `0x18001b4d4`
- end: `0x18001b9c1`
- name: `?get_DiagnosisResult@Rootcause@@QEAAJPEAUIXMLDOMDocument2@@@Z`
- size: `1261`
- prototype: `__int64 __fastcall(struct _LIST_ENTRY **this, struct IXMLDOMDocument2 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x180015e30`

## callees

- `0x1800012b0`
- `0x18001955c`
- `0x180019d88`
- `0x180019ed8`
- `0x180019f40`
- `0x18001a02c`
- `0x18001aa50`
- `0x18001b4d4`
- `0x180026fa0`
- `0x180027ea4`
- `0x180029882`
- `0x18002a010`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x18001b5aa`
- `KERNEL32!HeapAlloc` at `0x18001b5aa`
- `KERNEL32!GetProcessHeap` at `0x18001b59b`
- `KERNEL32!GetProcessHeap` at `0x18001b59b`

## pseudocode

```c
__int64 __fastcall Rootcause::get_DiagnosisResult(struct _LIST_ENTRY **this, struct IXMLDOMDocument2 *a2)
{
  struct IXMLDOMDocument2 *v2; // r12
  struct IXMLDOMDocument2 *v4; // rsi
  unsigned int v5; // ebx
  int v6; // r8d
  int v7; // r9d
  int FirstInstance; // eax
  struct Rootcause::_SDIAG_ROOTCAUSE_INSTANCE *v9; // r15
  int Instance; // eax
  Rootcause *v11; // rcx
  struct Rootcause::_SDIAG_ROOTCAUSE_INSTANCE *v12; // r13
  HANDLE ProcessHeap; // rax
  struct Rootcause::_SDIAG_ROOTCAUSE_INSTANCE *v14; // rax
  struct Rootcause::_SDIAG_ROOTCAUSE_INSTANCE *v15; // r12
  __int64 v16; // rcx
  void *v17; // rax
  int v18; // eax
  unsigned int v19; // ebx
  __int64 v20; // rdx
  __int64 v21; // rcx
  struct _LIST_ENTRY *v22; // rax
  struct _LIST_ENTRY **p_Flink; // rcx
  __int64 v24; // rcx
  __int64 v25; // rcx
  void *v26; // rax
  int v27; // eax
  unsigned int v28; // ebx
  __int64 v29; // rdx
  __int64 v30; // rcx
  int v31; // r15d
  bool v32; // zf
  unsigned int v33; // r13d
  struct Rootcause::_SDIAG_ROOTCAUSE_INSTANCE *v34; // r15
  int v35; // eax
  int v36; // r8d
  int v37; // eax
  int v38; // r9d
  int v39; // r8d
  int v40; // eax
  int NextInstance; // eax
  struct Rootcause::_SDIAG_ROOTCAUSE_INSTANCE *v43; // [rsp+30h] [rbp-20h] BYREF
  struct Rootcause::_SDIAG_ROOTCAUSE_INSTANCE *v44; // [rsp+38h] [rbp-18h] BYREF
  struct Rootcause::_SDIAG_ROOTCAUSE_INSTANCE *v45; // [rsp+40h] [rbp-10h] BYREF
  int v47; // [rsp+A0h] [rbp+50h]
  struct IXMLDOMDocument2 *v48; // [rsp+A8h] [rbp+58h] BYREF

  v2 = a2;
  v44 = 0;
  v43 = 0;
  v4 = 0;
  v45 = 0;
  v48 = 0;
  if ( !a2 )
  {
    v5 = -2147024809;
    v6 = 640;
    v7 = -2147024809;
LABEL_3:
    SdpDebugTrace(1u, L"Rootcause::get_DiagnosisResult", v6, v7);
    return v5;
  }
  FirstInstance = Rootcause::GetFirstInstance((Rootcause *)this, this[16], &v43);
  v5 = FirstInstance;
  if ( FirstInstance < 0 )
  {
    v7 = FirstInstance;
    v6 = 647;
    goto LABEL_3;
  }
  v9 = v43;
  v47 = 0;
  if ( v43 )
  {
    while ( 1 )
    {
      Instance = Rootcause::GetInstance((Rootcause *)this, this[15], *((wchar_t **)v9 + 2), &v45);
      v5 = Instance;
      if ( Instance < 0 )
      {
        v6 = 656;
        goto LABEL_44;
      }
      v12 = v45;
      if ( v45 )
      {
        if ( *((_DWORD *)v9 + 6) != 1 )
        {
          Instance = Rootcause::FreeInstance(v11, v45);
          v5 = Instance;
          if ( Instance < 0 )
          {
            v6 = 703;
            goto LABEL_44;
          }
          Instance = Rootcause::PopulateInstance(
                       v24,
                       *((_QWORD *)v9 + 2),
                       *((unsigned int *)v9 + 6),
                       *((_QWORD *)v9 + 4),
                       *((_QWORD *)v9 + 5),
                       v12);
          v5 = Instance;
          if ( Instance < 0 )
          {
            v6 = 710;
            goto LABEL_44;
          }
          v25 = *((_QWORD *)v9 + 6);
          *((_QWORD *)v12 + 6) = v25;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 8LL))(v25);
          v26 = operator new[](saturated_mul(*((unsigned int *)this + 8), 0x10u));
          *((_QWORD *)v12 + 7) = v26;
          if ( !v26 )
          {
            v7 = -2147024882;
            v6 = 716;
            v5 = -2147024882;
            goto LABEL_3;
          }
          v27 = *((_DWORD *)this + 8);
          v28 = 0;
          for ( *((_DWORD *)v12 + 16) = v27; v28 < *((_DWORD *)v12 + 16); ++v28 )
          {
            v29 = 2LL * v28;
            *(_DWORD *)(*((_QWORD *)v12 + 7) + 8 * v29) = *(_DWORD *)(*((_QWORD *)v9 + 7) + 16LL * v28);
            *(_QWORD *)(*((_QWORD *)v12 + 7) + 8 * v29 + 8) = *(_QWORD *)(*((_QWORD *)v9 + 7) + 16LL * v28 + 8);
            v30 = *(_QWORD *)(*((_QWORD *)v12 + 7) + 16LL * v28 + 8);
            if ( v30 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 8LL))(v30);
          }
        }
      }
      else
      {
        ProcessHeap = GetProcessHeap();
        v14 = (struct Rootcause::_SDIAG_ROOTCAUSE_INSTANCE *)HeapAlloc(ProcessHeap, 0, 0x48u);
        v45 = v14;
        v15 = v14;
        if ( !v14 )
        {
          v7 = -2147024882;
          v6 = 665;
          v5 = -2147024882;
          goto LABEL_3;
        }
        memset_0(v14, 0, 0x48u);
        Instance = Rootcause::PopulateInstance(
                     *((_QWORD *)v9 + 5),
                     *((_QWORD *)v9 + 2),
                     *((unsigned int *)v9 + 6),
                     *((_QWORD *)v9 + 4),
                     *((_QWORD *)v9 + 5),
                     v15);
        v5 = Instance;
        if ( Instance < 0 )
        {
          v6 = 674;
          goto LABEL_44;
        }
        v16 = *((_QWORD *)v9 + 6);
        *((_QWORD *)v15 + 6) = v16;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 8LL))(v16);
        v17 = operator new[](saturated_mul(*((unsigned int *)this + 8), 0x10u));
        *((_QWORD *)v15 + 7) = v17;
        if ( !v17 )
        {
          v7 = -2147024882;
          v6 = 680;
          v5 = -2147024882;
          goto LABEL_3;
        }
        v18 = *((_DWORD *)this + 8);
        v19 = 0;
        for ( *((_DWORD *)v15 + 16) = v18; v19 < *((_DWORD *)v15 + 16); ++v19 )
        {
          v20 = 2LL * v19;
          *(_DWORD *)(*((_QWORD *)v15 + 7) + 8 * v20) = *(_DWORD *)(*((_QWORD *)v9 + 7) + 16LL * v19);
          *(_QWORD *)(*((_QWORD *)v15 + 7) + 8 * v20 + 8) = *(_QWORD *)(*((_QWORD *)v9 + 7) + 16LL * v19 + 8);
          v21 = *(_QWORD *)(*((_QWORD *)v15 + 7) + 16LL * v19 + 8);
          if ( v21 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 8LL))(v21);
        }
        v22 = this[15];
        p_Flink = &v22->Blink->Flink;
        if ( *p_Flink != v22 )
          __fastfail(3u);
        *(_QWORD *)v15 = v22;
        *((_QWORD *)v15 + 1) = p_Flink;
        *p_Flink = (struct _LIST_ENTRY *)v15;
        v22->Blink = (struct _LIST_ENTRY *)v15;
      }
      Instance = Rootcause::GetFirstInstance((Rootcause *)this, this[16], &v43);
      v5 = Instance;
      if ( Instance < 0 )
      {
        v6 = 736;
        goto LABEL_44;
      }
      v31 = 0;
      v32 = v47 == -1;
      v33 = ++v47;
      if ( !v32 )
        break;
LABEL_30:
      v9 = v43;
      if ( !v43 )
      {
        v2 = a2;
        goto LABEL_32;
      }
    }
    while ( 1 )
    {
      Instance = Rootcause::GetNextInstance((Rootcause *)this, this[16], &v43);
      v5 = Instance;
      if ( Instance < 0 )
        break;
      if ( ++v31 >= v33 )
        goto LABEL_30;
    }
    v6 = 740;
    goto LABEL_44;
  }
LABEL_32:
  Instance = Rootcause::GetFirstInstance((Rootcause *)this, this[15], &v44);
  v5 = Instance;
  if ( Instance < 0 )
  {
    v6 = 751;
LABEL_44:
    v7 = Instance;
    goto LABEL_3;
  }
  v34 = v44;
  if ( v44 )
  {
    while ( 1 )
    {
      if ( v4 )
      {
        ((void (__fastcall *)(struct IXMLDOMDocument2 *))v4->lpVtbl->Release)(v4);
        v4 = 0;
        v48 = 0;
      }
      if ( !*((_DWORD *)v34 + 6) )
        break;
      v35 = Rootcause::BuildResultXml((Rootcause *)this, v34, &v48);
      v5 = v35;
      if ( v35 < 0 )
      {
        v36 = 772;
        goto LABEL_48;
      }
      v4 = v48;
      v40 = SdpXmlAppend(v2, 0, v48);
      v5 = v40;
      if ( v40 < 0 )
      {
        v38 = v40;
        v39 = 775;
        goto LABEL_63;
      }
      NextInstance = Rootcause::GetNextInstance((Rootcause *)this, this[15], &v44);
      v5 = NextInstance;
      if ( NextInstance < 0 )
      {
        v38 = NextInstance;
        v39 = 778;
        goto LABEL_63;
      }
      v34 = v44;
      if ( !v44 )
        goto LABEL_64;
    }
    v5 = -2143551221;
    v39 = 768;
    v38 = -2143551221;
    goto LABEL_63;
  }
  v35 = Rootcause::BuildResultXml((Rootcause *)this, 0, &v48);
  v5 = v35;
  if ( v35 < 0 )
  {
    v36 = 755;
LABEL_48:
    SdpDebugTrace(1u, L"Rootcause::get_DiagnosisResult", v36, v35);
    v4 = v48;
    goto LABEL_64;
  }
  v4 = v48;
  v37 = SdpXmlAppend(v2, 0, v48);
  v5 = v37;
  if ( v37 < 0 )
  {
    v38 = v37;
    v39 = 758;
LABEL_63:
    SdpDebugTrace(1u, L"Rootcause::get_DiagnosisResult", v39, v38);
  }
LABEL_64:
  if ( v4 )
    ((void (__fastcall *)(struct IXMLDOMDocument2 *))v4->lpVtbl->Release)(v4);
  return v5;
}

```

## disassembly

```asm
0x18001b4d4  mov     [rsp-38h+arg_0], rbx
0x18001b4d9  mov     [rsp-38h+arg_8], rdx
0x18001b4de  push    rbp
0x18001b4df  push    rsi
0x18001b4e0  push    rdi
0x18001b4e1  push    r12
0x18001b4e3  push    r13
0x18001b4e5  push    r14
0x18001b4e7  push    r15
0x18001b4e9  mov     rbp, rsp
0x18001b4ec  sub     rsp, 50h
0x18001b4f0  xor     r13d, r13d
0x18001b4f3  mov     r12, rdx
0x18001b4f6  mov     [rbp+var_18], r13
0x18001b4fa  mov     r14, rcx
0x18001b4fd  mov     [rbp+var_20], r13
0x18001b501  mov     esi, r13d
0x18001b504  mov     [rbp+var_10], r13
0x18001b508  mov     [rbp+arg_18], r13
0x18001b50c  test    rdx, rdx
0x18001b50f  jnz     short loc_18001B535
0x18001b511  mov     ebx, 80070057h
0x18001b516  mov     r8d, 280h; int
0x18001b51c  mov     r9d, ebx; int
0x18001b51f  mov     ecx, 1; Level
0x18001b524  lea     rdx, aRootcauseGetDi; "Rootcause::get_DiagnosisResult"
0x18001b52b  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18001b530  jmp     loc_18001B9A7
0x18001b535  mov     rdx, [rcx+80h]; struct _LIST_ENTRY *
0x18001b53c  lea     r8, [rbp+var_20]; struct Rootcause::_SDIAG_ROOTCAUSE_INSTANCE **
0x18001b540  call    ?GetFirstInstance@Rootcause@@AEAAJPEAU_LIST_ENTRY@@PEAPEAU_SDIAG_ROOTCAUSE_INSTANCE@1@@Z; Rootcause::GetFirstInstance(_LIST_ENTRY *,Rootcause::_SDIAG_ROOTCAUSE_INSTANCE * *)
0x18001b545  mov     ebx, eax
0x18001b547  test    eax, eax
0x18001b549  jns     short loc_18001B556
0x18001b54b  mov     r9d, eax
0x18001b54e  mov     r8d, 287h
0x18001b554  jmp     short loc_18001B51F
0x18001b556  mov     r15, [rbp+var_20]
0x18001b55a  mov     edi, 1
0x18001b55f  mov     [rbp+arg_10], r13d
0x18001b563  test    r15, r15
0x18001b566  jz      loc_18001B7F2
0x18001b56c  or      r12, 0FFFFFFFFFFFFFFFFh
0x18001b570  mov     r8, [r15+10h]; String1
0x18001b574  lea     r9, [rbp+var_10]; struct Rootcause::_SDIAG_ROOTCAUSE_INSTANCE **
0x18001b578  mov     rdx, [r14+78h]; struct _LIST_ENTRY *
0x18001b57c  mov     rcx, r14; this
0x18001b57f  call    ?GetInstance@Rootcause@@AEAAJPEAU_LIST_ENTRY@@PEBGPEAPEAU_SDIAG_ROOTCAUSE_INSTANCE@1@@Z; Rootcause::GetInstance(_LIST_ENTRY *,ushort const *,Rootcause::_SDIAG_ROOTCAUSE_INSTANCE * *)
0x18001b584  mov     ebx, eax
0x18001b586  test    eax, eax
0x18001b588  js      loc_18001B872
0x18001b58e  mov     r13, [rbp+var_10]
0x18001b592  test    r13, r13
0x18001b595  jnz     loc_18001B6B9
0x18001b59b  call    cs:__imp_GetProcessHeap
0x18001b5a1  xor     edx, edx; dwFlags
0x18001b5a3  lea     r8d, [r13+48h]; dwBytes
0x18001b5a7  mov     rcx, rax; hHeap
0x18001b5aa  call    cs:__imp_HeapAlloc
0x18001b5b0  mov     [rbp+var_10], rax
0x18001b5b4  mov     r12, rax
0x18001b5b7  test    rax, rax
0x18001b5ba  jz      loc_18001B830
0x18001b5c0  xor     edx, edx; Val
0x18001b5c2  lea     r8d, [r13+48h]; Size
0x18001b5c6  mov     rcx, rax; void *
0x18001b5c9  call    memset_0
0x18001b5ce  mov     rcx, [r15+28h]
0x18001b5d2  mov     r9, [r15+20h]
0x18001b5d6  mov     r8d, [r15+18h]
0x18001b5da  mov     rdx, [r15+10h]
0x18001b5de  mov     [rsp+50h+var_28], r12
0x18001b5e3  mov     [rsp+50h+var_30], rcx
0x18001b5e8  call    ?PopulateInstance@Rootcause@@AEAAJPEBGW4SDIAG_ROOTCAUSE_STATUS@1@PEAUtagSAFEARRAY@@2PEAU_SDIAG_ROOTCAUSE_INSTANCE@1@@Z; Rootcause::PopulateInstance(ushort const *,Rootcause::SDIAG_ROOTCAUSE_STATUS,tagSAFEARRAY *,tagSAFEARRAY *,Rootcause::_SDIAG_ROOTCAUSE_INSTANCE *)
0x18001b5ed  mov     ebx, eax
0x18001b5ef  test    eax, eax
0x18001b5f1  js      loc_18001B828
0x18001b5f7  mov     rcx, [r15+30h]
0x18001b5fb  mov     [r12+30h], rcx
0x18001b600  mov     rax, [rcx]
0x18001b603  mov     rax, [rax+8]
0x18001b607  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b60c  mov     ecx, [r14+20h]
0x18001b610  lea     eax, [r13+10h]
0x18001b614  mul     rcx
0x18001b617  lea     rcx, [r13-1]
0x18001b61b  cmovb   rax, rcx
0x18001b61f  mov     rcx, rax; unsigned __int64
0x18001b622  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18001b627  mov     [r12+38h], rax
0x18001b62c  test    rax, rax
0x18001b62f  jz      loc_18001B817
0x18001b635  mov     eax, [r14+20h]
0x18001b639  xor     ebx, ebx
0x18001b63b  mov     [r12+40h], eax
0x18001b640  test    eax, eax
0x18001b642  jz      short loc_18001B68F
0x18001b644  mov     rax, [r15+38h]
0x18001b648  mov     rcx, [r12+38h]
0x18001b64d  mov     edx, ebx
0x18001b64f  add     rdx, rdx
0x18001b652  mov     eax, [rax+rdx*8]
0x18001b655  mov     [rcx+rdx*8], eax
0x18001b658  mov     rax, [r15+38h]
0x18001b65c  mov     rcx, [r12+38h]
0x18001b661  mov     rax, [rax+rdx*8+8]
0x18001b666  mov     [rcx+rdx*8+8], rax
0x18001b66b  mov     rax, [r12+38h]
0x18001b670  mov     rcx, [rax+rdx*8+8]
0x18001b675  test    rcx, rcx
0x18001b678  jz      short loc_18001B686
0x18001b67a  mov     rax, [rcx]
0x18001b67d  mov     rax, [rax+8]
0x18001b681  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b686  add     ebx, edi
0x18001b688  cmp     ebx, [r12+40h]
0x18001b68d  jb      short loc_18001B644
0x18001b68f  mov     rax, [r14+78h]
0x18001b693  mov     rcx, [rax+8]
0x18001b697  cmp     [rcx], rax
0x18001b69a  jnz     loc_18001B810
0x18001b6a0  mov     [r12], rax
0x18001b6a4  mov     [r12+8], rcx
0x18001b6a9  mov     [rcx], r12
0x18001b6ac  mov     [rax+8], r12
0x18001b6b0  or      r12, 0FFFFFFFFFFFFFFFFh
0x18001b6b4  jmp     loc_18001B78C
0x18001b6b9  cmp     [r15+18h], edi
0x18001b6bd  jz      loc_18001B78C
0x18001b6c3  mov     rdx, r13; struct Rootcause::_SDIAG_ROOTCAUSE_INSTANCE *
0x18001b6c6  call    ?FreeInstance@Rootcause@@AEAAJPEAU_SDIAG_ROOTCAUSE_INSTANCE@1@@Z; Rootcause::FreeInstance(Rootcause::_SDIAG_ROOTCAUSE_INSTANCE *)
0x18001b6cb  mov     ebx, eax
0x18001b6cd  test    eax, eax
0x18001b6cf  js      loc_18001B85A
0x18001b6d5  mov     rax, [r15+28h]
0x18001b6d9  mov     r9, [r15+20h]
0x18001b6dd  mov     r8d, [r15+18h]
0x18001b6e1  mov     rdx, [r15+10h]
0x18001b6e5  mov     [rsp+50h+var_28], r13
0x18001b6ea  mov     [rsp+50h+var_30], rax
0x18001b6ef  call    ?PopulateInstance@Rootcause@@AEAAJPEBGW4SDIAG_ROOTCAUSE_STATUS@1@PEAUtagSAFEARRAY@@2PEAU_SDIAG_ROOTCAUSE_INSTANCE@1@@Z; Rootcause::PopulateInstance(ushort const *,Rootcause::SDIAG_ROOTCAUSE_STATUS,tagSAFEARRAY *,tagSAFEARRAY *,Rootcause::_SDIAG_ROOTCAUSE_INSTANCE *)
0x18001b6f4  mov     ebx, eax
0x18001b6f6  test    eax, eax
0x18001b6f8  js      loc_18001B852
0x18001b6fe  mov     rcx, [r15+30h]
0x18001b702  mov     [r13+30h], rcx
0x18001b706  mov     rax, [rcx]
0x18001b709  mov     rax, [rax+8]
0x18001b70d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b712  mov     ecx, [r14+20h]
0x18001b716  mov     eax, 10h
0x18001b71b  mul     rcx
0x18001b71e  cmovb   rax, r12
0x18001b722  mov     rcx, rax; unsigned __int64
0x18001b725  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18001b72a  mov     [r13+38h], rax
0x18001b72e  test    rax, rax
0x18001b731  jz      loc_18001B841
0x18001b737  mov     eax, [r14+20h]
0x18001b73b  xor     ebx, ebx
0x18001b73d  mov     [r13+40h], eax
0x18001b741  test    eax, eax
0x18001b743  jz      short loc_18001B78C
0x18001b745  mov     rax, [r15+38h]
0x18001b749  mov     rcx, [r13+38h]
0x18001b74d  mov     edx, ebx
0x18001b74f  add     rdx, rdx
0x18001b752  mov     eax, [rax+rdx*8]
0x18001b755  mov     [rcx+rdx*8], eax
0x18001b758  mov     rax, [r15+38h]
0x18001b75c  mov     rcx, [r13+38h]
0x18001b760  mov     rax, [rax+rdx*8+8]
0x18001b765  mov     [rcx+rdx*8+8], rax
0x18001b76a  mov     rax, [r13+38h]
0x18001b76e  mov     rcx, [rax+rdx*8+8]
0x18001b773  test    rcx, rcx
0x18001b776  jz      short loc_18001B784
0x18001b778  mov     rax, [rcx]
0x18001b77b  mov     rax, [rax+8]
0x18001b77f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b784  add     ebx, edi
0x18001b786  cmp     ebx, [r13+40h]
0x18001b78a  jb      short loc_18001B745
0x18001b78c  mov     rdx, [r14+80h]; struct _LIST_ENTRY *
0x18001b793  lea     r8, [rbp+var_20]; struct Rootcause::_SDIAG_ROOTCAUSE_INSTANCE **
0x18001b797  mov     rcx, r14; this
0x18001b79a  call    ?GetFirstInstance@Rootcause@@AEAAJPEAU_LIST_ENTRY@@PEAPEAU_SDIAG_ROOTCAUSE_INSTANCE@1@@Z; Rootcause::GetFirstInstance(_LIST_ENTRY *,Rootcause::_SDIAG_ROOTCAUSE_INSTANCE * *)
0x18001b79f  mov     ebx, eax
0x18001b7a1  test    eax, eax
0x18001b7a3  js      loc_18001B86A
0x18001b7a9  mov     r13d, [rbp+arg_10]
0x18001b7ad  mov     r15d, esi
0x18001b7b0  add     r13d, edi
0x18001b7b3  mov     [rbp+arg_10], r13d
0x18001b7b7  jz      short loc_18001B7DE
0x18001b7b9  mov     rdx, [r14+80h]; struct _LIST_ENTRY *
0x18001b7c0  lea     r8, [rbp+var_20]; struct Rootcause::_SDIAG_ROOTCAUSE_INSTANCE **
0x18001b7c4  mov     rcx, r14; this
0x18001b7c7  call    ?GetNextInstance@Rootcause@@AEAAJPEAU_LIST_ENTRY@@PEAPEAU_SDIAG_ROOTCAUSE_INSTANCE@1@@Z; Rootcause::GetNextInstance(_LIST_ENTRY *,Rootcause::_SDIAG_ROOTCAUSE_INSTANCE * *)
0x18001b7cc  mov     ebx, eax
0x18001b7ce  test    eax, eax
0x18001b7d0  js      loc_18001B862
0x18001b7d6  add     r15d, edi
0x18001b7d9  cmp     r15d, r13d
0x18001b7dc  jb      short loc_18001B7B9
0x18001b7de  mov     r15, [rbp+var_20]
0x18001b7e2  xor     r13d, r13d
0x18001b7e5  test    r15, r15
0x18001b7e8  jnz     loc_18001B570
0x18001b7ee  mov     r12, [rbp+arg_8]
0x18001b7f2  mov     rdx, [r14+78h]; struct _LIST_ENTRY *
0x18001b7f6  lea     r8, [rbp+var_18]; struct Rootcause::_SDIAG_ROOTCAUSE_INSTANCE **
0x18001b7fa  mov     rcx, r14; this
0x18001b7fd  call    ?GetFirstInstance@Rootcause@@AEAAJPEAU_LIST_ENTRY@@PEAPEAU_SDIAG_ROOTCAUSE_INSTANCE@1@@Z; Rootcause::GetFirstInstance(_LIST_ENTRY *,Rootcause::_SDIAG_ROOTCAUSE_INSTANCE * *)
0x18001b802  mov     ebx, eax
0x18001b804  test    eax, eax
0x18001b806  jns     short loc_18001B882
0x18001b808  mov     r8d, 2EFh
0x18001b80e  jmp     short loc_18001B878
0x18001b810  mov     ecx, 3
0x18001b815  int     29h; Win8: RtlFailFast(ecx)
0x18001b817  mov     r9d, 8007000Eh
0x18001b81d  mov     r8d, 2A8h
0x18001b823  mov     ebx, r9d
0x18001b826  jmp     short loc_18001B87B
0x18001b828  mov     r8d, 2A2h
0x18001b82e  jmp     short loc_18001B878
0x18001b830  mov     r9d, 8007000Eh
0x18001b836  mov     r8d, 299h
0x18001b83c  mov     ebx, r9d
0x18001b83f  jmp     short loc_18001B87B
0x18001b841  mov     r9d, 8007000Eh
0x18001b847  mov     r8d, 2CCh
0x18001b84d  mov     ebx, r9d
0x18001b850  jmp     short loc_18001B87B
0x18001b852  mov     r8d, 2C6h
0x18001b858  jmp     short loc_18001B878
0x18001b85a  mov     r8d, 2BFh
0x18001b860  jmp     short loc_18001B878
0x18001b862  mov     r8d, 2E4h
0x18001b868  jmp     short loc_18001B878
0x18001b86a  mov     r8d, 2E0h
0x18001b870  jmp     short loc_18001B878
0x18001b872  mov     r8d, 290h
0x18001b878  mov     r9d, eax
0x18001b87b  mov     ecx, edi
0x18001b87d  jmp     loc_18001B524
0x18001b882  mov     r15, [rbp+var_18]
0x18001b886  test    r15, r15
0x18001b889  jnz     short loc_18001B8E8
0x18001b88b  lea     r8, [rbp+arg_18]; struct IXMLDOMDocument2 **
0x18001b88f  xor     edx, edx; struct Rootcause::_SDIAG_ROOTCAUSE_INSTANCE *
0x18001b891  mov     rcx, r14; this
0x18001b894  call    ?BuildResultXml@Rootcause@@AEAAJPEAU_SDIAG_ROOTCAUSE_INSTANCE@1@PEAPEAUIXMLDOMDocument2@@@Z; Rootcause::BuildResultXml(Rootcause::_SDIAG_ROOTCAUSE_INSTANCE *,IXMLDOMDocument2 * *)
0x18001b899  mov     ebx, eax
0x18001b89b  test    eax, eax
0x18001b89d  jns     short loc_18001B8BF
0x18001b89f  mov     r8d, 2F3h; int
0x18001b8a5  mov     r9d, eax; int
0x18001b8a8  lea     rdx, aRootcauseGetDi; "Rootcause::get_DiagnosisResult"
0x18001b8af  mov     ecx, edi; Level
0x18001b8b1  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18001b8b6  mov     rsi, [rbp+arg_18]
0x18001b8ba  jmp     loc_18001B993
0x18001b8bf  mov     rsi, [rbp+arg_18]
0x18001b8c3  xor     edx, edx; struct IXMLDOMElement *
0x18001b8c5  mov     r8, rsi; struct IXMLDOMDocument2 *
0x18001b8c8  mov     rcx, r12; struct IXMLDOMDocument2 *
0x18001b8cb  call    ?SdpXmlAppend@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMElement@@0@Z; SdpXmlAppend(IXMLDOMDocument2 *,IXMLDOMElement *,IXMLDOMDocument2 *)
0x18001b8d0  mov     ebx, eax
0x18001b8d2  test    eax, eax
0x18001b8d4  jns     loc_18001B993
0x18001b8da  mov     r9d, eax
0x18001b8dd  mov     r8d, 2F6h
0x18001b8e3  jmp     loc_18001B985
0x18001b8e8  test    rsi, rsi
0x18001b8eb  jz      short loc_18001B903
0x18001b8ed  mov     rax, [rsi]
0x18001b8f0  mov     rcx, rsi
0x18001b8f3  mov     rax, [rax+10h]
0x18001b8f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b8fc  mov     rsi, r13
0x18001b8ff  mov     [rbp+arg_18], r13
0x18001b903  cmp     [r15+18h], r13d
0x18001b907  jz      short loc_18001B977
0x18001b909  lea     r8, [rbp+arg_18]; struct IXMLDOMDocument2 **
0x18001b90d  mov     rdx, r15; struct Rootcause::_SDIAG_ROOTCAUSE_INSTANCE *
0x18001b910  mov     rcx, r14; this
0x18001b913  call    ?BuildResultXml@Rootcause@@AEAAJPEAU_SDIAG_ROOTCAUSE_INSTANCE@1@PEAPEAUIXMLDOMDocument2@@@Z; Rootcause::BuildResultXml(Rootcause::_SDIAG_ROOTCAUSE_INSTANCE *,IXMLDOMDocument2 * *)
0x18001b918  mov     ebx, eax
0x18001b91a  test    eax, eax
0x18001b91c  js      short loc_18001B96C
0x18001b91e  mov     rsi, [rbp+arg_18]
0x18001b922  xor     edx, edx; struct IXMLDOMElement *
0x18001b924  mov     r8, rsi; struct IXMLDOMDocument2 *
0x18001b927  mov     rcx, r12; struct IXMLDOMDocument2 *
0x18001b92a  call    ?SdpXmlAppend@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMElement@@0@Z; SdpXmlAppend(IXMLDOMDocument2 *,IXMLDOMElement *,IXMLDOMDocument2 *)
0x18001b92f  mov     ebx, eax
0x18001b931  test    eax, eax
0x18001b933  js      short loc_18001B961
  ... truncated ...
```
