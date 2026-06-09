# WimFSFFindStreamResource

- ea: `0x14002e4f0`
- end: `0x14002e572`
- name: `WimFSFFindStreamResource`
- size: `130`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140027b40`
- `0x14003c230`

## callees

- `0x14002d1d0`
- `0x14002e4f0`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x14002e545`
- `ntoskrnl!RtlCompareMemory` at `0x14002e545`

## pseudocode

```c
__int64 __fastcall WimFSFFindStreamResource(__int64 a1, __int64 a2, unsigned int *a3)
{
  __int64 v3; // rdi
  unsigned __int64 v5; // rbx
  unsigned int i; // edi
  __int64 v7; // rsi

  v3 = *(_QWORD *)(a2 + 104);
  if ( (int)WimFSFInitializeOffsetTable(a1, v3) >= 0 )
  {
    v5 = *(_QWORD *)(v3 + 976) + 16 * ((unsigned __int64)*a3 >> (32 - *(_BYTE *)(v3 + 968)));
    for ( i = 0; i < *(_DWORD *)(v5 + 8); ++i )
    {
      v7 = *(_QWORD *)v5 + 50LL * i;
      if ( RtlCompareMemory((const void *)(v7 + 30), a3, 0x14u) == 20 && (*(_BYTE *)(v7 + 7) & 1) == 0 )
        return v7;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x14002e4f0  push    rbx
0x14002e4f2  push    rbp
0x14002e4f3  push    rsi
0x14002e4f4  push    rdi
0x14002e4f5  sub     rsp, 28h
0x14002e4f9  mov     rdi, [rdx+68h]
0x14002e4fd  mov     rbp, r8
0x14002e500  mov     rdx, rdi
0x14002e503  call    WimFSFInitializeOffsetTable
0x14002e508  test    eax, eax
0x14002e50a  js      short loc_14002E566
0x14002e50c  mov     ebx, [rbp+0]
0x14002e50f  mov     ecx, 20h ; ' '
0x14002e514  sub     ecx, [rdi+3C8h]
0x14002e51a  shr     rbx, cl
0x14002e51d  shl     rbx, 4
0x14002e521  add     rbx, [rdi+3D0h]
0x14002e528  xor     edi, edi
0x14002e52a  cmp     edi, [rbx+8]
0x14002e52d  jnb     short loc_14002E566
0x14002e52f  mov     eax, edi
0x14002e531  mov     r8d, 14h; Length
0x14002e537  imul    rsi, rax, 32h ; '2'
0x14002e53b  mov     rdx, rbp; Source2
0x14002e53e  add     rsi, [rbx]
0x14002e541  lea     rcx, [rsi+1Eh]; Source1
0x14002e545  call    cs:__imp_RtlCompareMemory
0x14002e54c  nop     dword ptr [rax+rax+00h]
0x14002e551  cmp     rax, 14h
0x14002e555  jnz     short loc_14002E55D
0x14002e557  test    byte ptr [rsi+7], 1
0x14002e55b  jz      short loc_14002E561
0x14002e55d  inc     edi
0x14002e55f  jmp     short loc_14002E52A
0x14002e561  mov     rax, rsi
0x14002e564  jmp     short loc_14002E568
0x14002e566  xor     eax, eax
0x14002e568  add     rsp, 28h
0x14002e56c  pop     rdi
0x14002e56d  pop     rsi
0x14002e56e  pop     rbp
0x14002e56f  pop     rbx
0x14002e570  retn
```
