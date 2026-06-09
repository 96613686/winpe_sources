# FillICMPropertyFromRegistry(IWiaPropertyStorage *,CWiaItem *)

- ea: `0x1800587e4`
- end: `0x180058d78`
- name: `?FillICMPropertyFromRegistry@@YAJPEAUIWiaPropertyStorage@@PEAVCWiaItem@@@Z`
- size: `1428`
- prototype: `int(struct IWiaPropertyStorage *, struct CWiaItem *)`
- caller_count: `2`
- callee_count: `21`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800453c0`
- `0x1800651c4`

## callees

- `0x18000b6a0`
- `0x18000c7c0`
- `0x18000cba0`
- `0x18000d770`
- `0x18000d7b0`
- `0x18000da10`
- `0x18000dd00`
- `0x18000f4fc`
- `0x180011a94`
- `0x18002c868`
- `0x18002c8b0`
- `0x18002de18`
- `0x18002def8`
- `0x18002e9d8`
- `0x18002eab4`
- `0x180033cc0`
- `0x180034658`
- `0x18003d888`
- `0x1800587e4`
- `0x180059ed4`
- `0x180078010`

## import_xrefs

- `KERNEL32!LocalFree` at `0x180058b19`
- `KERNEL32!LocalFree` at `0x180058b19`
- `KERNEL32!LocalAlloc` at `0x180058a0b`
- `KERNEL32!LocalAlloc` at `0x180058a0b`
- `mscms!GetStandardColorSpaceProfileW` at `0x180058c87`
- `mscms!GetStandardColorSpaceProfileW` at `0x180058c87`

## string_xrefs

- `0x18005881c`: `::FillICMPropertyFromRegistry`
- `0x180058ad1`: `FillICMPropertyFromRegistry, could not get ICM profile value!`
- `0x180058af5`: `FillICMPropertyFromRegistry, could not get ICM profile value!`
- `0x180058828`: `FillICMPropertyFromRegistry`
- `0x180058bce`: `Failed trying to read ICM color profile for NULL driver wrapper`
- `0x180058bf0`: `Failed trying to read ICM color profile for NULL driver wrapper`
- `0x180058b4f`: `FillICMPropertyFromRegistry, could not get ICM profile size!`
- `0x180058b73`: `FillICMPropertyFromRegistry, could not get ICM profile size!`
- `0x180058ca6`: `FillICMPropertyFromRegistry, using default color space profile`
- `0x180058cce`: `FillICMPropertyFromRegistry, using default color space profile`

## pseudocode

```c
__int64 __fastcall FillICMPropertyFromRegistry(struct IWiaPropertyStorage *a1, struct IWiaItem *a2)
{
  char ***v4; // rax
  char *v5; // rdx
  __int64 v6; // r8
  char *v7; // rbx
  void *v8; // rdx
  void **v9; // rax
  void *v10; // rdx
  __int64 v11; // rcx
  int RootObject; // edi
  char *v13; // rbx
  void *v14; // rdx
  void **v15; // rax
  void *v16; // rdx
  __int64 v17; // rcx
  struct IWiaItemVtbl *lpVtbl; // rdi
  void (__fastcall *v20)(struct IWiaItemVtbl *, _QWORD *, WCHAR *, char *, _QWORD, SIZE_T *); // rbx
  struct IWiaItemVtbl *v21; // r14
  struct IWiaItemVtbl *v22; // rdi
  __int64 (__fastcall *v23)(struct IWiaItemVtbl *, _QWORD *, WCHAR *, char *, struct IWiaItemVtbl *, SIZE_T *); // rbx
  char *v24; // rbx
  void *v25; // rdx
  void **v26; // rax
  void *v27; // rdx
  __int64 v28; // rcx
  char *v29; // rbx
  void *v30; // rdx
  void **v31; // rax
  void *v32; // rdx
  __int64 v33; // rcx
  char *v34; // rbx
  void *v35; // rdx
  int v36; // r9d
  char *v37; // rbx
  void *v38; // rdx
  char *v39; // rbx
  void *v40; // rdx
  void **v41; // rax
  void *v42; // rdx
  __int64 v43; // rcx
  struct CWiaItem *v44; // r14
  const WCHAR *v45; // rcx
  char *v46; // rbx
  void *v47; // rdx
  void **v48; // rax
  void *v49; // rdx
  __int64 v50; // rcx
  char *v51; // rbx
  void *v52; // rdx
  void **v53; // rax
  void *v54; // rdx
  __int64 v55; // rcx
  char *v56; // rbx
  void *v57; // rdx
  unsigned int lpMem; // [rsp+20h] [rbp-E0h]
  SIZE_T uBytes; // [rsp+40h] [rbp-C0h] BYREF
  int v60; // [rsp+48h] [rbp-B8h] BYREF
  struct CWiaItem *v61; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v62[80]; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v63[34]; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v64; // [rsp+1C0h] [rbp+C0h]
  WCHAR pBuffer[264]; // [rsp+1E0h] [rbp+E0h] BYREF

  v4 = (char ***)WiaTrace_Trace("::FillICMPropertyFromRegistry");
  CWiaTraceFn::CWiaTraceFn((CWiaTraceFn *)v62, v5, v6, (char **)"FillICMPropertyFromRegistry", lpMem, v4);
  uBytes = 0;
  v60 = 0;
  v61 = 0;
  if ( !a2 )
  {
    v7 = (char *)WiaTrace_TraceLog("NULL pointer passed for pWiaItem!");
    WriteDbgTraceErrorWI("FillICMPropertyFromRegistry", v7);
    WiaTrcLib::Free((WiaTrcLib *)v7, v8);
    v9 = (void **)WiaTrace_Trace("NULL pointer passed for pWiaItem!");
    WiaTrace_ProcessTrace_Ex(v11, v10, (void *)"FillICMPropertyFromRegistry", 1, v9);
    RootObject = -2147024809;
LABEL_3:
    v13 = (char *)WiaTrace_TraceLog("could not get item type!");
    WriteDbgTraceErrorWI("FillICMPropertyFromRegistry", v13);
    WiaTrcLib::Free((WiaTrcLib *)v13, v14);
    v15 = (void **)WiaTrace_Trace("could not get item type!");
LABEL_4:
    WiaTrace_ProcessTrace_Ex(v17, v16, (void *)"FillICMPropertyFromRegistry", 1, v15);
    goto LABEL_5;
  }
  RootObject = ((__int64 (__fastcall *)(struct IWiaItem *, int *))a2->lpVtbl->GetItemType)(a2, &v60);
  if ( RootObject < 0 )
    goto LABEL_3;
  if ( (v60 & 8) != 0 )
  {
    lpVtbl = a2[19].lpVtbl;
    if ( !lpVtbl )
    {
      v39 = (char *)WiaTrace_TraceLog("Failed trying to read ICM color profile for NULL driver wrapper");
      WriteDbgTraceErrorWI("FillICMPropertyFromRegistry", v39);
      WiaTrcLib::Free((WiaTrcLib *)v39, v40);
      v41 = (void **)WiaTrace_Trace("Failed trying to read ICM color profile for NULL driver wrapper");
      WiaTrace_ProcessTrace_Ex(v43, v42, (void *)"FillICMPropertyFromRegistry", 1, v41);
      RootObject = -2147418113;
      goto LABEL_5;
    }
    if ( a1 )
    {
      v20 = (void (__fastcall *)(struct IWiaItemVtbl *, _QWORD *, WCHAR *, char *, _QWORD, SIZE_T *))*((_QWORD *)lpVtbl->QueryInterface + 22);
      CSimpleStringBase<unsigned short>::CSimpleStringBase<unsigned short>((__int64)pBuffer, L"ICMProfile");
      CSimpleStringBase<unsigned short>::CSimpleStringBase<unsigned short>((__int64)v63, L"DeviceData");
      v20(lpVtbl, v63, pBuffer, (char *)&uBytes + 4, 0, &uBytes);
      v63[0] = &CSimpleStringBase<unsigned short>::`vftable';
      CSimpleStringBase<unsigned short>::DeleteStorage((__int64)v63);
      v64 = 0;
      *(_QWORD *)pBuffer = &CSimpleStringBase<unsigned short>::`vftable';
      CSimpleStringBase<unsigned short>::DeleteStorage((__int64)pBuffer);
      if ( !(_DWORD)uBytes )
      {
        v34 = (char *)WiaTrace_TraceLogWithSubComp(0, "FillICMPropertyFromRegistry, could not get ICM profile size!");
        WriteDbgTraceWarningWI("FillICMPropertyFromRegistry", v34);
        WiaTrcLib::Free((WiaTrcLib *)v34, v35);
        v31 = (void **)WiaTrace_TraceWithSubComp(0, "FillICMPropertyFromRegistry, could not get ICM profile size!");
        v36 = 2;
LABEL_19:
        WiaTrace_ProcessTrace_Ex(v33, v32, (void *)"FillICMPropertyFromRegistry", v36, v31);
LABEL_20:
        RootObject = 0;
        goto LABEL_5;
      }
      v21 = (struct IWiaItemVtbl *)LocalAlloc(0x40u, (unsigned int)uBytes);
      if ( v21 )
      {
        v22 = a2[19].lpVtbl;
        HIDWORD(uBytes) = 3;
        v23 = (__int64 (__fastcall *)(struct IWiaItemVtbl *, _QWORD *, WCHAR *, char *, struct IWiaItemVtbl *, SIZE_T *))*((_QWORD *)v22->QueryInterface + 22);
        CSimpleStringBase<unsigned short>::CSimpleStringBase<unsigned short>((__int64)pBuffer, L"ICMProfile");
        CSimpleStringBase<unsigned short>::CSimpleStringBase<unsigned short>((__int64)v63, L"DeviceData");
        LODWORD(v23) = v23(v22, v63, pBuffer, (char *)&uBytes + 4, v21, &uBytes);
        v63[0] = &CSimpleStringBase<unsigned short>::`vftable';
        CSimpleStringBase<unsigned short>::DeleteStorage((__int64)v63);
        v64 = 0;
        *(_QWORD *)pBuffer = &CSimpleStringBase<unsigned short>::`vftable';
        CSimpleStringBase<unsigned short>::DeleteStorage((__int64)pBuffer);
        if ( (int)v23 < 0 )
        {
          v24 = (char *)WiaTrace_TraceLogWithSubComp(0, "FillICMPropertyFromRegistry, could not get ICM profile value!");
          WriteDbgTraceWarningWI("FillICMPropertyFromRegistry", v24);
          WiaTrcLib::Free((WiaTrcLib *)v24, v25);
          v26 = (void **)WiaTrace_TraceWithSubComp(0, "FillICMPropertyFromRegistry, could not get ICM profile value!");
          WiaTrace_ProcessTrace_Ex(v28, v27, (void *)"FillICMPropertyFromRegistry", 2, v26);
          LocalFree(v21);
        }
        else
        {
          LODWORD(a2[18].lpVtbl) = uBytes;
          a2[17].lpVtbl = v21;
        }
        goto LABEL_20;
      }
      v29 = (char *)WiaTrace_TraceLog("not enough memory for ICM values!");
      WriteDbgTraceErrorWI("FillICMPropertyFromRegistry", v29);
      WiaTrcLib::Free((WiaTrcLib *)v29, v30);
      v31 = (void **)WiaTrace_Trace("not enough memory for ICM values!");
    }
    else
    {
      v37 = (char *)WiaTrace_TraceLog("no property stream provided!");
      WriteDbgTraceErrorWI("FillICMPropertyFromRegistry", v37);
      WiaTrcLib::Free((WiaTrcLib *)v37, v38);
      v31 = (void **)WiaTrace_Trace("no property stream provided!");
    }
    v36 = 1;
    goto LABEL_19;
  }
  RootObject = CWiaItem::GetRootObject((CWiaItem *)a2, &v61);
  if ( RootObject < 0 )
  {
    v56 = (char *)WiaTrace_TraceLog("could not get root item!");
    WriteDbgTraceErrorWI("FillICMPropertyFromRegistry", v56);
    WiaTrcLib::Free((WiaTrcLib *)v56, v57);
    v15 = (void **)WiaTrace_Trace("could not get root item!");
    goto LABEL_4;
  }
  v44 = v61;
  v45 = (const WCHAR *)*((_QWORD *)v61 + 17);
  if ( !v45 || (RootObject = SetValidProfileNames(v45, (unsigned __int64)*((int *)v61 + 36) >> 1, a2), RootObject < 0) )
  {
    memset_0(pBuffer, 0, 0x208u);
    LODWORD(uBytes) = 520;
    if ( GetStandardColorSpaceProfileW(0, 0x73524742u, pBuffer, (PDWORD)&uBytes) )
    {
      RootObject = SetValidProfileNames(pBuffer, (unsigned int)uBytes >> 1, a2);
      v46 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(
                      0,
                      0,
                      "FillICMPropertyFromRegistry, using default color space profile");
      WriteDbgTraceInfoWI("FillICMPropertyFromRegistry", v46);
      WiaTrcLib::Free((WiaTrcLib *)v46, v47);
      v48 = (void **)WiaTrace_TraceWithSubCompTraceLevel(
                       0,
                       0,
                       "FillICMPropertyFromRegistry, using default color space profile");
      WiaTrace_ProcessTrace_Ex(v50, v49, (void *)"FillICMPropertyFromRegistry", 4, v48);
    }
    else
    {
      v51 = (char *)WiaTrace_TraceLog("GetStandardColorSpaceProfile failed!");
      WriteDbgTraceErrorWI("FillICMPropertyFromRegistry", v51);
      WiaTrcLib::Free((WiaTrcLib *)v51, v52);
      v53 = (void **)WiaTrace_Trace("GetStandardColorSpaceProfile failed!");
      WiaTrace_ProcessTrace_Ex(v55, v54, (void *)"FillICMPropertyFromRegistry", 1, v53);
      RootObject = -2147467259;
    }
  }
  (*(void (__fastcall **)(struct CWiaItem *))(*(_QWORD *)v44 + 16LL))(v44);
LABEL_5:
  CWiaTraceFn::~CWiaTraceFn((CWiaTraceFn *)v62);
  return (unsigned int)RootObject;
}

