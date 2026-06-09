# CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)

- ea: `0x1800396e0`
- end: `0x180039788`
- name: `?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z`
- size: `168`
- prototype: `static int(void *, unsigned int, unsigned __int64, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180039890`

## callees

- `0x180002f34`
- `0x1800396e0`
- `0x180057010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800396fc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800396fc`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x180039729`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x180039729`

## pseudocode

```c
__int64 __fastcall CTCoAllocPolicy::Alloc(IMalloc *a1, char a2, SIZE_T a3, void **a4)
{
  void *v6; // rax
  void *v7; // rbx
  size_t v8; // rsi
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
0x1800396e0  mov     [rsp+arg_8], rbx
0x1800396e5  mov     [rsp+arg_10], rsi
0x1800396ea  mov     [rsp+ppMalloc], rcx
0x1800396ef  push    rdi
0x1800396f0  sub     rsp, 20h
0x1800396f4  mov     rcx, r8; cb
0x1800396f7  mov     rdi, r9
0x1800396fa  mov     esi, edx
0x1800396fc  call    cs:__imp_CoTaskMemAlloc
0x180039703  nop     dword ptr [rax+rax+00h]
0x180039708  mov     [rdi], rax
0x18003970b  mov     rbx, rax
0x18003970e  test    rax, rax
0x180039711  jz      short loc_180039772
0x180039713  mov     ecx, 1; dwMemContext
0x180039718  test    cl, sil
0x18003971b  jz      short loc_18003976E
0x18003971d  xor     esi, esi
0x18003971f  lea     rdx, [rsp+28h+ppMalloc]; ppMalloc
0x180039724  mov     [rsp+28h+ppMalloc], rsi
0x180039729  call    cs:__imp_CoGetMalloc
0x180039730  nop     dword ptr [rax+rax+00h]
0x180039735  test    eax, eax
0x180039737  js      short loc_180039761
0x180039739  mov     rcx, [rsp+28h+ppMalloc]
0x18003973e  mov     rdx, rbx
0x180039741  mov     rax, [rcx]
0x180039744  mov     rax, [rax+30h]
0x180039748  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003974d  mov     rcx, [rsp+28h+ppMalloc]
0x180039752  mov     rsi, rax
0x180039755  mov     rdx, [rcx]
0x180039758  mov     rax, [rdx+10h]
0x18003975c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039761  mov     rcx, [rdi]; void *
0x180039764  mov     r8, rsi; Size
0x180039767  xor     edx, edx; Val
0x180039769  call    memset_0
0x18003976e  xor     eax, eax
0x180039770  jmp     short loc_180039777
0x180039772  mov     eax, 8007000Eh
0x180039777  mov     rbx, [rsp+28h+arg_8]
0x18003977c  mov     rsi, [rsp+28h+arg_10]
0x180039781  add     rsp, 20h
0x180039785  pop     rdi
0x180039786  retn
```
