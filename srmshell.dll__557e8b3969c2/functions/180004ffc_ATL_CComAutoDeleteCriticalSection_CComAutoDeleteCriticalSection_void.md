# ATL::CComAutoDeleteCriticalSection::~CComAutoDeleteCriticalSection(void)

- ea: `0x180004ffc`
- end: `0x18000501b`
- name: `??1CComAutoDeleteCriticalSection@ATL@@QEAA@XZ`
- size: `31`
- prototype: `void __fastcall(ATL::CComAutoDeleteCriticalSection *__hidden this)`
- caller_count: `7`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001c061`
- `0x18001c0e7`
- `0x18001c26a`
- `0x18001c7ba`
- `0x18001e564`
- `0x18001e808`
- `0x18001e8fa`

## callees

- `0x180004ffc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000500f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000500f`

## pseudocode

```c
void __fastcall ATL::CComAutoDeleteCriticalSection::~CComAutoDeleteCriticalSection(
        ATL::CComAutoDeleteCriticalSection *this)
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
0x180004ffc  mov     [rsp+arg_0], rcx
0x180005001  sub     rsp, 28h
0x180005005  cmp     byte ptr [rcx+28h], 0
0x180005009  jz      short loc_180005016
0x18000500b  mov     byte ptr [rcx+28h], 0
0x18000500f  call    cs:__imp_DeleteCriticalSection
0x180005015  nop
0x180005016  add     rsp, 28h
0x18000501a  retn
```
