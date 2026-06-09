# SampPerformInitializeFailurePopup(long)

- ea: `0x18007c584`
- end: `0x18007c75f`
- name: `?SampPerformInitializeFailurePopup@@YAXJ@Z`
- size: `475`
- prototype: `void __fastcall(int)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, installer_update`

## callers

- `0x1800888c0`

## callees

- `0x18002cd80`
- `0x18007c584`
- `0x1800ac464`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18007c5e7`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18007c5e7`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18007c626`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18007c626`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x18007c683`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x18007c729`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x18007c683`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x18007c729`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18007c61d`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18007c655`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18007c61d`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18007c655`
- `ntdll!RtlNtStatusToDosError` at `0x18007c5d3`
- `ntdll!RtlNtStatusToDosError` at `0x18007c5d3`
- `ntdll!RtlAdjustPrivilege` at `0x18007c6e3`
- `ntdll!RtlAdjustPrivilege` at `0x18007c721`
- `ntdll!RtlAdjustPrivilege` at `0x18007c6e3`
- `ntdll!RtlAdjustPrivilege` at `0x18007c721`
- `ntdll!NtRaiseHardError` at `0x18007c70d`
- `ntdll!NtRaiseHardError` at `0x18007c70d`
- `ntdll!RtlInitUnicodeString` at `0x18007c66f`
- `ntdll!RtlInitUnicodeString` at `0x18007c66f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007c738`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007c738`

## string_xrefs

- `0x18007c5e0`: `ntdll.dll`

## pseudocode

```c
void __fastcall SampPerformInitializeFailurePopup(NTSTATUS a1)
{
  unsigned __int64 v1; // rbx
  ULONG v2; // eax
  HMODULE ModuleHandleW; // rdi
  const WCHAR *v4; // rdx
  UINT v5; // edi
  NTSTATUS v6; // ebx
  unsigned __int8 OldValue[8]; // [rsp+40h] [rbp-9h] BYREF
  WCHAR Buffer[4]; // [rsp+48h] [rbp-1h] BYREF
  ULONG Response; // [rsp+50h] [rbp+7h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+58h] [rbp+Fh] BYREF
  unsigned __int64 Parameters[2]; // [rsp+68h] [rbp+1Fh] BYREF
  va_list Arguments[2]; // [rsp+78h] [rbp+2Fh] BYREF
  __int128 v13; // [rsp+88h] [rbp+3Fh]

  v1 = a1;
  Response = 0;
  OldValue[0] = 0;
  *(_QWORD *)Buffer = 0;
  DestinationString = 0;
  *(_OWORD *)Arguments = 0;
  v13 = 0;
  v2 = RtlNtStatusToDosError(a1);
  if ( v2 == 317 )
  {
    ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
    if ( ModuleHandleW )
    {
      FormatMessageW(0xB00u, ModuleHandleW, v1, 0, Buffer, 0, 0);
      FreeLibrary(ModuleHandleW);
    }
  }
  else
  {
    FormatMessageW(0x3100u, 0, v2, 0, Buffer, 0, Arguments);
  }
  v4 = *(const WCHAR **)Buffer;
  if ( !*(_QWORD *)Buffer )
    v4 = L"Unmapped Error";
  RtlInitUnicodeString(&DestinationString, v4);
  Parameters[1] = v1;
  Parameters[0] = (unsigned __int64)&DestinationString;
  v5 = SetErrorMode(0);
  if ( !SampDsInitializationFailed || (_DWORD)v1 == -1073741087 )
  {
    if ( SampUseDsData == 1 )
      v6 = SampIsSetupInProgress(0) != 0 ? -1073741075 : -1073741109;
    else
      v6 = -1073741085;
  }
  else
  {
    v6 = SampIsSetupInProgress(0) != 0 ? -1073741076 : -1073741086;
  }
  if ( RtlAdjustPrivilege(0x13u, 1u, 0, OldValue) >= 0 )
  {
    NtRaiseHardError(v6, 2u, 1u, Parameters, 6u, &Response);
    RtlAdjustPrivilege(0x13u, OldValue[0], 0, OldValue);
  }
  SetErrorMode(v5);
  if ( *(_QWORD *)Buffer )
    LocalFree(*(HLOCAL *)Buffer);
}

