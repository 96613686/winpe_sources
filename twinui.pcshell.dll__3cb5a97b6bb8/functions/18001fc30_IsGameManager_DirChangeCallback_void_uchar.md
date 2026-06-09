# IsGameManager::DirChangeCallback(void *,uchar)

- ea: `0x18001fc30`
- end: `0x18001fdbf`
- name: `?DirChangeCallback@IsGameManager@@CAXPEAXE@Z`
- size: `399`
- prototype: `void __stdcall(PVOID, BOOLEAN)`
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180016e68`
- `0x18001fc30`
- `0x18001fdc8`
- `0x1800200ac`
- `0x180031c70`
- `0x1806fa010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001fc79`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001fc96`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001fcb6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001fc79`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001fc96`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001fcb6`
- `api-ms-win-core-file-l1-1-0!FindNextChangeNotification` at `0x18001fcd6`
- `api-ms-win-core-file-l1-1-0!FindNextChangeNotification` at `0x18001fcd6`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x18001fd10`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x18001fd10`
- `api-ms-win-core-kernel32-legacy-l1-1-0!UnregisterWait` at `0x18001fd2d`
- `api-ms-win-core-kernel32-legacy-l1-1-0!UnregisterWait` at `0x18001fd2d`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x18001fc82`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x18001fca2`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x18001fcbf`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x18001fc82`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x18001fca2`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x18001fcbf`

## string_xrefs

- `0x18001fd5b`: `pcshell\twinui\broadcastdvrcomponent\lib\isgamemanager.cpp`
- `0x18001fd8e`: `pcshell\twinui\broadcastdvrcomponent\lib\isgamemanager.cpp`
- `0x18001fda9`: `pcshell\twinui\broadcastdvrcomponent\lib\isgamemanager.cpp`

## pseudocode

```c
void __fastcall IsGameManager::DirChangeCallback(PVOID a1)
{
  __int64 v1; // rsi
  const WCHAR *StringRawBuffer; // rax
  const WCHAR *v4; // rax
  int v5; // ebx
  const WCHAR *v6; // rax
  const char *v7; // r9
  void *v8; // rdx
  const char *v9; // r9
  void *v10; // rcx
  int v11; // eax
  ULONG dwMilliseconds; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  void *phNewWaitObject; // [rsp+40h] [rbp+8h] BYREF

  v1 = *((_QWORD *)a1 + 4);
  GameDVRTraceProvider::IsGameManager_DirChangeCallback(*((const unsigned __int16 **)a1 + 1));
  if ( IsGameManager::_pStaticThis && *((_BYTE *)IsGameManager::_pStaticThis + 48) != 1 )
  {
    if ( *(_DWORD *)a1 == 1
      || (StringRawBuffer = WindowsGetStringRawBuffer(*((HSTRING *)a1 + 6), 0), PathFileExistsW(StringRawBuffer)) )
    {
      (*(void (__fastcall **)(IsGameManager *))(*(_QWORD *)IsGameManager::_pStaticThis + 48LL))(IsGameManager::_pStaticThis);
    }
    v4 = WindowsGetStringRawBuffer(*((HSTRING *)a1 + 7), 0);
    v5 = *((_DWORD *)a1 + 7);
    if ( v5 == PathFileExistsW(v4) || (v6 = WindowsGetStringRawBuffer(*((HSTRING *)a1 + 8), 0), !PathFileExistsW(v6)) )
    {
      v11 = IsGameManager::RegisterKGLLocationForNotifications(
              IsGameManager::_pStaticThis,
              (struct KGLUpdateLocationInfo *)a1);
      if ( v11 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x863,
          (unsigned int)"pcshell\\twinui\\broadcastdvrcomponent\\lib\\isgamemanager.cpp",
          (const char *)(unsigned int)v11,
          dwMilliseconds);
    }
    else if ( v1 == *((_QWORD *)a1 + 4) )
    {
      if ( !FindNextChangeNotification(*((HANDLE *)a1 + 4)) )
        wil::details::in1diag3::_Log_GetLastError(
          retaddr,
          (void *)0x86B,
          (unsigned int)"pcshell\\twinui\\broadcastdvrcomponent\\lib\\isgamemanager.cpp",
          v7);
      v8 = (void *)*((_QWORD *)a1 + 4);
      phNewWaitObject = (void *)-1LL;
      if ( RegisterWaitForSingleObject(&phNewWaitObject, v8, IsGameManager::DirChangeCallback, a1, 0xFFFFFFFF, 0xCu) )
      {
        v10 = (void *)_InterlockedExchange64((volatile __int64 *)a1 + 5, (__int64)phNewWaitObject);
        if ( v10 != (void *)-1LL )
          UnregisterWait(v10);
      }
      else
      {
        wil::details::in1diag3::_Log_GetLastError(
          retaddr,
          (void *)0x884,
          (unsigned int)"pcshell\\twinui\\broadcastdvrcomponent\\lib\\isgamemanager.cpp",
          v9);
      }
    }
  }
}

