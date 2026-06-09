# WapHttp3HandleTtlExpiry

- ea: `0x18007d048`
- end: `0x18007d313`
- name: `WapHttp3HandleTtlExpiry`
- size: `715`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x18007d31c`

## callees

- `0x1800052bc`
- `0x180014f04`
- `0x18002e1a4`
- `0x180051648`
- `0x18005176c`
- `0x1800722f0`
- `0x18007bbf4`
- `0x18007d048`
- `0x180092564`
- `0x180097810`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007d175`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007d175`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007d108`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007d2e0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007d108`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007d2e0`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18007d2d1`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18007d2d1`

## pseudocode

```c
void __fastcall WapHttp3HandleTtlExpiry(__int64 a1)
{
  bool v1; // zf
  _QWORD *v3; // r15
  int v4; // r8d
  __int64 v5; // rdx
  __int64 v6; // [rsp+70h] [rbp-28h] BYREF
  char v7; // [rsp+78h] [rbp-20h] BYREF

  v1 = *(_QWORD *)(a1 + 256) == 0;
  v6 = 0;
  v3 = (_QWORD *)(a1 + 456);
  v7 = 0;
  WaInitializeDnsQuery(
    a1 + 456,
    *(_QWORD *)(a1 + 416),
    *(_QWORD *)(a1 + 440),
    *(_QWORD *)(a1 + 448),
    *(_DWORD *)(a1 + 316),
    *(_QWORD *)(a1 + 8),
    *(_DWORD *)(a1 + 320),
    *(_DWORD *)(a1 + 324),
    !v1,
    *(_BYTE *)(a1 + 200),
    *(_BYTE *)(a1 + 201),
    (__int64)wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,unsigned int)>::destroy,
    a1);
  *(_BYTE *)(a1 + 314) = 1;
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 24));
  LOBYTE(v4) = 1;
  if ( (unsigned int)WaStartDnsQuery((_DWORD)v3, 0, v4, (unsigned int)&v7, (__int64)&v6) )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 24));
    if ( (xmmword_1800AD720 & 8) != 0 )
      WPP_SF_q(1027, 239, WPP_305d602a2c4b3ed688f990a0fb56ab50_Traceguids, a1);
    WaDereferenceDnsCache(*v3);
    v1 = *(_DWORD *)(a1 + 64) == 4;
    *(_BYTE *)(a1 + 314) = 0;
    if ( !v1 )
    {
      if ( (xmmword_1800AD720 & 8) == 0 )
      {
LABEL_19:
        LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 24));
        return;
      }
      v5 = 240;
LABEL_10:
      WPP_SF_(1027, v5, WPP_305d602a2c4b3ed688f990a0fb56ab50_Traceguids);
      goto LABEL_19;
    }
    if ( !*(_BYTE *)(a1 + 315) )
    {
      if ( (unsigned int)WaTpInitializeWorkItem((char *)(a1 + 352), (__int64)WapHttp3TtlExpiryCallback, a1, 1) )
      {
        if ( (xmmword_1800AD720 & 8) == 0 )
          goto LABEL_19;
        v5 = 241;
        goto LABEL_10;
      }
      *(_BYTE *)(a1 + 315) = 1;
    }
    WaInitializeDnsQuery(
      (_DWORD)v3,
      *(_QWORD *)(a1 + 416),
      *(_QWORD *)(a1 + 440),
      *(_QWORD *)(a1 + 448),
      *(_DWORD *)(a1 + 316),
      *(_QWORD *)(a1 + 8),
      *(_DWORD *)(a1 + 320),
      *(_DWORD *)(a1 + 324),
      *(_QWORD *)(a1 + 256) != 0,
      *(_BYTE *)(a1 + 200),
      *(_BYTE *)(a1 + 201),
      (__int64)WapHttp3TtlExpiryQueryCompletionRoutine,
      a1);
    *(_BYTE *)(a1 + 314) = 1;
    if ( (xmmword_1800AD720 & 8) != 0 )
      WPP_SF_q(1027, 242, WPP_305d602a2c4b3ed688f990a0fb56ab50_Traceguids, a1);
    _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(a1 + 8) + 4LL));
    SubmitThreadpoolWork(*(PTP_WORK *)(a1 + 360));
    goto LABEL_19;
  }
  if ( (xmmword_1800AD720 & 8) != 0 )
    WPP_SF_q(1027, 238, WPP_305d602a2c4b3ed688f990a0fb56ab50_Traceguids, a1);
  WapHttp3CompleteBackgroundResolution(a1, v6);
  WaDereferenceDnsQueryResult(v6);
}

```

