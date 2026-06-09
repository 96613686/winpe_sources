# CXmlContentFilter::~CXmlContentFilter(void)

- ea: `0x18000fe98`
- end: `0x18000ff02`
- name: `??1CXmlContentFilter@@QEAA@XZ`
- size: `106`
- prototype: `void __fastcall(CXmlContentFilter *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18000ff10`
- `0x18000ff80`

## callees

- `0x18000fc90`
- `0x18000fe98`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000fef5`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000fef5`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CXmlContentFilter::~CXmlContentFilter(CXmlContentFilter *this)
{
  __int64 v2; // rcx
  __int64 v3; // rcx

  if ( *((_BYTE *)this + 536) )
  {
    v2 = *((_QWORD *)this + 66);
    if ( v2 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v2 + 24LL))(v2, 1);
  }
  CFilterImpContentHandler::~CFilterImpContentHandler((CXmlContentFilter *)((char *)this + 88));
  v3 = *((_QWORD *)this + 10);
  if ( v3 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  if ( *((_BYTE *)this + 72) )
  {
    *((_BYTE *)this + 72) = 0;
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  }
}

```

## disassembly

```asm
0x18000fe98  push    rbx
0x18000fe9a  sub     rsp, 20h
0x18000fe9e  mov     rbx, rcx
0x18000fea1  cmp     byte ptr [rcx+218h], 0
0x18000fea8  jz      short loc_18000FEC7
0x18000feaa  mov     rcx, [rcx+210h]
0x18000feb1  test    rcx, rcx
0x18000feb4  jz      short loc_18000FEC7
0x18000feb6  mov     rax, [rcx]
0x18000feb9  mov     edx, 1
0x18000febe  mov     rax, [rax+18h]
0x18000fec2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fec7  lea     rcx, [rbx+58h]; this
0x18000fecb  call    ??1CFilterImpContentHandler@@QEAA@XZ; CFilterImpContentHandler::~CFilterImpContentHandler(void)
0x18000fed0  nop
0x18000fed1  mov     rcx, [rbx+50h]
0x18000fed5  test    rcx, rcx
0x18000fed8  jz      short loc_18000FEE7
0x18000feda  mov     rax, [rcx]
0x18000fedd  mov     rax, [rax+10h]
0x18000fee1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fee6  nop
0x18000fee7  lea     rcx, [rbx+20h]; lpCriticalSection
0x18000feeb  cmp     byte ptr [rcx+28h], 0
0x18000feef  jz      short loc_18000FEFC
0x18000fef1  mov     byte ptr [rcx+28h], 0
0x18000fef5  call    cs:__imp_DeleteCriticalSection
0x18000fefb  nop
0x18000fefc  add     rsp, 20h
0x18000ff00  pop     rbx
0x18000ff01  retn
```
