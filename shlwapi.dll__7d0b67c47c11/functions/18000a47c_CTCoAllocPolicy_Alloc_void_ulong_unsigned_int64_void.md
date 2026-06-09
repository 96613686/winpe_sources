# CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)

- ea: `0x18000a47c`
- end: `0x18000a4ca`
- name: `?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z`
- size: `78`
- prototype: `static int(void *, unsigned int, unsigned __int64, void **)`
- caller_count: `7`
- callee_count: `3`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18000a360`
- `0x18000eb1c`
- `0x1800260f8`
- `0x18002fc50`
- `0x180030e6c`
- `0x180031644`
- `0x18003189c`

## callees

- `0x18000a47c`
- `0x18000a5b8`
- `0x180013066`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000a48e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000a48e`

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
0x18000a47c  mov     [rsp+arg_0], rbx
0x18000a481  push    rdi
0x18000a482  sub     rsp, 20h
0x18000a486  mov     rcx, r8; cb
0x18000a489  mov     rdi, r9
0x18000a48c  mov     ebx, edx
0x18000a48e  call    cs:__imp_CoTaskMemAlloc
0x18000a494  mov     [rdi], rax
0x18000a497  test    rax, rax
0x18000a49a  jz      short loc_18000A4BA
0x18000a49c  test    bl, 1
0x18000a49f  jz      short loc_18000A4B6
0x18000a4a1  mov     rcx, rax; void *
0x18000a4a4  call    ?_CoTaskMemSize@CTCoAllocPolicy@@CA_KPEAX@Z; CTCoAllocPolicy::_CoTaskMemSize(void *)
0x18000a4a9  mov     rcx, [rdi]; void *
0x18000a4ac  mov     r8, rax; Size
0x18000a4af  xor     edx, edx; Val
0x18000a4b1  call    memset_0
0x18000a4b6  xor     eax, eax
0x18000a4b8  jmp     short loc_18000A4BF
0x18000a4ba  mov     eax, 8007000Eh
0x18000a4bf  mov     rbx, [rsp+28h+arg_0]
0x18000a4c4  add     rsp, 20h
0x18000a4c8  pop     rdi
0x18000a4c9  retn
```
