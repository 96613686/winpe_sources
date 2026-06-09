# CDlpActionLayoutUsb::InitializeRoutine(void *,ulong)

- ea: `0x18001dda0`
- end: `0x18001f069`
- name: `?InitializeRoutine@CDlpActionLayoutUsb@@EEAAJPEAXK@Z`
- size: `4809`
- prototype: `__int64 __fastcall(CDlpActionLayoutUsb *__hidden this, void *, unsigned int)`
- caller_count: `0`
- callee_count: `15`
- tags: `registry_config, installer_update`

## callees

- `0x180002898`
- `0x180007bbc`
- `0x18000aba4`
- `0x18000ea20`
- `0x180012f5c`
- `0x18001ce28`
- `0x18001dda0`
- `0x18001fd60`
- `0x180020cb4`
- `0x180021484`
- `0x1800239e0`
- `0x180023f44`
- `0x18007ec76`
- `0x18007ed40`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001ea45`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001eb32`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001ea45`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001eb32`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001ea54`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001eb41`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001ea54`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001eb41`

## string_xrefs

- `0x18001e48a`: `LayoutUsb: Initializing Boot WIM Path: [%s]`
- `0x18001e4b0`: `LayoutUsb: Initializing Install WIM Path: [%s]`
- `0x18001e4e6`: `LayoutUsb: Initializing Customization WIM Path: [%s]`
- `0x18001e50e`: `LayoutUsb: Initializing OEM Winre WIM Path: [%s]`
- `0x18001e554`: `LayoutUsb: Initializing Reconstruction Path Count: [%u]`
- `0x18001e58a`: `LayoutUsb: Initializing Reconstruction Path: [%s]`
- `0x18001e5c3`: `LayoutUsb: Initializing Customizations Directory: [%s]`
- `0x18001e5e9`: `LayoutUsb: Initializing OEM Extensibility Directory: [%s]`
- `0x18001e60f`: `LayoutUsb: Initializing OEM AutoApply Directory: [%s]`
- `0x18001e635`: `LayoutUsb: Initializing Cloud data Directory: [%s]`
- `0x18001ee10`: `sources\install.swm`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CDlpActionLayoutUsb::InitializeRoutine(CDlpActionLayoutUsb *this, void *a2, int a3)
{
  unsigned int v6; // r13d
  int v7; // edi
  __int64 v8; // rcx
  int v9; // eax
  __int64 v10; // rbx
  unsigned __int16 *v11; // rax
  __int64 v12; // rdi
  unsigned int v13; // ecx
  void *v14; // rdx
  void *v15; // r8
  void *v16; // r9
  unsigned int v17; // r10d
  _QWORD *v18; // r11
  unsigned __int16 v19; // r12
  unsigned int v20; // r15d
  void *v21; // r14
  unsigned int v22; // r15d
  unsigned __int16 *v23; // r14
  _QWORD *v24; // rax
  const wchar_t *v25; // rax
  __int64 v26; // rcx
  int *v27; // r15
  int *v28; // r9
  __int64 v29; // rcx
  int *v30; // r9
  __int64 v31; // rcx
  unsigned __int16 *v32; // r9
  __int64 v33; // rcx
  int *v34; // r9
  __int64 v35; // rcx
  int *v36; // r9
  __int64 v37; // rcx
  int v38; // r14d
  __int64 v39; // rcx
  int *v40; // r9
  __int64 v41; // rcx
  int *v42; // r9
  __int64 v43; // rcx
  int *v44; // r9
  __int64 v45; // rcx
  int *v46; // r9
  __int64 v47; // rcx
  unsigned __int16 v48; // ax
  __int64 v49; // rcx
  __int64 v50; // rcx
  unsigned int v51; // r14d
  __int64 v52; // rcx
  __int64 v53; // rcx
  __int64 v54; // rcx
  __int64 v55; // rcx
  unsigned int v56; // r15d
  const wchar_t *v57; // r9
  void *v58; // r15
  int StringCch; // eax
  unsigned __int16 *v60; // rbx
  int Internal; // eax
  unsigned __int16 *v62; // r13
  int v63; // eax
  void *v64; // r14
  int v65; // eax
  unsigned int v66; // edx
  void *v67; // r14
  int v68; // eax
  int v69; // r14d
  unsigned int v70; // r12d
  char *v71; // rbx
  _WORD *v72; // r15
  unsigned int v73; // edx
  int v74; // eax
  int v75; // eax
  int v76; // eax
  char *v77; // rbx
  HANDLE ProcessHeap; // rax
  void *v79; // r14
  int v80; // eax
  __int64 v81; // rcx
  int v82; // eax
  __int64 v83; // rcx
  HANDLE v84; // rax
  __int64 v85; // rcx
  __int64 v86; // rcx
  int v87; // eax
  __int64 v88; // rcx
  void *v89; // r14
  int v90; // eax
  void *v91; // r14
  int v92; // eax
  void *v93; // r14
  int v94; // eax
  unsigned __int16 *v95; // r12
  int v96; // eax
  void *v97; // r14
  int v98; // eax
  int v99; // eax
  int v100; // eax
  int v101; // eax
  int v102; // eax
  int v103; // eax
  int v104; // eax
  int v105; // eax
  int v106; // eax
  int v107; // eax
  int v108; // eax
  int v109; // eax
  int v110; // eax
  int v112; // [rsp+20h] [rbp-89h]
  int v113; // [rsp+28h] [rbp-81h]
  unsigned int v114; // [rsp+30h] [rbp-79h] BYREF
  unsigned int v115; // [rsp+34h] [rbp-75h]
  unsigned int v116; // [rsp+38h] [rbp-71h]
  void *v117; // [rsp+40h] [rbp-69h] BYREF
  unsigned __int16 *v118; // [rsp+48h] [rbp-61h]
  unsigned __int16 *v119; // [rsp+50h] [rbp-59h]
  void *v120; // [rsp+58h] [rbp-51h]
  void *v121; // [rsp+60h] [rbp-49h]
  void *v122; // [rsp+68h] [rbp-41h]
  void *v123; // [rsp+70h] [rbp-39h]
  unsigned __int16 *v124; // [rsp+78h] [rbp-31h]
  void *v125; // [rsp+80h] [rbp-29h]
  void *v126; // [rsp+88h] [rbp-21h]
  void *v127; // [rsp+90h] [rbp-19h]
  _QWORD *v128; // [rsp+98h] [rbp-11h]
  void *Src; // [rsp+A0h] [rbp-9h]
  const wchar_t *v130; // [rsp+A8h] [rbp-1h]
  __int128 Buf2; // [rsp+B0h] [rbp+7h] BYREF

  Buf2 = 0;
  v6 = 0;
  if ( !a2 )
  {
    v7 = -2147024809;
    v8 = *((_QWORD *)this + 11);
    if ( !v8 )
      goto LABEL_302;
    v113 = -2147024809;
    v112 = 455;
    goto LABEL_299;
  }
  v9 = (*(__int64 (__fastcall **)(CDlpActionLayoutUsb *, __int128 *))(*(_QWORD *)this + 56LL))(this, &Buf2);
  v7 = v9;
  if ( v9 < 0 )
  {
    v8 = *((_QWORD *)this + 11);
    if ( !v8 )
      goto LABEL_302;
    v113 = v9;
    v112 = 487;
    goto LABEL_299;
  }
  Src = 0;
  v119 = 0;
  v117 = 0;
  v127 = 0;
  v126 = 0;
  v115 = 0;
  v120 = 0;
  v121 = 0;
  v122 = 0;
  v123 = 0;
  if ( !memcmp_0(&WINDLP_ACTION_LAYOUTUSB, &Buf2, 0x10u) )
  {
    if ( a3 != 80 )
    {
      v7 = -2147024809;
      v8 = *((_QWORD *)this + 11);
      if ( !v8 )
        goto LABEL_302;
      v113 = -2147024809;
      v112 = 490;
      goto LABEL_299;
    }
    if ( WINDLP_ACTION_LAYOUTUSB != *(_OWORD *)a2 )
    {
      v7 = -2147024809;
      v8 = *((_QWORD *)this + 11);
      if ( !v8 )
        goto LABEL_302;
      v113 = -2147024809;
      v112 = 495;
      goto LABEL_299;
    }
    v124 = (unsigned __int16 *)*((_QWORD *)a2 + 2);
    if ( !v124 )
    {
      v7 = -2147024809;
      v8 = *((_QWORD *)this + 11);
      if ( !v8 )
        goto LABEL_302;
      v113 = -2147024809;
      v112 = 499;
      goto LABEL_299;
    }
    v125 = (void *)*((_QWORD *)a2 + 5);
    v10 = *((_QWORD *)a2 + 6);
    v11 = (unsigned __int16 *)*((_QWORD *)a2 + 7);
    v12 = *((_QWORD *)a2 + 8);
    v13 = *((_DWORD *)a2 + 18);
    v14 = v127;
    v15 = v127;
    v16 = v127;
    v17 = (unsigned int)v127;
    v18 = v127;
LABEL_41:
    v6 = *((_DWORD *)a2 + 7);
    v20 = *((_DWORD *)a2 + 8);
    v19 = *((_WORD *)a2 + 12);
    v21 = v125;
    v118 = v11;
    goto LABEL_42;
  }
  v19 = 0;
  v124 = 0;
  v10 = 0;
  v12 = 0;
  v114 = 0;
  if ( memcmp_0(&WINDLP_ACTION_RECOVEROEM, &Buf2, 0x10u) )
  {
    if ( memcmp_0(&WINDLP_ACTION_RECOVERUSB, &Buf2, 0x10u) )
    {
      v23 = 0;
      v118 = 0;
      v125 = 0;
      v24 = 0;
      v22 = 0;
      v116 = 0;
      goto LABEL_54;
    }
    if ( a3 != 152 )
    {
      v7 = -2147024809;
      v8 = *((_QWORD *)this + 11);
      if ( !v8 )
        goto LABEL_302;
      v113 = -2147024809;
      v112 = 537;
      goto LABEL_299;
    }
    if ( WINDLP_ACTION_RECOVERUSB != *(_OWORD *)a2 )
    {
      v7 = -2147024809;
      v8 = *((_QWORD *)this + 11);
      if ( !v8 )
        goto LABEL_302;
      v113 = -2147024809;
      v112 = 542;
      goto LABEL_299;
    }
    v16 = (void *)*((_QWORD *)a2 + 2);
    if ( !v16 )
    {
      v7 = -2147024809;
      v8 = *((_QWORD *)this + 11);
      if ( !v8 )
        goto LABEL_302;
      v113 = -2147024809;
      v112 = 546;
      goto LABEL_299;
    }
    v11 = (unsigned __int16 *)*((_QWORD *)a2 + 5);
    v119 = (unsigned __int16 *)*((_QWORD *)a2 + 6);
    v15 = (void *)*((_QWORD *)a2 + 17);
    v14 = (void *)*((_QWORD *)a2 + 8);
    v18 = (_QWORD *)*((_QWORD *)a2 + 9);
    v17 = *((_DWORD *)a2 + 20);
    v120 = (void *)*((_QWORD *)a2 + 11);
    v121 = (void *)*((_QWORD *)a2 + 12);
    v122 = (void *)*((_QWORD *)a2 + 13);
    v123 = (void *)*((_QWORD *)a2 + 18);
    v125 = (void *)*((_QWORD *)a2 + 7);
    v10 = *((_QWORD *)a2 + 14);
    v12 = *((_QWORD *)a2 + 15);
    v13 = *((_DWORD *)a2 + 32);
    goto LABEL_41;
  }
  if ( a3 != 48 )
  {
    v7 = -2147024809;
    v8 = *((_QWORD *)this + 11);
    if ( !v8 )
      goto LABEL_302;
    v113 = -2147024809;
    v112 = 515;
    goto LABEL_299;
  }
  if ( WINDLP_ACTION_RECOVEROEM != *(_OWORD *)a2 )
  {
    v7 = -2147024809;
    v8 = *((_QWORD *)this + 11);
    if ( !v8 )
      goto LABEL_302;
    v113 = -2147024809;
    v112 = 520;
    goto LABEL_299;
  }
  v16 = (void *)*((_QWORD *)a2 + 2);
  if ( !v16 )
  {
    v7 = -2147024809;
    v8 = *((_QWORD *)this + 11);
    if ( !v8 )
      goto LABEL_302;
    v113 = -2147024809;
    v112 = 524;
    goto LABEL_299;
  }
  v11 = (unsigned __int16 *)*((_QWORD *)a2 + 3);
  v118 = v11;
  if ( !v11 )
  {
    v7 = -2147024809;
    v8 = *((_QWORD *)this + 11);
    if ( !v8 )
      goto LABEL_302;
    v113 = -2147024809;
    v112 = 525;
    goto LABEL_299;
  }
  v6 = *((_DWORD *)a2 + 8);
  v20 = *((_DWORD *)a2 + 9);
  v21 = (void *)*((_QWORD *)a2 + 5);
  v125 = v21;
  v13 = 0;
  v14 = 0;
  v15 = 0;
  v17 = 0;
  v18 = 0;
LABEL_42:
  v116 = v20;
  if ( (v20 & 0xFFFFFF00) != 0 )
  {
    v7 = -2147024809;
    v8 = *((_QWORD *)this + 11);
    if ( !v8 )
      goto LABEL_302;
    v113 = -2147024809;
    v112 = 572;
    goto LABEL_299;
  }
  v114 = v13;
  v115 = v17;
  v127 = v14;
  v117 = v15;
  Src = v16;
  v128 = v18;
  v22 = v116;
  if ( v6 <= 2 )
  {
    v118 = v11;
    v117 = v15;
    v125 = v21;
    v127 = v14;
    v126 = v18;
    v115 = v17;
    v114 = v13;
    v24 = v18;
    Src = v16;
    v23 = v118;
LABEL_54:
    v128 = v24;
    goto LABEL_55;
  }
  if ( v6 != 3 )
  {
    v7 = -2147024809;
    v8 = *((_QWORD *)this + 11);
    if ( !v8 )
      goto LABEL_302;
    v113 = -2147024809;
    v112 = 580;
    goto LABEL_299;
  }
  v126 = v18;
  v23 = v118;
LABEL_55:
  if ( memcmp_0(&WINDLP_ACTION_RECOVEROEM, &Buf2, 0x10u) )
  {
    if ( (v22 & 0x10) != 0 )
    {
      if ( ((unsigned __int16)(v19 - 1) <= 0x5Fu || v19 >= 0x7Bu) && (unsigned __int16)(v19 - 65) > 0x19u )
      {
        v7 = -2147024735;
        v8 = *((_QWORD *)this + 11);
        if ( !v8 )
          goto LABEL_302;
        v113 = -2147024735;
        v112 = 586;
        goto LABEL_299;
      }
      v116 = v22 | 6;
    }
    else if ( (unsigned __int16)(v19 - 97) > 0x19u && (unsigned __int16)(v19 - 65) > 0x19u )
    {
      v7 = -2147024735;
      v8 = *((_QWORD *)this + 11);
      if ( !v8 )
        goto LABEL_302;
      v113 = -2147024735;
      v112 = 593;
      goto LABEL_299;
    }
  }
  if ( v127 )
  {
    if ( !v126 )
    {
      v7 = -2147024809;
      v8 = *((_QWORD *)this + 11);
      if ( !v8 )
        goto LABEL_302;
      v113 = -2147024809;
      v112 = 602;
      goto LABEL_299;
    }
    if ( !v115 )
    {
      v7 = -2147024809;
      v8 = *((_QWORD *)this + 11);
      if ( !v8 )
        goto LABEL_302;
      v113 = -2147024809;
      v112 = 603;
      goto LABEL_299;
    }
  }
  else if ( v126 || v115 )
  {
    v7 = -2147024809;
    v8 = *((_QWORD *)this + 11);
    if ( !v8 )
      goto LABEL_302;
    v113 = -2147024809;
    v112 = 601;
    goto LABEL_299;
  }
  if ( v6 )
  {
    if ( v6 == 1 )
    {
      v25 = L"NTFS";
    }
    else if ( v6 == 2 )
    {
      v25 = L"FAT32";
    }
    else
    {
      v25 = L"EXFAT";
    }
  }
  else
  {
    v25 = L"AUTO";
  }
  v130 = v25;
  v26 = *((_QWORD *)this + 11);
  v27 = &dword_180084C74;
  if ( v26 )
  {
    v28 = &dword_180084C74;
    if ( Src )
      v28 = (int *)Src;
    CDlpLogT<CEmptyType>::DlpLogFormat(v26, 2u, (__int64)L"LayoutUsb: Initializing Boot WIM Path: [%s]", v28);
  }
  v29 = *((_QWORD *)this + 11);
  if ( v29 )
  {
    v30 = &dword_180084C74;
    if ( v23 )
      v30 = (int *)v23;
    CDlpLogT<CEmptyType>::DlpLogFormat(v29, 2u, (__int64)L"LayoutUsb: Initializing Install WIM Path: [%s]", v30);
  }
  v31 = *((_QWORD *)this + 11);
  if ( v31 )
  {
    v32 = (unsigned __int16 *)&dword_180084C74;
    if ( v119 )
      v32 = v119;
    CDlpLogT<CEmptyType>::DlpLogFormat(v31, 2u, (__int64)L"LayoutUsb: Initializing Customization WIM Path: [%s]", v32);
  }
  v33 = *((_QWORD *)this + 11);
  if ( v33 )
  {
    v34 = &dword_180084C74;
    if ( v117 )
      v34 = (int *)v117;
    CDlpLogT<CEmptyType>::DlpLogFormat(v33, 2u, (__int64)L"LayoutUsb: Initializing OEM Winre WIM Path: [%s]", v34);
  }
  v35 = *((_QWORD *)this + 11);
  if ( v35 )
  {
    v36 = &dword_180084C74;
    if ( v127 )
      v36 = (int *)v127;
    CDlpLogT<CEmptyType>::DlpLogFormat(v35, 2u, (__int64)L"LayoutUsb: Initializing Reconstruction Volume: [%s]", v36);
  }
  v37 = *((_QWORD *)this + 11);
  if ( v37 )
    CDlpLogT<CEmptyType>::DlpLogFormat(
      v37,
      2u,
      (__int64)L"LayoutUsb: Initializing Reconstruction Path Count: [%u]",
      v115);
  v38 = 0;
  if ( v115 )
  {
    while ( 1 )
    {
      v8 = *((_QWORD *)this + 11);
      if ( !v128[v38] )
        break;
      if ( v8 )
        CDlpLogT<CEmptyType>::DlpLogFormat(v8, 2u, (__int64)L"LayoutUsb: Initializing Reconstruction Path: [%s]");
      if ( ++v38 >= v115 )
        goto LABEL_112;
    }
    v7 = -2147024809;
    if ( !v8 )
      goto LABEL_302;
    v113 = -2147024809;
    v112 = 628;
LABEL_299:
    v110 = CDlpLogT<CEmptyType>::DlpLogFormat(
             v8,
             4u,
             (__int64)L"%s(%d): Result = 0x%X",
             L"CDlpActionLayoutUsb::InitializeRoutine",
             v112,
             v113);
    v85 = (unsigned int)v110;
    if ( v110 < 0 )
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v110);
LABEL_301:
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v85);
    goto LABEL_302;
  }
