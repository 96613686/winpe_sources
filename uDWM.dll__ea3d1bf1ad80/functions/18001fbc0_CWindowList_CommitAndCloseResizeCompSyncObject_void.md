# CWindowList::CommitAndCloseResizeCompSyncObject(void)

- ea: `0x18001fbc0`
- end: `0x18001fc59`
- name: `?CommitAndCloseResizeCompSyncObject@CWindowList@@AEAAXXZ`
- size: `153`
- prototype: `void __fastcall(CWindowList *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001f680`
- `0x1800dae54`
- `0x1800df3d0`

## callees

- `0x18001fbc0`
- `0x18001fc60`
- `0x18007f8f8`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001fc10`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001fc10`
- `USER32!__imp_ConfirmResizeCommit` at `0x18001fbf8`
- `USER32!__imp_ConfirmResizeCommit` at `0x18001fbf8`
- `win32u!NtDCompositionCommitSynchronizationObject` at `0x18001fbeb`
- `win32u!NtDCompositionCommitSynchronizationObject` at `0x18001fbeb`

## pseudocode

```c
void __fastcall CWindowList::CommitAndCloseResizeCompSyncObject(CWindowList *this)
{
  void *v1; // rdx
  void *v3; // rcx
  int v4; // eax
  int v5; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v1 = (void *)*((_QWORD *)this + 75);
  if ( v1 )
  {
    if ( *((_BYTE *)this + 634) )
    {
      v4 = CCompositor::SynchronizedCommit(*((CCompositor **)CDesktopManager::s_pDesktopManagerInstance + 6), v1);
      if ( v4 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xAF8,
          (unsigned int)"clientcore\\windows\\dwm\\udwm\\windowlist.cpp",
          (const char *)(unsigned int)v4,
          v5);
      *((_BYTE *)this + 634) = 0;
    }
    NtDCompositionCommitSynchronizationObject(*((_QWORD *)this + 75));
    ConfirmResizeCommit(*((_QWORD *)this + 76));
    v3 = (void *)*((_QWORD *)this + 75);
    *((_QWORD *)this + 76) = 0;
    CloseHandle(v3);
    *((_QWORD *)this + 75) = 0;
  }
}

```

## disassembly

```asm
0x18001fbc0  push    rbx; int
0x18001fbc2  sub     rsp, 20h
0x18001fbc6  mov     rdx, [rcx+258h]; void *
0x18001fbcd  mov     rbx, rcx
0x18001fbd0  test    rdx, rdx
0x18001fbd3  jnz     short loc_18001FBDB
0x18001fbd5  add     rsp, 20h
0x18001fbd9  pop     rbx
0x18001fbda  retn
0x18001fbdb  cmp     byte ptr [rcx+27Ah], 0
0x18001fbe2  jnz     short loc_18001FC23
0x18001fbe4  mov     rcx, [rbx+258h]
0x18001fbeb  call    cs:__imp_NtDCompositionCommitSynchronizationObject
0x18001fbf1  mov     rcx, [rbx+260h]
0x18001fbf8  call    cs:__imp_ConfirmResizeCommit
0x18001fbfe  mov     rcx, [rbx+258h]; hObject
0x18001fc05  mov     qword ptr [rbx+260h], 0
0x18001fc10  call    cs:__imp_CloseHandle
0x18001fc16  mov     qword ptr [rbx+258h], 0
0x18001fc21  jmp     short loc_18001FBD5
0x18001fc23  mov     rcx, cs:?s_pDesktopManagerInstance@CDesktopManager@@0PEAV1@EA; CDesktopManager * CDesktopManager::s_pDesktopManagerInstance
0x18001fc2a  mov     rcx, [rcx+30h]; this
0x18001fc2e  call    ?SynchronizedCommit@CCompositor@@QEAAJPEAX@Z; CCompositor::SynchronizedCommit(void *)
0x18001fc33  test    eax, eax
0x18001fc35  jns     short loc_18001FC50
0x18001fc37  mov     rcx, [rsp+28h]; this
0x18001fc3c  lea     r8, aClientcoreWind_34; "clientcore\\windows\\dwm\\udwm\\windowl"...
0x18001fc43  mov     r9d, eax; char *
0x18001fc46  mov     edx, 0AF8h; void *
0x18001fc4b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001fc50  mov     byte ptr [rbx+27Ah], 0
0x18001fc57  jmp     short loc_18001FBE4
```
