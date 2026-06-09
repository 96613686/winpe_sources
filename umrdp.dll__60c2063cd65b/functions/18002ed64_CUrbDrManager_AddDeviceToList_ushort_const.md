# CUrbDrManager::AddDeviceToList(ushort const *)

- ea: `0x18002ed64`
- end: `0x18002eeee`
- name: `?AddDeviceToList@CUrbDrManager@@AEAAJPEBG@Z`
- size: `394`
- prototype: `__int64 __fastcall(CUrbDrManager *__hidden this, LPCWSTR lpFileName)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, loader_planting`

## callers

- `0x18002fd30`
- `0x180030710`

## callees

- `0x18000b8f8`
- `0x18000f75c`
- `0x18002ed64`
- `0x18002fc84`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002edbb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002edbb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002eeca`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002eedd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002eeca`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002eedd`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18002ee43`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18002ee43`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002edac`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002edac`
- `ntdll!RtlInitUnicodeString` at `0x18002ed80`
- `ntdll!RtlInitUnicodeString` at `0x18002ed80`
- `KERNEL32!ResumeThread` at `0x18002ee75`
- `KERNEL32!ResumeThread` at `0x18002ee75`

## pseudocode

```c
__int64 __fastcall CUrbDrManager::AddDeviceToList(CUrbDrManager *this, LPCWSTR lpFileName)
{
  HANDLE FileW; // rsi
  signed int LastError; // eax
  unsigned int v6; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  HANDLE Thread; // rdi
  __int64 v9; // rax
  __int64 v10; // rcx
  unsigned int v11; // eax
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-38h] BYREF

  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, lpFileName);
  FileW = CreateFileW(lpFileName, 1u, 3u, 0, 3u, 0x40000000u, 0);
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 1) != 0
      && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_D(
        *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
        60,
        WPP_e96ad774d77a3b20501daafc53de2dbd_Traceguids,
        CurrentThreadActivityIdPrefix);
    }
  }
  else
  {
    Thread = CreateThread(0, 0, EvtWorkerThread, this, 4u, 0);
    if ( (unsigned int)DynArray<_USBHUB_DEVICE_DATA,unsigned long>::Grow(
                         (char *)this + 48,
                         *((unsigned int *)this + 13)) )
    {
      v9 = *((_QWORD *)this + 7);
      v10 = 2LL * *((unsigned int *)this + 13);
      *(_QWORD *)(v9 + 8 * v10) = FileW;
      *(_QWORD *)(v9 + 8 * v10 + 8) = Thread;
      ++*((_DWORD *)this + 13);
      ResumeThread(Thread);
      return 0;
    }
    else
    {
      if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 1) != 0
        && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
      {
        v11 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_D(
          *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
          61,
          WPP_e96ad774d77a3b20501daafc53de2dbd_Traceguids,
          v11);
      }
      if ( FileW )
        CloseHandle(FileW);
      v6 = -2147024888;
      if ( Thread )
        CloseHandle(Thread);
    }
  }
  return v6;
}

