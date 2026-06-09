# CTCoAllocPolicy::Realloc(void *,ulong,void *,unsigned __int64,void * *)

- ea: `0x180010a80`
- end: `0x180010ada`
- name: `?Realloc@CTCoAllocPolicy@@SAJPEAXK0_KPEAPEAX@Z`
- size: `90`
- prototype: `__int64 __fastcall(void *, __int64, void *, SIZE_T, void **)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180011910`
- `0x180014d80`

## callees

- `0x180002f94`
- `0x18000af9c`
- `0x180010a80`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180010a93`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180010a93`

## pseudocode

```c
__int64 __fastcall CTCoAllocPolicy::Realloc(void *a1, __int64 a2, void *a3, SIZE_T a4, void **a5)
{
  void *v6; // rax
  unsigned __int64 v7; // rax

  v6 = CoTaskMemRealloc(a3, a4);
  *a5 = v6;
  if ( !v6 )
    return 2147942414LL;
  v7 = CTCoAllocPolicy::_CoTaskMemSize(v6);
  if ( v7 > a4 )
    memset_0((char *)*a5 + a4, 0, v7 - a4);
  return 0;
}

```

## disassembly

```asm
0x180010a80  mov     [rsp+arg_0], rbx
0x180010a85  push    rdi
0x180010a86  sub     rsp, 20h
0x180010a8a  mov     rdx, r9; cb
0x180010a8d  mov     rcx, r8; pv
0x180010a90  mov     rbx, r9
0x180010a93  call    cs:__imp_CoTaskMemRealloc
0x180010a99  mov     rdi, [rsp+28h+arg_20]
0x180010a9e  mov     [rdi], rax
0x180010aa1  test    rax, rax
0x180010aa4  jz      short loc_180010ACA
0x180010aa6  mov     rcx, rax; void *
0x180010aa9  call    ?_CoTaskMemSize@CTCoAllocPolicy@@CA_KPEAX@Z; CTCoAllocPolicy::_CoTaskMemSize(void *)
0x180010aae  cmp     rax, rbx
0x180010ab1  jbe     short loc_180010AC6
0x180010ab3  mov     rcx, [rdi]
0x180010ab6  sub     rax, rbx
0x180010ab9  add     rcx, rbx; void *
0x180010abc  mov     r8, rax; Size
0x180010abf  xor     edx, edx; Val
0x180010ac1  call    memset_0
0x180010ac6  xor     eax, eax
0x180010ac8  jmp     short loc_180010ACF
0x180010aca  mov     eax, 8007000Eh
0x180010acf  mov     rbx, [rsp+28h+arg_0]
0x180010ad4  add     rsp, 20h
0x180010ad8  pop     rdi
0x180010ad9  retn
```
