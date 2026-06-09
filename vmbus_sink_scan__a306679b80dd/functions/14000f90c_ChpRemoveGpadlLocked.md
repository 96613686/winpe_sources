# ChpRemoveGpadlLocked

- ea: `0x14000f90c`
- end: `0x14000f9c6`
- name: `ChpRemoveGpadlLocked`
- size: `186`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x14000f5f0`

## callees

- `0x1400030b4`
- `0x14000f90c`
- `0x14000fe8c`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x14000f997`
- `ntoskrnl!KeSetEvent` at `0x14000f997`

## pseudocode

```c
char __fastcall ChpRemoveGpadlLocked(__int64 a1, __int64 *a2)
{
  __int64 v4; // rdx
  __int64 **v5; // rax
  __int64 v6; // rdi
  _QWORD *v7; // rax
  __int64 v8; // rdx
  struct _KEVENT *v9; // rcx

  v4 = *a2;
  if ( *(__int64 **)(v4 + 8) != a2 || (v5 = (__int64 **)a2[1], *v5 != a2) )
    __fastfail(3u);
  v6 = a2[7];
  *v5 = (__int64 *)v4;
  *(_QWORD *)(v4 + 8) = v5;
  a2[1] = (__int64)a2;
  *a2 = (__int64)a2;
  LOBYTE(v7) = ChDereferenceChannelInternal(v6, 23, 215);
  v8 = *((unsigned int *)a2 + 16);
  if ( (_DWORD)v8 )
  {
    LOBYTE(v7) = DvFreeHandleEntry(a1 + 736, v8);
    *((_DWORD *)a2 + 16) = 0;
  }
  v9 = *(struct _KEVENT **)(v6 + 752);
  if ( v9 )
  {
    v7 = (_QWORD *)(v6 + 736);
    if ( (_QWORD *)*v7 == v7 )
    {
      LOBYTE(v7) = KeSetEvent(v9, 0, 0);
      *(_QWORD *)(v6 + 752) = 0;
    }
  }
  return (char)v7;
}

```

## disassembly

```asm
0x14000f90c  mov     [rsp+arg_0], rbx
0x14000f911  mov     [rsp+arg_8], rsi
0x14000f916  push    rdi
0x14000f917  sub     rsp, 20h
0x14000f91b  mov     rbx, rdx
0x14000f91e  mov     rsi, rcx
0x14000f921  mov     rdx, [rdx]
0x14000f924  cmp     [rdx+8], rbx
0x14000f928  jnz     loc_14000F9BF
0x14000f92e  mov     rax, [rbx+8]
0x14000f932  cmp     [rax], rbx
0x14000f935  jnz     loc_14000F9BF
0x14000f93b  mov     rdi, [rbx+38h]
0x14000f93f  mov     r8d, 0D7h
0x14000f945  mov     [rax], rdx
0x14000f948  mov     rcx, rdi
0x14000f94b  mov     [rdx+8], rax
0x14000f94f  mov     edx, 17h
0x14000f954  mov     [rbx+8], rbx
0x14000f958  mov     [rbx], rbx
0x14000f95b  call    ChDereferenceChannelInternal
0x14000f960  mov     edx, [rbx+40h]
0x14000f963  test    edx, edx
0x14000f965  jz      short loc_14000F97A
0x14000f967  lea     rcx, [rsi+2E0h]
0x14000f96e  call    DvFreeHandleEntry
0x14000f973  mov     dword ptr [rbx+40h], 0
0x14000f97a  mov     rcx, [rdi+2F0h]; Event
0x14000f981  test    rcx, rcx
0x14000f984  jz      short loc_14000F9AE
0x14000f986  lea     rax, [rdi+2E0h]
0x14000f98d  cmp     [rax], rax
0x14000f990  jnz     short loc_14000F9AE
0x14000f992  xor     r8d, r8d; Wait
0x14000f995  xor     edx, edx; Increment
0x14000f997  call    cs:__imp_KeSetEvent
0x14000f99e  nop     dword ptr [rax+rax+00h]
0x14000f9a3  mov     qword ptr [rdi+2F0h], 0
0x14000f9ae  mov     rbx, [rsp+28h+arg_0]
0x14000f9b3  mov     rsi, [rsp+28h+arg_8]
0x14000f9b8  add     rsp, 20h
0x14000f9bc  pop     rdi
0x14000f9bd  retn
0x14000f9bf  mov     ecx, 3
0x14000f9c4  int     29h; Win8: RtlFailFast(ecx)
```
