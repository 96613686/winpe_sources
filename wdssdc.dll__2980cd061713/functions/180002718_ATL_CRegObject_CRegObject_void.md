# ATL::CRegObject::~CRegObject(void)

- ea: `0x180002718`
- end: `0x1800027d3`
- name: `??1CRegObject@ATL@@UEAA@XZ`
- size: `187`
- prototype: `void __fastcall(ATL::CRegObject *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800028e0`
- `0x1800050c8`

## callees

- `0x180002718`
- `0x180003384`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000278b`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800027a7`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000278b`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800027a7`
- `KERNEL32!DeleteCriticalSection` at `0x18000276f`
- `KERNEL32!DeleteCriticalSection` at `0x18000276f`
- `KERNEL32!LeaveCriticalSection` at `0x180002756`
- `KERNEL32!LeaveCriticalSection` at `0x180002756`
- `KERNEL32!EnterCriticalSection` at `0x18000273b`
- `KERNEL32!EnterCriticalSection` at `0x18000273b`

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
0x180002718  mov     [rsp+arg_0], rbx
0x18000271d  mov     [rsp+arg_8], rsi
0x180002722  push    rdi
0x180002723  sub     rsp, 20h
0x180002727  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x18000272e  mov     rbx, rcx
0x180002731  lea     rsi, [rcx+20h]
0x180002735  mov     [rcx], rax
0x180002738  mov     rcx, rsi; lpCriticalSection
0x18000273b  call    cs:__imp_EnterCriticalSection
0x180002742  nop     dword ptr [rax+rax+00h]
0x180002747  lea     rdi, [rbx+8]
0x18000274b  mov     rcx, rdi; this
0x18000274e  call    ?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ; ATL::CExpansionVector::ClearReplacements(void)
0x180002753  mov     rcx, rsi; lpCriticalSection
0x180002756  call    cs:__imp_LeaveCriticalSection
0x18000275d  nop     dword ptr [rax+rax+00h]
0x180002762  cmp     byte ptr [rsi+28h], 0
0x180002766  jz      short loc_18000277B
0x180002768  mov     rcx, rsi; lpCriticalSection
0x18000276b  mov     byte ptr [rsi+28h], 0
0x18000276f  call    cs:__imp_DeleteCriticalSection
0x180002776  nop     dword ptr [rax+rax+00h]
0x18000277b  mov     rcx, rdi; this
0x18000277e  call    ?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ; ATL::CExpansionVector::ClearReplacements(void)
0x180002783  mov     rcx, [rdi]; Block
0x180002786  test    rcx, rcx
0x180002789  jz      short loc_18000279E
0x18000278b  call    cs:__imp_free
0x180002792  nop     dword ptr [rax+rax+00h]
0x180002797  mov     qword ptr [rdi], 0
0x18000279e  mov     rcx, [rbx+10h]; Block
0x1800027a2  test    rcx, rcx
0x1800027a5  jz      short loc_1800027BB
0x1800027a7  call    cs:__imp_free
0x1800027ae  nop     dword ptr [rax+rax+00h]
0x1800027b3  mov     qword ptr [rbx+10h], 0
0x1800027bb  mov     rsi, [rsp+28h+arg_8]
0x1800027c0  mov     dword ptr [rbx+18h], 0
0x1800027c7  mov     rbx, [rsp+28h+arg_0]
0x1800027cc  add     rsp, 20h
0x1800027d0  pop     rdi
0x1800027d1  retn
```
