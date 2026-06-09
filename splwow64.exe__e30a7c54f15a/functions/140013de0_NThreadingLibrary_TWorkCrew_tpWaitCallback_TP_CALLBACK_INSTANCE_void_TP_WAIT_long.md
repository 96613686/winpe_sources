# NThreadingLibrary::TWorkCrew::tpWaitCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_WAIT *,long)

- ea: `0x140013de0`
- end: `0x140013f12`
- name: `?tpWaitCallback@TWorkCrew@NThreadingLibrary@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z`
- size: `306`
- prototype: `static void(struct _TP_CALLBACK_INSTANCE *, void *, struct _TP_WAIT *, int)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x1400133fc`
- `0x1400139b0`
- `0x140013de0`
- `0x140016010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140013e17`
- `KERNEL32!GetCurrentThreadId` at `0x140013e72`
- `KERNEL32!GetCurrentThreadId` at `0x140013e17`
- `KERNEL32!GetCurrentThreadId` at `0x140013e72`
- `KERNEL32!EnterCriticalSection` at `0x140013e0e`
- `KERNEL32!EnterCriticalSection` at `0x140013e69`
- `KERNEL32!EnterCriticalSection` at `0x140013e0e`
- `KERNEL32!EnterCriticalSection` at `0x140013e69`
- `KERNEL32!LeaveCriticalSection` at `0x140013e42`
- `KERNEL32!LeaveCriticalSection` at `0x140013f01`
- `KERNEL32!LeaveCriticalSection` at `0x140013e42`
- `KERNEL32!LeaveCriticalSection` at `0x140013f01`

## pseudocode

```c
void __fastcall NThreadingLibrary::TWorkCrew::tpWaitCallback(
        struct _TP_CALLBACK_INSTANCE *a1,
        __int64 *a2,
        struct _TP_WAIT *a3,
        int a4)
{
  __int64 v6; // rbx
  __int64 v7; // rsi
  __int64 v9; // rax
  signed __int32 v10; // eax
  signed __int32 v11; // edx

  if ( a2 && *((_DWORD *)a2 + 16) == 1953063799 )
  {
    v6 = a2[10];
    EnterCriticalSection((LPCRITICAL_SECTION)(v6 + 40));
    ++*(_DWORD *)(v6 + 84);
    *(_DWORD *)(v6 + 80) = GetCurrentThreadId();
    if ( !*((_DWORD *)a2 + 17) )
    {
      v7 = a2[10];
      if ( (*(_DWORD *)(v7 + 84))-- == 1 )
        *(_DWORD *)(v7 + 80) = 0;
      LeaveCriticalSection((LPCRITICAL_SECTION)(v7 + 40));
      v9 = *a2;
      if ( a4 == 258 )
        (*(void (__fastcall **)(__int64 *))(v9 + 40))(a2);
      else
        (*(void (__fastcall **)(__int64 *))(v9 + 24))(a2);
      EnterCriticalSection((LPCRITICAL_SECTION)(v7 + 40));
      ++*(_DWORD *)(v7 + 84);
      *(_DWORD *)(v7 + 80) = GetCurrentThreadId();
      if ( !*((_DWORD *)a2 + 17) )
      {
        if ( *((_DWORD *)a2 + 32) )
        {
          if ( *((_DWORD *)a2 + 33) )
            NThreadingLibrary::TWorkCrew::MoveWorkItemToCancelQueue(
              (NThreadingLibrary::TWorkCrew *)a2[10],
              (struct NThreadingLibrary::TWorkItem *)a2);
        }
        else
        {
          do
            v10 = *((_DWORD *)a2 + 2);
          while ( v10 != 0x7FFFFFFF
               && v10 != _InterlockedCompareExchange((volatile signed __int32 *)a2 + 2, v10 + 1, v10) );
          NThreadingLibrary::TWorkCrew::AddItem(
            (NThreadingLibrary::TWorkCrew *)a2[10],
            (struct NThreadingLibrary::TWorkItem *)a2);
          do
            v11 = *((_DWORD *)a2 + 2);
          while ( v11 != 0x7FFFFFFF
               && v11 != _InterlockedCompareExchange((volatile signed __int32 *)a2 + 2, v11 - 1, v11) );
          if ( v11 == 1 )
            (*(void (__fastcall **)(__int64 *))(*a2 + 8))(a2);
        }
      }
    }
    if ( !--*(_DWORD *)(v6 + 84) )
      *(_DWORD *)(v6 + 80) = 0;
    LeaveCriticalSection((LPCRITICAL_SECTION)(v6 + 40));
  }
}

```

## disassembly

