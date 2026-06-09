# FrameBuffer::CopyTo(ByteBuffer *,ulong)

- ea: `0x18000d6f8`
- end: `0x18000d7b1`
- name: `?CopyTo@FrameBuffer@@QEAAJPEAVByteBuffer@@K@Z`
- size: `185`
- prototype: `__int64 __fastcall(FrameBuffer *this, struct ByteBuffer *, int)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x18000c030`
- `0x18000c19c`
- `0x18000c300`

## callees

- `0x18000d6f8`
- `0x18000d890`
- `0x18000d954`
- `0x18000dc00`

## pseudocode

```c
__int64 __fastcall FrameBuffer::CopyTo(FrameBuffer *this, struct ByteBuffer *a2, int a3)
{
  __int64 v3; // r10
  unsigned int v6; // edx
  unsigned int v7; // edi
  unsigned int v8; // eax
  FrameObfuscator *v9; // rcx
  unsigned __int8 *v10; // rdx
  int v11; // ebp
  __int64 v12; // rbx

  v3 = *(_QWORD *)this;
  v6 = *(_DWORD *)((char *)this + 10) - *((_DWORD *)this + 12);
  v7 = *(_DWORD *)(*(_QWORD *)this + 12LL) - *(_DWORD *)(*(_QWORD *)this + 16LL);
  v8 = v7;
  if ( v7 >= v6 )
    v8 = *(_DWORD *)((char *)this + 10) - *((_DWORD *)this + 12);
  if ( v8 >= *((_DWORD *)a2 + 2) - *((_DWORD *)a2 + 3) )
  {
    v7 = *((_DWORD *)a2 + 2) - *((_DWORD *)a2 + 3);
  }
  else if ( v7 >= v6 )
  {
    v7 = *(_DWORD *)((char *)this + 10) - *((_DWORD *)this + 12);
  }
  v9 = (FrameBuffer *)((char *)this + 20);
  v10 = (unsigned __int8 *)(*(_QWORD *)v3 + *(unsigned int *)(v3 + 16));
  if ( !a3 )
  {
    FrameObfuscator::ProcessMask(v9, v10, v7);
    v11 = 0;
LABEL_12:
    if ( v7 )
    {
      v12 = *(_QWORD *)this;
      memcpy_0(
        (void *)(*(_QWORD *)a2 + *((unsigned int *)a2 + 3)),
        (const void *)(**(_QWORD **)this + *(unsigned int *)(*(_QWORD *)this + 16LL)),
        v7);
      *(_DWORD *)(v12 + 16) += v7;
      *((_DWORD *)a2 + 3) += v7;
    }
    *((_QWORD *)this + 6) += v7;
    return (unsigned int)v11;
  }
  if ( (a3 & 1) == 0 )
    return (unsigned int)-2147467259;
  v11 = FrameObfuscator::ProcessMaskAndUtf8(v9, v10, v7, (a3 & 2) != 0);
  if ( v11 >= 0 )
    goto LABEL_12;
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18000d6f8  push    rbx
0x18000d6fa  push    rbp
0x18000d6fb  push    rsi
0x18000d6fc  push    rdi
0x18000d6fd  push    r14
0x18000d6ff  sub     rsp, 20h
0x18000d703  mov     r10, [rcx]
0x18000d706  mov     r14, rdx
0x18000d709  mov     edx, [rcx+0Ah]
0x18000d70c  mov     rsi, rcx
0x18000d70f  sub     edx, [rcx+30h]
0x18000d712  mov     edi, [r10+0Ch]
0x18000d716  sub     edi, [r10+10h]
0x18000d71a  mov     ecx, [r14+8]
0x18000d71e  mov     eax, edi
0x18000d720  sub     ecx, [r14+0Ch]
0x18000d724  cmp     edi, edx
0x18000d726  cmovnb  eax, edx
0x18000d729  cmp     eax, ecx
0x18000d72b  jnb     short loc_18000D734
0x18000d72d  cmp     edi, edx
0x18000d72f  cmovnb  edi, edx
0x18000d732  jmp     short loc_18000D736
0x18000d734  mov     edi, ecx
0x18000d736  mov     edx, [r10+10h]
0x18000d73a  lea     rcx, [rsi+14h]; this
0x18000d73e  add     rdx, [r10]; unsigned __int8 *
0x18000d741  test    r8d, r8d
0x18000d744  jnz     short loc_18000D752
0x18000d746  mov     r8d, edi; unsigned int
0x18000d749  call    ?ProcessMask@FrameObfuscator@@AEAAXPEAEK@Z; FrameObfuscator::ProcessMask(uchar *,ulong)
0x18000d74e  xor     ebp, ebp
0x18000d750  jmp     short loc_18000D774
0x18000d752  test    r8b, 1
0x18000d756  jz      short loc_18000D79F
0x18000d758  test    r8b, 2
0x18000d75c  mov     r9d, 0
0x18000d762  mov     r8d, edi; unsigned int
0x18000d765  setnbe  r9b; int
0x18000d769  call    ?ProcessMaskAndUtf8@FrameObfuscator@@AEAAJPEAEKH@Z; FrameObfuscator::ProcessMaskAndUtf8(uchar *,ulong,int)
0x18000d76e  mov     ebp, eax
0x18000d770  test    eax, eax
0x18000d772  js      short loc_18000D7A4
0x18000d774  test    edi, edi
0x18000d776  jz      short loc_18000D797
0x18000d778  mov     rbx, [rsi]
0x18000d77b  mov     ecx, [r14+0Ch]
0x18000d77f  add     rcx, [r14]; void *
0x18000d782  mov     r8d, edi; Size
0x18000d785  mov     edx, [rbx+10h]
0x18000d788  add     rdx, [rbx]; Src
0x18000d78b  call    memcpy_0
0x18000d790  add     [rbx+10h], edi
0x18000d793  add     [r14+0Ch], edi
0x18000d797  mov     eax, edi
0x18000d799  add     [rsi+30h], rax
0x18000d79d  jmp     short loc_18000D7A4
0x18000d79f  mov     ebp, 80004005h
0x18000d7a4  mov     eax, ebp
0x18000d7a6  add     rsp, 20h
0x18000d7aa  pop     r14
0x18000d7ac  pop     rdi
0x18000d7ad  pop     rsi
0x18000d7ae  pop     rbp
0x18000d7af  pop     rbx
0x18000d7b0  retn
```
