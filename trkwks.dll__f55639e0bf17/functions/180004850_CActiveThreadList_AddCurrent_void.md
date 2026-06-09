# CActiveThreadList::AddCurrent(void)

- ea: `0x180004850`
- end: `0x1800048cc`
- name: `?AddCurrent@CActiveThreadList@@QEAAJXZ`
- size: `124`
- prototype: `__int64 __fastcall(CActiveThreadList *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180003c80`
- `0x180003d00`

## callees

- `0x180004850`
- `0x18000fd48`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000486a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000486a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004892`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004892`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004879`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800048b8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004879`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800048b8`

## pseudocode

```c
__int64 __fastcall CActiveThreadList::AddCurrent(CActiveThreadList *this)
{
  CActiveThreadList *v1; // rbx
  int v2; // esi

  v1 = g_pActiveThreadList;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)g_pActiveThreadList + 16));
  if ( *((_DWORD *)v1 + 1) >= *(_DWORD *)v1 )
  {
    v2 = CActiveThreadList::Grow(v1);
    if ( v2 < 0 )
      goto LABEL_4;
    *(_DWORD *)(*((_QWORD *)v1 + 1) + 4LL * *((unsigned int *)v1 + 1)) = GetCurrentThreadId();
  }
  else
  {
    v2 = 0;
    *(_DWORD *)(*((_QWORD *)v1 + 1) + 4LL * *((unsigned int *)v1 + 1)) = GetCurrentThreadId();
  }
  ++*((_DWORD *)v1 + 1);
LABEL_4:
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v1 + 16));
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180004850  mov     [rsp+arg_0], rbx
0x180004855  mov     [rsp+arg_8], rsi
0x18000485a  push    rdi
0x18000485b  sub     rsp, 20h
0x18000485f  mov     rbx, cs:g_pActiveThreadList
0x180004866  lea     rcx, [rbx+10h]; lpCriticalSection
0x18000486a  call    cs:__imp_EnterCriticalSection
0x180004870  mov     eax, [rbx]
0x180004872  cmp     [rbx+4], eax
0x180004875  jnb     short loc_1800048AA
0x180004877  xor     esi, esi
0x180004879  call    cs:__imp_GetCurrentThreadId
0x18000487f  mov     ecx, [rbx+4]
0x180004882  mov     edx, eax
0x180004884  mov     rax, [rbx+8]
0x180004888  mov     [rax+rcx*4], edx
0x18000488b  inc     dword ptr [rbx+4]
0x18000488e  lea     rcx, [rbx+10h]; lpCriticalSection
0x180004892  call    cs:__imp_LeaveCriticalSection
0x180004898  mov     rbx, [rsp+28h+arg_0]
0x18000489d  mov     eax, esi
0x18000489f  mov     rsi, [rsp+28h+arg_8]
0x1800048a4  add     rsp, 20h
0x1800048a8  pop     rdi
0x1800048a9  retn
0x1800048aa  mov     rcx, rbx; this
0x1800048ad  call    ?Grow@CActiveThreadList@@AEAAJXZ; CActiveThreadList::Grow(void)
0x1800048b2  mov     esi, eax
0x1800048b4  test    eax, eax
0x1800048b6  js      short loc_18000488E
0x1800048b8  call    cs:__imp_GetCurrentThreadId
0x1800048be  mov     r8d, [rbx+4]
0x1800048c2  mov     rdx, [rbx+8]
0x1800048c6  mov     [rdx+r8*4], eax
0x1800048ca  jmp     short loc_18000488B
```
