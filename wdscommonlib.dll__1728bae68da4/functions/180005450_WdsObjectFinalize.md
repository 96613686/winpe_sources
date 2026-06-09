# WdsObjectFinalize

- ea: `0x180005450`
- end: `0x18000560d`
- name: `WdsObjectFinalize`
- size: `445`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180005450`
- `0x180031010`

## import_xrefs

- `msvcrt!free` at `0x180005575`
- `msvcrt!free` at `0x1800055ac`
- `msvcrt!free` at `0x1800055d9`
- `msvcrt!free` at `0x180005575`
- `msvcrt!free` at `0x1800055ac`
- `msvcrt!free` at `0x1800055d9`
- `KERNEL32!EnterCriticalSection` at `0x180005468`
- `KERNEL32!EnterCriticalSection` at `0x18000551b`
- `KERNEL32!EnterCriticalSection` at `0x180005468`
- `KERNEL32!EnterCriticalSection` at `0x18000551b`
- `KERNEL32!LeaveCriticalSection` at `0x1800054e7`
- `KERNEL32!LeaveCriticalSection` at `0x1800055bb`
- `KERNEL32!LeaveCriticalSection` at `0x1800055ea`
- `KERNEL32!LeaveCriticalSection` at `0x1800054e7`
- `KERNEL32!LeaveCriticalSection` at `0x1800055bb`
- `KERNEL32!LeaveCriticalSection` at `0x1800055ea`
- `KERNEL32!DeleteCriticalSection` at `0x1800055ca`
- `KERNEL32!DeleteCriticalSection` at `0x1800055ca`
- `KERNEL32!WaitForSingleObject` at `0x180005501`
- `KERNEL32!WaitForSingleObject` at `0x180005501`
- `KERNEL32!CreateEventW` at `0x1800054c4`
- `KERNEL32!CreateEventW` at `0x1800054c4`
- `KERNEL32!CloseHandle` at `0x18000559c`
- `KERNEL32!CloseHandle` at `0x18000559c`

## pseudocode

```c
void __fastcall WdsObjectFinalize(LPCRITICAL_SECTION lpCriticalSection)
{
  __int64 i; // rdi
  PRTL_CRITICAL_SECTION_DEBUG DebugInfo; // rax
  HANDLE EventW; // rax
  HANDLE LockSemaphore; // rcx
  __int64 j; // rdi
  PRTL_CRITICAL_SECTION_DEBUG v7; // rax
  _DWORD *v8; // r14
  HANDLE v9; // rcx

  EnterCriticalSection(lpCriticalSection);
  lpCriticalSection[1].LockSemaphore = 0;
  if ( LODWORD(lpCriticalSection[1].OwningThread) )
  {
LABEL_23:
    LeaveCriticalSection(lpCriticalSection);
    return;
  }
  if ( lpCriticalSection[1].DebugInfo )
  {
    for ( i = 0; (unsigned int)i < lpCriticalSection[1].RecursionCount; i = (unsigned int)(i + 1) )
    {
      DebugInfo = lpCriticalSection[1].DebugInfo;
      if ( (*((_DWORD *)&DebugInfo->Type + 6 * i) & 0xFFFFFFFD) != 0 )
      {
        if ( *((_DWORD *)&DebugInfo->Type + 6 * i) != 3 )
          *((_DWORD *)&DebugInfo->Type + 6 * i) = 4;
        if ( ++LODWORD(lpCriticalSection[1].OwningThread) == 1 )
        {
          EventW = CreateEventW(0, 1, 0, 0);
          lpCriticalSection[1].LockSemaphore = EventW;
          if ( !EventW )
            goto LABEL_23;
        }
      }
    }
  }
  LeaveCriticalSection(lpCriticalSection);
  LockSemaphore = lpCriticalSection[1].LockSemaphore;
  if ( !LockSemaphore || WaitForSingleObject(LockSemaphore, 0x2710u) != 258 )
  {
    EnterCriticalSection(lpCriticalSection);
    if ( lpCriticalSection[1].DebugInfo )
    {
      for ( j = 0; (unsigned int)j < lpCriticalSection[1].RecursionCount; j = (unsigned int)(j + 1) )
      {
        v7 = lpCriticalSection[1].DebugInfo;
        if ( (*((_DWORD *)&v7->Type + 6 * j) & 0xFFFFFFFD) != 0 )
        {
          --*(_DWORD *)(*((_QWORD *)&v7->CriticalSection + 3 * j) + 8LL);
          v8 = (_DWORD *)*((_QWORD *)&lpCriticalSection[1].DebugInfo->CriticalSection + 3 * j);
          if ( !v8[2] )
          {
            (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v8 + 8LL))(*((_QWORD *)v8 + 2));
            free(v8);
          }
          *((_DWORD *)&lpCriticalSection[1].DebugInfo->Type + 6 * j) = 2;
        }
      }
      v9 = lpCriticalSection[1].LockSemaphore;
      if ( v9 )
        CloseHandle(v9);
      free(lpCriticalSection[1].DebugInfo);
    }
    LeaveCriticalSection(lpCriticalSection);
    DeleteCriticalSection(lpCriticalSection);
    free(lpCriticalSection);
  }
}

