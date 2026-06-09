# CTCoAllocPolicy::_CoTaskMemSize(void *)

- ea: `0x1800039e0`
- end: `0x180003a4c`
- name: `?_CoTaskMemSize@CTCoAllocPolicy@@CA_KPEAX@Z`
- size: `108`
- prototype: `unsigned __int64 __fastcall(void *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800020d0`
- `0x180002670`

## callees

- `0x1800039e0`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x1800039fe`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x1800039fe`

## pseudocode

```c
__int64 __fastcall CTCoAllocPolicy::_CoTaskMemSize(void *a1)
{
  __int64 v2; // rbx
  LPMALLOC ppMalloc; // [rsp+38h] [rbp+10h] BYREF

  ppMalloc = 0;
  if ( CoGetMalloc(1u, &ppMalloc) < 0 )
    return 0;
  v2 = ((__int64 (__fastcall *)(LPMALLOC, void *))ppMalloc->lpVtbl->GetSize)(ppMalloc, a1);
  ((void (__fastcall *)(LPMALLOC))ppMalloc->lpVtbl->Release)(ppMalloc);
  return v2;
}

```

## disassembly

```asm
0x1800039e0  mov     [rsp+arg_0], rbx
0x1800039e5  push    rdi
0x1800039e6  sub     rsp, 20h
0x1800039ea  mov     rbx, rcx
0x1800039ed  lea     rdx, [rsp+28h+ppMalloc]; ppMalloc
0x1800039f2  xor     edi, edi
0x1800039f4  mov     ecx, 1; dwMemContext
0x1800039f9  mov     [rsp+28h+ppMalloc], rdi
0x1800039fe  call    cs:__imp_CoGetMalloc
0x180003a04  test    eax, eax
0x180003a06  js      short loc_180003A3E
0x180003a08  mov     rcx, [rsp+28h+ppMalloc]
0x180003a0d  mov     rdx, rbx
0x180003a10  mov     rax, [rcx]
0x180003a13  mov     rax, [rax+30h]
0x180003a17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a1c  mov     rcx, [rsp+28h+ppMalloc]
0x180003a21  mov     rbx, rax
0x180003a24  mov     rdx, [rcx]
0x180003a27  mov     rax, [rdx+10h]
0x180003a2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a30  mov     rax, rbx
0x180003a33  mov     rbx, [rsp+28h+arg_0]
0x180003a38  add     rsp, 20h
0x180003a3c  pop     rdi
0x180003a3d  retn
0x180003a3e  mov     rbx, [rsp+28h+arg_0]
0x180003a43  mov     rax, rdi
0x180003a46  add     rsp, 20h
0x180003a4a  pop     rdi
0x180003a4b  retn
```
