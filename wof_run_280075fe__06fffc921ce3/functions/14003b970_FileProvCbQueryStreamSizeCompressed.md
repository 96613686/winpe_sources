# FileProvCbQueryStreamSizeCompressed

- ea: `0x14003b970`
- end: `0x14003b9be`
- name: `FileProvCbQueryStreamSizeCompressed`
- size: `78`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140023150`
- `0x14003b970`

## pseudocode

```c
__int64 __fastcall FileProvCbQueryStreamSizeCompressed(__int64 a1, __int64 *a2, char a3)
{
  _DWORD *v3; // rax
  __int64 v5; // rdx

  v3 = *(_DWORD **)(a1 + 24);
  if ( v3 )
  {
    v5 = -(__int64)(unsigned int)*v3 & (*(_QWORD *)(a1 + 16) + (unsigned int)(*v3 - 1));
    if ( !a3 )
    {
      *a2 = v5;
      return 0;
    }
  }
  else
  {
    if ( !a3 )
    {
      *a2 = *(_QWORD *)(a1 + 16);
      return 0;
    }
    v5 = *(_QWORD *)(a1 + 16);
  }
  RtlWriteULong64ToUser(a2, v5);
  return 0;
}

```

## disassembly

```asm
0x14003b970  sub     rsp, 28h
0x14003b974  mov     rax, [rcx+18h]
0x14003b978  mov     r10, rdx
0x14003b97b  test    rax, rax
0x14003b97e  jz      short loc_14003B9AB
0x14003b980  mov     r9d, [rax]
0x14003b983  lea     edx, [r9-1]
0x14003b987  neg     r9
0x14003b98a  add     rdx, [rcx+10h]
0x14003b98e  and     rdx, r9
0x14003b991  test    r8b, r8b
0x14003b994  jz      short loc_14003B9A6
0x14003b996  mov     rcx, r10
0x14003b999  call    RtlWriteULong64ToUser
0x14003b99e  xor     eax, eax
0x14003b9a0  add     rsp, 28h
0x14003b9a4  retn
0x14003b9a6  mov     [r10], rdx
0x14003b9a9  jmp     short loc_14003B99E
0x14003b9ab  mov     rax, [rcx+10h]
0x14003b9af  test    r8b, r8b
0x14003b9b2  jz      short loc_14003B9B9
0x14003b9b4  mov     rdx, rax
0x14003b9b7  jmp     short loc_14003B996
0x14003b9b9  mov     [rdx], rax
0x14003b9bc  jmp     short loc_14003B99E
```
