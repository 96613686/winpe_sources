# WimFSFReadWimResourceSwitchStacks

- ea: `0x140022544`
- end: `0x1400225ec`
- name: `WimFSFReadWimResourceSwitchStacks`
- size: `168`
- prototype: `__int64 __fastcall(PVOID Parameter)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x14002d678`
- `0x14003d2d0`

## callees

- `0x14000d3b8`
- `0x14000fb60`
- `0x140022544`

## import_xrefs

- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x14002259d`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x14002259d`

## pseudocode

```c
__int64 __fastcall WimFSFReadWimResourceSwitchStacks(NTSTATUS *Parameter)
{
  NTSTATUS v2; // ebx

  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 15, WPP_3158cc7d99213f3216ee7f88e8d8f42f_Traceguids);
  v2 = KeExpandKernelStackAndCalloutEx(
         WimFSFReadWimResourceCallout,
         Parameter,
         0x4000u,
         0,
         *(PVOID *)(*((_QWORD *)Parameter + 3) + 1032LL));
  if ( v2 >= 0 )
    v2 = Parameter[31];
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 16, WPP_3158cc7d99213f3216ee7f88e8d8f42f_Traceguids, (unsigned int)v2);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x140022544  mov     [rsp+arg_0], rbx
0x140022549  push    rdi
0x14002254a  sub     rsp, 30h
0x14002254e  mov     rdi, rcx
0x140022551  mov     rcx, cs:WPP_GLOBAL_Control
0x140022558  mov     eax, [rcx+2Ch]
0x14002255b  test    al, 20h
0x14002255d  jz      short loc_14002257A
0x14002255f  cmp     byte ptr [rcx+29h], 4
0x140022563  jb      short loc_14002257A
0x140022565  mov     rcx, [rcx+18h]
0x140022569  lea     r8, WPP_3158cc7d99213f3216ee7f88e8d8f42f_Traceguids
0x140022570  mov     edx, 0Fh
0x140022575  call    WPP_SF_
0x14002257a  mov     rax, [rdi+18h]
0x14002257e  xor     r9d, r9d; Wait
0x140022581  mov     r8d, 4000h; Size
0x140022587  mov     rdx, rdi; Parameter
0x14002258a  mov     rcx, [rax+408h]
0x140022591  mov     [rsp+38h+Context], rcx; Context
0x140022596  lea     rcx, WimFSFReadWimResourceCallout; Callout
0x14002259d  call    cs:__imp_KeExpandKernelStackAndCalloutEx
0x1400225a4  nop     dword ptr [rax+rax+00h]
0x1400225a9  mov     ebx, eax
0x1400225ab  test    eax, eax
0x1400225ad  js      short loc_1400225B2
0x1400225af  mov     ebx, [rdi+7Ch]
0x1400225b2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400225b9  mov     eax, [rcx+2Ch]
0x1400225bc  test    al, 20h
0x1400225be  jz      short loc_1400225DE
0x1400225c0  cmp     byte ptr [rcx+29h], 4
0x1400225c4  jb      short loc_1400225DE
0x1400225c6  mov     rcx, [rcx+18h]
0x1400225ca  lea     r8, WPP_3158cc7d99213f3216ee7f88e8d8f42f_Traceguids
0x1400225d1  mov     edx, 10h
0x1400225d6  mov     r9d, ebx
0x1400225d9  call    WPP_SF_d
0x1400225de  mov     eax, ebx
0x1400225e0  mov     rbx, [rsp+38h+arg_0]
0x1400225e5  add     rsp, 30h
0x1400225e9  pop     rdi
0x1400225ea  retn
```
