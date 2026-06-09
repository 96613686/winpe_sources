# ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection(void)

- ea: `0x18000327c`
- end: `0x180003295`
- name: `??1CComSafeDeleteCriticalSection@ATL@@QEAA@XZ`
- size: `25`
- prototype: `void __fastcall(ATL::CComSafeDeleteCriticalSection *__hidden this)`
- caller_count: `33`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180002dd0`
- `0x180002e14`
- `0x180002e58`
- `0x180002ee0`
- `0x180002f68`
- `0x180003018`
- `0x18000305c`
- `0x1800030a0`
- `0x180003124`
- `0x1800031a8`
- `0x18000322c`
- `0x18000324c`
- `0x1800032e0`
- `0x180012128`
- `0x1800161c0`
- `0x1800161f4`
- `0x18001852c`
- `0x18001c690`
- `0x18001d670`
- `0x1800252bc`
- `0x180026468`
- `0x180026878`
- `0x1800271d4`
- `0x1800276a8`
- `0x180027aa4`
- `0x180027e98`
- `0x1800290cc`
- `0x180029950`
- `0x180029d1c`
- `0x18002b86c`
- `0x18002c8e8`
- `0x18002dfd0`
- `0x18002f1a0`

## callees

- `0x18000327c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000328a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000328a`

## pseudocode

```c
void __fastcall ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection(
        ATL::CComSafeDeleteCriticalSection *this)
{
  if ( *((_BYTE *)this + 40) )
  {
    *((_BYTE *)this + 40) = 0;
    DeleteCriticalSection((LPCRITICAL_SECTION)this);
  }
}

```

## disassembly

```asm
0x18000327c  sub     rsp, 28h
0x180003280  cmp     byte ptr [rcx+28h], 0
0x180003284  jz      short loc_180003290
0x180003286  mov     byte ptr [rcx+28h], 0
0x18000328a  call    cs:__imp_DeleteCriticalSection
0x180003290  add     rsp, 28h
0x180003294  retn
```
