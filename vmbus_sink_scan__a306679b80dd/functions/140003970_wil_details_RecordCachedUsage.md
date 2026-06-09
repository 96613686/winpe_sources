# wil_details_RecordCachedUsage

- ea: `0x140003970`
- end: `0x140003abe`
- name: `wil_details_RecordCachedUsage`
- size: `334`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140027b20`

## callees

- `0x140003970`
- `0x140017000`

## import_xrefs

- `ntoskrnl!RtlRecordFeatureUsage` at `0x140003a9f`
- `ntoskrnl!RtlRecordFeatureUsage` at `0x140003a9f`

## pseudocode

```c
_DWORD *__fastcall wil_details_RecordCachedUsage(int a1, __int64 a2)
{
  unsigned __int32 v3; // ecx
  int v4; // r8d
  signed __int32 v5; // eax
  signed __int32 v6; // ett
  unsigned int v7; // eax
  char *v8; // rdx
  _DWORD *result; // rax
  _DWORD v10[2]; // [rsp+20h] [rbp-48h] BYREF
  char v11; // [rsp+28h] [rbp-40h] BYREF

  _m_prefetchw((const void *)a2);
  v3 = _InterlockedAnd((volatile signed __int32 *)a2, 0xFFC0401E);
  v4 = (v3 >> 1) & 0xF;
  if ( v4 )
  {
    _m_prefetchw((const void *)(a2 + 4));
    v5 = *(_DWORD *)(a2 + 4);
    do
    {
      v6 = v5;
      v5 = _InterlockedCompareExchange((volatile signed __int32 *)(a2 + 4), v4 | v5, v5);
    }
    while ( v6 != v5 );
    v7 = v4 & ~v5;
  }
  else
  {
    v7 = 0;
  }
  if ( (v7 & 1) != 0 )
  {
    v10[0] = a1;
    v8 = &v11;
    v10[1] = 65538;
  }
  else
  {
    v8 = (char *)v10;
  }
  if ( (v7 & 2) != 0 )
  {
    *(_DWORD *)v8 = a1;
    *((_DWORD *)v8 + 1) = 65542;
    v8 += 8;
  }
  if ( (v7 & 4) != 0 )
  {
    *(_DWORD *)v8 = a1;
    *((_DWORD *)v8 + 1) = 65539;
    v8 += 8;
  }
  if ( v7 >= 8 )
  {
    *(_DWORD *)v8 = a1;
    *((_DWORD *)v8 + 1) = 65543;
    v8 += 8;
  }
  if ( ((v3 >> 5) & 0x1FF) != 0 )
  {
    *(_DWORD *)v8 = a1;
    *((_WORD *)v8 + 3) = (v3 >> 5) & 0x1FF;
    *((_WORD *)v8 + 2) = 4 * ((v3 >> 14) & 1);
    v8 += 8;
  }
  if ( ((v3 >> 15) & 0x7F) != 0 )
  {
    *(_DWORD *)v8 = a1;
    *((_WORD *)v8 + 3) = (v3 >> 15) & 0x7F;
    *((_WORD *)v8 + 2) = 4 * ((v3 >> 22) & 1) + 1;
    v8 += 8;
  }
  result = v10;
  if ( (v8 - (char *)v10) >> 3 > 0 )
    return (_DWORD *)RtlRecordFeatureUsage(v10);
  return result;
}

