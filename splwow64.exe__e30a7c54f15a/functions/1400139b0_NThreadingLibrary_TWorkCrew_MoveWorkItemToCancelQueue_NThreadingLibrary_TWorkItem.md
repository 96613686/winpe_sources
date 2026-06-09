# NThreadingLibrary::TWorkCrew::MoveWorkItemToCancelQueue(NThreadingLibrary::TWorkItem *)

- ea: `0x1400139b0`
- end: `0x140013abc`
- name: `?MoveWorkItemToCancelQueue@TWorkCrew@NThreadingLibrary@@AEAAJPEAVTWorkItem@2@@Z`
- size: `268`
- prototype: `__int64 __fastcall(NThreadingLibrary::TWorkCrew *__hidden this, struct NThreadingLibrary::TWorkItem *)`
- caller_count: `6`
- callee_count: `3`
- tags: ``

## callers

- `0x1400133fc`
- `0x140013870`
- `0x140013cc0`
- `0x140013d00`
- `0x140013de0`
- `0x140013f20`

## callees

- `0x140012bd4`
- `0x1400139b0`
- `0x1400140b8`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1400139ce`
- `KERNEL32!GetCurrentThreadId` at `0x1400139ce`
- `KERNEL32!SetEvent` at `0x140013a5d`
- `KERNEL32!SetEvent` at `0x140013a91`
- `KERNEL32!SetEvent` at `0x140013a5d`
- `KERNEL32!SetEvent` at `0x140013a91`
- `KERNEL32!EnterCriticalSection` at `0x1400139c5`
- `KERNEL32!EnterCriticalSection` at `0x1400139c5`
- `KERNEL32!LeaveCriticalSection` at `0x140013aab`
- `KERNEL32!LeaveCriticalSection` at `0x140013aab`

## pseudocode

```c
__int64 __fastcall NThreadingLibrary::TWorkCrew::MoveWorkItemToCancelQueue(
        NThreadingLibrary::TWorkCrew *this,
        __int64 a2)
{
  int LastErrorAsHResult; // ebx
  unsigned __int64 v5; // rdx
  __int64 v6; // rcx
  __int64 v7; // rbp
  NCoreLibrary *v8; // rcx

  LastErrorAsHResult = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)this + 1);
  ++*((_DWORD *)this + 21);
  *((_DWORD *)this + 20) = GetCurrentThreadId();
  if ( !*(_DWORD *)(a2 + 72) && *(_QWORD *)(a2 + 80) )
  {
    v5 = a2 + 32;
    *(_DWORD *)(a2 + 72) = 1;
    v6 = *(_QWORD *)(a2 + 48);
    v7 = -a2;
    *(_QWORD *)(v6 + 24) = *(_QWORD *)(v5 + 24);
    *(_QWORD *)(*(_QWORD *)(v5 + 24) + 16LL) = *(_QWORD *)(v5 + 16);
    *(_QWORD *)(v5 + 16) = v5;
    *(_QWORD *)(v5 + 24) = v5;
    if ( (v5 & -(__int64)(v7 != 0)) != 0 )
    {
      if ( !*(_QWORD *)((v5 & -(__int64)(v7 != 0)) + 0x10) || !*(_QWORD *)((v5 & -(__int64)(v7 != 0)) + 0x18) )
        LastErrorAsHResult = -2147467259;
      if ( LastErrorAsHResult >= 0 )
        LastErrorAsHResult = NCoreLibrary::TLink::Link(
                               *((NCoreLibrary::TLink **)this + 21),
                               (struct NCoreLibrary::TLink *)(v5 & -(__int64)(v7 != 0)));
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
        LastErrorAsHResult = NCoreLibrary::GetLastErrorAsHResult(v8);
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
0x1400139b0  push    rbx
0x1400139b2  push    rbp
0x1400139b3  push    rsi
0x1400139b4  push    rdi
0x1400139b5  sub     rsp, 28h
0x1400139b9  mov     rdi, rcx
0x1400139bc  mov     rbp, rdx
0x1400139bf  add     rcx, 28h ; '('; lpCriticalSection
0x1400139c3  xor     ebx, ebx
0x1400139c5  call    cs:__imp_EnterCriticalSection
0x1400139cb  inc     dword ptr [rdi+54h]
0x1400139ce  call    cs:__imp_GetCurrentThreadId
0x1400139d4  mov     [rdi+50h], eax
0x1400139d7  cmp     [rbp+48h], ebx
0x1400139da  jnz     loc_140013A97
0x1400139e0  cmp     [rbp+50h], rbx
0x1400139e4  jz      loc_140013A97
0x1400139ea  lea     rdx, [rbp+20h]
0x1400139ee  mov     dword ptr [rbp+48h], 1
0x1400139f5  mov     rcx, [rdx+10h]
0x1400139f9  neg     rbp
0x1400139fc  mov     rax, [rdx+18h]
0x140013a00  mov     [rcx+18h], rax
0x140013a04  mov     rax, [rdx+10h]
0x140013a08  mov     rcx, [rdx+18h]
0x140013a0c  mov     [rcx+10h], rax
0x140013a10  sbb     rax, rax
0x140013a13  mov     [rdx+10h], rdx
0x140013a17  mov     [rdx+18h], rdx
0x140013a1b  and     rax, rdx
0x140013a1e  jz      short loc_140013A48
0x140013a20  cmp     [rax+10h], rbx
0x140013a24  jz      short loc_140013A2C
0x140013a26  cmp     [rax+18h], rbx
0x140013a2a  jnz     short loc_140013A31
0x140013a2c  mov     ebx, 80004005h
0x140013a31  test    ebx, ebx
0x140013a33  js      short loc_140013A4D
0x140013a35  mov     rcx, [rdi+0A8h]; this
0x140013a3c  mov     rdx, rax; struct NCoreLibrary::TLink *
0x140013a3f  call    ?Link@TLink@NCoreLibrary@@QEAAJPEAV12@@Z; NCoreLibrary::TLink::Link(NCoreLibrary::TLink *)
0x140013a44  mov     ebx, eax
0x140013a46  jmp     short loc_140013A4D
0x140013a48  mov     ebx, 80070057h
0x140013a4d  cmp     dword ptr [rdi+0C0h], 0
0x140013a54  jnz     short loc_140013A72
0x140013a56  mov     rcx, [rdi+0B8h]; hEvent
0x140013a5d  call    cs:__imp_SetEvent
0x140013a63  test    eax, eax
0x140013a65  jz      short loc_140013A6B
0x140013a67  xor     ebx, ebx
0x140013a69  jmp     short loc_140013A72
0x140013a6b  call    ?GetLastErrorAsHResult@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsHResult(void)
0x140013a70  mov     ebx, eax
0x140013a72  dec     dword ptr [rdi+0C8h]
0x140013a78  cmp     dword ptr [rdi+0B0h], 0
0x140013a7f  jz      short loc_140013A97
0x140013a81  cmp     dword ptr [rdi+0C8h], 0
0x140013a88  jnz     short loc_140013A97
0x140013a8a  mov     rcx, [rdi+0D0h]; hEvent
0x140013a91  call    cs:__imp_SetEvent
0x140013a97  add     dword ptr [rdi+54h], 0FFFFFFFFh
0x140013a9b  mov     eax, [rdi+54h]
0x140013a9e  jnz     short loc_140013AA7
0x140013aa0  mov     dword ptr [rdi+50h], 0
0x140013aa7  lea     rcx, [rdi+28h]; lpCriticalSection
0x140013aab  call    cs:__imp_LeaveCriticalSection
0x140013ab1  mov     eax, ebx
0x140013ab3  add     rsp, 28h
0x140013ab7  pop     rdi
0x140013ab8  pop     rsi
0x140013ab9  pop     rbp
0x140013aba  pop     rbx
0x140013abb  retn
```
