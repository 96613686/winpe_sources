# Windows::Configuration::RamMB(void)

- ea: `0x18008d550`
- end: `0x18008d5fc`
- name: `?RamMB@Configuration@Windows@@UEAAIXZ`
- size: `172`
- prototype: `unsigned int __fastcall(Windows::Configuration *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, service_task, installer_update`

## callees

- `0x18002dedc`
- `0x180066574`
- `0x18008d550`
- `0x1800dd930`
- `0x1800e46b0`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GlobalMemoryStatusEx` at `0x18008d59b`
- `api-ms-win-core-sysinfo-l1-1-0!GlobalMemoryStatusEx` at `0x18008d59b`
- `api-ms-win-core-sysinfo-l1-2-1!GetPhysicallyInstalledSystemMemory` at `0x18008d574`
- `api-ms-win-core-sysinfo-l1-2-1!GetPhysicallyInstalledSystemMemory` at `0x18008d574`

## string_xrefs

- `0x18008d5bd`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Configuration.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Configuration::RamMB(Windows::Configuration *this)
{
  const char *v3; // r9
  unsigned __int64 v4; // rcx
  __int64 result; // rax
  const char *v6; // r9
  unsigned __int64 TotalMemoryInKilobytes; // [rsp+20h] [rbp-68h] BYREF
  _MEMORYSTATUSEX Buffer; // [rsp+30h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  TotalMemoryInKilobytes = 0;
  if ( GetPhysicallyInstalledSystemMemory(&TotalMemoryInKilobytes) )
  {
    v4 = TotalMemoryInKilobytes;
  }
  else
  {
    memset(&Buffer, 0, sizeof(Buffer));
    Buffer.dwLength = 64;
    if ( !GlobalMemoryStatusEx(&Buffer) )
    {
      wil::details::in1diag3::_Log_GetLastError(
        retaddr,
        (void *)0x4F,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Configuration.cpp",
        v3);
      return 0xFFFFFFFFLL;
    }
    v4 = Buffer.ullTotalPhys >> 10;
    TotalMemoryInKilobytes = Buffer.ullTotalPhys >> 10;
  }
  try
  {
    result = wil::safe_cast<unsigned int,unsigned __int64,0>(v4 >> 10);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x57,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Configuration.cpp",
      v6);
    return 0xFFFFFFFFLL;
  }
  return result;
}

```

## disassembly

```asm
0x18008d550  sub     rsp, 88h
0x18008d557  mov     rax, cs:__security_cookie
0x18008d55e  xor     rax, rsp
0x18008d561  mov     [rsp+88h+var_18], rax
0x18008d566  mov     [rsp+88h+TotalMemoryInKilobytes], 0
0x18008d56f  lea     rcx, [rsp+88h+TotalMemoryInKilobytes]; TotalMemoryInKilobytes
0x18008d574  call    cs:__imp_GetPhysicallyInstalledSystemMemory
0x18008d57a  test    eax, eax
0x18008d57c  jnz     short loc_18008D5D3
0x18008d57e  xor     edx, edx; Val
0x18008d580  lea     r8d, [rax+40h]; Size
0x18008d584  lea     rcx, [rsp+88h+Buffer]; void *
0x18008d589  call    memset
0x18008d58e  mov     [rsp+88h+Buffer.dwLength], 40h ; '@'
0x18008d596  lea     rcx, [rsp+88h+Buffer]; lpBuffer
0x18008d59b  call    cs:__imp_GlobalMemoryStatusEx
0x18008d5a1  test    eax, eax
0x18008d5a3  jz      short loc_18008D5B5
0x18008d5a5  mov     rcx, [rsp+88h+Buffer.ullTotalPhys]
0x18008d5aa  shr     rcx, 0Ah
0x18008d5ae  mov     [rsp+88h+TotalMemoryInKilobytes], rcx
0x18008d5b3  jmp     short loc_18008D5D8
0x18008d5b5  mov     rcx, [rsp+88h]; this
0x18008d5bd  lea     r8, aCW1SSrcOrchest_10; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x18008d5c4  mov     edx, 4Fh ; 'O'; void *
0x18008d5c9  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x18008d5ce  or      eax, 0FFFFFFFFh
0x18008d5d1  jmp     short loc_18008D5E6
0x18008d5d3  mov     rcx, [rsp+88h+TotalMemoryInKilobytes]
0x18008d5d8  shr     rcx, 0Ah
0x18008d5dc  call    ??$safe_cast@I_K$0A@@wil@@YAI_K@Z; wil::safe_cast<uint,unsigned __int64,0>(unsigned __int64)
0x18008d5e1  jmp     short loc_18008D5E6
0x18008d5e3  or      eax, 0FFFFFFFFh
0x18008d5e6  mov     rcx, [rsp+88h+var_18]
0x18008d5eb  xor     rcx, rsp; StackCookie
0x18008d5ee  call    __security_check_cookie
0x18008d5f3  add     rsp, 88h
0x18008d5fa  retn
```
