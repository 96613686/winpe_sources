# VmpWholeDiskRemovedDelayed(VM_ROOT_EXTENSION *,_DEVICE_OBJECT *)

- ea: `0x1400149e8`
- end: `0x140014a3b`
- name: `?VmpWholeDiskRemovedDelayed@@YAJPEAVVM_ROOT_EXTENSION@@PEAU_DEVICE_OBJECT@@@Z`
- size: `83`
- prototype: `__int64 __fastcall(struct VM_ROOT_EXTENSION *, struct _DEVICE_OBJECT *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x14000e300`

## callees

- `0x140003e70`
- `0x140003ef0`
- `0x140005090`
- `0x1400149e8`

## pseudocode

```c
__int64 __fastcall VmpWholeDiskRemovedDelayed(struct VM_ROOT_EXTENSION *a1, struct _DEVICE_OBJECT *a2)
{
  int v4; // ebx
  __int64 result; // rax

  if ( !*((_QWORD *)a1 + 49) )
    return 0;
  VmpRestoreExtensionDriver((__int64)a1);
  v4 = (*(__int64 (__fastcall **)(struct _DEVICE_OBJECT *))(*((_QWORD *)a1 + 49) + 56LL))(a2);
  VmpPageExtensionDriver((__int64)a1);
  result = 0;
  if ( v4 < 0 )
    return (unsigned int)v4;
  return result;
}

```

## disassembly

```asm
0x1400149e8  mov     [rsp+arg_0], rbx
0x1400149ed  push    rdi
0x1400149ee  sub     rsp, 20h
0x1400149f2  cmp     qword ptr [rcx+188h], 0
0x1400149fa  mov     rbx, rdx
0x1400149fd  mov     rdi, rcx
0x140014a00  jz      short loc_140014A2D
0x140014a02  call    VmpRestoreExtensionDriver
0x140014a07  mov     rax, [rdi+188h]
0x140014a0e  mov     rcx, rbx
0x140014a11  mov     rax, [rax+38h]
0x140014a15  call    _guard_dispatch_icall
0x140014a1a  mov     rcx, rdi
0x140014a1d  mov     ebx, eax
0x140014a1f  call    VmpPageExtensionDriver
0x140014a24  xor     eax, eax
0x140014a26  test    ebx, ebx
0x140014a28  cmovs   eax, ebx
0x140014a2b  jmp     short loc_140014A2F
0x140014a2d  xor     eax, eax
0x140014a2f  mov     rbx, [rsp+28h+arg_0]
0x140014a34  add     rsp, 20h
0x140014a38  pop     rdi
0x140014a39  retn
```
