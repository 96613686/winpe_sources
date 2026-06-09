# RegisterAspNetMMC(int)

- ea: `0x18003c630`
- end: `0x18003c86b`
- name: `?RegisterAspNetMMC@@YAJH@Z`
- size: `571`
- prototype: `__int64 __fastcall(int)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18003dd10`
- `0x18003ef38`

## callees

- `0x180007824`
- `0x18003abe4`
- `0x18003c630`
- `0x18003d288`
- `0x18004d030`
- `0x18004d350`
- `0x1800653c0`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18003c813`
- `KERNEL32!CloseHandle` at `0x18003c81e`
- `KERNEL32!CloseHandle` at `0x18003c813`
- `KERNEL32!CloseHandle` at `0x18003c81e`
- `KERNEL32!WaitForSingleObject` at `0x18003c804`
- `KERNEL32!WaitForSingleObject` at `0x18003c804`
- `KERNEL32!CreateProcessW` at `0x18003c7e7`
- `KERNEL32!CreateProcessW` at `0x18003c7e7`

## string_xrefs

- `0x18003c679`: `Setting AspNetMMCExt Registry keys`
- `0x18003c687`: `Removing AspNetMMCExt Registry keys`
- `0x18003c776`: `\AspNetMmcExt.dll /tlb:AspNetMmcExt.tlb`

## pseudocode

```c
__int64 __fastcall RegisterAspNetMMC(int a1)
{
  const char *v2; // rsi
  __int64 v3; // rdx
  WCHAR *v4; // rcx
  WCHAR v5; // ax
  WCHAR *v6; // rax
  unsigned int LastWin32Error; // ebx
  struct _PROCESS_INFORMATION lpProcessInformation_8; // [rsp+58h] [rbp-B0h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+78h] [rbp-90h] BYREF
  WCHAR CommandLine[264]; // [rsp+E8h] [rbp-20h] BYREF

  memset_0(CommandLine, 0, 0x20Au);
  v2 = "Removing AspNetMMCExt Registry keys";
  if ( a1 )
    v2 = "Setting AspNetMMCExt Registry keys";
  CSetupLogging::Log(1, "RegisterAspNetMMC", 0, v2, 0);
  memset_0(&StartupInfo.cb + 1, 0, 0x64u);
  StartupInfo.cb = 104;
  memset(&lpProcessInformation_8, 0, sizeof(lpProcessInformation_8));
  SetAspNetMMCKeys(a1);
  v3 = 261;
  v4 = CommandLine;
  do
  {
    if ( v3 == -2147483385 )
      break;
    v5 = *(WCHAR *)((char *)v4 + (char *)&Names::s_wszInstallDirectory - (char *)CommandLine);
    if ( !v5 )
      break;
    *v4++ = v5;
    --v3;
  }
  while ( v3 );
  v6 = v4 - 1;
  if ( v3 )
    v6 = v4;
  *v6 = 0;
  LastWin32Error = v3 == 0 ? 0x8007007A : 0;
  if ( v3 )
  {
    LastWin32Error = StringCchCatW(CommandLine, 0x105u, L"\\Regasm.exe ");
    if ( !LastWin32Error )
    {
      LastWin32Error = StringCchCatW(CommandLine, 0x105u, &Names::s_wszInstallDirectory);
      if ( !LastWin32Error )
      {
        LastWin32Error = StringCchCatW(CommandLine, 0x105u, L"\\AspNetMmcExt.dll /tlb:AspNetMmcExt.tlb");
        if ( !LastWin32Error && (a1 || (LastWin32Error = StringCchCatW(CommandLine, 0x105u, L" /unregister")) == 0) )
        {
          if ( !CreateProcessW(0, CommandLine, 0, 0, 0, 0x8000000u, 0, 0, &StartupInfo, &lpProcessInformation_8)
            || WaitForSingleObject(lpProcessInformation_8.hProcess, 0xFFFFFFFF) == -1 )
          {
            LastWin32Error = GetLastWin32Error();
          }
          else
          {
            CloseHandle(lpProcessInformation_8.hProcess);
            CloseHandle(lpProcessInformation_8.hThread);
          }
        }
      }
    }
  }
  CSetupLogging::Log(LastWin32Error, "RegisterAspNetMMC", 0, v2, 0);
  return LastWin32Error;
}

