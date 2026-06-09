# CVssFunctionTracer::ComDisableSEH(CVssDebugInfo)

- ea: `0x180034cfc`
- end: `0x180034e5c`
- name: `?ComDisableSEH@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@@Z`
- size: `352`
- prototype: `void __fastcall(__int64, struct CVssDebugInfo *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000aa5c`

## callees

- `0x1800036c4`
- `0x1800339c0`
- `0x180033c2c`
- `0x180033e60`
- `0x180034038`
- `0x1800340e4`
- `0x180034cfc`
- `0x1800358f4`
- `0x18003649c`
- `0x180037080`
- `0x18004b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180034d44`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180034d44`

## string_xrefs

- `0x180034d77`: `CLSID_GlobalOptions`
- `0x180034dde`: `CoCreateInstance(CLSID_GlobalOptions) failed [0x%08lx]`
- `0x180034e46`: `pIGLB->Set(COMGLB_EXCEPTION_HANDLING, COMGLB_EXCEPTION_DONOT_HANDLE)`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CVssFunctionTracer::ComDisableSEH(__int64 a1, struct CVssDebugInfo *a2)
{
  HRESULT v4; // eax
  struct CVssDebugInfo *v5; // rax
  struct CVssDebugInfo *v6; // rax
  CVssDebugInfo *v7; // rax
  CVssDebugInfo *v8; // rax
  unsigned int v9; // r10d
  int v10; // eax
  CVssDebugInfo *v11; // rax
  unsigned int v12; // r10d
  LPVOID *ppv; // [rsp+20h] [rbp-E0h]
  _BYTE v14[168]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v15[168]; // [rsp+E8h] [rbp-18h] BYREF
  _BYTE v16[192]; // [rsp+190h] [rbp+90h] BYREF
  LPVOID v17; // [rsp+260h] [rbp+160h] BYREF
  struct CVssDebugInfo *v18; // [rsp+268h] [rbp+168h]

  v18 = a2;
  v17 = 0;
  v4 = CoCreateInstance(&CLSID_GlobalOptions, 0, 1u, &GUID_0000015b_0000_0000_c000_000000000046, &v17);
  *(_DWORD *)(a1 + 8) = v4;
  if ( v4 < 0 )
  {
    v5 = (struct CVssDebugInfo *)CVssDebugInfo::operator<<(a2, (CVssDebugInfo *)v14);
    v6 = CVssDebugInfo::operator<<(v5, (CVssDebugInfo *)v16, L"CLSID_GlobalOptions");
    v7 = CVssDebugInfo::operator<<(v6, (CVssDebugInfo *)v15, *(_DWORD *)(a1 + 8));
    CVssFunctionTracer::LogError(a1, 13, v7);
    CVssDebugInfo::~CVssDebugInfo((CVssDebugInfo *)v16);
    CVssDebugInfo::~CVssDebugInfo((CVssDebugInfo *)v14);
    v8 = CVssDebugInfo::CVssDebugInfo((CVssDebugInfo *)v14, a2);
    LODWORD(ppv) = v9;
    CVssFunctionTracer::Throw(a1, v8, v9, L"CoCreateInstance(CLSID_GlobalOptions) failed [0x%08lx]", ppv);
  }
  v10 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64))(*(_QWORD *)v17 + 24LL))(v17, 1, 1);
  *(_DWORD *)(a1 + 8) = v10;
  if ( v10 < 0 )
  {
    v11 = CVssDebugInfo::CVssDebugInfo((CVssDebugInfo *)v14, a2);
    CVssFunctionTracer::TranslateGenericError(
      a1,
      v11,
      v12,
      L"pIGLB->Set(COMGLB_EXCEPTION_HANDLING, COMGLB_EXCEPTION_DONOT_HANDLE)");
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v17);
  CVssDebugInfo::~CVssDebugInfo(a2);
}

```

## disassembly

