# CObjIdIndexChangeNotifier::StartListening(void)

- ea: `0x180007b20`
- end: `0x180007c00`
- name: `?StartListening@CObjIdIndexChangeNotifier@@AEAAXXZ`
- size: `224`
- prototype: `void __fastcall(CObjIdIndexChangeNotifier *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1800077b0`
- `0x180007a50`

## callees

- `0x180001678`
- `0x180007b20`
- `0x18000d038`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180007bca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007ba5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007be4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007bf2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007ba5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007be4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007bf2`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x180007b9b`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x180007b9b`
- `api-ms-win-core-file-l2-1-0!ReadDirectoryChangesW` at `0x180007b84`
- `api-ms-win-core-file-l2-1-0!ReadDirectoryChangesW` at `0x180007b84`

## pseudocode

```c
void __fastcall CObjIdIndexChangeNotifier::StartListening(CObjIdIndexChangeNotifier *this)
{
  struct _OVERLAPPED *v2; // rdi
  DWORD *lpBytesReturned; // rbp
  char *v4; // rdx
  __int64 v5; // rax
  void *v6; // rcx
  DWORD LastError; // eax
  DWORD v8; // eax
  struct _OVERLAPPED *lpOverlapped; // [rsp+30h] [rbp-38h]

  v2 = (struct _OVERLAPPED *)((char *)this + 2240);
  lpOverlapped = (struct _OVERLAPPED *)((char *)this + 2240);
  *((_QWORD *)this + 281) = 0;
  lpBytesReturned = (DWORD *)((char *)this + 2232);
  *((_QWORD *)this + 282) = 0;
  v4 = (char *)this + 80;
  v5 = *((_QWORD *)this + 2);
  v6 = (void *)*((_QWORD *)this + 1);
  *((_QWORD *)this + 283) = v5;
  v2->Internal = -1073741595;
  if ( !ReadDirectoryChangesW(v6, v4, 0x868u, 0, 1u, lpBytesReturned, lpOverlapped, 0) )
  {
    InterlockedCloseHandle((void **)this + 1, (void *)0xFFFFFFFFFFFFFFFFLL, 0);
    LastError = GetLastError();
    TrkRaiseWin32Error(LastError);
  }
  if ( GetOverlappedResult(*((HANDLE *)this + 1), v2, lpBytesReturned, 0) )
  {
    SetEvent(*((HANDLE *)this + 283));
  }
  else if ( GetLastError() != 996 )
  {
    v8 = GetLastError();
    TrkRaiseWin32Error(v8);
  }
}

```

## disassembly

```asm
0x180007b20  push    rbx
0x180007b22  push    rbp
0x180007b23  push    rsi
0x180007b24  push    rdi
0x180007b25  sub     rsp, 48h
0x180007b29  mov     rbx, rcx
0x180007b2c  lea     rdi, [rcx+8C0h]
0x180007b33  xor     ecx, ecx
0x180007b35  xor     r9d, r9d; bWatchSubtree
0x180007b38  mov     [rsp+68h+lpCompletionRoutine], rcx; lpCompletionRoutine
0x180007b3d  mov     r8d, 868h; nBufferLength
0x180007b43  mov     [rsp+68h+lpOverlapped], rdi; lpOverlapped
0x180007b48  mov     [rbx+8C8h], rcx
0x180007b4f  lea     rbp, [rbx+8B8h]
0x180007b56  mov     [rbx+8D0h], rcx
0x180007b5d  lea     rdx, [rbx+50h]; lpBuffer
0x180007b61  mov     rax, [rbx+10h]
0x180007b65  mov     rcx, [rbx+8]; hDirectory
0x180007b69  mov     [rsp+68h+lpBytesReturned], rbp; lpBytesReturned
0x180007b6e  mov     [rbx+8D8h], rax
0x180007b75  mov     qword ptr [rdi], 0FFFFFFFFC00000E5h
0x180007b7c  mov     [rsp+68h+dwNotifyFilter], 1; dwNotifyFilter
0x180007b84  call    cs:__imp_ReadDirectoryChangesW
0x180007b8a  test    eax, eax
0x180007b8c  jz      short loc_180007BD1
0x180007b8e  mov     rcx, [rbx+8]; hFile
0x180007b92  xor     r9d, r9d; bWait
0x180007b95  mov     r8, rbp; lpNumberOfBytesTransferred
0x180007b98  mov     rdx, rdi; lpOverlapped
0x180007b9b  call    cs:__imp_GetOverlappedResult
0x180007ba1  test    eax, eax
0x180007ba3  jnz     short loc_180007BBB
0x180007ba5  call    cs:__imp_GetLastError
0x180007bab  cmp     eax, 3E4h
0x180007bb0  jnz     short loc_180007BF2
0x180007bb2  add     rsp, 48h
0x180007bb6  pop     rdi
0x180007bb7  pop     rsi
0x180007bb8  pop     rbp
0x180007bb9  pop     rbx
0x180007bba  retn
0x180007bbb  mov     rcx, [rbx+8D8h]
0x180007bc2  add     rsp, 48h
0x180007bc6  pop     rdi
0x180007bc7  pop     rsi
0x180007bc8  pop     rbp
0x180007bc9  pop     rbx
0x180007bca  jmp     cs:__imp_SetEvent
0x180007bd1  xor     r8d, r8d; int
0x180007bd4  lea     rcx, [rbx+8]; void **
0x180007bd8  mov     rdx, 0FFFFFFFFFFFFFFFFh; void *
0x180007bdf  call    ?InterlockedCloseHandle@@YAXPEAPEAXPEAXH@Z; InterlockedCloseHandle(void * *,void *,int)
0x180007be4  call    cs:__imp_GetLastError
0x180007bea  mov     ecx, eax; int
0x180007bec  call    ?TrkRaiseWin32Error@@YAXJ@Z; TrkRaiseWin32Error(long)
0x180007bf2  call    cs:__imp_GetLastError
0x180007bf8  mov     ecx, eax; int
0x180007bfa  call    ?TrkRaiseWin32Error@@YAXJ@Z; TrkRaiseWin32Error(long)
```
