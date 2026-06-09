# CWiaDevMgrLH::CreateInstance(_GUID const &,void * *)

- ea: `0x18002cb40`
- end: `0x18002ce1a`
- name: `?CreateInstance@CWiaDevMgrLH@@SAJAEBU_GUID@@PEAPEAX@Z`
- size: `730`
- prototype: `__int64 __fastcall(const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x18003b854`

## callees

- `0x180004790`
- `0x18000c7c0`
- `0x18000cba0`
- `0x18000d770`
- `0x18000d7b0`
- `0x18000da10`
- `0x18000dd00`
- `0x18002c868`
- `0x18002c8b0`
- `0x18002cb40`
- `0x18002de18`
- `0x18002def8`
- `0x180033884`
- `0x180056d94`
- `0x180078010`

## string_xrefs

- `0x18002cc0b`: `CWiaDevMgrLH::CreateInstance, Unknown interface (0x%X)`
- `0x18002cc31`: `CWiaDevMgrLH::CreateInstance, Unknown interface (0x%X)`
- `0x18002cb52`: `CWiaDevMgrLH::CreateInstance`
- `0x18002cce6`: `CWiaDevMgrLH::CreateInstance, QI failed`
- `0x18002cd08`: `CWiaDevMgrLH::CreateInstance, QI failed`
- `0x18002cb7e`: `CWiaDevMgrLH::CreateInstance, Invalid pointer`
- `0x18002cba0`: `CWiaDevMgrLH::CreateInstance, Invalid pointer`
- `0x18002cdb6`: `CWiaDevMgrLH::CreateInstance, Out of Memory`
- `0x18002cdd8`: `CWiaDevMgrLH::CreateInstance, Out of Memory`
- `0x18002cd5f`: `CWiaDevMgrLH::CreateInstance, Initialize failed`
- `0x18002cd81`: `CWiaDevMgrLH::CreateInstance, Initialize failed`
- `0x18002cd11`: `CWiaDevMgrLH::CreateInstance, Created WiaDevMgr`
- `0x18002cd37`: `CWiaDevMgrLH::CreateInstance, Created WiaDevMgr`

## pseudocode

