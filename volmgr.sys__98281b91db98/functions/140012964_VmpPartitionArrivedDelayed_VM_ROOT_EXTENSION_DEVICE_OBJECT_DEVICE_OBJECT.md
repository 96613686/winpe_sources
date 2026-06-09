# VmpPartitionArrivedDelayed(VM_ROOT_EXTENSION *,_DEVICE_OBJECT *,_DEVICE_OBJECT *)

- ea: `0x140012964`
- end: `0x1400129c7`
- name: `?VmpPartitionArrivedDelayed@@YAJPEAVVM_ROOT_EXTENSION@@PEAU_DEVICE_OBJECT@@1@Z`
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
- `0x140012964`

## pseudocode

```c
__int64 __fastcall VmpPartitionArrivedDelayed(
        struct VM_ROOT_EXTENSION *a1,
        struct _DEVICE_OBJECT *a2,
        struct _DEVICE_OBJECT *a3)
{
  int v6; // ebx
  __int64 result; // rax

  if ( !*((_QWORD *)a1 + 49) )
    return 0;
  VmpRestoreExtensionDriver((__int64)a1);
  v6 = (*(__int64 (__fastcall **)(struct _DEVICE_OBJECT *, struct _DEVICE_OBJECT *))(*((_QWORD *)a1 + 49) + 24LL))(
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
0x140012964  mov     [rsp+arg_0], rbx
0x140012969  mov     [rsp+arg_8], rsi
0x14001296e  push    rdi
0x14001296f  sub     rsp, 20h
0x140012973  cmp     qword ptr [rcx+188h], 0
0x14001297b  mov     rbx, r8
0x14001297e  mov     rsi, rdx
0x140012981  mov     rdi, rcx
0x140012984  jz      short loc_1400129B4
0x140012986  call    VmpRestoreExtensionDriver
0x14001298b  mov     rax, [rdi+188h]
0x140012992  mov     rdx, rbx
0x140012995  mov     rcx, rsi
0x140012998  mov     rax, [rax+18h]
0x14001299c  call    _guard_dispatch_icall
0x1400129a1  mov     rcx, rdi
0x1400129a4  mov     ebx, eax
0x1400129a6  call    VmpPageExtensionDriver
0x1400129ab  xor     eax, eax
0x1400129ad  test    ebx, ebx
0x1400129af  cmovs   eax, ebx
0x1400129b2  jmp     short loc_1400129B6
0x1400129b4  xor     eax, eax
0x1400129b6  mov     rbx, [rsp+28h+arg_0]
0x1400129bb  mov     rsi, [rsp+28h+arg_8]
0x1400129c0  add     rsp, 20h
0x1400129c4  pop     rdi
0x1400129c5  retn
```
