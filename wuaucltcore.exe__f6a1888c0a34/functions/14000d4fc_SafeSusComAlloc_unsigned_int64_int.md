# SafeSusComAlloc(unsigned __int64,int)

- ea: `0x14000d4fc`
- end: `0x14000d532`
- name: `?SafeSusComAlloc@@YAPEAX_KH@Z`
- size: `54`
- prototype: `void *__fastcall(size_t Size, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x14000d598`

## callees

- `0x14000d4fc`
- `0x140020760`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14000d509`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14000d509`

## pseudocode

```c
void *__fastcall SafeSusComAlloc(size_t Size)
{
  void *v2; // rax
  void *v3; // rbx

  v2 = CoTaskMemAlloc(Size);
  v3 = v2;
  if ( v2 )
    memset(v2, 0, Size);
  return v3;
}

```

## disassembly

```asm
0x14000d4fc  mov     [rsp+arg_0], rbx
0x14000d501  push    rdi
0x14000d502  sub     rsp, 20h
0x14000d506  mov     rdi, rcx
0x14000d509  call    cs:__imp_CoTaskMemAlloc
0x14000d50f  mov     rbx, rax
0x14000d512  test    rax, rax
0x14000d515  jz      short loc_14000D524
0x14000d517  mov     r8, rdi; Size
0x14000d51a  xor     edx, edx; Val
0x14000d51c  mov     rcx, rax; void *
0x14000d51f  call    memset
0x14000d524  mov     rax, rbx
0x14000d527  mov     rbx, [rsp+28h+arg_0]
0x14000d52c  add     rsp, 20h
0x14000d530  pop     rdi
0x14000d531  retn
```