## disassembly

```asm
0x18007d048  mov     r11, rsp
0x18007d04b  mov     [r11+10h], rbx
0x18007d04f  mov     [r11+18h], r14
0x18007d053  push    r15
0x18007d055  sub     rsp, 90h
0x18007d05c  mov     rax, cs:__security_cookie
0x18007d063  xor     rax, rsp
0x18007d066  mov     [rsp+98h+var_18], rax
0x18007d06e  cmp     qword ptr [rcx+100h], 0
0x18007d076  lea     rax, ?destroy@?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@UEAAXXZ; wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::destroy(void)
0x18007d07d  mov     rbx, rcx
0x18007d080  mov     qword ptr [r11-28h], 0
0x18007d088  mov     [r11-38h], rbx
0x18007d08c  lea     r15, [rcx+1C8h]
0x18007d093  mov     [r11-40h], rax
0x18007d097  setnz   cl
0x18007d09a  mov     [rsp+98h+var_20], 0
0x18007d09f  mov     al, [rbx+0C9h]
0x18007d0a5  mov     r9, [rbx+1C0h]
0x18007d0ac  mov     r8, [rbx+1B8h]
0x18007d0b3  mov     rdx, [rbx+1A0h]
0x18007d0ba  mov     [rsp+98h+var_48], al
0x18007d0be  mov     al, [rbx+0C8h]
0x18007d0c4  mov     [rsp+98h+var_50], al
0x18007d0c8  mov     eax, [rbx+144h]
0x18007d0ce  mov     [rsp+98h+var_58], cl
0x18007d0d2  mov     rcx, r15
0x18007d0d5  mov     [rsp+98h+var_60], eax
0x18007d0d9  mov     eax, [rbx+140h]
0x18007d0df  mov     [rsp+98h+var_68], eax
0x18007d0e3  mov     rax, [rbx+8]
0x18007d0e7  mov     [r11-70h], rax
0x18007d0eb  mov     eax, [rbx+13Ch]
0x18007d0f1  mov     dword ptr [rsp+98h+var_78], eax
0x18007d0f5  call    WaInitializeDnsQuery
0x18007d0fa  lea     r14, [rbx+18h]
0x18007d0fe  mov     byte ptr [rbx+13Ah], 1
0x18007d105  mov     rcx, r14; lpCriticalSection
0x18007d108  call    cs:__imp_LeaveCriticalSection
0x18007d10f  nop     dword ptr [rax+rax+00h]
0x18007d114  lea     rax, [rsp+98h+var_28]
0x18007d119  mov     r8b, 1
0x18007d11c  lea     r9, [rsp+98h+var_20]
0x18007d121  mov     [rsp+98h+var_78], rax
0x18007d126  xor     edx, edx
0x18007d128  mov     rcx, r15
0x18007d12b  call    WaStartDnsQuery
0x18007d130  test    eax, eax
0x18007d132  jnz     short loc_18007D172
0x18007d134  test    byte ptr cs:xmmword_1800AD720, 8
0x18007d13b  jz      short loc_18007D156
0x18007d13d  mov     edx, 0EEh
0x18007d142  lea     r8, WPP_305d602a2c4b3ed688f990a0fb56ab50_Traceguids
0x18007d149  mov     ecx, 403h
0x18007d14e  mov     r9, rbx
0x18007d151  call    WPP_SF_q
0x18007d156  mov     rdx, [rsp+98h+var_28]
0x18007d15b  mov     rcx, rbx
0x18007d15e  call    WapHttp3CompleteBackgroundResolution
0x18007d163  mov     rcx, [rsp+98h+var_28]
0x18007d168  call    WaDereferenceDnsQueryResult
0x18007d16d  jmp     loc_18007D2EC
0x18007d172  mov     rcx, r14; lpCriticalSection
0x18007d175  call    cs:__imp_EnterCriticalSection
0x18007d17c  nop     dword ptr [rax+rax+00h]
0x18007d181  test    byte ptr cs:xmmword_1800AD720, 8
0x18007d188  jz      short loc_18007D1A3
0x18007d18a  mov     edx, 0EFh
0x18007d18f  lea     r8, WPP_305d602a2c4b3ed688f990a0fb56ab50_Traceguids
0x18007d196  mov     ecx, 403h
0x18007d19b  mov     r9, rbx
0x18007d19e  call    WPP_SF_q
0x18007d1a3  mov     rcx, [r15]
0x18007d1a6  call    WaDereferenceDnsCache
0x18007d1ab  cmp     dword ptr [rbx+40h], 4
0x18007d1af  mov     byte ptr [rbx+13Ah], 0
0x18007d1b6  jz      short loc_18007D1E0
0x18007d1b8  test    byte ptr cs:xmmword_1800AD720, 8
0x18007d1bf  jz      loc_18007D2DD
0x18007d1c5  mov     edx, 0F0h
0x18007d1ca  mov     ecx, 403h
0x18007d1cf  lea     r8, WPP_305d602a2c4b3ed688f990a0fb56ab50_Traceguids
0x18007d1d6  call    WPP_SF_
0x18007d1db  jmp     loc_18007D2DD
0x18007d1e0  cmp     byte ptr [rbx+13Bh], 0
0x18007d1e7  jnz     short loc_18007D221
0x18007d1e9  lea     rcx, [rbx+160h]; pv
0x18007d1f0  mov     r9b, 1
0x18007d1f3  mov     r8, rbx
0x18007d1f6  lea     rdx, WapHttp3TtlExpiryCallback
0x18007d1fd  call    WaTpInitializeWorkItem
0x18007d202  test    eax, eax
0x18007d204  jz      short loc_18007D21A
0x18007d206  test    byte ptr cs:xmmword_1800AD720, 8
0x18007d20d  jz      loc_18007D2DD
0x18007d213  mov     edx, 0F1h
0x18007d218  jmp     short loc_18007D1CA
0x18007d21a  mov     byte ptr [rbx+13Bh], 1
0x18007d221  cmp     qword ptr [rbx+100h], 0
0x18007d229  lea     rax, WapHttp3TtlExpiryQueryCompletionRoutine
0x18007d230  mov     r9, [rbx+1C0h]
0x18007d237  mov     rcx, r15
0x18007d23a  mov     r8, [rbx+1B8h]
0x18007d241  setnz   dl
0x18007d244  mov     [rsp+98h+var_38], rbx
0x18007d249  mov     [rsp+98h+var_40], rax
0x18007d24e  mov     al, [rbx+0C9h]
0x18007d254  mov     [rsp+98h+var_48], al
0x18007d258  mov     al, [rbx+0C8h]
0x18007d25e  mov     [rsp+98h+var_50], al
0x18007d262  mov     eax, [rbx+144h]
0x18007d268  mov     [rsp+98h+var_58], dl
0x18007d26c  mov     rdx, [rbx+1A0h]
0x18007d273  mov     [rsp+98h+var_60], eax
0x18007d277  mov     eax, [rbx+140h]
0x18007d27d  mov     [rsp+98h+var_68], eax
0x18007d281  mov     rax, [rbx+8]
0x18007d285  mov     [rsp+98h+var_70], rax
0x18007d28a  mov     eax, [rbx+13Ch]
0x18007d290  mov     dword ptr [rsp+98h+var_78], eax
0x18007d294  call    WaInitializeDnsQuery
0x18007d299  mov     byte ptr [rbx+13Ah], 1
0x18007d2a0  test    byte ptr cs:xmmword_1800AD720, 8
0x18007d2a7  jz      short loc_18007D2C2
0x18007d2a9  mov     edx, 0F2h
0x18007d2ae  lea     r8, WPP_305d602a2c4b3ed688f990a0fb56ab50_Traceguids
0x18007d2b5  mov     ecx, 403h
0x18007d2ba  mov     r9, rbx
0x18007d2bd  call    WPP_SF_q
0x18007d2c2  mov     rax, [rbx+8]
0x18007d2c6  lock inc dword ptr [rax+4]
0x18007d2ca  mov     rcx, [rbx+168h]; pwk
0x18007d2d1  call    cs:__imp_SubmitThreadpoolWork
0x18007d2d8  nop     dword ptr [rax+rax+00h]
0x18007d2dd  mov     rcx, r14; lpCriticalSection
0x18007d2e0  call    cs:__imp_LeaveCriticalSection
0x18007d2e7  nop     dword ptr [rax+rax+00h]
0x18007d2ec  mov     rcx, [rsp+98h+var_18]
0x18007d2f4  xor     rcx, rsp; StackCookie
0x18007d2f7  call    __security_check_cookie
0x18007d2fc  lea     r11, [rsp+98h+var_8]
0x18007d304  mov     rbx, [r11+18h]
0x18007d308  mov     r14, [r11+20h]
0x18007d30c  mov     rsp, r11
0x18007d30f  pop     r15
0x18007d311  retn
```
