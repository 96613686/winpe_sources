# wil::details::ReportFailure_CaughtExceptionCommon<1>(void *,uint,char const *,char const *,char const *,void *,ushort *,unsigned __int64,wil::SupportedExceptions)

- ea: `0x180009810`
- end: `0x180009912`
- name: `??$ReportFailure_CaughtExceptionCommon@$00@details@wil@@YA?AUResultStatus@01@PEAXIPEBD110PEAG_KW4SupportedExceptions@1@@Z`
- size: `258`
- prototype: `__int64 __fastcall(__int64, int, int, int, int, int, __int64, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180009778`

## callees

- `0x180001dc0`
- `0x180002b8c`
- `0x180002bec`
- `0x180004374`
- `0x180009810`
- `0x18000d010`

## pseudocode

```c
__int64 __fastcall wil::details::ReportFailure_CaughtExceptionCommon<1>(
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
  wil::details::ReportFailure_Base<1,0>(a2, a3, a4, v15, v18, a7, a1, a8);
  return a1;
}

```

## disassembly

```asm
0x180009810  push    rbx
0x180009812  push    rbp
0x180009813  push    rsi
0x180009814  push    rdi
0x180009815  push    r12
0x180009817  push    r14
0x180009819  push    r15
0x18000981b  sub     rsp, 70h
0x18000981f  mov     rax, cs:__security_cookie
0x180009826  xor     rax, rsp
0x180009829  mov     [rsp+0A8h+var_40], rax
0x18000982e  mov     r15, [rsp+0A8h+arg_30]
0x180009836  xor     r12d, r12d
0x180009839  mov     rdi, [rsp+0A8h+arg_38]
0x180009841  mov     rbx, rcx
0x180009844  mov     [rsp+0A8h+var_48], r12b
0x180009849  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000984d  mov     r14, r9
0x180009850  mov     ebp, r8d
0x180009853  mov     rsi, rdx
0x180009856  inc     rcx
0x180009859  cmp     [rdi+rcx*2], r12w
0x18000985e  jnz     short loc_180009856
0x180009860  mov     rax, cs:g_pfnResultFromCaughtExceptionInternal
0x180009867  mov     [rbx], r12
0x18000986a  mov     dword ptr [rbx+8], 1
0x180009871  test    rax, rax
0x180009874  jz      short loc_1800098E2
0x180009876  lea     rdx, [rdi+rcx*2]
0x18000987a  mov     r8d, 800h
0x180009880  sub     r8, rcx
0x180009883  lea     r9, [rsp+0A8h+var_48]
0x180009888  lea     rcx, [rsp+0A8h+var_58]
0x18000988d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009892  movsd   xmm0, qword ptr [rax]
0x180009896  mov     r9d, [rax+8]
0x18000989a  movsd   qword ptr [rbx], xmm0
0x18000989e  mov     [rbx+8], r9d
0x1800098a2  cmp     [rbx], r12d
0x1800098a5  jge     short loc_1800098E2
0x1800098a7  mov     [rsp+0A8h+var_70], rdi
0x1800098ac  mov     r8, r14
0x1800098af  mov     [rsp+0A8h+var_78], rbx
0x1800098b4  mov     edx, ebp
0x1800098b6  mov     rcx, rsi
0x1800098b9  mov     [rsp+0A8h+var_80], r15
0x1800098be  call    ??$ReportFailure_Base@$00$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<1,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x1800098c3  mov     rax, rbx
0x1800098c6  mov     rcx, [rsp+0A8h+var_40]
0x1800098cb  xor     rcx, rsp; StackCookie
0x1800098ce  call    __security_check_cookie
0x1800098d3  add     rsp, 70h
0x1800098d7  pop     r15
0x1800098d9  pop     r14
0x1800098db  pop     r12
0x1800098dd  pop     rdi
0x1800098de  pop     rsi
0x1800098df  pop     rbp
0x1800098e0  pop     rbx
0x1800098e1  retn
0x1800098e2  mov     ecx, 8007023Eh; this
0x1800098e7  mov     [rbx], ecx
0x1800098e9  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800098ee  mov     [rsp+0A8h+var_70], rdi
0x1800098f3  mov     rcx, rsi
0x1800098f6  mov     [rbx+4], eax
0x1800098f9  mov     r8, r14
0x1800098fc  mov     [rsp+0A8h+var_78], rbx
0x180009901  mov     edx, ebp
0x180009903  mov     [rbx+8], r12d
0x180009907  mov     [rsp+0A8h+var_80], r15
0x18000990c  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
