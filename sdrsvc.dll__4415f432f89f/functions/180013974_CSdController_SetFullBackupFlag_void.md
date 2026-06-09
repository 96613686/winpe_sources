# CSdController::_SetFullBackupFlag(void)

- ea: `0x180013974`
- end: `0x180013a36`
- name: `?_SetFullBackupFlag@CSdController@@AEAAJXZ`
- size: `194`
- prototype: `__int64 __fastcall(CSdController *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180012948`

## callees

- `0x180013974`
- `0x18001586c`
- `0x180015974`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800139c8`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800139c8`

## pseudocode

```c
__int64 __fastcall CSdController::_SetFullBackupFlag(CSdController *this)
{
  HRESULT v1; // ebx
  __int16 v2; // ax
  HRESULT v4; // [rsp+30h] [rbp-40h] BYREF
  __int16 v5; // [rsp+34h] [rbp-3Ch]
  __int16 v6; // [rsp+36h] [rbp-3Ah]
  LPVOID ppv; // [rsp+80h] [rbp+10h] BYREF

  ppv = this;
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v4, "CSdController::_SetFullBackupFlag", 1117, 1);
  ppv = 0;
  v1 = CoCreateInstance(&CLSID_SdBackupConfig, 0, 1u, &IID_ISdBackupConfig, &ppv);
  v4 = v1;
  v2 = 1125;
  if ( v1 < 0
    || (v5 = 1125, v1 = (*(__int64 (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 56LL))(ppv), v4 = v1, v2 = 1127, v1 < 0) )
  {
    v6 = v2;
  }
  else
  {
    v5 = 1127;
  }
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v4);
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x180013974  mov     [rsp-8+arg_8], rbx
0x180013979  mov     [rsp-8+arg_0], rcx
0x18001397e  push    rbp
0x18001397f  mov     rbp, rsp
0x180013982  sub     rsp, 70h
0x180013986  mov     ebx, 1
0x18001398b  lea     rdx, aCsdcontrollerS_4; "CSdController::_SetFullBackupFlag"
0x180013992  mov     r9d, ebx; unsigned __int16
0x180013995  lea     rcx, [rbp+var_40]; this
0x180013999  mov     r8d, 45Dh; unsigned __int16
0x18001399f  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x1800139a4  lea     rax, [rbp+arg_0]
0x1800139a8  mov     [rbp+arg_0], 0
0x1800139b0  lea     r9, IID_ISdBackupConfig; riid
0x1800139b7  mov     [rsp+70h+ppv], rax; ppv
0x1800139bc  mov     r8d, ebx; dwClsContext
0x1800139bf  lea     rcx, CLSID_SdBackupConfig; rclsid
0x1800139c6  xor     edx, edx; pUnkOuter
0x1800139c8  call    cs:__imp_CoCreateInstance
0x1800139ce  mov     ebx, eax
0x1800139d0  mov     [rbp+var_40], eax
0x1800139d3  test    eax, eax
0x1800139d5  mov     eax, 465h
0x1800139da  jns     short loc_1800139E2
0x1800139dc  mov     [rbp+var_3A], ax
0x1800139e0  jmp     short loc_180013A08
0x1800139e2  mov     rcx, [rbp+arg_0]
0x1800139e6  mov     [rbp+var_3C], ax
0x1800139ea  mov     rax, [rcx]
0x1800139ed  mov     rax, [rax+38h]
0x1800139f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800139f6  mov     ebx, eax
0x1800139f8  mov     [rbp+var_40], eax
0x1800139fb  test    eax, eax
0x1800139fd  mov     eax, 467h
0x180013a02  js      short loc_1800139DC
0x180013a04  mov     [rbp+var_3C], ax
0x180013a08  mov     rcx, [rbp+arg_0]
0x180013a0c  test    rcx, rcx
0x180013a0f  jz      short loc_180013A1D
0x180013a11  mov     rdx, [rcx]
0x180013a14  mov     rax, [rdx+10h]
0x180013a18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013a1d  lea     rcx, [rbp+var_40]; this
0x180013a21  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180013a26  mov     eax, ebx
0x180013a28  mov     rbx, [rsp+70h+arg_8]
0x180013a30  add     rsp, 70h
0x180013a34  pop     rbp
0x180013a35  retn
```
