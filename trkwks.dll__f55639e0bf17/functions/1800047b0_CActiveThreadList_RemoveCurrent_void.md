# CActiveThreadList::RemoveCurrent(void)

- ea: `0x1800047b0`
- end: `0x180004843`
- name: `?RemoveCurrent@CActiveThreadList@@QEAAJXZ`
- size: `147`
- prototype: `__int64 __fastcall(CActiveThreadList *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180003c00`
- `0x180003cc4`
- `0x180003d00`

## callees

- `0x1800047b0`
- `0x180010fbe`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800047d1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800047d1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000482d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000482d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800047c2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800047c2`

## pseudocode

```c
__int64 __fastcall CActiveThreadList::RemoveCurrent(CActiveThreadList *this)
{
  CActiveThreadList *v1; // rbx
  int v2; // esi
  struct _RTL_CRITICAL_SECTION *v3; // rdi
  DWORD CurrentThreadId; // ebp
  unsigned int v5; // edx
  unsigned int i; // ecx
  __int64 v7; // r9
  unsigned int v8; // ebx

  v1 = g_pActiveThreadList;
  v2 = 0;
  v3 = (struct _RTL_CRITICAL_SECTION *)((char *)g_pActiveThreadList + 16);
  CurrentThreadId = GetCurrentThreadId();
  EnterCriticalSection(v3);
  v5 = *((_DWORD *)v1 + 1);
  for ( i = 0; i < v5; ++i )
  {
    v7 = *((_QWORD *)v1 + 1);
    if ( *(_DWORD *)(v7 + 4LL * i) == CurrentThreadId )
    {
      *((_DWORD *)v1 + 1) = v5 - 1;
      memcpy_0((void *)(v7 + 4LL * i), (const void *)(v7 + 4LL * (i + 1)), 4LL * (v5 - 1 - i));
      *(_DWORD *)(*((_QWORD *)v1 + 1) + 4LL * *((unsigned int *)v1 + 1)) = 0;
      v2 = 1;
      break;
    }
  }
  v8 = -2147467259;
  if ( v2 )
    v8 = 0;
  LeaveCriticalSection(v3);
  return v8;
}

```

## disassembly

```asm
0x1800047b0  push    rbx
0x1800047b2  push    rbp
0x1800047b3  push    rsi
0x1800047b4  push    rdi
0x1800047b5  sub     rsp, 28h
0x1800047b9  mov     rbx, cs:g_pActiveThreadList
0x1800047c0  xor     esi, esi
0x1800047c2  call    cs:__imp_GetCurrentThreadId
0x1800047c8  lea     rdi, [rbx+10h]
0x1800047cc  mov     ebp, eax
0x1800047ce  mov     rcx, rdi; lpCriticalSection
0x1800047d1  call    cs:__imp_EnterCriticalSection
0x1800047d7  mov     edx, [rbx+4]
0x1800047da  xor     ecx, ecx
0x1800047dc  cmp     ecx, edx
0x1800047de  jnb     short loc_18000481E
0x1800047e0  mov     r9, [rbx+8]
0x1800047e4  lea     r11d, [rcx+1]
0x1800047e8  mov     eax, ecx
0x1800047ea  cmp     [r9+rax*4], ebp
0x1800047ee  lea     r10, [r9+rax*4]
0x1800047f2  jnz     short loc_18000483E
0x1800047f4  lea     eax, [rdx-1]
0x1800047f7  mov     [rbx+4], eax
0x1800047fa  lea     rdx, [r9+r11*4]; Src
0x1800047fe  sub     eax, ecx
0x180004800  mov     rcx, r10; void *
0x180004803  mov     r8d, eax
0x180004806  shl     r8, 2; Size
0x18000480a  call    memcpy_0
0x18000480f  mov     edx, [rbx+4]
0x180004812  mov     rax, [rbx+8]
0x180004816  mov     [rax+rdx*4], esi
0x180004819  mov     esi, 1
0x18000481e  xor     edx, edx
0x180004820  mov     ebx, 80004005h
0x180004825  test    esi, esi
0x180004827  mov     rcx, rdi; lpCriticalSection
0x18000482a  cmovnz  ebx, edx
0x18000482d  call    cs:__imp_LeaveCriticalSection
0x180004833  mov     eax, ebx
0x180004835  add     rsp, 28h
0x180004839  pop     rdi
0x18000483a  pop     rsi
0x18000483b  pop     rbp
0x18000483c  pop     rbx
0x18000483d  retn
0x18000483e  mov     ecx, r11d
0x180004841  jmp     short loc_1800047DC
```
