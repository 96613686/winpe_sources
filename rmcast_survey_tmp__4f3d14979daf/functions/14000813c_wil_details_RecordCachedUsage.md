# wil_details_RecordCachedUsage

- ea: `0x14000813c`
- end: `0x14000828a`
- name: `wil_details_RecordCachedUsage`
- size: `334`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140036990`

## callees

- `0x14000813c`
- `0x14001cdf0`

## import_xrefs

- `ntoskrnl!RtlRecordFeatureUsage` at `0x14000826b`
- `ntoskrnl!RtlRecordFeatureUsage` at `0x14000826b`

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
0x14000813c  sub     rsp, 68h
0x140008140  mov     rax, cs:__security_cookie
0x140008147  xor     rax, rsp
0x14000814a  mov     [rsp+68h+var_18], rax
0x14000814f  mov     r9, rdx
0x140008152  mov     r10d, ecx
0x140008155  prefetchw byte ptr [rdx]
0x140008158  mov     eax, [rdx]
0x14000815a  mov     r8d, eax
0x14000815d  and     r8d, 0FFC0401Eh
0x140008164  lock cmpxchg [rdx], r8d
0x140008169  jnz     short loc_14000815A
0x14000816b  mov     r8d, eax
0x14000816e  mov     ecx, eax
0x140008170  shr     r8d, 1
0x140008173  and     r8d, 0Fh
0x140008177  jz      short loc_140008194
0x140008179  prefetchw byte ptr [rdx+4]
0x14000817d  mov     eax, [rdx+4]
0x140008180  mov     edx, eax
0x140008182  or      edx, r8d
0x140008185  lock cmpxchg [r9+4], edx
0x14000818b  jnz     short loc_140008180
0x14000818d  not     eax
0x14000818f  and     eax, r8d
0x140008192  jmp     short loc_140008197
0x140008194  mov     eax, r8d
0x140008197  mov     r8d, 2
0x14000819d  lea     r9d, [r8-1]
0x1400081a1  test    r9b, al
0x1400081a4  jz      short loc_1400081BA
0x1400081a6  mov     [rsp+68h+var_48], r10d
0x1400081ab  lea     rdx, [rsp+68h+var_40]
0x1400081b0  mov     [rsp+68h+var_44], 10002h
0x1400081b8  jmp     short loc_1400081BF
0x1400081ba  lea     rdx, [rsp+68h+var_48]
0x1400081bf  test    r8b, al
0x1400081c2  jz      short loc_1400081D2
0x1400081c4  mov     [rdx], r10d
0x1400081c7  mov     dword ptr [rdx+4], 10006h
0x1400081ce  add     rdx, 8
0x1400081d2  test    al, 4
0x1400081d4  jz      short loc_1400081E4
0x1400081d6  mov     [rdx], r10d
0x1400081d9  mov     dword ptr [rdx+4], 10003h
0x1400081e0  add     rdx, 8
0x1400081e4  cmp     eax, 8
0x1400081e7  jb      short loc_1400081F7
0x1400081e9  mov     [rdx], r10d
0x1400081ec  mov     dword ptr [rdx+4], 10007h
0x1400081f3  add     rdx, 8
0x1400081f7  mov     r8d, ecx
0x1400081fa  mov     r11d, 1FFh
0x140008200  shr     r8d, 5
0x140008204  test    r11d, r8d
0x140008207  jz      short loc_14000822A
0x140008209  and     r8w, r11w
0x14000820d  mov     [rdx], r10d
0x140008210  mov     eax, ecx
0x140008212  mov     [rdx+6], r8w
0x140008217  shr     eax, 0Eh
0x14000821a  and     ax, r9w
0x14000821e  shl     ax, 2
0x140008222  mov     [rdx+4], ax
0x140008226  add     rdx, 8
0x14000822a  mov     eax, ecx
0x14000822c  shr     eax, 0Fh
0x14000822f  test    al, 7Fh
0x140008231  jz      short loc_140008255
0x140008233  shr     ecx, 16h
0x140008236  and     ax, 7Fh
0x14000823a  and     cx, r9w
0x14000823e  mov     [rdx], r10d
0x140008241  shl     cx, 2
0x140008245  add     cx, r9w
0x140008249  mov     [rdx+6], ax
0x14000824d  mov     [rdx+4], cx
0x140008251  add     rdx, 8
0x140008255  lea     rax, [rsp+68h+var_48]
0x14000825a  sub     rdx, rax
0x14000825d  sar     rdx, 3
0x140008261  test    rdx, rdx
0x140008264  jle     short loc_140008277
0x140008266  lea     rcx, [rsp+68h+var_48]
0x14000826b  call    cs:__imp_RtlRecordFeatureUsage
0x140008272  nop     dword ptr [rax+rax+00h]
0x140008277  mov     rcx, [rsp+68h+var_18]
0x14000827c  xor     rcx, rsp; StackCookie
0x14000827f  call    __security_check_cookie
0x140008284  add     rsp, 68h
0x140008288  retn
```
