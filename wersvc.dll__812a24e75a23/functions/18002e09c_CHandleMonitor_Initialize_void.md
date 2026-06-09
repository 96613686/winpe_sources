# CHandleMonitor::Initialize(void)

- ea: `0x18002e09c`
- end: `0x18002e24a`
- name: `?Initialize@CHandleMonitor@@QEAAJXZ`
- size: `430`
- prototype: `__int64 __fastcall(CHandleMonitor *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800181f8`

## callees

- `0x18002e09c`
- `0x18002e738`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18002e164`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18002e164`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e18e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e1f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e18e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e1f9`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002e0d5`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002e0fc`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002e0d5`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002e0fc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002e186`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002e1e7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002e21d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002e232`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002e186`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002e1e7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002e21d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002e232`

## pseudocode

```c
__int64 __fastcall CHandleMonitor::Initialize(CHandleMonitor *this)
{
  bool v1; // zf
  signed int v3; // ebx
  char *EventW; // rbx
  char *v5; // rcx
  __int64 *v6; // rsi
  HANDLE Thread; // rax
  void *v8; // rcx
  signed int v9; // eax
  __int64 v10; // rbx
  __int64 v11; // rdi
  __int64 v12; // rbx
  __int64 v13; // rbx
  void *v14; // rcx
  signed int LastError; // eax
  HANDLE hObject; // [rsp+40h] [rbp+8h] BYREF
  HANDLE v18; // [rsp+48h] [rbp+10h] BYREF

  v1 = *(_DWORD *)this == 0;
  v18 = 0;
  hObject = 0;
  if ( !v1 )
    goto LABEL_2;
  EventW = (char *)CreateEventW(0, 0, 0, 0);
  v18 = EventW;
  if ( EventW == (char *)-1LL
    || EventW + 1 == (char *)1
    || (v5 = (char *)CreateEventW(0, 1, 0, 0), hObject = v5, v5 == (char *)-1LL || v5 + 1 == (char *)1) )
  {
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError > 0 )
      v3 = (unsigned __int16)LastError | 0x80070000;
  }
  else
  {
    *((_QWORD *)this + 14) = v5;
    v6 = (__int64 *)((char *)this + 56);
    *((_QWORD *)this + 13) = EventW;
    if ( (unsigned __int8)utl::vector<tlx::unique_any<tlx::file_handle_traits>,utl::allocator<tlx::unique_any<tlx::file_handle_traits>>>::push_back(
                            (char *)this + 56,
                            &v18)
      && (unsigned __int8)utl::vector<tlx::unique_any<tlx::file_handle_traits>,utl::allocator<tlx::unique_any<tlx::file_handle_traits>>>::push_back(
                            (char *)this + 56,
                            &hObject) )
    {
      Thread = CreateThread(0, 0, CHandleMonitor::StaticThreadProc, this, 0, 0);
      if ( (unsigned __int64)Thread + 1 > 1 )
      {
        v8 = (void *)*((_QWORD *)this + 15);
        *((_QWORD *)this + 15) = Thread;
        if ( (unsigned __int64)v8 + 1 > 1 )
          CloseHandle(v8);
LABEL_13:
        *(_DWORD *)this = 1;
LABEL_2:
        v3 = 0;
        goto LABEL_21;
      }
      v9 = GetLastError();
      v3 = v9;
      if ( v9 > 0 )
        v3 = (unsigned __int16)v9 | 0x80070000;
      if ( v3 >= 0 )
        goto LABEL_13;
    }
    else
    {
      v10 = *((_QWORD *)this + 8);
      *((_QWORD *)this + 13) = 0;
      *((_QWORD *)this + 14) = 0;
      v11 = *v6;
      v12 = v10 - *v6;
      v6[1] = *v6;
      v13 = v12 >> 3;
      while ( v13 )
      {
        --v13;
        v14 = *(void **)(v11 + 8 * v13);
        if ( (unsigned __int64)v14 + 1 > 1 )
          CloseHandle(v14);
      }
      v3 = -2147024882;
    }
  }
LABEL_21:
  if ( (unsigned __int64)hObject + 1 > 1 )
    CloseHandle(hObject);
  if ( (unsigned __int64)v18 + 1 > 1 )
    CloseHandle(v18);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18002e09c  mov     rax, rsp
0x18002e09f  mov     [rax+18h], rbx
0x18002e0a3  mov     [rax+20h], rsi
0x18002e0a7  push    rdi
0x18002e0a8  sub     rsp, 30h
0x18002e0ac  cmp     dword ptr [rcx], 0
0x18002e0af  mov     rdi, rcx
0x18002e0b2  mov     qword ptr [rax+10h], 0
0x18002e0ba  mov     qword ptr [rax+8], 0
0x18002e0c2  jz      short loc_18002E0CB
0x18002e0c4  xor     ebx, ebx
0x18002e0c6  jmp     loc_18002E20E
0x18002e0cb  xor     r9d, r9d; lpName
0x18002e0ce  xor     r8d, r8d; bInitialState
0x18002e0d1  xor     edx, edx; bManualReset
0x18002e0d3  xor     ecx, ecx; lpEventAttributes
0x18002e0d5  call    cs:__imp_CreateEventW
0x18002e0db  mov     rbx, rax
0x18002e0de  mov     [rsp+38h+arg_8], rax
0x18002e0e3  inc     rax
0x18002e0e6  cmp     rax, 1
0x18002e0ea  jbe     loc_18002E1F9
0x18002e0f0  xor     r9d, r9d; lpName
0x18002e0f3  xor     r8d, r8d; bInitialState
0x18002e0f6  xor     ecx, ecx; lpEventAttributes
0x18002e0f8  lea     edx, [r9+1]; bManualReset
0x18002e0fc  call    cs:__imp_CreateEventW
0x18002e102  mov     rcx, rax
0x18002e105  mov     [rsp+38h+hObject], rax
0x18002e10a  inc     rax
0x18002e10d  cmp     rax, 1
0x18002e111  jbe     loc_18002E1F9
0x18002e117  mov     [rdi+70h], rcx
0x18002e11b  lea     rsi, [rdi+38h]
0x18002e11f  mov     rcx, rsi
0x18002e122  mov     [rdi+68h], rbx
0x18002e126  lea     rdx, [rsp+38h+arg_8]
0x18002e12b  call    ?push_back@?$vector@V?$unique_any@Ufile_handle_traits@tlx@@@tlx@@V?$allocator@V?$unique_any@Ufile_handle_traits@tlx@@@tlx@@@utl@@@utl@@QEAA_N$$QEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@@Z; utl::vector<tlx::unique_any<tlx::file_handle_traits>,utl::allocator<tlx::unique_any<tlx::file_handle_traits>>>::push_back(tlx::unique_any<tlx::file_handle_traits> &&)
0x18002e130  test    al, al
0x18002e132  jz      short loc_18002E1B2
0x18002e134  lea     rdx, [rsp+38h+hObject]
0x18002e139  mov     rcx, rsi
0x18002e13c  call    ?push_back@?$vector@V?$unique_any@Ufile_handle_traits@tlx@@@tlx@@V?$allocator@V?$unique_any@Ufile_handle_traits@tlx@@@tlx@@@utl@@@utl@@QEAA_N$$QEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@@Z; utl::vector<tlx::unique_any<tlx::file_handle_traits>,utl::allocator<tlx::unique_any<tlx::file_handle_traits>>>::push_back(tlx::unique_any<tlx::file_handle_traits> &&)
0x18002e141  test    al, al
0x18002e143  jz      short loc_18002E1B2
0x18002e145  mov     [rsp+38h+lpThreadId], 0; lpThreadId
0x18002e14e  lea     r8, ?StaticThreadProc@CHandleMonitor@@CAKPEAX@Z; lpStartAddress
0x18002e155  mov     r9, rdi; lpParameter
0x18002e158  mov     [rsp+38h+dwCreationFlags], 0; dwCreationFlags
0x18002e160  xor     edx, edx; dwStackSize
0x18002e162  xor     ecx, ecx; lpThreadAttributes
0x18002e164  call    cs:__imp_CreateThread
0x18002e16a  lea     rcx, [rax+1]
0x18002e16e  cmp     rcx, 1
0x18002e172  jbe     short loc_18002E18E
0x18002e174  mov     rcx, [rdi+78h]; hObject
0x18002e178  mov     [rdi+78h], rax
0x18002e17c  lea     rax, [rcx+1]
0x18002e180  cmp     rax, 1
0x18002e184  jbe     short loc_18002E1A7
0x18002e186  call    cs:__imp_CloseHandle
0x18002e18c  jmp     short loc_18002E1A7
0x18002e18e  call    cs:__imp_GetLastError
0x18002e194  mov     ebx, eax
0x18002e196  test    eax, eax
0x18002e198  jle     short loc_18002E1A3
0x18002e19a  movzx   ebx, ax
0x18002e19d  or      ebx, 80070000h
0x18002e1a3  test    ebx, ebx
0x18002e1a5  js      short loc_18002E20E
0x18002e1a7  mov     dword ptr [rdi], 1
0x18002e1ad  jmp     loc_18002E0C4
0x18002e1b2  mov     rbx, [rsi+8]
0x18002e1b6  mov     qword ptr [rdi+68h], 0
0x18002e1be  mov     qword ptr [rdi+70h], 0
0x18002e1c6  mov     rdi, [rsi]
0x18002e1c9  sub     rbx, rdi
0x18002e1cc  mov     [rsi+8], rdi
0x18002e1d0  sar     rbx, 3
0x18002e1d4  jmp     short loc_18002E1ED
0x18002e1d6  dec     rbx
0x18002e1d9  mov     rcx, [rdi+rbx*8]; hObject
0x18002e1dd  lea     rax, [rcx+1]
0x18002e1e1  cmp     rax, 1
0x18002e1e5  jbe     short loc_18002E1ED
0x18002e1e7  call    cs:__imp_CloseHandle
0x18002e1ed  test    rbx, rbx
0x18002e1f0  jnz     short loc_18002E1D6
0x18002e1f2  mov     ebx, 8007000Eh
0x18002e1f7  jmp     short loc_18002E20E
0x18002e1f9  call    cs:__imp_GetLastError
0x18002e1ff  mov     ebx, eax
0x18002e201  test    eax, eax
0x18002e203  jle     short loc_18002E20E
0x18002e205  movzx   ebx, ax
0x18002e208  or      ebx, 80070000h
0x18002e20e  mov     rcx, [rsp+38h+hObject]; hObject
0x18002e213  lea     rax, [rcx+1]
0x18002e217  cmp     rax, 1
0x18002e21b  jbe     short loc_18002E223
0x18002e21d  call    cs:__imp_CloseHandle
0x18002e223  mov     rcx, [rsp+38h+arg_8]; hObject
0x18002e228  lea     rdx, [rcx+1]
0x18002e22c  cmp     rdx, 1
0x18002e230  jbe     short loc_18002E238
0x18002e232  call    cs:__imp_CloseHandle
0x18002e238  mov     rsi, [rsp+38h+arg_18]
0x18002e23d  mov     eax, ebx
0x18002e23f  mov     rbx, [rsp+38h+arg_10]
0x18002e244  add     rsp, 30h
0x18002e248  pop     rdi
0x18002e249  retn
```
