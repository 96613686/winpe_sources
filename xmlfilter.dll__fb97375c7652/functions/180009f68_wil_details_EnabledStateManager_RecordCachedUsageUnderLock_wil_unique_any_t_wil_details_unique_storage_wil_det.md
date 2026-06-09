# wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)

- ea: `0x180009f68`
- end: `0x18000a11f`
- name: `?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z`
- size: `439`
- prototype: `__int64 (__fastcall *__fastcall(__int64))(_QWORD, __int64, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180002cc0`
- `0x180002e80`
- `0x180009914`

## callees

- `0x1800020e0`
- `0x180009f68`
- `0x18000cf64`
- `0x180017010`

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
0x180009f68  push    rbx
0x180009f6a  push    rbp
0x180009f6b  push    rsi
0x180009f6c  push    rdi
0x180009f6d  push    r14
0x180009f6f  push    r15
0x180009f71  sub     rsp, 78h
0x180009f75  mov     rax, cs:__security_cookie
0x180009f7c  xor     rax, rsp
0x180009f7f  mov     [rsp+0A8h+var_48], rax
0x180009f84  mov     rsi, rcx
0x180009f87  mov     rbx, [rcx+20h]
0x180009f8b  mov     rdi, [rcx+28h]
0x180009f8f  mov     rax, rdi
0x180009f92  sub     rax, rbx
0x180009f95  cmp     rax, 10h
0x180009f99  jb      loc_18000A105
0x180009f9f  mov     ebp, 1
0x180009fa4  lea     r14d, [rbp+1]
0x180009fa8  mov     r15d, 1FFh
0x180009fae  cmp     rbx, rdi
0x180009fb1  jz      loc_18000A0D2
0x180009fb7  mov     r8, [rbx+8]
0x180009fbb  mov     r10d, [rbx]
0x180009fbe  prefetchw byte ptr [r8]
0x180009fc2  mov     eax, [r8]
0x180009fc5  mov     ecx, eax
0x180009fc7  and     ecx, 0FFC0401Eh
0x180009fcd  lock cmpxchg [r8], ecx
0x180009fd2  jnz     short loc_180009FC5
0x180009fd4  mov     ecx, eax
0x180009fd6  mov     r9d, eax
0x180009fd9  shr     r9d, 1
0x180009fdc  and     r9d, 0Fh
0x180009fe0  jz      short loc_180009FFF
0x180009fe2  prefetchw byte ptr [r8+4]
0x180009fe7  mov     eax, [r8+4]
0x180009feb  mov     edx, eax
0x180009fed  or      edx, r9d
0x180009ff0  lock cmpxchg [r8+4], edx
0x180009ff6  jnz     short loc_180009FEB
0x180009ff8  not     eax
0x180009ffa  and     eax, r9d
0x180009ffd  jmp     short loc_18000A002
0x180009fff  mov     eax, r9d
0x18000a002  test    bpl, al
0x18000a005  jz      short loc_18000A01B
0x18000a007  mov     [rsp+0A8h+var_78], r10d
0x18000a00c  mov     [rsp+0A8h+var_74], 10002h
0x18000a014  lea     rdx, [rsp+0A8h+var_70]
0x18000a019  jmp     short loc_18000A020
0x18000a01b  lea     rdx, [rsp+0A8h+var_78]
0x18000a020  test    r14b, al
0x18000a023  jz      short loc_18000A033
0x18000a025  mov     [rdx], r10d
0x18000a028  mov     dword ptr [rdx+4], 10006h
0x18000a02f  add     rdx, 8
0x18000a033  test    al, 4
0x18000a035  jz      short loc_18000A045
0x18000a037  mov     [rdx], r10d
0x18000a03a  mov     dword ptr [rdx+4], 10003h
0x18000a041  add     rdx, 8
0x18000a045  cmp     eax, 8
0x18000a048  jb      short loc_18000A058
0x18000a04a  mov     [rdx], r10d
0x18000a04d  mov     dword ptr [rdx+4], 10007h
0x18000a054  add     rdx, 8
0x18000a058  mov     r8d, ecx
0x18000a05b  shr     r8d, 5
0x18000a05f  test    r15d, r8d
0x18000a062  jz      short loc_18000A084
0x18000a064  mov     [rdx], r10d
0x18000a067  mov     eax, ecx
0x18000a069  shr     eax, 0Eh
0x18000a06c  and     ax, bp
0x18000a06f  shl     ax, 2
0x18000a073  mov     [rdx+4], ax
0x18000a077  and     r8w, r15w; unsigned __int64
0x18000a07b  mov     [rdx+6], r8w
0x18000a080  add     rdx, 8
0x18000a084  mov     eax, ecx
0x18000a086  shr     eax, 0Fh
0x18000a089  test    al, 7Fh
0x18000a08b  jz      short loc_18000A0AD
0x18000a08d  mov     [rdx], r10d
0x18000a090  shr     ecx, 16h
0x18000a093  and     cx, bp
0x18000a096  shl     cx, 2
0x18000a09a  add     cx, bp
0x18000a09d  mov     [rdx+4], cx
0x18000a0a1  and     ax, 7Fh
0x18000a0a5  mov     [rdx+6], ax
0x18000a0a9  add     rdx, 8
0x18000a0ad  lea     rax, [rsp+0A8h+var_78]
0x18000a0b2  sub     rdx, rax
0x18000a0b5  sar     rdx, 3; struct __WIL_RTL_FEATURE_USAGE_DATA *
0x18000a0b9  test    rdx, rdx
0x18000a0bc  jle     short loc_18000A0C9
0x18000a0be  lea     rcx, [rsp+0A8h+var_78]; this
0x18000a0c3  call    ?WilApi_RecordFeatureUsageReports@details@wil@@YAXPEAU__WIL_RTL_FEATURE_USAGE_DATA@@_K@Z; wil::details::WilApi_RecordFeatureUsageReports(__WIL_RTL_FEATURE_USAGE_DATA *,unsigned __int64)
0x18000a0c8  nop
0x18000a0c9  add     rbx, 10h
0x18000a0cd  jmp     loc_180009FAE
0x18000a0d2  mov     rax, [rsi+20h]
0x18000a0d6  mov     [rsi+28h], rax
0x18000a0da  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x18000a0e1  test    rax, rax
0x18000a0e4  jnz     short loc_18000A0F2
0x18000a0e6  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x18000a0ed  test    rax, rax
0x18000a0f0  jz      short loc_18000A105
0x18000a0f2  xor     r9d, r9d
0x18000a0f5  xor     r8d, r8d
0x18000a0f8  mov     edx, 0FEh
0x18000a0fd  xor     ecx, ecx
0x18000a0ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a104  nop
0x18000a105  mov     rcx, [rsp+0A8h+var_48]
0x18000a10a  xor     rcx, rsp; StackCookie
0x18000a10d  call    __security_check_cookie
0x18000a112  add     rsp, 78h
0x18000a116  pop     r15
0x18000a118  pop     r14
0x18000a11a  pop     rdi
0x18000a11b  pop     rsi
0x18000a11c  pop     rbp
0x18000a11d  pop     rbx
0x18000a11e  retn
```
