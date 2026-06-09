# VmpPerformanceOff(VM_VOLUME_EXTENSION *,_IRP *)

- ea: `0x140012d60`
- end: `0x140012dad`
- name: `?VmpPerformanceOff@@YAXPEAVVM_VOLUME_EXTENSION@@PEAU_IRP@@@Z`
- size: `77`
- prototype: `void __fastcall(struct VM_VOLUME_EXTENSION *, struct _IRP *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140001ae0`

## callees

- `0x140005090`
- `0x140012d60`

## pseudocode

```c
void __fastcall VmpPerformanceOff(struct VM_VOLUME_EXTENSION *a1, struct _IRP *a2)
{
  if ( *((_BYTE *)a1 + 161)
    && _InterlockedCompareExchange((volatile signed __int32 *)a1 + 54, 0, 1) == 1
    && !(*(unsigned __int8 (__fastcall **)(char *, _QWORD, _QWORD))(*((_QWORD *)a1 + 1) + 312LL))(
          (char *)a1 + 224,
          0,
          0) )
  {
    *((_BYTE *)a1 + 161) = 0;
  }
}

```

## disassembly

```asm
0x140012d60  push    rbx
0x140012d62  sub     rsp, 20h
0x140012d66  mov     al, [rcx+0A1h]
0x140012d6c  mov     rbx, rcx
0x140012d6f  test    al, al
0x140012d71  jz      short loc_140012DA6
0x140012d73  xor     edx, edx
0x140012d75  lea     eax, [rdx+1]
0x140012d78  lock cmpxchg [rcx+0D8h], edx
0x140012d80  jnz     short loc_140012DA6
0x140012d82  mov     rax, [rcx+8]
0x140012d86  xor     r8d, r8d
0x140012d89  add     rcx, 0E0h
0x140012d90  mov     rax, [rax+138h]
0x140012d97  call    _guard_dispatch_icall
0x140012d9c  test    al, al
0x140012d9e  jnz     short loc_140012DA6
0x140012da0  mov     [rbx+0A1h], al
0x140012da6  add     rsp, 20h
0x140012daa  pop     rbx
0x140012dab  retn
```
