# CRegEventProvider::AddRequest(CRegistryEventRequest *,ulong)

- ea: `0x180008570`
- end: `0x1800086a6`
- name: `?AddRequest@CRegEventProvider@@IEAAJPEAVCRegistryEventRequest@@K@Z`
- size: `310`
- prototype: `__int64 __fastcall(CRegEventProvider *__hidden this, struct CRegistryEventRequest *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180006740`

## callees

- `0x1800082d0`
- `0x180008570`
- `0x180013d88`
- `0x180013f00`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000861b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000861b`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180008683`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180008683`
- `wbemcomn!??ACFlexArray@@QEAAAEAPEAXH@Z` at `0x1800085dd`
- `wbemcomn!??ACFlexArray@@QEAAAEAPEAXH@Z` at `0x1800085dd`
- `wbemcomn!?GetAt@CFlexArray@@QEBAPEAXH@Z` at `0x1800085b1`
- `wbemcomn!?GetAt@CFlexArray@@QEBAPEAXH@Z` at `0x1800085b1`
- `wbemcomn!?InsertAt@CFlexArray@@QEAAHHPEAX@Z` at `0x180008609`
- `wbemcomn!?InsertAt@CFlexArray@@QEAAHHPEAX@Z` at `0x18000863b`
- `wbemcomn!?InsertAt@CFlexArray@@QEAAHHPEAX@Z` at `0x180008609`
- `wbemcomn!?InsertAt@CFlexArray@@QEAAHHPEAX@Z` at `0x18000863b`

## pseudocode

```c
__int64 __fastcall CRegEventProvider::AddRequest(
        CRegEventProvider *this,
        struct CRegistryEventRequest *a2,
        unsigned int a3)
{
  CFlexArray *v7; // rsi
  int v8; // r15d
  int i; // ebp
  char *v10; // rdi
  unsigned int v11; // esi
  __int64 v12; // rbx
  signed int v13; // edi
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+60h] [rbp+8h] BYREF

  if ( !a2 )
    return 2147749889LL;
  v7 = (CRegEventProvider *)((char *)this + 88);
  v8 = *((_DWORD *)this + 22);
  for ( i = 0; ; ++i )
  {
    if ( i >= v8 )
    {
      v13 = CRegistryEventRequest::Activate(a2);
      if ( v13 >= 0 )
      {
        if ( CFlexArray::InsertAt(v7, *(_DWORD *)v7, a2) )
        {
          v13 = -1;
        }
        else
        {
          _InterlockedIncrement((volatile signed __int32 *)a2 + 2);
          v13 = *(_DWORD *)v7 - 1;
          if ( v13 >= 0 )
          {
            if ( !v8 )
              *((_QWORD *)this + 9) = CreateThread(0, 0, CRegEventProvider::Worker, this, 0, (LPDWORD)this + 16);
            return (unsigned int)v13;
          }
        }
        CRegistryEventRequest::Deactivate(a2, a3);
      }
      return (unsigned int)v13;
    }
    v10 = (char *)CFlexArray::GetAt(v7, i);
    if ( (*(unsigned int (__fastcall **)(char *, struct CRegistryEventRequest *))(*(_QWORD *)v10 + 48LL))(v10, a2) )
      break;
  }
  v11 = *((_DWORD *)a2 + 6);
  v12 = *(_QWORD *)CFlexArray::operator[]((char *)a2 + 32, 0);
  CInCritSec::CInCritSec((CInCritSec *)&lpCriticalSection, (struct _RTL_CRITICAL_SECTION *)(v10 + 184));
  if ( *((_DWORD *)v10 + 6) > v11 )
    *((_DWORD *)v10 + 6) = v11;
  CFlexArray::InsertAt((CFlexArray *)(v10 + 32), *((_DWORD *)v10 + 8), (void *)(unsigned int)v12);
  _InterlockedIncrement((volatile signed __int32 *)v10 + 41);
  LeaveCriticalSection(lpCriticalSection);
  return 0;
}

