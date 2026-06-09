# WanpCreateAdapter

- ea: `0x14000d620`
- end: `0x14000d8bb`
- name: `WanpCreateAdapter`
- size: `667`
- prototype: `__int64 __fastcall(__int128 *, const UNICODE_STRING *, const UNICODE_STRING *, __int64, char, __int64 *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14000df30`

## callees

- `0x1400051c0`
- `0x14000d620`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14000d6f4`
- `ntoskrnl!ExAllocatePool2` at `0x14000d6f4`
- `ntoskrnl!RtlUnicodeStringToAnsiString` at `0x14000d7fe`
- `ntoskrnl!RtlUnicodeStringToAnsiString` at `0x14000d7fe`
- `ntoskrnl!KeInitializeSpinLock` at `0x14000d86d`
- `ntoskrnl!KeInitializeSpinLock` at `0x14000d86d`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000d7d6`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000d7d6`

## pseudocode

```c
__int64 __fastcall WanpCreateAdapter(
        __int128 *a1,
        const UNICODE_STRING *a2,
        const UNICODE_STRING *a3,
        __int64 a4,
        char a5,
        __int64 *a6)
{
  const UNICODE_STRING *v6; // rsi
  unsigned int Length; // eax
  unsigned int v10; // eax
  unsigned int v11; // ecx
  unsigned int v12; // r8d
  unsigned int v13; // eax
  unsigned int v14; // ecx
  unsigned int v15; // edx
  unsigned int v16; // ecx
  __int64 Pool2; // rax
  __int64 v18; // rdi
  char *v19; // rbx
  __int64 v20; // rax
  unsigned __int64 v21; // rbx
  unsigned __int64 v22; // rbx
  __int128 v23; // xmm0

  v6 = a3;
  if ( a5 == 1 && *a6 )
    return 0;
  *a6 = 0;
  Length = a2->Length;
  if ( !a3->Buffer )
    v6 = a2;
  if ( Length + 2 >= Length && Length + 5 >= Length + 2 )
  {
    v10 = (Length + 5) & 0xFFFFFFFC;
    v11 = 2 * v10;
    if ( 2 * v10 >= v10 )
    {
      v12 = v11 + 392;
      if ( v11 + 392 >= v11 )
      {
        v13 = v6->Length;
        if ( v13 + 2 >= v13 && v13 + 5 >= v13 + 2 )
        {
          v14 = (v13 + 5) & 0xFFFFFFFC;
          v15 = v12 + v14;
          if ( v12 + v14 >= v14 )
          {
            v16 = (v13 >> 1) + v15;
            if ( v16 >= v15 && v16 + 2 >= v16 )
            {
              Pool2 = ExAllocatePool2(64, v16 + 2, 1634759255);
              v18 = Pool2;
              if ( Pool2 )
              {
                *(_WORD *)(Pool2 + 56) = a2->Length;
                v19 = (char *)((Pool2 + 395) & 0xFFFFFFFFFFFFFFFCuLL);
                *(_WORD *)(Pool2 + 58) = a2->Length;
                *(_QWORD *)(Pool2 + 64) = v19;
                memmove(v19, a2->Buffer, a2->Length);
                v20 = a2->Length;
                *(_WORD *)(v18 + 72) = v20;
                v21 = (unsigned __int64)&v19[v20 + 5];
                LOWORD(v20) = a2->Length;
                v21 &= 0xFFFFFFFFFFFFFFFCuLL;
                *(_QWORD *)(v18 + 80) = v21;
                *(_WORD *)(v18 + 74) = v20;
                memmove((void *)v21, a2->Buffer, a2->Length);
                *(_WORD *)(*(_QWORD *)(v18 + 80) + 2 * ((unsigned __int64)a2->Length >> 1)) = 0;
                *(_BYTE *)(v18 + 149) = 1;
                v22 = a2->Length + 5LL + v21;
                *(_WORD *)(v18 + 88) = v6->Length;
                v22 &= 0xFFFFFFFFFFFFFFFCuLL;
                *(_WORD *)(v18 + 90) = v6->Length;
                *(_QWORD *)(v18 + 96) = v22;
                memmove((void *)v22, v6->Buffer, v6->Length);
                *(_WORD *)(*(_QWORD *)(v18 + 96) + 2 * ((unsigned __int64)v6->Length >> 1)) = 0;
                *(_QWORD *)(v18 + 112) = (v22 + *(unsigned __int16 *)(v18 + 88) + 5LL) & 0xFFFFFFFFFFFFFFFCuLL;
                if ( KeGetCurrentIrql() )
                {
                  *(_WORD *)(v18 + 106) = 0;
                }
                else
                {
                  *(_WORD *)(v18 + 106) = (v6->Length >> 1) + 1;
                  RtlUnicodeStringToAnsiString((PANSI_STRING)(v18 + 104), v6, 0);
                }
                v23 = *a1;
                *(_BYTE *)(v18 + 148) = 0;
                *(_OWORD *)(v18 + 152) = v23;
                *(_DWORD *)(v18 + 144) = -1;
                *(_DWORD *)(v18 + 140) = -1;
                *(_DWORD *)(v18 + 188) = 2017809152;
                *(_WORD *)(v18 + 192) = 120;
                *(_BYTE *)(v18 + 191) = BYTE1(*(_DWORD *)(v18 + 136));
                *(_BYTE *)(v18 + 192) = *(_BYTE *)(v18 + 136);
                KeInitializeSpinLock((PKSPIN_LOCK)(v18 + 120));
                *(_DWORD *)(v18 + 48) = 1633968471;
                *(_DWORD *)(v18 + 360) = -1;
                *(_DWORD *)(v18 + 344) = 0;
                *(_DWORD *)(v18 + 128) = 1;
                _InterlockedAdd((volatile signed __int32 *)(v18 + 132), 1u);
                *a6 = v18;
                return 0;
              }
            }
          }
        }
      }
    }
  }
  return 3221225626LL;
}

