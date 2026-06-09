# FreeFilterHashTable

- ea: `0x14000aad0`
- end: `0x14000ab56`
- name: `FreeFilterHashTable`
- size: `134`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x14000b34c`
- `0x14000c55c`

## callees

- `0x140001118`
- `0x14000164c`
- `0x140001a70`
- `0x14000aad0`

## pseudocode

```c
ULONG __fastcall FreeFilterHashTable(__int64 a1, __int64 a2, __int64 a3)
{
  _QWORD *v3; // rbx
  __int64 v4; // rdx
  __int64 v5; // r8
  __int64 i; // rsi
  _QWORD *v7; // rdi
  _QWORD *v8; // rbp
  __int64 v9; // rdx

  v3 = P;
  DbgTrace(2, "UevFilter.FreeHandleHashTable: Entry\n", a3);
  if ( v3 )
  {
    for ( i = 0; (unsigned int)i < *((_DWORD *)v3 + 4); i = (unsigned int)(i + 1) )
    {
      v7 = (_QWORD *)v3[i + 3];
      while ( v7 )
      {
        v8 = v7;
        v7 = (_QWORD *)*v7;
        v9 = v8[2];
        if ( v9 )
          ((void (__fastcall *)(_QWORD *))v3[1])(v3);
        FreeGenericBuffer(v8, v9, v5);
      }
    }
    FreeGenericBuffer(v3, v4, v5);
  }
  return DbgTrace(2, "UevFilter.FreeHandleHashTable: Exit\n", v5);
}

```

## disassembly

```asm
0x14000aad0  push    rbx
0x14000aad2  push    rbp
0x14000aad3  push    rsi
0x14000aad4  push    rdi
0x14000aad5  sub     rsp, 28h
0x14000aad9  mov     rbx, cs:P
0x14000aae0  lea     rdx, aUevfilterFreeh; "UevFilter.FreeHandleHashTable: Entry\n"
0x14000aae7  mov     ecx, 2
0x14000aaec  call    DbgTrace
0x14000aaf1  test    rbx, rbx
0x14000aaf4  jz      short loc_14000AB3B
0x14000aaf6  xor     esi, esi
0x14000aaf8  cmp     [rbx+10h], esi
0x14000aafb  jbe     short loc_14000AB33
0x14000aafd  mov     rdi, [rbx+rsi*8+18h]
0x14000ab02  jmp     short loc_14000AB27
0x14000ab04  mov     rbp, rdi
0x14000ab07  mov     rdi, [rdi]
0x14000ab0a  mov     rdx, [rbp+10h]
0x14000ab0e  test    rdx, rdx
0x14000ab11  jz      short loc_14000AB1F
0x14000ab13  mov     rax, [rbx+8]
0x14000ab17  mov     rcx, rbx
0x14000ab1a  call    _guard_dispatch_icall
0x14000ab1f  mov     rcx, rbp; P
0x14000ab22  call    FreeGenericBuffer
0x14000ab27  test    rdi, rdi
0x14000ab2a  jnz     short loc_14000AB04
0x14000ab2c  inc     esi
0x14000ab2e  cmp     esi, [rbx+10h]
0x14000ab31  jb      short loc_14000AAFD
0x14000ab33  mov     rcx, rbx; P
0x14000ab36  call    FreeGenericBuffer
0x14000ab3b  lea     rdx, aUevfilterFreeh_0; "UevFilter.FreeHandleHashTable: Exit\n"
0x14000ab42  mov     ecx, 2
0x14000ab47  call    DbgTrace
0x14000ab4c  add     rsp, 28h
0x14000ab50  pop     rdi
0x14000ab51  pop     rsi
0x14000ab52  pop     rbp
0x14000ab53  pop     rbx
0x14000ab54  retn
```
