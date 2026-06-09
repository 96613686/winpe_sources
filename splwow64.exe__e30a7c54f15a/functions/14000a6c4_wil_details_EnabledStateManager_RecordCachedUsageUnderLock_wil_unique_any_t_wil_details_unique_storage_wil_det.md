# wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)

- ea: `0x14000a6c4`
- end: `0x14000a879`
- name: `?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z`
- size: `437`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140008810`
- `0x140008950`
- `0x14000a0bc`

## callees

- `0x140001ee0`
- `0x14000a6c4`
- `0x14000c104`
- `0x140016010`

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
0x14000a6c4  push    rbx
0x14000a6c6  push    rbp
0x14000a6c7  push    rsi
0x14000a6c8  push    rdi
0x14000a6c9  push    r14
0x14000a6cb  push    r15
0x14000a6cd  sub     rsp, 78h
0x14000a6d1  mov     rax, cs:__security_cookie
0x14000a6d8  xor     rax, rsp
0x14000a6db  mov     [rsp+0A8h+var_48], rax
0x14000a6e0  mov     rdi, [rcx+28h]
0x14000a6e4  mov     rsi, rcx
0x14000a6e7  mov     rbx, [rcx+20h]
0x14000a6eb  mov     rax, rdi
0x14000a6ee  sub     rax, rbx
0x14000a6f1  cmp     rax, 10h
0x14000a6f5  jb      loc_14000A85F
0x14000a6fb  mov     ebp, 1
0x14000a700  mov     r15d, 1FFh
0x14000a706  lea     r14d, [rbp+1]
0x14000a70a  cmp     rbx, rdi
0x14000a70d  jz      loc_14000A82D
0x14000a713  mov     r8, [rbx+8]
0x14000a717  mov     r10d, [rbx]
0x14000a71a  prefetchw byte ptr [r8]
0x14000a71e  mov     eax, [r8]
0x14000a721  mov     ecx, eax
0x14000a723  and     ecx, 0FFC0401Eh
0x14000a729  lock cmpxchg [r8], ecx
0x14000a72e  jnz     short loc_14000A721
0x14000a730  mov     r9d, eax
0x14000a733  mov     ecx, eax
0x14000a735  shr     r9d, 1
0x14000a738  and     r9d, 0Fh
0x14000a73c  jz      short loc_14000A75B
0x14000a73e  prefetchw byte ptr [r8+4]
0x14000a743  mov     eax, [r8+4]
0x14000a747  mov     edx, eax
0x14000a749  or      edx, r9d
0x14000a74c  lock cmpxchg [r8+4], edx
0x14000a752  jnz     short loc_14000A747
0x14000a754  not     eax
0x14000a756  and     eax, r9d
0x14000a759  jmp     short loc_14000A75E
0x14000a75b  mov     eax, r9d
0x14000a75e  test    bpl, al
0x14000a761  jz      short loc_14000A777
0x14000a763  mov     [rsp+0A8h+var_78], r10d
0x14000a768  lea     rdx, [rsp+0A8h+var_70]
0x14000a76d  mov     [rsp+0A8h+var_74], 10002h
0x14000a775  jmp     short loc_14000A77C
0x14000a777  lea     rdx, [rsp+0A8h+var_78]
0x14000a77c  test    r14b, al
0x14000a77f  jz      short loc_14000A78F
0x14000a781  mov     [rdx], r10d
0x14000a784  mov     dword ptr [rdx+4], 10006h
0x14000a78b  add     rdx, 8
0x14000a78f  test    al, 4
0x14000a791  jz      short loc_14000A7A1
0x14000a793  mov     [rdx], r10d
0x14000a796  mov     dword ptr [rdx+4], 10003h
0x14000a79d  add     rdx, 8
0x14000a7a1  cmp     eax, 8
0x14000a7a4  jb      short loc_14000A7B4
0x14000a7a6  mov     [rdx], r10d
0x14000a7a9  mov     dword ptr [rdx+4], 10007h
0x14000a7b0  add     rdx, 8
0x14000a7b4  mov     r8d, ecx
0x14000a7b7  shr     r8d, 5
0x14000a7bb  test    r15d, r8d
0x14000a7be  jz      short loc_14000A7E0
0x14000a7c0  and     r8w, r15w; unsigned __int64
0x14000a7c4  mov     [rdx], r10d
0x14000a7c7  mov     eax, ecx
0x14000a7c9  mov     [rdx+6], r8w
0x14000a7ce  shr     eax, 0Eh
0x14000a7d1  and     ax, bp
0x14000a7d4  shl     ax, 2
0x14000a7d8  mov     [rdx+4], ax
0x14000a7dc  add     rdx, 8
0x14000a7e0  mov     eax, ecx
0x14000a7e2  shr     eax, 0Fh
0x14000a7e5  test    al, 7Fh
0x14000a7e7  jz      short loc_14000A809
0x14000a7e9  shr     ecx, 16h
0x14000a7ec  and     ax, 7Fh
0x14000a7f0  and     cx, bp
0x14000a7f3  mov     [rdx], r10d
0x14000a7f6  shl     cx, 2
0x14000a7fa  add     cx, bp
0x14000a7fd  mov     [rdx+6], ax
0x14000a801  mov     [rdx+4], cx
0x14000a805  add     rdx, 8
0x14000a809  lea     rax, [rsp+0A8h+var_78]
0x14000a80e  sub     rdx, rax
0x14000a811  sar     rdx, 3; struct __WIL_RTL_FEATURE_USAGE_DATA *
0x14000a815  test    rdx, rdx
0x14000a818  jle     short loc_14000A824
0x14000a81a  lea     rcx, [rsp+0A8h+var_78]; this
0x14000a81f  call    ?WilApi_RecordFeatureUsageReports@details@wil@@YAXPEAU__WIL_RTL_FEATURE_USAGE_DATA@@_K@Z; wil::details::WilApi_RecordFeatureUsageReports(__WIL_RTL_FEATURE_USAGE_DATA *,unsigned __int64)
0x14000a824  add     rbx, 10h
0x14000a828  jmp     loc_14000A70A
0x14000a82d  mov     rax, [rsi+20h]
0x14000a831  mov     [rsi+28h], rax
0x14000a835  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x14000a83c  test    rax, rax
0x14000a83f  jnz     short loc_14000A84D
0x14000a841  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x14000a848  test    rax, rax
0x14000a84b  jz      short loc_14000A85F
0x14000a84d  xor     r9d, r9d
0x14000a850  xor     r8d, r8d
0x14000a853  mov     edx, 0FEh
0x14000a858  xor     ecx, ecx
0x14000a85a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a85f  mov     rcx, [rsp+0A8h+var_48]
0x14000a864  xor     rcx, rsp; StackCookie
0x14000a867  call    __security_check_cookie
0x14000a86c  add     rsp, 78h
0x14000a870  pop     r15
0x14000a872  pop     r14
0x14000a874  pop     rdi
0x14000a875  pop     rsi
0x14000a876  pop     rbp
0x14000a877  pop     rbx
0x14000a878  retn
```
