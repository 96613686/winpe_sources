# CHungApp::_TerminateProcessCallback(void)

- ea: `0x18002b424`
- end: `0x18002b4e6`
- name: `?_TerminateProcessCallback@CHungApp@@AEAAXXZ`
- size: `194`
- prototype: `void __fastcall(CHungApp *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18002710c`
- `0x180029800`

## callees

- `0x180013df4`
- `0x18002b424`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x18002b4b0`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x18002b4b0`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18002b49e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18002b49e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18002b448`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18002b45f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18002b4da`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18002b448`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18002b45f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18002b4da`

## pseudocode

```c
void __fastcall CHungApp::_TerminateProcessCallback(CHungApp *this)
{
  struct _TP_WAIT *v2; // rcx
  struct _TP_WAIT *v3; // rcx
  struct _TP_WAIT *v4; // rcx
  void *v5; // rdx

  if ( *((_DWORD *)this + 12) )
  {
    v2 = (struct _TP_WAIT *)*((_QWORD *)this + 299);
    if ( v2 )
      SetThreadpoolWait(v2, 0, 0);
    v3 = (struct _TP_WAIT *)*((_QWORD *)this + 300);
    if ( v3 )
      SetThreadpoolWait(v3, 0, 0);
    if ( !*((_DWORD *)this + 612) )
    {
      if ( *((_QWORD *)this + 148) == -1 || *((_QWORD *)this + 148) == 0 )
        MicrosoftTelemetryAssertTriggeredNoArgs(v3);
      *((_DWORD *)this + 612) = 1;
      *((_DWORD *)this + 82) = 1;
      GetSystemTimeAsFileTime((LPFILETIME)this + 305);
      TerminateProcess(*((HANDLE *)this + 148), 0xCFFFFFFF);
      v4 = (struct _TP_WAIT *)*((_QWORD *)this + 301);
      if ( v4 )
      {
        v5 = (void *)*((_QWORD *)this + 148);
        if ( (unsigned __int64)v5 + 1 > 1 )
          SetThreadpoolWait(v4, v5, &CHungApp::ms_shortTerminationTimeoutFT);
      }
    }
  }
}

```

## disassembly

```asm
0x18002b424  push    rbx
0x18002b426  sub     rsp, 20h
0x18002b42a  cmp     dword ptr [rcx+30h], 0
0x18002b42e  mov     rbx, rcx
0x18002b431  jz      loc_18002B4E0
0x18002b437  mov     rcx, [rcx+958h]; pwa
0x18002b43e  test    rcx, rcx
0x18002b441  jz      short loc_18002B44E
0x18002b443  xor     r8d, r8d; pftTimeout
0x18002b446  xor     edx, edx; h
0x18002b448  call    cs:__imp_SetThreadpoolWait
0x18002b44e  mov     rcx, [rbx+960h]; pwa
0x18002b455  test    rcx, rcx
0x18002b458  jz      short loc_18002B465
0x18002b45a  xor     r8d, r8d; pftTimeout
0x18002b45d  xor     edx, edx; h
0x18002b45f  call    cs:__imp_SetThreadpoolWait
0x18002b465  cmp     dword ptr [rbx+990h], 0
0x18002b46c  jnz     short loc_18002B4E0
0x18002b46e  mov     rax, [rbx+4A0h]
0x18002b475  inc     rax
0x18002b478  cmp     rax, 1
0x18002b47c  ja      short loc_18002B483
0x18002b47e  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18002b483  lea     rcx, [rbx+988h]; lpSystemTimeAsFileTime
0x18002b48a  mov     dword ptr [rbx+990h], 1
0x18002b494  mov     dword ptr [rbx+148h], 1
0x18002b49e  call    cs:__imp_GetSystemTimeAsFileTime
0x18002b4a4  mov     rcx, [rbx+4A0h]; hProcess
0x18002b4ab  mov     edx, 0CFFFFFFFh; uExitCode
0x18002b4b0  call    cs:__imp_TerminateProcess
0x18002b4b6  mov     rcx, [rbx+968h]; pwa
0x18002b4bd  test    rcx, rcx
0x18002b4c0  jz      short loc_18002B4E0
0x18002b4c2  mov     rdx, [rbx+4A0h]; h
0x18002b4c9  lea     rax, [rdx+1]
0x18002b4cd  cmp     rax, 1
0x18002b4d1  jbe     short loc_18002B4E0
0x18002b4d3  lea     r8, ?ms_shortTerminationTimeoutFT@CHungApp@@0U_FILETIME@@A; pftTimeout
0x18002b4da  call    cs:__imp_SetThreadpoolWait
0x18002b4e0  add     rsp, 20h
0x18002b4e4  pop     rbx
0x18002b4e5  retn
```
