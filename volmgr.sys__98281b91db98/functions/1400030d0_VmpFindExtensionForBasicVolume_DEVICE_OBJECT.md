# VmpFindExtensionForBasicVolume(_DEVICE_OBJECT *)

- ea: `0x1400030d0`
- end: `0x14000311c`
- name: `?VmpFindExtensionForBasicVolume@@YAPEAVVM_VOLUME_EXTENSION@@PEAU_DEVICE_OBJECT@@@Z`
- size: `76`
- prototype: `struct VM_VOLUME_EXTENSION *__fastcall(struct _DEVICE_OBJECT *)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x140003000`
- `0x14000e888`

## callees

- `0x1400030d0`

## pseudocode

```c
struct _DEVICE_OBJECT **__fastcall VmpFindExtensionForBasicVolume(struct _DEVICE_OBJECT *a1)
{
  struct _DEVICE_OBJECT **result; // rax
  char v2; // r9
  struct VM_ROOT_EXTENSION *i; // rdx

  result = 0;
  v2 = 0;
  for ( i = (struct VM_ROOT_EXTENSION *)*((_QWORD *)VmRootExtension + 26);
        i != (struct VM_ROOT_EXTENSION *)((char *)VmRootExtension + 208);
        i = *(struct VM_ROOT_EXTENSION **)i )
  {
    result = (struct _DEVICE_OBJECT **)((char *)i - 32);
    if ( !*((_BYTE *)i + 394) && (result[43] == a1 || result[44] == a1) )
    {
      v2 = 1;
      break;
    }
  }
  if ( !v2 )
    return 0;
  return result;
}

```

## disassembly

```asm
0x1400030d0  mov     r8, cs:?VmRootExtension@@3PEAVVM_ROOT_EXTENSION@@EA; VM_ROOT_EXTENSION * VmRootExtension
0x1400030d7  xor     eax, eax
0x1400030d9  xor     r9b, r9b
0x1400030dc  add     r8, 0D0h
0x1400030e3  mov     rdx, [r8]
0x1400030e6  cmp     rdx, r8
0x1400030e9  jz      short loc_140003112
0x1400030eb  lea     rax, [rdx-20h]
0x1400030ef  cmp     [rax+1AAh], r9b
0x1400030f6  jnz     short loc_14000310A
0x1400030f8  cmp     [rax+158h], rcx
0x1400030ff  jz      short loc_14000310F
0x140003101  cmp     [rax+160h], rcx
0x140003108  jz      short loc_14000310F
0x14000310a  mov     rdx, [rdx]
0x14000310d  jmp     short loc_1400030E6
0x14000310f  mov     r9b, 1
0x140003112  xor     ecx, ecx
0x140003114  test    r9b, r9b
0x140003117  cmovz   rax, rcx
0x14000311b  retn
```
