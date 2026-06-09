# InpProcessCompletedDeferredPackets

- ea: `0x1400089a8`
- end: `0x140008aba`
- name: `InpProcessCompletedDeferredPackets`
- size: `274`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140007f9c`
- `0x140008338`

## callees

- `0x1400049a0`
- `0x140005750`
- `0x140005ae0`
- `0x140005ca0`
- `0x1400089a8`
- `0x140008d20`

## pseudocode

```c
void __fastcall InpProcessCompletedDeferredPackets(__int64 a1, char a2)
{
  __int64 v2; // r14
  _QWORD *v4; // rbx
  _QWORD *v6; // r15
  __int64 v7; // rdi
  _QWORD *v8; // rax
  _QWORD *v9; // rcx
  char v10; // bp
  __int64 v11; // rcx
  unsigned int v12; // r9d
  __int64 v13; // r8
  unsigned int v14; // ebx

  v2 = a1 + 1104;
  v4 = *(_QWORD **)(a1 + 1104);
  if ( v4 != (_QWORD *)(a1 + 1104) )
  {
    do
    {
      v6 = (_QWORD *)*v4;
      v7 = (__int64)(v4 - 3);
      if ( (*(_BYTE *)(v4 - 1) & 0x20) != 0 )
      {
        if ( *(_QWORD *)(v7 + 48) )
          InpUnmapPacketMdl(a1, v4 - 3);
        v8 = (_QWORD *)*v4;
        if ( *(_QWORD **)(*v4 + 8LL) != v4 || (v9 = (_QWORD *)v4[1], (_QWORD *)*v9 != v4) )
          __fastfail(3u);
        *v9 = v8;
        v8[1] = v9;
        --*(_DWORD *)(a1 + 1152);
        --*(_DWORD *)(a1 + 1156);
        v10 = *(_BYTE *)(v7 + 17);
        if ( !a2
          || (*(_BYTE *)(v7 + 16) & 4) == 0
          || (v11 = *(unsigned int *)(v7 + 64) + 160LL,
              v12 = *(_DWORD *)(v7 + 80),
              v13 = v7 + *(unsigned int *)(v7 + 84),
              *(_QWORD *)(v7 + 64) = *(_QWORD *)(v7 + 168),
              *(_QWORD *)(v7 + 56) = InpCompletionSent,
              (unsigned __int8)OutSendCompletionAtDpcLevel(a1, (__int64)v4, (const void *)(v11 + v13), v12, 0)) )
        {
          v14 = *(_DWORD *)(v7 + 8) - *(_DWORD *)(v7 + 12);
          InpFreePacket(a1, v7);
          InpPacketFreedLocked(a1, v14);
        }
        InpPacketCompletedLocked(a1, v10);
      }
      v4 = v6;
    }
    while ( v6 != (_QWORD *)v2 );
  }
}

```

## disassembly

```asm
0x1400089a8  push    rbx
0x1400089aa  push    rbp
0x1400089ab  push    rsi
0x1400089ac  push    rdi
0x1400089ad  push    r12
0x1400089af  push    r14
0x1400089b1  push    r15
0x1400089b3  sub     rsp, 30h
0x1400089b7  lea     r14, [rcx+450h]
0x1400089be  mov     r12b, dl
0x1400089c1  mov     rbx, [r14]
0x1400089c4  mov     rsi, rcx
0x1400089c7  cmp     rbx, r14
0x1400089ca  jz      loc_140008AA3
0x1400089d0  mov     r15, [rbx]
0x1400089d3  lea     rdi, [rbx-18h]
0x1400089d7  test    byte ptr [rdi+10h], 20h
0x1400089db  jz      loc_140008A97
0x1400089e1  cmp     qword ptr [rdi+30h], 0
0x1400089e6  jz      short loc_1400089F3
0x1400089e8  mov     rdx, rdi
0x1400089eb  mov     rcx, rsi
0x1400089ee  call    InpUnmapPacketMdl
0x1400089f3  mov     rax, [rbx]
0x1400089f6  cmp     [rax+8], rbx
0x1400089fa  jnz     loc_140008AB3
0x140008a00  mov     rcx, [rbx+8]
0x140008a04  cmp     [rcx], rbx
0x140008a07  jnz     loc_140008AB3
0x140008a0d  mov     [rcx], rax
0x140008a10  mov     [rax+8], rcx
0x140008a14  dec     dword ptr [rsi+480h]
0x140008a1a  dec     dword ptr [rsi+484h]
0x140008a20  mov     bpl, [rdi+11h]
0x140008a24  test    r12b, r12b
0x140008a27  jz      short loc_140008A71
0x140008a29  test    byte ptr [rdi+10h], 4
0x140008a2d  jz      short loc_140008A71
0x140008a2f  mov     ecx, [rdi+40h]
0x140008a32  mov     rdx, rbx
0x140008a35  mov     rax, [rdi+0A8h]
0x140008a3c  add     rcx, 0A0h
0x140008a43  mov     r8d, [rdi+54h]
0x140008a47  mov     r9d, [rdi+50h]
0x140008a4b  add     r8, rdi
0x140008a4e  mov     [rdi+40h], rax
0x140008a52  add     r8, rcx
0x140008a55  lea     rax, InpCompletionSent
0x140008a5c  mov     [rsp+68h+var_48], 0
0x140008a61  mov     rcx, rsi
0x140008a64  mov     [rdi+38h], rax
0x140008a68  call    OutSendCompletionAtDpcLevel
0x140008a6d  test    al, al
0x140008a6f  jz      short loc_140008A8C
0x140008a71  mov     ebx, [rdi+8]
0x140008a74  mov     rdx, rdi
0x140008a77  sub     ebx, [rdi+0Ch]
0x140008a7a  mov     rcx, rsi
0x140008a7d  call    InpFreePacket
0x140008a82  mov     edx, ebx
0x140008a84  mov     rcx, rsi
0x140008a87  call    InpPacketFreedLocked
0x140008a8c  mov     dl, bpl
0x140008a8f  mov     rcx, rsi
0x140008a92  call    InpPacketCompletedLocked
0x140008a97  mov     rbx, r15
0x140008a9a  cmp     r15, r14
0x140008a9d  jnz     loc_1400089D0
0x140008aa3  add     rsp, 30h
0x140008aa7  pop     r15
0x140008aa9  pop     r14
0x140008aab  pop     r12
0x140008aad  pop     rdi
0x140008aae  pop     rsi
0x140008aaf  pop     rbp
0x140008ab0  pop     rbx
0x140008ab1  retn
0x140008ab3  mov     ecx, 3
0x140008ab8  int     29h; Win8: RtlFailFast(ecx)
```
