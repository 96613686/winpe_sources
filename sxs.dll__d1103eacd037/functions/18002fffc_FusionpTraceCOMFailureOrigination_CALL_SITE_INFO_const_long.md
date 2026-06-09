# FusionpTraceCOMFailureOrigination(_CALL_SITE_INFO const &,long)

- ea: `0x18002fffc`
- end: `0x180030141`
- name: `?FusionpTraceCOMFailureOrigination@@YAXAEBU_CALL_SITE_INFO@@J@Z`
- size: `325`
- prototype: `void(const struct _CALL_SITE_INFO *, int)`
- caller_count: `10`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002e6d0`
- `0x18002fe20`
- `0x180031260`
- `0x180040a30`
- `0x18004cde0`
- `0x180054e60`
- `0x18005bce0`
- `0x18005be40`
- `0x18005cfa0`
- `0x18005efe0`

## callees

- `0x18000c000`
- `0x18002fffc`
- `0x180059760`
- `0x18006a110`

## import_xrefs

- `ntdll!_snprintf_s` at `0x18003009e`
- `ntdll!_snprintf_s` at `0x18003009e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030022`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030022`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180030111`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180030111`
- `api-ms-win-core-localization-l1-2-0!FormatMessageA` at `0x180030075`
- `api-ms-win-core-localization-l1-2-0!FormatMessageA` at `0x180030075`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180030030`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180030030`

## string_xrefs

- `0x1800300b6`: `%s(%lu): [function %s %Iubit process %wZ tid 0x%lx] COM Error 0x%08lx (%s)\n`
- `0x1800300c1`: `%s(%lu): [function %s %Iubit process %wZ tid 0x%lx] COM Error 0x%08lx (%s) %s\n`

## pseudocode

```c
void __fastcall FusionpTraceCOMFailureOrigination(const struct _CALL_SITE_INFO *a1, DWORD a2)
{
  DWORD LastError; // esi
  DWORD CurrentThreadId; // ebp
  const char *v6; // rdx
  UNICODE_STRING SearchString; // [rsp+60h] [rbp-B8h] BYREF
  CHAR Buffer[128]; // [rsp+70h] [rbp-A8h] BYREF

  LastError = GetLastError();
  CurrentThreadId = GetCurrentThreadId();
  FusionpGetProcessImageFileName(&SearchString);
  Buffer[0] = 0;
  if ( !FormatMessageA(0x10FFu, 0, a2, 0, Buffer, 0x80u, 0) )
  {
    _snprintf_s(Buffer, 0x80u, 0x7Fu, "<Untranslatable HRESULT 0x%08lx>", a2);
    Buffer[127] = 0;
  }
  v6 = "%s(%lu): [function %s %Iubit process %wZ tid 0x%lx] COM Error 0x%08lx (%s) %s\n";
  if ( !*((_QWORD *)a1 + 2) )
    v6 = "%s(%lu): [function %s %Iubit process %wZ tid 0x%lx] COM Error 0x%08lx (%s)\n";
  FusionpDbgPrintEx(
    0xC0000000,
    v6,
    *(_QWORD *)a1,
    *((unsigned int *)a1 + 6),
    *((_QWORD *)a1 + 1),
    64,
    &SearchString,
    CurrentThreadId,
    a2,
    Buffer,
    *((_QWORD *)a1 + 2));
  SetLastError(LastError);
}

```

## disassembly

