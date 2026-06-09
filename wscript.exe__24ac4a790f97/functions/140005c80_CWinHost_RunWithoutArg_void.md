# CWinHost::RunWithoutArg(void)

- ea: `0x140005c80`
- end: `0x140005cd4`
- name: `?RunWithoutArg@CWinHost@@UEAAHXZ`
- size: `84`
- prototype: `__int64 __fastcall(CWinHost *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x140005c80`
- `0x140018010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x140005cab`
- `ole32!CoCreateInstance` at `0x140005cab`

## pseudocode

```c
HRESULT __fastcall CWinHost::RunWithoutArg(CWinHost *this)
{
  HRESULT result; // eax
  int v2; // eax
  int v3; // ecx
  LPVOID ppv; // [rsp+48h] [rbp+10h] BYREF

  ppv = 0;
  result = CoCreateInstance(&CLSID_WSHExtension, 0, 1u, &IID_IWSHExtension, &ppv);
  if ( result >= 0 )
  {
    v2 = (*(__int64 (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 32LL))(ppv);
    v3 = 0;
    if ( v2 < 0 )
      return v2;
    return v3;
  }
  return result;
}

```

## disassembly

```asm
0x140005c80  sub     rsp, 38h
0x140005c84  xor     edx, edx; pUnkOuter
0x140005c86  mov     [rsp+38h+arg_8], 0
0x140005c8f  lea     rax, [rsp+38h+arg_8]
0x140005c94  lea     r9, IID_IWSHExtension; riid
0x140005c9b  mov     [rsp+38h+ppv], rax; ppv
0x140005ca0  lea     rcx, CLSID_WSHExtension; rclsid
0x140005ca7  lea     r8d, [rdx+1]; dwClsContext
0x140005cab  call    cs:__imp_CoCreateInstance
0x140005cb1  test    eax, eax
0x140005cb3  js      short loc_140005CCF
0x140005cb5  mov     rcx, [rsp+38h+arg_8]
0x140005cba  mov     rax, [rcx]
0x140005cbd  mov     rax, [rax+20h]
0x140005cc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005cc6  xor     ecx, ecx
0x140005cc8  test    eax, eax
0x140005cca  cmovs   ecx, eax
0x140005ccd  mov     eax, ecx
0x140005ccf  add     rsp, 38h
0x140005cd3  retn
```
