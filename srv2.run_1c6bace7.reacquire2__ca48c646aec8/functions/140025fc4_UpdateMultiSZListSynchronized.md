# UpdateMultiSZListSynchronized

- ea: `0x140025fc4`
- end: `0x140026097`
- name: `UpdateMultiSZListSynchronized`
- size: `211`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x140077c5c`

## callees

- `0x140025fc4`
- `0x1400260a0`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140026041`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140026041`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140026069`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140026069`
- `srvnet!SrvLibFreeMemory` at `0x14002607d`
- `srvnet!SrvLibFreeMemory` at `0x14002607d`
- `srvnet!SrvLibGetMultiSZList` at `0x140025ff5`
- `srvnet!SrvLibGetMultiSZList` at `0x140025ff5`

## string_xrefs

- `0x140025fea`: `\Registry\Machine\System\CurrentControlSet\Services\LanmanServer\Parameters`

## pseudocode

```c
__int64 UpdateMultiSZListSynchronized()
{
  int MultiSZList; // ebx
  __int64 v1; // rdi
  char v3; // [rsp+20h] [rbp-18h]
  __int64 v4; // [rsp+58h] [rbp+20h] BYREF

  v4 = 0;
  v3 = 0;
  MultiSZList = SrvLibGetMultiSZList(
                  &v4,
                  L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\LanmanServer\\Parameters",
                  L"RequireWindowsHelloForBusinessExceptionList",
                  0,
                  v3);
  if ( MultiSZList >= 0 )
  {
    ExAcquirePushLockExclusiveEx(&Smb2RequireWindowsHelloForBusinessExceptionListLock, 0);
    v1 = Smb2RequireWindowsHelloForBusinessExceptionList;
    Smb2RequireWindowsHelloForBusinessExceptionList = v4;
    ExReleasePushLockExclusiveEx(&Smb2RequireWindowsHelloForBusinessExceptionListLock, 0);
    if ( v1 )
      SrvLibFreeMemory(v1);
  }
  else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
         && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x4000) != 0
         && BYTE1(WPP_GLOBAL_Control->Timer) )
  {
    WPP_SF_Sd(WPP_GLOBAL_Control->AttachedDevice);
  }
  return (unsigned int)MultiSZList;
}

```

## disassembly

```asm
0x140025fc4  mov     rax, rsp
0x140025fc7  mov     [rax+8], rbx
0x140025fcb  mov     [rax+20h], r9
0x140025fcf  push    rdi
0x140025fd0  sub     rsp, 30h
0x140025fd4  xor     r9d, r9d
0x140025fd7  mov     qword ptr [rax+20h], 0
0x140025fdf  lea     r8, aRequirewindows; "RequireWindowsHelloForBusinessException"...
0x140025fe6  mov     byte ptr [rax-18h], 0
0x140025fea  lea     rdx, aRegistryMachin_2; "\\Registry\\Machine\\System\\CurrentCon"...
0x140025ff1  lea     rcx, [rax+20h]
0x140025ff5  call    cs:__imp_SrvLibGetMultiSZList
0x140025ffc  nop     dword ptr [rax+rax+00h]
0x140026001  mov     ebx, eax
0x140026003  test    eax, eax
0x140026005  jns     short loc_140026038
0x140026007  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002600e  lea     rax, WPP_GLOBAL_Control
0x140026015  cmp     rcx, rax
0x140026018  jz      short loc_140026089
0x14002601a  test    dword ptr [rcx+2Ch], 4000h
0x140026021  jz      short loc_140026089
0x140026023  cmp     byte ptr [rcx+29h], 1
0x140026027  jb      short loc_140026089
0x140026029  mov     rcx, [rcx+18h]
0x14002602d  mov     dword ptr [rsp+38h+var_18], ebx
0x140026031  call    WPP_SF_Sd
0x140026036  jmp     short loc_140026089
0x140026038  xor     edx, edx
0x14002603a  lea     rcx, Smb2RequireWindowsHelloForBusinessExceptionListLock
0x140026041  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x140026048  nop     dword ptr [rax+rax+00h]
0x14002604d  mov     rax, [rsp+38h+arg_18]
0x140026052  lea     rcx, Smb2RequireWindowsHelloForBusinessExceptionListLock
0x140026059  mov     rdi, cs:Smb2RequireWindowsHelloForBusinessExceptionList
0x140026060  xor     edx, edx
0x140026062  mov     cs:Smb2RequireWindowsHelloForBusinessExceptionList, rax
0x140026069  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140026070  nop     dword ptr [rax+rax+00h]
0x140026075  test    rdi, rdi
0x140026078  jz      short loc_140026089
0x14002607a  mov     rcx, rdi
0x14002607d  call    cs:__imp_SrvLibFreeMemory
0x140026084  nop     dword ptr [rax+rax+00h]
0x140026089  mov     eax, ebx
0x14002608b  mov     rbx, [rsp+38h+arg_0]
0x140026090  add     rsp, 30h
0x140026094  pop     rdi
0x140026095  retn
```
