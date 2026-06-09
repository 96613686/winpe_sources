# wil::details::ReportFailure_GetLastError<2>(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x180027c5c`
- end: `0x180027d31`
- name: `??$ReportFailure_GetLastError@$01@details@wil@@YAKPEAXIPEBD110@Z`
- size: `213`
- prototype: `__int64 __fastcall(int, __int64, __int64, __int64, int, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x180028538`

## callees

- `0x180003a58`
- `0x180003c64`
- `0x180006c4c`
- `0x180027c5c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027c6e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027c6e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180027d19`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180027d19`

## string_xrefs

- `0x180027c9b`: `onecoreuap\net\tethering\service\userutils.cpp`
- `0x180027d04`: `onecoreuap\net\tethering\service\userutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall wil::details::ReportFailure_GetLastError<2>(
        int a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6)
{
  int v7; // edx
  int LastError; // ebx
  unsigned __int64 v9; // rcx
  wil::details *v11; // [rsp+30h] [rbp-38h]
  _DWORD v12[6]; // [rsp+50h] [rbp-18h] BYREF

  LastError = GetLastError();
  if ( !LastError )
  {
    LODWORD(v11) = -2147024228;
    wil::details::ReportFailure_Hr<2>(a1, 39, (int)"onecoreuap\\net\\tethering\\service\\userutils.cpp", 0, 0, a6, v11);
    LastError = 668;
  }
  if ( LastError > 0 )
    v9 = (unsigned __int16)LastError | 0x80070000;
  else
    v9 = (unsigned int)LastError;
  v12[0] = v9;
  v12[1] = wil::details::HrToNtStatus((wil::details *)v9, v7);
  v12[2] = 0;
  wil::details::ReportFailure_Base<2,0>(
    a1,
    39,
    (unsigned int)"onecoreuap\\net\\tethering\\service\\userutils.cpp",
    0,
    0,
    a6,
    (__int64)v12,
    0);
  SetLastError(LastError);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x180027c5c  mov     [rsp+arg_0], rbx
0x180027c61  mov     [rsp+arg_8], rsi
0x180027c66  push    rdi
0x180027c67  sub     rsp, 60h
0x180027c6b  mov     rdi, rcx
0x180027c6e  call    cs:__imp_GetLastError
0x180027c74  mov     ebx, eax
0x180027c76  mov     rsi, [rsp+68h+arg_28]
0x180027c7e  test    eax, eax
0x180027c80  jnz     short loc_180027CB2
0x180027c82  mov     dword ptr [rsp+68h+var_38], 8007029Ch; wil::details *
0x180027c8a  mov     [rsp+68h+var_40], rsi; __int64
0x180027c8f  mov     [rsp+68h+var_48], 0; __int64
0x180027c98  xor     r9d, r9d; int
0x180027c9b  lea     r8, aOnecoreuapNetT_1; "onecoreuap\\net\\tethering\\service\\us"...
0x180027ca2  lea     edx, [rax+27h]; int
0x180027ca5  mov     rcx, rdi; int
0x180027ca8  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180027cad  mov     ebx, 29Ch
0x180027cb2  test    ebx, ebx
0x180027cb4  jg      short loc_180027CBA
0x180027cb6  mov     ecx, ebx
0x180027cb8  jmp     short loc_180027CC3
0x180027cba  movzx   ecx, bx
0x180027cbd  or      ecx, 80070000h; this
0x180027cc3  mov     [rsp+68h+var_18], ecx
0x180027cc7  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180027ccc  mov     [rsp+68h+var_14], eax
0x180027cd0  mov     [rsp+68h+var_10], 0
0x180027cd8  mov     [rsp+68h+var_20], 0
0x180027ce0  mov     [rsp+68h+var_30], 0
0x180027ce9  lea     rax, [rsp+68h+var_18]
0x180027cee  mov     [rsp+68h+var_38], rax
0x180027cf3  mov     [rsp+68h+var_40], rsi
0x180027cf8  mov     [rsp+68h+var_48], 0
0x180027d01  xor     r9d, r9d
0x180027d04  lea     r8, aOnecoreuapNetT_1; "onecoreuap\\net\\tethering\\service\\us"...
0x180027d0b  lea     edx, [r9+27h]
0x180027d0f  mov     rcx, rdi
0x180027d12  call    ??$ReportFailure_Base@$01$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<2,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x180027d17  mov     ecx, ebx; dwErrCode
0x180027d19  call    cs:__imp_SetLastError
0x180027d1f  mov     eax, ebx
0x180027d21  mov     rbx, [rsp+68h+arg_0]
0x180027d26  mov     rsi, [rsp+68h+arg_8]
0x180027d2b  add     rsp, 60h
0x180027d2f  pop     rdi
0x180027d30  retn
```
