# PipeTryRead

- ea: `0x1400026f0`
- end: `0x14000279d`
- name: `PipeTryRead`
- size: `173`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140002000`
- `0x14001661c`

## callees

- `0x140001560`
- `0x1400026f0`

## pseudocode

```c
__int64 __fastcall PipeTryRead(__int64 a1, __int64 a2, _DWORD *a3)
{
  __int64 v6; // rbp
  __int64 result; // rax

  if ( !*(_BYTE *)(a1 + 273) )
    return PipeTryReadSingle(a1, a2, 0, a3);
  v6 = *(_QWORD *)(a2 + 184);
  result = PipeTryReadSingle(a1, a2, 1, a3);
  if ( (int)result >= 0 )
  {
    while ( *(_QWORD *)(a2 + 56) != *(_DWORD *)(v6 + 8) )
    {
      result = PipeTryReadSingle(a1, a2, 1, a3);
      if ( (int)result < 0 )
        goto LABEL_5;
    }
    return 0;
  }
LABEL_5:
  if ( (_DWORD)result == -2147483643 || (_DWORD)result == -1073741807 && *(_QWORD *)(a2 + 56) )
    return 0;
  return result;
}

```

## disassembly

```asm
0x1400026f0  mov     [rsp+arg_10], rsi
0x1400026f5  mov     [rsp+arg_18], rdi
0x1400026fa  push    r14
0x1400026fc  sub     rsp, 20h
0x140002700  cmp     byte ptr [rcx+111h], 0
0x140002707  mov     r14, r8
0x14000270a  mov     rdi, rdx
0x14000270d  mov     rsi, rcx
0x140002710  mov     r9, r8
0x140002713  jz      short loc_140002783
0x140002715  mov     [rsp+28h+arg_0], rbx
0x14000271a  mov     r8b, 1
0x14000271d  mov     [rsp+28h+arg_8], rbp
0x140002722  mov     rbp, [rdx+0B8h]
0x140002729  call    PipeTryReadSingle
0x14000272e  test    eax, eax
0x140002730  js      short loc_140002750
0x140002732  mov     eax, [rbp+8]
0x140002735  cmp     [rdi+38h], rax
0x140002739  jz      short loc_140002765
0x14000273b  mov     r9, r14
0x14000273e  mov     r8b, 1
0x140002741  mov     rdx, rdi
0x140002744  mov     rcx, rsi
0x140002747  call    PipeTryReadSingle
0x14000274c  test    eax, eax
0x14000274e  jns     short loc_140002732
0x140002750  cmp     eax, 80000005h
0x140002755  jz      short loc_140002765
0x140002757  cmp     eax, 0C0000011h
0x14000275c  jnz     short loc_140002767
0x14000275e  cmp     qword ptr [rdi+38h], 0
0x140002763  jbe     short loc_140002767
0x140002765  xor     eax, eax
0x140002767  mov     rbp, [rsp+28h+arg_8]
0x14000276c  mov     rbx, [rsp+28h+arg_0]
0x140002771  mov     rsi, [rsp+28h+arg_10]
0x140002776  mov     rdi, [rsp+28h+arg_18]
0x14000277b  add     rsp, 20h
0x14000277f  pop     r14
0x140002781  retn
0x140002783  xor     r8d, r8d
0x140002786  call    PipeTryReadSingle
0x14000278b  mov     rsi, [rsp+28h+arg_10]
0x140002790  mov     rdi, [rsp+28h+arg_18]
0x140002795  add     rsp, 20h
0x140002799  pop     r14
0x14000279b  retn
```
