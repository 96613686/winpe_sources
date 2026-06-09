# NThreadingLibrary::TWorkCrew::MoveWorkItemToCancelQueue(NThreadingLibrary::TWorkItem *)

- ea: `0x140007a90`
- end: `0x140007c23`
- name: `?MoveWorkItemToCancelQueue@TWorkCrew@NThreadingLibrary@@AEAAJPEAVTWorkItem@2@@Z`
- size: `403`
- prototype: `__int64 __fastcall(NThreadingLibrary::TWorkCrew *__hidden this, struct NThreadingLibrary::TWorkItem *)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x140007600`
- `0x14000b130`
- `0x140056798`
- `0x140056a40`
- `0x140056b00`

## callees

- `0x140007a90`
- `0x1400087c8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140007b63`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140007c06`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140007b63`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140007c06`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140007b95`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140007b95`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140007aa5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140007aa5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140007ab4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140007ab4`

## pseudocode

```c
__int64 __fastcall NThreadingLibrary::TWorkCrew::MoveWorkItemToCancelQueue(
        NThreadingLibrary::TWorkCrew *this,
        struct NThreadingLibrary::TWorkItem *a2)
{
  int LastErrorAsHResult; // esi
  char *v5; // rdx
  __int64 v6; // rax
  __int64 v7; // r9
  __int64 v8; // rcx
  char *v11; // rcx

  LastErrorAsHResult = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)this + 1);
  ++*((_DWORD *)this + 21);
  *((_DWORD *)this + 20) = GetCurrentThreadId();
  if ( !*((_DWORD *)a2 + 18) && *((_QWORD *)a2 + 10) )
  {
    *((_DWORD *)a2 + 18) = 1;
    v5 = (char *)a2 + 32;
    *(_QWORD *)(*((_QWORD *)a2 + 6) + 24LL) = *((_QWORD *)a2 + 7);
    *(_QWORD *)(*((_QWORD *)a2 + 7) + 16LL) = *((_QWORD *)a2 + 6);
    *((_QWORD *)a2 + 6) = (char *)a2 + 32;
    *((_QWORD *)a2 + 7) = (char *)a2 + 32;
    if ( !a2 )
      v5 = 0;
    if ( v5 )
    {
      v6 = *((_QWORD *)v5 + 2);
      if ( !v6 || !*((_QWORD *)v5 + 3) )
        LastErrorAsHResult = -2147467259;
      if ( LastErrorAsHResult >= 0 )
      {
        v7 = *((_QWORD *)this + 21);
        if ( (char *)v6 != v5 )
        {
          v11 = (char *)*((_QWORD *)v5 + 3);
          if ( v11 != v5 )
          {
            *(_QWORD *)(v6 + 24) = v11;
            *(_QWORD *)(*((_QWORD *)v5 + 3) + 16LL) = *((_QWORD *)v5 + 2);
            *((_QWORD *)v5 + 2) = v5;
            *((_QWORD *)v5 + 3) = v5;
          }
        }
        LastErrorAsHResult = 0;
        *(_QWORD *)(*(_QWORD *)(v7 + 16) + 24LL) = v5;
        *((_QWORD *)v5 + 2) = *(_QWORD *)(v7 + 16);
        *((_QWORD *)v5 + 3) = v7;
        *(_QWORD *)(v7 + 16) = v5;
      }
    }
    else
    {
      LastErrorAsHResult = -2147024809;
    }
    if ( !*((_DWORD *)this + 48) )
    {
      if ( SetEvent(*((HANDLE *)this + 23)) )
        LastErrorAsHResult = 0;
      else
        LastErrorAsHResult = GetLastErrorAsHResult(v8);
    }
    --*((_DWORD *)this + 50);
    if ( *((_DWORD *)this + 44) && !*((_DWORD *)this + 50) )
      SetEvent(*((HANDLE *)this + 26));
  }
  if ( (*((_DWORD *)this + 21))-- == 1 )
    *((_DWORD *)this + 20) = 0;
  LeaveCriticalSection((LPCRITICAL_SECTION)this + 1);
  return (unsigned int)LastErrorAsHResult;
}

```

## disassembly

