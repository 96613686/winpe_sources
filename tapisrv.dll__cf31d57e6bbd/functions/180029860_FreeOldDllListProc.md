# FreeOldDllListProc

- ea: `0x180029860`
- end: `0x180029910`
- name: `FreeOldDllListProc`
- size: `176`
- prototype: `__int64 __fastcall(int *lpThreadParameter)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x180029860`
- `0x18002c8d4`
- `0x180040010`

## import_xrefs

- `KERNEL32!GetCurrentThread` at `0x180029872`
- `KERNEL32!GetCurrentThread` at `0x180029872`
- `KERNEL32!SetThreadPriority` at `0x180029880`
- `KERNEL32!SetThreadPriority` at `0x180029880`
- `KERNEL32!FreeLibrary` at `0x1800298c0`
- `KERNEL32!FreeLibrary` at `0x1800298c0`
- `KERNEL32!Sleep` at `0x18002988d`
- `KERNEL32!Sleep` at `0x18002988d`
- `KERNEL32!LeaveCriticalSection` at `0x1800298f8`
- `KERNEL32!LeaveCriticalSection` at `0x1800298f8`
- `KERNEL32!EnterCriticalSection` at `0x18002989f`
- `KERNEL32!EnterCriticalSection` at `0x18002989f`

## pseudocode

```c
__int64 __fastcall FreeOldDllListProc(int *lpThreadParameter)
{
  HANDLE CurrentThread; // rax
  __int64 v3; // rdi
  __int64 v4; // rbx

  CurrentThread = GetCurrentThread();
  SetThreadPriority(CurrentThread, -2);
  while ( *lpThreadParameter > 0 )
    Sleep(0x64u);
  EnterCriticalSection(&gManagementDllsCritSec);
  v3 = *((_QWORD *)lpThreadParameter + 1);
  if ( v3 )
  {
    do
    {
      if ( *(_QWORD *)v3 )
      {
        (*(void (**)(void))(v3 + 24))();
        FreeLibrary(*(HMODULE *)v3);
      }
      ServerFree(*(LPVOID *)(v3 + 232));
      v4 = *(_QWORD *)(v3 + 248);
      ServerFree((LPVOID)v3);
      v3 = v4;
    }
    while ( v4 );
  }
  ServerFree(lpThreadParameter);
  LeaveCriticalSection(&gManagementDllsCritSec);
  return 0;
}

```

## disassembly

```asm
0x180029860  mov     [rsp+arg_0], rbx
0x180029865  mov     [rsp+arg_8], rsi
0x18002986a  push    rdi
0x18002986b  sub     rsp, 20h
0x18002986f  mov     rsi, rcx
0x180029872  call    cs:__imp_GetCurrentThread
0x180029878  mov     rcx, rax; hThread
0x18002987b  mov     edx, 0FFFFFFFEh; nPriority
0x180029880  call    cs:__imp_SetThreadPriority
0x180029886  jmp     short loc_180029893
0x180029888  mov     ecx, 64h ; 'd'; dwMilliseconds
0x18002988d  call    cs:__imp_Sleep
0x180029893  cmp     dword ptr [rsi], 0
0x180029896  jg      short loc_180029888
0x180029898  lea     rcx, gManagementDllsCritSec; lpCriticalSection
0x18002989f  call    cs:__imp_EnterCriticalSection
0x1800298a5  mov     rdi, [rsi+8]
0x1800298a9  test    rdi, rdi
0x1800298ac  jz      short loc_1800298E9
0x1800298ae  cmp     qword ptr [rdi], 0
0x1800298b2  jz      short loc_1800298C6
0x1800298b4  mov     rax, [rdi+18h]
0x1800298b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800298bd  mov     rcx, [rdi]; hLibModule
0x1800298c0  call    cs:__imp_FreeLibrary
0x1800298c6  mov     rcx, [rdi+0E8h]; lpMem
0x1800298cd  call    ServerFree
0x1800298d2  mov     rbx, [rdi+0F8h]
0x1800298d9  mov     rcx, rdi; lpMem
0x1800298dc  call    ServerFree
0x1800298e1  mov     rdi, rbx
0x1800298e4  test    rbx, rbx
0x1800298e7  jnz     short loc_1800298AE
0x1800298e9  mov     rcx, rsi; lpMem
0x1800298ec  call    ServerFree
0x1800298f1  lea     rcx, gManagementDllsCritSec; lpCriticalSection
0x1800298f8  call    cs:__imp_LeaveCriticalSection
0x1800298fe  mov     rbx, [rsp+28h+arg_0]
0x180029903  xor     eax, eax
0x180029905  mov     rsi, [rsp+28h+arg_8]
0x18002990a  add     rsp, 20h
0x18002990e  pop     rdi
0x18002990f  retn
```
