# wil_details_RecordCachedUsage

- ea: `0x1800120e4`
- end: `0x18001222a`
- name: `wil_details_RecordCachedUsage`
- size: `326`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180010eb0`

## callees

- `0x180011ecc`
- `0x1800120e4`
- `0x1800155c0`

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
0x1800120e4  sub     rsp, 68h
0x1800120e8  mov     rax, cs:__security_cookie
0x1800120ef  xor     rax, rsp
0x1800120f2  mov     [rsp+68h+var_18], rax
0x1800120f7  mov     r9, rdx
0x1800120fa  mov     r10d, ecx
0x1800120fd  prefetchw byte ptr [rdx]
0x180012100  mov     eax, [rdx]
0x180012102  mov     r8d, eax
0x180012105  and     r8d, 0FFC0401Eh
0x18001210c  lock cmpxchg [rdx], r8d
0x180012111  jnz     short loc_180012102
0x180012113  mov     r8d, eax
0x180012116  mov     ecx, eax
0x180012118  shr     r8d, 1
0x18001211b  and     r8d, 0Fh
0x18001211f  jz      short loc_18001213C
0x180012121  prefetchw byte ptr [rdx+4]
0x180012125  mov     eax, [rdx+4]
0x180012128  mov     edx, eax
0x18001212a  or      edx, r8d
0x18001212d  lock cmpxchg [r9+4], edx
0x180012133  jnz     short loc_180012128
0x180012135  not     eax
0x180012137  and     eax, r8d
0x18001213a  jmp     short loc_18001213F
0x18001213c  mov     eax, r8d
0x18001213f  mov     r8d, 2
0x180012145  lea     r9d, [r8-1]
0x180012149  test    r9b, al
0x18001214c  jz      short loc_180012162
0x18001214e  mov     [rsp+68h+var_48], r10d
0x180012153  lea     rdx, [rsp+68h+var_40]
0x180012158  mov     [rsp+68h+var_44], 10002h
0x180012160  jmp     short loc_180012167
0x180012162  lea     rdx, [rsp+68h+var_48]
0x180012167  test    r8b, al
0x18001216a  jz      short loc_18001217A
0x18001216c  mov     [rdx], r10d
0x18001216f  mov     dword ptr [rdx+4], 10006h
0x180012176  add     rdx, 8
0x18001217a  test    al, 4
0x18001217c  jz      short loc_18001218C
0x18001217e  mov     [rdx], r10d
0x180012181  mov     dword ptr [rdx+4], 10003h
0x180012188  add     rdx, 8
0x18001218c  cmp     eax, 8
0x18001218f  jb      short loc_18001219F
0x180012191  mov     [rdx], r10d
0x180012194  mov     dword ptr [rdx+4], 10007h
0x18001219b  add     rdx, 8
0x18001219f  mov     r8d, ecx
0x1800121a2  mov     r11d, 1FFh
0x1800121a8  shr     r8d, 5
0x1800121ac  test    r11d, r8d
0x1800121af  jz      short loc_1800121D2
0x1800121b1  and     r8w, r11w; unsigned __int64
0x1800121b5  mov     [rdx], r10d
0x1800121b8  mov     eax, ecx
0x1800121ba  mov     [rdx+6], r8w
0x1800121bf  shr     eax, 0Eh
0x1800121c2  and     ax, r9w
0x1800121c6  shl     ax, 2
0x1800121ca  mov     [rdx+4], ax
0x1800121ce  add     rdx, 8
0x1800121d2  mov     eax, ecx
0x1800121d4  shr     eax, 0Fh
0x1800121d7  test    al, 7Fh
0x1800121d9  jz      short loc_1800121FD
0x1800121db  shr     ecx, 16h
0x1800121de  and     ax, 7Fh
0x1800121e2  and     cx, r9w
0x1800121e6  mov     [rdx], r10d
0x1800121e9  shl     cx, 2
0x1800121ed  add     cx, r9w
0x1800121f1  mov     [rdx+6], ax
0x1800121f5  mov     [rdx+4], cx
0x1800121f9  add     rdx, 8
0x1800121fd  lea     rax, [rsp+68h+var_48]
0x180012202  sub     rdx, rax
0x180012205  sar     rdx, 3; struct __WIL_RTL_FEATURE_USAGE_DATA *
0x180012209  test    rdx, rdx
0x18001220c  jle     short loc_180012218
0x18001220e  lea     rcx, [rsp+68h+var_48]; this
0x180012213  call    ?WilApi_RecordFeatureUsageReports@details@wil@@YAXPEAU__WIL_RTL_FEATURE_USAGE_DATA@@_K@Z; wil::details::WilApi_RecordFeatureUsageReports(__WIL_RTL_FEATURE_USAGE_DATA *,unsigned __int64)
0x180012218  mov     rcx, [rsp+68h+var_18]
0x18001221d  xor     rcx, rsp; StackCookie
0x180012220  call    __security_check_cookie
0x180012225  add     rsp, 68h
0x180012229  retn
```
