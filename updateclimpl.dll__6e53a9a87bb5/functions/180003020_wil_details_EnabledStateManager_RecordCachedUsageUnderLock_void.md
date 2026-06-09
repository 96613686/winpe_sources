# wil::details::EnabledStateManager::RecordCachedUsageUnderLock(void)

- ea: `0x180003020`
- end: `0x1800031f1`
- name: `?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXXZ`
- size: `465`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x180002e80`
- `0x180003200`
- `0x180003948`
- `0x1800161d0`

## callees

- `0x180002fc4`
- `0x180003020`
- `0x180010310`
- `0x1800148e0`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::details::EnabledStateManager *this)
{
  int *v2; // rbx
  int *v3; // rsi
  __int64 v4; // r9
  int v5; // r10d
  unsigned __int32 v6; // edx
  unsigned int v7; // ecx
  char *v8; // r8
  signed __int64 v9; // r8
  void (__fastcall *v10)(_QWORD, __int64, _QWORD, _QWORD); // rax
  _DWORD v11[2]; // [rsp+30h] [rbp-58h] BYREF
  char v12; // [rsp+38h] [rbp-50h] BYREF

  v2 = (int *)*((_QWORD *)this + 6);
  v3 = (int *)*((_QWORD *)this + 7);
  if ( (unsigned __int64)((char *)v3 - (char *)v2) >= 0x10 )
  {
    for ( ; v2 != v3; v2 += 4 )
    {
      v4 = *((_QWORD *)v2 + 1);
      v5 = *v2;
      _m_prefetchw((const void *)v4);
      v6 = _InterlockedAnd((volatile signed __int32 *)v4, 0xFFC0401E);
      v7 = (v6 >> 1) & 0xF;
      if ( v7 )
      {
        _m_prefetchw((const void *)(v4 + 4));
        v7 &= ~_InterlockedOr((volatile signed __int32 *)(v4 + 4), v7);
      }
      v8 = (char *)v11;
      if ( (v7 & 1) != 0 )
      {
        v11[0] = v5;
        v11[1] = 65538;
        v8 = &v12;
      }
      if ( (v7 & 2) != 0 )
      {
        *(_DWORD *)v8 = v5;
        *((_DWORD *)v8 + 1) = 65542;
        v8 += 8;
      }
      if ( (v7 & 4) != 0 )
      {
        *(_DWORD *)v8 = v5;
        *((_DWORD *)v8 + 1) = 65539;
        v8 += 8;
      }
      if ( v7 >= 8 )
      {
        *(_DWORD *)v8 = v5;
        *((_DWORD *)v8 + 1) = 65543;
        v8 += 8;
      }
      if ( ((v6 >> 5) & 0x1FF) != 0 )
      {
        *(_DWORD *)v8 = v5;
        *((_WORD *)v8 + 2) = 4 * ((v6 >> 14) & 1);
        *((_WORD *)v8 + 3) = (v6 >> 5) & 0x1FF;
        v8 += 8;
      }
      if ( ((v6 >> 15) & 0x7F) != 0 )
      {
        *(_DWORD *)v8 = v5;
        *((_WORD *)v8 + 2) = (4 * ((v6 >> 22) & 1)) | 1;
        *((_WORD *)v8 + 3) = (v6 >> 15) & 0x7F;
        v8 += 8;
      }
      v9 = (v8 - (char *)v11) >> 3;
      if ( v9 > 0 )
        wil::details::WilApi_RecordFeatureUsageReports(
          (wil::details *)v11,
          (struct __WIL_RTL_FEATURE_USAGE_DATA *)v9,
          v9);
    }
    *((_QWORD *)this + 7) = *((_QWORD *)this + 6);
    v10 = (void (__fastcall *)(_QWORD, __int64, _QWORD, _QWORD))g_wil_details_internalRecordFeatureUsage;
    if ( g_wil_details_internalRecordFeatureUsage
      || (v10 = (void (__fastcall *)(_QWORD, __int64, _QWORD, _QWORD))g_wil_details_apiRecordFeatureUsage) != 0 )
    {
      v10(0, 254, 0, 0);
    }
  }
}

```

## disassembly

