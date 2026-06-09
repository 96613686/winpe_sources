# CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)

- ea: `0x180026660`
- end: `0x1800266f2`
- name: `?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z`
- size: `146`
- prototype: `static int(void *, unsigned int, unsigned __int64, void **)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800285b4`
- `0x180051db8`

## callees

- `0x180003c88`
- `0x180026660`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x18002669a`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x18002669a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002667a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002667a`

## pseudocode

```c
__int64 __fastcall CTCoAllocPolicy::Alloc(IMalloc *a1, __int64 a2, SIZE_T a3, void **a4)
{
  void *v5; // rax
  void *v6; // rbx
  size_t v7; // rsi
  LPMALLOC ppMalloc; // [rsp+30h] [rbp+8h] BYREF

  ppMalloc = a1;
  v5 = CoTaskMemAlloc(a3);
  *a4 = v5;
  v6 = v5;
  if ( !v5 )
    return 2147942414LL;
  v7 = 0;
  ppMalloc = 0;
  if ( CoGetMalloc(1u, &ppMalloc) >= 0 )
  {
    v7 = ((__int64 (__fastcall *)(LPMALLOC, void *))ppMalloc->lpVtbl->GetSize)(ppMalloc, v6);
    ((void (__fastcall *)(LPMALLOC))ppMalloc->lpVtbl->Release)(ppMalloc);
  }
  memset_0(*a4, 0, v7);
  return 0;
}

```

## disassembly

```asm
0x180026660  mov     [rsp+arg_8], rbx
0x180026665  mov     [rsp+arg_10], rsi
0x18002666a  mov     [rsp+ppMalloc], rcx
0x18002666f  push    rdi
0x180026670  sub     rsp, 20h
0x180026674  mov     rcx, r8; cb
0x180026677  mov     rdi, r9
0x18002667a  call    cs:__imp_CoTaskMemAlloc
0x180026680  mov     [rdi], rax
0x180026683  mov     rbx, rax
0x180026686  test    rax, rax
0x180026689  jz      short loc_1800266DD
0x18002668b  xor     esi, esi
0x18002668d  lea     rdx, [rsp+28h+ppMalloc]; ppMalloc
0x180026692  mov     [rsp+28h+ppMalloc], rsi
0x180026697  lea     ecx, [rsi+1]; dwMemContext
0x18002669a  call    cs:__imp_CoGetMalloc
0x1800266a0  test    eax, eax
0x1800266a2  js      short loc_1800266CC
0x1800266a4  mov     rcx, [rsp+28h+ppMalloc]
0x1800266a9  mov     rdx, rbx
0x1800266ac  mov     rax, [rcx]
0x1800266af  mov     rax, [rax+30h]
0x1800266b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800266b8  mov     rcx, [rsp+28h+ppMalloc]
0x1800266bd  mov     rsi, rax
0x1800266c0  mov     rdx, [rcx]
0x1800266c3  mov     rax, [rdx+10h]
0x1800266c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800266cc  mov     rcx, [rdi]; void *
0x1800266cf  mov     r8, rsi; Size
0x1800266d2  xor     edx, edx; Val
0x1800266d4  call    memset_0
0x1800266d9  xor     eax, eax
0x1800266db  jmp     short loc_1800266E2
0x1800266dd  mov     eax, 8007000Eh
0x1800266e2  mov     rbx, [rsp+28h+arg_8]
0x1800266e7  mov     rsi, [rsp+28h+arg_10]
0x1800266ec  add     rsp, 20h
0x1800266f0  pop     rdi
0x1800266f1  retn
```
