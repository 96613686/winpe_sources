# wil_details_RecordCachedUsage

- ea: `0x1800138f0`
- end: `0x180013a37`
- name: `wil_details_RecordCachedUsage`
- size: `327`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000fdb0`

## callees

- `0x180011dd4`
- `0x1800138f0`
- `0x18003c240`

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
0x1800138f0  sub     rsp, 68h
0x1800138f4  mov     rax, cs:__security_cookie
0x1800138fb  xor     rax, rsp
0x1800138fe  mov     [rsp+68h+var_18], rax
0x180013903  mov     r9, rdx
0x180013906  mov     r10d, ecx
0x180013909  prefetchw byte ptr [rdx]
0x18001390c  mov     eax, [rdx]
0x18001390e  mov     r8d, eax
0x180013911  and     r8d, 0FFC0401Eh
0x180013918  lock cmpxchg [rdx], r8d
0x18001391d  jnz     short loc_18001390E
0x18001391f  mov     ecx, eax
0x180013921  mov     r8d, eax
0x180013924  shr     r8d, 1
0x180013927  and     r8d, 0Fh
0x18001392b  jz      short loc_180013948
0x18001392d  prefetchw byte ptr [rdx+4]
0x180013931  mov     eax, [rdx+4]
0x180013934  mov     edx, eax
0x180013936  or      edx, r8d
0x180013939  lock cmpxchg [r9+4], edx
0x18001393f  jnz     short loc_180013934
0x180013941  not     eax
0x180013943  and     eax, r8d
0x180013946  jmp     short loc_18001394B
0x180013948  mov     eax, r8d
0x18001394b  mov     r8d, 2
0x180013951  lea     r9d, [r8-1]
0x180013955  test    r9b, al
0x180013958  jz      short loc_18001396E
0x18001395a  mov     [rsp+68h+var_48], r10d
0x18001395f  mov     [rsp+68h+var_44], 10002h
0x180013967  lea     rdx, [rsp+68h+var_40]
0x18001396c  jmp     short loc_180013973
0x18001396e  lea     rdx, [rsp+68h+var_48]
0x180013973  test    r8b, al
0x180013976  jz      short loc_180013986
0x180013978  mov     [rdx], r10d
0x18001397b  mov     dword ptr [rdx+4], 10006h
0x180013982  add     rdx, 8
0x180013986  test    al, 4
0x180013988  jz      short loc_180013998
0x18001398a  mov     [rdx], r10d
0x18001398d  mov     dword ptr [rdx+4], 10003h
0x180013994  add     rdx, 8
0x180013998  cmp     eax, 8
0x18001399b  jb      short loc_1800139AB
0x18001399d  mov     [rdx], r10d
0x1800139a0  mov     dword ptr [rdx+4], 10007h
0x1800139a7  add     rdx, 8
0x1800139ab  mov     r8d, ecx
0x1800139ae  shr     r8d, 5
0x1800139b2  mov     r11d, 1FFh
0x1800139b8  test    r11d, r8d
0x1800139bb  jz      short loc_1800139DE
0x1800139bd  mov     [rdx], r10d
0x1800139c0  mov     eax, ecx
0x1800139c2  shr     eax, 0Eh
0x1800139c5  and     ax, r9w
0x1800139c9  shl     ax, 2
0x1800139cd  mov     [rdx+4], ax
0x1800139d1  and     r8w, r11w; unsigned __int64
0x1800139d5  mov     [rdx+6], r8w
0x1800139da  add     rdx, 8
0x1800139de  mov     eax, ecx
0x1800139e0  shr     eax, 0Fh
0x1800139e3  test    al, 7Fh
0x1800139e5  jz      short loc_180013A09
0x1800139e7  mov     [rdx], r10d
0x1800139ea  shr     ecx, 16h
0x1800139ed  and     cx, r9w
0x1800139f1  shl     cx, 2
0x1800139f5  add     cx, r9w
0x1800139f9  mov     [rdx+4], cx
0x1800139fd  and     ax, 7Fh
0x180013a01  mov     [rdx+6], ax
0x180013a05  add     rdx, 8
0x180013a09  lea     rax, [rsp+68h+var_48]
0x180013a0e  sub     rdx, rax
0x180013a11  sar     rdx, 3; struct __WIL_RTL_FEATURE_USAGE_DATA *
0x180013a15  test    rdx, rdx
0x180013a18  jle     short loc_180013A25
0x180013a1a  lea     rcx, [rsp+68h+var_48]; this
0x180013a1f  call    ?WilApi_RecordFeatureUsageReports@details@wil@@YAXPEAU__WIL_RTL_FEATURE_USAGE_DATA@@_K@Z; wil::details::WilApi_RecordFeatureUsageReports(__WIL_RTL_FEATURE_USAGE_DATA *,unsigned __int64)
0x180013a24  nop
0x180013a25  mov     rcx, [rsp+68h+var_18]
0x180013a2a  xor     rcx, rsp; StackCookie
0x180013a2d  call    __security_check_cookie
0x180013a32  add     rsp, 68h
0x180013a36  retn
```
