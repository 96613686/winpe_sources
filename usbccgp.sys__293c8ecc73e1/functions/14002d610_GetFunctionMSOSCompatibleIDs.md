# GetFunctionMSOSCompatibleIDs

- ea: `0x14002d610`
- end: `0x14002d691`
- name: `GetFunctionMSOSCompatibleIDs`
- size: `129`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140024928`
- `0x1400249d4`

## callees

- `0x14002d610`
- `0x14002d698`

## pseudocode

```c
char __fastcall GetFunctionMSOSCompatibleIDs(__int64 a1, _QWORD *a2, _QWORD *a3)
{
  __int64 v5; // rdx
  unsigned int v6; // ecx
  char result; // al
  __int64 v8; // rdx

  v5 = *(_QWORD *)(a1 + 232);
  v6 = 0;
  *a3 = 0;
  *a2 = 0;
  if ( *(_QWORD *)(v5 + 1128) )
    return GetFunctionMsOs20CompatibleIDs(a1, a2, a3);
  v8 = *(_QWORD *)(v5 + 1120);
  if ( v8 )
  {
    while ( v6 < *(unsigned __int8 *)(v8 + 8) )
    {
      if ( *(unsigned __int8 *)(v8 + 24LL * v6 + 16) == *(_DWORD *)(a1 + 8) )
      {
        result = 1;
        *a2 = v8 + 18 + 24LL * v6;
        *a3 = v8 + 26 + 24LL * v6;
        return result;
      }
      ++v6;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x14002d610  push    rbx
0x14002d612  sub     rsp, 20h
0x14002d616  mov     r10, rdx
0x14002d619  mov     r11, rcx
0x14002d61c  mov     rdx, [rcx+0E8h]
0x14002d623  mov     r9, r8
0x14002d626  xor     ecx, ecx
0x14002d628  mov     [r8], rcx
0x14002d62b  mov     [r10], rcx
0x14002d62e  cmp     [rdx+468h], rcx
0x14002d635  jz      short loc_14002D644
0x14002d637  mov     rdx, r10
0x14002d63a  mov     rcx, r11
0x14002d63d  call    GetFunctionMsOs20CompatibleIDs
0x14002d642  jmp     short loc_14002D68A
0x14002d644  mov     rdx, [rdx+460h]
0x14002d64b  test    rdx, rdx
0x14002d64e  jz      short loc_14002D688
0x14002d650  movzx   ebx, byte ptr [rdx+8]
0x14002d654  cmp     ecx, ebx
0x14002d656  jnb     short loc_14002D688
0x14002d658  mov     eax, ecx
0x14002d65a  lea     r8, [rax+rax*2]
0x14002d65e  movzx   eax, byte ptr [rdx+r8*8+10h]
0x14002d664  cmp     eax, [r11+8]
0x14002d668  jz      short loc_14002D66E
0x14002d66a  inc     ecx
0x14002d66c  jmp     short loc_14002D654
0x14002d66e  lea     rcx, [rdx+12h]
0x14002d672  mov     al, 1
0x14002d674  lea     rcx, [rcx+r8*8]
0x14002d678  mov     [r10], rcx
0x14002d67b  lea     rcx, [rdx+1Ah]
0x14002d67f  lea     rcx, [rcx+r8*8]
0x14002d683  mov     [r9], rcx
0x14002d686  jmp     short loc_14002D68A
0x14002d688  xor     al, al
0x14002d68a  add     rsp, 20h
0x14002d68e  pop     rbx
0x14002d68f  retn
```
