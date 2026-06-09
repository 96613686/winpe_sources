# CVarVector::CVarVector(int,tagSAFEARRAY *,int)

- ea: `0x1800061e0`
- end: `0x180007234`
- name: `??0CVarVector@@QEAA@HPEAUtagSAFEARRAY@@H@Z`
- size: `4180`
- prototype: `CVarVector *(CVarVector *__hidden this, int, struct tagSAFEARRAY *, int)`
- caller_count: `2`
- callee_count: `18`
- tags: `installer_update`

## callers

- `0x180005ec0`
- `0x180039b70`

## callees

- `0x180005258`
- `0x180005790`
- `0x180005880`
- `0x180005980`
- `0x1800061e0`
- `0x18000723c`
- `0x180008c80`
- `0x18000a290`
- `0x18000b8b0`
- `0x180014120`
- `0x1800243c0`
- `0x180027490`
- `0x18002856c`
- `0x1800289e0`
- `0x18002ca74`
- `0x18002ee7c`
- `0x180039a10`
- `0x180047010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800062e7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800062e7`
- `OLEAUT32!__imp_SysFreeString` at `0x1800064a4`
- `OLEAUT32!__imp_SysFreeString` at `0x1800064a4`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180006420`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180006696`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180007115`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800071e8`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180006420`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180006696`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180007115`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800071e8`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x180006271`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x18000630e`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x180006271`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x18000630e`
- `OLEAUT32!__imp_SafeArrayGetElemsize` at `0x18000636a`
- `OLEAUT32!__imp_SafeArrayGetElemsize` at `0x18000636a`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1800062a7`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180006334`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180006701`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1800062a7`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180006334`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180006701`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180006294`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1800066ee`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180006294`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1800066ee`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x180006507`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x18000666e`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x180006507`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x18000666e`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
CVarVector *__fastcall CVarVector::CVarVector(CVarVector *this, unsigned int a2, struct tagSAFEARRAY *a3, int a4)
{
  struct tagSAFEARRAY *v5; // rbx
  int v8; // r14d
  int v9; // eax
  unsigned int v10; // edx
  void *v11; // rbx
  SAFEARRAY *v12; // r14
  unsigned int v14; // r15d
  unsigned __int16 *BSTRAtThrow; // rbx
  CVar *v16; // rax
  CVar *v17; // rsi
  unsigned int v18; // edx
  char *v19; // rbx
  int v20; // eax
  unsigned int v21; // edx
  struct IUnknown *v22; // rsi
  char *v23; // rax
  CVar *v24; // rbx
  unsigned int v25; // edx
  HRESULT Element; // eax
  BOOL v27; // ecx
  CSafeArray *v28; // rax
  __int16 v29; // si
  char *v30; // rax
  CVar *v31; // rbx
  unsigned int v32; // edx
  char v33; // si
  char *v34; // rax
  CVar *v35; // rbx
  unsigned int v36; // edx
  __int16 v37; // si
  char *v38; // rax
  CVar *v39; // rbx
  unsigned int v40; // edx
  int v41; // xmm6_4
  char *v42; // rax
  CVar *v43; // rbx
  unsigned int v44; // edx
  __int64 v45; // xmm6_8
  char *v46; // rax
  CVar *v47; // rbx
  unsigned int v48; // edx
  struct IDispatch *DispatchAt; // rsi
  char *v50; // rax
  CVar *v51; // rbx
  unsigned int v52; // edx
  SAFEARRAY *psa; // [rsp+30h] [rbp-158h] BYREF
  char v54; // [rsp+38h] [rbp-150h] BYREF
  char v55; // [rsp+39h] [rbp-14Fh] BYREF
  char v56; // [rsp+3Ah] [rbp-14Eh] BYREF
  char v57; // [rsp+3Bh] [rbp-14Dh] BYREF
  char v58; // [rsp+3Ch] [rbp-14Ch] BYREF
  char v59; // [rsp+3Dh] [rbp-14Bh] BYREF
  char v60; // [rsp+3Eh] [rbp-14Ah] BYREF
  char v61; // [rsp+3Fh] [rbp-149h] BYREF
  char pExceptionObject; // [rsp+40h] [rbp-148h] BYREF
  char v63; // [rsp+41h] [rbp-147h] BYREF
  char v64; // [rsp+42h] [rbp-146h] BYREF
  char v65; // [rsp+43h] [rbp-145h] BYREF
  char v66; // [rsp+44h] [rbp-144h] BYREF
  char v67; // [rsp+45h] [rbp-143h] BYREF
  char v68; // [rsp+46h] [rbp-142h] BYREF
  char v69; // [rsp+47h] [rbp-141h] BYREF
  char v70; // [rsp+48h] [rbp-140h] BYREF
  char v71; // [rsp+49h] [rbp-13Fh] BYREF
  char v72; // [rsp+4Ah] [rbp-13Eh] BYREF
  LONG plLbound; // [rsp+4Ch] [rbp-13Ch] BYREF
  int v74; // [rsp+50h] [rbp-138h]
  struct tagSAFEARRAYBOUND v75; // [rsp+58h] [rbp-130h] BYREF
  int v76; // [rsp+60h] [rbp-128h]
  LONG plUbound; // [rsp+64h] [rbp-124h] BYREF
  LONG v78[2]; // [rsp+68h] [rbp-120h] BYREF
  LONG v79[2]; // [rsp+70h] [rbp-118h] BYREF
  struct IUnknown *v80; // [rsp+78h] [rbp-110h] BYREF
  LONG v81[2]; // [rsp+80h] [rbp-108h] BYREF
  LONG v82; // [rsp+88h] [rbp-100h] BYREF
  unsigned int i; // [rsp+90h] [rbp-F8h]
  LONG rgIndices; // [rsp+98h] [rbp-F0h] BYREF
  int v85; // [rsp+A0h] [rbp-E8h] BYREF
  int v86; // [rsp+A4h] [rbp-E4h]
  signed int v87; // [rsp+B8h] [rbp-D0h]
  SAFEARRAY *v88; // [rsp+C0h] [rbp-C8h]
  __int64 pv; // [rsp+C8h] [rbp-C0h] BYREF
  char v90[8]; // [rsp+D0h] [rbp-B8h] BYREF
  char v91[8]; // [rsp+D8h] [rbp-B0h] BYREF
  char v92[8]; // [rsp+E0h] [rbp-A8h] BYREF
  char *v93; // [rsp+E8h] [rbp-A0h]
  char v94[8]; // [rsp+F0h] [rbp-98h] BYREF
  char *v95; // [rsp+F8h] [rbp-90h]
  char v96[8]; // [rsp+100h] [rbp-88h] BYREF
  char *v97; // [rsp+108h] [rbp-80h]
  char *v98; // [rsp+110h] [rbp-78h]
  char *v99; // [rsp+118h] [rbp-70h]
  unsigned __int16 *v100; // [rsp+120h] [rbp-68h]
  CVar *v101; // [rsp+128h] [rbp-60h]
  char *v102; // [rsp+130h] [rbp-58h]

  v5 = a3;
  *((_DWORD *)this + 3) = 8;
  *((_DWORD *)this + 2) = 0;
  *((_DWORD *)this + 4) = 100;
  *((_QWORD *)this + 3) = (char *)this + 32;
  *((_QWORD *)this + 13) = 0;
  *((_QWORD *)this + 14) = 0;
  psa = 0;
  v8 = 0;
  v74 = 0;
  *(_DWORD *)this = a2;
  if ( a2 <= 0x11 && (v9 = 142140, _bittest(&v9, a2)) )
  {
    v76 = 1;
  }
  else
  {
    v27 = 0;
    v76 = 0;
    if ( a2 == 12 && a3 )
    {
      v81[0] = 0;
      v79[0] = 0;
      SafeArrayGetLBound(a3, 1u, v81);
      SafeArrayGetUBound(v5, 1u, v79);
      v27 = v79[0] == v81[0] - 1;
      v76 = v27;
    }
    if ( !v27 )
    {
      *((_DWORD *)this + 24) = 2;
      return this;
    }
  }
  if ( v5 )
  {
    if ( SafeArrayGetDim(v5) == 1 )
    {
      plLbound = 0;
      plUbound = 0;
      SafeArrayGetLBound(v5, 1u, &plLbound);
      SafeArrayGetUBound(v5, 1u, &plUbound);
      if ( plLbound )
      {
        if ( (int)COleAuto::_SafeArrayCopy(v5, &psa) < 0 )
        {
          *((_DWORD *)this + 24) = 1;
          return this;
        }
        v8 = 1;
        v74 = 1;
        v75.cElements = plUbound - plLbound + 1;
        v75.lLbound = 0;
        COleAuto::_SafeArrayRedim(psa, &v75);
        v5 = psa;
      }
      else
      {
        psa = v5;
      }
      if ( a4 )
      {
        if ( v8 )
        {
          v28 = (CSafeArray *)CWin32DefaultArena::WbemMemAlloc(0x28u);
          v80 = (struct IUnknown *)v28;
          if ( v28 )
            v11 = CSafeArray::CSafeArray(v28, psa, a2, 6, 32);
          else
            v11 = 0;
        }
        else
        {
          if ( hHeap )
            v11 = HeapAlloc(hHeap, 0, 0x28u);
          else
            v11 = 0;
          v80 = (struct IUnknown *)v11;
          if ( v11 )
          {
            v12 = psa;
            *((_DWORD *)v11 + 3) = 0;
            *((_QWORD *)v11 + 4) = 0;
            if ( SafeArrayGetDim(v12) != 1 )
              *((_DWORD *)v11 + 3) = 1;
            *((_QWORD *)v11 + 4) = v12;
            v78[0] = 0;
            if ( SafeArrayGetUBound(*((SAFEARRAY **)v11 + 4), 1u, v78) )
              *((_DWORD *)v11 + 3) = 1;
            *((_DWORD *)v11 + 6) = v78[0] + 1;
            *((_DWORD *)v11 + 7) = 0;
            *(_DWORD *)v11 = v78[0];
            *((_DWORD *)v11 + 4) = a2;
            *((_DWORD *)v11 + 2) = 32;
            *((_DWORD *)v11 + 1) = 1;
            *((_DWORD *)v11 + 5) = SafeArrayGetElemsize(*((SAFEARRAY **)v11 + 4));
          }
          else
          {
            v11 = 0;
          }
        }
        *((_QWORD *)this + 13) = v11;
        if ( !v11 )
        {
          CMemoryLog::Write((CMemoryLog *)&unk_18006A9C0, 0xFFFFFFFE);
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_s(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              48,
              &WPP_2a153f28302f3c49102d4d5d1835c102_Traceguids,
              "CX_MemoryException()");
          }
          throw (CX_MemoryException *)&v54;
        }
        if ( *((_DWORD *)v11 + 3) )
        {
          CSafeArray::`scalar deleting destructor'((CSafeArray *)v11, v10);
          *((_QWORD *)this + 13) = 0;
          *((_DWORD *)this + 24) = 1;
        }
        *((_DWORD *)this + 24) = 0;
      }
      else
      {
        CSafeArray::CSafeArray((CSafeArray *)&v85, v5, a2, 5, 32);
        v14 = 0;
        for ( i = 0; ; i = v14 )
        {
          if ( (int)v14 >= v85 + 1 )
          {
            if ( v8 )
              SafeArrayDestroy(psa);
            *((_DWORD *)this + 24) = 0;
            if ( v86 == 2 )
              SafeArrayDestroy(v88);
            return this;
          }
          if ( *(_DWORD *)this != 8 )
            break;
          BSTRAtThrow = CSafeArray::GetBSTRAtThrow((CSafeArray *)&v85, v14);
          v100 = BSTRAtThrow;
          v16 = (CVar *)CWin32DefaultArena::WbemMemAlloc(0x20u);
          v101 = v16;
          if ( v16 )
            v17 = CVar::CVar(v16, 8, BSTRAtThrow);
          else
            v17 = 0;
          if ( !v17 )
          {
            CMemoryLog::Write((CMemoryLog *)&unk_18006A9C0, 0xFFFFFFFE);
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_s(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                61,
                &WPP_2a153f28302f3c49102d4d5d1835c102_Traceguids,
                "CX_MemoryException()");
            }
            throw (CX_MemoryException *)&v71;
          }
          if ( (unsigned int)CFlexArray::Add((CVarVector *)((char *)this + 8), v17) )
          {
            CVar::`scalar deleting destructor'(v17, v18);
            CMemoryLog::Write((CMemoryLog *)&unk_18006A9C0, 0xFFFFFFFE);
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_s(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                62,
                &WPP_2a153f28302f3c49102d4d5d1835c102_Traceguids,
                "CX_MemoryException()");
            }
            throw (CX_MemoryException *)&v72;
          }
          if ( BSTRAtThrow )
            SysFreeString(BSTRAtThrow);
LABEL_36:
          ++v14;
        }
        switch ( *(_DWORD *)this )
        {
          case 2:
            v37 = *(_WORD *)CSafeArray::GetScalarAt(&v85, v92, v14);
            v38 = (char *)CWin32DefaultArena::WbemMemAlloc(0x20u);
            v39 = (CVar *)v38;
            v97 = v38;
            if ( v38 )
            {
              *((_DWORD *)v38 + 6) = 0;
              *(_DWORD *)v38 = 0;
              *((_DWORD *)v38 + 7) = 1;
              *(_OWORD *)(v38 + 8) = 0;
              *(_DWORD *)v38 = 2;
              *((_WORD *)v38 + 4) = v37;
            }
            else
            {
              v39 = 0;
            }
            if ( !v39 )
            {
              CMemoryLog::Write((CMemoryLog *)&unk_18006A9C0, 0xFFFFFFFE);
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_s(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  53,
                  &WPP_2a153f28302f3c49102d4d5d1835c102_Traceguids,
                  "CX_MemoryException()");
              }
              throw (CX_MemoryException *)&v59;
            }
            if ( (unsigned int)CFlexArray::Add((CVarVector *)((char *)this + 8), v39) )
            {
              CVar::`scalar deleting destructor'(v39, v40);
              CMemoryLog::Write((CMemoryLog *)&unk_18006A9C0, 0xFFFFFFFE);
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_s(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  54,
                  &WPP_2a153f28302f3c49102d4d5d1835c102_Traceguids,
                  "CX_MemoryException()");
              }
              throw (CX_MemoryException *)&v60;
            }
            goto LABEL_36;
          case 3:
            rgIndices = v14;
            pv = 0;
            SafeArrayGetElement(v88, &rgIndices, &pv);
            v19 = (char *)CWin32DefaultArena::WbemMemAlloc(0x20u);
            v93 = v19;
            if ( v19 )
            {
              v20 = pv;
              *((_DWORD *)v19 + 6) = 0;
              *(_DWORD *)v19 = 0;
              *((_DWORD *)v19 + 7) = 1;
              *(_OWORD *)(v19 + 8) = 0;
              *((_DWORD *)v19 + 2) = v20;
              *(_DWORD *)v19 = 3;
            }
            else
            {
              v19 = 0;
            }
            if ( !v19 )
            {
              CMemoryLog::Write((CMemoryLog *)&unk_18006A9C0, 0xFFFFFFFE);
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_s(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  55,
                  &WPP_2a153f28302f3c49102d4d5d1835c102_Traceguids,
                  "CX_MemoryException()");
              }
              throw (CX_MemoryException *)&v61;
            }
            if ( (unsigned int)CFlexArray::Add((CVarVector *)((char *)this + 8), v19) )
            {
              CVar::`scalar deleting destructor'((CVar *)v19, v21);
              CMemoryLog::Write((CMemoryLog *)&unk_18006A9C0, 0xFFFFFFFE);
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_s(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  56,
                  &WPP_2a153f28302f3c49102d4d5d1835c102_Traceguids,
                  "CX_MemoryException()");
              }
              throw (CX_MemoryException *)&pExceptionObject;
            }
            goto LABEL_36;
          case 4:
            v41 = *(_DWORD *)CSafeArray::GetScalarAt(&v85, v94, v14);
            v42 = (char *)CWin32DefaultArena::WbemMemAlloc(0x20u);
            v43 = (CVar *)v42;
            v95 = v42;
            if ( v42 )
            {
              *((_DWORD *)v42 + 6) = 0;
              *(_DWORD *)v42 = 0;
              *((_DWORD *)v42 + 7) = 1;
              *(_OWORD *)(v42 + 8) = 0;
              *((_DWORD *)v42 + 2) = v41;
              *(_DWORD *)v42 = 4;
            }
            else
            {
              v43 = 0;
            }
            if ( !v43 )
            {
              CMemoryLog::Write((CMemoryLog *)&unk_18006A9C0, 0xFFFFFFFE);
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_s(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  57,
                  &WPP_2a153f28302f3c49102d4d5d1835c102_Traceguids,
                  "CX_MemoryException()");
              }
              throw (CX_MemoryException *)&v63;
            }
            if ( (unsigned int)CFlexArray::Add((CVarVector *)((char *)this + 8), v43) )
            {
              CVar::`scalar deleting destructor'(v43, v44);
              CMemoryLog::Write((CMemoryLog *)&unk_18006A9C0, 0xFFFFFFFE);
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_s(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  58,
                  &WPP_2a153f28302f3c49102d4d5d1835c102_Traceguids,
                  "CX_MemoryException()");
              }
              throw (CX_MemoryException *)&v64;
            }
            goto LABEL_36;
          case 5:
            v45 = *(_QWORD *)CSafeArray::GetScalarAt(&v85, v96, v14);
            v46 = (char *)CWin32DefaultArena::WbemMemAlloc(0x20u);
            v47 = (CVar *)v46;
            v102 = v46;
            if ( v46 )
            {
              *((_DWORD *)v46 + 6) = 0;
              *(_DWORD *)v46 = 0;
              *((_DWORD *)v46 + 7) = 1;
              *(_OWORD *)(v46 + 8) = 0;
              *((_QWORD *)v46 + 1) = v45;
              *(_DWORD *)v46 = 5;
            }
            else
            {
              v47 = 0;
            }
            if ( !v47 )
            {
              CMemoryLog::Write((CMemoryLog *)&unk_18006A9C0, 0xFFFFFFFE);
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_s(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  59,
                  &WPP_2a153f28302f3c49102d4d5d1835c102_Traceguids,
                  "CX_MemoryException()");
              }
              throw (CX_MemoryException *)&v65;
            }
            if ( (unsigned int)CFlexArray::Add((CVarVector *)((char *)this + 8), v47) )
            {
              CVar::`scalar deleting destructor'(v47, v48);
              CMemoryLog::Write((CMemoryLog *)&unk_18006A9C0, 0xFFFFFFFE);
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_s(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  60,
                  &WPP_2a153f28302f3c49102d4d5d1835c102_Traceguids,
                  "CX_MemoryException()");
              }
              throw (CX_MemoryException *)&v66;
            }
            goto LABEL_36;
          case 9:
            DispatchAt = CSafeArray::GetDispatchAt((CSafeArray *)&v85, v14);
            v75 = (struct tagSAFEARRAYBOUND)DispatchAt;
            v50 = (char *)CWin32DefaultArena::WbemMemAlloc(0x20u);
            v51 = (CVar *)v50;
            v98 = v50;
            if ( v50 )
            {
              *((_DWORD *)v50 + 6) = 0;
              *(_DWORD *)v50 = 0;
              *((_DWORD *)v50 + 7) = 1;
              *(_OWORD *)(v50 + 8) = 0;
            }
            else
            {
              v51 = 0;
            }
            if ( !v51 )
            {
              CMemoryLog::Write((CMemoryLog *)&unk_18006A9C0, 0xFFFFFFFE);
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_s(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  63,
                  &WPP_2a153f28302f3c49102d4d5d1835c102_Traceguids,
                  "CX_MemoryException()");
              }
              throw (CX_MemoryException *)&v67;
            }
            CVar::SetDispatch(v51, DispatchAt);
            if ( (unsigned int)CFlexArray::Add((CVarVector *)((char *)this + 8), v51) )
            {
              CVar::`scalar deleting destructor'(v51, v52);
              CMemoryLog::Write((CMemoryLog *)&unk_18006A9C0, 0xFFFFFFFE);
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_s(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  64,
                  &WPP_2a153f28302f3c49102d4d5d1835c102_Traceguids,
                  "CX_MemoryException()");
              }
              throw (CX_MemoryException *)&v68;
            }
            if ( DispatchAt )
              ((void (__fastcall *)(struct IDispatch *))DispatchAt->lpVtbl->Release)(DispatchAt);
            v75 = 0;
            goto LABEL_36;
          case 0xB:
            v29 = *(_WORD *)CSafeArray::GetScalarAt(&v85, v90, v14);
            v30 = (char *)CWin32DefaultArena::WbemMemAlloc(0x20u);
            v31 = (CVar *)v30;
            *(_QWORD *)v81 = v30;
            if ( v30 )
            {
              *((_DWORD *)v30 + 6) = 0;
              *(_DWORD *)v30 = 0;
              *((_DWORD *)v30 + 7) = 1;
              *(_OWORD *)(v30 + 8) = 0;
              *((_WORD *)v30 + 4) = v29;
              *(_DWORD *)v30 = 11;
            }
            else
            {
              v31 = 0;
            }
            if ( !v31 )
            {
              CMemoryLog::Write((CMemoryLog *)&unk_18006A9C0, 0xFFFFFFFE);
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_s(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  49,
                  &WPP_2a153f28302f3c49102d4d5d1835c102_Traceguids,
                  "CX_MemoryException()");
              }
              throw (CX_MemoryException *)&v55;
            }
            if ( (unsigned int)CFlexArray::Add((CVarVector *)((char *)this + 8), v31) )
            {
              CVar::`scalar deleting destructor'(v31, v32);
              CMemoryLog::Write((CMemoryLog *)&unk_18006A9C0, 0xFFFFFFFE);
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_s(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  50,
                  &WPP_2a153f28302f3c49102d4d5d1835c102_Traceguids,
                  "CX_MemoryException()");
              }
              throw (CX_MemoryException *)&v56;
            }
            goto LABEL_36;
          case 0xD:
            v82 = v14;
            v80 = 0;
            if ( (int)v14 < v87 )
            {
              Element = SafeArrayGetElement(v88, &v82, &v80);
              v22 = v80;
              if ( Element )
                v22 = 0;
            }
            else
            {
              v22 = 0;
            }
            *(_QWORD *)v79 = v22;
            v23 = (char *)CWin32DefaultArena::WbemMemAlloc(0x20u);
            v24 = (CVar *)v23;
            v99 = v23;
            if ( v23 )
            {
              *((_DWORD *)v23 + 6) = 0;
              *(_DWORD *)v23 = 0;
              *((_DWORD *)v23 + 7) = 1;
              *(_OWORD *)(v23 + 8) = 0;
            }
            else
            {
              v24 = 0;
            }
            if ( !v24 )
            {
              CMemoryLog::Write((CMemoryLog *)&unk_18006A9C0, 0xFFFFFFFE);
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_s(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  65,
                  &WPP_2a153f28302f3c49102d4d5d1835c102_Traceguids,
                  "CX_MemoryException()");
              }
              throw (CX_MemoryException *)&v69;
            }
            CVar::SetUnknown(v24, v22);
            if ( (unsigned int)CFlexArray::Add((CVarVector *)((char *)this + 8), v24) )
            {
              CVar::`scalar deleting destructor'(v24, v25);
              CMemoryLog::Write((CMemoryLog *)&unk_18006A9C0, 0xFFFFFFFE);
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_s(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  66,
                  &WPP_2a153f28302f3c49102d4d5d1835c102_Traceguids,
                  "CX_MemoryException()");
              }
              throw (CX_MemoryException *)&v70;
            }
            if ( v22 )
              ((void (__fastcall *)(struct IUnknown *))v22->lpVtbl->Release)(v22);
            *(_QWORD *)v79 = 0;
            goto LABEL_36;
          case 0x11:
            v33 = *(_BYTE *)CSafeArray::GetScalarAt(&v85, v91, v14);
            v34 = (char *)CWin32DefaultArena::WbemMemAlloc(0x20u);
            v35 = (CVar *)v34;
            *(_QWORD *)v78 = v34;
            if ( v34 )
            {
              *((_DWORD *)v34 + 6) = 0;
              *(_DWORD *)v34 = 0;
              *((_DWORD *)v34 + 7) = 1;
              *(_OWORD *)(v34 + 8) = 0;
              *(_DWORD *)v34 = 17;
              v34[8] = v33;
            }
            else
            {
              v35 = 0;
            }
            if ( !v35 )
            {
              CMemoryLog::Write((CMemoryLog *)&unk_18006A9C0, 0xFFFFFFFE);
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_s(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  51,
                  &WPP_2a153f28302f3c49102d4d5d1835c102_Traceguids,
                  "CX_MemoryException()");
              }
              throw (CX_MemoryException *)&v57;
            }
            if ( (unsigned int)CFlexArray::Add((CVarVector *)((char *)this + 8), v35) )
            {
              CVar::`scalar deleting destructor'(v35, v36);
              CMemoryLog::Write((CMemoryLog *)&unk_18006A9C0, 0xFFFFFFFE);
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_s(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  52,
                  &WPP_2a153f28302f3c49102d4d5d1835c102_Traceguids,
                  "CX_MemoryException()");
              }
              throw (CX_MemoryException *)&v58;
            }
            goto LABEL_36;
          default:
            *((_DWORD *)this + 24) = 2;
            if ( v8 )
              SafeArrayDestroy(psa);
            if ( v86 == 2 )
              SafeArrayDestroy(v88);
            break;
        }
      }
    }
    else
    {
      *((_DWORD *)this + 24) = 2;
    }
  }
  else
  {
    *((_DWORD *)this + 24) = 0;
  }
  return this;
}

