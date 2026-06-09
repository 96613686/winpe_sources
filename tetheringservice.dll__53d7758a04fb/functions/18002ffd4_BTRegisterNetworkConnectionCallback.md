# BTRegisterNetworkConnectionCallback

- ea: `0x18002ffd4`
- end: `0x180030174`
- name: `BTRegisterNetworkConnectionCallback`
- size: `416`
- prototype: `__int64 __fastcall(volatile signed __int32 **, __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1800256e4`

## callees

- `0x180003088`
- `0x18002ffd4`
- `0x18003017c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180030081`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003009b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180030081`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003009b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030103`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030103`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x1800300f8`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x1800300f8`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800300cd`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800300cd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180030118`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180030127`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180030136`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180030145`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180030118`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180030127`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180030136`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180030145`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800300ed`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003014e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800300ed`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003014e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180030064`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180030064`

## pseudocode

```c
__int64 __fastcall BTRegisterNetworkConnectionCallback(volatile signed __int32 **a1, __int64 a2, __int64 a3)
{
  volatile signed __int32 *v5; // rax
  volatile signed __int32 *v6; // rbx
  DWORD LastError; // edi
  HANDLE FileW; // rax
  HANDLE EventW; // rax
  HANDLE v10; // rax
  HANDLE Thread; // rax
  void *v12; // rcx
  void *v13; // rcx
  void *v14; // rcx
  void *v15; // rcx

  if ( !a1 )
    return 87;
  *a1 = 0;
  v5 = (volatile signed __int32 *)BTAllocMem(0x50u);
  v6 = v5;
  if ( !v5 )
    return 8;
  memset_0((void *)v5, 0, 0x50u);
  _InterlockedIncrement(v6 + 18);
  *((_QWORD *)v6 + 1) = a3;
  *(_QWORD *)v6 = HandleNotificationStatic;
  *((_QWORD *)v6 + 2) = -1;
  FileW = CreateFileW(L"\\\\.\\\\BthPan", 0xC0000000, 3u, 0, 3u, 0x40000000u, 0);
  *((_QWORD *)v6 + 2) = FileW;
  if ( FileW == (HANDLE)-1LL )
    goto LABEL_11;
  EventW = CreateEventW(0, 0, 0, 0);
  *((_QWORD *)v6 + 6) = EventW;
  if ( !EventW )
    goto LABEL_11;
  v10 = CreateEventW(0, 1, 0, 0);
  *((_QWORD *)v6 + 8) = v10;
  if ( !v10 )
    goto LABEL_11;
  _InterlockedIncrement(v6 + 18);
  Thread = CreateThread(0, 0, BTNetworkConnectionThreadFunc, (LPVOID)v6, 4u, 0);
  *((_QWORD *)v6 + 7) = Thread;
  if ( Thread )
  {
    if ( ResumeThread(Thread) != -1 )
    {
      *a1 = v6;
      return 0;
    }
LABEL_11:
    LastError = GetLastError();
    if ( !LastError )
      return LastError;
    goto LABEL_12;
  }
  LastError = 87;
  if ( _InterlockedExchangeAdd(v6 + 18, 0xFFFFFFFF) == 1 )
    LocalFree((HLOCAL)v6);
LABEL_12:
  v12 = (void *)*((_QWORD *)v6 + 8);
  if ( v12 )
    CloseHandle(v12);
  v13 = (void *)*((_QWORD *)v6 + 2);
  if ( v13 != (void *)-1LL )
    CloseHandle(v13);
  v14 = (void *)*((_QWORD *)v6 + 6);
  if ( v14 )
    CloseHandle(v14);
  v15 = (void *)*((_QWORD *)v6 + 7);
  if ( v15 )
    CloseHandle(v15);
  LocalFree((HLOCAL)v6);
  return LastError;
}

```

## disassembly

