# FusionpLogErrorToDebugger(ulong,ulong,_UNICODE_STRING const * const *)

- ea: `0x180058dc4`
- end: `0x180058fbc`
- name: `?FusionpLogErrorToDebugger@@YAJKKPEBQEBU_UNICODE_STRING@@@Z`
- size: `504`
- prototype: `__int64 __fastcall(DWORD dwMessageId, unsigned int, const struct _UNICODE_STRING *const *)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x18002e4a0`
- `0x180058904`

## callees

- `0x18000c000`
- `0x18004d2d0`
- `0x180058cb8`
- `0x180058dc4`
- `0x18005d320`
- `0x18006a110`

## import_xrefs

- `ntdll!wcschr` at `0x180058ed2`
- `ntdll!wcschr` at `0x180058f88`
- `ntdll!wcschr` at `0x180058ed2`
- `ntdll!wcschr` at `0x180058f88`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180058e5c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180058e5c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180058f34`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180058f34`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180058e4c`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180058eb9`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180058e4c`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180058eb9`

## string_xrefs

- `0x180058e68`: `SXS.DLL: FusionpLogError/FormatMessageW failed %ld\n`
- `0x180058f20`: `SXS.DLL: %S`
- `0x180058f06`: `Syntax error in manifest file "`

## pseudocode

```c
__int64 __fastcall FusionpLogErrorToDebugger(DWORD dwMessageId, __int64 a2, va_list *a3)
{
  int v5; // eax
  DWORD v6; // r14d
  unsigned int v7; // esi
  DWORD LastError; // eax
  unsigned __int64 v9; // rdi
  __int64 v10; // rax
  wchar_t *v11; // rbx
  const wchar_t *v12; // rax
  WCHAR lpBuffer[4]; // [rsp+40h] [rbp-30h] BYREF
  __int64 v15; // [rsp+48h] [rbp-28h]
  WCHAR Buffer[4]; // [rsp+50h] [rbp-20h] BYREF
  char v17; // [rsp+58h] [rbp-18h]

  v5 = FusionpEventIdToError(dwMessageId);
  v6 = v5;
  if ( v5 > 0 )
    v7 = (unsigned __int16)v5 | 0x80070000;
  else
    v7 = v5;
  *(_QWORD *)Buffer = 0;
  *(_QWORD *)lpBuffer = 0;
  LOBYTE(v15) = 0;
  v17 = 1;
  if ( !FormatMessageW(0x2900u, g_hInstance, dwMessageId, 0, Buffer, 0x12Cu, (va_list *)&Arguments) )
    goto LABEL_5;
  v9 = -1;
  v10 = -1;
  do
    ++v10;
  while ( *(_WORD *)(*(_QWORD *)Buffer + 2 * v10) );
  LOBYTE(v15) = 1;
  if ( FormatMessageW(0x2500u, *(LPCVOID *)Buffer, 0, 0, lpBuffer, v10 + 1, a3) )
  {
    v11 = wcschr(*(const wchar_t **)lpBuffer, 0xAu);
    if ( !v11 )
      goto LABEL_14;
    v12 = *(const wchar_t **)lpBuffer;
    do
      ++v9;
    while ( *(_WORD *)(*(_QWORD *)lpBuffer + 2 * v9) );
    if ( v9 < 0x1F )
      goto LABEL_15;
    if ( !FusionpEqualStrings(*(WCHAR **)lpBuffer, 31, (WCHAR *)L"Syntax error in manifest file \"", 31, 1u) )
    {
LABEL_14:
      v12 = *(const wchar_t **)lpBuffer;
LABEL_15:
      FusionpDbgPrintEx(0xC0000000, "SXS.DLL: %S", v12);
      goto LABEL_16;
    }
    while ( wcschr(L"\r\n", *v11) )
      ++v11;
    FusionpDbgPrintEx(0xC0000000, "%wZ(%wZ): %S", a3[11], a3[12], v11);
  }
  else
  {
LABEL_5:
    LastError = GetLastError();
    FusionpDbgPrintEx(0xC0000000, "SXS.DLL: FusionpLogError/FormatMessageW failed %ld\n", LastError);
  }
LABEL_16:
  SetLastError(v6);
  CSmartPtrWithNamedDestructor<unsigned short,&void LocalFreeWcharPointer(unsigned short *),CSmartPtrWithNamedDestructorHelper<unsigned short,&void LocalFreeWcharPointer(unsigned short *)>>::~CSmartPtrWithNamedDestructor<unsigned short,&void LocalFreeWcharPointer(unsigned short *),CSmartPtrWithNamedDestructorHelper<unsigned short,&void LocalFreeWcharPointer(unsigned short *)>>(lpBuffer);
  CSmartPtrWithNamedDestructor<unsigned short,&void LocalFreeWcharPointer(unsigned short *),CSmartPtrWithNamedDestructorHelper<unsigned short,&void LocalFreeWcharPointer(unsigned short *)>>::~CSmartPtrWithNamedDestructor<unsigned short,&void LocalFreeWcharPointer(unsigned short *),CSmartPtrWithNamedDestructorHelper<unsigned short,&void LocalFreeWcharPointer(unsigned short *)>>(Buffer);
  return v7;
}

```

