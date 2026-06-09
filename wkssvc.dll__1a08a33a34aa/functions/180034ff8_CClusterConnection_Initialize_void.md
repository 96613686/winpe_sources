# CClusterConnection::Initialize(void *)

- ea: `0x180034ff8`
- end: `0x18003508f`
- name: `?Initialize@CClusterConnection@@QEAAKPEAX@Z`
- size: `151`
- prototype: `unsigned int __fastcall(CClusterConnection *__hidden this, void *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18001d6d8`

## callees

- `0x18001e9e0`
- `0x180021d0c`
- `0x180034ff8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003506e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003506e`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180035022`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180035022`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180035056`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180035056`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CClusterConnection::Initialize(CClusterConnection *this, void *a2)
{
  unsigned int v4; // ebx
  HANDLE EventW; // rax
  struct _RTL_CRITICAL_SECTION *v7; // [rsp+30h] [rbp+8h]

  v7 = (struct _RTL_CRITICAL_SECTION *)operator new(0x28u);
  InitializeCriticalSection(v7);
  *((_QWORD *)this + 54) = v7;
  v4 = CClusterConnection::InitializeIP(this);
  if ( !v4 )
  {
    *((_QWORD *)this + 55) = a2;
    EventW = CreateEventW(0, 1, 0, 0);
    *((_QWORD *)this + 52) = EventW;
    if ( !EventW )
      return GetLastError();
  }
  return v4;
}

```

## disassembly

```asm
0x180034ff8  mov     [rsp+arg_8], rbx
0x180034ffd  mov     [rsp+arg_10], rsi
0x180035002  push    rdi
0x180035003  sub     rsp, 20h
0x180035007  mov     rsi, rdx
0x18003500a  mov     rdi, rcx
0x18003500d  mov     ecx, 28h ; '('; Size
0x180035012  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180035017  mov     rbx, rax
0x18003501a  mov     [rsp+28h+arg_0], rax
0x18003501f  mov     rcx, rax; lpCriticalSection
0x180035022  call    cs:__imp_InitializeCriticalSection
0x180035029  nop     dword ptr [rax+rax+00h]
0x18003502e  nop
0x18003502f  mov     [rdi+1B0h], rbx
0x180035036  mov     rcx, rdi; this
0x180035039  call    ?InitializeIP@CClusterConnection@@AEAAKXZ; CClusterConnection::InitializeIP(void)
0x18003503e  mov     ebx, eax
0x180035040  test    eax, eax
0x180035042  jnz     short loc_18003507C
0x180035044  mov     [rdi+1B8h], rsi
0x18003504b  xor     r9d, r9d; lpName
0x18003504e  xor     r8d, r8d; bInitialState
0x180035051  lea     edx, [rax+1]; bManualReset
0x180035054  xor     ecx, ecx; lpEventAttributes
0x180035056  call    cs:__imp_CreateEventW
0x18003505d  nop     dword ptr [rax+rax+00h]
0x180035062  mov     [rdi+1A0h], rax
0x180035069  test    rax, rax
0x18003506c  jnz     short loc_18003507C
0x18003506e  call    cs:__imp_GetLastError
0x180035075  nop     dword ptr [rax+rax+00h]
0x18003507a  mov     ebx, eax
0x18003507c  mov     eax, ebx
0x18003507e  mov     rbx, [rsp+28h+arg_8]
0x180035083  mov     rsi, [rsp+28h+arg_10]
0x180035088  add     rsp, 20h
0x18003508c  pop     rdi
0x18003508d  retn
```
