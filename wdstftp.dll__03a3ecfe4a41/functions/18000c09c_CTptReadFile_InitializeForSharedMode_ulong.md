# CTptReadFile::InitializeForSharedMode(ulong)

- ea: `0x18000c09c`
- end: `0x18000c160`
- name: `?InitializeForSharedMode@CTptReadFile@@QEAAKK@Z`
- size: `196`
- prototype: `unsigned int __fastcall(LPCRITICAL_SECTION lpCriticalSection, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180009008`

## callees

- `0x18000c09c`
- `0x18003a6d4`
- `0x18003ce78`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18000c0ab`
- `KERNEL32!EnterCriticalSection` at `0x18000c0ab`
- `KERNEL32!LeaveCriticalSection` at `0x18000c147`
- `KERNEL32!LeaveCriticalSection` at `0x18000c147`
- `KERNEL32!GetLastError` at `0x18000c0e3`
- `KERNEL32!GetLastError` at `0x18000c0e3`
- `KERNEL32!CreateEventW` at `0x18000c0cb`
- `KERNEL32!CreateEventW` at `0x18000c0cb`

## string_xrefs

- `0x18000c136`: `base\eco\wds\transport\lib\tptreadfile.cpp`

## pseudocode

```c
__int64 __fastcall CTptReadFile::InitializeForSharedMode(LPCRITICAL_SECTION lpCriticalSection, int a2)
{
  HANDLE EventW; // rax
  DWORD LastError; // eax
  const char *v6; // rdx
  const char *v7; // rdx
  unsigned int v8; // ebx
  const char *v9; // rdx

  EnterCriticalSection(lpCriticalSection);
  LODWORD(lpCriticalSection[2].LockSemaphore) = a2;
  HIDWORD(lpCriticalSection[3].DebugInfo) = 1;
  EventW = CreateEventW(0, 0, 0, 0);
  lpCriticalSection[4].OwningThread = EventW;
  if ( EventW )
  {
    v8 = CMRSWLock::Initialize((CMRSWLock *)&lpCriticalSection[4].LockSemaphore);
    ElValidateWin32(v8, v9, "internal\\onecorebase\\private\\inc\\eco\\wds\\ChildCount.h", 0xD9u);
  }
  else
  {
    LastError = GetLastError();
    v8 = ElValidateWin32(LastError, v6, "internal\\onecorebase\\private\\inc\\eco\\wds\\ChildCount.h", 0xD5u);
    if ( !v8 )
      v8 = 31;
  }
  ElValidateWin32(v8, v7, "base\\eco\\wds\\transport\\lib\\tptreadfile.cpp", 0x7Bu);
  LeaveCriticalSection(lpCriticalSection);
  return v8;
}

```

## disassembly

```asm
0x18000c09c  mov     [rsp+arg_0], rbx
0x18000c0a1  push    rdi
0x18000c0a2  sub     rsp, 20h
0x18000c0a6  mov     ebx, edx
0x18000c0a8  mov     rdi, rcx
0x18000c0ab  call    cs:__imp_EnterCriticalSection
0x18000c0b2  nop     dword ptr [rax+rax+00h]
0x18000c0b7  xor     r9d, r9d; lpName
0x18000c0ba  mov     [rdi+68h], ebx
0x18000c0bd  xor     r8d, r8d; bInitialState
0x18000c0c0  mov     dword ptr [rdi+7Ch], 1
0x18000c0c7  xor     edx, edx; bManualReset
0x18000c0c9  xor     ecx, ecx; lpEventAttributes
0x18000c0cb  call    cs:__imp_CreateEventW
0x18000c0d2  nop     dword ptr [rax+rax+00h]
0x18000c0d7  mov     [rdi+0B0h], rax
0x18000c0de  test    rax, rax
0x18000c0e1  jnz     short loc_18000C10E
0x18000c0e3  call    cs:__imp_GetLastError
0x18000c0ea  nop     dword ptr [rax+rax+00h]
0x18000c0ef  mov     r9d, 0D5h; unsigned int
0x18000c0f5  lea     r8, aInternalOnecor_0; "internal\\onecorebase\\private\\inc\\ec"...
0x18000c0fc  mov     ecx, eax; unsigned int
0x18000c0fe  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000c103  mov     ebx, eax
0x18000c105  test    eax, eax
0x18000c107  jnz     short loc_18000C130
0x18000c109  lea     ebx, [rax+1Fh]
0x18000c10c  jmp     short loc_18000C130
0x18000c10e  lea     rcx, [rdi+0B8h]; this
0x18000c115  call    ?Initialize@CMRSWLock@@QEAAKK@Z; CMRSWLock::Initialize(ulong)
0x18000c11a  mov     r9d, 0D9h; unsigned int
0x18000c120  lea     r8, aInternalOnecor_0; "internal\\onecorebase\\private\\inc\\ec"...
0x18000c127  mov     ecx, eax; unsigned int
0x18000c129  mov     ebx, eax
0x18000c12b  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000c130  mov     r9d, 7Bh ; '{'; unsigned int
0x18000c136  lea     r8, aBaseEcoWdsTran_9; "base\\eco\\wds\\transport\\lib\\tptread"...
0x18000c13d  mov     ecx, ebx; unsigned int
0x18000c13f  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000c144  mov     rcx, rdi; lpCriticalSection
0x18000c147  call    cs:__imp_LeaveCriticalSection
0x18000c14e  nop     dword ptr [rax+rax+00h]
0x18000c153  mov     eax, ebx
0x18000c155  mov     rbx, [rsp+28h+arg_0]
0x18000c15a  add     rsp, 20h
0x18000c15e  pop     rdi
0x18000c15f  retn
```
