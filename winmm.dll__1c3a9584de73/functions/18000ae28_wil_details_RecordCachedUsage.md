# wil_details_RecordCachedUsage

- ea: `0x18000ae28`
- end: `0x18000af6f`
- name: `wil_details_RecordCachedUsage`
- size: `327`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180018734`

## callees

- `0x18000ae28`
- `0x18000c990`
- `0x1800194e4`

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
0x18000ae28  sub     rsp, 68h
0x18000ae2c  mov     rax, cs:__security_cookie
0x18000ae33  xor     rax, rsp
0x18000ae36  mov     [rsp+68h+var_18], rax
0x18000ae3b  mov     r9, rdx
0x18000ae3e  mov     r10d, ecx
0x18000ae41  prefetchw byte ptr [rdx]
0x18000ae44  mov     eax, [rdx]
0x18000ae46  mov     r8d, eax
0x18000ae49  and     r8d, 0FFC0401Eh
0x18000ae50  lock cmpxchg [rdx], r8d
0x18000ae55  jnz     short loc_18000AE46
0x18000ae57  mov     ecx, eax
0x18000ae59  mov     r8d, eax
0x18000ae5c  shr     r8d, 1
0x18000ae5f  and     r8d, 0Fh
0x18000ae63  jz      short loc_18000AE80
0x18000ae65  prefetchw byte ptr [rdx+4]
0x18000ae69  mov     eax, [rdx+4]
0x18000ae6c  mov     edx, eax
0x18000ae6e  or      edx, r8d
0x18000ae71  lock cmpxchg [r9+4], edx
0x18000ae77  jnz     short loc_18000AE6C
0x18000ae79  not     eax
0x18000ae7b  and     eax, r8d
0x18000ae7e  jmp     short loc_18000AE83
0x18000ae80  mov     eax, r8d
0x18000ae83  mov     r8d, 2
0x18000ae89  lea     r9d, [r8-1]
0x18000ae8d  test    r9b, al
0x18000ae90  jz      short loc_18000AEA6
0x18000ae92  mov     [rsp+68h+var_48], r10d
0x18000ae97  mov     [rsp+68h+var_44], 10002h
0x18000ae9f  lea     rdx, [rsp+68h+var_40]
0x18000aea4  jmp     short loc_18000AEAB
0x18000aea6  lea     rdx, [rsp+68h+var_48]
0x18000aeab  test    r8b, al
0x18000aeae  jz      short loc_18000AEBE
0x18000aeb0  mov     [rdx], r10d
0x18000aeb3  mov     dword ptr [rdx+4], 10006h
0x18000aeba  add     rdx, 8
0x18000aebe  test    al, 4
0x18000aec0  jz      short loc_18000AED0
0x18000aec2  mov     [rdx], r10d
0x18000aec5  mov     dword ptr [rdx+4], 10003h
0x18000aecc  add     rdx, 8
0x18000aed0  cmp     eax, 8
0x18000aed3  jb      short loc_18000AEE3
0x18000aed5  mov     [rdx], r10d
0x18000aed8  mov     dword ptr [rdx+4], 10007h
0x18000aedf  add     rdx, 8
0x18000aee3  mov     r8d, ecx
0x18000aee6  shr     r8d, 5
0x18000aeea  mov     r11d, 1FFh
0x18000aef0  test    r11d, r8d
0x18000aef3  jz      short loc_18000AF16
0x18000aef5  mov     [rdx], r10d
0x18000aef8  mov     eax, ecx
0x18000aefa  shr     eax, 0Eh
0x18000aefd  and     ax, r9w
0x18000af01  shl     ax, 2
0x18000af05  mov     [rdx+4], ax
0x18000af09  and     r8w, r11w; unsigned __int64
0x18000af0d  mov     [rdx+6], r8w
0x18000af12  add     rdx, 8
0x18000af16  mov     eax, ecx
0x18000af18  shr     eax, 0Fh
0x18000af1b  test    al, 7Fh
0x18000af1d  jz      short loc_18000AF41
0x18000af1f  mov     [rdx], r10d
0x18000af22  shr     ecx, 16h
0x18000af25  and     cx, r9w
0x18000af29  shl     cx, 2
0x18000af2d  add     cx, r9w
0x18000af31  mov     [rdx+4], cx
0x18000af35  and     ax, 7Fh
0x18000af39  mov     [rdx+6], ax
0x18000af3d  add     rdx, 8
0x18000af41  lea     rax, [rsp+68h+var_48]
0x18000af46  sub     rdx, rax
0x18000af49  sar     rdx, 3; struct __WIL_RTL_FEATURE_USAGE_DATA *
0x18000af4d  test    rdx, rdx
0x18000af50  jle     short loc_18000AF5D
0x18000af52  lea     rcx, [rsp+68h+var_48]; this
0x18000af57  call    ?WilApi_RecordFeatureUsageReports@details@wil@@YAXPEAU__WIL_RTL_FEATURE_USAGE_DATA@@_K@Z; wil::details::WilApi_RecordFeatureUsageReports(__WIL_RTL_FEATURE_USAGE_DATA *,unsigned __int64)
0x18000af5c  nop
0x18000af5d  mov     rcx, [rsp+68h+var_18]
0x18000af62  xor     rcx, rsp; StackCookie
0x18000af65  call    __security_check_cookie
0x18000af6a  add     rsp, 68h
0x18000af6e  retn
```
