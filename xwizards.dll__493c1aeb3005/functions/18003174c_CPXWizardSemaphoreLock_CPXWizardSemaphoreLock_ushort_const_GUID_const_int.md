# CPXWizardSemaphoreLock::CPXWizardSemaphoreLock(ushort * const,_GUID const *,int)

- ea: `0x18003174c`
- end: `0x180031b28`
- name: `??0CPXWizardSemaphoreLock@@QEAA@QEAGPEBU_GUID@@H@Z`
- size: `988`
- prototype: `CPXWizardSemaphoreLock *__fastcall(CPXWizardSemaphoreLock *__hidden this, unsigned __int16 *const, const struct _GUID *, int)`
- caller_count: `2`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001f6f8`
- `0x180021d04`

## callees

- `0x180001200`
- `0x180004370`
- `0x1800085a8`
- `0x18000ae04`
- `0x18000ae90`
- `0x18003174c`
- `0x180032004`
- `0x1800323a4`
- `0x180032a02`
- `0x180032a30`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180031801`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180031801`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800317eb`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800317eb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180031ac8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180031ac8`
- `api-ms-win-core-synch-l1-2-1!CreateSemaphoreW` at `0x180031a3c`
- `api-ms-win-core-synch-l1-2-1!CreateSemaphoreW` at `0x180031a3c`

## pseudocode

```c
// Hidden C++ exception states: #try_helpers=1
CPXWizardSemaphoreLock *__fastcall CPXWizardSemaphoreLock::CPXWizardSemaphoreLock(
        CPXWizardSemaphoreLock *this,
        unsigned __int16 *const a2,
        struct _GUID *a3)
{
  CPXWizardSemaphoreLock *v4; // rsi
  CPXWizardSemaphoreLock *v5; // r13
  CPXWizardMutexLock **v6; // r12
  __int64 v7; // r15
  unsigned __int64 v8; // r15
  unsigned __int16 *v9; // rdi
  CPXWizardMutexLock *v10; // rax
  CPXWizardMutexLock *v11; // rax
  CPXWizardMutexLock *v12; // rax
  CPXWizardMutexLock *v13; // rax
  HANDLE SemaphoreW; // rax
  int LastErrorHRESULT; // eax
  int refreshed; // eax
  struct _GUID *rguid; // [rsp+30h] [rbp-D8h]
  CPXWizardMutexLock **v21; // [rsp+60h] [rbp-A8h]
  CPXWizardMutexLock **v22; // [rsp+68h] [rbp-A0h]
  _QWORD *v23; // [rsp+70h] [rbp-98h]
  OLECHAR sz[40]; // [rsp+80h] [rbp-88h] BYREF