```asm
0x18002ffd4  mov     [rsp+arg_0], rbx
0x18002ffd9  mov     [rsp+arg_10], rsi
0x18002ffde  push    rdi
0x18002ffdf  sub     rsp, 40h
0x18002ffe3  mov     rsi, r8
0x18002ffe6  mov     rdi, rcx
0x18002ffe9  test    rcx, rcx
0x18002ffec  jz      loc_18003015D
0x18002fff2  mov     qword ptr [rcx], 0
0x18002fff9  mov     ecx, 50h ; 'P'; Size
0x18002fffe  call    BTAllocMem
0x180030003  mov     rbx, rax
0x180030006  test    rax, rax
0x180030009  jnz     short loc_180030013
0x18003000b  lea     edi, [rax+8]
0x18003000e  jmp     loc_180030162
0x180030013  xor     edx, edx; Val
0x180030015  mov     rcx, rbx; void *
0x180030018  lea     r8d, [rdx+50h]; Size
0x18003001c  call    memset_0
0x180030021  lock inc dword ptr [rbx+48h]
0x180030025  mov     [rbx+8], rsi
0x180030029  lea     rax, ?HandleNotificationStatic@@YAXPEAXPEAU_BT_ADDRESS@@H@Z; HandleNotificationStatic(void *,_BT_ADDRESS *,int)
0x180030030  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180030034  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x18003003d  mov     [rsp+48h+dwFlagsAndAttributes], 40000000h; dwFlagsAndAttributes
0x180030045  lea     rcx, FileName; "\\\\.\\\\BthPan"
0x18003004c  xor     r9d, r9d; lpSecurityAttributes
0x18003004f  mov     [rbx], rax
0x180030052  mov     edx, 0C0000000h; dwDesiredAccess
0x180030057  mov     [rbx+10h], rsi
0x18003005b  lea     r8d, [rsi+4]; dwShareMode
0x18003005f  mov     [rsp+48h+dwCreationDisposition], r8d; dwCreationDisposition
0x180030064  call    cs:__imp_CreateFileW
0x18003006a  mov     [rbx+10h], rax
0x18003006e  cmp     rax, rsi
0x180030071  jz      loc_180030103
0x180030077  xor     r9d, r9d; lpName
0x18003007a  xor     r8d, r8d; bInitialState
0x18003007d  xor     edx, edx; bManualReset
0x18003007f  xor     ecx, ecx; lpEventAttributes
0x180030081  call    cs:__imp_CreateEventW
0x180030087  mov     [rbx+30h], rax
0x18003008b  test    rax, rax
0x18003008e  jz      short loc_180030103
0x180030090  xor     r9d, r9d; lpName
0x180030093  lea     edx, [rsi+2]; bManualReset
0x180030096  xor     r8d, r8d; bInitialState
0x180030099  xor     ecx, ecx; lpEventAttributes
0x18003009b  call    cs:__imp_CreateEventW
0x1800300a1  mov     [rbx+40h], rax
0x1800300a5  test    rax, rax
0x1800300a8  jz      short loc_180030103
0x1800300aa  lock inc dword ptr [rbx+48h]
0x1800300ae  mov     qword ptr [rsp+48h+dwFlagsAndAttributes], 0; lpThreadId
0x1800300b7  lea     r8, BTNetworkConnectionThreadFunc; lpStartAddress
0x1800300be  mov     r9, rbx; lpParameter
0x1800300c1  mov     [rsp+48h+dwCreationDisposition], 4; dwCreationFlags
0x1800300c9  xor     edx, edx; dwStackSize
0x1800300cb  xor     ecx, ecx; lpThreadAttributes
0x1800300cd  call    cs:__imp_CreateThread
0x1800300d3  mov     [rbx+38h], rax
0x1800300d7  test    rax, rax
0x1800300da  jnz     short loc_1800300F5
0x1800300dc  lea     edi, [rsi+58h]
0x1800300df  mov     eax, esi
0x1800300e1  lock xadd [rbx+48h], eax
0x1800300e6  add     eax, esi
0x1800300e8  jnz     short loc_18003010F
0x1800300ea  mov     rcx, rbx; hMem
0x1800300ed  call    cs:__imp_LocalFree
0x1800300f3  jmp     short loc_18003010F
0x1800300f5  mov     rcx, rax; hThread
0x1800300f8  call    cs:__imp_ResumeThread
0x1800300fe  cmp     eax, 0FFFFFFFFh
0x180030101  jnz     short loc_180030156
0x180030103  call    cs:__imp_GetLastError
0x180030109  mov     edi, eax
0x18003010b  test    eax, eax
0x18003010d  jz      short loc_180030162
0x18003010f  mov     rcx, [rbx+40h]; hObject
0x180030113  test    rcx, rcx
0x180030116  jz      short loc_18003011E
0x180030118  call    cs:__imp_CloseHandle
0x18003011e  mov     rcx, [rbx+10h]; hObject
0x180030122  cmp     rcx, rsi
0x180030125  jz      short loc_18003012D
0x180030127  call    cs:__imp_CloseHandle
0x18003012d  mov     rcx, [rbx+30h]; hObject
0x180030131  test    rcx, rcx
0x180030134  jz      short loc_18003013C
0x180030136  call    cs:__imp_CloseHandle
0x18003013c  mov     rcx, [rbx+38h]; hObject
0x180030140  test    rcx, rcx
0x180030143  jz      short loc_18003014B
0x180030145  call    cs:__imp_CloseHandle
0x18003014b  mov     rcx, rbx; hMem
0x18003014e  call    cs:__imp_LocalFree
0x180030154  jmp     short loc_180030162
0x180030156  mov     [rdi], rbx
0x180030159  xor     edi, edi
0x18003015b  jmp     short loc_180030162
0x18003015d  mov     edi, 57h ; 'W'
0x180030162  mov     rbx, [rsp+48h+arg_0]
0x180030167  mov     eax, edi
0x180030169  mov     rsi, [rsp+48h+arg_10]
0x18003016e  add     rsp, 40h
0x180030172  pop     rdi
0x180030173  retn
```
