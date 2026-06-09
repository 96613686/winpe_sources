# DllGetClassObject

- ea: `0x1800036f0`
- end: `0x18000376c`
- name: `DllGetClassObject`
- size: `124`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800036f0`
- `0x18000386c`
- `0x18002d010`

## string_xrefs

- `0x180003712`: `Adapter_DllGetClassObject`

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
0x1800036f0  mov     rax, rsp
0x1800036f3  mov     [rax+8], rbx
0x1800036f7  mov     [rax+10h], rsi
0x1800036fb  push    rdi
0x1800036fc  sub     rsp, 40h
0x180003700  mov     rdi, rdx
0x180003703  mov     qword ptr [rax+20h], 0
0x18000370b  mov     rsi, rcx
0x18000370e  lea     rdx, [rax+20h]
0x180003712  lea     rcx, aAdapterDllgetc; "Adapter_DllGetClassObject"
0x180003719  mov     rbx, r8
0x18000371c  call    GetFunctionPointer
0x180003721  test    eax, eax
0x180003723  jnz     short loc_180003755
0x180003725  movups  xmm0, cs:g_providerClassID
0x18000372c  mov     rax, [rsp+48h+arg_18]
0x180003731  lea     rdx, MI_Main
0x180003738  mov     r9, rdi
0x18000373b  mov     [rsp+48h+var_28], rbx
0x180003740  mov     r8, rsi
0x180003743  lea     rcx, [rsp+48h+var_18]
0x180003748  movdqu  [rsp+48h+var_18], xmm0
0x18000374e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003753  jmp     short loc_18000375C
0x180003755  mov     qword ptr [rbx], 0
0x18000375c  mov     rbx, [rsp+48h+arg_0]
0x180003761  mov     rsi, [rsp+48h+arg_8]
0x180003766  add     rsp, 40h
0x18000376a  pop     rdi
0x18000376b  retn
```
