# CDescriptionManager::FinalConstruct(void)

- ea: `0x180049608`
- end: `0x18004975a`
- name: `?FinalConstruct@CDescriptionManager@@QEAAJXZ`
- size: `338`
- prototype: `signed int __fastcall(CDescriptionManager *this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180033694`

## callees

- `0x180049608`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004963e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004963e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049651`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004972d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049651`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004972d`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x1800496d8`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x1800496d8`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x180049706`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x180049706`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x1800496f2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x1800496f2`

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
0x180049608  push    rbx
0x18004960a  sub     rsp, 20h
0x18004960e  xor     r9d, r9d; lpName
0x180049611  mov     qword ptr [rcx+1D0h], 0
0x18004961c  mov     rbx, rcx
0x18004961f  mov     qword ptr [rcx+1D8h], 0
0x18004962a  mov     qword ptr [rcx+1E0h], 0FFFFFFFFFFFFFFFFh
0x180049635  xor     r8d, r8d; bInitialState
0x180049638  xor     ecx, ecx; lpEventAttributes
0x18004963a  lea     edx, [r9+1]; bManualReset
0x18004963e  call    cs:__imp_CreateEventW
0x180049644  mov     [rbx+1E0h], rax
0x18004964b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18004964f  jnz     short loc_18004966C
0x180049651  call    cs:__imp_GetLastError
0x180049657  test    eax, eax
0x180049659  jle     loc_180049754
0x18004965f  movzx   eax, ax
0x180049662  or      eax, 80070000h
0x180049667  jmp     loc_180049754
0x18004966c  xor     ecx, ecx; reserved
0x18004966e  mov     dword ptr [rbx+188h], 3
0x180049678  mov     qword ptr [rbx+190h], 0
0x180049683  mov     qword ptr [rbx+198h], 0
0x18004968e  mov     qword ptr [rbx+1A0h], 0
0x180049699  mov     qword ptr [rbx+1A8h], 0
0x1800496a4  mov     qword ptr [rbx+1B0h], 0
0x1800496af  mov     qword ptr [rbx+1B8h], 0
0x1800496ba  mov     dword ptr [rbx+1C0h], 0
0x1800496c4  mov     dword ptr [rbx+1C4h], 1
0x1800496ce  mov     dword ptr [rbx+1C8h], 48h ; 'H'
0x1800496d8  call    cs:__imp_CreateThreadpool
0x1800496de  mov     [rbx+1D0h], rax
0x1800496e5  test    rax, rax
0x1800496e8  jz      short loc_18004972D
0x1800496ea  mov     edx, 14h; cthrdMost
0x1800496ef  mov     rcx, rax; ptpp
0x1800496f2  call    cs:__imp_SetThreadpoolThreadMaximum
0x1800496f8  mov     rax, [rbx+1D0h]
0x1800496ff  mov     [rbx+190h], rax
0x180049706  call    cs:__imp_CreateThreadpoolCleanupGroup
0x18004970c  mov     [rbx+1D8h], rax
0x180049713  mov     rcx, rax
0x180049716  test    rax, rax
0x180049719  jz      short loc_18004972D
0x18004971b  xor     eax, eax
0x18004971d  mov     [rbx+198h], rcx
0x180049724  mov     [rbx+1A0h], rax
0x18004972b  jmp     short loc_180049743
0x18004972d  call    cs:__imp_GetLastError
0x180049733  test    eax, eax
0x180049735  jle     short loc_180049741
0x180049737  movzx   eax, ax
0x18004973a  or      eax, 80070000h
0x18004973f  test    eax, eax
0x180049741  jnz     short loc_180049754
0x180049743  lea     rcx, [rbx+260h]
0x18004974a  mov     [rbx+268h], rcx
0x180049751  mov     [rcx], rcx
0x180049754  add     rsp, 20h
0x180049758  pop     rbx
0x180049759  retn
```
