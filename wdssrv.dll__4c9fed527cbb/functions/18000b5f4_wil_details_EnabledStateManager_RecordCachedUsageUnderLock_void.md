# wil::details::EnabledStateManager::RecordCachedUsageUnderLock(void)

- ea: `0x18000b5f4`
- end: `0x18000b7c0`
- name: `?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXXZ`
- size: `460`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x1800063c0`
- `0x180006500`
- `0x18000724c`
- `0x18001c600`

## callees

- `0x18000b5f4`
- `0x18000e6c8`
- `0x18001c150`
- `0x18001d010`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::details::EnabledStateManager *this)
{
  int *v1; // rsi
  int *v3; // rbx
  __int64 v4; // r9
  int v5; // r10d
  unsigned __int32 v6; // edx
  unsigned int v7; // ecx
  char *v8; // r8
  signed __int64 v9; // r8
  void (__fastcall *v10)(_QWORD, __int64, _QWORD, _QWORD); // rax
  _DWORD v11[2]; // [rsp+30h] [rbp-58h] BYREF
  char v12; // [rsp+38h] [rbp-50h] BYREF

  v1 = (int *)*((_QWORD *)this + 7);
  v3 = (int *)*((_QWORD *)this + 6);
  if ( (unsigned __int64)((char *)v1 - (char *)v3) >= 0x10 )
  {
    while ( v3 != v1 )
    {
      v4 = *((_QWORD *)v3 + 1);
      v5 = *v3;
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
        v8 = &v12;
        v11[1] = 65538;
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
        *((_WORD *)v8 + 3) = (v6 >> 5) & 0x1FF;
        *((_WORD *)v8 + 2) = 4 * ((v6 >> 14) & 1);
        v8 += 8;
      }
      if ( ((v6 >> 15) & 0x7F) != 0 )
      {
        *(_DWORD *)v8 = v5;
        *((_WORD *)v8 + 3) = (v6 >> 15) & 0x7F;
        *((_WORD *)v8 + 2) = 4 * ((v6 >> 22) & 1) + 1;
        v8 += 8;
      }
      v9 = (v8 - (char *)v11) >> 3;
      if ( v9 > 0 )
        wil::details::WilApi_RecordFeatureUsageReports(
          (wil::details *)v11,
          (struct __WIL_RTL_FEATURE_USAGE_DATA *)v9,
          v9);
      v3 += 4;
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
0x18000b5f4  mov     [rsp+arg_8], rbx
0x18000b5f9  mov     [rsp+arg_10], rbp
0x18000b5fe  mov     [rsp+arg_18], rsi
0x18000b603  push    rdi
0x18000b604  push    r14
0x18000b606  push    r15
0x18000b608  sub     rsp, 70h
0x18000b60c  mov     rax, cs:__security_cookie
0x18000b613  xor     rax, rsp
0x18000b616  mov     [rsp+88h+var_28], rax
0x18000b61b  mov     rsi, [rcx+38h]
0x18000b61f  mov     rdi, rcx
0x18000b622  mov     rbx, [rcx+30h]
0x18000b626  mov     rax, rsi
0x18000b629  sub     rax, rbx
0x18000b62c  cmp     rax, 10h
0x18000b630  jb      loc_18000B798
0x18000b636  mov     ebp, 1
0x18000b63b  mov     r15d, 1FFh
0x18000b641  lea     r14d, [rbp+1]
0x18000b645  cmp     rbx, rsi
0x18000b648  jz      loc_18000B766
0x18000b64e  mov     r9, [rbx+8]
0x18000b652  mov     r10d, [rbx]
0x18000b655  prefetchw byte ptr [r9]
0x18000b659  mov     eax, [r9]
0x18000b65c  mov     ecx, eax
0x18000b65e  and     ecx, 0FFC0401Eh
0x18000b664  lock cmpxchg [r9], ecx
0x18000b669  jnz     short loc_18000B65C
0x18000b66b  mov     ecx, eax
0x18000b66d  mov     edx, eax
0x18000b66f  shr     ecx, 1
0x18000b671  and     ecx, 0Fh
0x18000b674  jz      short loc_18000B691
0x18000b676  prefetchw byte ptr [r9+4]
0x18000b67b  mov     eax, [r9+4]
0x18000b67f  mov     r8d, eax
0x18000b682  or      r8d, ecx
0x18000b685  lock cmpxchg [r9+4], r8d
0x18000b68b  jnz     short loc_18000B67F
0x18000b68d  not     eax
0x18000b68f  and     ecx, eax
0x18000b691  lea     r8, [rsp+88h+var_58]
0x18000b696  test    bpl, cl
0x18000b699  jz      short loc_18000B6AD
0x18000b69b  mov     [rsp+88h+var_58], r10d
0x18000b6a0  lea     r8, [rsp+88h+var_50]
0x18000b6a5  mov     [rsp+88h+var_54], 10002h
0x18000b6ad  test    r14b, cl
0x18000b6b0  jz      short loc_18000B6C1
0x18000b6b2  mov     [r8], r10d
0x18000b6b5  mov     dword ptr [r8+4], 10006h
0x18000b6bd  add     r8, 8
0x18000b6c1  test    cl, 4
0x18000b6c4  jz      short loc_18000B6D5
0x18000b6c6  mov     [r8], r10d
0x18000b6c9  mov     dword ptr [r8+4], 10003h
0x18000b6d1  add     r8, 8
0x18000b6d5  cmp     ecx, 8
0x18000b6d8  jb      short loc_18000B6E9
0x18000b6da  mov     [r8], r10d
0x18000b6dd  mov     dword ptr [r8+4], 10007h
0x18000b6e5  add     r8, 8
0x18000b6e9  mov     ecx, edx
0x18000b6eb  shr     ecx, 5
0x18000b6ee  test    r15d, ecx
0x18000b6f1  jz      short loc_18000B714
0x18000b6f3  and     cx, r15w
0x18000b6f7  mov     [r8], r10d
0x18000b6fa  mov     eax, edx
0x18000b6fc  mov     [r8+6], cx
0x18000b701  shr     eax, 0Eh
0x18000b704  and     ax, bp
0x18000b707  shl     ax, 2
0x18000b70b  mov     [r8+4], ax
0x18000b710  add     r8, 8
0x18000b714  mov     eax, edx
0x18000b716  shr     eax, 0Fh
0x18000b719  test    al, 7Fh
0x18000b71b  jz      short loc_18000B73F
0x18000b71d  shr     edx, 16h
0x18000b720  and     ax, 7Fh
0x18000b724  and     dx, bp
0x18000b727  mov     [r8], r10d
0x18000b72a  shl     dx, 2
0x18000b72e  add     dx, bp
0x18000b731  mov     [r8+6], ax
0x18000b736  mov     [r8+4], dx
0x18000b73b  add     r8, 8
0x18000b73f  lea     rax, [rsp+88h+var_58]
0x18000b744  sub     r8, rax
0x18000b747  sar     r8, 3; unsigned __int64
0x18000b74b  test    r8, r8
0x18000b74e  jle     short loc_18000B75D
0x18000b750  mov     rdx, r8; struct __WIL_RTL_FEATURE_USAGE_DATA *
0x18000b753  lea     rcx, [rsp+88h+var_58]; this
0x18000b758  call    ?WilApi_RecordFeatureUsageReports@details@wil@@YAXPEAU__WIL_RTL_FEATURE_USAGE_DATA@@_K@Z; wil::details::WilApi_RecordFeatureUsageReports(__WIL_RTL_FEATURE_USAGE_DATA *,unsigned __int64)
0x18000b75d  add     rbx, 10h
0x18000b761  jmp     loc_18000B645
0x18000b766  mov     rax, [rdi+30h]
0x18000b76a  mov     [rdi+38h], rax
0x18000b76e  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x18000b775  test    rax, rax
0x18000b778  jnz     short loc_18000B786
0x18000b77a  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x18000b781  test    rax, rax
0x18000b784  jz      short loc_18000B798
0x18000b786  xor     r9d, r9d
0x18000b789  xor     r8d, r8d
0x18000b78c  mov     edx, 0FEh
0x18000b791  xor     ecx, ecx
0x18000b793  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b798  mov     rcx, [rsp+88h+var_28]
0x18000b79d  xor     rcx, rsp; StackCookie
0x18000b7a0  call    __security_check_cookie
0x18000b7a5  lea     r11, [rsp+88h+var_18]
0x18000b7aa  mov     rbx, [r11+28h]
0x18000b7ae  mov     rbp, [r11+30h]
0x18000b7b2  mov     rsi, [r11+38h]
0x18000b7b6  mov     rsp, r11
0x18000b7b9  pop     r15
0x18000b7bb  pop     r14
0x18000b7bd  pop     rdi
0x18000b7be  retn
```
