# XE_NamedPipeChannelSvr::Listen(void)

- ea: `0x1005fc8c0`
- end: `0x1005fc9e0`
- name: `?Listen@XE_NamedPipeChannelSvr@@UEAAPEAVXE_IProxySessionTransport@@XZ`
- size: `288`
- prototype: `struct XE_IProxySessionTransport *__fastcall(XE_NamedPipeChannelSvr *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1005fc8c0`
- `0x1005fca00`

## import_xrefs

- `KERNEL32!GetOverlappedResult` at `0x1005fc98d`
- `KERNEL32!GetOverlappedResult` at `0x1005fc98d`
- `KERNEL32!WaitForMultipleObjects` at `0x1005fc969`
- `KERNEL32!WaitForMultipleObjects` at `0x1005fc969`
- `KERNEL32!CreateNamedPipeW` at `0x1005fc907`
- `KERNEL32!CreateNamedPipeW` at `0x1005fc907`
- `KERNEL32!ConnectNamedPipe` at `0x1005fc92f`
- `KERNEL32!ConnectNamedPipe` at `0x1005fc92f`
- `KERNEL32!CancelIo` at `0x1005fc9bd`
- `KERNEL32!CancelIo` at `0x1005fc9bd`
- `KERNEL32!CloseHandle` at `0x1005fc9c6`
- `KERNEL32!CloseHandle` at `0x1005fc9c6`
- `KERNEL32!GetLastError` at `0x1005fc939`
- `KERNEL32!GetLastError` at `0x1005fc939`

## pseudocode

