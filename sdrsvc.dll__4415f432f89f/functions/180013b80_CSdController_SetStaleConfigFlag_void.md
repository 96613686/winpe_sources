# CSdController::_SetStaleConfigFlag(void)

- ea: `0x180013b80`
- end: `0x180013c42`
- name: `?_SetStaleConfigFlag@CSdController@@AEAAJXZ`
- size: `194`
- prototype: `__int64 __fastcall(CSdController *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180012948`

## callees

- `0x180013b80`
- `0x18001586c`
- `0x180015974`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180013bd4`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180013bd4`

## string_xrefs

- `0x180013b97`: `CSdController::_SetStaleConfigFlag`

## pseudocode

```c
__int64 __fastcall CSdController::_SetStaleConfigFlag(CSdController *this)
{
  HRESULT v1; // ebx
  __int16 v2; // ax
  HRESULT v4; // [rsp+30h] [rbp-40h] BYREF
  __int16 v5; // [rsp+34h] [rbp-3Ch]
  __int16 v6; // [rsp+36h] [rbp-3Ah]
  LPVOID ppv; // [rsp+80h] [rbp+10h] BYREF

  ppv = this;
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v4, "CSdController::_SetStaleConfigFlag", 1136, 1);
  ppv = 0;
  v1 = CoCreateInstance(&CLSID_SdBackupConfig, 0, 1u, &IID_ISdBackupConfig, &ppv);
  v4 = v1;
  v2 = 1144;
  if ( v1 < 0
    || (v5 = 1144, v1 = (*(__int64 (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 64LL))(ppv), v4 = v1, v2 = 1146, v1 < 0) )
  {
    v6 = v2;
  }
  else
  {
    v5 = 1146;
  }
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v4);
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x180013b80  mov     [rsp-8+arg_8], rbx
0x180013b85  mov     [rsp-8+arg_0], rcx
0x180013b8a  push    rbp
0x180013b8b  mov     rbp, rsp
0x180013b8e  sub     rsp, 70h
0x180013b92  mov     ebx, 1
0x180013b97  lea     rdx, aCsdcontrollerS; "CSdController::_SetStaleConfigFlag"
0x180013b9e  mov     r9d, ebx; unsigned __int16
0x180013ba1  lea     rcx, [rbp+var_40]; this
0x180013ba5  mov     r8d, 470h; unsigned __int16
0x180013bab  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180013bb0  lea     rax, [rbp+arg_0]
0x180013bb4  mov     [rbp+arg_0], 0
0x180013bbc  lea     r9, IID_ISdBackupConfig; riid
0x180013bc3  mov     [rsp+70h+ppv], rax; ppv
0x180013bc8  mov     r8d, ebx; dwClsContext
0x180013bcb  lea     rcx, CLSID_SdBackupConfig; rclsid
0x180013bd2  xor     edx, edx; pUnkOuter
0x180013bd4  call    cs:__imp_CoCreateInstance
0x180013bda  mov     ebx, eax
0x180013bdc  mov     [rbp+var_40], eax
0x180013bdf  test    eax, eax
0x180013be1  mov     eax, 478h
0x180013be6  jns     short loc_180013BEE
0x180013be8  mov     [rbp+var_3A], ax
0x180013bec  jmp     short loc_180013C14
0x180013bee  mov     rcx, [rbp+arg_0]
0x180013bf2  mov     [rbp+var_3C], ax
0x180013bf6  mov     rax, [rcx]
0x180013bf9  mov     rax, [rax+40h]
0x180013bfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013c02  mov     ebx, eax
0x180013c04  mov     [rbp+var_40], eax
0x180013c07  test    eax, eax
0x180013c09  mov     eax, 47Ah
0x180013c0e  js      short loc_180013BE8
0x180013c10  mov     [rbp+var_3C], ax
0x180013c14  mov     rcx, [rbp+arg_0]
0x180013c18  test    rcx, rcx
0x180013c1b  jz      short loc_180013C29
0x180013c1d  mov     rdx, [rcx]
0x180013c20  mov     rax, [rdx+10h]
0x180013c24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013c29  lea     rcx, [rbp+var_40]; this
0x180013c2d  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180013c32  mov     eax, ebx
0x180013c34  mov     rbx, [rsp+70h+arg_8]
0x180013c3c  add     rsp, 70h
0x180013c40  pop     rbp
0x180013c41  retn
```
