# USDWrapper::CreateDeviceInfoStorage(void)

- ea: `0x180015f90`
- end: `0x180016995`
- name: `?CreateDeviceInfoStorage@USDWrapper@@UEAAPEAUIWiaPropertyStorage@@XZ`
- size: `2565`
- prototype: `struct IWiaPropertyStorage *__fastcall(USDWrapper *__hidden this)`
- caller_count: `0`
- callee_count: `23`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x18000b6a0`
- `0x18000cba0`
- `0x18000d770`
- `0x18000d7b0`
- `0x18000da10`
- `0x180010d78`
- `0x180015f90`
- `0x18001699c`
- `0x180016ab8`
- `0x180016e88`
- `0x180018ad8`
- `0x18001fb30`
- `0x18002c868`
- `0x18002c8b0`
- `0x18002de18`
- `0x18002def8`
- `0x18002e9d8`
- `0x18002eab4`
- `0x180033884`
- `0x180033cc0`
- `0x180034658`
- `0x1800690c0`
- `0x180078010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180016300`
- `OLEAUT32!__imp_SysAllocString` at `0x180016431`
- `OLEAUT32!__imp_SysAllocString` at `0x180016300`
- `OLEAUT32!__imp_SysAllocString` at `0x180016431`
- `api-ms-win-core-com-l1-1-0!FreePropVariantArray` at `0x1800162dc`
- `api-ms-win-core-com-l1-1-0!FreePropVariantArray` at `0x1800162dc`

## string_xrefs

- `0x18001619b`: `USDWrapper::CreateDeviceInfoStorage`
- `0x1800161df`: `USDWrapper::CreateDeviceInfoStorage`
- `0x180016214`: `USDWrapper::CreateDeviceInfoStorage`
- `0x180016325`: `USDWrapper::CreateDeviceInfoStorage`
- `0x180016355`: `USDWrapper::CreateDeviceInfoStorage`
- `0x180016393`: `USDWrapper::CreateDeviceInfoStorage`
- `0x1800163c5`: `USDWrapper::CreateDeviceInfoStorage`
- `0x1800163e7`: `USDWrapper::CreateDeviceInfoStorage`
- `0x18001641e`: `USDWrapper::CreateDeviceInfoStorage`
- `0x18001645e`: `USDWrapper::CreateDeviceInfoStorage`
- `0x180016492`: `USDWrapper::CreateDeviceInfoStorage`
- `0x1800164c2`: `USDWrapper::CreateDeviceInfoStorage`
- `0x1800164fe`: `USDWrapper::CreateDeviceInfoStorage`
- `0x18001653e`: `USDWrapper::CreateDeviceInfoStorage`
- `0x18001657e`: `USDWrapper::CreateDeviceInfoStorage`
- `0x1800165be`: `USDWrapper::CreateDeviceInfoStorage`
- `0x1800165fe`: `USDWrapper::CreateDeviceInfoStorage`
- `0x18001665c`: `USDWrapper::CreateDeviceInfoStorage`
- `0x1800166c2`: `USDWrapper::CreateDeviceInfoStorage`
- `0x180016706`: `USDWrapper::CreateDeviceInfoStorage`
- `0x180016738`: `USDWrapper::CreateDeviceInfoStorage`
- `0x180016766`: `USDWrapper::CreateDeviceInfoStorage`
- `0x180016784`: `USDWrapper::CreateDeviceInfoStorage`
- `0x1800167b5`: `USDWrapper::CreateDeviceInfoStorage`
- `0x1800167dc`: `USDWrapper::CreateDeviceInfoStorage`
- `0x18001680c`: `USDWrapper::CreateDeviceInfoStorage`
- `0x18001688f`: `USDWrapper::CreateDeviceInfoStorage`
- `0x1800168d1`: `USDWrapper::CreateDeviceInfoStorage`
- `0x18001691a`: `USDWrapper::CreateDeviceInfoStorage`
- `0x18001694d`: `USDWrapper::CreateDeviceInfoStorage`
- `0x180016380`: `CreateDevInfoStg, NULL device property string`
- `0x1800163aa`: `CreateDevInfoStg, NULL device property string`
- `0x180016481`: `CreateDevInfoStg, IPropertyStorage is NULL`
- `0x1800164a9`: `CreateDevInfoStg, IPropertyStorage is NULL`
- `0x1800167cb`: `GetDriverDLLVersion, unable to alloc get driver version resource information, defaulting to 0.0.0.0`
- `0x1800167f3`: `GetDriverDLLVersion, unable to alloc get driver version resource information, defaulting to 0.0.0.0`
- `0x1800168b3`: `Hardware configuration: %u`
- `0x1800168e8`: `Hardware configuration: %u`
- `0x180016729`: `CreateDevInfoStg, Unknown device property`
- `0x18001674f`: `CreateDevInfoStg, Unknown device property`
- `0x180016314`: `CreateDevInfoStg, unable to alloc dev info strings`
- `0x18001633c`: `CreateDevInfoStg, unable to alloc dev info strings`
- `0x18001696d`: `CreateDevInfoStg`
- `0x180016909`: `CreateDevInfoStg, WritePropertyNames Failed (0x%X)`
- `0x180016934`: `CreateDevInfoStg, WritePropertyNames Failed (0x%X)`

## pseudocode

```c
struct IWiaPropertyStorage *__fastcall USDWrapper::CreateDeviceInfoStorage(unsigned __int16 **this)
{
  CWIADevInfo *v2; // rax
  CWIADevInfo *v4; // rax
  CWIADevInfo *v5; // rsi
  unsigned int v6; // edx
  unsigned int v7; // r8d
  __int64 v8; // r13
  __int64 v9; // r15
  PROPID v10; // r12d
  unsigned __int16 *v11; // rdi
  __int64 v12; // rax
  char *v13; // rbx
  void *v14; // rdx
  void **v15; // rax
  void *v16; // rdx
  __int64 v17; // rcx
  char *v18; // rbx
  void *v19; // rdx
  const char *v20; // r8
  unsigned __int16 *v21; // r9
  __int64 v22; // rbx
  int v23; // edi
  int v24; // eax
  BSTR v25; // rax
  char *v26; // rbx
  void *v27; // rdx
  void **v28; // rax
  void *v29; // rdx
  __int64 v30; // rcx
  char *v31; // rbx
  void *v32; // rdx
  void **v33; // rax
  void *v34; // rdx
  __int64 v35; // rcx
  char *v36; // rbx
  void *v37; // rdx
  void **v38; // rax
  void *v39; // rdx
  __int64 v40; // rcx
  char *v41; // rbx
  void *v42; // rdx
  char *v43; // rbx
  void *v44; // rdx
  void **v45; // rax
  void *v46; // rdx
  __int64 v47; // rcx
  char *v48; // rbx
  void *v49; // rdx
  char *v50; // rbx
  void *v51; // rdx
  char *v52; // rbx
  void *v53; // rdx
  char *v54; // rbx
  void *v55; // rdx
  char *v56; // rbx
  void *v57; // rdx
  int v58; // r9d
  char *v59; // rbx
  void *v60; // rdx
  int v61; // r9d
  char *v62; // rbx
  void *v63; // rdx
  char *v64; // rbx
  void *v65; // rdx
  char *v66; // rbx
  void *v67; // rdx
  void **v68; // rax
  void *v69; // rdx
  __int64 v70; // rcx
  char *v71; // rbx
  void *v72; // rdx
  void **v73; // rax
  void *v74; // rdx
  __int64 v75; // rcx
  char *v76; // rbx
  void *v77; // rdx
  void **lpMem; // rax
  void *v79; // rdx
  __int64 v80; // rcx
  int v81; // eax
  int v82; // r9d
  char *v83; // rbx
  void *v84; // rdx
  int v85; // r9d
  char *v86; // rbx
  void *v87; // rdx
  char *v88; // rbx
  void *v89; // rdx
  void **v90; // rax
  void *v91; // rdx
  __int64 v92; // rcx
  __int64 v93; // [rsp+30h] [rbp-D0h] BYREF
  CWIADevInfo *v94; // [rsp+38h] [rbp-C8h]
  PROPVARIANT rgvars[48]; // [rsp+40h] [rbp-C0h] BYREF
  struct tagPROPSPEC v96[16]; // [rsp+1C0h] [rbp+C0h] BYREF
  unsigned __int16 v97[264]; // [rsp+2C0h] [rbp+1C0h] BYREF