```

## disassembly

```asm
0x18002ed64  push    rbx
0x18002ed66  push    rbp
0x18002ed67  push    rsi
0x18002ed68  push    rdi
0x18002ed69  sub     rsp, 58h
0x18002ed6d  mov     rbp, rcx
0x18002ed70  xorps   xmm0, xmm0
0x18002ed73  lea     rcx, [rsp+78h+DestinationString]; DestinationString
0x18002ed78  mov     rbx, rdx
0x18002ed7b  movups  xmmword ptr [rsp+78h+DestinationString.Length], xmm0
0x18002ed80  call    cs:__imp_RtlInitUnicodeString
0x18002ed86  mov     r8d, 3; dwShareMode
0x18002ed8c  mov     [rsp+78h+hTemplateFile], 0; hTemplateFile
0x18002ed95  mov     [rsp+78h+dwFlagsAndAttributes], 40000000h; dwFlagsAndAttributes
0x18002ed9d  xor     r9d, r9d; lpSecurityAttributes
0x18002eda0  mov     rcx, rbx; lpFileName
0x18002eda3  mov     [rsp+78h+dwCreationDisposition], r8d; dwCreationDisposition
0x18002eda8  lea     edx, [r8-2]; dwDesiredAccess
0x18002edac  call    cs:__imp_CreateFileW
0x18002edb2  mov     rsi, rax
0x18002edb5  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002edb9  jnz     short loc_18002EE24
0x18002edbb  call    cs:__imp_GetLastError
0x18002edc1  mov     ebx, eax
0x18002edc3  test    eax, eax
0x18002edc5  jle     short loc_18002EDD0
0x18002edc7  movzx   ebx, ax
0x18002edca  or      ebx, 80070000h
0x18002edd0  mov     rax, cs:WPP_GLOBAL_Control
0x18002edd7  lea     rcx, WPP_GLOBAL_Control
0x18002edde  cmp     rax, rcx
0x18002ede1  jz      loc_18002EEE3
0x18002ede7  test    byte ptr [rax+1Ch], 1
0x18002edeb  jz      loc_18002EEE3
0x18002edf1  cmp     byte ptr [rax+19h], 2
0x18002edf5  jb      loc_18002EEE3
0x18002edfb  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18002ee00  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ee07  lea     r8, WPP_e96ad774d77a3b20501daafc53de2dbd_Traceguids
0x18002ee0e  mov     edx, 3Ch ; '<'
0x18002ee13  mov     r9d, eax
0x18002ee16  mov     rcx, [rcx+10h]
0x18002ee1a  call    WPP_SF_D
0x18002ee1f  jmp     loc_18002EEE3
0x18002ee24  mov     qword ptr [rsp+78h+dwFlagsAndAttributes], 0; lpThreadId
0x18002ee2d  lea     r8, EvtWorkerThread; lpStartAddress
0x18002ee34  mov     r9, rbp; lpParameter
0x18002ee37  mov     [rsp+78h+dwCreationDisposition], 4; dwCreationFlags
0x18002ee3f  xor     edx, edx; dwStackSize
0x18002ee41  xor     ecx, ecx; lpThreadAttributes
0x18002ee43  call    cs:__imp_CreateThread
0x18002ee49  mov     edx, [rbp+34h]
0x18002ee4c  lea     rcx, [rbp+30h]
0x18002ee50  mov     rdi, rax
0x18002ee53  call    ?Grow@?$DynArray@U_USBHUB_DEVICE_DATA@@K@@AEAAHK@Z; DynArray<_USBHUB_DEVICE_DATA,ulong>::Grow(ulong)
0x18002ee58  test    eax, eax
0x18002ee5a  jz      short loc_18002EE7F
0x18002ee5c  mov     ecx, [rbp+34h]
0x18002ee5f  mov     rax, [rbp+38h]
0x18002ee63  add     rcx, rcx
0x18002ee66  mov     [rax+rcx*8], rsi
0x18002ee6a  mov     [rax+rcx*8+8], rdi
0x18002ee6f  mov     rcx, rdi; hThread
0x18002ee72  inc     dword ptr [rbp+34h]
0x18002ee75  call    cs:__imp_ResumeThread
0x18002ee7b  xor     ebx, ebx
0x18002ee7d  jmp     short loc_18002EEE3
0x18002ee7f  mov     rax, cs:WPP_GLOBAL_Control
0x18002ee86  lea     rcx, WPP_GLOBAL_Control
0x18002ee8d  cmp     rax, rcx
0x18002ee90  jz      short loc_18002EEC2
0x18002ee92  test    byte ptr [rax+1Ch], 1
0x18002ee96  jz      short loc_18002EEC2
0x18002ee98  cmp     byte ptr [rax+19h], 2
0x18002ee9c  jb      short loc_18002EEC2
0x18002ee9e  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18002eea3  mov     rcx, cs:WPP_GLOBAL_Control
0x18002eeaa  lea     r8, WPP_e96ad774d77a3b20501daafc53de2dbd_Traceguids
0x18002eeb1  mov     edx, 3Dh ; '='
0x18002eeb6  mov     r9d, eax
0x18002eeb9  mov     rcx, [rcx+10h]
0x18002eebd  call    WPP_SF_D
0x18002eec2  test    rsi, rsi
0x18002eec5  jz      short loc_18002EED0
0x18002eec7  mov     rcx, rsi; hObject
0x18002eeca  call    cs:__imp_CloseHandle
0x18002eed0  mov     ebx, 80070008h
0x18002eed5  test    rdi, rdi
0x18002eed8  jz      short loc_18002EEE3
0x18002eeda  mov     rcx, rdi; hObject
0x18002eedd  call    cs:__imp_CloseHandle
0x18002eee3  mov     eax, ebx
0x18002eee5  add     rsp, 58h
0x18002eee9  pop     rdi
0x18002eeea  pop     rsi
0x18002eeeb  pop     rbp
0x18002eeec  pop     rbx
0x18002eeed  retn
```
