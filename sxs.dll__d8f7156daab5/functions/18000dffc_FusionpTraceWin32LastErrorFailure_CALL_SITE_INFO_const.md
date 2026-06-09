# FusionpTraceWin32LastErrorFailure(_CALL_SITE_INFO const &)

- ea: `0x18000dffc`
- end: `0x18000e150`
- name: `?FusionpTraceWin32LastErrorFailure@@YAXAEBU_CALL_SITE_INFO@@@Z`
- size: `340`
- prototype: `void __fastcall(const struct _CALL_SITE_INFO *)`
- caller_count: `244`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800011f0`
- `0x1800017b8`
- `0x180001fe0`
- `0x180002a70`
- `0x180005338`
- `0x1800055c0`
- `0x1800057e0`
- `0x1800059d0`
- `0x180005f60`
- `0x1800075c0`
- `0x1800077b0`
- `0x180007b10`
- `0x180007e10`
- `0x180008a80`
- `0x180009170`
- `0x180009640`
- `0x180009f00`
- `0x18000a960`
- `0x18000bc20`
- `0x18000c070`
- `0x18000c820`
- `0x18000cd10`
- `0x18000d4d0`
- `0x18000e160`
- `0x18000f170`
- `0x180010bd0`
- `0x180010e20`
- `0x180011170`
- `0x180011580`
- `0x180011de0`
- `0x1800131e0`
- `0x1800135f0`
- `0x180013af0`
- `0x1800143e0`
- `0x180015088`
- `0x180015518`
- `0x1800156d0`
- `0x180015a80`
- `0x180016870`
- `0x180017760`
- `0x180017910`
- `0x180017bc0`
- `0x180017dc0`
- `0x180019cc0`
- `0x18001b1f0`
- `0x18001be10`
- `0x18001c320`
- `0x18001d6f0`
- `0x18001db00`
- `0x18001f2c0`

## callees

- `0x18000c000`
- `0x18000dffc`
- `0x180059760`
- `0x18006a110`

## import_xrefs

- `ntdll!_snprintf_s` at `0x18000e137`
- `ntdll!_snprintf_s` at `0x18000e137`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e01d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e039`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e01d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e039`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e0f1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e0f1`
- `api-ms-win-core-localization-l1-2-0!FormatMessageA` at `0x18000e07e`
- `api-ms-win-core-localization-l1-2-0!FormatMessageA` at `0x18000e07e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e02b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e02b`

## pseudocode

```c
void __fastcall FusionpTraceWin32LastErrorFailure(const struct _CALL_SITE_INFO *a1)
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
    0x80000010,
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
0x18000dffc  push    rbx
0x18000dffe  push    rbp
0x18000dfff  push    rsi
0x18000e000  push    rdi
0x18000e001  sub     rsp, 108h
0x18000e008  mov     rax, cs:__security_cookie
0x18000e00f  xor     rax, rsp
0x18000e012  mov     [rsp+128h+var_38], rax
0x18000e01a  mov     rdi, rcx
0x18000e01d  call    cs:__imp_GetLastError
0x18000e024  nop     dword ptr [rax+rax+00h]
0x18000e029  mov     esi, eax
0x18000e02b  call    cs:__imp_GetCurrentThreadId
0x18000e032  nop     dword ptr [rax+rax+00h]
0x18000e037  mov     ebp, eax
0x18000e039  call    cs:__imp_GetLastError
0x18000e040  nop     dword ptr [rax+rax+00h]
0x18000e045  lea     rcx, [rsp+128h+SearchString]; SearchString
0x18000e04a  mov     ebx, eax
0x18000e04c  call    ?FusionpGetProcessImageFileName@@YAXPEAU_UNICODE_STRING@@@Z; FusionpGetProcessImageFileName(_UNICODE_STRING *)
0x18000e051  lea     rax, [rsp+128h+Buffer]
0x18000e056  mov     [rsp+128h+Arguments], 0; Arguments
0x18000e05f  mov     [rsp+128h+nSize], 80h; nSize
0x18000e067  xor     r9d, r9d; dwLanguageId
0x18000e06a  mov     r8d, ebx; dwMessageId
0x18000e06d  mov     [rsp+128h+lpBuffer], rax; lpBuffer
0x18000e072  xor     edx, edx; lpSource
0x18000e074  mov     [rsp+128h+Buffer], 0
0x18000e079  mov     ecx, 10FFh; dwFlags
0x18000e07e  call    cs:__imp_FormatMessageA
0x18000e085  nop     dword ptr [rax+rax+00h]
0x18000e08a  test    eax, eax
0x18000e08c  jz      loc_18000E11A
0x18000e092  mov     rax, [rdi+10h]
0x18000e096  lea     rcx, aSLuFunctionSIu; "%s(%lu): [function %s %Iubit process %w"...
0x18000e09d  mov     r9d, [rdi+18h]
0x18000e0a1  lea     rdx, aSLuFunctionSIu_2; "%s(%lu): [function %s %Iubit process %w"...
0x18000e0a8  mov     r8, [rdi]
0x18000e0ab  test    rax, rax
0x18000e0ae  mov     [rsp+128h+var_D8], rax
0x18000e0b3  lea     rax, [rsp+128h+Buffer]
0x18000e0b8  mov     [rsp+128h+var_E0], rax
0x18000e0bd  cmovz   rdx, rcx; char *
0x18000e0c1  mov     [rsp+128h+var_E8], ebx
0x18000e0c5  lea     rax, [rsp+128h+SearchString]
0x18000e0ca  mov     [rsp+128h+var_F0], ebp
0x18000e0ce  mov     ecx, 80000010h; unsigned int
0x18000e0d3  mov     [rsp+128h+Arguments], rax
0x18000e0d8  mov     rax, [rdi+8]
0x18000e0dc  mov     qword ptr [rsp+128h+nSize], 40h ; '@'
0x18000e0e5  mov     [rsp+128h+lpBuffer], rax
0x18000e0ea  call    ?FusionpDbgPrintEx@@YAKKPEBDZZ; FusionpDbgPrintEx(ulong,char const *,...)
0x18000e0ef  mov     ecx, esi; dwErrCode
0x18000e0f1  call    cs:__imp_SetLastError
0x18000e0f8  nop     dword ptr [rax+rax+00h]
0x18000e0fd  mov     rcx, [rsp+128h+var_38]
0x18000e105  xor     rcx, rsp; StackCookie
0x18000e108  call    __security_check_cookie
0x18000e10d  add     rsp, 108h
0x18000e114  pop     rdi
0x18000e115  pop     rsi
0x18000e116  pop     rbp
0x18000e117  pop     rbx
0x18000e118  retn
0x18000e11a  mov     edx, 80h; BufferCount
0x18000e11f  mov     [rsp+128h+nSize], ebx
0x18000e123  lea     r9, aUntranslatable; "<Untranslatable Win32 status %d (0x%08l"...
0x18000e12a  mov     dword ptr [rsp+128h+lpBuffer], ebx
0x18000e12e  lea     rcx, [rsp+128h+Buffer]; Buffer
0x18000e133  lea     r8d, [rdx-1]; MaxCount
0x18000e137  call    cs:__imp__snprintf_s
0x18000e13e  nop     dword ptr [rax+rax+00h]
0x18000e143  mov     [rsp+128h+var_39], 0
0x18000e14b  jmp     loc_18000E092
```