```

## disassembly

```asm
0x14000d620  push    rbx
0x14000d622  push    rbp
0x14000d623  push    rsi
0x14000d624  push    rdi
0x14000d625  push    r13
0x14000d627  push    r14
0x14000d629  push    r15
0x14000d62b  sub     rsp, 20h
0x14000d62f  mov     r15, [rsp+58h+arg_28]
0x14000d637  mov     r13d, 1
0x14000d63d  mov     rsi, r8
0x14000d640  mov     r14, rdx
0x14000d643  mov     rbp, rcx
0x14000d646  cmp     [rsp+58h+arg_20], r13b
0x14000d64e  jnz     short loc_14000D65A
0x14000d650  cmp     qword ptr [r15], 0
0x14000d654  jnz     loc_14000D8A2
0x14000d65a  mov     qword ptr [r15], 0
0x14000d661  movzx   eax, word ptr [rdx]
0x14000d664  cmp     qword ptr [r8+8], 0
0x14000d669  cmovz   rsi, r14
0x14000d66d  lea     ecx, [rax+2]
0x14000d670  cmp     ecx, eax
0x14000d672  jb      loc_14000D8A6
0x14000d678  lea     eax, [rcx+3]
0x14000d67b  cmp     eax, ecx
0x14000d67d  jb      loc_14000D8A6
0x14000d683  mov     r9d, 0FFFFFFFCh
0x14000d689  and     eax, r9d
0x14000d68c  lea     ecx, [rax+rax]
0x14000d68f  cmp     ecx, eax
0x14000d691  jb      loc_14000D8A6
0x14000d697  lea     r8d, [rcx+188h]
0x14000d69e  cmp     r8d, ecx
0x14000d6a1  jb      loc_14000D8A6
0x14000d6a7  movzx   eax, word ptr [rsi]
0x14000d6aa  lea     edx, [rax+2]
0x14000d6ad  cmp     edx, eax
0x14000d6af  jb      loc_14000D8A6
0x14000d6b5  lea     ecx, [rdx+3]
0x14000d6b8  cmp     ecx, edx
0x14000d6ba  jb      loc_14000D8A6
0x14000d6c0  and     ecx, r9d
0x14000d6c3  lea     edx, [r8+rcx]
0x14000d6c7  cmp     edx, ecx
0x14000d6c9  jb      loc_14000D8A6
0x14000d6cf  shr     eax, 1
0x14000d6d1  lea     ecx, [rax+rdx]
0x14000d6d4  cmp     ecx, edx
0x14000d6d6  jb      loc_14000D8A6
0x14000d6dc  lea     eax, [rcx+2]
0x14000d6df  cmp     eax, ecx
0x14000d6e1  jb      loc_14000D8A6
0x14000d6e7  mov     edx, eax
0x14000d6e9  mov     ecx, 40h ; '@'
0x14000d6ee  mov     r8d, 61707257h
0x14000d6f4  call    cs:__imp_ExAllocatePool2
0x14000d6fb  nop     dword ptr [rax+rax+00h]
0x14000d700  mov     rdi, rax
0x14000d703  test    rax, rax
0x14000d706  jz      loc_14000D8A6
0x14000d70c  movzx   ecx, word ptr [r14]
0x14000d710  lea     rbx, [rax+18Bh]
0x14000d717  mov     [rax+38h], cx
0x14000d71b  and     rbx, 0FFFFFFFFFFFFFFFCh
0x14000d71f  movzx   ecx, word ptr [r14]
0x14000d723  mov     [rax+3Ah], cx
0x14000d727  mov     rcx, rbx; void *
0x14000d72a  mov     [rax+40h], rbx
0x14000d72e  movzx   r8d, word ptr [r14]; Size
0x14000d732  mov     rdx, [r14+8]; Src
0x14000d736  call    memmove
0x14000d73b  movzx   eax, word ptr [r14]
0x14000d73f  add     rbx, 5
0x14000d743  mov     [rdi+48h], ax
0x14000d747  add     rbx, rax
0x14000d74a  movzx   eax, word ptr [r14]
0x14000d74e  and     rbx, 0FFFFFFFFFFFFFFFCh
0x14000d752  mov     [rdi+50h], rbx
0x14000d756  mov     rcx, rbx; void *
0x14000d759  mov     [rdi+4Ah], ax
0x14000d75d  movzx   r8d, word ptr [r14]; Size
0x14000d761  mov     rdx, [r14+8]; Src
0x14000d765  call    memmove
0x14000d76a  movzx   edx, word ptr [r14]
0x14000d76e  xor     eax, eax
0x14000d770  mov     rcx, [rdi+50h]
0x14000d774  shr     rdx, 1
0x14000d777  mov     [rcx+rdx*2], ax
0x14000d77b  mov     [rdi+95h], r13b
0x14000d782  movzx   eax, word ptr [r14]
0x14000d786  add     rax, 5
0x14000d78a  add     rbx, rax
0x14000d78d  movzx   eax, word ptr [rsi]
0x14000d790  mov     [rdi+58h], ax
0x14000d794  and     rbx, 0FFFFFFFFFFFFFFFCh
0x14000d798  movzx   eax, word ptr [rsi]
0x14000d79b  mov     rcx, rbx; void *
0x14000d79e  mov     [rdi+5Ah], ax
0x14000d7a2  mov     [rdi+60h], rbx
0x14000d7a6  movzx   r8d, word ptr [rsi]; Size
0x14000d7aa  mov     rdx, [rsi+8]; Src
0x14000d7ae  call    memmove
0x14000d7b3  movzx   edx, word ptr [rsi]
0x14000d7b6  xor     eax, eax
0x14000d7b8  mov     rcx, [rdi+60h]
0x14000d7bc  shr     rdx, 1
0x14000d7bf  mov     [rcx+rdx*2], ax
0x14000d7c3  movzx   ecx, word ptr [rdi+58h]
0x14000d7c7  add     rcx, 5
0x14000d7cb  add     rcx, rbx
0x14000d7ce  and     rcx, 0FFFFFFFFFFFFFFFCh
0x14000d7d2  mov     [rdi+70h], rcx
0x14000d7d6  call    cs:__imp_KeGetCurrentIrql
0x14000d7dd  nop     dword ptr [rax+rax+00h]
0x14000d7e2  test    al, al
0x14000d7e4  jnz     short loc_14000D80C
0x14000d7e6  movzx   eax, word ptr [rsi]
0x14000d7e9  lea     rcx, [rdi+68h]; DestinationString
0x14000d7ed  shr     ax, 1
0x14000d7f0  xor     r8d, r8d; AllocateDestinationString
0x14000d7f3  add     ax, r13w
0x14000d7f7  mov     rdx, rsi; SourceString
0x14000d7fa  mov     [rdi+6Ah], ax
0x14000d7fe  call    cs:__imp_RtlUnicodeStringToAnsiString
0x14000d805  nop     dword ptr [rax+rax+00h]
0x14000d80a  jmp     short loc_14000D812
0x14000d80c  xor     eax, eax
0x14000d80e  mov     [rdi+6Ah], ax
0x14000d812  movups  xmm0, xmmword ptr [rbp+0]
0x14000d816  mov     byte ptr [rdi+94h], 0
0x14000d81d  lea     rcx, [rdi+78h]; SpinLock
0x14000d821  or      ebx, 0FFFFFFFFh
0x14000d824  movdqu  xmmword ptr [rdi+98h], xmm0
0x14000d82c  mov     [rdi+90h], ebx
0x14000d832  mov     [rdi+8Ch], ebx
0x14000d838  mov     eax, cs:dword_140007290
0x14000d83e  mov     [rdi+0BCh], eax
0x14000d844  movzx   eax, cs:word_140007294
0x14000d84b  mov     [rdi+0C0h], ax
0x14000d852  mov     eax, [rdi+88h]
0x14000d858  shr     eax, 8
0x14000d85b  mov     [rdi+0BFh], al
0x14000d861  mov     al, [rdi+88h]
0x14000d867  mov     [rdi+0C0h], al
0x14000d86d  call    cs:__imp_KeInitializeSpinLock
0x14000d874  nop     dword ptr [rax+rax+00h]
0x14000d879  mov     dword ptr [rdi+30h], 61646157h
0x14000d880  mov     [rdi+168h], ebx
0x14000d886  mov     dword ptr [rdi+158h], 0
0x14000d890  mov     [rdi+80h], r13d
0x14000d897  lock add [rdi+84h], r13d
0x14000d89f  mov     [r15], rdi
0x14000d8a2  xor     eax, eax
0x14000d8a4  jmp     short loc_14000D8AB
0x14000d8a6  mov     eax, 0C000009Ah
0x14000d8ab  add     rsp, 20h
0x14000d8af  pop     r15
0x14000d8b1  pop     r14
0x14000d8b3  pop     r13
0x14000d8b5  pop     rdi
0x14000d8b6  pop     rsi
0x14000d8b7  pop     rbp
0x14000d8b8  pop     rbx
0x14000d8b9  retn
```
