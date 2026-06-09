# wil::details::ReportFailure_GetLastError<2>(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x18001c8bc`
- end: `0x18001c95b`
- name: `??$ReportFailure_GetLastError@$01@details@wil@@YAKPEAXIPEBD110@Z`
- size: `159`
- prototype: `__int64 __fastcall(wil::details *, __int64, __int64, const char *, int, char *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x180022184`

## callees

- `0x18001a1f8`
- `0x18001a3bc`
- `0x18001c840`
- `0x18001c8bc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001c943`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001c943`

## string_xrefs

- `0x18001c8d3`: `shell\services\hdsrv\shsrvice\shsrvice.cpp`
- `0x18001c90e`: `shell\services\hdsrv\shsrvice\shsrvice.cpp`

## pseudocode

```c
__int64 __fastcall wil::details::ReportFailure_GetLastError<2>(
        wil::details *a1,
        __int64 a2,
        __int64 a3,
        const char *a4,
        int a5,
        char *a6)
{
  int v6; // edi
  int LastErrorFail; // eax
  DWORD v8; // ebx
  unsigned __int64 v9; // rcx
  __int64 v10; // rdx
  const char *v12; // [rsp+20h] [rbp-48h]
  void *v13; // [rsp+30h] [rbp-38h]
  _DWORD v14[6]; // [rsp+50h] [rbp-18h] BYREF

  v6 = (int)a1;
  LastErrorFail = wil::details::GetLastErrorFail(
                    a1,
                    (void *)0x43F,
                    (unsigned int)"shell\\services\\hdsrv\\shsrvice\\shsrvice.cpp",
                    a4,
                    v12,
                    a6,
                    v13);
  v8 = LastErrorFail;
  if ( LastErrorFail > 0 )
    v9 = (unsigned __int16)LastErrorFail | 0x80070000;
  else
    v9 = (unsigned int)LastErrorFail;
  v14[0] = v9;
  v14[1] = wil::details::HrToNtStatus((wil::details *)v9, 0);
  v14[2] = v10;
  wil::details::ReportFailure_Base<2,0>(
    v6,
    1087,
    (unsigned int)"shell\\services\\hdsrv\\shsrvice\\shsrvice.cpp",
    0,
    v10,
    (__int64)a6,
    (__int64)v14);
  SetLastError(v8);
  return v8;
}

```

## disassembly

```asm
0x18001c8bc  mov     [rsp+arg_0], rbx
0x18001c8c1  mov     [rsp+arg_8], rsi
0x18001c8c6  push    rdi
0x18001c8c7  sub     rsp, 60h
0x18001c8cb  mov     rsi, [rsp+68h+arg_28]
0x18001c8d3  lea     r8, aShellServicesH; "shell\\services\\hdsrv\\shsrvice\\shsrv"...
0x18001c8da  mov     edx, 43Fh; void *
0x18001c8df  mov     [rsp+68h+var_40], rsi; char *
0x18001c8e4  mov     rdi, rcx
0x18001c8e7  call    ?GetLastErrorFail@details@wil@@YAKPEAXIPEBD110@Z; wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)
0x18001c8ec  xor     edx, edx; int
0x18001c8ee  mov     ebx, eax
0x18001c8f0  test    eax, eax
0x18001c8f2  jg      short loc_18001C8F8
0x18001c8f4  mov     ecx, eax
0x18001c8f6  jmp     short loc_18001C901
0x18001c8f8  movzx   ecx, bx
0x18001c8fb  or      ecx, 80070000h; this
0x18001c901  mov     [rsp+68h+var_18], ecx
0x18001c905  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18001c90a  mov     [rsp+68h+var_20], edx
0x18001c90e  lea     r8, aShellServicesH; "shell\\services\\hdsrv\\shsrvice\\shsrv"...
0x18001c915  mov     [rsp+68h+var_14], eax
0x18001c919  xor     r9d, r9d
0x18001c91c  lea     rax, [rsp+68h+var_18]
0x18001c921  mov     [rsp+68h+var_10], edx
0x18001c925  mov     [rsp+68h+var_38], rax
0x18001c92a  mov     rcx, rdi
0x18001c92d  mov     [rsp+68h+var_40], rsi
0x18001c932  mov     [rsp+68h+var_48], rdx
0x18001c937  mov     edx, 43Fh
0x18001c93c  call    ??$ReportFailure_Base@$01$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<2,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x18001c941  mov     ecx, ebx; dwErrCode
0x18001c943  call    cs:__imp_SetLastError
0x18001c949  mov     rsi, [rsp+68h+arg_8]
0x18001c94e  mov     eax, ebx
0x18001c950  mov     rbx, [rsp+68h+arg_0]
0x18001c955  add     rsp, 60h
0x18001c959  pop     rdi
0x18001c95a  retn
```
