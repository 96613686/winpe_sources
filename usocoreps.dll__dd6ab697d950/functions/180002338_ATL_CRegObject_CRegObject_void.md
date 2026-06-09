# ATL::CRegObject::~CRegObject(void)

- ea: `0x180002338`
- end: `0x1800023d4`
- name: `??1CRegObject@ATL@@UEAA@XZ`
- size: `156`
- prototype: `void __fastcall(ATL::CRegObject *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180002430`
- `0x1800043ec`
- `0x180004714`

## callees

- `0x180002338`
- `0x180002f58`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180002399`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800023af`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180002399`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800023af`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000235b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000235b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180002383`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180002383`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002370`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002370`

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
0x180002338  mov     [rsp+arg_0], rbx
0x18000233d  mov     [rsp+arg_8], rsi
0x180002342  push    rdi
0x180002343  sub     rsp, 20h
0x180002347  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x18000234e  mov     rbx, rcx
0x180002351  lea     rsi, [rcx+20h]
0x180002355  mov     [rcx], rax
0x180002358  mov     rcx, rsi; lpCriticalSection
0x18000235b  call    cs:__imp_EnterCriticalSection
0x180002361  lea     rdi, [rbx+8]
0x180002365  mov     rcx, rdi; this
0x180002368  call    ?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ; ATL::CExpansionVector::ClearReplacements(void)
0x18000236d  mov     rcx, rsi; lpCriticalSection
0x180002370  call    cs:__imp_LeaveCriticalSection
0x180002376  cmp     byte ptr [rsi+28h], 0
0x18000237a  jz      short loc_180002389
0x18000237c  mov     rcx, rsi; lpCriticalSection
0x18000237f  mov     byte ptr [rsi+28h], 0
0x180002383  call    cs:__imp_DeleteCriticalSection
0x180002389  mov     rcx, rdi; this
0x18000238c  call    ?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ; ATL::CExpansionVector::ClearReplacements(void)
0x180002391  mov     rcx, [rdi]; Block
0x180002394  test    rcx, rcx
0x180002397  jz      short loc_1800023A6
0x180002399  call    cs:__imp_free
0x18000239f  mov     qword ptr [rdi], 0
0x1800023a6  mov     rcx, [rbx+10h]; Block
0x1800023aa  test    rcx, rcx
0x1800023ad  jz      short loc_1800023BD
0x1800023af  call    cs:__imp_free
0x1800023b5  mov     qword ptr [rbx+10h], 0
0x1800023bd  mov     rsi, [rsp+28h+arg_8]
0x1800023c2  mov     dword ptr [rbx+18h], 0
0x1800023c9  mov     rbx, [rsp+28h+arg_0]
0x1800023ce  add     rsp, 20h
0x1800023d2  pop     rdi
0x1800023d3  retn
```
