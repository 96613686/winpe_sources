# CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)

- ea: `0x1800063c0`
- end: `0x18000640e`
- name: `?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z`
- size: `78`
- prototype: `__int64 __fastcall(void *, char, SIZE_T, void **)`
- caller_count: `10`
- callee_count: `3`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800056a0`
- `0x18000c438`
- `0x18000c6d4`
- `0x18000e9f8`
- `0x180015c90`
- `0x1800164b8`
- `0x180016b04`
- `0x18001d188`
- `0x18001d3f0`
- `0x18001d5ec`

## callees

- `0x180002f94`
- `0x1800063c0`
- `0x18000af9c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800063d2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800063d2`

## pseudocode

```c
__int64 __fastcall CTCoAllocPolicy::Alloc(void *a1, char a2, SIZE_T a3, void **a4)
{
  void *v6; // rax
  size_t v7; // rax

  v6 = CoTaskMemAlloc(a3);
  *a4 = v6;
  if ( !v6 )
    return 2147942414LL;
  if ( (a2 & 1) != 0 )
  {
    v7 = CTCoAllocPolicy::_CoTaskMemSize(v6);
    memset_0(*a4, 0, v7);
  }
  return 0;
}

```

## disassembly

```asm
0x1800063c0  mov     [rsp+arg_0], rbx
0x1800063c5  push    rdi
0x1800063c6  sub     rsp, 20h
0x1800063ca  mov     rcx, r8; cb
0x1800063cd  mov     rdi, r9
0x1800063d0  mov     ebx, edx
0x1800063d2  call    cs:__imp_CoTaskMemAlloc
0x1800063d8  mov     [rdi], rax
0x1800063db  test    rax, rax
0x1800063de  jz      short loc_1800063FE
0x1800063e0  test    bl, 1
0x1800063e3  jz      short loc_1800063FA
0x1800063e5  mov     rcx, rax; void *
0x1800063e8  call    ?_CoTaskMemSize@CTCoAllocPolicy@@CA_KPEAX@Z; CTCoAllocPolicy::_CoTaskMemSize(void *)
0x1800063ed  mov     rcx, [rdi]; void *
0x1800063f0  mov     r8, rax; Size
0x1800063f3  xor     edx, edx; Val
0x1800063f5  call    memset_0
0x1800063fa  xor     eax, eax
0x1800063fc  jmp     short loc_180006403
0x1800063fe  mov     eax, 8007000Eh
0x180006403  mov     rbx, [rsp+28h+arg_0]
0x180006408  add     rsp, 20h
0x18000640c  pop     rdi
0x18000640d  retn
```
