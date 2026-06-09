# wil_details_RecordCachedUsage

- ea: `0x18000cb40`
- end: `0x18000cc86`
- name: `wil_details_RecordCachedUsage`
- size: `326`
- prototype: `void __fastcall(int, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000a394`

## callees

- `0x18000ba04`
- `0x18000cb40`
- `0x18000cff0`

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
0x18000cb40  sub     rsp, 68h
0x18000cb44  mov     rax, cs:__security_cookie
0x18000cb4b  xor     rax, rsp
0x18000cb4e  mov     [rsp+68h+var_18], rax
0x18000cb53  mov     r9, rdx
0x18000cb56  mov     r10d, ecx
0x18000cb59  prefetchw byte ptr [rdx]
0x18000cb5c  mov     eax, [rdx]
0x18000cb5e  mov     r8d, eax
0x18000cb61  and     r8d, 0FFC0401Eh
0x18000cb68  lock cmpxchg [rdx], r8d
0x18000cb6d  jnz     short loc_18000CB5E
0x18000cb6f  mov     r8d, eax
0x18000cb72  mov     ecx, eax
0x18000cb74  shr     r8d, 1
0x18000cb77  and     r8d, 0Fh
0x18000cb7b  jz      short loc_18000CB98
0x18000cb7d  prefetchw byte ptr [rdx+4]
0x18000cb81  mov     eax, [rdx+4]
0x18000cb84  mov     edx, eax
0x18000cb86  or      edx, r8d
0x18000cb89  lock cmpxchg [r9+4], edx
0x18000cb8f  jnz     short loc_18000CB84
0x18000cb91  not     eax
0x18000cb93  and     eax, r8d
0x18000cb96  jmp     short loc_18000CB9B
0x18000cb98  mov     eax, r8d
0x18000cb9b  mov     r8d, 2
0x18000cba1  lea     r9d, [r8-1]
0x18000cba5  test    r9b, al
0x18000cba8  jz      short loc_18000CBBE
0x18000cbaa  mov     [rsp+68h+var_48], r10d
0x18000cbaf  lea     rdx, [rsp+68h+var_40]
0x18000cbb4  mov     [rsp+68h+var_44], 10002h
0x18000cbbc  jmp     short loc_18000CBC3
0x18000cbbe  lea     rdx, [rsp+68h+var_48]
0x18000cbc3  test    r8b, al
0x18000cbc6  jz      short loc_18000CBD6
0x18000cbc8  mov     [rdx], r10d
0x18000cbcb  mov     dword ptr [rdx+4], 10006h
0x18000cbd2  add     rdx, 8
0x18000cbd6  test    al, 4
0x18000cbd8  jz      short loc_18000CBE8
0x18000cbda  mov     [rdx], r10d
0x18000cbdd  mov     dword ptr [rdx+4], 10003h
0x18000cbe4  add     rdx, 8
0x18000cbe8  cmp     eax, 8
0x18000cbeb  jb      short loc_18000CBFB
0x18000cbed  mov     [rdx], r10d
0x18000cbf0  mov     dword ptr [rdx+4], 10007h
0x18000cbf7  add     rdx, 8
0x18000cbfb  mov     r8d, ecx
0x18000cbfe  mov     r11d, 1FFh
0x18000cc04  shr     r8d, 5
0x18000cc08  test    r11d, r8d
0x18000cc0b  jz      short loc_18000CC2E
0x18000cc0d  and     r8w, r11w; unsigned __int64
0x18000cc11  mov     [rdx], r10d
0x18000cc14  mov     eax, ecx
0x18000cc16  mov     [rdx+6], r8w
0x18000cc1b  shr     eax, 0Eh
0x18000cc1e  and     ax, r9w
0x18000cc22  shl     ax, 2
0x18000cc26  mov     [rdx+4], ax
0x18000cc2a  add     rdx, 8
0x18000cc2e  mov     eax, ecx
0x18000cc30  shr     eax, 0Fh
0x18000cc33  test    al, 7Fh
0x18000cc35  jz      short loc_18000CC59
0x18000cc37  shr     ecx, 16h
0x18000cc3a  and     ax, 7Fh
0x18000cc3e  and     cx, r9w
0x18000cc42  mov     [rdx], r10d
0x18000cc45  shl     cx, 2
0x18000cc49  add     cx, r9w
0x18000cc4d  mov     [rdx+6], ax
0x18000cc51  mov     [rdx+4], cx
0x18000cc55  add     rdx, 8
0x18000cc59  lea     rax, [rsp+68h+var_48]
0x18000cc5e  sub     rdx, rax
0x18000cc61  sar     rdx, 3; struct __WIL_RTL_FEATURE_USAGE_DATA *
0x18000cc65  test    rdx, rdx
0x18000cc68  jle     short loc_18000CC74
0x18000cc6a  lea     rcx, [rsp+68h+var_48]; this
0x18000cc6f  call    ?WilApi_RecordFeatureUsageReports@details@wil@@YAXPEAU__WIL_RTL_FEATURE_USAGE_DATA@@_K@Z; wil::details::WilApi_RecordFeatureUsageReports(__WIL_RTL_FEATURE_USAGE_DATA *,unsigned __int64)
0x18000cc74  mov     rcx, [rsp+68h+var_18]
0x18000cc79  xor     rcx, rsp; StackCookie
0x18000cc7c  call    __security_check_cookie
0x18000cc81  add     rsp, 68h
0x18000cc85  retn
```
