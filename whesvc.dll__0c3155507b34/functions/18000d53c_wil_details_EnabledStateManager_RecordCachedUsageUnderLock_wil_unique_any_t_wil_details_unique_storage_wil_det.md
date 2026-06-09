# wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)

- ea: `0x18000d53c`
- end: `0x18000d6f3`
- name: `?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z`
- size: `439`
- prototype: `__int64 (__fastcall *__fastcall(__int64))(_QWORD, __int64, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000d0f0`
- `0x18000f650`
- `0x18000f6b0`

## callees

- `0x1800032e0`
- `0x18000d53c`
- `0x18000eca4`
- `0x180029010`

## pseudocode

```c
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
0x18000d53c  push    rbx
0x18000d53e  push    rbp
0x18000d53f  push    rsi
0x18000d540  push    rdi
0x18000d541  push    r14
0x18000d543  push    r15
0x18000d545  sub     rsp, 78h
0x18000d549  mov     rax, cs:__security_cookie
0x18000d550  xor     rax, rsp
0x18000d553  mov     [rsp+0A8h+var_48], rax
0x18000d558  mov     rsi, rcx
0x18000d55b  mov     rbx, [rcx+20h]
0x18000d55f  mov     rdi, [rcx+28h]
0x18000d563  mov     rax, rdi
0x18000d566  sub     rax, rbx
0x18000d569  cmp     rax, 10h
0x18000d56d  jb      loc_18000D6D9
0x18000d573  mov     ebp, 1
0x18000d578  lea     r14d, [rbp+1]
0x18000d57c  mov     r15d, 1FFh
0x18000d582  cmp     rbx, rdi
0x18000d585  jz      loc_18000D6A6
0x18000d58b  mov     r8, [rbx+8]
0x18000d58f  mov     r10d, [rbx]
0x18000d592  prefetchw byte ptr [r8]
0x18000d596  mov     eax, [r8]
0x18000d599  mov     ecx, eax
0x18000d59b  and     ecx, 0FFC0401Eh
0x18000d5a1  lock cmpxchg [r8], ecx
0x18000d5a6  jnz     short loc_18000D599
0x18000d5a8  mov     ecx, eax
0x18000d5aa  mov     r9d, eax
0x18000d5ad  shr     r9d, 1
0x18000d5b0  and     r9d, 0Fh
0x18000d5b4  jz      short loc_18000D5D3
0x18000d5b6  prefetchw byte ptr [r8+4]
0x18000d5bb  mov     eax, [r8+4]
0x18000d5bf  mov     edx, eax
0x18000d5c1  or      edx, r9d
0x18000d5c4  lock cmpxchg [r8+4], edx
0x18000d5ca  jnz     short loc_18000D5BF
0x18000d5cc  not     eax
0x18000d5ce  and     eax, r9d
0x18000d5d1  jmp     short loc_18000D5D6
0x18000d5d3  mov     eax, r9d
0x18000d5d6  test    bpl, al
0x18000d5d9  jz      short loc_18000D5EF
0x18000d5db  mov     [rsp+0A8h+var_78], r10d
0x18000d5e0  mov     [rsp+0A8h+var_74], 10002h
0x18000d5e8  lea     rdx, [rsp+0A8h+var_70]
0x18000d5ed  jmp     short loc_18000D5F4
0x18000d5ef  lea     rdx, [rsp+0A8h+var_78]
0x18000d5f4  test    r14b, al
0x18000d5f7  jz      short loc_18000D607
0x18000d5f9  mov     [rdx], r10d
0x18000d5fc  mov     dword ptr [rdx+4], 10006h
0x18000d603  add     rdx, 8
0x18000d607  test    al, 4
0x18000d609  jz      short loc_18000D619
0x18000d60b  mov     [rdx], r10d
0x18000d60e  mov     dword ptr [rdx+4], 10003h
0x18000d615  add     rdx, 8
0x18000d619  cmp     eax, 8
0x18000d61c  jb      short loc_18000D62C
0x18000d61e  mov     [rdx], r10d
0x18000d621  mov     dword ptr [rdx+4], 10007h
0x18000d628  add     rdx, 8
0x18000d62c  mov     r8d, ecx
0x18000d62f  shr     r8d, 5
0x18000d633  test    r15d, r8d
0x18000d636  jz      short loc_18000D658
0x18000d638  mov     [rdx], r10d
0x18000d63b  mov     eax, ecx
0x18000d63d  shr     eax, 0Eh
0x18000d640  and     ax, bp
0x18000d643  shl     ax, 2
0x18000d647  mov     [rdx+4], ax
0x18000d64b  and     r8w, r15w; unsigned __int64
0x18000d64f  mov     [rdx+6], r8w
0x18000d654  add     rdx, 8
0x18000d658  mov     eax, ecx
0x18000d65a  shr     eax, 0Fh
0x18000d65d  test    al, 7Fh
0x18000d65f  jz      short loc_18000D681
0x18000d661  mov     [rdx], r10d
0x18000d664  shr     ecx, 16h
0x18000d667  and     cx, bp
0x18000d66a  shl     cx, 2
0x18000d66e  add     cx, bp
0x18000d671  mov     [rdx+4], cx
0x18000d675  and     ax, 7Fh
0x18000d679  mov     [rdx+6], ax
0x18000d67d  add     rdx, 8
0x18000d681  lea     rax, [rsp+0A8h+var_78]
0x18000d686  sub     rdx, rax
0x18000d689  sar     rdx, 3; struct __WIL_RTL_FEATURE_USAGE_DATA *
0x18000d68d  test    rdx, rdx
0x18000d690  jle     short loc_18000D69D
0x18000d692  lea     rcx, [rsp+0A8h+var_78]; this
0x18000d697  call    ?WilApi_RecordFeatureUsageReports@details@wil@@YAXPEAU__WIL_RTL_FEATURE_USAGE_DATA@@_K@Z; wil::details::WilApi_RecordFeatureUsageReports(__WIL_RTL_FEATURE_USAGE_DATA *,unsigned __int64)
0x18000d69c  nop
0x18000d69d  add     rbx, 10h
0x18000d6a1  jmp     loc_18000D582
0x18000d6a6  mov     rax, [rsi+20h]
0x18000d6aa  mov     [rsi+28h], rax
0x18000d6ae  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x18000d6b5  test    rax, rax
0x18000d6b8  jnz     short loc_18000D6C6
0x18000d6ba  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x18000d6c1  test    rax, rax
0x18000d6c4  jz      short loc_18000D6D9
0x18000d6c6  xor     r9d, r9d
0x18000d6c9  xor     r8d, r8d
0x18000d6cc  mov     edx, 0FEh
0x18000d6d1  xor     ecx, ecx
0x18000d6d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d6d8  nop
0x18000d6d9  mov     rcx, [rsp+0A8h+var_48]
0x18000d6de  xor     rcx, rsp; StackCookie
0x18000d6e1  call    __security_check_cookie
0x18000d6e6  add     rsp, 78h
0x18000d6ea  pop     r15
0x18000d6ec  pop     r14
0x18000d6ee  pop     rdi
0x18000d6ef  pop     rsi
0x18000d6f0  pop     rbp
0x18000d6f1  pop     rbx
0x18000d6f2  retn
```
