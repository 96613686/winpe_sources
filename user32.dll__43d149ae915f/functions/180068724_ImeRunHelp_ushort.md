# ImeRunHelp(ushort *)

- ea: `0x180068724`
- end: `0x180068963`
- name: `?ImeRunHelp@@YAXPEAG@Z`
- size: `575`
- prototype: `void __fastcall(wchar_t *Source)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x1800151d0`

## callees

- `0x18005b990`
- `0x1800673d0`
- `0x180068724`
- `0x180092078`
- `0x180096dc5`
- `0x180096e00`

## import_xrefs

- `ntdll!wcsncpy_s` at `0x18006881e`
- `ntdll!wcsncpy_s` at `0x18006884f`
- `ntdll!wcsncpy_s` at `0x18006886e`
- `ntdll!wcsncpy_s` at `0x18006881e`
- `ntdll!wcsncpy_s` at `0x18006884f`
- `ntdll!wcsncpy_s` at `0x18006886e`
- `ntdll!_wcsicmp` at `0x180068783`
- `ntdll!_wcsicmp` at `0x180068783`
- `ntdll!NtClose` at `0x180068927`
- `ntdll!NtClose` at `0x180068932`
- `ntdll!NtClose` at `0x180068927`
- `ntdll!NtClose` at `0x180068932`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x180068909`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x180068909`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x1800687cd`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x1800687cd`

## pseudocode

```c
void __fastcall ImeRunHelp(wchar_t *Source)
{
  __int64 v2; // rdi
  UINT SystemWindowsDirectoryW; // eax
  __int64 v4; // rbx
  int v5; // edx
  int v6; // r8d
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+50h] [rbp-B0h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+70h] [rbp-90h] BYREF
  WCHAR Buffer[264]; // [rsp+E0h] [rbp-20h] BYREF
  wchar_t Destination[520]; // [rsp+2F0h] [rbp+1F0h] BYREF

  v2 = -1;
  do
    ++v2;
  while ( Source[v2] );
  if ( (unsigned int)v2 > 4 && !_wcsicmp(&Source[(unsigned int)v2 - 4], L".HLP") )
  {
    WinHelpW(0, Source, 0xBu, 0);
    return;
  }
  memset_0(&StartupInfo, 0, sizeof(StartupInfo));
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  SystemWindowsDirectoryW = GetSystemWindowsDirectoryW(Buffer, 0x105u);
  v4 = SystemWindowsDirectoryW;
  if ( SystemWindowsDirectoryW < 0x105 )
  {
    if ( SystemWindowsDirectoryW )
    {
      if ( Buffer[SystemWindowsDirectoryW - 1] != 92 )
      {
        Buffer[SystemWindowsDirectoryW] = 92;
        v4 = SystemWindowsDirectoryW + 1;
        if ( (unsigned int)v4 >= 0x105 )
          return;
      }
      if ( (unsigned int)(261 - v4) <= 7 )
        return;
      wcsncpy_s(&Buffer[v4], (unsigned int)(261 - v4), L"hh.exe ", 0xFFFFFFFFFFFFFFFFuLL);
      v4 = (unsigned int)(v4 + 7);
    }
    if ( (_DWORD)v4 && (unsigned int)(v4 + v2) < 0x208 )
    {
      wcsncpy_s(Destination, 0x208u, Buffer, 0x208u);
      wcsncpy_s(&Destination[v4], 520LL - (unsigned int)v4, Source, 0xFFFFFFFFFFFFFFFFuLL);
      memset_0(&StartupInfo, 0, sizeof(StartupInfo));
      StartupInfo.cb = 104;
      StartupInfo.wShowWindow = 5;
      StartupInfo.dwFlags = 65;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_SS(*((_QWORD *)WPP_GLOBAL_Control + 2), v5, v6, (unsigned int)Buffer, (__int64)Source);
      }
      if ( CreateProcessW(Buffer, Destination, 0, 0, 0, 0x20u, 0, 0, &StartupInfo, &ProcessInformation) )
      {
        WaitForInputIdle(ProcessInformation.hProcess, 0x2710u);
        NtClose(ProcessInformation.hProcess);
        NtClose(ProcessInformation.hThread);
      }
    }
  }
}

```

