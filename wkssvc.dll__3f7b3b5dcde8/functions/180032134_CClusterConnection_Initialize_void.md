# CClusterConnection::Initialize(void *)

- ea: `0x180032134`
- end: `0x1800321b8`
- name: `?Initialize@CClusterConnection@@QEAAKPEAX@Z`
- size: `132`
- prototype: `__int64 __fastcall(CClusterConnection *this, void *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18001c120`

## callees

- `0x18001d388`
- `0x18002055c`
- `0x180032134`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003219e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003219e`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18003215e`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18003215e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003218c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003218c`

## pseudocode

```c
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
0x180032134  mov     [rsp+arg_8], rbx
0x180032139  mov     [rsp+arg_10], rsi
0x18003213e  push    rdi
0x18003213f  sub     rsp, 20h
0x180032143  mov     rsi, rdx
0x180032146  mov     rdi, rcx
0x180032149  mov     ecx, 28h ; '('; Size
0x18003214e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180032153  mov     rbx, rax
0x180032156  mov     [rsp+28h+arg_0], rax
0x18003215b  mov     rcx, rax; lpCriticalSection
0x18003215e  call    cs:__imp_InitializeCriticalSection
0x180032164  nop
0x180032165  mov     [rdi+1B0h], rbx
0x18003216c  mov     rcx, rdi; this
0x18003216f  call    ?InitializeIP@CClusterConnection@@AEAAKXZ; CClusterConnection::InitializeIP(void)
0x180032174  mov     ebx, eax
0x180032176  test    eax, eax
0x180032178  jnz     short loc_1800321A6
0x18003217a  mov     [rdi+1B8h], rsi
0x180032181  xor     r9d, r9d; lpName
0x180032184  xor     r8d, r8d; bInitialState
0x180032187  lea     edx, [rax+1]; bManualReset
0x18003218a  xor     ecx, ecx; lpEventAttributes
0x18003218c  call    cs:__imp_CreateEventW
0x180032192  mov     [rdi+1A0h], rax
0x180032199  test    rax, rax
0x18003219c  jnz     short loc_1800321A6
0x18003219e  call    cs:__imp_GetLastError
0x1800321a4  mov     ebx, eax
0x1800321a6  mov     eax, ebx
0x1800321a8  mov     rbx, [rsp+28h+arg_8]
0x1800321ad  mov     rsi, [rsp+28h+arg_10]
0x1800321b2  add     rsp, 20h
0x1800321b6  pop     rdi
0x1800321b7  retn
```
