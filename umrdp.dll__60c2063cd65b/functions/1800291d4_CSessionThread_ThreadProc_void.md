# CSessionThread::ThreadProc(void)

- ea: `0x1800291d4`
- end: `0x180029308`
- name: `?ThreadProc@CSessionThread@@AEAAXXZ`
- size: `308`
- prototype: `void __fastcall __noreturn(CSessionThread *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180029310`

## callees

- `0x180007da0`
- `0x18000b3d0`
- `0x18000bd44`
- `0x1800291d4`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800292aa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800292c1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800292aa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800292c1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180029213`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180029213`
- `KERNEL32!FreeLibraryAndExitThread` at `0x180029301`
- `KERNEL32!FreeLibraryAndExitThread` at `0x180029301`

## pseudocode

```c
void __fastcall __noreturn CSessionThread::ThreadProc(HANDLE *this)
{
  int v1; // ebp
  DWORD v2; // r12d
  HMODULE v3; // r15
  CTSCriticalSection *v5; // rbx
  __int64 **v6; // r14
  __int64 *v7; // rsi
  __int64 *v8; // rsi
  _QWORD *v9; // rax
  __int64 v10; // rcx
  HANDLE v11; // rcx
  HANDLE v12; // rcx
  CTSCriticalSection *v13; // [rsp+50h] [rbp+8h] BYREF

  v1 = 0;
  v2 = 0;
  v3 = 0;
  _InterlockedIncrement((volatile signed __int32 *)&g_ulActiveThreads);
  v5 = (CTSCriticalSection *)(this + 9);
  v6 = (__int64 **)(this + 7);
  while ( 1 )
  {
    if ( !*((_DWORD *)this + 28) )
      v2 = WaitForSingleObject(this[13], 0x1D4C0u);
    while ( 1 )
    {
      v13 = v5;
      CTSCriticalSection::Lock(v5);
      v7 = *v6;
      if ( *v6 == (__int64 *)v6 )
      {
        v8 = 0;
      }
      else
      {
        --*((_DWORD *)this + 12);
        v9 = (_QWORD *)v7[1];
        v10 = *v7;
        v8 = v7 - 2;
        *v9 = v10;
        *(_QWORD *)(v10 + 8) = v9;
      }
      CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&v13);
      if ( !v8 )
        break;
      ((void (__fastcall *)(__int64))*v8)(v8[1]);
      operator delete(v8);
    }
    if ( *((_DWORD *)this + 28) || v2 == 258 )
    {
      v13 = v5;
      CTSCriticalSection::Lock(v5);
      if ( *v6 == (__int64 *)v6 )
      {
        v11 = this[13];
        v1 = 1;
        v3 = (HMODULE)this[15];
        this[15] = 0;
        if ( v11 )
        {
          CloseHandle(v11);
          this[13] = 0;
        }
        v12 = this[12];
        if ( v12 )
        {
          CloseHandle(v12);
          this[12] = 0;
        }
      }
      else
      {
        v1 = 0;
      }
      CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&v13);
    }
    if ( v1 )
    {
      (*(void (__fastcall **)(HANDLE))(*(_QWORD *)this[4] + 16LL))(this[4]);
      _InterlockedDecrement((volatile signed __int32 *)&g_ulActiveThreads);
      FreeLibraryAndExitThread(v3, 0);
    }
  }
}

```

## disassembly

