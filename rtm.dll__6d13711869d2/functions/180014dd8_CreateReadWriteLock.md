# CreateReadWriteLock

- ea: `0x180014dd8`
- end: `0x180014f8f`
- name: `CreateReadWriteLock`
- size: `439`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180014bfc`
- `0x180014d2c`

## callees

- `0x180014dd8`
- `0x18001f7e8`
- `0x18001f952`
- `0x18001f980`
- `0x180020010`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x180014e26`
- `KERNEL32!HeapAlloc` at `0x180014e26`
- `KERNEL32!HeapFree` at `0x180014ec5`
- `KERNEL32!HeapFree` at `0x180014f21`
- `KERNEL32!HeapFree` at `0x180014ec5`
- `KERNEL32!HeapFree` at `0x180014f21`
- `KERNEL32!InitializeCriticalSection` at `0x180014e91`
- `KERNEL32!InitializeCriticalSection` at `0x180014e91`
- `KERNEL32!GetLastError` at `0x180014e39`
- `KERNEL32!GetLastError` at `0x180014eb1`
- `KERNEL32!GetLastError` at `0x180014f0b`
- `KERNEL32!GetLastError` at `0x180014e39`
- `KERNEL32!GetLastError` at `0x180014eb1`
- `KERNEL32!GetLastError` at `0x180014f0b`
- `KERNEL32!CreateEventA` at `0x180014ea2`
- `KERNEL32!CreateEventA` at `0x180014ea2`

## string_xrefs

- `0x180014e58`: `CreateReadWriteLock failed to allocate lock : %x`
- `0x180014f3b`: `CreateReadWriteLock failed to initialize critical section : %x`
- `0x180014ee3`: `CreateReadWriteLock failed to create event : %x`

## pseudocode

```c
__int64 __fastcall CreateReadWriteLock(_QWORD *a1)
{
  char *v2; // rax
  _QWORD *v3; // rbx
  DWORD v4; // eax
  DWORD LastError; // edi
  HANDLE EventA; // rax
  int v8; // [rsp+30h] [rbp-818h] BYREF
  _BYTE v9[2044]; // [rsp+34h] [rbp-814h] BYREF

  v8 = 0;
  memset_0(v9, 0, sizeof(v9));
  *a1 = 0;
  v2 = (char *)HeapAlloc(hHeap, 0, 0x48u);
  v3 = v2;
  if ( v2 )
  {
    InitializeCriticalSection((LPCRITICAL_SECTION)(v2 + 8));
    EventA = CreateEventA(0, 0, 0, 0);
    v3[7] = EventA;
    if ( EventA )
    {
      *((_DWORD *)v3 + 16) = 0;
      *((_DWORD *)v3 + 12) = 0;
      *v3 = 0;
      *a1 = v3;
      return 0;
    }
    LastError = GetLastError();
    HeapFree(hHeap, 0, v3);
    if ( qword_18002B8A8 )
    {
      LOWORD(v8) = 0;
      FormatRRASErrorString(&v8, L"CreateReadWriteLock failed to create event : %x", LastError);
      goto LABEL_4;
    }
  }
  else
  {
    v4 = GetLastError();
    LastError = v4;
    if ( qword_18002B8A8 )
    {
      LOWORD(v8) = 0;
      FormatRRASErrorString(&v8, L"CreateReadWriteLock failed to allocate lock : %x", v4);
LABEL_4:
      ((void (__fastcall *)(__int64, __int64, int *))gMgmTemplateFunc)(gMgmEtwContext, qword_18002B8A8, &v8);
    }
  }
  return LastError;
}

```

## disassembly

