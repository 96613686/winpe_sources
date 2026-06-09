# WerpReinitializeKernelCrashDump

- ea: `0x18006ce60`
- end: `0x18006cf45`
- name: `WerpReinitializeKernelCrashDump`
- size: `229`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18007e000`

## callees

- `0x1800318c8`
- `0x18003fb94`
- `0x18006ce60`

## import_xrefs

- `ntdll!RtlAdjustPrivilege` at `0x18006ce7d`
- `ntdll!RtlAdjustPrivilege` at `0x18006cf00`
- `ntdll!RtlAdjustPrivilege` at `0x18006ce7d`
- `ntdll!RtlAdjustPrivilege` at `0x18006cf00`
- `ntdll!NtSetSystemInformation` at `0x18006cebc`
- `ntdll!NtSetSystemInformation` at `0x18006cebc`

## string_xrefs

- `0x18006ce9e`: `onecore\windows\feedback\core\werdll\lib\werpapi.cpp`
- `0x18006cedb`: `onecore\windows\feedback\core\werdll\lib\werpapi.cpp`
- `0x18006cf15`: `onecore\windows\feedback\core\werdll\lib\werpapi.cpp`

## pseudocode

```c
__int64 WerpReinitializeKernelCrashDump()
{
  NTSTATUS v0; // eax
  int v1; // ebx
  __int64 v2; // rdx
  NTSTATUS v4; // eax
  NTSTATUS v5; // ebx
  int v6; // eax
  int v7; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  unsigned __int8 OldValue; // [rsp+30h] [rbp+8h] BYREF

  OldValue = 0;
  v0 = RtlAdjustPrivilege(0x14u, 1u, 0, &OldValue);
  v1 = v0 | 0x10000000;
  if ( v0 < 0 )
  {
    v2 = 9396;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v2,
      (unsigned int)"onecore\\windows\\feedback\\core\\werdll\\lib\\werpapi.cpp",
      (const char *)(unsigned int)v1,
      v7);
    return (unsigned int)v1;
  }
  v4 = NtSetSystemInformation(SystemCrashDumpStateInformation, 0, 0);
  v5 = v4;
  if ( v4 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x24BB,
      (unsigned int)"onecore\\windows\\feedback\\core\\werdll\\lib\\werpapi.cpp",
      (const char *)(v4 | 0x10000000u),
      v7);
  if ( !OldValue )
  {
    v6 = RtlAdjustPrivilege(0x14u, 0, 0, &OldValue) | 0x10000000;
    if ( v6 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x24C7,
        (unsigned int)"onecore\\windows\\feedback\\core\\werdll\\lib\\werpapi.cpp",
        (const char *)(unsigned int)v6,
        v7);
  }
  v1 = v5 | 0x10000000;
  if ( v1 < 0 )
  {
    v2 = 9418;
    goto LABEL_3;
  }
  return 0;
}

```

## disassembly

```asm
0x18006ce60  mov     [rsp+arg_8], rbx
0x18006ce65  push    rdi; int
0x18006ce66  sub     rsp, 20h
0x18006ce6a  xor     r8d, r8d; ForThread
0x18006ce6d  mov     [rsp+28h+OldValue], 0
0x18006ce72  lea     r9, [rsp+28h+OldValue]; OldValue
0x18006ce77  mov     dl, 1; NewValue
0x18006ce79  lea     ecx, [r8+14h]; Privilege
0x18006ce7d  call    cs:__imp_RtlAdjustPrivilege
0x18006ce84  nop     dword ptr [rax+rax+00h]
0x18006ce89  mov     ebx, eax
0x18006ce8b  mov     edi, 10000000h
0x18006ce90  or      ebx, edi
0x18006ce92  jge     short loc_18006CEB4
0x18006ce94  mov     edx, 24B4h; void *
0x18006ce99  mov     rcx, [rsp+28h]; this
0x18006ce9e  lea     r8, aOnecoreWindows_9; "onecore\\windows\\feedback\\core\\werdl"...
0x18006cea5  mov     r9d, ebx; char *
0x18006cea8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006cead  mov     eax, ebx
0x18006ceaf  jmp     loc_18006CF39
0x18006ceb4  xor     edx, edx; SystemInformation
0x18006ceb6  xor     r8d, r8d; SystemInformationLength
0x18006ceb9  lea     ecx, [rdx+22h]; SystemInformationClass
0x18006cebc  call    cs:__imp_NtSetSystemInformation
0x18006cec3  nop     dword ptr [rax+rax+00h]
0x18006cec8  mov     ebx, eax
0x18006ceca  test    eax, eax
0x18006cecc  jns     short loc_18006CEEC
0x18006cece  mov     r9d, eax
0x18006ced1  or      r9d, edi; char *
0x18006ced4  jge     short loc_18006CEEC
0x18006ced6  mov     rcx, [rsp+28h]; this
0x18006cedb  lea     r8, aOnecoreWindows_9; "onecore\\windows\\feedback\\core\\werdl"...
0x18006cee2  mov     edx, 24BBh; void *
0x18006cee7  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18006ceec  cmp     [rsp+28h+OldValue], 0
0x18006cef1  jnz     short loc_18006CF29
0x18006cef3  xor     edx, edx; NewValue
0x18006cef5  lea     r9, [rsp+28h+OldValue]; OldValue
0x18006cefa  xor     r8d, r8d; ForThread
0x18006cefd  lea     ecx, [rdx+14h]; Privilege
0x18006cf00  call    cs:__imp_RtlAdjustPrivilege
0x18006cf07  nop     dword ptr [rax+rax+00h]
0x18006cf0c  or      eax, edi
0x18006cf0e  jge     short loc_18006CF29
0x18006cf10  mov     rcx, [rsp+28h]; this
0x18006cf15  lea     r8, aOnecoreWindows_9; "onecore\\windows\\feedback\\core\\werdl"...
0x18006cf1c  mov     r9d, eax; char *
0x18006cf1f  mov     edx, 24C7h; void *
0x18006cf24  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18006cf29  or      ebx, edi
0x18006cf2b  jge     short loc_18006CF37
0x18006cf2d  mov     edx, 24CAh
0x18006cf32  jmp     loc_18006CE99
0x18006cf37  xor     eax, eax
0x18006cf39  mov     rbx, [rsp+28h+arg_8]
0x18006cf3e  add     rsp, 20h
0x18006cf42  pop     rdi
0x18006cf43  retn
```
