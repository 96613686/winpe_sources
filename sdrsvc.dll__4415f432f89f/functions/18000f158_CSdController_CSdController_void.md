# CSdController::~CSdController(void)

- ea: `0x18000f158`
- end: `0x18000f225`
- name: `??1CSdController@@AEAA@XZ`
- size: `205`
- prototype: `void __fastcall(CSdController *__hidden this)`
- caller_count: `5`
- callee_count: `3`
- tags: `file_ops, loader_planting`

## callers

- `0x180008a40`
- `0x180008c00`
- `0x180008ce0`
- `0x18000a7a8`
- `0x18000cc80`

## callees

- `0x180001554`
- `0x18000f158`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f17b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f17b`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x18000f1fb`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x18000f1fb`
- `ntdll!RtlFreeHeap` at `0x18000f1f1`
- `ntdll!RtlFreeHeap` at `0x18000f1f1`

## pseudocode

```c
void __fastcall CSdController::~CSdController(CSdController *this)
{
  char *v2; // rcx
  __int64 v3; // rcx
  __int64 v4; // rcx
  union _SLIST_HEADER *v5; // rdi
  PSLIST_ENTRY v6; // rax

  v2 = (char *)*((_QWORD *)this + 19);
  if ( (unsigned __int64)(v2 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    CloseHandle(v2);
    *((_QWORD *)this + 19) = 0;
  }
  v3 = *((_QWORD *)this + 18);
  if ( v3 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  v4 = *((_QWORD *)this + 17);
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  v5 = (union _SLIST_HEADER *)*((_QWORD *)this + 5);
  if ( v5 )
  {
    *((_QWORD *)this + 5) = 0;
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v5, 0xFFFFFFFF) == 1 )
    {
      while ( 1 )
      {
        v6 = InterlockedPopEntrySList(v5 + 1);
        if ( !v6 )
          break;
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, &v6[-17]);
      }
      operator delete(v5);
    }
  }
  *((_DWORD *)this + 4) = 1280463971;
}

```

## disassembly

```asm
0x18000f158  mov     [rsp+arg_8], rbx
0x18000f15d  mov     [rsp+arg_10], rsi
0x18000f162  push    rdi
0x18000f163  sub     rsp, 20h
0x18000f167  mov     rbx, rcx
0x18000f16a  mov     rcx, [rcx+98h]; hObject
0x18000f171  lea     rax, [rcx-1]
0x18000f175  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000f179  ja      short loc_18000F18C
0x18000f17b  call    cs:__imp_CloseHandle
0x18000f181  mov     qword ptr [rbx+98h], 0
0x18000f18c  mov     rcx, [rbx+90h]
0x18000f193  test    rcx, rcx
0x18000f196  jz      short loc_18000F1A4
0x18000f198  mov     rax, [rcx]
0x18000f19b  mov     rax, [rax+10h]
0x18000f19f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f1a4  mov     rcx, [rbx+88h]
0x18000f1ab  test    rcx, rcx
0x18000f1ae  jz      short loc_18000F1BC
0x18000f1b0  mov     rax, [rcx]
0x18000f1b3  mov     rax, [rax+10h]
0x18000f1b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f1bc  mov     rdi, [rbx+28h]
0x18000f1c0  test    rdi, rdi
0x18000f1c3  jz      short loc_18000F20E
0x18000f1c5  mov     qword ptr [rbx+28h], 0
0x18000f1cd  or      eax, 0FFFFFFFFh
0x18000f1d0  lock xadd [rdi], eax
0x18000f1d4  cmp     eax, 1
0x18000f1d7  jnz     short loc_18000F20E
0x18000f1d9  jmp     short loc_18000F1F7
0x18000f1db  mov     rcx, gs:60h
0x18000f1e4  lea     r8, [rax-110h]; P
0x18000f1eb  xor     edx, edx; Flags
0x18000f1ed  mov     rcx, [rcx+30h]; HeapHandle
0x18000f1f1  call    cs:__imp_RtlFreeHeap
0x18000f1f7  lea     rcx, [rdi+10h]; ListHead
0x18000f1fb  call    cs:__imp_InterlockedPopEntrySList
0x18000f201  test    rax, rax
0x18000f204  jnz     short loc_18000F1DB
0x18000f206  mov     rcx, rdi; Block
0x18000f209  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000f20e  mov     rsi, [rsp+28h+arg_10]
0x18000f213  mov     dword ptr [rbx+10h], 4C525463h
0x18000f21a  mov     rbx, [rsp+28h+arg_8]
0x18000f21f  add     rsp, 20h
0x18000f223  pop     rdi
0x18000f224  retn
```
