# FusionpTraceWin32FailureNoFormatting(_FRAME_INFO const &,ulong,char const *)

- ea: `0x180067800`
- end: `0x180067944`
- name: `?FusionpTraceWin32FailureNoFormatting@@YAXAEBU_FRAME_INFO@@KPEBD@Z`
- size: `324`
- prototype: `void(const struct _FRAME_INFO *, unsigned int, const char *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18006794c`

## callees

- `0x18000c000`
- `0x180059760`
- `0x180067800`
- `0x18006a110`

## import_xrefs

- `ntdll!_snprintf_s` at `0x1800678a9`
- `ntdll!_snprintf_s` at `0x1800678a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180067828`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180067828`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180067919`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180067919`
- `api-ms-win-core-localization-l1-2-0!FormatMessageA` at `0x18006787c`
- `api-ms-win-core-localization-l1-2-0!FormatMessageA` at `0x18006787c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180067836`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180067836`

## pseudocode

```c
void __fastcall FusionpTraceWin32FailureNoFormatting(const struct _FRAME_INFO *a1, DWORD a2, const char *a3)
{
  DWORD LastError; // ebp
  DWORD CurrentThreadId; // r14d
  const char *v8; // rdx
  UNICODE_STRING SearchString; // [rsp+60h] [rbp-C8h] BYREF
  CHAR Buffer[128]; // [rsp+70h] [rbp-B8h] BYREF

  LastError = GetLastError();
  CurrentThreadId = GetCurrentThreadId();
  FusionpGetProcessImageFileName(&SearchString);
  Buffer[0] = 0;
  if ( !FormatMessageA(0x10FFu, 0, a2, 0, Buffer, 0x80u, 0) )
  {
    _snprintf_s(Buffer, 0x80u, 0x7Fu, "<Untranslatable Win32 status %d (0x%08lx)>", a2, a2);
    Buffer[127] = 0;
  }
  v8 = "%s(%lu): [function %s %Iubit process %wZ tid 0x%lx] Win32 Error %d (%s) %s\n";
  if ( !a3 )
    v8 = "%s(%lu): [function %s %Iubit process %wZ tid 0x%lx] Win32 Error %d (%s)\n";
  FusionpDbgPrintEx(
    0x80000010,
    v8,
    *(_QWORD *)a1,
    *((unsigned int *)a1 + 4),
    *((_QWORD *)a1 + 1),
    64,
    &SearchString,
    CurrentThreadId,
    a2,
    Buffer,
    a3);
  SetLastError(LastError);
}

```

## disassembly

```asm
0x180067800  push    rbx
0x180067802  push    rbp
0x180067803  push    rsi
0x180067804  push    rdi
0x180067805  push    r14
0x180067807  sub     rsp, 100h
0x18006780e  mov     rax, cs:__security_cookie
0x180067815  xor     rax, rsp
0x180067818  mov     [rsp+128h+var_38], rax
0x180067820  mov     rsi, r8
0x180067823  mov     ebx, edx
0x180067825  mov     rdi, rcx
0x180067828  call    cs:__imp_GetLastError
0x18006782f  nop     dword ptr [rax+rax+00h]
0x180067834  mov     ebp, eax
0x180067836  call    cs:__imp_GetCurrentThreadId
0x18006783d  nop     dword ptr [rax+rax+00h]
0x180067842  lea     rcx, [rsp+128h+SearchString]; SearchString
0x180067847  mov     r14d, eax
0x18006784a  call    ?FusionpGetProcessImageFileName@@YAXPEAU_UNICODE_STRING@@@Z; FusionpGetProcessImageFileName(_UNICODE_STRING *)
0x18006784f  lea     rax, [rsp+128h+Buffer]
0x180067854  mov     [rsp+128h+Arguments], 0; Arguments
0x18006785d  mov     [rsp+128h+nSize], 80h; nSize
0x180067865  xor     r9d, r9d; dwLanguageId
0x180067868  mov     r8d, ebx; dwMessageId
0x18006786b  mov     [rsp+128h+lpBuffer], rax; lpBuffer
0x180067870  xor     edx, edx; lpSource
0x180067872  mov     [rsp+128h+Buffer], 0
0x180067877  mov     ecx, 10FFh; dwFlags
0x18006787c  call    cs:__imp_FormatMessageA
0x180067883  nop     dword ptr [rax+rax+00h]
0x180067888  test    eax, eax
0x18006788a  jnz     short loc_1800678BD
0x18006788c  mov     [rsp+128h+nSize], ebx
0x180067890  lea     r9, aUntranslatable; "<Untranslatable Win32 status %d (0x%08l"...
0x180067897  mov     edx, 80h; BufferCount
0x18006789c  mov     dword ptr [rsp+128h+lpBuffer], ebx
0x1800678a0  lea     r8d, [rax+7Fh]; MaxCount
0x1800678a4  lea     rcx, [rsp+128h+Buffer]; Buffer
0x1800678a9  call    cs:__imp__snprintf_s
0x1800678b0  nop     dword ptr [rax+rax+00h]
0x1800678b5  mov     [rsp+128h+var_39], 0
0x1800678bd  mov     r9d, [rdi+10h]
0x1800678c1  lea     rax, aSLuFunctionSIu; "%s(%lu): [function %s %Iubit process %w"...
0x1800678c8  mov     r8, [rdi]
0x1800678cb  lea     rdx, aSLuFunctionSIu_2; "%s(%lu): [function %s %Iubit process %w"...
0x1800678d2  mov     [rsp+128h+var_D8], rsi
0x1800678d7  test    rsi, rsi
0x1800678da  mov     ecx, 80000010h; unsigned int
0x1800678df  cmovz   rdx, rax; char *
0x1800678e3  lea     rax, [rsp+128h+Buffer]
0x1800678e8  mov     [rsp+128h+var_E0], rax
0x1800678ed  lea     rax, [rsp+128h+SearchString]
0x1800678f2  mov     [rsp+128h+var_E8], ebx
0x1800678f6  mov     [rsp+128h+var_F0], r14d
0x1800678fb  mov     [rsp+128h+Arguments], rax
0x180067900  mov     rax, [rdi+8]
0x180067904  mov     qword ptr [rsp+128h+nSize], 40h ; '@'
0x18006790d  mov     [rsp+128h+lpBuffer], rax
0x180067912  call    ?FusionpDbgPrintEx@@YAKKPEBDZZ; FusionpDbgPrintEx(ulong,char const *,...)
0x180067917  mov     ecx, ebp; dwErrCode
0x180067919  call    cs:__imp_SetLastError
0x180067920  nop     dword ptr [rax+rax+00h]
0x180067925  mov     rcx, [rsp+128h+var_38]
0x18006792d  xor     rcx, rsp; StackCookie
0x180067930  call    __security_check_cookie
0x180067935  add     rsp, 100h
0x18006793c  pop     r14
0x18006793e  pop     rdi
0x18006793f  pop     rsi
0x180067940  pop     rbp
0x180067941  pop     rbx
0x180067942  retn
```
