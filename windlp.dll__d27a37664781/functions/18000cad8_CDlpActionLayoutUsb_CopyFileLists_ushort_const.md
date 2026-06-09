# CDlpActionLayoutUsb::CopyFileLists(ushort const *)

- ea: `0x18000cad8`
- end: `0x18000d0f3`
- name: `?CopyFileLists@CDlpActionLayoutUsb@@AEAAJPEBG@Z`
- size: `1563`
- prototype: `__int64 __fastcall(CDlpActionLayoutUsb *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800244d4`

## callees

- `0x18000a088`
- `0x18000aba4`
- `0x18000b9a8`
- `0x18000be9c`
- `0x18000c4d8`
- `0x18000cad8`
- `0x18000d888`
- `0x180012f5c`
- `0x18001fd60`
- `0x180028640`
- `0x180029424`
- `0x18002beb4`
- `0x18002cd9c`
- `0x18007ec76`
- `0x18007ed40`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d08e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d0b0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d08e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d0b0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d09d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d0bf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d09d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d0bf`

## string_xrefs

- `0x18000cf58`: `CDlpActionLayoutUsb::CopyFileLists`
- `0x18000cfee`: `CDlpActionLayoutUsb::CopyFileLists`
- `0x18000d059`: `CDlpActionLayoutUsb::CopyFileLists`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CDlpActionLayoutUsb::CopyFileLists(union _ULARGE_INTEGER *this, const unsigned __int16 *a2)
{
  unsigned __int16 *v4; // r15
  unsigned __int16 *v5; // r13
  unsigned int v6; // edi
  union _ULARGE_INTEGER v7; // rcx
  int v8; // eax
  int v9; // eax
  int v10; // eax
  int v11; // eax
  int v12; // eax
  int v13; // eax
  int v14; // eax
  int v15; // eax
  int v16; // eax
  union _ULARGE_INTEGER *v17; // r8
  union _ULARGE_INTEGER *v18; // rdx
  int v19; // eax
  int v20; // eax
  int v21; // eax
  int v22; // eax
  int v23; // eax
  int v24; // eax
  int v25; // eax
  int v26; // eax
  union _ULARGE_INTEGER v27; // rcx
  int v28; // eax
  __int64 v29; // rcx
  int FolderPath; // eax
  int v31; // eax
  void (*v32)(void *, unsigned __int64, unsigned __int64, int *); // rdx
  union _ULARGE_INTEGER v33; // rcx
  int v34; // eax
  __int64 v35; // rcx
  int v36; // eax
  int v37; // eax
  __int64 v38; // rcx
  HANDLE ProcessHeap; // rax
  HANDLE v40; // rax
  union _ULARGE_INTEGER v42; // [rsp+20h] [rbp-50h]
  __int64 v43; // [rsp+28h] [rbp-48h]
  unsigned __int16 *v44; // [rsp+40h] [rbp-30h] BYREF
  unsigned __int16 *v45; // [rsp+48h] [rbp-28h] BYREF
  __int128 Buf2; // [rsp+50h] [rbp-20h] BYREF

  v4 = 0;
  v44 = 0;
  v5 = 0;
  v45 = 0;
  if ( !a2 )
  {
    v6 = -2147024809;
    v7 = this[11];
    if ( !v7.QuadPart )
      goto LABEL_85;
    LODWORD(v43) = -2147024809;
    v42.LowPart = 1214;
LABEL_82:
    v37 = ((__int64 (*)(_QWORD, _QWORD, _QWORD, ...))CDlpLogT<CEmptyType>::DlpLogFormat)(
            (union _ULARGE_INTEGER)v7.QuadPart,
            4,
            L"%s(%d): Result = 0x%X",
            L"CDlpActionLayoutUsb::CopyFileLists",
            v42.QuadPart,
            v43);
    v38 = (unsigned int)v37;
    if ( v37 < 0 )
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v37);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v38);
    goto LABEL_85;
  }
  Buf2 = 0;
  v8 = (*(__int64 (__fastcall **)(union _ULARGE_INTEGER *, __int128 *))(this->QuadPart + 56))(this, &Buf2);
  v6 = v8;
  if ( v8 < 0 )
  {
    v7 = this[11];
    if ( !v7.QuadPart )
      goto LABEL_85;
    LODWORD(v43) = v8;
    v42.LowPart = 1218;
    goto LABEL_82;
  }
  if ( !memcmp_0(&WINDLP_ACTION_RECOVERUSB, &Buf2, 0x10u) )
  {
    v9 = CDlpActionLayoutUsb::CopyBootFiles((CDlpActionLayoutUsb *)this, a2);
    v6 = v9;
    if ( v9 < 0 )
    {
      v7 = this[11];
      if ( !v7.QuadPart )
        goto LABEL_85;
      LODWORD(v43) = v9;
      v42.LowPart = 1221;
      goto LABEL_82;
    }
  }
  if ( this[121].HighPart )
  {
    v10 = CDlpActionLayoutUsb::SendActionMessage(this, 15);
    v6 = v10;
    if ( v10 < 0 )
    {
      v7 = this[11];
      if ( !v7.QuadPart )
        goto LABEL_85;
      LODWORD(v43) = v10;
      v42.LowPart = 1226;
      goto LABEL_82;
    }
    v11 = CDlpActionLayoutUsb::CopyFileList((__int64)this, (__int64)&this[121], (__int64)&this[123], (__int64)a2);
    v6 = v11;
    if ( v11 < 0 )
    {
      v7 = this[11];
      if ( !v7.QuadPart )
        goto LABEL_85;
      LODWORD(v43) = v11;
      v42.LowPart = 1227;
      goto LABEL_82;
    }
  }
  if ( this[125].HighPart )
  {
    v12 = CDlpActionLayoutUsb::SendActionMessage(this, 13);
    v6 = v12;
    if ( v12 < 0 )
    {
      v7 = this[11];
      if ( !v7.QuadPart )
        goto LABEL_85;
      LODWORD(v43) = v12;
      v42.LowPart = 1232;
      goto LABEL_82;
    }
    v13 = CDlpActionLayoutUsb::CopyFileList((__int64)this, (__int64)&this[125], (__int64)&this[127], (__int64)a2);
    v6 = v13;
    if ( v13 < 0 )
    {
      v7 = this[11];
      if ( !v7.QuadPart )
        goto LABEL_85;
      LODWORD(v43) = v13;
      v42.LowPart = 1233;
      goto LABEL_82;
    }
  }
  if ( this[129].HighPart )
  {
    if ( this[173].QuadPart )
    {
      v16 = CDlpActionLayoutUsb::SendActionMessage(this, 17);
      v6 = v16;
      if ( v16 < 0 )
      {
        v7 = this[11];
        if ( !v7.QuadPart )
          goto LABEL_85;
        LODWORD(v43) = v16;
        v42.LowPart = 1245;
        goto LABEL_82;
      }
      v17 = this + 131;
      v18 = this + 129;
      if ( this[174].LowPart )
      {
        v19 = CDlpActionLayoutUsb::SplitFileList(this, (__int64)v18, (__int64)v17, (__int64)a2);
        v6 = v19;
        if ( v19 < 0 )
        {
          v7 = this[11];
          if ( !v7.QuadPart )
            goto LABEL_85;
          LODWORD(v43) = v19;
          v42.LowPart = 1248;
          goto LABEL_82;
        }
      }
      else
      {
        v20 = CDlpActionLayoutUsb::SplitWimList((char *)this, (__int64)v18, (__int64)v17, (__int64)a2);
        v6 = v20;
        if ( v20 < 0 )
        {
          v7 = this[11];
          if ( !v7.QuadPart )
            goto LABEL_85;
          LODWORD(v43) = v20;
          v42.LowPart = 1252;
          goto LABEL_82;
        }
      }
    }
    else
    {
      v14 = CDlpActionLayoutUsb::SendActionMessage(this, 14);
      v6 = v14;
      if ( v14 < 0 )
      {
        v7 = this[11];
        if ( !v7.QuadPart )
          goto LABEL_85;
        LODWORD(v43) = v14;
        v42.LowPart = 1240;
        goto LABEL_82;
      }
      v15 = CDlpActionLayoutUsb::CopyFileList((__int64)this, (__int64)&this[129], (__int64)&this[131], (__int64)a2);
      v6 = v15;
      if ( v15 < 0 )
      {
        v7 = this[11];
        if ( !v7.QuadPart )
          goto LABEL_85;
        LODWORD(v43) = v15;
        v42.LowPart = 1241;
        goto LABEL_82;
      }
    }
  }
  if ( this[133].HighPart || this[137].HighPart )
  {
    v21 = CDlpActionLayoutUsb::SendActionMessage(this, 16);
    v6 = v21;
    if ( v21 < 0 )
    {
      v7 = this[11];
      if ( !v7.QuadPart )
        goto LABEL_85;
      LODWORD(v43) = v21;
      v42.LowPart = 1259;
      goto LABEL_82;
    }
    if ( this[133].HighPart )
    {
      v22 = CDlpActionLayoutUsb::CopyFileList((__int64)this, (__int64)&this[133], (__int64)&this[135], (__int64)a2);
      v6 = v22;
      if ( v22 < 0 )
      {
        v7 = this[11];
        if ( !v7.QuadPart )
          goto LABEL_85;
        LODWORD(v43) = v22;
        v42.LowPart = 1263;
        goto LABEL_82;
      }
    }
    if ( this[137].HighPart )
    {
      v23 = CDlpActionLayoutUsb::SplitFileList(this, (__int64)&this[137], (__int64)&this[139], (__int64)a2);
      v6 = v23;
      if ( v23 < 0 )
      {
        v7 = this[11];
        if ( !v7.QuadPart )
          goto LABEL_85;
        LODWORD(v43) = v23;
        v42.LowPart = 1268;
        goto LABEL_82;
      }
    }
  }
  if ( this[145].HighPart )
  {
    v24 = CDlpActionLayoutUsb::CopyFileList((__int64)this, (__int64)&this[145], (__int64)&this[147], (__int64)a2);
    v6 = v24;
    if ( v24 < 0 )
    {
      v7 = this[11];
      if ( !v7.QuadPart )
        goto LABEL_85;
      LODWORD(v43) = v24;
      v42.LowPart = 1274;
      goto LABEL_82;
    }
  }
  if ( !this[169].QuadPart )
    goto LABEL_85;
  v25 = CDlpActionLayoutUsb::SendActionMessage(this, 18);
  v6 = v25;
  if ( v25 < 0 )
  {
    v7 = this[11];
    if ( !v7.QuadPart )
      goto LABEL_85;
    LODWORD(v43) = v25;
    v42.LowPart = 1279;
    goto LABEL_82;
  }
  v26 = STRAPI_Format(&v44, L"%c:\\sources", LOWORD(this[170].QuadPart));
  v6 = v26;
  if ( v26 >= 0 )
  {
    v4 = v44;
    FolderPath = CMiscHelpersT<CEmptyType>::CreateFolderPath(v44);
    v6 = FolderPath;
    if ( FolderPath < 0 )
    {
      v7 = this[11];
      if ( !v7.QuadPart )
        goto LABEL_85;
      LODWORD(v43) = FolderPath;
      v42.LowPart = 1282;
      goto LABEL_82;
    }
    v31 = CMiscHelpersT<CEmptyType>::CombinePath(v4, L"Reconstruct", L"WIM", &v45);
    v6 = v31;
    if ( v31 >= 0 )
    {
      v5 = v45;
      v36 = CDlpWimCapture::Capture((CDlpWimCapture *)&this[149], v32, this, v45, this[173], v43);
      v6 = v36;
      if ( v36 >= 0 )
        goto LABEL_85;
      v7 = this[11];
      if ( !v7.QuadPart )
        goto LABEL_85;
      LODWORD(v43) = v36;
      v42.LowPart = 1291;
      goto LABEL_82;
    }
    v33 = this[11];
    if ( v33.QuadPart )
    {
      v34 = ((__int64 (*)(_QWORD, _QWORD, _QWORD, ...))CDlpLogT<CEmptyType>::DlpLogFormat)(
              (union _ULARGE_INTEGER)v33.QuadPart,
              4,
              L"%s(%d): Result = 0x%X",
              L"CDlpActionLayoutUsb::CopyFileLists",
              1284,
              v31);
      v35 = (unsigned int)v34;
      if ( v34 < 0 )
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v34);
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v35);
    }
    v5 = v45;
  }
  else
  {
    v27 = this[11];
    if ( v27.QuadPart )
    {
      v28 = ((__int64 (*)(_QWORD, _QWORD, _QWORD, ...))CDlpLogT<CEmptyType>::DlpLogFormat)(
              (union _ULARGE_INTEGER)v27.QuadPart,
              4,
              L"%s(%d): Result = 0x%X",
              L"CDlpActionLayoutUsb::CopyFileLists",
              1281,
              v26);
      v29 = (unsigned int)v28;
      if ( v28 < 0 )
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v28);
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v29);
    }
    v4 = v44;
  }
LABEL_85:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v6);
  if ( v5 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v5 - 2);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  if ( v4 )
  {
    v40 = GetProcessHeap();
    HeapFree(v40, 0, v4 - 2);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  return v6;
}

```

