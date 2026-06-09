# CFciPropertiesShellExt::StartBackgroundThread(ulong (*)(void *),HWND__ *)

- ea: `0x18000f294`
- end: `0x18000f358`
- name: `?StartBackgroundThread@CFciPropertiesShellExt@@AEAAJP6AKPEAX@ZPEAUHWND__@@@Z`
- size: `196`
- prototype: `signed int __fastcall(CFciPropertiesShellExt *this, LPTHREAD_START_ROUTINE lpStartAddress, HWND)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18000c398`
- `0x18000e224`
- `0x18000f6dc`

## callees

- `0x1800052b0`
- `0x18000f294`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f31e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f31e`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18000f2ef`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18000f2ef`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18000f310`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18000f310`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f33e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f33e`

## pseudocode

```c
signed int __fastcall CFciPropertiesShellExt::StartBackgroundThread(
        CFciPropertiesShellExt *this,
        LPTHREAD_START_ROUTINE lpStartAddress,
        HWND a3)
{
  CFciPropertiesShellExt::PropertyInfo *v5; // rbx
  CFciPropertiesShellExt::PropertyInfo *v6; // rbp
  CFciPropertiesShellExt::PropertyInfo *v7; // rsi
  HANDLE Thread; // rbx
  signed int result; // eax
  void *v10; // rcx

  *((_QWORD *)this + 20) = a3;
  *((_DWORD *)this + 42) = 0;
  *((_DWORD *)this + 43) = 0;
  v5 = (CFciPropertiesShellExt::PropertyInfo *)*((_QWORD *)this + 12);
  v6 = (CFciPropertiesShellExt::PropertyInfo *)*((_QWORD *)this + 13);
  if ( v5 != v6 )
  {
    v7 = (CFciPropertiesShellExt::PropertyInfo *)*((_QWORD *)this + 12);
    do
    {
      CFciPropertiesShellExt::PropertyInfo::~PropertyInfo(v7);
      v7 = (CFciPropertiesShellExt::PropertyInfo *)((char *)v7 + 224);
    }
    while ( v7 != v6 );
    *((_QWORD *)this + 13) = v5;
  }
  ResetEvent(*((HANDLE *)this + 19));
  Thread = CreateThread(0, 0, lpStartAddress, this, 0, 0);
  if ( Thread )
  {
    v10 = (void *)*((_QWORD *)this + 17);
    if ( v10 )
      CloseHandle(v10);
    *((_QWORD *)this + 17) = Thread;
    return 0;
  }
  else
  {
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x18000f294  push    rbx
0x18000f296  push    rbp
0x18000f297  push    rsi
0x18000f298  push    rdi
0x18000f299  push    r14
0x18000f29b  sub     rsp, 30h
0x18000f29f  mov     r14, rdx
0x18000f2a2  mov     rdi, rcx
0x18000f2a5  mov     [rcx+0A0h], r8
0x18000f2ac  mov     dword ptr [rcx+0A8h], 0
0x18000f2b6  mov     dword ptr [rcx+0ACh], 0
0x18000f2c0  mov     rbx, [rcx+60h]
0x18000f2c4  mov     rbp, [rcx+68h]
0x18000f2c8  cmp     rbx, rbp
0x18000f2cb  jz      short loc_18000F2E8
0x18000f2cd  mov     rsi, rbx
0x18000f2d0  mov     rcx, rsi; this
0x18000f2d3  call    ??1PropertyInfo@CFciPropertiesShellExt@@QEAA@XZ; CFciPropertiesShellExt::PropertyInfo::~PropertyInfo(void)
0x18000f2d8  add     rsi, 0E0h
0x18000f2df  cmp     rsi, rbp
0x18000f2e2  jnz     short loc_18000F2D0
0x18000f2e4  mov     [rdi+68h], rbx
0x18000f2e8  mov     rcx, [rdi+98h]; hEvent
0x18000f2ef  call    cs:__imp_ResetEvent
0x18000f2f5  mov     [rsp+58h+lpThreadId], 0; lpThreadId
0x18000f2fe  mov     [rsp+58h+dwCreationFlags], 0; dwCreationFlags
0x18000f306  mov     r9, rdi; lpParameter
0x18000f309  mov     r8, r14; lpStartAddress
0x18000f30c  xor     edx, edx; dwStackSize
0x18000f30e  xor     ecx, ecx; lpThreadAttributes
0x18000f310  call    cs:__imp_CreateThread
0x18000f316  mov     rbx, rax
0x18000f319  test    rax, rax
0x18000f31c  jnz     short loc_18000F332
0x18000f31e  call    cs:__imp_GetLastError
0x18000f324  test    eax, eax
0x18000f326  jle     short loc_18000F34D
0x18000f328  movzx   eax, ax
0x18000f32b  or      eax, 80070000h
0x18000f330  jmp     short loc_18000F34D
0x18000f332  mov     rcx, [rdi+88h]; hObject
0x18000f339  test    rcx, rcx
0x18000f33c  jz      short loc_18000F344
0x18000f33e  call    cs:__imp_CloseHandle
0x18000f344  mov     [rdi+88h], rbx
0x18000f34b  xor     eax, eax
0x18000f34d  add     rsp, 30h
0x18000f351  pop     r14
0x18000f353  pop     rdi
0x18000f354  pop     rsi
0x18000f355  pop     rbp
0x18000f356  pop     rbx
0x18000f357  retn
```
