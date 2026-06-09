# CVdsPack::MigrateGetTargetInfo(_GUID,IVdsPack * *,IVdsProvider * *,_VDS_PROVIDER_PROP *,IVdsMigrateDisks * *)

- ea: `0x140040808`
- end: `0x140040a2d`
- name: `?MigrateGetTargetInfo@CVdsPack@@QEAAJU_GUID@@PEAPEAUIVdsPack@@PEAPEAUIVdsProvider@@PEAU_VDS_PROVIDER_PROP@@PEAPEAUIVdsMigrateDisks@@@Z`
- size: `549`
- prototype: `__int64 __fastcall(CVdsPack *__hidden this, struct _GUID *, struct IVdsPack **, struct IVdsProvider **, struct _VDS_PROVIDER_PROP *, struct IVdsMigrateDisks **)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x140017250`

## callees

- `0x14000dd3c`
- `0x140012c48`
- `0x14002e123`
- `0x140040808`
- `0x140056010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400409d4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400409eb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400409d4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400409eb`
- `vdsutil!VdsTraceEx` at `0x14004090f`
- `vdsutil!VdsTraceEx` at `0x1400409c5`
- `vdsutil!VdsTraceEx` at `0x14004090f`
- `vdsutil!VdsTraceEx` at `0x1400409c5`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140040853`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140040853`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x1400409fd`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x1400409fd`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CVdsPack::MigrateGetTargetInfo(
        CVdsPack *this,
        struct _GUID *a2,
        struct IVdsPack **a3,
        struct IVdsProvider **a4,
        struct _VDS_PROVIDER_PROP *a5,
        struct IVdsMigrateDisks **a6)
{
  struct _VDS_PROVIDER_PROP *v9; // rdi
  const char *v10; // r8
  struct IUnknown *v11; // rsi
  int v12; // ebx
  int v13; // eax
  int v14; // eax
  int v15; // eax
  struct IVdsPack *v16; // rax
  struct IVdsProvider *v17; // rax
  LPWSTR pwszName; // rcx
  LPWSTR pwszVersion; // rcx
  struct IUnknown *v21; // [rsp+20h] [rbp-30h] BYREF
  struct _GUID v22; // [rsp+30h] [rbp-20h] BYREF
  _BYTE v23[16]; // [rsp+40h] [rbp-10h] BYREF
  struct IVdsProvider *v24; // [rsp+80h] [rbp+30h] BYREF
  struct IVdsPack *v25; // [rsp+90h] [rbp+40h] BYREF

  v21 = 0;
  v25 = 0;
  v24 = 0;
  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v23, 0x5Eu, "CVdsPack::MigrateGetTargetInfo()");
  v9 = a5;
  if ( !a3 || !a4 || !a5 || !a6 )
  {
    v10 = "CVdsPack::MigrateGetTargetInfo, 1";
    goto LABEL_19;
  }
  memset_0(a5, 0, sizeof(struct _VDS_PROVIDER_PROP));
  v22 = *a2;
  if ( (int)CVdsService::GetObjectFromProviders(&v22, VDS_OT_PACK, &v21) < 0 )
  {
    v10 = "CVdsPack::MigrateGetTargetInfo, 2";
LABEL_19:
    v12 = -2147024809;
    VdsTraceEx(94, 0, v10);
    goto LABEL_20;
  }
  v11 = v21;
  if ( !v21 )
  {
    v10 = "CVdsPack::MigrateGetTargetInfo, 2b";
    goto LABEL_19;
  }
  v12 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, struct IVdsPack **))v21->lpVtbl->QueryInterface)(
          v21,
          &IID_IVdsPack,
          &v25);
  ((void (__fastcall *)(struct IUnknown *))v11->lpVtbl->Release)(v11);
  if ( v12 >= 0 )
  {
    v13 = ((__int64 (__fastcall *)(struct IVdsPack *, struct IVdsProvider **))v25->lpVtbl->GetProvider)(v25, &v24);
    v12 = v13;
    if ( v13 >= 0 )
    {
      v14 = ((__int64 (__fastcall *)(struct IVdsProvider *, struct _VDS_PROVIDER_PROP *))v24->lpVtbl->GetProperties)(
              v24,
              v9);
      v12 = v14;
      if ( v14 >= 0 )
      {
        v15 = ((__int64 (__fastcall *)(struct IVdsPack *, GUID *, struct IVdsMigrateDisks **))v25->lpVtbl->QueryInterface)(
                v25,
                &IID_IVdsMigrateDisks,
                a6);
        v12 = v15;
        if ( v15 >= 0 )
        {
          v16 = v25;
          v25 = 0;
          *a3 = v16;
          v17 = v24;
          v24 = 0;
          *a4 = v17;
        }
        else
        {
          VdsTraceEx(94, 0, "CVdsPack::MigrateGetTargetInfo, 6, hr=%lX", (unsigned int)v15);
        }
      }
      else
      {
        VdsTraceEx(94, 0, "CVdsPack::MigrateGetTargetInfo, 5, hr=%lX", (unsigned int)v14);
      }
    }
    else
    {
      VdsTraceEx(94, 0, "CVdsPack::MigrateGetTargetInfo, 4, hr=%lX", (unsigned int)v13);
    }
  }
  else
  {
    VdsTraceEx(94, 0, "CVdsPack::MigrateGetTargetInfo, 3, hr=%lX", (unsigned int)v12);
  }
