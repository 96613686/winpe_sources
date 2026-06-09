# CWiaPropStg::SetPropertyStream(_GUID *,IWiaItem *,IStream *)

- ea: `0x18005da08`
- end: `0x18005dd26`
- name: `?SetPropertyStream@CWiaPropStg@@QEAAJPEAU_GUID@@PEAUIWiaItem@@PEAUIStream@@@Z`
- size: `798`
- prototype: `int(CWiaPropStg *__hidden this, struct _GUID *, struct IWiaItem *, struct IStream *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18006ab50`

## callees

- `0x18000cba0`
- `0x18000d770`
- `0x18000da10`
- `0x1800202b8`
- `0x18002de18`
- `0x18002def8`
- `0x18005d490`
- `0x18005da08`
- `0x180078010`

## import_xrefs

- `KERNEL32!LocalFree` at `0x18005dcda`
- `KERNEL32!LocalFree` at `0x18005dd1b`
- `KERNEL32!LocalFree` at `0x18005dcda`
- `KERNEL32!LocalFree` at `0x18005dd1b`
- `ole32!PropVariantClear` at `0x18005dd04`
- `ole32!PropVariantClear` at `0x18005dd04`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18005db24`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18005db24`
- `api-ms-win-core-com-l2-1-1!StgOpenPropStg` at `0x18005db5a`
- `api-ms-win-core-com-l2-1-1!StgOpenPropStg` at `0x18005db5a`

## string_xrefs

- `0x18005dab4`: `CWiaPropStg::SetPropertyStream, Writing Compatibility ID failed!`
- `0x18005dada`: `CWiaPropStg::SetPropertyStream, Writing Compatibility ID failed!`
- `0x18005dbab`: `CWiaPropStg::SetPropertyStream, open storage failed 0x%X`
- `0x18005dbd3`: `CWiaPropStg::SetPropertyStream, open storage failed 0x%X`
- `0x18005dc8a`: `CWiaPropStg::SetPropertyStream, WriteMultiple failed`
- `0x18005dcb0`: `CWiaPropStg::SetPropertyStream, WriteMultiple failed`

## pseudocode

