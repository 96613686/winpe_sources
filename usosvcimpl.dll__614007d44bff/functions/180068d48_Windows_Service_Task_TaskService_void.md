# Windows::Service::Task::TaskService(void)

- ea: `0x180068d48`
- end: `0x180068eeb`
- name: `?TaskService@Task@Service@Windows@@CA?AV?$com_ptr_t@UITaskService@@Uerr_exception_policy@wil@@@wil@@XZ`
- size: `419`
- prototype: `__int64 __fastcall(int)`
- caller_count: `5`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180069948`
- `0x18006a178`
- `0x18006ad4c`
- `0x18006b18c`
- `0x18006c480`

## callees

- `0x1800112d0`
- `0x180068d48`
- `0x1800e4630`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180068d8f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180068d8f`
- `OLEAUT32!__imp_VariantInit` at `0x180068daf`
- `OLEAUT32!__imp_VariantInit` at `0x180068dcd`
- `OLEAUT32!__imp_VariantInit` at `0x180068deb`
- `OLEAUT32!__imp_VariantInit` at `0x180068e08`
- `OLEAUT32!__imp_VariantInit` at `0x180068daf`
- `OLEAUT32!__imp_VariantInit` at `0x180068dcd`
- `OLEAUT32!__imp_VariantInit` at `0x180068deb`
- `OLEAUT32!__imp_VariantInit` at `0x180068e08`
- `OLEAUT32!__imp_VariantClear` at `0x180068e8b`
- `OLEAUT32!__imp_VariantClear` at `0x180068e96`
- `OLEAUT32!__imp_VariantClear` at `0x180068ea1`
- `OLEAUT32!__imp_VariantClear` at `0x180068eac`
- `OLEAUT32!__imp_VariantClear` at `0x180068e8b`
- `OLEAUT32!__imp_VariantClear` at `0x180068e96`
- `OLEAUT32!__imp_VariantClear` at `0x180068ea1`
- `OLEAUT32!__imp_VariantClear` at `0x180068eac`

## string_xrefs

- `0x180068ec4`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Scheduler.cpp`
- `0x180068ed9`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Scheduler.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
LPVOID *__fastcall Windows::Service::Task::TaskService(LPVOID *a1)
{
  HRESULT Instance; // eax
  LPVOID v3; // rdi
  __int64 (__fastcall *v4)(LPVOID, VARIANTARG *, __int128 *, __int128 *); // rbx
  int v5; // eax
  int ppv; // [rsp+20h] [rbp-E0h]
  int v8[4]; // [rsp+40h] [rbp-C0h] BYREF
  IRecordInfo *v9; // [rsp+50h] [rbp-B0h]
  __int128 v10; // [rsp+60h] [rbp-A0h] BYREF
  IRecordInfo *v11; // [rsp+70h] [rbp-90h]
  __int128 v12; // [rsp+80h] [rbp-80h] BYREF
  IRecordInfo *v13; // [rsp+90h] [rbp-70h]
  VARIANTARG v14; // [rsp+A0h] [rbp-60h] BYREF
  VARIANTARG v15; // [rsp+B8h] [rbp-48h] BYREF
  VARIANTARG v16; // [rsp+D0h] [rbp-30h] BYREF
  VARIANTARG pvarg; // [rsp+E8h] [rbp-18h] BYREF
  VARIANTARG v18; // [rsp+100h] [rbp+0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+48h]
  IRecordInfo *pRecInfo; // [rsp+158h] [rbp+58h]
  IRecordInfo *v21; // [rsp+160h] [rbp+60h]
  IRecordInfo *v22; // [rsp+168h] [rbp+68h]

  *a1 = 0;
  Instance = CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &IID_ITaskService, a1);
  if ( Instance < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xF,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Scheduler.cpp",
      (const char *)(unsigned int)Instance,
      ppv);
  v3 = *a1;
  v4 = *(__int64 (__fastcall **)(LPVOID, VARIANTARG *, __int128 *, __int128 *))(*(_QWORD *)*a1 + 80LL);
  VariantInit(&pvarg);
  *(_OWORD *)v8 = *(_OWORD *)&pvarg.vt;
  pRecInfo = pvarg.pRecInfo;
  VariantInit(&v16);
  v10 = *(_OWORD *)&v16.vt;
  v21 = v16.pRecInfo;
  VariantInit(&v15);
  v12 = *(_OWORD *)&v15.vt;
  v22 = v15.pRecInfo;
  VariantInit(&v14);
  v9 = pRecInfo;
  v11 = v21;
  v13 = v22;
  v18 = v14;
  v5 = v4(v3, &v18, &v12, &v10);
  if ( v5 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x15,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Scheduler.cpp",
      (const char *)(unsigned int)v5,
      (int)v8);
  VariantClear(&v14);
  VariantClear(&v15);
  VariantClear(&v16);
  VariantClear(&pvarg);
  return a1;
}

```

## disassembly

