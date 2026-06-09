# CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)

- ea: `0x180005d80`
- end: `0x180005e2a`
- name: `?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z`
- size: `170`
- prototype: `static int(void *, unsigned int, unsigned __int64, void **)`
- caller_count: `7`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180003e20`
- `0x180004fd0`
- `0x180005300`
- `0x1800059f0`
- `0x18000b89c`
- `0x18000f64c`
- `0x180015d30`

## callees

- `0x180005d80`
- `0x18000cb84`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x180005dc4`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x180005dc4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180005d9c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180005d9c`

## pseudocode

```c
__int64 __fastcall CTCoAllocPolicy::Alloc(IMalloc *a1, char a2, SIZE_T a3, void **a4)
{
  void *v6; // rax
  void *v7; // rbx
  size_t v8; // rdi
  LPMALLOC ppMalloc; // [rsp+30h] [rbp+8h] BYREF

  ppMalloc = a1;
  v6 = CoTaskMemAlloc(a3);
  *a4 = v6;
  v7 = v6;
  if ( !v6 )
    return 2147942414LL;
  if ( (a2 & 1) != 0 )
  {
    v8 = 0;
    ppMalloc = 0;
    if ( CoGetMalloc(1u, &ppMalloc) >= 0 )
    {
      v8 = ((__int64 (__fastcall *)(LPMALLOC, void *))ppMalloc->lpVtbl->GetSize)(ppMalloc, v7);
      ((void (__fastcall *)(LPMALLOC))ppMalloc->lpVtbl->Release)(ppMalloc);
    }
    memset_0(*a4, 0, v8);
  }
  return 0;
}

```

## disassembly

```asm
0x180005d80  mov     [rsp+arg_8], rbx
0x180005d85  mov     [rsp+arg_10], rsi
0x180005d8a  mov     [rsp+ppMalloc], rcx
0x180005d8f  push    rdi
0x180005d90  sub     rsp, 20h
0x180005d94  mov     rcx, r8; cb
0x180005d97  mov     rsi, r9
0x180005d9a  mov     edi, edx
0x180005d9c  call    cs:__imp_CoTaskMemAlloc
0x180005da2  mov     [rsi], rax
0x180005da5  mov     rbx, rax
0x180005da8  test    rax, rax
0x180005dab  jz      short loc_180005E15
0x180005dad  test    dil, 1
0x180005db1  jz      short loc_180005E03
0x180005db3  xor     edi, edi
0x180005db5  lea     rdx, [rsp+28h+ppMalloc]; ppMalloc
0x180005dba  mov     ecx, 1; dwMemContext
0x180005dbf  mov     [rsp+28h+ppMalloc], rdi
0x180005dc4  call    cs:__imp_CoGetMalloc
0x180005dca  test    eax, eax
0x180005dcc  js      short loc_180005DF6
0x180005dce  mov     rcx, [rsp+28h+ppMalloc]
0x180005dd3  mov     rdx, rbx
0x180005dd6  mov     rax, [rcx]
0x180005dd9  mov     rax, [rax+30h]
0x180005ddd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005de2  mov     rcx, [rsp+28h+ppMalloc]
0x180005de7  mov     rdi, rax
0x180005dea  mov     rdx, [rcx]
0x180005ded  mov     rax, [rdx+10h]
0x180005df1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005df6  mov     rcx, [rsi]; void *
0x180005df9  mov     r8, rdi; Size
0x180005dfc  xor     edx, edx; Val
0x180005dfe  call    memset_0
0x180005e03  xor     eax, eax
0x180005e05  mov     rbx, [rsp+28h+arg_8]
0x180005e0a  mov     rsi, [rsp+28h+arg_10]
0x180005e0f  add     rsp, 20h
0x180005e13  pop     rdi
0x180005e14  retn
0x180005e15  mov     rbx, [rsp+28h+arg_8]
0x180005e1a  mov     eax, 8007000Eh
0x180005e1f  mov     rsi, [rsp+28h+arg_10]
0x180005e24  add     rsp, 20h
0x180005e28  pop     rdi
0x180005e29  retn
```