```

## disassembly

```asm
0x18007c584  mov     [rsp-8+arg_8], rbx
0x18007c589  mov     [rsp-8+arg_10], rdi
0x18007c58e  push    rbp
0x18007c58f  lea     rbp, [rsp-57h]
0x18007c594  sub     rsp, 0A0h
0x18007c59b  mov     rax, cs:__security_cookie
0x18007c5a2  xor     rax, rsp
0x18007c5a5  mov     [rbp+57h+var_8], rax
0x18007c5a9  xorps   xmm1, xmm1
0x18007c5ac  movsxd  rbx, ecx
0x18007c5af  xorps   xmm0, xmm0
0x18007c5b2  mov     [rbp+57h+Response], 0
0x18007c5b9  mov     ecx, ebx; Status
0x18007c5bb  mov     [rbp+57h+OldValue], 0
0x18007c5bf  mov     qword ptr [rbp+57h+Buffer], 0
0x18007c5c7  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x18007c5cb  movups  xmmword ptr [rbp+57h+var_28], xmm1
0x18007c5cf  movups  [rbp+57h+var_18], xmm1
0x18007c5d3  call    cs:__imp_RtlNtStatusToDosError
0x18007c5d9  cmp     eax, 13Dh
0x18007c5de  jnz     short loc_18007C62E
0x18007c5e0  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18007c5e7  call    cs:__imp_GetModuleHandleW
0x18007c5ed  mov     rdi, rax
0x18007c5f0  test    rax, rax
0x18007c5f3  jz      short loc_18007C65B
0x18007c5f5  mov     [rsp+0A0h+Arguments], 0; Arguments
0x18007c5fe  lea     rax, [rbp+57h+Buffer]
0x18007c602  mov     [rsp+0A0h+nSize], 0; nSize
0x18007c60a  xor     r9d, r9d; dwLanguageId
0x18007c60d  mov     r8d, ebx; dwMessageId
0x18007c610  mov     [rsp+0A0h+lpBuffer], rax; lpBuffer
0x18007c615  mov     rdx, rdi; lpSource
0x18007c618  mov     ecx, 0B00h; dwFlags
0x18007c61d  call    cs:__imp_FormatMessageW
0x18007c623  mov     rcx, rdi; hLibModule
0x18007c626  call    cs:__imp_FreeLibrary
0x18007c62c  jmp     short loc_18007C65B
0x18007c62e  lea     rcx, [rbp+57h+var_28]
0x18007c632  xor     r9d, r9d; dwLanguageId
0x18007c635  mov     [rsp+0A0h+Arguments], rcx; Arguments
0x18007c63a  mov     r8d, eax; dwMessageId
0x18007c63d  lea     rcx, [rbp+57h+Buffer]
0x18007c641  mov     [rsp+0A0h+nSize], 0; nSize
0x18007c649  mov     [rsp+0A0h+lpBuffer], rcx; lpBuffer
0x18007c64e  xor     edx, edx; lpSource
0x18007c650  mov     ecx, 3100h; dwFlags
0x18007c655  call    cs:__imp_FormatMessageW
0x18007c65b  mov     rdx, qword ptr [rbp+57h+Buffer]
0x18007c65f  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18007c663  test    rdx, rdx
0x18007c666  jnz     short loc_18007C66F
0x18007c668  lea     rdx, aUnmappedError; "Unmapped Error"
0x18007c66f  call    cs:__imp_RtlInitUnicodeString
0x18007c675  lea     rax, [rbp+57h+DestinationString]
0x18007c679  mov     [rbp+57h+var_30], rbx
0x18007c67d  xor     ecx, ecx; uMode
0x18007c67f  mov     [rbp+57h+Parameters], rax
0x18007c683  call    cs:__imp_SetErrorMode
0x18007c689  cmp     cs:?SampDsInitializationFailed@@3EA, 0; uchar SampDsInitializationFailed
0x18007c690  mov     edi, eax
0x18007c692  jz      short loc_18007C6B2
0x18007c694  cmp     ebx, 0C00002E1h
0x18007c69a  jz      short loc_18007C6B2
0x18007c69c  xor     ecx, ecx; unsigned __int8 *
0x18007c69e  call    ?SampIsSetupInProgress@@YAEPEAE@Z; SampIsSetupInProgress(uchar *)
0x18007c6a3  neg     al
0x18007c6a5  sbb     ebx, ebx
0x18007c6a7  and     ebx, 0Ah
0x18007c6aa  add     ebx, 0C00002E2h
0x18007c6b0  jmp     short loc_18007C6D6
0x18007c6b2  cmp     cs:?SampUseDsData@@3EA, 1; uchar SampUseDsData
0x18007c6b9  jnz     short loc_18007C6D1
0x18007c6bb  xor     ecx, ecx; unsigned __int8 *
0x18007c6bd  call    ?SampIsSetupInProgress@@YAEPEAE@Z; SampIsSetupInProgress(uchar *)
0x18007c6c2  neg     al
0x18007c6c4  sbb     ebx, ebx
0x18007c6c6  and     ebx, 22h
0x18007c6c9  add     ebx, 0C00002CBh
0x18007c6cf  jmp     short loc_18007C6D6
0x18007c6d1  mov     ebx, 0C00002E3h
0x18007c6d6  xor     r8d, r8d; ForThread
0x18007c6d9  lea     r9, [rbp+57h+OldValue]; OldValue
0x18007c6dd  mov     dl, 1; NewValue
0x18007c6df  lea     ecx, [r8+13h]; Privilege
0x18007c6e3  call    cs:__imp_RtlAdjustPrivilege
0x18007c6e9  test    eax, eax
0x18007c6eb  js      short loc_18007C727
0x18007c6ed  mov     edx, 2; NumberOfParameters
0x18007c6f2  lea     rax, [rbp+57h+Response]
0x18007c6f6  mov     qword ptr [rsp+0A0h+nSize], rax; Response
0x18007c6fb  lea     r9, [rbp+57h+Parameters]; Parameters
0x18007c6ff  mov     ecx, ebx; ErrorStatus
0x18007c701  mov     dword ptr [rsp+0A0h+lpBuffer], 6; ValidResponseOptions
0x18007c709  lea     r8d, [rdx-1]; UnicodeStringParameterMask
0x18007c70d  call    cs:__imp_NtRaiseHardError
0x18007c713  mov     dl, [rbp+57h+OldValue]; NewValue
0x18007c716  lea     r9, [rbp+57h+OldValue]; OldValue
0x18007c71a  xor     r8d, r8d; ForThread
0x18007c71d  lea     ecx, [r8+13h]; Privilege
0x18007c721  call    cs:__imp_RtlAdjustPrivilege
0x18007c727  mov     ecx, edi; uMode
0x18007c729  call    cs:__imp_SetErrorMode
0x18007c72f  mov     rcx, qword ptr [rbp+57h+Buffer]; hMem
0x18007c733  test    rcx, rcx
0x18007c736  jz      short loc_18007C73E
0x18007c738  call    cs:__imp_LocalFree
0x18007c73e  mov     rcx, [rbp+57h+var_8]
0x18007c742  xor     rcx, rsp; StackCookie
0x18007c745  call    __security_check_cookie
0x18007c74a  lea     r11, [rsp+0A0h+var_s0]
0x18007c752  mov     rbx, [r11+18h]
0x18007c756  mov     rdi, [r11+20h]
0x18007c75a  mov     rsp, r11
0x18007c75d  pop     rbp
0x18007c75e  retn
```
