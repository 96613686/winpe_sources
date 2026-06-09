# IsDesktopShellProcess(void)

- ea: `0x1800caac0`
- end: `0x1800cacc8`
- name: `?IsDesktopShellProcess@@YA_NXZ`
- size: `520`
- prototype: `bool(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800ad95c`

## callees

- `0x18008e98c`
- `0x1800ae018`
- `0x1800c7544`
- `0x1800caac0`
- `0x18010b010`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x1800cab05`
- `ntdll!RtlInitUnicodeString` at `0x1800cab05`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800cac0a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800cac1e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800cac32`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800cac0a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800cac1e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800cac32`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800cabf1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800cabf1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800cac76`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800cac76`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800cab94`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800cabce`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800cab94`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800cabce`
- `api-ms-win-core-apiquery-l1-1-0!ApiSetQueryApiSetPresence` at `0x1800cab17`
- `api-ms-win-core-apiquery-l1-1-0!ApiSetQueryApiSetPresence` at `0x1800cab17`

## string_xrefs

- `0x1800cabe8`: `ext-ms-win-ntuser-window-l1-1-0.dll`
- `0x1800cac14`: `GetWindowThreadProcessId`
- `0x1800cac28`: `IsGUIThread`

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
0x1800caac0  mov     [rsp-28h+arg_10], rbx
0x1800caac5  push    rbp
0x1800caac6  push    rsi
0x1800caac7  push    rdi
0x1800caac8  push    r12
0x1800caaca  push    r14
0x1800caacc  mov     rbp, rsp
0x1800caacf  sub     rsp, 40h
0x1800caad3  mov     bl, cs:?g_isDesktopShellProcessState@IsDesktopShellProcessDetails@@3U?$atomic@W4IsDesktopShellProcessState@IsDesktopShellProcessDetails@@@std@@A; std::atomic<IsDesktopShellProcessDetails::IsDesktopShellProcessState> IsDesktopShellProcessDetails::g_isDesktopShellProcessState
0x1800caad9  mov     r12d, 1
0x1800caadf  mov     al, cs:?g_isDesktopShellProcessState@IsDesktopShellProcessDetails@@3U?$atomic@W4IsDesktopShellProcessState@IsDesktopShellProcessDetails@@@std@@A; std::atomic<IsDesktopShellProcessDetails::IsDesktopShellProcessState> IsDesktopShellProcessDetails::g_isDesktopShellProcessState
0x1800caae5  nop
0x1800caae6  test    al, al
0x1800caae8  jnz     loc_1800CACAE
0x1800caaee  xorps   xmm0, xmm0
0x1800caaf1  lea     rdx, aExtMsWinNtuser; "ext-ms-win-ntuser-window-l1-1-0"
0x1800caaf8  lea     rcx, [rbp+DestinationString]; DestinationString
0x1800caafc  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x1800cab00  lea     ebx, [r12+1]
0x1800cab05  call    cs:__imp_RtlInitUnicodeString
0x1800cab0b  lea     rdx, [rbp+arg_0]
0x1800cab0f  mov     byte ptr [rbp+arg_0], 0
0x1800cab13  lea     rcx, [rbp+DestinationString]
0x1800cab17  call    cs:__imp_ApiSetQueryApiSetPresence
0x1800cab1d  test    eax, eax
0x1800cab1f  jns     short loc_1800CAB2B
0x1800cab21  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800cab26  jmp     loc_1800CACA6
0x1800cab2b  cmp     byte ptr [rbp+arg_0], 0
0x1800cab2f  jz      loc_1800CACA6
0x1800cab35  mov     rax, gs:60h
0x1800cab3e  cmp     dword ptr [rax+2C0h], 0
0x1800cab45  jz      loc_1800CACA6
0x1800cab4b  mov     rax, gs:60h
0x1800cab54  mov     rax, [rax+20h]
0x1800cab58  test    rax, rax
0x1800cab5b  jz      short loc_1800CABAC
0x1800cab5d  movzx   ecx, word ptr [rax+0C0h]
0x1800cab64  cmp     cx, bx
0x1800cab67  jb      short loc_1800CABAC
0x1800cab69  cmp     ecx, 10h
0x1800cab6c  jb      short loc_1800CABA1
0x1800cab6e  mov     rax, [rax+0C8h]
0x1800cab75  mov     edx, 8; cchCount1
0x1800cab7a  mov     r8, cs:lpString2; lpString2
0x1800cab81  add     rax, 0FFFFFFFFFFFFFFF0h
0x1800cab85  shr     rcx, 1
0x1800cab88  mov     r9d, edx; cchCount2
0x1800cab8b  mov     [rsp+40h+bIgnoreCase], r12d; bIgnoreCase
0x1800cab90  lea     rcx, [rax+rcx*2]; lpString1
0x1800cab94  call    cs:__imp_CompareStringOrdinal
0x1800cab9a  cmp     eax, ebx
0x1800cab9c  setnz   al
0x1800cab9f  jmp     short loc_1800CABA4
0x1800caba1  mov     al, r12b
0x1800caba4  test    al, al
0x1800caba6  jnz     loc_1800CACA6
0x1800cabac  lea     rcx, [rbp+DestinationString]; retstr
0x1800cabb0  call    ?GetFileName@ImagePath@@CA?AU_UNICODE_STRING@@XZ; ImagePath::GetFileName(void)
0x1800cabb5  or      r9d, 0FFFFFFFFh; cchCount2
0x1800cabb9  mov     [rsp+40h+bIgnoreCase], r12d; bIgnoreCase
0x1800cabbe  lea     r8, aExplorerExe; "explorer.exe"
0x1800cabc5  movzx   edx, word ptr [rax]
0x1800cabc8  mov     rcx, [rax+8]; lpString1
0x1800cabcc  shr     edx, 1; cchCount1
0x1800cabce  call    cs:__imp_CompareStringOrdinal
0x1800cabd4  cmp     eax, ebx
0x1800cabd6  jnz     loc_1800CACA6
0x1800cabdc  lea     r8, [rbp+phModule]; phModule
0x1800cabe0  mov     [rbp+phModule], 0
0x1800cabe8  lea     rdx, aExtMsWinNtuser_0; "ext-ms-win-ntuser-window-l1-1-0.dll"
0x1800cabef  xor     ecx, ecx; dwFlags
0x1800cabf1  call    cs:__imp_GetModuleHandleExW
0x1800cabf7  test    eax, eax
0x1800cabf9  jz      loc_1800CAC9D
0x1800cabff  mov     rcx, [rbp+phModule]; hModule
0x1800cac03  lea     rdx, aGetshellwindow; "GetShellWindow"
0x1800cac0a  call    cs:__imp_GetProcAddress
0x1800cac10  mov     rcx, [rbp+phModule]; hModule
0x1800cac14  lea     rdx, aGetwindowthrea; "GetWindowThreadProcessId"
0x1800cac1b  mov     r14, rax
0x1800cac1e  call    cs:__imp_GetProcAddress
0x1800cac24  mov     rcx, [rbp+phModule]; hModule
0x1800cac28  lea     rdx, aIsguithread; "IsGUIThread"
0x1800cac2f  mov     rdi, rax
0x1800cac32  call    cs:__imp_GetProcAddress
0x1800cac38  mov     rsi, rax
0x1800cac3b  test    r14, r14
0x1800cac3e  jz      short loc_1800CAC98
0x1800cac40  test    rdi, rdi
0x1800cac43  jz      short loc_1800CAC98
0x1800cac45  test    rax, rax
0x1800cac48  jz      short loc_1800CAC98
0x1800cac4a  mov     rax, r14
0x1800cac4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cac52  test    rax, rax
0x1800cac55  jz      short loc_1800CAC86
0x1800cac57  mov     rcx, rax
0x1800cac5a  mov     [rbp+arg_0], 0
0x1800cac61  mov     rax, rdi
0x1800cac64  lea     rdx, [rbp+arg_0]
0x1800cac68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cac6d  test    eax, eax
0x1800cac6f  jnz     short loc_1800CAC76
0x1800cac71  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800cac76  call    cs:__imp_GetCurrentProcessId
0x1800cac7c  cmp     eax, [rbp+arg_0]
0x1800cac7f  jnz     short loc_1800CAC9D
0x1800cac81  mov     bl, r12b
0x1800cac84  jmp     short loc_1800CAC9D
0x1800cac86  xor     ecx, ecx
0x1800cac88  mov     rax, rsi
0x1800cac8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cac90  test    eax, eax
0x1800cac92  cmovnz  ebx, r12d
0x1800cac96  jmp     short loc_1800CAC9D
0x1800cac98  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800cac9d  lea     rcx, [rbp+phModule]
0x1800caca1  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x1800caca6  mov     al, bl
0x1800caca8  xchg    al, cs:?g_isDesktopShellProcessState@IsDesktopShellProcessDetails@@3U?$atomic@W4IsDesktopShellProcessState@IsDesktopShellProcessDetails@@@std@@A; std::atomic<IsDesktopShellProcessDetails::IsDesktopShellProcessState> IsDesktopShellProcessDetails::g_isDesktopShellProcessState
0x1800cacae  cmp     bl, r12b
0x1800cacb1  mov     rbx, [rsp+40h+arg_10]
0x1800cacb9  setz    al
0x1800cacbc  add     rsp, 40h
0x1800cacc0  pop     r14
0x1800cacc2  pop     r12
0x1800cacc4  pop     rdi
0x1800cacc5  pop     rsi
0x1800cacc6  pop     rbp
0x1800cacc7  retn
```