```asm
0x18002fffc  mov     [rsp+arg_10], rbx
0x180030001  push    rbp
0x180030002  push    rsi
0x180030003  push    rdi
0x180030004  sub     rsp, 100h
0x18003000b  mov     rax, cs:__security_cookie
0x180030012  xor     rax, rsp
0x180030015  mov     [rsp+118h+var_28], rax
0x18003001d  mov     edi, edx
0x18003001f  mov     rbx, rcx
0x180030022  call    cs:__imp_GetLastError
0x180030029  nop     dword ptr [rax+rax+00h]
0x18003002e  mov     esi, eax
0x180030030  call    cs:__imp_GetCurrentThreadId
0x180030037  nop     dword ptr [rax+rax+00h]
0x18003003c  lea     rcx, [rsp+118h+SearchString]; SearchString
0x180030041  mov     ebp, eax
0x180030043  call    ?FusionpGetProcessImageFileName@@YAXPEAU_UNICODE_STRING@@@Z; FusionpGetProcessImageFileName(_UNICODE_STRING *)
0x180030048  lea     rax, [rsp+118h+Buffer]
0x18003004d  mov     [rsp+118h+Arguments], 0; Arguments
0x180030056  mov     [rsp+118h+nSize], 80h; nSize
0x18003005e  xor     r9d, r9d; dwLanguageId
0x180030061  mov     r8d, edi; dwMessageId
0x180030064  mov     [rsp+118h+lpBuffer], rax; lpBuffer
0x180030069  xor     edx, edx; lpSource
0x18003006b  mov     [rsp+118h+Buffer], 0
0x180030070  mov     ecx, 10FFh; dwFlags
0x180030075  call    cs:__imp_FormatMessageA
0x18003007c  nop     dword ptr [rax+rax+00h]
0x180030081  test    eax, eax
0x180030083  jnz     short loc_1800300B2
0x180030085  lea     r9, aUntranslatable_1; "<Untranslatable HRESULT 0x%08lx>"
0x18003008c  mov     dword ptr [rsp+118h+lpBuffer], edi
0x180030090  mov     edx, 80h; BufferCount
0x180030095  lea     r8d, [rax+7Fh]; MaxCount
0x180030099  lea     rcx, [rsp+118h+Buffer]; Buffer
0x18003009e  call    cs:__imp__snprintf_s
0x1800300a5  nop     dword ptr [rax+rax+00h]
0x1800300aa  mov     [rsp+118h+var_29], 0
0x1800300b2  mov     rax, [rbx+10h]
0x1800300b6  lea     rcx, aSLuFunctionSIu_0; "%s(%lu): [function %s %Iubit process %w"...
0x1800300bd  mov     r9d, [rbx+18h]
0x1800300c1  lea     rdx, aSLuFunctionSIu_1; "%s(%lu): [function %s %Iubit process %w"...
0x1800300c8  mov     r8, [rbx]
0x1800300cb  test    rax, rax
0x1800300ce  mov     [rsp+118h+var_C8], rax
0x1800300d3  lea     rax, [rsp+118h+Buffer]
0x1800300d8  mov     [rsp+118h+var_D0], rax
0x1800300dd  cmovz   rdx, rcx; char *
0x1800300e1  mov     [rsp+118h+var_D8], edi
0x1800300e5  lea     rax, [rsp+118h+SearchString]
0x1800300ea  mov     [rsp+118h+var_E0], ebp
0x1800300ee  mov     ecx, 0C0000000h; unsigned int
0x1800300f3  mov     [rsp+118h+Arguments], rax
0x1800300f8  mov     rax, [rbx+8]
0x1800300fc  mov     qword ptr [rsp+118h+nSize], 40h ; '@'
0x180030105  mov     [rsp+118h+lpBuffer], rax
0x18003010a  call    ?FusionpDbgPrintEx@@YAKKPEBDZZ; FusionpDbgPrintEx(ulong,char const *,...)
0x18003010f  mov     ecx, esi; dwErrCode
0x180030111  call    cs:__imp_SetLastError
0x180030118  nop     dword ptr [rax+rax+00h]
0x18003011d  mov     rcx, [rsp+118h+var_28]
0x180030125  xor     rcx, rsp; StackCookie
0x180030128  call    __security_check_cookie
0x18003012d  mov     rbx, [rsp+118h+arg_10]
0x180030135  add     rsp, 100h
0x18003013c  pop     rdi
0x18003013d  pop     rsi
0x18003013e  pop     rbp
0x18003013f  retn
```
