# CPXWizardSemaphoreLock::CPXWizardSemaphoreLock(ushort * const,_GUID const *,int)

- ea: `0x180010ff4`
- end: `0x1800113cb`
- name: `??0CPXWizardSemaphoreLock@@QEAA@QEAGPEBU_GUID@@H@Z`
- size: `983`
- prototype: `CPXWizardSemaphoreLock *__fastcall(CPXWizardSemaphoreLock *this, unsigned __int16 *const, struct _GUID *)`
- caller_count: `2`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800085ac`
- `0x180009ca0`

## callees

- `0x1800011dc`
- `0x180003b90`
- `0x180007820`
- `0x18000a948`
- `0x18000abbc`
- `0x180010ff4`
- `0x180011578`
- `0x180011c8c`
- `0x1800127d6`
- `0x180012800`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001136b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001136b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800110a9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800110a9`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180011093`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180011093`
- `api-ms-win-core-synch-l1-2-1!CreateSemaphoreW` at `0x1800112e4`
- `api-ms-win-core-synch-l1-2-1!CreateSemaphoreW` at `0x1800112e4`

## pseudocode

```c
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
  int v15; // edx
  int LastErrorHRESULT; // eax
  int refreshed; // eax
  struct _GUID *rguid; // [rsp+30h] [rbp-D8h]
  CPXWizardMutexLock **v22; // [rsp+60h] [rbp-A8h]
  CPXWizardMutexLock **v23; // [rsp+68h] [rbp-A0h]
  _QWORD *v24; // [rsp+70h] [rbp-98h]
  OLECHAR sz[40]; // [rsp+80h] [rbp-88h] BYREF

  rguid = a3;
  v4 = this;
  v5 = this;
  *(_DWORD *)this = 0;
  v24 = (_QWORD *)((char *)this + 8);
  *((_QWORD *)this + 1) = 0;
  v6 = (CPXWizardMutexLock **)((char *)this + 24);
  v23 = (CPXWizardMutexLock **)((char *)this + 24);
  *((_QWORD *)this + 3) = 0;
  v22 = (CPXWizardMutexLock **)((char *)this + 32);
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
      (unsigned int)&WPP_683b19af0e50371563cab88aabf72b9d_Traceguids,
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
    v6 = v23;
  }
  if ( !*v6 )
  {
    *(_DWORD *)v4 = -2147024882;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      goto LABEL_37;
    WPP_SF_SD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      11,
      (unsigned int)&WPP_683b19af0e50371563cab88aabf72b9d_Traceguids,
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
  *v22 = v13;
  if ( !*v22 )
  {
    *(_DWORD *)v4 = -2147024882;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      goto LABEL_37;
    WPP_SF_SD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      12,
      (unsigned int)&WPP_683b19af0e50371563cab88aabf72b9d_Traceguids,
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
    *v24 = SemaphoreW;
    if ( !SemaphoreW )
    {
      LastErrorHRESULT = GetLastErrorHRESULT();
      *(_DWORD *)v4 = LastErrorHRESULT;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_SD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          13,
          (unsigned int)&WPP_683b19af0e50371563cab88aabf72b9d_Traceguids,
          (_DWORD)v9,
          LastErrorHRESULT);
    }
    if ( *(int *)v4 >= 0 )
    {
      refreshed = CPXWizardSemaphoreLock::HrRefreshReferenceCount(v5, v15);
      *(_DWORD *)v4 = refreshed;
      if ( refreshed < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_D(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          14,
          &WPP_683b19af0e50371563cab88aabf72b9d_Traceguids,
          (unsigned int)refreshed);
    }
  }
LABEL_37:
  CoTaskMemFree(v9);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      15,
      &WPP_683b19af0e50371563cab88aabf72b9d_Traceguids,
      *(unsigned int *)v4);
  return v5;
}

```

## disassembly

