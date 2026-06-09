# WdcDataMonitor::Start(void)

- ea: `0x18002a3b4`
- end: `0x18002a580`
- name: `?Start@WdcDataMonitor@@QEAAJXZ`
- size: `460`
- prototype: `__int64 __fastcall(WdcDataMonitor *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x18002415c`
- `0x1800759b4`

## callees

- `0x18000b854`
- `0x18002a3b4`
- `0x18003b0ac`
- `0x180086010`

## import_xrefs

- `KERNEL32!CreateThread` at `0x18002a49c`
- `KERNEL32!CreateThread` at `0x18002a49c`
- `KERNEL32!GetLastError` at `0x18002a4b3`
- `KERNEL32!GetLastError` at `0x18002a4d4`
- `KERNEL32!GetLastError` at `0x18002a515`
- `KERNEL32!GetLastError` at `0x18002a4b3`
- `KERNEL32!GetLastError` at `0x18002a4d4`
- `KERNEL32!GetLastError` at `0x18002a515`
- `KERNEL32!CreateEventW` at `0x18002a449`
- `KERNEL32!CreateEventW` at `0x18002a46f`
- `KERNEL32!CreateEventW` at `0x18002a449`
- `KERNEL32!CreateEventW` at `0x18002a46f`
- `KERNEL32!SetThreadPriority` at `0x18002a4f9`
- `KERNEL32!SetThreadPriority` at `0x18002a4f9`
- `KERNEL32!GetCurrentThread` at `0x18002a4eb`
- `KERNEL32!GetCurrentThread` at `0x18002a4eb`

## pseudocode

