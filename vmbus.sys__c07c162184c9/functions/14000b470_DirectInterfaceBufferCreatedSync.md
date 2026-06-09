# DirectInterfaceBufferCreatedSync

- ea: `0x14000b470`
- end: `0x14000b4ea`
- name: `DirectInterfaceBufferCreatedSync`
- size: `122`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x14000b470`
- `0x14000be30`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x14000b4cd`
- `ntoskrnl!KeSetEvent` at `0x14000b4cd`

## pseudocode

```c
LONG __fastcall DirectInterfaceBufferCreatedSync(int a1, __int64 a2, __int64 a3)
{
  int v4; // ebx

  v4 = a2;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_qdD(WPP_GLOBAL_Control->AttachedDevice, a2, a3, a3, a1, a2);
  }
  if ( a1 < 0 )
    v4 = 0;
  *(_DWORD *)(a3 + 4) = v4;
  return KeSetEvent(*(PRKEVENT *)(a3 + 24), 0, 0);
}

```

## disassembly

```asm
0x14000b470  mov     [rsp+arg_0], rbx
0x14000b475  mov     [rsp+arg_8], rsi
0x14000b47a  push    rdi
0x14000b47b  sub     rsp, 30h
0x14000b47f  mov     rdi, r8
0x14000b482  mov     ebx, edx
0x14000b484  mov     esi, ecx
0x14000b486  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b48d  lea     rax, WPP_GLOBAL_Control
0x14000b494  cmp     rcx, rax
0x14000b497  jz      short loc_14000B4BA
0x14000b499  mov     eax, [rcx+2Ch]
0x14000b49c  test    al, 10h
0x14000b49e  jz      short loc_14000B4BA
0x14000b4a0  cmp     byte ptr [rcx+29h], 4
0x14000b4a4  jb      short loc_14000B4BA
0x14000b4a6  mov     rcx, [rcx+18h]
0x14000b4aa  mov     r9, r8
0x14000b4ad  mov     [rsp+38h+var_10], edx
0x14000b4b1  mov     [rsp+38h+var_18], esi
0x14000b4b5  call    WPP_SF_qdD
0x14000b4ba  xor     eax, eax
0x14000b4bc  test    esi, esi
0x14000b4be  cmovs   ebx, eax
0x14000b4c1  xor     r8d, r8d; Wait
0x14000b4c4  mov     [rdi+4], ebx
0x14000b4c7  xor     edx, edx; Increment
0x14000b4c9  mov     rcx, [rdi+18h]; Event
0x14000b4cd  call    cs:__imp_KeSetEvent
0x14000b4d4  nop     dword ptr [rax+rax+00h]
0x14000b4d9  mov     rbx, [rsp+38h+arg_0]
0x14000b4de  mov     rsi, [rsp+38h+arg_8]
0x14000b4e3  add     rsp, 30h
0x14000b4e7  pop     rdi
0x14000b4e8  retn
```
