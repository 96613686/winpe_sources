# STTABLE::Iterate(void (*)(STTABLE_ITEM *,unsigned __int64,int *),unsigned __int64)

- ea: `0x18000c670`
- end: `0x18000c7de`
- name: `?Iterate@STTABLE@@QEAAXP6AXPEAVSTTABLE_ITEM@@_KPEAH@Z1@Z`
- size: `366`
- prototype: `void __fastcall(STTABLE *this, void (*)(struct STTABLE_ITEM *, unsigned __int64, int *), __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000c8f0`
- `0x18000d180`

## callees

- `0x18000c670`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000c7af`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000c7af`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000c6bc`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000c6bc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c7c7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c7c7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c697`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c697`

## pseudocode

```c
void __fastcall STTABLE::Iterate(STTABLE *this, void (*a2)(struct STTABLE_ITEM *, unsigned __int64, int *), __int64 a3)
{
  struct _RTL_CRITICAL_SECTION *v3; // r12
  volatile signed __int32 *v5; // rsi
  __int64 v6; // rbp
  __int64 v7; // rcx
  volatile signed __int32 **v8; // r15
  volatile signed __int32 *v9; // rdi
  volatile signed __int32 **v10; // r13
  volatile signed __int32 *v11; // r14
  volatile signed __int32 **v12; // rcx
  volatile signed __int32 **v13; // rax
  _DWORD *v14; // rcx
  int v15; // eax
  __int64 v17; // [rsp+80h] [rbp+18h] BYREF
  __int64 v18; // [rsp+88h] [rbp+20h]

  v17 = a3;
  v3 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 128);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 128));
  *((_DWORD *)this + 29) = 1;
  v5 = (volatile signed __int32 *)((char *)this + 120);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)this + 30, 0) > 0 )
    WaitForSingleObject(*((HANDLE *)this + 21), 0xFFFFFFFF);
  *v5 = -1;
  v6 = 0;
  v7 = *((_QWORD *)this + 2);
  v18 = v7;
  if ( *((_DWORD *)this + 26) )
  {
    while ( 1 )
    {
      v8 = (volatile signed __int32 **)(*(_QWORD *)(v7 + 8 * v6) + 8LL);
      LODWORD(v17) = 0;
      v9 = *v8;
      if ( *v8 != (volatile signed __int32 *)v8 )
      {
        do
        {
          v10 = *(volatile signed __int32 ***)v9;
          v11 = v9 - 2;
          _InterlockedIncrement(v9 + 4);
          ((void (__fastcall *)(volatile signed __int32 *, _QWORD, __int64 *))a2)(v9 - 2, 0, &v17);
          if ( (_DWORD)v17 )
          {
            v12 = *(volatile signed __int32 ***)v9;
            if ( *(volatile signed __int32 **)(*(_QWORD *)v9 + 8LL) != v9
              || (v13 = (volatile signed __int32 **)*((_QWORD *)v9 + 1), *v13 != v9) )
            {
              __fastfail(3u);
            }
            *v13 = (volatile signed __int32 *)v12;
            v12[1] = (volatile signed __int32 *)v13;
            if ( _InterlockedExchangeAdd(v11 + 6, 0xFFFFFFFF) == 1 && v9 != (volatile signed __int32 *)8 )
              (**(void (__fastcall ***)(volatile signed __int32 *, __int64))v11)(v9 - 2, 1);
          }
          v9 = (volatile signed __int32 *)v10;
        }
        while ( v10 != v8 );
      }
      v6 = (unsigned int)(v6 + 1);
      if ( (unsigned int)v6 >= *((_DWORD *)this + 26) )
        break;
      v7 = v18;
    }
    v14 = (_DWORD *)((char *)this + 120);
  }
  else
  {
    v14 = (_DWORD *)((char *)this + 120);
  }
  v15 = _InterlockedDecrement(v5);
  if ( v15 < 0 )
  {
    *v14 = 0;
    *((_DWORD *)this + 29) = 0;
    LeaveCriticalSection(v3);
  }
  else if ( *((_DWORD *)this + 29) )
  {
    if ( !v15 )
      SetEvent(*((HANDLE *)this + 21));
  }
}