LABEL_20:
  pwszName = v9->pwszName;
  if ( pwszName )
  {
    CoTaskMemFree(pwszName);
    v9->pwszName = 0;
  }
  pwszVersion = v9->pwszVersion;
  if ( pwszVersion )
  {
    CoTaskMemFree(pwszVersion);
    v9->pwszVersion = 0;
  }
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v23);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v24);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v25);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x140040808  mov     [rsp-28h+arg_8], rbx
0x14004080d  mov     [rsp-28h+arg_0], rcx
0x140040812  push    rbp
0x140040813  push    rsi
0x140040814  push    rdi
0x140040815  push    r12
0x140040817  push    r14
0x140040819  mov     rbp, rsp
0x14004081c  sub     rsp, 50h
0x140040820  mov     r14, r9
0x140040823  mov     r12, r8
0x140040826  mov     rbx, rdx
0x140040829  mov     [rbp+var_30], 0
0x140040831  mov     [rbp+arg_10], 0
0x140040839  mov     [rbp+arg_0], 0
0x140040841  lea     r8, aCvdspackMigrat_29; "CVdsPack::MigrateGetTargetInfo()"
0x140040848  mov     esi, 5Eh ; '^'
0x14004084d  mov     edx, esi
0x14004084f  lea     rcx, [rbp+var_10]
0x140040853  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x140040859  nop
0x14004085a  mov     rdi, [rbp+arg_20]
0x14004085e  test    r12, r12
0x140040861  jz      loc_1400409B5
0x140040867  test    r14, r14
0x14004086a  jz      loc_1400409B5
0x140040870  test    rdi, rdi
0x140040873  jz      loc_1400409B5
0x140040879  cmp     [rbp+arg_28], 0
0x14004087e  jz      loc_1400409B5
0x140040884  xor     edx, edx; Val
0x140040886  lea     r8d, [rsi-1Eh]; Size
0x14004088a  mov     rcx, rdi; void *
0x14004088d  call    memset_0
0x140040892  movaps  xmm0, xmmword ptr [rbx]
0x140040895  movdqa  xmmword ptr [rbp+var_20.Data1], xmm0
0x14004089a  lea     r8, [rbp+var_30]; struct IUnknown **
0x14004089e  lea     edx, [rsi-54h]; enum _VDS_OBJECT_TYPE
0x1400408a1  lea     rcx, [rbp+var_20]; struct _GUID
0x1400408a5  call    ?GetObjectFromProviders@CVdsService@@SAJU_GUID@@W4_VDS_OBJECT_TYPE@@PEAPEAUIUnknown@@@Z; CVdsService::GetObjectFromProviders(_GUID,_VDS_OBJECT_TYPE,IUnknown * *)
0x1400408aa  test    eax, eax
0x1400408ac  jns     short loc_1400408BA
0x1400408ae  lea     r8, aCvdspackMigrat_5; "CVdsPack::MigrateGetTargetInfo, 2"
0x1400408b5  jmp     loc_1400409BC
0x1400408ba  mov     rsi, [rbp+var_30]
0x1400408be  test    rsi, rsi
0x1400408c1  jnz     short loc_1400408D2
0x1400408c3  lea     r8, aCvdspackMigrat_19; "CVdsPack::MigrateGetTargetInfo, 2b"
0x1400408ca  lea     ecx, [rsi+5Eh]
0x1400408cd  jmp     loc_1400409BE
0x1400408d2  mov     rax, [rsi]
0x1400408d5  lea     r8, [rbp+arg_10]
0x1400408d9  lea     rdx, IID_IVdsPack
0x1400408e0  mov     rcx, rsi
0x1400408e3  mov     rax, [rax]
0x1400408e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400408eb  mov     ebx, eax
0x1400408ed  mov     rdx, [rsi]
0x1400408f0  mov     rcx, rsi
0x1400408f3  mov     rax, [rdx+10h]
0x1400408f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400408fc  test    ebx, ebx
0x1400408fe  jns     short loc_14004091A
0x140040900  mov     r9d, ebx
0x140040903  lea     r8, aCvdspackMigrat_36; "CVdsPack::MigrateGetTargetInfo, 3, hr=%"...
0x14004090a  xor     edx, edx
0x14004090c  lea     ecx, [rdx+5Eh]
0x14004090f  call    cs:__imp_VdsTraceEx
0x140040915  jmp     loc_1400409CB
0x14004091a  mov     rcx, [rbp+arg_10]
0x14004091e  mov     rax, [rcx]
0x140040921  lea     rdx, [rbp+arg_0]
0x140040925  mov     rax, [rax+20h]
0x140040929  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004092e  mov     ebx, eax
0x140040930  test    eax, eax
0x140040932  jns     short loc_140040940
0x140040934  mov     r9d, eax
0x140040937  lea     r8, aCvdspackMigrat_37; "CVdsPack::MigrateGetTargetInfo, 4, hr=%"...
0x14004093e  jmp     short loc_14004090A
0x140040940  mov     rcx, [rbp+arg_0]
0x140040944  mov     rax, [rcx]
0x140040947  mov     rdx, rdi
0x14004094a  mov     rax, [rax+18h]
0x14004094e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140040953  mov     ebx, eax
0x140040955  test    eax, eax
0x140040957  jns     short loc_140040965
0x140040959  mov     r9d, eax
0x14004095c  lea     r8, aCvdspackMigrat_35; "CVdsPack::MigrateGetTargetInfo, 5, hr=%"...
0x140040963  jmp     short loc_14004090A
0x140040965  mov     rcx, [rbp+arg_10]
0x140040969  mov     rax, [rcx]
0x14004096c  mov     r8, [rbp+arg_28]
0x140040970  lea     rdx, IID_IVdsMigrateDisks
0x140040977  mov     rax, [rax]
0x14004097a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004097f  mov     ebx, eax
0x140040981  test    eax, eax
0x140040983  jns     short loc_140040994
0x140040985  mov     r9d, eax
0x140040988  lea     r8, aCvdspackMigrat_11; "CVdsPack::MigrateGetTargetInfo, 6, hr=%"...
0x14004098f  jmp     loc_14004090A
0x140040994  mov     rax, [rbp+arg_10]
0x140040998  mov     [rbp+arg_10], 0
0x1400409a0  mov     [r12], rax
0x1400409a4  mov     rax, [rbp+arg_0]
0x1400409a8  mov     [rbp+arg_0], 0
0x1400409b0  mov     [r14], rax
0x1400409b3  jmp     short loc_1400409CB
0x1400409b5  lea     r8, aCvdspackMigrat_31; "CVdsPack::MigrateGetTargetInfo, 1"
0x1400409bc  mov     ecx, esi
0x1400409be  mov     ebx, 80070057h
0x1400409c3  xor     edx, edx
0x1400409c5  call    cs:__imp_VdsTraceEx
0x1400409cb  mov     rcx, [rdi+10h]; pv
0x1400409cf  test    rcx, rcx
0x1400409d2  jz      short loc_1400409E2
0x1400409d4  call    cs:__imp_CoTaskMemFree
0x1400409da  mov     qword ptr [rdi+10h], 0
0x1400409e2  mov     rcx, [rdi+28h]; pv
0x1400409e6  test    rcx, rcx
0x1400409e9  jz      short loc_1400409F9
0x1400409eb  call    cs:__imp_CoTaskMemFree
0x1400409f1  mov     qword ptr [rdi+28h], 0
0x1400409f9  lea     rcx, [rbp+var_10]
0x1400409fd  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x140040a03  nop
0x140040a04  lea     rcx, [rbp+arg_0]
0x140040a08  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140040a0d  nop
0x140040a0e  lea     rcx, [rbp+arg_10]
0x140040a12  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140040a17  mov     eax, ebx
0x140040a19  mov     rbx, [rsp+50h+arg_8]
0x140040a21  add     rsp, 50h
0x140040a25  pop     r14
0x140040a27  pop     r12
0x140040a29  pop     rdi
0x140040a2a  pop     rsi
0x140040a2b  pop     rbp
0x140040a2c  retn
```
