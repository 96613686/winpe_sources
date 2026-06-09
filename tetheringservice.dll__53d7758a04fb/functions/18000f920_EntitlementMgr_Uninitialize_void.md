# EntitlementMgr::Uninitialize(void)

- ea: `0x18000f920`
- end: `0x18000f99e`
- name: `?Uninitialize@EntitlementMgr@@QEAAXXZ`
- size: `126`
- prototype: `void __fastcall(EntitlementMgr *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18000eb14`
- `0x180014ab0`
- `0x180015e30`

## callees

- `0x18000f920`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f96f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f986`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f96f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f986`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x18000f93f`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x18000f93f`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueEx` at `0x18000f959`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueEx` at `0x18000f959`

## pseudocode

```c
void __fastcall EntitlementMgr::Uninitialize(EntitlementMgr *this)
{
  void *v1; // rdx
  void *v3; // rcx
  void *v4; // rcx

  v1 = (void *)*((_QWORD *)this + 1);
  if ( v1 && *((_BYTE *)this + 94) )
  {
    DeleteTimerQueueTimer(*(HANDLE *)this, v1, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
    *((_QWORD *)this + 1) = 0;
  }
  if ( *(_QWORD *)this )
  {
    DeleteTimerQueueEx(*(HANDLE *)this, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
    *(_QWORD *)this = 0;
  }
  v3 = (void *)*((_QWORD *)this + 2);
  if ( v3 )
  {
    CloseHandle(v3);
    *((_QWORD *)this + 2) = 0;
  }
  v4 = (void *)*((_QWORD *)this + 3);
  if ( v4 )
  {
    CloseHandle(v4);
    *((_QWORD *)this + 3) = 0;
  }
  *((_BYTE *)this + 94) = 0;
}

```

## disassembly

```asm
0x18000f920  push    rbx
0x18000f922  sub     rsp, 20h
0x18000f926  mov     rdx, [rcx+8]; Timer
0x18000f92a  mov     rbx, rcx
0x18000f92d  test    rdx, rdx
0x18000f930  jz      short loc_18000F94D
0x18000f932  cmp     byte ptr [rcx+5Eh], 0
0x18000f936  jz      short loc_18000F94D
0x18000f938  mov     rcx, [rcx]; TimerQueue
0x18000f93b  or      r8, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x18000f93f  call    cs:__imp_DeleteTimerQueueTimer
0x18000f945  mov     qword ptr [rbx+8], 0
0x18000f94d  mov     rcx, [rbx]; TimerQueue
0x18000f950  test    rcx, rcx
0x18000f953  jz      short loc_18000F966
0x18000f955  or      rdx, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x18000f959  call    cs:__imp_DeleteTimerQueueEx
0x18000f95f  mov     qword ptr [rbx], 0
0x18000f966  mov     rcx, [rbx+10h]; hObject
0x18000f96a  test    rcx, rcx
0x18000f96d  jz      short loc_18000F97D
0x18000f96f  call    cs:__imp_CloseHandle
0x18000f975  mov     qword ptr [rbx+10h], 0
0x18000f97d  mov     rcx, [rbx+18h]; hObject
0x18000f981  test    rcx, rcx
0x18000f984  jz      short loc_18000F994
0x18000f986  call    cs:__imp_CloseHandle
0x18000f98c  mov     qword ptr [rbx+18h], 0
0x18000f994  mov     byte ptr [rbx+5Eh], 0
0x18000f998  add     rsp, 20h
0x18000f99c  pop     rbx
0x18000f99d  retn
```
