# FusionpTraceWin32LastErrorFailureOrigination(_CALL_SITE_INFO const &)

- ea: `0x18000a804`
- end: `0x18000a94f`
- name: `?FusionpTraceWin32LastErrorFailureOrigination@@YAXAEBU_CALL_SITE_INFO@@@Z`
- size: `331`
- prototype: `void __fastcall(const struct _CALL_SITE_INFO *)`
- caller_count: `93`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180005f60`
- `0x180007b10`
- `0x180007e10`
- `0x180009170`
- `0x180009640`
- `0x180009a00`
- `0x18000a960`
- `0x18000bc20`
- `0x18000cd10`
- `0x18000f170`
- `0x180011de0`
- `0x1800135f0`
- `0x180015a80`
- `0x180016870`
- `0x180019740`
- `0x180019cc0`
- `0x18001b1f0`
- `0x18001d988`
- `0x18001db00`
- `0x180021150`
- `0x180023ee0`
- `0x180025e00`
- `0x1800265b0`
- `0x180026a60`
- `0x180027160`
- `0x180029a30`
- `0x18002aa40`
- `0x18002bdb4`
- `0x18002c5b0`
- `0x18002c760`
- `0x18002cc78`
- `0x18002d6ec`
- `0x18002d908`
- `0x18002da50`
- `0x18002ee20`
- `0x180030950`
- `0x180031260`
- `0x180036b18`
- `0x18003ecc8`
- `0x18003f060`
- `0x180040050`
- `0x180040a30`
- `0x1800419e4`
- `0x1800434a0`
- `0x180044820`
- `0x1800458b0`
- `0x1800479c0`
- `0x1800489f0`
- `0x180049590`
- `0x18004a060`

## callees

- `0x18000a804`
- `0x18000c000`
- `0x180059760`
- `0x18006a110`

## import_xrefs

- `ntdll!_snprintf_s` at `0x18000a8b3`
- `ntdll!_snprintf_s` at `0x18000a8b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a825`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a841`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a825`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a841`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a926`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a926`
- `api-ms-win-core-localization-l1-2-0!FormatMessageA` at `0x18000a886`
- `api-ms-win-core-localization-l1-2-0!FormatMessageA` at `0x18000a886`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a833`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a833`

## pseudocode

```c
void __fastcall FusionpTraceWin32LastErrorFailureOrigination(const struct _CALL_SITE_INFO *a1)
{
  DWORD LastError; // esi
  DWORD CurrentThreadId; // ebp
  DWORD v4; // ebx
  const char *v5; // rdx
  UNICODE_STRING SearchString; // [rsp+60h] [rbp-C8h] BYREF
  CHAR Buffer[128]; // [rsp+70h] [rbp-B8h] BYREF

  LastError = GetLastError();
  CurrentThreadId = GetCurrentThreadId();
  v4 = GetLastError();
  FusionpGetProcessImageFileName(&SearchString);
  Buffer[0] = 0;
  if ( !FormatMessageA(0x10FFu, 0, v4, 0, Buffer, 0x80u, 0) )
  {
    _snprintf_s(Buffer, 0x80u, 0x7Fu, "<Untranslatable Win32 status %d (0x%08lx)>", v4, v4);
    Buffer[127] = 0;
  }
  v5 = "%s(%lu): [function %s %Iubit process %wZ tid 0x%lx] Win32 Error %d (%s) %s\n";
  if ( !*((_QWORD *)a1 + 2) )
    v5 = "%s(%lu): [function %s %Iubit process %wZ tid 0x%lx] Win32 Error %d (%s)\n";
  FusionpDbgPrintEx(
    0xC0000000,
    v5,
    *(_QWORD *)a1,
    *((unsigned int *)a1 + 6),
    *((_QWORD *)a1 + 1),
    64,
    &SearchString,
    CurrentThreadId,
    v4,
    Buffer,
    *((_QWORD *)a1 + 2));
  SetLastError(LastError);
}

```

## disassembly

