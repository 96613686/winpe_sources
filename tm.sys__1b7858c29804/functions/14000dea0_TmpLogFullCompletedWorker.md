# TmpLogFullCompletedWorker

- ea: `0x14000dea0`
- end: `0x14000df21`
- name: `TmpLogFullCompletedWorker`
- size: `129`
- prototype: `__int64 __fastcall(PVOID Object)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x14000dea0`

## import_xrefs

- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14000ded9`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14000ded9`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000defa`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000defa`
- `ntoskrnl!ObfDereferenceObject` at `0x14000df09`
- `ntoskrnl!ObfDereferenceObject` at `0x14000df09`
- `ntoskrnl!KeSetEvent` at `0x14000dec1`
- `ntoskrnl!KeSetEvent` at `0x14000dec1`

## pseudocode

```c
LONG_PTR __fastcall TmpLogFullCompletedWorker(char *Object)
{
  _InterlockedAnd((volatile signed __int32 *)Object + 33, 0xFFFFFFFD);
  KeSetEvent((PRKEVENT)(Object + 688), 0, 0);
  ExAcquireResourceExclusiveLite((PERESOURCE)(Object + 784), 1u);
  if ( (*((_DWORD *)Object + 33) & 4) == 0 )
    _InterlockedAnd((volatile signed __int32 *)Object + 222, 0xFFFFFFFB);
  ExReleaseResourceLite((PERESOURCE)(Object + 784));
  return ObfDereferenceObject(Object);
}

```

## disassembly

```asm
0x14000dea0  mov     [rsp+arg_0], rbx
0x14000dea5  push    rdi
0x14000dea6  sub     rsp, 20h
0x14000deaa  mov     rbx, rcx
0x14000dead  lock and dword ptr [rcx+84h], 0FFFFFFFDh
0x14000deb5  add     rcx, 2B0h; Event
0x14000debc  xor     r8d, r8d; Wait
0x14000debf  xor     edx, edx; Increment
0x14000dec1  call    cs:__imp_KeSetEvent
0x14000dec8  nop     dword ptr [rax+rax+00h]
0x14000decd  lea     rdi, [rbx+310h]
0x14000ded4  mov     dl, 1; Wait
0x14000ded6  mov     rcx, rdi; Resource
0x14000ded9  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14000dee0  nop     dword ptr [rax+rax+00h]
0x14000dee5  mov     eax, [rbx+84h]
0x14000deeb  test    al, 4
0x14000deed  jnz     short loc_14000DEF7
0x14000deef  lock and dword ptr [rbx+378h], 0FFFFFFFBh
0x14000def7  mov     rcx, rdi; Resource
0x14000defa  call    cs:__imp_ExReleaseResourceLite
0x14000df01  nop     dword ptr [rax+rax+00h]
0x14000df06  mov     rcx, rbx; Object
0x14000df09  call    cs:__imp_ObfDereferenceObject
0x14000df10  nop     dword ptr [rax+rax+00h]
0x14000df15  mov     rbx, [rsp+28h+arg_0]
0x14000df1a  add     rsp, 20h
0x14000df1e  pop     rdi
0x14000df1f  retn
```
