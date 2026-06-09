# FileProvCompressWorkItem

- ea: `0x14003ac70`
- end: `0x14003add5`
- name: `FileProvCompressWorkItem`
- size: `357`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x14003a6a8`

## callees

- `0x140006620`
- `0x14000c888`
- `0x14000c8a0`
- `0x1400116c0`
- `0x14003ac70`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x14003acf6`
- `ntoskrnl!KeSetEvent` at `0x14003acf6`
- `ntoskrnl!RtlCompressBuffer` at `0x14003acd8`
- `ntoskrnl!RtlCompressBuffer` at `0x14003acd8`

## pseudocode

```c
LONG __fastcall FileProvCompressWorkItem(__int64 a1)
{
  int v1; // eax
  _DWORD *v3; // rdi
  NTSTATUS v4; // eax
  void *v6; // rcx
  int v7; // edi
  unsigned int v8; // ecx

  v1 = *(_DWORD *)(a1 + 32);
  *(_DWORD *)(a1 + 128) = 0;
  if ( (v1 & 0xFFFFFFFC) != 0 || v1 == 1 )
  {
    v6 = *(void **)(a1 + 72);
    if ( v1 == 1 )
    {
      *(_QWORD *)(*(_QWORD *)(a1 + 120) + 17336LL) = v6;
      *(_DWORD *)(*(_QWORD *)(a1 + 120) + 17344LL) = 0;
      v7 = LZX_Encode(*(_QWORD *)(a1 + 120), *(_QWORD *)(a1 + 64), *(unsigned int *)(a1 + 88), a1 + 92);
      LZX_EncodeFlush(*(_QWORD *)(a1 + 120));
      LZX_EncodeNewGroup(*(_QWORD *)(a1 + 120));
      if ( v7 || (v8 = *(_DWORD *)(*(_QWORD *)(a1 + 120) + 17344LL), v8 >= *(_DWORD *)(a1 + 88)) )
      {
        memmove(*(void **)(a1 + 72), *(const void **)(a1 + 64), *(unsigned int *)(a1 + 88));
        v8 = *(_DWORD *)(a1 + 88);
      }
      *(_DWORD *)(a1 + 92) = v8;
    }
    else
    {
      memmove(v6, *(const void **)(a1 + 64), *(unsigned int *)(a1 + 88));
      *(_DWORD *)(a1 + 92) = *(_DWORD *)(a1 + 88);
    }
  }
  else
  {
    v3 = (_DWORD *)(a1 + 92);
    v4 = RtlCompressBuffer(
           FileProvXPressAlgorithm,
           *(PUCHAR *)(a1 + 64),
           *(_DWORD *)(a1 + 88),
           *(PUCHAR *)(a1 + 72),
           *(_DWORD *)(a1 + 88) - 1,
           **(_DWORD **)(a1 + 40),
           (PULONG)(a1 + 92),
           *(PVOID *)(a1 + 80));
    if ( v4 == 279 )
    {
      *v3 = 0;
    }
    else if ( v4 == -1073741789 )
    {
      memmove(*(void **)(a1 + 72), *(const void **)(a1 + 64), *(unsigned int *)(a1 + 88));
      *v3 = *(_DWORD *)(a1 + 88);
    }
    else if ( v4 < 0 )
    {
      *(_DWORD *)(a1 + 128) = v4;
    }
  }
  return KeSetEvent((PRKEVENT)(a1 + 96), 0, 0);
}

```

## disassembly

