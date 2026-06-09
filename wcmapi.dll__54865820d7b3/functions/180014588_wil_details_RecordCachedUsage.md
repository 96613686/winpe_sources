# wil_details_RecordCachedUsage

- ea: `0x180014588`
- end: `0x1800146d0`
- name: `wil_details_RecordCachedUsage`
- size: `328`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000f02c`

## callees

- `0x180008a90`
- `0x180010a28`
- `0x180014588`

## pseudocode

```c
void __fastcall wil_details_RecordCachedUsage(int a1, __int64 a2)
{
  unsigned __int32 v3; // ecx
  int v4; // r8d
  signed __int32 v5; // eax
  signed __int32 v6; // ett
  unsigned int v7; // eax
  char *v8; // rdx
  unsigned __int64 v9; // r8
  __int64 v10; // rdx
  _DWORD v11[2]; // [rsp+20h] [rbp-48h] BYREF
  char v12; // [rsp+28h] [rbp-40h] BYREF

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
    v11[0] = a1;
    v11[1] = 65538;
    v8 = &v12;
  }
  else
  {
    v8 = (char *)v11;
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
  v9 = v3 >> 5;
  if ( (v9 & 0x1FF) != 0 )
  {
    *(_DWORD *)v8 = a1;
    *((_WORD *)v8 + 2) = 4 * ((v3 >> 14) & 1);
    LOWORD(v9) = v9 & 0x1FF;
    *((_WORD *)v8 + 3) = v9;
    v8 += 8;
  }
  if ( ((v3 >> 15) & 0x7F) != 0 )
  {
    *(_DWORD *)v8 = a1;
    *((_WORD *)v8 + 2) = 4 * ((v3 >> 22) & 1) + 1;
    *((_WORD *)v8 + 3) = (v3 >> 15) & 0x7F;
    v8 += 8;
  }
  v10 = (v8 - (char *)v11) >> 3;
  if ( v10 > 0 )
    wil::details::WilApi_RecordFeatureUsageReports((wil::details *)v11, (struct __WIL_RTL_FEATURE_USAGE_DATA *)v10, v9);
}

```

## disassembly

```asm
0x180014588  sub     rsp, 68h
0x18001458c  mov     rax, cs:__security_cookie
0x180014593  xor     rax, rsp
0x180014596  mov     [rsp+68h+var_18], rax
0x18001459b  mov     r9, rdx
0x18001459e  mov     r10d, ecx
0x1800145a1  prefetchw byte ptr [rdx]
0x1800145a4  mov     eax, [rdx]
0x1800145a6  mov     r8d, eax
0x1800145a9  and     r8d, 0FFC0401Eh
0x1800145b0  lock cmpxchg [rdx], r8d
0x1800145b5  jnz     short loc_1800145A6
0x1800145b7  mov     ecx, eax
0x1800145b9  mov     r8d, eax
0x1800145bc  shr     r8d, 1
0x1800145bf  and     r8d, 0Fh
0x1800145c3  jz      short loc_1800145E0
0x1800145c5  prefetchw byte ptr [rdx+4]
0x1800145c9  mov     eax, [rdx+4]
0x1800145cc  mov     edx, eax
0x1800145ce  or      edx, r8d
0x1800145d1  lock cmpxchg [r9+4], edx
0x1800145d7  jnz     short loc_1800145CC
0x1800145d9  not     eax
0x1800145db  and     eax, r8d
0x1800145de  jmp     short loc_1800145E3
0x1800145e0  mov     eax, r8d
0x1800145e3  mov     r8d, 2
0x1800145e9  lea     r9d, [r8-1]
0x1800145ed  test    r9b, al
0x1800145f0  jz      short loc_180014606
0x1800145f2  mov     [rsp+68h+var_48], r10d
0x1800145f7  mov     [rsp+68h+var_44], 10002h
0x1800145ff  lea     rdx, [rsp+68h+var_40]
0x180014604  jmp     short loc_18001460B
0x180014606  lea     rdx, [rsp+68h+var_48]
0x18001460b  test    r8b, al
0x18001460e  jz      short loc_18001461E
0x180014610  mov     [rdx], r10d
0x180014613  mov     dword ptr [rdx+4], 10006h
0x18001461a  add     rdx, 8
0x18001461e  test    al, 4
0x180014620  jz      short loc_180014630
0x180014622  mov     [rdx], r10d
0x180014625  mov     dword ptr [rdx+4], 10003h
0x18001462c  add     rdx, 8
0x180014630  cmp     eax, 8
0x180014633  jb      short loc_180014643
0x180014635  mov     [rdx], r10d
0x180014638  mov     dword ptr [rdx+4], 10007h
0x18001463f  add     rdx, 8
0x180014643  mov     r8d, ecx
0x180014646  shr     r8d, 5
0x18001464a  mov     r11d, 1FFh
0x180014650  test    r11d, r8d
0x180014653  jz      short loc_180014676
0x180014655  mov     [rdx], r10d
0x180014658  mov     eax, ecx
0x18001465a  shr     eax, 0Eh
0x18001465d  and     ax, r9w
0x180014661  shl     ax, 2
0x180014665  mov     [rdx+4], ax
0x180014669  and     r8w, r11w; unsigned __int64
0x18001466d  mov     [rdx+6], r8w
0x180014672  add     rdx, 8
0x180014676  mov     eax, ecx
0x180014678  shr     eax, 0Fh
0x18001467b  test    al, 7Fh
0x18001467d  jz      short loc_1800146A1
0x18001467f  mov     [rdx], r10d
0x180014682  shr     ecx, 16h
0x180014685  and     cx, r9w
0x180014689  shl     cx, 2
0x18001468d  add     cx, r9w
0x180014691  mov     [rdx+4], cx
0x180014695  and     ax, 7Fh
0x180014699  mov     [rdx+6], ax
0x18001469d  add     rdx, 8
0x1800146a1  lea     rax, [rsp+68h+var_48]
0x1800146a6  sub     rdx, rax
0x1800146a9  sar     rdx, 3; struct __WIL_RTL_FEATURE_USAGE_DATA *
0x1800146ad  test    rdx, rdx
0x1800146b0  jle     short loc_1800146BD
0x1800146b2  lea     rcx, [rsp+68h+var_48]; this
0x1800146b7  call    ?WilApi_RecordFeatureUsageReports@details@wil@@YAXPEAU__WIL_RTL_FEATURE_USAGE_DATA@@_K@Z; wil::details::WilApi_RecordFeatureUsageReports(__WIL_RTL_FEATURE_USAGE_DATA *,unsigned __int64)
0x1800146bc  nop
0x1800146bd  mov     rcx, [rsp+68h+var_18]
0x1800146c2  xor     rcx, rsp; StackCookie
0x1800146c5  call    __security_check_cookie
0x1800146ca  add     rsp, 68h
0x1800146ce  retn
```
