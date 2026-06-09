# SafeSusComAlloc(unsigned __int64,int)

- ea: `0x18000a684`
- end: `0x18000a6ca`
- name: `?SafeSusComAlloc@@YAPEAX_KH@Z`
- size: `70`
- prototype: `void *__fastcall(size_t Size, int)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000a7b4`
- `0x180038658`

## callees

- `0x18000a684`
- `0x1800492e0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000a698`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000a698`

## pseudocode

```c
void *__fastcall SafeSusComAlloc(size_t Size, int a2)
{
  void *v4; // rax
  void *v5; // rbx

  v4 = CoTaskMemAlloc(Size);
  v5 = v4;
  if ( v4 && a2 )
    memset(v4, 0, Size);
  return v5;
}

```

## disassembly

```asm
0x18000a684  mov     [rsp+arg_0], rbx
0x18000a689  mov     [rsp+arg_8], rsi
0x18000a68e  push    rdi
0x18000a68f  sub     rsp, 20h
0x18000a693  mov     esi, edx
0x18000a695  mov     rdi, rcx
0x18000a698  call    cs:__imp_CoTaskMemAlloc
0x18000a69e  mov     rbx, rax
0x18000a6a1  test    rax, rax
0x18000a6a4  jz      short loc_18000A6B7
0x18000a6a6  test    esi, esi
0x18000a6a8  jz      short loc_18000A6B7
0x18000a6aa  mov     r8, rdi; Size
0x18000a6ad  xor     edx, edx; Val
0x18000a6af  mov     rcx, rax; void *
0x18000a6b2  call    memset
0x18000a6b7  mov     rsi, [rsp+28h+arg_8]
0x18000a6bc  mov     rax, rbx
0x18000a6bf  mov     rbx, [rsp+28h+arg_0]
0x18000a6c4  add     rsp, 20h
0x18000a6c8  pop     rdi
0x18000a6c9  retn
```
