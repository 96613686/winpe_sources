# CTSparseBlock<ulong,uchar *,20,1>::RemoveValue(ulong)

- ea: `0x1800102b4`
- end: `0x18001041b`
- name: `?RemoveValue@?$CTSparseBlock@KPEAE$0BE@$00@@QEAAJK@Z`
- size: `359`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180010268`

## callees

- `0x18000b69c`
- `0x1800102b4`
- `0x18002a07c`

## pseudocode

```c
__int64 __fastcall CTSparseBlock<unsigned long,unsigned char *,20,1>::RemoveValue(__int64 a1)
{
  __int64 i; // rbx
  __int64 v3; // rax
  int v4; // r15d
  int v5; // edx
  int v6; // ebp
  int v7; // edx
  __int64 v8; // rdx

  for ( i = a1; i; i = *(_QWORD *)(i + 192) )
  {
    if ( *(_DWORD *)(i + 8) != -20 )
      break;
  }
  v3 = *(_QWORD *)(a1 + 200);
  v4 = 0;
  if ( v3 )
  {
    v5 = *(_DWORD *)(a1 + 208);
    if ( v5 + *(_DWORD *)(v3 + 8) )
    {
      if ( v5 )
        *(_DWORD *)(a1 + 208) = v5 - 1;
      else
        v4 = 1;
    }
  }
  v6 = 0;
  while ( i )
  {
    v7 = *(_DWORD *)(i + 8);
    if ( v7 )
    {
      if ( *(char *)(i + 24) < 0 )
      {
        v6 = CTSparseBlock<unsigned long,WRITER_SINK_CALLBACK *,20,1>::SetValue(
               (_DWORD *)a1,
               v7 - 1,
               *(__int64 (__fastcall ***)(_QWORD, _QWORD *))(i + 32));
        if ( v6 < 0 )
          break;
      }
    }
    memmove_0((void *)(i + 32), (const void *)(i + 40), 0x98u);
    v8 = 0;
    do
    {
      *(_BYTE *)(v8 + i + 24) *= 2;
      if ( (unsigned int)v8 < 2 && *(char *)((unsigned int)(v8 + 1) + i + 24) < 0 )
        *(_BYTE *)(v8 + i + 24) |= 1u;
      v8 = (unsigned int)(v8 + 1);
    }
    while ( (unsigned int)v8 < 3 );
    if ( v4 && *(_QWORD *)(i + 192) == *(_QWORD *)(a1 + 200) )
    {
      *(_QWORD *)(a1 + 200) = i;
      *(_DWORD *)(a1 + 208) = 19;
    }
    i = *(_QWORD *)(i + 192);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800102b4  push    rbx
0x1800102b6  push    rbp
0x1800102b7  push    rsi
0x1800102b8  push    rdi
0x1800102b9  push    r14
0x1800102bb  push    r15
0x1800102bd  sub     rsp, 28h
0x1800102c1  mov     rdi, rcx
0x1800102c4  mov     rbx, rcx
0x1800102c7  test    rcx, rcx
0x1800102ca  jz      short loc_1800102E0
0x1800102cc  mov     eax, [rbx+8]
0x1800102cf  add     eax, 14h
0x1800102d2  jnz     short loc_1800102E0
0x1800102d4  mov     rbx, [rbx+0C0h]
0x1800102db  test    rbx, rbx
0x1800102de  jnz     short loc_1800102CC
0x1800102e0  mov     rax, [rcx+0C8h]
0x1800102e7  xor     r15d, r15d
0x1800102ea  test    rax, rax
0x1800102ed  jz      short loc_18001030F
0x1800102ef  mov     edx, [rcx+0D0h]
0x1800102f5  mov     ecx, [rax+8]
0x1800102f8  add     ecx, edx
0x1800102fa  jz      short loc_18001030F
0x1800102fc  test    edx, edx
0x1800102fe  jnz     short loc_180010306
0x180010300  lea     r15d, [rdx+1]
0x180010304  jmp     short loc_18001030F
0x180010306  lea     eax, [rdx-1]
0x180010309  mov     [rdi+0D0h], eax
0x18001030f  xor     ebp, ebp
0x180010311  jmp     loc_180010403
0x180010316  mov     edx, [rbx+8]
0x180010319  test    edx, edx
0x18001031b  jnz     short loc_180010327
0x18001031d  lea     r14d, [rdx+1]
0x180010321  neg     edx
0x180010323  mov     esi, edx
0x180010325  jmp     short loc_18001034A
0x180010327  xor     r14d, r14d
0x18001032a  xor     esi, esi
0x18001032c  cmp     [rbx+18h], sil
0x180010330  jge     short loc_18001034A
0x180010332  mov     r8, [rbx+20h]
0x180010336  dec     edx
0x180010338  mov     rcx, rdi
0x18001033b  call    ?SetValue@?$CTSparseBlock@KPEAUWRITER_SINK_CALLBACK@@$0BE@$00@@QEAAJKPEAUWRITER_SINK_CALLBACK@@@Z; CTSparseBlock<ulong,WRITER_SINK_CALLBACK *,20,1>::SetValue(ulong,WRITER_SINK_CALLBACK *)
0x180010340  mov     ebp, eax
0x180010342  test    eax, eax
0x180010344  js      loc_18001040C
0x18001034a  mov     r8d, 13h
0x180010350  mov     ecx, esi
0x180010352  add     rcx, 4
0x180010356  lea     edx, [rsi+1]
0x180010359  sub     r8d, esi
0x18001035c  lea     rdx, [rdx+4]
0x180010360  shl     r8, 3; Size
0x180010364  lea     rdx, [rbx+rdx*8]; Src
0x180010368  lea     rcx, [rbx+rcx*8]; void *
0x18001036c  call    memmove_0
0x180010371  mov     eax, esi
0x180010373  shr     eax, 3
0x180010376  mov     edx, eax
0x180010378  lea     r10, [rax+rbx]
0x18001037c  mov     r11b, [r10+18h]
0x180010380  cmp     eax, 3
0x180010383  jnb     short loc_1800103A4
0x180010385  shl     byte ptr [rdx+rbx+18h], 1
0x180010389  cmp     edx, 2
0x18001038c  jnb     short loc_18001039D
0x18001038e  lea     eax, [rdx+1]
0x180010391  cmp     byte ptr [rax+rbx+18h], 0
0x180010396  jge     short loc_18001039D
0x180010398  or      byte ptr [rdx+rbx+18h], 1
0x18001039d  inc     edx
0x18001039f  cmp     edx, 3
0x1800103a2  jb      short loc_180010385
0x1800103a4  test    r14d, r14d
0x1800103a7  jz      short loc_1800103D6
0x1800103a9  and     sil, 7
0x1800103ad  jbe     short loc_1800103D6
0x1800103af  movzx   ecx, sil
0x1800103b3  lea     rax, qword_18002EEF8
0x1800103ba  sub     rax, rcx
0x1800103bd  mov     dl, [rax]
0x1800103bf  lea     rax, ?s_bLeftBitMasks@?$CTSparseBlock@KPEAUWRITER_SINK_CALLBACK@@$0BE@$00@@0PAEA; uchar near * CTSparseBlock<ulong,WRITER_SINK_CALLBACK *,20,1>::s_bLeftBitMasks
0x1800103c6  and     dl, [r10+18h]
0x1800103ca  mov     al, [rcx+rax]
0x1800103cd  and     al, r11b
0x1800103d0  or      dl, al
0x1800103d2  mov     [r10+18h], dl
0x1800103d6  test    r15d, r15d
0x1800103d9  jz      short loc_1800103FC
0x1800103db  mov     rax, [rdi+0C8h]
0x1800103e2  cmp     [rbx+0C0h], rax
0x1800103e9  jnz     short loc_1800103FC
0x1800103eb  mov     [rdi+0C8h], rbx
0x1800103f2  mov     dword ptr [rdi+0D0h], 13h
0x1800103fc  mov     rbx, [rbx+0C0h]
0x180010403  test    rbx, rbx
0x180010406  jnz     loc_180010316
0x18001040c  mov     eax, ebp
0x18001040e  add     rsp, 28h
0x180010412  pop     r15
0x180010414  pop     r14
0x180010416  pop     rdi
0x180010417  pop     rsi
0x180010418  pop     rbp
0x180010419  pop     rbx
0x18001041a  retn
```
