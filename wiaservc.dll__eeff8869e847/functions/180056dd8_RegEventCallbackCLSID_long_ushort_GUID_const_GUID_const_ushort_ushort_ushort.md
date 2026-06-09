# RegEventCallbackCLSID(long,ushort *,_GUID const *,_GUID const *,ushort *,ushort *,ushort *)

- ea: `0x180056dd8`
- end: `0x1800570c9`
- name: `?RegEventCallbackCLSID@@YAJJPEAGPEBU_GUID@@1000@Z`
- size: `753`
- prototype: `__int64 __fastcall(int, unsigned __int16 *, const struct _GUID *, const struct _GUID *Buf1, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `13`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18005b060`
- `0x18005b760`

## callees

- `0x18000c7c0`
- `0x18000cba0`
- `0x18000d770`
- `0x18000d7b0`
- `0x18000da10`
- `0x18000dd00`
- `0x1800202b8`
- `0x18002c868`
- `0x18002c8b0`
- `0x18002de18`
- `0x18002def8`
- `0x1800315a0`
- `0x180056dd8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180056f77`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180056f77`

## string_xrefs

- `0x180056e74`: `RegEventCallbackCLSID, bad pClsID`
- `0x180056e96`: `RegEventCallbackCLSID, bad pClsID`
- `0x180056ded`: `RegEventCallbackCLSID`
- `0x180056e1c`: `RegEventCallbackCLSID, bad pEventGUID`
- `0x180056e3e`: `RegEventCallbackCLSID, bad pEventGUID`
- `0x180057066`: `RegEventCallbackCLSID, Invalid operation`
- `0x180057088`: `RegEventCallbackCLSID, Invalid operation`
- `0x180056f85`: `RegEventCallbackProgram, CoImpersonateClient failed (0x%X)`
- `0x180056fa7`: `RegEventCallbackProgram, CoImpersonateClient failed (0x%X)`

## pseudocode

```c
__int64 __fastcall RegEventCallbackCLSID(
        int a1,
        unsigned __int16 *a2,
        const struct _GUID *a3,
        const struct _GUID *Buf1,
        unsigned __int16 *a5,
        unsigned __int16 *a6,
        unsigned __int16 *a7)
{
  struct tagWiaTraceData_Type *v11; // rax
  char *v12; // rdx
  unsigned int v13; // r8d
  char *v14; // rbx
  void *v15; // rdx
  void *v16; // rax
  int v17; // edx
  int v18; // ecx
  char *v20; // rbx
  void *v21; // rdx
  void *v22; // rax
  int v23; // edx
  int v24; // ecx
  HRESULT v25; // edi
  char *v26; // rbx
  void *v27; // rdx
  void *v28; // rax
  int v29; // edx
  int v30; // ecx
  char *v31; // rbx
  void *v32; // rdx
  char *v33; // rbx
  void *v34; // rdx
  char *v35; // rbx
  void *v36; // rdx
  void *v37; // rax
  int v38; // edx
  int v39; // ecx
  HRESULT v40; // ebx
  char *v41; // rbx
  void *v42; // rdx
  char *v43; // rbx
  void *v44; // rdx
  void *v45; // rax
  int v46; // edx
  int v47; // ecx
  unsigned int lpMem; // [rsp+20h] [rbp-B8h]
  _BYTE v49[136]; // [rsp+50h] [rbp-88h] BYREF

  v11 = (struct tagWiaTraceData_Type *)WiaTrace_Trace("RegEventCallbackCLSID");
  CWiaTraceFn::CWiaTraceFn((CWiaTraceFn *)v49, v12, v13, "RegEventCallbackCLSID", lpMem, v11);
  if ( !a3 )
  {
    v14 = (char *)WiaTrace_TraceLog("RegEventCallbackCLSID, bad pEventGUID");
    WriteDbgTraceErrorWI("RegEventCallbackCLSID", v14);
    WiaTrcLib::Free((WiaTrcLib *)v14, v15);
    v16 = (void *)WiaTrace_Trace("RegEventCallbackCLSID, bad pEventGUID");
    WiaTrace_ProcessTrace_Ex(v18, v17, (int)"RegEventCallbackCLSID", 1, v16);
    CWiaTraceFn::~CWiaTraceFn((CWiaTraceFn *)v49);
    return 2147942487LL;
  }
  if ( !Buf1 )
  {
    v20 = (char *)WiaTrace_TraceLog("RegEventCallbackCLSID, bad pClsID");
    WriteDbgTraceErrorWI("RegEventCallbackCLSID", v20);
    WiaTrcLib::Free((WiaTrcLib *)v20, v21);
    v22 = (void *)WiaTrace_Trace("RegEventCallbackCLSID, bad pClsID");
    WiaTrace_ProcessTrace_Ex(v24, v23, (int)"RegEventCallbackCLSID", 1, v22);
    v25 = -2147024809;
    goto LABEL_14;
  }
  switch ( a1 )
  {
    case 1:
      v26 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(0, 0, "CWiaDevMgr::RegisterEventCallback");
      WriteDbgTraceInfoWI("RegEventCallbackCLSID", v26);
      WiaTrcLib::Free((WiaTrcLib *)v26, v27);
      v28 = (void *)WiaTrace_TraceWithSubCompTraceLevel(0, 0, "CWiaDevMgr::RegisterEventCallback");
LABEL_11:
      WiaTrace_ProcessTrace_Ex(v30, v29, (int)"RegEventCallbackCLSID", 4, v28);
      v25 = CoImpersonateClient();
      if ( v25 >= 0 )
      {
        v40 = CEventNotifier::RegisterEventCallback((CEventNotifier *)&g_eventNotifier, a1, a2, a3, Buf1, 0, a5, a6, a7);
        v25 = SafeCoRevertToSelf();
        if ( v25 >= 0 )
        {
          v25 = v40;
          goto LABEL_14;
        }
        v41 = (char *)WiaTrace_TraceLog("SafeCoRevertToSelf failed (0x%X)");
        WriteDbgTraceErrorWI("RegEventCallbackCLSID", v41);
        WiaTrcLib::Free((WiaTrcLib *)v41, v42);
        v37 = (void *)WiaTrace_Trace("SafeCoRevertToSelf failed (0x%X)", (unsigned int)v25);
      }
      else
      {
        v35 = (char *)WiaTrace_TraceLog("RegEventCallbackProgram, CoImpersonateClient failed (0x%X)");
        WriteDbgTraceErrorWI("RegEventCallbackCLSID", v35);
        WiaTrcLib::Free((WiaTrcLib *)v35, v36);
        v37 = (void *)WiaTrace_Trace("RegEventCallbackProgram, CoImpersonateClient failed (0x%X)", (unsigned int)v25);
      }
      WiaTrace_ProcessTrace_Ex(v39, v38, (int)"RegEventCallbackCLSID", 1, v37);
LABEL_14:
      CWiaTraceFn::~CWiaTraceFn((CWiaTraceFn *)v49);
      return (unsigned int)v25;
    case 2:
      v31 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(0, 0, "CWiaDevMgr::UnregisterEventCallback");
      WriteDbgTraceInfoWI("RegEventCallbackCLSID", v31);
      WiaTrcLib::Free((WiaTrcLib *)v31, v32);
      v28 = (void *)WiaTrace_TraceWithSubCompTraceLevel(0, 0, "CWiaDevMgr::UnregisterEventCallback");
      goto LABEL_11;
    case 4:
      v33 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(0, 0, "CWiaDevMgr::SetDefaultHandler");
      WriteDbgTraceInfoWI("RegEventCallbackCLSID", v33);
      WiaTrcLib::Free((WiaTrcLib *)v33, v34);
      v28 = (void *)WiaTrace_TraceWithSubCompTraceLevel(0, 0, "CWiaDevMgr::SetDefaultHandler");
      goto LABEL_11;
  }
  v43 = (char *)WiaTrace_TraceLog("RegEventCallbackCLSID, Invalid operation");
  WriteDbgTraceErrorWI("RegEventCallbackCLSID", v43);
  WiaTrcLib::Free((WiaTrcLib *)v43, v44);
  v45 = (void *)WiaTrace_Trace("RegEventCallbackCLSID, Invalid operation");
  WiaTrace_ProcessTrace_Ex(v47, v46, (int)"RegEventCallbackCLSID", 1, v45);
  CWiaTraceFn::~CWiaTraceFn((CWiaTraceFn *)v49);
  return 2147946717LL;
}

