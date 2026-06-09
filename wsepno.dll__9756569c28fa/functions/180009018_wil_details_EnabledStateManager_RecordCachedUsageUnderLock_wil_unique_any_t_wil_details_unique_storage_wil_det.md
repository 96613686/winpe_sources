# wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)

- ea: `0x180009018`
- end: `0x1800091cf`
- name: `?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z`
- size: `439`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180003c50`
- `0x180003e30`
- `0x180008474`

## callees

- `0x180001770`
- `0x180009018`
- `0x18000b154`
- `0x18000f010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 (__fastcall *__fastcall wil::details::EnabledStateManager::RecordCachedUsageUnderLock(
        __int64 a1))(_QWORD, __int64, _QWORD, _QWORD)
{
  int *v2; // rbx
  int *v3; // rdi
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

  v2 = *(int **)(a1 + 32);
  v3 = *(int **)(a1 + 40);
  result = (__int64 (__fastcall *)(_QWORD, __int64, _QWORD, _QWORD))((char *)v3 - (char *)v2);
  if ( (unsigned __int64)((char *)v3 - (char *)v2) >= 0x10 )
  {
    while ( v2 != v3 )
    {
      v5 = *((_QWORD *)v2 + 1);
      v6 = *v2;
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
        v12[1] = 65538;
        v9 = &v13;
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
        *(_DWORD *)v9 = v6;
        *((_WORD *)v9 + 2) = 4 * ((v7 >> 14) & 1);
        LOWORD(v10) = v10 & 0x1FF;
        *((_WORD *)v9 + 3) = v10;
        v9 += 8;
      }
      if ( ((v7 >> 15) & 0x7F) != 0 )
      {
        *(_DWORD *)v9 = v6;
        *((_WORD *)v9 + 2) = 4 * ((v7 >> 22) & 1) + 1;
        *((_WORD *)v9 + 3) = (v7 >> 15) & 0x7F;
        v9 += 8;
      }
      v11 = (v9 - (char *)v12) >> 3;
      if ( v11 > 0 )
        wil::details::WilApi_RecordFeatureUsageReports(
          (wil::details *)v12,
          (struct __WIL_RTL_FEATURE_USAGE_DATA *)v11,
          v10);
      v2 += 4;
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
0x180009018  push    rbx
0x18000901a  push    rbp
0x18000901b  push    rsi
0x18000901c  push    rdi
0x18000901d  push    r14
0x18000901f  push    r15
0x180009021  sub     rsp, 78h
0x180009025  mov     rax, cs:__security_cookie
0x18000902c  xor     rax, rsp
0x18000902f  mov     [rsp+0A8h+var_48], rax
0x180009034  mov     rsi, rcx
0x180009037  mov     rbx, [rcx+20h]
0x18000903b  mov     rdi, [rcx+28h]
0x18000903f  mov     rax, rdi
0x180009042  sub     rax, rbx
0x180009045  cmp     rax, 10h
0x180009049  jb      loc_1800091B5
0x18000904f  mov     ebp, 1
0x180009054  lea     r14d, [rbp+1]
0x180009058  mov     r15d, 1FFh
0x18000905e  cmp     rbx, rdi
0x180009061  jz      loc_180009182
0x180009067  mov     r8, [rbx+8]
0x18000906b  mov     r10d, [rbx]
0x18000906e  prefetchw byte ptr [r8]
0x180009072  mov     eax, [r8]
0x180009075  mov     ecx, eax
0x180009077  and     ecx, 0FFC0401Eh
0x18000907d  lock cmpxchg [r8], ecx
0x180009082  jnz     short loc_180009075
0x180009084  mov     ecx, eax
0x180009086  mov     r9d, eax
0x180009089  shr     r9d, 1
0x18000908c  and     r9d, 0Fh
0x180009090  jz      short loc_1800090AF
0x180009092  prefetchw byte ptr [r8+4]
0x180009097  mov     eax, [r8+4]
0x18000909b  mov     edx, eax
0x18000909d  or      edx, r9d
0x1800090a0  lock cmpxchg [r8+4], edx
0x1800090a6  jnz     short loc_18000909B
0x1800090a8  not     eax
0x1800090aa  and     eax, r9d
0x1800090ad  jmp     short loc_1800090B2
0x1800090af  mov     eax, r9d
0x1800090b2  test    bpl, al
0x1800090b5  jz      short loc_1800090CB
0x1800090b7  mov     [rsp+0A8h+var_78], r10d
0x1800090bc  mov     [rsp+0A8h+var_74], 10002h
0x1800090c4  lea     rdx, [rsp+0A8h+var_70]
0x1800090c9  jmp     short loc_1800090D0
0x1800090cb  lea     rdx, [rsp+0A8h+var_78]
0x1800090d0  test    r14b, al
0x1800090d3  jz      short loc_1800090E3
0x1800090d5  mov     [rdx], r10d
0x1800090d8  mov     dword ptr [rdx+4], 10006h
0x1800090df  add     rdx, 8
0x1800090e3  test    al, 4
0x1800090e5  jz      short loc_1800090F5
0x1800090e7  mov     [rdx], r10d
0x1800090ea  mov     dword ptr [rdx+4], 10003h
0x1800090f1  add     rdx, 8
0x1800090f5  cmp     eax, 8
0x1800090f8  jb      short loc_180009108
0x1800090fa  mov     [rdx], r10d
0x1800090fd  mov     dword ptr [rdx+4], 10007h
0x180009104  add     rdx, 8
0x180009108  mov     r8d, ecx
0x18000910b  shr     r8d, 5
0x18000910f  test    r15d, r8d
0x180009112  jz      short loc_180009134
0x180009114  mov     [rdx], r10d
0x180009117  mov     eax, ecx
0x180009119  shr     eax, 0Eh
0x18000911c  and     ax, bp
0x18000911f  shl     ax, 2
0x180009123  mov     [rdx+4], ax
0x180009127  and     r8w, r15w; unsigned __int64
0x18000912b  mov     [rdx+6], r8w
0x180009130  add     rdx, 8
0x180009134  mov     eax, ecx
0x180009136  shr     eax, 0Fh
0x180009139  test    al, 7Fh
0x18000913b  jz      short loc_18000915D
0x18000913d  mov     [rdx], r10d
0x180009140  shr     ecx, 16h
0x180009143  and     cx, bp
0x180009146  shl     cx, 2
0x18000914a  add     cx, bp
0x18000914d  mov     [rdx+4], cx
0x180009151  and     ax, 7Fh
0x180009155  mov     [rdx+6], ax
0x180009159  add     rdx, 8
0x18000915d  lea     rax, [rsp+0A8h+var_78]
0x180009162  sub     rdx, rax
0x180009165  sar     rdx, 3; struct __WIL_RTL_FEATURE_USAGE_DATA *
0x180009169  test    rdx, rdx
0x18000916c  jle     short loc_180009179
0x18000916e  lea     rcx, [rsp+0A8h+var_78]; this
0x180009173  call    ?WilApi_RecordFeatureUsageReports@details@wil@@YAXPEAU__WIL_RTL_FEATURE_USAGE_DATA@@_K@Z; wil::details::WilApi_RecordFeatureUsageReports(__WIL_RTL_FEATURE_USAGE_DATA *,unsigned __int64)
0x180009178  nop
0x180009179  add     rbx, 10h
0x18000917d  jmp     loc_18000905E
0x180009182  mov     rax, [rsi+20h]
0x180009186  mov     [rsi+28h], rax
0x18000918a  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x180009191  test    rax, rax
0x180009194  jnz     short loc_1800091A2
0x180009196  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x18000919d  test    rax, rax
0x1800091a0  jz      short loc_1800091B5
0x1800091a2  xor     r9d, r9d
0x1800091a5  xor     r8d, r8d
0x1800091a8  mov     edx, 0FEh
0x1800091ad  xor     ecx, ecx
0x1800091af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800091b4  nop
0x1800091b5  mov     rcx, [rsp+0A8h+var_48]
0x1800091ba  xor     rcx, rsp; StackCookie
0x1800091bd  call    __security_check_cookie
0x1800091c2  add     rsp, 78h
0x1800091c6  pop     r15
0x1800091c8  pop     r14
0x1800091ca  pop     rdi
0x1800091cb  pop     rsi
0x1800091cc  pop     rbp
0x1800091cd  pop     rbx
0x1800091ce  retn
```
