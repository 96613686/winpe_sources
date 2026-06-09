# FrameRenderCancelCallback

- ea: `0x14001c160`
- end: `0x14001c1c7`
- name: `FrameRenderCancelCallback`
- size: `103`
- prototype: `void __stdcall(PKSSTREAM_POINTER StreamPointer)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140004bac`
- `0x14001c160`

## import_xrefs

- `ks!KsStreamPointerDelete` at `0x14001c1af`
- `ks!KsStreamPointerDelete` at `0x14001c1af`

## pseudocode

```c
void __fastcall FrameRenderCancelCallback(PKSSTREAM_POINTER StreamPointer)
{
  __int64 v2; // rdi

  v2 = *(_QWORD *)StreamPointer->Context;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 23, WPP_9e091edf6a993739dccdf8ddcdcaa537_Traceguids);
  *(_QWORD *)(v2 + 176) = 0;
  KsStreamPointerDelete(StreamPointer);
}

```

## disassembly

```asm
0x14001c160  mov     [rsp+arg_0], rbx
0x14001c165  push    rdi
0x14001c166  sub     rsp, 20h
0x14001c16a  mov     rax, [rcx]
0x14001c16d  mov     rbx, rcx
0x14001c170  mov     rdi, [rax]
0x14001c173  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c17a  lea     rax, WPP_GLOBAL_Control
0x14001c181  cmp     rcx, rax
0x14001c184  jz      short loc_14001C1A1
0x14001c186  cmp     byte ptr [rcx+29h], 4
0x14001c18a  jb      short loc_14001C1A1
0x14001c18c  mov     rcx, [rcx+18h]
0x14001c190  lea     r8, WPP_9e091edf6a993739dccdf8ddcdcaa537_Traceguids
0x14001c197  mov     edx, 17h
0x14001c19c  call    WPP_SF_
0x14001c1a1  mov     rcx, rbx; StreamPointer
0x14001c1a4  mov     qword ptr [rdi+0B0h], 0
0x14001c1af  call    cs:__imp_KsStreamPointerDelete
0x14001c1b6  nop     dword ptr [rax+rax+00h]
0x14001c1bb  mov     rbx, [rsp+28h+arg_0]
0x14001c1c0  add     rsp, 20h
0x14001c1c4  pop     rdi
0x14001c1c5  retn
```