```asm
0x180014dd8  mov     [rsp+arg_8], rbx
0x180014ddd  push    rdi
0x180014dde  sub     rsp, 840h
0x180014de5  mov     rax, cs:__security_cookie
0x180014dec  xor     rax, rsp
0x180014def  mov     [rsp+848h+var_18], rax
0x180014df7  mov     rdi, rcx
0x180014dfa  xor     eax, eax
0x180014dfc  mov     [rsp+848h+var_818], eax
0x180014e00  xor     edx, edx; Val
0x180014e02  mov     r8d, 7FCh; Size
0x180014e08  lea     rcx, [rsp+848h+var_814]; void *
0x180014e0d  call    memset_0
0x180014e12  mov     qword ptr [rdi], 0
0x180014e19  xor     edx, edx; dwFlags
0x180014e1b  lea     r8d, [rdx+48h]; dwBytes
0x180014e1f  mov     rcx, cs:hHeap; hHeap
0x180014e26  call    cs:__imp_HeapAlloc
0x180014e2c  mov     rbx, rax
0x180014e2f  mov     [rsp+848h+lpMem], rax
0x180014e34  test    rax, rax
0x180014e37  jnz     short loc_180014E8D
0x180014e39  call    cs:__imp_GetLastError
0x180014e3f  mov     edi, eax
0x180014e41  cmp     cs:qword_18002B8A8, rbx
0x180014e48  jz      loc_180014F6C
0x180014e4e  xor     ecx, ecx
0x180014e50  mov     word ptr [rsp+848h+var_818], cx
0x180014e55  mov     r8d, eax
0x180014e58  lea     rdx, aCreatereadwrit_1; "CreateReadWriteLock failed to allocate "...
0x180014e5f  lea     rcx, [rsp+848h+var_818]
0x180014e64  call    FormatRRASErrorString
0x180014e69  lea     r8, [rsp+848h+var_818]
0x180014e6e  mov     rdx, cs:qword_18002B8A8
0x180014e75  mov     rcx, cs:gMgmEtwContext
0x180014e7c  mov     rax, cs:gMgmTemplateFunc
0x180014e83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014e88  jmp     loc_180014F6C
0x180014e8d  lea     rcx, [rax+8]; lpCriticalSection
0x180014e91  call    cs:__imp_InitializeCriticalSection
0x180014e97  nop
0x180014e98  xor     r9d, r9d; lpName
0x180014e9b  xor     r8d, r8d; bInitialState
0x180014e9e  xor     edx, edx; bManualReset
0x180014ea0  xor     ecx, ecx; lpEventAttributes
0x180014ea2  call    cs:__imp_CreateEventA
0x180014ea8  mov     [rbx+38h], rax
0x180014eac  test    rax, rax
0x180014eaf  jnz     short loc_180014EEF
0x180014eb1  call    cs:__imp_GetLastError
0x180014eb7  mov     edi, eax
0x180014eb9  mov     r8, rbx; lpMem
0x180014ebc  xor     edx, edx; dwFlags
0x180014ebe  mov     rcx, cs:hHeap; hHeap
0x180014ec5  call    cs:__imp_HeapFree
0x180014ecb  cmp     cs:qword_18002B8A8, 0
0x180014ed3  jz      loc_180014F6C
0x180014ed9  xor     eax, eax
0x180014edb  mov     word ptr [rsp+848h+var_818], ax
0x180014ee0  mov     r8d, edi
0x180014ee3  lea     rdx, aCreatereadwrit; "CreateReadWriteLock failed to create ev"...
0x180014eea  jmp     loc_180014E5F
0x180014eef  mov     dword ptr [rbx+40h], 0
0x180014ef6  mov     dword ptr [rbx+30h], 0
0x180014efd  mov     qword ptr [rbx], 0
0x180014f04  mov     [rdi], rbx
0x180014f07  xor     edi, edi
0x180014f09  jmp     short loc_180014F6C
0x180014f0b  call    cs:__imp_GetLastError
0x180014f11  mov     edi, eax
0x180014f13  mov     r8, [rsp+848h+lpMem]; lpMem
0x180014f18  xor     edx, edx; dwFlags
0x180014f1a  mov     rcx, cs:hHeap; hHeap
0x180014f21  call    cs:__imp_HeapFree
0x180014f27  cmp     cs:qword_18002B8A8, 0
0x180014f2f  jz      short loc_180014F6C
0x180014f31  xor     eax, eax
0x180014f33  mov     word ptr [rsp+848h+var_818], ax
0x180014f38  mov     r8d, edi
0x180014f3b  lea     rdx, aCreatereadwrit_0; "CreateReadWriteLock failed to initializ"...
0x180014f42  lea     rcx, [rsp+848h+var_818]
0x180014f47  call    FormatRRASErrorString
0x180014f4c  lea     r8, [rsp+848h+var_818]
0x180014f51  mov     rdx, cs:qword_18002B8A8
0x180014f58  mov     rcx, cs:gMgmEtwContext
0x180014f5f  mov     rax, cs:gMgmTemplateFunc
0x180014f66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014f6b  nop
0x180014f6c  mov     eax, edi
0x180014f6e  mov     rcx, [rsp+848h+var_18]
0x180014f76  xor     rcx, rsp; StackCookie
0x180014f79  call    __security_check_cookie
0x180014f7e  mov     rbx, [rsp+848h+arg_8]
0x180014f86  add     rsp, 840h
0x180014f8d  pop     rdi
0x180014f8e  retn
```