  memset_0(v96, 0, sizeof(v96));
  memset_0(rgvars, 0, sizeof(rgvars));
  memset_0(v97, 0, 0x208u);
  v93 = 0;
  v2 = (CWIADevInfo *)operator new(0x30u);
  if ( !v2 )
    return 0;
  v4 = CWIADevInfo::CWIADevInfo(v2);
  v94 = v4;
  v5 = v4;
  if ( !v4 )
    return 0;
  if ( (int)CWIADevInfo::Initialize(v4, (struct USDWrapper *)this) < 0 )
  {
LABEL_61:
    CWIADevInfo::`scalar deleting destructor'(v5, v6);
    return 0;
  }
  memset_0(v96, 0, sizeof(v96));
  memset_0(rgvars, 0, sizeof(rgvars));
  memset_0(v97, 0, 0x208u);
  v8 = 0;
  v9 = 0;
  do
  {
    v10 = g_piDeviceInfo[v8];
    v11 = 0;
    rgvars[v9 + 1] = 0;
    v12 = v8;
    v96[v12].ulKind = 1;
    *(&v96[0].propid + 1 * v12) = v10;
    LOWORD(rgvars[v9]) = 8;
    if ( v10 <= 0xA )
    {
      switch ( v10 )
      {
        case 0xAu:
          v11 = this[375];
          v64 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(4, 0, "UI class identifier: %ws", v11);
          WriteDbgTraceInfoWI("USDWrapper::CreateDeviceInfoStorage", v64);
          WiaTrcLib::Free((WiaTrcLib *)v64, v65);
          v20 = "UI class identifier: %ws";
          break;
        case 2u:
          v11 = this[42];
          v18 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(4, 0, "Device internal name: %ws", v11);
          WriteDbgTraceInfoWI("USDWrapper::CreateDeviceInfoStorage", v18);
          WiaTrcLib::Free((WiaTrcLib *)v18, v19);
          v20 = "Device internal name: %ws";
          break;
        case 3u:
          v11 = this[153];
          v56 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(4, 0, "Vendor description: %ws", v11);
          WriteDbgTraceInfoWI("USDWrapper::CreateDeviceInfoStorage", v56);
          WiaTrcLib::Free((WiaTrcLib *)v56, v57);
          v20 = "Vendor description: %ws";
          break;
        case 4u:
          v11 = this[190];
          v54 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(4, 0, "Device description: %ws", v11);
          WriteDbgTraceInfoWI("USDWrapper::CreateDeviceInfoStorage", v54);
          WiaTrcLib::Free((WiaTrcLib *)v54, v55);
          v20 = "Device description: %ws";
          break;
        case 5u:
          v61 = *((_DWORD *)this + 16);
          LOWORD(rgvars[v9]) = 3;
          LODWORD(rgvars[v9 + 1]) = v61;
          v62 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(4, 0, "Device type: 0x%04.4X", v61);
          WriteDbgTraceInfoWI("USDWrapper::CreateDeviceInfoStorage", v62);
          WiaTrcLib::Free((WiaTrcLib *)v62, v63);
          v15 = (void **)WiaTrace_TraceWithSubCompTraceLevel(
                           4,
                           0,
                           "Device type: 0x%04.4X",
                           *((unsigned int *)this + 16));
          goto LABEL_27;
        case 6u:
          v11 = this[227];
          v52 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(4, 0, "Port name: %ws", v11);
          WriteDbgTraceInfoWI("USDWrapper::CreateDeviceInfoStorage", v52);
          WiaTrcLib::Free((WiaTrcLib *)v52, v53);
          v20 = "Port name: %ws";
          break;
        case 7u:
          v11 = this[301];
          v41 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(4, 0, "Device name: %ws", v11);
          WriteDbgTraceInfoWI("USDWrapper::CreateDeviceInfoStorage", v41);
          WiaTrcLib::Free((WiaTrcLib *)v41, v42);
          v20 = "Device name: %ws";
          break;
        case 8u:
          v11 = L"local";
          goto LABEL_28;
        case 9u:
          v11 = (unsigned __int16 *)&Class;
          goto LABEL_28;
        default:
          goto LABEL_54;
      }
      goto LABEL_25;
    }
    switch ( v10 )
    {
      case 0xBu:
        v85 = *((_DWORD *)this + 12);
        LOWORD(rgvars[v9]) = 3;
        LODWORD(rgvars[v9 + 1]) = v85;
        v86 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(4, 0, "Hardware configuration: %u", v85);
        WriteDbgTraceInfoWI("USDWrapper::CreateDeviceInfoStorage", v86);
        WiaTrcLib::Free((WiaTrcLib *)v86, v87);
        v20 = "Hardware configuration: %u";
        goto LABEL_58;
      case 0xCu:
        v11 = this[338];
        v50 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(4, 0, "Baud rate: %ws", v11);
        WriteDbgTraceInfoWI("USDWrapper::CreateDeviceInfoStorage", v50);
        WiaTrcLib::Free((WiaTrcLib *)v50, v51);
        v20 = "Baud rate: %ws";
LABEL_25:
        v21 = v11;
LABEL_26:
        v15 = (void **)WiaTrace_TraceWithSubCompTraceLevel(4, 0, v20, v21);
        goto LABEL_27;
      case 0xDu:
        v81 = *((_DWORD *)this + 15);
        v82 = *((_DWORD *)this + 12);
        LOWORD(rgvars[v9]) = 3;
        LODWORD(rgvars[v9 + 1]) = v81;
        v83 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(4, 0, "Generic capabilities: 0x%X", v82);
        WriteDbgTraceInfoWI("USDWrapper::CreateDeviceInfoStorage", v83);
        WiaTrcLib::Free((WiaTrcLib *)v83, v84);
        v20 = "Generic capabilities: 0x%X";
LABEL_58:
        v21 = (unsigned __int16 *)*((unsigned int *)this + 12);
        goto LABEL_26;
    }
    if ( v10 != 14 )
    {
      if ( v10 == 15 )
      {
        if ( !GetDriverDLLVersion((struct USDInfo *)(this + 3), v97, v7) )
        {
          v76 = (char *)WiaTrace_TraceLogWithSubComp(
                          0,
                          "GetDriverDLLVersion, unable to alloc get driver version resource information, defaulting to 0.0.0.0");
          WriteDbgTraceWarningWI("USDWrapper::CreateDeviceInfoStorage", v76);
          WiaTrcLib::Free((WiaTrcLib *)v76, v77);
          lpMem = (void **)WiaTrace_TraceWithSubComp(
                             0,
                             "GetDriverDLLVersion, unable to alloc get driver version resource information, defaulting to 0.0.0.0");
          WiaTrace_ProcessTrace_Ex(v80, v79, (void *)"USDWrapper::CreateDeviceInfoStorage", 2, lpMem);
          StringCchCopyW(v97, 0x104u, L"0.0.0.0");
        }
        v11 = v97;
        v13 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(4, 0, "Driver version: %ws", v97);
        WriteDbgTraceInfoWI("USDWrapper::CreateDeviceInfoStorage", v13);
        WiaTrcLib::Free((WiaTrcLib *)v13, v14);
        v15 = (void **)WiaTrace_TraceWithSubCompTraceLevel(4, 0, "Driver version: %ws", v97);
        goto LABEL_27;
      }
      if ( v10 != 16 )
      {
        if ( v10 != 17 )
        {
LABEL_54:
          v66 = (char *)WiaTrace_TraceLog("CreateDevInfoStg, Unknown device property");
          WriteDbgTraceErrorWI("USDWrapper::CreateDeviceInfoStorage", v66);
          WiaTrcLib::Free((WiaTrcLib *)v66, v67);
          v68 = (void **)WiaTrace_Trace("CreateDevInfoStg, Unknown device property");
          WiaTrace_ProcessTrace_Ex(v70, v69, (void *)"USDWrapper::CreateDeviceInfoStorage", 1, v68);
          v71 = (char *)WiaTrace_TraceLog("  propid = %li");
          WriteDbgTraceErrorWI("USDWrapper::CreateDeviceInfoStorage", v71);
          WiaTrcLib::Free((WiaTrcLib *)v71, v72);
          v73 = (void **)WiaTrace_Trace("  propid = %li", v10);
          WiaTrace_ProcessTrace_Ex(v75, v74, (void *)"USDWrapper::CreateDeviceInfoStorage", 1, v73);
          goto LABEL_28;
        }
        v58 = *((_DWORD *)this + 14);
        LOWORD(rgvars[v9]) = 3;
        LODWORD(rgvars[v9 + 1]) = v58;
        v59 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(4, 0, "STI driver version: %u (WIA %u.0)");
        WriteDbgTraceInfoWI("USDWrapper::CreateDeviceInfoStorage", v59);
        WiaTrcLib::Free((WiaTrcLib *)v59, v60);
        v15 = (void **)WiaTrace_TraceWithSubCompTraceLevel(4, 0, "STI driver version: %u (WIA %u.0)");
LABEL_27:
        WiaTrace_ProcessTrace_Ex(v17, v16, (void *)"USDWrapper::CreateDeviceInfoStorage", 4, v15);
        goto LABEL_28;
      }
      v11 = this[449];
      v48 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(4, 0, "PnP identifier: %ws", v11);
      WriteDbgTraceInfoWI("USDWrapper::CreateDeviceInfoStorage", v48);
      WiaTrcLib::Free((WiaTrcLib *)v48, v49);
      v20 = "PnP identifier: %ws";
      goto LABEL_25;
    }
    StringCchPrintfW(v97, 0x104u, L"%d.%d", 2, 0);
    v11 = v97;
LABEL_28:
    if ( LOWORD(rgvars[v9]) == 8 )
    {
      if ( v11 )
      {
        v25 = SysAllocString(v11);
        rgvars[v9 + 1] = v25;
        if ( !v25 )
        {
          v26 = (char *)WiaTrace_TraceLogWithSubComp(0, "CreateDevInfoStg, unable to alloc dev info strings");
          WriteDbgTraceWarningWI("USDWrapper::CreateDeviceInfoStorage", v26);
          WiaTrcLib::Free((WiaTrcLib *)v26, v27);
          v28 = (void **)WiaTrace_TraceWithSubComp(0, "CreateDevInfoStg, unable to alloc dev info strings");
          WiaTrace_ProcessTrace_Ex(v30, v29, (void *)"USDWrapper::CreateDeviceInfoStorage", 2, v28);
        }
      }
      else
      {
        v31 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(0, 0, "CreateDevInfoStg, NULL device property string");
        WriteDbgTraceInfoWI("USDWrapper::CreateDeviceInfoStorage", v31);
        WiaTrcLib::Free((WiaTrcLib *)v31, v32);
        v33 = (void **)WiaTrace_TraceWithSubCompTraceLevel(0, 0, "CreateDevInfoStg, NULL device property string");
        WiaTrace_ProcessTrace_Ex(v35, v34, (void *)"USDWrapper::CreateDeviceInfoStorage", 4, v33);
        v36 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(0, 0, "  propid = %li", v10);
        WriteDbgTraceInfoWI("USDWrapper::CreateDeviceInfoStorage", v36);
        WiaTrcLib::Free((WiaTrcLib *)v36, v37);
        v38 = (void **)WiaTrace_TraceWithSubCompTraceLevel(0, 0, "  propid = %li", v10);
        WiaTrace_ProcessTrace_Ex(v40, v39, (void *)"USDWrapper::CreateDeviceInfoStorage", 4, v38);
        rgvars[v9 + 1] = SysAllocString(L"Empty");
      }
    }
    ++v8;
    v9 += 3;
  }
  while ( v8 != 16 );
  v5 = v94;
  v22 = *((_QWORD *)v94 + 1);
  if ( v22 )
  {
    v23 = (*(__int64 (__fastcall **)(__int64, __int64, struct tagPROPSPEC *, PROPVARIANT *, int))(*(_QWORD *)v22 + 32LL))(
            v22,
            16,
            v96,
            rgvars,
            2);
    if ( v23 < 0 )
    {
      ReportReadWriteMultipleError(v23, "CreateDevInfoStg", 0, 0, 0x10u, v96);
    }
    else
    {
      v24 = (*(__int64 (__fastcall **)(__int64, __int64, PROPID *, LPOLESTR *))(*(_QWORD *)v22 + 56LL))(
              v22,
              16,
              g_piDeviceInfo,
              g_pszDeviceInfo);
      v23 = v24;
      if ( v24 < 0 )
      {
        v88 = (char *)WiaTrace_TraceLogWithSubComp(0, "CreateDevInfoStg, WritePropertyNames Failed (0x%X)", v24);
        WriteDbgTraceWarningWI("USDWrapper::CreateDeviceInfoStorage", v88);
        WiaTrcLib::Free((WiaTrcLib *)v88, v89);
        v90 = (void **)WiaTrace_TraceWithSubComp(0, "CreateDevInfoStg, WritePropertyNames Failed (0x%X)", v23);
        WiaTrace_ProcessTrace_Ex(v92, v91, (void *)"USDWrapper::CreateDeviceInfoStorage", 2, v90);
      }
      else
      {
        v23 = (**(__int64 (__fastcall ***)(CWIADevInfo *, GUID *, __int64 *))v94)(v94, &IID_IWiaPropertyStorage, &v93);
      }
    }
  }
  else
  {
    v43 = (char *)WiaTrace_TraceLogWithSubComp(0, "CreateDevInfoStg, IPropertyStorage is NULL");
    WriteDbgTraceWarningWI("USDWrapper::CreateDeviceInfoStorage", v43);
    WiaTrcLib::Free((WiaTrcLib *)v43, v44);
    v45 = (void **)WiaTrace_TraceWithSubComp(0, "CreateDevInfoStg, IPropertyStorage is NULL");
    WiaTrace_ProcessTrace_Ex(v47, v46, (void *)"USDWrapper::CreateDeviceInfoStorage", 2, v45);
    v23 = -2147418113;
  }
  FreePropVariantArray(0x10u, rgvars);
  if ( v23 < 0 )
    goto LABEL_61;
  return (struct IWiaPropertyStorage *)v93;
}

```

## disassembly

```asm
0x180015f90  push    rbp
0x180015f92  push    rbx
0x180015f93  push    rsi
0x180015f94  push    rdi
0x180015f95  push    r12
0x180015f97  push    r13
0x180015f99  push    r14
0x180015f9b  push    r15
0x180015f9d  lea     rbp, [rsp-3E8h]
0x180015fa5  sub     rsp, 4E8h
0x180015fac  mov     rax, cs:__security_cookie
0x180015fb3  xor     rax, rsp
0x180015fb6  mov     [rbp+420h+var_50], rax
0x180015fbd  mov     r14, rcx
0x180015fc0  mov     ebx, 100h
0x180015fc5  mov     r8d, ebx; Size
0x180015fc8  lea     rcx, [rbp+420h+var_360]; void *
0x180015fcf  xor     edx, edx; Val
0x180015fd1  call    memset_0
0x180015fd6  mov     edi, 180h
0x180015fdb  lea     rcx, [rsp+520h+rgvars]; void *
0x180015fe0  mov     r8d, edi; Size
0x180015fe3  xor     edx, edx; Val
0x180015fe5  call    memset_0
0x180015fea  mov     r15d, 208h
0x180015ff0  lea     rcx, [rbp+420h+var_260]; void *
0x180015ff7  mov     r8d, r15d; Size
0x180015ffa  xor     edx, edx; Val
0x180015ffc  call    memset_0
0x180016001  mov     ecx, 30h ; '0'; Size
0x180016006  mov     [rsp+520h+var_4F0], 0
0x18001600f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180016014  test    rax, rax
0x180016017  jnz     short loc_18001603E
0x180016019  xor     eax, eax
0x18001601b  mov     rcx, [rbp+420h+var_50]
0x180016022  xor     rcx, rsp; StackCookie
0x180016025  call    __security_check_cookie
0x18001602a  add     rsp, 4E8h
0x180016031  pop     r15
0x180016033  pop     r14
0x180016035  pop     r13
0x180016037  pop     r12
0x180016039  pop     rdi
0x18001603a  pop     rsi
0x18001603b  pop     rbx
0x18001603c  pop     rbp
0x18001603d  retn
0x18001603e  mov     rcx, rax; this
0x180016041  call    ??0CWIADevInfo@@QEAA@XZ; CWIADevInfo::CWIADevInfo(void)
0x180016046  mov     [rsp+520h+var_4E8], rax
0x18001604b  mov     rsi, rax
0x18001604e  test    rax, rax
0x180016051  jz      short loc_180016019
0x180016053  mov     rdx, r14; struct USDWrapper *
0x180016056  mov     rcx, rax; this
0x180016059  call    ?Initialize@CWIADevInfo@@QEAAJPEAVUSDWrapper@@@Z; CWIADevInfo::Initialize(USDWrapper *)
0x18001605e  test    eax, eax
0x180016060  js      loc_180016988
0x180016066  mov     r8, rbx; Size
0x180016069  lea     rcx, [rbp+420h+var_360]; void *
0x180016070  xor     edx, edx; Val
0x180016072  call    memset_0
0x180016077  mov     r8, rdi; Size
0x18001607a  lea     rcx, [rsp+520h+rgvars]; void *
0x18001607f  xor     edx, edx; Val
0x180016081  call    memset_0
0x180016086  mov     r8, r15; Size
0x180016089  lea     rcx, [rbp+420h+var_260]; void *
0x180016090  xor     edx, edx; Val
0x180016092  call    memset_0
0x180016097  xor     r13d, r13d
0x18001609a  lea     rsi, g_piDeviceInfo
0x1800160a1  xor     r15d, r15d
0x1800160a4  lea     ebx, [r13+4]
0x1800160a8  lea     ecx, [rbx-1]
0x1800160ab  mov     r12d, [rsi+r13*4]
0x1800160af  xor     edi, edi
0x1800160b1  mov     rax, r13
0x1800160b4  mov     [rsp+r15+520h+var_4D8], rdi
0x1800160b9  add     rax, rax
0x1800160bc  mov     [rbp+rax*8+420h+var_360.ulKind], 1
0x1800160c7  mov     dword ptr [rbp+rax*8+420h+var_360.8], r12d
0x1800160cf  lea     eax, [rdi+8]
0x1800160d2  mov     word ptr [rsp+r15+520h+rgvars], ax
0x1800160d8  cmp     r12d, 0Ah
0x1800160dc  ja      short loc_180016132
0x1800160de  jz      loc_1800166E9
0x1800160e4  mov     eax, r12d
0x1800160e7  sub     eax, 2
0x1800160ea  jz      loc_1800161C2
0x1800160f0  sub     eax, 1
0x1800160f3  jz      loc_1800165E1
0x1800160f9  sub     eax, 1
0x1800160fc  jz      loc_1800165A1
0x180016102  sub     eax, 1
0x180016105  jz      loc_1800166A0
0x18001610b  sub     eax, 1
0x18001610e  jz      loc_180016561
0x180016114  sub     eax, 1
0x180016117  jz      loc_180016441
0x18001611d  sub     eax, 1
0x180016120  jnz     loc_18001636B
0x180016126  lea     rdi, aLocal; "local"
0x18001612d  jmp     loc_180016220
0x180016132  mov     eax, r12d
0x180016135  sub     eax, 0Bh
0x180016138  jz      loc_1800168AF
0x18001613e  sub     eax, 1
0x180016141  jz      loc_180016521
0x180016147  sub     eax, 1
0x18001614a  jz      loc_180016869
0x180016150  sub     eax, 1
0x180016153  jz      loc_18001683A
0x180016159  sub     eax, 1
0x18001615c  jnz     loc_1800164D8
0x180016162  lea     rcx, [r14+18h]; struct USDInfo *
0x180016166  lea     rdx, [rbp+420h+var_260]; unsigned __int16 *
0x18001616d  call    ?GetDriverDLLVersion@@YAHPEAVUSDInfo@@PEAGI@Z; GetDriverDLLVersion(USDInfo *,ushort *,uint)
0x180016172  test    eax, eax
0x180016174  jz      loc_1800167CB
0x18001617a  lea     r9, [rbp+420h+var_260]
0x180016181  xor     edx, edx
0x180016183  lea     r8, aDriverVersionW; "Driver version: %ws"
0x18001618a  mov     ecx, ebx
0x18001618c  lea     rdi, [rbp+420h+var_260]
0x180016193  call    WiaTrace_TraceLogWithSubCompTraceLevel
0x180016198  mov     rdx, rax; char *
0x18001619b  lea     rcx, aUsdwrapperCrea_0; "USDWrapper::CreateDeviceInfoStorage"
0x1800161a2  mov     rbx, rax
0x1800161a5  call    ?WriteDbgTraceInfoWI@@YAXPEAD0ZZ; WriteDbgTraceInfoWI(char *,char *,...)
0x1800161aa  mov     rcx, rbx; this
0x1800161ad  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x1800161b2  lea     r9, [rbp+420h+var_260]
0x1800161b9  lea     r8, aDriverVersionW; "Driver version: %ws"
0x1800161c0  jmp     short loc_180016200
0x1800161c2  mov     rdi, [r14+150h]
0x1800161c9  lea     r8, aDeviceInternal; "Device internal name: %ws"
0x1800161d0  mov     r9, rdi
0x1800161d3  xor     edx, edx
0x1800161d5  mov     ecx, ebx
0x1800161d7  call    WiaTrace_TraceLogWithSubCompTraceLevel
0x1800161dc  mov     rdx, rax; char *
0x1800161df  lea     rcx, aUsdwrapperCrea_0; "USDWrapper::CreateDeviceInfoStorage"
0x1800161e6  mov     rbx, rax
0x1800161e9  call    ?WriteDbgTraceInfoWI@@YAXPEAD0ZZ; WriteDbgTraceInfoWI(char *,char *,...)
0x1800161ee  mov     rcx, rbx; this
0x1800161f1  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x1800161f6  lea     r8, aDeviceInternal; "Device internal name: %ws"
0x1800161fd  mov     r9, rdi
0x180016200  xor     edx, edx
0x180016202  lea     ebx, [rdx+4]
0x180016205  mov     ecx, ebx
0x180016207  call    WiaTrace_TraceWithSubCompTraceLevel
0x18001620c  mov     r9d, ebx; int
0x18001620f  mov     [rsp+520h+lpMem], rax; lpMem
0x180016214  lea     r8, aUsdwrapperCrea_0; "USDWrapper::CreateDeviceInfoStorage"
0x18001621b  call    WiaTrace_ProcessTrace_Ex
0x180016220  mov     eax, 8
0x180016225  cmp     word ptr [rsp+r15+520h+rgvars], ax
0x18001622b  jz      loc_1800162F4
0x180016231  mov     r12d, 10h
0x180016237  inc     r13
0x18001623a  add     r15, 18h
0x18001623e  lea     ecx, [r12-0Dh]
0x180016243  cmp     r13, r12
0x180016246  jnz     loc_1800160AB
0x18001624c  mov     rsi, [rsp+520h+var_4E8]
0x180016251  mov     rbx, [rsi+8]
0x180016255  test    rbx, rbx
0x180016258  jz      loc_180016481
0x18001625e  mov     rax, [rbx]
0x180016261  lea     r9, [rsp+520h+rgvars]
0x180016266  lea     r8, [rbp+420h+var_360]
0x18001626d  mov     dword ptr [rsp+520h+lpMem], 2
0x180016275  mov     edx, r12d
0x180016278  mov     rcx, rbx
0x18001627b  mov     rax, [rax+20h]
0x18001627f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016284  mov     edi, eax
0x180016286  test    eax, eax
0x180016288  js      loc_18001695E
0x18001628e  mov     rax, [rbx]
0x180016291  lea     r9, g_pszDeviceInfo
0x180016298  lea     r8, g_piDeviceInfo
0x18001629f  mov     edx, r12d
0x1800162a2  mov     rcx, rbx
0x1800162a5  mov     rax, [rax+38h]
0x1800162a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800162ae  mov     edi, eax
0x1800162b0  test    eax, eax
0x1800162b2  js      loc_180016906
0x1800162b8  mov     rax, [rsi]
0x1800162bb  lea     r8, [rsp+520h+var_4F0]
0x1800162c0  lea     rdx, IID_IWiaPropertyStorage
0x1800162c7  mov     rcx, rsi
0x1800162ca  mov     rax, [rax]
0x1800162cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800162d2  mov     edi, eax
0x1800162d4  lea     rdx, [rsp+520h+rgvars]; rgvars
0x1800162d9  mov     ecx, r12d; cVariants
0x1800162dc  call    cs:__imp_FreePropVariantArray
0x1800162e2  test    edi, edi
0x1800162e4  js      loc_180016988
0x1800162ea  mov     rax, [rsp+520h+var_4F0]
0x1800162ef  jmp     loc_18001601B
0x1800162f4  test    rdi, rdi
0x1800162f7  jz      loc_180016380
0x1800162fd  mov     rcx, rdi; psz
0x180016300  call    cs:__imp_SysAllocString
0x180016306  mov     [rsp+r15+520h+var_4D8], rax
0x18001630b  test    rax, rax
0x18001630e  jnz     loc_180016231
0x180016314  lea     rdx, aCreatedevinfos_4; "CreateDevInfoStg, unable to alloc dev i"...
0x18001631b  xor     ecx, ecx
0x18001631d  call    WiaTrace_TraceLogWithSubComp
0x180016322  mov     rdx, rax; char *
0x180016325  lea     rcx, aUsdwrapperCrea_0; "USDWrapper::CreateDeviceInfoStorage"
0x18001632c  mov     rbx, rax
0x18001632f  call    ?WriteDbgTraceWarningWI@@YAXPEAD0ZZ; WriteDbgTraceWarningWI(char *,char *,...)
0x180016334  mov     rcx, rbx; this
0x180016337  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18001633c  lea     rdx, aCreatedevinfos_4; "CreateDevInfoStg, unable to alloc dev i"...
0x180016343  xor     ecx, ecx
0x180016345  call    WiaTrace_TraceWithSubComp
0x18001634a  mov     r9d, 2; int
0x180016350  mov     [rsp+520h+lpMem], rax; lpMem
0x180016355  lea     r8, aUsdwrapperCrea_0; "USDWrapper::CreateDeviceInfoStorage"
0x18001635c  call    WiaTrace_ProcessTrace_Ex
0x180016361  mov     ebx, 4
0x180016366  jmp     loc_180016231
0x18001636b  cmp     eax, 1
0x18001636e  jnz     loc_180016729
0x180016374  lea     rdi, Class
0x18001637b  jmp     loc_180016220
0x180016380  lea     r8, aCreatedevinfos_3; "CreateDevInfoStg, NULL device property "...
0x180016387  xor     edx, edx
0x180016389  xor     ecx, ecx
0x18001638b  call    WiaTrace_TraceLogWithSubCompTraceLevel
0x180016390  mov     rdx, rax; char *
0x180016393  lea     rcx, aUsdwrapperCrea_0; "USDWrapper::CreateDeviceInfoStorage"
0x18001639a  mov     rbx, rax
0x18001639d  call    ?WriteDbgTraceInfoWI@@YAXPEAD0ZZ; WriteDbgTraceInfoWI(char *,char *,...)
0x1800163a2  mov     rcx, rbx; this
0x1800163a5  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x1800163aa  lea     r8, aCreatedevinfos_3; "CreateDevInfoStg, NULL device property "...
0x1800163b1  xor     edx, edx
0x1800163b3  xor     ecx, ecx
0x1800163b5  call    WiaTrace_TraceWithSubCompTraceLevel
0x1800163ba  mov     r9d, 4; int
0x1800163c0  mov     [rsp+520h+lpMem], rax; lpMem
0x1800163c5  lea     r8, aUsdwrapperCrea_0; "USDWrapper::CreateDeviceInfoStorage"
0x1800163cc  call    WiaTrace_ProcessTrace_Ex
0x1800163d1  mov     r9d, r12d
0x1800163d4  lea     r8, aPropidLi; "  propid = %li"
0x1800163db  xor     edx, edx
0x1800163dd  xor     ecx, ecx
0x1800163df  call    WiaTrace_TraceLogWithSubCompTraceLevel
0x1800163e4  mov     rdx, rax; char *
0x1800163e7  lea     rcx, aUsdwrapperCrea_0; "USDWrapper::CreateDeviceInfoStorage"
0x1800163ee  mov     rbx, rax
0x1800163f1  call    ?WriteDbgTraceInfoWI@@YAXPEAD0ZZ; WriteDbgTraceInfoWI(char *,char *,...)
0x1800163f6  mov     rcx, rbx; this
0x1800163f9  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x1800163fe  mov     r9d, r12d
0x180016401  lea     r8, aPropidLi; "  propid = %li"
0x180016408  xor     edx, edx
0x18001640a  xor     ecx, ecx
0x18001640c  call    WiaTrace_TraceWithSubCompTraceLevel
0x180016411  mov     ebx, 4
0x180016416  mov     [rsp+520h+lpMem], rax; lpMem
0x18001641b  mov     r9d, ebx; int
0x18001641e  lea     r8, aUsdwrapperCrea_0; "USDWrapper::CreateDeviceInfoStorage"
0x180016425  call    WiaTrace_ProcessTrace_Ex
0x18001642a  lea     rcx, aEmpty; "Empty"
0x180016431  call    cs:__imp_SysAllocString
0x180016437  mov     [rsp+r15+520h+var_4D8], rax
0x18001643c  jmp     loc_180016231
0x180016441  mov     rdi, [r14+968h]
0x180016448  lea     r8, aDeviceNameWs; "Device name: %ws"
0x18001644f  mov     r9, rdi
0x180016452  xor     edx, edx
0x180016454  mov     ecx, ebx
0x180016456  call    WiaTrace_TraceLogWithSubCompTraceLevel
0x18001645b  mov     rdx, rax; char *
0x18001645e  lea     rcx, aUsdwrapperCrea_0; "USDWrapper::CreateDeviceInfoStorage"
0x180016465  mov     rbx, rax
0x180016468  call    ?WriteDbgTraceInfoWI@@YAXPEAD0ZZ; WriteDbgTraceInfoWI(char *,char *,...)
0x18001646d  mov     rcx, rbx; this
0x180016470  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180016475  lea     r8, aDeviceNameWs; "Device name: %ws"
0x18001647c  jmp     loc_1800161FD
0x180016481  lea     rdx, aCreatedevinfos_0; "CreateDevInfoStg, IPropertyStorage is N"...
0x180016488  xor     ecx, ecx
0x18001648a  call    WiaTrace_TraceLogWithSubComp
0x18001648f  mov     rdx, rax; char *
0x180016492  lea     rcx, aUsdwrapperCrea_0; "USDWrapper::CreateDeviceInfoStorage"
0x180016499  mov     rbx, rax
0x18001649c  call    ?WriteDbgTraceWarningWI@@YAXPEAD0ZZ; WriteDbgTraceWarningWI(char *,char *,...)
0x1800164a1  mov     rcx, rbx; this
  ... truncated ...
```
