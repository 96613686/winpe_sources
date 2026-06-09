# wil::details::ReportFailure_CaughtExceptionCommon<1>(void *,uint,char const *,char const *,char const *,void *,ushort *,unsigned __int64,wil::SupportedExceptions)

- ea: `0x18000e0b0`
- end: `0x18000e19c`
- name: `??$ReportFailure_CaughtExceptionCommon@$00@details@wil@@YA?AUResultStatus@01@PEAXIPEBD110PEAG_KW4SupportedExceptions@1@@Z`
- size: `236`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000e028`

## callees

- `0x18000df94`
- `0x18000dff0`
- `0x18000e0b0`
- `0x180012eec`
- `0x18002c010`

## pseudocode

```c
__int64 __fastcall wil::details::ReportFailure_CaughtExceptionCommon<1>(
        __int64 a1,
        __int64 a2,
        int a3,
        __int64 a4,
        int a5,
        int a6,
        __int64 a7,
        __int64 a8)
{
  __int64 v8; // rdi
  __int64 v10; // rcx
  __int64 (__fastcall *v12)(_BYTE *, __int64, __int64, int *); // rax
  __int64 v13; // rax
  int v14; // ecx
  int v16; // r9d
  _BYTE v17[56]; // [rsp+50h] [rbp-38h] BYREF
  int v18; // [rsp+A0h] [rbp+18h] BYREF

  v18 = a3;
  v8 = a8;
  LOBYTE(v18) = 0;
  v10 = -1;
  do
    ++v10;
  while ( *(_WORD *)(a8 + 2 * v10) );
  v12 = (__int64 (__fastcall *)(_BYTE *, __int64, __int64, int *))g_pfnResultFromCaughtExceptionInternal;
  *(_QWORD *)a1 = 0;
  *(_DWORD *)(a1 + 8) = 1;
  if ( !v12
    || (v13 = v12(v17, v8 + 2 * v10, 2048 - v10, &v18),
        v14 = *(_DWORD *)(v13 + 8),
        *(_QWORD *)a1 = *(_QWORD *)v13,
        *(_DWORD *)(a1 + 8) = v14,
        *(int *)a1 >= 0) )
  {
    *(_DWORD *)a1 = -2147024322;
    *(_DWORD *)(a1 + 4) = wil::details::HrToNtStatus((wil::details *)0x8007023ELL, a2);
    *(_DWORD *)(a1 + 8) = 0;
    wil::details::ReportFailure_Base<3,0>(
      a2,
      416,
      (unsigned int)"onecore\\drivers\\storage\\storsvc\\storageusage\\storagegrovelerscans.cpp",
      v16);
  }
  wil::details::ReportFailure_Base<1,0>(
    a2,
    416,
    "onecore\\drivers\\storage\\storsvc\\storageusage\\storagegrovelerscans.cpp");
  return a1;
}

```

## disassembly

```asm
0x18000e0b0  mov     rax, rsp
0x18000e0b3  mov     [rax+18h], r8d
0x18000e0b7  push    rbx
0x18000e0b8  push    rbp
0x18000e0b9  push    rsi
0x18000e0ba  push    rdi
0x18000e0bb  sub     rsp, 68h
0x18000e0bf  mov     rdi, [rsp+88h+arg_38]
0x18000e0c7  xor     ebp, ebp
0x18000e0c9  mov     rbx, rcx
0x18000e0cc  mov     [rax+18h], bpl
0x18000e0d0  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000e0d4  mov     rsi, rdx
0x18000e0d7  inc     rcx
0x18000e0da  cmp     [rdi+rcx*2], bp
0x18000e0de  jnz     short loc_18000E0D7
0x18000e0e0  mov     rax, cs:g_pfnResultFromCaughtExceptionInternal
0x18000e0e7  mov     [rbx], rbp
0x18000e0ea  mov     dword ptr [rbx+8], 1
0x18000e0f1  test    rax, rax
0x18000e0f4  jz      short loc_18000E15E
0x18000e0f6  lea     rdx, [rdi+rcx*2]
0x18000e0fa  mov     r8d, 800h
0x18000e100  sub     r8, rcx
0x18000e103  lea     r9, [rsp+88h+arg_10]
0x18000e10b  lea     rcx, [rsp+88h+var_38]
0x18000e110  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e115  movsd   xmm0, qword ptr [rax]
0x18000e119  mov     ecx, [rax+8]
0x18000e11c  movsd   qword ptr [rbx], xmm0
0x18000e120  mov     [rbx+8], ecx
0x18000e123  cmp     [rbx], ebp
0x18000e125  jge     short loc_18000E15E
0x18000e127  mov     rax, [rsp+88h+arg_30]
0x18000e12f  lea     r8, aOnecoreDrivers; "onecore\\drivers\\storage\\storsvc\\sto"...
0x18000e136  mov     [rsp+88h+var_50], rdi
0x18000e13b  mov     edx, 1A0h
0x18000e140  mov     [rsp+88h+var_58], rbx
0x18000e145  mov     rcx, rsi
0x18000e148  mov     [rsp+88h+var_60], rax
0x18000e14d  call    ??$ReportFailure_Base@$00$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<1,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x18000e152  mov     rax, rbx
0x18000e155  add     rsp, 68h
0x18000e159  pop     rdi
0x18000e15a  pop     rsi
0x18000e15b  pop     rbp
0x18000e15c  pop     rbx
0x18000e15d  retn
0x18000e15e  mov     ecx, 8007023Eh; this
0x18000e163  mov     [rbx], ecx
0x18000e165  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000e16a  mov     [rbx+4], eax
0x18000e16d  lea     r8, aOnecoreDrivers; "onecore\\drivers\\storage\\storsvc\\sto"...
0x18000e174  mov     rax, [rsp+88h+arg_30]
0x18000e17c  mov     edx, 1A0h
0x18000e181  mov     [rsp+88h+var_50], rdi
0x18000e186  mov     rcx, rsi
0x18000e189  mov     [rsp+88h+var_58], rbx
0x18000e18e  mov     [rsp+88h+var_60], rax
0x18000e193  mov     [rbx+8], ebp
0x18000e196  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
