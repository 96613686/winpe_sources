# wil_details_RecordCachedUsage

- ea: `0x14001ee44`
- end: `0x14001ef8b`
- name: `wil_details_RecordCachedUsage`
- size: `327`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14004e980`

## callees

- `0x14001ee44`
- `0x140039740`
- `0x14004e9d4`

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
    return (_DWORD *)wil_details_RecordFeatureUsageCallback(v10);
  return result;
}

```

## disassembly

```asm
0x14001ee44  sub     rsp, 68h
0x14001ee48  mov     rax, cs:__security_cookie
0x14001ee4f  xor     rax, rsp
0x14001ee52  mov     [rsp+68h+var_18], rax
0x14001ee57  mov     r9, rdx
0x14001ee5a  mov     r10d, ecx
0x14001ee5d  prefetchw byte ptr [rdx]
0x14001ee60  mov     eax, [rdx]
0x14001ee62  mov     r8d, eax
0x14001ee65  and     r8d, 0FFC0401Eh
0x14001ee6c  lock cmpxchg [rdx], r8d
0x14001ee71  jnz     short loc_14001EE62
0x14001ee73  mov     r8d, eax
0x14001ee76  mov     ecx, eax
0x14001ee78  shr     r8d, 1
0x14001ee7b  and     r8d, 0Fh
0x14001ee7f  jz      short loc_14001EE9C
0x14001ee81  prefetchw byte ptr [rdx+4]
0x14001ee85  mov     eax, [rdx+4]
0x14001ee88  mov     edx, eax
0x14001ee8a  or      edx, r8d
0x14001ee8d  lock cmpxchg [r9+4], edx
0x14001ee93  jnz     short loc_14001EE88
0x14001ee95  not     eax
0x14001ee97  and     eax, r8d
0x14001ee9a  jmp     short loc_14001EE9F
0x14001ee9c  mov     eax, r8d
0x14001ee9f  mov     r8d, 2
0x14001eea5  lea     r9d, [r8-1]
0x14001eea9  test    r9b, al
0x14001eeac  jz      short loc_14001EEC2
0x14001eeae  mov     [rsp+68h+var_48], r10d
0x14001eeb3  lea     rdx, [rsp+68h+var_40]
0x14001eeb8  mov     [rsp+68h+var_44], 10002h
0x14001eec0  jmp     short loc_14001EEC7
0x14001eec2  lea     rdx, [rsp+68h+var_48]
0x14001eec7  test    r8b, al
0x14001eeca  jz      short loc_14001EEDA
0x14001eecc  mov     [rdx], r10d
0x14001eecf  mov     dword ptr [rdx+4], 10006h
0x14001eed6  add     rdx, 8
0x14001eeda  test    al, 4
0x14001eedc  jz      short loc_14001EEEC
0x14001eede  mov     [rdx], r10d
0x14001eee1  mov     dword ptr [rdx+4], 10003h
0x14001eee8  add     rdx, 8
0x14001eeec  cmp     eax, 8
0x14001eeef  jb      short loc_14001EEFF
0x14001eef1  mov     [rdx], r10d
0x14001eef4  mov     dword ptr [rdx+4], 10007h
0x14001eefb  add     rdx, 8
0x14001eeff  mov     r8d, ecx
0x14001ef02  mov     r11d, 1FFh
0x14001ef08  shr     r8d, 5
0x14001ef0c  test    r11d, r8d
0x14001ef0f  jz      short loc_14001EF32
0x14001ef11  and     r8w, r11w
0x14001ef15  mov     [rdx], r10d
0x14001ef18  mov     eax, ecx
0x14001ef1a  mov     [rdx+6], r8w
0x14001ef1f  shr     eax, 0Eh
0x14001ef22  and     ax, r9w
0x14001ef26  shl     ax, 2
0x14001ef2a  mov     [rdx+4], ax
0x14001ef2e  add     rdx, 8
0x14001ef32  mov     eax, ecx
0x14001ef34  shr     eax, 0Fh
0x14001ef37  test    al, 7Fh
0x14001ef39  jz      short loc_14001EF5D
0x14001ef3b  shr     ecx, 16h
0x14001ef3e  and     ax, 7Fh
0x14001ef42  and     cx, r9w
0x14001ef46  mov     [rdx], r10d
0x14001ef49  shl     cx, 2
0x14001ef4d  add     cx, r9w
0x14001ef51  mov     [rdx+6], ax
0x14001ef55  mov     [rdx+4], cx
0x14001ef59  add     rdx, 8
0x14001ef5d  lea     rax, [rsp+68h+var_48]
0x14001ef62  sub     rdx, rax
0x14001ef65  sar     rdx, 3
0x14001ef69  test    rdx, rdx
0x14001ef6c  jle     short loc_14001EF78
0x14001ef6e  lea     rcx, [rsp+68h+var_48]
0x14001ef73  call    wil_details_RecordFeatureUsageCallback
0x14001ef78  mov     rcx, [rsp+68h+var_18]
0x14001ef7d  xor     rcx, rsp; StackCookie
0x14001ef80  call    __security_check_cookie
0x14001ef85  add     rsp, 68h
0x14001ef89  retn
```