```asm
0x1800291d4  mov     [rsp+arg_8], rbx
0x1800291d9  mov     [rsp+arg_10], rbp
0x1800291de  push    rsi
0x1800291df  push    rdi
0x1800291e0  push    r12
0x1800291e2  push    r14
0x1800291e4  push    r15
0x1800291e6  sub     rsp, 20h
0x1800291ea  xor     ebp, ebp
0x1800291ec  xor     r12d, r12d
0x1800291ef  xor     r15d, r15d
0x1800291f2  mov     rdi, rcx
0x1800291f5  lock inc cs:?g_ulActiveThreads@@3KA; ulong g_ulActiveThreads
0x1800291fc  lea     rbx, [rcx+48h]
0x180029200  lea     r14, [rcx+38h]
0x180029204  cmp     dword ptr [rdi+70h], 0
0x180029208  jnz     short loc_18002921C
0x18002920a  mov     rcx, [rdi+68h]; hHandle
0x18002920e  mov     edx, 1D4C0h; dwMilliseconds
0x180029213  call    cs:__imp_WaitForSingleObject
0x180029219  mov     r12d, eax
0x18002921c  mov     rcx, rbx; this
0x18002921f  mov     [rsp+48h+arg_0], rbx
0x180029224  call    ?Lock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::Lock(void)
0x180029229  mov     rsi, [r14]
0x18002922c  cmp     rsi, r14
0x18002922f  jnz     short loc_180029235
0x180029231  xor     esi, esi
0x180029233  jmp     short loc_18002924A
0x180029235  dec     dword ptr [rdi+30h]
0x180029238  mov     rax, [rsi+8]
0x18002923c  mov     rcx, [rsi]
0x18002923f  add     rsi, 0FFFFFFFFFFFFFFF0h
0x180029243  mov     [rax], rcx
0x180029246  mov     [rcx+8], rax
0x18002924a  lea     rcx, [rsp+48h+arg_0]; this
0x18002924f  call    ??1CTSAutoLock@@QEAA@XZ; CTSAutoLock::~CTSAutoLock(void)
0x180029254  test    rsi, rsi
0x180029257  jz      short loc_18002926F
0x180029259  mov     rcx, [rsi+8]
0x18002925d  mov     rax, [rsi]
0x180029260  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029265  mov     rcx, rsi; Block
0x180029268  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002926d  jmp     short loc_18002921C
0x18002926f  cmp     dword ptr [rdi+70h], 0
0x180029273  jnz     short loc_18002927E
0x180029275  cmp     r12d, 102h
0x18002927c  jnz     short loc_1800292DD
0x18002927e  mov     rcx, rbx; this
0x180029281  mov     [rsp+48h+arg_0], rbx
0x180029286  call    ?Lock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::Lock(void)
0x18002928b  cmp     [r14], r14
0x18002928e  jnz     short loc_1800292D1
0x180029290  mov     rcx, [rdi+68h]; hObject
0x180029294  mov     ebp, 1
0x180029299  mov     r15, [rdi+78h]
0x18002929d  mov     qword ptr [rdi+78h], 0
0x1800292a5  test    rcx, rcx
0x1800292a8  jz      short loc_1800292B8
0x1800292aa  call    cs:__imp_CloseHandle
0x1800292b0  mov     qword ptr [rdi+68h], 0
0x1800292b8  mov     rcx, [rdi+60h]; hObject
0x1800292bc  test    rcx, rcx
0x1800292bf  jz      short loc_1800292D3
0x1800292c1  call    cs:__imp_CloseHandle
0x1800292c7  mov     qword ptr [rdi+60h], 0
0x1800292cf  jmp     short loc_1800292D3
0x1800292d1  xor     ebp, ebp
0x1800292d3  lea     rcx, [rsp+48h+arg_0]; this
0x1800292d8  call    ??1CTSAutoLock@@QEAA@XZ; CTSAutoLock::~CTSAutoLock(void)
0x1800292dd  test    ebp, ebp
0x1800292df  jz      loc_180029204
0x1800292e5  mov     rcx, [rdi+20h]
0x1800292e9  mov     rax, [rcx]
0x1800292ec  mov     rax, [rax+10h]
0x1800292f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800292f5  lock dec cs:?g_ulActiveThreads@@3KA; ulong g_ulActiveThreads
0x1800292fc  xor     edx, edx; dwExitCode
0x1800292fe  mov     rcx, r15; hLibModule
0x180029301  call    cs:__imp_FreeLibraryAndExitThread
```
