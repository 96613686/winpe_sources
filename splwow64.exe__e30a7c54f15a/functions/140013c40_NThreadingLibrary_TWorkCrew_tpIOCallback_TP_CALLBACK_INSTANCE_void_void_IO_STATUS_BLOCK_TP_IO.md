# NThreadingLibrary::TWorkCrew::tpIOCallback(_TP_CALLBACK_INSTANCE *,void *,void *,_IO_STATUS_BLOCK *,_TP_IO *)

- ea: `0x140013c40`
- end: `0x140013caf`
- name: `?tpIOCallback@TWorkCrew@NThreadingLibrary@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAX1PEAU_IO_STATUS_BLOCK@@PEAU_TP_IO@@@Z`
- size: `111`
- prototype: `void __fastcall(struct _TP_CALLBACK_INSTANCE *, void *, void *, struct _IO_STATUS_BLOCK *, struct _TP_IO *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140013c40`
- `0x140016010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140013c6c`
- `KERNEL32!GetCurrentThreadId` at `0x140013c6c`
- `KERNEL32!EnterCriticalSection` at `0x140013c63`
- `KERNEL32!EnterCriticalSection` at `0x140013c63`
- `KERNEL32!LeaveCriticalSection` at `0x140013c9e`
- `KERNEL32!LeaveCriticalSection` at `0x140013c9e`

## pseudocode

```c
void __fastcall NThreadingLibrary::TWorkCrew::tpIOCallback(
        struct _TP_CALLBACK_INSTANCE *a1,
        _QWORD *a2,
        void *a3,
        struct _IO_STATUS_BLOCK *a4)
{
  __int64 v5; // rbx

  if ( a2 && *((_DWORD *)a2 + 16) == 1953063799 )
  {
    v5 = a2[10];
    EnterCriticalSection((LPCRITICAL_SECTION)(v5 + 40));
    ++*(_DWORD *)(v5 + 84);
    *(_DWORD *)(v5 + 80) = GetCurrentThreadId();
    if ( !*((_DWORD *)a2 + 17) )
      (*(void (__fastcall **)(_QWORD *))(*a2 + 24LL))(a2);
    if ( (*(_DWORD *)(v5 + 84))-- == 1 )
      *(_DWORD *)(v5 + 80) = 0;
    LeaveCriticalSection((LPCRITICAL_SECTION)(v5 + 40));
  }
}

```

## disassembly

```asm
0x140013c40  test    rdx, rdx
0x140013c43  jz      short locret_140013CAE
0x140013c45  mov     [rsp+arg_0], rbx
0x140013c4a  push    rdi
0x140013c4b  sub     rsp, 20h
0x140013c4f  cmp     dword ptr [rdx+40h], 74696377h
0x140013c56  mov     rdi, rdx
0x140013c59  jnz     short loc_140013CA4
0x140013c5b  mov     rbx, [rdx+50h]
0x140013c5f  lea     rcx, [rbx+28h]; lpCriticalSection
0x140013c63  call    cs:__imp_EnterCriticalSection
0x140013c69  inc     dword ptr [rbx+54h]
0x140013c6c  call    cs:__imp_GetCurrentThreadId
0x140013c72  mov     [rbx+50h], eax
0x140013c75  cmp     dword ptr [rdi+44h], 0
0x140013c79  jnz     short loc_140013C8A
0x140013c7b  mov     rax, [rdi]
0x140013c7e  mov     rcx, rdi
0x140013c81  mov     rax, [rax+18h]
0x140013c85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013c8a  add     dword ptr [rbx+54h], 0FFFFFFFFh
0x140013c8e  mov     eax, [rbx+54h]
0x140013c91  jnz     short loc_140013C9A
0x140013c93  mov     dword ptr [rbx+50h], 0
0x140013c9a  lea     rcx, [rbx+28h]; lpCriticalSection
0x140013c9e  call    cs:__imp_LeaveCriticalSection
0x140013ca4  mov     rbx, [rsp+28h+arg_0]
0x140013ca9  add     rsp, 20h
0x140013cad  pop     rdi
0x140013cae  retn
```