```c
__int64 __fastcall WdcDataMonitor::Start(WdcDataMonitor *this)
{
  __int64 v1; // rax
  int v3; // eax
  signed int v4; // ebx
  int v5; // eax
  HANDLE v6; // rax
  signed int LastError; // eax
  signed int v8; // eax
  HANDLE CurrentThread; // rax
  signed int v10; // eax
  __int64 dwCreationFlags; // [rsp+20h] [rbp-18h]
  DWORD ThreadId; // [rsp+40h] [rbp+8h] BYREF

  v1 = *(_QWORD *)this;
  ThreadId = 0;
  v3 = (*(__int64 (__fastcall **)(WdcDataMonitor *, __int64))(v1 + 48))(this, 1);
  v4 = v3;
  if ( v3 < 0 )
    goto LABEL_2;
  *((_QWORD *)this + 12) = (char *)this + 88;
  *((_QWORD *)this + 11) = (char *)this + 88;
  memset_0((char *)this + 8184, 0, 0x1E0u);
  memset_0((char *)this + 8664, 0, 0x1E0u);
  *((_QWORD *)this + 1146) = CreateEventW(0, 1, 0, 0);
  v5 = *((_DWORD *)this + 2040);
  if ( v5 != 1 )
  {
    if ( v5 )
      goto LABEL_28;
    v3 = (*(__int64 (__fastcall **)(WdcDataMonitor *))(*(_QWORD *)this + 136LL))(this);
    v4 = v3;
    if ( v3 >= 0 )
      goto LABEL_28;
    goto LABEL_2;
  }
  *((_QWORD *)this + 1145) = CreateEventW(0, 0, 0, 0);
  v6 = CreateThread(0, 0, WdcDataMonitor::UpdateThread, this, 0, &ThreadId);
  *((_QWORD *)this + 1147) = v6;
  if ( !v6 )
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( !LastError )
      goto LABEL_17;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    if ( v4 < 0 )
      goto LABEL_18;
  }
  if ( *((_QWORD *)this + 1147) == -1 )
  {
    v8 = GetLastError();
    v4 = v8;
    if ( v8 )
    {
      if ( v8 > 0 )
        v4 = (unsigned __int16)v8 | 0x80070000;
      if ( v4 >= 0 )
        goto LABEL_15;
LABEL_18:
      LODWORD(dwCreationFlags) = v4;
      goto LABEL_3;
    }
LABEL_17:
    v4 = -2147467259;
    goto LABEL_18;
  }
LABEL_15:
  CurrentThread = GetCurrentThread();
  if ( SetThreadPriority(CurrentThread, 2) )
  {
    v4 = 0;
LABEL_28:
    *((_DWORD *)this + 2324) = 1;
    *((_DWORD *)this + 2288) = 1;
    return (unsigned int)v4;
  }
  v10 = GetLastError();
  v4 = v10;
  if ( v10 )
  {
    if ( v10 > 0 )
      v4 = (unsigned __int16)v10 | 0x80070000;
    if ( v4 >= 0 )
      goto LABEL_28;
  }
  else
  {
    v4 = -2147467259;
  }
  v3 = v4;
LABEL_2:
  LODWORD(dwCreationFlags) = v3;
LABEL_3:
  WdcDebugMessage(
    "base\\diagnosis\\pdui\\perfmon\\mon\\data.cpp",
    "WdcDataMonitor::Start",
    0,
    L"FAILURE: 0x%08x",
    dwCreationFlags);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18002a3b4  mov     [rsp+arg_8], rbx
0x18002a3b9  mov     [rsp+arg_10], rsi
0x18002a3be  push    rdi
0x18002a3bf  sub     rsp, 30h
0x18002a3c3  mov     rax, [rcx]
0x18002a3c6  mov     edx, 1
0x18002a3cb  mov     rdi, rcx
0x18002a3ce  mov     [rsp+38h+ThreadId], 0
0x18002a3d6  mov     rax, [rax+30h]
0x18002a3da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a3df  mov     ebx, eax
0x18002a3e1  test    eax, eax
0x18002a3e3  jns     short loc_18002A40B
0x18002a3e5  mov     dword ptr [rsp+38h+dwCreationFlags], eax
0x18002a3e9  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x18002a3f0  xor     r8d, r8d; int
0x18002a3f3  lea     rdx, aWdcdatamonitor; "WdcDataMonitor::Start"
0x18002a3fa  lea     rcx, aBaseDiagnosisP_31; "base\\diagnosis\\pdui\\perfmon\\mon\\da"...
0x18002a401  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x18002a406  jmp     loc_18002A56E
0x18002a40b  lea     rax, [rdi+58h]
0x18002a40f  mov     esi, 1E0h
0x18002a414  mov     r8d, esi; Size
0x18002a417  mov     [rax+8], rax
0x18002a41b  lea     rcx, [rdi+1FF8h]; void *
0x18002a422  mov     [rax], rax
0x18002a425  xor     edx, edx; Val
0x18002a427  call    memset_0
0x18002a42c  lea     rcx, [rdi+21D8h]; void *
0x18002a433  mov     r8d, esi; Size
0x18002a436  xor     edx, edx; Val
0x18002a438  call    memset_0
0x18002a43d  xor     r9d, r9d; lpName
0x18002a440  xor     r8d, r8d; bInitialState
0x18002a443  xor     ecx, ecx; lpEventAttributes
0x18002a445  lea     edx, [r9+1]; bManualReset
0x18002a449  call    cs:__imp_CreateEventW
0x18002a44f  mov     [rdi+23D0h], rax
0x18002a456  mov     eax, [rdi+1FE0h]
0x18002a45c  cmp     eax, 1
0x18002a45f  jnz     loc_18002A53A
0x18002a465  xor     r9d, r9d; lpName
0x18002a468  xor     r8d, r8d; bInitialState
0x18002a46b  xor     edx, edx; bManualReset
0x18002a46d  xor     ecx, ecx; lpEventAttributes
0x18002a46f  call    cs:__imp_CreateEventW
0x18002a475  mov     [rdi+23C8h], rax
0x18002a47c  mov     r9, rdi; lpParameter
0x18002a47f  lea     r8, ?UpdateThread@WdcDataMonitor@@KAKPEAX@Z; lpStartAddress
0x18002a486  xor     edx, edx; dwStackSize
0x18002a488  lea     rax, [rsp+38h+ThreadId]
0x18002a48d  xor     ecx, ecx; lpThreadAttributes
0x18002a48f  mov     [rsp+38h+lpThreadId], rax; lpThreadId
0x18002a494  mov     dword ptr [rsp+38h+dwCreationFlags], 0; dwCreationFlags
0x18002a49c  call    cs:__imp_CreateThread
0x18002a4a2  mov     [rdi+23D8h], rax
0x18002a4a9  mov     esi, 80070000h
0x18002a4ae  test    rax, rax
0x18002a4b1  jnz     short loc_18002A4CA
0x18002a4b3  call    cs:__imp_GetLastError
0x18002a4b9  mov     ebx, eax
0x18002a4bb  test    eax, eax
0x18002a4bd  jz      short loc_18002A507
0x18002a4bf  jle     short loc_18002A4C6
0x18002a4c1  movzx   ebx, ax
0x18002a4c4  or      ebx, esi
0x18002a4c6  test    ebx, ebx
0x18002a4c8  js      short loc_18002A50C
0x18002a4ca  cmp     qword ptr [rdi+23D8h], 0FFFFFFFFFFFFFFFFh
0x18002a4d2  jnz     short loc_18002A4EB
0x18002a4d4  call    cs:__imp_GetLastError
0x18002a4da  mov     ebx, eax
0x18002a4dc  test    eax, eax
0x18002a4de  jz      short loc_18002A507
0x18002a4e0  jle     short loc_18002A4E7
0x18002a4e2  movzx   ebx, ax
0x18002a4e5  or      ebx, esi
0x18002a4e7  test    ebx, ebx
0x18002a4e9  js      short loc_18002A50C
0x18002a4eb  call    cs:__imp_GetCurrentThread
0x18002a4f1  mov     rcx, rax; hThread
0x18002a4f4  mov     edx, 2; nPriority
0x18002a4f9  call    cs:__imp_SetThreadPriority
0x18002a4ff  test    eax, eax
0x18002a501  jz      short loc_18002A515
0x18002a503  xor     ebx, ebx
0x18002a505  jmp     short loc_18002A55A
0x18002a507  mov     ebx, 80004005h
0x18002a50c  mov     dword ptr [rsp+38h+dwCreationFlags], ebx
0x18002a510  jmp     loc_18002A3E9
0x18002a515  call    cs:__imp_GetLastError
0x18002a51b  mov     ebx, eax
0x18002a51d  test    eax, eax
0x18002a51f  jz      short loc_18002A52E
0x18002a521  jle     short loc_18002A528
0x18002a523  movzx   ebx, ax
0x18002a526  or      ebx, esi
0x18002a528  test    ebx, ebx
0x18002a52a  jns     short loc_18002A55A
0x18002a52c  jmp     short loc_18002A533
0x18002a52e  mov     ebx, 80004005h
0x18002a533  mov     eax, ebx
0x18002a535  jmp     loc_18002A3E5
0x18002a53a  test    eax, eax
0x18002a53c  jnz     short loc_18002A55A
0x18002a53e  mov     rax, [rdi]
0x18002a541  mov     rcx, rdi
0x18002a544  mov     rax, [rax+88h]
0x18002a54b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a550  mov     ebx, eax
0x18002a552  test    eax, eax
0x18002a554  js      loc_18002A3E5
0x18002a55a  mov     dword ptr [rdi+2450h], 1
0x18002a564  mov     dword ptr [rdi+23C0h], 1
0x18002a56e  mov     rsi, [rsp+38h+arg_10]
0x18002a573  mov     eax, ebx
0x18002a575  mov     rbx, [rsp+38h+arg_8]
0x18002a57a  add     rsp, 30h
0x18002a57e  pop     rdi
0x18002a57f  retn
```