```c
__int64 __fastcall CWiaDevMgrLH::CreateInstance(const struct _GUID *a1, void **a2)
{
  char ***v4; // rax
  char *v5; // rdx
  __int64 v6; // r8
  char *v7; // rbx
  void *v8; // rdx
  void **v9; // rax
  void *v10; // rdx
  __int64 v11; // rcx
  int v12; // esi
  __int64 v13; // rax
  __int64 v14; // rax
  char *v15; // rbx
  void *v16; // rdx
  void **v17; // rax
  void *v18; // rdx
  __int64 v19; // rcx
  int v20; // r9d
  _DWORD *v21; // rdi
  char ***v22; // rax
  char *v23; // rdx
  __int64 v24; // r8
  CWiaDevMgrBase *v25; // rcx
  char *v26; // rbx
  void *v27; // rdx
  void **v28; // rax
  void *v29; // rdx
  __int64 v30; // rcx
  char *v31; // rbx
  void *v32; // rdx
  char *v33; // rbx
  void *v34; // rdx
  char *v35; // rbx
  void *v36; // rdx
  void **v37; // rax
  void *v38; // rdx
  __int64 v39; // rcx
  unsigned int lpMem; // [rsp+20h] [rbp-D8h]
  unsigned int lpMema; // [rsp+20h] [rbp-D8h]
  _BYTE v43[80]; // [rsp+30h] [rbp-C8h] BYREF
  _BYTE v44[120]; // [rsp+80h] [rbp-78h] BYREF

  v4 = (char ***)WiaTrace_Trace("CWiaDevMgrLH::CreateInstance");
  CWiaTraceFn::CWiaTraceFn((CWiaTraceFn *)v44, v5, v6, (char **)"CWiaDevMgrLH::CreateInstance", lpMem, v4);
  if ( a2 )
  {
    *a2 = 0;
    v13 = *(_QWORD *)&a1->Data1 - *(_QWORD *)&IID_IWiaDevMgr2.Data1;
    if ( *(_QWORD *)&a1->Data1 == *(_QWORD *)&IID_IWiaDevMgr2.Data1 )
      v13 = *(_QWORD *)a1->Data4 - *(_QWORD *)IID_IWiaDevMgr2.Data4;
    if ( v13 )
    {
      v14 = *(_QWORD *)&a1->Data1 - *(_QWORD *)&IID_IUnknown.Data1;
      if ( *(_QWORD *)&a1->Data1 == *(_QWORD *)&IID_IUnknown.Data1 )
        v14 = *(_QWORD *)a1->Data4 - *(_QWORD *)IID_IUnknown.Data4;
      if ( v14 )
      {
        v12 = -2147467262;
        v15 = (char *)WiaTrace_TraceLog("CWiaDevMgrLH::CreateInstance, Unknown interface (0x%X)");
        WriteDbgTraceErrorWI("CWiaDevMgrLH::CreateInstance", v15);
        WiaTrcLib::Free((WiaTrcLib *)v15, v16);
        v17 = (void **)WiaTrace_Trace("CWiaDevMgrLH::CreateInstance, Unknown interface (0x%X)", -2147467262);
        v20 = 1;
LABEL_15:
        WiaTrace_ProcessTrace_Ex(v19, v18, (void *)"CWiaDevMgrLH::CreateInstance", v20, v17);
        goto LABEL_19;
      }
    }
    v21 = operator new(0x20u);
    if ( !v21 )
    {
      v35 = (char *)WiaTrace_TraceLog("CWiaDevMgrLH::CreateInstance, Out of Memory");
      WriteDbgTraceErrorWI("CWiaDevMgrLH::CreateInstance", v35);
      WiaTrcLib::Free((WiaTrcLib *)v35, v36);
      v37 = (void **)WiaTrace_Trace("CWiaDevMgrLH::CreateInstance, Out of Memory");
      WiaTrace_ProcessTrace_Ex(v39, v38, (void *)"CWiaDevMgrLH::CreateInstance", 1, v37);
      v12 = -2147024882;
      goto LABEL_19;
    }
    v21[2] = 0;
    *(_QWORD *)v21 = &CWiaDevMgrBase::`vftable';
    *((_QWORD *)v21 + 2) = 0;
    IncClientCount();
    *(_QWORD *)v21 = &CWiaDevMgrLH::`vftable'{for `CWiaDevMgrBase'};
    *((_QWORD *)v21 + 3) = &CWiaDevMgrLH::`vftable'{for `IWiaDevMgr2'};
    v22 = (char ***)WiaTrace_Trace("CWiaDevMgrLH::CWiaDevMgrLH");
    CWiaTraceFn::CWiaTraceFn((CWiaTraceFn *)v43, v23, v24, (char **)"CWiaDevMgrLH::CWiaDevMgrLH", lpMema, v22);
    CWiaTraceFn::~CWiaTraceFn((CWiaTraceFn *)v43);
    v12 = CWiaDevMgrBase::Initialize(v25);
    if ( v12 < 0 )
    {
      v33 = (char *)WiaTrace_TraceLog("CWiaDevMgrLH::CreateInstance, Initialize failed");
      WriteDbgTraceErrorWI("CWiaDevMgrLH::CreateInstance", v33);
      WiaTrcLib::Free((WiaTrcLib *)v33, v34);
      v28 = (void **)WiaTrace_Trace("CWiaDevMgrLH::CreateInstance, Initialize failed");
    }
    else
    {
      v12 = (**(__int64 (__fastcall ***)(void *, const struct _GUID *, void **))v21)(v21, a1, a2);
      if ( v12 >= 0 )
      {
        v31 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(0, 0, "CWiaDevMgrLH::CreateInstance, Created WiaDevMgr");
        WriteDbgTraceInfoWI("CWiaDevMgrLH::CreateInstance", v31);
        WiaTrcLib::Free((WiaTrcLib *)v31, v32);
        v17 = (void **)WiaTrace_TraceWithSubCompTraceLevel(0, 0, "CWiaDevMgrLH::CreateInstance, Created WiaDevMgr");
        v20 = 4;
        goto LABEL_15;
      }
      v26 = (char *)WiaTrace_TraceLog("CWiaDevMgrLH::CreateInstance, QI failed");
      WriteDbgTraceErrorWI("CWiaDevMgrLH::CreateInstance", v26);
      WiaTrcLib::Free((WiaTrcLib *)v26, v27);
      v28 = (void **)WiaTrace_Trace("CWiaDevMgrLH::CreateInstance, QI failed");
    }
    WiaTrace_ProcessTrace_Ex(v30, v29, (void *)"CWiaDevMgrLH::CreateInstance", 1, v28);
    (*(void (__fastcall **)(_DWORD *, __int64))(*(_QWORD *)v21 + 24LL))(v21, 1);
    goto LABEL_19;
  }
  v7 = (char *)WiaTrace_TraceLog("CWiaDevMgrLH::CreateInstance, Invalid pointer");
  WriteDbgTraceErrorWI("CWiaDevMgrLH::CreateInstance", v7);
  WiaTrcLib::Free((WiaTrcLib *)v7, v8);
  v9 = (void **)WiaTrace_Trace("CWiaDevMgrLH::CreateInstance, Invalid pointer");
  WiaTrace_ProcessTrace_Ex(v11, v10, (void *)"CWiaDevMgrLH::CreateInstance", 1, v9);
  v12 = -2147467261;
