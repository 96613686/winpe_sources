# CTELogEvent

- ea: `0x14000b010`
- end: `0x14000b172`
- name: `CTELogEvent`
- size: `354`
- prototype: `__int64 __usercall@<rax>(PVOID IoObject@<rcx>, __int64, size_t Size, void *Src)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140005600`
- `0x14000b010`

## import_xrefs

- `ntoskrnl!IoAllocateErrorLogEntry` at `0x14000b0bc`
- `ntoskrnl!IoAllocateErrorLogEntry` at `0x14000b0bc`
- `ntoskrnl!IoWriteErrorLogEntry` at `0x14000b153`
- `ntoskrnl!IoWriteErrorLogEntry` at `0x14000b153`

## pseudocode

```c
__int64 __fastcall CTELogEvent(PVOID IoObject, int a2, int a3, unsigned __int16 a4, __int64 a5, size_t Size, void *Src)
{
  unsigned int v8; // r11d
  unsigned __int16 i; // r10
  int v13; // edx
  _WORD *j; // rcx
  unsigned int v16; // edi
  char v17; // dl
  unsigned __int16 *ErrorLogEntry; // rax
  unsigned __int16 *v19; // rbx
  unsigned __int16 v20; // cx
  _WORD *k; // rdx
  __int16 *v22; // r8
  __int16 v23; // ax

  v8 = 0;
  for ( i = 0; i < a4; ++i )
  {
    v13 = 2;
    for ( j = *(_WORD **)(a5 + 8LL * i); *j; ++j )
      v13 += 2;
    if ( v13 + v8 < v8 )
      return 3221225990LL;
    v8 += v13;
  }
  v16 = Size;
  if ( (Size & 3) != 0 )
    v16 = Size - (Size & 3) + 4;
  if ( v8 + v16 > 0xC4 )
    return 3221225507LL;
  v17 = 44;
  if ( v8 + v16 <= 4 )
    v17 = 48;
  ErrorLogEntry = (unsigned __int16 *)IoAllocateErrorLogEntry(
                                        IoObject,
                                        (unsigned __int8)v8 + (unsigned __int8)v16 + v17);
  v19 = ErrorLogEntry;
  if ( !ErrorLogEntry )
    return 3221225626LL;
  *((_DWORD *)ErrorLogEntry + 4) = a3;
  *((_DWORD *)ErrorLogEntry + 3) = a2;
  ErrorLogEntry[2] = a4;
  ErrorLogEntry[1] = v16;
  ErrorLogEntry[3] = v16 + 44;
  if ( (_DWORD)Size )
    memmove(ErrorLogEntry + 20, Src, (unsigned int)Size);
  v20 = 0;
  for ( k = (unsigned __int16 *)((char *)v19 + v16 + v19[3]); v20 < a4; ++v20 )
  {
    v22 = *(__int16 **)(a5 + 8LL * v20);
    do
    {
      v23 = *v22++;
      *k++ = v23;
    }
    while ( v23 );
  }
  IoWriteErrorLogEntry(v19);
  return 0;
}

```

## disassembly

