# _anonymous_namespace_::security_process_state::_security_process_state

- ea: `0x180080cfc`
- end: `0x180080ddf`
- name: `_anonymous_namespace_::security_process_state::_security_process_state`
- size: `227`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180082b70`

## callees

- `0x180049674`
- `0x180080cfc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180080d0f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180080d0f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180080d79`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180080d79`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180080d1f`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180080d1f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180080d36`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180080d53`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180080d90`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180080daf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180080dcc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180080d36`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180080d53`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180080d90`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180080daf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180080dcc`

## pseudocode

```c
void __fastcall anonymous_namespace_::security_process_state::_security_process_state(__int64 a1)
{
  HANDLE v2; // rcx
  void *v3; // rcx
  HANDLE v4; // rcx
  struct _TP_WAIT *v5; // rcx
  void *v6; // rcx
  void *v7; // rcx
  HANDLE v8; // rcx

  v2 = *(HANDLE *)a1;
  if ( v2 && WaitForSingleObject(v2, 0) )
    TerminateProcess(*(HANDLE *)a1, 0xFFFFFFFF);
  v3 = *(void **)(a1 + 8);
  if ( v3 )
  {
    *(_QWORD *)(a1 + 8) = 0;
    CloseHandle(v3);
  }
  *(_QWORD *)(a1 + 8) = 0;
  v4 = *(HANDLE *)a1;
  if ( *(_QWORD *)a1 )
  {
    *(_QWORD *)a1 = 0;
    CloseHandle(v4);
  }
  *(_QWORD *)a1 = 0;
  *(_DWORD *)(a1 + 16) = 0;
  std::vector<char>::~vector<char>((char **)(a1 + 56));
  v5 = *(struct _TP_WAIT **)(a1 + 32);
  if ( v5 )
    CloseThreadpoolWait(v5);
  v6 = *(void **)(a1 + 24);
  if ( v6 )
  {
    *(_QWORD *)(a1 + 24) = 0;
    CloseHandle(v6);
  }
  *(_QWORD *)(a1 + 24) = 0;
  v7 = *(void **)(a1 + 8);
  if ( v7 )
  {
    *(_QWORD *)(a1 + 8) = 0;
    CloseHandle(v7);
  }
  *(_QWORD *)(a1 + 8) = 0;
  v8 = *(HANDLE *)a1;
  if ( *(_QWORD *)a1 )
  {
    *(_QWORD *)a1 = 0;
    CloseHandle(v8);
  }
  *(_QWORD *)a1 = 0;
}

```

## disassembly

```asm
0x180080cfc  push    rbx
0x180080cfe  sub     rsp, 20h
0x180080d02  mov     rbx, rcx
0x180080d05  mov     rcx, [rcx]; hHandle
0x180080d08  test    rcx, rcx
0x180080d0b  jz      short loc_180080D25
0x180080d0d  xor     edx, edx; dwMilliseconds
0x180080d0f  call    cs:__imp_WaitForSingleObject
0x180080d15  test    eax, eax
0x180080d17  jz      short loc_180080D25
0x180080d19  mov     rcx, [rbx]; hProcess
0x180080d1c  or      edx, 0FFFFFFFFh; uExitCode
0x180080d1f  call    cs:__imp_TerminateProcess
0x180080d25  mov     rcx, [rbx+8]; hObject
0x180080d29  test    rcx, rcx
0x180080d2c  jz      short loc_180080D3C
0x180080d2e  mov     qword ptr [rbx+8], 0
0x180080d36  call    cs:__imp_CloseHandle
0x180080d3c  mov     qword ptr [rbx+8], 0
0x180080d44  mov     rcx, [rbx]; hObject
0x180080d47  test    rcx, rcx
0x180080d4a  jz      short loc_180080D59
0x180080d4c  mov     qword ptr [rbx], 0
0x180080d53  call    cs:__imp_CloseHandle
0x180080d59  mov     qword ptr [rbx], 0
0x180080d60  lea     rcx, [rbx+38h]
0x180080d64  mov     dword ptr [rbx+10h], 0
0x180080d6b  call    ??1?$vector@DV?$allocator@D@std@@@std@@QEAA@XZ; std::vector<char>::~vector<char>(void)
0x180080d70  mov     rcx, [rbx+20h]; pwa
0x180080d74  test    rcx, rcx
0x180080d77  jz      short loc_180080D7F
0x180080d79  call    cs:__imp_CloseThreadpoolWait
0x180080d7f  mov     rcx, [rbx+18h]; hObject
0x180080d83  test    rcx, rcx
0x180080d86  jz      short loc_180080D96
0x180080d88  mov     qword ptr [rbx+18h], 0
0x180080d90  call    cs:__imp_CloseHandle
0x180080d96  mov     qword ptr [rbx+18h], 0
0x180080d9e  mov     rcx, [rbx+8]; hObject
0x180080da2  test    rcx, rcx
0x180080da5  jz      short loc_180080DB5
0x180080da7  mov     qword ptr [rbx+8], 0
0x180080daf  call    cs:__imp_CloseHandle
0x180080db5  mov     qword ptr [rbx+8], 0
0x180080dbd  mov     rcx, [rbx]; hObject
0x180080dc0  test    rcx, rcx
0x180080dc3  jz      short loc_180080DD2
0x180080dc5  mov     qword ptr [rbx], 0
0x180080dcc  call    cs:__imp_CloseHandle
0x180080dd2  mov     qword ptr [rbx], 0
0x180080dd9  add     rsp, 20h
0x180080ddd  pop     rbx
0x180080dde  retn
```
