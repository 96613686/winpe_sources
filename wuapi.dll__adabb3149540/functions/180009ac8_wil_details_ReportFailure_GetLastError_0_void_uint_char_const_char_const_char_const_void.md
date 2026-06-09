# wil::details::ReportFailure_GetLastError<0>(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x180009ac8`
- end: `0x180009b49`
- name: `??$ReportFailure_GetLastError@$0A@@details@wil@@YAKPEAXIPEBD110@Z`
- size: `129`
- prototype: `void __fastcall __noreturn(int, int, int, int, int, char *)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x180009b50`

## callees

- `0x180002130`
- `0x180002748`
- `0x18000a99c`

## string_xrefs

- `0x180009ada`: `C:\__w\1\s\src\inc\UndockedUpdateStack.hpp`
- `0x180009b14`: `C:\__w\1\s\src\inc\UndockedUpdateStack.hpp`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_GetLastError<0>(
        wil::details *a1,
        __int64 a2,
        __int64 a3,
        const char *a4,
        int a5,
        char *a6)
{
  int v6; // edi
  int LastErrorFail; // eax
  __int64 v8; // rdx
  __int64 v9; // rax
  __int64 v10; // xmm0_8
  int v11; // r9d
  const char *v12; // [rsp+20h] [rbp-58h]
  int v13; // [rsp+20h] [rbp-58h]
  void *v14; // [rsp+30h] [rbp-48h]
  __int64 v15; // [rsp+50h] [rbp-28h] BYREF
  int v16; // [rsp+58h] [rbp-20h]
  _BYTE v17[24]; // [rsp+60h] [rbp-18h] BYREF

  v6 = (int)a1;
  LastErrorFail = wil::details::GetLastErrorFail(
                    a1,
                    (void *)0x173,
                    (unsigned int)"C:\\__w\\1\\s\\src\\inc\\UndockedUpdateStack.hpp",
                    a4,
                    v12,
                    a6,
                    v14);
  v8 = (unsigned __int16)LastErrorFail | 0x80070000;
  if ( LastErrorFail <= 0 )
    v8 = (unsigned int)LastErrorFail;
  v9 = wil::details::ResultStatus::FromResult(v17, v8);
  v10 = *(_QWORD *)v9;
  v16 = *(_DWORD *)(v9 + 8);
  v15 = v10;
  wil::details::ReportFailure_Base<0,0>(
    v6,
    371,
    (unsigned int)"C:\\__w\\1\\s\\src\\inc\\UndockedUpdateStack.hpp",
    v11,
    v13,
    (__int64)a6,
    (__int64)&v15,
    0);
}

```

## disassembly

```asm
0x180009ac8  mov     [rsp+arg_0], rbx
0x180009acd  push    rdi
0x180009ace  sub     rsp, 70h
0x180009ad2  mov     rbx, [rsp+78h+arg_28]
0x180009ada  lea     r8, aCW1SSrcIncUndo; "C:\\__w\\1\\s\\src\\inc\\UndockedUpdate"...
0x180009ae1  mov     edx, 173h; void *
0x180009ae6  mov     [rsp+78h+var_50], rbx; char *
0x180009aeb  mov     rdi, rcx
0x180009aee  call    ?GetLastErrorFail@details@wil@@YAKPEAXIPEBD110@Z; wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)
0x180009af3  movzx   edx, ax
0x180009af6  lea     rcx, [rsp+78h+var_18]
0x180009afb  or      edx, 80070000h
0x180009b01  test    eax, eax
0x180009b03  cmovle  edx, eax
0x180009b06  call    ?FromResult@ResultStatus@details@wil@@SA?AU123@J@Z; wil::details::ResultStatus::FromResult(long)
0x180009b0b  mov     [rsp+78h+var_40], 0
0x180009b14  lea     r8, aCW1SSrcIncUndo; "C:\\__w\\1\\s\\src\\inc\\UndockedUpdate"...
0x180009b1b  mov     edx, 173h
0x180009b20  mov     rcx, rdi
0x180009b23  movsd   xmm0, qword ptr [rax]
0x180009b27  mov     eax, [rax+8]
0x180009b2a  mov     [rsp+78h+var_20], eax
0x180009b2e  lea     rax, [rsp+78h+var_28]
0x180009b33  mov     [rsp+78h+var_48], rax
0x180009b38  mov     [rsp+78h+var_50], rbx
0x180009b3d  movsd   [rsp+78h+var_28], xmm0
0x180009b43  call    ??$ReportFailure_Base@$0A@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<0,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
