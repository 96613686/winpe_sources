# CHMELibraryPathMonitor::Initialize(ushort const *)

- ea: `0x14008add8`
- end: `0x14008af49`
- name: `?Initialize@CHMELibraryPathMonitor@@QEAAJPEBG@Z`
- size: `369`
- prototype: `__int64 __fastcall(CHMELibraryPathMonitor *__hidden this, LPCWSTR lpPathName)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x1400798c8`

## callees

- `0x14000c780`
- `0x14008add8`
- `0x14008ba54`

## import_xrefs

- `KERNEL32!CreateThread` at `0x14008aed5`
- `KERNEL32!CreateThread` at `0x14008aed5`
- `KERNEL32!FindCloseChangeNotification` at `0x14008af0f`
- `KERNEL32!FindCloseChangeNotification` at `0x14008af27`
- `KERNEL32!FindCloseChangeNotification` at `0x14008af0f`
- `KERNEL32!FindCloseChangeNotification` at `0x14008af27`
- `KERNEL32!FindFirstChangeNotificationW` at `0x14008ae32`
- `KERNEL32!FindFirstChangeNotificationW` at `0x14008ae90`
- `KERNEL32!FindFirstChangeNotificationW` at `0x14008ae32`
- `KERNEL32!FindFirstChangeNotificationW` at `0x14008ae90`
- `KERNEL32!CreateEventW` at `0x14008adf7`
- `KERNEL32!CreateEventW` at `0x14008adf7`
- `KERNEL32!GetLastError` at `0x14008ae0c`
- `KERNEL32!GetLastError` at `0x14008ae42`
- `KERNEL32!GetLastError` at `0x14008aea0`
- `KERNEL32!GetLastError` at `0x14008aee4`
- `KERNEL32!GetLastError` at `0x14008ae0c`
- `KERNEL32!GetLastError` at `0x14008ae42`
- `KERNEL32!GetLastError` at `0x14008aea0`
- `KERNEL32!GetLastError` at `0x14008aee4`
- `ole32!CoTaskMemFree` at `0x14008aefb`
- `ole32!CoTaskMemFree` at `0x14008aefb`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x14008ae76`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x14008ae76`

## pseudocode

