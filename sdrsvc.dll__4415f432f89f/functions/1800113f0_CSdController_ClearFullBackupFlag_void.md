# CSdController::_ClearFullBackupFlag(void)

- ea: `0x1800113f0`
- end: `0x1800114b2`
- name: `?_ClearFullBackupFlag@CSdController@@AEAAJXZ`
- size: `194`
- prototype: `__int64 __fastcall(CSdController *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180012948`

## callees

- `0x1800113f0`
- `0x18001586c`
- `0x180015974`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180011444`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180011444`

## pseudocode

```c
__int64 __fastcall CSdController::_ClearFullBackupFlag(CSdController *this)
{
  HRESULT v1; // ebx
  __int16 v2; // ax
  HRESULT v4; // [rsp+30h] [rbp-40h] BYREF
  __int16 v5; // [rsp+34h] [rbp-3Ch]
  __int16 v6; // [rsp+36h] [rbp-3Ah]
  LPVOID ppv; // [rsp+80h] [rbp+10h] BYREF

  ppv = this;
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v4, "CSdController::_ClearFullBackupFlag", 1098, 1);
  ppv = 0;
  v1 = CoCreateInstance(&CLSID_SdBackupConfig, 0, 1u, &IID_ISdScheduleConfigPriv, &ppv);
  v4 = v1;
  v2 = 1106;
  if ( v1 < 0
    || (v5 = 1106, v1 = (*(__int64 (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 24LL))(ppv), v4 = v1, v2 = 1108, v1 < 0) )
  {
    v6 = v2;
  }
  else
  {
    v5 = 1108;
  }
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v4);
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x1800113f0  mov     [rsp-8+arg_8], rbx
0x1800113f5  mov     [rsp-8+arg_0], rcx
0x1800113fa  push    rbp
0x1800113fb  mov     rbp, rsp
0x1800113fe  sub     rsp, 70h
0x180011402  mov     ebx, 1
0x180011407  lea     rdx, aCsdcontrollerC_3; "CSdController::_ClearFullBackupFlag"
0x18001140e  mov     r9d, ebx; unsigned __int16
0x180011411  lea     rcx, [rbp+var_40]; this
0x180011415  mov     r8d, 44Ah; unsigned __int16
0x18001141b  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180011420  lea     rax, [rbp+arg_0]
0x180011424  mov     [rbp+arg_0], 0
0x18001142c  lea     r9, IID_ISdScheduleConfigPriv; riid
0x180011433  mov     [rsp+70h+ppv], rax; ppv
0x180011438  mov     r8d, ebx; dwClsContext
0x18001143b  lea     rcx, CLSID_SdBackupConfig; rclsid
0x180011442  xor     edx, edx; pUnkOuter
0x180011444  call    cs:__imp_CoCreateInstance
0x18001144a  mov     ebx, eax
0x18001144c  mov     [rbp+var_40], eax
0x18001144f  test    eax, eax
0x180011451  mov     eax, 452h
0x180011456  jns     short loc_18001145E
0x180011458  mov     [rbp+var_3A], ax
0x18001145c  jmp     short loc_180011484
0x18001145e  mov     rcx, [rbp+arg_0]
0x180011462  mov     [rbp+var_3C], ax
0x180011466  mov     rax, [rcx]
0x180011469  mov     rax, [rax+18h]
0x18001146d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011472  mov     ebx, eax
0x180011474  mov     [rbp+var_40], eax
0x180011477  test    eax, eax
0x180011479  mov     eax, 454h
0x18001147e  js      short loc_180011458
0x180011480  mov     [rbp+var_3C], ax
0x180011484  mov     rcx, [rbp+arg_0]
0x180011488  test    rcx, rcx
0x18001148b  jz      short loc_180011499
0x18001148d  mov     rdx, [rcx]
0x180011490  mov     rax, [rdx+10h]
0x180011494  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011499  lea     rcx, [rbp+var_40]; this
0x18001149d  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x1800114a2  mov     eax, ebx
0x1800114a4  mov     rbx, [rsp+70h+arg_8]
0x1800114ac  add     rsp, 70h
0x1800114b0  pop     rbp
0x1800114b1  retn
```
