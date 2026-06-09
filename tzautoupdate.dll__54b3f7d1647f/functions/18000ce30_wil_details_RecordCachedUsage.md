# wil_details_RecordCachedUsage

- ea: `0x18000ce30`
- end: `0x18000cf77`
- name: `wil_details_RecordCachedUsage`
- size: `327`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180007a10`

## callees

- `0x180009be0`
- `0x18000ce30`
- `0x18001b150`

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
0x18000ce30  sub     rsp, 68h
0x18000ce34  mov     rax, cs:__security_cookie
0x18000ce3b  xor     rax, rsp
0x18000ce3e  mov     [rsp+68h+var_18], rax
0x18000ce43  mov     r9, rdx
0x18000ce46  mov     r10d, ecx
0x18000ce49  prefetchw byte ptr [rdx]
0x18000ce4c  mov     eax, [rdx]
0x18000ce4e  mov     r8d, eax
0x18000ce51  and     r8d, 0FFC0401Eh
0x18000ce58  lock cmpxchg [rdx], r8d
0x18000ce5d  jnz     short loc_18000CE4E
0x18000ce5f  mov     ecx, eax
0x18000ce61  mov     r8d, eax
0x18000ce64  shr     r8d, 1
0x18000ce67  and     r8d, 0Fh
0x18000ce6b  jz      short loc_18000CE88
0x18000ce6d  prefetchw byte ptr [rdx+4]
0x18000ce71  mov     eax, [rdx+4]
0x18000ce74  mov     edx, eax
0x18000ce76  or      edx, r8d
0x18000ce79  lock cmpxchg [r9+4], edx
0x18000ce7f  jnz     short loc_18000CE74
0x18000ce81  not     eax
0x18000ce83  and     eax, r8d
0x18000ce86  jmp     short loc_18000CE8B
0x18000ce88  mov     eax, r8d
0x18000ce8b  mov     r8d, 2
0x18000ce91  lea     r9d, [r8-1]
0x18000ce95  test    r9b, al
0x18000ce98  jz      short loc_18000CEAE
0x18000ce9a  mov     [rsp+68h+var_48], r10d
0x18000ce9f  mov     [rsp+68h+var_44], 10002h
0x18000cea7  lea     rdx, [rsp+68h+var_40]
0x18000ceac  jmp     short loc_18000CEB3
0x18000ceae  lea     rdx, [rsp+68h+var_48]
0x18000ceb3  test    r8b, al
0x18000ceb6  jz      short loc_18000CEC6
0x18000ceb8  mov     [rdx], r10d
0x18000cebb  mov     dword ptr [rdx+4], 10006h
0x18000cec2  add     rdx, 8
0x18000cec6  test    al, 4
0x18000cec8  jz      short loc_18000CED8
0x18000ceca  mov     [rdx], r10d
0x18000cecd  mov     dword ptr [rdx+4], 10003h
0x18000ced4  add     rdx, 8
0x18000ced8  cmp     eax, 8
0x18000cedb  jb      short loc_18000CEEB
0x18000cedd  mov     [rdx], r10d
0x18000cee0  mov     dword ptr [rdx+4], 10007h
0x18000cee7  add     rdx, 8
0x18000ceeb  mov     r8d, ecx
0x18000ceee  shr     r8d, 5
0x18000cef2  mov     r11d, 1FFh
0x18000cef8  test    r11d, r8d
0x18000cefb  jz      short loc_18000CF1E
0x18000cefd  mov     [rdx], r10d
0x18000cf00  mov     eax, ecx
0x18000cf02  shr     eax, 0Eh
0x18000cf05  and     ax, r9w
0x18000cf09  shl     ax, 2
0x18000cf0d  mov     [rdx+4], ax
0x18000cf11  and     r8w, r11w; unsigned __int64
0x18000cf15  mov     [rdx+6], r8w
0x18000cf1a  add     rdx, 8
0x18000cf1e  mov     eax, ecx
0x18000cf20  shr     eax, 0Fh
0x18000cf23  test    al, 7Fh
0x18000cf25  jz      short loc_18000CF49
0x18000cf27  mov     [rdx], r10d
0x18000cf2a  shr     ecx, 16h
0x18000cf2d  and     cx, r9w
0x18000cf31  shl     cx, 2
0x18000cf35  add     cx, r9w
0x18000cf39  mov     [rdx+4], cx
0x18000cf3d  and     ax, 7Fh
0x18000cf41  mov     [rdx+6], ax
0x18000cf45  add     rdx, 8
0x18000cf49  lea     rax, [rsp+68h+var_48]
0x18000cf4e  sub     rdx, rax
0x18000cf51  sar     rdx, 3; struct __WIL_RTL_FEATURE_USAGE_DATA *
0x18000cf55  test    rdx, rdx
0x18000cf58  jle     short loc_18000CF65
0x18000cf5a  lea     rcx, [rsp+68h+var_48]; this
0x18000cf5f  call    ?WilApi_RecordFeatureUsageReports@details@wil@@YAXPEAU__WIL_RTL_FEATURE_USAGE_DATA@@_K@Z; wil::details::WilApi_RecordFeatureUsageReports(__WIL_RTL_FEATURE_USAGE_DATA *,unsigned __int64)
0x18000cf64  nop
0x18000cf65  mov     rcx, [rsp+68h+var_18]
0x18000cf6a  xor     rcx, rsp; StackCookie
0x18000cf6d  call    __security_check_cookie
0x18000cf72  add     rsp, 68h
0x18000cf76  retn
```
