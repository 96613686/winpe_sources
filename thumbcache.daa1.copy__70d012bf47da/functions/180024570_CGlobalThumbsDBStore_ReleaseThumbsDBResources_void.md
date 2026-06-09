# CGlobalThumbsDBStore::ReleaseThumbsDBResources(void)

- ea: `0x180024570`
- end: `0x18002460f`
- name: `?ReleaseThumbsDBResources@CGlobalThumbsDBStore@@QEAAJXZ`
- size: `159`
- prototype: `__int64 __fastcall(CGlobalThumbsDBStore *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800244e4`

## callees

- `0x180024570`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800245b2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800245b2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002458c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002458c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800245c0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800245c0`
- `SHELL32!SHChangeNotify` at `0x180024607`
- `SHELL32!SHChangeNotify` at `0x180024607`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CGlobalThumbsDBStore::ReleaseThumbsDBResources(RTL_SRWLOCK *this)
{
  unsigned int v2; // ebp
  PVOID Ptr; // rsi
  PVOID v4; // r14
  int v5; // r15d

  if ( LODWORD(this[5].Ptr) )
  {
    return (unsigned int)-2147467259;
  }
  else
  {
    v2 = 0;
    AcquireSRWLockExclusive(this + 1);
    Ptr = this[2].Ptr;
    this[2].Ptr = 0;
    v4 = this[3].Ptr;
    v5 = (int)this[4].Ptr;
    this[2].Ptr = 0;
    this[3].Ptr = 0;
    this[4].Ptr = 0;
    ReleaseSRWLockExclusive(this + 1);
    if ( v4 && v5 == 1 )
      SHChangeNotify(0x2000, 5u, v4, 0);
    CoTaskMemFree(v4);
    if ( Ptr )
      (*(void (__fastcall **)(PVOID))(*(_QWORD *)Ptr + 16LL))(Ptr);
  }
  return v2;
}

```

## disassembly

```asm
0x180024570  push    rbx
0x180024572  push    rbp
0x180024573  push    rsi
0x180024574  push    rdi
0x180024575  push    r14
0x180024577  push    r15
0x180024579  sub     rsp, 28h
0x18002457d  mov     rdi, rcx
0x180024580  cmp     dword ptr [rcx+28h], 0
0x180024584  jnz     short loc_1800245EB
0x180024586  xor     ebp, ebp
0x180024588  add     rcx, 8; SRWLock
0x18002458c  call    cs:__imp_AcquireSRWLockExclusive
0x180024592  mov     rsi, [rdi+10h]
0x180024596  mov     [rdi+10h], rbp
0x18002459a  mov     r14, [rdi+18h]
0x18002459e  mov     r15d, [rdi+20h]
0x1800245a2  mov     [rdi+10h], rbp
0x1800245a6  mov     [rdi+18h], rbp
0x1800245aa  mov     [rdi+20h], rbp
0x1800245ae  lea     rcx, [rdi+8]; SRWLock
0x1800245b2  call    cs:__imp_ReleaseSRWLockExclusive
0x1800245b8  test    r14, r14
0x1800245bb  jnz     short loc_1800245F2
0x1800245bd  mov     rcx, r14; pv
0x1800245c0  call    cs:__imp_CoTaskMemFree
0x1800245c6  nop
0x1800245c7  test    rsi, rsi
0x1800245ca  jz      short loc_1800245DC
0x1800245cc  mov     rdx, [rsi]
0x1800245cf  mov     rcx, rsi
0x1800245d2  mov     rax, [rdx+10h]
0x1800245d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800245db  nop
0x1800245dc  mov     eax, ebp
0x1800245de  add     rsp, 28h
0x1800245e2  pop     r15
0x1800245e4  pop     r14
0x1800245e6  pop     rdi
0x1800245e7  pop     rsi
0x1800245e8  pop     rbp
0x1800245e9  pop     rbx
0x1800245ea  retn
0x1800245eb  mov     ebp, 80004005h
0x1800245f0  jmp     short loc_1800245DC
0x1800245f2  cmp     r15d, 1
0x1800245f6  jnz     short loc_1800245BD
0x1800245f8  xor     r9d, r9d; dwItem2
0x1800245fb  mov     r8, r14; dwItem1
0x1800245fe  lea     edx, [r15+4]; uFlags
0x180024602  mov     ecx, 2000h; wEventId
0x180024607  call    cs:__imp_SHChangeNotify
0x18002460d  jmp     short loc_1800245BD
```
