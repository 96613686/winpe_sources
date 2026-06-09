# WcInsertDirectoryTableSourceList

- ea: `0x14001ea78`
- end: `0x14001ead3`
- name: `WcInsertDirectoryTableSourceList`
- size: `91`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14002a614`

## callees

- `0x14001e94c`
- `0x14001ea78`

## pseudocode

```c
__int64 __fastcall WcInsertDirectoryTableSourceList(__int64 **a1, const UNICODE_STRING *a2)
{
  int inserted; // ecx
  __int64 *i; // rbx

  inserted = 0;
  for ( i = *a1; i != (__int64 *)a1; i = (__int64 *)*i )
  {
    if ( (i[4] & 1) != 0 )
    {
      inserted = WcInsertDirectoryTableEntry(*(_QWORD *)(i[3] + 32), a2, i[3]);
      if ( inserted < 0 )
        return (unsigned int)inserted;
      *((_DWORD *)i + 8) &= ~1u;
    }
  }
  return (unsigned int)inserted;
}

```

## disassembly

```asm
0x14001ea78  mov     [rsp+arg_0], rbx
0x14001ea7d  mov     [rsp+arg_8], rsi
0x14001ea82  push    rdi
0x14001ea83  sub     rsp, 20h
0x14001ea87  mov     rdi, rcx
0x14001ea8a  mov     rsi, rdx
0x14001ea8d  xor     ecx, ecx
0x14001ea8f  mov     rbx, [rdi]
0x14001ea92  jmp     short loc_14001EABB
0x14001ea94  mov     eax, [rbx+20h]
0x14001ea97  test    al, 1
0x14001ea99  jz      short loc_14001EAB8
0x14001ea9b  mov     rcx, [rbx+18h]
0x14001ea9f  mov     rdx, rsi
0x14001eaa2  mov     r8, rcx
0x14001eaa5  mov     rcx, [rcx+20h]
0x14001eaa9  call    WcInsertDirectoryTableEntry
0x14001eaae  mov     ecx, eax
0x14001eab0  test    eax, eax
0x14001eab2  js      short loc_14001EAC0
0x14001eab4  and     dword ptr [rbx+20h], 0FFFFFFFEh
0x14001eab8  mov     rbx, [rbx]
0x14001eabb  cmp     rbx, rdi
0x14001eabe  jnz     short loc_14001EA94
0x14001eac0  mov     rbx, [rsp+28h+arg_0]
0x14001eac5  mov     eax, ecx
0x14001eac7  mov     rsi, [rsp+28h+arg_8]
0x14001eacc  add     rsp, 20h
0x14001ead0  pop     rdi
0x14001ead1  retn
```