```asm
0x140013de0  test    rdx, rdx
0x140013de3  jz      locret_140013F11
0x140013de9  push    rbx
0x140013dea  push    rbp
0x140013deb  push    rsi
0x140013dec  push    rdi
0x140013ded  push    r14
0x140013def  sub     rsp, 20h
0x140013df3  cmp     dword ptr [rdx+40h], 74696377h
0x140013dfa  mov     ebp, r9d
0x140013dfd  mov     rdi, rdx
0x140013e00  jnz     loc_140013F07
0x140013e06  mov     rbx, [rdx+50h]
0x140013e0a  lea     rcx, [rbx+28h]; lpCriticalSection
0x140013e0e  call    cs:__imp_EnterCriticalSection
0x140013e14  inc     dword ptr [rbx+54h]
0x140013e17  call    cs:__imp_GetCurrentThreadId
0x140013e1d  mov     [rbx+50h], eax
0x140013e20  cmp     dword ptr [rdi+44h], 0
0x140013e24  jnz     loc_140013EF0
0x140013e2a  mov     rsi, [rdi+50h]
0x140013e2e  add     dword ptr [rsi+54h], 0FFFFFFFFh
0x140013e32  mov     eax, [rsi+54h]
0x140013e35  jnz     short loc_140013E3E
0x140013e37  mov     dword ptr [rsi+50h], 0
0x140013e3e  lea     rcx, [rsi+28h]; lpCriticalSection
0x140013e42  call    cs:__imp_LeaveCriticalSection
0x140013e48  mov     rax, [rdi]
0x140013e4b  mov     rcx, rdi
0x140013e4e  cmp     ebp, 102h
0x140013e54  jnz     short loc_140013E5C
0x140013e56  mov     rax, [rax+28h]
0x140013e5a  jmp     short loc_140013E60
0x140013e5c  mov     rax, [rax+18h]
0x140013e60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013e65  lea     rcx, [rsi+28h]; lpCriticalSection
0x140013e69  call    cs:__imp_EnterCriticalSection
0x140013e6f  inc     dword ptr [rsi+54h]
0x140013e72  call    cs:__imp_GetCurrentThreadId
0x140013e78  mov     [rsi+50h], eax
0x140013e7b  cmp     dword ptr [rdi+44h], 0
0x140013e7f  jnz     short loc_140013EF0
0x140013e81  cmp     dword ptr [rdi+80h], 0
0x140013e88  jnz     short loc_140013EDB
0x140013e8a  mov     esi, 7FFFFFFFh
0x140013e8f  jmp     short loc_140013E9B
0x140013e91  lea     ecx, [rax+1]
0x140013e94  lock cmpxchg [rdi+8], ecx
0x140013e99  jz      short loc_140013EA2
0x140013e9b  mov     eax, [rdi+8]
0x140013e9e  cmp     eax, esi
0x140013ea0  jnz     short loc_140013E91
0x140013ea2  mov     rcx, [rdi+50h]; this
0x140013ea6  mov     rdx, rdi; struct NThreadingLibrary::TWorkItem *
0x140013ea9  call    ?AddItem@TWorkCrew@NThreadingLibrary@@QEAAJPEAVTWorkItem@2@@Z; NThreadingLibrary::TWorkCrew::AddItem(NThreadingLibrary::TWorkItem *)
0x140013eae  jmp     short loc_140013EBC
0x140013eb0  lea     ecx, [rdx-1]
0x140013eb3  mov     eax, edx
0x140013eb5  lock cmpxchg [rdi+8], ecx
0x140013eba  jz      short loc_140013EC3
0x140013ebc  mov     edx, [rdi+8]
0x140013ebf  cmp     edx, esi
0x140013ec1  jnz     short loc_140013EB0
0x140013ec3  lea     eax, [rdx-1]
0x140013ec6  test    eax, eax
0x140013ec8  jnz     short loc_140013EF0
0x140013eca  mov     rax, [rdi]
0x140013ecd  mov     rcx, rdi
0x140013ed0  mov     rax, [rax+8]
0x140013ed4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013ed9  jmp     short loc_140013EF0
0x140013edb  cmp     dword ptr [rdi+84h], 0
0x140013ee2  jz      short loc_140013EF0
0x140013ee4  mov     rcx, [rdi+50h]; this
0x140013ee8  mov     rdx, rdi; struct NThreadingLibrary::TWorkItem *
0x140013eeb  call    ?MoveWorkItemToCancelQueue@TWorkCrew@NThreadingLibrary@@AEAAJPEAVTWorkItem@2@@Z; NThreadingLibrary::TWorkCrew::MoveWorkItemToCancelQueue(NThreadingLibrary::TWorkItem *)
0x140013ef0  dec     dword ptr [rbx+54h]
0x140013ef3  mov     eax, [rbx+54h]
0x140013ef6  test    eax, eax
0x140013ef8  jnz     short loc_140013EFD
0x140013efa  mov     [rbx+50h], eax
0x140013efd  lea     rcx, [rbx+28h]; lpCriticalSection
0x140013f01  call    cs:__imp_LeaveCriticalSection
0x140013f07  add     rsp, 20h
0x140013f0b  pop     r14
0x140013f0d  pop     rdi
0x140013f0e  pop     rsi
0x140013f0f  pop     rbp
0x140013f10  pop     rbx
0x140013f11  retn
```
