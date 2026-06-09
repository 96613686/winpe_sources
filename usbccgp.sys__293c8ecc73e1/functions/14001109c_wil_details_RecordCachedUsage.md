# wil_details_RecordCachedUsage

- ea: `0x14001109c`
- end: `0x1400111ea`
- name: `wil_details_RecordCachedUsage`
- size: `334`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140022ce0`

## callees

- `0x14001109c`
- `0x140014d10`

## import_xrefs

- `ntoskrnl!RtlRecordFeatureUsage` at `0x1400111cb`
- `ntoskrnl!RtlRecordFeatureUsage` at `0x1400111cb`

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
0x14001109c  sub     rsp, 68h
0x1400110a0  mov     rax, cs:__security_cookie
0x1400110a7  xor     rax, rsp
0x1400110aa  mov     [rsp+68h+var_18], rax
0x1400110af  mov     r9, rdx
0x1400110b2  mov     r10d, ecx
0x1400110b5  prefetchw byte ptr [rdx]
0x1400110b8  mov     eax, [rdx]
0x1400110ba  mov     r8d, eax
0x1400110bd  and     r8d, 0FFC0401Eh
0x1400110c4  lock cmpxchg [rdx], r8d
0x1400110c9  jnz     short loc_1400110BA
0x1400110cb  mov     r8d, eax
0x1400110ce  mov     ecx, eax
0x1400110d0  shr     r8d, 1
0x1400110d3  and     r8d, 0Fh
0x1400110d7  jz      short loc_1400110F4
0x1400110d9  prefetchw byte ptr [rdx+4]
0x1400110dd  mov     eax, [rdx+4]
0x1400110e0  mov     edx, eax
0x1400110e2  or      edx, r8d
0x1400110e5  lock cmpxchg [r9+4], edx
0x1400110eb  jnz     short loc_1400110E0
0x1400110ed  not     eax
0x1400110ef  and     eax, r8d
0x1400110f2  jmp     short loc_1400110F7
0x1400110f4  mov     eax, r8d
0x1400110f7  mov     r8d, 2
0x1400110fd  lea     r9d, [r8-1]
0x140011101  test    r9b, al
0x140011104  jz      short loc_14001111A
0x140011106  mov     [rsp+68h+var_48], r10d
0x14001110b  lea     rdx, [rsp+68h+var_40]
0x140011110  mov     [rsp+68h+var_44], 10002h
0x140011118  jmp     short loc_14001111F
0x14001111a  lea     rdx, [rsp+68h+var_48]
0x14001111f  test    r8b, al
0x140011122  jz      short loc_140011132
0x140011124  mov     [rdx], r10d
0x140011127  mov     dword ptr [rdx+4], 10006h
0x14001112e  add     rdx, 8
0x140011132  test    al, 4
0x140011134  jz      short loc_140011144
0x140011136  mov     [rdx], r10d
0x140011139  mov     dword ptr [rdx+4], 10003h
0x140011140  add     rdx, 8
0x140011144  cmp     eax, 8
0x140011147  jb      short loc_140011157
0x140011149  mov     [rdx], r10d
0x14001114c  mov     dword ptr [rdx+4], 10007h
0x140011153  add     rdx, 8
0x140011157  mov     r8d, ecx
0x14001115a  mov     r11d, 1FFh
0x140011160  shr     r8d, 5
0x140011164  test    r11d, r8d
0x140011167  jz      short loc_14001118A
0x140011169  and     r8w, r11w
0x14001116d  mov     [rdx], r10d
0x140011170  mov     eax, ecx
0x140011172  mov     [rdx+6], r8w
0x140011177  shr     eax, 0Eh
0x14001117a  and     ax, r9w
0x14001117e  shl     ax, 2
0x140011182  mov     [rdx+4], ax
0x140011186  add     rdx, 8
0x14001118a  mov     eax, ecx
0x14001118c  shr     eax, 0Fh
0x14001118f  test    al, 7Fh
0x140011191  jz      short loc_1400111B5
0x140011193  shr     ecx, 16h
0x140011196  and     ax, 7Fh
0x14001119a  and     cx, r9w
0x14001119e  mov     [rdx], r10d
0x1400111a1  shl     cx, 2
0x1400111a5  add     cx, r9w
0x1400111a9  mov     [rdx+6], ax
0x1400111ad  mov     [rdx+4], cx
0x1400111b1  add     rdx, 8
0x1400111b5  lea     rax, [rsp+68h+var_48]
0x1400111ba  sub     rdx, rax
0x1400111bd  sar     rdx, 3
0x1400111c1  test    rdx, rdx
0x1400111c4  jle     short loc_1400111D7
0x1400111c6  lea     rcx, [rsp+68h+var_48]
0x1400111cb  call    cs:__imp_RtlRecordFeatureUsage
0x1400111d2  nop     dword ptr [rax+rax+00h]
0x1400111d7  mov     rcx, [rsp+68h+var_18]
0x1400111dc  xor     rcx, rsp; StackCookie
0x1400111df  call    __security_check_cookie
0x1400111e4  add     rsp, 68h
0x1400111e8  retn
```
