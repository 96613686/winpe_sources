# NetworkChangeMonitor::~NetworkChangeMonitor(void)

- ea: `0x1800651b4`
- end: `0x18006527d`
- name: `??1NetworkChangeMonitor@@AEAA@XZ`
- size: `201`
- prototype: `void __fastcall(NetworkChangeMonitor *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180065170`

## callees

- `0x180013820`
- `0x1800651b4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180065260`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180065260`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800651e2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800651ff`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006521c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180065239`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800651e2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800651ff`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006521c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180065239`

## pseudocode

```c
void __fastcall NetworkChangeMonitor::~NetworkChangeMonitor(NetworkChangeMonitor *this)
{
  _QWORD *v2; // rcx
  void *v3; // rcx
  void *v4; // rcx
  void *v5; // rcx
  void *v6; // rcx

  *(_QWORD *)this = &NetworkChangeMonitor::`vftable';
  v2 = (_QWORD *)((char *)this + 144);
  if ( *v2 )
    WxFreeHeapEx(v2);
  v3 = (void *)*((_QWORD *)this + 14);
  if ( v3 )
  {
    CloseHandle(v3);
    *((_QWORD *)this + 14) = 0;
  }
  v4 = (void *)*((_QWORD *)this + 13);
  if ( v4 )
  {
    CloseHandle(v4);
    *((_QWORD *)this + 13) = 0;
  }
  v5 = (void *)*((_QWORD *)this + 12);
  if ( v5 )
  {
    CloseHandle(v5);
    *((_QWORD *)this + 12) = 0;
  }
  v6 = (void *)*((_QWORD *)this + 11);
  if ( v6 )
  {
    CloseHandle(v6);
    *((_QWORD *)this + 11) = 0;
  }
  if ( *((_QWORD *)this + 7) )
    WxFreeHeapEx((char *)this + 56);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  *(_QWORD *)this = &RefCountContext::`vftable';
}

```

## disassembly

```asm
0x1800651b4  push    rbx
0x1800651b6  sub     rsp, 20h
0x1800651ba  lea     rax, ??_7NetworkChangeMonitor@@6B@; const NetworkChangeMonitor::`vftable'
0x1800651c1  mov     rbx, rcx
0x1800651c4  mov     [rcx], rax
0x1800651c7  add     rcx, 90h
0x1800651ce  cmp     qword ptr [rcx], 0
0x1800651d2  jz      short loc_1800651D9
0x1800651d4  call    WxFreeHeapEx
0x1800651d9  mov     rcx, [rbx+70h]; hObject
0x1800651dd  test    rcx, rcx
0x1800651e0  jz      short loc_1800651F6
0x1800651e2  call    cs:__imp_CloseHandle
0x1800651e9  nop     dword ptr [rax+rax+00h]
0x1800651ee  mov     qword ptr [rbx+70h], 0
0x1800651f6  mov     rcx, [rbx+68h]; hObject
0x1800651fa  test    rcx, rcx
0x1800651fd  jz      short loc_180065213
0x1800651ff  call    cs:__imp_CloseHandle
0x180065206  nop     dword ptr [rax+rax+00h]
0x18006520b  mov     qword ptr [rbx+68h], 0
0x180065213  mov     rcx, [rbx+60h]; hObject
0x180065217  test    rcx, rcx
0x18006521a  jz      short loc_180065230
0x18006521c  call    cs:__imp_CloseHandle
0x180065223  nop     dword ptr [rax+rax+00h]
0x180065228  mov     qword ptr [rbx+60h], 0
0x180065230  mov     rcx, [rbx+58h]; hObject
0x180065234  test    rcx, rcx
0x180065237  jz      short loc_18006524D
0x180065239  call    cs:__imp_CloseHandle
0x180065240  nop     dword ptr [rax+rax+00h]
0x180065245  mov     qword ptr [rbx+58h], 0
0x18006524d  lea     rcx, [rbx+38h]
0x180065251  cmp     qword ptr [rcx], 0
0x180065255  jz      short loc_18006525C
0x180065257  call    WxFreeHeapEx
0x18006525c  lea     rcx, [rbx+10h]; lpCriticalSection
0x180065260  call    cs:__imp_DeleteCriticalSection
0x180065267  nop     dword ptr [rax+rax+00h]
0x18006526c  lea     rax, ??_7RefCountContext@@6B@; const RefCountContext::`vftable'
0x180065273  mov     [rbx], rax
0x180065276  add     rsp, 20h
0x18006527a  pop     rbx
0x18006527b  retn
```
