# wil::ActivityThreadWatcher::ActivityThreadWatcher(wil::details::IFailureCallback *,wil::details::StoredCallContextInfo const &)

- ea: `0x18001b190`
- end: `0x18001b287`
- name: `??0ActivityThreadWatcher@wil@@QEAA@PEAUIFailureCallback@details@1@AEBVStoredCallContextInfo@31@@Z`
- size: `247`
- prototype: `wil::ActivityThreadWatcher *__fastcall(wil::ActivityThreadWatcher *this, struct wil::details::IFailureCallback *, const struct wil::details::StoredCallContextInfo *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800221ec`

## callees

- `0x180003d0a`
- `0x180003da4`
- `0x180004575`
- `0x1800084d0`
- `0x18001b190`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001b21c`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001b21c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001b1e8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001b1e8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001b1da`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001b1da`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001b270`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001b270`

## pseudocode

```c
wil::ActivityThreadWatcher *__fastcall wil::ActivityThreadWatcher::ActivityThreadWatcher(
        wil::ActivityThreadWatcher *this,
        struct wil::details::IFailureCallback *a2,
        const struct wil::details::StoredCallContextInfo *a3)
{
  struct wil::details::IFailureCallback *v3; // rbp
  _WORD *v5; // rbx
  __int64 v6; // rax
  SIZE_T v7; // rsi
  HANDLE ProcessHeap; // rax
  void *v9; // rax
  _QWORD *v10; // rbx
  _QWORD *Local; // rax

  v3 = a2;
  *((_BYTE *)this + 24) = 0;
  *(_DWORD *)this = *(_DWORD *)a3;
  *((_QWORD *)this + 1) = *((_QWORD *)a3 + 1);
  v5 = (_WORD *)*((_QWORD *)a3 + 2);
  if ( *((_BYTE *)a3 + 24) )
  {
    v6 = -1;
    do
      ++v6;
    while ( v5[v6] );
    if ( v6 )
    {
      v7 = 2 * v6 + 2;
      ProcessHeap = GetProcessHeap();
      v9 = HeapAlloc(ProcessHeap, 0, v7);
      *((_QWORD *)this + 2) = v9;
      if ( v9 )
      {
        *((_BYTE *)this + 24) = 1;
        if ( v7 )
        {
          if ( v5 )
          {
            memcpy_0(v9, v5, v7);
          }
          else
          {
            memset_0(v9, 0, v7);
            *(_DWORD *)_o__errno() = 22;
            invalid_parameter_noinfo();
          }
        }
      }
    }
  }
  else
  {
    *((_QWORD *)this + 2) = v5;
  }
  v10 = (_QWORD *)((char *)this + 32);
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = v3;
  *((_QWORD *)this + 6) = 0;
  *((_DWORD *)this + 14) = 0;
  *((_QWORD *)this + 8) = this;
  *((_BYTE *)this + 72) = 0;
  if ( wil::details::g_pThreadFailureCallbacks )
  {
    LOBYTE(a2) = 1;
    Local = (_QWORD *)wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(
                        this,
                        a2);
    *v10 = Local;
    if ( Local )
    {
      *((_QWORD *)this + 6) = *Local;
      *Local = v10;
      *((_DWORD *)this + 14) = GetCurrentThreadId();
    }
  }
  return this;
}

```

## disassembly

```asm
0x18001b190  push    rbx
0x18001b192  push    rbp
0x18001b193  push    rsi
0x18001b194  push    rdi
0x18001b195  push    r14
0x18001b197  sub     rsp, 20h
0x18001b19b  mov     rbp, rdx
0x18001b19e  mov     rdi, rcx
0x18001b1a1  xor     r14d, r14d
0x18001b1a4  mov     [rcx+18h], r14b
0x18001b1a8  mov     eax, [r8]
0x18001b1ab  mov     [rcx], eax
0x18001b1ad  mov     rax, [r8+8]
0x18001b1b1  mov     [rcx+8], rax
0x18001b1b5  mov     rbx, [r8+10h]
0x18001b1b9  cmp     [r8+18h], r14b
0x18001b1bd  jz      short loc_18001B22F
0x18001b1bf  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001b1c3  inc     rax
0x18001b1c6  cmp     [rbx+rax*2], r14w
0x18001b1cb  jnz     short loc_18001B1C3
0x18001b1cd  test    rax, rax
0x18001b1d0  jz      short loc_18001B233
0x18001b1d2  lea     rsi, ds:2[rax*2]
0x18001b1da  call    cs:__imp_GetProcessHeap
0x18001b1e0  mov     rcx, rax; hHeap
0x18001b1e3  mov     r8, rsi; dwBytes
0x18001b1e6  xor     edx, edx; dwFlags
0x18001b1e8  call    cs:__imp_HeapAlloc
0x18001b1ee  mov     [rdi+10h], rax
0x18001b1f2  test    rax, rax
0x18001b1f5  jz      short loc_18001B233
0x18001b1f7  mov     byte ptr [rdi+18h], 1
0x18001b1fb  test    rsi, rsi
0x18001b1fe  jz      short loc_18001B233
0x18001b200  mov     r8, rsi; Size
0x18001b203  mov     rcx, rax; void *
0x18001b206  test    rbx, rbx
0x18001b209  jz      short loc_18001B215
0x18001b20b  mov     rdx, rbx; Src
0x18001b20e  call    memcpy_0
0x18001b213  jmp     short loc_18001B233
0x18001b215  xor     edx, edx; Val
0x18001b217  call    memset_0
0x18001b21c  call    cs:__imp__o__errno
0x18001b222  mov     dword ptr [rax], 16h
0x18001b228  call    _invalid_parameter_noinfo
0x18001b22d  jmp     short loc_18001B233
0x18001b22f  mov     [rcx+10h], rbx
0x18001b233  lea     rbx, [rdi+20h]
0x18001b237  mov     [rbx], r14
0x18001b23a  mov     [rbx+8], rbp
0x18001b23e  mov     [rbx+10h], r14
0x18001b242  mov     [rbx+18h], r14d
0x18001b246  mov     [rbx+20h], rdi
0x18001b24a  mov     [rbx+28h], r14b
0x18001b24e  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, r14; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18001b255  jz      short loc_18001B279
0x18001b257  mov     dl, 1
0x18001b259  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x18001b25e  mov     [rbx], rax
0x18001b261  test    rax, rax
0x18001b264  jz      short loc_18001B279
0x18001b266  mov     rcx, [rax]
0x18001b269  mov     [rbx+10h], rcx
0x18001b26d  mov     [rax], rbx
0x18001b270  call    cs:__imp_GetCurrentThreadId
0x18001b276  mov     [rbx+18h], eax
0x18001b279  mov     rax, rdi
0x18001b27c  add     rsp, 20h
0x18001b280  pop     r14
0x18001b282  pop     rdi
0x18001b283  pop     rsi
0x18001b284  pop     rbp
0x18001b285  pop     rbx
0x18001b286  retn
```