  rguid = a3;
  v4 = this;
  v5 = this;
  *(_DWORD *)this = 0;
  v23 = (_QWORD *)((char *)this + 8);
  *((_QWORD *)this + 1) = 0;
  v6 = (CPXWizardMutexLock **)((char *)this + 24);
  v22 = (CPXWizardMutexLock **)((char *)this + 24);
  *((_QWORD *)this + 3) = 0;
  v21 = (CPXWizardMutexLock **)((char *)this + 32);
  *((_QWORD *)this + 4) = 0;
  *((_DWORD *)this + 4) = -1;
  memset_0(sz, 0, sizeof(sz));
  v7 = 19;
  if ( a3 )
  {
    StringFromGUID2(a3, sz, 40);
    v7 = 58;
  }
  v8 = v7 + 1;
  v9 = (unsigned __int16 *)CoTaskMemAlloc(2 * v8);
  if ( !v9 )
  {
    *(_DWORD *)v4 = -2147024882;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      goto LABEL_37;
    WPP_SF_SD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      10,
      (unsigned int)WPP_683b19af0e50371563cab88aabf72b9d_Traceguids,
      (unsigned int)sz,
      14);
  }
  if ( *(int *)v4 < 0 )
    goto LABEL_37;
  *v9 = 0;
  StringCchCatW(v9, v8, L"_CPXWMSL_:");
  StringCchCatW(v9, v8, L"_XWCSL_:");
  try
  {
    v10 = (CPXWizardMutexLock *)operator new(0x18u);
    if ( v10 )
      v11 = CPXWizardMutexLock::CPXWizardMutexLock(v10, v9, rguid);
    else
      v11 = 0;
    *v6 = v11;
  }
  catch ( ... )
  {
    v5 = this;
    rguid = a3;
    v4 = this;
    v6 = v22;
  }
  if ( !*v6 )
  {
    *(_DWORD *)v4 = -2147024882;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      goto LABEL_37;
    WPP_SF_SD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      11,
      (unsigned int)WPP_683b19af0e50371563cab88aabf72b9d_Traceguids,
      (_DWORD)v9,
      14);
  }
  if ( *(int *)v4 < 0 )
    goto LABEL_37;
  *v9 = 0;
  StringCchCatW(v9, v8, L"_CPXWUSL_:");
  StringCchCatW(v9, v8, L"_XWCSL_:");
  v12 = (CPXWizardMutexLock *)operator new(0x18u);
  if ( v12 )
    v13 = CPXWizardMutexLock::CPXWizardMutexLock(v12, v9, rguid);
  else
    v13 = 0;
  *v21 = v13;
  if ( !*v21 )
  {
    *(_DWORD *)v4 = -2147024882;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      goto LABEL_37;
    WPP_SF_SD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      12,
      (unsigned int)WPP_683b19af0e50371563cab88aabf72b9d_Traceguids,
      (_DWORD)v9,
      14);
  }
  if ( *(int *)v4 >= 0 )
  {
    *v9 = 0;
    StringCchCatW(v9, v8, L"_XWCSL_:");
    if ( rguid )
      StringCchCatW(v9, v8, sz);
    SemaphoreW = CreateSemaphoreW(0, 0, 100, v9);
    *v23 = SemaphoreW;
    if ( !SemaphoreW )
    {
      LastErrorHRESULT = GetLastErrorHRESULT();
      *(_DWORD *)v4 = LastErrorHRESULT;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_SD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          13,
          (unsigned int)WPP_683b19af0e50371563cab88aabf72b9d_Traceguids,
          (_DWORD)v9,
          LastErrorHRESULT);
    }
    if ( *(int *)v4 >= 0 )
    {
      refreshed = CPXWizardSemaphoreLock::HrRefreshReferenceCount(v5, 1);
      *(_DWORD *)v4 = refreshed;
      if ( refreshed < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          14,
          WPP_683b19af0e50371563cab88aabf72b9d_Traceguids,
          (unsigned int)refreshed);
    }
  }
LABEL_37:
  CoTaskMemFree(v9);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      15,
      WPP_683b19af0e50371563cab88aabf72b9d_Traceguids,
      *(unsigned int *)v4);
  return v5;
}

