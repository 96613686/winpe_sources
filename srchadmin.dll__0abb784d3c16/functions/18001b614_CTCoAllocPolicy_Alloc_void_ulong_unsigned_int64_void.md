# CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)

- ea: `0x18001b614`
- end: `0x18001b63b`
- name: `?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z`
- size: `39`
- prototype: `__int64 __fastcall(void *, __int64, SIZE_T, void **)`
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001a220`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001b620`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001b620`

## pseudocode

```c
__int64 __fastcall CTCoAllocPolicy::Alloc(void *a1, __int64 a2, SIZE_T a3, void **a4)
{
  void *v5; // rax

  v5 = CoTaskMemAlloc(a3);
  *a4 = v5;
  return v5 == 0 ? 0x8007000E : 0;
}

```

## disassembly

```asm
0x18001b614  push    rbx
0x18001b616  sub     rsp, 20h
0x18001b61a  mov     rcx, r8; cb
0x18001b61d  mov     rbx, r9
0x18001b620  call    cs:__imp_CoTaskMemAlloc
0x18001b626  mov     [rbx], rax
0x18001b629  neg     rax
0x18001b62c  sbb     eax, eax
0x18001b62e  not     eax
0x18001b630  and     eax, 8007000Eh
0x18001b635  add     rsp, 20h
0x18001b639  pop     rbx
0x18001b63a  retn
```
