# wil_details_RecordCachedUsage

- ea: `0x18000f9a0`
- end: `0x18000fae7`
- name: `wil_details_RecordCachedUsage`
- size: `327`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180009b24`

## callees

- `0x180005320`
- `0x18000b7a0`
- `0x18000f9a0`

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
0x18000f9a0  sub     rsp, 68h
0x18000f9a4  mov     rax, cs:__security_cookie
0x18000f9ab  xor     rax, rsp
0x18000f9ae  mov     [rsp+68h+var_18], rax
0x18000f9b3  mov     r9, rdx
0x18000f9b6  mov     r10d, ecx
0x18000f9b9  prefetchw byte ptr [rdx]
0x18000f9bc  mov     eax, [rdx]
0x18000f9be  mov     r8d, eax
0x18000f9c1  and     r8d, 0FFC0401Eh
0x18000f9c8  lock cmpxchg [rdx], r8d
0x18000f9cd  jnz     short loc_18000F9BE
0x18000f9cf  mov     ecx, eax
0x18000f9d1  mov     r8d, eax
0x18000f9d4  shr     r8d, 1
0x18000f9d7  and     r8d, 0Fh
0x18000f9db  jz      short loc_18000F9F8
0x18000f9dd  prefetchw byte ptr [rdx+4]
0x18000f9e1  mov     eax, [rdx+4]
0x18000f9e4  mov     edx, eax
0x18000f9e6  or      edx, r8d
0x18000f9e9  lock cmpxchg [r9+4], edx
0x18000f9ef  jnz     short loc_18000F9E4
0x18000f9f1  not     eax
0x18000f9f3  and     eax, r8d
0x18000f9f6  jmp     short loc_18000F9FB
0x18000f9f8  mov     eax, r8d
0x18000f9fb  mov     r8d, 2
0x18000fa01  lea     r9d, [r8-1]
0x18000fa05  test    r9b, al
0x18000fa08  jz      short loc_18000FA1E
0x18000fa0a  mov     [rsp+68h+var_48], r10d
0x18000fa0f  mov     [rsp+68h+var_44], 10002h
0x18000fa17  lea     rdx, [rsp+68h+var_40]
0x18000fa1c  jmp     short loc_18000FA23
0x18000fa1e  lea     rdx, [rsp+68h+var_48]
0x18000fa23  test    r8b, al
0x18000fa26  jz      short loc_18000FA36
0x18000fa28  mov     [rdx], r10d
0x18000fa2b  mov     dword ptr [rdx+4], 10006h
0x18000fa32  add     rdx, 8
0x18000fa36  test    al, 4
0x18000fa38  jz      short loc_18000FA48
0x18000fa3a  mov     [rdx], r10d
0x18000fa3d  mov     dword ptr [rdx+4], 10003h
0x18000fa44  add     rdx, 8
0x18000fa48  cmp     eax, 8
0x18000fa4b  jb      short loc_18000FA5B
0x18000fa4d  mov     [rdx], r10d
0x18000fa50  mov     dword ptr [rdx+4], 10007h
0x18000fa57  add     rdx, 8
0x18000fa5b  mov     r8d, ecx
0x18000fa5e  shr     r8d, 5
0x18000fa62  mov     r11d, 1FFh
0x18000fa68  test    r11d, r8d
0x18000fa6b  jz      short loc_18000FA8E
0x18000fa6d  mov     [rdx], r10d
0x18000fa70  mov     eax, ecx
0x18000fa72  shr     eax, 0Eh
0x18000fa75  and     ax, r9w
0x18000fa79  shl     ax, 2
0x18000fa7d  mov     [rdx+4], ax
0x18000fa81  and     r8w, r11w; unsigned __int64
0x18000fa85  mov     [rdx+6], r8w
0x18000fa8a  add     rdx, 8
0x18000fa8e  mov     eax, ecx
0x18000fa90  shr     eax, 0Fh
0x18000fa93  test    al, 7Fh
0x18000fa95  jz      short loc_18000FAB9
0x18000fa97  mov     [rdx], r10d
0x18000fa9a  shr     ecx, 16h
0x18000fa9d  and     cx, r9w
0x18000faa1  shl     cx, 2
0x18000faa5  add     cx, r9w
0x18000faa9  mov     [rdx+4], cx
0x18000faad  and     ax, 7Fh
0x18000fab1  mov     [rdx+6], ax
0x18000fab5  add     rdx, 8
0x18000fab9  lea     rax, [rsp+68h+var_48]
0x18000fabe  sub     rdx, rax
0x18000fac1  sar     rdx, 3; struct __WIL_RTL_FEATURE_USAGE_DATA *
0x18000fac5  test    rdx, rdx
0x18000fac8  jle     short loc_18000FAD5
0x18000faca  lea     rcx, [rsp+68h+var_48]; this
0x18000facf  call    ?WilApi_RecordFeatureUsageReports@details@wil@@YAXPEAU__WIL_RTL_FEATURE_USAGE_DATA@@_K@Z; wil::details::WilApi_RecordFeatureUsageReports(__WIL_RTL_FEATURE_USAGE_DATA *,unsigned __int64)
0x18000fad4  nop
0x18000fad5  mov     rcx, [rsp+68h+var_18]
0x18000fada  xor     rcx, rsp; StackCookie
0x18000fadd  call    __security_check_cookie
0x18000fae2  add     rsp, 68h
0x18000fae6  retn
```