```

## disassembly

```asm
0x18003174c  mov     [rsp+arg_8], rbx
0x180031751  mov     [rsp+arg_18], rsi
0x180031756  push    rdi
0x180031757  push    r12
0x180031759  push    r13
0x18003175b  push    r14
0x18003175d  push    r15
0x18003175f  sub     rsp, 0E0h
0x180031766  mov     rax, cs:__security_cookie
0x18003176d  xor     rax, rsp
0x180031770  mov     [rsp+108h+var_38], rax
0x180031778  mov     rdi, r8
0x18003177b  mov     [rsp+108h+rguid], r8
0x180031780  mov     rsi, rcx
0x180031783  mov     r13, rcx
0x180031786  mov     [rsp+108h+var_C8], rcx
0x18003178b  mov     [rsp+108h+var_C0], r8
0x180031790  xor     ebx, ebx
0x180031792  mov     [rcx], ebx
0x180031794  lea     rax, [rcx+8]
0x180031798  mov     [rsp+108h+var_98], rax
0x18003179d  mov     [rax], rbx
0x1800317a0  lea     r12, [rcx+18h]
0x1800317a4  mov     [rsp+108h+var_A0], r12
0x1800317a9  mov     [r12], rbx
0x1800317ad  lea     rax, [rcx+20h]
0x1800317b1  mov     [rsp+108h+var_A8], rax
0x1800317b6  mov     [rax], rbx
0x1800317b9  mov     dword ptr [rcx+10h], 0FFFFFFFFh
0x1800317c0  xor     edx, edx; Val
0x1800317c2  lea     r8d, [rbx+50h]; Size
0x1800317c6  lea     rcx, [rsp+108h+sz]; void *
0x1800317ce  call    memset_0
0x1800317d3  lea     r15d, [rbx+13h]
0x1800317d7  test    rdi, rdi
0x1800317da  jz      short loc_1800317F5
0x1800317dc  lea     r8d, [rbx+28h]; cchMax
0x1800317e0  lea     rdx, [rsp+108h+sz]; lpsz
0x1800317e8  mov     rcx, rdi; rguid
0x1800317eb  call    cs:__imp_StringFromGUID2
0x1800317f1  lea     r15d, [rbx+3Ah]
0x1800317f5  inc     r15
0x1800317f8  mov     [rsp+108h+var_B0], r15
0x1800317fd  lea     rcx, [r15+r15]; cb
0x180031801  call    cs:__imp_CoTaskMemAlloc
0x180031807  mov     rdi, rax
0x18003180a  mov     [rsp+108h+var_D0], rax
0x18003180f  test    rax, rax
0x180031812  jnz     short loc_180031860
0x180031814  mov     dword ptr [rsi], 8007000Eh
0x18003181a  lea     r14, WPP_GLOBAL_Control
0x180031821  mov     rcx, cs:WPP_GLOBAL_Control
0x180031828  cmp     rcx, r14
0x18003182b  jz      loc_180031AC5
0x180031831  test    byte ptr [rcx+1Ch], 4
0x180031835  jz      loc_180031AC5
0x18003183b  lea     edx, [rax+0Ah]
0x18003183e  mov     [rsp+108h+var_E8], 8007000Eh
0x180031846  lea     r9, [rsp+108h+sz]
0x18003184e  lea     r8, WPP_683b19af0e50371563cab88aabf72b9d_Traceguids
0x180031855  mov     rcx, [rcx+10h]
0x180031859  call    WPP_SF_SD
0x18003185e  jmp     short loc_180031867
0x180031860  lea     r14, WPP_GLOBAL_Control
0x180031867  cmp     [rsi], ebx
0x180031869  jl      loc_180031AC5
0x18003186f  mov     [rdi], bx
0x180031872  lea     r8, aCpxwmsl; "_CPXWMSL_:"
0x180031879  mov     rdx, r15; unsigned __int64
0x18003187c  mov     rcx, rdi; unsigned __int16 *
0x18003187f  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180031884  lea     r8, aXwcsl; "_XWCSL_:"
0x18003188b  mov     rdx, r15; unsigned __int64
0x18003188e  mov     rcx, rdi; unsigned __int16 *
0x180031891  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180031896  nop
0x180031897  mov     ecx, 18h; Size
0x18003189c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800318a1  test    rax, rax
0x1800318a4  jz      short loc_1800318B8
0x1800318a6  mov     r8, [rsp+108h+rguid]; rguid
0x1800318ab  mov     rdx, rdi; unsigned __int16 *
0x1800318ae  mov     rcx, rax; this
0x1800318b1  call    ??0CPXWizardMutexLock@@QEAA@QEAGPEBU_GUID@@@Z; CPXWizardMutexLock::CPXWizardMutexLock(ushort * const,_GUID const *)
0x1800318b6  jmp     short loc_1800318BB
0x1800318b8  mov     rax, rbx
0x1800318bb  mov     [r12], rax
0x1800318bf  jmp     short loc_1800318EB
0x1800318c1  xor     ebx, ebx
0x1800318c3  lea     r14, WPP_GLOBAL_Control
0x1800318ca  mov     rdi, [rsp+108h+var_D0]
0x1800318cf  mov     r13, [rsp+108h+var_C8]
0x1800318d4  mov     r8, [rsp+108h+var_C0]
0x1800318d9  mov     [rsp+108h+rguid], r8
0x1800318de  mov     rsi, r13
0x1800318e1  mov     r12, [rsp+108h+var_A0]
0x1800318e6  mov     r15, [rsp+108h+var_B0]
0x1800318eb  cmp     [r12], rbx
0x1800318ef  jnz     short loc_180031931
0x1800318f1  mov     dword ptr [rsi], 8007000Eh
0x1800318f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800318fe  cmp     rcx, r14
0x180031901  jz      loc_180031AC5
0x180031907  test    byte ptr [rcx+1Ch], 4
0x18003190b  jz      loc_180031AC5
0x180031911  mov     edx, 0Bh
0x180031916  mov     [rsp+108h+var_E8], 8007000Eh
0x18003191e  mov     r9, rdi
0x180031921  lea     r8, WPP_683b19af0e50371563cab88aabf72b9d_Traceguids
0x180031928  mov     rcx, [rcx+10h]
0x18003192c  call    WPP_SF_SD
0x180031931  cmp     [rsi], ebx
0x180031933  jl      loc_180031AC5
0x180031939  mov     [rdi], bx
0x18003193c  lea     r8, aCpxwusl; "_CPXWUSL_:"
0x180031943  mov     rdx, r15; unsigned __int64
0x180031946  mov     rcx, rdi; unsigned __int16 *
0x180031949  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18003194e  lea     r8, aXwcsl; "_XWCSL_:"
0x180031955  mov     rdx, r15; unsigned __int64
0x180031958  mov     rcx, rdi; unsigned __int16 *
0x18003195b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180031960  nop
0x180031961  mov     ecx, 18h; Size
0x180031966  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003196b  mov     r12, [rsp+108h+rguid]
0x180031970  test    rax, rax
0x180031973  jz      short loc_180031985
0x180031975  mov     r8, r12; rguid
0x180031978  mov     rdx, rdi; unsigned __int16 *
0x18003197b  mov     rcx, rax; this
0x18003197e  call    ??0CPXWizardMutexLock@@QEAA@QEAGPEBU_GUID@@@Z; CPXWizardMutexLock::CPXWizardMutexLock(ushort * const,_GUID const *)
0x180031983  jmp     short loc_180031988
0x180031985  mov     rax, rbx
0x180031988  mov     rcx, [rsp+108h+var_A8]
0x18003198d  mov     [rcx], rax
0x180031990  jmp     short loc_1800319B7
0x180031992  xor     ebx, ebx
0x180031994  lea     r14, WPP_GLOBAL_Control
0x18003199b  mov     rdi, [rsp+108h+var_D0]
0x1800319a0  mov     r13, [rsp+108h+var_C8]
0x1800319a5  mov     r12, [rsp+108h+var_C0]
0x1800319aa  mov     rsi, r13
0x1800319ad  mov     r15, [rsp+108h+var_B0]
0x1800319b2  mov     rcx, [rsp+108h+var_A8]
0x1800319b7  cmp     [rcx], rbx
0x1800319ba  jnz     short loc_1800319FC
0x1800319bc  mov     dword ptr [rsi], 8007000Eh
0x1800319c2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800319c9  cmp     rcx, r14
0x1800319cc  jz      loc_180031AC5
0x1800319d2  test    byte ptr [rcx+1Ch], 4
0x1800319d6  jz      loc_180031AC5
0x1800319dc  mov     edx, 0Ch
0x1800319e1  mov     [rsp+108h+var_E8], 8007000Eh
0x1800319e9  mov     r9, rdi
0x1800319ec  lea     r8, WPP_683b19af0e50371563cab88aabf72b9d_Traceguids
0x1800319f3  mov     rcx, [rcx+10h]
0x1800319f7  call    WPP_SF_SD
0x1800319fc  cmp     [rsi], ebx
0x1800319fe  jl      loc_180031AC5
0x180031a04  mov     [rdi], bx
0x180031a07  lea     r8, aXwcsl; "_XWCSL_:"
0x180031a0e  mov     rdx, r15; unsigned __int64
0x180031a11  mov     rcx, rdi; unsigned __int16 *
0x180031a14  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180031a19  test    r12, r12
0x180031a1c  jz      short loc_180031A31
0x180031a1e  lea     r8, [rsp+108h+sz]; unsigned __int16 *
0x180031a26  mov     rdx, r15; unsigned __int64
0x180031a29  mov     rcx, rdi; unsigned __int16 *
0x180031a2c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180031a31  mov     r9, rdi; lpName
0x180031a34  xor     edx, edx; lInitialCount
0x180031a36  xor     ecx, ecx; lpSemaphoreAttributes
0x180031a38  lea     r8d, [rdx+64h]; lMaximumCount
0x180031a3c  call    cs:__imp_CreateSemaphoreW
0x180031a42  mov     rcx, [rsp+108h+var_98]
0x180031a47  mov     [rcx], rax
0x180031a4a  test    rax, rax
0x180031a4d  jnz     short loc_180031A84
0x180031a4f  call    ?GetLastErrorHRESULT@@YAJXZ; GetLastErrorHRESULT(void)
0x180031a54  mov     [rsi], eax
0x180031a56  mov     rcx, cs:WPP_GLOBAL_Control
0x180031a5d  cmp     rcx, r14
0x180031a60  jz      short loc_180031A84
0x180031a62  test    byte ptr [rcx+1Ch], 4
0x180031a66  jz      short loc_180031A84
0x180031a68  mov     edx, 0Dh
0x180031a6d  mov     [rsp+108h+var_E8], eax
0x180031a71  mov     r9, rdi
0x180031a74  lea     r8, WPP_683b19af0e50371563cab88aabf72b9d_Traceguids
0x180031a7b  mov     rcx, [rcx+10h]
0x180031a7f  call    WPP_SF_SD
0x180031a84  cmp     [rsi], ebx
0x180031a86  jl      short loc_180031AC5
0x180031a88  mov     edx, 1; int
0x180031a8d  mov     rcx, r13; this
0x180031a90  call    ?HrRefreshReferenceCount@CPXWizardSemaphoreLock@@AEAAJH@Z; CPXWizardSemaphoreLock::HrRefreshReferenceCount(int)
0x180031a95  mov     [rsi], eax
0x180031a97  test    eax, eax
0x180031a99  jns     short loc_180031AC5
0x180031a9b  mov     rcx, cs:WPP_GLOBAL_Control
0x180031aa2  cmp     rcx, r14
0x180031aa5  jz      short loc_180031AC5
0x180031aa7  test    byte ptr [rcx+1Ch], 4
0x180031aab  jz      short loc_180031AC5
0x180031aad  mov     edx, 0Eh
0x180031ab2  mov     r9d, eax
0x180031ab5  lea     r8, WPP_683b19af0e50371563cab88aabf72b9d_Traceguids
0x180031abc  mov     rcx, [rcx+10h]
0x180031ac0  call    WPP_SF_d
0x180031ac5  mov     rcx, rdi; pv
0x180031ac8  call    cs:__imp_CoTaskMemFree
0x180031ace  mov     rcx, cs:WPP_GLOBAL_Control
0x180031ad5  cmp     rcx, r14
0x180031ad8  jz      short loc_180031AF8
0x180031ada  test    byte ptr [rcx+1Ch], 10h
0x180031ade  jz      short loc_180031AF8
0x180031ae0  mov     edx, 0Fh
0x180031ae5  mov     r9d, [rsi]
0x180031ae8  lea     r8, WPP_683b19af0e50371563cab88aabf72b9d_Traceguids
0x180031aef  mov     rcx, [rcx+10h]
0x180031af3  call    WPP_SF_d
0x180031af8  mov     rax, r13
0x180031afb  mov     rcx, [rsp+108h+var_38]
0x180031b03  xor     rcx, rsp; StackCookie
0x180031b06  call    __security_check_cookie
0x180031b0b  lea     r11, [rsp+108h+var_28]
0x180031b13  mov     rbx, [r11+38h]
0x180031b17  mov     rsi, [r11+48h]
0x180031b1b  mov     rsp, r11
0x180031b1e  pop     r15
0x180031b20  pop     r14
0x180031b22  pop     r13
0x180031b24  pop     r12
0x180031b26  pop     rdi
0x180031b27  retn
```