```

## disassembly

```asm
0x140003970  sub     rsp, 68h
0x140003974  mov     rax, cs:__security_cookie
0x14000397b  xor     rax, rsp
0x14000397e  mov     [rsp+68h+var_18], rax
0x140003983  mov     r9, rdx
0x140003986  mov     r10d, ecx
0x140003989  prefetchw byte ptr [rdx]
0x14000398c  mov     eax, [rdx]
0x14000398e  mov     r8d, eax
0x140003991  and     r8d, 0FFC0401Eh
0x140003998  lock cmpxchg [rdx], r8d
0x14000399d  jnz     short loc_14000398E
0x14000399f  mov     r8d, eax
0x1400039a2  mov     ecx, eax
0x1400039a4  shr     r8d, 1
0x1400039a7  and     r8d, 0Fh
0x1400039ab  jz      short loc_1400039C8
0x1400039ad  prefetchw byte ptr [rdx+4]
0x1400039b1  mov     eax, [rdx+4]
0x1400039b4  mov     edx, eax
0x1400039b6  or      edx, r8d
0x1400039b9  lock cmpxchg [r9+4], edx
0x1400039bf  jnz     short loc_1400039B4
0x1400039c1  not     eax
0x1400039c3  and     eax, r8d
0x1400039c6  jmp     short loc_1400039CB
0x1400039c8  mov     eax, r8d
0x1400039cb  mov     r8d, 2
0x1400039d1  lea     r9d, [r8-1]
0x1400039d5  test    r9b, al
0x1400039d8  jz      short loc_1400039EE
0x1400039da  mov     [rsp+68h+var_48], r10d
0x1400039df  lea     rdx, [rsp+68h+var_40]
0x1400039e4  mov     [rsp+68h+var_44], 10002h
0x1400039ec  jmp     short loc_1400039F3
0x1400039ee  lea     rdx, [rsp+68h+var_48]
0x1400039f3  test    r8b, al
0x1400039f6  jz      short loc_140003A06
0x1400039f8  mov     [rdx], r10d
0x1400039fb  mov     dword ptr [rdx+4], 10006h
0x140003a02  add     rdx, 8
0x140003a06  test    al, 4
0x140003a08  jz      short loc_140003A18
0x140003a0a  mov     [rdx], r10d
0x140003a0d  mov     dword ptr [rdx+4], 10003h
0x140003a14  add     rdx, 8
0x140003a18  cmp     eax, 8
0x140003a1b  jb      short loc_140003A2B
0x140003a1d  mov     [rdx], r10d
0x140003a20  mov     dword ptr [rdx+4], 10007h
0x140003a27  add     rdx, 8
0x140003a2b  mov     r8d, ecx
0x140003a2e  mov     r11d, 1FFh
0x140003a34  shr     r8d, 5
0x140003a38  test    r11d, r8d
0x140003a3b  jz      short loc_140003A5E
0x140003a3d  and     r8w, r11w
0x140003a41  mov     [rdx], r10d
0x140003a44  mov     eax, ecx
0x140003a46  mov     [rdx+6], r8w
0x140003a4b  shr     eax, 0Eh
0x140003a4e  and     ax, r9w
0x140003a52  shl     ax, 2
0x140003a56  mov     [rdx+4], ax
0x140003a5a  add     rdx, 8
0x140003a5e  mov     eax, ecx
0x140003a60  shr     eax, 0Fh
0x140003a63  test    al, 7Fh
0x140003a65  jz      short loc_140003A89
0x140003a67  shr     ecx, 16h
0x140003a6a  and     ax, 7Fh
0x140003a6e  and     cx, r9w
0x140003a72  mov     [rdx], r10d
0x140003a75  shl     cx, 2
0x140003a79  add     cx, r9w
0x140003a7d  mov     [rdx+6], ax
0x140003a81  mov     [rdx+4], cx
0x140003a85  add     rdx, 8
0x140003a89  lea     rax, [rsp+68h+var_48]
0x140003a8e  sub     rdx, rax
0x140003a91  sar     rdx, 3
0x140003a95  test    rdx, rdx
0x140003a98  jle     short loc_140003AAB
0x140003a9a  lea     rcx, [rsp+68h+var_48]
0x140003a9f  call    cs:__imp_RtlRecordFeatureUsage
0x140003aa6  nop     dword ptr [rax+rax+00h]
0x140003aab  mov     rcx, [rsp+68h+var_18]
0x140003ab0  xor     rcx, rsp; StackCookie
0x140003ab3  call    __security_check_cookie
0x140003ab8  add     rsp, 68h
0x140003abc  retn
```