```asm
0x180010ff4  mov     [rsp+arg_8], rbx
0x180010ff9  mov     [rsp+arg_18], rsi
0x180010ffe  push    rdi
0x180010fff  push    r12
0x180011001  push    r13
0x180011003  push    r14
0x180011005  push    r15
0x180011007  sub     rsp, 0E0h
0x18001100e  mov     rax, cs:__security_cookie
0x180011015  xor     rax, rsp
0x180011018  mov     [rsp+108h+var_38], rax
0x180011020  mov     rdi, r8
0x180011023  mov     [rsp+108h+rguid], r8
0x180011028  mov     rsi, rcx
0x18001102b  mov     r13, rcx
0x18001102e  mov     [rsp+108h+var_C8], rcx
0x180011033  mov     [rsp+108h+var_C0], r8
0x180011038  xor     ebx, ebx
0x18001103a  mov     [rcx], ebx
0x18001103c  lea     rax, [rcx+8]
0x180011040  mov     [rsp+108h+var_98], rax
0x180011045  mov     [rax], rbx
0x180011048  lea     r12, [rcx+18h]
0x18001104c  mov     [rsp+108h+var_A0], r12
0x180011051  mov     [r12], rbx
0x180011055  lea     rax, [rcx+20h]
0x180011059  mov     [rsp+108h+var_A8], rax
0x18001105e  mov     [rax], rbx
0x180011061  mov     dword ptr [rcx+10h], 0FFFFFFFFh
0x180011068  xor     edx, edx; Val
0x18001106a  lea     r8d, [rbx+50h]; Size
0x18001106e  lea     rcx, [rsp+108h+sz]; void *
0x180011076  call    memset_0
0x18001107b  lea     r15d, [rbx+13h]
0x18001107f  test    rdi, rdi
0x180011082  jz      short loc_18001109D
0x180011084  lea     r8d, [rbx+28h]; cchMax
0x180011088  lea     rdx, [rsp+108h+sz]; lpsz
0x180011090  mov     rcx, rdi; rguid
0x180011093  call    cs:__imp_StringFromGUID2
0x180011099  lea     r15d, [rbx+3Ah]
0x18001109d  inc     r15
0x1800110a0  mov     [rsp+108h+var_B0], r15
0x1800110a5  lea     rcx, [r15+r15]; cb
0x1800110a9  call    cs:__imp_CoTaskMemAlloc
0x1800110af  mov     rdi, rax
0x1800110b2  mov     [rsp+108h+var_D0], rax
0x1800110b7  test    rax, rax
0x1800110ba  jnz     short loc_180011108
0x1800110bc  mov     dword ptr [rsi], 8007000Eh
0x1800110c2  lea     r14, WPP_GLOBAL_Control
0x1800110c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800110d0  cmp     rcx, r14
0x1800110d3  jz      loc_180011368
0x1800110d9  test    byte ptr [rcx+1Ch], 4
0x1800110dd  jz      loc_180011368
0x1800110e3  lea     edx, [rax+0Ah]
0x1800110e6  mov     [rsp+108h+var_E8], 8007000Eh
0x1800110ee  lea     r9, [rsp+108h+sz]
0x1800110f6  lea     r8, WPP_683b19af0e50371563cab88aabf72b9d_Traceguids
0x1800110fd  mov     rcx, [rcx+10h]
0x180011101  call    WPP_SF_SD
0x180011106  jmp     short loc_18001110F
0x180011108  lea     r14, WPP_GLOBAL_Control
0x18001110f  cmp     [rsi], ebx
0x180011111  jl      loc_180011368
0x180011117  mov     [rdi], bx
0x18001111a  lea     r8, aCpxwmsl; "_CPXWMSL_:"
0x180011121  mov     rdx, r15; unsigned __int64
0x180011124  mov     rcx, rdi; unsigned __int16 *
0x180011127  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001112c  lea     r8, aXwcsl; "_XWCSL_:"
0x180011133  mov     rdx, r15; unsigned __int64
0x180011136  mov     rcx, rdi; unsigned __int16 *
0x180011139  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001113e  nop
0x18001113f  mov     ecx, 18h; Size
0x180011144  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180011149  test    rax, rax
0x18001114c  jz      short loc_180011160
0x18001114e  mov     r8, [rsp+108h+rguid]; rguid
0x180011153  mov     rdx, rdi; unsigned __int16 *
0x180011156  mov     rcx, rax; this
0x180011159  call    ??0CPXWizardMutexLock@@QEAA@QEAGPEBU_GUID@@@Z; CPXWizardMutexLock::CPXWizardMutexLock(ushort * const,_GUID const *)
0x18001115e  jmp     short loc_180011163
0x180011160  mov     rax, rbx
0x180011163  mov     [r12], rax
0x180011167  jmp     short loc_180011193
0x180011169  xor     ebx, ebx
0x18001116b  lea     r14, WPP_GLOBAL_Control
0x180011172  mov     rdi, [rsp+108h+var_D0]
0x180011177  mov     r13, [rsp+108h+var_C8]
0x18001117c  mov     r8, [rsp+108h+var_C0]
0x180011181  mov     [rsp+108h+rguid], r8
0x180011186  mov     rsi, r13
0x180011189  mov     r12, [rsp+108h+var_A0]
0x18001118e  mov     r15, [rsp+108h+var_B0]
0x180011193  cmp     [r12], rbx
0x180011197  jnz     short loc_1800111D9
0x180011199  mov     dword ptr [rsi], 8007000Eh
0x18001119f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800111a6  cmp     rcx, r14
0x1800111a9  jz      loc_180011368
0x1800111af  test    byte ptr [rcx+1Ch], 4
0x1800111b3  jz      loc_180011368
0x1800111b9  mov     edx, 0Bh
0x1800111be  mov     [rsp+108h+var_E8], 8007000Eh
0x1800111c6  mov     r9, rdi
0x1800111c9  lea     r8, WPP_683b19af0e50371563cab88aabf72b9d_Traceguids
0x1800111d0  mov     rcx, [rcx+10h]
0x1800111d4  call    WPP_SF_SD
0x1800111d9  cmp     [rsi], ebx
0x1800111db  jl      loc_180011368
0x1800111e1  mov     [rdi], bx
0x1800111e4  lea     r8, aCpxwusl; "_CPXWUSL_:"
0x1800111eb  mov     rdx, r15; unsigned __int64
0x1800111ee  mov     rcx, rdi; unsigned __int16 *
0x1800111f1  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800111f6  lea     r8, aXwcsl; "_XWCSL_:"
0x1800111fd  mov     rdx, r15; unsigned __int64
0x180011200  mov     rcx, rdi; unsigned __int16 *
0x180011203  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180011208  nop
0x180011209  mov     ecx, 18h; Size
0x18001120e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180011213  mov     r12, [rsp+108h+rguid]
0x180011218  test    rax, rax
0x18001121b  jz      short loc_18001122D
0x18001121d  mov     r8, r12; rguid
0x180011220  mov     rdx, rdi; unsigned __int16 *
0x180011223  mov     rcx, rax; this
0x180011226  call    ??0CPXWizardMutexLock@@QEAA@QEAGPEBU_GUID@@@Z; CPXWizardMutexLock::CPXWizardMutexLock(ushort * const,_GUID const *)
0x18001122b  jmp     short loc_180011230
0x18001122d  mov     rax, rbx
0x180011230  mov     rcx, [rsp+108h+var_A8]
0x180011235  mov     [rcx], rax
0x180011238  jmp     short loc_18001125F
0x18001123a  xor     ebx, ebx
0x18001123c  lea     r14, WPP_GLOBAL_Control
0x180011243  mov     rdi, [rsp+108h+var_D0]
0x180011248  mov     r13, [rsp+108h+var_C8]
0x18001124d  mov     r12, [rsp+108h+var_C0]
0x180011252  mov     rsi, r13
0x180011255  mov     r15, [rsp+108h+var_B0]
0x18001125a  mov     rcx, [rsp+108h+var_A8]
0x18001125f  cmp     [rcx], rbx
0x180011262  jnz     short loc_1800112A4
0x180011264  mov     dword ptr [rsi], 8007000Eh
0x18001126a  mov     rcx, cs:WPP_GLOBAL_Control
0x180011271  cmp     rcx, r14
0x180011274  jz      loc_180011368
0x18001127a  test    byte ptr [rcx+1Ch], 4
0x18001127e  jz      loc_180011368
0x180011284  mov     edx, 0Ch
0x180011289  mov     [rsp+108h+var_E8], 8007000Eh
0x180011291  mov     r9, rdi
0x180011294  lea     r8, WPP_683b19af0e50371563cab88aabf72b9d_Traceguids
0x18001129b  mov     rcx, [rcx+10h]
0x18001129f  call    WPP_SF_SD
0x1800112a4  cmp     [rsi], ebx
0x1800112a6  jl      loc_180011368
0x1800112ac  mov     [rdi], bx
0x1800112af  lea     r8, aXwcsl; "_XWCSL_:"
0x1800112b6  mov     rdx, r15; unsigned __int64
0x1800112b9  mov     rcx, rdi; unsigned __int16 *
0x1800112bc  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800112c1  test    r12, r12
0x1800112c4  jz      short loc_1800112D9
0x1800112c6  lea     r8, [rsp+108h+sz]; unsigned __int16 *
0x1800112ce  mov     rdx, r15; unsigned __int64
0x1800112d1  mov     rcx, rdi; unsigned __int16 *
0x1800112d4  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800112d9  mov     r9, rdi; lpName
0x1800112dc  xor     edx, edx; lInitialCount
0x1800112de  xor     ecx, ecx; lpSemaphoreAttributes
0x1800112e0  lea     r8d, [rdx+64h]; lMaximumCount
0x1800112e4  call    cs:__imp_CreateSemaphoreW
0x1800112ea  mov     rcx, [rsp+108h+var_98]
0x1800112ef  mov     [rcx], rax
0x1800112f2  test    rax, rax
0x1800112f5  jnz     short loc_18001132C
0x1800112f7  call    ?GetLastErrorHRESULT@@YAJXZ; GetLastErrorHRESULT(void)
0x1800112fc  mov     [rsi], eax
0x1800112fe  mov     rcx, cs:WPP_GLOBAL_Control
0x180011305  cmp     rcx, r14
0x180011308  jz      short loc_18001132C
0x18001130a  test    byte ptr [rcx+1Ch], 4
0x18001130e  jz      short loc_18001132C
0x180011310  mov     edx, 0Dh
0x180011315  mov     [rsp+108h+var_E8], eax
0x180011319  mov     r9, rdi
0x18001131c  lea     r8, WPP_683b19af0e50371563cab88aabf72b9d_Traceguids
0x180011323  mov     rcx, [rcx+10h]
0x180011327  call    WPP_SF_SD
0x18001132c  cmp     [rsi], ebx
0x18001132e  jl      short loc_180011368
0x180011330  mov     rcx, r13; this
0x180011333  call    ?HrRefreshReferenceCount@CPXWizardSemaphoreLock@@AEAAJH@Z; CPXWizardSemaphoreLock::HrRefreshReferenceCount(int)
0x180011338  mov     [rsi], eax
0x18001133a  test    eax, eax
0x18001133c  jns     short loc_180011368
0x18001133e  mov     rcx, cs:WPP_GLOBAL_Control
0x180011345  cmp     rcx, r14
0x180011348  jz      short loc_180011368
0x18001134a  test    byte ptr [rcx+1Ch], 4
0x18001134e  jz      short loc_180011368
0x180011350  mov     edx, 0Eh
0x180011355  mov     r9d, eax
0x180011358  lea     r8, WPP_683b19af0e50371563cab88aabf72b9d_Traceguids
0x18001135f  mov     rcx, [rcx+10h]
0x180011363  call    WPP_SF_D
0x180011368  mov     rcx, rdi; pv
0x18001136b  call    cs:__imp_CoTaskMemFree
0x180011371  mov     rcx, cs:WPP_GLOBAL_Control
0x180011378  cmp     rcx, r14
0x18001137b  jz      short loc_18001139B
0x18001137d  test    byte ptr [rcx+1Ch], 10h
0x180011381  jz      short loc_18001139B
0x180011383  mov     edx, 0Fh
0x180011388  mov     r9d, [rsi]
0x18001138b  lea     r8, WPP_683b19af0e50371563cab88aabf72b9d_Traceguids
0x180011392  mov     rcx, [rcx+10h]
0x180011396  call    WPP_SF_D
0x18001139b  mov     rax, r13
0x18001139e  mov     rcx, [rsp+108h+var_38]
0x1800113a6  xor     rcx, rsp; StackCookie
0x1800113a9  call    __security_check_cookie
0x1800113ae  lea     r11, [rsp+108h+var_28]
0x1800113b6  mov     rbx, [r11+38h]
0x1800113ba  mov     rsi, [r11+48h]
0x1800113be  mov     rsp, r11
0x1800113c1  pop     r15
0x1800113c3  pop     r14
0x1800113c5  pop     r13
0x1800113c7  pop     r12
0x1800113c9  pop     rdi
0x1800113ca  retn
```