```asm
0x18000a804  push    rbx
0x18000a806  push    rbp
0x18000a807  push    rsi
0x18000a808  push    rdi
0x18000a809  sub     rsp, 108h
0x18000a810  mov     rax, cs:__security_cookie
0x18000a817  xor     rax, rsp
0x18000a81a  mov     [rsp+128h+var_38], rax
0x18000a822  mov     rdi, rcx
0x18000a825  call    cs:__imp_GetLastError
0x18000a82c  nop     dword ptr [rax+rax+00h]
0x18000a831  mov     esi, eax
0x18000a833  call    cs:__imp_GetCurrentThreadId
0x18000a83a  nop     dword ptr [rax+rax+00h]
0x18000a83f  mov     ebp, eax
0x18000a841  call    cs:__imp_GetLastError
0x18000a848  nop     dword ptr [rax+rax+00h]
0x18000a84d  lea     rcx, [rsp+128h+SearchString]; SearchString
0x18000a852  mov     ebx, eax
0x18000a854  call    ?FusionpGetProcessImageFileName@@YAXPEAU_UNICODE_STRING@@@Z; FusionpGetProcessImageFileName(_UNICODE_STRING *)
0x18000a859  lea     rax, [rsp+128h+Buffer]
0x18000a85e  mov     [rsp+128h+Arguments], 0; Arguments
0x18000a867  mov     [rsp+128h+nSize], 80h; nSize
0x18000a86f  xor     r9d, r9d; dwLanguageId
0x18000a872  mov     r8d, ebx; dwMessageId
0x18000a875  mov     [rsp+128h+lpBuffer], rax; lpBuffer
0x18000a87a  xor     edx, edx; lpSource
0x18000a87c  mov     [rsp+128h+Buffer], 0
0x18000a881  mov     ecx, 10FFh; dwFlags
0x18000a886  call    cs:__imp_FormatMessageA
0x18000a88d  nop     dword ptr [rax+rax+00h]
0x18000a892  test    eax, eax
0x18000a894  jnz     short loc_18000A8C7
0x18000a896  mov     [rsp+128h+nSize], ebx
0x18000a89a  lea     r9, aUntranslatable; "<Untranslatable Win32 status %d (0x%08l"...
0x18000a8a1  mov     edx, 80h; BufferCount
0x18000a8a6  mov     dword ptr [rsp+128h+lpBuffer], ebx
0x18000a8aa  lea     r8d, [rax+7Fh]; MaxCount
0x18000a8ae  lea     rcx, [rsp+128h+Buffer]; Buffer
0x18000a8b3  call    cs:__imp__snprintf_s
0x18000a8ba  nop     dword ptr [rax+rax+00h]
0x18000a8bf  mov     [rsp+128h+var_39], 0
0x18000a8c7  mov     rax, [rdi+10h]
0x18000a8cb  lea     rcx, aSLuFunctionSIu; "%s(%lu): [function %s %Iubit process %w"...
0x18000a8d2  mov     r9d, [rdi+18h]
0x18000a8d6  lea     rdx, aSLuFunctionSIu_2; "%s(%lu): [function %s %Iubit process %w"...
0x18000a8dd  mov     r8, [rdi]
0x18000a8e0  test    rax, rax
0x18000a8e3  mov     [rsp+128h+var_D8], rax
0x18000a8e8  lea     rax, [rsp+128h+Buffer]
0x18000a8ed  mov     [rsp+128h+var_E0], rax
0x18000a8f2  cmovz   rdx, rcx; char *
0x18000a8f6  mov     [rsp+128h+var_E8], ebx
0x18000a8fa  lea     rax, [rsp+128h+SearchString]
0x18000a8ff  mov     [rsp+128h+var_F0], ebp
0x18000a903  mov     ecx, 0C0000000h; unsigned int
0x18000a908  mov     [rsp+128h+Arguments], rax
0x18000a90d  mov     rax, [rdi+8]
0x18000a911  mov     qword ptr [rsp+128h+nSize], 40h ; '@'
0x18000a91a  mov     [rsp+128h+lpBuffer], rax
0x18000a91f  call    ?FusionpDbgPrintEx@@YAKKPEBDZZ; FusionpDbgPrintEx(ulong,char const *,...)
0x18000a924  mov     ecx, esi; dwErrCode
0x18000a926  call    cs:__imp_SetLastError
0x18000a92d  nop     dword ptr [rax+rax+00h]
0x18000a932  mov     rcx, [rsp+128h+var_38]
0x18000a93a  xor     rcx, rsp; StackCookie
0x18000a93d  call    __security_check_cookie
0x18000a942  add     rsp, 108h
0x18000a949  pop     rdi
0x18000a94a  pop     rsi
0x18000a94b  pop     rbp
0x18000a94c  pop     rbx
0x18000a94d  retn
```
