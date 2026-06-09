# wil_details_RecordCachedUsage

- ea: `0x140001d98`
- end: `0x140001edf`
- name: `wil_details_RecordCachedUsage`
- size: `327`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14000a5f0`

## callees

- `0x140001d98`
- `0x140001fe4`
- `0x140002bb0`

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
    return (_DWORD *)wil_details_RtlRecordFeatureUsage(v10);
  return result;
}

```

## disassembly

```asm
0x140001d98  sub     rsp, 68h
0x140001d9c  mov     rax, cs:__security_cookie
0x140001da3  xor     rax, rsp
0x140001da6  mov     [rsp+68h+var_18], rax
0x140001dab  mov     r9, rdx
0x140001dae  mov     r10d, ecx
0x140001db1  prefetchw byte ptr [rdx]
0x140001db4  mov     eax, [rdx]
0x140001db6  mov     r8d, eax
0x140001db9  and     r8d, 0FFC0401Eh
0x140001dc0  lock cmpxchg [rdx], r8d
0x140001dc5  jnz     short loc_140001DB6
0x140001dc7  mov     r8d, eax
0x140001dca  mov     ecx, eax
0x140001dcc  shr     r8d, 1
0x140001dcf  and     r8d, 0Fh
0x140001dd3  jz      short loc_140001DF0
0x140001dd5  prefetchw byte ptr [rdx+4]
0x140001dd9  mov     eax, [rdx+4]
0x140001ddc  mov     edx, eax
0x140001dde  or      edx, r8d
0x140001de1  lock cmpxchg [r9+4], edx
0x140001de7  jnz     short loc_140001DDC
0x140001de9  not     eax
0x140001deb  and     eax, r8d
0x140001dee  jmp     short loc_140001DF3
0x140001df0  mov     eax, r8d
0x140001df3  mov     r8d, 2
0x140001df9  lea     r9d, [r8-1]
0x140001dfd  test    r9b, al
0x140001e00  jz      short loc_140001E16
0x140001e02  mov     [rsp+68h+var_48], r10d
0x140001e07  lea     rdx, [rsp+68h+var_40]
0x140001e0c  mov     [rsp+68h+var_44], 10002h
0x140001e14  jmp     short loc_140001E1B
0x140001e16  lea     rdx, [rsp+68h+var_48]
0x140001e1b  test    r8b, al
0x140001e1e  jz      short loc_140001E2E
0x140001e20  mov     [rdx], r10d
0x140001e23  mov     dword ptr [rdx+4], 10006h
0x140001e2a  add     rdx, 8
0x140001e2e  test    al, 4
0x140001e30  jz      short loc_140001E40
0x140001e32  mov     [rdx], r10d
0x140001e35  mov     dword ptr [rdx+4], 10003h
0x140001e3c  add     rdx, 8
0x140001e40  cmp     eax, 8
0x140001e43  jb      short loc_140001E53
0x140001e45  mov     [rdx], r10d
0x140001e48  mov     dword ptr [rdx+4], 10007h
0x140001e4f  add     rdx, 8
0x140001e53  mov     r8d, ecx
0x140001e56  mov     r11d, 1FFh
0x140001e5c  shr     r8d, 5
0x140001e60  test    r11d, r8d
0x140001e63  jz      short loc_140001E86
0x140001e65  and     r8w, r11w
0x140001e69  mov     [rdx], r10d
0x140001e6c  mov     eax, ecx
0x140001e6e  mov     [rdx+6], r8w
0x140001e73  shr     eax, 0Eh
0x140001e76  and     ax, r9w
0x140001e7a  shl     ax, 2
0x140001e7e  mov     [rdx+4], ax
0x140001e82  add     rdx, 8
0x140001e86  mov     eax, ecx
0x140001e88  shr     eax, 0Fh
0x140001e8b  test    al, 7Fh
0x140001e8d  jz      short loc_140001EB1
0x140001e8f  shr     ecx, 16h
0x140001e92  and     ax, 7Fh
0x140001e96  and     cx, r9w
0x140001e9a  mov     [rdx], r10d
0x140001e9d  shl     cx, 2
0x140001ea1  add     cx, r9w
0x140001ea5  mov     [rdx+6], ax
0x140001ea9  mov     [rdx+4], cx
0x140001ead  add     rdx, 8
0x140001eb1  lea     rax, [rsp+68h+var_48]
0x140001eb6  sub     rdx, rax
0x140001eb9  sar     rdx, 3
0x140001ebd  test    rdx, rdx
0x140001ec0  jle     short loc_140001ECC
0x140001ec2  lea     rcx, [rsp+68h+var_48]
0x140001ec7  call    wil_details_RtlRecordFeatureUsage
0x140001ecc  mov     rcx, [rsp+68h+var_18]
0x140001ed1  xor     rcx, rsp; StackCookie
0x140001ed4  call    __security_check_cookie
0x140001ed9  add     rsp, 68h
0x140001edd  retn
```
