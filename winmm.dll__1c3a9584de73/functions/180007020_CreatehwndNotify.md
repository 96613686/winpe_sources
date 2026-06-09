# CreatehwndNotify

- ea: `0x180007020`
- end: `0x180007281`
- name: `CreatehwndNotify`
- size: `609`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180004e0c`
- `0x180010c10`

## callees

- `0x180007020`
- `0x180007288`
- `0x18000b1f8`
- `0x18000b6d4`
- `0x180015eb4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000702b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000702b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007042`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007132`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800071f8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007042`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007132`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800071f8`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800070f7`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800070f7`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18000708a`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18000708a`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800070c3`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800070c3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800070cf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007119`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800070cf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007119`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800071cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000722c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800071cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000722c`

## pseudocode

```c
__int64 CreatehwndNotify()
{
  HANDLE EventA; // rsi
  HANDLE Thread; // rdi
  BOOL v3; // ebx
  DWORD v4; // eax
  DWORD LastError; // eax

  EnterCriticalSection(&mciCritSec);
  if ( hwndNotify )
  {
    LeaveCriticalSection(&mciCritSec);
    return 1;
  }
  else if ( (unsigned int)CreateMMClass() )
  {
    if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_c5fb3da3b9933c3192700b6086acf07d_Traceguids);
    }
    EventA = CreateEventA(0, 0, 0, 0);
    if ( EventA )
    {
      Thread = CreateThread(0, 0, (LPTHREAD_START_ROUTINE)mciwindow, EventA, 0, &mciWindowThreadId);
      CloseHandle(Thread);
      if ( Thread )
      {
        if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            25,
            WPP_c5fb3da3b9933c3192700b6086acf07d_Traceguids,
            mciWindowThreadId);
        }
        WaitForSingleObject(EventA, 0xFFFFFFFF);
        if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_c5fb3da3b9933c3192700b6086acf07d_Traceguids, hwndNotify);
        }
      }
      else if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control
             && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
             && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        LastError = GetLastError();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_c5fb3da3b9933c3192700b6086acf07d_Traceguids, LastError);
      }
      CloseHandle(EventA);
    }
    v3 = hwndNotify != 0;
    LeaveCriticalSection(&mciCritSec);
    return v3;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v4 = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_c5fb3da3b9933c3192700b6086acf07d_Traceguids, v4);
    }
    LeaveCriticalSection(&mciCritSec);
    return 0;
  }
}