```

## disassembly

```asm
0x180005450  mov     [rsp+arg_0], rbx
0x180005455  mov     [rsp+arg_8], rsi
0x18000545a  mov     [rsp+arg_10], rdi
0x18000545f  push    r14
0x180005461  sub     rsp, 20h
0x180005465  mov     rbx, rcx
0x180005468  call    cs:__imp_EnterCriticalSection
0x18000546f  nop     dword ptr [rax+rax+00h]
0x180005474  and     qword ptr [rbx+40h], 0
0x180005479  cmp     dword ptr [rbx+38h], 0
0x18000547d  jnz     loc_1800055E7
0x180005483  cmp     qword ptr [rbx+28h], 0
0x180005488  jz      short loc_1800054E4
0x18000548a  xor     edi, edi
0x18000548c  cmp     [rbx+34h], edi
0x18000548f  jbe     short loc_1800054E4
0x180005491  mov     rax, [rbx+28h]
0x180005495  lea     rcx, [rdi+rdi*2]
0x180005499  test    dword ptr [rax+rcx*8], 0FFFFFFFDh
0x1800054a0  jz      short loc_1800054DD
0x1800054a2  cmp     dword ptr [rax+rcx*8], 3
0x1800054a6  jz      short loc_1800054AF
0x1800054a8  mov     dword ptr [rax+rcx*8], 4
0x1800054af  inc     dword ptr [rbx+38h]
0x1800054b2  cmp     dword ptr [rbx+38h], 1
0x1800054b6  jnz     short loc_1800054DD
0x1800054b8  xor     r9d, r9d; lpName
0x1800054bb  xor     r8d, r8d; bInitialState
0x1800054be  xor     ecx, ecx; lpEventAttributes
0x1800054c0  lea     edx, [r9+1]; bManualReset
0x1800054c4  call    cs:__imp_CreateEventW
0x1800054cb  nop     dword ptr [rax+rax+00h]
0x1800054d0  mov     [rbx+40h], rax
0x1800054d4  test    rax, rax
0x1800054d7  jz      loc_1800055E7
0x1800054dd  inc     edi
0x1800054df  cmp     edi, [rbx+34h]
0x1800054e2  jb      short loc_180005491
0x1800054e4  mov     rcx, rbx; lpCriticalSection
0x1800054e7  call    cs:__imp_LeaveCriticalSection
0x1800054ee  nop     dword ptr [rax+rax+00h]
0x1800054f3  mov     rcx, [rbx+40h]; hHandle
0x1800054f7  test    rcx, rcx
0x1800054fa  jz      short loc_180005518
0x1800054fc  mov     edx, 2710h; dwMilliseconds
0x180005501  call    cs:__imp_WaitForSingleObject
0x180005508  nop     dword ptr [rax+rax+00h]
0x18000550d  cmp     eax, 102h
0x180005512  jz      loc_1800055F6
0x180005518  mov     rcx, rbx; lpCriticalSection
0x18000551b  call    cs:__imp_EnterCriticalSection
0x180005522  nop     dword ptr [rax+rax+00h]
0x180005527  cmp     qword ptr [rbx+28h], 0
0x18000552c  jz      loc_1800055B8
0x180005532  xor     edi, edi
0x180005534  cmp     [rbx+34h], edi
0x180005537  jbe     short loc_180005593
0x180005539  mov     rax, [rbx+28h]
0x18000553d  lea     rsi, [rdi+rdi*2]
0x180005541  test    dword ptr [rax+rsi*8], 0FFFFFFFDh
0x180005548  jz      short loc_18000558C
0x18000554a  mov     rax, [rax+rsi*8+8]
0x18000554f  dec     dword ptr [rax+8]
0x180005552  mov     rax, [rbx+28h]
0x180005556  mov     r14, [rax+rsi*8+8]
0x18000555b  cmp     dword ptr [r14+8], 0
0x180005560  jnz     short loc_180005581
0x180005562  mov     rax, [r14]
0x180005565  mov     rcx, [r14+10h]
0x180005569  mov     rax, [rax+8]
0x18000556d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005572  mov     rcx, r14; Block
0x180005575  call    cs:__imp_free
0x18000557c  nop     dword ptr [rax+rax+00h]
0x180005581  mov     rax, [rbx+28h]
0x180005585  mov     dword ptr [rax+rsi*8], 2
0x18000558c  inc     edi
0x18000558e  cmp     edi, [rbx+34h]
0x180005591  jb      short loc_180005539
0x180005593  mov     rcx, [rbx+40h]; hObject
0x180005597  test    rcx, rcx
0x18000559a  jz      short loc_1800055A8
0x18000559c  call    cs:__imp_CloseHandle
0x1800055a3  nop     dword ptr [rax+rax+00h]
0x1800055a8  mov     rcx, [rbx+28h]; Block
0x1800055ac  call    cs:__imp_free
0x1800055b3  nop     dword ptr [rax+rax+00h]
0x1800055b8  mov     rcx, rbx; lpCriticalSection
0x1800055bb  call    cs:__imp_LeaveCriticalSection
0x1800055c2  nop     dword ptr [rax+rax+00h]
0x1800055c7  mov     rcx, rbx; lpCriticalSection
0x1800055ca  call    cs:__imp_DeleteCriticalSection
0x1800055d1  nop     dword ptr [rax+rax+00h]
0x1800055d6  mov     rcx, rbx; Block
0x1800055d9  call    cs:__imp_free
0x1800055e0  nop     dword ptr [rax+rax+00h]
0x1800055e5  jmp     short loc_1800055F6
0x1800055e7  mov     rcx, rbx; lpCriticalSection
0x1800055ea  call    cs:__imp_LeaveCriticalSection
0x1800055f1  nop     dword ptr [rax+rax+00h]
0x1800055f6  mov     rbx, [rsp+28h+arg_0]
0x1800055fb  mov     rsi, [rsp+28h+arg_8]
0x180005600  mov     rdi, [rsp+28h+arg_10]
0x180005605  add     rsp, 20h
0x180005609  pop     r14
0x18000560b  retn
```