```

## disassembly

```asm
0x180056dd8  push    rbx
0x180056dda  push    rbp
0x180056ddb  push    rdi
0x180056ddc  push    r12
0x180056dde  push    r13
0x180056de0  push    r14
0x180056de2  push    r15
0x180056de4  sub     rsp, 0A0h
0x180056deb  mov     ebp, ecx
0x180056ded  lea     r13, aRegeventcallba_2; "RegEventCallbackCLSID"
0x180056df4  mov     rcx, r13
0x180056df7  mov     r14, r9
0x180056dfa  mov     r15, r8
0x180056dfd  mov     r12, rdx
0x180056e00  call    WiaTrace_Trace
0x180056e05  mov     r9, r13; char *
0x180056e08  mov     [rsp+0D8h+lpString], rax; struct tagWiaTraceData_Type *
0x180056e0d  lea     rcx, [rsp+0D8h+var_88]; this
0x180056e12  call    ??0CWiaTraceFn@@QEAA@PEADK0KPEAUtagWiaTraceData_Type@@@Z; CWiaTraceFn::CWiaTraceFn(char *,ulong,char *,ulong,tagWiaTraceData_Type *)
0x180056e17  test    r15, r15
0x180056e1a  jnz     short loc_180056E6F
0x180056e1c  lea     rcx, aRegeventcallba_0; "RegEventCallbackCLSID, bad pEventGUID"
0x180056e23  call    WiaTrace_TraceLog
0x180056e28  mov     rdx, rax; char *
0x180056e2b  mov     rcx, r13; char *
0x180056e2e  mov     rbx, rax
0x180056e31  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180056e36  mov     rcx, rbx; this
0x180056e39  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180056e3e  lea     rcx, aRegeventcallba_0; "RegEventCallbackCLSID, bad pEventGUID"
0x180056e45  call    WiaTrace_Trace
0x180056e4a  lea     r9d, [r15+1]; int
0x180056e4e  mov     [rsp+0D8h+lpMem], rax; lpMem
0x180056e53  mov     r8, r13; int
0x180056e56  call    WiaTrace_ProcessTrace_Ex
0x180056e5b  lea     rcx, [rsp+0D8h+var_88]; this
0x180056e60  call    ??1CWiaTraceFn@@QEAA@XZ; CWiaTraceFn::~CWiaTraceFn(void)
0x180056e65  mov     eax, 80070057h
0x180056e6a  jmp     loc_1800570B6
0x180056e6f  test    r14, r14
0x180056e72  jnz     short loc_180056EBD
0x180056e74  lea     rcx, aRegeventcallba_3; "RegEventCallbackCLSID, bad pClsID"
0x180056e7b  call    WiaTrace_TraceLog
0x180056e80  mov     rdx, rax; char *
0x180056e83  mov     rcx, r13; char *
0x180056e86  mov     rbx, rax
0x180056e89  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180056e8e  mov     rcx, rbx; this
0x180056e91  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180056e96  lea     rcx, aRegeventcallba_3; "RegEventCallbackCLSID, bad pClsID"
0x180056e9d  call    WiaTrace_Trace
0x180056ea2  lea     r9d, [r14+1]; int
0x180056ea6  mov     [rsp+0D8h+lpMem], rax; lpMem
0x180056eab  mov     r8, r13; int
0x180056eae  call    WiaTrace_ProcessTrace_Ex
0x180056eb3  mov     edi, 80070057h
0x180056eb8  jmp     loc_180056FC8
0x180056ebd  cmp     ebp, 1
0x180056ec0  jnz     short loc_180056EF1
0x180056ec2  lea     r8, aCwiadevmgrRegi_4; "CWiaDevMgr::RegisterEventCallback"
0x180056ec9  xor     edx, edx
0x180056ecb  xor     ecx, ecx
0x180056ecd  call    WiaTrace_TraceLogWithSubCompTraceLevel
0x180056ed2  mov     rdx, rax; char *
0x180056ed5  mov     rcx, r13; char *
0x180056ed8  mov     rbx, rax
0x180056edb  call    ?WriteDbgTraceInfoWI@@YAXPEAD0ZZ; WriteDbgTraceInfoWI(char *,char *,...)
0x180056ee0  mov     rcx, rbx; this
0x180056ee3  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180056ee8  lea     r8, aCwiadevmgrRegi_4; "CWiaDevMgr::RegisterEventCallback"
0x180056eef  jmp     short loc_180056F5B
0x180056ef1  cmp     ebp, 2
0x180056ef4  jnz     short loc_180056F25
0x180056ef6  lea     r8, aCwiadevmgrUnre; "CWiaDevMgr::UnregisterEventCallback"
0x180056efd  xor     edx, edx
0x180056eff  xor     ecx, ecx
0x180056f01  call    WiaTrace_TraceLogWithSubCompTraceLevel
0x180056f06  mov     rdx, rax; char *
0x180056f09  mov     rcx, r13; char *
0x180056f0c  mov     rbx, rax
0x180056f0f  call    ?WriteDbgTraceInfoWI@@YAXPEAD0ZZ; WriteDbgTraceInfoWI(char *,char *,...)
0x180056f14  mov     rcx, rbx; this
0x180056f17  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180056f1c  lea     r8, aCwiadevmgrUnre; "CWiaDevMgr::UnregisterEventCallback"
0x180056f23  jmp     short loc_180056F5B
0x180056f25  cmp     ebp, 4
0x180056f28  jnz     loc_180057066
0x180056f2e  lea     r8, aCwiadevmgrSetd; "CWiaDevMgr::SetDefaultHandler"
0x180056f35  xor     edx, edx
0x180056f37  xor     ecx, ecx
0x180056f39  call    WiaTrace_TraceLogWithSubCompTraceLevel
0x180056f3e  mov     rdx, rax; char *
0x180056f41  mov     rcx, r13; char *
0x180056f44  mov     rbx, rax
0x180056f47  call    ?WriteDbgTraceInfoWI@@YAXPEAD0ZZ; WriteDbgTraceInfoWI(char *,char *,...)
0x180056f4c  mov     rcx, rbx; this
0x180056f4f  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180056f54  lea     r8, aCwiadevmgrSetd; "CWiaDevMgr::SetDefaultHandler"
0x180056f5b  xor     edx, edx
0x180056f5d  xor     ecx, ecx
0x180056f5f  call    WiaTrace_TraceWithSubCompTraceLevel
0x180056f64  mov     r9d, 4; int
0x180056f6a  mov     [rsp+0D8h+lpMem], rax; lpMem
0x180056f6f  mov     r8, r13; int
0x180056f72  call    WiaTrace_ProcessTrace_Ex
0x180056f77  call    cs:__imp_CoImpersonateClient
0x180056f7d  mov     edi, eax
0x180056f7f  test    eax, eax
0x180056f81  jns     short loc_180056FD9
0x180056f83  mov     edx, eax
0x180056f85  lea     rcx, aRegeventcallba_5; "RegEventCallbackProgram, CoImpersonateC"...
0x180056f8c  call    WiaTrace_TraceLog
0x180056f91  mov     rdx, rax; char *
0x180056f94  mov     rcx, r13; char *
0x180056f97  mov     rbx, rax
0x180056f9a  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180056f9f  mov     rcx, rbx; this
0x180056fa2  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180056fa7  lea     rcx, aRegeventcallba_5; "RegEventCallbackProgram, CoImpersonateC"...
0x180056fae  mov     edx, edi
0x180056fb0  call    WiaTrace_Trace
0x180056fb5  mov     r9d, 1; int
0x180056fbb  mov     [rsp+0D8h+lpMem], rax; lpMem
0x180056fc0  mov     r8, r13; int
0x180056fc3  call    WiaTrace_ProcessTrace_Ex
0x180056fc8  lea     rcx, [rsp+0D8h+var_88]; this
0x180056fcd  call    ??1CWiaTraceFn@@QEAA@XZ; CWiaTraceFn::~CWiaTraceFn(void)
0x180056fd2  mov     eax, edi
0x180056fd4  jmp     loc_1800570B6
0x180056fd9  mov     rax, [rsp+0D8h+arg_30]
0x180056fe1  lea     rcx, ?g_eventNotifier@@3VCEventNotifier@@A; this
0x180056fe8  mov     [rsp+0D8h+var_98], rax; unsigned __int16 *
0x180056fed  mov     r9, r15; struct _GUID *
0x180056ff0  mov     rax, [rsp+0D8h+arg_28]
0x180056ff8  mov     r8, r12; unsigned __int16 *
0x180056ffb  mov     [rsp+0D8h+var_A0], rax; unsigned __int16 *
0x180057000  mov     edx, ebp; int
0x180057002  mov     rax, [rsp+0D8h+arg_20]
0x18005700a  mov     [rsp+0D8h+var_A8], rax; unsigned __int16 *
0x18005700f  mov     [rsp+0D8h+lpString], 0; lpString
0x180057018  mov     [rsp+0D8h+lpMem], r14; Buf1
0x18005701d  call    ?RegisterEventCallback@CEventNotifier@@QEAAJJPEAGPEBU_GUID@@1PEBG000@Z; CEventNotifier::RegisterEventCallback(long,ushort *,_GUID const *,_GUID const *,ushort const *,ushort *,ushort *,ushort *)
0x180057022  mov     ebx, eax
0x180057024  call    ?SafeCoRevertToSelf@@YAJXZ; SafeCoRevertToSelf(void)
0x180057029  mov     edi, eax
0x18005702b  test    eax, eax
0x18005702d  jns     short loc_18005705F
0x18005702f  mov     edx, eax
0x180057031  lea     rcx, aSafecorevertto_1; "SafeCoRevertToSelf failed (0x%X)"
0x180057038  call    WiaTrace_TraceLog
0x18005703d  mov     rdx, rax; char *
0x180057040  mov     rcx, r13; char *
0x180057043  mov     rbx, rax
0x180057046  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18005704b  mov     rcx, rbx; this
0x18005704e  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180057053  lea     rcx, aSafecorevertto_1; "SafeCoRevertToSelf failed (0x%X)"
0x18005705a  jmp     loc_180056FAE
0x18005705f  mov     edi, ebx
0x180057061  jmp     loc_180056FC8
0x180057066  lea     rcx, aRegeventcallba_1; "RegEventCallbackCLSID, Invalid operatio"...
0x18005706d  call    WiaTrace_TraceLog
0x180057072  mov     rdx, rax; char *
0x180057075  mov     rcx, r13; char *
0x180057078  mov     rbx, rax
0x18005707b  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180057080  mov     rcx, rbx; this
0x180057083  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180057088  lea     rcx, aRegeventcallba_1; "RegEventCallbackCLSID, Invalid operatio"...
0x18005708f  call    WiaTrace_Trace
0x180057094  mov     r9d, 1; int
0x18005709a  mov     [rsp+0D8h+lpMem], rax; lpMem
0x18005709f  mov     r8, r13; int
0x1800570a2  call    WiaTrace_ProcessTrace_Ex
0x1800570a7  lea     rcx, [rsp+0D8h+var_88]; this
0x1800570ac  call    ??1CWiaTraceFn@@QEAA@XZ; CWiaTraceFn::~CWiaTraceFn(void)
0x1800570b1  mov     eax, 800710DDh
0x1800570b6  add     rsp, 0A0h
0x1800570bd  pop     r15
0x1800570bf  pop     r14
0x1800570c1  pop     r13
0x1800570c3  pop     r12
0x1800570c5  pop     rdi
0x1800570c6  pop     rbp
0x1800570c7  pop     rbx
0x1800570c8  retn
```
