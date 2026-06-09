# CObjectPathParser::Empty(void)

- ea: `0x1800146fc`
- end: `0x180014745`
- name: `?Empty@CObjectPathParser@@AEAAXXZ`
- size: `73`
- prototype: `void __fastcall(CObjectPathParser *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000e110`
- `0x1800144b0`
- `0x1800147e4`

## callees

- `0x180014588`
- `0x1800146fc`
- `0x180015348`

## import_xrefs

- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18001471d`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180014726`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18001471d`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180014726`

## pseudocode

```c
void __fastcall CObjectPathParser::Empty(CObjectPathParser *this)
{
  void *v1; // rdi
  KeyRef *v3; // rcx

  v1 = (void *)*((_QWORD *)this + 2);
  if ( v1 )
  {
    CGenLexer::~CGenLexer(*((CGenLexer **)this + 2));
    CWin32DefaultArena::WbemMemFree(v1);
  }
  CWin32DefaultArena::WbemMemFree(*(void **)this);
  v3 = (KeyRef *)*((_QWORD *)this + 4);
  if ( v3 )
    KeyRef::`scalar deleting destructor'(v3);
}

```

## disassembly

```asm
0x1800146fc  mov     [rsp+arg_0], rbx
0x180014701  push    rdi
0x180014702  sub     rsp, 20h
0x180014706  mov     rdi, [rcx+10h]
0x18001470a  mov     rbx, rcx
0x18001470d  test    rdi, rdi
0x180014710  jz      short loc_180014723
0x180014712  mov     rcx, rdi; this
0x180014715  call    ??1CGenLexer@@QEAA@XZ; CGenLexer::~CGenLexer(void)
0x18001471a  mov     rcx, rdi
0x18001471d  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180014723  mov     rcx, [rbx]
0x180014726  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18001472c  mov     rcx, [rbx+20h]; this
0x180014730  test    rcx, rcx
0x180014733  jz      short loc_18001473A
0x180014735  call    ??_GKeyRef@@QEAAPEAXI@Z; KeyRef::`scalar deleting destructor'(uint)
0x18001473a  mov     rbx, [rsp+28h+arg_0]
0x18001473f  add     rsp, 20h
0x180014743  pop     rdi
0x180014744  retn
```
