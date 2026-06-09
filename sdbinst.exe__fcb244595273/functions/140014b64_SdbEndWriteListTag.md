# SdbEndWriteListTag

- ea: `0x140014b64`
- end: `0x140014d09`
- name: `SdbEndWriteListTag`
- size: `421`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `8`
- callee_count: `6`
- tags: ``

## callers

- `0x140014574`
- `0x1400147d0`
- `0x1400153a4`
- `0x140019410`
- `0x14001c730`
- `0x14001d808`
- `0x14001fc0c`
- `0x1400207cc`

## callees

- `0x14001008c`
- `0x140014380`
- `0x140014b64`
- `0x14001561c`
- `0x140016148`
- `0x140018d48`

## string_xrefs

- `0x140014be5`: `Failed to write the data`
- `0x140014b9f`: `SdbEndWriteListTag`
- `0x140014ce5`: `SdbEndWriteListTag`

## pseudocode

```c
__int64 __fastcall SdbEndWriteListTag(__int64 a1, __int64 a2)
{
  unsigned int v2; // esi
  __int64 v5; // rbp
  __int64 v6; // r8
  unsigned int FirstTag; // eax
  __int64 v8; // rax
  bool v9; // zf
  __int64 v10; // rdx
  __int64 v11; // [rsp+30h] [rbp-28h] BYREF
  unsigned int v12; // [rsp+38h] [rbp-20h]
  int v13; // [rsp+70h] [rbp+18h] BYREF

  v2 = a2;
  if ( (SdbGetTagFromTagID(a1, a2) & 0xF000) != 0x7000 )
  {
    AslLogCallPrintf(1, "SdbEndWriteListTag", 402, "This is not a list tag");
    return 0;
  }
  v13 = *(_DWORD *)(a1 + 20) - v2 - 6;
  if ( !(unsigned int)SdbpWriteBufferedData(a1, v2 + 2, &v13, 4, 0) )
  {
    AslLogCallPrintf(1, "SdbEndWriteListTag", 413, "Failed to write the data");
    return 0;
  }
  v5 = 0;
  if ( !*(_DWORD *)(a1 + 2636) )
    return 1;
  while ( 1 )
  {
    if ( *(_WORD *)(a1 + 40 * v5 + 52) != (unsigned __int16)SdbGetTagFromTagID(a1, v2)
      || !*(_DWORD *)(a1 + 40 * v5 + 56) )
    {
      goto LABEL_17;
    }
    v6 = *(unsigned __int16 *)(a1 + 40 * v5 + 54);
    v11 = 0;
    FirstTag = SdbFindFirstTag(a1, v2, v6);
    v8 = FirstTag ? SdbpTagToKey(a1, FirstTag, *(unsigned int *)(a1 + 40 * v5 + 80)) : 0LL;
    v9 = *(_DWORD *)(a1 + 40 * v5 + 60) == 0;
    v11 = v8;
    v12 = v2;
    if ( v9 )
      break;
    if ( *(_QWORD *)(a1 + 40 * v5 + 64) != v8 )
    {
      *(_QWORD *)(a1 + 40 * v5 + 64) = v8;
      break;
    }
LABEL_17:
    v5 = (unsigned int)(v5 + 1);
    if ( (unsigned int)v5 >= *(_DWORD *)(a1 + 2636) )
      return 1;
  }
  v10 = *(unsigned int *)(a1 + 40 * v5 + 72);
  if ( (_DWORD)v10 != *(_DWORD *)(a1 + 40 * v5 + 76) )
  {
    SdbpWriteBufferedData(a1, v10, &v11, 12, 0);
    *(_DWORD *)(a1 + 40 * v5 + 72) += 12;
    goto LABEL_17;
  }
  AslLogCallPrintf(
    1,
    "SdbEndWriteListTag",
    480,
    "Too many index entries for tag %04x, key %04x",
    *(unsigned __int16 *)(a1 + 40 * v5 + 52),
    *(unsigned __int16 *)(a1 + 40 * v5 + 54));
  return 0;
}

```

## disassembly

