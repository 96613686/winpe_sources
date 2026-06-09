# wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)

- ea: `0x140009390`
- end: `0x140009545`
- name: `?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z`
- size: `437`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140004970`
- `0x140004ab0`
- `0x140008b44`

## callees

- `0x140009390`
- `0x14000bf94`
- `0x140014910`
- `0x140015010`

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
0x140009390  push    rbx
0x140009392  push    rbp
0x140009393  push    rsi
0x140009394  push    rdi
0x140009395  push    r14
0x140009397  push    r15
0x140009399  sub     rsp, 78h
0x14000939d  mov     rax, cs:__security_cookie
0x1400093a4  xor     rax, rsp
0x1400093a7  mov     [rsp+0A8h+var_48], rax
0x1400093ac  mov     rdi, [rcx+28h]
0x1400093b0  mov     rsi, rcx
0x1400093b3  mov     rbx, [rcx+20h]
0x1400093b7  mov     rax, rdi
0x1400093ba  sub     rax, rbx
0x1400093bd  cmp     rax, 10h
0x1400093c1  jb      loc_14000952B
0x1400093c7  mov     ebp, 1
0x1400093cc  mov     r15d, 1FFh
0x1400093d2  lea     r14d, [rbp+1]
0x1400093d6  cmp     rbx, rdi
0x1400093d9  jz      loc_1400094F9
0x1400093df  mov     r8, [rbx+8]
0x1400093e3  mov     r10d, [rbx]
0x1400093e6  prefetchw byte ptr [r8]
0x1400093ea  mov     eax, [r8]
0x1400093ed  mov     ecx, eax
0x1400093ef  and     ecx, 0FFC0401Eh
0x1400093f5  lock cmpxchg [r8], ecx
0x1400093fa  jnz     short loc_1400093ED
0x1400093fc  mov     r9d, eax
0x1400093ff  mov     ecx, eax
0x140009401  shr     r9d, 1
0x140009404  and     r9d, 0Fh
0x140009408  jz      short loc_140009427
0x14000940a  prefetchw byte ptr [r8+4]
0x14000940f  mov     eax, [r8+4]
0x140009413  mov     edx, eax
0x140009415  or      edx, r9d
0x140009418  lock cmpxchg [r8+4], edx
0x14000941e  jnz     short loc_140009413
0x140009420  not     eax
0x140009422  and     eax, r9d
0x140009425  jmp     short loc_14000942A
0x140009427  mov     eax, r9d
0x14000942a  test    bpl, al
0x14000942d  jz      short loc_140009443
0x14000942f  mov     [rsp+0A8h+var_78], r10d
0x140009434  lea     rdx, [rsp+0A8h+var_70]
0x140009439  mov     [rsp+0A8h+var_74], 10002h
0x140009441  jmp     short loc_140009448
0x140009443  lea     rdx, [rsp+0A8h+var_78]
0x140009448  test    r14b, al
0x14000944b  jz      short loc_14000945B
0x14000944d  mov     [rdx], r10d
0x140009450  mov     dword ptr [rdx+4], 10006h
0x140009457  add     rdx, 8
0x14000945b  test    al, 4
0x14000945d  jz      short loc_14000946D
0x14000945f  mov     [rdx], r10d
0x140009462  mov     dword ptr [rdx+4], 10003h
0x140009469  add     rdx, 8
0x14000946d  cmp     eax, 8
0x140009470  jb      short loc_140009480
0x140009472  mov     [rdx], r10d
0x140009475  mov     dword ptr [rdx+4], 10007h
0x14000947c  add     rdx, 8
0x140009480  mov     r8d, ecx
0x140009483  shr     r8d, 5
0x140009487  test    r15d, r8d
0x14000948a  jz      short loc_1400094AC
0x14000948c  and     r8w, r15w; unsigned __int64
0x140009490  mov     [rdx], r10d
0x140009493  mov     eax, ecx
0x140009495  mov     [rdx+6], r8w
0x14000949a  shr     eax, 0Eh
0x14000949d  and     ax, bp
0x1400094a0  shl     ax, 2
0x1400094a4  mov     [rdx+4], ax
0x1400094a8  add     rdx, 8
0x1400094ac  mov     eax, ecx
0x1400094ae  shr     eax, 0Fh
0x1400094b1  test    al, 7Fh
0x1400094b3  jz      short loc_1400094D5
0x1400094b5  shr     ecx, 16h
0x1400094b8  and     ax, 7Fh
0x1400094bc  and     cx, bp
0x1400094bf  mov     [rdx], r10d
0x1400094c2  shl     cx, 2
0x1400094c6  add     cx, bp
0x1400094c9  mov     [rdx+6], ax
0x1400094cd  mov     [rdx+4], cx
0x1400094d1  add     rdx, 8
0x1400094d5  lea     rax, [rsp+0A8h+var_78]
0x1400094da  sub     rdx, rax
0x1400094dd  sar     rdx, 3; struct __WIL_RTL_FEATURE_USAGE_DATA *
0x1400094e1  test    rdx, rdx
0x1400094e4  jle     short loc_1400094F0
0x1400094e6  lea     rcx, [rsp+0A8h+var_78]; this
0x1400094eb  call    ?WilApi_RecordFeatureUsageReports@details@wil@@YAXPEAU__WIL_RTL_FEATURE_USAGE_DATA@@_K@Z; wil::details::WilApi_RecordFeatureUsageReports(__WIL_RTL_FEATURE_USAGE_DATA *,unsigned __int64)
0x1400094f0  add     rbx, 10h
0x1400094f4  jmp     loc_1400093D6
0x1400094f9  mov     rax, [rsi+20h]
0x1400094fd  mov     [rsi+28h], rax
0x140009501  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x140009508  test    rax, rax
0x14000950b  jnz     short loc_140009519
0x14000950d  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x140009514  test    rax, rax
0x140009517  jz      short loc_14000952B
0x140009519  xor     r9d, r9d
0x14000951c  xor     r8d, r8d
0x14000951f  mov     edx, 0FEh
0x140009524  xor     ecx, ecx
0x140009526  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000952b  mov     rcx, [rsp+0A8h+var_48]
0x140009530  xor     rcx, rsp; StackCookie
0x140009533  call    __security_check_cookie
0x140009538  add     rsp, 78h
0x14000953c  pop     r15
0x14000953e  pop     r14
0x140009540  pop     rdi
0x140009541  pop     rsi
0x140009542  pop     rbp
0x140009543  pop     rbx
0x140009544  retn
```
