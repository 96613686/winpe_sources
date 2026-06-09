# VmQueryBasicExtension(void *,ulong,unsigned __int64,unsigned __int64,_DEVICE_OBJECT * *)

- ea: `0x14000fb20`
- end: `0x14000fb4c`
- name: `?VmQueryBasicExtension@@YAPEAXPEAXK_K1PEAPEAU_DEVICE_OBJECT@@@Z`
- size: `44`
- prototype: `void *__fastcall(void *, unsigned int, unsigned __int64, unsigned __int64, struct _DEVICE_OBJECT **)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x14000fb20`
- `0x14001203c`

## pseudocode

```c
struct VM_VOLUME_EXTENSION *__fastcall VmQueryBasicExtension(
        struct VM_ROOT_EXTENSION *a1,
        int a2,
        __int64 a3,
        __int64 a4,
        struct _DEVICE_OBJECT **a5)
{
  struct VM_VOLUME_EXTENSION *result; // rax
  struct _DEVICE_OBJECT *v6; // rcx

  result = VmpFindExtensionForPartition(a1, a2, a3, a4);
  if ( a5 )
  {
    if ( result )
      v6 = (struct _DEVICE_OBJECT *)*((_QWORD *)result + 43);
    else
      v6 = 0;
    *a5 = v6;
  }
  return result;
}

```

## disassembly

```asm
0x14000fb20  sub     rsp, 28h
0x14000fb24  call    ?VmpFindExtensionForPartition@@YAPEAVVM_VOLUME_EXTENSION@@PEAVVM_ROOT_EXTENSION@@K_K1@Z; VmpFindExtensionForPartition(VM_ROOT_EXTENSION *,ulong,unsigned __int64,unsigned __int64)
0x14000fb29  mov     rdx, [rsp+28h+arg_20]
0x14000fb2e  test    rdx, rdx
0x14000fb31  jz      short loc_14000FB46
0x14000fb33  test    rax, rax
0x14000fb36  jz      short loc_14000FB41
0x14000fb38  mov     rcx, [rax+158h]
0x14000fb3f  jmp     short loc_14000FB43
0x14000fb41  xor     ecx, ecx
0x14000fb43  mov     [rdx], rcx
0x14000fb46  add     rsp, 28h
0x14000fb4a  retn
```
