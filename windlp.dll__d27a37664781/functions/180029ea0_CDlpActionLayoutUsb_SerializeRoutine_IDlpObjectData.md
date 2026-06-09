# CDlpActionLayoutUsb::SerializeRoutine(IDlpObjectData *)

- ea: `0x180029ea0`
- end: `0x18002a5cc`
- name: `?SerializeRoutine@CDlpActionLayoutUsb@@EEAAJPEAVIDlpObjectData@@@Z`
- size: `1836`
- prototype: `__int64 __fastcall(CDlpActionLayoutUsb *__hidden this, struct IDlpObjectData *)`
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update`

## callees

- `0x18000aba4`
- `0x180012f5c`
- `0x18001fd60`
- `0x180028640`
- `0x180029ea0`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002a598`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002a598`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002a5a7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002a5a7`

## string_xrefs

- `0x18002a2c9`: `LayoutPath`
- `0x18002a046`: `ReconstructionPathCount`
- `0x18002a283`: `BootWimPath`
- `0x18002a30f`: `InstallWimPath`
- `0x18002a355`: `OemWinreWimPath`
- `0x18002a39b`: `CustomizationWimPath`
- `0x18002a427`: `CustomizationWimPath`
- `0x18002a46d`: `OemExtensibilityDirPath`
- `0x18002a4b3`: `AutoApplyDirPath`
- `0x18002a4f6`: `CloudDataPath`
- `0x18002a094`: `ReconstructionPath`
- `0x18002a0ca`: `ReconstructionPath`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CDlpActionLayoutUsb::SerializeRoutine(CDlpActionLayoutUsb *this, struct IDlpObjectData *a2)
{
  unsigned __int16 *v4; // r13
  unsigned int v5; // edi
  __int64 v6; // rcx
  char *v7; // rsi
  int v8; // eax
  int v9; // eax
  int v10; // eax
  int v11; // eax
  int v12; // eax
  int v13; // eax
  int v14; // r14d
  int v15; // eax
  int v16; // eax
  int v17; // eax
  __int64 v18; // rcx
  int v19; // eax
  __int64 v20; // rcx
  __int64 v21; // rcx
  int v22; // eax
  __int64 v23; // rcx
  _QWORD *v24; // rcx
  __int64 v25; // rcx
  int v26; // eax
  __int64 v27; // rcx
  int v28; // eax
  int v29; // eax
  int v30; // eax
  int v31; // eax
  int v32; // eax
  int v33; // eax
  int v34; // eax
  int v35; // eax
  int v36; // eax
  int v37; // eax
  int v38; // eax
  int v39; // eax
  int v40; // eax
  __int64 v41; // rcx
  HANDLE ProcessHeap; // rax
  int v44; // [rsp+20h] [rbp-10h]
  int v45; // [rsp+28h] [rbp-8h]
  _QWORD *v46; // [rsp+78h] [rbp+48h] BYREF
  unsigned __int16 *v47; // [rsp+80h] [rbp+50h] BYREF
  __int64 v48; // [rsp+88h] [rbp+58h]

  v48 = 0;
  v4 = 0;
  v47 = 0;
  if ( !a2 )
  {
    v5 = -2147024809;
    v6 = *((_QWORD *)this + 11);
    if ( !v6 )
      goto LABEL_97;
    v45 = -2147024809;
    v44 = 932;
LABEL_94:
    v40 = CDlpLogT<CEmptyType>::DlpLogFormat(
            v6,
            4,
            L"%s(%d): Result = 0x%X",
            L"CDlpActionLayoutUsb::SerializeRoutine",
            v44,
            v45);
    v41 = (unsigned int)v40;
    if ( v40 < 0 )
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v40);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v41);
    goto LABEL_97;
  }
  v7 = (char *)a2 + 8;
  v8 = (*(__int64 (__fastcall **)(char *, const wchar_t *, _QWORD))(*((_QWORD *)a2 + 1) + 24LL))(
         (char *)a2 + 8,
         L"FileSystemType",
         *((unsigned int *)this + 341));
  v5 = v8;
  if ( v8 < 0 )
  {
    v6 = *((_QWORD *)this + 11);
    if ( !v6 )
      goto LABEL_97;
    v45 = v8;
    v44 = 934;
    goto LABEL_94;
  }
  v9 = (*(__int64 (__fastcall **)(char *, const wchar_t *, _QWORD))(*(_QWORD *)v7 + 24LL))(
         v7,
         L"Flags",
         *((unsigned int *)this + 342));
  v5 = v9;
  if ( v9 < 0 )
  {
    v6 = *((_QWORD *)this + 11);
    if ( !v6 )
      goto LABEL_97;
    v45 = v9;
    v44 = 935;
    goto LABEL_94;
  }
  v10 = (*(__int64 (__fastcall **)(char *, const wchar_t *, _QWORD))(*(_QWORD *)v7 + 32LL))(
          v7,
          L"MaxVolumeSize",
          *((_QWORD *)this + 172));
  v5 = v10;
  if ( v10 < 0 )
  {
    v6 = *((_QWORD *)this + 11);
    if ( !v6 )
      goto LABEL_97;
    v45 = v10;
    v44 = 936;
    goto LABEL_94;
  }
  v11 = (*(__int64 (__fastcall **)(char *, const wchar_t *, _QWORD))(*(_QWORD *)v7 + 32LL))(
          v7,
          L"FileSplitSize",
          *((_QWORD *)this + 173));
  v5 = v11;
  if ( v11 < 0 )
  {
    v6 = *((_QWORD *)this + 11);
    if ( !v6 )
      goto LABEL_97;
    v45 = v11;
    v44 = 937;
    goto LABEL_94;
  }
  v12 = (*(__int64 (__fastcall **)(char *, const wchar_t *, _QWORD))(*(_QWORD *)v7 + 24LL))(
          v7,
          L"UseSimplifiedWimSplit",
          *((unsigned int *)this + 348));
  v5 = v12;
  if ( v12 < 0 )
  {
    v6 = *((_QWORD *)this + 11);
    if ( !v6 )
      goto LABEL_97;
    v45 = v12;
    v44 = 938;
    goto LABEL_94;
  }
  v13 = (*(__int64 (__fastcall **)(char *, const wchar_t *, _QWORD))(*(_QWORD *)v7 + 24LL))(
          v7,
          L"ReconstructionPathCount",
          *((unsigned int *)this + 287));
  v5 = v13;
  if ( v13 < 0 )
  {
    v6 = *((_QWORD *)this + 11);
    if ( !v6 )
      goto LABEL_97;
    v45 = v13;
    v44 = 939;
    goto LABEL_94;
  }
  v14 = 0;
  if ( !*((_DWORD *)this + 287) )
  {
LABEL_28:
    if ( *((_WORD *)this + 680) )
    {
      v17 = STRAPI_Format(&v47, L"%c", *((unsigned __int16 *)this + 680));
      v5 = v17;
      if ( v17 < 0 )
      {
        v18 = *((_QWORD *)this + 11);
        if ( v18 )
        {
          v19 = CDlpLogT<CEmptyType>::DlpLogFormat(
                  v18,
                  4,
                  L"%s(%d): Result = 0x%X",
                  L"CDlpActionLayoutUsb::SerializeRoutine",
                  950,
                  v17);
          v20 = (unsigned int)v19;
          if ( v19 < 0 )
            CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v19);
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v20);
        }
        v4 = v47;
        goto LABEL_97;
      }
      v4 = v47;
      v28 = (*(__int64 (__fastcall **)(char *, const wchar_t *, unsigned __int16 *))(*(_QWORD *)v7 + 40LL))(
              v7,
              L"UsbDriveLetter",
              v47);
      v5 = v28;
      if ( v28 < 0 )
      {
        v6 = *((_QWORD *)this + 11);
        if ( !v6 )
          goto LABEL_97;
        v45 = v28;
        v44 = 951;
        goto LABEL_94;
      }
    }
    if ( *((_QWORD *)this + 110)
      && (v29 = (*(__int64 (__fastcall **)(char *, const wchar_t *))(*(_QWORD *)v7 + 40LL))(v7, L"BootWimPath"),
          v5 = v29,
          v29 < 0) )
    {
      v6 = *((_QWORD *)this + 11);
      if ( !v6 )
        goto LABEL_97;
      v45 = v29;
      v44 = 955;
    }
    else if ( *((_QWORD *)this + 119)
           && (v30 = (*(__int64 (__fastcall **)(char *, const wchar_t *))(*(_QWORD *)v7 + 40LL))(v7, L"LayoutPath"),
               v5 = v30,
               v30 < 0) )
    {
      v6 = *((_QWORD *)this + 11);
      if ( !v6 )
        goto LABEL_97;
      v45 = v30;
      v44 = 959;
    }
    else if ( *((_QWORD *)this + 111)
           && (v31 = (*(__int64 (__fastcall **)(char *, const wchar_t *))(*(_QWORD *)v7 + 40LL))(v7, L"InstallWimPath"),
               v5 = v31,
               v31 < 0) )
    {
      v6 = *((_QWORD *)this + 11);
      if ( !v6 )
        goto LABEL_97;
      v45 = v31;
      v44 = 963;
    }
    else if ( *((_QWORD *)this + 116)
           && (v32 = (*(__int64 (__fastcall **)(char *, const wchar_t *))(*(_QWORD *)v7 + 40LL))(v7, L"OemWinreWimPath"),
               v5 = v32,
               v32 < 0) )
    {
      v6 = *((_QWORD *)this + 11);
      if ( !v6 )
        goto LABEL_97;
      v45 = v32;
      v44 = 967;
    }
    else if ( *((_QWORD *)this + 113)
           && (v33 = (*(__int64 (__fastcall **)(char *, const wchar_t *))(*(_QWORD *)v7 + 40LL))(
                       v7,
                       L"CustomizationWimPath"),
               v5 = v33,
               v33 < 0) )
    {
      v6 = *((_QWORD *)this + 11);
      if ( !v6 )
        goto LABEL_97;
      v45 = v33;
      v44 = 971;
    }
    else if ( *((_QWORD *)this + 118)
           && (v34 = (*(__int64 (__fastcall **)(char *, const wchar_t *))(*(_QWORD *)v7 + 40LL))(
                       v7,
                       L"ReconstructionRoot"),
               v5 = v34,
               v34 < 0) )
    {
      v6 = *((_QWORD *)this + 11);
      if ( !v6 )
        goto LABEL_97;
      v45 = v34;
      v44 = 975;
    }
    else if ( *((_QWORD *)this + 112)
           && (v35 = (*(__int64 (__fastcall **)(char *, const wchar_t *))(*(_QWORD *)v7 + 40LL))(
                       v7,
                       L"CustomizationWimPath"),
               v5 = v35,
               v35 < 0) )
    {
      v6 = *((_QWORD *)this + 11);
      if ( !v6 )
        goto LABEL_97;
      v45 = v35;
      v44 = 979;
    }
    else if ( *((_QWORD *)this + 114)
           && (v36 = (*(__int64 (__fastcall **)(char *, const wchar_t *))(*(_QWORD *)v7 + 40LL))(
                       v7,
                       L"OemExtensibilityDirPath"),
               v5 = v36,
               v36 < 0) )
    {
      v6 = *((_QWORD *)this + 11);
      if ( !v6 )
        goto LABEL_97;
      v45 = v36;
      v44 = 983;
    }
    else if ( *((_QWORD *)this + 115)
           && (v37 = (*(__int64 (__fastcall **)(char *, const wchar_t *))(*(_QWORD *)v7 + 40LL))(
                       v7,
                       L"AutoApplyDirPath"),
               v5 = v37,
               v37 < 0) )
    {
      v6 = *((_QWORD *)this + 11);
      if ( !v6 )
        goto LABEL_97;
      v45 = v37;
      v44 = 987;
    }
    else if ( *((_QWORD *)this + 117)
           && (v38 = (*(__int64 (__fastcall **)(char *, const wchar_t *))(*(_QWORD *)v7 + 40LL))(v7, L"CloudDataPath"),
               v5 = v38,
               v38 < 0) )
    {
      v6 = *((_QWORD *)this + 11);
      if ( !v6 )
        goto LABEL_97;
      v45 = v38;
      v44 = 991;
    }
    else
    {
      if ( !*((_QWORD *)this + 120) )
        goto LABEL_97;
      v39 = (*(__int64 (__fastcall **)(char *, const wchar_t *))(*(_QWORD *)v7 + 40LL))(v7, L"VolumeLabel");
      v5 = v39;
      if ( v39 >= 0 )
        goto LABEL_97;
      v6 = *((_QWORD *)this + 11);
      if ( !v6 )
        goto LABEL_97;
      v45 = v39;
      v44 = 995;
    }
    goto LABEL_94;
  }
  while ( 1 )
  {
    v46 = 0;
    v15 = (*(__int64 (__fastcall **)(struct IDlpObjectData *, const wchar_t *, _QWORD **))(*(_QWORD *)a2 + 24LL))(
            a2,
            L"ReconstructionPath",
            &v46);
    v5 = v15;
    if ( v15 < 0 )
    {
      v25 = *((_QWORD *)this + 11);
      if ( v25 )
      {
        v26 = CDlpLogT<CEmptyType>::DlpLogFormat(
                v25,
                4,
                L"%s(%d): Result = 0x%X",
                L"CDlpActionLayoutUsb::SerializeRoutine",
                944,
                v15);
        v27 = (unsigned int)v26;
        if ( v26 < 0 )
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v26);
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v27);
      }
      v24 = v46;
      if ( v46 )
        goto LABEL_40;
      goto LABEL_97;
    }
    v16 = (*(__int64 (__fastcall **)(_QWORD *, const wchar_t *, _QWORD))(v46[1] + 40LL))(
            v46 + 1,
            L"ReconstructionPath",
            *(_QWORD *)(*((_QWORD *)this + 144) + 8LL * v14));
    v5 = v16;
    if ( v16 < 0 )
      break;
    if ( v46 )
      (*(void (__fastcall **)(_QWORD *))(*v46 + 16LL))(v46);
    if ( (unsigned int)++v14 >= *((_DWORD *)this + 287) )
      goto LABEL_28;
  }
  v21 = *((_QWORD *)this + 11);
  if ( v21 )
  {
    v22 = CDlpLogT<CEmptyType>::DlpLogFormat(
            v21,
            4,
            L"%s(%d): Result = 0x%X",
            L"CDlpActionLayoutUsb::SerializeRoutine",
            945,
            v16);
    v23 = (unsigned int)v22;
    if ( v22 < 0 )
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v22);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v23);
  }
  v24 = v46;
  if ( v46 )
