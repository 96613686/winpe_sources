# FilterSendNetBufferListsComplete

- ea: `0x14000a850`
- end: `0x14000a878`
- name: `FilterSendNetBufferListsComplete`
- size: `40`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x14000a850`
- `0x14000a880`
- `0x14000ab50`

## pseudocode

```c
void __fastcall FilterSendNetBufferListsComplete(__int64 a1, struct _NET_BUFFER_LIST *a2, unsigned int a3)
{
  if ( *(_BYTE *)(a1 + 2682) )
    FilterSendNetBufferListsCompleteWDI(a2, a3);
  else
    FilterSendNetBufferListsCompleteLegacy(a1, a2, a3);
}

```

## disassembly

```asm
0x14000a850  sub     rsp, 28h
0x14000a854  cmp     byte ptr [rcx+0A7Ah], 0
0x14000a85b  mov     rax, rdx
0x14000a85e  jz      short loc_14000A871
0x14000a860  mov     edx, r8d
0x14000a863  mov     rcx, rax; NetBufferList
0x14000a866  call    FilterSendNetBufferListsCompleteWDI
0x14000a86b  add     rsp, 28h
0x14000a86f  retn
0x14000a871  call    FilterSendNetBufferListsCompleteLegacy
0x14000a876  jmp     short loc_14000A86B
```
