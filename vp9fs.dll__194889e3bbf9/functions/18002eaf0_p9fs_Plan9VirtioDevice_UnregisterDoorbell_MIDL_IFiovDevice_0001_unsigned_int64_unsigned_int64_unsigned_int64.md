# p9fs::Plan9VirtioDevice::UnregisterDoorbell(__MIDL_IFiovDevice_0001,unsigned __int64,unsigned __int64,unsigned __int64)

- ea: `0x18002eaf0`
- end: `0x18002eb54`
- name: `?UnregisterDoorbell@Plan9VirtioDevice@p9fs@@UEAAJW4__MIDL_IFiovDevice_0001@@_K11@Z`
- size: `100`
- prototype: `int __high(enum __MIDL_IFiovDevice_0001, unsigned __int64, unsigned __int64, unsigned __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x180009fe4`
- `0x18002eaf0`
- `0x180034010`

## string_xrefs

- `0x18002eb34`: `onecore\vm\dv\storage\plan9\dll\windows\p9virtio.cpp`

## pseudocode

```c
__int64 __fastcall p9fs::Plan9VirtioDevice::UnregisterDoorbell(__int64 a1, char a2, __int64 a3, int a4)
{
  __int64 v4; // rbx
  int v5; // eax
  unsigned int v6; // ebx
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  v4 = a3;
  LOBYTE(a3) = a2;
  v5 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64, __int64))(**(_QWORD **)(*(_QWORD *)(a1 + 40) + 8LL) + 40LL))(
         *(_QWORD *)(*(_QWORD *)(a1 + 40) + 8LL),
         a1 + 24,
         a3,
         v4);
  v6 = v5;
  if ( v5 >= 0 )
    return 0;
  else
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x279,
      (unsigned int)"onecore\\vm\\dv\\storage\\plan9\\dll\\windows\\p9virtio.cpp",
      (const char *)(unsigned int)v5,
      a4);
  return v6;
}

```

## disassembly

```asm
0x18002eaf0  push    rbx
0x18002eaf2  sub     rsp, 40h
0x18002eaf6  mov     rax, [rcx+28h]
0x18002eafa  mov     rbx, r8
0x18002eafd  mov     r10, [rsp+48h+arg_20]
0x18002eb02  mov     r8b, dl
0x18002eb05  mov     [rsp+48h+var_20], r10
0x18002eb0a  lea     rdx, [rcx+18h]
0x18002eb0e  mov     qword ptr [rsp+48h+var_28], r9; int
0x18002eb13  mov     r9, rbx
0x18002eb16  mov     r11, [rax+8]
0x18002eb1a  mov     rcx, r11
0x18002eb1d  mov     rax, [r11]
0x18002eb20  mov     rax, [rax+28h]
0x18002eb24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002eb29  mov     ebx, eax
0x18002eb2b  test    eax, eax
0x18002eb2d  jns     short loc_18002EB4A
0x18002eb2f  mov     rcx, [rsp+48h]; this
0x18002eb34  lea     r8, aOnecoreVmDvSto_0; "onecore\\vm\\dv\\storage\\plan9\\dll\\w"...
0x18002eb3b  mov     r9d, eax; char *
0x18002eb3e  mov     edx, 279h; void *
0x18002eb43  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002eb48  jmp     short loc_18002EB4C
0x18002eb4a  xor     ebx, ebx
0x18002eb4c  mov     eax, ebx
0x18002eb4e  add     rsp, 40h
0x18002eb52  pop     rbx
0x18002eb53  retn
```
