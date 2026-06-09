# P2P_THREAD_POOL::WorkerThreadRoutine(void *)

- ea: `0x18006a0f0`
- end: `0x18006a1a4`
- name: `?WorkerThreadRoutine@P2P_THREAD_POOL@@CAKPEAX@Z`
- size: `180`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18006a0f0`
- `0x18006a1ac`
- `0x180098010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006a162`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006a162`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x18006a155`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x18006a155`
- `api-ms-win-core-io-l1-1-0!GetQueuedCompletionStatus` at `0x18006a125`
- `api-ms-win-core-io-l1-1-0!GetQueuedCompletionStatus` at `0x18006a125`

## pseudocode

```c
void __fastcall __noreturn P2P_THREAD_POOL::WorkerThreadRoutine(HANDLE *Parameter)
{
  DWORD LastError; // esi
  LPOVERLAPPED v3; // r8
  HMODULE v4; // rbx
  LPOVERLAPPED v5; // rcx
  int Internal; // edx
  DWORD NumberOfBytesTransferred; // [rsp+50h] [rbp+8h] BYREF
  LPOVERLAPPED Overlapped; // [rsp+58h] [rbp+10h] BYREF
  unsigned __int64 CompletionKey; // [rsp+60h] [rbp+18h] BYREF

  LastError = 0;
  NumberOfBytesTransferred = 0;
  CompletionKey = 0;
  Overlapped = 0;
  while ( 1 )
  {
    GetQueuedCompletionStatus(*Parameter, &NumberOfBytesTransferred, &CompletionKey, &Overlapped, 0xFFFFFFFF);
    v3 = Overlapped;
    if ( !Overlapped )
      break;
    if ( Overlapped == (LPOVERLAPPED)(Parameter + 2) )
      goto LABEL_4;
    v5 = Overlapped - 1;
    Internal = Overlapped->Internal;
    NumberOfBytesTransferred = Overlapped->InternalHigh;
    LODWORD(Overlapped[1].Internal) = Internal;
    HIDWORD(v3[1].Internal) = NumberOfBytesTransferred;
    v3[1].InternalHigh = CompletionKey;
    ((void (__fastcall *)(LPOVERLAPPED))v3[-1].Internal)(v5);
  }
  LastError = GetLastError();
LABEL_4:
  v4 = (HMODULE)Parameter[6];
  P2P_THREAD_POOL::Dereference((P2P_THREAD_POOL *)Parameter);
  FreeLibraryAndExitThread(v4, LastError);
}

```

## disassembly

```asm
0x18006a0f0  push    rbx
0x18006a0f2  push    rsi
0x18006a0f3  push    rdi
0x18006a0f4  sub     rsp, 30h
0x18006a0f8  xor     esi, esi
0x18006a0fa  mov     rdi, rcx
0x18006a0fd  mov     [rsp+48h+NumberOfBytesTransferred], esi
0x18006a101  mov     [rsp+48h+CompletionKey], rsi
0x18006a106  mov     [rsp+48h+Overlapped], rsi
0x18006a10b  mov     rcx, [rdi]; CompletionPort
0x18006a10e  lea     r9, [rsp+48h+Overlapped]; lpOverlapped
0x18006a113  lea     r8, [rsp+48h+CompletionKey]; lpCompletionKey
0x18006a118  mov     [rsp+48h+dwMilliseconds], 0FFFFFFFFh; dwMilliseconds
0x18006a120  lea     rdx, [rsp+48h+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x18006a125  call    cs:__imp_GetQueuedCompletionStatus
0x18006a12c  nop     dword ptr [rax+rax+00h]
0x18006a131  mov     r8, [rsp+48h+Overlapped]
0x18006a136  test    r8, r8
0x18006a139  jz      short loc_18006A162
0x18006a13b  lea     rax, [rdi+10h]
0x18006a13f  cmp     r8, rax
0x18006a142  jnz     short loc_18006A172
0x18006a144  mov     rbx, [rdi+30h]
0x18006a148  mov     rcx, rdi; this
0x18006a14b  call    ?Dereference@P2P_THREAD_POOL@@AEAAXXZ; P2P_THREAD_POOL::Dereference(void)
0x18006a150  mov     edx, esi; dwExitCode
0x18006a152  mov     rcx, rbx; hLibModule
0x18006a155  call    cs:__imp_FreeLibraryAndExitThread
0x18006a15c  nop     dword ptr [rax+rax+00h]
0x18006a161  int     3; Trap to Debugger
0x18006a162  call    cs:__imp_GetLastError
0x18006a169  nop     dword ptr [rax+rax+00h]
0x18006a16e  mov     esi, eax
0x18006a170  jmp     short loc_18006A144
0x18006a172  mov     eax, [r8+8]
0x18006a176  lea     rcx, [r8-20h]
0x18006a17a  mov     edx, [r8]
0x18006a17d  mov     [rsp+48h+NumberOfBytesTransferred], eax
0x18006a181  mov     [r8+20h], edx
0x18006a185  mov     eax, [rsp+48h+NumberOfBytesTransferred]
0x18006a189  mov     [r8+24h], eax
0x18006a18d  mov     rax, [rsp+48h+CompletionKey]
0x18006a192  mov     [r8+28h], rax
0x18006a196  mov     rax, [r8-20h]
0x18006a19a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a19f  jmp     loc_18006A10B
```
