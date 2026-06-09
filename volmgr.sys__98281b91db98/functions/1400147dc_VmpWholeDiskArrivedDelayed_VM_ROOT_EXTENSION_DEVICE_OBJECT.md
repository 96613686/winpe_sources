# VmpWholeDiskArrivedDelayed(VM_ROOT_EXTENSION *,_DEVICE_OBJECT *)

- ea: `0x1400147dc`
- end: `0x14001482f`
- name: `?VmpWholeDiskArrivedDelayed@@YAJPEAVVM_ROOT_EXTENSION@@PEAU_DEVICE_OBJECT@@@Z`
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
- `0x1400147dc`

## pseudocode

```c
__int64 __fastcall VmpWholeDiskArrivedDelayed(struct VM_ROOT_EXTENSION *a1, struct _DEVICE_OBJECT *a2)
{
  int v4; // ebx
  __int64 result; // rax

  if ( !*((_QWORD *)a1 + 49) )
    return 0;
  VmpRestoreExtensionDriver((__int64)a1);
  v4 = (*(__int64 (__fastcall **)(struct _DEVICE_OBJECT *))(*((_QWORD *)a1 + 49) + 8LL))(a2);
  VmpPageExtensionDriver((__int64)a1);
  result = 0;
  if ( v4 < 0 )
    return (unsigned int)v4;
  return result;
}

```

## disassembly

```asm
0x1400147dc  mov     [rsp+arg_0], rbx
0x1400147e1  push    rdi
0x1400147e2  sub     rsp, 20h
0x1400147e6  cmp     qword ptr [rcx+188h], 0
0x1400147ee  mov     rbx, rdx
0x1400147f1  mov     rdi, rcx
0x1400147f4  jz      short loc_140014821
0x1400147f6  call    VmpRestoreExtensionDriver
0x1400147fb  mov     rax, [rdi+188h]
0x140014802  mov     rcx, rbx
0x140014805  mov     rax, [rax+8]
0x140014809  call    _guard_dispatch_icall
0x14001480e  mov     rcx, rdi
0x140014811  mov     ebx, eax
0x140014813  call    VmpPageExtensionDriver
0x140014818  xor     eax, eax
0x14001481a  test    ebx, ebx
0x14001481c  cmovs   eax, ebx
0x14001481f  jmp     short loc_140014823
0x140014821  xor     eax, eax
0x140014823  mov     rbx, [rsp+28h+arg_0]
0x140014828  add     rsp, 20h
0x14001482c  pop     rdi
0x14001482d  retn
```