## disassembly

```asm
0x180068724  mov     [rsp-8+arg_8], rbx
0x180068729  mov     [rsp-8+arg_10], rsi
0x18006872e  push    rbp
0x18006872f  push    rdi
0x180068730  push    r12
0x180068732  push    r14
0x180068734  push    r15
0x180068736  lea     rbp, [rsp-610h]
0x18006873e  sub     rsp, 710h
0x180068745  mov     rax, cs:__security_cookie
0x18006874c  xor     rax, rsp
0x18006874f  mov     [rbp+630h+var_30], rax
0x180068756  or      r12, 0FFFFFFFFFFFFFFFFh
0x18006875a  mov     r14, rcx
0x18006875d  mov     rdi, r12
0x180068760  xor     r15d, r15d
0x180068763  inc     rdi
0x180068766  cmp     [rcx+rdi*2], r15w
0x18006876b  jnz     short loc_180068763
0x18006876d  cmp     edi, 4
0x180068770  jbe     short loc_1800687A3
0x180068772  mov     eax, edi
0x180068774  lea     rdx, aHlp; ".HLP"
0x18006877b  add     rax, 0FFFFFFFFFFFFFFFCh
0x18006877f  lea     rcx, [rcx+rax*2]; String1
0x180068783  call    cs:__imp__wcsicmp
0x180068789  test    eax, eax
0x18006878b  jnz     short loc_1800687A3
0x18006878d  xor     r9d, r9d; dwData
0x180068790  lea     r8d, [rax+0Bh]; uCommand
0x180068794  mov     rdx, r14; lpszHelp
0x180068797  xor     ecx, ecx; hWndMain
0x180068799  call    WinHelpW
0x18006879e  jmp     loc_180068938
0x1800687a3  xor     edx, edx; Val
0x1800687a5  lea     rcx, [rsp+730h+StartupInfo]; void *
0x1800687aa  lea     r8d, [rdx+68h]; Size
0x1800687ae  call    memset_0
0x1800687b3  xorps   xmm0, xmm0
0x1800687b6  lea     rcx, [rbp+630h+Buffer]; lpBuffer
0x1800687ba  xor     eax, eax
0x1800687bc  mov     esi, 105h
0x1800687c1  mov     edx, esi; uSize
0x1800687c3  mov     qword ptr [rsp+730h+ProcessInformation.dwProcessId], rax
0x1800687c8  movups  xmmword ptr [rsp+730h+ProcessInformation.hProcess], xmm0
0x1800687cd  call    cs:__imp_GetSystemWindowsDirectoryW
0x1800687d3  mov     ebx, eax
0x1800687d5  cmp     eax, esi
0x1800687d7  jnb     loc_180068938
0x1800687dd  test    eax, eax
0x1800687df  jz      short loc_180068827
0x1800687e1  lea     ecx, [rbx-1]
0x1800687e4  mov     eax, 5Ch ; '\'
0x1800687e9  cmp     [rbp+rcx*2+630h+Buffer], ax
0x1800687ee  jz      short loc_1800687FF
0x1800687f0  mov     [rbp+rbx*2+630h+Buffer], ax
0x1800687f5  inc     ebx
0x1800687f7  cmp     ebx, esi
0x1800687f9  jnb     loc_180068938
0x1800687ff  sub     esi, ebx
0x180068801  cmp     esi, 7
0x180068804  jbe     loc_180068938
0x18006880a  lea     rcx, [rbp+630h+Buffer]
0x18006880e  mov     edx, esi; SizeInWords
0x180068810  lea     rcx, [rcx+rbx*2]; Destination
0x180068814  mov     r9, r12; MaxCount
0x180068817  lea     r8, aHhExe; "hh.exe "
0x18006881e  call    cs:__imp_wcsncpy_s
0x180068824  add     ebx, 7
0x180068827  test    ebx, ebx
0x180068829  jz      loc_180068938
0x18006882f  lea     eax, [rbx+rdi]
0x180068832  mov     edi, 208h
0x180068837  cmp     eax, edi
0x180068839  jnb     loc_180068938
0x18006883f  mov     r9d, edi; MaxCount
0x180068842  lea     r8, [rbp+630h+Buffer]; Source
0x180068846  mov     edx, edi; SizeInWords
0x180068848  lea     rcx, [rbp+630h+Destination]; Destination
0x18006884f  call    cs:__imp_wcsncpy_s
0x180068855  mov     eax, ebx
0x180068857  lea     rcx, [rbp+630h+Destination]
0x18006885e  sub     rdi, rax
0x180068861  lea     rcx, [rcx+rbx*2]; Destination
0x180068865  mov     rdx, rdi; SizeInWords
0x180068868  mov     r9, r12; MaxCount
0x18006886b  mov     r8, r14; Source
0x18006886e  call    cs:__imp_wcsncpy_s
0x180068874  xor     edx, edx; Val
0x180068876  lea     rcx, [rsp+730h+StartupInfo]; void *
0x18006887b  lea     r8d, [rdx+68h]; Size
0x18006887f  call    memset_0
0x180068884  mov     eax, 5
0x180068889  mov     [rsp+730h+StartupInfo.cb], 68h ; 'h'
0x180068891  mov     [rbp+630h+StartupInfo.wShowWindow], ax
0x180068895  mov     [rbp+630h+StartupInfo.dwFlags], 41h ; 'A'
0x18006889c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800688a3  lea     rax, WPP_GLOBAL_Control
0x1800688aa  cmp     rcx, rax
0x1800688ad  jz      short loc_1800688CD
0x1800688af  test    byte ptr [rcx+1Ch], 10h
0x1800688b3  jz      short loc_1800688CD
0x1800688b5  cmp     byte ptr [rcx+19h], 4
0x1800688b9  jb      short loc_1800688CD
0x1800688bb  mov     rcx, [rcx+10h]
0x1800688bf  lea     r9, [rbp+630h+Buffer]
0x1800688c3  mov     qword ptr [rsp+730h+bInheritHandles], r14
0x1800688c8  call    WPP_SF_SS
0x1800688cd  lea     rax, [rsp+730h+ProcessInformation]
0x1800688d2  xor     r9d, r9d; lpThreadAttributes
0x1800688d5  mov     [rsp+730h+lpProcessInformation], rax; lpProcessInformation
0x1800688da  lea     rdx, [rbp+630h+Destination]; lpCommandLine
0x1800688e1  lea     rax, [rsp+730h+StartupInfo]
0x1800688e6  xor     r8d, r8d; lpProcessAttributes
0x1800688e9  mov     [rsp+730h+lpStartupInfo], rax; lpStartupInfo
0x1800688ee  lea     rcx, [rbp+630h+Buffer]; lpApplicationName
0x1800688f2  mov     [rsp+730h+lpCurrentDirectory], r15; lpCurrentDirectory
0x1800688f7  mov     [rsp+730h+lpEnvironment], r15; lpEnvironment
0x1800688fc  mov     [rsp+730h+dwCreationFlags], 20h ; ' '; dwCreationFlags
0x180068904  mov     [rsp+730h+bInheritHandles], r15d; bInheritHandles
0x180068909  call    cs:__imp_CreateProcessW
0x18006890f  test    eax, eax
0x180068911  jz      short loc_180068938
0x180068913  mov     rcx, [rsp+730h+ProcessInformation.hProcess]; hProcess
0x180068918  mov     edx, 2710h; dwMilliseconds
0x18006891d  call    WaitForInputIdle
0x180068922  mov     rcx, [rsp+730h+ProcessInformation.hProcess]; Handle
0x180068927  call    cs:__imp_NtClose
0x18006892d  mov     rcx, [rsp+730h+ProcessInformation.hThread]; Handle
0x180068932  call    cs:__imp_NtClose
0x180068938  mov     rcx, [rbp+630h+var_30]
0x18006893f  xor     rcx, rsp; StackCookie
0x180068942  call    __security_check_cookie
0x180068947  lea     r11, [rsp+730h+var_20]
0x18006894f  mov     rbx, [r11+38h]
0x180068953  mov     rsi, [r11+40h]
0x180068957  mov     rsp, r11
0x18006895a  pop     r15
0x18006895c  pop     r14
0x18006895e  pop     r12
0x180068960  pop     rdi
0x180068961  pop     rbp
0x180068962  retn
```
