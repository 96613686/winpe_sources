# wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)

- ea: `0x180008420`
- end: `0x1800085d7`
- name: `?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z`
- size: `439`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180002b50`
- `0x180002c90`
- `0x180007dcc`

## callees

- `0x180001e40`
- `0x180008420`
- `0x18000c214`
- `0x18001b010`

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
0x180008420  push    rbx
0x180008422  push    rbp
0x180008423  push    rsi
0x180008424  push    rdi
0x180008425  push    r14
0x180008427  push    r15
0x180008429  sub     rsp, 78h
0x18000842d  mov     rax, cs:__security_cookie
0x180008434  xor     rax, rsp
0x180008437  mov     [rsp+0A8h+var_48], rax
0x18000843c  mov     rsi, rcx
0x18000843f  mov     rbx, [rcx+20h]
0x180008443  mov     rdi, [rcx+28h]
0x180008447  mov     rax, rdi
0x18000844a  sub     rax, rbx
0x18000844d  cmp     rax, 10h
0x180008451  jb      loc_1800085BD
0x180008457  mov     ebp, 1
0x18000845c  lea     r14d, [rbp+1]
0x180008460  mov     r15d, 1FFh
0x180008466  cmp     rbx, rdi
0x180008469  jz      loc_18000858A
0x18000846f  mov     r8, [rbx+8]
0x180008473  mov     r10d, [rbx]
0x180008476  prefetchw byte ptr [r8]
0x18000847a  mov     eax, [r8]
0x18000847d  mov     ecx, eax
0x18000847f  and     ecx, 0FFC0401Eh
0x180008485  lock cmpxchg [r8], ecx
0x18000848a  jnz     short loc_18000847D
0x18000848c  mov     ecx, eax
0x18000848e  mov     r9d, eax
0x180008491  shr     r9d, 1
0x180008494  and     r9d, 0Fh
0x180008498  jz      short loc_1800084B7
0x18000849a  prefetchw byte ptr [r8+4]
0x18000849f  mov     eax, [r8+4]
0x1800084a3  mov     edx, eax
0x1800084a5  or      edx, r9d
0x1800084a8  lock cmpxchg [r8+4], edx
0x1800084ae  jnz     short loc_1800084A3
0x1800084b0  not     eax
0x1800084b2  and     eax, r9d
0x1800084b5  jmp     short loc_1800084BA
0x1800084b7  mov     eax, r9d
0x1800084ba  test    bpl, al
0x1800084bd  jz      short loc_1800084D3
0x1800084bf  mov     [rsp+0A8h+var_78], r10d
0x1800084c4  mov     [rsp+0A8h+var_74], 10002h
0x1800084cc  lea     rdx, [rsp+0A8h+var_70]
0x1800084d1  jmp     short loc_1800084D8
0x1800084d3  lea     rdx, [rsp+0A8h+var_78]
0x1800084d8  test    r14b, al
0x1800084db  jz      short loc_1800084EB
0x1800084dd  mov     [rdx], r10d
0x1800084e0  mov     dword ptr [rdx+4], 10006h
0x1800084e7  add     rdx, 8
0x1800084eb  test    al, 4
0x1800084ed  jz      short loc_1800084FD
0x1800084ef  mov     [rdx], r10d
0x1800084f2  mov     dword ptr [rdx+4], 10003h
0x1800084f9  add     rdx, 8
0x1800084fd  cmp     eax, 8
0x180008500  jb      short loc_180008510
0x180008502  mov     [rdx], r10d
0x180008505  mov     dword ptr [rdx+4], 10007h
0x18000850c  add     rdx, 8
0x180008510  mov     r8d, ecx
0x180008513  shr     r8d, 5
0x180008517  test    r15d, r8d
0x18000851a  jz      short loc_18000853C
0x18000851c  mov     [rdx], r10d
0x18000851f  mov     eax, ecx
0x180008521  shr     eax, 0Eh
0x180008524  and     ax, bp
0x180008527  shl     ax, 2
0x18000852b  mov     [rdx+4], ax
0x18000852f  and     r8w, r15w; unsigned __int64
0x180008533  mov     [rdx+6], r8w
0x180008538  add     rdx, 8
0x18000853c  mov     eax, ecx
0x18000853e  shr     eax, 0Fh
0x180008541  test    al, 7Fh
0x180008543  jz      short loc_180008565
0x180008545  mov     [rdx], r10d
0x180008548  shr     ecx, 16h
0x18000854b  and     cx, bp
0x18000854e  shl     cx, 2
0x180008552  add     cx, bp
0x180008555  mov     [rdx+4], cx
0x180008559  and     ax, 7Fh
0x18000855d  mov     [rdx+6], ax
0x180008561  add     rdx, 8
0x180008565  lea     rax, [rsp+0A8h+var_78]
0x18000856a  sub     rdx, rax
0x18000856d  sar     rdx, 3; struct __WIL_RTL_FEATURE_USAGE_DATA *
0x180008571  test    rdx, rdx
0x180008574  jle     short loc_180008581
0x180008576  lea     rcx, [rsp+0A8h+var_78]; this
0x18000857b  call    ?WilApi_RecordFeatureUsageReports@details@wil@@YAXPEAU__WIL_RTL_FEATURE_USAGE_DATA@@_K@Z; wil::details::WilApi_RecordFeatureUsageReports(__WIL_RTL_FEATURE_USAGE_DATA *,unsigned __int64)
0x180008580  nop
0x180008581  add     rbx, 10h
0x180008585  jmp     loc_180008466
0x18000858a  mov     rax, [rsi+20h]
0x18000858e  mov     [rsi+28h], rax
0x180008592  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x180008599  test    rax, rax
0x18000859c  jnz     short loc_1800085AA
0x18000859e  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x1800085a5  test    rax, rax
0x1800085a8  jz      short loc_1800085BD
0x1800085aa  xor     r9d, r9d
0x1800085ad  xor     r8d, r8d
0x1800085b0  mov     edx, 0FEh
0x1800085b5  xor     ecx, ecx
0x1800085b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800085bc  nop
0x1800085bd  mov     rcx, [rsp+0A8h+var_48]
0x1800085c2  xor     rcx, rsp; StackCookie
0x1800085c5  call    __security_check_cookie
0x1800085ca  add     rsp, 78h
0x1800085ce  pop     r15
0x1800085d0  pop     r14
0x1800085d2  pop     rdi
0x1800085d3  pop     rsi
0x1800085d4  pop     rbp
0x1800085d5  pop     rbx
0x1800085d6  retn
```
