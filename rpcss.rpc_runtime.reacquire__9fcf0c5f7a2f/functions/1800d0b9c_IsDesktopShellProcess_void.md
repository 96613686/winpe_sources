# IsDesktopShellProcess(void)

- ea: `0x1800d0b9c`
- end: `0x1800d0ddb`
- name: `?IsDesktopShellProcess@@YA_NXZ`
- size: `575`
- prototype: `bool(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800b2c44`

## callees

- `0x180095c0c`
- `0x1800b3240`
- `0x1800cd5a4`
- `0x1800d0b9c`
- `0x180114010`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x1800d0be1`
- `ntdll!RtlInitUnicodeString` at `0x1800d0be1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800d0d04`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800d0d1e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800d0d38`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800d0d04`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800d0d1e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800d0d38`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800d0ce5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800d0ce5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800d0d82`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800d0d82`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800d0c7c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800d0cbc`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800d0c7c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800d0cbc`
- `api-ms-win-core-apiquery-l1-1-0!ApiSetQueryApiSetPresence` at `0x1800d0bf9`
- `api-ms-win-core-apiquery-l1-1-0!ApiSetQueryApiSetPresence` at `0x1800d0bf9`

## string_xrefs

- `0x1800d0cdc`: `ext-ms-win-ntuser-window-l1-1-0.dll`
- `0x1800d0d2e`: `IsGUIThread`
- `0x1800d0d14`: `GetWindowThreadProcessId`

## pseudocode

```c
bool IsDesktopShellProcess(void)
{
  char v0; // bl
  __int64 v1; // rcx
  struct _RTL_USER_PROCESS_PARAMETERS *ProcessParameters; // rax
  unsigned __int64 Length; // rcx
  bool v4; // al
  struct _UNICODE_STRING *FileName; // rax
  __int64 (*ProcAddress)(void); // r14
  FARPROC v7; // rdi
  FARPROC v8; // rax
  __int64 v9; // rcx
  unsigned int (__fastcall *v10)(_QWORD); // rsi
  __int64 v11; // rax
  __int64 v12; // rcx
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-10h] BYREF
  int v15; // [rsp+70h] [rbp+30h] BYREF
  HMODULE phModule; // [rsp+78h] [rbp+38h] BYREF

  v0 = IsDesktopShellProcessDetails::g_isDesktopShellProcessState;
  if ( !IsDesktopShellProcessDetails::g_isDesktopShellProcessState )
  {
    DestinationString = 0;
    v0 = 2;
    RtlInitUnicodeString(&DestinationString, L"ext-ms-win-ntuser-window-l1-1-0");
    LOBYTE(v15) = 0;
    if ( (int)ApiSetQueryApiSetPresence(&DestinationString, &v15) >= 0 )
    {
      if ( (_BYTE)v15 && NtCurrentPeb()->SessionId )
      {
        if ( (ProcessParameters = NtCurrentPeb()->ProcessParameters) == 0
          || (Length = ProcessParameters->DesktopInfo.Length, (unsigned __int16)Length < 2u)
          || ((unsigned int)Length < 0x10
            ? (v4 = 1)
            : (v4 = CompareStringOrdinal(
                      &ProcessParameters->DesktopInfo.Buffer[(Length >> 1) - 8],
                      8,
                      L"\\Default",
                      8,
                      1) != 2),
              !v4) )
        {
          FileName = ImagePath::GetFileName(&DestinationString);
          if ( CompareStringOrdinal(FileName->Buffer, FileName->Length >> 1, L"explorer.exe", -1, 1) == 2 )
          {
            phModule = 0;
            if ( GetModuleHandleExW(0, L"ext-ms-win-ntuser-window-l1-1-0.dll", &phModule) )
            {
              ProcAddress = GetProcAddress(phModule, "GetShellWindow");
              v7 = GetProcAddress(phModule, "GetWindowThreadProcessId");
              v8 = GetProcAddress(phModule, "IsGUIThread");
              v10 = (unsigned int (__fastcall *)(_QWORD))v8;
              if ( ProcAddress && v7 && v8 )
              {
                v11 = ProcAddress();
                if ( v11 )
                {
                  v15 = 0;
                  if ( !((unsigned int (__fastcall *)(__int64, int *))v7)(v11, &v15) )
                    MicrosoftTelemetryAssertTriggeredNoArgs(v12);
                  if ( GetCurrentProcessId() == v15 )
                    v0 = 1;
                }
                else if ( v10(0) )
                {
                  v0 = 1;
                }
              }
              else
              {
                MicrosoftTelemetryAssertTriggeredNoArgs(v9);
              }
            }
            wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&phModule);
          }
        }
      }
    }
    else
    {
      MicrosoftTelemetryAssertTriggeredNoArgs(v1);
    }
    IsDesktopShellProcessDetails::g_isDesktopShellProcessState = v0;
  }
  return v0 == 1;
}

```

