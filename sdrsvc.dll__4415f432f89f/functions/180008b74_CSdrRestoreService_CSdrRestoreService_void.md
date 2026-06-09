# CSdrRestoreService::~CSdrRestoreService(void)

- ea: `0x180008b74`
- end: `0x180008bf8`
- name: `??1CSdrRestoreService@@QEAA@XZ`
- size: `132`
- prototype: `void __fastcall(CSdrRestoreService *__hidden this)`
- caller_count: `5`
- callee_count: `3`
- tags: `file_ops, loader_planting, service_task`

## callers

- `0x180008a80`
- `0x180008c80`
- `0x180008d50`
- `0x18000a8fc`
- `0x18000cd90`

## callees

- `0x180001554`
- `0x180008b74`
- `0x180020488`

## import_xrefs

- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x180008bce`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x180008bce`
- `ntdll!RtlFreeHeap` at `0x180008bc4`
- `ntdll!RtlFreeHeap` at `0x180008bc4`

## pseudocode

```c
void __fastcall CSdrRestoreService::~CSdrRestoreService(CSdrRestoreService *this)
{
  union _SLIST_HEADER *v2; // rbx
  PSLIST_ENTRY v3; // rax

  CBsString::_Release((CSdrRestoreService *)((char *)this + 40));
  v2 = (union _SLIST_HEADER *)*((_QWORD *)this + 4);
  if ( v2 )
  {
    *((_QWORD *)this + 4) = 0;
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v2, 0xFFFFFFFF) == 1 )
    {
      while ( 1 )
      {
        v3 = InterlockedPopEntrySList(v2 + 1);
        if ( !v3 )
          break;
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, &v3[-17]);
      }
      operator delete(v2);
    }
  }
  *((_DWORD *)this + 2) = 1129739122;
}

```

## disassembly

```asm
0x180008b74  mov     [rsp+arg_8], rbx
0x180008b79  mov     [rsp+arg_10], rsi
0x180008b7e  push    rdi
0x180008b7f  sub     rsp, 20h
0x180008b83  mov     rdi, rcx
0x180008b86  add     rcx, 28h ; '('; this
0x180008b8a  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x180008b8f  mov     rbx, [rdi+20h]
0x180008b93  test    rbx, rbx
0x180008b96  jz      short loc_180008BE1
0x180008b98  mov     qword ptr [rdi+20h], 0
0x180008ba0  or      eax, 0FFFFFFFFh
0x180008ba3  lock xadd [rbx], eax
0x180008ba7  cmp     eax, 1
0x180008baa  jnz     short loc_180008BE1
0x180008bac  jmp     short loc_180008BCA
0x180008bae  mov     rcx, gs:60h
0x180008bb7  lea     r8, [rax-110h]; P
0x180008bbe  xor     edx, edx; Flags
0x180008bc0  mov     rcx, [rcx+30h]; HeapHandle
0x180008bc4  call    cs:__imp_RtlFreeHeap
0x180008bca  lea     rcx, [rbx+10h]; ListHead
0x180008bce  call    cs:__imp_InterlockedPopEntrySList
0x180008bd4  test    rax, rax
0x180008bd7  jnz     short loc_180008BAE
0x180008bd9  mov     rcx, rbx; Block
0x180008bdc  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180008be1  mov     rbx, [rsp+28h+arg_8]
0x180008be6  mov     rsi, [rsp+28h+arg_10]
0x180008beb  mov     dword ptr [rdi+8], 43567372h
0x180008bf2  add     rsp, 20h
0x180008bf6  pop     rdi
0x180008bf7  retn
```
