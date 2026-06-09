# ComputeEventEntryHash

- ea: `0x180011670`
- end: `0x180011702`
- name: `ComputeEventEntryHash`
- size: `146`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180010290`

## callees

- `0x18000c6b0`
- `0x180011670`

## pseudocode

```c
__int64 __fastcall ComputeEventEntryHash(char a1, unsigned __int8 a2, __int64 a3)
{
  unsigned __int64 v5; // rcx
  unsigned int v7; // r10d
  int v8; // eax
  unsigned __int8 v9; // bl
  unsigned int v11; // [rsp+30h] [rbp+8h] BYREF

  v5 = 0;
  v7 = 0;
  do
  {
    v8 = *(unsigned __int8 *)(a3 + v5++ + 16);
    v7 = (1025 * (v7 + v8)) ^ ((1025 * (v7 + v8)) >> 6);
  }
  while ( v5 < 8 );
  v9 = a1 + 2;
  v11 = v7;
  if ( v9 < a2 )
  {
    do
    {
      RunningHash(&v11, *(_QWORD *)(a3 + 16LL * v9), *(unsigned int *)(a3 + 16LL * v9 + 8));
      ++v9;
    }
    while ( v9 < a2 );
    v7 = v11;
  }
  return 32769 * ((9 * v7) ^ ((9 * v7) >> 11));
}

```

## disassembly

```asm
0x180011670  mov     [rsp+arg_8], rbx
0x180011675  mov     [rsp+arg_10], rsi
0x18001167a  push    rdi
0x18001167b  sub     rsp, 20h
0x18001167f  mov     bl, cl
0x180011681  mov     rdi, r8
0x180011684  xor     ecx, ecx
0x180011686  mov     sil, dl
0x180011689  xor     r10d, r10d
0x18001168c  movzx   eax, byte ptr [r8+rcx+10h]
0x180011692  inc     rcx
0x180011695  add     eax, r10d
0x180011698  imul    r9d, eax, 401h
0x18001169f  mov     r10d, r9d
0x1800116a2  shr     r10d, 6
0x1800116a6  xor     r10d, r9d
0x1800116a9  cmp     rcx, 8
0x1800116ad  jb      short loc_18001168C
0x1800116af  add     bl, 2
0x1800116b2  mov     [rsp+28h+arg_0], r10d
0x1800116b7  cmp     bl, sil
0x1800116ba  jnb     short loc_1800116E1
0x1800116bc  movzx   edx, bl
0x1800116bf  lea     rcx, [rsp+28h+arg_0]
0x1800116c4  add     rdx, rdx
0x1800116c7  mov     r8d, [rdi+rdx*8+8]
0x1800116cc  mov     rdx, [rdi+rdx*8]
0x1800116d0  call    RunningHash
0x1800116d5  inc     bl
0x1800116d7  cmp     bl, sil
0x1800116da  jb      short loc_1800116BC
0x1800116dc  mov     r10d, [rsp+28h+arg_0]
0x1800116e1  mov     rbx, [rsp+28h+arg_8]
0x1800116e6  lea     eax, [r10+r10*8]
0x1800116ea  mov     rsi, [rsp+28h+arg_10]
0x1800116ef  mov     ecx, eax
0x1800116f1  shr     ecx, 0Bh
0x1800116f4  xor     ecx, eax
0x1800116f6  imul    eax, ecx, 8001h
0x1800116fc  add     rsp, 20h
0x180011700  pop     rdi
0x180011701  retn
```
