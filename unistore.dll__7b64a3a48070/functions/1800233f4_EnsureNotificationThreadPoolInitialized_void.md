# EnsureNotificationThreadPoolInitialized(void)

- ea: `0x1800233f4`
- end: `0x180023507`
- name: `?EnsureNotificationThreadPoolInitialized@@YAJXZ`
- size: `275`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800231ac`

## callees

- `0x1800233f4`
- `0x1800703c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180023401`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180023401`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180023423`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180023423`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002345b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002345b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x1800234ed`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x1800234ed`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x180023449`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x180023449`
- `UserDataPlatformHelperUtil!SetPoolThreadBasePriority` at `0x180023480`
- `UserDataPlatformHelperUtil!SetPoolThreadBasePriority` at `0x180023480`

## pseudocode

```c
__int64 EnsureNotificationThreadPoolInitialized(void)
{
  __int64 v0; // r8
  unsigned int v1; // ebx
  __int64 v3; // r9
  struct _TP_POOL *Threadpool; // rax
  signed int LastError; // eax
  int v6; // eax
  __int64 v7; // r8

  EnterCriticalSection(&g_clientNotifyLock);
  if ( g_notificationShutdown )
  {
    v1 = -2147418113;
    v3 = 23;
    goto LABEL_6;
  }
  if ( !ptpp )
  {
    Threadpool = CreateThreadpool(0);
    ptpp = Threadpool;
    if ( Threadpool )
    {
      v6 = SetPoolThreadBasePriority(Threadpool, -2);
      if ( v6 < 0 )
        Log_UnistoreHREvent_7((unsigned int)v6, 0, v7, 30);
      xmmword_18010D850 = 0;
      dword_18010D86C = 1;
      qword_18010D838 = (__int64)ptpp;
      dword_18010D830 = 3;
      qword_18010D840 = 0;
      qword_18010D848 = 0;
      qword_18010D860 = 0;
      dword_18010D868 = 0;
      dword_18010D870 = 72;
      SetThreadpoolThreadMaximum(ptpp, 1u);
      goto LABEL_3;
    }
    LastError = GetLastError();
    v1 = LastError;
    if ( LastError > 0 )
      v1 = (unsigned __int16)LastError | 0x80070000;
    v3 = 28;
LABEL_6:
    Log_UnistoreHREvent_7(v1, 0, v0, v3);
    goto LABEL_4;
  }
LABEL_3:
  v1 = 0;
LABEL_4:
  LeaveCriticalSection(&g_clientNotifyLock);
  return v1;
}

```

## disassembly

```asm
0x1800233f4  push    rbx
0x1800233f6  sub     rsp, 30h
0x1800233fa  lea     rcx, ?g_clientNotifyLock@@3Vrecursive_mutex@utl@@A; lpCriticalSection
0x180023401  call    cs:__imp_EnterCriticalSection
0x180023407  cmp     cs:?g_notificationShutdown@@3HA, 0; int g_notificationShutdown
0x18002340e  jnz     short loc_180023431
0x180023410  cmp     cs:ptpp, 0
0x180023418  jz      short loc_180023447
0x18002341a  xor     ebx, ebx
0x18002341c  lea     rcx, ?g_clientNotifyLock@@3Vrecursive_mutex@utl@@A; lpCriticalSection
0x180023423  call    cs:__imp_LeaveCriticalSection
0x180023429  mov     eax, ebx
0x18002342b  add     rsp, 30h
0x18002342f  pop     rbx
0x180023430  retn
0x180023431  mov     ebx, 8000FFFFh
0x180023436  mov     r9d, 17h
0x18002343c  xor     edx, edx
0x18002343e  mov     ecx, ebx
0x180023440  call    Log_UnistoreHREvent_7
0x180023445  jmp     short loc_18002341C
0x180023447  xor     ecx, ecx; reserved
0x180023449  call    cs:__imp_CreateThreadpool
0x18002344f  mov     cs:ptpp, rax
0x180023456  test    rax, rax
0x180023459  jnz     short loc_180023478
0x18002345b  call    cs:__imp_GetLastError
0x180023461  mov     ebx, eax
0x180023463  test    eax, eax
0x180023465  jle     short loc_180023470
0x180023467  movzx   ebx, ax
0x18002346a  or      ebx, 80070000h
0x180023470  mov     r9d, 1Ch
0x180023476  jmp     short loc_18002343C
0x180023478  mov     edx, 0FFFFFFFEh
0x18002347d  mov     rcx, rax
0x180023480  call    cs:__imp_?SetPoolThreadBasePriority@@YAJPEAU_TP_POOL@@J@Z; SetPoolThreadBasePriority(_TP_POOL *,long)
0x180023486  test    eax, eax
0x180023488  js      short loc_1800234F8
0x18002348a  mov     rcx, cs:ptpp; ptpp
0x180023491  xorps   xmm0, xmm0
0x180023494  mov     edx, 1; cthrdMost
0x180023499  movdqa  cs:xmmword_18010D850, xmm0
0x1800234a1  mov     cs:dword_18010D86C, edx
0x1800234a7  mov     cs:qword_18010D838, rcx
0x1800234ae  mov     cs:dword_18010D830, 3
0x1800234b8  mov     cs:qword_18010D840, 0
0x1800234c3  mov     cs:qword_18010D848, 0
0x1800234ce  mov     cs:qword_18010D860, 0
0x1800234d9  mov     cs:dword_18010D868, 0
0x1800234e3  mov     cs:dword_18010D870, 48h ; 'H'
0x1800234ed  call    cs:__imp_SetThreadpoolThreadMaximum
0x1800234f3  jmp     loc_18002341A
0x1800234f8  xor     edx, edx
0x1800234fa  mov     ecx, eax
0x1800234fc  lea     r9d, [rdx+1Eh]
0x180023500  call    Log_UnistoreHREvent_7
0x180023505  jmp     short loc_18002348A
```
