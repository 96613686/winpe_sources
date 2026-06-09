# CDUIResourceManager::UninitThread(void)

- ea: `0x1800d8578`
- end: `0x1800d862e`
- name: `?UninitThread@CDUIResourceManager@@QEAAXXZ`
- size: `182`
- prototype: `void __fastcall(CDUIResourceManager *__hidden this)`
- caller_count: `5`
- callee_count: `4`
- tags: `file_ops, registry_config`

## callers

- `0x180039940`
- `0x180052470`
- `0x180074e30`
- `0x180085718`
- `0x180091160`

## callees

- `0x18004b1c4`
- `0x1800d8288`
- `0x1800d8578`
- `0x1800d8750`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800d8622`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800d85cf`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800d85cf`
- `api-ms-win-core-processthreads-l1-1-0!TlsFree` at `0x1800d85e4`
- `api-ms-win-core-processthreads-l1-1-0!TlsFree` at `0x1800d85e4`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1800d85b4`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1800d85b4`
- `DUI70!UnInitProcessPriv` at `0x1800d8609`
- `DUI70!UnInitProcessPriv` at `0x1800d8609`
- `DUI70!UnInitThread` at `0x1800d85c0`
- `DUI70!UnInitThread` at `0x1800d85c0`
- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x1800d859b`
- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x1800d859b`

## pseudocode

```c
void __fastcall CDUIResourceManager::UninitThread(DWORD *this)
{
  struct CDUIResourceManager::REFCOUNTEDPARSER *RefCountedParserForThread; // rax
  __int64 v3; // rcx
  struct CDUIResourceManager::REFCOUNTEDPARSER *v4; // rdi
  bool v5; // zf
  unsigned int v6; // edx

  RefCountedParserForThread = CDUIResourceManager::_GetRefCountedParserForThread((CDUIResourceManager *)this);
  v4 = RefCountedParserForThread;
  if ( RefCountedParserForThread )
  {
    v5 = (*((_DWORD *)RefCountedParserForThread + 2))-- == 1;
    if ( v5 )
    {
      DirectUI::DUIXmlParser::Destroy(*(DirectUI::DUIXmlParser **)RefCountedParserForThread);
      CZeroInitNew::operator delete(v4);
      TlsSetValue(this[4], 0);
    }
  }
  UnInitThread(v3);
  AcquireSRWLockExclusive((PSRWLOCK)this);
  v5 = this[3]-- == 1;
  if ( v5 )
  {
    TlsFree(this[4]);
    v6 = this[16];
    this[4] = -1;
    CDUIResourceManager::_UnregisterElements((CDUIResourceManager *)this, v6);
    UnInitProcessPriv(&_ImageBase);
  }
  ReleaseSRWLockExclusive((PSRWLOCK)this);
}

```

## disassembly

```asm
0x1800d8578  mov     [rsp+arg_8], rbx
0x1800d857d  push    rdi
0x1800d857e  sub     rsp, 20h
0x1800d8582  mov     rbx, rcx
0x1800d8585  call    ?_GetRefCountedParserForThread@CDUIResourceManager@@AEBAPEAUREFCOUNTEDPARSER@1@XZ; CDUIResourceManager::_GetRefCountedParserForThread(void)
0x1800d858a  mov     rdi, rax
0x1800d858d  test    rax, rax
0x1800d8590  jz      short loc_1800D85C0
0x1800d8592  sub     dword ptr [rax+8], 1
0x1800d8596  jnz     short loc_1800D85C0
0x1800d8598  mov     rcx, [rax]
0x1800d859b  call    cs:__imp_?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ; DirectUI::DUIXmlParser::Destroy(void)
0x1800d85a2  nop     dword ptr [rax+rax+00h]
0x1800d85a7  mov     rcx, rdi; lpMem
0x1800d85aa  call    ??3CZeroInitNew@@SAXPEAX@Z; CZeroInitNew::operator delete(void *)
0x1800d85af  mov     ecx, [rbx+10h]; dwTlsIndex
0x1800d85b2  xor     edx, edx; lpTlsValue
0x1800d85b4  call    cs:__imp_TlsSetValue
0x1800d85bb  nop     dword ptr [rax+rax+00h]
0x1800d85c0  call    cs:__imp_UnInitThread
0x1800d85c7  nop     dword ptr [rax+rax+00h]
0x1800d85cc  mov     rcx, rbx; SRWLock
0x1800d85cf  call    cs:__imp_AcquireSRWLockExclusive
0x1800d85d6  nop     dword ptr [rax+rax+00h]
0x1800d85db  sub     dword ptr [rbx+0Ch], 1
0x1800d85df  jnz     short loc_1800D8615
0x1800d85e1  mov     ecx, [rbx+10h]; dwTlsIndex
0x1800d85e4  call    cs:__imp_TlsFree
0x1800d85eb  nop     dword ptr [rax+rax+00h]
0x1800d85f0  mov     edx, [rbx+40h]; unsigned int
0x1800d85f3  mov     rcx, rbx; this
0x1800d85f6  mov     dword ptr [rbx+10h], 0FFFFFFFFh
0x1800d85fd  call    ?_UnregisterElements@CDUIResourceManager@@AEAAXI@Z; CDUIResourceManager::_UnregisterElements(uint)
0x1800d8602  lea     rcx, __ImageBase
0x1800d8609  call    cs:__imp_UnInitProcessPriv
0x1800d8610  nop     dword ptr [rax+rax+00h]
0x1800d8615  mov     rcx, rbx
0x1800d8618  mov     rbx, [rsp+28h+arg_8]
0x1800d861d  add     rsp, 20h
0x1800d8621  pop     rdi
0x1800d8622  jmp     cs:__imp_ReleaseSRWLockExclusive
```
