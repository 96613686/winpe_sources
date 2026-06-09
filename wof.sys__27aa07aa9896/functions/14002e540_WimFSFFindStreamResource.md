# WimFSFFindStreamResource

- ea: `0x14002e540`
- end: `0x14002e5c2`
- name: `WimFSFFindStreamResource`
- size: `130`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140027b90`
- `0x14003c280`

## callees

- `0x14002d220`
- `0x14002e540`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x14002e595`
- `ntoskrnl!RtlCompareMemory` at `0x14002e595`

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
0x14002e540  push    rbx
0x14002e542  push    rbp
0x14002e543  push    rsi
0x14002e544  push    rdi
0x14002e545  sub     rsp, 28h
0x14002e549  mov     rdi, [rdx+68h]
0x14002e54d  mov     rbp, r8
0x14002e550  mov     rdx, rdi
0x14002e553  call    WimFSFInitializeOffsetTable
0x14002e558  test    eax, eax
0x14002e55a  js      short loc_14002E5B6
0x14002e55c  mov     ebx, [rbp+0]
0x14002e55f  mov     ecx, 20h ; ' '
0x14002e564  sub     ecx, [rdi+3C8h]
0x14002e56a  shr     rbx, cl
0x14002e56d  shl     rbx, 4
0x14002e571  add     rbx, [rdi+3D0h]
0x14002e578  xor     edi, edi
0x14002e57a  cmp     edi, [rbx+8]
0x14002e57d  jnb     short loc_14002E5B6
0x14002e57f  mov     eax, edi
0x14002e581  mov     r8d, 14h; Length
0x14002e587  imul    rsi, rax, 32h ; '2'
0x14002e58b  mov     rdx, rbp; Source2
0x14002e58e  add     rsi, [rbx]
0x14002e591  lea     rcx, [rsi+1Eh]; Source1
0x14002e595  call    cs:__imp_RtlCompareMemory
0x14002e59c  nop     dword ptr [rax+rax+00h]
0x14002e5a1  cmp     rax, 14h
0x14002e5a5  jnz     short loc_14002E5AD
0x14002e5a7  test    byte ptr [rsi+7], 1
0x14002e5ab  jz      short loc_14002E5B1
0x14002e5ad  inc     edi
0x14002e5af  jmp     short loc_14002E57A
0x14002e5b1  mov     rax, rsi
0x14002e5b4  jmp     short loc_14002E5B8
0x14002e5b6  xor     eax, eax
0x14002e5b8  add     rsp, 28h
0x14002e5bc  pop     rdi
0x14002e5bd  pop     rsi
0x14002e5be  pop     rbp
0x14002e5bf  pop     rbx
0x14002e5c0  retn
```