```c
__int64 __fastcall CWiaPropStg::SetPropertyStream(
        CWiaPropStg *this,
        struct _GUID *a2,
        struct IWiaItem *a3,
        IUnknown *a4)
{
  __int64 v6; // rax
  HRESULT PropsFromStorage; // edi
  char *v8; // rbx
  void *v9; // rdx
  void **v10; // rax
  void *v11; // rdx
  __int64 v12; // rcx
  int v14; // esi
  CWiaPropStg *v15; // rcx
  char *v16; // rbx
  void *v17; // rdx
  void **v18; // rax
  void *v19; // rdx
  __int64 v20; // rcx
  int v21; // esi
  char *v22; // rbx
  void *v23; // rdx
  void **v24; // rax
  void *v25; // rdx
  __int64 v26; // rcx
  char *v27; // rbx
  void *v28; // rdx
  void **v29; // rax
  void *v30; // rdx
  __int64 v31; // rcx
  __int64 i; // rbx
  IPropertyStorage *ppPropStg; // [rsp+60h] [rbp-60h] BYREF
  HLOCAL v34; // [rsp+68h] [rbp-58h] BYREF
  HLOCAL hMem; // [rsp+70h] [rbp-50h] BYREF
  int v36; // [rsp+78h] [rbp-48h] BYREF
  __int64 v37; // [rsp+80h] [rbp-40h]
  __int16 v38; // [rsp+88h] [rbp-38h] BYREF
  struct _GUID *v39; // [rsp+90h] [rbp-30h]
  unsigned int v40; // [rsp+C8h] [rbp+8h] BYREF
  int v41; // [rsp+CCh] [rbp+Ch]

  v41 = HIDWORD(this);
  ppPropStg = 0;
  hMem = 0;
  v34 = 0;
  v36 = 1;
  v37 = 4122;
  v40 = 0;
  v6 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&GUID_NULL.Data1;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&GUID_NULL.Data1 )
    v6 = *(_QWORD *)a2->Data4 - *(_QWORD *)GUID_NULL.Data4;
  if ( v6 )
  {
    v38 = 72;
    v39 = a2;
    PropsFromStorage = ((__int64 (__fastcall *)(struct IWiaItem *, __int64, int *, __int16 *, int))a3[1].lpVtbl->AnalyzeItem)(
                         &a3[1],
                         1,
                         &v36,
                         &v38,
                         4098);
    if ( PropsFromStorage < 0 )
    {
      v8 = (char *)WiaTrace_TraceLog("CWiaPropStg::SetPropertyStream, Writing Compatibility ID failed!");
      WriteDbgTraceErrorWI("CWiaPropStg::SetPropertyStream", v8);
      WiaTrcLib::Free((WiaTrcLib *)v8, v9);
      v10 = (void **)WiaTrace_Trace("CWiaPropStg::SetPropertyStream, Writing Compatibility ID failed!");
      WiaTrace_ProcessTrace_Ex(v12, v11, (void *)"CWiaPropStg::SetPropertyStream", 1, v10);
      return (unsigned int)PropsFromStorage;
    }
  }
  if ( a4 )
  {
    v14 = 0;
    PropsFromStorage = CoImpersonateClient();
    if ( PropsFromStorage < 0 )
      goto LABEL_15;
    v14 = 1;
    PropsFromStorage = StgOpenPropStg(a4, &GUID_NULL, 0, 0, &ppPropStg);
    if ( PropsFromStorage < 0 )
    {
      v16 = (char *)WiaTrace_TraceLog("CWiaPropStg::SetPropertyStream, open storage failed 0x%X");
      WriteDbgTraceErrorWI("CWiaPropStg::SetPropertyStream", v16);
      WiaTrcLib::Free((WiaTrcLib *)v16, v17);
      v18 = (void **)WiaTrace_Trace("CWiaPropStg::SetPropertyStream, open storage failed 0x%X", PropsFromStorage);
      WiaTrace_ProcessTrace_Ex(v20, v19, (void *)"CWiaPropStg::SetPropertyStream", 1, v18);
    }
    else
    {
      PropsFromStorage = CWiaPropStg::GetPropsFromStorage(
                           v15,
                           ppPropStg,
                           &v40,
                           (struct tagPROPSPEC **)&hMem,
                           (struct tagPROPVARIANT **)&v34);
      if ( !ppPropStg )
        goto LABEL_15;
      ((void (__fastcall *)(IPropertyStorage *))ppPropStg->lpVtbl->Release)(ppPropStg);
    }
    ppPropStg = 0;
LABEL_15:
    if ( v14 )
    {
      v21 = SafeCoRevertToSelf();
      if ( v21 < 0 )
      {
        v22 = (char *)WiaTrace_TraceLog("SafeCoRevertToSelf failed (0x%X)");
        WriteDbgTraceErrorWI("CWiaPropStg::SetPropertyStream", v22);
        WiaTrcLib::Free((WiaTrcLib *)v22, v23);
        v24 = (void **)WiaTrace_Trace("SafeCoRevertToSelf failed (0x%X)", v21);
        WiaTrace_ProcessTrace_Ex(v26, v25, (void *)"CWiaPropStg::SetPropertyStream", 1, v24);
        PropsFromStorage = v21;
      }
    }
    if ( PropsFromStorage >= 0 )
    {
      PropsFromStorage = ((__int64 (__fastcall *)(struct IWiaItem *, _QWORD, HLOCAL, HLOCAL, int))a3[1].lpVtbl->AnalyzeItem)(
                           &a3[1],
                           v40,
                           hMem,
                           v34,
                           4098);
      if ( PropsFromStorage < 0 )
      {
        v27 = (char *)WiaTrace_TraceLog("CWiaPropStg::SetPropertyStream, WriteMultiple failed");
        WriteDbgTraceErrorWI("CWiaPropStg::SetPropertyStream", v27);
        WiaTrcLib::Free((WiaTrcLib *)v27, v28);
        v29 = (void **)WiaTrace_Trace("CWiaPropStg::SetPropertyStream, WriteMultiple failed");
        WiaTrace_ProcessTrace_Ex(v31, v30, (void *)"CWiaPropStg::SetPropertyStream", 1, v29);
      }
    }
    if ( hMem )
      LocalFree(hMem);
    if ( v34 )
    {
      for ( i = 0; (unsigned int)i < v40; i = (unsigned int)(i + 1) )
        PropVariantClear((PROPVARIANT *)v34 + 3 * i);
      LocalFree(v34);
    }
    return (unsigned int)PropsFromStorage;
  }
  return 0;
}

```

## disassembly

