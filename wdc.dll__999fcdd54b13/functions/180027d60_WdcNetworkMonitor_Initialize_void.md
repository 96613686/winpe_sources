# WdcNetworkMonitor::Initialize(void)

- ea: `0x180027d60`
- end: `0x180027e18`
- name: `?Initialize@WdcNetworkMonitor@@UEAAJXZ`
- size: `184`
- prototype: `__int64 __fastcall(WdcNetworkMonitor *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000b854`
- `0x180027d60`

## import_xrefs

- `KERNEL32!CreateThread` at `0x180027d8f`
- `KERNEL32!CreateThread` at `0x180027d8f`
- `KERNEL32!GetLastError` at `0x180027da1`
- `KERNEL32!GetLastError` at `0x180027dc6`
- `KERNEL32!GetLastError` at `0x180027da1`
- `KERNEL32!GetLastError` at `0x180027dc6`

## pseudocode

```c
__int64 __fastcall WdcNetworkMonitor::Initialize(WdcNetworkMonitor *this)
{
  signed int v2; // ebx
  HANDLE v3; // rax
  signed int LastError; // eax
  signed int v5; // eax
  __int64 dwCreationFlags; // [rsp+20h] [rbp-18h]
  DWORD ThreadId; // [rsp+40h] [rbp+8h] BYREF

  v2 = 0;
  ThreadId = 0;
  v3 = CreateThread(0, 0, (LPTHREAD_START_ROUTINE)WdcNetworkMonitor::AddressThread, this, 0, &ThreadId);
  *((_QWORD *)this + 1171) = v3;
  if ( !v3 )
  {
    LastError = GetLastError();
    v2 = LastError;
    if ( !LastError )
      goto LABEL_12;
    if ( LastError > 0 )
      v2 = (unsigned __int16)LastError | 0x80070000;
    if ( v2 < 0 )
      goto LABEL_13;
  }
  if ( *((_QWORD *)this + 1171) != -1 )
    return (unsigned int)v2;
  v5 = GetLastError();
  v2 = v5;
  if ( !v5 )
  {
LABEL_12:
    v2 = -2147467259;
LABEL_13:
    LODWORD(dwCreationFlags) = v2;
    WdcDebugMessage(
      "base\\diagnosis\\pdui\\perfmon\\mon\\network.cpp",
      "WdcNetworkMonitor::Initialize",
      0,
      L"FAILURE: 0x%08x",
      dwCreationFlags);
    return (unsigned int)v2;
  }
  if ( v5 > 0 )
    v2 = (unsigned __int16)v5 | 0x80070000;
  if ( v2 < 0 )
    goto LABEL_13;
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180027d60  mov     [rsp+arg_8], rbx
0x180027d65  push    rdi
0x180027d66  sub     rsp, 30h
0x180027d6a  lea     rax, [rsp+38h+ThreadId]
0x180027d6f  mov     rdi, rcx
0x180027d72  xor     ebx, ebx
0x180027d74  mov     [rsp+38h+lpThreadId], rax; lpThreadId
0x180027d79  mov     r9, rcx; lpParameter
0x180027d7c  mov     dword ptr [rsp+38h+dwCreationFlags], ebx; dwCreationFlags
0x180027d80  lea     r8, ?AddressThread@WdcNetworkMonitor@@CAKPEAX@Z; lpStartAddress
0x180027d87  mov     [rsp+38h+ThreadId], ebx
0x180027d8b  xor     edx, edx; dwStackSize
0x180027d8d  xor     ecx, ecx; lpThreadAttributes
0x180027d8f  call    cs:__imp_CreateThread
0x180027d95  mov     [rdi+2498h], rax
0x180027d9c  test    rax, rax
0x180027d9f  jnz     short loc_180027DBC
0x180027da1  call    cs:__imp_GetLastError
0x180027da7  mov     ebx, eax
0x180027da9  test    eax, eax
0x180027dab  jz      short loc_180027DE3
0x180027dad  jle     short loc_180027DB8
0x180027daf  movzx   ebx, ax
0x180027db2  or      ebx, 80070000h
0x180027db8  test    ebx, ebx
0x180027dba  js      short loc_180027DE8
0x180027dbc  cmp     qword ptr [rdi+2498h], 0FFFFFFFFFFFFFFFFh
0x180027dc4  jnz     short loc_180027E0B
0x180027dc6  call    cs:__imp_GetLastError
0x180027dcc  mov     ebx, eax
0x180027dce  test    eax, eax
0x180027dd0  jz      short loc_180027DE3
0x180027dd2  jle     short loc_180027DDD
0x180027dd4  movzx   ebx, ax
0x180027dd7  or      ebx, 80070000h
0x180027ddd  test    ebx, ebx
0x180027ddf  jns     short loc_180027E0B
0x180027de1  jmp     short loc_180027DE8
0x180027de3  mov     ebx, 80004005h
0x180027de8  mov     eax, ebx
0x180027dea  mov     dword ptr [rsp+38h+dwCreationFlags], ebx
0x180027dee  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x180027df5  xor     r8d, r8d; int
0x180027df8  lea     rdx, aWdcnetworkmoni_4; "WdcNetworkMonitor::Initialize"
0x180027dff  lea     rcx, aBaseDiagnosisP_11; "base\\diagnosis\\pdui\\perfmon\\mon\\ne"...
0x180027e06  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x180027e0b  mov     eax, ebx
0x180027e0d  mov     rbx, [rsp+38h+arg_8]
0x180027e12  add     rsp, 30h
0x180027e16  pop     rdi
0x180027e17  retn
```
