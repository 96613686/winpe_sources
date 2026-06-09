# Windows::Configuration::RamMB(void)

- ea: `0x180044940`
- end: `0x180044a1e`
- name: `?RamMB@Configuration@Windows@@UEAAIXZ`
- size: `222`
- prototype: `unsigned int __fastcall(Windows::Configuration *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, service_task, installer_update`

## callees

- `0x180007660`
- `0x18000856c`
- `0x1800209fc`
- `0x180023458`
- `0x180036198`
- `0x180044940`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GlobalMemoryStatusEx` at `0x18004498b`
- `api-ms-win-core-sysinfo-l1-1-0!GlobalMemoryStatusEx` at `0x18004498b`
- `api-ms-win-core-sysinfo-l1-2-1!GetPhysicallyInstalledSystemMemory` at `0x180044964`
- `api-ms-win-core-sysinfo-l1-2-1!GetPhysicallyInstalledSystemMemory` at `0x180044964`

## string_xrefs

- `0x1800449ad`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\servicesystem\configuration.cpp`
- `0x180044a0b`: `onecore\internal\sdk\inc\wil\opensource/wil/safecast.h`

## pseudocode

```c
__int64 __fastcall Windows::Configuration::RamMB(Windows::Configuration *this)
{
  const char *v3; // r9
  unsigned __int64 v4; // rcx
  __int64 result; // rax
  int v6; // eax
  const char *v7; // r9
  unsigned int v8; // [rsp+20h] [rbp-68h] BYREF
  unsigned __int64 TotalMemoryInKilobytes; // [rsp+28h] [rbp-60h] BYREF
  _MEMORYSTATUSEX Buffer; // [rsp+30h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  TotalMemoryInKilobytes = 0;
  if ( GetPhysicallyInstalledSystemMemory(&TotalMemoryInKilobytes) )
  {
    v4 = TotalMemoryInKilobytes;
  }
  else
  {
    memset_0(&Buffer, 0, sizeof(Buffer));
    Buffer.dwLength = 64;
    if ( !GlobalMemoryStatusEx(&Buffer) )
    {
      wil::details::in1diag3::Log_GetLastError(
        retaddr,
        (void *)0x3B,
        (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\servicesystem\\configuration.cpp",
        v3);
      return 0xFFFFFFFFLL;
    }
    v4 = Buffer.ullTotalPhys >> 10;
    TotalMemoryInKilobytes = Buffer.ullTotalPhys >> 10;
  }
  try
  {
    v8 = 0;
    v6 = ULongLongToUInt(v4 >> 10, &v8);
    if ( v6 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x132,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/safecast.h",
        (const char *)(unsigned int)v6,
        v8);
    result = v8;
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x43,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\servicesystem\\configuration.cpp",
      v7);
    return 0xFFFFFFFFLL;
  }
  return result;
}

```

## disassembly

```asm
0x180044940  sub     rsp, 88h
0x180044947  mov     rax, cs:__security_cookie
0x18004494e  xor     rax, rsp
0x180044951  mov     [rsp+88h+var_18], rax
0x180044956  mov     [rsp+88h+TotalMemoryInKilobytes], 0
0x18004495f  lea     rcx, [rsp+88h+TotalMemoryInKilobytes]; TotalMemoryInKilobytes
0x180044964  call    cs:__imp_GetPhysicallyInstalledSystemMemory
0x18004496a  test    eax, eax
0x18004496c  jnz     short loc_1800449C3
0x18004496e  xor     edx, edx; Val
0x180044970  lea     r8d, [rax+40h]; Size
0x180044974  lea     rcx, [rsp+88h+Buffer]; void *
0x180044979  call    memset_0
0x18004497e  mov     [rsp+88h+Buffer.dwLength], 40h ; '@'
0x180044986  lea     rcx, [rsp+88h+Buffer]; lpBuffer
0x18004498b  call    cs:__imp_GlobalMemoryStatusEx
0x180044991  test    eax, eax
0x180044993  jz      short loc_1800449A5
0x180044995  mov     rcx, [rsp+88h+Buffer.ullTotalPhys]
0x18004499a  shr     rcx, 0Ah
0x18004499e  mov     [rsp+88h+TotalMemoryInKilobytes], rcx
0x1800449a3  jmp     short loc_1800449C8
0x1800449a5  mov     rcx, [rsp+88h]; this
0x1800449ad  lea     r8, aOnecoreEnduser_21; "onecore\\enduser\\windowsupdate\\muse\\"...
0x1800449b4  mov     edx, 3Bh ; ';'; void *
0x1800449b9  call    ?Log_GetLastError@in1diag3@details@wil@@YAKPEAXIPEBD@Z; wil::details::in1diag3::Log_GetLastError(void *,uint,char const *)
0x1800449be  or      eax, 0FFFFFFFFh
0x1800449c1  jmp     short loc_1800449F3
0x1800449c3  mov     rcx, [rsp+88h+TotalMemoryInKilobytes]
0x1800449c8  mov     [rsp+88h+var_68], 0; int
0x1800449d0  shr     rcx, 0Ah; unsigned __int64
0x1800449d4  lea     rdx, [rsp+88h+var_68]; unsigned int *
0x1800449d9  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x1800449de  mov     rcx, [rsp+88h]; this
0x1800449e6  test    eax, eax
0x1800449e8  js      short loc_180044A08
0x1800449ea  mov     eax, [rsp+88h+var_68]
0x1800449ee  jmp     short loc_1800449F3
0x1800449f0  or      eax, 0FFFFFFFFh
0x1800449f3  mov     rcx, [rsp+88h+var_18]
0x1800449f8  xor     rcx, rsp; StackCookie
0x1800449fb  call    __security_check_cookie
0x180044a00  add     rsp, 88h
0x180044a07  retn
0x180044a08  mov     r9d, eax; char *
0x180044a0b  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180044a12  mov     edx, 132h; void *
0x180044a17  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
