# wil_details_RecordCachedUsage

- ea: `0x140003c88`
- end: `0x140003dd6`
- name: `wil_details_RecordCachedUsage`
- size: `334`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140017de0`

## callees

- `0x140003c88`
- `0x1400050b0`

## import_xrefs

- `ntoskrnl!RtlRecordFeatureUsage` at `0x140003db7`
- `ntoskrnl!RtlRecordFeatureUsage` at `0x140003db7`

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
0x140003c88  sub     rsp, 68h
0x140003c8c  mov     rax, cs:__security_cookie
0x140003c93  xor     rax, rsp
0x140003c96  mov     [rsp+68h+var_18], rax
0x140003c9b  mov     r9, rdx
0x140003c9e  mov     r10d, ecx
0x140003ca1  prefetchw byte ptr [rdx]
0x140003ca4  mov     eax, [rdx]
0x140003ca6  mov     r8d, eax
0x140003ca9  and     r8d, 0FFC0401Eh
0x140003cb0  lock cmpxchg [rdx], r8d
0x140003cb5  jnz     short loc_140003CA6
0x140003cb7  mov     r8d, eax
0x140003cba  mov     ecx, eax
0x140003cbc  shr     r8d, 1
0x140003cbf  and     r8d, 0Fh
0x140003cc3  jz      short loc_140003CE0
0x140003cc5  prefetchw byte ptr [rdx+4]
0x140003cc9  mov     eax, [rdx+4]
0x140003ccc  mov     edx, eax
0x140003cce  or      edx, r8d
0x140003cd1  lock cmpxchg [r9+4], edx
0x140003cd7  jnz     short loc_140003CCC
0x140003cd9  not     eax
0x140003cdb  and     eax, r8d
0x140003cde  jmp     short loc_140003CE3
0x140003ce0  mov     eax, r8d
0x140003ce3  mov     r8d, 2
0x140003ce9  lea     r9d, [r8-1]
0x140003ced  test    r9b, al
0x140003cf0  jz      short loc_140003D06
0x140003cf2  mov     [rsp+68h+var_48], r10d
0x140003cf7  lea     rdx, [rsp+68h+var_40]
0x140003cfc  mov     [rsp+68h+var_44], 10002h
0x140003d04  jmp     short loc_140003D0B
0x140003d06  lea     rdx, [rsp+68h+var_48]
0x140003d0b  test    r8b, al
0x140003d0e  jz      short loc_140003D1E
0x140003d10  mov     [rdx], r10d
0x140003d13  mov     dword ptr [rdx+4], 10006h
0x140003d1a  add     rdx, 8
0x140003d1e  test    al, 4
0x140003d20  jz      short loc_140003D30
0x140003d22  mov     [rdx], r10d
0x140003d25  mov     dword ptr [rdx+4], 10003h
0x140003d2c  add     rdx, 8
0x140003d30  cmp     eax, 8
0x140003d33  jb      short loc_140003D43
0x140003d35  mov     [rdx], r10d
0x140003d38  mov     dword ptr [rdx+4], 10007h
0x140003d3f  add     rdx, 8
0x140003d43  mov     r8d, ecx
0x140003d46  mov     r11d, 1FFh
0x140003d4c  shr     r8d, 5
0x140003d50  test    r11d, r8d
0x140003d53  jz      short loc_140003D76
0x140003d55  and     r8w, r11w
0x140003d59  mov     [rdx], r10d
0x140003d5c  mov     eax, ecx
0x140003d5e  mov     [rdx+6], r8w
0x140003d63  shr     eax, 0Eh
0x140003d66  and     ax, r9w
0x140003d6a  shl     ax, 2
0x140003d6e  mov     [rdx+4], ax
0x140003d72  add     rdx, 8
0x140003d76  mov     eax, ecx
0x140003d78  shr     eax, 0Fh
0x140003d7b  test    al, 7Fh
0x140003d7d  jz      short loc_140003DA1
0x140003d7f  shr     ecx, 16h
0x140003d82  and     ax, 7Fh
0x140003d86  and     cx, r9w
0x140003d8a  mov     [rdx], r10d
0x140003d8d  shl     cx, 2
0x140003d91  add     cx, r9w
0x140003d95  mov     [rdx+6], ax
0x140003d99  mov     [rdx+4], cx
0x140003d9d  add     rdx, 8
0x140003da1  lea     rax, [rsp+68h+var_48]
0x140003da6  sub     rdx, rax
0x140003da9  sar     rdx, 3
0x140003dad  test    rdx, rdx
0x140003db0  jle     short loc_140003DC3
0x140003db2  lea     rcx, [rsp+68h+var_48]
0x140003db7  call    cs:__imp_RtlRecordFeatureUsage
0x140003dbe  nop     dword ptr [rax+rax+00h]
0x140003dc3  mov     rcx, [rsp+68h+var_18]
0x140003dc8  xor     rcx, rsp; StackCookie
0x140003dcb  call    __security_check_cookie
0x140003dd0  add     rsp, 68h
0x140003dd4  retn
```
