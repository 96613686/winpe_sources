# HTTP_LOG_SITE_ENTRY::Update(IAppHostElement *,int)

- ea: `0x180007cf0`
- end: `0x180007ddb`
- name: `?Update@HTTP_LOG_SITE_ENTRY@@QEAAJPEAUIAppHostElement@@H@Z`
- size: `235`
- prototype: `__int64 __fastcall(HTTP_LOG_SITE_ENTRY *__hidden this, struct IAppHostElement *, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x180008858`

## callees

- `0x180001048`
- `0x180005bd4`
- `0x180006ca8`
- `0x1800073e8`
- `0x180007cf0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007d90`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007d90`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007d49`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007d49`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180007d69`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180007d73`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180007dae`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180007db8`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180007d69`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180007d73`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180007dae`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180007db8`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x180007d5f`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x180007da4`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x180007d5f`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x180007da4`

## pseudocode

```c
__int64 __fastcall HTTP_LOG_SITE_ENTRY::Update(HTTP_LOG_SITE_ENTRY *this, struct IAppHostElement *a2, int a3)
{
  int ConfigContext; // eax
  char *v5; // rbx
  int updated; // ebp
  RTL_SRWLOCK *v7; // rcx
  __int64 v8; // rsi
  void *Block; // [rsp+58h] [rbp+20h] BYREF

  Block = 0;
  ConfigContext = HTTP_LOG_SITE_ENTRY::CreateConfigContext(this, a2, a3, (struct IAppHostElement **)&Block);
  v5 = (char *)Block;
  updated = ConfigContext;
  if ( ConfigContext < 0
    || (HTTP_LOG_FILE_CONFIG::CalculateChange(
          (HTTP_LOG_FILE_CONFIG *)Block,
          *((struct HTTP_LOG_FILE_CONFIG **)this + 11)),
        (v7 = (RTL_SRWLOCK *)*((_QWORD *)this + 10)) != 0)
    && (updated = LOG_WRITER::UpdateConfig(v7, (const struct HTTP_LOG_FILE_CONFIG_CONTEXT *)v5), updated < 0) )
  {
    if ( v5 )
    {
      MULTISZ::~MULTISZ((MULTISZ *)(v5 + 160));
      STRU::~STRU((STRU *)(v5 + 104));
      STRU::~STRU((STRU *)(v5 + 48));
      operator delete(v5);
    }
  }
  else
  {
    EnterCriticalSection((LPCRITICAL_SECTION)this + 1);
    v8 = *((_QWORD *)this + 11);
    if ( v8 )
    {
      MULTISZ::~MULTISZ((MULTISZ *)(v8 + 160));
      STRU::~STRU((STRU *)(v8 + 104));
      STRU::~STRU((STRU *)(v8 + 48));
      operator delete((void *)v8);
    }
    *((_QWORD *)this + 11) = v5;
    *((_DWORD *)this + 28) = 2;
    LeaveCriticalSection((LPCRITICAL_SECTION)this + 1);
  }
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x180007cf0  mov     rax, rsp
0x180007cf3  mov     [rax+8], rbx
0x180007cf7  mov     [rax+10h], rbp
0x180007cfb  push    rsi
0x180007cfc  push    rdi
0x180007cfd  push    r14
0x180007cff  sub     rsp, 20h
0x180007d03  lea     r9, [rax+20h]; struct HTTP_LOG_FILE_CONFIG **
0x180007d07  mov     qword ptr [rax+20h], 0
0x180007d0f  mov     rdi, rcx
0x180007d12  call    ?CreateConfigContext@HTTP_LOG_SITE_ENTRY@@AEAAJPEAUIAppHostElement@@HPEAPEAVHTTP_LOG_FILE_CONFIG@@@Z; HTTP_LOG_SITE_ENTRY::CreateConfigContext(IAppHostElement *,int,HTTP_LOG_FILE_CONFIG * *)
0x180007d17  mov     rbx, [rsp+38h+Block]
0x180007d1c  mov     ebp, eax
0x180007d1e  test    eax, eax
0x180007d20  js      short loc_180007D98
0x180007d22  mov     rdx, [rdi+58h]; struct HTTP_LOG_FILE_CONFIG *
0x180007d26  mov     rcx, rbx; this
0x180007d29  call    ?CalculateChange@HTTP_LOG_FILE_CONFIG@@QEAAXPEAV1@@Z; HTTP_LOG_FILE_CONFIG::CalculateChange(HTTP_LOG_FILE_CONFIG *)
0x180007d2e  mov     rcx, [rdi+50h]; this
0x180007d32  test    rcx, rcx
0x180007d35  jz      short loc_180007D45
0x180007d37  mov     rdx, rbx; struct HTTP_LOG_FILE_CONFIG_CONTEXT *
0x180007d3a  call    ?UpdateConfig@LOG_WRITER@@QEAAJPEBVHTTP_LOG_FILE_CONFIG_CONTEXT@@@Z; LOG_WRITER::UpdateConfig(HTTP_LOG_FILE_CONFIG_CONTEXT const *)
0x180007d3f  mov     ebp, eax
0x180007d41  test    eax, eax
0x180007d43  js      short loc_180007D98
0x180007d45  lea     rcx, [rdi+28h]; lpCriticalSection
0x180007d49  call    cs:__imp_EnterCriticalSection
0x180007d4f  mov     rsi, [rdi+58h]
0x180007d53  test    rsi, rsi
0x180007d56  jz      short loc_180007D81
0x180007d58  lea     rcx, [rsi+0A0h]
0x180007d5f  call    cs:__imp_??1MULTISZ@@QEAA@XZ; MULTISZ::~MULTISZ(void)
0x180007d65  lea     rcx, [rsi+68h]
0x180007d69  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180007d6f  lea     rcx, [rsi+30h]
0x180007d73  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180007d79  mov     rcx, rsi; Block
0x180007d7c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180007d81  lea     rcx, [rdi+28h]; lpCriticalSection
0x180007d85  mov     [rdi+58h], rbx
0x180007d89  mov     dword ptr [rdi+70h], 2
0x180007d90  call    cs:__imp_LeaveCriticalSection
0x180007d96  jmp     short loc_180007DC6
0x180007d98  test    rbx, rbx
0x180007d9b  jz      short loc_180007DC6
0x180007d9d  lea     rcx, [rbx+0A0h]
0x180007da4  call    cs:__imp_??1MULTISZ@@QEAA@XZ; MULTISZ::~MULTISZ(void)
0x180007daa  lea     rcx, [rbx+68h]
0x180007dae  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180007db4  lea     rcx, [rbx+30h]
0x180007db8  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180007dbe  mov     rcx, rbx; Block
0x180007dc1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180007dc6  mov     rbx, [rsp+38h+arg_0]
0x180007dcb  mov     eax, ebp
0x180007dcd  mov     rbp, [rsp+38h+arg_8]
0x180007dd2  add     rsp, 20h
0x180007dd6  pop     r14
0x180007dd8  pop     rdi
0x180007dd9  pop     rsi
0x180007dda  retn
```
