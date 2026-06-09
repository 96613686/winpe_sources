# wil_details_RecordCachedUsage

- ea: `0x180016ec4`
- end: `0x18001700b`
- name: `wil_details_RecordCachedUsage`
- size: `327`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800155ec`

## callees

- `0x1800106c0`
- `0x180016358`
- `0x180016ec4`

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
0x180016ec4  sub     rsp, 68h
0x180016ec8  mov     rax, cs:__security_cookie
0x180016ecf  xor     rax, rsp
0x180016ed2  mov     [rsp+68h+var_18], rax
0x180016ed7  mov     r9, rdx
0x180016eda  mov     r10d, ecx
0x180016edd  prefetchw byte ptr [rdx]
0x180016ee0  mov     eax, [rdx]
0x180016ee2  mov     r8d, eax
0x180016ee5  and     r8d, 0FFC0401Eh
0x180016eec  lock cmpxchg [rdx], r8d
0x180016ef1  jnz     short loc_180016EE2
0x180016ef3  mov     ecx, eax
0x180016ef5  mov     r8d, eax
0x180016ef8  shr     r8d, 1
0x180016efb  and     r8d, 0Fh
0x180016eff  jz      short loc_180016F1C
0x180016f01  prefetchw byte ptr [rdx+4]
0x180016f05  mov     eax, [rdx+4]
0x180016f08  mov     edx, eax
0x180016f0a  or      edx, r8d
0x180016f0d  lock cmpxchg [r9+4], edx
0x180016f13  jnz     short loc_180016F08
0x180016f15  not     eax
0x180016f17  and     eax, r8d
0x180016f1a  jmp     short loc_180016F1F
0x180016f1c  mov     eax, r8d
0x180016f1f  mov     r8d, 2
0x180016f25  lea     r9d, [r8-1]
0x180016f29  test    r9b, al
0x180016f2c  jz      short loc_180016F42
0x180016f2e  mov     [rsp+68h+var_48], r10d
0x180016f33  mov     [rsp+68h+var_44], 10002h
0x180016f3b  lea     rdx, [rsp+68h+var_40]
0x180016f40  jmp     short loc_180016F47
0x180016f42  lea     rdx, [rsp+68h+var_48]
0x180016f47  test    r8b, al
0x180016f4a  jz      short loc_180016F5A
0x180016f4c  mov     [rdx], r10d
0x180016f4f  mov     dword ptr [rdx+4], 10006h
0x180016f56  add     rdx, 8
0x180016f5a  test    al, 4
0x180016f5c  jz      short loc_180016F6C
0x180016f5e  mov     [rdx], r10d
0x180016f61  mov     dword ptr [rdx+4], 10003h
0x180016f68  add     rdx, 8
0x180016f6c  cmp     eax, 8
0x180016f6f  jb      short loc_180016F7F
0x180016f71  mov     [rdx], r10d
0x180016f74  mov     dword ptr [rdx+4], 10007h
0x180016f7b  add     rdx, 8
0x180016f7f  mov     r8d, ecx
0x180016f82  shr     r8d, 5
0x180016f86  mov     r11d, 1FFh
0x180016f8c  test    r11d, r8d
0x180016f8f  jz      short loc_180016FB2
0x180016f91  mov     [rdx], r10d
0x180016f94  mov     eax, ecx
0x180016f96  shr     eax, 0Eh
0x180016f99  and     ax, r9w
0x180016f9d  shl     ax, 2
0x180016fa1  mov     [rdx+4], ax
0x180016fa5  and     r8w, r11w; unsigned __int64
0x180016fa9  mov     [rdx+6], r8w
0x180016fae  add     rdx, 8
0x180016fb2  mov     eax, ecx
0x180016fb4  shr     eax, 0Fh
0x180016fb7  test    al, 7Fh
0x180016fb9  jz      short loc_180016FDD
0x180016fbb  mov     [rdx], r10d
0x180016fbe  shr     ecx, 16h
0x180016fc1  and     cx, r9w
0x180016fc5  shl     cx, 2
0x180016fc9  add     cx, r9w
0x180016fcd  mov     [rdx+4], cx
0x180016fd1  and     ax, 7Fh
0x180016fd5  mov     [rdx+6], ax
0x180016fd9  add     rdx, 8
0x180016fdd  lea     rax, [rsp+68h+var_48]
0x180016fe2  sub     rdx, rax
0x180016fe5  sar     rdx, 3; struct __WIL_RTL_FEATURE_USAGE_DATA *
0x180016fe9  test    rdx, rdx
0x180016fec  jle     short loc_180016FF9
0x180016fee  lea     rcx, [rsp+68h+var_48]; this
0x180016ff3  call    ?WilApi_RecordFeatureUsageReports@details@wil@@YAXPEAU__WIL_RTL_FEATURE_USAGE_DATA@@_K@Z; wil::details::WilApi_RecordFeatureUsageReports(__WIL_RTL_FEATURE_USAGE_DATA *,unsigned __int64)
0x180016ff8  nop
0x180016ff9  mov     rcx, [rsp+68h+var_18]
0x180016ffe  xor     rcx, rsp; StackCookie
0x180017001  call    __security_check_cookie
0x180017006  add     rsp, 68h
0x18001700a  retn
```
