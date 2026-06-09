# ATL::CRegObject::~CRegObject(void)

- ea: `0x140001ff4`
- end: `0x140002090`
- name: `??1CRegObject@ATL@@UEAA@XZ`
- size: `156`
- prototype: `void __fastcall(ATL::CRegObject *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x140002160`
- `0x14000550c`
- `0x140005834`

## callees

- `0x140001ff4`
- `0x1400032c0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x140002055`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14000206b`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x140002055`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14000206b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14000202c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14000202c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14000203f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14000203f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140002017`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140002017`

## pseudocode

```c
void __fastcall ATL::CRegObject::~CRegObject(ATL::CRegObject *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // rsi
  void **v3; // rdi
  void *v4; // rcx

  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 32);
  *(_QWORD *)this = &ATL::CRegObject::`vftable';
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  v3 = (void **)((char *)this + 8);
  ATL::CExpansionVector::ClearReplacements((ATL::CRegObject *)((char *)this + 8));
  LeaveCriticalSection(v2);
  if ( LOBYTE(v2[1].DebugInfo) )
  {
    LOBYTE(v2[1].DebugInfo) = 0;
    DeleteCriticalSection(v2);
  }
  ATL::CExpansionVector::ClearReplacements((ATL::CRegObject *)((char *)this + 8));
  if ( *v3 )
  {
    free(*v3);
    *v3 = 0;
  }
  v4 = (void *)*((_QWORD *)this + 2);
  if ( v4 )
  {
    free(v4);
    *((_QWORD *)this + 2) = 0;
  }
  *((_DWORD *)this + 6) = 0;
}

```

## disassembly

```asm
0x140001ff4  mov     [rsp+arg_0], rbx
0x140001ff9  mov     [rsp+arg_8], rsi
0x140001ffe  push    rdi
0x140001fff  sub     rsp, 20h
0x140002003  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x14000200a  mov     rbx, rcx
0x14000200d  lea     rsi, [rcx+20h]
0x140002011  mov     [rcx], rax
0x140002014  mov     rcx, rsi; lpCriticalSection
0x140002017  call    cs:__imp_EnterCriticalSection
0x14000201d  lea     rdi, [rbx+8]
0x140002021  mov     rcx, rdi; this
0x140002024  call    ?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ; ATL::CExpansionVector::ClearReplacements(void)
0x140002029  mov     rcx, rsi; lpCriticalSection
0x14000202c  call    cs:__imp_LeaveCriticalSection
0x140002032  cmp     byte ptr [rsi+28h], 0
0x140002036  jz      short loc_140002045
0x140002038  mov     rcx, rsi; lpCriticalSection
0x14000203b  mov     byte ptr [rsi+28h], 0
0x14000203f  call    cs:__imp_DeleteCriticalSection
0x140002045  mov     rcx, rdi; this
0x140002048  call    ?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ; ATL::CExpansionVector::ClearReplacements(void)
0x14000204d  mov     rcx, [rdi]; Block
0x140002050  test    rcx, rcx
0x140002053  jz      short loc_140002062
0x140002055  call    cs:__imp_free
0x14000205b  mov     qword ptr [rdi], 0
0x140002062  mov     rcx, [rbx+10h]; Block
0x140002066  test    rcx, rcx
0x140002069  jz      short loc_140002079
0x14000206b  call    cs:__imp_free
0x140002071  mov     qword ptr [rbx+10h], 0
0x140002079  mov     rsi, [rsp+28h+arg_8]
0x14000207e  mov     dword ptr [rbx+18h], 0
0x140002085  mov     rbx, [rsp+28h+arg_0]
0x14000208a  add     rsp, 20h
0x14000208e  pop     rdi
0x14000208f  retn
```
