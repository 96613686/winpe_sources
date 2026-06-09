# RecreateStickyShare

- ea: `0x180023c00`
- end: `0x180023e31`
- name: `RecreateStickyShare`
- size: `561`
- prototype: `__int64 __usercall@<rax>(void *Src@<rcx>, __int64)`
- caller_count: `0`
- callee_count: `8`
- tags: `service_task`

## callees

- `0x1800023f0`
- `0x180003f60`
- `0x18001d680`
- `0x18001deb0`
- `0x18001e80c`
- `0x1800214a4`
- `0x180023c00`
- `0x1800269ac`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023d63`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023d63`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180023dca`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180023dd9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180023de8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180023df7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180023e06`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180023dca`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180023dd9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180023de8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180023df7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180023e06`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180023cd4`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180023cd4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023ce5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023d6e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023d77`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023ce5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023d6e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023d77`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180023d48`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180023d48`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180023ca8`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180023ca8`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180023d58`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180023d58`

## pseudocode

```c
__int64 __fastcall RecreateStickyShare(const WCHAR *Src, int a2, WCHAR *a3, __int64 a4, _DWORD *a5)
{
  HANDLE Thread; // rdi
  HANDLE EventW; // rbx
  int LastError; // esi
  int v11; // r8d
  DWORD ThreadId[4]; // [rsp+50h] [rbp-79h] BYREF
  HLOCAL v14; // [rsp+60h] [rbp-69h] BYREF
  int v15; // [rsp+68h] [rbp-61h]
  HLOCAL hMem; // [rsp+70h] [rbp-59h]
  HLOCAL v17; // [rsp+88h] [rbp-41h]
  HLOCAL v18; // [rsp+98h] [rbp-31h]
  HLOCAL v19; // [rsp+A8h] [rbp-21h]

  memset_0(&v14, 0, 0x78u);
  if ( GetStickyShareInfo(Src, a2, a3, (__int64 *)&v14) )
  {
    Thread = 0;
    EventW = 0;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 72, WPP_6c51fa01af1134468f88fcdefbc326dc_Traceguids, Src);
    }
    if ( v15 == 1 )
    {
      EventW = CreateEventW(0, 1, 0, 0);
      if ( EventW )
      {
        ThreadId[0] = 0;
        Thread = CreateThread(0, 0, PrintShareAnnounce, EventW, 0, ThreadId);
        if ( !Thread )
        {
          CloseHandle(EventW);
          EventW = 0;
        }
      }
      if ( v15 == 1 && !Thread )
        goto LABEL_13;
    }
    ++*a5;
    if ( (*(_BYTE *)a5 & 0x3F) == 0 )
LABEL_13:
      AnnounceServiceStatus(1);
    LastError = I_NetrShareAdd(0, 505, (wint_t *)&v14, 0, 0, 1, 1u, 0, 0, 0);
    if ( EventW )
    {
      SetEvent(EventW);
      if ( WaitForSingleObject(Thread, 0xFFFFFFFF) == -1 )
        LastError = GetLastError();
      CloseHandle(EventW);
      CloseHandle(Thread);
    }
    if ( LastError
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      WPP_SF_SSl(*((_QWORD *)WPP_GLOBAL_Control + 2), 73, v11, (_DWORD)Src, (__int64)v17, LastError);
    }
    if ( hMem )
      LocalFree(hMem);
    if ( v17 )
      LocalFree(v17);
    if ( v18 )
      LocalFree(v18);
    if ( v14 )
      LocalFree(v14);
    if ( v19 )
      LocalFree(v19);
  }
  return 0;
}