```asm
0x140007a90  push    rbx
0x140007a92  push    rbp
0x140007a93  push    rsi
0x140007a94  push    rdi
0x140007a95  sub     rsp, 28h
0x140007a99  mov     rdi, rcx
0x140007a9c  mov     rbp, rdx
0x140007a9f  add     rcx, 28h ; '('; lpCriticalSection
0x140007aa3  xor     esi, esi
0x140007aa5  call    cs:__imp_EnterCriticalSection
0x140007aac  nop     dword ptr [rax+rax+00h]
0x140007ab1  inc     dword ptr [rdi+54h]
0x140007ab4  call    cs:__imp_GetCurrentThreadId
0x140007abb  nop     dword ptr [rax+rax+00h]
0x140007ac0  mov     [rdi+50h], eax
0x140007ac3  cmp     [rbp+48h], esi
0x140007ac6  jnz     loc_140007B84
0x140007acc  cmp     [rbp+50h], rsi
0x140007ad0  jz      loc_140007B84
0x140007ad6  mov     dword ptr [rbp+48h], 1
0x140007add  lea     rdx, [rbp+20h]
0x140007ae1  mov     rcx, [rdx+10h]
0x140007ae5  mov     rax, [rdx+18h]
0x140007ae9  mov     [rcx+18h], rax
0x140007aed  mov     rax, [rdx+10h]
0x140007af1  mov     rcx, [rdx+18h]
0x140007af5  mov     [rcx+10h], rax
0x140007af9  xor     eax, eax
0x140007afb  test    rbp, rbp
0x140007afe  mov     [rdx+10h], rdx
0x140007b02  mov     [rdx+18h], rdx
0x140007b06  cmovz   rdx, rax
0x140007b0a  test    rdx, rdx
0x140007b0d  jz      loc_140007BC5
0x140007b13  mov     rax, [rdx+10h]
0x140007b17  test    rax, rax
0x140007b1a  jnz     loc_140007BB6
0x140007b20  mov     esi, 80004005h
0x140007b25  test    esi, esi
0x140007b27  js      short loc_140007B53
0x140007b29  mov     r9, [rdi+0A8h]
0x140007b30  cmp     rax, rdx
0x140007b33  jnz     loc_140007BCC
0x140007b39  mov     rax, [r9+10h]
0x140007b3d  xor     esi, esi
0x140007b3f  mov     [rax+18h], rdx
0x140007b43  mov     rax, [r9+10h]
0x140007b47  mov     [rdx+10h], rax
0x140007b4b  mov     [rdx+18h], r9
0x140007b4f  mov     [r9+10h], rdx
0x140007b53  cmp     dword ptr [rdi+0C0h], 0
0x140007b5a  jnz     short loc_140007B75
0x140007b5c  mov     rcx, [rdi+0B8h]; hEvent
0x140007b63  call    cs:__imp_SetEvent
0x140007b6a  nop     dword ptr [rax+rax+00h]
0x140007b6f  test    eax, eax
0x140007b71  jz      short loc_140007BAD
0x140007b73  xor     esi, esi
0x140007b75  dec     dword ptr [rdi+0C8h]
0x140007b7b  cmp     dword ptr [rdi+0B0h], 0
0x140007b82  jnz     short loc_140007BF6
0x140007b84  add     dword ptr [rdi+54h], 0FFFFFFFFh
0x140007b88  mov     eax, [rdi+54h]
0x140007b8b  jz      loc_140007C17
0x140007b91  lea     rcx, [rdi+28h]; lpCriticalSection
0x140007b95  call    cs:__imp_LeaveCriticalSection
0x140007b9c  nop     dword ptr [rax+rax+00h]
0x140007ba1  mov     eax, esi
0x140007ba3  add     rsp, 28h
0x140007ba7  pop     rdi
0x140007ba8  pop     rsi
0x140007ba9  pop     rbp
0x140007baa  pop     rbx
0x140007bab  retn
0x140007bad  call    GetLastErrorAsHResult
0x140007bb2  mov     esi, eax
0x140007bb4  jmp     short loc_140007B75
0x140007bb6  cmp     [rdx+18h], rsi
0x140007bba  jnz     loc_140007B25
0x140007bc0  jmp     loc_140007B20
0x140007bc5  mov     esi, 80070057h
0x140007bca  jmp     short loc_140007B53
0x140007bcc  mov     rcx, [rdx+18h]
0x140007bd0  cmp     rcx, rdx
0x140007bd3  jz      loc_140007B39
0x140007bd9  mov     [rax+18h], rcx
0x140007bdd  mov     rcx, [rdx+18h]
0x140007be1  mov     rax, [rdx+10h]
0x140007be5  mov     [rcx+10h], rax
0x140007be9  mov     [rdx+10h], rdx
0x140007bed  mov     [rdx+18h], rdx
0x140007bf1  jmp     loc_140007B39
0x140007bf6  cmp     dword ptr [rdi+0C8h], 0
0x140007bfd  jnz     short loc_140007B84
0x140007bff  mov     rcx, [rdi+0D0h]; hEvent
0x140007c06  call    cs:__imp_SetEvent
0x140007c0d  nop     dword ptr [rax+rax+00h]
0x140007c12  jmp     loc_140007B84
0x140007c17  mov     dword ptr [rdi+50h], 0
0x140007c1e  jmp     loc_140007B91
```