```asm
0x18005da08  mov     rax, rsp
0x18005da0b  mov     [rax+10h], rbx
0x18005da0f  mov     [rax+18h], rsi
0x18005da13  mov     [rax+8], rcx
0x18005da17  push    rdi
0x18005da18  push    r12
0x18005da1a  push    r14
0x18005da1c  sub     rsp, 80h
0x18005da23  mov     rbx, r9
0x18005da26  mov     r14, r8
0x18005da29  mov     qword ptr [rax-60h], 0
0x18005da31  mov     qword ptr [rax-50h], 0
0x18005da39  mov     qword ptr [rax-58h], 0
0x18005da41  mov     r12d, 1
0x18005da47  mov     [rax-48h], r12d
0x18005da4b  mov     qword ptr [rax-40h], 101Ah
0x18005da53  mov     dword ptr [rax+8], 0
0x18005da5a  mov     rax, [rdx]
0x18005da5d  sub     rax, qword ptr cs:GUID_NULL.Data1
0x18005da64  jnz     short loc_18005DA71
0x18005da66  mov     rax, [rdx+8]
0x18005da6a  sub     rax, qword ptr cs:GUID_NULL.Data4
0x18005da71  test    rax, rax
0x18005da74  jz      loc_18005DB15
0x18005da7a  mov     eax, 48h ; 'H'
0x18005da7f  mov     [rsp+98h+var_38], ax
0x18005da84  mov     [rsp+98h+var_30], rdx
0x18005da89  lea     rcx, [r8+8]
0x18005da8d  mov     rax, [rcx]
0x18005da90  mov     dword ptr [rsp+98h+ppPropStg], 1002h
0x18005da98  lea     r9, [rsp+98h+var_38]
0x18005da9d  lea     r8, [rsp+98h+var_48]
0x18005daa2  mov     edx, r12d
0x18005daa5  mov     rax, [rax+20h]
0x18005daa9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005daae  mov     edi, eax
0x18005dab0  test    eax, eax
0x18005dab2  jns     short loc_18005DB15
0x18005dab4  lea     rcx, aCwiapropstgSet_0; "CWiaPropStg::SetPropertyStream, Writing"...
0x18005dabb  call    WiaTrace_TraceLog
0x18005dac0  mov     rbx, rax
0x18005dac3  mov     rdx, rax; char *
0x18005dac6  lea     rcx, aCwiapropstgSet; "CWiaPropStg::SetPropertyStream"
0x18005dacd  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18005dad2  mov     rcx, rbx; this
0x18005dad5  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18005dada  lea     rcx, aCwiapropstgSet_0; "CWiaPropStg::SetPropertyStream, Writing"...
0x18005dae1  call    WiaTrace_Trace
0x18005dae6  mov     [rsp+98h+ppPropStg], rax; lpMem
0x18005daeb  mov     r9d, r12d; int
0x18005daee  lea     r8, aCwiapropstgSet; "CWiaPropStg::SetPropertyStream"
0x18005daf5  call    WiaTrace_ProcessTrace_Ex
0x18005dafa  mov     eax, edi
0x18005dafc  lea     r11, [rsp+98h+var_18]
0x18005db04  mov     rbx, [r11+28h]
0x18005db08  mov     rsi, [r11+30h]
0x18005db0c  mov     rsp, r11
0x18005db0f  pop     r14
0x18005db11  pop     r12
0x18005db13  pop     rdi
0x18005db14  retn
0x18005db15  test    rbx, rbx
0x18005db18  jnz     short loc_18005DB1E
0x18005db1a  xor     eax, eax
0x18005db1c  jmp     short loc_18005DAFC
0x18005db1e  xor     esi, esi
0x18005db20  mov     [rsp+98h+var_64], esi
0x18005db24  call    cs:__imp_CoImpersonateClient
0x18005db2a  mov     edi, eax
0x18005db2c  mov     [rsp+98h+var_68], eax
0x18005db30  test    eax, eax
0x18005db32  js      loc_18005DBFC
0x18005db38  mov     esi, r12d
0x18005db3b  mov     [rsp+98h+var_64], r12d
0x18005db40  lea     rax, [rsp+98h+var_60]
0x18005db45  mov     [rsp+98h+ppPropStg], rax; ppPropStg
0x18005db4a  xor     r9d, r9d; dwReserved
0x18005db4d  xor     r8d, r8d; grfFlags
0x18005db50  lea     rdx, GUID_NULL; fmtid
0x18005db57  mov     rcx, rbx; pUnk
0x18005db5a  call    cs:__imp_StgOpenPropStg
0x18005db60  mov     edi, eax
0x18005db62  mov     [rsp+98h+var_68], eax
0x18005db66  test    eax, eax
0x18005db68  js      short loc_18005DBA9
0x18005db6a  lea     rax, [rsp+98h+var_58]
0x18005db6f  mov     [rsp+98h+ppPropStg], rax; struct tagPROPVARIANT **
0x18005db74  lea     r9, [rsp+98h+hMem]; struct tagPROPSPEC **
0x18005db79  lea     r8, [rsp+98h+arg_0]; unsigned int *
0x18005db81  mov     rdx, [rsp+98h+var_60]; struct IPropertyStorage *
0x18005db86  call    ?GetPropsFromStorage@CWiaPropStg@@AEAAJPEAUIPropertyStorage@@PEAKPEAPEAUtagPROPSPEC@@PEAPEAUtagPROPVARIANT@@@Z; CWiaPropStg::GetPropsFromStorage(IPropertyStorage *,ulong *,tagPROPSPEC * *,tagPROPVARIANT * *)
0x18005db8b  mov     edi, eax
0x18005db8d  mov     [rsp+98h+var_68], eax
0x18005db91  mov     rcx, [rsp+98h+var_60]
0x18005db96  test    rcx, rcx
0x18005db99  jz      short loc_18005DBFC
0x18005db9b  mov     rax, [rcx]
0x18005db9e  mov     rax, [rax+10h]
0x18005dba2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005dba7  jmp     short loc_18005DBF3
0x18005dba9  mov     edx, edi
0x18005dbab  lea     rcx, aCwiapropstgSet_2; "CWiaPropStg::SetPropertyStream, open st"...
0x18005dbb2  call    WiaTrace_TraceLog
0x18005dbb7  mov     rbx, rax
0x18005dbba  mov     rdx, rax; char *
0x18005dbbd  lea     rcx, aCwiapropstgSet; "CWiaPropStg::SetPropertyStream"
0x18005dbc4  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18005dbc9  mov     rcx, rbx; this
0x18005dbcc  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18005dbd1  mov     edx, edi
0x18005dbd3  lea     rcx, aCwiapropstgSet_2; "CWiaPropStg::SetPropertyStream, open st"...
0x18005dbda  call    WiaTrace_Trace
0x18005dbdf  mov     [rsp+98h+ppPropStg], rax; lpMem
0x18005dbe4  mov     r9d, r12d; int
0x18005dbe7  lea     r8, aCwiapropstgSet; "CWiaPropStg::SetPropertyStream"
0x18005dbee  call    WiaTrace_ProcessTrace_Ex
0x18005dbf3  mov     [rsp+98h+var_60], 0
0x18005dbfc  test    esi, esi
0x18005dbfe  jz      short loc_18005DC57
0x18005dc00  call    ?SafeCoRevertToSelf@@YAJXZ; SafeCoRevertToSelf(void)
0x18005dc05  mov     esi, eax
0x18005dc07  test    eax, eax
0x18005dc09  jns     short loc_18005DC57
0x18005dc0b  mov     edx, eax
0x18005dc0d  lea     rcx, aSafecorevertto_1; "SafeCoRevertToSelf failed (0x%X)"
0x18005dc14  call    WiaTrace_TraceLog
0x18005dc19  mov     rbx, rax
0x18005dc1c  mov     rdx, rax; char *
0x18005dc1f  lea     rcx, aCwiapropstgSet; "CWiaPropStg::SetPropertyStream"
0x18005dc26  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18005dc2b  mov     rcx, rbx; this
0x18005dc2e  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18005dc33  mov     edx, esi
0x18005dc35  lea     rcx, aSafecorevertto_1; "SafeCoRevertToSelf failed (0x%X)"
0x18005dc3c  call    WiaTrace_Trace
0x18005dc41  mov     [rsp+98h+ppPropStg], rax; lpMem
0x18005dc46  mov     r9d, r12d; int
0x18005dc49  lea     r8, aCwiapropstgSet; "CWiaPropStg::SetPropertyStream"
0x18005dc50  call    WiaTrace_ProcessTrace_Ex
0x18005dc55  mov     edi, esi
0x18005dc57  test    edi, edi
0x18005dc59  js      short loc_18005DCD0
0x18005dc5b  lea     rcx, [r14+8]
0x18005dc5f  mov     rax, [rcx]
0x18005dc62  mov     dword ptr [rsp+98h+ppPropStg], 1002h
0x18005dc6a  mov     r9, [rsp+98h+var_58]
0x18005dc6f  mov     r8, [rsp+98h+hMem]
0x18005dc74  mov     edx, [rsp+98h+arg_0]
0x18005dc7b  mov     rax, [rax+20h]
0x18005dc7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005dc84  mov     edi, eax
0x18005dc86  test    eax, eax
0x18005dc88  jns     short loc_18005DCD0
0x18005dc8a  lea     rcx, aCwiapropstgSet_1; "CWiaPropStg::SetPropertyStream, WriteMu"...
0x18005dc91  call    WiaTrace_TraceLog
0x18005dc96  mov     rbx, rax
0x18005dc99  mov     rdx, rax; char *
0x18005dc9c  lea     rcx, aCwiapropstgSet; "CWiaPropStg::SetPropertyStream"
0x18005dca3  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18005dca8  mov     rcx, rbx; this
0x18005dcab  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18005dcb0  lea     rcx, aCwiapropstgSet_1; "CWiaPropStg::SetPropertyStream, WriteMu"...
0x18005dcb7  call    WiaTrace_Trace
0x18005dcbc  mov     [rsp+98h+ppPropStg], rax; lpMem
0x18005dcc1  mov     r9d, r12d; int
0x18005dcc4  lea     r8, aCwiapropstgSet; "CWiaPropStg::SetPropertyStream"
0x18005dccb  call    WiaTrace_ProcessTrace_Ex
0x18005dcd0  mov     rcx, [rsp+98h+hMem]; hMem
0x18005dcd5  test    rcx, rcx
0x18005dcd8  jz      short loc_18005DCE0
0x18005dcda  call    cs:__imp_LocalFree
0x18005dce0  cmp     [rsp+98h+var_58], 0
0x18005dce6  jz      loc_18005DAFA
0x18005dcec  xor     ebx, ebx
0x18005dcee  cmp     [rsp+98h+arg_0], ebx
0x18005dcf5  jbe     short loc_18005DD16
0x18005dcf7  lea     rcx, [rbx+rbx*2]
0x18005dcfb  mov     rax, [rsp+98h+var_58]
0x18005dd00  lea     rcx, [rax+rcx*8]; pvar
0x18005dd04  call    cs:__imp_PropVariantClear
0x18005dd0a  add     ebx, r12d
0x18005dd0d  cmp     ebx, [rsp+98h+arg_0]
0x18005dd14  jb      short loc_18005DCF7
0x18005dd16  mov     rcx, [rsp+98h+var_58]; hMem
0x18005dd1b  call    cs:__imp_LocalFree
0x18005dd21  jmp     loc_18005DAFA
0x1800778b2  push    rbx
0x1800778b4  push    rbp
0x1800778b5  push    rdi
0x1800778b6  sub     rsp, 30h
0x1800778ba  mov     rbp, rdx
0x1800778bd  cmp     dword ptr [rbp+34h], 0
0x1800778c1  jz      short loc_18007791E
0x1800778c3  call    ?SafeCoRevertToSelf@@YAJXZ; SafeCoRevertToSelf(void)
0x1800778c8  mov     edi, eax
0x1800778ca  test    eax, eax
0x1800778cc  jns     short loc_18007791E
0x1800778ce  mov     edx, eax
0x1800778d0  lea     rcx, aSafecorevertto_1; "SafeCoRevertToSelf failed (0x%X)"
0x1800778d7  call    WiaTrace_TraceLog
0x1800778dc  mov     rbx, rax
0x1800778df  mov     rdx, rax; char *
0x1800778e2  lea     rcx, aCwiapropstgSet; "CWiaPropStg::SetPropertyStream"
0x1800778e9  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x1800778ee  mov     rcx, rbx; this
0x1800778f1  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x1800778f6  mov     edx, edi
0x1800778f8  lea     rcx, aSafecorevertto_1; "SafeCoRevertToSelf failed (0x%X)"
0x1800778ff  call    WiaTrace_Trace
0x180077904  mov     [rsp+48h+lpMem], rax; lpMem
0x180077909  mov     r9d, 1; int
0x18007790f  lea     r8, aCwiapropstgSet; "CWiaPropStg::SetPropertyStream"
0x180077916  call    WiaTrace_ProcessTrace_Ex
0x18007791b  mov     [rbp+30h], edi
0x18007791e  add     rsp, 30h
0x180077922  pop     rdi
0x180077923  pop     rbp
0x180077924  pop     rbx
0x180077925  retn
```