```asm
0x14000b010  push    rbx
0x14000b012  push    rbp
0x14000b013  push    rdi
0x14000b014  push    r12
0x14000b016  push    r13
0x14000b018  push    r14
0x14000b01a  push    r15
0x14000b01c  sub     rsp, 20h
0x14000b020  mov     r14, [rsp+58h+arg_20]
0x14000b028  xor     r13d, r13d
0x14000b02b  mov     r15d, r8d
0x14000b02e  mov     r11d, r13d
0x14000b031  mov     r10d, r13d
0x14000b034  movzx   ebp, r9w
0x14000b038  mov     r12d, edx
0x14000b03b  mov     r8, rcx
0x14000b03e  cmp     r10w, bp
0x14000b042  jnb     short loc_14000B07C
0x14000b044  movzx   eax, r10w
0x14000b048  mov     edx, 2
0x14000b04d  mov     rcx, [r14+rax*8]
0x14000b051  jmp     short loc_14000B05A
0x14000b053  lea     rcx, [rcx+2]
0x14000b057  add     edx, 2
0x14000b05a  cmp     [rcx], r13w
0x14000b05e  jnz     short loc_14000B053
0x14000b060  lea     eax, [rdx+r11]
0x14000b064  cmp     eax, r11d
0x14000b067  jb      short loc_14000B072
0x14000b069  mov     r11d, eax
0x14000b06c  inc     r10w
0x14000b070  jmp     short loc_14000B03E
0x14000b072  mov     eax, 0C0000206h
0x14000b077  jmp     loc_14000B161
0x14000b07c  mov     eax, dword ptr [rsp+58h+Size]
0x14000b083  mov     edi, dword ptr [rsp+58h+Size]
0x14000b08a  and     eax, 3
0x14000b08d  jz      short loc_14000B094
0x14000b08f  sub     edi, eax
0x14000b091  add     edi, 4
0x14000b094  lea     eax, [r11+rdi]
0x14000b098  cmp     eax, 0C4h
0x14000b09d  jbe     short loc_14000B0A9
0x14000b09f  mov     eax, 0C0000023h
0x14000b0a4  jmp     loc_14000B161
0x14000b0a9  mov     edx, 2Ch ; ','
0x14000b0ae  cmp     eax, 4
0x14000b0b1  lea     ecx, [rdx+4]
0x14000b0b4  cmovbe  edx, ecx
0x14000b0b7  mov     rcx, r8; IoObject
0x14000b0ba  add     dl, al; EntrySize
0x14000b0bc  call    cs:__imp_IoAllocateErrorLogEntry
0x14000b0c3  nop     dword ptr [rax+rax+00h]
0x14000b0c8  mov     rbx, rax
0x14000b0cb  test    rax, rax
0x14000b0ce  jnz     short loc_14000B0DA
0x14000b0d0  mov     eax, 0C000009Ah
0x14000b0d5  jmp     loc_14000B161
0x14000b0da  mov     [rax+10h], r15d
0x14000b0de  mov     [rax+0Ch], r12d
0x14000b0e2  mov     [rax+4], bp
0x14000b0e6  mov     eax, 2Ch ; ','
0x14000b0eb  add     eax, edi
0x14000b0ed  mov     [rbx+2], di
0x14000b0f1  mov     [rbx+6], ax
0x14000b0f5  cmp     dword ptr [rsp+58h+Size], r13d
0x14000b0fd  jbe     short loc_14000B118
0x14000b0ff  mov     r8d, dword ptr [rsp+58h+Size]; Size
0x14000b107  lea     rcx, [rbx+28h]; void *
0x14000b10b  mov     rdx, [rsp+58h+Src]; Src
0x14000b113  call    memmove
0x14000b118  movzx   edx, word ptr [rbx+6]
0x14000b11c  mov     ecx, r13d
0x14000b11f  mov     eax, edi
0x14000b121  add     rax, rbx
0x14000b124  add     rdx, rax
0x14000b127  cmp     r13w, bp
0x14000b12b  jnb     short loc_14000B150
0x14000b12d  movzx   eax, cx
0x14000b130  mov     r8, [r14+rax*8]
0x14000b134  movzx   eax, word ptr [r8]
0x14000b138  lea     r8, [r8+2]
0x14000b13c  mov     [rdx], ax
0x14000b13f  add     rdx, 2
0x14000b143  test    ax, ax
0x14000b146  jnz     short loc_14000B134
0x14000b148  inc     cx
0x14000b14b  cmp     cx, bp
0x14000b14e  jb      short loc_14000B12D
0x14000b150  mov     rcx, rbx; ElEntry
0x14000b153  call    cs:__imp_IoWriteErrorLogEntry
0x14000b15a  nop     dword ptr [rax+rax+00h]
0x14000b15f  xor     eax, eax
0x14000b161  add     rsp, 20h
0x14000b165  pop     r15
0x14000b167  pop     r14
0x14000b169  pop     r13
0x14000b16b  pop     r12
0x14000b16d  pop     rdi
0x14000b16e  pop     rbp
0x14000b16f  pop     rbx
0x14000b170  retn
```
