# AutoProxyResolver::CheckAutoProxyThreadRunning(void)

- ea: `0x180063c78`
- end: `0x180063ef3`
- name: `?CheckAutoProxyThreadRunning@AutoProxyResolver@@AEAAJXZ`
- size: `635`
- prototype: `__int64 __fastcall(AutoProxyResolver *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x180063afc`

## callees

- `0x180017678`
- `0x1800639c0`
- `0x180063c78`
- `0x1800656b8`
- `0x180065730`
- `0x180065838`
- `0x1800a1d10`
- `0x1800cf008`
- `0x1800db6b0`
- `0x1800de010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180063cbf`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180063cbf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180063cd4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180063cd4`
- `api-ms-win-core-synch-l1-1-0!CreateEventExA` at `0x180063d54`
- `api-ms-win-core-synch-l1-1-0!CreateEventExA` at `0x180063d54`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180063d88`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180063d88`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x180063e18`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x180063e18`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180063ddc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180063ddc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180063e26`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180063e52`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180063e26`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180063e52`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180063cfc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180063d0a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180063cfc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180063d0a`

## pseudocode

```c
__int64 __fastcall AutoProxyResolver::CheckAutoProxyThreadRunning(AutoProxyResolver *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // r15
  signed int v3; // ebp
  LruResourceContext *v4; // rbx
  HANDLE Event; // rdi
  HANDLE Thread; // rsi
  unsigned int v7; // r14d
  int v9; // eax
  int v10; // eax
  DWORD CurrentThreadId; // eax
  __int64 v12; // rax
  signed int v13; // eax
  signed int LastError; // eax
  __int64 dwCreationFlags; // [rsp+20h] [rbp-68h]
  struct LruResourceContext *v16; // [rsp+38h] [rbp-50h] BYREF

  if ( (xmmword_180107A60 & 0x20) != 0 )
    WPP_SF_(1029, 74, WPP_9b6adbbdda853e7c1a9973765ab89a86_Traceguids);
  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 384);
  v3 = 0;
  v4 = 0;
  v16 = 0;
  Event = 0;
  Thread = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 384));
  if ( !*((_DWORD *)this + 113) )
  {
    v7 = 0;
    goto LABEL_5;
  }
  v9 = WxReferenceDll();
  v3 = v9;
  if ( v9 < 0 )
  {
    v7 = v9;
  }
  else
  {
    _InterlockedAdd((volatile signed __int32 *)this + 111, 1u);
    Event = CreateEventExA(0, 0, 1u, 0x100002u);
    if ( Event )
    {
      Thread = CreateThread(
                 0,
                 0,
                 (LPTHREAD_START_ROUTINE)AutoProxyResolver::AutoProxyThreadStart,
                 this,
                 4u,
                 (LPDWORD)this + 110);
      if ( Thread )
      {
        v10 = LruResourceContext::CreateInstance(
                (struct IResourceManager *)(-(__int64)(this != 0) & ((unsigned __int64)this + 16)),
                &v16);
        v4 = v16;
        v3 = v10;
        if ( v10 < 0 )
        {
          v7 = v10;
        }
        else
        {
          v3 = LruResourceManager::InformUsage(g_pLruResourceManager, v16);
          if ( v3 >= 0 )
          {
            CurrentThreadId = GetCurrentThreadId();
            *((_QWORD *)this + 62) = v4;
            *((_DWORD *)this + 112) = CurrentThreadId;
            v4 = 0;
            v12 = *(_QWORD *)this;
            *((_QWORD *)this + 54) = Event;
            Event = 0;
            *((_DWORD *)this + 113) = 0;
            (*(void (__fastcall **)(AutoProxyResolver *))(v12 + 8))(this);
            ResumeThread(Thread);
            v7 = v3;
            goto LABEL_5;
          }
          v7 = v3;
        }
      }
      else
      {
        LastError = GetLastError();
        v3 = LastError;
        if ( LastError > 0 )
          v3 = (unsigned __int16)LastError | 0x80070000;
        if ( v3 < 0 )
        {
          v7 = v3;
        }
        else
        {
          v7 = -2147418113;
          v3 = -2147418113;
        }
      }
    }
    else
    {
      v13 = GetLastError();
      v3 = v13;
      if ( v13 > 0 )
        v3 = (unsigned __int16)v13 | 0x80070000;
      if ( v3 < 0 )
      {
        v7 = v3;
      }
      else
      {
        v7 = -2147418113;
        v3 = -2147418113;
      }
    }
    WxDereferenceDll();
  }
LABEL_5:
  LeaveCriticalSection(v2);
  if ( (xmmword_180107A60 & 0x20) != 0 )
    WPP_SF_d(1029, 75, WPP_9b6adbbdda853e7c1a9973765ab89a86_Traceguids, (unsigned int)v3, dwCreationFlags);
  if ( v4 )
    LruResourceContext::Release(v4);
  if ( Thread )
    CloseHandle(Thread);
  if ( Event )
    CloseHandle(Event);
  return v7;
}

```

