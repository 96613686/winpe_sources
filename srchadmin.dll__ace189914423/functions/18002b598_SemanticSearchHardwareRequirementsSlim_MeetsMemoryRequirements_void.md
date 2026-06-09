# SemanticSearchHardwareRequirementsSlim::MeetsMemoryRequirements(void)

- ea: `0x18002b598`
- end: `0x18002b649`
- name: `?MeetsMemoryRequirements@SemanticSearchHardwareRequirementsSlim@@CA_NXZ`
- size: `177`
- prototype: `bool(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x18002b2a4`

## callees

- `0x180005cc0`
- `0x18000687c`
- `0x18002b598`
- `0x18002c144`
- `0x18002c164`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GlobalMemoryStatusEx` at `0x18002b5f0`
- `api-ms-win-core-sysinfo-l1-1-0!GlobalMemoryStatusEx` at `0x18002b5f0`
- `api-ms-win-core-sysinfo-l1-2-1!GetPhysicallyInstalledSystemMemory` at `0x18002b5bc`
- `api-ms-win-core-sysinfo-l1-2-1!GetPhysicallyInstalledSystemMemory` at `0x18002b5bc`

## pseudocode

```c
bool SemanticSearchHardwareRequirementsSlim::MeetsMemoryRequirements(void)
{
  void *v0; // rdx
  unsigned int v1; // r8d
  const char *v2; // r9
  const char *v3; // r9
  DWORDLONG ullTotalPhys; // rax
  unsigned __int64 TotalMemoryInKilobytes; // [rsp+20h] [rbp-68h] BYREF
  _MEMORYSTATUSEX Buffer; // [rsp+30h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  TotalMemoryInKilobytes = 0;
  if ( GetPhysicallyInstalledSystemMemory(&TotalMemoryInKilobytes) )
  {
    ullTotalPhys = TotalMemoryInKilobytes << 10;
  }
  else
  {
    wil::details::in1diag3::_Log_GetLastError(retaddr, v0, v1, v2);
    memset_0(&Buffer, 0, sizeof(Buffer));
    Buffer.dwLength = 64;
    if ( !GlobalMemoryStatusEx(&Buffer) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0xDD,
        (unsigned int)"onecoreuap\\internal\\base\\inc\\SemanticSearchHardwareRequirementsSlim.h",
        v3);
    ullTotalPhys = Buffer.ullTotalPhys;
  }
  return ullTotalPhys >= 0x400000000LL;
}

```

## disassembly

```asm
0x18002b598  sub     rsp, 88h
0x18002b59f  mov     rax, cs:__security_cookie
0x18002b5a6  xor     rax, rsp
0x18002b5a9  mov     [rsp+88h+var_18], rax
0x18002b5ae  lea     rcx, [rsp+88h+TotalMemoryInKilobytes]; TotalMemoryInKilobytes
0x18002b5b3  mov     [rsp+88h+TotalMemoryInKilobytes], 0
0x18002b5bc  call    cs:__imp_GetPhysicallyInstalledSystemMemory
0x18002b5c2  test    eax, eax
0x18002b5c4  jnz     short loc_18002B61B
0x18002b5c6  mov     rcx, [rsp+88h]; this
0x18002b5ce  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x18002b5d3  xor     edx, edx; Val
0x18002b5d5  lea     rcx, [rsp+88h+Buffer]; void *
0x18002b5da  lea     r8d, [rdx+40h]; Size
0x18002b5de  call    memset_0
0x18002b5e3  lea     rcx, [rsp+88h+Buffer]; lpBuffer
0x18002b5e8  mov     [rsp+88h+Buffer.dwLength], 40h ; '@'
0x18002b5f0  call    cs:__imp_GlobalMemoryStatusEx
0x18002b5f6  test    eax, eax
0x18002b5f8  jnz     short loc_18002B614
0x18002b5fa  mov     rcx, [rsp+88h]; this
0x18002b602  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\base\\inc\\Semant"...
0x18002b609  mov     edx, 0DDh; void *
0x18002b60e  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18002b614  mov     rax, [rsp+88h+Buffer.ullTotalPhys]
0x18002b619  jmp     short loc_18002B624
0x18002b61b  mov     rax, [rsp+88h+TotalMemoryInKilobytes]
0x18002b620  shl     rax, 0Ah
0x18002b624  mov     rcx, 400000000h
0x18002b62e  cmp     rax, rcx
0x18002b631  setnb   al
0x18002b634  mov     rcx, [rsp+88h+var_18]
0x18002b639  xor     rcx, rsp; StackCookie
0x18002b63c  call    __security_check_cookie
0x18002b641  add     rsp, 88h
0x18002b648  retn
```
