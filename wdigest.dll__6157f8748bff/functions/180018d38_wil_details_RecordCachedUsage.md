# wil_details_RecordCachedUsage

- ea: `0x180018d38`
- end: `0x180018e7e`
- name: `wil_details_RecordCachedUsage`
- size: `326`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180015d10`

## callees

- `0x180012880`
- `0x180016b14`
- `0x180018d38`

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
    v8 = &v12;
    v11[1] = 65538;
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
    LOWORD(v9) = v9 & 0x1FF;
    *(_DWORD *)v8 = a1;
    *((_WORD *)v8 + 3) = v9;
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
  v10 = (v8 - (char *)v11) >> 3;
  if ( v10 > 0 )
    wil::details::WilApi_RecordFeatureUsageReports((wil::details *)v11, (struct __WIL_RTL_FEATURE_USAGE_DATA *)v10, v9);
}

```

## disassembly

```asm
0x180018d38  sub     rsp, 68h
0x180018d3c  mov     rax, cs:__security_cookie
0x180018d43  xor     rax, rsp
0x180018d46  mov     [rsp+68h+var_18], rax
0x180018d4b  mov     r9, rdx
0x180018d4e  mov     r10d, ecx
0x180018d51  prefetchw byte ptr [rdx]
0x180018d54  mov     eax, [rdx]
0x180018d56  mov     r8d, eax
0x180018d59  and     r8d, 0FFC0401Eh
0x180018d60  lock cmpxchg [rdx], r8d
0x180018d65  jnz     short loc_180018D56
0x180018d67  mov     r8d, eax
0x180018d6a  mov     ecx, eax
0x180018d6c  shr     r8d, 1
0x180018d6f  and     r8d, 0Fh
0x180018d73  jz      short loc_180018D90
0x180018d75  prefetchw byte ptr [rdx+4]
0x180018d79  mov     eax, [rdx+4]
0x180018d7c  mov     edx, eax
0x180018d7e  or      edx, r8d
0x180018d81  lock cmpxchg [r9+4], edx
0x180018d87  jnz     short loc_180018D7C
0x180018d89  not     eax
0x180018d8b  and     eax, r8d
0x180018d8e  jmp     short loc_180018D93
0x180018d90  mov     eax, r8d
0x180018d93  mov     r8d, 2
0x180018d99  lea     r9d, [r8-1]
0x180018d9d  test    r9b, al
0x180018da0  jz      short loc_180018DB6
0x180018da2  mov     [rsp+68h+var_48], r10d
0x180018da7  lea     rdx, [rsp+68h+var_40]
0x180018dac  mov     [rsp+68h+var_44], 10002h
0x180018db4  jmp     short loc_180018DBB
0x180018db6  lea     rdx, [rsp+68h+var_48]
0x180018dbb  test    r8b, al
0x180018dbe  jz      short loc_180018DCE
0x180018dc0  mov     [rdx], r10d
0x180018dc3  mov     dword ptr [rdx+4], 10006h
0x180018dca  add     rdx, 8
0x180018dce  test    al, 4
0x180018dd0  jz      short loc_180018DE0
0x180018dd2  mov     [rdx], r10d
0x180018dd5  mov     dword ptr [rdx+4], 10003h
0x180018ddc  add     rdx, 8
0x180018de0  cmp     eax, 8
0x180018de3  jb      short loc_180018DF3
0x180018de5  mov     [rdx], r10d
0x180018de8  mov     dword ptr [rdx+4], 10007h
0x180018def  add     rdx, 8
0x180018df3  mov     r8d, ecx
0x180018df6  mov     r11d, 1FFh
0x180018dfc  shr     r8d, 5
0x180018e00  test    r11d, r8d
0x180018e03  jz      short loc_180018E26
0x180018e05  and     r8w, r11w; unsigned __int64
0x180018e09  mov     [rdx], r10d
0x180018e0c  mov     eax, ecx
0x180018e0e  mov     [rdx+6], r8w
0x180018e13  shr     eax, 0Eh
0x180018e16  and     ax, r9w
0x180018e1a  shl     ax, 2
0x180018e1e  mov     [rdx+4], ax
0x180018e22  add     rdx, 8
0x180018e26  mov     eax, ecx
0x180018e28  shr     eax, 0Fh
0x180018e2b  test    al, 7Fh
0x180018e2d  jz      short loc_180018E51
0x180018e2f  shr     ecx, 16h
0x180018e32  and     ax, 7Fh
0x180018e36  and     cx, r9w
0x180018e3a  mov     [rdx], r10d
0x180018e3d  shl     cx, 2
0x180018e41  add     cx, r9w
0x180018e45  mov     [rdx+6], ax
0x180018e49  mov     [rdx+4], cx
0x180018e4d  add     rdx, 8
0x180018e51  lea     rax, [rsp+68h+var_48]
0x180018e56  sub     rdx, rax
0x180018e59  sar     rdx, 3; struct __WIL_RTL_FEATURE_USAGE_DATA *
0x180018e5d  test    rdx, rdx
0x180018e60  jle     short loc_180018E6C
0x180018e62  lea     rcx, [rsp+68h+var_48]; this
0x180018e67  call    ?WilApi_RecordFeatureUsageReports@details@wil@@YAXPEAU__WIL_RTL_FEATURE_USAGE_DATA@@_K@Z; wil::details::WilApi_RecordFeatureUsageReports(__WIL_RTL_FEATURE_USAGE_DATA *,unsigned __int64)
0x180018e6c  mov     rcx, [rsp+68h+var_18]
0x180018e71  xor     rcx, rsp; StackCookie
0x180018e74  call    __security_check_cookie
0x180018e79  add     rsp, 68h
0x180018e7d  retn
```