```asm
0x14003ac70  mov     [rsp+arg_8], rbx
0x14003ac75  mov     [rsp+arg_10], rbp
0x14003ac7a  push    rdi
0x14003ac7b  sub     rsp, 40h
0x14003ac7f  mov     eax, [rcx+20h]
0x14003ac82  xor     ebp, ebp
0x14003ac84  mov     [rcx+80h], ebp
0x14003ac8a  mov     rbx, rcx
0x14003ac8d  test    eax, 0FFFFFFFCh
0x14003ac92  jnz     loc_14003AD3E
0x14003ac98  cmp     eax, 1
0x14003ac9b  jz      loc_14003AD3E
0x14003aca1  mov     rax, [rcx+28h]
0x14003aca5  lea     rdi, [rcx+5Ch]
0x14003aca9  mov     r8d, [rcx+58h]; UncompressedBufferSize
0x14003acad  mov     r10, [rcx+50h]
0x14003acb1  mov     r9, [rbx+48h]; CompressedBuffer
0x14003acb5  mov     ecx, [rax]
0x14003acb7  mov     rdx, [rbx+40h]; UncompressedBuffer
0x14003acbb  lea     eax, [r8-1]
0x14003acbf  mov     [rsp+48h+WorkSpace], r10; WorkSpace
0x14003acc4  mov     [rsp+48h+FinalCompressedSize], rdi; FinalCompressedSize
0x14003acc9  mov     [rsp+48h+UncompressedChunkSize], ecx; UncompressedChunkSize
0x14003accd  movzx   ecx, cs:FileProvXPressAlgorithm; CompressionFormatAndEngine
0x14003acd4  mov     [rsp+48h+CompressedBufferSize], eax; CompressedBufferSize
0x14003acd8  call    cs:__imp_RtlCompressBuffer
0x14003acdf  nop     dword ptr [rax+rax+00h]
0x14003ace4  cmp     eax, 117h
0x14003ace9  jnz     short loc_14003AD13
0x14003aceb  mov     [rdi], ebp
0x14003aced  lea     rcx, [rbx+60h]; Event
0x14003acf1  xor     r8d, r8d; Wait
0x14003acf4  xor     edx, edx; Increment
0x14003acf6  call    cs:__imp_KeSetEvent
0x14003acfd  nop     dword ptr [rax+rax+00h]
0x14003ad02  mov     rbx, [rsp+48h+arg_8]
0x14003ad07  mov     rbp, [rsp+48h+arg_10]
0x14003ad0c  add     rsp, 40h
0x14003ad10  pop     rdi
0x14003ad11  retn
0x14003ad13  cmp     eax, 0C0000023h
0x14003ad18  jz      short loc_14003AD26
0x14003ad1a  test    eax, eax
0x14003ad1c  jns     short loc_14003ACED
0x14003ad1e  mov     [rbx+80h], eax
0x14003ad24  jmp     short loc_14003ACED
0x14003ad26  mov     r8d, [rbx+58h]; Size
0x14003ad2a  mov     rdx, [rbx+40h]; Src
0x14003ad2e  mov     rcx, [rbx+48h]; void *
0x14003ad32  call    memmove
0x14003ad37  mov     eax, [rbx+58h]
0x14003ad3a  mov     [rdi], eax
0x14003ad3c  jmp     short loc_14003ACED
0x14003ad3e  mov     rcx, [rcx+48h]; void *
0x14003ad42  mov     [rsp+48h+arg_0], rsi
0x14003ad47  cmp     eax, 1
0x14003ad4a  jnz     short loc_14003ADAF
0x14003ad4c  mov     rax, [rbx+78h]
0x14003ad50  lea     r9, [rbx+5Ch]
0x14003ad54  mov     [rax+43B8h], rcx
0x14003ad5b  mov     rax, [rbx+78h]
0x14003ad5f  mov     [rax+43C0h], ebp
0x14003ad65  mov     r8d, [rbx+58h]
0x14003ad69  mov     rdx, [rbx+40h]
0x14003ad6d  mov     rcx, [rbx+78h]
0x14003ad71  call    LZX_Encode
0x14003ad76  mov     rcx, [rbx+78h]
0x14003ad7a  mov     edi, eax
0x14003ad7c  call    LZX_EncodeFlush
0x14003ad81  mov     rcx, [rbx+78h]
0x14003ad85  call    LZX_EncodeNewGroup
0x14003ad8a  test    edi, edi
0x14003ad8c  jz      short loc_14003ADC4
0x14003ad8e  mov     r8d, [rbx+58h]; Size
0x14003ad92  mov     rdx, [rbx+40h]; Src
0x14003ad96  mov     rcx, [rbx+48h]; void *
0x14003ad9a  call    memmove
0x14003ad9f  mov     ecx, [rbx+58h]
0x14003ada2  mov     [rbx+5Ch], ecx
0x14003ada5  mov     rsi, [rsp+48h+arg_0]
0x14003adaa  jmp     loc_14003ACED
0x14003adaf  mov     r8d, [rbx+58h]; Size
0x14003adb3  mov     rdx, [rbx+40h]; Src
0x14003adb7  call    memmove
0x14003adbc  mov     eax, [rbx+58h]
0x14003adbf  mov     [rbx+5Ch], eax
0x14003adc2  jmp     short loc_14003ADA5
0x14003adc4  mov     rax, [rbx+78h]
0x14003adc8  mov     ecx, [rax+43C0h]
0x14003adce  cmp     ecx, [rbx+58h]
0x14003add1  jb      short loc_14003ADA2
0x14003add3  jmp     short loc_14003AD8E
```
