# CTCoAllocPolicy::Realloc(void *,ulong,void *,unsigned __int64,void * *)

- ea: `0x18000e8d8`
- end: `0x18000e932`
- name: `?Realloc@CTCoAllocPolicy@@SAJPEAXK0_KPEAPEAX@Z`
- size: `90`
- prototype: `static int(void *, unsigned int, void *, unsigned __int64, void **)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18000ec78`
- `0x1800231f0`
- `0x180023ab8`

## callees

- `0x18000687c`
- `0x18000e8d8`
- `0x18000ec14`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18000e8eb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18000e8eb`

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
0x18000e8d8  mov     [rsp+arg_0], rbx
0x18000e8dd  push    rdi
0x18000e8de  sub     rsp, 20h
0x18000e8e2  mov     rdx, r9; cb
0x18000e8e5  mov     rcx, r8; pv
0x18000e8e8  mov     rbx, r9
0x18000e8eb  call    cs:__imp_CoTaskMemRealloc
0x18000e8f1  mov     rdi, [rsp+28h+arg_20]
0x18000e8f6  mov     [rdi], rax
0x18000e8f9  test    rax, rax
0x18000e8fc  jz      short loc_18000E922
0x18000e8fe  mov     rcx, rax; void *
0x18000e901  call    ?_CoTaskMemSize@CTCoAllocPolicy@@CA_KPEAX@Z; CTCoAllocPolicy::_CoTaskMemSize(void *)
0x18000e906  cmp     rax, rbx
0x18000e909  jbe     short loc_18000E91E
0x18000e90b  mov     rcx, [rdi]
0x18000e90e  sub     rax, rbx
0x18000e911  add     rcx, rbx; void *
0x18000e914  mov     r8, rax; Size
0x18000e917  xor     edx, edx; Val
0x18000e919  call    memset_0
0x18000e91e  xor     eax, eax
0x18000e920  jmp     short loc_18000E927
0x18000e922  mov     eax, 8007000Eh
0x18000e927  mov     rbx, [rsp+28h+arg_0]
0x18000e92c  add     rsp, 20h
0x18000e930  pop     rdi
0x18000e931  retn
```
