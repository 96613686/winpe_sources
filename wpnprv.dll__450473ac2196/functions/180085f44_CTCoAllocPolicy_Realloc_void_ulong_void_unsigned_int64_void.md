# CTCoAllocPolicy::Realloc(void *,ulong,void *,unsigned __int64,void * *)

- ea: `0x180085f44`
- end: `0x180085fed`
- name: `?Realloc@CTCoAllocPolicy@@SAJPEAXK0_KPEAPEAX@Z`
- size: `169`
- prototype: `__int64 __fastcall(IMalloc *, __int64, void *, SIZE_T, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180085ff4`

## callees

- `0x180008294`
- `0x180085f44`
- `0x180096010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x180085f8a`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x180085f8a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180085f61`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180085f61`

## pseudocode

```c
__int64 __fastcall CTCoAllocPolicy::Realloc(IMalloc *a1, __int64 a2, void *a3, SIZE_T a4, void **a5)
{
  void *v6; // rax
  void **v7; // rsi
  void *v8; // rdi
  unsigned __int64 v9; // rdi
  LPMALLOC ppMalloc; // [rsp+30h] [rbp+8h] BYREF

  ppMalloc = a1;
  v6 = CoTaskMemRealloc(a3, a4);
  v7 = a5;
  v8 = v6;
  *a5 = v6;
  if ( !v6 )
    return 2147942414LL;
  ppMalloc = 0;
  if ( CoGetMalloc(1u, &ppMalloc) >= 0 )
  {
    v9 = ((__int64 (__fastcall *)(LPMALLOC, void *))ppMalloc->lpVtbl->GetSize)(ppMalloc, v8);
    ((void (__fastcall *)(LPMALLOC))ppMalloc->lpVtbl->Release)(ppMalloc);
    if ( v9 > a4 )
      memset_0((char *)*v7 + a4, 0, v9 - a4);
  }
  return 0;
}

```

## disassembly

```asm
0x180085f44  mov     [rsp+arg_8], rbx
0x180085f49  mov     [rsp+arg_10], rsi
0x180085f4e  mov     [rsp+ppMalloc], rcx
0x180085f53  push    rdi
0x180085f54  sub     rsp, 20h
0x180085f58  mov     rdx, r9; cb
0x180085f5b  mov     rcx, r8; pv
0x180085f5e  mov     rbx, r9
0x180085f61  call    cs:__imp_CoTaskMemRealloc
0x180085f67  mov     rsi, [rsp+28h+arg_20]
0x180085f6c  mov     rdi, rax
0x180085f6f  mov     [rsi], rax
0x180085f72  test    rax, rax
0x180085f75  jz      short loc_180085FD8
0x180085f77  lea     rdx, [rsp+28h+ppMalloc]; ppMalloc
0x180085f7c  mov     [rsp+28h+ppMalloc], 0
0x180085f85  mov     ecx, 1; dwMemContext
0x180085f8a  call    cs:__imp_CoGetMalloc
0x180085f90  test    eax, eax
0x180085f92  js      short loc_180085FD4
0x180085f94  mov     rcx, [rsp+28h+ppMalloc]
0x180085f99  mov     rdx, rdi
0x180085f9c  mov     rax, [rcx]
0x180085f9f  mov     rax, [rax+30h]
0x180085fa3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085fa8  mov     rcx, [rsp+28h+ppMalloc]
0x180085fad  mov     rdi, rax
0x180085fb0  mov     rdx, [rcx]
0x180085fb3  mov     rax, [rdx+10h]
0x180085fb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085fbc  cmp     rdi, rbx
0x180085fbf  jbe     short loc_180085FD4
0x180085fc1  mov     rcx, [rsi]
0x180085fc4  sub     rdi, rbx
0x180085fc7  add     rcx, rbx; void *
0x180085fca  mov     r8, rdi; Size
0x180085fcd  xor     edx, edx; Val
0x180085fcf  call    memset_0
0x180085fd4  xor     eax, eax
0x180085fd6  jmp     short loc_180085FDD
0x180085fd8  mov     eax, 8007000Eh
0x180085fdd  mov     rbx, [rsp+28h+arg_8]
0x180085fe2  mov     rsi, [rsp+28h+arg_10]
0x180085fe7  add     rsp, 20h
0x180085feb  pop     rdi
0x180085fec  retn
```
