# CDescriptionManager::FinalConstruct(void)

- ea: `0x18004c4f4`
- end: `0x18004c66b`
- name: `?FinalConstruct@CDescriptionManager@@QEAAJXZ`
- size: `375`
- prototype: `__int64 __fastcall(CDescriptionManager *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800355d4`

## callees

- `0x18004c4f4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004c52a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004c52a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004c543`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004c637`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004c543`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004c637`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x18004c5d0`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x18004c5d0`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x18004c60a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x18004c60a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x18004c5f0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x18004c5f0`

## pseudocode

```c
signed int __fastcall CDescriptionManager::FinalConstruct(CDescriptionManager *this)
{
  HANDLE EventW; // rax
  signed int result; // eax
  struct _TP_POOL *Threadpool; // rax
  PTP_CLEANUP_GROUP ThreadpoolCleanupGroup; // rax
  PTP_CLEANUP_GROUP v6; // rcx
  bool v7; // zf

  *((_QWORD *)this + 58) = 0;
  *((_QWORD *)this + 59) = 0;
  *((_QWORD *)this + 60) = -1;
  EventW = CreateEventW(0, 1, 0, 0);
  *((_QWORD *)this + 60) = EventW;
  if ( EventW == (HANDLE)-1LL )
  {
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
    return result;
  }
  *((_DWORD *)this + 98) = 3;
  *((_QWORD *)this + 50) = 0;
  *((_QWORD *)this + 51) = 0;
  *((_QWORD *)this + 52) = 0;
  *((_QWORD *)this + 53) = 0;
  *((_QWORD *)this + 54) = 0;
  *((_QWORD *)this + 55) = 0;
  *((_DWORD *)this + 112) = 0;
  *((_DWORD *)this + 113) = 1;
  *((_DWORD *)this + 114) = 72;
  Threadpool = CreateThreadpool(0);
  *((_QWORD *)this + 58) = Threadpool;
  if ( Threadpool )
  {
    SetThreadpoolThreadMaximum(Threadpool, 0x14u);
    *((_QWORD *)this + 50) = *((_QWORD *)this + 58);
    ThreadpoolCleanupGroup = CreateThreadpoolCleanupGroup();
    *((_QWORD *)this + 59) = ThreadpoolCleanupGroup;
    v6 = ThreadpoolCleanupGroup;
    if ( ThreadpoolCleanupGroup )
    {
      result = 0;
      *((_QWORD *)this + 51) = v6;
      *((_QWORD *)this + 52) = 0;
LABEL_10:
      *((_QWORD *)this + 77) = (char *)this + 608;
      *((_QWORD *)this + 76) = (char *)this + 608;
      return result;
    }
  }
  result = GetLastError();
  v7 = result == 0;
  if ( result > 0 )
  {
    result = (unsigned __int16)result | 0x80070000;
    v7 = result == 0;
  }
  if ( v7 )
    goto LABEL_10;
  return result;
}

```

## disassembly

```asm
0x18004c4f4  push    rbx
0x18004c4f6  sub     rsp, 20h
0x18004c4fa  xor     r9d, r9d; lpName
0x18004c4fd  mov     qword ptr [rcx+1D0h], 0
0x18004c508  mov     rbx, rcx
0x18004c50b  mov     qword ptr [rcx+1D8h], 0
0x18004c516  mov     qword ptr [rcx+1E0h], 0FFFFFFFFFFFFFFFFh
0x18004c521  xor     r8d, r8d; bInitialState
0x18004c524  xor     ecx, ecx; lpEventAttributes
0x18004c526  lea     edx, [r9+1]; bManualReset
0x18004c52a  call    cs:__imp_CreateEventW
0x18004c531  nop     dword ptr [rax+rax+00h]
0x18004c536  mov     [rbx+1E0h], rax
0x18004c53d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18004c541  jnz     short loc_18004C564
0x18004c543  call    cs:__imp_GetLastError
0x18004c54a  nop     dword ptr [rax+rax+00h]
0x18004c54f  test    eax, eax
0x18004c551  jle     loc_18004C664
0x18004c557  movzx   eax, ax
0x18004c55a  or      eax, 80070000h
0x18004c55f  jmp     loc_18004C664
0x18004c564  xor     ecx, ecx; reserved
0x18004c566  mov     dword ptr [rbx+188h], 3
0x18004c570  mov     qword ptr [rbx+190h], 0
0x18004c57b  mov     qword ptr [rbx+198h], 0
0x18004c586  mov     qword ptr [rbx+1A0h], 0
0x18004c591  mov     qword ptr [rbx+1A8h], 0
0x18004c59c  mov     qword ptr [rbx+1B0h], 0
0x18004c5a7  mov     qword ptr [rbx+1B8h], 0
0x18004c5b2  mov     dword ptr [rbx+1C0h], 0
0x18004c5bc  mov     dword ptr [rbx+1C4h], 1
0x18004c5c6  mov     dword ptr [rbx+1C8h], 48h ; 'H'
0x18004c5d0  call    cs:__imp_CreateThreadpool
0x18004c5d7  nop     dword ptr [rax+rax+00h]
0x18004c5dc  mov     [rbx+1D0h], rax
0x18004c5e3  test    rax, rax
0x18004c5e6  jz      short loc_18004C637
0x18004c5e8  mov     edx, 14h; cthrdMost
0x18004c5ed  mov     rcx, rax; ptpp
0x18004c5f0  call    cs:__imp_SetThreadpoolThreadMaximum
0x18004c5f7  nop     dword ptr [rax+rax+00h]
0x18004c5fc  mov     rax, [rbx+1D0h]
0x18004c603  mov     [rbx+190h], rax
0x18004c60a  call    cs:__imp_CreateThreadpoolCleanupGroup
0x18004c611  nop     dword ptr [rax+rax+00h]
0x18004c616  mov     [rbx+1D8h], rax
0x18004c61d  mov     rcx, rax
0x18004c620  test    rax, rax
0x18004c623  jz      short loc_18004C637
0x18004c625  xor     eax, eax
0x18004c627  mov     [rbx+198h], rcx
0x18004c62e  mov     [rbx+1A0h], rax
0x18004c635  jmp     short loc_18004C653
0x18004c637  call    cs:__imp_GetLastError
0x18004c63e  nop     dword ptr [rax+rax+00h]
0x18004c643  test    eax, eax
0x18004c645  jle     short loc_18004C651
0x18004c647  movzx   eax, ax
0x18004c64a  or      eax, 80070000h
0x18004c64f  test    eax, eax
0x18004c651  jnz     short loc_18004C664
0x18004c653  lea     rcx, [rbx+260h]
0x18004c65a  mov     [rbx+268h], rcx
0x18004c661  mov     [rcx], rcx
0x18004c664  add     rsp, 20h
0x18004c668  pop     rbx
0x18004c669  retn
```
