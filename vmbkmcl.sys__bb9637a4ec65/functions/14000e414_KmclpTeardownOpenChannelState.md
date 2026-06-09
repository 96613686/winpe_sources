# KmclpTeardownOpenChannelState

- ea: `0x14000e414`
- end: `0x14000e4d8`
- name: `KmclpTeardownOpenChannelState`
- size: `196`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x14000b3d8`
- `0x14000d9b0`
- `0x14001cdd4`

## callees

- `0x140007914`
- `0x14000e414`
- `0x140011b60`
- `0x140011ed0`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000e454`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000e454`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000e46c`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000e46c`

## pseudocode

```c
__int64 __fastcall KmclpTeardownOpenChannelState(__int64 a1)
{
  __int64 result; // rax
  _QWORD *v3; // rbx

  if ( !*(_BYTE *)(a1 + 1729) )
  {
    PkUninitializeRingBuffer(a1 + 64);
    result = InCloseChannel(a1);
  }
  if ( *(_BYTE *)(a1 + 1728) )
  {
    ExAcquirePushLockExclusiveEx(a1 + 2808, 0);
    *(_BYTE *)(a1 + 2806) = 0;
    result = ExReleasePushLockExclusiveEx(a1 + 2808, 0);
    v3 = (_QWORD *)(a1 + 2368);
    if ( *(_DWORD *)(a1 + 3096) )
    {
      *(_QWORD *)(a1 + 2704) = 0;
      result = (*(__int64 (__fastcall **)(_QWORD))(a1 + 2472))(*v3);
      *(_DWORD *)(a1 + 3096) = 0;
    }
    if ( (*(_BYTE *)(a1 + 2344) & 0x10) != 0 )
    {
      result = (*(__int64 (__fastcall **)(_QWORD))(a1 + 2392))(*v3);
      *(_BYTE *)(a1 + 2344) &= ~0x10u;
    }
  }
  return result;
}

```

## disassembly

```asm
0x14000e414  mov     [rsp+arg_0], rbx
0x14000e419  push    rdi
0x14000e41a  sub     rsp, 20h
0x14000e41e  cmp     byte ptr [rcx+6C1h], 0
0x14000e425  mov     rdi, rcx
0x14000e428  jnz     short loc_14000E43B
0x14000e42a  add     rcx, 40h ; '@'
0x14000e42e  call    PkUninitializeRingBuffer
0x14000e433  mov     rcx, rdi
0x14000e436  call    InCloseChannel
0x14000e43b  cmp     byte ptr [rdi+6C0h], 0
0x14000e442  jz      loc_14000E4CC
0x14000e448  lea     rbx, [rdi+0AF8h]
0x14000e44f  xor     edx, edx
0x14000e451  mov     rcx, rbx
0x14000e454  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14000e45b  nop     dword ptr [rax+rax+00h]
0x14000e460  xor     edx, edx
0x14000e462  mov     byte ptr [rdi+0AF6h], 0
0x14000e469  mov     rcx, rbx
0x14000e46c  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14000e473  nop     dword ptr [rax+rax+00h]
0x14000e478  mov     edx, [rdi+0C18h]
0x14000e47e  lea     rbx, [rdi+940h]
0x14000e485  test    edx, edx
0x14000e487  jz      short loc_14000E4AD
0x14000e489  mov     qword ptr [rdi+0A90h], 0
0x14000e494  mov     rax, [rdi+9A8h]
0x14000e49b  mov     rcx, [rbx]
0x14000e49e  call    _guard_dispatch_icall
0x14000e4a3  mov     dword ptr [rdi+0C18h], 0
0x14000e4ad  test    byte ptr [rdi+928h], 10h
0x14000e4b4  jz      short loc_14000E4CC
0x14000e4b6  mov     rax, [rdi+958h]
0x14000e4bd  mov     rcx, [rbx]
0x14000e4c0  call    _guard_dispatch_icall
0x14000e4c5  and     byte ptr [rdi+928h], 0EFh
0x14000e4cc  mov     rbx, [rsp+28h+arg_0]
0x14000e4d1  add     rsp, 20h
0x14000e4d5  pop     rdi
0x14000e4d6  retn
```
