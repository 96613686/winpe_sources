# CDirectoryListener::_Init(void)

- ea: `0x1800909cc`
- end: `0x180090af1`
- name: `?_Init@CDirectoryListener@@AEAAJXZ`
- size: `293`
- prototype: `__int64 __fastcall(CDirectoryListener *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1800902dc`

## callees

- `0x18007b01c`
- `0x1800909cc`
- `0x180090af8`

## import_xrefs

- `KERNEL32!CreateEventW` at `0x180090a4d`
- `KERNEL32!CreateEventW` at `0x180090a6b`
- `KERNEL32!CreateEventW` at `0x180090a4d`
- `KERNEL32!CreateEventW` at `0x180090a6b`
- `KERNEL32!RegisterWaitForSingleObject` at `0x180090aa5`
- `KERNEL32!RegisterWaitForSingleObject` at `0x180090aa5`
- `KERNEL32!GetLastError` at `0x180090a25`
- `KERNEL32!GetLastError` at `0x180090a25`
- `KERNEL32!CreateFileW` at `0x180090a12`
- `KERNEL32!CreateFileW` at `0x180090a12`

## pseudocode

```c
__int64 __fastcall CDirectoryListener::_Init(CDirectoryListener *this)
{
  const WCHAR *v2; // rcx
  HANDLE FileW; // rax
  signed int LastError; // eax
  int Instance; // ecx
  HANDLE EventW; // rax
  HANDLE v7; // rax

  if ( *((_DWORD *)this + 146) )
    v2 = (const WCHAR *)*((_QWORD *)this + 74);
  else
    v2 = &Str;
  FileW = CreateFileW(v2, 1u, 7u, 0, 3u, 0x42000000u, 0);
  *((_QWORD *)this + 79) = FileW;
  if ( FileW != (HANDLE)-1LL
    && (EventW = CreateEventW(0, 0, 0, 0), (*((_QWORD *)this + 80) = EventW) != 0)
    && (v7 = CreateEventW(0, 1, 0, 0), (*((_QWORD *)this + 82) = v7) != 0) )
  {
    if ( RegisterWaitForSingleObject(
           (PHANDLE)this + 81,
           *((HANDLE *)this + 80),
           CDirectoryListener::s_Callback,
           this,
           0xFFFFFFFF,
           0) )
    {
      Instance = CThreadCallback::CreateInstance(
                   (struct IThreadNotify *)(((unsigned __int64)this + 40) & -(__int64)(this != 0)),
                   (struct CThreadCallback **)this + 78);
      if ( Instance >= 0 )
      {
        Instance = CDirectoryListener::_RegisterForChanges(this);
        if ( Instance >= 0 )
          return 0;
      }
    }
    else
    {
      return (unsigned int)-2147024882;
    }
  }
  else
  {
    LastError = GetLastError();
    Instance = LastError;
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x1800909cc  push    rbx
0x1800909ce  sub     rsp, 40h
0x1800909d2  cmp     dword ptr [rcx+248h], 0
0x1800909d9  mov     rbx, rcx
0x1800909dc  jnz     short loc_1800909E7
0x1800909de  lea     rcx, Str
0x1800909e5  jmp     short loc_1800909EE
0x1800909e7  mov     rcx, [rcx+250h]; lpFileName
0x1800909ee  xor     r9d, r9d; lpSecurityAttributes
0x1800909f1  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x1800909fa  mov     [rsp+48h+dwFlagsAndAttributes], 42000000h; dwFlagsAndAttributes
0x180090a02  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x180090a0a  lea     edx, [r9+1]; dwDesiredAccess
0x180090a0e  lea     r8d, [r9+7]; dwShareMode
0x180090a12  call    cs:__imp_CreateFileW
0x180090a18  mov     [rbx+278h], rax
0x180090a1f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180090a23  jnz     short loc_180090A43
0x180090a25  call    cs:__imp_GetLastError
0x180090a2b  mov     ecx, eax
0x180090a2d  test    eax, eax
0x180090a2f  jle     loc_180090AE9
0x180090a35  movzx   ecx, ax
0x180090a38  or      ecx, 80070000h
0x180090a3e  jmp     loc_180090AE9
0x180090a43  xor     r9d, r9d; lpName
0x180090a46  xor     r8d, r8d; bInitialState
0x180090a49  xor     edx, edx; bManualReset
0x180090a4b  xor     ecx, ecx; lpEventAttributes
0x180090a4d  call    cs:__imp_CreateEventW
0x180090a53  mov     [rbx+280h], rax
0x180090a5a  test    rax, rax
0x180090a5d  jz      short loc_180090A25
0x180090a5f  xor     r9d, r9d; lpName
0x180090a62  xor     r8d, r8d; bInitialState
0x180090a65  xor     ecx, ecx; lpEventAttributes
0x180090a67  lea     edx, [r9+1]; bManualReset
0x180090a6b  call    cs:__imp_CreateEventW
0x180090a71  mov     [rbx+290h], rax
0x180090a78  test    rax, rax
0x180090a7b  jz      short loc_180090A25
0x180090a7d  mov     rdx, [rbx+280h]; hObject
0x180090a84  lea     rcx, [rbx+288h]; phNewWaitObject
0x180090a8b  mov     [rsp+48h+dwFlagsAndAttributes], 0; dwFlags
0x180090a93  lea     r8, ?s_Callback@CDirectoryListener@@CAXPEAXE@Z; Callback
0x180090a9a  mov     r9, rbx; Context
0x180090a9d  mov     [rsp+48h+dwCreationDisposition], 0FFFFFFFFh; dwMilliseconds
0x180090aa5  call    cs:__imp_RegisterWaitForSingleObject
0x180090aab  test    eax, eax
0x180090aad  jnz     short loc_180090AB6
0x180090aaf  mov     ecx, 8007000Eh
0x180090ab4  jmp     short loc_180090AE9
0x180090ab6  lea     r8, [rbx+28h]
0x180090aba  mov     rax, rbx
0x180090abd  neg     rax
0x180090ac0  lea     rdx, [rbx+270h]; struct CThreadCallback **
0x180090ac7  sbb     rcx, rcx
0x180090aca  and     rcx, r8; struct IThreadNotify *
0x180090acd  call    ?CreateInstance@CThreadCallback@@SAJPEAUIThreadNotify@@PEAPEAV1@@Z; CThreadCallback::CreateInstance(IThreadNotify *,CThreadCallback * *)
0x180090ad2  mov     ecx, eax
0x180090ad4  test    eax, eax
0x180090ad6  js      short loc_180090AE9
0x180090ad8  mov     rcx, rbx; this
0x180090adb  call    ?_RegisterForChanges@CDirectoryListener@@AEAAJXZ; CDirectoryListener::_RegisterForChanges(void)
0x180090ae0  mov     ecx, eax
0x180090ae2  xor     eax, eax
0x180090ae4  test    ecx, ecx
0x180090ae6  cmovns  ecx, eax
0x180090ae9  mov     eax, ecx
0x180090aeb  add     rsp, 40h
0x180090aef  pop     rbx
0x180090af0  retn
```
