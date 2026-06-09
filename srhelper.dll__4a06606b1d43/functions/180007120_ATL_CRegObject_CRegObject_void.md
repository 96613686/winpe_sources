# ATL::CRegObject::~CRegObject(void)

- ea: `0x180007120`
- end: `0x1800071bc`
- name: `??1CRegObject@ATL@@UEAA@XZ`
- size: `156`
- prototype: `void __fastcall(ATL::CRegObject *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180007270`
- `0x180009a6c`
- `0x180009d8c`

## callees

- `0x180007120`
- `0x180007fd0`

## import_xrefs

- `msvcrt!free` at `0x180007181`
- `msvcrt!free` at `0x180007197`
- `msvcrt!free` at `0x180007181`
- `msvcrt!free` at `0x180007197`
- `KERNEL32!LeaveCriticalSection` at `0x180007158`
- `KERNEL32!LeaveCriticalSection` at `0x180007158`
- `KERNEL32!EnterCriticalSection` at `0x180007143`
- `KERNEL32!EnterCriticalSection` at `0x180007143`
- `KERNEL32!DeleteCriticalSection` at `0x18000716b`
- `KERNEL32!DeleteCriticalSection` at `0x18000716b`

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
0x180007120  mov     [rsp+arg_0], rbx
0x180007125  mov     [rsp+arg_8], rsi
0x18000712a  push    rdi
0x18000712b  sub     rsp, 20h
0x18000712f  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x180007136  mov     rbx, rcx
0x180007139  lea     rsi, [rcx+20h]
0x18000713d  mov     [rcx], rax
0x180007140  mov     rcx, rsi; lpCriticalSection
0x180007143  call    cs:__imp_EnterCriticalSection
0x180007149  lea     rdi, [rbx+8]
0x18000714d  mov     rcx, rdi; this
0x180007150  call    ?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ; ATL::CExpansionVector::ClearReplacements(void)
0x180007155  mov     rcx, rsi; lpCriticalSection
0x180007158  call    cs:__imp_LeaveCriticalSection
0x18000715e  cmp     byte ptr [rsi+28h], 0
0x180007162  jz      short loc_180007171
0x180007164  mov     rcx, rsi; lpCriticalSection
0x180007167  mov     byte ptr [rsi+28h], 0
0x18000716b  call    cs:__imp_DeleteCriticalSection
0x180007171  mov     rcx, rdi; this
0x180007174  call    ?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ; ATL::CExpansionVector::ClearReplacements(void)
0x180007179  mov     rcx, [rdi]; Block
0x18000717c  test    rcx, rcx
0x18000717f  jz      short loc_18000718E
0x180007181  call    cs:__imp_free
0x180007187  mov     qword ptr [rdi], 0
0x18000718e  mov     rcx, [rbx+10h]; Block
0x180007192  test    rcx, rcx
0x180007195  jz      short loc_1800071A5
0x180007197  call    cs:__imp_free
0x18000719d  mov     qword ptr [rbx+10h], 0
0x1800071a5  mov     rsi, [rsp+28h+arg_8]
0x1800071aa  mov     dword ptr [rbx+18h], 0
0x1800071b1  mov     rbx, [rsp+28h+arg_0]
0x1800071b6  add     rsp, 20h
0x1800071ba  pop     rdi
0x1800071bb  retn
```