```

## disassembly

```asm
0x1800061e0  mov     rax, rsp
0x1800061e3  mov     [rax+10h], rbx
0x1800061e7  mov     [rax+18h], rsi
0x1800061eb  mov     [rax+8], rcx
0x1800061ef  push    rdi
0x1800061f0  push    r12
0x1800061f2  push    r13
0x1800061f4  push    r14
0x1800061f6  push    r15
0x1800061f8  sub     rsp, 160h
0x1800061ff  movaps  xmmword ptr [rax-38h], xmm6
0x180006203  movaps  xmmword ptr [rax-48h], xmm7
0x180006207  mov     r15d, r9d
0x18000620a  mov     rbx, r8
0x18000620d  mov     esi, edx
0x18000620f  mov     rdi, rcx
0x180006212  mov     dword ptr [rcx+0Ch], 8
0x180006219  xor     r12d, r12d
0x18000621c  mov     [rcx+8], r12d
0x180006220  mov     dword ptr [rcx+10h], 64h ; 'd'
0x180006227  lea     rax, [rcx+20h]
0x18000622b  mov     [rcx+18h], rax
0x18000622f  mov     [rcx+68h], r12
0x180006233  mov     [rcx+70h], r12
0x180006237  mov     [rsp+188h+psa], r12
0x18000623c  mov     r14d, r12d
0x18000623f  mov     [rsp+188h+var_138], r12d
0x180006244  mov     [rcx], edx
0x180006246  cmp     edx, 11h
0x180006249  ja      loc_1800066C0
0x18000624f  mov     eax, 22B3Ch
0x180006254  bt      eax, edx
0x180006257  jnb     loc_1800066C0
0x18000625d  mov     [rsp+188h+var_128], 1
0x180006265  test    rbx, rbx
0x180006268  jz      loc_1800064BA
0x18000626e  mov     rcx, rbx; psa
0x180006271  call    cs:__imp_SafeArrayGetDim
0x180006277  cmp     eax, 1
0x18000627a  jnz     loc_180006732
0x180006280  mov     [rsp+188h+plLbound], r12d
0x180006285  mov     [rsp+188h+plUbound], r12d
0x18000628a  lea     r8, [rsp+188h+plLbound]; plLbound
0x18000628f  mov     edx, eax; nDim
0x180006291  mov     rcx, rbx; psa
0x180006294  call    cs:__imp_SafeArrayGetLBound
0x18000629a  lea     r8, [rsp+188h+plUbound]; plUbound
0x18000629f  mov     edx, 1; nDim
0x1800062a4  mov     rcx, rbx; psa
0x1800062a7  call    cs:__imp_SafeArrayGetUBound
0x1800062ad  cmp     [rsp+188h+plLbound], 0
0x1800062b2  jnz     loc_18000673E
0x1800062b8  mov     [rsp+188h+psa], rbx
0x1800062bd  test    r15d, r15d
0x1800062c0  jz      loc_1800063B8
0x1800062c6  test    r14d, r14d
0x1800062c9  jnz     loc_180006797
0x1800062cf  mov     rcx, cs:hHeap; hHeap
0x1800062d6  test    rcx, rcx
0x1800062d9  jz      loc_1800067D6
0x1800062df  xor     edx, edx; dwFlags
0x1800062e1  mov     r8d, 28h ; '('; dwBytes
0x1800062e7  call    cs:__imp_HeapAlloc
0x1800062ed  mov     rbx, rax
0x1800062f0  mov     [rsp+188h+var_110], rbx
0x1800062f5  test    rbx, rbx
0x1800062f8  jz      loc_1800067F6
0x1800062fe  mov     r14, [rsp+188h+psa]
0x180006303  mov     [rbx+0Ch], r12d
0x180006307  mov     [rbx+20h], r12
0x18000630b  mov     rcx, r14; psa
0x18000630e  call    cs:__imp_SafeArrayGetDim
0x180006314  cmp     eax, 1
0x180006317  jnz     loc_1800067DE
0x18000631d  mov     [rbx+20h], r14
0x180006321  mov     [rsp+188h+var_120], r12d
0x180006326  lea     r8, [rsp+188h+var_120]; plUbound
0x18000632b  mov     edx, 1; nDim
0x180006330  mov     rcx, [rbx+20h]; psa
0x180006334  call    cs:__imp_SafeArrayGetUBound
0x18000633a  test    eax, eax
0x18000633c  jnz     loc_1800067EA
0x180006342  mov     eax, [rsp+188h+var_120]
0x180006346  inc     eax
0x180006348  mov     [rbx+18h], eax
0x18000634b  mov     [rbx+1Ch], r12d
0x18000634f  mov     eax, [rsp+188h+var_120]
0x180006353  mov     [rbx], eax
0x180006355  mov     [rbx+10h], esi
0x180006358  mov     dword ptr [rbx+8], 20h ; ' '
0x18000635f  mov     dword ptr [rbx+4], 1
0x180006366  mov     rcx, [rbx+20h]; psa
0x18000636a  call    cs:__imp_SafeArrayGetElemsize
0x180006370  mov     [rbx+14h], eax
0x180006373  mov     [rdi+68h], rbx
0x180006377  test    rbx, rbx
0x18000637a  jz      loc_1800067FE
0x180006380  cmp     dword ptr [rbx+0Ch], 0
0x180006384  jnz     loc_18000685B
0x18000638a  mov     [rdi+60h], r12d
0x18000638e  mov     rax, rdi
0x180006391  lea     r11, [rsp+188h+var_28]
0x180006399  mov     rbx, [r11+38h]
0x18000639d  mov     rsi, [r11+40h]
0x1800063a1  movaps  xmm6, xmmword ptr [r11-10h]
0x1800063a6  movaps  xmm7, xmmword ptr [r11-20h]
0x1800063ab  mov     rsp, r11
0x1800063ae  pop     r15
0x1800063b0  pop     r14
0x1800063b2  pop     r13
0x1800063b4  pop     r12
0x1800063b6  pop     rdi
0x1800063b7  retn
0x1800063b8  mov     [rsp+188h+var_168], 20h ; ' '; int
0x1800063c0  mov     r9d, 5; int
0x1800063c6  mov     r8d, esi; int
0x1800063c9  mov     rdx, rbx; struct tagSAFEARRAY *
0x1800063cc  lea     rcx, [rsp+188h+var_E8]; this
0x1800063d4  call    ??0CSafeArray@@QEAA@PEAUtagSAFEARRAY@@HHH@Z; CSafeArray::CSafeArray(tagSAFEARRAY *,int,int,int)
0x1800063d9  nop
0x1800063da  mov     r15d, r12d
0x1800063dd  mov     [rsp+188h+var_F8], r12d
0x1800063e5  lea     r13, __ImageBase
0x1800063ec  xorps   xmm7, xmm7
0x1800063ef  mov     eax, [rsp+188h+var_E8]
0x1800063f6  inc     eax
0x1800063f8  cmp     r15d, eax
0x1800063fb  jl      short loc_18000642B
0x1800063fd  test    r14d, r14d
0x180006400  jnz     loc_1800071E3
0x180006406  mov     [rdi+60h], r12d
0x18000640a  cmp     [rsp+188h+var_E4], 2
0x180006412  jnz     loc_18000638E
0x180006418  mov     rcx, [rsp+188h+var_C8]; psa
0x180006420  call    cs:__imp_SafeArrayDestroy
0x180006426  jmp     loc_18000638E
0x18000642b  mov     eax, [rdi]
0x18000642d  cmp     eax, 8
0x180006430  jnz     loc_1800064C3
0x180006436  mov     edx, r15d; int
0x180006439  lea     rcx, [rsp+188h+var_E8]; this
0x180006441  call    ?GetBSTRAtThrow@CSafeArray@@QEAAPEAGH@Z; CSafeArray::GetBSTRAtThrow(int)
0x180006446  mov     rbx, rax
0x180006449  mov     [rsp+188h+var_68], rax
0x180006451  mov     ecx, 20h ; ' '; unsigned __int64
0x180006456  call    ?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18000645b  mov     [rsp+188h+var_60], rax
0x180006463  test    rax, rax
0x180006466  jz      loc_1800065AF
0x18000646c  mov     r8, rbx; unsigned __int16 *
0x18000646f  mov     edx, 8; int
0x180006474  mov     rcx, rax; this
0x180006477  call    ??0CVar@@QEAA@HPEAG@Z; CVar::CVar(int,ushort *)
0x18000647c  mov     rsi, rax
0x18000647f  test    rsi, rsi
0x180006482  jz      loc_180007120
0x180006488  lea     rcx, [rdi+8]; this
0x18000648c  mov     rdx, rsi; void *
0x18000648f  call    ?Add@CFlexArray@@QEAAHPEAX@Z; CFlexArray::Add(void *)
0x180006494  test    eax, eax
0x180006496  jnz     loc_18000717D
0x18000649c  test    rbx, rbx
0x18000649f  jz      short loc_1800064AA
0x1800064a1  mov     rcx, rbx; bstrString
0x1800064a4  call    cs:__imp_SysFreeString
0x1800064aa  inc     r15d
0x1800064ad  mov     [rsp+188h+var_F8], r15d
0x1800064b5  jmp     loc_1800063EF
0x1800064ba  mov     [rdi+60h], r12d
0x1800064be  jmp     loc_18000638E
0x1800064c3  add     eax, 0FFFFFFFEh; switch 16 cases
0x1800064c6  cmp     eax, 0Fh
0x1800064c9  ja      def_1800064DC; jumptable 00000001800064DC default case, cases 6-8,10,12,14-16
0x1800064cf  cdqe
0x1800064d1  mov     ecx, ds:(jpt_1800064DC - 180000000h)[r13+rax*4]
0x1800064d9  add     rcx, r13
0x1800064dc  jmp     rcx; switch jump
0x1800064de  mov     [rsp+188h+rgIndices], r15d; jumptable 00000001800064DC case 3
0x1800064e6  movsd   [rsp+188h+pv], xmm7
0x1800064ef  lea     r8, [rsp+188h+pv]; pv
0x1800064f7  lea     rdx, [rsp+188h+rgIndices]; rgIndices
0x1800064ff  mov     rcx, [rsp+188h+var_C8]; psa
0x180006507  call    cs:__imp_SafeArrayGetElement
0x18000650d  mov     ecx, 20h ; ' '; unsigned __int64
0x180006512  call    ?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180006517  mov     rbx, rax
0x18000651a  mov     [rsp+188h+var_A0], rax
0x180006522  test    rax, rax
0x180006525  jz      loc_1800065B7
0x18000652b  mov     eax, dword ptr [rsp+188h+pv]
0x180006532  mov     [rbx+18h], r12d
0x180006536  mov     [rbx], r12d
0x180006539  mov     dword ptr [rbx+1Ch], 1
0x180006540  xorps   xmm0, xmm0
0x180006543  movups  xmmword ptr [rbx+8], xmm0
0x180006547  mov     [rbx+8], eax
0x18000654a  mov     dword ptr [rbx], 3
0x180006550  test    rbx, rbx
0x180006553  jz      loc_180006C0C
0x180006559  lea     rcx, [rdi+8]; this
0x18000655d  mov     rdx, rbx; void *
0x180006560  call    ?Add@CFlexArray@@QEAAHPEAX@Z; CFlexArray::Add(void *)
0x180006565  test    eax, eax
0x180006567  jz      loc_1800064AA
0x18000656d  mov     rcx, rbx; this
0x180006570  call    ??_GCVar@@QEAAPEAXI@Z; CVar::`scalar deleting destructor'(uint)
0x180006575  mov     edx, 0FFFFFFFEh; int
0x18000657a  lea     rcx, unk_18006A9C0; this
0x180006581  call    ?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180006586  lea     rax, WPP_GLOBAL_Control
0x18000658d  mov     rcx, cs:WPP_GLOBAL_Control
0x180006594  cmp     rcx, rax
0x180006597  jnz     loc_180006C69
0x18000659d  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x1800065a4  lea     rcx, [rsp+188h+pExceptionObject]; pExceptionObject
0x1800065a9  call    _CxxThrowException_0
0x1800065af  mov     rsi, r12
0x1800065b2  jmp     loc_18000647F
0x1800065b7  mov     rbx, r12
0x1800065ba  jmp     short loc_180006550
0x1800065bc  mov     [rsp+188h+var_100], r15d; jumptable 00000001800064DC case 13
0x1800065c4  mov     [rsp+188h+var_110], r12
0x1800065c9  cmp     r15d, [rsp+188h+var_D0]
0x1800065d1  jl      loc_180006659
0x1800065d7  mov     rsi, r12
0x1800065da  mov     qword ptr [rsp+188h+var_118], rsi
0x1800065df  mov     ecx, 20h ; ' '; unsigned __int64
0x1800065e4  call    ?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x1800065e9  mov     rbx, rax
0x1800065ec  mov     [rsp+188h+var_70], rax
0x1800065f4  test    rax, rax
0x1800065f7  jz      short loc_180006654
0x1800065f9  mov     [rax+18h], r12d
0x1800065fd  mov     [rax], r12d
0x180006600  mov     dword ptr [rax+1Ch], 1
0x180006607  xorps   xmm0, xmm0
0x18000660a  movups  xmmword ptr [rax+8], xmm0
0x18000660e  test    rbx, rbx
0x180006611  jz      loc_18000703D
0x180006617  mov     rdx, rsi; struct IUnknown *
0x18000661a  mov     rcx, rbx; this
0x18000661d  call    ?SetUnknown@CVar@@QEAAXPEAUIUnknown@@@Z; CVar::SetUnknown(IUnknown *)
0x180006622  lea     rcx, [rdi+8]; this
0x180006626  mov     rdx, rbx; void *
0x180006629  call    ?Add@CFlexArray@@QEAAHPEAX@Z; CFlexArray::Add(void *)
0x18000662e  test    eax, eax
0x180006630  jnz     loc_18000709A
0x180006636  test    rsi, rsi
0x180006639  jz      short loc_18000664A
0x18000663b  mov     rax, [rsi]
0x18000663e  mov     rcx, rsi
0x180006641  mov     rax, [rax+10h]
0x180006645  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000664a  mov     qword ptr [rsp+188h+var_118], r12
0x18000664f  jmp     loc_1800064AA
0x180006654  mov     rbx, r12
0x180006657  jmp     short loc_18000660E
0x180006659  lea     r8, [rsp+188h+var_110]; pv
0x18000665e  lea     rdx, [rsp+188h+var_100]; rgIndices
0x180006666  mov     rcx, [rsp+188h+var_C8]; psa
0x18000666e  call    cs:__imp_SafeArrayGetElement
0x180006674  mov     rsi, [rsp+188h+var_110]
0x180006679  test    eax, eax
0x18000667b  cmovnz  rsi, r12
0x18000667f  jmp     loc_1800065DA
0x180006684  cmp     [rsp+188h+var_E4], 2
0x18000668c  jnz     short loc_18000669D
0x18000668e  mov     rcx, [rsp+188h+var_C8]; psa
0x180006696  call    cs:__imp_SafeArrayDestroy
0x18000669c  nop
0x18000669d  jmp     loc_18000638E
0x1800066a2  test    rsi, rsi
0x1800066a5  jz      short loc_1800066B6
0x1800066a7  mov     rax, [rsi]
0x1800066aa  mov     rcx, rsi
0x1800066ad  mov     rax, [rax+10h]
0x1800066b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800066b6  mov     qword ptr [rsp+188h+var_130.cElements], r12
0x1800066bb  jmp     loc_1800064AA
0x1800066c0  mov     ecx, r12d
0x1800066c3  mov     [rsp+188h+var_128], ecx
0x1800066c7  cmp     esi, 0Ch
0x1800066ca  jnz     short loc_18000671E
0x1800066cc  test    rbx, rbx
0x1800066cf  jz      short loc_18000671E
0x1800066d1  mov     [rsp+188h+var_108], r12d
0x1800066d9  mov     [rsp+188h+var_118], r12d
0x1800066de  lea     r8, [rsp+188h+var_108]; plLbound
0x1800066e6  mov     edx, 1; nDim
0x1800066eb  mov     rcx, rbx; psa
0x1800066ee  call    cs:__imp_SafeArrayGetLBound
0x1800066f4  lea     r8, [rsp+188h+var_118]; plUbound
0x1800066f9  mov     edx, 1; nDim
0x1800066fe  mov     rcx, rbx; psa
0x180006701  call    cs:__imp_SafeArrayGetUBound
0x180006707  mov     eax, [rsp+188h+var_108]
0x18000670e  dec     eax
0x180006710  mov     ecx, r12d
0x180006713  cmp     [rsp+188h+var_118], eax
0x180006717  setz    cl
  ... truncated ...
```
