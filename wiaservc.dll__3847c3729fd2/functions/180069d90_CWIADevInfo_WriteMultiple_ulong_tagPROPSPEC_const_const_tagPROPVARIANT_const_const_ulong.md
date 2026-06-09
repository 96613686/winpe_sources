# CWIADevInfo::WriteMultiple(ulong,tagPROPSPEC const * const,tagPROPVARIANT const * const,ulong)

- ea: `0x180069d90`
- end: `0x18006a0bb`
- name: `?WriteMultiple@CWIADevInfo@@UEAAJKQEBUtagPROPSPEC@@QEBUtagPROPVARIANT@@K@Z`
- size: `811`
- prototype: `__int64 __fastcall(CWIADevInfo *__hidden this, unsigned int, const struct tagPROPSPEC *const, const struct tagPROPVARIANT *const, unsigned int)`
- caller_count: `0`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callees

- `0x18000b6a0`
- `0x18000c7c0`
- `0x18000cba0`
- `0x18000d770`
- `0x18000da10`
- `0x18000dd00`
- `0x1800202b8`
- `0x18002de18`
- `0x18002def8`
- `0x18002e9d8`
- `0x18002eab4`
- `0x18006953c`
- `0x180069b10`
- `0x180069d90`
- `0x180078010`

## import_xrefs

- `KERNEL32!LocalFree` at `0x180069f43`
- `KERNEL32!LocalFree` at `0x180069f43`
- `KERNEL32!LocalAlloc` at `0x180069e0c`
- `KERNEL32!LocalAlloc` at `0x180069e0c`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180069df0`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180069df0`

## string_xrefs

- `0x180069f4b`: `CWIADevInfo::WriteMultiple, out of memory`
- `0x180069f71`: `CWIADevInfo::WriteMultiple, out of memory`
- `0x180069ef7`: `CWIADevInfo::WriteMultiple, updated registry, but failed to update property storage`
- `0x180069f1d`: `CWIADevInfo::WriteMultiple, updated registry, but failed to update property storage`
- `0x180069e68`: `CWIADevInfo::WriteMultiple, property not allowed to be written`
- `0x180069e8e`: `CWIADevInfo::WriteMultiple, property not allowed to be written`
- `0x180069da8`: `CWIADevInfo::WriteMultiple`
- `0x180069e77`: `CWIADevInfo::WriteMultiple`
- `0x180069ea5`: `CWIADevInfo::WriteMultiple`
- `0x180069f06`: `CWIADevInfo::WriteMultiple`
- `0x180069f34`: `CWIADevInfo::WriteMultiple`
- `0x180069f5a`: `CWIADevInfo::WriteMultiple`
- `0x180069f88`: `CWIADevInfo::WriteMultiple`
- `0x180069fbf`: `CWIADevInfo::WriteMultiple`
- `0x180069ff5`: `CWIADevInfo::WriteMultiple`
- `0x18006a005`: `Error attempting to update device settings, could not impersonate client, therefore we do not have sufficient credentials to write to the registry`
- `0x18006a027`: `Error attempting to update device settings, could not impersonate client, therefore we do not have sufficient credentials to write to the registry`
- `0x180069fab`: `CWIADevInfo::WriteMultiple, could not revert to self, hr = %08X`
- `0x180069fd9`: `CWIADevInfo::WriteMultiple, could not revert to self, hr = %08X`

## pseudocode