```

## disassembly

```asm
0x18003c630  mov     rax, rsp
0x18003c633  mov     [rax+10h], rbx
0x18003c637  mov     [rax+18h], rsi
0x18003c63b  mov     [rax+20h], rdi
0x18003c63f  push    rbp
0x18003c640  push    r14
0x18003c642  push    r15
0x18003c644  lea     rbp, [rax-218h]
0x18003c64b  sub     rsp, 300h
0x18003c652  mov     rax, cs:__security_cookie
0x18003c659  xor     rax, rsp
0x18003c65c  mov     [rbp+210h+var_20], rax
0x18003c663  mov     edi, ecx
0x18003c665  xor     edx, edx; Val
0x18003c667  lea     rcx, [rbp+210h+CommandLine]; void *
0x18003c66b  mov     r8d, 20Ah; Size
0x18003c671  call    memset_0
0x18003c676  xor     r14d, r14d
0x18003c679  lea     rax, aSettingAspnetm; "Setting AspNetMMCExt Registry keys"
0x18003c680  test    edi, edi
0x18003c682  mov     qword ptr [rsp+310h+bInheritHandles], r14; unsigned __int16 *
0x18003c687  lea     rsi, aRemovingAspnet; "Removing AspNetMMCExt Registry keys"
0x18003c68e  cmovnz  rsi, rax
0x18003c692  lea     rdx, aRegisteraspnet_2; "RegisterAspNetMMC"
0x18003c699  mov     r9, rsi; char *
0x18003c69c  lea     ecx, [r14+1]; int
0x18003c6a0  xor     r8d, r8d; unsigned int
0x18003c6a3  call    ?Log@CSetupLogging@@SAXJPEBDI0PEBG@Z; CSetupLogging::Log(long,char const *,uint,char const *,ushort const *)
0x18003c6a8  xor     edx, edx; Val
0x18003c6aa  lea     r8d, [r14+64h]; Size
0x18003c6ae  lea     rcx, [rsp+310h+StartupInfo+4]; void *
0x18003c6b3  call    memset_0
0x18003c6b8  xorps   xmm0, xmm0
0x18003c6bb  mov     [rsp+310h+StartupInfo.cb], 68h ; 'h'
0x18003c6c3  xor     eax, eax
0x18003c6c5  mov     ecx, edi; int
0x18003c6c7  movups  xmmword ptr [rsp+310h+lpProcessInformation+8], xmm0
0x18003c6cc  mov     [rsp+310h+var_2B0], rax
0x18003c6d1  call    ?SetAspNetMMCKeys@@YAJH@Z; SetAspNetMMCKeys(int)
0x18003c6d6  lea     r8, ?s_wszInstallDirectory@Names@@0PAGA; ushort near * Names::s_wszInstallDirectory
0x18003c6dd  mov     r15d, 105h
0x18003c6e3  lea     rax, [rbp+210h+CommandLine]
0x18003c6e7  mov     edx, r15d
0x18003c6ea  sub     r8, rax
0x18003c6ed  lea     rcx, [rbp+210h+CommandLine]
0x18003c6f1  lea     rax, [rdx+7FFFFEF9h]
0x18003c6f8  test    rax, rax
0x18003c6fb  jz      short loc_18003C714
0x18003c6fd  movzx   eax, word ptr [r8+rcx]
0x18003c702  test    ax, ax
0x18003c705  jz      short loc_18003C714
0x18003c707  mov     [rcx], ax
0x18003c70a  add     rcx, 2
0x18003c70e  sub     rdx, 1
0x18003c712  jnz     short loc_18003C6F1
0x18003c714  test    rdx, rdx
0x18003c717  lea     rax, [rcx-2]
0x18003c71b  cmovnz  rax, rcx
0x18003c71f  mov     [rax], r14w
0x18003c723  mov     rax, rdx
0x18003c726  neg     rax
0x18003c729  sbb     ebx, ebx
0x18003c72b  not     ebx
0x18003c72d  and     ebx, 8007007Ah
0x18003c733  test    rdx, rdx
0x18003c736  jz      loc_18003C824
0x18003c73c  lea     r8, aRegasmExe; "\\Regasm.exe "
0x18003c743  mov     rdx, r15; unsigned __int64
0x18003c746  lea     rcx, [rbp+210h+CommandLine]; unsigned __int16 *
0x18003c74a  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18003c74f  mov     ebx, eax
0x18003c751  test    eax, eax
0x18003c753  jnz     loc_18003C824
0x18003c759  lea     r8, ?s_wszInstallDirectory@Names@@0PAGA; unsigned __int16 *
0x18003c760  mov     rdx, r15; unsigned __int64
0x18003c763  lea     rcx, [rbp+210h+CommandLine]; unsigned __int16 *
0x18003c767  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18003c76c  mov     ebx, eax
0x18003c76e  test    eax, eax
0x18003c770  jnz     loc_18003C824
0x18003c776  lea     r8, aAspnetmmcextDl; "\\AspNetMmcExt.dll /tlb:AspNetMmcExt.tl"...
0x18003c77d  mov     rdx, r15; unsigned __int64
0x18003c780  lea     rcx, [rbp+210h+CommandLine]; unsigned __int16 *
0x18003c784  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18003c789  mov     ebx, eax
0x18003c78b  test    eax, eax
0x18003c78d  jnz     loc_18003C824
0x18003c793  test    edi, edi
0x18003c795  jnz     short loc_18003C7B0
0x18003c797  lea     r8, aUnregister; " /unregister"
0x18003c79e  mov     rdx, r15; unsigned __int64
0x18003c7a1  lea     rcx, [rbp+210h+CommandLine]; unsigned __int16 *
0x18003c7a5  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18003c7aa  mov     ebx, eax
0x18003c7ac  test    eax, eax
0x18003c7ae  jnz     short loc_18003C824
0x18003c7b0  lea     rax, [rsp+310h+lpProcessInformation+8]
0x18003c7b5  xor     r9d, r9d; lpThreadAttributes
0x18003c7b8  mov     [rsp+310h+lpProcessInformation], rax; lpProcessInformation
0x18003c7bd  lea     rdx, [rbp+210h+CommandLine]; lpCommandLine
0x18003c7c1  lea     rax, [rsp+310h+StartupInfo]
0x18003c7c6  xor     r8d, r8d; lpProcessAttributes
0x18003c7c9  mov     [rsp+310h+lpStartupInfo], rax; lpStartupInfo
0x18003c7ce  xor     ecx, ecx; lpApplicationName
0x18003c7d0  mov     [rsp+310h+lpCurrentDirectory], r14; lpCurrentDirectory
0x18003c7d5  mov     [rsp+310h+lpEnvironment], r14; lpEnvironment
0x18003c7da  mov     [rsp+310h+dwCreationFlags], 8000000h; dwCreationFlags
0x18003c7e2  mov     [rsp+310h+bInheritHandles], r14d; bInheritHandles
0x18003c7e7  call    cs:__imp_CreateProcessW
0x18003c7ed  test    eax, eax
0x18003c7ef  jnz     short loc_18003C7FA
0x18003c7f1  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x18003c7f6  mov     ebx, eax
0x18003c7f8  jmp     short loc_18003C824
0x18003c7fa  mov     rcx, [rsp+310h+lpProcessInformation+8]; hHandle
0x18003c7ff  or      edi, 0FFFFFFFFh
0x18003c802  mov     edx, edi; dwMilliseconds
0x18003c804  call    cs:__imp_WaitForSingleObject
0x18003c80a  cmp     eax, edi
0x18003c80c  jz      short loc_18003C7F1
0x18003c80e  mov     rcx, [rsp+310h+lpProcessInformation+8]; hObject
0x18003c813  call    cs:__imp_CloseHandle
0x18003c819  mov     rcx, [rsp+310h+hObject]; hObject
0x18003c81e  call    cs:__imp_CloseHandle
0x18003c824  mov     r9, rsi; char *
0x18003c827  mov     qword ptr [rsp+310h+bInheritHandles], r14; unsigned __int16 *
0x18003c82c  xor     r8d, r8d; unsigned int
0x18003c82f  lea     rdx, aRegisteraspnet_2; "RegisterAspNetMMC"
0x18003c836  mov     ecx, ebx; int
0x18003c838  call    ?Log@CSetupLogging@@SAXJPEBDI0PEBG@Z; CSetupLogging::Log(long,char const *,uint,char const *,ushort const *)
0x18003c83d  mov     eax, ebx
0x18003c83f  mov     rcx, [rbp+210h+var_20]
0x18003c846  xor     rcx, rsp; StackCookie
0x18003c849  call    __security_check_cookie
0x18003c84e  lea     r11, [rsp+310h+var_10]
0x18003c856  mov     rbx, [r11+28h]
0x18003c85a  mov     rsi, [r11+30h]
0x18003c85e  mov     rdi, [r11+38h]
0x18003c862  mov     rsp, r11
0x18003c865  pop     r15
0x18003c867  pop     r14
0x18003c869  pop     rbp
0x18003c86a  retn
```