```

## disassembly

```asm
0x180008570  mov     [rsp+arg_8], rbx
0x180008575  mov     [rsp+arg_10], rbp
0x18000857a  push    rsi
0x18000857b  push    rdi
0x18000857c  push    r12
0x18000857e  push    r14
0x180008580  push    r15
0x180008582  sub     rsp, 30h
0x180008586  mov     r12d, r8d
0x180008589  mov     rbx, rdx
0x18000858c  mov     r14, rcx
0x18000858f  test    rdx, rdx
0x180008592  jnz     short loc_18000859E
0x180008594  mov     eax, 80041001h
0x180008599  jmp     loc_18000868F
0x18000859e  lea     rsi, [rcx+58h]
0x1800085a2  mov     r15d, [rsi]
0x1800085a5  xor     ebp, ebp
0x1800085a7  cmp     ebp, r15d
0x1800085aa  jge     short loc_180008625
0x1800085ac  mov     edx, ebp
0x1800085ae  mov     rcx, rsi
0x1800085b1  call    cs:__imp_?GetAt@CFlexArray@@QEBAPEAXH@Z; CFlexArray::GetAt(int)
0x1800085b7  mov     rdi, rax
0x1800085ba  mov     rcx, [rax]
0x1800085bd  mov     rax, [rcx+30h]
0x1800085c1  mov     rdx, rbx
0x1800085c4  mov     rcx, rdi
0x1800085c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800085cc  test    eax, eax
0x1800085ce  jnz     short loc_1800085D4
0x1800085d0  inc     ebp
0x1800085d2  jmp     short loc_1800085A7
0x1800085d4  mov     esi, [rbx+18h]
0x1800085d7  lea     rcx, [rbx+20h]
0x1800085db  xor     edx, edx
0x1800085dd  call    cs:__imp_??ACFlexArray@@QEAAAEAPEAXH@Z; CFlexArray::operator[](int)
0x1800085e3  mov     rbx, [rax]
0x1800085e6  lea     rdx, [rdi+0B8h]; struct _RTL_CRITICAL_SECTION *
0x1800085ed  lea     rcx, [rsp+58h+lpCriticalSection]; this
0x1800085f2  call    ??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; CInCritSec::CInCritSec(_RTL_CRITICAL_SECTION *)
0x1800085f7  nop
0x1800085f8  cmp     [rdi+18h], esi
0x1800085fb  jbe     short loc_180008600
0x1800085fd  mov     [rdi+18h], esi
0x180008600  lea     rcx, [rdi+20h]
0x180008604  mov     r8d, ebx
0x180008607  mov     edx, [rcx]
0x180008609  call    cs:__imp_?InsertAt@CFlexArray@@QEAAHHPEAX@Z; CFlexArray::InsertAt(int,void *)
0x18000860f  lock inc dword ptr [rdi+0A4h]
0x180008616  mov     rcx, [rsp+58h+lpCriticalSection]; lpCriticalSection
0x18000861b  call    cs:__imp_LeaveCriticalSection
0x180008621  xor     eax, eax
0x180008623  jmp     short loc_18000868F
0x180008625  mov     rcx, rbx; this
0x180008628  call    ?Activate@CRegistryEventRequest@@QEAAJXZ; CRegistryEventRequest::Activate(void)
0x18000862d  mov     edi, eax
0x18000862f  test    eax, eax
0x180008631  js      short loc_18000868D
0x180008633  mov     r8, rbx
0x180008636  mov     edx, [rsi]
0x180008638  mov     rcx, rsi
0x18000863b  call    cs:__imp_?InsertAt@CFlexArray@@QEAAHHPEAX@Z; CFlexArray::InsertAt(int,void *)
0x180008641  test    eax, eax
0x180008643  jz      short loc_18000864A
0x180008645  or      edi, 0FFFFFFFFh
0x180008648  jmp     short loc_180008655
0x18000864a  lock inc dword ptr [rbx+8]
0x18000864e  mov     edi, [rsi]
0x180008650  sub     edi, 1
0x180008653  jns     short loc_180008662
0x180008655  mov     edx, r12d; unsigned int
0x180008658  mov     rcx, rbx; this
0x18000865b  call    ?Deactivate@CRegistryEventRequest@@QEAAJK@Z; CRegistryEventRequest::Deactivate(ulong)
0x180008660  jmp     short loc_18000868D
0x180008662  test    r15d, r15d
0x180008665  jnz     short loc_18000868D
0x180008667  lea     rax, [r14+40h]
0x18000866b  mov     [rsp+58h+lpThreadId], rax; lpThreadId
0x180008670  mov     [rsp+58h+dwCreationFlags], r15d; dwCreationFlags
0x180008675  mov     r9, r14; lpParameter
0x180008678  lea     r8, ?Worker@CRegEventProvider@@KAKPEAX@Z; lpStartAddress
0x18000867f  xor     edx, edx; dwStackSize
0x180008681  xor     ecx, ecx; lpThreadAttributes
0x180008683  call    cs:__imp_CreateThread
0x180008689  mov     [r14+48h], rax
0x18000868d  mov     eax, edi
0x18000868f  mov     rbx, [rsp+58h+arg_8]
0x180008694  mov     rbp, [rsp+58h+arg_10]
0x180008699  add     rsp, 30h
0x18000869d  pop     r15
0x18000869f  pop     r14
0x1800086a1  pop     r12
0x1800086a3  pop     rdi
0x1800086a4  pop     rsi
0x1800086a5  retn
```