```c
__int64 __fastcall CWIADevInfo::WriteMultiple(
        struct IWiaPropertyStorage *this,
        unsigned int a2,
        const struct tagPROPSPEC *const a3,
        const struct tagPROPVARIANT *const a4)
{
  __int64 v5; // rbp
  struct tagWiaTraceData_Type *v8; // rax
  char *v9; // rdx
  unsigned int v10; // r8d
  HRESULT updated; // edi
  struct tagPROPSPEC *v13; // r14
  unsigned int i; // ebx
  __int64 v15; // rdi
  struct tagPROPSPEC *v16; // r8
  struct tagPROPSPEC *v17; // rdi
  char *v18; // rbx
  void *v19; // rdx
  void **v20; // rax
  void *v21; // rdx
  __int64 v22; // rcx
  char *v23; // rbx
  void *v24; // rdx
  void **v25; // rax
  void *v26; // rdx
  __int64 v27; // rcx
  char *v28; // rbx
  void *v29; // rdx
  void **v30; // rax
  void *v31; // rdx
  __int64 v32; // rcx
  int v33; // eax
  HRESULT v34; // ebp
  char *v35; // rbx
  void *v36; // rdx
  void **v37; // rax
  void *v38; // rdx
  __int64 v39; // rcx
  char *v40; // rbx
  void *v41; // rdx
  void **v42; // rax
  void *v43; // rdx
  __int64 v44; // rcx
  char *v45; // rbx
  void *v46; // rdx
  void **v47; // rax
  void *v48; // rdx
  __int64 v49; // rcx
  unsigned int lpMem; // [rsp+20h] [rbp-98h]
  _BYTE v51[136]; // [rsp+30h] [rbp-88h] BYREF

  v5 = a2;
  v8 = (struct tagWiaTraceData_Type *)WiaTrace_Trace("CWIADevInfo::WriteMultiple");
  CWiaTraceFn::CWiaTraceFn((CWiaTraceFn *)v51, v9, v10, "CWIADevInfo::WriteMultiple", lpMem, v8);
  if ( (unsigned int)v5 > 0xAAAAAAA )
  {
    v45 = (char *)WiaTrace_TraceLog("Invalid cpspec argument (%u) (E_INVALIDARG)");
    WriteDbgTraceErrorWI("CWIADevInfo::WriteMultiple", v45);
    WiaTrcLib::Free((WiaTrcLib *)v45, v46);
    v47 = (void **)WiaTrace_Trace("Invalid cpspec argument (%u) (E_INVALIDARG)", v5);
    WiaTrace_ProcessTrace_Ex(v49, v48, (void *)"CWIADevInfo::WriteMultiple", 1, v47);
    CWiaTraceFn::~CWiaTraceFn((CWiaTraceFn *)v51);
    return 2147942487LL;
  }
  else if ( (_DWORD)v5 )
  {
    updated = CoImpersonateClient();
    if ( updated < 0 )
    {
      v40 = (char *)WiaTrace_TraceLog("Error attempting to update device settings, could not impersonate client, therefor"
                                      "e we do not have sufficient credentials to write to the registry");
      WriteDbgTraceErrorWI("CWIADevInfo::WriteMultiple", v40);
      WiaTrcLib::Free((WiaTrcLib *)v40, v41);
      v42 = (void **)WiaTrace_Trace(
                       "Error attempting to update device settings, could not impersonate client, therefore we do not hav"
                       "e sufficient credentials to write to the registry");
      WiaTrace_ProcessTrace_Ex(v44, v43, (void *)"CWIADevInfo::WriteMultiple", 1, v42);
    }
    else
    {
      v13 = (struct tagPROPSPEC *)LocalAlloc(0x40u, 16 * v5);
      if ( v13 )
      {
        for ( i = 0; i < (unsigned int)v5; ++i )
        {
          v15 = i;
          v16 = &v13[v15];
          v17 = (struct tagPROPSPEC *)&a3[v15];
          v16->ulKind = 1;
          if ( (int)GetPropID(this, v17, v16) < 0 || v17->propid != 6 && v17->propid != 7 && v17->propid != 12 )
          {
            v18 = (char *)WiaTrace_TraceLog("CWIADevInfo::WriteMultiple, property not allowed to be written");
            WriteDbgTraceErrorWI("CWIADevInfo::WriteMultiple", v18);
            WiaTrcLib::Free((WiaTrcLib *)v18, v19);
            v20 = (void **)WiaTrace_Trace("CWIADevInfo::WriteMultiple, property not allowed to be written");
            WiaTrace_ProcessTrace_Ex(v22, v21, (void *)"CWIADevInfo::WriteMultiple", 1, v20);
            updated = -2147024891;
            goto LABEL_17;
          }
        }
        updated = CWIADevInfo::UpdateDeviceProperties((CWIADevInfo *)this, v5, v13, a4);
        if ( updated >= 0 )
        {
          updated = (*((__int64 (__fastcall **)(struct IWiaPropertyStorageVtbl *, _QWORD, struct tagPROPSPEC *, const struct tagPROPVARIANT *const, int))this[1].lpVtbl->QueryInterface
                     + 4))(
                      this[1].lpVtbl,
                      (unsigned int)v5,
                      v13,
                      a4,
                      2);
          if ( updated < 0 )
          {
            v23 = (char *)WiaTrace_TraceLog("CWIADevInfo::WriteMultiple, updated registry, but failed to update property storage");
            WriteDbgTraceErrorWI("CWIADevInfo::WriteMultiple", v23);
            WiaTrcLib::Free((WiaTrcLib *)v23, v24);
            v25 = (void **)WiaTrace_Trace("CWIADevInfo::WriteMultiple, updated registry, but failed to update property storage");
            WiaTrace_ProcessTrace_Ex(v27, v26, (void *)"CWIADevInfo::WriteMultiple", 1, v25);
          }
        }
LABEL_17:
        LocalFree(v13);
      }
      else
      {
        v28 = (char *)WiaTrace_TraceLog("CWIADevInfo::WriteMultiple, out of memory");
        WriteDbgTraceErrorWI("CWIADevInfo::WriteMultiple", v28);
        WiaTrcLib::Free((WiaTrcLib *)v28, v29);
        v30 = (void **)WiaTrace_Trace("CWIADevInfo::WriteMultiple, out of memory");
        WiaTrace_ProcessTrace_Ex(v32, v31, (void *)"CWIADevInfo::WriteMultiple", 1, v30);
        updated = -2147024882;
      }
      v33 = SafeCoRevertToSelf();
      v34 = v33;
      if ( v33 < 0 )
      {
        v35 = (char *)WiaTrace_TraceLogWithSubComp(
                        1,
                        "CWIADevInfo::WriteMultiple, could not revert to self, hr = %08X",
                        v33);
        WriteDbgTraceWarningWI("CWIADevInfo::WriteMultiple", v35);
        WiaTrcLib::Free((WiaTrcLib *)v35, v36);
        v37 = (void **)WiaTrace_TraceWithSubComp(
                         1,
                         "CWIADevInfo::WriteMultiple, could not revert to self, hr = %08X",
                         v34);
        WiaTrace_ProcessTrace_Ex(v39, v38, (void *)"CWIADevInfo::WriteMultiple", 2, v37);
        updated = v34;
      }
    }
    CWiaTraceFn::~CWiaTraceFn((CWiaTraceFn *)v51);
    return (unsigned int)updated;
  }
  else
  {
    CWiaTraceFn::~CWiaTraceFn((CWiaTraceFn *)v51);
    return 0;
  }
}

```

