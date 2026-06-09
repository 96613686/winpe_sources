# CWiaDevMgr::CreateDevice(ushort *,IWiaItem * *)

- ea: `0x18005b560`
- end: `0x18005b6a8`
- name: `?CreateDevice@CWiaDevMgr@@EEAAJPEAGPEAPEAUIWiaItem@@@Z`
- size: `328`
- prototype: `__int64 __fastcall(CWiaDevMgr *this, unsigned __int16 *, struct IWiaItem **)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18000c7c0`
- `0x18000cba0`
- `0x18000d770`
- `0x18000da10`
- `0x18000dd00`
- `0x18002d6e4`
- `0x18002de18`
- `0x18002def8`
- `0x18005b560`
- `0x180078010`

## import_xrefs

- `OLEAUT32!__imp_SysStringLen` at `0x18005b5ad`
- `OLEAUT32!__imp_SysStringLen` at `0x18005b5ad`

## string_xrefs

- `0x18005b56d`: `CWiaDevMgr::CreateDevice`
- `0x18005b57f`: `CWiaDevMgr::CreateDevice`
- `0x18005b64c`: `CWiaDevMgr::CreateDevice`
- `0x18005b67a`: `CWiaDevMgr::CreateDevice`
- `0x18005b63d`: `CWiaDevMgr::CreateDevice, bad pointer passed`
- `0x18005b663`: `CWiaDevMgr::CreateDevice, bad pointer passed`

## pseudocode