```asm
0x140014b64  mov     [rsp+arg_0], rbx
0x140014b69  mov     [rsp+arg_8], rbp
0x140014b6e  push    rsi
0x140014b6f  push    rdi
0x140014b70  push    r14
0x140014b72  sub     rsp, 40h
0x140014b76  mov     esi, edx
0x140014b78  mov     rbx, rcx
0x140014b7b  call    SdbGetTagFromTagID
0x140014b80  mov     ecx, 0F000h
0x140014b85  and     ax, cx
0x140014b88  mov     ecx, 7000h
0x140014b8d  cmp     ax, cx
0x140014b90  jz      short loc_140014BB7
0x140014b92  lea     r9, aThisIsNotAList; "This is not a list tag"
0x140014b99  mov     r8d, 192h
0x140014b9f  lea     rdx, aSdbendwritelis_3; "SdbEndWriteListTag"
0x140014ba6  mov     ecx, 1
0x140014bab  call    AslLogCallPrintf
0x140014bb0  xor     eax, eax
0x140014bb2  jmp     loc_140014CC1
0x140014bb7  mov     eax, [rbx+14h]
0x140014bba  lea     edx, [rsi+2]
0x140014bbd  sub     eax, esi
0x140014bbf  mov     [rsp+58h+var_38], 0
0x140014bc7  sub     eax, 6
0x140014bca  lea     r8, [rsp+58h+arg_10]
0x140014bcf  mov     r9d, 4
0x140014bd5  mov     [rsp+58h+arg_10], eax
0x140014bd9  mov     rcx, rbx
0x140014bdc  call    SdbpWriteBufferedData
0x140014be1  test    eax, eax
0x140014be3  jnz     short loc_140014BF4
0x140014be5  lea     r9, aFailedToWriteT_0; "Failed to write the data"
0x140014bec  mov     r8d, 19Dh
0x140014bf2  jmp     short loc_140014B9F
0x140014bf4  xor     ebp, ebp
0x140014bf6  cmp     [rbx+0A4Ch], ebp
0x140014bfc  jbe     loc_140014CBC
0x140014c02  mov     edx, esi
0x140014c04  mov     rcx, rbx
0x140014c07  call    SdbGetTagFromTagID
0x140014c0c  lea     rdi, ds:0[rbp*4]
0x140014c14  add     rdi, rbp
0x140014c17  cmp     [rbx+rdi*8+34h], ax
0x140014c1c  jnz     loc_140014CAE
0x140014c22  cmp     dword ptr [rbx+rdi*8+38h], 0
0x140014c27  jz      loc_140014CAE
0x140014c2d  movzx   r8d, word ptr [rbx+rdi*8+36h]
0x140014c33  mov     edx, esi
0x140014c35  mov     rcx, rbx
0x140014c38  mov     [rsp+58h+var_28], 0
0x140014c41  call    SdbFindFirstTag
0x140014c46  test    eax, eax
0x140014c48  jz      short loc_140014C66
0x140014c4a  lea     r8, ds:0[rbp*4]
0x140014c52  mov     edx, eax
0x140014c54  add     r8, rbp
0x140014c57  mov     rcx, rbx
0x140014c5a  mov     r8d, [rbx+r8*8+50h]
0x140014c5f  call    SdbpTagToKey
0x140014c64  jmp     short loc_140014C68
0x140014c66  xor     eax, eax
0x140014c68  cmp     dword ptr [rbx+rdi*8+3Ch], 0
0x140014c6d  mov     [rsp+58h+var_28], rax
0x140014c72  mov     [rsp+58h+var_20], esi
0x140014c76  jz      short loc_140014C84
0x140014c78  cmp     [rbx+rdi*8+40h], rax
0x140014c7d  jz      short loc_140014CAE
0x140014c7f  mov     [rbx+rdi*8+40h], rax
0x140014c84  mov     edx, [rbx+rdi*8+48h]
0x140014c88  cmp     edx, [rbx+rdi*8+4Ch]
0x140014c8c  jz      short loc_140014CD4
0x140014c8e  mov     r9d, 0Ch
0x140014c94  mov     [rsp+58h+var_38], 0
0x140014c9c  lea     r8, [rsp+58h+var_28]
0x140014ca1  mov     rcx, rbx
0x140014ca4  call    SdbpWriteBufferedData
0x140014ca9  add     dword ptr [rbx+rdi*8+48h], 0Ch
0x140014cae  inc     ebp
0x140014cb0  cmp     ebp, [rbx+0A4Ch]
0x140014cb6  jb      loc_140014C02
0x140014cbc  mov     eax, 1
0x140014cc1  mov     rbx, [rsp+58h+arg_0]
0x140014cc6  mov     rbp, [rsp+58h+arg_8]
0x140014ccb  add     rsp, 40h
0x140014ccf  pop     r14
0x140014cd1  pop     rdi
0x140014cd2  pop     rsi
0x140014cd3  retn
0x140014cd4  movzx   ecx, word ptr [rbx+rdi*8+34h]
0x140014cd9  lea     r9, aTooManyIndexEn; "Too many index entries for tag %04x, ke"...
0x140014ce0  movzx   eax, word ptr [rbx+rdi*8+36h]
0x140014ce5  lea     rdx, aSdbendwritelis_3; "SdbEndWriteListTag"
0x140014cec  mov     [rsp+58h+var_30], eax
0x140014cf0  mov     r8d, 1E0h
0x140014cf6  mov     [rsp+58h+var_38], ecx
0x140014cfa  mov     ecx, 1
0x140014cff  call    AslLogCallPrintf
0x140014d04  jmp     loc_140014BB0
```
