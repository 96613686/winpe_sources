# p9fs::Plan9VirtioDevice::RegisterDoorbell(__MIDL_IFiovDevice_0001,unsigned __int64,unsigned __int64,unsigned __int64,void *)

- ea: `0x18002e830`
- end: `0x18002e89e`
- name: `?RegisterDoorbell@Plan9VirtioDevice@p9fs@@UEAAJW4__MIDL_IFiovDevice_0001@@_K11PEAX@Z`
- size: `110`
- prototype: `int __high(enum __MIDL_IFiovDevice_0001, unsigned __int64, unsigned __int64, unsigned __int64, void *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x180009fe4`
- `0x18002e830`
- `0x180034010`

## string_xrefs

- `0x18002e87e`: `onecore\vm\dv\storage\plan9\dll\windows\p9virtio.cpp`

## pseudocode

```c
__int64 __fastcall p9fs::Plan9VirtioDevice::RegisterDoorbell(__int64 a1, char a2, __int64 a3, int a4)
{
  __int64 v4; // rbx
  int v5; // eax
  unsigned int v6; // ebx
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  v4 = a3;
  LOBYTE(a3) = a2;
  v5 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64, __int64))(**(_QWORD **)(*(_QWORD *)(a1 + 40) + 8LL) + 32LL))(
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
      (void *)0x271,
      (unsigned int)"onecore\\vm\\dv\\storage\\plan9\\dll\\windows\\p9virtio.cpp",
      (const char *)(unsigned int)v5,
      a4);
  return v6;
}

```

## disassembly

```asm
0x18002e830  push    rbx
0x18002e832  sub     rsp, 40h
0x18002e836  mov     rax, [rcx+28h]
0x18002e83a  mov     rbx, r8
0x18002e83d  mov     r10, [rsp+48h+arg_28]
0x18002e842  mov     r8b, dl
0x18002e845  mov     [rsp+48h+var_18], r10
0x18002e84a  lea     rdx, [rcx+18h]
0x18002e84e  mov     r10, [rsp+48h+arg_20]
0x18002e853  mov     r11, [rax+8]
0x18002e857  mov     [rsp+48h+var_20], r10
0x18002e85c  mov     rcx, r11
0x18002e85f  mov     qword ptr [rsp+48h+var_28], r9; int
0x18002e864  mov     r9, rbx
0x18002e867  mov     rax, [r11]
0x18002e86a  mov     rax, [rax+20h]
0x18002e86e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e873  mov     ebx, eax
0x18002e875  test    eax, eax
0x18002e877  jns     short loc_18002E894
0x18002e879  mov     rcx, [rsp+48h]; this
0x18002e87e  lea     r8, aOnecoreVmDvSto_0; "onecore\\vm\\dv\\storage\\plan9\\dll\\w"...
0x18002e885  mov     r9d, eax; char *
0x18002e888  mov     edx, 271h; void *
0x18002e88d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002e892  jmp     short loc_18002E896
0x18002e894  xor     ebx, ebx
0x18002e896  mov     eax, ebx
0x18002e898  add     rsp, 40h
0x18002e89c  pop     rbx
0x18002e89d  retn
```
