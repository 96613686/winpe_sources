# CTptReadFile::Initialize(ulong,ulong)

- ea: `0x18000bfcc`
- end: `0x18000c094`
- name: `?Initialize@CTptReadFile@@QEAAKKK@Z`
- size: `200`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection, int)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180006590`
- `0x180008d80`

## callees

- `0x18000bfcc`
- `0x18003a6d4`
- `0x18003ce78`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18000bfdb`
- `KERNEL32!EnterCriticalSection` at `0x18000bfdb`
- `KERNEL32!LeaveCriticalSection` at `0x18000c07b`
- `KERNEL32!LeaveCriticalSection` at `0x18000c07b`
- `KERNEL32!GetLastError` at `0x18000c017`
- `KERNEL32!GetLastError` at `0x18000c017`
- `KERNEL32!CreateEventW` at `0x18000bfff`
- `KERNEL32!CreateEventW` at `0x18000bfff`

## string_xrefs

- `0x18000c06a`: `base\eco\wds\transport\lib\tptreadfile.cpp`

## pseudocode

```c
__int64 __fastcall CTptReadFile::Initialize(LPCRITICAL_SECTION lpCriticalSection, int a2)
{
  HANDLE EventW; // rax
  unsigned int v5; // edx
  DWORD LastError; // eax
  const char *v7; // rdx
  const char *v8; // rdx
  unsigned int v9; // ebx
  const char *v10; // rdx

  EnterCriticalSection(lpCriticalSection);
  HIDWORD(lpCriticalSection[3].DebugInfo) = 0;
  HIDWORD(lpCriticalSection[2].LockSemaphore) = 2;
  LODWORD(lpCriticalSection[2].LockSemaphore) = a2;
  EventW = CreateEventW(0, 0, 0, 0);
  lpCriticalSection[4].OwningThread = EventW;
  if ( EventW )
  {
    v9 = CMRSWLock::Initialize((CMRSWLock *)&lpCriticalSection[4].LockSemaphore, v5);
    ElValidateWin32(v9, v10, "internal\\onecorebase\\private\\inc\\eco\\wds\\ChildCount.h", 0xD9u);
  }
  else
  {
    LastError = GetLastError();
    v9 = ElValidateWin32(LastError, v7, "internal\\onecorebase\\private\\inc\\eco\\wds\\ChildCount.h", 0xD5u);
    if ( !v9 )
      v9 = 31;
  }
  ElValidateWin32(v9, v8, "base\\eco\\wds\\transport\\lib\\tptreadfile.cpp", 0x54u);
  LeaveCriticalSection(lpCriticalSection);
  return v9;
}

```

## disassembly

```asm
0x18000bfcc  mov     [rsp+arg_0], rbx
0x18000bfd1  push    rdi
0x18000bfd2  sub     rsp, 20h
0x18000bfd6  mov     ebx, edx
0x18000bfd8  mov     rdi, rcx
0x18000bfdb  call    cs:__imp_EnterCriticalSection
0x18000bfe2  nop     dword ptr [rax+rax+00h]
0x18000bfe7  and     dword ptr [rdi+7Ch], 0
0x18000bfeb  xor     r9d, r9d; lpName
0x18000bfee  xor     r8d, r8d; bInitialState
0x18000bff1  mov     dword ptr [rdi+6Ch], 2
0x18000bff8  xor     edx, edx; bManualReset
0x18000bffa  mov     [rdi+68h], ebx
0x18000bffd  xor     ecx, ecx; lpEventAttributes
0x18000bfff  call    cs:__imp_CreateEventW
0x18000c006  nop     dword ptr [rax+rax+00h]
0x18000c00b  mov     [rdi+0B0h], rax
0x18000c012  test    rax, rax
0x18000c015  jnz     short loc_18000C042
0x18000c017  call    cs:__imp_GetLastError
0x18000c01e  nop     dword ptr [rax+rax+00h]
0x18000c023  mov     r9d, 0D5h; unsigned int
0x18000c029  lea     r8, aInternalOnecor_0; "internal\\onecorebase\\private\\inc\\ec"...
0x18000c030  mov     ecx, eax; unsigned int
0x18000c032  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000c037  mov     ebx, eax
0x18000c039  test    eax, eax
0x18000c03b  jnz     short loc_18000C064
0x18000c03d  lea     ebx, [rax+1Fh]
0x18000c040  jmp     short loc_18000C064
0x18000c042  lea     rcx, [rdi+0B8h]; this
0x18000c049  call    ?Initialize@CMRSWLock@@QEAAKK@Z; CMRSWLock::Initialize(ulong)
0x18000c04e  mov     r9d, 0D9h; unsigned int
0x18000c054  lea     r8, aInternalOnecor_0; "internal\\onecorebase\\private\\inc\\ec"...
0x18000c05b  mov     ecx, eax; unsigned int
0x18000c05d  mov     ebx, eax
0x18000c05f  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000c064  mov     r9d, 54h ; 'T'; unsigned int
0x18000c06a  lea     r8, aBaseEcoWdsTran_9; "base\\eco\\wds\\transport\\lib\\tptread"...
0x18000c071  mov     ecx, ebx; unsigned int
0x18000c073  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000c078  mov     rcx, rdi; lpCriticalSection
0x18000c07b  call    cs:__imp_LeaveCriticalSection
0x18000c082  nop     dword ptr [rax+rax+00h]
0x18000c087  mov     eax, ebx
0x18000c089  mov     rbx, [rsp+28h+arg_0]
0x18000c08e  add     rsp, 20h
0x18000c092  pop     rdi
0x18000c093  retn
```