```c
__int64 __fastcall CWiaDevMgr::CreateDevice(CWiaDevMgr *this, unsigned __int16 *a2, struct IWiaItem **a3)
{
  struct tagWiaTraceData_Type *v5; // rax
  char *v6; // rdx
  unsigned int v7; // r8d
  CWiaDevMgrBase *v8; // rcx
  int v9; // ebx
  char *v10; // rbx
  void *v11; // rdx
  void **v12; // rax
  void *v13; // rdx
  __int64 v14; // rcx
  unsigned int lpMem; // [rsp+20h] [rbp-78h]
  struct _GUID v17; // [rsp+30h] [rbp-68h] BYREF
  _BYTE v18[88]; // [rsp+40h] [rbp-58h] BYREF
  struct IUnknown *v19; // [rsp+A8h] [rbp+10h] BYREF

  v5 = (struct tagWiaTraceData_Type *)WiaTrace_Trace("CWiaDevMgr::CreateDevice");
  CWiaTraceFn::CWiaTraceFn((CWiaTraceFn *)v18, v6, v7, "CWiaDevMgr::CreateDevice", lpMem, v5);
  v19 = 0;
  if ( a2 && SysStringLen(a2) && a3 )
  {
    v17 = CLSID_WiaDevMgr;
    v9 = CWiaDevMgrBase::CreateWIADevice(v8, &v17, 0, a2, &v19, 1u);
    if ( v9 >= 0 )
    {
      v9 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, struct IWiaItem **))v19->lpVtbl->QueryInterface)(
             v19,
             &IID_IWiaItem,
             a3);
      ((void (__fastcall *)(struct IUnknown *))v19->lpVtbl->Release)(v19);
      v19 = 0;
    }
  }
  else
  {
    v10 = (char *)WiaTrace_TraceLog("CWiaDevMgr::CreateDevice, bad pointer passed");
    WriteDbgTraceErrorWI("CWiaDevMgr::CreateDevice", v10);
    WiaTrcLib::Free((WiaTrcLib *)v10, v11);
    v12 = (void **)WiaTrace_Trace("CWiaDevMgr::CreateDevice, bad pointer passed");
    WiaTrace_ProcessTrace_Ex(v14, v13, (void *)"CWiaDevMgr::CreateDevice", 1, v12);
    v9 = -2147467261;
  }
  CWiaTraceFn::~CWiaTraceFn((CWiaTraceFn *)v18);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18005b560  mov     [rsp+arg_0], rbx
0x18005b565  push    rdi
0x18005b566  sub     rsp, 90h
0x18005b56d  lea     rcx, aCwiadevmgrCrea_1; "CWiaDevMgr::CreateDevice"
0x18005b574  mov     rdi, r8
0x18005b577  mov     rbx, rdx
0x18005b57a  call    WiaTrace_Trace
0x18005b57f  lea     r9, aCwiadevmgrCrea_1; "CWiaDevMgr::CreateDevice"
0x18005b586  mov     [rsp+98h+var_70], rax; struct tagWiaTraceData_Type *
0x18005b58b  lea     rcx, [rsp+98h+var_58]; this
0x18005b590  call    ??0CWiaTraceFn@@QEAA@PEADK0KPEAUtagWiaTraceData_Type@@@Z; CWiaTraceFn::CWiaTraceFn(char *,ulong,char *,ulong,tagWiaTraceData_Type *)
0x18005b595  mov     [rsp+98h+arg_8], 0
0x18005b5a1  test    rbx, rbx
0x18005b5a4  jz      loc_18005B63D
0x18005b5aa  mov     rcx, rbx; pbstr
0x18005b5ad  call    cs:__imp_SysStringLen
0x18005b5b3  test    eax, eax
0x18005b5b5  jz      loc_18005B63D
0x18005b5bb  test    rdi, rdi
0x18005b5be  jz      short loc_18005B63D
0x18005b5c0  movups  xmm0, xmmword ptr cs:CLSID_WiaDevMgr.Data1
0x18005b5c7  lea     rax, [rsp+98h+arg_8]
0x18005b5cf  mov     dword ptr [rsp+98h+var_70], 1; unsigned int
0x18005b5d7  mov     r9, rbx; unsigned __int16 *
0x18005b5da  mov     [rsp+98h+lpMem], rax; struct IUnknown **
0x18005b5df  xor     r8d, r8d; int
0x18005b5e2  lea     rdx, [rsp+98h+var_68]; struct _GUID
0x18005b5e7  movdqu  xmmword ptr [rsp+98h+var_68.Data1], xmm0
0x18005b5ed  call    ?CreateWIADevice@CWiaDevMgrBase@@IEAAJU_GUID@@JPEAGPEAPEAUIUnknown@@K@Z; CWiaDevMgrBase::CreateWIADevice(_GUID,long,ushort *,IUnknown * *,ulong)
0x18005b5f2  mov     ebx, eax
0x18005b5f4  test    eax, eax
0x18005b5f6  js      loc_18005B68B
0x18005b5fc  mov     rcx, [rsp+98h+arg_8]
0x18005b604  lea     rdx, IID_IWiaItem
0x18005b60b  mov     r8, rdi
0x18005b60e  mov     rax, [rcx]
0x18005b611  mov     rax, [rax]
0x18005b614  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b619  mov     rcx, [rsp+98h+arg_8]
0x18005b621  mov     ebx, eax
0x18005b623  mov     rax, [rcx]
0x18005b626  mov     rax, [rax+10h]
0x18005b62a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b62f  mov     [rsp+98h+arg_8], 0
0x18005b63b  jmp     short loc_18005B68B
0x18005b63d  lea     rcx, aCwiadevmgrCrea; "CWiaDevMgr::CreateDevice, bad pointer p"...
0x18005b644  call    WiaTrace_TraceLog
0x18005b649  mov     rdx, rax; char *
0x18005b64c  lea     rcx, aCwiadevmgrCrea_1; "CWiaDevMgr::CreateDevice"
0x18005b653  mov     rbx, rax
0x18005b656  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18005b65b  mov     rcx, rbx; this
0x18005b65e  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18005b663  lea     rcx, aCwiadevmgrCrea; "CWiaDevMgr::CreateDevice, bad pointer p"...
0x18005b66a  call    WiaTrace_Trace
0x18005b66f  mov     r9d, 1; int
0x18005b675  mov     [rsp+98h+lpMem], rax; lpMem
0x18005b67a  lea     r8, aCwiadevmgrCrea_1; "CWiaDevMgr::CreateDevice"
0x18005b681  call    WiaTrace_ProcessTrace_Ex
0x18005b686  mov     ebx, 80004003h
0x18005b68b  lea     rcx, [rsp+98h+var_58]; this
0x18005b690  call    ??1CWiaTraceFn@@QEAA@XZ; CWiaTraceFn::~CWiaTraceFn(void)
0x18005b695  mov     eax, ebx
0x18005b697  mov     rbx, [rsp+98h+arg_0]
0x18005b69f  add     rsp, 90h
0x18005b6a6  pop     rdi
0x18005b6a7  retn
```
