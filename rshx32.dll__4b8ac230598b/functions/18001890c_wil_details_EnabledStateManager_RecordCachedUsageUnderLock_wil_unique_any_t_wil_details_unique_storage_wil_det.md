# wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)

- ea: `0x18001890c`
- end: `0x180018ac1`
- name: `?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z`
- size: `437`
- prototype: `__int64 (__fastcall *__fastcall(__int64))(_QWORD, __int64, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180016960`
- `0x1800169c0`
- `0x1800186d4`

## callees

- `0x18001890c`
- `0x180018e78`
- `0x18001d370`
- `0x18001e010`

## pseudocode

```c
__int64 (__fastcall *__fastcall wil::details::EnabledStateManager::RecordCachedUsageUnderLock(
        __int64 a1))(_QWORD, __int64, _QWORD, _QWORD)
{
  int *v1; // rdi
  int *v3; // rbx
  __int64 (__fastcall *result)(_QWORD, __int64, _QWORD, _QWORD); // rax
  __int64 v5; // r8
  int v6; // r10d
  unsigned __int32 v7; // ecx
  unsigned __int32 v8; // eax
  char *v9; // rdx
  unsigned __int64 v10; // r8
  __int64 v11; // rdx
  _DWORD v12[2]; // [rsp+30h] [rbp-78h] BYREF
  char v13; // [rsp+38h] [rbp-70h] BYREF

  v1 = *(int **)(a1 + 40);
  v3 = *(int **)(a1 + 32);
  result = (__int64 (__fastcall *)(_QWORD, __int64, _QWORD, _QWORD))((char *)v1 - (char *)v3);
  if ( (unsigned __int64)((char *)v1 - (char *)v3) >= 0x10 )
  {
    while ( v3 != v1 )
    {
      v5 = *((_QWORD *)v3 + 1);
      v6 = *v3;
      _m_prefetchw((const void *)v5);
      v7 = _InterlockedAnd((volatile signed __int32 *)v5, 0xFFC0401E);
      if ( ((v7 >> 1) & 0xF) != 0 )
      {
        _m_prefetchw((const void *)(v5 + 4));
        v8 = (v7 >> 1) & 0xF & ~_InterlockedOr((volatile signed __int32 *)(v5 + 4), (v7 >> 1) & 0xF);
      }
      else
      {
        v8 = 0;
      }
      if ( (v8 & 1) != 0 )
      {
        v12[0] = v6;
        v9 = &v13;
        v12[1] = 65538;
      }
      else
      {
        v9 = (char *)v12;
      }
      if ( (v8 & 2) != 0 )
      {
        *(_DWORD *)v9 = v6;
        *((_DWORD *)v9 + 1) = 65542;
        v9 += 8;
      }
      if ( (v8 & 4) != 0 )
      {
        *(_DWORD *)v9 = v6;
        *((_DWORD *)v9 + 1) = 65539;
        v9 += 8;
      }
      if ( v8 >= 8 )
      {
        *(_DWORD *)v9 = v6;
        *((_DWORD *)v9 + 1) = 65543;
        v9 += 8;
      }
      v10 = v7 >> 5;
      if ( (v10 & 0x1FF) != 0 )
      {
        LOWORD(v10) = v10 & 0x1FF;
        *(_DWORD *)v9 = v6;
        *((_WORD *)v9 + 3) = v10;
        *((_WORD *)v9 + 2) = 4 * ((v7 >> 14) & 1);
        v9 += 8;
      }
      if ( ((v7 >> 15) & 0x7F) != 0 )
      {
        *(_DWORD *)v9 = v6;
        *((_WORD *)v9 + 3) = (v7 >> 15) & 0x7F;
        *((_WORD *)v9 + 2) = 4 * ((v7 >> 22) & 1) + 1;
        v9 += 8;
      }
      v11 = (v9 - (char *)v12) >> 3;
      if ( v11 > 0 )
        wil::details::WilApi_RecordFeatureUsageReports(
          (wil::details *)v12,
          (struct __WIL_RTL_FEATURE_USAGE_DATA *)v11,
          v10);
      v3 += 4;
    }
    *(_QWORD *)(a1 + 40) = *(_QWORD *)(a1 + 32);
    result = (__int64 (__fastcall *)(_QWORD, __int64, _QWORD, _QWORD))g_wil_details_internalRecordFeatureUsage;
    if ( g_wil_details_internalRecordFeatureUsage )
      return (__int64 (__fastcall *)(_QWORD, __int64, _QWORD, _QWORD))result(0, 254, 0, 0);
    result = (__int64 (__fastcall *)(_QWORD, __int64, _QWORD, _QWORD))g_wil_details_apiRecordFeatureUsage;
    if ( g_wil_details_apiRecordFeatureUsage )
      return (__int64 (__fastcall *)(_QWORD, __int64, _QWORD, _QWORD))result(0, 254, 0, 0);
  }
  return result;
}

```

## disassembly