```

## disassembly

```asm
0x180007020  sub     rsp, 38h
0x180007024  lea     rcx, mciCritSec; lpCriticalSection
0x18000702b  call    cs:__imp_EnterCriticalSection
0x180007031  cmp     cs:hwndNotify, 0
0x180007039  jz      short loc_180007052
0x18000703b  lea     rcx, mciCritSec; lpCriticalSection
0x180007042  call    cs:__imp_LeaveCriticalSection
0x180007048  mov     eax, 1
0x18000704d  add     rsp, 38h
0x180007051  retn
0x180007052  mov     [rsp+38h+arg_0], rbx
0x180007057  call    ?CreateMMClass@@YAHXZ; CreateMMClass(void)
0x18000705c  test    eax, eax
0x18000705e  jz      loc_1800071AA
0x180007064  mov     rcx, cs:WPP_GLOBAL_Control
0x18000706b  lea     rbx, WPP_GLOBAL_Control
0x180007072  mov     [rsp+38h+arg_8], rsi
0x180007077  cmp     rcx, rbx
0x18000707a  jnz     loc_180007179
0x180007080  xor     r9d, r9d; lpName
0x180007083  xor     r8d, r8d; bInitialState
0x180007086  xor     edx, edx; bManualReset
0x180007088  xor     ecx, ecx; lpEventAttributes
0x18000708a  call    cs:__imp_CreateEventA
0x180007090  mov     rsi, rax
0x180007093  test    rax, rax
0x180007096  jz      loc_18000711F
0x18000709c  lea     rax, ?mciWindowThreadId@@3KA; ulong mciWindowThreadId
0x1800070a3  mov     [rsp+38h+var_8], rdi
0x1800070a8  mov     [rsp+38h+lpThreadId], rax; lpThreadId
0x1800070ad  lea     r8, ?mciwindow@@YAXPEAX@Z; lpStartAddress
0x1800070b4  mov     r9, rsi; lpParameter
0x1800070b7  mov     [rsp+38h+dwCreationFlags], 0; dwCreationFlags
0x1800070bf  xor     edx, edx; dwStackSize
0x1800070c1  xor     ecx, ecx; lpThreadAttributes
0x1800070c3  call    cs:__imp_CreateThread
0x1800070c9  mov     rcx, rax; hObject
0x1800070cc  mov     rdi, rax
0x1800070cf  call    cs:__imp_CloseHandle
0x1800070d5  test    rdi, rdi
0x1800070d8  mov     rdi, [rsp+38h+var_8]
0x1800070dd  jz      loc_180007205
0x1800070e3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800070ea  cmp     rcx, rbx
0x1800070ed  jnz     short loc_180007149
0x1800070ef  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x1800070f4  mov     rcx, rsi; hHandle
0x1800070f7  call    cs:__imp_WaitForSingleObject
0x1800070fd  mov     rcx, cs:WPP_GLOBAL_Control
0x180007104  cmp     rcx, rbx
0x180007107  jz      short loc_180007116
0x180007109  test    dword ptr [rcx+1Ch], 400000h
0x180007110  jnz     loc_180007256
0x180007116  mov     rcx, rsi; hObject
0x180007119  call    cs:__imp_CloseHandle
0x18000711f  xor     ebx, ebx
0x180007121  lea     rcx, mciCritSec; lpCriticalSection
0x180007128  cmp     cs:hwndNotify, rbx
0x18000712f  setnz   bl
0x180007132  call    cs:__imp_LeaveCriticalSection
0x180007138  mov     rsi, [rsp+38h+arg_8]
0x18000713d  mov     eax, ebx
0x18000713f  mov     rbx, [rsp+38h+arg_0]
0x180007144  jmp     loc_18000704D
0x180007149  test    dword ptr [rcx+1Ch], 400000h
0x180007150  jz      short loc_1800070EF
0x180007152  cmp     byte ptr [rcx+19h], 4
0x180007156  jb      short loc_1800070EF
0x180007158  mov     r9d, cs:?mciWindowThreadId@@3KA; ulong mciWindowThreadId
0x18000715f  lea     r8, WPP_c5fb3da3b9933c3192700b6086acf07d_Traceguids
0x180007166  mov     rcx, [rcx+10h]
0x18000716a  mov     edx, 19h
0x18000716f  call    WPP_SF_d
0x180007174  jmp     loc_1800070EF
0x180007179  test    dword ptr [rcx+1Ch], 400000h
0x180007180  jz      loc_180007080
0x180007186  cmp     byte ptr [rcx+19h], 4
0x18000718a  jb      loc_180007080
0x180007190  mov     rcx, [rcx+10h]
0x180007194  lea     r8, WPP_c5fb3da3b9933c3192700b6086acf07d_Traceguids
0x18000719b  mov     edx, 17h
0x1800071a0  call    WPP_SF_
0x1800071a5  jmp     loc_180007080
0x1800071aa  mov     rax, cs:WPP_GLOBAL_Control
0x1800071b1  lea     rbx, WPP_GLOBAL_Control
0x1800071b8  cmp     rax, rbx
0x1800071bb  jz      short loc_1800071F1
0x1800071bd  test    dword ptr [rax+1Ch], 400000h
0x1800071c4  jz      short loc_1800071F1
0x1800071c6  cmp     byte ptr [rax+19h], 2
0x1800071ca  jb      short loc_1800071F1
0x1800071cc  call    cs:__imp_GetLastError
0x1800071d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800071d9  lea     r8, WPP_c5fb3da3b9933c3192700b6086acf07d_Traceguids
0x1800071e0  mov     edx, 16h
0x1800071e5  mov     r9d, eax
0x1800071e8  mov     rcx, [rcx+10h]
0x1800071ec  call    WPP_SF_d
0x1800071f1  lea     rcx, mciCritSec; lpCriticalSection
0x1800071f8  call    cs:__imp_LeaveCriticalSection
0x1800071fe  xor     eax, eax
0x180007200  jmp     loc_18000713F
0x180007205  mov     rax, cs:WPP_GLOBAL_Control
0x18000720c  cmp     rax, rbx
0x18000720f  jz      loc_180007116
0x180007215  test    dword ptr [rax+1Ch], 400000h
0x18000721c  jz      loc_180007116
0x180007222  cmp     byte ptr [rax+19h], 2
0x180007226  jb      loc_180007116
0x18000722c  call    cs:__imp_GetLastError
0x180007232  mov     rcx, cs:WPP_GLOBAL_Control
0x180007239  lea     r8, WPP_c5fb3da3b9933c3192700b6086acf07d_Traceguids
0x180007240  mov     edx, 18h
0x180007245  mov     r9d, eax
0x180007248  mov     rcx, [rcx+10h]
0x18000724c  call    WPP_SF_d
0x180007251  jmp     loc_180007116
0x180007256  cmp     byte ptr [rcx+19h], 4
0x18000725a  jb      loc_180007116
0x180007260  mov     r9, cs:hwndNotify
0x180007267  lea     r8, WPP_c5fb3da3b9933c3192700b6086acf07d_Traceguids
0x18000726e  mov     rcx, [rcx+10h]
0x180007272  mov     edx, 1Ah
0x180007277  call    WPP_SF_q
0x18000727c  jmp     loc_180007116
```