```

## disassembly

```asm
0x18000c670  mov     [rsp+arg_10], r8
0x18000c675  mov     [rsp+arg_8], rdx
0x18000c67a  push    rbx
0x18000c67b  push    rbp
0x18000c67c  push    rsi
0x18000c67d  push    rdi
0x18000c67e  push    r12
0x18000c680  push    r13
0x18000c682  push    r14
0x18000c684  push    r15
0x18000c686  sub     rsp, 28h
0x18000c68a  lea     r12, [rcx+80h]
0x18000c691  mov     rbx, rcx
0x18000c694  mov     rcx, r12; lpCriticalSection
0x18000c697  call    cs:__imp_EnterCriticalSection
0x18000c69d  xor     eax, eax
0x18000c69f  mov     dword ptr [rbx+74h], 1
0x18000c6a6  lea     rsi, [rbx+78h]
0x18000c6aa  lock xadd [rsi], eax
0x18000c6ae  test    eax, eax
0x18000c6b0  jle     short loc_18000C6C2
0x18000c6b2  mov     rcx, [rbx+0A8h]; hHandle
0x18000c6b9  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000c6bc  call    cs:__imp_WaitForSingleObject
0x18000c6c2  mov     dword ptr [rsi], 0FFFFFFFFh
0x18000c6c8  xor     ebp, ebp
0x18000c6ca  mov     rcx, [rbx+10h]
0x18000c6ce  mov     [rsp+68h+arg_18], rcx
0x18000c6d6  cmp     [rbx+68h], ebp
0x18000c6d9  jbe     loc_18000C78F
0x18000c6df  mov     r15, [rcx+rbp*8]
0x18000c6e3  add     r15, 8
0x18000c6e7  mov     dword ptr [rsp+68h+arg_10], 0
0x18000c6f2  mov     rdi, [r15]
0x18000c6f5  cmp     rdi, r15
0x18000c6f8  jz      short loc_18000C76E
0x18000c6fa  mov     r13, [rdi]
0x18000c6fd  lea     r14, [rdi-8]
0x18000c701  lock inc dword ptr [r14+18h]
0x18000c706  mov     rax, [rsp+68h+arg_8]
0x18000c70b  lea     r8, [rsp+68h+arg_10]
0x18000c713  xor     edx, edx
0x18000c715  mov     rcx, r14
0x18000c718  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c71d  cmp     dword ptr [rsp+68h+arg_10], 0
0x18000c725  jz      short loc_18000C766
0x18000c727  mov     rcx, [rdi]
0x18000c72a  cmp     [rcx+8], rdi
0x18000c72e  jnz     short loc_18000C782
0x18000c730  mov     rax, [rdi+8]
0x18000c734  cmp     [rax], rdi
0x18000c737  jnz     short loc_18000C782
0x18000c739  mov     [rax], rcx
0x18000c73c  mov     [rcx+8], rax
0x18000c740  or      eax, 0FFFFFFFFh
0x18000c743  lock xadd [r14+18h], eax
0x18000c749  cmp     eax, 1
0x18000c74c  jnz     short loc_18000C766
0x18000c74e  test    r14, r14
0x18000c751  jz      short loc_18000C766
0x18000c753  mov     rax, [r14]
0x18000c756  mov     edx, 1
0x18000c75b  mov     rcx, r14
0x18000c75e  mov     rax, [rax]
0x18000c761  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c766  mov     rdi, r13
0x18000c769  cmp     r13, r15
0x18000c76c  jnz     short loc_18000C6FA
0x18000c76e  inc     ebp
0x18000c770  cmp     ebp, [rbx+68h]
0x18000c773  jnb     short loc_18000C789
0x18000c775  mov     rcx, [rsp+68h+arg_18]
0x18000c77d  jmp     loc_18000C6DF
0x18000c782  mov     ecx, 3
0x18000c787  int     29h; Win8: RtlFailFast(ecx)
0x18000c789  lea     rcx, [rbx+78h]
0x18000c78d  jmp     short loc_18000C792
0x18000c78f  mov     rcx, rsi
0x18000c792  or      eax, 0FFFFFFFFh
0x18000c795  lock xadd [rsi], eax
0x18000c799  sub     eax, 1
0x18000c79c  js      short loc_18000C7B7
0x18000c79e  cmp     dword ptr [rbx+74h], 0
0x18000c7a2  jz      short loc_18000C7CD
0x18000c7a4  test    eax, eax
0x18000c7a6  jnz     short loc_18000C7CD
0x18000c7a8  mov     rcx, [rbx+0A8h]; hEvent
0x18000c7af  call    cs:__imp_SetEvent
0x18000c7b5  jmp     short loc_18000C7CD
0x18000c7b7  mov     dword ptr [rcx], 0
0x18000c7bd  mov     rcx, r12; lpCriticalSection
0x18000c7c0  mov     dword ptr [rbx+74h], 0
0x18000c7c7  call    cs:__imp_LeaveCriticalSection
0x18000c7cd  add     rsp, 28h
0x18000c7d1  pop     r15
0x18000c7d3  pop     r14
0x18000c7d5  pop     r13
0x18000c7d7  pop     r12
0x18000c7d9  pop     rdi
0x18000c7da  pop     rsi
0x18000c7db  pop     rbp
0x18000c7dc  pop     rbx
0x18000c7dd  retn
```
