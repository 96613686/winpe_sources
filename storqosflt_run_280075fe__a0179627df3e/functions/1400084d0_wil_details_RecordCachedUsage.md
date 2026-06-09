# wil_details_RecordCachedUsage

- ea: `0x1400084d0`
- end: `0x14000861e`
- name: `wil_details_RecordCachedUsage`
- size: `334`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140013b40`

## callees

- `0x1400084d0`
- `0x140008d20`

## import_xrefs

- `ntoskrnl!RtlRecordFeatureUsage` at `0x1400085ff`
- `ntoskrnl!RtlRecordFeatureUsage` at `0x1400085ff`

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
0x1400084d0  sub     rsp, 68h
0x1400084d4  mov     rax, cs:__security_cookie
0x1400084db  xor     rax, rsp
0x1400084de  mov     [rsp+68h+var_18], rax
0x1400084e3  mov     r9, rdx
0x1400084e6  mov     r10d, ecx
0x1400084e9  prefetchw byte ptr [rdx]
0x1400084ec  mov     eax, [rdx]
0x1400084ee  mov     r8d, eax
0x1400084f1  and     r8d, 0FFC0401Eh
0x1400084f8  lock cmpxchg [rdx], r8d
0x1400084fd  jnz     short loc_1400084EE
0x1400084ff  mov     r8d, eax
0x140008502  mov     ecx, eax
0x140008504  shr     r8d, 1
0x140008507  and     r8d, 0Fh
0x14000850b  jz      short loc_140008528
0x14000850d  prefetchw byte ptr [rdx+4]
0x140008511  mov     eax, [rdx+4]
0x140008514  mov     edx, eax
0x140008516  or      edx, r8d
0x140008519  lock cmpxchg [r9+4], edx
0x14000851f  jnz     short loc_140008514
0x140008521  not     eax
0x140008523  and     eax, r8d
0x140008526  jmp     short loc_14000852B
0x140008528  mov     eax, r8d
0x14000852b  mov     r8d, 2
0x140008531  lea     r9d, [r8-1]
0x140008535  test    r9b, al
0x140008538  jz      short loc_14000854E
0x14000853a  mov     [rsp+68h+var_48], r10d
0x14000853f  lea     rdx, [rsp+68h+var_40]
0x140008544  mov     [rsp+68h+var_44], 10002h
0x14000854c  jmp     short loc_140008553
0x14000854e  lea     rdx, [rsp+68h+var_48]
0x140008553  test    r8b, al
0x140008556  jz      short loc_140008566
0x140008558  mov     [rdx], r10d
0x14000855b  mov     dword ptr [rdx+4], 10006h
0x140008562  add     rdx, 8
0x140008566  test    al, 4
0x140008568  jz      short loc_140008578
0x14000856a  mov     [rdx], r10d
0x14000856d  mov     dword ptr [rdx+4], 10003h
0x140008574  add     rdx, 8
0x140008578  cmp     eax, 8
0x14000857b  jb      short loc_14000858B
0x14000857d  mov     [rdx], r10d
0x140008580  mov     dword ptr [rdx+4], 10007h
0x140008587  add     rdx, 8
0x14000858b  mov     r8d, ecx
0x14000858e  mov     r11d, 1FFh
0x140008594  shr     r8d, 5
0x140008598  test    r11d, r8d
0x14000859b  jz      short loc_1400085BE
0x14000859d  and     r8w, r11w
0x1400085a1  mov     [rdx], r10d
0x1400085a4  mov     eax, ecx
0x1400085a6  mov     [rdx+6], r8w
0x1400085ab  shr     eax, 0Eh
0x1400085ae  and     ax, r9w
0x1400085b2  shl     ax, 2
0x1400085b6  mov     [rdx+4], ax
0x1400085ba  add     rdx, 8
0x1400085be  mov     eax, ecx
0x1400085c0  shr     eax, 0Fh
0x1400085c3  test    al, 7Fh
0x1400085c5  jz      short loc_1400085E9
0x1400085c7  shr     ecx, 16h
0x1400085ca  and     ax, 7Fh
0x1400085ce  and     cx, r9w
0x1400085d2  mov     [rdx], r10d
0x1400085d5  shl     cx, 2
0x1400085d9  add     cx, r9w
0x1400085dd  mov     [rdx+6], ax
0x1400085e1  mov     [rdx+4], cx
0x1400085e5  add     rdx, 8
0x1400085e9  lea     rax, [rsp+68h+var_48]
0x1400085ee  sub     rdx, rax
0x1400085f1  sar     rdx, 3
0x1400085f5  test    rdx, rdx
0x1400085f8  jle     short loc_14000860B
0x1400085fa  lea     rcx, [rsp+68h+var_48]
0x1400085ff  call    cs:__imp_RtlRecordFeatureUsage
0x140008606  nop     dword ptr [rax+rax+00h]
0x14000860b  mov     rcx, [rsp+68h+var_18]
0x140008610  xor     rcx, rsp; StackCookie
0x140008613  call    __security_check_cookie
0x140008618  add     rsp, 68h
0x14000861c  retn
```
