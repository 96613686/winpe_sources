# Windows::UI::Core::CDispatcher::Cleanup(void)

- ea: `0x180037680`
- end: `0x180037752`
- name: `?Cleanup@CDispatcher@Core@UI@Windows@@UEAAJXZ`
- size: `210`
- prototype: `__int64 __fastcall(Windows::UI::Core::CDispatcher *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800375a8`

## callees

- `0x1800038e0`
- `0x180006c30`
- `0x180037680`
- `0x180050360`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1800376a2`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1800376a2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800376de`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003770f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003773f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800376de`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003770f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003773f`

## string_xrefs

- `0x180037727`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\dispatcher.cpp`

## pseudocode

```c
__int64 __fastcall Windows::UI::Core::CDispatcher::Cleanup(struct _TP_WAIT **this)
{
  struct _TP_WAIT *v2; // rcx
  struct _TP_WAIT *v3; // rcx
  struct _TP_WAIT *v4; // rcx
  struct _TP_WAIT *v5; // rcx
  int v7; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( Windows::UI::Core::CDispatcher::CheckAccess((Windows::UI::Core::CDispatcher *)this) )
    wil::details::in1diag3::FailFast_Hr(
      retaddr,
      (void *)0x89,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\dispatcher.cpp",
      (const char *)0x8000FFFFLL,
      v7);
  v2 = this[30];
  if ( v2 )
  {
    CloseThreadpoolWait(v2);
    this[30] = 0;
  }
  v3 = this[29];
  if ( v3 )
  {
    CloseHandle(v3);
    this[29] = 0;
  }
  v4 = this[27];
  *((_DWORD *)this + 30) = 0;
  if ( v4 )
  {
    CloseHandle(v4);
    this[27] = 0;
  }
  v5 = this[97];
  if ( v5 )
  {
    CloseHandle(v5);
    this[97] = 0;
  }
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(this + 98);
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(this + 99);
  return 0;
}

```

## disassembly

```asm
0x180037680  push    rbx; int
0x180037682  sub     rsp, 20h
0x180037686  mov     rbx, rcx
0x180037689  call    ?CheckAccess@CDispatcher@Core@UI@Windows@@QEAAHXZ; Windows::UI::Core::CDispatcher::CheckAccess(void)
0x18003768e  test    eax, eax
0x180037690  jnz     loc_180037722
0x180037696  mov     rcx, [rbx+0F0h]; pwa
0x18003769d  test    rcx, rcx
0x1800376a0  jz      short loc_1800376B3
0x1800376a2  call    cs:__imp_CloseThreadpoolWait
0x1800376a8  mov     qword ptr [rbx+0F0h], 0
0x1800376b3  mov     rcx, [rbx+0E8h]; hObject
0x1800376ba  test    rcx, rcx
0x1800376bd  jnz     short loc_18003770F
0x1800376bf  mov     rcx, [rbx+0D8h]; hObject
0x1800376c6  mov     dword ptr [rbx+78h], 0
0x1800376cd  test    rcx, rcx
0x1800376d0  jnz     short loc_18003773F
0x1800376d2  mov     rcx, [rbx+308h]; hObject
0x1800376d9  test    rcx, rcx
0x1800376dc  jz      short loc_1800376EF
0x1800376de  call    cs:__imp_CloseHandle
0x1800376e4  mov     qword ptr [rbx+308h], 0
0x1800376ef  lea     rcx, [rbx+310h]
0x1800376f6  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x1800376fb  lea     rcx, [rbx+318h]
0x180037702  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180037707  xor     eax, eax
0x180037709  add     rsp, 20h
0x18003770d  pop     rbx
0x18003770e  retn
0x18003770f  call    cs:__imp_CloseHandle
0x180037715  mov     qword ptr [rbx+0E8h], 0
0x180037720  jmp     short loc_1800376BF
0x180037722  mov     rcx, [rsp+28h]; this
0x180037727  lea     r8, aOnecoreuapWind_14; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x18003772e  mov     r9d, 8000FFFFh; char *
0x180037734  mov     edx, 89h; void *
0x180037739  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x18003773f  call    cs:__imp_CloseHandle
0x180037745  mov     qword ptr [rbx+0D8h], 0
0x180037750  jmp     short loc_1800376D2
```
