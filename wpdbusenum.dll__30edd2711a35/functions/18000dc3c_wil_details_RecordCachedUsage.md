# wil_details_RecordCachedUsage

- ea: `0x18000dc3c`
- end: `0x18000dd83`
- name: `wil_details_RecordCachedUsage`
- size: `327`
- prototype: `void __fastcall(int, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000cc00`

## callees

- `0x1800097d0`
- `0x18000d690`
- `0x18000dc3c`

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
0x18000dc3c  sub     rsp, 68h
0x18000dc40  mov     rax, cs:__security_cookie
0x18000dc47  xor     rax, rsp
0x18000dc4a  mov     [rsp+68h+var_18], rax
0x18000dc4f  mov     r9, rdx
0x18000dc52  mov     r10d, ecx
0x18000dc55  prefetchw byte ptr [rdx]
0x18000dc58  mov     eax, [rdx]
0x18000dc5a  mov     r8d, eax
0x18000dc5d  and     r8d, 0FFC0401Eh
0x18000dc64  lock cmpxchg [rdx], r8d
0x18000dc69  jnz     short loc_18000DC5A
0x18000dc6b  mov     ecx, eax
0x18000dc6d  mov     r8d, eax
0x18000dc70  shr     r8d, 1
0x18000dc73  and     r8d, 0Fh
0x18000dc77  jz      short loc_18000DC94
0x18000dc79  prefetchw byte ptr [rdx+4]
0x18000dc7d  mov     eax, [rdx+4]
0x18000dc80  mov     edx, eax
0x18000dc82  or      edx, r8d
0x18000dc85  lock cmpxchg [r9+4], edx
0x18000dc8b  jnz     short loc_18000DC80
0x18000dc8d  not     eax
0x18000dc8f  and     eax, r8d
0x18000dc92  jmp     short loc_18000DC97
0x18000dc94  mov     eax, r8d
0x18000dc97  mov     r8d, 2
0x18000dc9d  lea     r9d, [r8-1]
0x18000dca1  test    r9b, al
0x18000dca4  jz      short loc_18000DCBA
0x18000dca6  mov     [rsp+68h+var_48], r10d
0x18000dcab  mov     [rsp+68h+var_44], 10002h
0x18000dcb3  lea     rdx, [rsp+68h+var_40]
0x18000dcb8  jmp     short loc_18000DCBF
0x18000dcba  lea     rdx, [rsp+68h+var_48]
0x18000dcbf  test    r8b, al
0x18000dcc2  jz      short loc_18000DCD2
0x18000dcc4  mov     [rdx], r10d
0x18000dcc7  mov     dword ptr [rdx+4], 10006h
0x18000dcce  add     rdx, 8
0x18000dcd2  test    al, 4
0x18000dcd4  jz      short loc_18000DCE4
0x18000dcd6  mov     [rdx], r10d
0x18000dcd9  mov     dword ptr [rdx+4], 10003h
0x18000dce0  add     rdx, 8
0x18000dce4  cmp     eax, 8
0x18000dce7  jb      short loc_18000DCF7
0x18000dce9  mov     [rdx], r10d
0x18000dcec  mov     dword ptr [rdx+4], 10007h
0x18000dcf3  add     rdx, 8
0x18000dcf7  mov     r8d, ecx
0x18000dcfa  shr     r8d, 5
0x18000dcfe  mov     r11d, 1FFh
0x18000dd04  test    r11d, r8d
0x18000dd07  jz      short loc_18000DD2A
0x18000dd09  mov     [rdx], r10d
0x18000dd0c  mov     eax, ecx
0x18000dd0e  shr     eax, 0Eh
0x18000dd11  and     ax, r9w
0x18000dd15  shl     ax, 2
0x18000dd19  mov     [rdx+4], ax
0x18000dd1d  and     r8w, r11w; unsigned __int64
0x18000dd21  mov     [rdx+6], r8w
0x18000dd26  add     rdx, 8
0x18000dd2a  mov     eax, ecx
0x18000dd2c  shr     eax, 0Fh
0x18000dd2f  test    al, 7Fh
0x18000dd31  jz      short loc_18000DD55
0x18000dd33  mov     [rdx], r10d
0x18000dd36  shr     ecx, 16h
0x18000dd39  and     cx, r9w
0x18000dd3d  shl     cx, 2
0x18000dd41  add     cx, r9w
0x18000dd45  mov     [rdx+4], cx
0x18000dd49  and     ax, 7Fh
0x18000dd4d  mov     [rdx+6], ax
0x18000dd51  add     rdx, 8
0x18000dd55  lea     rax, [rsp+68h+var_48]
0x18000dd5a  sub     rdx, rax
0x18000dd5d  sar     rdx, 3; struct __WIL_RTL_FEATURE_USAGE_DATA *
0x18000dd61  test    rdx, rdx
0x18000dd64  jle     short loc_18000DD71
0x18000dd66  lea     rcx, [rsp+68h+var_48]; this
0x18000dd6b  call    ?WilApi_RecordFeatureUsageReports@details@wil@@YAXPEAU__WIL_RTL_FEATURE_USAGE_DATA@@_K@Z; wil::details::WilApi_RecordFeatureUsageReports(__WIL_RTL_FEATURE_USAGE_DATA *,unsigned __int64)
0x18000dd70  nop
0x18000dd71  mov     rcx, [rsp+68h+var_18]
0x18000dd76  xor     rcx, rsp; StackCookie
0x18000dd79  call    __security_check_cookie
0x18000dd7e  add     rsp, 68h
0x18000dd82  retn
```