```asm
0x180068d48  mov     [rsp-8+arg_0], rcx
0x180068d4d  push    rbp
0x180068d4e  push    rbx
0x180068d4f  push    rsi
0x180068d50  push    rdi
0x180068d51  lea     rbp, [rsp-28h]
0x180068d56  sub     rsp, 128h
0x180068d5d  mov     rsi, rcx
0x180068d60  mov     [rsp+140h+var_110], 0
0x180068d68  mov     r8d, 1; dwClsContext
0x180068d6e  mov     [rsp+140h+var_110], r8d
0x180068d73  mov     qword ptr [rcx], 0
0x180068d7a  mov     qword ptr [rsp+140h+ppv], rcx; int
0x180068d7f  lea     r9, IID_ITaskService; riid
0x180068d86  xor     edx, edx; pUnkOuter
0x180068d88  lea     rcx, CLSID_TaskScheduler; rclsid
0x180068d8f  call    cs:__imp_CoCreateInstance
0x180068d95  mov     rcx, [rbp+48h]; this
0x180068d99  test    eax, eax
0x180068d9b  js      loc_180068ED6
0x180068da1  mov     rdi, [rsi]
0x180068da4  mov     rax, [rdi]
0x180068da7  mov     rbx, [rax+50h]
0x180068dab  lea     rcx, [rbp+40h+pvarg]; pvarg
0x180068daf  call    cs:__imp_VariantInit
0x180068db5  nop
0x180068db6  movups  xmm0, xmmword ptr [rbp+40h+pvarg]
0x180068dba  movups  xmmword ptr [rsp+140h+var_100], xmm0
0x180068dbf  movsd   xmm0, qword ptr [rbp+40h+pvarg+10h]
0x180068dc4  movsd   [rbp+40h+arg_8], xmm0
0x180068dc9  lea     rcx, [rbp+40h+var_70]; pvarg
0x180068dcd  call    cs:__imp_VariantInit
0x180068dd3  nop
0x180068dd4  movups  xmm0, xmmword ptr [rbp+40h+var_70]
0x180068dd8  movups  [rsp+140h+var_E0], xmm0
0x180068ddd  movsd   xmm0, qword ptr [rbp+40h+var_70+10h]
0x180068de2  movsd   [rbp+40h+arg_10], xmm0
0x180068de7  lea     rcx, [rbp+40h+var_88]; pvarg
0x180068deb  call    cs:__imp_VariantInit
0x180068df1  nop
0x180068df2  movups  xmm0, xmmword ptr [rbp+40h+var_88]
0x180068df6  movups  [rbp+40h+var_C0], xmm0
0x180068dfa  movsd   xmm0, qword ptr [rbp+40h+var_88+10h]
0x180068dff  movsd   [rbp+40h+arg_18], xmm0
0x180068e04  lea     rcx, [rbp+40h+var_A0]; pvarg
0x180068e08  call    cs:__imp_VariantInit
0x180068e0e  nop
0x180068e0f  movups  xmm0, xmmword ptr [rsp+140h+var_100]
0x180068e14  movaps  xmmword ptr [rsp+140h+var_100], xmm0
0x180068e19  movsd   xmm0, [rbp+40h+arg_8]
0x180068e1e  movsd   [rsp+140h+var_F0], xmm0
0x180068e24  movups  xmm0, [rsp+140h+var_E0]
0x180068e29  movaps  [rsp+140h+var_E0], xmm0
0x180068e2e  movsd   xmm0, [rbp+40h+arg_10]
0x180068e33  movsd   [rsp+140h+var_D0], xmm0
0x180068e39  movups  xmm0, [rbp+40h+var_C0]
0x180068e3d  movaps  [rbp+40h+var_C0], xmm0
0x180068e41  movsd   xmm0, [rbp+40h+arg_18]
0x180068e46  movsd   [rbp+40h+var_B0], xmm0
0x180068e4b  movups  xmm0, xmmword ptr [rbp+40h+var_A0]
0x180068e4f  movaps  [rbp+40h+var_40], xmm0
0x180068e53  movsd   xmm1, qword ptr [rbp+40h+var_A0+10h]
0x180068e58  movsd   [rbp+40h+var_30], xmm1
0x180068e5d  lea     rax, [rsp+140h+var_100]
0x180068e62  mov     qword ptr [rsp+140h+ppv], rax; int
0x180068e67  lea     r9, [rsp+140h+var_E0]
0x180068e6c  lea     r8, [rbp+40h+var_C0]
0x180068e70  lea     rdx, [rbp+40h+var_40]
0x180068e74  mov     rcx, rdi
0x180068e77  mov     rax, rbx
0x180068e7a  call    _guard_dispatch_icall
0x180068e7f  mov     rcx, [rbp+48h]; this
0x180068e83  test    eax, eax
0x180068e85  js      short loc_180068EC1
0x180068e87  lea     rcx, [rbp+40h+var_A0]; pvarg
0x180068e8b  call    cs:__imp_VariantClear
0x180068e91  nop
0x180068e92  lea     rcx, [rbp+40h+var_88]; pvarg
0x180068e96  call    cs:__imp_VariantClear
0x180068e9c  nop
0x180068e9d  lea     rcx, [rbp+40h+var_70]; pvarg
0x180068ea1  call    cs:__imp_VariantClear
0x180068ea7  nop
0x180068ea8  lea     rcx, [rbp+40h+pvarg]; pvarg
0x180068eac  call    cs:__imp_VariantClear
0x180068eb2  mov     rax, rsi
0x180068eb5  add     rsp, 128h
0x180068ebc  pop     rdi
0x180068ebd  pop     rsi
0x180068ebe  pop     rbx
0x180068ebf  pop     rbp
0x180068ec0  retn
0x180068ec1  mov     r9d, eax; char *
0x180068ec4  lea     r8, aCW1SSrcOrchest_38; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x180068ecb  mov     edx, 15h; void *
0x180068ed0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180068ed6  mov     r9d, eax; char *
0x180068ed9  lea     r8, aCW1SSrcOrchest_38; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x180068ee0  mov     edx, 0Fh; void *
0x180068ee5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
