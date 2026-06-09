# SqosPreClose

- ea: `0x140014740`
- end: `0x1400147d8`
- name: `SqosPreClose`
- size: `152`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x140008250`
- `0x140008368`
- `0x140014740`

## import_xrefs

- `FLTMGR!FltDeleteStreamHandleContext` at `0x140014772`
- `FLTMGR!FltDeleteStreamHandleContext` at `0x140014772`

## pseudocode

```c
__int64 __fastcall SqosPreClose(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v4; // r8

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 31, a3, *(_QWORD *)(a2 + 32));
  }
  FltDeleteStreamHandleContext(*(PFLT_INSTANCE *)(a2 + 24), *(PFILE_OBJECT *)(a2 + 32), 0);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 32, v4, 1);
  }
  return 1;
}

```

## disassembly

```asm
0x140014740  mov     [rsp+arg_0], rbx
0x140014745  push    rdi
0x140014746  sub     rsp, 20h
0x14001474a  mov     rbx, rdx
0x14001474d  mov     rcx, cs:WPP_GLOBAL_Control
0x140014754  lea     rdi, WPP_GLOBAL_Control
0x14001475b  cmp     rcx, rdi
0x14001475e  jz      short loc_140014767
0x140014760  mov     eax, [rcx+2Ch]
0x140014763  test    al, 2
0x140014765  jnz     short loc_1400147A2
0x140014767  mov     rdx, [rbx+20h]; FileObject
0x14001476b  xor     r8d, r8d; OldContext
0x14001476e  mov     rcx, [rbx+18h]; Instance
0x140014772  call    cs:__imp_FltDeleteStreamHandleContext
0x140014779  nop     dword ptr [rax+rax+00h]
0x14001477e  mov     rcx, cs:WPP_GLOBAL_Control
0x140014785  cmp     rcx, rdi
0x140014788  jz      short loc_140014791
0x14001478a  mov     eax, [rcx+2Ch]
0x14001478d  test    al, 2
0x14001478f  jnz     short loc_1400147BC
0x140014791  mov     rbx, [rsp+28h+arg_0]
0x140014796  mov     eax, 1
0x14001479b  add     rsp, 20h
0x14001479f  pop     rdi
0x1400147a0  retn
0x1400147a2  cmp     byte ptr [rcx+29h], 5
0x1400147a6  jb      short loc_140014767
0x1400147a8  mov     r9, [rbx+20h]
0x1400147ac  mov     edx, 1Fh
0x1400147b1  mov     rcx, [rcx+18h]
0x1400147b5  call    WPP_SF_q
0x1400147ba  jmp     short loc_140014767
0x1400147bc  cmp     byte ptr [rcx+29h], 5
0x1400147c0  jb      short loc_140014791
0x1400147c2  mov     rcx, [rcx+18h]
0x1400147c6  mov     edx, 20h ; ' '
0x1400147cb  mov     r9d, 1
0x1400147d1  call    WPP_SF_D
0x1400147d6  jmp     short loc_140014791
```