```asm
0x180034cfc  mov     [rsp-8+arg_8], rdx
0x180034d01  push    rbp
0x180034d02  push    rbx
0x180034d03  push    rdi
0x180034d04  lea     rbp, [rsp-140h]
0x180034d0c  sub     rsp, 240h
0x180034d13  mov     rbx, rdx
0x180034d16  mov     rdi, rcx
0x180034d19  mov     [rbp+150h+arg_0], 0
0x180034d24  lea     rax, [rbp+150h+arg_0]
0x180034d2b  mov     [rsp+250h+ppv], rax; ppv
0x180034d30  lea     r9, _GUID_0000015b_0000_0000_c000_000000000046; riid
0x180034d37  xor     edx, edx; pUnkOuter
0x180034d39  lea     r8d, [rdx+1]; dwClsContext
0x180034d3d  lea     rcx, CLSID_GlobalOptions; rclsid
0x180034d44  call    cs:__imp_CoCreateInstance
0x180034d4a  mov     [rdi+8], eax
0x180034d4d  shr     eax, 1Fh
0x180034d50  test    al, al
0x180034d52  jz      loc_180034DF4
0x180034d58  movups  xmm0, xmmword ptr cs:CLSID_GlobalOptions.Data1
0x180034d5f  movdqu  [rsp+250h+var_220], xmm0
0x180034d65  lea     r8, [rsp+250h+var_220]
0x180034d6a  lea     rdx, [rsp+250h+var_210]; this
0x180034d6f  mov     rcx, rbx; struct CVssDebugInfo *
0x180034d72  call    ??6CVssDebugInfo@@QEAA?AU0@U_GUID@@@Z; CVssDebugInfo::operator<<(_GUID)
0x180034d77  lea     r8, aClsidGlobalopt; "CLSID_GlobalOptions"
0x180034d7e  lea     rdx, [rbp+150h+var_C0]; this
0x180034d85  mov     rcx, rax; struct CVssDebugInfo *
0x180034d88  call    ??6CVssDebugInfo@@QEAA?AU0@PEBG@Z; CVssDebugInfo::operator<<(ushort const *)
0x180034d8d  mov     r8d, [rdi+8]; dwMessageId
0x180034d91  lea     rdx, [rbp+150h+var_168]; this
0x180034d95  mov     rcx, rax; struct CVssDebugInfo *
0x180034d98  call    ??6CVssDebugInfo@@QEAA?AU0@J@Z; CVssDebugInfo::operator<<(long)
0x180034d9d  mov     r9d, 1
0x180034da3  mov     r8, rax
0x180034da6  lea     edx, [r9+0Ch]
0x180034daa  mov     rcx, rdi
0x180034dad  call    ?LogError@CVssFunctionTracer@@QEAAXKUCVssDebugInfo@@G@Z; CVssFunctionTracer::LogError(ulong,CVssDebugInfo,ushort)
0x180034db2  lea     rcx, [rbp+150h+var_C0]; this
0x180034db9  call    ??1CVssDebugInfo@@QEAA@XZ; CVssDebugInfo::~CVssDebugInfo(void)
0x180034dbe  lea     rcx, [rsp+250h+var_210]; this
0x180034dc3  call    ??1CVssDebugInfo@@QEAA@XZ; CVssDebugInfo::~CVssDebugInfo(void)
0x180034dc8  mov     r10d, [rdi+8]
0x180034dcc  mov     rdx, rbx; struct CVssDebugInfo *
0x180034dcf  lea     rcx, [rsp+250h+var_210]; this
0x180034dd4  call    ??0CVssDebugInfo@@QEAA@AEBU0@@Z; CVssDebugInfo::CVssDebugInfo(CVssDebugInfo const &)
0x180034dd9  mov     dword ptr [rsp+250h+ppv], r10d
0x180034dde  lea     r9, aCocreateinstan_1; "CoCreateInstance(CLSID_GlobalOptions) f"...
0x180034de5  mov     r8d, r10d
0x180034de8  mov     rdx, rax
0x180034deb  mov     rcx, rdi
0x180034dee  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
0x180034df4  mov     rcx, [rbp+150h+arg_0]
0x180034dfb  mov     rax, [rcx]
0x180034dfe  mov     edx, 1
0x180034e03  mov     r8d, edx
0x180034e06  mov     rax, [rax+18h]
0x180034e0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034e0f  mov     r10d, eax
0x180034e12  mov     [rdi+8], eax
0x180034e15  test    eax, eax
0x180034e17  js      short loc_180034E39
0x180034e19  lea     rcx, [rbp+150h+arg_0]
0x180034e20  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180034e25  nop
0x180034e26  mov     rcx, rbx; this
0x180034e29  call    ??1CVssDebugInfo@@QEAA@XZ; CVssDebugInfo::~CVssDebugInfo(void)
0x180034e2e  add     rsp, 240h
0x180034e35  pop     rdi
0x180034e36  pop     rbx
0x180034e37  pop     rbp
0x180034e38  retn
0x180034e39  mov     rdx, rbx; struct CVssDebugInfo *
0x180034e3c  lea     rcx, [rsp+250h+var_210]; this
0x180034e41  call    ??0CVssDebugInfo@@QEAA@AEBU0@@Z; CVssDebugInfo::CVssDebugInfo(CVssDebugInfo const &)
0x180034e46  lea     r9, aPiglbSetComglb; "pIGLB->Set(COMGLB_EXCEPTION_HANDLING, C"...
0x180034e4d  mov     r8d, r10d
0x180034e50  mov     rdx, rax
0x180034e53  mov     rcx, rdi
0x180034e56  call    ?TranslateGenericError@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JPEBGZZ; CVssFunctionTracer::TranslateGenericError(CVssDebugInfo,long,ushort const *,...)
```