LABEL_19:
  CWiaTraceFn::~CWiaTraceFn((CWiaTraceFn *)v44);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18002cb40  push    rbx
0x18002cb42  push    rsi
0x18002cb43  push    rdi
0x18002cb44  push    r14
0x18002cb46  push    r15
0x18002cb48  sub     rsp, 0D0h
0x18002cb4f  mov     rbx, rcx
0x18002cb52  lea     r15, aCwiadevmgrlhCr_2; "CWiaDevMgrLH::CreateInstance"
0x18002cb59  mov     rcx, r15
0x18002cb5c  mov     r14, rdx
0x18002cb5f  call    WiaTrace_Trace
0x18002cb64  mov     r9, r15; char *
0x18002cb67  mov     [rsp+0F8h+var_D0], rax; struct tagWiaTraceData_Type *
0x18002cb6c  lea     rcx, [rsp+0F8h+var_78]; this
0x18002cb74  call    ??0CWiaTraceFn@@QEAA@PEADK0KPEAUtagWiaTraceData_Type@@@Z; CWiaTraceFn::CWiaTraceFn(char *,ulong,char *,ulong,tagWiaTraceData_Type *)
0x18002cb79  test    r14, r14
0x18002cb7c  jnz     short loc_18002CBC7
0x18002cb7e  lea     rcx, aCwiadevmgrlhCr_9; "CWiaDevMgrLH::CreateInstance, Invalid p"...
0x18002cb85  call    WiaTrace_TraceLog
0x18002cb8a  mov     rdx, rax; char *
0x18002cb8d  mov     rcx, r15; char *
0x18002cb90  mov     rbx, rax
0x18002cb93  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18002cb98  mov     rcx, rbx; this
0x18002cb9b  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18002cba0  lea     rcx, aCwiadevmgrlhCr_9; "CWiaDevMgrLH::CreateInstance, Invalid p"...
0x18002cba7  call    WiaTrace_Trace
0x18002cbac  lea     r9d, [r14+1]; int
0x18002cbb0  mov     [rsp+0F8h+lpMem], rax; lpMem
0x18002cbb5  mov     r8, r15; int
0x18002cbb8  call    WiaTrace_ProcessTrace_Ex
0x18002cbbd  mov     esi, 80004003h
0x18002cbc2  jmp     loc_18002CDFC
0x18002cbc7  mov     qword ptr [r14], 0
0x18002cbce  mov     rax, [rbx]
0x18002cbd1  sub     rax, qword ptr cs:IID_IWiaDevMgr2.Data1
0x18002cbd8  jnz     short loc_18002CBE5
0x18002cbda  mov     rax, [rbx+8]
0x18002cbde  sub     rax, qword ptr cs:IID_IWiaDevMgr2.Data4
0x18002cbe5  test    rax, rax
0x18002cbe8  jz      short loc_18002CC48
0x18002cbea  mov     rax, [rbx]
0x18002cbed  sub     rax, qword ptr cs:IID_IUnknown.Data1
0x18002cbf4  jnz     short loc_18002CC01
0x18002cbf6  mov     rax, [rbx+8]
0x18002cbfa  sub     rax, qword ptr cs:IID_IUnknown.Data4
0x18002cc01  test    rax, rax
0x18002cc04  jz      short loc_18002CC48
0x18002cc06  mov     esi, 80004002h
0x18002cc0b  lea     rcx, aCwiadevmgrlhCr_0; "CWiaDevMgrLH::CreateInstance, Unknown i"...
0x18002cc12  mov     edx, esi
0x18002cc14  call    WiaTrace_TraceLog
0x18002cc19  mov     rdx, rax; char *
0x18002cc1c  mov     rcx, r15; char *
0x18002cc1f  mov     rbx, rax
0x18002cc22  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18002cc27  mov     rcx, rbx; this
0x18002cc2a  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18002cc2f  mov     edx, esi
0x18002cc31  lea     rcx, aCwiadevmgrlhCr_0; "CWiaDevMgrLH::CreateInstance, Unknown i"...
0x18002cc38  call    WiaTrace_Trace
0x18002cc3d  mov     r9d, 1
0x18002cc43  jmp     loc_18002CD4D
0x18002cc48  mov     ecx, 20h ; ' '; Size
0x18002cc4d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002cc52  mov     rdi, rax
0x18002cc55  test    rax, rax
0x18002cc58  jz      loc_18002CDB6
0x18002cc5e  lea     rax, ??_7CWiaDevMgrBase@@6B@; const CWiaDevMgrBase::`vftable'
0x18002cc65  mov     dword ptr [rdi+8], 0
0x18002cc6c  mov     [rdi], rax
0x18002cc6f  mov     qword ptr [rdi+10h], 0
0x18002cc77  call    ?IncClientCount@@YAKXZ; IncClientCount(void)
0x18002cc7c  lea     rax, ??_7CWiaDevMgrLH@@6BCWiaDevMgrBase@@@; const CWiaDevMgrLH::`vftable'{for `CWiaDevMgrBase'}
0x18002cc83  mov     [rdi], rax
0x18002cc86  lea     rcx, aCwiadevmgrlhCw_0; "CWiaDevMgrLH::CWiaDevMgrLH"
0x18002cc8d  lea     rax, ??_7CWiaDevMgrLH@@6BIWiaDevMgr2@@@; const CWiaDevMgrLH::`vftable'{for `IWiaDevMgr2'}
0x18002cc94  mov     [rdi+18h], rax
0x18002cc98  call    WiaTrace_Trace
0x18002cc9d  lea     r9, aCwiadevmgrlhCw_0; "CWiaDevMgrLH::CWiaDevMgrLH"
0x18002cca4  mov     [rsp+0F8h+var_D0], rax; struct tagWiaTraceData_Type *
0x18002cca9  lea     rcx, [rsp+0F8h+var_C8]; this
0x18002ccae  call    ??0CWiaTraceFn@@QEAA@PEADK0KPEAUtagWiaTraceData_Type@@@Z; CWiaTraceFn::CWiaTraceFn(char *,ulong,char *,ulong,tagWiaTraceData_Type *)
0x18002ccb3  lea     rcx, [rsp+0F8h+var_C8]; this
0x18002ccb8  call    ??1CWiaTraceFn@@QEAA@XZ; CWiaTraceFn::~CWiaTraceFn(void)
0x18002ccbd  call    ?Initialize@CWiaDevMgrBase@@IEAAJXZ; CWiaDevMgrBase::Initialize(void)
0x18002ccc2  mov     esi, eax
0x18002ccc4  test    eax, eax
0x18002ccc6  js      loc_18002CD5F
0x18002cccc  mov     rax, [rdi]
0x18002cccf  mov     r8, r14
0x18002ccd2  mov     rdx, rbx
0x18002ccd5  mov     rcx, rdi
0x18002ccd8  mov     rax, [rax]
0x18002ccdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cce0  mov     esi, eax
0x18002cce2  test    eax, eax
0x18002cce4  jns     short loc_18002CD11
0x18002cce6  lea     rcx, aCwiadevmgrlhCr_8; "CWiaDevMgrLH::CreateInstance, QI failed"
0x18002cced  call    WiaTrace_TraceLog
0x18002ccf2  mov     rdx, rax; char *
0x18002ccf5  mov     rcx, r15; char *
0x18002ccf8  mov     rbx, rax
0x18002ccfb  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18002cd00  mov     rcx, rbx; this
0x18002cd03  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18002cd08  lea     rcx, aCwiadevmgrlhCr_8; "CWiaDevMgrLH::CreateInstance, QI failed"
0x18002cd0f  jmp     short loc_18002CD88
0x18002cd11  lea     r8, aCwiadevmgrlhCr_5; "CWiaDevMgrLH::CreateInstance, Created W"...
0x18002cd18  xor     edx, edx
0x18002cd1a  xor     ecx, ecx
0x18002cd1c  call    WiaTrace_TraceLogWithSubCompTraceLevel
0x18002cd21  mov     rdx, rax; char *
0x18002cd24  mov     rcx, r15; char *
0x18002cd27  mov     rbx, rax
0x18002cd2a  call    ?WriteDbgTraceInfoWI@@YAXPEAD0ZZ; WriteDbgTraceInfoWI(char *,char *,...)
0x18002cd2f  mov     rcx, rbx; this
0x18002cd32  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18002cd37  lea     r8, aCwiadevmgrlhCr_5; "CWiaDevMgrLH::CreateInstance, Created W"...
0x18002cd3e  xor     edx, edx
0x18002cd40  xor     ecx, ecx
0x18002cd42  call    WiaTrace_TraceWithSubCompTraceLevel
0x18002cd47  mov     r9d, 4; int
0x18002cd4d  mov     r8, r15; int
0x18002cd50  mov     [rsp+0F8h+lpMem], rax; lpMem
0x18002cd55  call    WiaTrace_ProcessTrace_Ex
0x18002cd5a  jmp     loc_18002CDFC
0x18002cd5f  lea     rcx, aCwiadevmgrlhCr_10; "CWiaDevMgrLH::CreateInstance, Initializ"...
0x18002cd66  call    WiaTrace_TraceLog
0x18002cd6b  mov     rdx, rax; char *
0x18002cd6e  mov     rcx, r15; char *
0x18002cd71  mov     rbx, rax
0x18002cd74  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18002cd79  mov     rcx, rbx; this
0x18002cd7c  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18002cd81  lea     rcx, aCwiadevmgrlhCr_10; "CWiaDevMgrLH::CreateInstance, Initializ"...
0x18002cd88  call    WiaTrace_Trace
0x18002cd8d  mov     r9d, 1; int
0x18002cd93  mov     [rsp+0F8h+lpMem], rax; lpMem
0x18002cd98  mov     r8, r15; int
0x18002cd9b  call    WiaTrace_ProcessTrace_Ex
0x18002cda0  mov     rax, [rdi]
0x18002cda3  mov     edx, 1
0x18002cda8  mov     rcx, rdi
0x18002cdab  mov     rax, [rax+18h]
0x18002cdaf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cdb4  jmp     short loc_18002CDFC
0x18002cdb6  lea     rcx, aCwiadevmgrlhCr_4; "CWiaDevMgrLH::CreateInstance, Out of Me"...
0x18002cdbd  call    WiaTrace_TraceLog
0x18002cdc2  mov     rdx, rax; char *
0x18002cdc5  mov     rcx, r15; char *
0x18002cdc8  mov     rbx, rax
0x18002cdcb  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18002cdd0  mov     rcx, rbx; this
0x18002cdd3  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18002cdd8  lea     rcx, aCwiadevmgrlhCr_4; "CWiaDevMgrLH::CreateInstance, Out of Me"...
0x18002cddf  call    WiaTrace_Trace
0x18002cde4  mov     r9d, 1; int
0x18002cdea  mov     [rsp+0F8h+lpMem], rax; lpMem
0x18002cdef  mov     r8, r15; int
0x18002cdf2  call    WiaTrace_ProcessTrace_Ex
0x18002cdf7  mov     esi, 8007000Eh
0x18002cdfc  lea     rcx, [rsp+0F8h+var_78]; this
0x18002ce04  call    ??1CWiaTraceFn@@QEAA@XZ; CWiaTraceFn::~CWiaTraceFn(void)
0x18002ce09  mov     eax, esi
0x18002ce0b  add     rsp, 0D0h
0x18002ce12  pop     r15
0x18002ce14  pop     r14
0x18002ce16  pop     rdi
0x18002ce17  pop     rsi
0x18002ce18  pop     rbx
0x18002ce19  retn
```