```

## disassembly

```asm
0x18001fc30  mov     [rsp+arg_8], rbx
0x18001fc35  mov     [rsp+arg_10], rsi
0x18001fc3a  push    rdi
0x18001fc3b  sub     rsp, 30h
0x18001fc3f  mov     rsi, [rcx+20h]
0x18001fc43  mov     rdi, rcx
0x18001fc46  mov     rcx, [rcx+8]; unsigned __int16 *
0x18001fc4a  call    ?IsGameManager_DirChangeCallback@GameDVRTraceProvider@@SAXPEBG@Z; GameDVRTraceProvider::IsGameManager_DirChangeCallback(ushort const *)
0x18001fc4f  mov     rax, cs:?_pStaticThis@IsGameManager@@0PEAV1@EA; IsGameManager * IsGameManager::_pStaticThis
0x18001fc56  test    rax, rax
0x18001fc59  jz      loc_18001FD33
0x18001fc5f  mov     al, [rax+30h]
0x18001fc62  cmp     al, 1
0x18001fc64  jz      loc_18001FD33
0x18001fc6a  cmp     dword ptr [rdi], 1
0x18001fc6d  jz      loc_18001FD71
0x18001fc73  mov     rcx, [rdi+30h]; string
0x18001fc77  xor     edx, edx; length
0x18001fc79  call    cs:__imp_WindowsGetStringRawBuffer
0x18001fc7f  mov     rcx, rax; pszPath
0x18001fc82  call    cs:__imp_PathFileExistsW
0x18001fc88  test    eax, eax
0x18001fc8a  jnz     loc_18001FD71
0x18001fc90  mov     rcx, [rdi+38h]; string
0x18001fc94  xor     edx, edx; length
0x18001fc96  call    cs:__imp_WindowsGetStringRawBuffer
0x18001fc9c  mov     ebx, [rdi+1Ch]
0x18001fc9f  mov     rcx, rax; pszPath
0x18001fca2  call    cs:__imp_PathFileExistsW
0x18001fca8  cmp     ebx, eax
0x18001fcaa  jz      loc_18001FD43
0x18001fcb0  mov     rcx, [rdi+40h]; string
0x18001fcb4  xor     edx, edx; length
0x18001fcb6  call    cs:__imp_WindowsGetStringRawBuffer
0x18001fcbc  mov     rcx, rax; pszPath
0x18001fcbf  call    cs:__imp_PathFileExistsW
0x18001fcc5  test    eax, eax
0x18001fcc7  jz      short loc_18001FD43
0x18001fcc9  mov     rax, [rdi+20h]
0x18001fccd  cmp     rsi, rax
0x18001fcd0  jnz     short loc_18001FD33
0x18001fcd2  mov     rcx, [rdi+20h]; hChangeHandle
0x18001fcd6  call    cs:__imp_FindNextChangeNotification
0x18001fcdc  test    eax, eax
0x18001fcde  jz      loc_18001FD89
0x18001fce4  mov     rdx, [rdi+20h]; hObject
0x18001fce8  lea     r8, ?DirChangeCallback@IsGameManager@@CAXPEAXE@Z; Callback
0x18001fcef  mov     [rsp+38h+dwFlags], 0Ch; dwFlags
0x18001fcf7  lea     rcx, [rsp+38h+phNewWaitObject]; phNewWaitObject
0x18001fcfc  mov     r9, rdi; Context
0x18001fcff  mov     [rsp+38h+dwMilliseconds], 0FFFFFFFFh; dwMilliseconds
0x18001fd07  mov     [rsp+38h+phNewWaitObject], 0FFFFFFFFFFFFFFFFh
0x18001fd10  call    cs:__imp_RegisterWaitForSingleObject
0x18001fd16  test    eax, eax
0x18001fd18  jz      loc_18001FDA4
0x18001fd1e  mov     rcx, [rsp+38h+phNewWaitObject]
0x18001fd23  xchg    rcx, [rdi+28h]; WaitHandle
0x18001fd27  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18001fd2b  jz      short loc_18001FD33
0x18001fd2d  call    cs:__imp_UnregisterWait
0x18001fd33  mov     rbx, [rsp+38h+arg_8]
0x18001fd38  mov     rsi, [rsp+38h+arg_10]
0x18001fd3d  add     rsp, 30h
0x18001fd41  pop     rdi
0x18001fd42  retn
0x18001fd43  mov     rcx, cs:?_pStaticThis@IsGameManager@@0PEAV1@EA; this
0x18001fd4a  mov     rdx, rdi; struct KGLUpdateLocationInfo *
0x18001fd4d  call    ?RegisterKGLLocationForNotifications@IsGameManager@@AEAAJPEAUKGLUpdateLocationInfo@@@Z; IsGameManager::RegisterKGLLocationForNotifications(KGLUpdateLocationInfo *)
0x18001fd52  test    eax, eax
0x18001fd54  jns     short loc_18001FD33
0x18001fd56  mov     rcx, [rsp+38h]; this
0x18001fd5b  lea     r8, aPcshellTwinuiB; "pcshell\\twinui\\broadcastdvrcomponent"...
0x18001fd62  mov     r9d, eax; char *
0x18001fd65  mov     edx, 863h; void *
0x18001fd6a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001fd6f  jmp     short loc_18001FD33
0x18001fd71  mov     rcx, cs:?_pStaticThis@IsGameManager@@0PEAV1@EA; IsGameManager * IsGameManager::_pStaticThis
0x18001fd78  mov     rax, [rcx]
0x18001fd7b  mov     rax, [rax+30h]
0x18001fd7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fd84  jmp     loc_18001FC90
0x18001fd89  mov     rcx, [rsp+38h]; this
0x18001fd8e  lea     r8, aPcshellTwinuiB; "pcshell\\twinui\\broadcastdvrcomponent"...
0x18001fd95  mov     edx, 86Bh; void *
0x18001fd9a  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x18001fd9f  jmp     loc_18001FCE4
0x18001fda4  mov     rcx, [rsp+38h]; this
0x18001fda9  lea     r8, aPcshellTwinuiB; "pcshell\\twinui\\broadcastdvrcomponent"...
0x18001fdb0  mov     edx, 884h; void *
0x18001fdb5  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x18001fdba  jmp     loc_18001FD33
```
