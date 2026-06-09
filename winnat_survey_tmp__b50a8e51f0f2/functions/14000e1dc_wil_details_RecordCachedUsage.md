# wil_details_RecordCachedUsage

- ea: `0x14000e1dc`
- end: `0x14000e32a`
- name: `wil_details_RecordCachedUsage`
- size: `334`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14002f140`

## callees

- `0x14000e1dc`
- `0x14001ede0`

## import_xrefs

- `ntoskrnl!RtlRecordFeatureUsage` at `0x14000e30b`
- `ntoskrnl!RtlRecordFeatureUsage` at `0x14000e30b`

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
0x14000e1dc  sub     rsp, 68h
0x14000e1e0  mov     rax, cs:__security_cookie
0x14000e1e7  xor     rax, rsp
0x14000e1ea  mov     [rsp+68h+var_18], rax
0x14000e1ef  mov     r9, rdx
0x14000e1f2  mov     r10d, ecx
0x14000e1f5  prefetchw byte ptr [rdx]
0x14000e1f8  mov     eax, [rdx]
0x14000e1fa  mov     r8d, eax
0x14000e1fd  and     r8d, 0FFC0401Eh
0x14000e204  lock cmpxchg [rdx], r8d
0x14000e209  jnz     short loc_14000E1FA
0x14000e20b  mov     r8d, eax
0x14000e20e  mov     ecx, eax
0x14000e210  shr     r8d, 1
0x14000e213  and     r8d, 0Fh
0x14000e217  jz      short loc_14000E234
0x14000e219  prefetchw byte ptr [rdx+4]
0x14000e21d  mov     eax, [rdx+4]
0x14000e220  mov     edx, eax
0x14000e222  or      edx, r8d
0x14000e225  lock cmpxchg [r9+4], edx
0x14000e22b  jnz     short loc_14000E220
0x14000e22d  not     eax
0x14000e22f  and     eax, r8d
0x14000e232  jmp     short loc_14000E237
0x14000e234  mov     eax, r8d
0x14000e237  mov     r8d, 2
0x14000e23d  lea     r9d, [r8-1]
0x14000e241  test    r9b, al
0x14000e244  jz      short loc_14000E25A
0x14000e246  mov     [rsp+68h+var_48], r10d
0x14000e24b  lea     rdx, [rsp+68h+var_40]
0x14000e250  mov     [rsp+68h+var_44], 10002h
0x14000e258  jmp     short loc_14000E25F
0x14000e25a  lea     rdx, [rsp+68h+var_48]
0x14000e25f  test    r8b, al
0x14000e262  jz      short loc_14000E272
0x14000e264  mov     [rdx], r10d
0x14000e267  mov     dword ptr [rdx+4], 10006h
0x14000e26e  add     rdx, 8
0x14000e272  test    al, 4
0x14000e274  jz      short loc_14000E284
0x14000e276  mov     [rdx], r10d
0x14000e279  mov     dword ptr [rdx+4], 10003h
0x14000e280  add     rdx, 8
0x14000e284  cmp     eax, 8
0x14000e287  jb      short loc_14000E297
0x14000e289  mov     [rdx], r10d
0x14000e28c  mov     dword ptr [rdx+4], 10007h
0x14000e293  add     rdx, 8
0x14000e297  mov     r8d, ecx
0x14000e29a  mov     r11d, 1FFh
0x14000e2a0  shr     r8d, 5
0x14000e2a4  test    r11d, r8d
0x14000e2a7  jz      short loc_14000E2CA
0x14000e2a9  and     r8w, r11w
0x14000e2ad  mov     [rdx], r10d
0x14000e2b0  mov     eax, ecx
0x14000e2b2  mov     [rdx+6], r8w
0x14000e2b7  shr     eax, 0Eh
0x14000e2ba  and     ax, r9w
0x14000e2be  shl     ax, 2
0x14000e2c2  mov     [rdx+4], ax
0x14000e2c6  add     rdx, 8
0x14000e2ca  mov     eax, ecx
0x14000e2cc  shr     eax, 0Fh
0x14000e2cf  test    al, 7Fh
0x14000e2d1  jz      short loc_14000E2F5
0x14000e2d3  shr     ecx, 16h
0x14000e2d6  and     ax, 7Fh
0x14000e2da  and     cx, r9w
0x14000e2de  mov     [rdx], r10d
0x14000e2e1  shl     cx, 2
0x14000e2e5  add     cx, r9w
0x14000e2e9  mov     [rdx+6], ax
0x14000e2ed  mov     [rdx+4], cx
0x14000e2f1  add     rdx, 8
0x14000e2f5  lea     rax, [rsp+68h+var_48]
0x14000e2fa  sub     rdx, rax
0x14000e2fd  sar     rdx, 3
0x14000e301  test    rdx, rdx
0x14000e304  jle     short loc_14000E317
0x14000e306  lea     rcx, [rsp+68h+var_48]
0x14000e30b  call    cs:__imp_RtlRecordFeatureUsage
0x14000e312  nop     dword ptr [rax+rax+00h]
0x14000e317  mov     rcx, [rsp+68h+var_18]
0x14000e31c  xor     rcx, rsp; StackCookie
0x14000e31f  call    __security_check_cookie
0x14000e324  add     rsp, 68h
0x14000e328  retn
```
