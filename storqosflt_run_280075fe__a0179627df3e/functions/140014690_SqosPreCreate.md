# SqosPreCreate

- ea: `0x140014690`
- end: `0x140014735`
- name: `SqosPreCreate`
- size: `165`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x140003460`
- `0x140008250`
- `0x140008368`
- `0x140014690`

## pseudocode

```c
__int64 __fastcall SqosPreCreate(__int64 a1, __int64 a2, _QWORD *a3)
{
  unsigned int v5; // edi
  __int64 v6; // r8
  __int64 v8; // [rsp+68h] [rbp+20h] BYREF

  v8 = 0;
  v5 = 1;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 26, a3, *(_QWORD *)(a2 + 32));
  }
  if ( (int)SqospAllocateStreamHandleContext(a2, &v8) >= 0 )
  {
    v5 = 0;
    *a3 = v8;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 27, v6, v5);
  }
  return v5;
}

```

## disassembly

```asm
0x140014690  push    rbx
0x140014692  push    rbp
0x140014693  push    rsi
0x140014694  push    rdi
0x140014695  sub     rsp, 28h
0x140014699  mov     rsi, r8
0x14001469c  mov     [rsp+48h+arg_18], 0
0x1400146a5  mov     rbx, rdx
0x1400146a8  mov     edi, 1
0x1400146ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1400146b4  lea     rbp, WPP_GLOBAL_Control
0x1400146bb  cmp     rcx, rbp
0x1400146be  jz      short loc_1400146C7
0x1400146c0  mov     eax, [rcx+2Ch]
0x1400146c3  test    al, 2
0x1400146c5  jnz     short loc_140014702
0x1400146c7  lea     rdx, [rsp+48h+arg_18]
0x1400146cc  mov     rcx, rbx
0x1400146cf  call    SqospAllocateStreamHandleContext
0x1400146d4  test    eax, eax
0x1400146d6  js      short loc_1400146E2
0x1400146d8  mov     rax, [rsp+48h+arg_18]
0x1400146dd  xor     edi, edi
0x1400146df  mov     [rsi], rax
0x1400146e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400146e9  cmp     rcx, rbp
0x1400146ec  jz      short loc_1400146F6
0x1400146ee  mov     edx, [rcx+2Ch]
0x1400146f1  test    dl, 2
0x1400146f4  jnz     short loc_14001471C
0x1400146f6  mov     eax, edi
0x1400146f8  add     rsp, 28h
0x1400146fc  pop     rdi
0x1400146fd  pop     rsi
0x1400146fe  pop     rbp
0x1400146ff  pop     rbx
0x140014700  retn
0x140014702  cmp     byte ptr [rcx+29h], 5
0x140014706  jb      short loc_1400146C7
0x140014708  mov     r9, [rbx+20h]
0x14001470c  mov     edx, 1Ah
0x140014711  mov     rcx, [rcx+18h]
0x140014715  call    WPP_SF_q
0x14001471a  jmp     short loc_1400146C7
0x14001471c  cmp     byte ptr [rcx+29h], 5
0x140014720  jb      short loc_1400146F6
0x140014722  mov     rcx, [rcx+18h]
0x140014726  mov     edx, 1Bh
0x14001472b  mov     r9d, edi
0x14001472e  call    WPP_SF_D
0x140014733  jmp     short loc_1400146F6
```
