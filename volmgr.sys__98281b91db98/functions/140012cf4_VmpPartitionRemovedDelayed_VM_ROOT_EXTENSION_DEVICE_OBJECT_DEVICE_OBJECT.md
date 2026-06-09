# VmpPartitionRemovedDelayed(VM_ROOT_EXTENSION *,_DEVICE_OBJECT *,_DEVICE_OBJECT *)

- ea: `0x140012cf4`
- end: `0x140012d57`
- name: `?VmpPartitionRemovedDelayed@@YAJPEAVVM_ROOT_EXTENSION@@PEAU_DEVICE_OBJECT@@1@Z`
- size: `99`
- prototype: `__int64 __fastcall(struct VM_ROOT_EXTENSION *, struct _DEVICE_OBJECT *, struct _DEVICE_OBJECT *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x14000e300`

## callees

- `0x140003e70`
- `0x140003ef0`
- `0x140005090`
- `0x140012cf4`

## pseudocode

```c
__int64 __fastcall VmpPartitionRemovedDelayed(
        struct VM_ROOT_EXTENSION *a1,
        struct _DEVICE_OBJECT *a2,
        struct _DEVICE_OBJECT *a3)
{
  int v6; // ebx
  __int64 result; // rax

  if ( !*((_QWORD *)a1 + 49) )
    return 0;
  VmpRestoreExtensionDriver((__int64)a1);
  v6 = (*(__int64 (__fastcall **)(struct _DEVICE_OBJECT *, struct _DEVICE_OBJECT *))(*((_QWORD *)a1 + 49) + 40LL))(
         a2,
         a3);
  VmpPageExtensionDriver((__int64)a1);
  result = 0;
  if ( v6 < 0 )
    return (unsigned int)v6;
  return result;
}

```

## disassembly

```asm
0x140012cf4  mov     [rsp+arg_0], rbx
0x140012cf9  mov     [rsp+arg_8], rsi
0x140012cfe  push    rdi
0x140012cff  sub     rsp, 20h
0x140012d03  cmp     qword ptr [rcx+188h], 0
0x140012d0b  mov     rbx, r8
0x140012d0e  mov     rsi, rdx
0x140012d11  mov     rdi, rcx
0x140012d14  jz      short loc_140012D44
0x140012d16  call    VmpRestoreExtensionDriver
0x140012d1b  mov     rax, [rdi+188h]
0x140012d22  mov     rdx, rbx
0x140012d25  mov     rcx, rsi
0x140012d28  mov     rax, [rax+28h]
0x140012d2c  call    _guard_dispatch_icall
0x140012d31  mov     rcx, rdi
0x140012d34  mov     ebx, eax
0x140012d36  call    VmpPageExtensionDriver
0x140012d3b  xor     eax, eax
0x140012d3d  test    ebx, ebx
0x140012d3f  cmovs   eax, ebx
0x140012d42  jmp     short loc_140012D46
0x140012d44  xor     eax, eax
0x140012d46  mov     rbx, [rsp+28h+arg_0]
0x140012d4b  mov     rsi, [rsp+28h+arg_8]
0x140012d50  add     rsp, 20h
0x140012d54  pop     rdi
0x140012d55  retn
```