## disassembly

```asm
0x18000cad8  mov     [rsp-28h+arg_10], rbx
0x18000cadd  mov     [rsp-28h+arg_18], rsi
0x18000cae2  push    rbp
0x18000cae3  push    rdi
0x18000cae4  push    r13
0x18000cae6  push    r14
0x18000cae8  push    r15
0x18000caea  mov     rbp, rsp
0x18000caed  sub     rsp, 70h
0x18000caf1  mov     rax, cs:__security_cookie
0x18000caf8  xor     rax, rsp
0x18000cafb  mov     [rbp+var_10], rax
0x18000caff  mov     rsi, rdx
0x18000cb02  mov     rbx, rcx
0x18000cb05  xor     r15d, r15d
0x18000cb08  mov     [rbp+var_30], r15
0x18000cb0c  xor     r13d, r13d
0x18000cb0f  mov     [rbp+var_28], r13
0x18000cb13  test    rdx, rdx
0x18000cb16  jnz     short loc_18000CB3B
0x18000cb18  mov     edi, 80070057h
0x18000cb1d  mov     rcx, [rcx+58h]
0x18000cb21  test    rcx, rcx
0x18000cb24  jz      loc_18000D081
0x18000cb2a  mov     dword ptr [rsp+70h+var_48], edi
0x18000cb2e  mov     dword ptr [rsp+70h+var_50], 4BEh
0x18000cb36  jmp     loc_18000D059
0x18000cb3b  xorps   xmm0, xmm0
0x18000cb3e  movups  [rbp+Buf2], xmm0
0x18000cb42  mov     rax, [rcx]
0x18000cb45  lea     rdx, [rbp+Buf2]
0x18000cb49  mov     rax, [rax+38h]
0x18000cb4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cb52  mov     edi, eax
0x18000cb54  test    eax, eax
0x18000cb56  jns     short loc_18000CB76
0x18000cb58  mov     rcx, [rbx+58h]
0x18000cb5c  test    rcx, rcx
0x18000cb5f  jz      loc_18000D081
0x18000cb65  mov     dword ptr [rsp+70h+var_48], eax
0x18000cb69  mov     dword ptr [rsp+70h+var_50], 4C2h
0x18000cb71  jmp     loc_18000D059
0x18000cb76  mov     r8d, 10h; Size
0x18000cb7c  lea     rdx, [rbp+Buf2]; Buf2
0x18000cb80  lea     rcx, WINDLP_ACTION_RECOVERUSB; Buf1
0x18000cb87  call    memcmp_0
0x18000cb8c  test    eax, eax
0x18000cb8e  jnz     short loc_18000CBBF
0x18000cb90  mov     rdx, rsi; unsigned __int16 *
0x18000cb93  mov     rcx, rbx; this
0x18000cb96  call    ?CopyBootFiles@CDlpActionLayoutUsb@@AEAAJPEBG@Z; CDlpActionLayoutUsb::CopyBootFiles(ushort const *)
0x18000cb9b  mov     edi, eax
0x18000cb9d  test    eax, eax
0x18000cb9f  jns     short loc_18000CBBF
0x18000cba1  mov     rcx, [rbx+58h]
0x18000cba5  test    rcx, rcx
0x18000cba8  jz      loc_18000D081
0x18000cbae  mov     dword ptr [rsp+70h+var_48], eax
0x18000cbb2  mov     dword ptr [rsp+70h+var_50], 4C5h
0x18000cbba  jmp     loc_18000D059
0x18000cbbf  lea     r14, [rbx+3C8h]
0x18000cbc6  cmp     dword ptr [r14+4], 0
0x18000cbcb  jz      short loc_18000CC37
0x18000cbcd  mov     edx, 0Fh
0x18000cbd2  mov     rcx, rbx
0x18000cbd5  call    ?SendActionMessage@CDlpActionLayoutUsb@@AEAAJW4LAYOUTUSB_ACTION@@@Z; CDlpActionLayoutUsb::SendActionMessage(LAYOUTUSB_ACTION)
0x18000cbda  mov     edi, eax
0x18000cbdc  test    eax, eax
0x18000cbde  jns     short loc_18000CBFE
0x18000cbe0  mov     rcx, [rbx+58h]
0x18000cbe4  test    rcx, rcx
0x18000cbe7  jz      loc_18000D081
0x18000cbed  mov     dword ptr [rsp+70h+var_48], eax
0x18000cbf1  mov     dword ptr [rsp+70h+var_50], 4CAh
0x18000cbf9  jmp     loc_18000D059
0x18000cbfe  lea     r8, [rbx+3D8h]
0x18000cc05  mov     r9, rsi
0x18000cc08  mov     rdx, r14
0x18000cc0b  mov     rcx, rbx
0x18000cc0e  call    ?CopyFileList@CDlpActionLayoutUsb@@AEAAJPEAV?$CArray@VDH_SSTRING@@V1@VCAdaptorDefault@@VCPoliciesDefault@@@@0PEBG@Z; CDlpActionLayoutUsb::CopyFileList(CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault> *,CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault> *,ushort const *)
0x18000cc13  mov     edi, eax
0x18000cc15  test    eax, eax
0x18000cc17  jns     short loc_18000CC37
0x18000cc19  mov     rcx, [rbx+58h]
0x18000cc1d  test    rcx, rcx
0x18000cc20  jz      loc_18000D081
0x18000cc26  mov     dword ptr [rsp+70h+var_48], eax
0x18000cc2a  mov     dword ptr [rsp+70h+var_50], 4CBh
0x18000cc32  jmp     loc_18000D059
0x18000cc37  lea     r14, [rbx+3E8h]
0x18000cc3e  cmp     dword ptr [r14+4], 0
0x18000cc43  jz      short loc_18000CCAF
0x18000cc45  mov     edx, 0Dh
0x18000cc4a  mov     rcx, rbx
0x18000cc4d  call    ?SendActionMessage@CDlpActionLayoutUsb@@AEAAJW4LAYOUTUSB_ACTION@@@Z; CDlpActionLayoutUsb::SendActionMessage(LAYOUTUSB_ACTION)
0x18000cc52  mov     edi, eax
0x18000cc54  test    eax, eax
0x18000cc56  jns     short loc_18000CC76
0x18000cc58  mov     rcx, [rbx+58h]
0x18000cc5c  test    rcx, rcx
0x18000cc5f  jz      loc_18000D081
0x18000cc65  mov     dword ptr [rsp+70h+var_48], eax
0x18000cc69  mov     dword ptr [rsp+70h+var_50], 4D0h
0x18000cc71  jmp     loc_18000D059
0x18000cc76  lea     r8, [rbx+3F8h]
0x18000cc7d  mov     r9, rsi
0x18000cc80  mov     rdx, r14
0x18000cc83  mov     rcx, rbx
0x18000cc86  call    ?CopyFileList@CDlpActionLayoutUsb@@AEAAJPEAV?$CArray@VDH_SSTRING@@V1@VCAdaptorDefault@@VCPoliciesDefault@@@@0PEBG@Z; CDlpActionLayoutUsb::CopyFileList(CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault> *,CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault> *,ushort const *)
0x18000cc8b  mov     edi, eax
0x18000cc8d  test    eax, eax
0x18000cc8f  jns     short loc_18000CCAF
0x18000cc91  mov     rcx, [rbx+58h]
0x18000cc95  test    rcx, rcx
0x18000cc98  jz      loc_18000D081
0x18000cc9e  mov     dword ptr [rsp+70h+var_48], eax
0x18000cca2  mov     dword ptr [rsp+70h+var_50], 4D1h
0x18000ccaa  jmp     loc_18000D059
0x18000ccaf  lea     r14, [rbx+408h]
0x18000ccb6  cmp     dword ptr [r14+4], 0
0x18000ccbb  jz      loc_18000CDD2
0x18000ccc1  mov     rcx, rbx
0x18000ccc4  cmp     qword ptr [rbx+568h], 0
0x18000cccc  jnz     short loc_18000CD39
0x18000ccce  mov     edx, 0Eh
0x18000ccd3  call    ?SendActionMessage@CDlpActionLayoutUsb@@AEAAJW4LAYOUTUSB_ACTION@@@Z; CDlpActionLayoutUsb::SendActionMessage(LAYOUTUSB_ACTION)
0x18000ccd8  mov     edi, eax
0x18000ccda  test    eax, eax
0x18000ccdc  jns     short loc_18000CCFC
0x18000ccde  mov     rcx, [rbx+58h]
0x18000cce2  test    rcx, rcx
0x18000cce5  jz      loc_18000D081
0x18000cceb  mov     dword ptr [rsp+70h+var_48], eax
0x18000ccef  mov     dword ptr [rsp+70h+var_50], 4D8h
0x18000ccf7  jmp     loc_18000D059
0x18000ccfc  lea     r8, [rbx+418h]
0x18000cd03  mov     r9, rsi
0x18000cd06  mov     rdx, r14
0x18000cd09  mov     rcx, rbx
0x18000cd0c  call    ?CopyFileList@CDlpActionLayoutUsb@@AEAAJPEAV?$CArray@VDH_SSTRING@@V1@VCAdaptorDefault@@VCPoliciesDefault@@@@0PEBG@Z; CDlpActionLayoutUsb::CopyFileList(CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault> *,CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault> *,ushort const *)
0x18000cd11  mov     edi, eax
0x18000cd13  test    eax, eax
0x18000cd15  jns     loc_18000CDD2
0x18000cd1b  mov     rcx, [rbx+58h]
0x18000cd1f  test    rcx, rcx
0x18000cd22  jz      loc_18000D081
0x18000cd28  mov     dword ptr [rsp+70h+var_48], eax
0x18000cd2c  mov     dword ptr [rsp+70h+var_50], 4D9h
0x18000cd34  jmp     loc_18000D059
0x18000cd39  mov     edx, 11h
0x18000cd3e  call    ?SendActionMessage@CDlpActionLayoutUsb@@AEAAJW4LAYOUTUSB_ACTION@@@Z; CDlpActionLayoutUsb::SendActionMessage(LAYOUTUSB_ACTION)
0x18000cd43  mov     edi, eax
0x18000cd45  test    eax, eax
0x18000cd47  jns     short loc_18000CD67
0x18000cd49  mov     rcx, [rbx+58h]
0x18000cd4d  test    rcx, rcx
0x18000cd50  jz      loc_18000D081
0x18000cd56  mov     dword ptr [rsp+70h+var_48], eax
0x18000cd5a  mov     dword ptr [rsp+70h+var_50], 4DDh
0x18000cd62  jmp     loc_18000D059
0x18000cd67  lea     r8, [rbx+418h]
0x18000cd6e  mov     r9, rsi
0x18000cd71  mov     rdx, r14
0x18000cd74  mov     rcx, rbx; lpParameter
0x18000cd77  cmp     dword ptr [rbx+570h], 0
0x18000cd7e  jz      short loc_18000CDA9
0x18000cd80  call    ?SplitFileList@CDlpActionLayoutUsb@@AEAAJPEAV?$CArray@VDH_SSTRING@@V1@VCAdaptorDefault@@VCPoliciesDefault@@@@0PEBG@Z; CDlpActionLayoutUsb::SplitFileList(CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault> *,CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault> *,ushort const *)
0x18000cd85  mov     edi, eax
0x18000cd87  test    eax, eax
0x18000cd89  jns     short loc_18000CDD2
0x18000cd8b  mov     rcx, [rbx+58h]
0x18000cd8f  test    rcx, rcx
0x18000cd92  jz      loc_18000D081
0x18000cd98  mov     dword ptr [rsp+70h+var_48], eax
0x18000cd9c  mov     dword ptr [rsp+70h+var_50], 4E0h
0x18000cda4  jmp     loc_18000D059
0x18000cda9  call    ?SplitWimList@CDlpActionLayoutUsb@@AEAAJPEAV?$CArray@VDH_SSTRING@@V1@VCAdaptorDefault@@VCPoliciesDefault@@@@0PEBG@Z; CDlpActionLayoutUsb::SplitWimList(CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault> *,CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault> *,ushort const *)
0x18000cdae  mov     edi, eax
0x18000cdb0  test    eax, eax
0x18000cdb2  jns     short loc_18000CDD2
0x18000cdb4  mov     rcx, [rbx+58h]
0x18000cdb8  test    rcx, rcx
0x18000cdbb  jz      loc_18000D081
0x18000cdc1  mov     dword ptr [rsp+70h+var_48], eax
0x18000cdc5  mov     dword ptr [rsp+70h+var_50], 4E4h
0x18000cdcd  jmp     loc_18000D059
0x18000cdd2  lea     r14, [rbx+428h]
0x18000cdd9  cmp     dword ptr [r14+4], 0
0x18000cdde  jnz     short loc_18000CDED
0x18000cde0  cmp     dword ptr [rbx+44Ch], 0
0x18000cde7  jz      loc_18000CEA3
0x18000cded  mov     edx, 10h
0x18000cdf2  mov     rcx, rbx
0x18000cdf5  call    ?SendActionMessage@CDlpActionLayoutUsb@@AEAAJW4LAYOUTUSB_ACTION@@@Z; CDlpActionLayoutUsb::SendActionMessage(LAYOUTUSB_ACTION)
0x18000cdfa  mov     edi, eax
0x18000cdfc  test    eax, eax
0x18000cdfe  jns     short loc_18000CE1E
0x18000ce00  mov     rcx, [rbx+58h]
0x18000ce04  test    rcx, rcx
0x18000ce07  jz      loc_18000D081
0x18000ce0d  mov     dword ptr [rsp+70h+var_48], eax
0x18000ce11  mov     dword ptr [rsp+70h+var_50], 4EBh
0x18000ce19  jmp     loc_18000D059
0x18000ce1e  cmp     dword ptr [rbx+42Ch], 0
0x18000ce25  jz      short loc_18000CE60
0x18000ce27  lea     r8, [rbx+438h]
0x18000ce2e  mov     r9, rsi
0x18000ce31  mov     rdx, r14
0x18000ce34  mov     rcx, rbx
0x18000ce37  call    ?CopyFileList@CDlpActionLayoutUsb@@AEAAJPEAV?$CArray@VDH_SSTRING@@V1@VCAdaptorDefault@@VCPoliciesDefault@@@@0PEBG@Z; CDlpActionLayoutUsb::CopyFileList(CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault> *,CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault> *,ushort const *)
0x18000ce3c  mov     edi, eax
0x18000ce3e  test    eax, eax
0x18000ce40  jns     short loc_18000CE60
0x18000ce42  mov     rcx, [rbx+58h]
0x18000ce46  test    rcx, rcx
0x18000ce49  jz      loc_18000D081
0x18000ce4f  mov     dword ptr [rsp+70h+var_48], eax
0x18000ce53  mov     dword ptr [rsp+70h+var_50], 4EFh
0x18000ce5b  jmp     loc_18000D059
0x18000ce60  lea     rdx, [rbx+448h]
0x18000ce67  cmp     dword ptr [rdx+4], 0
0x18000ce6b  jz      short loc_18000CEA3
0x18000ce6d  lea     r8, [rbx+458h]
0x18000ce74  mov     r9, rsi
0x18000ce77  mov     rcx, rbx
0x18000ce7a  call    ?SplitFileList@CDlpActionLayoutUsb@@AEAAJPEAV?$CArray@VDH_SSTRING@@V1@VCAdaptorDefault@@VCPoliciesDefault@@@@0PEBG@Z; CDlpActionLayoutUsb::SplitFileList(CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault> *,CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault> *,ushort const *)
0x18000ce7f  mov     edi, eax
0x18000ce81  test    eax, eax
0x18000ce83  jns     short loc_18000CEA3
0x18000ce85  mov     rcx, [rbx+58h]
0x18000ce89  test    rcx, rcx
0x18000ce8c  jz      loc_18000D081
0x18000ce92  mov     dword ptr [rsp+70h+var_48], eax
0x18000ce96  mov     dword ptr [rsp+70h+var_50], 4F4h
0x18000ce9e  jmp     loc_18000D059
0x18000cea3  lea     rdx, [rbx+488h]
0x18000ceaa  cmp     dword ptr [rdx+4], 0
0x18000ceae  jz      short loc_18000CEE6
0x18000ceb0  lea     r8, [rbx+498h]
0x18000ceb7  mov     r9, rsi
0x18000ceba  mov     rcx, rbx
0x18000cebd  call    ?CopyFileList@CDlpActionLayoutUsb@@AEAAJPEAV?$CArray@VDH_SSTRING@@V1@VCAdaptorDefault@@VCPoliciesDefault@@@@0PEBG@Z; CDlpActionLayoutUsb::CopyFileList(CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault> *,CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault> *,ushort const *)
0x18000cec2  mov     edi, eax
0x18000cec4  test    eax, eax
0x18000cec6  jns     short loc_18000CEE6
0x18000cec8  mov     rcx, [rbx+58h]
0x18000cecc  test    rcx, rcx
0x18000cecf  jz      loc_18000D081
0x18000ced5  mov     dword ptr [rsp+70h+var_48], eax
0x18000ced9  mov     dword ptr [rsp+70h+var_50], 4FAh
0x18000cee1  jmp     loc_18000D059
0x18000cee6  cmp     qword ptr [rbx+548h], 0
0x18000ceee  jz      loc_18000D081
0x18000cef4  mov     edx, 12h
0x18000cef9  mov     rcx, rbx
0x18000cefc  call    ?SendActionMessage@CDlpActionLayoutUsb@@AEAAJW4LAYOUTUSB_ACTION@@@Z; CDlpActionLayoutUsb::SendActionMessage(LAYOUTUSB_ACTION)
0x18000cf01  mov     edi, eax
0x18000cf03  test    eax, eax
0x18000cf05  jns     short loc_18000CF25
0x18000cf07  mov     rcx, [rbx+58h]
0x18000cf0b  test    rcx, rcx
0x18000cf0e  jz      loc_18000D081
0x18000cf14  mov     dword ptr [rsp+70h+var_48], eax
0x18000cf18  mov     dword ptr [rsp+70h+var_50], 4FFh
0x18000cf20  jmp     loc_18000D059
0x18000cf25  movzx   r8d, word ptr [rbx+550h]
0x18000cf2d  lea     rdx, aCSources; "%c:\\sources"
0x18000cf34  lea     rcx, [rbp+var_30]; unsigned __int16 **
0x18000cf38  call    ?STRAPI_Format@@YAJPEAPEAGPEBGZZ; STRAPI_Format(ushort * *,ushort const *,...)
0x18000cf3d  mov     edi, eax
0x18000cf3f  test    eax, eax
0x18000cf41  jns     short loc_18000CF89
0x18000cf43  mov     rcx, [rbx+58h]
0x18000cf47  test    rcx, rcx
0x18000cf4a  jz      short loc_18000CF80
0x18000cf4c  mov     dword ptr [rsp+70h+var_48], eax
0x18000cf50  mov     dword ptr [rsp+70h+var_50], 501h
0x18000cf58  lea     r9, aCdlpactionlayo_10; "CDlpActionLayoutUsb::CopyFileLists"
0x18000cf5f  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x18000cf66  mov     edx, 4
0x18000cf6b  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x18000cf70  mov     ecx, eax
0x18000cf72  test    eax, eax
0x18000cf74  jns     short loc_18000CF7B
0x18000cf76  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18000cf7b  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18000cf80  mov     r15, [rbp+var_30]
0x18000cf84  jmp     loc_18000D081
0x18000cf89  mov     r15, [rbp+var_30]
0x18000cf8d  mov     rcx, r15
0x18000cf90  call    ?CreateFolderPath@?$CMiscHelpersT@VCEmptyType@@@@SAJPEBGPEAU_SECURITY_ATTRIBUTES@@@Z; CMiscHelpersT<CEmptyType>::CreateFolderPath(ushort const *,_SECURITY_ATTRIBUTES *)
0x18000cf95  mov     edi, eax
0x18000cf97  test    eax, eax
0x18000cf99  jns     short loc_18000CFB9
0x18000cf9b  mov     rcx, [rbx+58h]
0x18000cf9f  test    rcx, rcx
0x18000cfa2  jz      loc_18000D081
0x18000cfa8  mov     dword ptr [rsp+70h+var_48], eax
0x18000cfac  mov     dword ptr [rsp+70h+var_50], 502h
0x18000cfb4  jmp     loc_18000D059
  ... truncated ...
```
