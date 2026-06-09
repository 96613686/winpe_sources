# WapTcpHandleTtlExpiry

- ea: `0x18008e09c`
- end: `0x18008e368`
- name: `WapTcpHandleTtlExpiry`
- size: `716`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x18008e370`

## callees

- `0x1800052bc`
- `0x180014f04`
- `0x18002e1a4`
- `0x180051648`
- `0x18005176c`
- `0x1800722f0`
- `0x18008dc58`
- `0x18008e09c`
- `0x180092564`
- `0x180097810`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18008e1c7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18008e1c7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008e15c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008e335`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008e15c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008e335`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18008e326`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18008e326`

## pseudocode

```c
void __fastcall WapTcpHandleTtlExpiry(__int64 a1)
{
  bool v1; // zf
  _QWORD *v3; // r15
  int v4; // r8d
  __int64 v5; // rdx
  __int64 v6; // [rsp+70h] [rbp-28h] BYREF
  char v7; // [rsp+78h] [rbp-20h] BYREF

  v1 = *(_QWORD *)(a1 + 288) == 0;
  v6 = 0;
  v3 = (_QWORD *)(a1 + 512);
  v7 = 0;
  WaInitializeDnsQuery(
    a1 + 512,
    *(_QWORD *)(a1 + 472),
    *(_QWORD *)(a1 + 496),
    *(_QWORD *)(a1 + 504),
    *(_DWORD *)(a1 + 372),
    *(_QWORD *)(a1 + 8),
    *(_DWORD *)(a1 + 376),
    *(_DWORD *)(a1 + 380),
    !v1,
    *(_BYTE *)(a1 + 236),
    *(_BYTE *)(a1 + 237),
    (__int64)wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,unsigned int)>::destroy,
    a1);
  *(_BYTE *)(a1 + 370) = 1;
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 24));
  LOBYTE(v4) = 1;
  if ( (unsigned int)WaStartDnsQuery((_DWORD)v3, 0, v4, (unsigned int)&v7, (__int64)&v6) )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 24));
    if ( (xmmword_1800AD720 & 8) != 0 )
      WPP_SF_q(1027, 94, WPP_14086b36644f38024399eb8d606249d9_Traceguids, a1);
    WaDereferenceDnsCache(*v3);
    v1 = *(_DWORD *)(a1 + 224) == 4;
    *(_BYTE *)(a1 + 370) = 0;
    if ( !v1 )
    {
      if ( (xmmword_1800AD720 & 8) == 0 )
      {
LABEL_19:
        LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 24));
        return;
      }
      v5 = 95;
LABEL_10:
      WPP_SF_(1027, v5, WPP_14086b36644f38024399eb8d606249d9_Traceguids);
      goto LABEL_19;
    }
    if ( !*(_BYTE *)(a1 + 371) )
    {
      if ( (unsigned int)WaTpInitializeWorkItem((char *)(a1 + 408), (__int64)WapTcpTtlExpiryCallback, a1, 1) )
      {
        if ( (xmmword_1800AD720 & 8) == 0 )
          goto LABEL_19;
        v5 = 96;
        goto LABEL_10;
      }
      *(_BYTE *)(a1 + 371) = 1;
    }
    WaInitializeDnsQuery(
      (_DWORD)v3,
      *(_QWORD *)(a1 + 472),
      *(_QWORD *)(a1 + 496),
      *(_QWORD *)(a1 + 504),
      *(_DWORD *)(a1 + 372),
      *(_QWORD *)(a1 + 8),
      *(_DWORD *)(a1 + 376),
      *(_DWORD *)(a1 + 380),
      *(_QWORD *)(a1 + 288) != 0,
      *(_BYTE *)(a1 + 236),
      *(_BYTE *)(a1 + 237),
      (__int64)WapTcpTtlExpiryQueryCompletionRoutine,
      a1);
    *(_BYTE *)(a1 + 370) = 1;
    if ( (xmmword_1800AD720 & 8) != 0 )
      WPP_SF_q(1027, 97, WPP_14086b36644f38024399eb8d606249d9_Traceguids, a1);
    _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(a1 + 8) + 4LL));
    SubmitThreadpoolWork(*(PTP_WORK *)(a1 + 416));
    goto LABEL_19;
  }
  if ( (xmmword_1800AD720 & 8) != 0 )
    WPP_SF_q(1027, 93, WPP_14086b36644f38024399eb8d606249d9_Traceguids, a1);
  WapTcpCompleteBackgroundResolution(a1, v6);
  WaDereferenceDnsQueryResult(v6);
}