```c
__int64 __fastcall CHMELibraryPathMonitor::Initialize(CHMELibraryPathMonitor *this, LPCWSTR lpPathName)
{
  HANDLE EventW; // rax
  signed int LastError; // eax
  int v6; // ebx
  HANDLE v7; // rax
  signed int v8; // eax
  HANDLE v9; // rax
  signed int v10; // eax
  HANDLE Thread; // rax
  signed int v12; // eax
  void *v13; // rcx
  void *v14; // rcx
  PWSTR ppszPath; // [rsp+60h] [rbp+8h] BYREF

  ATL::CSimpleStringT<unsigned short,0>::SetString(this, lpPathName);
  EventW = CreateEventW(0, 0, 0, 0);
  *((_QWORD *)this + 2) = EventW;
  if ( !EventW )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    if ( v6 < 0 )
      goto LABEL_18;
  }
  v7 = FindFirstChangeNotificationW(lpPathName, 1, 0x13u);
  *((_QWORD *)this + 3) = v7;
  if ( v7 == (HANDLE)-1LL )
  {
    v8 = GetLastError();
    v6 = v8;
    if ( v8 > 0 )
      v6 = (unsigned __int16)v8 | 0x80070000;
    if ( v6 < 0 )
      goto LABEL_18;
  }
  ppszPath = 0;
  v6 = SHGetKnownFolderPath(&FOLDERID_PublicLibraries, 0, 0, &ppszPath);
  if ( v6 >= 0 )
  {
    v9 = FindFirstChangeNotificationW(ppszPath, 1, 0x13u);
    *((_QWORD *)this + 4) = v9;
    if ( v9 != (HANDLE)-1LL )
      goto LABEL_14;
    v10 = GetLastError();
    v6 = v10;
    if ( v10 > 0 )
      v6 = (unsigned __int16)v10 | 0x80070000;
    if ( v6 >= 0 )
    {
LABEL_14:
      Thread = CreateThread(0, 0, CHMELibraryPathMonitor::_FolderWatchProc, this, 0, 0);
      *((_QWORD *)this + 1) = Thread;
      if ( !Thread )
      {
        v12 = GetLastError();
        v6 = v12;
        if ( v12 > 0 )
          v6 = (unsigned __int16)v12 | 0x80070000;
      }
    }
  }
  CoTaskMemFree(ppszPath);
  if ( v6 < 0 )
  {
LABEL_18:
    v13 = (void *)*((_QWORD *)this + 3);
    if ( v13 != (void *)-1LL )
    {
      FindCloseChangeNotification(v13);
      *((_QWORD *)this + 3) = -1;
    }
    v14 = (void *)*((_QWORD *)this + 4);
    if ( v14 != (void *)-1LL )
    {
      FindCloseChangeNotification(v14);
      *((_QWORD *)this + 4) = -1;
    }
    CHMELibraryPathMonitor::_ClearLibraryPathFolderMonitoring(this);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x14008add8  push    rbx
0x14008adda  push    rsi
0x14008addb  push    rdi
0x14008addc  push    r15
0x14008adde  sub     rsp, 38h
0x14008ade2  mov     rsi, rdx
0x14008ade5  mov     rdi, rcx
0x14008ade8  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *)
0x14008aded  xor     r9d, r9d; lpName
0x14008adf0  xor     r8d, r8d; bInitialState
0x14008adf3  xor     edx, edx; bManualReset
0x14008adf5  xor     ecx, ecx; lpEventAttributes
0x14008adf7  call    cs:__imp_CreateEventW
0x14008adfd  mov     [rdi+10h], rax
0x14008ae01  mov     r15d, 80070000h
0x14008ae07  test    rax, rax
0x14008ae0a  jnz     short loc_14008AE26
0x14008ae0c  call    cs:__imp_GetLastError
0x14008ae12  mov     ebx, eax
0x14008ae14  test    eax, eax
0x14008ae16  jle     short loc_14008AE1E
0x14008ae18  movzx   ebx, ax
0x14008ae1b  or      ebx, r15d
0x14008ae1e  test    ebx, ebx
0x14008ae20  js      loc_14008AF05
0x14008ae26  mov     edx, 1; bWatchSubtree
0x14008ae2b  mov     rcx, rsi; lpPathName
0x14008ae2e  lea     r8d, [rdx+12h]; dwNotifyFilter
0x14008ae32  call    cs:__imp_FindFirstChangeNotificationW
0x14008ae38  mov     [rdi+18h], rax
0x14008ae3c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14008ae40  jnz     short loc_14008AE5C
0x14008ae42  call    cs:__imp_GetLastError
0x14008ae48  mov     ebx, eax
0x14008ae4a  test    eax, eax
0x14008ae4c  jle     short loc_14008AE54
0x14008ae4e  movzx   ebx, ax
0x14008ae51  or      ebx, r15d
0x14008ae54  test    ebx, ebx
0x14008ae56  js      loc_14008AF05
0x14008ae5c  lea     r9, [rsp+58h+ppszPath]; ppszPath
0x14008ae61  mov     [rsp+58h+ppszPath], 0
0x14008ae6a  xor     r8d, r8d; hToken
0x14008ae6d  lea     rcx, FOLDERID_PublicLibraries; rfid
0x14008ae74  xor     edx, edx; dwFlags
0x14008ae76  call    cs:__imp_SHGetKnownFolderPath
0x14008ae7c  mov     ebx, eax
0x14008ae7e  test    eax, eax
0x14008ae80  js      short loc_14008AEF6
0x14008ae82  mov     rcx, [rsp+58h+ppszPath]; lpPathName
0x14008ae87  mov     edx, 1; bWatchSubtree
0x14008ae8c  lea     r8d, [rdx+12h]; dwNotifyFilter
0x14008ae90  call    cs:__imp_FindFirstChangeNotificationW
0x14008ae96  mov     [rdi+20h], rax
0x14008ae9a  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14008ae9e  jnz     short loc_14008AEB6
0x14008aea0  call    cs:__imp_GetLastError
0x14008aea6  mov     ebx, eax
0x14008aea8  test    eax, eax
0x14008aeaa  jle     short loc_14008AEB2
0x14008aeac  movzx   ebx, ax
0x14008aeaf  or      ebx, r15d
0x14008aeb2  test    ebx, ebx
0x14008aeb4  js      short loc_14008AEF6
0x14008aeb6  mov     [rsp+58h+lpThreadId], 0; lpThreadId
0x14008aebf  lea     r8, ?_FolderWatchProc@CHMELibraryPathMonitor@@KAKPEAX@Z; lpStartAddress
0x14008aec6  mov     r9, rdi; lpParameter
0x14008aec9  mov     [rsp+58h+dwCreationFlags], 0; dwCreationFlags
0x14008aed1  xor     edx, edx; dwStackSize
0x14008aed3  xor     ecx, ecx; lpThreadAttributes
0x14008aed5  call    cs:__imp_CreateThread
0x14008aedb  mov     [rdi+8], rax
0x14008aedf  test    rax, rax
0x14008aee2  jnz     short loc_14008AEF6
0x14008aee4  call    cs:__imp_GetLastError
0x14008aeea  mov     ebx, eax
0x14008aeec  test    eax, eax
0x14008aeee  jle     short loc_14008AEF6
0x14008aef0  movzx   ebx, ax
0x14008aef3  or      ebx, r15d
0x14008aef6  mov     rcx, [rsp+58h+ppszPath]; pv
0x14008aefb  call    cs:__imp_CoTaskMemFree
0x14008af01  test    ebx, ebx
0x14008af03  jns     short loc_14008AF3D
0x14008af05  mov     rcx, [rdi+18h]; hChangeHandle
0x14008af09  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x14008af0d  jz      short loc_14008AF1D
0x14008af0f  call    cs:__imp_FindCloseChangeNotification
0x14008af15  mov     qword ptr [rdi+18h], 0FFFFFFFFFFFFFFFFh
0x14008af1d  mov     rcx, [rdi+20h]; hChangeHandle
0x14008af21  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x14008af25  jz      short loc_14008AF35
0x14008af27  call    cs:__imp_FindCloseChangeNotification
0x14008af2d  mov     qword ptr [rdi+20h], 0FFFFFFFFFFFFFFFFh
0x14008af35  mov     rcx, rdi; this
0x14008af38  call    ?_ClearLibraryPathFolderMonitoring@CHMELibraryPathMonitor@@IEAAXXZ; CHMELibraryPathMonitor::_ClearLibraryPathFolderMonitoring(void)
0x14008af3d  mov     eax, ebx
0x14008af3f  add     rsp, 38h
0x14008af43  pop     r15
0x14008af45  pop     rdi
0x14008af46  pop     rsi
0x14008af47  pop     rbx
0x14008af48  retn
```
