# VmpQueryCapabilities(VM_ROOT_EXTENSION *,_IRP *)

- ea: `0x140012f18`
- end: `0x140012f9a`
- name: `?VmpQueryCapabilities@@YAJPEAVVM_ROOT_EXTENSION@@PEAU_IRP@@@Z`
- size: `130`
- prototype: `__int64 __fastcall(struct VM_ROOT_EXTENSION *, struct _IRP *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x140001ae0`

## callees

- `0x140003e70`
- `0x140003ef0`
- `0x140005090`
- `0x140012f18`

## pseudocode

```c
__int64 __fastcall VmpQueryCapabilities(struct VM_ROOT_EXTENSION *a1, struct _IRP *a2)
{
  unsigned int v4; // esi
  struct _IRP *MasterIrp; // rax

  if ( *((_QWORD *)a1 + 49) )
  {
    VmpRestoreExtensionDriver((__int64)a1);
    v4 = (*(__int64 (__fastcall **)(struct _IRP *))(*((_QWORD *)a1 + 49) + 96LL))(a2);
    VmpPageExtensionDriver((__int64)a1);
  }
  else
  {
    if ( a2->Tail.Overlay.CurrentStackLocation->Parameters.Read.Length < 3 )
      return 3221225485LL;
    MasterIrp = a2->AssociatedIrp.MasterIrp;
    v4 = 0;
    MasterIrp->Type = 0;
    LOBYTE(MasterIrp->Size) = 0;
    a2->IoStatus.Information = 3;
  }
  return v4;
}

```

## disassembly

```asm
0x140012f18  mov     [rsp+arg_0], rbx
0x140012f1d  mov     [rsp+arg_8], rsi
0x140012f22  push    rdi
0x140012f23  sub     rsp, 20h
0x140012f27  mov     rdi, rcx
0x140012f2a  mov     rbx, rdx
0x140012f2d  xor     ecx, ecx
0x140012f2f  cmp     [rdi+188h], rcx
0x140012f36  jz      short loc_140012F5F
0x140012f38  mov     rcx, rdi
0x140012f3b  call    VmpRestoreExtensionDriver
0x140012f40  mov     rax, [rdi+188h]
0x140012f47  mov     rcx, rbx
0x140012f4a  mov     rax, [rax+60h]
0x140012f4e  call    _guard_dispatch_icall
0x140012f53  mov     rcx, rdi
0x140012f56  mov     esi, eax
0x140012f58  call    VmpPageExtensionDriver
0x140012f5d  jmp     short loc_140012F87
0x140012f5f  mov     rax, [rdx+0B8h]
0x140012f66  cmp     dword ptr [rax+8], 3
0x140012f6a  jnb     short loc_140012F73
0x140012f6c  mov     eax, 0C000000Dh
0x140012f71  jmp     short loc_140012F89
0x140012f73  mov     rax, [rdx+18h]
0x140012f77  mov     esi, ecx
0x140012f79  mov     [rax], cx
0x140012f7c  mov     [rax+2], cl
0x140012f7f  mov     qword ptr [rdx+38h], 3
0x140012f87  mov     eax, esi
0x140012f89  mov     rbx, [rsp+28h+arg_0]
0x140012f8e  mov     rsi, [rsp+28h+arg_8]
0x140012f93  add     rsp, 20h
0x140012f97  pop     rdi
0x140012f98  retn
```
