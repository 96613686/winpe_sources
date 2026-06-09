# WdipSnapshotLogger(WDILOGGER,ushort * const)

- ea: `0x18000d514`
- end: `0x18000d6c5`
- name: `?WdipSnapshotLogger@@YAJW4WDILOGGER@@QEAG@Z`
- size: `433`
- prototype: `__int64 __fastcall(int, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180006b90`

## callees

- `0x180002ba0`
- `0x1800093d0`
- `0x18000d514`
- `0x18000f1c2`
- `0x18000f1f0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d662`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d662`
- `api-ms-win-core-file-l2-1-0!CopyFileExW` at `0x18000d654`
- `api-ms-win-core-file-l2-1-0!CopyFileExW` at `0x18000d654`
- `api-ms-win-eventing-controller-l1-1-0!ControlTraceW` at `0x18000d5c6`
- `api-ms-win-eventing-controller-l1-1-0!ControlTraceW` at `0x18000d609`
- `api-ms-win-eventing-controller-l1-1-0!ControlTraceW` at `0x18000d5c6`
- `api-ms-win-eventing-controller-l1-1-0!ControlTraceW` at `0x18000d609`

## pseudocode

```c
__int64 __fastcall WdipSnapshotLogger(int a1, const unsigned __int16 *a2)
{
  signed int v4; // ebx
  unsigned int v5; // r11d
  signed int v6; // eax
  signed int v7; // eax
  signed int LastError; // eax
  _EVENT_TRACE_PROPERTIES Properties; // [rsp+30h] [rbp-4A8h] BYREF
  unsigned __int16 v11[261]; // [rsp+A8h] [rbp-430h] BYREF
  WCHAR ExistingFileName[263]; // [rsp+2B2h] [rbp-226h] BYREF

  v4 = 0;
  memset_0(&Properties, 0, 0x490u);
  Properties.Wnode.BufferSize = 1168;
  Properties.Wnode.Flags = 0x20000;
  Properties.LoggerNameOffset = 120;
  Properties.LogFileNameOffset = 642;
  if ( a1 )
  {
    if ( a1 == 1 )
    {
      StringCchCopyW(ExistingFileName, 0x104u, a2);
      StringCchCopyW(v11, v5, L"Circular Kernel Context Logger");
      v6 = ControlTraceW(0, L"Circular Kernel Context Logger", &Properties, 3u);
      v4 = v6;
      if ( v6 > 0 )
        v4 = (unsigned __int16)v6 | 0x80070000;
      if ( v4 < 0 )
        WdipTraceError(
          (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\utils.cpp",
          (int)L"WdipSnapshotLogger",
          139,
          (int)L"Error = %d",
          v4);
    }
  }
  else
  {
    v7 = ControlTraceW(0, L"WdiContextLog", &Properties, 3u);
    v4 = v7;
    if ( v7 > 0 )
      v4 = (unsigned __int16)v7 | 0x80070000;
    if ( v4 >= 0 )
    {
      if ( CopyFileExW(ExistingFileName, a2, 0, 0, 0, 0) )
      {
        return 0;
      }
      else
      {
        LastError = GetLastError();
        v4 = LastError;
        if ( LastError > 0 )
          v4 = (unsigned __int16)LastError | 0x80070000;
        if ( v4 < 0 )
          WdipTraceError(
            (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\utils.cpp",
            (int)L"WdipSnapshotLogger",
            157,
            (int)L"Error = %d",
            v4);
      }
    }
    else
    {
      WdipTraceError(
        (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\utils.cpp",
        (int)L"WdipSnapshotLogger",
        150,
        (int)L"Error = %d",
        v4);
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000d514  mov     [rsp+arg_0], rbx
0x18000d519  mov     [rsp+arg_10], rsi
0x18000d51e  push    rdi
0x18000d51f  sub     rsp, 4D0h
0x18000d526  mov     rax, cs:__security_cookie
0x18000d52d  xor     rax, rsp
0x18000d530  mov     [rsp+4D8h+var_18], rax
0x18000d538  mov     rsi, rdx
0x18000d53b  mov     edi, ecx
0x18000d53d  xor     edx, edx; Val
0x18000d53f  lea     rcx, [rsp+4D8h+Properties]; void *
0x18000d544  mov     r8d, 490h; Size
0x18000d54a  xor     ebx, ebx
0x18000d54c  call    memset_0
0x18000d551  mov     [rsp+4D8h+Properties.Wnode.BufferSize], 490h
0x18000d559  mov     [rsp+4D8h+Properties.Wnode.Flags], 20000h
0x18000d561  mov     [rsp+4D8h+Properties.LoggerNameOffset], 78h ; 'x'
0x18000d56c  mov     [rsp+4D8h+Properties.LogFileNameOffset], 282h
0x18000d577  test    edi, edi
0x18000d579  jz      short loc_18000D5F5
0x18000d57b  cmp     edi, 1
0x18000d57e  jnz     loc_18000D69E
0x18000d584  mov     r11d, 104h
0x18000d58a  lea     rcx, [rsp+4D8h+ExistingFileName]; unsigned __int16 *
0x18000d592  mov     edx, r11d; unsigned __int64
0x18000d595  mov     r8, rsi; unsigned __int16 *
0x18000d598  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000d59d  lea     r8, InstanceName; "Circular Kernel Context Logger"
0x18000d5a4  mov     edx, r11d; unsigned __int64
0x18000d5a7  lea     rcx, [rsp+4D8h+var_430]; unsigned __int16 *
0x18000d5af  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000d5b4  lea     r9d, [rbx+3]; ControlCode
0x18000d5b8  xor     ecx, ecx; TraceHandle
0x18000d5ba  lea     r8, [rsp+4D8h+Properties]; Properties
0x18000d5bf  lea     rdx, InstanceName; "Circular Kernel Context Logger"
0x18000d5c6  call    cs:__imp_ControlTraceW
0x18000d5cc  mov     ebx, eax
0x18000d5ce  test    eax, eax
0x18000d5d0  jle     short loc_18000D5DB
0x18000d5d2  movzx   ebx, ax
0x18000d5d5  or      ebx, 80070000h
0x18000d5db  test    ebx, ebx
0x18000d5dd  jns     loc_18000D69E
0x18000d5e3  movzx   eax, bx
0x18000d5e6  mov     r8d, 8Bh
0x18000d5ec  mov     dword ptr [rsp+4D8h+pbCancel], eax
0x18000d5f0  jmp     loc_18000D684
0x18000d5f5  mov     r9d, 3; ControlCode
0x18000d5fb  lea     r8, [rsp+4D8h+Properties]; Properties
0x18000d600  lea     rdx, aWdicontextlog; "WdiContextLog"
0x18000d607  xor     ecx, ecx; TraceHandle
0x18000d609  call    cs:__imp_ControlTraceW
0x18000d60f  mov     ebx, eax
0x18000d611  mov     edi, 80070000h
0x18000d616  test    eax, eax
0x18000d618  jle     short loc_18000D61F
0x18000d61a  movzx   ebx, ax
0x18000d61d  or      ebx, edi
0x18000d61f  test    ebx, ebx
0x18000d621  jns     short loc_18000D632
0x18000d623  movzx   eax, bx
0x18000d626  mov     r8d, 96h
0x18000d62c  mov     dword ptr [rsp+4D8h+pbCancel], eax
0x18000d630  jmp     short loc_18000D684
0x18000d632  mov     [rsp+4D8h+dwCopyFlags], 0; dwCopyFlags
0x18000d63a  lea     rcx, [rsp+4D8h+ExistingFileName]; lpExistingFileName
0x18000d642  xor     r9d, r9d; lpData
0x18000d645  mov     [rsp+4D8h+pbCancel], 0; pbCancel
0x18000d64e  xor     r8d, r8d; lpProgressRoutine
0x18000d651  mov     rdx, rsi; lpNewFileName
0x18000d654  call    cs:__imp_CopyFileExW
0x18000d65a  test    eax, eax
0x18000d65c  jz      short loc_18000D662
0x18000d65e  xor     ebx, ebx
0x18000d660  jmp     short loc_18000D69E
0x18000d662  call    cs:__imp_GetLastError
0x18000d668  mov     ebx, eax
0x18000d66a  test    eax, eax
0x18000d66c  jle     short loc_18000D673
0x18000d66e  movzx   ebx, ax
0x18000d671  or      ebx, edi
0x18000d673  test    ebx, ebx
0x18000d675  jns     short loc_18000D69E
0x18000d677  movzx   ecx, bx
0x18000d67a  mov     r8d, 9Dh; int
0x18000d680  mov     dword ptr [rsp+4D8h+pbCancel], ecx; Args
0x18000d684  lea     r9, aErrorD_0; "Error = %d"
0x18000d68b  lea     rdx, aWdipsnapshotlo; "WdipSnapshotLogger"
0x18000d692  lea     rcx, aClientcoreBase_1; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x18000d699  call    WdipTraceError
0x18000d69e  mov     eax, ebx
0x18000d6a0  mov     rcx, [rsp+4D8h+var_18]
0x18000d6a8  xor     rcx, rsp; StackCookie
0x18000d6ab  call    __security_check_cookie
0x18000d6b0  lea     r11, [rsp+4D8h+var_8]
0x18000d6b8  mov     rbx, [r11+10h]
0x18000d6bc  mov     rsi, [r11+20h]
0x18000d6c0  mov     rsp, r11
0x18000d6c3  pop     rdi
0x18000d6c4  retn
```