```asm
0x18001890c  push    rbx
0x18001890e  push    rbp
0x18001890f  push    rsi
0x180018910  push    rdi
0x180018911  push    r14
0x180018913  push    r15
0x180018915  sub     rsp, 78h
0x180018919  mov     rax, cs:__security_cookie
0x180018920  xor     rax, rsp
0x180018923  mov     [rsp+0A8h+var_48], rax
0x180018928  mov     rdi, [rcx+28h]
0x18001892c  mov     rsi, rcx
0x18001892f  mov     rbx, [rcx+20h]
0x180018933  mov     rax, rdi
0x180018936  sub     rax, rbx
0x180018939  cmp     rax, 10h
0x18001893d  jb      loc_180018AA7
0x180018943  mov     ebp, 1
0x180018948  mov     r15d, 1FFh
0x18001894e  lea     r14d, [rbp+1]
0x180018952  cmp     rbx, rdi
0x180018955  jz      loc_180018A75
0x18001895b  mov     r8, [rbx+8]
0x18001895f  mov     r10d, [rbx]
0x180018962  prefetchw byte ptr [r8]
0x180018966  mov     eax, [r8]
0x180018969  mov     ecx, eax
0x18001896b  and     ecx, 0FFC0401Eh
0x180018971  lock cmpxchg [r8], ecx
0x180018976  jnz     short loc_180018969
0x180018978  mov     r9d, eax
0x18001897b  mov     ecx, eax
0x18001897d  shr     r9d, 1
0x180018980  and     r9d, 0Fh
0x180018984  jz      short loc_1800189A3
0x180018986  prefetchw byte ptr [r8+4]
0x18001898b  mov     eax, [r8+4]
0x18001898f  mov     edx, eax
0x180018991  or      edx, r9d
0x180018994  lock cmpxchg [r8+4], edx
0x18001899a  jnz     short loc_18001898F
0x18001899c  not     eax
0x18001899e  and     eax, r9d
0x1800189a1  jmp     short loc_1800189A6
0x1800189a3  mov     eax, r9d
0x1800189a6  test    bpl, al
0x1800189a9  jz      short loc_1800189BF
0x1800189ab  mov     [rsp+0A8h+var_78], r10d
0x1800189b0  lea     rdx, [rsp+0A8h+var_70]
0x1800189b5  mov     [rsp+0A8h+var_74], 10002h
0x1800189bd  jmp     short loc_1800189C4
0x1800189bf  lea     rdx, [rsp+0A8h+var_78]
0x1800189c4  test    r14b, al
0x1800189c7  jz      short loc_1800189D7
0x1800189c9  mov     [rdx], r10d
0x1800189cc  mov     dword ptr [rdx+4], 10006h
0x1800189d3  add     rdx, 8
0x1800189d7  test    al, 4
0x1800189d9  jz      short loc_1800189E9
0x1800189db  mov     [rdx], r10d
0x1800189de  mov     dword ptr [rdx+4], 10003h
0x1800189e5  add     rdx, 8
0x1800189e9  cmp     eax, 8
0x1800189ec  jb      short loc_1800189FC
0x1800189ee  mov     [rdx], r10d
0x1800189f1  mov     dword ptr [rdx+4], 10007h
0x1800189f8  add     rdx, 8
0x1800189fc  mov     r8d, ecx
0x1800189ff  shr     r8d, 5
0x180018a03  test    r15d, r8d
0x180018a06  jz      short loc_180018A28
0x180018a08  and     r8w, r15w; unsigned __int64
0x180018a0c  mov     [rdx], r10d
0x180018a0f  mov     eax, ecx
0x180018a11  mov     [rdx+6], r8w
0x180018a16  shr     eax, 0Eh
0x180018a19  and     ax, bp
0x180018a1c  shl     ax, 2
0x180018a20  mov     [rdx+4], ax
0x180018a24  add     rdx, 8
0x180018a28  mov     eax, ecx
0x180018a2a  shr     eax, 0Fh
0x180018a2d  test    al, 7Fh
0x180018a2f  jz      short loc_180018A51
0x180018a31  shr     ecx, 16h
0x180018a34  and     ax, 7Fh
0x180018a38  and     cx, bp
0x180018a3b  mov     [rdx], r10d
0x180018a3e  shl     cx, 2
0x180018a42  add     cx, bp
0x180018a45  mov     [rdx+6], ax
0x180018a49  mov     [rdx+4], cx
0x180018a4d  add     rdx, 8
0x180018a51  lea     rax, [rsp+0A8h+var_78]
0x180018a56  sub     rdx, rax
0x180018a59  sar     rdx, 3; struct __WIL_RTL_FEATURE_USAGE_DATA *
0x180018a5d  test    rdx, rdx
0x180018a60  jle     short loc_180018A6C
0x180018a62  lea     rcx, [rsp+0A8h+var_78]; this
0x180018a67  call    ?WilApi_RecordFeatureUsageReports@details@wil@@YAXPEAU__WIL_RTL_FEATURE_USAGE_DATA@@_K@Z; wil::details::WilApi_RecordFeatureUsageReports(__WIL_RTL_FEATURE_USAGE_DATA *,unsigned __int64)
0x180018a6c  add     rbx, 10h
0x180018a70  jmp     loc_180018952
0x180018a75  mov     rax, [rsi+20h]
0x180018a79  mov     [rsi+28h], rax
0x180018a7d  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x180018a84  test    rax, rax
0x180018a87  jnz     short loc_180018A95
0x180018a89  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x180018a90  test    rax, rax
0x180018a93  jz      short loc_180018AA7
0x180018a95  xor     r9d, r9d
0x180018a98  xor     r8d, r8d
0x180018a9b  mov     edx, 0FEh
0x180018aa0  xor     ecx, ecx
0x180018aa2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018aa7  mov     rcx, [rsp+0A8h+var_48]
0x180018aac  xor     rcx, rsp; StackCookie
0x180018aaf  call    __security_check_cookie
0x180018ab4  add     rsp, 78h
0x180018ab8  pop     r15
0x180018aba  pop     r14
0x180018abc  pop     rdi
0x180018abd  pop     rsi
0x180018abe  pop     rbp
0x180018abf  pop     rbx
0x180018ac0  retn
```