## disassembly

```asm
0x180058dc4  mov     [rsp-28h+arg_8], rbx
0x180058dc9  mov     [rsp-28h+arg_18], rsi
0x180058dce  push    rbp
0x180058dcf  push    rdi
0x180058dd0  push    r12
0x180058dd2  push    r14
0x180058dd4  push    r15
0x180058dd6  mov     rbp, rsp
0x180058dd9  sub     rsp, 70h
0x180058ddd  mov     rax, cs:__security_cookie
0x180058de4  xor     rax, rsp
0x180058de7  mov     [rbp+var_10], rax
0x180058deb  mov     r15, r8
0x180058dee  mov     ebx, ecx
0x180058df0  call    ?FusionpEventIdToError@@YAKK@Z; FusionpEventIdToError(ulong)
0x180058df5  xor     r12d, r12d
0x180058df8  mov     r14d, eax
0x180058dfb  test    eax, eax
0x180058dfd  jg      short loc_180058E03
0x180058dff  mov     esi, eax
0x180058e01  jmp     short loc_180058E0D
0x180058e03  movzx   esi, r14w
0x180058e07  or      esi, 80070000h
0x180058e0d  mov     rdx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; lpSource
0x180058e14  lea     rax, Arguments
0x180058e1b  mov     [rsp+70h+Arguments], rax; Arguments
0x180058e20  xor     r9d, r9d; dwLanguageId
0x180058e23  lea     rax, [rbp+Buffer]
0x180058e27  mov     [rsp+70h+nSize], 12Ch; nSize
0x180058e2f  mov     r8d, ebx; dwMessageId
0x180058e32  mov     [rsp+70h+lpBuffer], rax; lpBuffer
0x180058e37  mov     ecx, 2900h; dwFlags
0x180058e3c  mov     qword ptr [rbp+Buffer], r12
0x180058e40  mov     qword ptr [rbp+var_30], r12
0x180058e44  mov     byte ptr [rbp+var_28], r12b
0x180058e48  mov     [rbp+var_18], 1
0x180058e4c  call    cs:__imp_FormatMessageW
0x180058e53  nop     dword ptr [rax+rax+00h]
0x180058e58  test    eax, eax
0x180058e5a  jnz     short loc_180058E81
0x180058e5c  call    cs:__imp_GetLastError
0x180058e63  nop     dword ptr [rax+rax+00h]
0x180058e68  lea     rdx, aSxsDllFusionpl; "SXS.DLL: FusionpLogError/FormatMessageW"...
0x180058e6f  mov     ecx, 0C0000000h; unsigned int
0x180058e74  mov     r8d, eax
0x180058e77  call    ?FusionpDbgPrintEx@@YAKKPEBDZZ; FusionpDbgPrintEx(ulong,char const *,...)
0x180058e7c  jmp     loc_180058F31
0x180058e81  mov     rdx, qword ptr [rbp+Buffer]; lpSource
0x180058e85  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180058e89  mov     rax, rdi
0x180058e8c  inc     rax
0x180058e8f  cmp     [rdx+rax*2], r12w
0x180058e94  jnz     short loc_180058E8C
0x180058e96  inc     eax
0x180058e98  mov     [rsp+70h+Arguments], r15; Arguments
0x180058e9d  mov     [rsp+70h+nSize], eax; nSize
0x180058ea1  xor     r9d, r9d; dwLanguageId
0x180058ea4  lea     rax, [rbp+var_30]
0x180058ea8  mov     byte ptr [rbp+var_28], 1
0x180058eac  xor     r8d, r8d; dwMessageId
0x180058eaf  mov     [rsp+70h+lpBuffer], rax; lpBuffer
0x180058eb4  mov     ecx, 2500h; dwFlags
0x180058eb9  call    cs:__imp_FormatMessageW
0x180058ec0  nop     dword ptr [rax+rax+00h]
0x180058ec5  test    eax, eax
0x180058ec7  jz      short loc_180058E5C
0x180058ec9  mov     rcx, qword ptr [rbp+var_30]; Str
0x180058ecd  mov     edx, 0Ah; Ch
0x180058ed2  call    cs:__imp_wcschr
0x180058ed9  nop     dword ptr [rax+rax+00h]
0x180058ede  mov     rbx, rax
0x180058ee1  test    rax, rax
0x180058ee4  jz      short loc_180058F19
0x180058ee6  mov     rax, qword ptr [rbp+var_30]
0x180058eea  inc     rdi
0x180058eed  cmp     [rax+rdi*2], r12w
0x180058ef2  jnz     short loc_180058EEA
0x180058ef4  mov     edx, 1Fh; unsigned __int64
0x180058ef9  cmp     rdi, rdx
0x180058efc  jb      short loc_180058F1D
0x180058efe  mov     r9d, edx; unsigned __int64
0x180058f01  mov     byte ptr [rsp+70h+lpBuffer], 1; bool
0x180058f06  lea     r8, aSyntaxErrorInM; "Syntax error in manifest file \""
0x180058f0d  mov     rcx, rax; unsigned __int16 *
0x180058f10  call    ?FusionpEqualStrings@@YA_NPEBG_K01_N@Z; FusionpEqualStrings(ushort const *,unsigned __int64,ushort const *,unsigned __int64,bool)
0x180058f15  test    al, al
0x180058f17  jnz     short loc_180058F7E
0x180058f19  mov     rax, qword ptr [rbp+var_30]
0x180058f1d  mov     r8, rax
0x180058f20  lea     rdx, aSxsDllS; "SXS.DLL: %S"
0x180058f27  mov     ecx, 0C0000000h; unsigned int
0x180058f2c  call    ?FusionpDbgPrintEx@@YAKKPEBDZZ; FusionpDbgPrintEx(ulong,char const *,...)
0x180058f31  mov     ecx, r14d; dwErrCode
0x180058f34  call    cs:__imp_SetLastError
0x180058f3b  nop     dword ptr [rax+rax+00h]
0x180058f40  lea     rcx, [rbp+var_30]
0x180058f44  call    ??1?$CSmartPtrWithNamedDestructor@G$1?LocalFreeWcharPointer@@YAXPEAG@ZV?$CSmartPtrWithNamedDestructorHelper@G$1?LocalFreeWcharPointer@@YAXPEAG@Z@@@@QEAA@XZ; CSmartPtrWithNamedDestructor<ushort,&LocalFreeWcharPointer(ushort *),CSmartPtrWithNamedDestructorHelper<ushort,&LocalFreeWcharPointer(ushort *)>>::~CSmartPtrWithNamedDestructor<ushort,&LocalFreeWcharPointer(ushort *),CSmartPtrWithNamedDestructorHelper<ushort,&LocalFreeWcharPointer(ushort *)>>(void)
0x180058f49  lea     rcx, [rbp+Buffer]
0x180058f4d  call    ??1?$CSmartPtrWithNamedDestructor@G$1?LocalFreeWcharPointer@@YAXPEAG@ZV?$CSmartPtrWithNamedDestructorHelper@G$1?LocalFreeWcharPointer@@YAXPEAG@Z@@@@QEAA@XZ; CSmartPtrWithNamedDestructor<ushort,&LocalFreeWcharPointer(ushort *),CSmartPtrWithNamedDestructorHelper<ushort,&LocalFreeWcharPointer(ushort *)>>::~CSmartPtrWithNamedDestructor<ushort,&LocalFreeWcharPointer(ushort *),CSmartPtrWithNamedDestructorHelper<ushort,&LocalFreeWcharPointer(ushort *)>>(void)
0x180058f52  mov     eax, esi
0x180058f54  mov     rcx, [rbp+var_10]
0x180058f58  xor     rcx, rsp; StackCookie
0x180058f5b  call    __security_check_cookie
0x180058f60  lea     r11, [rsp+70h+var_s0]
0x180058f65  mov     rbx, [r11+38h]
0x180058f69  mov     rsi, [r11+48h]
0x180058f6d  mov     rsp, r11
0x180058f70  pop     r15
0x180058f72  pop     r14
0x180058f74  pop     r12
0x180058f76  pop     rdi
0x180058f77  pop     rbp
0x180058f78  retn
0x180058f7a  add     rbx, 2
0x180058f7e  movzx   edx, word ptr [rbx]; Ch
0x180058f81  lea     rcx, asc_18008E2A8; "\r\n"
0x180058f88  call    cs:__imp_wcschr
0x180058f8f  nop     dword ptr [rax+rax+00h]
0x180058f94  test    rax, rax
0x180058f97  jnz     short loc_180058F7A
0x180058f99  mov     r9, [r15+60h]
0x180058f9d  lea     rdx, aWzWzS; "%wZ(%wZ): %S"
0x180058fa4  mov     r8, [r15+58h]
0x180058fa8  mov     ecx, 0C0000000h; unsigned int
0x180058fad  mov     [rsp+70h+lpBuffer], rbx
0x180058fb2  call    ?FusionpDbgPrintEx@@YAKKPEBDZZ; FusionpDbgPrintEx(ulong,char const *,...)
0x180058fb7  jmp     loc_180058F31
```
