# wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)

- ea: `0x180006b40`
- end: `0x180006cf5`
- name: `?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z`
- size: `437`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000671c`

## callees

- `0x180001670`
- `0x180006b40`
- `0x180008a84`
- `0x18000e010`

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
0x180006b40  push    rbx
0x180006b42  push    rbp
0x180006b43  push    rsi
0x180006b44  push    rdi
0x180006b45  push    r14
0x180006b47  push    r15
0x180006b49  sub     rsp, 78h
0x180006b4d  mov     rax, cs:__security_cookie
0x180006b54  xor     rax, rsp
0x180006b57  mov     [rsp+0A8h+var_48], rax
0x180006b5c  mov     rdi, [rcx+28h]
0x180006b60  mov     rsi, rcx
0x180006b63  mov     rbx, [rcx+20h]
0x180006b67  mov     rax, rdi
0x180006b6a  sub     rax, rbx
0x180006b6d  cmp     rax, 10h
0x180006b71  jb      loc_180006CDB
0x180006b77  mov     ebp, 1
0x180006b7c  mov     r15d, 1FFh
0x180006b82  lea     r14d, [rbp+1]
0x180006b86  cmp     rbx, rdi
0x180006b89  jz      loc_180006CA9
0x180006b8f  mov     r8, [rbx+8]
0x180006b93  mov     r10d, [rbx]
0x180006b96  prefetchw byte ptr [r8]
0x180006b9a  mov     eax, [r8]
0x180006b9d  mov     ecx, eax
0x180006b9f  and     ecx, 0FFC0401Eh
0x180006ba5  lock cmpxchg [r8], ecx
0x180006baa  jnz     short loc_180006B9D
0x180006bac  mov     r9d, eax
0x180006baf  mov     ecx, eax
0x180006bb1  shr     r9d, 1
0x180006bb4  and     r9d, 0Fh
0x180006bb8  jz      short loc_180006BD7
0x180006bba  prefetchw byte ptr [r8+4]
0x180006bbf  mov     eax, [r8+4]
0x180006bc3  mov     edx, eax
0x180006bc5  or      edx, r9d
0x180006bc8  lock cmpxchg [r8+4], edx
0x180006bce  jnz     short loc_180006BC3
0x180006bd0  not     eax
0x180006bd2  and     eax, r9d
0x180006bd5  jmp     short loc_180006BDA
0x180006bd7  mov     eax, r9d
0x180006bda  test    bpl, al
0x180006bdd  jz      short loc_180006BF3
0x180006bdf  mov     [rsp+0A8h+var_78], r10d
0x180006be4  lea     rdx, [rsp+0A8h+var_70]
0x180006be9  mov     [rsp+0A8h+var_74], 10002h
0x180006bf1  jmp     short loc_180006BF8
0x180006bf3  lea     rdx, [rsp+0A8h+var_78]
0x180006bf8  test    r14b, al
0x180006bfb  jz      short loc_180006C0B
0x180006bfd  mov     [rdx], r10d
0x180006c00  mov     dword ptr [rdx+4], 10006h
0x180006c07  add     rdx, 8
0x180006c0b  test    al, 4
0x180006c0d  jz      short loc_180006C1D
0x180006c0f  mov     [rdx], r10d
0x180006c12  mov     dword ptr [rdx+4], 10003h
0x180006c19  add     rdx, 8
0x180006c1d  cmp     eax, 8
0x180006c20  jb      short loc_180006C30
0x180006c22  mov     [rdx], r10d
0x180006c25  mov     dword ptr [rdx+4], 10007h
0x180006c2c  add     rdx, 8
0x180006c30  mov     r8d, ecx
0x180006c33  shr     r8d, 5
0x180006c37  test    r15d, r8d
0x180006c3a  jz      short loc_180006C5C
0x180006c3c  and     r8w, r15w; unsigned __int64
0x180006c40  mov     [rdx], r10d
0x180006c43  mov     eax, ecx
0x180006c45  mov     [rdx+6], r8w
0x180006c4a  shr     eax, 0Eh
0x180006c4d  and     ax, bp
0x180006c50  shl     ax, 2
0x180006c54  mov     [rdx+4], ax
0x180006c58  add     rdx, 8
0x180006c5c  mov     eax, ecx
0x180006c5e  shr     eax, 0Fh
0x180006c61  test    al, 7Fh
0x180006c63  jz      short loc_180006C85
0x180006c65  shr     ecx, 16h
0x180006c68  and     ax, 7Fh
0x180006c6c  and     cx, bp
0x180006c6f  mov     [rdx], r10d
0x180006c72  shl     cx, 2
0x180006c76  add     cx, bp
0x180006c79  mov     [rdx+6], ax
0x180006c7d  mov     [rdx+4], cx
0x180006c81  add     rdx, 8
0x180006c85  lea     rax, [rsp+0A8h+var_78]
0x180006c8a  sub     rdx, rax
0x180006c8d  sar     rdx, 3; struct __WIL_RTL_FEATURE_USAGE_DATA *
0x180006c91  test    rdx, rdx
0x180006c94  jle     short loc_180006CA0
0x180006c96  lea     rcx, [rsp+0A8h+var_78]; this
0x180006c9b  call    ?WilApi_RecordFeatureUsageReports@details@wil@@YAXPEAU__WIL_RTL_FEATURE_USAGE_DATA@@_K@Z; wil::details::WilApi_RecordFeatureUsageReports(__WIL_RTL_FEATURE_USAGE_DATA *,unsigned __int64)
0x180006ca0  add     rbx, 10h
0x180006ca4  jmp     loc_180006B86
0x180006ca9  mov     rax, [rsi+20h]
0x180006cad  mov     [rsi+28h], rax
0x180006cb1  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x180006cb8  test    rax, rax
0x180006cbb  jnz     short loc_180006CC9
0x180006cbd  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x180006cc4  test    rax, rax
0x180006cc7  jz      short loc_180006CDB
0x180006cc9  xor     r9d, r9d
0x180006ccc  xor     r8d, r8d
0x180006ccf  mov     edx, 0FEh
0x180006cd4  xor     ecx, ecx
0x180006cd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006cdb  mov     rcx, [rsp+0A8h+var_48]
0x180006ce0  xor     rcx, rsp; StackCookie
0x180006ce3  call    __security_check_cookie
0x180006ce8  add     rsp, 78h
0x180006cec  pop     r15
0x180006cee  pop     r14
0x180006cf0  pop     rdi
0x180006cf1  pop     rsi
0x180006cf2  pop     rbp
0x180006cf3  pop     rbx
0x180006cf4  retn
```
