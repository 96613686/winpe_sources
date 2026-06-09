# CNotificationEngine::~CNotificationEngine(void)

- ea: `0x18003413c`
- end: `0x18003425d`
- name: `??1CNotificationEngine@@EEAA@XZ`
- size: `289`
- prototype: `void __fastcall(CNotificationEngine *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180034270`

## callees

- `0x180001610`
- `0x180002818`
- `0x18003413c`
- `0x180034898`
- `0x180091eaa`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x1800341d7`
- `KERNEL32!WaitForSingleObject` at `0x1800341d7`
- `KERNEL32!SetEvent` at `0x1800341ca`
- `KERNEL32!SetEvent` at `0x1800341ca`
- `KERNEL32!CloseHandle` at `0x1800341e6`
- `KERNEL32!CloseHandle` at `0x180034213`
- `KERNEL32!CloseHandle` at `0x1800341e6`
- `KERNEL32!CloseHandle` at `0x180034213`
- `KERNEL32!DeleteCriticalSection` at `0x180034251`
- `KERNEL32!DeleteCriticalSection` at `0x180034251`
- `USER32!SendMessageW` at `0x180034180`
- `USER32!SendMessageW` at `0x180034180`
- `USER32!UnregisterClassW` at `0x1800341b9`
- `USER32!UnregisterClassW` at `0x1800341b9`
- `USER32!IsWindow` at `0x180034168`
- `USER32!IsWindow` at `0x180034168`
- `USER32!GetClassInfoW` at `0x1800341a1`
- `USER32!GetClassInfoW` at `0x1800341a1`

## pseudocode

```c
void __fastcall CNotificationEngine::~CNotificationEngine(CNotificationEngine *this)
{
  HWND v2; // rcx
  HINSTANCE v3; // rcx
  void *v4; // rcx
  void *v5; // rcx
  void *v6; // rcx
  unsigned int *v7; // rdx
  __int64 v8; // rax
  struct tagWNDCLASSW WndClass; // [rsp+20h] [rbp-58h] BYREF

  *(_QWORD *)this = &CNotificationEngine::`vftable';
  memset_0(&WndClass, 0, sizeof(WndClass));
  v2 = (HWND)*((_QWORD *)this + 1);
  if ( v2 && IsWindow(v2) )
    SendMessageW(*((HWND *)this + 1), 0x10u, 0, 0);
  v3 = hinstMapiXWAB;
  *((_QWORD *)this + 1) = 0;
  if ( GetClassInfoW(v3, aContactsNotifi, &WndClass) )
    UnregisterClassW(aContactsNotifi, hinstMapiXWAB);
  if ( *((_QWORD *)this + 4) != -1 )
  {
    SetEvent(*((HANDLE *)this + 3));
    WaitForSingleObject(*((HANDLE *)this + 4), 0xFFFFFFFF);
  }
  v4 = (void *)*((_QWORD *)this + 4);
  if ( v4 )
  {
    CloseHandle(v4);
    *((_QWORD *)this + 4) = 0;
  }
  v5 = (void *)*((_QWORD *)this + 2);
  if ( v5 )
  {
    operator delete(v5);
    *((_QWORD *)this + 2) = 0;
  }
  v6 = (void *)*((_QWORD *)this + 3);
  if ( v6 )
  {
    CloseHandle(v6);
    *((_QWORD *)this + 3) = 0;
  }
  OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>((char *)this + 88);
  while ( 1 )
  {
    v8 = *((_QWORD *)this + 5);
    if ( !v8 )
      break;
    if ( !*(_DWORD *)v8 )
      break;
    v7 = *(unsigned int **)(v8 + 8);
    if ( !v7 )
      break;
    CNotificationEngine::Unadvise(this, *v7);
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
}

```

## disassembly

```asm
0x18003413c  push    rbx
0x18003413e  sub     rsp, 70h
0x180034142  xor     edx, edx; Val
0x180034144  lea     rax, ??_7CNotificationEngine@@6B@; const CNotificationEngine::`vftable'
0x18003414b  mov     rbx, rcx
0x18003414e  mov     [rcx], rax
0x180034151  lea     rcx, [rsp+78h+WndClass]; void *
0x180034156  lea     r8d, [rdx+48h]; Size
0x18003415a  call    memset_0
0x18003415f  mov     rcx, [rbx+8]; hWnd
0x180034163  test    rcx, rcx
0x180034166  jz      short loc_180034186
0x180034168  call    cs:__imp_IsWindow
0x18003416e  test    eax, eax
0x180034170  jz      short loc_180034186
0x180034172  mov     rcx, [rbx+8]; hWnd
0x180034176  xor     r9d, r9d; lParam
0x180034179  xor     r8d, r8d; wParam
0x18003417c  lea     edx, [r9+10h]; Msg
0x180034180  call    cs:__imp_SendMessageW
0x180034186  mov     rcx, cs:hinstMapiXWAB; hInstance
0x18003418d  lea     r8, [rsp+78h+WndClass]; lpWndClass
0x180034192  lea     rdx, aContactsNotifi; "Contacts Notification Engine"
0x180034199  mov     qword ptr [rbx+8], 0
0x1800341a1  call    cs:__imp_GetClassInfoW
0x1800341a7  test    eax, eax
0x1800341a9  jz      short loc_1800341BF
0x1800341ab  mov     rdx, cs:hinstMapiXWAB; hInstance
0x1800341b2  lea     rcx, aContactsNotifi; "Contacts Notification Engine"
0x1800341b9  call    cs:__imp_UnregisterClassW
0x1800341bf  cmp     qword ptr [rbx+20h], 0FFFFFFFFFFFFFFFFh
0x1800341c4  jz      short loc_1800341DD
0x1800341c6  mov     rcx, [rbx+18h]; hEvent
0x1800341ca  call    cs:__imp_SetEvent
0x1800341d0  mov     rcx, [rbx+20h]; hHandle
0x1800341d4  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800341d7  call    cs:__imp_WaitForSingleObject
0x1800341dd  mov     rcx, [rbx+20h]; hObject
0x1800341e1  test    rcx, rcx
0x1800341e4  jz      short loc_1800341F4
0x1800341e6  call    cs:__imp_CloseHandle
0x1800341ec  mov     qword ptr [rbx+20h], 0
0x1800341f4  mov     rcx, [rbx+10h]; Block
0x1800341f8  test    rcx, rcx
0x1800341fb  jz      short loc_18003420A
0x1800341fd  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180034202  mov     qword ptr [rbx+10h], 0
0x18003420a  mov     rcx, [rbx+18h]; hObject
0x18003420e  test    rcx, rcx
0x180034211  jz      short loc_180034221
0x180034213  call    cs:__imp_CloseHandle
0x180034219  mov     qword ptr [rbx+18h], 0
0x180034221  lea     rcx, [rbx+58h]
0x180034225  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x18003422a  jmp     short loc_180034244
0x18003422c  cmp     dword ptr [rax], 0
0x18003422f  jz      short loc_18003424D
0x180034231  mov     rdx, [rax+8]
0x180034235  test    rdx, rdx
0x180034238  jz      short loc_18003424D
0x18003423a  mov     edx, [rdx]; unsigned int
0x18003423c  mov     rcx, rbx; this
0x18003423f  call    ?Unadvise@CNotificationEngine@@QEAAJK@Z; CNotificationEngine::Unadvise(ulong)
0x180034244  mov     rax, [rbx+28h]
0x180034248  test    rax, rax
0x18003424b  jnz     short loc_18003422C
0x18003424d  lea     rcx, [rbx+30h]; lpCriticalSection
0x180034251  call    cs:__imp_DeleteCriticalSection
0x180034257  add     rsp, 70h
0x18003425b  pop     rbx
0x18003425c  retn
```
