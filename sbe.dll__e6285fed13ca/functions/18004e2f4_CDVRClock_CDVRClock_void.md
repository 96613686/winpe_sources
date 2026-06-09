# CDVRClock::~CDVRClock(void)

- ea: `0x18004e2f4`
- end: `0x18004e3d3`
- name: `??1CDVRClock@@QEAA@XZ`
- size: `223`
- prototype: `void __fastcall(CDVRClock *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180008f10`

## callees

- `0x1800017e0`
- `0x18004e2f4`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x18004e349`
- `KERNEL32!WaitForSingleObject` at `0x18004e349`
- `KERNEL32!SetEvent` at `0x18004e332`
- `KERNEL32!SetEvent` at `0x18004e332`
- `KERNEL32!CloseHandle` at `0x18004e353`
- `KERNEL32!CloseHandle` at `0x18004e372`
- `KERNEL32!CloseHandle` at `0x18004e353`
- `KERNEL32!CloseHandle` at `0x18004e372`
- `KERNEL32!DeleteCriticalSection` at `0x18004e3b5`
- `KERNEL32!DeleteCriticalSection` at `0x18004e3b5`
- `KERNEL32!DeleteCriticalSection` at `0x18004e3cc`
- `KERNEL32!LeaveCriticalSection` at `0x18004e33c`
- `KERNEL32!LeaveCriticalSection` at `0x18004e33c`
- `KERNEL32!EnterCriticalSection` at `0x18004e321`
- `KERNEL32!EnterCriticalSection` at `0x18004e321`
- `WINMM!timeEndPeriod` at `0x18004e363`
- `WINMM!timeEndPeriod` at `0x18004e363`

## pseudocode

```c
void __fastcall CDVRClock::~CDVRClock(CDVRClock *this)
{
  bool v1; // zf
  void *v3; // rcx
  UINT v4; // ecx
  void *v5; // rcx
  _QWORD *v6; // rcx
  _QWORD *v7; // rcx

  v1 = *((_QWORD *)this + 7) == 0;
  *(_QWORD *)this = &CDVRClock::`vftable'{for `IReferenceClock'};
  *((_QWORD *)this + 1) = &CDVRClock::`vftable'{for `CTIGetTime<__int64>'};
  if ( !v1 )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)this + 2);
    v3 = (void *)*((_QWORD *)this + 8);
    *((_DWORD *)this + 18) = 1;
    SetEvent(v3);
    LeaveCriticalSection((LPCRITICAL_SECTION)this + 2);
    WaitForSingleObject(*((HANDLE *)this + 7), 0xFFFFFFFF);
    CloseHandle(*((HANDLE *)this + 7));
    v4 = *((_DWORD *)this + 40);
    if ( v4 )
      timeEndPeriod(v4);
  }
  v5 = (void *)*((_QWORD *)this + 8);
  if ( v5 )
    CloseHandle(v5);
  while ( 1 )
  {
    v6 = (_QWORD *)*((_QWORD *)this + 6);
    if ( !v6 )
      break;
    *((_QWORD *)this + 6) = *v6;
    operator delete(v6, 0x20u);
  }
  while ( 1 )
  {
    v7 = (_QWORD *)*((_QWORD *)this + 5);
    if ( !v7 )
      break;
    *((_QWORD *)this + 5) = *v7;
    operator delete(v7, 0x20u);
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 2);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 288));
}

```

## disassembly

```asm
0x18004e2f4  mov     [rsp+arg_0], rbx
0x18004e2f9  push    rdi
0x18004e2fa  sub     rsp, 20h
0x18004e2fe  cmp     qword ptr [rcx+38h], 0
0x18004e303  lea     rax, ??_7CDVRClock@@6BIReferenceClock@@@; const CDVRClock::`vftable'{for `IReferenceClock'}
0x18004e30a  mov     [rcx], rax
0x18004e30d  mov     rdi, rcx
0x18004e310  lea     rax, ??_7CDVRClock@@6B?$CTIGetTime@_J@@@; const CDVRClock::`vftable'{for `CTIGetTime<__int64>'}
0x18004e317  mov     [rcx+8], rax
0x18004e31b  jz      short loc_18004E369
0x18004e31d  add     rcx, 50h ; 'P'; lpCriticalSection
0x18004e321  call    cs:__imp_EnterCriticalSection
0x18004e327  mov     rcx, [rdi+40h]; hEvent
0x18004e32b  mov     dword ptr [rdi+48h], 1
0x18004e332  call    cs:__imp_SetEvent
0x18004e338  lea     rcx, [rdi+50h]; lpCriticalSection
0x18004e33c  call    cs:__imp_LeaveCriticalSection
0x18004e342  mov     rcx, [rdi+38h]; hHandle
0x18004e346  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18004e349  call    cs:__imp_WaitForSingleObject
0x18004e34f  mov     rcx, [rdi+38h]; hObject
0x18004e353  call    cs:__imp_CloseHandle
0x18004e359  mov     ecx, [rdi+0A0h]; uPeriod
0x18004e35f  test    ecx, ecx
0x18004e361  jz      short loc_18004E369
0x18004e363  call    cs:__imp_timeEndPeriod
0x18004e369  mov     rcx, [rdi+40h]; hObject
0x18004e36d  test    rcx, rcx
0x18004e370  jz      short loc_18004E378
0x18004e372  call    cs:__imp_CloseHandle
0x18004e378  mov     ebx, 20h ; ' '
0x18004e37d  jmp     short loc_18004E38E
0x18004e37f  mov     rax, [rcx]
0x18004e382  mov     rdx, rbx; unsigned __int64
0x18004e385  mov     [rdi+30h], rax
0x18004e389  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18004e38e  mov     rcx, [rdi+30h]; void *
0x18004e392  test    rcx, rcx
0x18004e395  jnz     short loc_18004E37F
0x18004e397  jmp     short loc_18004E3A8
0x18004e399  mov     rax, [rcx]
0x18004e39c  mov     rdx, rbx; unsigned __int64
0x18004e39f  mov     [rdi+28h], rax
0x18004e3a3  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18004e3a8  mov     rcx, [rdi+28h]; void *
0x18004e3ac  test    rcx, rcx
0x18004e3af  jnz     short loc_18004E399
0x18004e3b1  lea     rcx, [rdi+50h]; lpCriticalSection
0x18004e3b5  call    cs:__imp_DeleteCriticalSection
0x18004e3bb  lea     rcx, [rdi+120h]
0x18004e3c2  mov     rbx, [rsp+28h+arg_0]
0x18004e3c7  add     rsp, 20h
0x18004e3cb  pop     rdi
0x18004e3cc  jmp     cs:__imp_DeleteCriticalSection
```
