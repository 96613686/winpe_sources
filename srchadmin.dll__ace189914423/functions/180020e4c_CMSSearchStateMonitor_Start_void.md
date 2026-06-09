# CMSSearchStateMonitor::Start(void)

- ea: `0x180020e4c`
- end: `0x180020edc`
- name: `?Start@CMSSearchStateMonitor@@QEAAJXZ`
- size: `144`
- prototype: `__int64 __fastcall(CMSSearchStateMonitor *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18001f740`

## callees

- `0x18000d4dc`
- `0x180010680`
- `0x180020e4c`

## import_xrefs

- `SHLWAPI!__imp_SHCreateThread` at `0x180020e9c`
- `SHLWAPI!__imp_SHCreateThread` at `0x180020e9c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180020e6b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180020e6b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020eba`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020eba`

## pseudocode

```c
__int64 __fastcall CMSSearchStateMonitor::Start(CMSSearchStateMonitor *this)
{
  int Error; // ebx
  HANDLE EventW; // rax
  void *v4; // rcx

  if ( *(_QWORD *)this )
  {
    return 1;
  }
  else
  {
    Error = 0;
    EventW = CreateEventW(0, 0, 0, 0);
    *((_QWORD *)this + 8) = EventW;
    if ( !EventW && (Error = ResultFromLastError(), Error < 0)
      || !SHCreateThread(CMSSearchStateMonitor::s_ThreadProc, this, 8u, CMSSearchStateMonitor::s_ThreadCreateCallback)
      && (Error = ResultFromKnownLastError(), Error < 0) )
    {
      v4 = (void *)*((_QWORD *)this + 8);
      if ( v4 )
      {
        CloseHandle(v4);
        *((_QWORD *)this + 8) = 0;
      }
    }
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x180020e4c  mov     [rsp+arg_0], rbx
0x180020e51  push    rdi
0x180020e52  sub     rsp, 20h
0x180020e56  cmp     qword ptr [rcx], 0
0x180020e5a  mov     rdi, rcx
0x180020e5d  jnz     short loc_180020ECA
0x180020e5f  xor     r9d, r9d; lpName
0x180020e62  xor     r8d, r8d; bInitialState
0x180020e65  xor     edx, edx; bManualReset
0x180020e67  xor     ecx, ecx; lpEventAttributes
0x180020e69  xor     ebx, ebx
0x180020e6b  call    cs:__imp_CreateEventW
0x180020e71  mov     [rdi+40h], rax
0x180020e75  test    rax, rax
0x180020e78  jnz     short loc_180020E85
0x180020e7a  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x180020e7f  mov     ebx, eax
0x180020e81  test    eax, eax
0x180020e83  js      short loc_180020EB1
0x180020e85  lea     r9, ?s_ThreadCreateCallback@CMSSearchStateMonitor@@CAKPEAX@Z; pfnCallback
0x180020e8c  mov     r8d, 8; flags
0x180020e92  mov     rdx, rdi; pData
0x180020e95  lea     rcx, ?s_ThreadProc@CMSSearchStateMonitor@@CAKPEAX@Z; pfnThreadProc
0x180020e9c  call    cs:__imp_SHCreateThread
0x180020ea2  test    eax, eax
0x180020ea4  jnz     short loc_180020ECF
0x180020ea6  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180020eab  mov     ebx, eax
0x180020ead  test    eax, eax
0x180020eaf  jns     short loc_180020ECF
0x180020eb1  mov     rcx, [rdi+40h]; hObject
0x180020eb5  test    rcx, rcx
0x180020eb8  jz      short loc_180020ECF
0x180020eba  call    cs:__imp_CloseHandle
0x180020ec0  mov     qword ptr [rdi+40h], 0
0x180020ec8  jmp     short loc_180020ECF
0x180020eca  mov     ebx, 1
0x180020ecf  mov     eax, ebx
0x180020ed1  mov     rbx, [rsp+28h+arg_0]
0x180020ed6  add     rsp, 20h
0x180020eda  pop     rdi
0x180020edb  retn
```
