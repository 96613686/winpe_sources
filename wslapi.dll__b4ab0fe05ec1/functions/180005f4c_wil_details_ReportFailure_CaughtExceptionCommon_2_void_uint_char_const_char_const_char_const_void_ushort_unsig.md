# wil::details::ReportFailure_CaughtExceptionCommon<2>(void *,uint,char const *,char const *,char const *,void *,ushort *,unsigned __int64,wil::SupportedExceptions)

- ea: `0x180005f4c`
- end: `0x18000605b`
- name: `??$ReportFailure_CaughtExceptionCommon@$01@details@wil@@YA?AUResultStatus@01@PEAXIPEBD110PEAG_KW4SupportedExceptions@1@@Z`
- size: `271`
- prototype: `__int64 __fastcall(__int64, int, int, int, int, int, __int64, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180005eb4`

## callees

- `0x180001dc0`
- `0x180002b98`
- `0x180002bec`
- `0x180004374`
- `0x180005f4c`
- `0x18000d010`

## pseudocode

```c
__int64 __fastcall wil::details::ReportFailure_CaughtExceptionCommon<2>(
        __int64 a1,
        int a2,
        int a3,
        int a4,
        int a5,
        int a6,
        __int64 a7,
        __int64 a8)
{
  __int64 v9; // rcx
  __int64 (__fastcall *v13)(_BYTE *, __int64, __int64, _BYTE *); // rax
  __int64 v14; // rax
  int v15; // r9d
  int v17; // r9d
  int v18; // [rsp+20h] [rbp-88h]
  _BYTE v19[16]; // [rsp+50h] [rbp-58h] BYREF
  _BYTE v20[8]; // [rsp+60h] [rbp-48h] BYREF

  v20[0] = 0;
  v9 = -1;
  do
    ++v9;
  while ( *(_WORD *)(a8 + 2 * v9) );
  v13 = (__int64 (__fastcall *)(_BYTE *, __int64, __int64, _BYTE *))g_pfnResultFromCaughtExceptionInternal;
  *(_QWORD *)a1 = 0;
  *(_DWORD *)(a1 + 8) = 1;
  if ( !v13
    || (v14 = v13(v19, a8 + 2 * v9, 2048 - v9, v20),
        v15 = *(_DWORD *)(v14 + 8),
        *(_QWORD *)a1 = *(_QWORD *)v14,
        *(_DWORD *)(a1 + 8) = v15,
        *(int *)a1 >= 0) )
  {
    *(_DWORD *)a1 = -2147024322;
    *(_DWORD *)(a1 + 4) = wil::details::HrToNtStatus((wil::details *)0x8007023ELL, a2);
    *(_DWORD *)(a1 + 8) = 0;
    wil::details::ReportFailure_Base<3,0>(a2, a3, a4, v17, v18, a7, a1, a8);
  }
  wil::details::ReportFailure_Base<2,0>(a2, a3, a4, 0, 0, a7, a1, a8);
  return a1;
}

```

## disassembly

```asm
0x180005f4c  push    rbx
0x180005f4e  push    rbp
0x180005f4f  push    rsi
0x180005f50  push    rdi
0x180005f51  push    r12
0x180005f53  push    r14
0x180005f55  push    r15
0x180005f57  sub     rsp, 70h
0x180005f5b  mov     rax, cs:__security_cookie
0x180005f62  xor     rax, rsp
0x180005f65  mov     [rsp+0A8h+var_40], rax
0x180005f6a  mov     r15, [rsp+0A8h+arg_30]
0x180005f72  xor     r12d, r12d
0x180005f75  mov     rdi, [rsp+0A8h+arg_38]
0x180005f7d  mov     rbx, rcx
0x180005f80  mov     [rsp+0A8h+var_48], r12b
0x180005f85  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180005f89  mov     r14, r9
0x180005f8c  mov     ebp, r8d
0x180005f8f  mov     rsi, rdx
0x180005f92  inc     rcx
0x180005f95  cmp     [rdi+rcx*2], r12w
0x180005f9a  jnz     short loc_180005F92
0x180005f9c  mov     rax, cs:g_pfnResultFromCaughtExceptionInternal
0x180005fa3  mov     [rbx], r12
0x180005fa6  mov     dword ptr [rbx+8], 1
0x180005fad  test    rax, rax
0x180005fb0  jz      short loc_18000602B
0x180005fb2  lea     rdx, [rdi+rcx*2]
0x180005fb6  mov     r8d, 800h
0x180005fbc  sub     r8, rcx
0x180005fbf  lea     r9, [rsp+0A8h+var_48]
0x180005fc4  lea     rcx, [rsp+0A8h+var_58]
0x180005fc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005fce  movsd   xmm0, qword ptr [rax]
0x180005fd2  mov     r9d, [rax+8]
0x180005fd6  movsd   qword ptr [rbx], xmm0
0x180005fda  mov     [rbx+8], r9d
0x180005fde  cmp     [rbx], r12d
0x180005fe1  jge     short loc_18000602B
0x180005fe3  mov     [rsp+0A8h+var_60], r12d
0x180005fe8  xor     r9d, r9d
0x180005feb  mov     [rsp+0A8h+var_70], rdi
0x180005ff0  mov     r8, r14
0x180005ff3  mov     [rsp+0A8h+var_78], rbx
0x180005ff8  mov     edx, ebp
0x180005ffa  mov     [rsp+0A8h+var_80], r15
0x180005fff  mov     rcx, rsi
0x180006002  mov     [rsp+0A8h+var_88], r12
0x180006007  call    ??$ReportFailure_Base@$01$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<2,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x18000600c  mov     rax, rbx
0x18000600f  mov     rcx, [rsp+0A8h+var_40]
0x180006014  xor     rcx, rsp; StackCookie
0x180006017  call    __security_check_cookie
0x18000601c  add     rsp, 70h
0x180006020  pop     r15
0x180006022  pop     r14
0x180006024  pop     r12
0x180006026  pop     rdi
0x180006027  pop     rsi
0x180006028  pop     rbp
0x180006029  pop     rbx
0x18000602a  retn
0x18000602b  mov     ecx, 8007023Eh; this
0x180006030  mov     [rbx], ecx
0x180006032  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180006037  mov     [rsp+0A8h+var_70], rdi
0x18000603c  mov     rcx, rsi
0x18000603f  mov     [rbx+4], eax
0x180006042  mov     r8, r14
0x180006045  mov     [rsp+0A8h+var_78], rbx
0x18000604a  mov     edx, ebp
0x18000604c  mov     [rbx+8], r12d
0x180006050  mov     [rsp+0A8h+var_80], r15
0x180006055  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