## disassembly

```asm
0x180069d90  push    rbx
0x180069d92  push    rbp
0x180069d93  push    rdi
0x180069d94  push    r12
0x180069d96  push    r13
0x180069d98  push    r14
0x180069d9a  push    r15
0x180069d9c  sub     rsp, 80h
0x180069da3  mov     r15, rcx
0x180069da6  mov     ebp, edx
0x180069da8  lea     r14, aCwiadevinfoWri; "CWIADevInfo::WriteMultiple"
0x180069daf  mov     r12, r9
0x180069db2  mov     rcx, r14
0x180069db5  mov     r13, r8
0x180069db8  call    WiaTrace_Trace
0x180069dbd  mov     r9, r14; char *
0x180069dc0  mov     [rsp+0B8h+var_90], rax; struct tagWiaTraceData_Type *
0x180069dc5  lea     rcx, [rsp+0B8h+var_88]; this
0x180069dca  call    ??0CWiaTraceFn@@QEAA@PEADK0KPEAUtagWiaTraceData_Type@@@Z; CWiaTraceFn::CWiaTraceFn(char *,ulong,char *,ulong,tagWiaTraceData_Type *)
0x180069dcf  cmp     ebp, 0AAAAAAAh
0x180069dd5  ja      loc_18006A054
0x180069ddb  test    ebp, ebp
0x180069ddd  jnz     short loc_180069DF0
0x180069ddf  lea     rcx, [rsp+0B8h+var_88]; this
0x180069de4  call    ??1CWiaTraceFn@@QEAA@XZ; CWiaTraceFn::~CWiaTraceFn(void)
0x180069de9  xor     eax, eax
0x180069deb  jmp     loc_18006A0A8
0x180069df0  call    cs:__imp_CoImpersonateClient
0x180069df6  mov     edi, eax
0x180069df8  test    eax, eax
0x180069dfa  js      loc_18006A005
0x180069e00  mov     rdx, rbp
0x180069e03  mov     ecx, 40h ; '@'; uFlags
0x180069e08  shl     rdx, 4; uBytes
0x180069e0c  call    cs:__imp_LocalAlloc
0x180069e12  mov     r14, rax
0x180069e15  test    rax, rax
0x180069e18  jz      loc_180069F4B
0x180069e1e  xor     ebx, ebx
0x180069e20  cmp     ebx, ebp
0x180069e22  jnb     loc_180069EBB
0x180069e28  mov     ecx, ebx
0x180069e2a  add     rcx, rcx
0x180069e2d  lea     rdi, ds:0[rcx*8]
0x180069e35  lea     r8, [r14+rcx*8]; struct tagPROPSPEC *
0x180069e39  add     rdi, r13
0x180069e3c  mov     rdx, rdi; struct tagPROPSPEC *
0x180069e3f  mov     dword ptr [r8], 1
0x180069e46  mov     rcx, r15; struct IWiaPropertyStorage *
0x180069e49  call    ?GetPropID@@YAJPEAUIWiaPropertyStorage@@PEAUtagPROPSPEC@@1@Z; GetPropID(IWiaPropertyStorage *,tagPROPSPEC *,tagPROPSPEC *)
0x180069e4e  test    eax, eax
0x180069e50  js      short loc_180069E68
0x180069e52  mov     ecx, [rdi+8]
0x180069e55  sub     ecx, 6
0x180069e58  jz      short loc_180069E64
0x180069e5a  sub     ecx, 1
0x180069e5d  jz      short loc_180069E64
0x180069e5f  cmp     ecx, 5
0x180069e62  jnz     short loc_180069E68
0x180069e64  inc     ebx
0x180069e66  jmp     short loc_180069E20
0x180069e68  lea     rcx, aCwiadevinfoWri_4; "CWIADevInfo::WriteMultiple, property no"...
0x180069e6f  call    WiaTrace_TraceLog
0x180069e74  mov     rdx, rax; char *
0x180069e77  lea     rcx, aCwiadevinfoWri; "CWIADevInfo::WriteMultiple"
0x180069e7e  mov     rbx, rax
0x180069e81  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180069e86  mov     rcx, rbx; this
0x180069e89  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180069e8e  lea     rcx, aCwiadevinfoWri_4; "CWIADevInfo::WriteMultiple, property no"...
0x180069e95  call    WiaTrace_Trace
0x180069e9a  mov     r9d, 1; int
0x180069ea0  mov     [rsp+0B8h+lpMem], rax; lpMem
0x180069ea5  lea     r8, aCwiadevinfoWri; "CWIADevInfo::WriteMultiple"
0x180069eac  call    WiaTrace_ProcessTrace_Ex
0x180069eb1  mov     edi, 80070005h
0x180069eb6  jmp     loc_180069F40
0x180069ebb  mov     r9, r12; struct tagPROPVARIANT *
0x180069ebe  mov     r8, r14; struct tagPROPSPEC *
0x180069ec1  mov     edx, ebp; unsigned int
0x180069ec3  mov     rcx, r15; this
0x180069ec6  call    ?UpdateDeviceProperties@CWIADevInfo@@AEAAJKPEBUtagPROPSPEC@@PEBUtagPROPVARIANT@@@Z; CWIADevInfo::UpdateDeviceProperties(ulong,tagPROPSPEC const *,tagPROPVARIANT const *)
0x180069ecb  mov     edi, eax
0x180069ecd  test    eax, eax
0x180069ecf  js      short loc_180069F40
0x180069ed1  mov     rcx, [r15+8]
0x180069ed5  mov     r9, r12
0x180069ed8  mov     r8, r14
0x180069edb  mov     dword ptr [rsp+0B8h+lpMem], 2
0x180069ee3  mov     edx, ebp
0x180069ee5  mov     rax, [rcx]
0x180069ee8  mov     rax, [rax+20h]
0x180069eec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069ef1  mov     edi, eax
0x180069ef3  test    eax, eax
0x180069ef5  jns     short loc_180069F40
0x180069ef7  lea     rcx, aCwiadevinfoWri_0; "CWIADevInfo::WriteMultiple, updated reg"...
0x180069efe  call    WiaTrace_TraceLog
0x180069f03  mov     rdx, rax; char *
0x180069f06  lea     rcx, aCwiadevinfoWri; "CWIADevInfo::WriteMultiple"
0x180069f0d  mov     rbx, rax
0x180069f10  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180069f15  mov     rcx, rbx; this
0x180069f18  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180069f1d  lea     rcx, aCwiadevinfoWri_0; "CWIADevInfo::WriteMultiple, updated reg"...
0x180069f24  call    WiaTrace_Trace
0x180069f29  mov     r9d, 1; int
0x180069f2f  mov     [rsp+0B8h+lpMem], rax; lpMem
0x180069f34  lea     r8, aCwiadevinfoWri; "CWIADevInfo::WriteMultiple"
0x180069f3b  call    WiaTrace_ProcessTrace_Ex
0x180069f40  mov     rcx, r14; hMem
0x180069f43  call    cs:__imp_LocalFree
0x180069f49  jmp     short loc_180069F99
0x180069f4b  lea     rcx, aCwiadevinfoWri_2; "CWIADevInfo::WriteMultiple, out of memo"...
0x180069f52  call    WiaTrace_TraceLog
0x180069f57  mov     rdx, rax; char *
0x180069f5a  lea     rcx, aCwiadevinfoWri; "CWIADevInfo::WriteMultiple"
0x180069f61  mov     rbx, rax
0x180069f64  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180069f69  mov     rcx, rbx; this
0x180069f6c  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180069f71  lea     rcx, aCwiadevinfoWri_2; "CWIADevInfo::WriteMultiple, out of memo"...
0x180069f78  call    WiaTrace_Trace
0x180069f7d  mov     r9d, 1; int
0x180069f83  mov     [rsp+0B8h+lpMem], rax; lpMem
0x180069f88  lea     r8, aCwiadevinfoWri; "CWIADevInfo::WriteMultiple"
0x180069f8f  call    WiaTrace_ProcessTrace_Ex
0x180069f94  mov     edi, 8007000Eh
0x180069f99  call    ?SafeCoRevertToSelf@@YAJXZ; SafeCoRevertToSelf(void)
0x180069f9e  mov     ebp, eax
0x180069fa0  test    eax, eax
0x180069fa2  jns     loc_18006A046
0x180069fa8  mov     r8d, eax
0x180069fab  lea     rdx, aCwiadevinfoWri_1; "CWIADevInfo::WriteMultiple, could not r"...
0x180069fb2  mov     ecx, 1
0x180069fb7  call    WiaTrace_TraceLogWithSubComp
0x180069fbc  mov     rdx, rax; char *
0x180069fbf  lea     rcx, aCwiadevinfoWri; "CWIADevInfo::WriteMultiple"
0x180069fc6  mov     rbx, rax
0x180069fc9  call    ?WriteDbgTraceWarningWI@@YAXPEAD0ZZ; WriteDbgTraceWarningWI(char *,char *,...)
0x180069fce  mov     rcx, rbx; this
0x180069fd1  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180069fd6  mov     r8d, ebp
0x180069fd9  lea     rdx, aCwiadevinfoWri_1; "CWIADevInfo::WriteMultiple, could not r"...
0x180069fe0  mov     ecx, 1
0x180069fe5  call    WiaTrace_TraceWithSubComp
0x180069fea  mov     r9d, 2; int
0x180069ff0  mov     [rsp+0B8h+lpMem], rax; lpMem
0x180069ff5  lea     r8, aCwiadevinfoWri; "CWIADevInfo::WriteMultiple"
0x180069ffc  call    WiaTrace_ProcessTrace_Ex
0x18006a001  mov     edi, ebp
0x18006a003  jmp     short loc_18006A046
0x18006a005  lea     rcx, aErrorAttemptin; "Error attempting to update device setti"...
0x18006a00c  call    WiaTrace_TraceLog
0x18006a011  mov     rdx, rax; char *
0x18006a014  mov     rcx, r14; char *
0x18006a017  mov     rbx, rax
0x18006a01a  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18006a01f  mov     rcx, rbx; this
0x18006a022  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18006a027  lea     rcx, aErrorAttemptin; "Error attempting to update device setti"...
0x18006a02e  call    WiaTrace_Trace
0x18006a033  mov     r9d, 1; int
0x18006a039  mov     [rsp+0B8h+lpMem], rax; lpMem
0x18006a03e  mov     r8, r14; int
0x18006a041  call    WiaTrace_ProcessTrace_Ex
0x18006a046  lea     rcx, [rsp+0B8h+var_88]; this
0x18006a04b  call    ??1CWiaTraceFn@@QEAA@XZ; CWiaTraceFn::~CWiaTraceFn(void)
0x18006a050  mov     eax, edi
0x18006a052  jmp     short loc_18006A0A8
0x18006a054  mov     edx, ebp
0x18006a056  lea     rcx, aInvalidCpspecA; "Invalid cpspec argument (%u) (E_INVALID"...
0x18006a05d  call    WiaTrace_TraceLog
0x18006a062  mov     rdx, rax; char *
0x18006a065  mov     rcx, r14; char *
0x18006a068  mov     rbx, rax
0x18006a06b  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18006a070  mov     rcx, rbx; this
0x18006a073  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18006a078  mov     edx, ebp
0x18006a07a  lea     rcx, aInvalidCpspecA; "Invalid cpspec argument (%u) (E_INVALID"...
0x18006a081  call    WiaTrace_Trace
0x18006a086  mov     r9d, 1; int
0x18006a08c  mov     [rsp+0B8h+lpMem], rax; lpMem
0x18006a091  mov     r8, r14; int
0x18006a094  call    WiaTrace_ProcessTrace_Ex
0x18006a099  lea     rcx, [rsp+0B8h+var_88]; this
0x18006a09e  call    ??1CWiaTraceFn@@QEAA@XZ; CWiaTraceFn::~CWiaTraceFn(void)
0x18006a0a3  mov     eax, 80070057h
0x18006a0a8  add     rsp, 80h
0x18006a0af  pop     r15
0x18006a0b1  pop     r14
0x18006a0b3  pop     r13
0x18006a0b5  pop     r12
0x18006a0b7  pop     rdi
0x18006a0b8  pop     rbp
0x18006a0b9  pop     rbx
0x18006a0ba  retn
```