```

## disassembly

```asm
0x180023c00  mov     [rsp-8+arg_18], rbx
0x180023c05  push    rbp
0x180023c06  push    rsi
0x180023c07  push    rdi
0x180023c08  push    r14
0x180023c0a  push    r15
0x180023c0c  lea     rbp, [rsp-27h]
0x180023c11  sub     rsp, 0F0h
0x180023c18  mov     rax, cs:__security_cookie
0x180023c1f  xor     rax, rsp
0x180023c22  mov     [rbp+47h+var_30], rax
0x180023c26  mov     rsi, [rbp+47h+arg_20]
0x180023c2a  mov     ebx, edx
0x180023c2c  xor     edx, edx; Val
0x180023c2e  mov     rdi, r8
0x180023c31  mov     r14, rcx
0x180023c34  lea     rcx, [rbp+47h+var_B0]; void *
0x180023c38  lea     r8d, [rdx+78h]; Size
0x180023c3c  call    memset_0
0x180023c41  lea     r9, [rbp+47h+var_B0]
0x180023c45  mov     r8, rdi
0x180023c48  mov     edx, ebx
0x180023c4a  mov     rcx, r14; Src
0x180023c4d  call    GetStickyShareInfo
0x180023c52  test    al, al
0x180023c54  jz      loc_180023E0C
0x180023c5a  xor     edi, edi
0x180023c5c  xor     ebx, ebx
0x180023c5e  mov     rcx, cs:WPP_GLOBAL_Control
0x180023c65  lea     r15, WPP_GLOBAL_Control
0x180023c6c  cmp     rcx, r15
0x180023c6f  jz      short loc_180023C96
0x180023c71  test    dword ptr [rcx+1Ch], 100h
0x180023c78  jz      short loc_180023C96
0x180023c7a  cmp     byte ptr [rcx+19h], 2
0x180023c7e  jb      short loc_180023C96
0x180023c80  mov     rcx, [rcx+10h]
0x180023c84  lea     edx, [rdi+48h]
0x180023c87  mov     r9, r14
0x180023c8a  lea     r8, WPP_6c51fa01af1134468f88fcdefbc326dc_Traceguids
0x180023c91  call    WPP_SF_S
0x180023c96  cmp     [rbp+47h+var_A8], 1
0x180023c9a  jnz     short loc_180023CF8
0x180023c9c  xor     r9d, r9d; lpName
0x180023c9f  xor     r8d, r8d; bInitialState
0x180023ca2  xor     ecx, ecx; lpEventAttributes
0x180023ca4  lea     edx, [r9+1]; bManualReset
0x180023ca8  call    cs:__imp_CreateEventW
0x180023cae  mov     rbx, rax
0x180023cb1  test    rax, rax
0x180023cb4  jz      short loc_180023CED
0x180023cb6  lea     rax, [rbp+47h+ThreadId]
0x180023cba  mov     [rbp+47h+ThreadId], edi
0x180023cbd  mov     [rsp+110h+lpThreadId], rax; lpThreadId
0x180023cc2  lea     r8, PrintShareAnnounce; lpStartAddress
0x180023cc9  mov     r9, rbx; lpParameter
0x180023ccc  mov     [rsp+110h+dwCreationFlags], edi; dwCreationFlags
0x180023cd0  xor     edx, edx; dwStackSize
0x180023cd2  xor     ecx, ecx; lpThreadAttributes
0x180023cd4  call    cs:__imp_CreateThread
0x180023cda  mov     rdi, rax
0x180023cdd  test    rax, rax
0x180023ce0  jnz     short loc_180023CED
0x180023ce2  mov     rcx, rbx; hObject
0x180023ce5  call    cs:__imp_CloseHandle
0x180023ceb  xor     ebx, ebx
0x180023ced  cmp     [rbp+47h+var_A8], 1
0x180023cf1  jnz     short loc_180023CF8
0x180023cf3  test    rdi, rdi
0x180023cf6  jz      short loc_180023CFF
0x180023cf8  inc     dword ptr [rsi]
0x180023cfa  test    byte ptr [rsi], 3Fh
0x180023cfd  jnz     short loc_180023D09
0x180023cff  mov     ecx, 1
0x180023d04  call    AnnounceServiceStatus
0x180023d09  mov     [rsp+110h+var_C8], 0
0x180023d12  lea     r8, [rbp+47h+var_B0]
0x180023d16  mov     [rsp+110h+var_D0], 0
0x180023d1b  xor     r9d, r9d
0x180023d1e  mov     [rsp+110h+var_D8], 0
0x180023d23  mov     edx, 1F9h
0x180023d28  mov     [rsp+110h+var_E0], 1
0x180023d2d  xor     ecx, ecx
0x180023d2f  mov     byte ptr [rsp+110h+lpThreadId], 1
0x180023d34  mov     byte ptr [rsp+110h+dwCreationFlags], 0
0x180023d39  call    I_NetrShareAdd
0x180023d3e  mov     esi, eax
0x180023d40  test    rbx, rbx
0x180023d43  jz      short loc_180023D84
0x180023d45  mov     rcx, rbx; hEvent
0x180023d48  call    cs:__imp_SetEvent
0x180023d4e  or      r15d, 0FFFFFFFFh
0x180023d52  mov     rcx, rdi; hHandle
0x180023d55  mov     edx, r15d; dwMilliseconds
0x180023d58  call    cs:__imp_WaitForSingleObject
0x180023d5e  cmp     eax, r15d
0x180023d61  jnz     short loc_180023D6B
0x180023d63  call    cs:__imp_GetLastError
0x180023d69  mov     esi, eax
0x180023d6b  mov     rcx, rbx; hObject
0x180023d6e  call    cs:__imp_CloseHandle
0x180023d74  mov     rcx, rdi; hObject
0x180023d77  call    cs:__imp_CloseHandle
0x180023d7d  lea     r15, WPP_GLOBAL_Control
0x180023d84  test    esi, esi
0x180023d86  jz      short loc_180023DC1
0x180023d88  mov     rcx, cs:WPP_GLOBAL_Control
0x180023d8f  cmp     rcx, r15
0x180023d92  jz      short loc_180023DC1
0x180023d94  test    dword ptr [rcx+1Ch], 100h
0x180023d9b  jz      short loc_180023DC1
0x180023d9d  cmp     byte ptr [rcx+19h], 1
0x180023da1  jb      short loc_180023DC1
0x180023da3  mov     rax, [rbp+47h+var_88]
0x180023da7  mov     edx, 49h ; 'I'
0x180023dac  mov     rcx, [rcx+10h]
0x180023db0  mov     r9, r14
0x180023db3  mov     dword ptr [rsp+110h+lpThreadId], esi
0x180023db7  mov     qword ptr [rsp+110h+dwCreationFlags], rax
0x180023dbc  call    WPP_SF_SSl
0x180023dc1  mov     rcx, [rbp+47h+hMem]; hMem
0x180023dc5  test    rcx, rcx
0x180023dc8  jz      short loc_180023DD0
0x180023dca  call    cs:__imp_LocalFree
0x180023dd0  mov     rcx, [rbp+47h+var_88]; hMem
0x180023dd4  test    rcx, rcx
0x180023dd7  jz      short loc_180023DDF
0x180023dd9  call    cs:__imp_LocalFree
0x180023ddf  mov     rcx, [rbp+47h+var_78]; hMem
0x180023de3  test    rcx, rcx
0x180023de6  jz      short loc_180023DEE
0x180023de8  call    cs:__imp_LocalFree
0x180023dee  mov     rcx, [rbp+47h+var_B0]; hMem
0x180023df2  test    rcx, rcx
0x180023df5  jz      short loc_180023DFD
0x180023df7  call    cs:__imp_LocalFree
0x180023dfd  mov     rcx, [rbp+47h+var_68]; hMem
0x180023e01  test    rcx, rcx
0x180023e04  jz      short loc_180023E0C
0x180023e06  call    cs:__imp_LocalFree
0x180023e0c  xor     eax, eax
0x180023e0e  mov     rcx, [rbp+47h+var_30]
0x180023e12  xor     rcx, rsp; StackCookie
0x180023e15  call    __security_check_cookie
0x180023e1a  mov     rbx, [rsp+110h+arg_18]
0x180023e22  add     rsp, 0F0h
0x180023e29  pop     r15
0x180023e2b  pop     r14
0x180023e2d  pop     rdi
0x180023e2e  pop     rsi
0x180023e2f  pop     rbp
0x180023e30  retn
```