```

## disassembly

```asm
0x18008e09c  mov     r11, rsp
0x18008e09f  mov     [r11+10h], rbx
0x18008e0a3  mov     [r11+18h], r14
0x18008e0a7  push    r15
0x18008e0a9  sub     rsp, 90h
0x18008e0b0  mov     rax, cs:__security_cookie
0x18008e0b7  xor     rax, rsp
0x18008e0ba  mov     [rsp+98h+var_18], rax
0x18008e0c2  cmp     qword ptr [rcx+120h], 0
0x18008e0ca  lea     rax, ?destroy@?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@UEAAXXZ; wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::destroy(void)
0x18008e0d1  mov     rbx, rcx
0x18008e0d4  mov     qword ptr [r11-28h], 0
0x18008e0dc  mov     [r11-38h], rbx
0x18008e0e0  lea     r15, [rcx+200h]
0x18008e0e7  mov     [r11-40h], rax
0x18008e0eb  setnz   cl
0x18008e0ee  mov     [rsp+98h+var_20], 0
0x18008e0f3  mov     al, [rbx+0EDh]
0x18008e0f9  mov     r9, [rbx+1F8h]
0x18008e100  mov     r8, [rbx+1F0h]
0x18008e107  mov     rdx, [rbx+1D8h]
0x18008e10e  mov     [rsp+98h+var_48], al
0x18008e112  mov     al, [rbx+0ECh]
0x18008e118  mov     [rsp+98h+var_50], al
0x18008e11c  mov     eax, [rbx+17Ch]
0x18008e122  mov     [rsp+98h+var_58], cl
0x18008e126  mov     rcx, r15
0x18008e129  mov     [rsp+98h+var_60], eax
0x18008e12d  mov     eax, [rbx+178h]
0x18008e133  mov     [rsp+98h+var_68], eax
0x18008e137  mov     rax, [rbx+8]
0x18008e13b  mov     [r11-70h], rax
0x18008e13f  mov     eax, [rbx+174h]
0x18008e145  mov     dword ptr [rsp+98h+var_78], eax
0x18008e149  call    WaInitializeDnsQuery
0x18008e14e  lea     r14, [rbx+18h]
0x18008e152  mov     byte ptr [rbx+172h], 1
0x18008e159  mov     rcx, r14; lpCriticalSection
0x18008e15c  call    cs:__imp_LeaveCriticalSection
0x18008e163  nop     dword ptr [rax+rax+00h]
0x18008e168  lea     rax, [rsp+98h+var_28]
0x18008e16d  mov     r8b, 1
0x18008e170  lea     r9, [rsp+98h+var_20]
0x18008e175  mov     [rsp+98h+var_78], rax
0x18008e17a  xor     edx, edx
0x18008e17c  mov     rcx, r15
0x18008e17f  call    WaStartDnsQuery
0x18008e184  test    eax, eax
0x18008e186  jnz     short loc_18008E1C4
0x18008e188  test    byte ptr cs:xmmword_1800AD720, 8
0x18008e18f  jz      short loc_18008E1A8
0x18008e191  lea     edx, [rax+5Dh]
0x18008e194  mov     ecx, 403h
0x18008e199  mov     r9, rbx
0x18008e19c  lea     r8, WPP_14086b36644f38024399eb8d606249d9_Traceguids
0x18008e1a3  call    WPP_SF_q
0x18008e1a8  mov     rdx, [rsp+98h+var_28]
0x18008e1ad  mov     rcx, rbx
0x18008e1b0  call    WapTcpCompleteBackgroundResolution
0x18008e1b5  mov     rcx, [rsp+98h+var_28]
0x18008e1ba  call    WaDereferenceDnsQueryResult
0x18008e1bf  jmp     loc_18008E341
0x18008e1c4  mov     rcx, r14; lpCriticalSection
0x18008e1c7  call    cs:__imp_EnterCriticalSection
0x18008e1ce  nop     dword ptr [rax+rax+00h]
0x18008e1d3  test    byte ptr cs:xmmword_1800AD720, 8
0x18008e1da  jz      short loc_18008E1F5
0x18008e1dc  mov     edx, 5Eh ; '^'
0x18008e1e1  lea     r8, WPP_14086b36644f38024399eb8d606249d9_Traceguids
0x18008e1e8  mov     ecx, 403h
0x18008e1ed  mov     r9, rbx
0x18008e1f0  call    WPP_SF_q
0x18008e1f5  mov     rcx, [r15]
0x18008e1f8  call    WaDereferenceDnsCache
0x18008e1fd  cmp     dword ptr [rbx+0E0h], 4
0x18008e204  mov     byte ptr [rbx+172h], 0
0x18008e20b  jz      short loc_18008E235
0x18008e20d  test    byte ptr cs:xmmword_1800AD720, 8
0x18008e214  jz      loc_18008E332
0x18008e21a  mov     edx, 5Fh ; '_'
0x18008e21f  mov     ecx, 403h
0x18008e224  lea     r8, WPP_14086b36644f38024399eb8d606249d9_Traceguids
0x18008e22b  call    WPP_SF_
0x18008e230  jmp     loc_18008E332
0x18008e235  cmp     byte ptr [rbx+173h], 0
0x18008e23c  jnz     short loc_18008E276
0x18008e23e  lea     rcx, [rbx+198h]; pv
0x18008e245  mov     r9b, 1
0x18008e248  mov     r8, rbx
0x18008e24b  lea     rdx, WapTcpTtlExpiryCallback
0x18008e252  call    WaTpInitializeWorkItem
0x18008e257  test    eax, eax
0x18008e259  jz      short loc_18008E26F
0x18008e25b  test    byte ptr cs:xmmword_1800AD720, 8
0x18008e262  jz      loc_18008E332
0x18008e268  mov     edx, 60h ; '`'
0x18008e26d  jmp     short loc_18008E21F
0x18008e26f  mov     byte ptr [rbx+173h], 1
0x18008e276  cmp     qword ptr [rbx+120h], 0
0x18008e27e  lea     rax, WapTcpTtlExpiryQueryCompletionRoutine
0x18008e285  mov     r9, [rbx+1F8h]
0x18008e28c  mov     rcx, r15
0x18008e28f  mov     r8, [rbx+1F0h]
0x18008e296  setnz   dl
0x18008e299  mov     [rsp+98h+var_38], rbx
0x18008e29e  mov     [rsp+98h+var_40], rax
0x18008e2a3  mov     al, [rbx+0EDh]
0x18008e2a9  mov     [rsp+98h+var_48], al
0x18008e2ad  mov     al, [rbx+0ECh]
0x18008e2b3  mov     [rsp+98h+var_50], al
0x18008e2b7  mov     eax, [rbx+17Ch]
0x18008e2bd  mov     [rsp+98h+var_58], dl
0x18008e2c1  mov     rdx, [rbx+1D8h]
0x18008e2c8  mov     [rsp+98h+var_60], eax
0x18008e2cc  mov     eax, [rbx+178h]
0x18008e2d2  mov     [rsp+98h+var_68], eax
0x18008e2d6  mov     rax, [rbx+8]
0x18008e2da  mov     [rsp+98h+var_70], rax
0x18008e2df  mov     eax, [rbx+174h]
0x18008e2e5  mov     dword ptr [rsp+98h+var_78], eax
0x18008e2e9  call    WaInitializeDnsQuery
0x18008e2ee  mov     byte ptr [rbx+172h], 1
0x18008e2f5  test    byte ptr cs:xmmword_1800AD720, 8
0x18008e2fc  jz      short loc_18008E317
0x18008e2fe  mov     edx, 61h ; 'a'
0x18008e303  lea     r8, WPP_14086b36644f38024399eb8d606249d9_Traceguids
0x18008e30a  mov     ecx, 403h
0x18008e30f  mov     r9, rbx
0x18008e312  call    WPP_SF_q
0x18008e317  mov     rax, [rbx+8]
0x18008e31b  lock inc dword ptr [rax+4]
0x18008e31f  mov     rcx, [rbx+1A0h]; pwk
0x18008e326  call    cs:__imp_SubmitThreadpoolWork
0x18008e32d  nop     dword ptr [rax+rax+00h]
0x18008e332  mov     rcx, r14; lpCriticalSection
0x18008e335  call    cs:__imp_LeaveCriticalSection
0x18008e33c  nop     dword ptr [rax+rax+00h]
0x18008e341  mov     rcx, [rsp+98h+var_18]
0x18008e349  xor     rcx, rsp; StackCookie
0x18008e34c  call    __security_check_cookie
0x18008e351  lea     r11, [rsp+98h+var_8]
0x18008e359  mov     rbx, [r11+18h]
0x18008e35d  mov     r14, [r11+20h]
0x18008e361  mov     rsp, r11
0x18008e364  pop     r15
0x18008e366  retn
```
