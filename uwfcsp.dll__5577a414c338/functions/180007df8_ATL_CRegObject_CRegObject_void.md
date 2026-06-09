# ATL::CRegObject::~CRegObject(void)

- ea: `0x180007df8`
- end: `0x180007e94`
- name: `??1CRegObject@ATL@@UEAA@XZ`
- size: `156`
- prototype: `void __fastcall(ATL::CRegObject *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1800082e0`
- `0x18000bb3c`
- `0x18000be5c`

## callees

- `0x180007df8`
- `0x180008cbc`

## import_xrefs

- `msvcrt!free` at `0x180007e59`
- `msvcrt!free` at `0x180007e6f`
- `msvcrt!free` at `0x180007e59`
- `msvcrt!free` at `0x180007e6f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180007e43`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180007e43`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007e30`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007e30`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007e1b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007e1b`

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
0x180007df8  mov     [rsp+arg_0], rbx
0x180007dfd  mov     [rsp+arg_8], rsi
0x180007e02  push    rdi
0x180007e03  sub     rsp, 20h
0x180007e07  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x180007e0e  mov     rbx, rcx
0x180007e11  lea     rsi, [rcx+20h]
0x180007e15  mov     [rcx], rax
0x180007e18  mov     rcx, rsi; lpCriticalSection
0x180007e1b  call    cs:__imp_EnterCriticalSection
0x180007e21  lea     rdi, [rbx+8]
0x180007e25  mov     rcx, rdi; this
0x180007e28  call    ?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ; ATL::CExpansionVector::ClearReplacements(void)
0x180007e2d  mov     rcx, rsi; lpCriticalSection
0x180007e30  call    cs:__imp_LeaveCriticalSection
0x180007e36  cmp     byte ptr [rsi+28h], 0
0x180007e3a  jz      short loc_180007E49
0x180007e3c  mov     rcx, rsi; lpCriticalSection
0x180007e3f  mov     byte ptr [rsi+28h], 0
0x180007e43  call    cs:__imp_DeleteCriticalSection
0x180007e49  mov     rcx, rdi; this
0x180007e4c  call    ?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ; ATL::CExpansionVector::ClearReplacements(void)
0x180007e51  mov     rcx, [rdi]; Block
0x180007e54  test    rcx, rcx
0x180007e57  jz      short loc_180007E66
0x180007e59  call    cs:__imp_free
0x180007e5f  mov     qword ptr [rdi], 0
0x180007e66  mov     rcx, [rbx+10h]; Block
0x180007e6a  test    rcx, rcx
0x180007e6d  jz      short loc_180007E7D
0x180007e6f  call    cs:__imp_free
0x180007e75  mov     qword ptr [rbx+10h], 0
0x180007e7d  mov     rsi, [rsp+28h+arg_8]
0x180007e82  mov     dword ptr [rbx+18h], 0
0x180007e89  mov     rbx, [rsp+28h+arg_0]
0x180007e8e  add     rsp, 20h
0x180007e92  pop     rdi
0x180007e93  retn
```
