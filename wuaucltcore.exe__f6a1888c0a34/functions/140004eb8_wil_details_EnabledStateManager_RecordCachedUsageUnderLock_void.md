# wil::details::EnabledStateManager::RecordCachedUsageUnderLock(void)

- ea: `0x140004eb8`
- end: `0x140005089`
- name: `?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXXZ`
- size: `465`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x140004cc4`
- `0x14000a5f0`
- `0x14000a740`
- `0x140022030`

## callees

- `0x140004c68`
- `0x140004eb8`
- `0x14001aa60`
- `0x1400206e0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x140004eb8  mov     [rsp+arg_8], rbx
0x140004ebd  mov     [rsp+arg_10], rbp
0x140004ec2  mov     [rsp+arg_18], rsi
0x140004ec7  push    rdi
0x140004ec8  push    r14
0x140004eca  push    r15
0x140004ecc  sub     rsp, 70h
0x140004ed0  mov     rax, cs:__security_cookie
0x140004ed7  xor     rax, rsp
0x140004eda  mov     [rsp+88h+var_28], rax
0x140004edf  mov     rdi, rcx
0x140004ee2  mov     rbx, [rcx+30h]
0x140004ee6  mov     rsi, [rcx+38h]
0x140004eea  mov     rax, rsi
0x140004eed  sub     rax, rbx
0x140004ef0  cmp     rax, 10h
0x140004ef4  jb      loc_140005062
0x140004efa  cmp     rbx, rsi
0x140004efd  jz      loc_14000502F
0x140004f03  mov     ebp, 1
0x140004f08  lea     r14d, [rbp+1]
0x140004f0c  mov     r15d, 1FFh
0x140004f12  mov     r9, [rbx+8]
0x140004f16  mov     r10d, [rbx]
0x140004f19  prefetchw byte ptr [r9]
0x140004f1d  mov     eax, [r9]
0x140004f20  mov     ecx, eax
0x140004f22  and     ecx, 0FFC0401Eh
0x140004f28  lock cmpxchg [r9], ecx
0x140004f2d  jnz     short loc_140004F20
0x140004f2f  mov     edx, eax
0x140004f31  mov     ecx, eax
0x140004f33  shr     ecx, 1
0x140004f35  and     ecx, 0Fh
0x140004f38  jz      short loc_140004F55
0x140004f3a  prefetchw byte ptr [r9+4]
0x140004f3f  mov     eax, [r9+4]
0x140004f43  mov     r8d, eax
0x140004f46  or      r8d, ecx
0x140004f49  lock cmpxchg [r9+4], r8d
0x140004f4f  jnz     short loc_140004F43
0x140004f51  not     eax
0x140004f53  and     ecx, eax
0x140004f55  lea     r8, [rsp+88h+var_58]
0x140004f5a  test    bpl, cl
0x140004f5d  jz      short loc_140004F71
0x140004f5f  mov     [rsp+88h+var_58], r10d
0x140004f64  mov     [rsp+88h+var_54], 10002h
0x140004f6c  lea     r8, [rsp+88h+var_50]
0x140004f71  test    r14b, cl
0x140004f74  jz      short loc_140004F85
0x140004f76  mov     [r8], r10d
0x140004f79  mov     dword ptr [r8+4], 10006h
0x140004f81  add     r8, 8
0x140004f85  test    cl, 4
0x140004f88  jz      short loc_140004F99
0x140004f8a  mov     [r8], r10d
0x140004f8d  mov     dword ptr [r8+4], 10003h
0x140004f95  add     r8, 8
0x140004f99  cmp     ecx, 8
0x140004f9c  jb      short loc_140004FAD
0x140004f9e  mov     [r8], r10d
0x140004fa1  mov     dword ptr [r8+4], 10007h
0x140004fa9  add     r8, 8
0x140004fad  mov     ecx, edx
0x140004faf  shr     ecx, 5
0x140004fb2  test    r15d, ecx
0x140004fb5  jz      short loc_140004FD8
0x140004fb7  mov     [r8], r10d
0x140004fba  mov     eax, edx
0x140004fbc  shr     eax, 0Eh
0x140004fbf  and     ax, bp
0x140004fc2  shl     ax, 2
0x140004fc6  mov     [r8+4], ax
0x140004fcb  and     cx, r15w
0x140004fcf  mov     [r8+6], cx
0x140004fd4  add     r8, 8
0x140004fd8  mov     eax, edx
0x140004fda  shr     eax, 0Fh
0x140004fdd  test    al, 7Fh
0x140004fdf  jz      short loc_140005003
0x140004fe1  mov     [r8], r10d
0x140004fe4  shr     edx, 16h
0x140004fe7  and     dx, bp
0x140004fea  shl     dx, 2
0x140004fee  or      dx, bp
0x140004ff1  mov     [r8+4], dx
0x140004ff6  and     ax, 7Fh
0x140004ffa  mov     [r8+6], ax
0x140004fff  add     r8, 8
0x140005003  lea     rax, [rsp+88h+var_58]
0x140005008  sub     r8, rax
0x14000500b  sar     r8, 3; unsigned __int64
0x14000500f  test    r8, r8
0x140005012  jle     short loc_140005022
0x140005014  mov     rdx, r8; struct __WIL_RTL_FEATURE_USAGE_DATA *
0x140005017  lea     rcx, [rsp+88h+var_58]; this
0x14000501c  call    ?WilApi_RecordFeatureUsageReports@details@wil@@YAXPEAU__WIL_RTL_FEATURE_USAGE_DATA@@_K@Z; wil::details::WilApi_RecordFeatureUsageReports(__WIL_RTL_FEATURE_USAGE_DATA *,unsigned __int64)
0x140005021  nop
0x140005022  add     rbx, 10h
0x140005026  cmp     rbx, rsi
0x140005029  jnz     loc_140004F12
0x14000502f  mov     rax, [rdi+30h]
0x140005033  mov     [rdi+38h], rax
0x140005037  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x14000503e  test    rax, rax
0x140005041  jnz     short loc_14000504F
0x140005043  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x14000504a  test    rax, rax
0x14000504d  jz      short loc_140005062
0x14000504f  xor     r9d, r9d
0x140005052  xor     r8d, r8d
0x140005055  mov     edx, 0FEh
0x14000505a  xor     ecx, ecx
0x14000505c  call    _guard_dispatch_icall
0x140005061  nop
0x140005062  mov     rcx, [rsp+88h+var_28]
0x140005067  xor     rcx, rsp; StackCookie
0x14000506a  call    __security_check_cookie
0x14000506f  lea     r11, [rsp+88h+var_18]
0x140005074  mov     rbx, [r11+28h]
0x140005078  mov     rbp, [r11+30h]
0x14000507c  mov     rsi, [r11+38h]
0x140005080  mov     rsp, r11
0x140005083  pop     r15
0x140005085  pop     r14
0x140005087  pop     rdi
0x140005088  retn
```