LABEL_40:
    (*(void (__fastcall **)(_QWORD *))(*v46 + 16LL))(v24);
LABEL_97:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v5);
  if ( v4 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v4 - 2);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  return v5;
}

```

## disassembly

```asm
0x180029ea0  mov     [rsp-38h+arg_0], rbx
0x180029ea5  push    rbp
0x180029ea6  push    rsi
0x180029ea7  push    rdi
0x180029ea8  push    r12
0x180029eaa  push    r13
0x180029eac  push    r14
0x180029eae  push    r15
0x180029eb0  mov     rbp, rsp
0x180029eb3  sub     rsp, 30h
0x180029eb7  mov     r15, rdx
0x180029eba  mov     rbx, rcx
0x180029ebd  xor     r12d, r12d
0x180029ec0  mov     [rbp+arg_18], r12
0x180029ec4  mov     r13d, r12d
0x180029ec7  mov     [rbp+arg_10], r12
0x180029ecb  test    rdx, rdx
0x180029ece  jnz     short loc_180029EF3
0x180029ed0  mov     edi, 80070057h
0x180029ed5  mov     rcx, [rcx+58h]
0x180029ed9  test    rcx, rcx
0x180029edc  jz      loc_18002A58B
0x180029ee2  mov     [rsp+30h+var_8], edi
0x180029ee6  mov     [rsp+30h+var_10], 3A4h
0x180029eee  jmp     loc_18002A563
0x180029ef3  lea     rsi, [rdx+8]
0x180029ef7  mov     rax, [rsi]
0x180029efa  mov     r8d, [rcx+554h]
0x180029f01  lea     rdx, aFilesystemtype; "FileSystemType"
0x180029f08  mov     rcx, rsi
0x180029f0b  mov     rax, [rax+18h]
0x180029f0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029f14  mov     edi, eax
0x180029f16  test    eax, eax
0x180029f18  jns     short loc_180029F38
0x180029f1a  mov     rcx, [rbx+58h]
0x180029f1e  test    rcx, rcx
0x180029f21  jz      loc_18002A58B
0x180029f27  mov     [rsp+30h+var_8], eax
0x180029f2b  mov     [rsp+30h+var_10], 3A6h
0x180029f33  jmp     loc_18002A563
0x180029f38  mov     rax, [rsi]
0x180029f3b  mov     r8d, [rbx+558h]
0x180029f42  lea     rdx, aFlags; "Flags"
0x180029f49  mov     rcx, rsi
0x180029f4c  mov     rax, [rax+18h]
0x180029f50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029f55  mov     edi, eax
0x180029f57  test    eax, eax
0x180029f59  jns     short loc_180029F79
0x180029f5b  mov     rcx, [rbx+58h]
0x180029f5f  test    rcx, rcx
0x180029f62  jz      loc_18002A58B
0x180029f68  mov     [rsp+30h+var_8], eax
0x180029f6c  mov     [rsp+30h+var_10], 3A7h
0x180029f74  jmp     loc_18002A563
0x180029f79  mov     rax, [rsi]
0x180029f7c  mov     r8, [rbx+560h]
0x180029f83  lea     rdx, aMaxvolumesize; "MaxVolumeSize"
0x180029f8a  mov     rcx, rsi
0x180029f8d  mov     rax, [rax+20h]
0x180029f91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029f96  mov     edi, eax
0x180029f98  test    eax, eax
0x180029f9a  jns     short loc_180029FBA
0x180029f9c  mov     rcx, [rbx+58h]
0x180029fa0  test    rcx, rcx
0x180029fa3  jz      loc_18002A58B
0x180029fa9  mov     [rsp+30h+var_8], eax
0x180029fad  mov     [rsp+30h+var_10], 3A8h
0x180029fb5  jmp     loc_18002A563
0x180029fba  mov     rax, [rsi]
0x180029fbd  mov     r8, [rbx+568h]
0x180029fc4  lea     rdx, aFilesplitsize; "FileSplitSize"
0x180029fcb  mov     rcx, rsi
0x180029fce  mov     rax, [rax+20h]
0x180029fd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029fd7  mov     edi, eax
0x180029fd9  test    eax, eax
0x180029fdb  jns     short loc_180029FFB
0x180029fdd  mov     rcx, [rbx+58h]
0x180029fe1  test    rcx, rcx
0x180029fe4  jz      loc_18002A58B
0x180029fea  mov     [rsp+30h+var_8], eax
0x180029fee  mov     [rsp+30h+var_10], 3A9h
0x180029ff6  jmp     loc_18002A563
0x180029ffb  mov     rax, [rsi]
0x180029ffe  mov     r8d, [rbx+570h]
0x18002a005  lea     rdx, aUsesimplifiedw; "UseSimplifiedWimSplit"
0x18002a00c  mov     rcx, rsi
0x18002a00f  mov     rax, [rax+18h]
0x18002a013  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a018  mov     edi, eax
0x18002a01a  test    eax, eax
0x18002a01c  jns     short loc_18002A03C
0x18002a01e  mov     rcx, [rbx+58h]
0x18002a022  test    rcx, rcx
0x18002a025  jz      loc_18002A58B
0x18002a02b  mov     [rsp+30h+var_8], eax
0x18002a02f  mov     [rsp+30h+var_10], 3AAh
0x18002a037  jmp     loc_18002A563
0x18002a03c  mov     rax, [rsi]
0x18002a03f  mov     r8d, [rbx+47Ch]
0x18002a046  lea     rdx, aReconstruction_0; "ReconstructionPathCount"
0x18002a04d  mov     rcx, rsi
0x18002a050  mov     rax, [rax+18h]
0x18002a054  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a059  mov     edi, eax
0x18002a05b  test    eax, eax
0x18002a05d  jns     short loc_18002A07D
0x18002a05f  mov     rcx, [rbx+58h]
0x18002a063  test    rcx, rcx
0x18002a066  jz      loc_18002A58B
0x18002a06c  mov     [rsp+30h+var_8], eax
0x18002a070  mov     [rsp+30h+var_10], 3ABh
0x18002a078  jmp     loc_18002A563
0x18002a07d  mov     r14d, r12d
0x18002a080  cmp     [rbx+47Ch], r12d
0x18002a087  jbe     short loc_18002A106
0x18002a089  mov     [rbp+arg_8], r12
0x18002a08d  mov     rax, [r15]
0x18002a090  lea     r8, [rbp+arg_8]
0x18002a094  lea     rdx, aReconstruction_1; "ReconstructionPath"
0x18002a09b  mov     rcx, r15
0x18002a09e  mov     rax, [rax+18h]
0x18002a0a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a0a7  mov     edi, eax
0x18002a0a9  test    eax, eax
0x18002a0ab  js      loc_18002A1D6
0x18002a0b1  mov     rcx, [rbp+arg_8]
0x18002a0b5  add     rcx, 8
0x18002a0b9  mov     rax, [rcx]
0x18002a0bc  mov     r8, [rbx+480h]
0x18002a0c3  movsxd  rdx, r14d
0x18002a0c6  mov     r8, [r8+rdx*8]
0x18002a0ca  lea     rdx, aReconstruction_1; "ReconstructionPath"
0x18002a0d1  mov     rax, [rax+28h]
0x18002a0d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a0da  mov     edi, eax
0x18002a0dc  test    eax, eax
0x18002a0de  js      loc_18002A179
0x18002a0e4  mov     rcx, [rbp+arg_8]
0x18002a0e8  test    rcx, rcx
0x18002a0eb  jz      short loc_18002A0FA
0x18002a0ed  mov     rax, [rcx]
0x18002a0f0  mov     rax, [rax+10h]
0x18002a0f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a0f9  nop
0x18002a0fa  inc     r14d
0x18002a0fd  cmp     r14d, [rbx+47Ch]
0x18002a104  jb      short loc_18002A089
0x18002a106  movzx   eax, word ptr [rbx+550h]
0x18002a10d  test    ax, ax
0x18002a110  jz      loc_18002A274
0x18002a116  mov     r8d, eax
0x18002a119  lea     rdx, aC; "%c"
0x18002a120  lea     rcx, [rbp+arg_10]; unsigned __int16 **
0x18002a124  call    ?STRAPI_Format@@YAJPEAPEAGPEBGZZ; STRAPI_Format(ushort * *,ushort const *,...)
0x18002a129  mov     edi, eax
0x18002a12b  test    eax, eax
0x18002a12d  jns     loc_18002A233
0x18002a133  mov     rcx, [rbx+58h]
0x18002a137  test    rcx, rcx
0x18002a13a  jz      short loc_18002A170
0x18002a13c  mov     [rsp+30h+var_8], eax
0x18002a140  mov     [rsp+30h+var_10], 3B6h
0x18002a148  lea     r9, aCdlpactionlayo_14; "CDlpActionLayoutUsb::SerializeRoutine"
0x18002a14f  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x18002a156  mov     edx, 4
0x18002a15b  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x18002a160  mov     ecx, eax
0x18002a162  test    eax, eax
0x18002a164  jns     short loc_18002A16B
0x18002a166  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18002a16b  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18002a170  mov     r13, [rbp+arg_10]
0x18002a174  jmp     loc_18002A58B
0x18002a179  mov     rcx, [rbx+58h]
0x18002a17d  test    rcx, rcx
0x18002a180  jz      short loc_18002A1B7
0x18002a182  mov     [rsp+30h+var_8], eax
0x18002a186  mov     [rsp+30h+var_10], 3B1h
0x18002a18e  lea     r9, aCdlpactionlayo_14; "CDlpActionLayoutUsb::SerializeRoutine"
0x18002a195  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x18002a19c  mov     edx, 4
0x18002a1a1  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x18002a1a6  mov     ecx, eax
0x18002a1a8  test    eax, eax
0x18002a1aa  jns     short loc_18002A1B1
0x18002a1ac  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18002a1b1  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18002a1b6  nop
0x18002a1b7  mov     rcx, [rbp+arg_8]
0x18002a1bb  test    rcx, rcx
0x18002a1be  jz      loc_18002A58B
0x18002a1c4  mov     rax, [rcx]
0x18002a1c7  mov     rax, [rax+10h]
0x18002a1cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a1d0  nop
0x18002a1d1  jmp     loc_18002A58B
0x18002a1d6  mov     rcx, [rbx+58h]
0x18002a1da  test    rcx, rcx
0x18002a1dd  jz      short loc_18002A214
0x18002a1df  mov     [rsp+30h+var_8], eax
0x18002a1e3  mov     [rsp+30h+var_10], 3B0h
0x18002a1eb  lea     r9, aCdlpactionlayo_14; "CDlpActionLayoutUsb::SerializeRoutine"
0x18002a1f2  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x18002a1f9  mov     edx, 4
0x18002a1fe  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x18002a203  mov     ecx, eax
0x18002a205  test    eax, eax
0x18002a207  jns     short loc_18002A20E
0x18002a209  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18002a20e  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18002a213  nop
0x18002a214  mov     rcx, [rbp+arg_8]
0x18002a218  test    rcx, rcx
0x18002a21b  jz      loc_18002A58B
0x18002a221  mov     rax, [rcx]
0x18002a224  mov     rax, [rax+10h]
0x18002a228  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a22d  nop
0x18002a22e  jmp     loc_18002A58B
0x18002a233  mov     rax, [rsi]
0x18002a236  mov     r13, [rbp+arg_10]
0x18002a23a  mov     r8, r13
0x18002a23d  lea     rdx, aUsbdriveletter; "UsbDriveLetter"
0x18002a244  mov     rcx, rsi
0x18002a247  mov     rax, [rax+28h]
0x18002a24b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a250  mov     edi, eax
0x18002a252  test    eax, eax
0x18002a254  jns     short loc_18002A274
0x18002a256  mov     rcx, [rbx+58h]
0x18002a25a  test    rcx, rcx
0x18002a25d  jz      loc_18002A58B
0x18002a263  mov     [rsp+30h+var_8], eax
0x18002a267  mov     [rsp+30h+var_10], 3B7h
0x18002a26f  jmp     loc_18002A563
0x18002a274  mov     r8, [rbx+370h]
0x18002a27b  test    r8, r8
0x18002a27e  jz      short loc_18002A2BA
0x18002a280  mov     rax, [rsi]
0x18002a283  lea     rdx, aBootwimpath; "BootWimPath"
0x18002a28a  mov     rcx, rsi
0x18002a28d  mov     rax, [rax+28h]
0x18002a291  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a296  mov     edi, eax
0x18002a298  test    eax, eax
0x18002a29a  jns     short loc_18002A2BA
0x18002a29c  mov     rcx, [rbx+58h]
0x18002a2a0  test    rcx, rcx
0x18002a2a3  jz      loc_18002A58B
0x18002a2a9  mov     [rsp+30h+var_8], eax
0x18002a2ad  mov     [rsp+30h+var_10], 3BBh
0x18002a2b5  jmp     loc_18002A563
0x18002a2ba  mov     r8, [rbx+3B8h]
0x18002a2c1  test    r8, r8
0x18002a2c4  jz      short loc_18002A300
0x18002a2c6  mov     rax, [rsi]
0x18002a2c9  lea     rdx, aLayoutpath; "LayoutPath"
0x18002a2d0  mov     rcx, rsi
0x18002a2d3  mov     rax, [rax+28h]
0x18002a2d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a2dc  mov     edi, eax
0x18002a2de  test    eax, eax
0x18002a2e0  jns     short loc_18002A300
0x18002a2e2  mov     rcx, [rbx+58h]
0x18002a2e6  test    rcx, rcx
0x18002a2e9  jz      loc_18002A58B
0x18002a2ef  mov     [rsp+30h+var_8], eax
0x18002a2f3  mov     [rsp+30h+var_10], 3BFh
0x18002a2fb  jmp     loc_18002A563
0x18002a300  mov     r8, [rbx+378h]
0x18002a307  test    r8, r8
0x18002a30a  jz      short loc_18002A346
0x18002a30c  mov     rax, [rsi]
0x18002a30f  lea     rdx, aInstallwimpath; "InstallWimPath"
0x18002a316  mov     rcx, rsi
0x18002a319  mov     rax, [rax+28h]
0x18002a31d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a322  mov     edi, eax
0x18002a324  test    eax, eax
0x18002a326  jns     short loc_18002A346
0x18002a328  mov     rcx, [rbx+58h]
0x18002a32c  test    rcx, rcx
0x18002a32f  jz      loc_18002A58B
0x18002a335  mov     [rsp+30h+var_8], eax
0x18002a339  mov     [rsp+30h+var_10], 3C3h
0x18002a341  jmp     loc_18002A563
0x18002a346  mov     r8, [rbx+3A0h]
0x18002a34d  test    r8, r8
0x18002a350  jz      short loc_18002A38C
0x18002a352  mov     rax, [rsi]
0x18002a355  lea     rdx, aOemwinrewimpat; "OemWinreWimPath"
0x18002a35c  mov     rcx, rsi
0x18002a35f  mov     rax, [rax+28h]
0x18002a363  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a368  mov     edi, eax
0x18002a36a  test    eax, eax
  ... truncated ...
```