```asm
0x180003020  mov     [rsp+arg_8], rbx
0x180003025  mov     [rsp+arg_10], rbp
0x18000302a  mov     [rsp+arg_18], rsi
0x18000302f  push    rdi
0x180003030  push    r14
0x180003032  push    r15
0x180003034  sub     rsp, 70h
0x180003038  mov     rax, cs:__security_cookie
0x18000303f  xor     rax, rsp
0x180003042  mov     [rsp+88h+var_28], rax
0x180003047  mov     rdi, rcx
0x18000304a  mov     rbx, [rcx+30h]
0x18000304e  mov     rsi, [rcx+38h]
0x180003052  mov     rax, rsi
0x180003055  sub     rax, rbx
0x180003058  cmp     rax, 10h
0x18000305c  jb      loc_1800031CA
0x180003062  cmp     rbx, rsi
0x180003065  jz      loc_180003197
0x18000306b  mov     ebp, 1
0x180003070  lea     r14d, [rbp+1]
0x180003074  mov     r15d, 1FFh
0x18000307a  mov     r9, [rbx+8]
0x18000307e  mov     r10d, [rbx]
0x180003081  prefetchw byte ptr [r9]
0x180003085  mov     eax, [r9]
0x180003088  mov     ecx, eax
0x18000308a  and     ecx, 0FFC0401Eh
0x180003090  lock cmpxchg [r9], ecx
0x180003095  jnz     short loc_180003088
0x180003097  mov     edx, eax
0x180003099  mov     ecx, eax
0x18000309b  shr     ecx, 1
0x18000309d  and     ecx, 0Fh
0x1800030a0  jz      short loc_1800030BD
0x1800030a2  prefetchw byte ptr [r9+4]
0x1800030a7  mov     eax, [r9+4]
0x1800030ab  mov     r8d, eax
0x1800030ae  or      r8d, ecx
0x1800030b1  lock cmpxchg [r9+4], r8d
0x1800030b7  jnz     short loc_1800030AB
0x1800030b9  not     eax
0x1800030bb  and     ecx, eax
0x1800030bd  lea     r8, [rsp+88h+var_58]
0x1800030c2  test    bpl, cl
0x1800030c5  jz      short loc_1800030D9
0x1800030c7  mov     [rsp+88h+var_58], r10d
0x1800030cc  mov     [rsp+88h+var_54], 10002h
0x1800030d4  lea     r8, [rsp+88h+var_50]
0x1800030d9  test    r14b, cl
0x1800030dc  jz      short loc_1800030ED
0x1800030de  mov     [r8], r10d
0x1800030e1  mov     dword ptr [r8+4], 10006h
0x1800030e9  add     r8, 8
0x1800030ed  test    cl, 4
0x1800030f0  jz      short loc_180003101
0x1800030f2  mov     [r8], r10d
0x1800030f5  mov     dword ptr [r8+4], 10003h
0x1800030fd  add     r8, 8
0x180003101  cmp     ecx, 8
0x180003104  jb      short loc_180003115
0x180003106  mov     [r8], r10d
0x180003109  mov     dword ptr [r8+4], 10007h
0x180003111  add     r8, 8
0x180003115  mov     ecx, edx
0x180003117  shr     ecx, 5
0x18000311a  test    r15d, ecx
0x18000311d  jz      short loc_180003140
0x18000311f  mov     [r8], r10d
0x180003122  mov     eax, edx
0x180003124  shr     eax, 0Eh
0x180003127  and     ax, bp
0x18000312a  shl     ax, 2
0x18000312e  mov     [r8+4], ax
0x180003133  and     cx, r15w
0x180003137  mov     [r8+6], cx
0x18000313c  add     r8, 8
0x180003140  mov     eax, edx
0x180003142  shr     eax, 0Fh
0x180003145  test    al, 7Fh
0x180003147  jz      short loc_18000316B
0x180003149  mov     [r8], r10d
0x18000314c  shr     edx, 16h
0x18000314f  and     dx, bp
0x180003152  shl     dx, 2
0x180003156  or      dx, bp
0x180003159  mov     [r8+4], dx
0x18000315e  and     ax, 7Fh
0x180003162  mov     [r8+6], ax
0x180003167  add     r8, 8
0x18000316b  lea     rax, [rsp+88h+var_58]
0x180003170  sub     r8, rax
0x180003173  sar     r8, 3; unsigned __int64
0x180003177  test    r8, r8
0x18000317a  jle     short loc_18000318A
0x18000317c  mov     rdx, r8; struct __WIL_RTL_FEATURE_USAGE_DATA *
0x18000317f  lea     rcx, [rsp+88h+var_58]; this
0x180003184  call    ?WilApi_RecordFeatureUsageReports@details@wil@@YAXPEAU__WIL_RTL_FEATURE_USAGE_DATA@@_K@Z; wil::details::WilApi_RecordFeatureUsageReports(__WIL_RTL_FEATURE_USAGE_DATA *,unsigned __int64)
0x180003189  nop
0x18000318a  add     rbx, 10h
0x18000318e  cmp     rbx, rsi
0x180003191  jnz     loc_18000307A
0x180003197  mov     rax, [rdi+30h]
0x18000319b  mov     [rdi+38h], rax
0x18000319f  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x1800031a6  test    rax, rax
0x1800031a9  jnz     short loc_1800031B7
0x1800031ab  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x1800031b2  test    rax, rax
0x1800031b5  jz      short loc_1800031CA
0x1800031b7  xor     r9d, r9d
0x1800031ba  xor     r8d, r8d
0x1800031bd  mov     edx, 0FEh
0x1800031c2  xor     ecx, ecx
0x1800031c4  call    _guard_dispatch_icall
0x1800031c9  nop
0x1800031ca  mov     rcx, [rsp+88h+var_28]
0x1800031cf  xor     rcx, rsp; StackCookie
0x1800031d2  call    __security_check_cookie
0x1800031d7  lea     r11, [rsp+88h+var_18]
0x1800031dc  mov     rbx, [r11+28h]
0x1800031e0  mov     rbp, [r11+30h]
0x1800031e4  mov     rsi, [r11+38h]
0x1800031e8  mov     rsp, r11
0x1800031eb  pop     r15
0x1800031ed  pop     r14
0x1800031ef  pop     rdi
0x1800031f0  retn
```
