# ATL::CRegObject::~CRegObject(void)

- ea: `0x180008a9c`
- end: `0x180008b38`
- name: `??1CRegObject@ATL@@UEAA@XZ`
- size: `156`
- prototype: `void __fastcall(ATL::CRegObject *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180008df0`
- `0x18000d7ec`
- `0x18000db0c`

## callees

- `0x180008a9c`
- `0x180009d78`

## import_xrefs

- `msvcrt!free` at `0x180008afd`
- `msvcrt!free` at `0x180008b13`
- `msvcrt!free` at `0x180008afd`
- `msvcrt!free` at `0x180008b13`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008ad4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008ad4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008abf`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008abf`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180008ae7`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180008ae7`

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
0x180008a9c  mov     [rsp+arg_0], rbx
0x180008aa1  mov     [rsp+arg_8], rsi
0x180008aa6  push    rdi
0x180008aa7  sub     rsp, 20h
0x180008aab  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x180008ab2  mov     rbx, rcx
0x180008ab5  lea     rsi, [rcx+20h]
0x180008ab9  mov     [rcx], rax
0x180008abc  mov     rcx, rsi; lpCriticalSection
0x180008abf  call    cs:__imp_EnterCriticalSection
0x180008ac5  lea     rdi, [rbx+8]
0x180008ac9  mov     rcx, rdi; this
0x180008acc  call    ?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ; ATL::CExpansionVector::ClearReplacements(void)
0x180008ad1  mov     rcx, rsi; lpCriticalSection
0x180008ad4  call    cs:__imp_LeaveCriticalSection
0x180008ada  cmp     byte ptr [rsi+28h], 0
0x180008ade  jz      short loc_180008AED
0x180008ae0  mov     rcx, rsi; lpCriticalSection
0x180008ae3  mov     byte ptr [rsi+28h], 0
0x180008ae7  call    cs:__imp_DeleteCriticalSection
0x180008aed  mov     rcx, rdi; this
0x180008af0  call    ?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ; ATL::CExpansionVector::ClearReplacements(void)
0x180008af5  mov     rcx, [rdi]; Block
0x180008af8  test    rcx, rcx
0x180008afb  jz      short loc_180008B0A
0x180008afd  call    cs:__imp_free
0x180008b03  mov     qword ptr [rdi], 0
0x180008b0a  mov     rcx, [rbx+10h]; Block
0x180008b0e  test    rcx, rcx
0x180008b11  jz      short loc_180008B21
0x180008b13  call    cs:__imp_free
0x180008b19  mov     qword ptr [rbx+10h], 0
0x180008b21  mov     rsi, [rsp+28h+arg_8]
0x180008b26  mov     dword ptr [rbx+18h], 0
0x180008b2d  mov     rbx, [rsp+28h+arg_0]
0x180008b32  add     rsp, 20h
0x180008b36  pop     rdi
0x180008b37  retn
```
