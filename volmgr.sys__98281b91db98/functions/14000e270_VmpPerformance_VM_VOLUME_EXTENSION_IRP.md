# VmpPerformance(VM_VOLUME_EXTENSION *,_IRP *)

- ea: `0x14000e270`
- end: `0x14000e2f4`
- name: `?VmpPerformance@@YAJPEAVVM_VOLUME_EXTENSION@@PEAU_IRP@@@Z`
- size: `132`
- prototype: `__int64 __fastcall(struct VM_VOLUME_EXTENSION *, struct _IRP *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x140001ae0`

## callees

- `0x140005090`
- `0x14000e270`
- `0x140015288`

## pseudocode

```c
__int64 __fastcall VmpPerformance(struct VM_VOLUME_EXTENSION *a1, struct _IRP *a2)
{
  __int64 result; // rax

  if ( a2->Tail.Overlay.CurrentStackLocation->Parameters.Read.Length < 0x58 )
    return 3221225485LL;
  if ( *((_BYTE *)a1 + 161) || (result = VmpQueryEnableCountersAlways(*(_QWORD *)a1), (int)result >= 0) )
  {
    (*(void (__fastcall **)(_QWORD, struct _IRP *, const wchar_t *, _QWORD))(*((_QWORD *)a1 + 1) + 336LL))(
      *((_QWORD *)a1 + 28),
      a2->AssociatedIrp.MasterIrp,
      L"VOLMGR  ",
      *((unsigned int *)a1 + 41));
    result = 0;
    a2->IoStatus.Information = 88;
  }
  return result;
}

```

## disassembly

```asm
0x14000e270  mov     [rsp+arg_0], rbx
0x14000e275  push    rdi
0x14000e276  sub     rsp, 30h
0x14000e27a  mov     rax, [rdx+0B8h]
0x14000e281  mov     rbx, rdx
0x14000e284  mov     rdi, rcx
0x14000e287  cmp     dword ptr [rax+8], 58h ; 'X'
0x14000e28b  jnb     short loc_14000E29E
0x14000e28d  mov     eax, 0C000000Dh
0x14000e292  mov     rbx, [rsp+38h+arg_0]
0x14000e297  add     rsp, 30h
0x14000e29b  pop     rdi
0x14000e29c  retn
0x14000e29e  movzx   eax, byte ptr [rcx+0A1h]
0x14000e2a5  test    al, al
0x14000e2a7  jnz     short loc_14000E2B5
0x14000e2a9  mov     rcx, [rcx]
0x14000e2ac  call    VmpQueryEnableCountersAlways
0x14000e2b1  test    eax, eax
0x14000e2b3  js      short loc_14000E2E8
0x14000e2b5  mov     rax, [rdi+8]
0x14000e2b9  lea     r8, aVolmgr; "VOLMGR  "
0x14000e2c0  mov     r9d, [rdi+0A4h]
0x14000e2c7  mov     rdx, [rbx+18h]
0x14000e2cb  mov     rcx, [rdi+0E0h]
0x14000e2d2  mov     rax, [rax+150h]
0x14000e2d9  call    _guard_dispatch_icall
0x14000e2de  xor     eax, eax
0x14000e2e0  mov     qword ptr [rbx+38h], 58h ; 'X'
0x14000e2e8  mov     rbx, [rsp+38h+arg_0]
0x14000e2ed  add     rsp, 30h
0x14000e2f1  pop     rdi
0x14000e2f2  retn
```