```

## disassembly

```asm
0x1800587e4  mov     [rsp-8+arg_0], rbx
0x1800587e9  mov     [rsp-8+arg_10], rsi
0x1800587ee  push    rbp
0x1800587ef  push    rdi
0x1800587f0  push    r12
0x1800587f2  push    r13
0x1800587f4  push    r14
0x1800587f6  lea     rbp, [rsp-300h]
0x1800587fe  sub     rsp, 400h
0x180058805  mov     rax, cs:__security_cookie
0x18005880c  xor     rax, rsp
0x18005880f  mov     [rbp+320h+var_30], rax
0x180058816  mov     rbx, rcx
0x180058819  mov     rsi, rdx
0x18005881c  lea     rcx, aFillicmpropert; "::FillICMPropertyFromRegistry"
0x180058823  call    WiaTrace_Trace
0x180058828  lea     r12, aFillicmpropert_1; "FillICMPropertyFromRegistry"
0x18005882f  mov     [rsp+420h+var_3F8], rax; struct tagWiaTraceData_Type *
0x180058834  mov     r9, r12; char *
0x180058837  lea     rcx, [rsp+420h+var_3C0]; this
0x18005883c  call    ??0CWiaTraceFn@@QEAA@PEADK0KPEAUtagWiaTraceData_Type@@@Z; CWiaTraceFn::CWiaTraceFn(char *,ulong,char *,ulong,tagWiaTraceData_Type *)
0x180058841  mov     dword ptr [rsp+420h+uBytes+4], 0
0x180058849  mov     r13d, 1
0x18005884f  mov     dword ptr [rsp+420h+uBytes], 0
0x180058857  mov     [rsp+420h+var_3D8], 0
0x18005885f  mov     [rsp+420h+var_3D0], 0
0x180058868  test    rsi, rsi
0x18005886b  jnz     loc_180058929
0x180058871  lea     rcx, aNullPointerPas_0; "NULL pointer passed for pWiaItem!"
0x180058878  call    WiaTrace_TraceLog
0x18005887d  mov     rdx, rax; char *
0x180058880  mov     rcx, r12; char *
0x180058883  mov     rbx, rax
0x180058886  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18005888b  mov     rcx, rbx; this
0x18005888e  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180058893  lea     rcx, aNullPointerPas_0; "NULL pointer passed for pWiaItem!"
0x18005889a  call    WiaTrace_Trace
0x18005889f  mov     r9d, r13d; int
0x1800588a2  mov     [rsp+420h+lpMem], rax; lpMem
0x1800588a7  mov     r8, r12; int
0x1800588aa  call    WiaTrace_ProcessTrace_Ex
0x1800588af  mov     edi, 80070057h
0x1800588b4  lea     rcx, aCouldNotGetIte_0; "could not get item type!"
0x1800588bb  call    WiaTrace_TraceLog
0x1800588c0  mov     rdx, rax; char *
0x1800588c3  mov     rcx, r12; char *
0x1800588c6  mov     rbx, rax
0x1800588c9  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x1800588ce  mov     rcx, rbx; this
0x1800588d1  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x1800588d6  lea     rcx, aCouldNotGetIte_0; "could not get item type!"
0x1800588dd  call    WiaTrace_Trace
0x1800588e2  mov     r9d, r13d; int
0x1800588e5  mov     [rsp+420h+lpMem], rax; lpMem
0x1800588ea  mov     r8, r12; int
0x1800588ed  call    WiaTrace_ProcessTrace_Ex
0x1800588f2  lea     rcx, [rsp+420h+var_3C0]; this
0x1800588f7  call    ??1CWiaTraceFn@@QEAA@XZ; CWiaTraceFn::~CWiaTraceFn(void)
0x1800588fc  mov     eax, edi
0x1800588fe  mov     rcx, [rbp+320h+var_30]
0x180058905  xor     rcx, rsp; StackCookie
0x180058908  call    __security_check_cookie
0x18005890d  lea     r11, [rsp+420h+var_20]
0x180058915  mov     rbx, [r11+30h]
0x180058919  mov     rsi, [r11+40h]
0x18005891d  mov     rsp, r11
0x180058920  pop     r14
0x180058922  pop     r13
0x180058924  pop     r12
0x180058926  pop     rdi
0x180058927  pop     rbp
0x180058928  retn
0x180058929  mov     rax, [rsi]
0x18005892c  lea     rdx, [rsp+420h+var_3D8]
0x180058931  mov     rcx, rsi
0x180058934  mov     rax, [rax+18h]
0x180058938  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005893d  mov     edi, eax
0x18005893f  test    eax, eax
0x180058941  js      loc_1800588B4
0x180058947  test    byte ptr [rsp+420h+var_3D8], 8
0x18005894c  jz      loc_180058C16
0x180058952  mov     rdi, [rsi+98h]
0x180058959  test    rdi, rdi
0x18005895c  jz      loc_180058BCE
0x180058962  test    rbx, rbx
0x180058965  jz      loc_180058B89
0x18005896b  mov     rax, [rdi]
0x18005896e  lea     rdx, aIcmprofile; "ICMProfile"
0x180058975  lea     rcx, [rbp+320h+pBuffer]
0x18005897c  mov     rbx, [rax+0B0h]
0x180058983  call    ??0?$CSimpleStringBase@G@@QEAA@PEBG@Z; CSimpleStringBase<ushort>::CSimpleStringBase<ushort>(ushort const *)
0x180058988  lea     rdx, aDevicedata; "DeviceData"
0x18005898f  lea     rcx, [rbp+320h+var_370]
0x180058993  call    ??0?$CSimpleStringBase@G@@QEAA@PEBG@Z; CSimpleStringBase<ushort>::CSimpleStringBase<ushort>(ushort const *)
0x180058998  lea     rax, [rsp+420h+uBytes]
0x18005899d  mov     rcx, rdi
0x1800589a0  mov     [rsp+420h+var_3F8], rax
0x1800589a5  lea     r9, [rsp+420h+uBytes+4]
0x1800589aa  mov     rax, rbx
0x1800589ad  mov     [rsp+420h+lpMem], 0
0x1800589b6  lea     r8, [rbp+320h+pBuffer]
0x1800589bd  lea     rdx, [rbp+320h+var_370]
0x1800589c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800589c6  lea     rbx, ??_7?$CSimpleStringBase@G@@6B@; const CSimpleStringBase<ushort>::`vftable'
0x1800589cd  lea     rcx, [rbp+320h+var_370]
0x1800589d1  mov     [rbp+320h+var_370], rbx
0x1800589d5  call    ?DeleteStorage@?$CSimpleStringBase@G@@AEAAXXZ; CSimpleStringBase<ushort>::DeleteStorage(void)
0x1800589da  lea     rcx, [rbp+320h+pBuffer]
0x1800589e1  mov     [rbp+320h+var_260], 0
0x1800589ec  mov     qword ptr [rbp+320h+pBuffer], rbx
0x1800589f3  call    ?DeleteStorage@?$CSimpleStringBase@G@@AEAAXXZ; CSimpleStringBase<ushort>::DeleteStorage(void)
0x1800589f8  mov     eax, dword ptr [rsp+420h+uBytes]
0x1800589fc  test    eax, eax
0x1800589fe  jz      loc_180058B4F
0x180058a04  mov     edx, eax; uBytes
0x180058a06  mov     ecx, 40h ; '@'; uFlags
0x180058a0b  call    cs:__imp_LocalAlloc
0x180058a11  mov     r14, rax
0x180058a14  test    rax, rax
0x180058a17  jz      loc_180058B24
0x180058a1d  mov     rdi, [rsi+98h]
0x180058a24  lea     rdx, aIcmprofile; "ICMProfile"
0x180058a2b  mov     dword ptr [rsp+420h+uBytes+4], 3
0x180058a33  mov     rcx, [rdi]
0x180058a36  mov     rbx, [rcx+0B0h]
0x180058a3d  lea     rcx, [rbp+320h+pBuffer]
0x180058a44  call    ??0?$CSimpleStringBase@G@@QEAA@PEBG@Z; CSimpleStringBase<ushort>::CSimpleStringBase<ushort>(ushort const *)
0x180058a49  lea     rdx, aDevicedata; "DeviceData"
0x180058a50  lea     rcx, [rbp+320h+var_370]
0x180058a54  call    ??0?$CSimpleStringBase@G@@QEAA@PEBG@Z; CSimpleStringBase<ushort>::CSimpleStringBase<ushort>(ushort const *)
0x180058a59  lea     rax, [rsp+420h+uBytes]
0x180058a5e  mov     rcx, rdi
0x180058a61  mov     [rsp+420h+var_3F8], rax
0x180058a66  lea     r9, [rsp+420h+uBytes+4]
0x180058a6b  mov     rax, rbx
0x180058a6e  mov     [rsp+420h+lpMem], r14
0x180058a73  lea     r8, [rbp+320h+pBuffer]
0x180058a7a  lea     rdx, [rbp+320h+var_370]
0x180058a7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058a83  lea     rdi, ??_7?$CSimpleStringBase@G@@6B@; const CSimpleStringBase<ushort>::`vftable'
0x180058a8a  mov     ebx, eax
0x180058a8c  lea     rcx, [rbp+320h+var_370]
0x180058a90  mov     [rbp+320h+var_370], rdi
0x180058a94  call    ?DeleteStorage@?$CSimpleStringBase@G@@AEAAXXZ; CSimpleStringBase<ushort>::DeleteStorage(void)
0x180058a99  lea     rcx, [rbp+320h+pBuffer]
0x180058aa0  mov     [rbp+320h+var_260], 0
0x180058aab  mov     qword ptr [rbp+320h+pBuffer], rdi
0x180058ab2  call    ?DeleteStorage@?$CSimpleStringBase@G@@AEAAXXZ; CSimpleStringBase<ushort>::DeleteStorage(void)
0x180058ab7  test    ebx, ebx
0x180058ab9  js      short loc_180058AD1
0x180058abb  mov     eax, dword ptr [rsp+420h+uBytes]
0x180058abf  mov     [rsi+90h], eax
0x180058ac5  mov     [rsi+88h], r14
0x180058acc  jmp     loc_180058BC7
0x180058ad1  lea     rdx, aFillicmpropert_2; "FillICMPropertyFromRegistry, could not "...
0x180058ad8  xor     ecx, ecx
0x180058ada  call    WiaTrace_TraceLogWithSubComp
0x180058adf  mov     rdx, rax; char *
0x180058ae2  mov     rcx, r12; char *
0x180058ae5  mov     rbx, rax
0x180058ae8  call    ?WriteDbgTraceWarningWI@@YAXPEAD0ZZ; WriteDbgTraceWarningWI(char *,char *,...)
0x180058aed  mov     rcx, rbx; this
0x180058af0  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180058af5  lea     rdx, aFillicmpropert_2; "FillICMPropertyFromRegistry, could not "...
0x180058afc  xor     ecx, ecx
0x180058afe  call    WiaTrace_TraceWithSubComp
0x180058b03  mov     r9d, 2; int
0x180058b09  mov     [rsp+420h+lpMem], rax; lpMem
0x180058b0e  mov     r8, r12; int
0x180058b11  call    WiaTrace_ProcessTrace_Ex
0x180058b16  mov     rcx, r14; hMem
0x180058b19  call    cs:__imp_LocalFree
0x180058b1f  jmp     loc_180058BC7
0x180058b24  lea     rcx, aNotEnoughMemor_0; "not enough memory for ICM values!"
0x180058b2b  call    WiaTrace_TraceLog
0x180058b30  mov     rdx, rax; char *
0x180058b33  mov     rcx, r12; char *
0x180058b36  mov     rbx, rax
0x180058b39  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180058b3e  mov     rcx, rbx; this
0x180058b41  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180058b46  lea     rcx, aNotEnoughMemor_0; "not enough memory for ICM values!"
0x180058b4d  jmp     short loc_180058BB2
0x180058b4f  lea     rdx, aFillicmpropert_3; "FillICMPropertyFromRegistry, could not "...
0x180058b56  xor     ecx, ecx
0x180058b58  call    WiaTrace_TraceLogWithSubComp
0x180058b5d  mov     rdx, rax; char *
0x180058b60  mov     rcx, r12; char *
0x180058b63  mov     rbx, rax
0x180058b66  call    ?WriteDbgTraceWarningWI@@YAXPEAD0ZZ; WriteDbgTraceWarningWI(char *,char *,...)
0x180058b6b  mov     rcx, rbx; this
0x180058b6e  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180058b73  lea     rdx, aFillicmpropert_3; "FillICMPropertyFromRegistry, could not "...
0x180058b7a  xor     ecx, ecx
0x180058b7c  call    WiaTrace_TraceWithSubComp
0x180058b81  mov     r9d, 2
0x180058b87  jmp     short loc_180058BBA
0x180058b89  lea     rcx, aNoPropertyStre; "no property stream provided!"
0x180058b90  call    WiaTrace_TraceLog
0x180058b95  mov     rdx, rax; char *
0x180058b98  mov     rcx, r12; char *
0x180058b9b  mov     rbx, rax
0x180058b9e  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180058ba3  mov     rcx, rbx; this
0x180058ba6  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180058bab  lea     rcx, aNoPropertyStre; "no property stream provided!"
0x180058bb2  call    WiaTrace_Trace
0x180058bb7  mov     r9d, r13d; int
0x180058bba  mov     r8, r12; int
0x180058bbd  mov     [rsp+420h+lpMem], rax; lpMem
0x180058bc2  call    WiaTrace_ProcessTrace_Ex
0x180058bc7  xor     edi, edi
0x180058bc9  jmp     loc_1800588F2
0x180058bce  lea     rcx, aFailedTryingTo; "Failed trying to read ICM color profile"...
0x180058bd5  call    WiaTrace_TraceLog
0x180058bda  mov     rdx, rax; char *
0x180058bdd  mov     rcx, r12; char *
0x180058be0  mov     rbx, rax
0x180058be3  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180058be8  mov     rcx, rbx; this
0x180058beb  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180058bf0  lea     rcx, aFailedTryingTo; "Failed trying to read ICM color profile"...
0x180058bf7  call    WiaTrace_Trace
0x180058bfc  mov     r9d, r13d; int
0x180058bff  mov     [rsp+420h+lpMem], rax; lpMem
0x180058c04  mov     r8, r12; int
0x180058c07  call    WiaTrace_ProcessTrace_Ex
0x180058c0c  mov     edi, 8000FFFFh
0x180058c11  jmp     loc_1800588F2
0x180058c16  lea     rdx, [rsp+420h+var_3D0]; struct CWiaItem **
0x180058c1b  mov     rcx, rsi; this
0x180058c1e  call    ?GetRootObject@CWiaItem@@QEAAJPEAPEAV1@@Z; CWiaItem::GetRootObject(CWiaItem * *)
0x180058c23  mov     edi, eax
0x180058c25  test    eax, eax
0x180058c27  js      loc_180058D4A
0x180058c2d  mov     r14, [rsp+420h+var_3D0]
0x180058c32  mov     rcx, [r14+88h]; lpString
0x180058c39  test    rcx, rcx
0x180058c3c  jz      short loc_180058C5A
0x180058c3e  movsxd  rdx, dword ptr [r14+90h]
0x180058c45  mov     r8, rsi; struct IWiaItem *
0x180058c48  shr     rdx, 1; unsigned int
0x180058c4b  call    ?SetValidProfileNames@@YAJPEBGKPEAUIWiaItem@@@Z; SetValidProfileNames(ushort const *,ulong,IWiaItem *)
0x180058c50  mov     edi, eax
0x180058c52  test    eax, eax
0x180058c54  jns     loc_180058D36
0x180058c5a  mov     ebx, 208h
0x180058c5f  lea     rcx, [rbp+320h+pBuffer]; void *
0x180058c66  mov     r8d, ebx; Size
0x180058c69  xor     edx, edx; Val
0x180058c6b  call    memset_0
0x180058c70  lea     r9, [rsp+420h+uBytes]; pcbSize
0x180058c75  mov     dword ptr [rsp+420h+uBytes], ebx
0x180058c79  lea     r8, [rbp+320h+pBuffer]; pBuffer
0x180058c80  mov     edx, 73524742h; dwSCS
0x180058c85  xor     ecx, ecx; pMachineName
0x180058c87  call    cs:__imp_GetStandardColorSpaceProfileW
0x180058c8d  test    eax, eax
0x180058c8f  jz      short loc_180058CF3
0x180058c91  mov     edx, dword ptr [rsp+420h+uBytes]
0x180058c95  lea     rcx, [rbp+320h+pBuffer]; lpString
0x180058c9c  shr     edx, 1; unsigned int
0x180058c9e  mov     r8, rsi; struct IWiaItem *
0x180058ca1  call    ?SetValidProfileNames@@YAJPEBGKPEAUIWiaItem@@@Z; SetValidProfileNames(ushort const *,ulong,IWiaItem *)
0x180058ca6  lea     r8, aFillicmpropert_0; "FillICMPropertyFromRegistry, using defa"...
0x180058cad  xor     edx, edx
0x180058caf  xor     ecx, ecx
0x180058cb1  mov     edi, eax
0x180058cb3  call    WiaTrace_TraceLogWithSubCompTraceLevel
0x180058cb8  mov     rdx, rax; char *
0x180058cbb  mov     rcx, r12; char *
0x180058cbe  mov     rbx, rax
0x180058cc1  call    ?WriteDbgTraceInfoWI@@YAXPEAD0ZZ; WriteDbgTraceInfoWI(char *,char *,...)
0x180058cc6  mov     rcx, rbx; this
0x180058cc9  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180058cce  lea     r8, aFillicmpropert_0; "FillICMPropertyFromRegistry, using defa"...
0x180058cd5  xor     edx, edx
0x180058cd7  xor     ecx, ecx
0x180058cd9  call    WiaTrace_TraceWithSubCompTraceLevel
0x180058cde  mov     r9d, 4; int
0x180058ce4  mov     [rsp+420h+lpMem], rax; lpMem
0x180058ce9  mov     r8, r12; int
0x180058cec  call    WiaTrace_ProcessTrace_Ex
0x180058cf1  jmp     short loc_180058D36
0x180058cf3  lea     rcx, aGetstandardcol_0; "GetStandardColorSpaceProfile failed!"
0x180058cfa  call    WiaTrace_TraceLog
0x180058cff  mov     rdx, rax; char *
0x180058d02  mov     rcx, r12; char *
0x180058d05  mov     rbx, rax
0x180058d08  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180058d0d  mov     rcx, rbx; this
0x180058d10  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180058d15  lea     rcx, aGetstandardcol_0; "GetStandardColorSpaceProfile failed!"
0x180058d1c  call    WiaTrace_Trace
0x180058d21  mov     r9d, r13d; int
0x180058d24  mov     [rsp+420h+lpMem], rax; lpMem
0x180058d29  mov     r8, r12; int
0x180058d2c  call    WiaTrace_ProcessTrace_Ex
  ... truncated ...
```