LABEL_112:
  v39 = *((_QWORD *)this + 11);
  if ( v39 )
  {
    v40 = &dword_180084C74;
    if ( v120 )
      v40 = (int *)v120;
    CDlpLogT<CEmptyType>::DlpLogFormat(v39, 2u, (__int64)L"LayoutUsb: Initializing Customizations Directory: [%s]", v40);
  }
  v41 = *((_QWORD *)this + 11);
  if ( v41 )
  {
    v42 = &dword_180084C74;
    if ( v121 )
      v42 = (int *)v121;
    CDlpLogT<CEmptyType>::DlpLogFormat(
      v41,
      2u,
      (__int64)L"LayoutUsb: Initializing OEM Extensibility Directory: [%s]",
      v42);
  }
  v43 = *((_QWORD *)this + 11);
  if ( v43 )
  {
    v44 = &dword_180084C74;
    if ( v122 )
      v44 = (int *)v122;
    CDlpLogT<CEmptyType>::DlpLogFormat(v43, 2u, (__int64)L"LayoutUsb: Initializing OEM AutoApply Directory: [%s]", v44);
  }
  v45 = *((_QWORD *)this + 11);
  if ( v45 )
  {
    v46 = &dword_180084C74;
    if ( v123 )
      v46 = (int *)v123;
    CDlpLogT<CEmptyType>::DlpLogFormat(v45, 2u, (__int64)L"LayoutUsb: Initializing Cloud data Directory: [%s]", v46);
  }
  v47 = *((_QWORD *)this + 11);
  if ( v47 )
  {
    if ( v19 )
      v48 = v19;
    else
      v48 = 63;
    CDlpLogT<CEmptyType>::DlpLogFormat(v47, 2u, (__int64)L"LayoutUsb: Initializing USB Drive: [%c:]", v48);
  }
  v49 = *((_QWORD *)this + 11);
  if ( v49 )
    CDlpLogT<CEmptyType>::DlpLogFormat(v49, 2u, (__int64)L"LayoutUsb: Initializing File System: [%s]", v130);
  v50 = *((_QWORD *)this + 11);
  v51 = v116;
  if ( v50 )
    CDlpLogT<CEmptyType>::DlpLogFormat(v50, 2u, (__int64)L"LayoutUsb: Initializing Flags: [0x%x]", v116);
  v52 = *((_QWORD *)this + 11);
  if ( v52 )
  {
    if ( v125 )
      v27 = (int *)v125;
    CDlpLogT<CEmptyType>::DlpLogFormat(v52, 2u, (__int64)L"LayoutUsb: Initializing Volume Label: [%s]", v27);
  }
  v53 = *((_QWORD *)this + 11);
  if ( v53 )
    CDlpLogT<CEmptyType>::DlpLogFormat(v53, 2u, (__int64)L"LayoutUsb: Initializing Max Volume: [0x%I64X]", v10);
  v54 = *((_QWORD *)this + 11);
  if ( v54 )
    CDlpLogT<CEmptyType>::DlpLogFormat(v54, 2u, (__int64)L"LayoutUsb: Initializing File Split Size: [0x%I64X]", v12);
  v55 = *((_QWORD *)this + 11);
  v56 = v114;
  if ( v55 )
  {
    v57 = L"TRUE";
    if ( !v114 )
      v57 = L"FALSE";
    CDlpLogT<CEmptyType>::DlpLogFormat(v55, 2u, (__int64)L"LayoutUsb: Initializing Use Simplified Wim Split: [%s]", v57);
  }
  *((_WORD *)this + 680) = v19;
  *((_DWORD *)this + 342) = v51;
  *((_DWORD *)this + 341) = v6;
  *((_QWORD *)this + 172) = v10;
  *((_QWORD *)this + 173) = v12;
  *((_DWORD *)this + 348) = v56;
  v58 = Src;
  if ( Src )
  {
    v114 = 0;
    StringCch = CGlobalHelpersT<CEmptyType>::GetStringCchLength<unsigned long>(Src, &v114);
    v7 = StringCch;
    if ( StringCch < 0
      || (StringCch = CImmutableStringsT<unsigned short,CImmutableStringsPolicyDefault>::CreateInternal(
                        v58,
                        v114,
                        (_QWORD *)this + 110),
          v7 = StringCch,
          StringCch < 0) )
    {
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(StringCch);
    }
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v7);
    if ( v7 < 0 )
    {
      v8 = *((_QWORD *)this + 11);
      if ( !v8 )
        goto LABEL_302;
      v113 = v7;
      v112 = 656;
      goto LABEL_299;
    }
  }
  v60 = v118;
  if ( v118 )
  {
    v114 = 0;
    Internal = CGlobalHelpersT<CEmptyType>::GetStringCchLength<unsigned long>(v118, &v114);
    v7 = Internal;
    if ( Internal < 0
      || (Internal = CImmutableStringsT<unsigned short,CImmutableStringsPolicyDefault>::CreateInternal(
                       v60,
                       v114,
                       (_QWORD *)this + 111),
          v7 = Internal,
          Internal < 0) )
    {
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(Internal);
    }
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v7);
    if ( v7 < 0 )
    {
      v8 = *((_QWORD *)this + 11);
      if ( !v8 )
        goto LABEL_302;
      v113 = v7;
      v112 = 660;
      goto LABEL_299;
    }
  }
  v62 = v119;
  if ( v119 )
  {
    v114 = 0;
    v63 = CGlobalHelpersT<CEmptyType>::GetStringCchLength<unsigned long>(v119, &v114);
    v7 = v63;
    if ( v63 < 0
      || (v63 = CImmutableStringsT<unsigned short,CImmutableStringsPolicyDefault>::CreateInternal(
                  v62,
                  v114,
                  (_QWORD *)this + 113),
          v7 = v63,
          v63 < 0) )
    {
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v63);
    }
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v7);
    if ( v7 < 0 )
    {
      v8 = *((_QWORD *)this + 11);
      if ( !v8 )
        goto LABEL_302;
      v113 = v7;
      v112 = 664;
      goto LABEL_299;
    }
  }
  v64 = v117;
  if ( v117 )
  {
    v114 = 0;
    v65 = CGlobalHelpersT<CEmptyType>::GetStringCchLength<unsigned long>(v117, &v114);
    v7 = v65;
    if ( v65 < 0
      || (v65 = CImmutableStringsT<unsigned short,CImmutableStringsPolicyDefault>::CreateInternal(
                  v64,
                  v114,
                  (_QWORD *)this + 116),
          v7 = v65,
          v65 < 0) )
    {
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v65);
    }
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v7);
    if ( v7 < 0 )
    {
      v8 = *((_QWORD *)this + 11);
      if ( !v8 )
        goto LABEL_302;
      v113 = v7;
      v112 = 668;
      goto LABEL_299;
    }
  }
  if ( !v126 )
  {
LABEL_202:
    v79 = v120;
    if ( v120 )
    {
      v114 = 0;
      v80 = CGlobalHelpersT<CEmptyType>::GetStringCchLength<unsigned long>(v120, &v114);
      v7 = v80;
      if ( v80 < 0
        || (v80 = CImmutableStringsT<unsigned short,CImmutableStringsPolicyDefault>::CreateInternal(
                    v79,
                    v114,
                    (_QWORD *)this + 112),
            v7 = v80,
            v80 < 0) )
      {
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v80);
      }
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v7);
      if ( v7 < 0 )
      {
        v8 = *((_QWORD *)this + 11);
        if ( !v8 )
          goto LABEL_302;
        v113 = v7;
        v112 = 683;
        goto LABEL_299;
      }
    }
    v89 = v121;
    if ( v121 )
    {
      v114 = 0;
      v90 = CGlobalHelpersT<CEmptyType>::GetStringCchLength<unsigned long>(v121, &v114);
      v7 = v90;
      if ( v90 < 0
        || (v90 = CImmutableStringsT<unsigned short,CImmutableStringsPolicyDefault>::CreateInternal(
                    v89,
                    v114,
                    (_QWORD *)this + 114),
            v7 = v90,
            v90 < 0) )
      {
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v90);
      }
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v7);
      if ( v7 < 0 )
      {
        v8 = *((_QWORD *)this + 11);
        if ( !v8 )
          goto LABEL_302;
        v113 = v7;
        v112 = 687;
        goto LABEL_299;
      }
    }
    v91 = v122;
    if ( v122 )
    {
      v114 = 0;
      v92 = CGlobalHelpersT<CEmptyType>::GetStringCchLength<unsigned long>(v122, &v114);
      v7 = v92;
      if ( v92 < 0
        || (v92 = CImmutableStringsT<unsigned short,CImmutableStringsPolicyDefault>::CreateInternal(
                    v91,
                    v114,
                    (_QWORD *)this + 115),
            v7 = v92,
            v92 < 0) )
      {
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v92);
      }
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v7);
      if ( v7 < 0 )
      {
        v8 = *((_QWORD *)this + 11);
        if ( !v8 )
          goto LABEL_302;
        v113 = v7;
        v112 = 691;
        goto LABEL_299;
      }
    }
    v93 = v123;
    if ( v123 )
    {
      v114 = 0;
      v94 = CGlobalHelpersT<CEmptyType>::GetStringCchLength<unsigned long>(v123, &v114);
      v7 = v94;
      if ( v94 < 0
        || (v94 = CImmutableStringsT<unsigned short,CImmutableStringsPolicyDefault>::CreateInternal(
                    v93,
                    v114,
                    (_QWORD *)this + 117),
            v7 = v94,
            v94 < 0) )
      {
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v94);
      }
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v7);
      if ( v7 < 0 )
      {
        v8 = *((_QWORD *)this + 11);
        if ( !v8 )
          goto LABEL_302;
        v113 = v7;
        v112 = 695;
        goto LABEL_299;
      }
    }
    v95 = v124;
    if ( v124 )
    {
      v114 = 0;
      v96 = CGlobalHelpersT<CEmptyType>::GetStringCchLength<unsigned long>(v124, &v114);
      v7 = v96;
      if ( v96 < 0
        || (v96 = CImmutableStringsT<unsigned short,CImmutableStringsPolicyDefault>::CreateInternal(
                    v95,
                    v114,
                    (_QWORD *)this + 119),
            v7 = v96,
            v96 < 0) )
      {
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v96);
      }
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v7);
      if ( v7 < 0 )
      {
        v8 = *((_QWORD *)this + 11);
        if ( !v8 )
          goto LABEL_302;
        v113 = v7;
        v112 = 699;
        goto LABEL_299;
      }
    }
    v97 = v125;
    if ( v125 )
    {
      v114 = 0;
      v98 = CGlobalHelpersT<CEmptyType>::GetStringCchLength<unsigned long>(v125, &v114);
      v7 = v98;
      if ( v98 >= 0 )
      {
        v99 = CImmutableStringsT<unsigned short,CImmutableStringsPolicyDefault>::CreateInternal(
                v97,
                v114,
                (_QWORD *)this + 120);
        v7 = v99;
        v97 = 0;
        if ( v99 < 0 )
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v99);
      }
      else
      {
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v98);
        v97 = 0;
      }
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v7);
      if ( v7 < 0 )
      {
        v8 = *((_QWORD *)this + 11);
        if ( !v8 )
          goto LABEL_302;
        v113 = v7;
        v112 = 703;
        goto LABEL_299;
      }
    }
    if ( !memcmp_0(&WINDLP_ACTION_LAYOUTUSB, &Buf2, 0x10u) )
    {
      v100 = CDlpActionLayoutUsb::PopulateLayoutPath(this, v95);
      v7 = v100;
      if ( v100 < 0 )
      {
        v8 = *((_QWORD *)this + 11);
        if ( !v8 )
          goto LABEL_302;
        v113 = v100;
        v112 = 712;
        goto LABEL_299;
      }
      if ( v60 )
      {
        if ( *((void **)this + 173) == v97 )
        {
          v102 = CDlpActionLayoutUsb::PopulateWimPath(this, 1, v60, 0);
          v7 = v102;
          if ( v102 < 0 )
          {
            v8 = *((_QWORD *)this + 11);
            if ( !v8 )
              goto LABEL_302;
            v113 = v102;
            v112 = 722;
            goto LABEL_299;
          }
        }
        else
        {
          v101 = CDlpActionLayoutUsb::PopulateWimPath(this, 1, v60, L"sources\\install.swm");
          v7 = v101;
          if ( v101 < 0 )
          {
            v8 = *((_QWORD *)this + 11);
            if ( !v8 )
              goto LABEL_302;
            v113 = v101;
            v112 = 718;
            goto LABEL_299;
          }
        }
      }
    }
    else if ( !memcmp_0(&WINDLP_ACTION_RECOVERUSB, &Buf2, 0x10u) )
    {
      v103 = CDlpActionLayoutUsb::PopulateBootPaths(this);
      v7 = v103;
      if ( v103 < 0 )
      {
        v8 = *((_QWORD *)this + 11);
        if ( !v8 )
          goto LABEL_302;
        v113 = v103;
        v112 = 730;
        goto LABEL_299;
      }
      v104 = CDlpActionLayoutUsb::PopulateWimPaths(this, (const unsigned __int16 *)v58, v60, v62);
      v7 = v104;
      if ( v104 < 0 )
      {
        v8 = *((_QWORD *)this + 11);
        if ( !v8 )
          goto LABEL_302;
        v113 = v104;
        v112 = 734;
        goto LABEL_299;
      }
    }
    v105 = CExclusiveAcquireLock::Init((CDlpActionLayoutUsb *)((char *)this + 560));
    v7 = v105;
    if ( v105 >= 0 )
    {
      v106 = CExclusiveAcquireLock::Init((CDlpActionLayoutUsb *)((char *)this + 688));
      v7 = v106;
      if ( v106 < 0 )
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v106);
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v7);
      if ( v7 >= 0 )
      {
        v107 = CExclusiveAcquireLock::Init((CDlpActionLayoutUsb *)((char *)this + 752));
        v7 = v107;
        if ( v107 < 0 )
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v107);
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v7);
        if ( v7 >= 0 )
        {
          v108 = CExclusiveAcquireLock::Init((CDlpActionLayoutUsb *)((char *)this + 816));
          v7 = v108;
          if ( v108 < 0 )
            CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v108);
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v7);
          if ( v7 >= 0 )
          {
            v109 = CExclusiveAcquireLock::Init((CDlpActionLayoutUsb *)((char *)this + 624));
            v7 = v109;
            if ( v109 < 0 )
              CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v109);
            CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v7);
            if ( v7 >= 0 )
              goto LABEL_302;
            v8 = *((_QWORD *)this + 11);
            if ( !v8 )
              goto LABEL_302;
            v113 = v7;
            v112 = 743;
          }
          else
          {
            v8 = *((_QWORD *)this + 11);
            if ( !v8 )
              goto LABEL_302;
            v113 = v7;
            v112 = 742;
          }
        }
        else
        {
          v8 = *((_QWORD *)this + 11);
          if ( !v8 )
            goto LABEL_302;
          v113 = v7;
          v112 = 741;
        }
      }
      else
      {
        v8 = *((_QWORD *)this + 11);
        if ( !v8 )
          goto LABEL_302;
        v113 = v7;
        v112 = 740;
      }
    }
    else
    {
      v8 = *((_QWORD *)this + 11);
      if ( !v8 )
        goto LABEL_302;
      v113 = v105;
      v112 = 739;
    }
    goto LABEL_299;
  }
  v66 = 0;
  v114 = 0;
  v67 = v127;
  if ( !v127 )
  {
LABEL_183:
    v68 = CImmutableStringsT<unsigned short,CImmutableStringsPolicyDefault>::CreateInternal(
            v67,
            v66,
            (_QWORD *)this + 118);
    v7 = v68;
    if ( v68 >= 0 )
      goto LABEL_185;
    goto LABEL_184;
  }
  v68 = CGlobalHelpersT<CEmptyType>::GetStringCchLength<unsigned long>(v127, &v114);
  v7 = v68;
  if ( v68 >= 0 )
  {
    v66 = v114;
    goto LABEL_183;
  }
