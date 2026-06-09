# CTCoAllocPolicy::Realloc(void *,ulong,void *,unsigned __int64,void * *)

- ea: `0x18003dea8`
- end: `0x18003df5e`
- name: `?Realloc@CTCoAllocPolicy@@SAJPEAXK0_KPEAPEAX@Z`
- size: `182`
- prototype: `static int(void *, unsigned int, void *, unsigned __int64, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18003b554`

## callees

- `0x180002f34`
- `0x18003dea8`
- `0x180057010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x18003def4`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x18003def4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18003dec5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18003dec5`

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
0x18003dea8  mov     [rsp+arg_8], rbx
0x18003dead  mov     [rsp+arg_10], rsi
0x18003deb2  mov     [rsp+ppMalloc], rcx
0x18003deb7  push    rdi
0x18003deb8  sub     rsp, 20h
0x18003debc  mov     rdx, r9; cb
0x18003debf  mov     rcx, r8; pv
0x18003dec2  mov     rbx, r9
0x18003dec5  call    cs:__imp_CoTaskMemRealloc
0x18003decc  nop     dword ptr [rax+rax+00h]
0x18003ded1  mov     rsi, [rsp+28h+arg_20]
0x18003ded6  mov     rdi, rax
0x18003ded9  mov     [rsi], rax
0x18003dedc  test    rax, rax
0x18003dedf  jz      short loc_18003DF48
0x18003dee1  lea     rdx, [rsp+28h+ppMalloc]; ppMalloc
0x18003dee6  mov     [rsp+28h+ppMalloc], 0
0x18003deef  mov     ecx, 1; dwMemContext
0x18003def4  call    cs:__imp_CoGetMalloc
0x18003defb  nop     dword ptr [rax+rax+00h]
0x18003df00  test    eax, eax
0x18003df02  js      short loc_18003DF44
0x18003df04  mov     rcx, [rsp+28h+ppMalloc]
0x18003df09  mov     rdx, rdi
0x18003df0c  mov     rax, [rcx]
0x18003df0f  mov     rax, [rax+30h]
0x18003df13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003df18  mov     rcx, [rsp+28h+ppMalloc]
0x18003df1d  mov     rdi, rax
0x18003df20  mov     rdx, [rcx]
0x18003df23  mov     rax, [rdx+10h]
0x18003df27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003df2c  cmp     rdi, rbx
0x18003df2f  jbe     short loc_18003DF44
0x18003df31  mov     rcx, [rsi]
0x18003df34  sub     rdi, rbx
0x18003df37  add     rcx, rbx; void *
0x18003df3a  mov     r8, rdi; Size
0x18003df3d  xor     edx, edx; Val
0x18003df3f  call    memset_0
0x18003df44  xor     eax, eax
0x18003df46  jmp     short loc_18003DF4D
0x18003df48  mov     eax, 8007000Eh
0x18003df4d  mov     rbx, [rsp+28h+arg_8]
0x18003df52  mov     rsi, [rsp+28h+arg_10]
0x18003df57  add     rsp, 20h
0x18003df5b  pop     rdi
0x18003df5c  retn
```
