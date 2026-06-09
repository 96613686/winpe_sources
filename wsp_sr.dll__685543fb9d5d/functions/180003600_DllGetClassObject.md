# DllGetClassObject

- ea: `0x180003600`
- end: `0x18000367d`
- name: `DllGetClassObject`
- size: `125`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180003600`
- `0x18000379c`
- `0x18002d010`

## string_xrefs

- `0x180003622`: `Adapter_DllGetClassObject`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  HRESULT result; // eax
  __int128 v7; // [rsp+30h] [rbp-18h] BYREF

  result = GetFunctionPointer("Adapter_DllGetClassObject");
  if ( result )
  {
    *ppv = 0;
  }
  else
  {
    v7 = g_providerClassID;
    return MEMORY[0](&v7, MI_Main, rclsid, riid, ppv);
  }
  return result;
}

```

## disassembly

```asm
0x180003600  mov     rax, rsp
0x180003603  mov     [rax+8], rbx
0x180003607  mov     [rax+10h], rsi
0x18000360b  push    rdi
0x18000360c  sub     rsp, 40h
0x180003610  mov     rdi, rdx
0x180003613  mov     qword ptr [rax+20h], 0
0x18000361b  mov     rsi, rcx
0x18000361e  lea     rdx, [rax+20h]
0x180003622  lea     rcx, aAdapterDllgetc; "Adapter_DllGetClassObject"
0x180003629  mov     rbx, r8
0x18000362c  call    GetFunctionPointer
0x180003631  test    eax, eax
0x180003633  jnz     short loc_180003665
0x180003635  movups  xmm0, cs:g_providerClassID
0x18000363c  mov     rax, [rsp+48h+arg_18]
0x180003641  lea     rdx, MI_Main
0x180003648  mov     r9, rdi
0x18000364b  mov     [rsp+48h+var_28], rbx
0x180003650  mov     r8, rsi
0x180003653  lea     rcx, [rsp+48h+var_18]
0x180003658  movdqu  [rsp+48h+var_18], xmm0
0x18000365e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003663  jmp     short loc_18000366C
0x180003665  mov     qword ptr [rbx], 0
0x18000366c  mov     rbx, [rsp+48h+arg_0]
0x180003671  mov     rsi, [rsp+48h+arg_8]
0x180003676  add     rsp, 40h
0x18000367a  pop     rdi
0x18000367b  retn
```
