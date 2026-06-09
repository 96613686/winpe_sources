# CThemeManagerDispatcher::`vector deleting destructor'(uint)

- ea: `0x1800052a0`
- end: `0x18000538c`
- name: `??_ECThemeManagerDispatcher@@UEAAPEAXI@Z`
- size: `236`
- prototype: `char *__fastcall(char *hMem, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callees

- `0x1800052a0`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800052d6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800052e9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800052fc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800052d6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800052e9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800052fc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005364`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005364`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18000537d`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18000537d`
- `ntdll!RtlDeleteCriticalSection` at `0x180005312`
- `ntdll!RtlDeleteCriticalSection` at `0x18000534b`
- `ntdll!RtlDeleteCriticalSection` at `0x180005312`
- `ntdll!RtlDeleteCriticalSection` at `0x18000534b`

## pseudocode

```c
char *__fastcall CThemeManagerDispatcher::`vector deleting destructor'(char *hMem, char a2)
{
  const void *v3; // rcx
  void *v5; // rcx
  void *v6; // rcx
  void *v7; // rcx
  __int64 v8; // rcx
  __int64 v9; // rdi

  *(_QWORD *)hMem = &CAPIDispatcher::`vftable';
  v3 = (const void *)*((_QWORD *)hMem + 3);
  if ( v3 )
  {
    UnmapViewOfFile(v3);
    *((_QWORD *)hMem + 3) = 0;
  }
  v5 = (void *)*((_QWORD *)hMem + 2);
  if ( v5 )
  {
    CloseHandle(v5);
    *((_QWORD *)hMem + 2) = 0;
  }
  v6 = (void *)*((_QWORD *)hMem + 13);
  if ( v6 )
  {
    CloseHandle(v6);
    *((_QWORD *)hMem + 13) = 0;
  }
  v7 = (void *)*((_QWORD *)hMem + 12);
  if ( v7 )
  {
    CloseHandle(v7);
    *((_QWORD *)hMem + 12) = 0;
  }
  if ( *((int *)hMem + 30) >= 0 )
    RtlDeleteCriticalSection((PRTL_CRITICAL_SECTION)(hMem + 128));
  v8 = *((_QWORD *)hMem + 4);
  if ( v8 )
  {
    do
    {
      v9 = *(_QWORD *)(v8 + 8);
      (**(void (__fastcall ***)(__int64, __int64))v8)(v8, 1);
      *((_QWORD *)hMem + 4) = v9;
      v8 = v9;
    }
    while ( v9 );
  }
  if ( *((int *)hMem + 10) >= 0 )
    RtlDeleteCriticalSection((PRTL_CRITICAL_SECTION)(hMem + 48));
  *(_QWORD *)hMem = &CQueueElement::`vftable';
  if ( (a2 & 1) != 0 )
    LocalFree(hMem);
  return hMem;
}

```

## disassembly

```asm
0x1800052a0  mov     [rsp+arg_0], rbx
0x1800052a5  mov     [rsp+arg_8], rsi
0x1800052aa  push    rdi
0x1800052ab  sub     rsp, 20h
0x1800052af  lea     rax, ??_7CAPIDispatcher@@6B@; const CAPIDispatcher::`vftable'
0x1800052b6  mov     rbx, rcx
0x1800052b9  mov     [rcx], rax
0x1800052bc  xor     edi, edi
0x1800052be  mov     rcx, [rcx+18h]; lpBaseAddress
0x1800052c2  mov     esi, edx
0x1800052c4  test    rcx, rcx
0x1800052c7  jnz     loc_18000537D
0x1800052cd  mov     rcx, [rbx+10h]; hObject
0x1800052d1  test    rcx, rcx
0x1800052d4  jz      short loc_1800052E0
0x1800052d6  call    cs:__imp_CloseHandle
0x1800052dc  mov     [rbx+10h], rdi
0x1800052e0  mov     rcx, [rbx+68h]; hObject
0x1800052e4  test    rcx, rcx
0x1800052e7  jz      short loc_1800052F3
0x1800052e9  call    cs:__imp_CloseHandle
0x1800052ef  mov     [rbx+68h], rdi
0x1800052f3  mov     rcx, [rbx+60h]; hObject
0x1800052f7  test    rcx, rcx
0x1800052fa  jz      short loc_180005306
0x1800052fc  call    cs:__imp_CloseHandle
0x180005302  mov     [rbx+60h], rdi
0x180005306  cmp     [rbx+78h], edi
0x180005309  jl      short loc_180005318
0x18000530b  lea     rcx, [rbx+80h]; CriticalSection
0x180005312  call    cs:__imp_RtlDeleteCriticalSection
0x180005318  mov     rcx, [rbx+20h]
0x18000531c  test    rcx, rcx
0x18000531f  jz      short loc_180005341
0x180005321  mov     rax, [rcx]
0x180005324  mov     edx, 1
0x180005329  mov     rdi, [rcx+8]
0x18000532d  mov     rax, [rax]
0x180005330  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005335  mov     [rbx+20h], rdi
0x180005339  mov     rcx, rdi
0x18000533c  test    rdi, rdi
0x18000533f  jnz     short loc_180005321
0x180005341  cmp     dword ptr [rbx+28h], 0
0x180005345  jl      short loc_180005351
0x180005347  lea     rcx, [rbx+30h]; CriticalSection
0x18000534b  call    cs:__imp_RtlDeleteCriticalSection
0x180005351  lea     rax, ??_7CQueueElement@@6B@; const CQueueElement::`vftable'
0x180005358  mov     [rbx], rax
0x18000535b  test    sil, 1
0x18000535f  jz      short loc_18000536A
0x180005361  mov     rcx, rbx; hMem
0x180005364  call    cs:__imp_LocalFree
0x18000536a  mov     rsi, [rsp+28h+arg_8]
0x18000536f  mov     rax, rbx
0x180005372  mov     rbx, [rsp+28h+arg_0]
0x180005377  add     rsp, 20h
0x18000537b  pop     rdi
0x18000537c  retn
0x18000537d  call    cs:__imp_UnmapViewOfFile
0x180005383  mov     [rbx+18h], rdi
0x180005387  jmp     loc_1800052CD
```
