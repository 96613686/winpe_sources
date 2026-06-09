# ATL::CRegObject::~CRegObject(void)

- ea: `0x180002bcc`
- end: `0x180002c68`
- name: `??1CRegObject@ATL@@UEAA@XZ`
- size: `156`
- prototype: `void __fastcall(ATL::CRegObject *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180002d90`
- `0x1800054fc`
- `0x18000581c`

## callees

- `0x180002bcc`
- `0x180003898`

## import_xrefs

- `msvcrt!free` at `0x180002c2d`
- `msvcrt!free` at `0x180002c43`
- `msvcrt!free` at `0x180002c2d`
- `msvcrt!free` at `0x180002c43`
- `KERNEL32!EnterCriticalSection` at `0x180002bef`
- `KERNEL32!EnterCriticalSection` at `0x180002bef`
- `KERNEL32!DeleteCriticalSection` at `0x180002c17`
- `KERNEL32!DeleteCriticalSection` at `0x180002c17`
- `KERNEL32!LeaveCriticalSection` at `0x180002c04`
- `KERNEL32!LeaveCriticalSection` at `0x180002c04`

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
0x180002bcc  mov     [rsp+arg_0], rbx
0x180002bd1  mov     [rsp+arg_8], rsi
0x180002bd6  push    rdi
0x180002bd7  sub     rsp, 20h
0x180002bdb  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x180002be2  mov     rbx, rcx
0x180002be5  lea     rsi, [rcx+20h]
0x180002be9  mov     [rcx], rax
0x180002bec  mov     rcx, rsi; lpCriticalSection
0x180002bef  call    cs:__imp_EnterCriticalSection
0x180002bf5  lea     rdi, [rbx+8]
0x180002bf9  mov     rcx, rdi; this
0x180002bfc  call    ?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ; ATL::CExpansionVector::ClearReplacements(void)
0x180002c01  mov     rcx, rsi; lpCriticalSection
0x180002c04  call    cs:__imp_LeaveCriticalSection
0x180002c0a  cmp     byte ptr [rsi+28h], 0
0x180002c0e  jz      short loc_180002C1D
0x180002c10  mov     rcx, rsi; lpCriticalSection
0x180002c13  mov     byte ptr [rsi+28h], 0
0x180002c17  call    cs:__imp_DeleteCriticalSection
0x180002c1d  mov     rcx, rdi; this
0x180002c20  call    ?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ; ATL::CExpansionVector::ClearReplacements(void)
0x180002c25  mov     rcx, [rdi]; Block
0x180002c28  test    rcx, rcx
0x180002c2b  jz      short loc_180002C3A
0x180002c2d  call    cs:__imp_free
0x180002c33  mov     qword ptr [rdi], 0
0x180002c3a  mov     rcx, [rbx+10h]; Block
0x180002c3e  test    rcx, rcx
0x180002c41  jz      short loc_180002C51
0x180002c43  call    cs:__imp_free
0x180002c49  mov     qword ptr [rbx+10h], 0
0x180002c51  mov     rsi, [rsp+28h+arg_8]
0x180002c56  mov     dword ptr [rbx+18h], 0
0x180002c5d  mov     rbx, [rsp+28h+arg_0]
0x180002c62  add     rsp, 20h
0x180002c66  pop     rdi
0x180002c67  retn
```
