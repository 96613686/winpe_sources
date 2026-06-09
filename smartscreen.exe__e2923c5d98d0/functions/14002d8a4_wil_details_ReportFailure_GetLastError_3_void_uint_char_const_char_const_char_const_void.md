# wil::details::ReportFailure_GetLastError<3>(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x14002d8a4`
- end: `0x14002d915`
- name: `??$ReportFailure_GetLastError@$02@details@wil@@YAKPEAXIPEBD110@Z`
- size: `113`
- prototype: `void __fastcall __noreturn(int, int, int, int, int, char *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x14002e5d0`

## callees

- `0x14000d430`
- `0x1400172c4`
- `0x14002d878`
- `0x14002d8a4`

## string_xrefs

- `0x14002d8bb`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`
- `0x14002d8ec`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_GetLastError<3>(
        wil::details *a1,
        void *a2,
        __int64 a3,
        const char *a4,
        int a5,
        char *a6)
{
  int v6; // ebx
  int v7; // edi
  signed int LastErrorFail; // eax
  int v9; // edx
  int v10; // r9d
  const char *v11; // [rsp+20h] [rbp-48h]
  int v12; // [rsp+20h] [rbp-48h]
  void *v13; // [rsp+30h] [rbp-38h]
  _DWORD v14[6]; // [rsp+50h] [rbp-18h] BYREF

  v6 = (int)a2;
  v7 = (int)a1;
  LastErrorFail = wil::details::GetLastErrorFail(
                    a1,
                    a2,
                    (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
                    a4,
                    v11,
                    a6,
                    v13);
  if ( LastErrorFail > 0 )
    LastErrorFail = (unsigned __int16)LastErrorFail | 0x80070000;
  v14[0] = LastErrorFail;
  v14[1] = wil::details::HrToNtStatus((wil::details *)(unsigned int)LastErrorFail, v9);
  v14[2] = 0;
  wil::details::ReportFailure_Base<3,0>(
    v7,
    v6,
    (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
    v10,
    v12,
    (__int64)a6,
    (__int64)v14);
}

```

## disassembly

```asm
0x14002d8a4  mov     [rsp+arg_0], rbx
0x14002d8a9  mov     [rsp+arg_8], rsi
0x14002d8ae  push    rdi
0x14002d8af  sub     rsp, 60h
0x14002d8b3  mov     rsi, [rsp+68h+arg_28]
0x14002d8bb  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x14002d8c2  mov     [rsp+68h+var_40], rsi; char *
0x14002d8c7  mov     ebx, edx
0x14002d8c9  mov     rdi, rcx
0x14002d8cc  call    ?GetLastErrorFail@details@wil@@YAKPEAXIPEBD110@Z; wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)
0x14002d8d1  test    eax, eax
0x14002d8d3  jle     short loc_14002D8DD
0x14002d8d5  movzx   eax, ax
0x14002d8d8  or      eax, 80070000h
0x14002d8dd  mov     ecx, eax; this
0x14002d8df  mov     [rsp+68h+var_18], eax
0x14002d8e3  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x14002d8e8  mov     [rsp+68h+var_14], eax
0x14002d8ec  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x14002d8f3  lea     rax, [rsp+68h+var_18]
0x14002d8f8  mov     [rsp+68h+var_10], 0
0x14002d900  mov     [rsp+68h+var_38], rax
0x14002d905  mov     edx, ebx
0x14002d907  mov     rcx, rdi
0x14002d90a  mov     [rsp+68h+var_40], rsi
0x14002d90f  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