LABEL_184:
  CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v68);
LABEL_185:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v7);
  if ( v7 < 0 )
  {
    v8 = *((_QWORD *)this + 11);
    if ( !v8 )
      goto LABEL_302;
    v113 = v7;
    v112 = 672;
    goto LABEL_299;
  }
  v69 = 0;
  v70 = v115;
  if ( !v115 )
    goto LABEL_202;
  while ( 1 )
  {
    v71 = 0;
    v117 = 0;
    v72 = (_WORD *)v128[v69];
    v73 = 0;
    v114 = 0;
    if ( v72 )
    {
      v74 = CGlobalHelpersT<CEmptyType>::GetStringCchLength<unsigned long>(v72, &v114);
      v7 = v74;
      if ( v74 < 0 )
      {
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v74);
        goto LABEL_196;
      }
      v73 = v114;
    }
    v75 = CImmutableStringsT<unsigned short,CImmutableStringsPolicyDefault>::CreateInternal(v72, v73, &v117);
    v7 = v75;
    if ( v75 < 0 )
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v75);
    v71 = (char *)v117;
LABEL_196:
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v7);
    if ( v7 < 0 )
      break;
    v76 = CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault>::Append((__int64)this + 1144, (__int64 *)&v117);
    v7 = v76;
    if ( v76 < 0 )
    {
      v81 = *((_QWORD *)this + 11);
      if ( v81 )
      {
        v82 = CDlpLogT<CEmptyType>::DlpLogFormat(
                v81,
                4u,
                (__int64)L"%s(%d): Result = 0x%X",
                L"CDlpActionLayoutUsb::InitializeRoutine",
                678,
                v76);
        v83 = (unsigned int)v82;
        if ( v82 < 0 )
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v82);
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v83);
      }
      v71 = (char *)v117;
      goto LABEL_214;
    }
    v77 = (char *)v117;
    if ( v117 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v77 - 4);
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    }
    if ( ++v69 >= v70 )
    {
      v60 = v118;
      v58 = Src;
      goto LABEL_202;
    }
  }
  v86 = *((_QWORD *)this + 11);
  if ( v86 )
  {
    v87 = CDlpLogT<CEmptyType>::DlpLogFormat(
            v86,
            4u,
            (__int64)L"%s(%d): Result = 0x%X",
            L"CDlpActionLayoutUsb::InitializeRoutine",
            677,
            v7);
    v88 = (unsigned int)v87;
    if ( v87 < 0 )
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v87);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v88);
  }
