# wil::details::ReportFailure_CaughtExceptionCommonNoReturnBase<3>(void *,uint,char const *,char const *,char const *,void *,ushort *,unsigned __int64,wil::SupportedExceptions)

- ea: `0x18000d058`
- end: `0x18000d134`
- name: `??$ReportFailure_CaughtExceptionCommonNoReturnBase@$02@details@wil@@YA?AUResultStatus@01@PEAXIPEBD110PEAG_KW4SupportedExceptions@1@@Z`
- size: `220`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000d028`

## callees

- `0x180004ec8`
- `0x1800082dc`
- `0x18000d058`
- `0x180034010`

## string_xrefs

- `0x18000d0db`: `onecore\vm\dv\storage\plan9\dll\p9await.h`
- `0x18000d107`: `onecore\vm\dv\storage\plan9\dll\p9await.h`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_CaughtExceptionCommonNoReturnBase<3>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        int a6,
        __int64 a7,
        __int64 a8)
{
  __int64 v8; // rcx
  int v10; // r9d
  int v11; // r9d
  _BYTE v12[16]; // [rsp+60h] [rbp-48h] BYREF
  _BYTE v13[56]; // [rsp+70h] [rbp-38h] BYREF

  v8 = -1;
  v13[0] = 0;
  do
    ++v8;
  while ( *(_WORD *)(a8 + 2 * v8) );
  if ( g_pfnResultFromCaughtExceptionInternal )
  {
    if ( _mm_cvtsi128_si32((__m128i)*(unsigned __int64 *)g_pfnResultFromCaughtExceptionInternal(
                                                           v12,
                                                           a8 + 2 * v8,
                                                           2048 - v8,
                                                           v13)) < 0 )
      wil::details::ReportFailure_Base<3,0>(
        a2,
        394,
        (unsigned int)"onecore\\vm\\dv\\storage\\plan9\\dll\\p9await.h",
        v10);
  }
  wil::details::HrToNtStatus((wil::details *)0x8007023ELL, a2);
  wil::details::ReportFailure_Base<3,0>(a2, 394, (unsigned int)"onecore\\vm\\dv\\storage\\plan9\\dll\\p9await.h", v11);
}

```

## disassembly

```asm
0x18000d058  push    rbx
0x18000d05a  push    rbp
0x18000d05b  push    rsi
0x18000d05c  push    rdi
0x18000d05d  sub     rsp, 88h
0x18000d064  mov     rsi, [rsp+0A8h+arg_30]
0x18000d06c  xor     ebp, ebp
0x18000d06e  mov     rbx, [rsp+0A8h+arg_38]
0x18000d076  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000d07a  mov     [rsp+0A8h+var_38], bpl
0x18000d07f  mov     rdi, rdx
0x18000d082  inc     rcx
0x18000d085  cmp     [rbx+rcx*2], bp
0x18000d089  jnz     short loc_18000D082
0x18000d08b  mov     rax, cs:g_pfnResultFromCaughtExceptionInternal
0x18000d092  test    rax, rax
0x18000d095  jz      short loc_18000D0F5
0x18000d097  lea     rdx, [rbx+rcx*2]
0x18000d09b  mov     r8d, 800h
0x18000d0a1  sub     r8, rcx
0x18000d0a4  lea     r9, [rsp+0A8h+var_38]
0x18000d0a9  lea     rcx, [rsp+0A8h+var_48]
0x18000d0ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d0b3  movsd   xmm0, qword ptr [rax]
0x18000d0b7  mov     eax, [rax+8]
0x18000d0ba  mov     [rsp+0A8h+var_50], eax
0x18000d0be  movd    eax, xmm0
0x18000d0c2  movsd   [rsp+0A8h+var_58], xmm0
0x18000d0c8  test    eax, eax
0x18000d0ca  jns     short loc_18000D0F5
0x18000d0cc  lea     rax, [rsp+0A8h+var_58]
0x18000d0d1  mov     [rsp+0A8h+var_70], rbx
0x18000d0d6  mov     [rsp+0A8h+var_78], rax
0x18000d0db  lea     r8, aOnecoreVmDvSto_1; "onecore\\vm\\dv\\storage\\plan9\\dll\\p"...
0x18000d0e2  mov     edx, 18Ah
0x18000d0e7  mov     [rsp+0A8h+var_80], rsi
0x18000d0ec  mov     rcx, rdi
0x18000d0ef  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x18000d0f5  mov     ecx, 8007023Eh; this
0x18000d0fa  mov     dword ptr [rsp+0A8h+var_58], ecx
0x18000d0fe  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000d103  mov     dword ptr [rsp+0A8h+var_58+4], eax
0x18000d107  lea     r8, aOnecoreVmDvSto_1; "onecore\\vm\\dv\\storage\\plan9\\dll\\p"...
0x18000d10e  lea     rax, [rsp+0A8h+var_58]
0x18000d113  mov     [rsp+0A8h+var_70], rbx
0x18000d118  mov     [rsp+0A8h+var_78], rax
0x18000d11d  mov     edx, 18Ah
0x18000d122  mov     rcx, rdi
0x18000d125  mov     [rsp+0A8h+var_80], rsi
0x18000d12a  mov     [rsp+0A8h+var_50], ebp
0x18000d12e  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
