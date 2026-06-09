# CTsUrbResult::AllocateUrb(ulong)

- ea: `0x14000491c`
- end: `0x1400049a6`
- name: `?AllocateUrb@CTsUrbResult@@IEAAPEAU_URB@@K@Z`
- size: `138`
- prototype: `struct _URB *__fastcall(CTsUrbResult *__hidden this, unsigned int)`
- caller_count: `14`
- callee_count: `2`
- tags: ``

## callers

- `0x140004df0`
- `0x140004ed0`
- `0x140004fb0`
- `0x1400050c0`
- `0x140005170`
- `0x140005270`
- `0x140005370`
- `0x1400053f0`
- `0x1400054a0`
- `0x140005560`
- `0x1400056f0`
- `0x1400057d0`
- `0x140005880`
- `0x140005b90`

## callees

- `0x140001ac0`
- `0x14000491c`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140004982`
- `ntoskrnl!ExAllocatePool2` at `0x140004982`

## pseudocode

```c
struct _URB *__fastcall CTsUrbResult::AllocateUrb(CTsUrbResult *this, unsigned int a2)
{
  struct _URB *result; // rax
  __int64 v3; // rbx

  result = 0;
  v3 = a2;
  if ( a2 <= 0xFFFF )
  {
    if ( a2 <= 0x698 )
    {
      result = (struct _URB *)((char *)this + 8);
LABEL_8:
      *((_QWORD *)this + 212) = result;
      return result;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_d(
        (__int64)WPP_GLOBAL_Control->AttachedDevice,
        0xAu,
        (__int64)&WPP_33b5c1abd2bc3b5ab5f1e33a32ecfbc2_Traceguids,
        a2);
    result = (struct _URB *)ExAllocatePool2(64, v3, 1179997012);
    if ( result )
      goto LABEL_8;
  }
  return result;
}

```

## disassembly

```asm
0x14000491c  mov     [rsp+arg_0], rbx
0x140004921  push    rdi
0x140004922  sub     rsp, 20h
0x140004926  xor     eax, eax
0x140004928  mov     ebx, edx
0x14000492a  mov     rdi, rcx
0x14000492d  cmp     edx, 0FFFFh
0x140004933  ja      short loc_14000499A
0x140004935  cmp     ebx, 698h
0x14000493b  ja      short loc_140004943
0x14000493d  lea     rax, [rcx+8]
0x140004941  jmp     short loc_140004993
0x140004943  mov     rcx, cs:WPP_GLOBAL_Control
0x14000494a  lea     rax, WPP_GLOBAL_Control
0x140004951  cmp     rcx, rax
0x140004954  jz      short loc_140004974
0x140004956  cmp     byte ptr [rcx+29h], 2
0x14000495a  jb      short loc_140004974
0x14000495c  mov     rcx, [rcx+18h]
0x140004960  lea     r8, WPP_33b5c1abd2bc3b5ab5f1e33a32ecfbc2_Traceguids
0x140004967  mov     edx, 0Ah
0x14000496c  mov     r9d, ebx
0x14000496f  call    WPP_SF_d
0x140004974  mov     rdx, rbx
0x140004977  mov     ecx, 40h ; '@'
0x14000497c  mov     r8d, 46555354h
0x140004982  call    cs:__imp_ExAllocatePool2
0x140004989  nop     dword ptr [rax+rax+00h]
0x14000498e  test    rax, rax
0x140004991  jz      short loc_14000499A
0x140004993  mov     [rdi+6A0h], rax
0x14000499a  mov     rbx, [rsp+28h+arg_0]
0x14000499f  add     rsp, 20h
0x1400049a3  pop     rdi
0x1400049a4  retn
```