LABEL_214:
  if ( v71 )
  {
    v84 = GetProcessHeap();
    HeapFree(v84, 0, v71 - 4);
    v85 = 0;
    goto LABEL_301;
  }
LABEL_302:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v7);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18001dda0  mov     [rsp-8+arg_10], rbx
0x18001dda5  push    rbp
0x18001dda6  push    rsi
0x18001dda7  push    rdi
0x18001dda8  push    r12
0x18001ddaa  push    r13
0x18001ddac  push    r14
0x18001ddae  push    r15
0x18001ddb0  lea     rbp, [rsp-27h]
0x18001ddb5  sub     rsp, 0D0h
0x18001ddbc  mov     rax, cs:__security_cookie
0x18001ddc3  xor     rax, rsp
0x18001ddc6  mov     [rbp+57h+var_40], rax
0x18001ddca  mov     r15d, r8d
0x18001ddcd  mov     r14, rdx
0x18001ddd0  mov     rsi, rcx
0x18001ddd3  xorps   xmm0, xmm0
0x18001ddd6  movups  [rbp+57h+Buf2], xmm0
0x18001ddda  xor     r13d, r13d
0x18001dddd  test    rdx, rdx
0x18001dde0  jnz     short loc_18001DE07
0x18001dde2  mov     eax, 80070057h
0x18001dde7  mov     edi, eax
0x18001dde9  mov     rcx, [rcx+58h]
0x18001dded  test    rcx, rcx
0x18001ddf0  jz      loc_18001F039
0x18001ddf6  mov     [rsp+100h+var_D8], eax
0x18001ddfa  mov     [rsp+100h+var_E0], 1C7h
0x18001de02  jmp     loc_18001F011
0x18001de07  mov     rax, [rcx]
0x18001de0a  lea     rdx, [rbp+57h+Buf2]
0x18001de0e  mov     rax, [rax+38h]
0x18001de12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001de17  mov     edi, eax
0x18001de19  test    eax, eax
0x18001de1b  jns     short loc_18001DE3B
0x18001de1d  mov     rcx, [rsi+58h]
0x18001de21  test    rcx, rcx
0x18001de24  jz      loc_18001F039
0x18001de2a  mov     [rsp+100h+var_D8], eax
0x18001de2e  mov     [rsp+100h+var_E0], 1E7h
0x18001de36  jmp     loc_18001F011
0x18001de3b  mov     [rbp+57h+Src], r13
0x18001de3f  mov     [rbp+57h+var_B0], r13
0x18001de43  mov     [rbp+57h+var_C0], r13
0x18001de47  mov     [rbp+57h+var_70], r13
0x18001de4b  mov     [rbp+57h+var_78], r13
0x18001de4f  mov     [rbp+57h+var_CC], r13d
0x18001de53  mov     [rbp+57h+var_A8], r13
0x18001de57  mov     [rbp+57h+var_A0], r13
0x18001de5b  mov     [rbp+57h+var_98], r13
0x18001de5f  mov     [rbp+57h+var_90], r13
0x18001de63  mov     r8d, 10h; Size
0x18001de69  lea     rdx, [rbp+57h+Buf2]; Buf2
0x18001de6d  lea     rcx, WINDLP_ACTION_LAYOUTUSB; Buf1
0x18001de74  call    memcmp_0
0x18001de79  test    eax, eax
0x18001de7b  jnz     loc_18001DF49
0x18001de81  cmp     r15d, 50h ; 'P'
0x18001de85  jz      short loc_18001DEAC
0x18001de87  mov     eax, 80070057h
0x18001de8c  mov     edi, eax
0x18001de8e  mov     rcx, [rsi+58h]
0x18001de92  test    rcx, rcx
0x18001de95  jz      loc_18001F039
0x18001de9b  mov     [rsp+100h+var_D8], eax
0x18001de9f  mov     [rsp+100h+var_E0], 1EAh
0x18001dea7  jmp     loc_18001F011
0x18001deac  mov     rax, qword ptr cs:WINDLP_ACTION_LAYOUTUSB
0x18001deb3  cmp     rax, [r14]
0x18001deb6  jnz     short loc_18001DF24
0x18001deb8  mov     rax, qword ptr cs:WINDLP_ACTION_LAYOUTUSB+8
0x18001debf  cmp     rax, [r14+8]
0x18001dec3  jnz     short loc_18001DF24
0x18001dec5  mov     rax, [r14+10h]
0x18001dec9  mov     [rbp+57h+var_88], rax
0x18001decd  test    rax, rax
0x18001ded0  jnz     short loc_18001DEF7
0x18001ded2  mov     eax, 80070057h
0x18001ded7  mov     edi, eax
0x18001ded9  mov     rcx, [rsi+58h]
0x18001dedd  test    rcx, rcx
0x18001dee0  jz      loc_18001F039
0x18001dee6  mov     [rsp+100h+var_D8], eax
0x18001deea  mov     [rsp+100h+var_E0], 1F3h
0x18001def2  jmp     loc_18001F011
0x18001def7  mov     rcx, [r14+28h]
0x18001defb  mov     [rbp+57h+var_80], rcx
0x18001deff  mov     rbx, [r14+30h]
0x18001df03  mov     rax, [r14+38h]
0x18001df07  mov     rdi, [r14+40h]
0x18001df0b  mov     ecx, [r14+48h]
0x18001df0f  mov     rdx, [rbp+57h+var_70]
0x18001df13  mov     r8, rdx
0x18001df16  mov     r9, rdx
0x18001df19  mov     r10d, edx
0x18001df1c  mov     r11, rdx
0x18001df1f  jmp     loc_18001E15F
0x18001df24  mov     eax, 80070057h
0x18001df29  mov     edi, eax
0x18001df2b  mov     rcx, [rsi+58h]
0x18001df2f  test    rcx, rcx
0x18001df32  jz      loc_18001F039
0x18001df38  mov     [rsp+100h+var_D8], eax
0x18001df3c  mov     [rsp+100h+var_E0], 1EFh
0x18001df44  jmp     loc_18001F011
0x18001df49  mov     r12d, r13d
0x18001df4c  mov     [rbp+57h+var_88], r13
0x18001df50  mov     rbx, r13
0x18001df53  mov     rdi, r13
0x18001df56  mov     [rbp+57h+var_D0], r13d
0x18001df5a  mov     r8d, 10h; Size
0x18001df60  lea     rdx, [rbp+57h+Buf2]; Buf2
0x18001df64  lea     rcx, WINDLP_ACTION_RECOVEROEM; Buf1
0x18001df6b  call    memcmp_0
0x18001df70  test    eax, eax
0x18001df72  jnz     loc_18001E06B
0x18001df78  cmp     r15d, 30h ; '0'
0x18001df7c  jz      short loc_18001DFA3
0x18001df7e  mov     eax, 80070057h
0x18001df83  mov     edi, eax
0x18001df85  mov     rcx, [rsi+58h]
0x18001df89  test    rcx, rcx
0x18001df8c  jz      loc_18001F039
0x18001df92  mov     [rsp+100h+var_D8], eax
0x18001df96  mov     [rsp+100h+var_E0], 203h
0x18001df9e  jmp     loc_18001F011
0x18001dfa3  mov     rax, qword ptr cs:WINDLP_ACTION_RECOVEROEM
0x18001dfaa  cmp     rax, [r14]
0x18001dfad  jnz     loc_18001E046
0x18001dfb3  mov     rax, qword ptr cs:WINDLP_ACTION_RECOVEROEM+8
0x18001dfba  cmp     rax, [r14+8]
0x18001dfbe  jnz     loc_18001E046
0x18001dfc4  mov     r9, [r14+10h]
0x18001dfc8  test    r9, r9
0x18001dfcb  jnz     short loc_18001DFF2
0x18001dfcd  mov     eax, 80070057h
0x18001dfd2  mov     edi, eax
0x18001dfd4  mov     rcx, [rsi+58h]
0x18001dfd8  test    rcx, rcx
0x18001dfdb  jz      loc_18001F039
0x18001dfe1  mov     [rsp+100h+var_D8], eax
0x18001dfe5  mov     [rsp+100h+var_E0], 20Ch
0x18001dfed  jmp     loc_18001F011
0x18001dff2  mov     rax, [r14+18h]
0x18001dff6  mov     [rbp+57h+var_B8], rax
0x18001dffa  test    rax, rax
0x18001dffd  jnz     short loc_18001E024
0x18001dfff  mov     eax, 80070057h
0x18001e004  mov     edi, eax
0x18001e006  mov     rcx, [rsi+58h]
0x18001e00a  test    rcx, rcx
0x18001e00d  jz      loc_18001F039
0x18001e013  mov     [rsp+100h+var_D8], eax
0x18001e017  mov     [rsp+100h+var_E0], 20Dh
0x18001e01f  jmp     loc_18001F011
0x18001e024  mov     r13d, [r14+20h]
0x18001e028  mov     r15d, [r14+24h]
0x18001e02c  mov     r14, [r14+28h]
0x18001e030  mov     [rbp+57h+var_80], r14
0x18001e034  mov     ecx, ebx
0x18001e036  mov     edx, ecx
0x18001e038  mov     r8d, ecx
0x18001e03b  mov     r10d, ebx
0x18001e03e  mov     r11d, ecx
0x18001e041  jmp     loc_18001E174
0x18001e046  mov     eax, 80070057h
0x18001e04b  mov     edi, eax
0x18001e04d  mov     rcx, [rsi+58h]
0x18001e051  test    rcx, rcx
0x18001e054  jz      loc_18001F039
0x18001e05a  mov     [rsp+100h+var_D8], eax
0x18001e05e  mov     [rsp+100h+var_E0], 208h
0x18001e066  jmp     loc_18001F011
0x18001e06b  mov     r8d, 10h; Size
0x18001e071  lea     rdx, [rbp+57h+Buf2]; Buf2
0x18001e075  lea     rcx, WINDLP_ACTION_RECOVERUSB; Buf1
0x18001e07c  call    memcmp_0
0x18001e081  test    eax, eax
0x18001e083  jnz     loc_18001E2BB
0x18001e089  cmp     r15d, 98h
0x18001e090  jz      short loc_18001E0B7
0x18001e092  mov     eax, 80070057h
0x18001e097  mov     edi, eax
0x18001e099  mov     rcx, [rsi+58h]
0x18001e09d  test    rcx, rcx
0x18001e0a0  jz      loc_18001F039
0x18001e0a6  mov     [rsp+100h+var_D8], eax
0x18001e0aa  mov     [rsp+100h+var_E0], 219h
0x18001e0b2  jmp     loc_18001F011
0x18001e0b7  mov     rax, qword ptr cs:WINDLP_ACTION_RECOVERUSB
0x18001e0be  cmp     rax, [r14]
0x18001e0c1  jnz     loc_18001E296
0x18001e0c7  mov     rax, qword ptr cs:WINDLP_ACTION_RECOVERUSB+8
0x18001e0ce  cmp     rax, [r14+8]
0x18001e0d2  jnz     loc_18001E296
0x18001e0d8  mov     r9, [r14+10h]
0x18001e0dc  test    r9, r9
0x18001e0df  jnz     short loc_18001E106
0x18001e0e1  mov     eax, 80070057h
0x18001e0e6  mov     edi, eax
0x18001e0e8  mov     rcx, [rsi+58h]
0x18001e0ec  test    rcx, rcx
0x18001e0ef  jz      loc_18001F039
0x18001e0f5  mov     [rsp+100h+var_D8], eax
0x18001e0f9  mov     [rsp+100h+var_E0], 222h
0x18001e101  jmp     loc_18001F011
0x18001e106  mov     rax, [r14+28h]
0x18001e10a  mov     rcx, [r14+30h]
0x18001e10e  mov     [rbp+57h+var_B0], rcx
0x18001e112  mov     r8, [r14+88h]
0x18001e119  mov     rdx, [r14+40h]
0x18001e11d  mov     r11, [r14+48h]
0x18001e121  mov     r10d, [r14+50h]
0x18001e125  mov     rcx, [r14+58h]
0x18001e129  mov     [rbp+57h+var_A8], rcx
0x18001e12d  mov     rcx, [r14+60h]
0x18001e131  mov     [rbp+57h+var_A0], rcx
0x18001e135  mov     rcx, [r14+68h]
0x18001e139  mov     [rbp+57h+var_98], rcx
0x18001e13d  mov     rcx, [r14+90h]
0x18001e144  mov     [rbp+57h+var_90], rcx
0x18001e148  mov     rcx, [r14+38h]
0x18001e14c  mov     [rbp+57h+var_80], rcx
0x18001e150  mov     rbx, [r14+70h]
0x18001e154  mov     rdi, [r14+78h]
0x18001e158  mov     ecx, [r14+80h]
0x18001e15f  mov     r13d, [r14+1Ch]
0x18001e163  mov     r15d, [r14+20h]
0x18001e167  movzx   r12d, word ptr [r14+18h]
0x18001e16c  mov     r14, [rbp+57h+var_80]
0x18001e170  mov     [rbp+57h+var_B8], rax
0x18001e174  mov     [rbp+57h+var_C8], r15d
0x18001e178  test    r15d, 0FFFFFF00h
0x18001e17f  jz      short loc_18001E1A6
0x18001e181  mov     eax, 80070057h
0x18001e186  mov     edi, eax
0x18001e188  mov     rcx, [rsi+58h]
0x18001e18c  test    rcx, rcx
0x18001e18f  jz      loc_18001F039
0x18001e195  mov     [rsp+100h+var_D8], eax
0x18001e199  mov     [rsp+100h+var_E0], 23Ch
0x18001e1a1  jmp     loc_18001F011
0x18001e1a6  mov     [rbp+57h+var_D0], ecx
0x18001e1a9  mov     r15, [rbp+57h+var_90]
0x18001e1ad  mov     [rbp+57h+var_90], r15
0x18001e1b1  mov     r15, [rbp+57h+var_98]
0x18001e1b5  mov     [rbp+57h+var_98], r15
0x18001e1b9  mov     r15, [rbp+57h+var_A0]
0x18001e1bd  mov     [rbp+57h+var_A0], r15
0x18001e1c1  mov     r15, [rbp+57h+var_A8]
0x18001e1c5  mov     [rbp+57h+var_A8], r15
0x18001e1c9  mov     [rbp+57h+var_CC], r10d
0x18001e1cd  mov     [rbp+57h+var_70], rdx
0x18001e1d1  mov     r15, [rbp+57h+var_88]
0x18001e1d5  mov     [rbp+57h+var_88], r15
0x18001e1d9  mov     [rbp+57h+var_C0], r8
0x18001e1dd  mov     r15, [rbp+57h+var_B0]
0x18001e1e1  mov     [rbp+57h+var_B0], r15
0x18001e1e5  mov     [rbp+57h+Src], r9
0x18001e1e9  mov     [rbp+57h+var_68], r11
0x18001e1ed  test    r13d, r13d
0x18001e1f0  mov     r15d, [rbp+57h+var_C8]
0x18001e1f4  jz      short loc_18001E23A
0x18001e1f6  cmp     r13d, 1
0x18001e1fa  jz      short loc_18001E23A
0x18001e1fc  cmp     r13d, 2
0x18001e200  jz      short loc_18001E23A
0x18001e202  cmp     r13d, 3
0x18001e206  jz      short loc_18001E22D
0x18001e208  mov     eax, 80070057h
0x18001e20d  mov     edi, eax
0x18001e20f  mov     rcx, [rsi+58h]
0x18001e213  test    rcx, rcx
0x18001e216  jz      loc_18001F039
0x18001e21c  mov     [rsp+100h+var_D8], eax
0x18001e220  mov     [rsp+100h+var_E0], 244h
0x18001e228  jmp     loc_18001F011
0x18001e22d  mov     [rbp+57h+var_78], r11
0x18001e231  mov     r14, [rbp+57h+var_B8]
0x18001e235  jmp     loc_18001E2D2
0x18001e23a  mov     [rbp+57h+var_B8], rax
0x18001e23e  mov     rax, [rbp+57h+var_B0]
0x18001e242  mov     [rbp+57h+var_B0], rax
0x18001e246  mov     [rbp+57h+var_C0], r8
0x18001e24a  mov     rax, [rbp+57h+var_88]
0x18001e24e  mov     [rbp+57h+var_88], rax
0x18001e252  mov     [rbp+57h+var_80], r14
0x18001e256  mov     [rbp+57h+var_70], rdx
0x18001e25a  mov     [rbp+57h+var_78], r11
0x18001e25e  mov     [rbp+57h+var_CC], r10d
0x18001e262  mov     rax, [rbp+57h+var_A8]
0x18001e266  mov     [rbp+57h+var_A8], rax
0x18001e26a  mov     rax, [rbp+57h+var_A0]
0x18001e26e  mov     [rbp+57h+var_A0], rax
0x18001e272  mov     rax, [rbp+57h+var_98]
0x18001e276  mov     [rbp+57h+var_98], rax
0x18001e27a  mov     rax, [rbp+57h+var_90]
0x18001e27e  mov     [rbp+57h+var_90], rax
0x18001e282  mov     [rbp+57h+var_D0], ecx
  ... truncated ...
```