## disassembly

```asm
0x1800d0b9c  mov     [rsp-28h+arg_10], rbx
0x1800d0ba1  push    rbp
0x1800d0ba2  push    rsi
0x1800d0ba3  push    rdi
0x1800d0ba4  push    r12
0x1800d0ba6  push    r14
0x1800d0ba8  mov     rbp, rsp
0x1800d0bab  sub     rsp, 40h
0x1800d0baf  mov     bl, cs:?g_isDesktopShellProcessState@IsDesktopShellProcessDetails@@3U?$atomic@W4IsDesktopShellProcessState@IsDesktopShellProcessDetails@@@std@@A; std::atomic<IsDesktopShellProcessDetails::IsDesktopShellProcessState> IsDesktopShellProcessDetails::g_isDesktopShellProcessState
0x1800d0bb5  mov     r12d, 1
0x1800d0bbb  mov     al, cs:?g_isDesktopShellProcessState@IsDesktopShellProcessDetails@@3U?$atomic@W4IsDesktopShellProcessState@IsDesktopShellProcessDetails@@@std@@A; std::atomic<IsDesktopShellProcessDetails::IsDesktopShellProcessState> IsDesktopShellProcessDetails::g_isDesktopShellProcessState
0x1800d0bc1  nop
0x1800d0bc2  test    al, al
0x1800d0bc4  jnz     loc_1800D0DC0
0x1800d0bca  xorps   xmm0, xmm0
0x1800d0bcd  lea     rdx, aExtMsWinNtuser; "ext-ms-win-ntuser-window-l1-1-0"
0x1800d0bd4  lea     rcx, [rbp+DestinationString]; DestinationString
0x1800d0bd8  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x1800d0bdc  lea     ebx, [r12+1]
0x1800d0be1  call    cs:__imp_RtlInitUnicodeString
0x1800d0be8  nop     dword ptr [rax+rax+00h]
0x1800d0bed  lea     rdx, [rbp+arg_0]
0x1800d0bf1  mov     byte ptr [rbp+arg_0], 0
0x1800d0bf5  lea     rcx, [rbp+DestinationString]
0x1800d0bf9  call    cs:__imp_ApiSetQueryApiSetPresence
0x1800d0c00  nop     dword ptr [rax+rax+00h]
0x1800d0c05  test    eax, eax
0x1800d0c07  jns     short loc_1800D0C13
0x1800d0c09  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800d0c0e  jmp     loc_1800D0DB8
0x1800d0c13  cmp     byte ptr [rbp+arg_0], 0
0x1800d0c17  jz      loc_1800D0DB8
0x1800d0c1d  mov     rax, gs:60h
0x1800d0c26  cmp     dword ptr [rax+2C0h], 0
0x1800d0c2d  jz      loc_1800D0DB8
0x1800d0c33  mov     rax, gs:60h
0x1800d0c3c  mov     rax, [rax+20h]
0x1800d0c40  test    rax, rax
0x1800d0c43  jz      short loc_1800D0C9A
0x1800d0c45  movzx   ecx, word ptr [rax+0C0h]
0x1800d0c4c  cmp     cx, bx
0x1800d0c4f  jb      short loc_1800D0C9A
0x1800d0c51  cmp     ecx, 10h
0x1800d0c54  jb      short loc_1800D0C8F
0x1800d0c56  mov     rax, [rax+0C8h]
0x1800d0c5d  mov     edx, 8; cchCount1
0x1800d0c62  mov     r8, cs:lpString2; lpString2
0x1800d0c69  add     rax, 0FFFFFFFFFFFFFFF0h
0x1800d0c6d  shr     rcx, 1
0x1800d0c70  mov     r9d, edx; cchCount2
0x1800d0c73  mov     [rsp+40h+bIgnoreCase], r12d; bIgnoreCase
0x1800d0c78  lea     rcx, [rax+rcx*2]; lpString1
0x1800d0c7c  call    cs:__imp_CompareStringOrdinal
0x1800d0c83  nop     dword ptr [rax+rax+00h]
0x1800d0c88  cmp     eax, ebx
0x1800d0c8a  setnz   al
0x1800d0c8d  jmp     short loc_1800D0C92
0x1800d0c8f  mov     al, r12b
0x1800d0c92  test    al, al
0x1800d0c94  jnz     loc_1800D0DB8
0x1800d0c9a  lea     rcx, [rbp+DestinationString]; retstr
0x1800d0c9e  call    ?GetFileName@ImagePath@@CA?AU_UNICODE_STRING@@XZ; ImagePath::GetFileName(void)
0x1800d0ca3  or      r9d, 0FFFFFFFFh; cchCount2
0x1800d0ca7  mov     [rsp+40h+bIgnoreCase], r12d; bIgnoreCase
0x1800d0cac  lea     r8, aExplorerExe; "explorer.exe"
0x1800d0cb3  movzx   edx, word ptr [rax]
0x1800d0cb6  mov     rcx, [rax+8]; lpString1
0x1800d0cba  shr     edx, 1; cchCount1
0x1800d0cbc  call    cs:__imp_CompareStringOrdinal
0x1800d0cc3  nop     dword ptr [rax+rax+00h]
0x1800d0cc8  cmp     eax, ebx
0x1800d0cca  jnz     loc_1800D0DB8
0x1800d0cd0  lea     r8, [rbp+phModule]; phModule
0x1800d0cd4  mov     [rbp+phModule], 0
0x1800d0cdc  lea     rdx, aExtMsWinNtuser_0; "ext-ms-win-ntuser-window-l1-1-0.dll"
0x1800d0ce3  xor     ecx, ecx; dwFlags
0x1800d0ce5  call    cs:__imp_GetModuleHandleExW
0x1800d0cec  nop     dword ptr [rax+rax+00h]
0x1800d0cf1  test    eax, eax
0x1800d0cf3  jz      loc_1800D0DAF
0x1800d0cf9  mov     rcx, [rbp+phModule]; hModule
0x1800d0cfd  lea     rdx, aGetshellwindow; "GetShellWindow"
0x1800d0d04  call    cs:__imp_GetProcAddress
0x1800d0d0b  nop     dword ptr [rax+rax+00h]
0x1800d0d10  mov     rcx, [rbp+phModule]; hModule
0x1800d0d14  lea     rdx, aGetwindowthrea; "GetWindowThreadProcessId"
0x1800d0d1b  mov     r14, rax
0x1800d0d1e  call    cs:__imp_GetProcAddress
0x1800d0d25  nop     dword ptr [rax+rax+00h]
0x1800d0d2a  mov     rcx, [rbp+phModule]; hModule
0x1800d0d2e  lea     rdx, aIsguithread; "IsGUIThread"
0x1800d0d35  mov     rdi, rax
0x1800d0d38  call    cs:__imp_GetProcAddress
0x1800d0d3f  nop     dword ptr [rax+rax+00h]
0x1800d0d44  mov     rsi, rax
0x1800d0d47  test    r14, r14
0x1800d0d4a  jz      short loc_1800D0DAA
0x1800d0d4c  test    rdi, rdi
0x1800d0d4f  jz      short loc_1800D0DAA
0x1800d0d51  test    rax, rax
0x1800d0d54  jz      short loc_1800D0DAA
0x1800d0d56  mov     rax, r14
0x1800d0d59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d0d5e  test    rax, rax
0x1800d0d61  jz      short loc_1800D0D98
0x1800d0d63  mov     rcx, rax
0x1800d0d66  mov     [rbp+arg_0], 0
0x1800d0d6d  mov     rax, rdi
0x1800d0d70  lea     rdx, [rbp+arg_0]
0x1800d0d74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d0d79  test    eax, eax
0x1800d0d7b  jnz     short loc_1800D0D82
0x1800d0d7d  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800d0d82  call    cs:__imp_GetCurrentProcessId
0x1800d0d89  nop     dword ptr [rax+rax+00h]
0x1800d0d8e  cmp     eax, [rbp+arg_0]
0x1800d0d91  jnz     short loc_1800D0DAF
0x1800d0d93  mov     bl, r12b
0x1800d0d96  jmp     short loc_1800D0DAF
0x1800d0d98  xor     ecx, ecx
0x1800d0d9a  mov     rax, rsi
0x1800d0d9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d0da2  test    eax, eax
0x1800d0da4  cmovnz  ebx, r12d
0x1800d0da8  jmp     short loc_1800D0DAF
0x1800d0daa  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800d0daf  lea     rcx, [rbp+phModule]
0x1800d0db3  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x1800d0db8  mov     al, bl
0x1800d0dba  xchg    al, cs:?g_isDesktopShellProcessState@IsDesktopShellProcessDetails@@3U?$atomic@W4IsDesktopShellProcessState@IsDesktopShellProcessDetails@@@std@@A; std::atomic<IsDesktopShellProcessDetails::IsDesktopShellProcessState> IsDesktopShellProcessDetails::g_isDesktopShellProcessState
0x1800d0dc0  cmp     bl, r12b
0x1800d0dc3  mov     rbx, [rsp+40h+arg_10]
0x1800d0dcb  setz    al
0x1800d0dce  add     rsp, 40h
0x1800d0dd2  pop     r14
0x1800d0dd4  pop     r12
0x1800d0dd6  pop     rdi
0x1800d0dd7  pop     rsi
0x1800d0dd8  pop     rbp
0x1800d0dd9  retn
```
