# WdsObjectFinalize

- ea: `0x1800049a0`
- end: `0x180004b5d`
- name: `WdsObjectFinalize`
- size: `445`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800049a0`
- `0x180030010`

## import_xrefs

- `msvcrt!free` at `0x180004ac5`
- `msvcrt!free` at `0x180004afc`
- `msvcrt!free` at `0x180004b29`
- `msvcrt!free` at `0x180004ac5`
- `msvcrt!free` at `0x180004afc`
- `msvcrt!free` at `0x180004b29`
- `KERNEL32!EnterCriticalSection` at `0x1800049b8`
- `KERNEL32!EnterCriticalSection` at `0x180004a6b`
- `KERNEL32!EnterCriticalSection` at `0x1800049b8`
- `KERNEL32!EnterCriticalSection` at `0x180004a6b`
- `KERNEL32!LeaveCriticalSection` at `0x180004a37`
- `KERNEL32!LeaveCriticalSection` at `0x180004b0b`
- `KERNEL32!LeaveCriticalSection` at `0x180004b3a`
- `KERNEL32!LeaveCriticalSection` at `0x180004a37`
- `KERNEL32!LeaveCriticalSection` at `0x180004b0b`
- `KERNEL32!LeaveCriticalSection` at `0x180004b3a`
- `KERNEL32!DeleteCriticalSection` at `0x180004b1a`
- `KERNEL32!DeleteCriticalSection` at `0x180004b1a`
- `KERNEL32!WaitForSingleObject` at `0x180004a51`
- `KERNEL32!WaitForSingleObject` at `0x180004a51`
- `KERNEL32!CreateEventW` at `0x180004a14`
- `KERNEL32!CreateEventW` at `0x180004a14`
- `KERNEL32!CloseHandle` at `0x180004aec`
- `KERNEL32!CloseHandle` at `0x180004aec`

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
0x1800049a0  mov     [rsp+arg_0], rbx
0x1800049a5  mov     [rsp+arg_8], rsi
0x1800049aa  mov     [rsp+arg_10], rdi
0x1800049af  push    r14
0x1800049b1  sub     rsp, 20h
0x1800049b5  mov     rbx, rcx
0x1800049b8  call    cs:__imp_EnterCriticalSection
0x1800049bf  nop     dword ptr [rax+rax+00h]
0x1800049c4  and     qword ptr [rbx+40h], 0
0x1800049c9  cmp     dword ptr [rbx+38h], 0
0x1800049cd  jnz     loc_180004B37
0x1800049d3  cmp     qword ptr [rbx+28h], 0
0x1800049d8  jz      short loc_180004A34
0x1800049da  xor     edi, edi
0x1800049dc  cmp     [rbx+34h], edi
0x1800049df  jbe     short loc_180004A34
0x1800049e1  mov     rax, [rbx+28h]
0x1800049e5  lea     rcx, [rdi+rdi*2]
0x1800049e9  test    dword ptr [rax+rcx*8], 0FFFFFFFDh
0x1800049f0  jz      short loc_180004A2D
0x1800049f2  cmp     dword ptr [rax+rcx*8], 3
0x1800049f6  jz      short loc_1800049FF
0x1800049f8  mov     dword ptr [rax+rcx*8], 4
0x1800049ff  inc     dword ptr [rbx+38h]
0x180004a02  cmp     dword ptr [rbx+38h], 1
0x180004a06  jnz     short loc_180004A2D
0x180004a08  xor     r9d, r9d; lpName
0x180004a0b  xor     r8d, r8d; bInitialState
0x180004a0e  xor     ecx, ecx; lpEventAttributes
0x180004a10  lea     edx, [r9+1]; bManualReset
0x180004a14  call    cs:__imp_CreateEventW
0x180004a1b  nop     dword ptr [rax+rax+00h]
0x180004a20  mov     [rbx+40h], rax
0x180004a24  test    rax, rax
0x180004a27  jz      loc_180004B37
0x180004a2d  inc     edi
0x180004a2f  cmp     edi, [rbx+34h]
0x180004a32  jb      short loc_1800049E1
0x180004a34  mov     rcx, rbx; lpCriticalSection
0x180004a37  call    cs:__imp_LeaveCriticalSection
0x180004a3e  nop     dword ptr [rax+rax+00h]
0x180004a43  mov     rcx, [rbx+40h]; hHandle
0x180004a47  test    rcx, rcx
0x180004a4a  jz      short loc_180004A68
0x180004a4c  mov     edx, 2710h; dwMilliseconds
0x180004a51  call    cs:__imp_WaitForSingleObject
0x180004a58  nop     dword ptr [rax+rax+00h]
0x180004a5d  cmp     eax, 102h
0x180004a62  jz      loc_180004B46
0x180004a68  mov     rcx, rbx; lpCriticalSection
0x180004a6b  call    cs:__imp_EnterCriticalSection
0x180004a72  nop     dword ptr [rax+rax+00h]
0x180004a77  cmp     qword ptr [rbx+28h], 0
0x180004a7c  jz      loc_180004B08
0x180004a82  xor     edi, edi
0x180004a84  cmp     [rbx+34h], edi
0x180004a87  jbe     short loc_180004AE3
0x180004a89  mov     rax, [rbx+28h]
0x180004a8d  lea     rsi, [rdi+rdi*2]
0x180004a91  test    dword ptr [rax+rsi*8], 0FFFFFFFDh
0x180004a98  jz      short loc_180004ADC
0x180004a9a  mov     rax, [rax+rsi*8+8]
0x180004a9f  dec     dword ptr [rax+8]
0x180004aa2  mov     rax, [rbx+28h]
0x180004aa6  mov     r14, [rax+rsi*8+8]
0x180004aab  cmp     dword ptr [r14+8], 0
0x180004ab0  jnz     short loc_180004AD1
0x180004ab2  mov     rax, [r14]
0x180004ab5  mov     rcx, [r14+10h]
0x180004ab9  mov     rax, [rax+8]
0x180004abd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ac2  mov     rcx, r14; Block
0x180004ac5  call    cs:__imp_free
0x180004acc  nop     dword ptr [rax+rax+00h]
0x180004ad1  mov     rax, [rbx+28h]
0x180004ad5  mov     dword ptr [rax+rsi*8], 2
0x180004adc  inc     edi
0x180004ade  cmp     edi, [rbx+34h]
0x180004ae1  jb      short loc_180004A89
0x180004ae3  mov     rcx, [rbx+40h]; hObject
0x180004ae7  test    rcx, rcx
0x180004aea  jz      short loc_180004AF8
0x180004aec  call    cs:__imp_CloseHandle
0x180004af3  nop     dword ptr [rax+rax+00h]
0x180004af8  mov     rcx, [rbx+28h]; Block
0x180004afc  call    cs:__imp_free
0x180004b03  nop     dword ptr [rax+rax+00h]
0x180004b08  mov     rcx, rbx; lpCriticalSection
0x180004b0b  call    cs:__imp_LeaveCriticalSection
0x180004b12  nop     dword ptr [rax+rax+00h]
0x180004b17  mov     rcx, rbx; lpCriticalSection
0x180004b1a  call    cs:__imp_DeleteCriticalSection
0x180004b21  nop     dword ptr [rax+rax+00h]
0x180004b26  mov     rcx, rbx; Block
0x180004b29  call    cs:__imp_free
0x180004b30  nop     dword ptr [rax+rax+00h]
0x180004b35  jmp     short loc_180004B46
0x180004b37  mov     rcx, rbx; lpCriticalSection
0x180004b3a  call    cs:__imp_LeaveCriticalSection
0x180004b41  nop     dword ptr [rax+rax+00h]
0x180004b46  mov     rbx, [rsp+28h+arg_0]
0x180004b4b  mov     rsi, [rsp+28h+arg_8]
0x180004b50  mov     rdi, [rsp+28h+arg_10]
0x180004b55  add     rsp, 20h
0x180004b59  pop     r14
0x180004b5b  retn
```
