# PipeFreeAndDeferCompletionList

- ea: `0x140002c50`
- end: `0x140002d18`
- name: `PipeFreeAndDeferCompletionList`
- size: `200`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140002b60`
- `0x140015c50`

## callees

- `0x140002c50`
- `0x1400030b4`
- `0x140015bf8`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140002cf1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002cf1`

## pseudocode

```c
void __fastcall PipeFreeAndDeferCompletionList(__int64 a1, _QWORD *a2, unsigned int a3)
{
  _QWORD *v6; // rdi
  int v7; // eax
  _QWORD *v8; // rax
  __int64 v9; // rax
  _QWORD *v10; // rcx

  while ( 1 )
  {
    v6 = (_QWORD *)*a2;
    if ( (_QWORD *)*a2 == a2 )
      break;
    v7 = *((_DWORD *)v6 - 4);
    switch ( v7 )
    {
      case 1:
        if ( (unsigned __int8)PipeDequeueIrpForCompletion(v6 - 17, a3) )
        {
          v8 = *(_QWORD **)(a1 + 8);
          if ( *v8 != a1 )
            goto LABEL_13;
          *v6 = a1;
          v6[1] = v8;
          *v8 = v6;
          *(_QWORD *)(a1 + 8) = v6;
        }
        break;
      case 2:
        DvFreeHandleEntry(*(v6 - 1) + 392LL, *((unsigned int *)v6 + 5));
        --*(_DWORD *)(*(v6 - 1) + 440LL);
LABEL_10:
        v9 = *v6;
        if ( *(_QWORD **)(*v6 + 8LL) != v6 || (v10 = (_QWORD *)v6[1], (_QWORD *)*v10 != v6) )
LABEL_13:
          __fastfail(3u);
        *v10 = v9;
        *(_QWORD *)(v9 + 8) = v10;
        ExFreePoolWithTag(v6 - 2, 0x73756256u);
        break;
      case 3:
        goto LABEL_10;
    }
  }
}

```

## disassembly

```asm
0x140002c50  push    rbx
0x140002c52  push    rbp
0x140002c53  push    rsi
0x140002c54  push    rdi
0x140002c55  sub     rsp, 28h
0x140002c59  mov     ebp, r8d
0x140002c5c  mov     [rsp+48h+arg_0], r14
0x140002c61  mov     rbx, rdx
0x140002c64  mov     rsi, rcx
0x140002c67  mov     rdi, [rbx]
0x140002c6a  cmp     rdi, rbx
0x140002c6d  jz      loc_140002D09
0x140002c73  mov     eax, [rdi-10h]
0x140002c76  cmp     eax, 1
0x140002c79  jnz     short loc_140002CA6
0x140002c7b  lea     rcx, [rdi-88h]
0x140002c82  mov     edx, ebp
0x140002c84  call    PipeDequeueIrpForCompletion
0x140002c89  test    al, al
0x140002c8b  jz      short loc_140002C67
0x140002c8d  mov     rax, [rsi+8]
0x140002c91  cmp     [rax], rsi
0x140002c94  jnz     short loc_140002D02
0x140002c96  mov     [rdi], rsi
0x140002c99  mov     [rdi+8], rax
0x140002c9d  mov     [rax], rdi
0x140002ca0  mov     [rsi+8], rdi
0x140002ca4  jmp     short loc_140002C67
0x140002ca6  cmp     eax, 2
0x140002ca9  jz      short loc_140002CB2
0x140002cab  cmp     eax, 3
0x140002cae  jnz     short loc_140002C67
0x140002cb0  jmp     short loc_140002CCF
0x140002cb2  mov     rcx, [rdi-8]
0x140002cb6  mov     edx, [rdi+14h]
0x140002cb9  add     rcx, 188h
0x140002cc0  call    DvFreeHandleEntry
0x140002cc5  mov     rax, [rdi-8]
0x140002cc9  dec     dword ptr [rax+1B8h]
0x140002ccf  mov     rax, [rdi]
0x140002cd2  cmp     [rax+8], rdi
0x140002cd6  jnz     short loc_140002D02
0x140002cd8  mov     rcx, [rdi+8]
0x140002cdc  cmp     [rcx], rdi
0x140002cdf  jnz     short loc_140002D02
0x140002ce1  mov     [rcx], rax
0x140002ce4  mov     edx, 73756256h; Tag
0x140002ce9  mov     [rax+8], rcx
0x140002ced  lea     rcx, [rdi-10h]; P
0x140002cf1  call    cs:__imp_ExFreePoolWithTag
0x140002cf8  nop     dword ptr [rax+rax+00h]
0x140002cfd  jmp     loc_140002C67
0x140002d02  mov     ecx, 3
0x140002d07  int     29h; Win8: RtlFailFast(ecx)
0x140002d09  mov     r14, [rsp+48h+arg_0]
0x140002d0e  add     rsp, 28h
0x140002d12  pop     rdi
0x140002d13  pop     rsi
0x140002d14  pop     rbp
0x140002d15  pop     rbx
0x140002d16  retn
```
