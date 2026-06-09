# CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)

- ea: `0x180028ffc`
- end: `0x18002904c`
- name: `?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z`
- size: `80`
- prototype: `static int(void *, unsigned int, unsigned __int64, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800225f0`

## callees

- `0x180028ffc`
- `0x1800364ac`
- `0x18003f588`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002900e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002900e`

## pseudocode

```c
__int64 __fastcall CTCoAllocPolicy::Alloc(void *a1, char a2, SIZE_T a3, void **a4)
{
  void *v6; // rax
  size_t v8; // rax

  v6 = CoTaskMemAlloc(a3);
  *a4 = v6;
  if ( !v6 )
    return 2147942414LL;
  if ( (a2 & 1) != 0 )
  {
    v8 = CTCoAllocPolicy::_CoTaskMemSize(v6);
    memset_0(*a4, 0, v8);
  }
  return 0;
}

```

## disassembly

```asm
0x180028ffc  mov     [rsp+arg_0], rbx
0x180029001  push    rdi
0x180029002  sub     rsp, 20h
0x180029006  mov     rcx, r8; cb
0x180029009  mov     rdi, r9
0x18002900c  mov     ebx, edx
0x18002900e  call    cs:__imp_CoTaskMemAlloc
0x180029014  mov     [rdi], rax
0x180029017  test    rax, rax
0x18002901a  jz      short loc_18002902E
0x18002901c  test    bl, 1
0x18002901f  jnz     short loc_180029035
0x180029021  xor     eax, eax
0x180029023  mov     rbx, [rsp+28h+arg_0]
0x180029028  add     rsp, 20h
0x18002902c  pop     rdi
0x18002902d  retn
0x18002902e  mov     eax, 8007000Eh
0x180029033  jmp     short loc_180029023
0x180029035  mov     rcx, rax; void *
0x180029038  call    ?_CoTaskMemSize@CTCoAllocPolicy@@CA_KPEAX@Z; CTCoAllocPolicy::_CoTaskMemSize(void *)
0x18002903d  mov     rcx, [rdi]; void *
0x180029040  mov     r8, rax; Size
0x180029043  xor     edx, edx; Val
0x180029045  call    memset_0
0x18002904a  jmp     short loc_180029021
```