## disassembly

```asm
0x180063c78  push    rbx
0x180063c7a  push    rbp
0x180063c7b  push    rsi
0x180063c7c  push    rdi
0x180063c7d  push    r14
0x180063c7f  push    r15
0x180063c81  sub     rsp, 58h
0x180063c85  mov     rax, cs:__security_cookie
0x180063c8c  xor     rax, rsp
0x180063c8f  mov     [rsp+88h+var_48], rax
0x180063c94  mov     r14, rcx
0x180063c97  test    byte ptr cs:xmmword_180107A60, 20h
0x180063c9e  jnz     loc_180063E90
0x180063ca4  lea     r15, [r14+180h]
0x180063cab  xor     ebp, ebp
0x180063cad  xor     ebx, ebx
0x180063caf  mov     [rsp+88h+var_54], ebp
0x180063cb3  mov     rcx, r15; lpCriticalSection
0x180063cb6  mov     [rsp+88h+var_50], rbx
0x180063cbb  xor     edi, edi
0x180063cbd  xor     esi, esi
0x180063cbf  call    cs:__imp_EnterCriticalSection
0x180063cc5  cmp     [r14+1C4h], ebx
0x180063ccc  jnz     short loc_180063D2D
0x180063cce  xor     r14d, r14d
0x180063cd1  mov     rcx, r15; lpCriticalSection
0x180063cd4  call    cs:__imp_LeaveCriticalSection
0x180063cda  test    byte ptr cs:xmmword_180107A60, 20h
0x180063ce1  jnz     loc_180063ED5
0x180063ce7  test    rbx, rbx
0x180063cea  jz      short loc_180063CF4
0x180063cec  mov     rcx, rbx; this
0x180063cef  call    ?Release@LruResourceContext@@QEAAKXZ; LruResourceContext::Release(void)
0x180063cf4  test    rsi, rsi
0x180063cf7  jz      short loc_180063D02
0x180063cf9  mov     rcx, rsi; hObject
0x180063cfc  call    cs:__imp_CloseHandle
0x180063d02  test    rdi, rdi
0x180063d05  jz      short loc_180063D10
0x180063d07  mov     rcx, rdi; hObject
0x180063d0a  call    cs:__imp_CloseHandle
0x180063d10  mov     eax, r14d
0x180063d13  mov     rcx, [rsp+88h+var_48]
0x180063d18  xor     rcx, rsp; StackCookie
0x180063d1b  call    __security_check_cookie
0x180063d20  add     rsp, 58h
0x180063d24  pop     r15
0x180063d26  pop     r14
0x180063d28  pop     rdi
0x180063d29  pop     rsi
0x180063d2a  pop     rbp
0x180063d2b  pop     rbx
0x180063d2c  retn
0x180063d2d  call    ?WxReferenceDll@@YAJXZ; WxReferenceDll(void)
0x180063d32  mov     ebp, eax
0x180063d34  test    eax, eax
0x180063d36  js      loc_180063EAB
0x180063d3c  mov     r8d, 1; dwFlags
0x180063d42  lock add [r14+1BCh], r8d
0x180063d4a  xor     edx, edx; lpName
0x180063d4c  xor     ecx, ecx; lpEventAttributes
0x180063d4e  mov     r9d, 100002h; dwDesiredAccess
0x180063d54  call    cs:__imp_CreateEventExA
0x180063d5a  mov     rdi, rax
0x180063d5d  test    rax, rax
0x180063d60  jz      loc_180063E26
0x180063d66  lea     rax, [r14+1B8h]
0x180063d6d  mov     r9, r14; lpParameter
0x180063d70  mov     [rsp+88h+lpThreadId], rax; lpThreadId
0x180063d75  lea     r8, ?AutoProxyThreadStart@AutoProxyResolver@@CAKPEAX@Z; lpStartAddress
0x180063d7c  xor     edx, edx; dwStackSize
0x180063d7e  mov     dword ptr [rsp+88h+dwCreationFlags], 4; dwCreationFlags
0x180063d86  xor     ecx, ecx; lpThreadAttributes
0x180063d88  call    cs:__imp_CreateThread
0x180063d8e  mov     rsi, rax
0x180063d91  test    rax, rax
0x180063d94  jz      loc_180063E52
0x180063d9a  mov     rax, r14
0x180063d9d  lea     rcx, [r14+10h]
0x180063da1  neg     rax
0x180063da4  lea     rdx, [rsp+88h+var_50]; struct LruResourceContext **
0x180063da9  sbb     r8, r8
0x180063dac  and     rcx, r8; struct IResourceManager *
0x180063daf  call    ?CreateInstance@LruResourceContext@@SAJPEAUIResourceManager@@PEAPEAV1@@Z; LruResourceContext::CreateInstance(IResourceManager *,LruResourceContext * *)
0x180063db4  mov     rbx, [rsp+88h+var_50]
0x180063db9  mov     ebp, eax
0x180063dbb  test    eax, eax
0x180063dbd  js      loc_180063EBB
0x180063dc3  mov     rcx, cs:?g_pLruResourceManager@@3PEAVLruResourceManager@@EA; this
0x180063dca  mov     rdx, rbx; struct LruResourceContext *
0x180063dcd  call    ?InformUsage@LruResourceManager@@QEAAJPEAVLruResourceContext@@@Z; LruResourceManager::InformUsage(LruResourceContext *)
0x180063dd2  mov     ebp, eax
0x180063dd4  test    eax, eax
0x180063dd6  js      loc_180063EC8
0x180063ddc  call    cs:__imp_GetCurrentThreadId
0x180063de2  mov     [r14+1F0h], rbx
0x180063de9  mov     rcx, r14
0x180063dec  mov     [r14+1C0h], eax
0x180063df3  xor     ebx, ebx
0x180063df5  mov     rax, [r14]
0x180063df8  mov     [r14+1B0h], rdi
0x180063dff  xor     edi, edi
0x180063e01  mov     dword ptr [r14+1C4h], 0
0x180063e0c  mov     rax, [rax+8]
0x180063e10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063e15  mov     rcx, rsi; hThread
0x180063e18  call    cs:__imp_ResumeThread
0x180063e1e  mov     r14d, ebp
0x180063e21  jmp     loc_180063CD1
0x180063e26  call    cs:__imp_GetLastError
0x180063e2c  mov     ebp, eax
0x180063e2e  test    eax, eax
0x180063e30  jle     short loc_180063E3B
0x180063e32  movzx   ebp, ax
0x180063e35  or      ebp, 80070000h
0x180063e3b  test    ebp, ebp
0x180063e3d  js      short loc_180063E8B
0x180063e3f  mov     r14d, 8000FFFFh
0x180063e45  mov     ebp, r14d
0x180063e48  mov     [rsp+88h+var_54], 9F3h
0x180063e50  jmp     short loc_180063E7C
0x180063e52  call    cs:__imp_GetLastError
0x180063e58  mov     ebp, eax
0x180063e5a  test    eax, eax
0x180063e5c  jle     short loc_180063E67
0x180063e5e  movzx   ebp, ax
0x180063e61  or      ebp, 80070000h
0x180063e67  test    ebp, ebp
0x180063e69  js      short loc_180063E86
0x180063e6b  mov     r14d, 8000FFFFh
0x180063e71  mov     ebp, r14d
0x180063e74  mov     [rsp+88h+var_54], 0A00h
0x180063e7c  call    ?WxDereferenceDll@@YAXXZ; WxDereferenceDll(void)
0x180063e81  jmp     loc_180063CD1
0x180063e86  mov     r14d, ebp
0x180063e89  jmp     short loc_180063E74
0x180063e8b  mov     r14d, ebp
0x180063e8e  jmp     short loc_180063E48
0x180063e90  mov     edx, 4Ah ; 'J'
0x180063e95  lea     r8, WPP_9b6adbbdda853e7c1a9973765ab89a86_Traceguids
0x180063e9c  mov     ecx, 405h
0x180063ea1  call    WPP_SF_
0x180063ea6  jmp     loc_180063CA4
0x180063eab  mov     [rsp+88h+var_54], 9E6h
0x180063eb3  mov     r14d, eax
0x180063eb6  jmp     loc_180063CD1
0x180063ebb  mov     [rsp+88h+var_54], 0A08h
0x180063ec3  mov     r14d, eax
0x180063ec6  jmp     short loc_180063E7C
0x180063ec8  mov     [rsp+88h+var_54], 0A09h
0x180063ed0  mov     r14d, ebp
0x180063ed3  jmp     short loc_180063E7C
0x180063ed5  mov     edx, 4Bh ; 'K'
0x180063eda  lea     r8, WPP_9b6adbbdda853e7c1a9973765ab89a86_Traceguids
0x180063ee1  mov     ecx, 405h
0x180063ee6  mov     r9d, ebp
0x180063ee9  call    WPP_SF_d
0x180063eee  jmp     loc_180063CE7
```