```c
struct XE_IProxySessionTransport *__fastcall XE_NamedPipeChannelSvr::Listen(XE_NamedPipeChannelSvr *this)
{
  HANDLE NamedPipeW; // rax
  void *v3; // rbx
  XE_NamedPipeChannelSvr *v4; // rcx
  void *v5; // rax
  DWORD v6; // eax
  HANDLE Handles[2]; // [rsp+40h] [rbp-38h] BYREF
  struct _OVERLAPPED Overlapped; // [rsp+50h] [rbp-28h] BYREF
  DWORD NumberOfBytesTransferred; // [rsp+80h] [rbp+8h] BYREF

  NamedPipeW = CreateNamedPipeW(
                 (LPCWSTR)this + 6,
                 0x40000003u,
                 6u,
                 *((_DWORD *)this + 133),
                 *((_DWORD *)this + 132),
                 *((_DWORD *)this + 132),
                 0,
                 0);
  v3 = NamedPipeW;
  if ( NamedPipeW != (HANDLE)-1LL )
  {
    memset(&Overlapped, 0, sizeof(Overlapped));
    if ( ConnectNamedPipe(NamedPipeW, &Overlapped) || GetLastError() == 535 )
      return XE_NamedPipeChannelSvr::CreateChannel(v4, v3, (const wchar_t *const)this + 6);
    v5 = (void *)*((_QWORD *)this + 68);
    Handles[0] = v3;
    Handles[1] = v5;
    v6 = WaitForMultipleObjects(2u, Handles, 0, 0xFFFFFFFF);
    if ( v6 )
    {
      if ( v6 == 1 )
      {
        CancelIo(v3);
        CloseHandle(v3);
      }
    }
    else
    {
      NumberOfBytesTransferred = 0;
      if ( GetOverlappedResult(v3, &Overlapped, &NumberOfBytesTransferred, 0) )
        return XE_NamedPipeChannelSvr::CreateChannel(v4, v3, (const wchar_t *const)this + 6);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1005fc8c0  mov     [rsp+arg_8], rbx
0x1005fc8c5  mov     [rsp+arg_10], rsi
0x1005fc8ca  push    rdi
0x1005fc8cb  sub     rsp, 70h
0x1005fc8cf  mov     eax, [rcx+210h]
0x1005fc8d5  mov     rsi, rcx
0x1005fc8d8  mov     r9d, [rcx+214h]; nMaxInstances
0x1005fc8df  mov     edx, 40000003h; dwOpenMode
0x1005fc8e4  mov     [rsp+78h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1005fc8ed  mov     r8d, 6; dwPipeMode
0x1005fc8f3  mov     [rsp+78h+nDefaultTimeOut], 0; nDefaultTimeOut
0x1005fc8fb  add     rcx, 0Ch; lpName
0x1005fc8ff  mov     [rsp+78h+nInBufferSize], eax; nInBufferSize
0x1005fc903  mov     [rsp+78h+nOutBufferSize], eax; nOutBufferSize
0x1005fc907  call    cs:__imp_CreateNamedPipeW
0x1005fc90d  mov     rbx, rax
0x1005fc910  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1005fc914  jz      loc_1005FC9CC
0x1005fc91a  xorps   xmm0, xmm0
0x1005fc91d  lea     rdx, [rsp+78h+Overlapped]; lpOverlapped
0x1005fc922  mov     rcx, rax; hNamedPipe
0x1005fc925  movups  xmmword ptr [rsp+78h+Overlapped.Internal], xmm0
0x1005fc92a  movups  xmmword ptr [rsp+78h+Overlapped.10h], xmm0
0x1005fc92f  call    cs:__imp_ConnectNamedPipe
0x1005fc935  test    eax, eax
0x1005fc937  jnz     short loc_1005FC997
0x1005fc939  call    cs:__imp_GetLastError
0x1005fc93f  cmp     eax, 217h
0x1005fc944  jz      short loc_1005FC997
0x1005fc946  mov     rax, [rsi+220h]
0x1005fc94d  lea     rdx, [rsp+78h+Handles]; lpHandles
0x1005fc952  xor     r8d, r8d; bWaitAll
0x1005fc955  mov     [rsp+78h+Handles], rbx
0x1005fc95a  mov     r9d, 0FFFFFFFFh; dwMilliseconds
0x1005fc960  mov     [rsp+78h+var_30], rax
0x1005fc965  lea     ecx, [r8+2]; nCount
0x1005fc969  call    cs:__imp_WaitForMultipleObjects
0x1005fc96f  test    eax, eax
0x1005fc971  jnz     short loc_1005FC9B5
0x1005fc973  xor     r9d, r9d; bWait
0x1005fc976  mov     [rsp+78h+NumberOfBytesTransferred], eax
0x1005fc97d  lea     r8, [rsp+78h+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x1005fc985  mov     rcx, rbx; hFile
0x1005fc988  lea     rdx, [rsp+78h+Overlapped]; lpOverlapped
0x1005fc98d  call    cs:__imp_GetOverlappedResult
0x1005fc993  test    eax, eax
0x1005fc995  jz      short loc_1005FC9CC
0x1005fc997  lea     r8, [rsi+0Ch]; wchar_t *
0x1005fc99b  mov     rdx, rbx; void *
0x1005fc99e  call    ?CreateChannel@XE_NamedPipeChannelSvr@@IEAAPEAVXE_IProxySessionTransport@@PEAXQEB_W@Z; XE_NamedPipeChannelSvr::CreateChannel(void *,wchar_t const * const)
0x1005fc9a3  lea     r11, [rsp+78h+var_8]
0x1005fc9a8  mov     rbx, [r11+18h]
0x1005fc9ac  mov     rsi, [r11+20h]
0x1005fc9b0  mov     rsp, r11
0x1005fc9b3  pop     rdi
0x1005fc9b4  retn
0x1005fc9b5  cmp     eax, 1
0x1005fc9b8  jnz     short loc_1005FC9CC
0x1005fc9ba  mov     rcx, rbx; hFile
0x1005fc9bd  call    cs:__imp_CancelIo
0x1005fc9c3  mov     rcx, rbx; hObject
0x1005fc9c6  call    cs:__imp_CloseHandle
0x1005fc9cc  lea     r11, [rsp+78h+var_8]
0x1005fc9d1  xor     eax, eax
0x1005fc9d3  mov     rbx, [r11+18h]
0x1005fc9d7  mov     rsi, [r11+20h]
0x1005fc9db  mov     rsp, r11
0x1005fc9de  pop     rdi
0x1005fc9df  retn
```
