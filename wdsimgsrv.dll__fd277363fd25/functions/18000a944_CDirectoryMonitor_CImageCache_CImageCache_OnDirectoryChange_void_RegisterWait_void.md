# CDirectoryMonitor<CImageCache,&CImageCache::OnDirectoryChange(void)>::RegisterWait(void)

- ea: `0x18000a944`
- end: `0x18000aa23`
- name: `?RegisterWait@?$CDirectoryMonitor@VCImageCache@@$1?OnDirectoryChange@1@QEAAKXZ@@AEAAKXZ`
- size: `223`
- prototype: `__int64 __fastcall(PVOID Context)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x180008de8`
- `0x18000abac`

## callees

- `0x1800080a8`
- `0x180008104`
- `0x180009430`
- `0x18000a944`
- `0x18000ab7c`
- `0x18000aeac`

## import_xrefs

- `KERNEL32!UnregisterWait` at `0x18000a98c`
- `KERNEL32!UnregisterWait` at `0x18000a98c`
- `KERNEL32!GetLastError` at `0x18000a9d5`
- `KERNEL32!GetLastError` at `0x18000a9d5`
- `KERNEL32!RegisterWaitForSingleObject` at `0x18000a9c5`
- `KERNEL32!RegisterWaitForSingleObject` at `0x18000a9c5`

## pseudocode

```c
__int64 __fastcall CDirectoryMonitor<CImageCache,&public: unsigned long CImageCache::OnDirectoryChange(void)>::RegisterWait(
        char *Context)
{
  unsigned int v2; // ebx
  void *v3; // rsi
  void **v4; // rdi
  DWORD LastError; // eax
  __int64 v6; // rdx
  int v7; // eax
  _BYTE v9[24]; // [rsp+30h] [rbp-18h] BYREF

  v2 = 0;
  v3 = 0;
  CAutoTypeLock<CCriticalSection>::CAutoTypeLock<CCriticalSection>(v9, Context);
  v4 = (void **)(Context + 80);
  if ( *((_QWORD *)Context + 10) )
  {
    v3 = *v4;
    *v4 = 0;
  }
  CAutoTypeLock<CCriticalSection>::Unlock(v9);
  if ( v3 )
    UnregisterWait(v3);
  CAutoTypeLock<CCriticalSection>::Lock(v9);
  if ( !*v4
    && !RegisterWaitForSingleObject(
          (PHANDLE)Context + 10,
          *((HANDLE *)Context + 9),
          CDirectoryMonitor<CImageCache,&public: unsigned long CImageCache::OnDirectoryChange(void)>::_WaitCallback,
          Context,
          0xFFFFFFFF,
          0x18u) )
  {
    LastError = GetLastError();
    v7 = ElValidateWin32_0(LastError, v6, "onecore\\internal\\base\\inc\\private\\eco\\wds\\DirMon.h", 313);
    if ( !v7 )
      v7 = 31;
    v2 = v7;
  }
  CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(v9);
  return v2;
}

```

## disassembly

```asm
0x18000a944  mov     rax, rsp
0x18000a947  mov     [rax+8], rbx
0x18000a94b  mov     [rax+10h], rbp
0x18000a94f  mov     [rax+18h], rsi
0x18000a953  push    rdi
0x18000a954  sub     rsp, 40h
0x18000a958  mov     rbp, rcx
0x18000a95b  mov     rdx, rcx
0x18000a95e  xor     ebx, ebx
0x18000a960  lea     rcx, [rax-18h]
0x18000a964  mov     esi, ebx
0x18000a966  call    ??0?$CAutoTypeLock@VCCriticalSection@@@@QEAA@PEAVCCriticalSection@@H@Z; CAutoTypeLock<CCriticalSection>::CAutoTypeLock<CCriticalSection>(CCriticalSection *,int)
0x18000a96b  lea     rdi, [rbp+50h]
0x18000a96f  cmp     [rdi], rbx
0x18000a972  jz      short loc_18000A97A
0x18000a974  mov     rsi, [rdi]
0x18000a977  mov     [rdi], rbx
0x18000a97a  lea     rcx, [rsp+48h+var_18]
0x18000a97f  call    ?Unlock@?$CAutoTypeLock@VCCriticalSection@@@@QEAAXXZ; CAutoTypeLock<CCriticalSection>::Unlock(void)
0x18000a984  test    rsi, rsi
0x18000a987  jz      short loc_18000A998
0x18000a989  mov     rcx, rsi; WaitHandle
0x18000a98c  call    cs:__imp_UnregisterWait
0x18000a993  nop     dword ptr [rax+rax+00h]
0x18000a998  lea     rcx, [rsp+48h+var_18]
0x18000a99d  call    ?Lock@?$CAutoTypeLock@VCCriticalSection@@@@QEAAXXZ; CAutoTypeLock<CCriticalSection>::Lock(void)
0x18000a9a2  cmp     [rdi], rbx
0x18000a9a5  jnz     short loc_18000AA01
0x18000a9a7  mov     rdx, [rbp+48h]; hObject
0x18000a9ab  lea     r8, ?_WaitCallback@?$CDirectoryMonitor@VCImageCache@@$1?OnDirectoryChange@1@QEAAKXZ@@CAXPEAXE@Z; Callback
0x18000a9b2  mov     [rsp+48h+dwFlags], 18h; dwFlags
0x18000a9ba  mov     r9, rbp; Context
0x18000a9bd  or      [rsp+48h+var_28], 0FFFFFFFFh
0x18000a9c2  mov     rcx, rdi; phNewWaitObject
0x18000a9c5  call    cs:__imp_RegisterWaitForSingleObject
0x18000a9cc  nop     dword ptr [rax+rax+00h]
0x18000a9d1  test    eax, eax
0x18000a9d3  jnz     short loc_18000AA01
0x18000a9d5  call    cs:__imp_GetLastError
0x18000a9dc  nop     dword ptr [rax+rax+00h]
0x18000a9e1  mov     r9d, 139h
0x18000a9e7  lea     r8, aOnecoreInterna_1; "onecore\\internal\\base\\inc\\private\\"...
0x18000a9ee  mov     ecx, eax
0x18000a9f0  call    ElValidateWin32_0
0x18000a9f5  test    eax, eax
0x18000a9f7  mov     ecx, 1Fh
0x18000a9fc  cmovz   eax, ecx
0x18000a9ff  mov     ebx, eax
0x18000aa01  lea     rcx, [rsp+48h+var_18]
0x18000aa06  call    ??1?$CAutoTypeLock@VCCriticalSection@@@@QEAA@XZ; CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(void)
0x18000aa0b  mov     rbp, [rsp+48h+arg_8]
0x18000aa10  mov     eax, ebx
0x18000aa12  mov     rbx, [rsp+48h+arg_0]
0x18000aa17  mov     rsi, [rsp+48h+arg_10]
0x18000aa1c  add     rsp, 40h
0x18000aa20  pop     rdi
0x18000aa21  retn
```
