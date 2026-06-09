# CToken::`scalar deleting destructor'(uint)

- ea: `0x180008970`
- end: `0x180008a74`
- name: `??_GCToken@@UEAAPEAXI@Z`
- size: `260`
- prototype: `CToken *__fastcall(CToken *this, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800087f0`
- `0x180008970`

## import_xrefs

- `wbemcomn!?Empty@CFlexArray@@QEAAXXZ` at `0x1800089a4`
- `wbemcomn!?Empty@CFlexArray@@QEAAXXZ` at `0x1800089a4`
- `wbemcomn!?GetAt@CFlexArray@@QEBAPEAXH@Z` at `0x180008a48`
- `wbemcomn!?GetAt@CFlexArray@@QEBAPEAXH@Z` at `0x180008a48`
- `wbemcomn!??1CFlexArray@@QEAA@XZ` at `0x1800089e4`
- `wbemcomn!??1CFlexArray@@QEAA@XZ` at `0x1800089e4`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800089bb`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800089d6`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800089f8`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180008a0f`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180008a2c`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180008a61`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800089bb`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800089d6`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800089f8`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180008a0f`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180008a2c`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180008a61`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
CToken *__fastcall CToken::`scalar deleting destructor'(CToken *this, char a2)
{
  int i; // ebx
  char *v5; // rbx
  char *v6; // rcx
  char *v7; // rsi
  char *v8; // rcx
  char *v9; // rcx
  char *v10; // rcx
  TString *v12; // rax
  TString *v13; // rsi

  *(_QWORD *)this = &CToken::`vftable';
  for ( i = 0; i < *((_DWORD *)this + 12); ++i )
  {
    v12 = (TString *)CFlexArray::GetAt((CToken *)((char *)this + 48), i);
    v13 = v12;
    if ( v12 )
    {
      TString::Empty(v12);
      CWin32DefaultArena::WbemMemFree(v13);
    }
  }
  CFlexArray::Empty((CToken *)((char *)this + 48));
  *((_DWORD *)this + 7) = 0;
  v5 = (char *)this + 24;
  v6 = (char *)*((_QWORD *)this + 2);
  if ( v6 != (char *)this + 24 )
    CWin32DefaultArena::WbemMemFree(v6);
  *((_QWORD *)this + 2) = v5;
  *((_DWORD *)this + 11) = 0;
  v7 = (char *)this + 40;
  v8 = (char *)*((_QWORD *)this + 4);
  if ( v8 != (char *)this + 40 )
    CWin32DefaultArena::WbemMemFree(v8);
  *((_QWORD *)this + 4) = v7;
  CFlexArray::~CFlexArray((CToken *)((char *)this + 48));
  *((_DWORD *)this + 11) = 0;
  v9 = (char *)*((_QWORD *)this + 4);
  if ( v9 != v7 )
    CWin32DefaultArena::WbemMemFree(v9);
  *((_QWORD *)this + 4) = v7;
  *((_DWORD *)this + 7) = 0;
  v10 = (char *)*((_QWORD *)this + 2);
  if ( v10 != v5 )
    CWin32DefaultArena::WbemMemFree(v10);
  *((_QWORD *)this + 2) = v5;
  *(_QWORD *)this = &CObject::`vftable';
  if ( (a2 & 1) != 0 )
    CWin32DefaultArena::WbemMemFree(this);
  return this;
}

```

## disassembly

```asm
0x180008970  mov     [rsp+arg_0], rcx
0x180008975  push    rbx
0x180008976  push    rbp
0x180008977  push    rsi
0x180008978  push    rdi
0x180008979  push    r14
0x18000897b  push    r15
0x18000897d  sub     rsp, 28h
0x180008981  mov     r14d, edx
0x180008984  mov     rdi, rcx
0x180008987  lea     rax, ??_7CToken@@6B@; const CToken::`vftable'
0x18000898e  mov     [rcx], rax
0x180008991  xor     r15d, r15d
0x180008994  mov     ebx, r15d
0x180008997  cmp     [rcx+30h], ebx
0x18000899a  jg      loc_180008A42
0x1800089a0  lea     rcx, [rdi+30h]
0x1800089a4  call    cs:__imp_?Empty@CFlexArray@@QEAAXXZ; CFlexArray::Empty(void)
0x1800089aa  mov     [rdi+1Ch], r15d
0x1800089ae  lea     rbx, [rdi+18h]
0x1800089b2  mov     rcx, [rdi+10h]
0x1800089b6  cmp     rcx, rbx
0x1800089b9  jz      short loc_1800089C1
0x1800089bb  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x1800089c1  mov     [rdi+10h], rbx
0x1800089c5  mov     [rdi+2Ch], r15d
0x1800089c9  lea     rsi, [rdi+28h]
0x1800089cd  mov     rcx, [rdi+20h]
0x1800089d1  cmp     rcx, rsi
0x1800089d4  jz      short loc_1800089DC
0x1800089d6  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x1800089dc  mov     [rdi+20h], rsi
0x1800089e0  lea     rcx, [rdi+30h]
0x1800089e4  call    cs:__imp_??1CFlexArray@@QEAA@XZ; CFlexArray::~CFlexArray(void)
0x1800089ea  nop
0x1800089eb  mov     [rdi+2Ch], r15d
0x1800089ef  mov     rcx, [rdi+20h]
0x1800089f3  cmp     rcx, rsi
0x1800089f6  jz      short loc_1800089FE
0x1800089f8  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x1800089fe  mov     [rdi+20h], rsi
0x180008a02  mov     [rdi+1Ch], r15d
0x180008a06  mov     rcx, [rdi+10h]
0x180008a0a  cmp     rcx, rbx
0x180008a0d  jz      short loc_180008A15
0x180008a0f  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180008a15  mov     [rdi+10h], rbx
0x180008a19  lea     rax, ??_7CObject@@6B@; const CObject::`vftable'
0x180008a20  mov     [rdi], rax
0x180008a23  test    r14b, 1
0x180008a27  jz      short loc_180008A32
0x180008a29  mov     rcx, rdi
0x180008a2c  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180008a32  mov     rax, rdi
0x180008a35  add     rsp, 28h
0x180008a39  pop     r15
0x180008a3b  pop     r14
0x180008a3d  pop     rdi
0x180008a3e  pop     rsi
0x180008a3f  pop     rbp
0x180008a40  pop     rbx
0x180008a41  retn
0x180008a42  mov     edx, ebx
0x180008a44  lea     rcx, [rdi+30h]
0x180008a48  call    cs:__imp_?GetAt@CFlexArray@@QEBAPEAXH@Z; CFlexArray::GetAt(int)
0x180008a4e  mov     rsi, rax
0x180008a51  test    rax, rax
0x180008a54  jz      short loc_180008A67
0x180008a56  mov     rcx, rax; this
0x180008a59  call    ?Empty@TString@@QEAAXXZ; TString::Empty(void)
0x180008a5e  mov     rcx, rsi
0x180008a61  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180008a67  inc     ebx
0x180008a69  cmp     ebx, [rdi+30h]
0x180008a6c  jl      short loc_180008A42
0x180008a6e  jmp     loc_1800089A0
```
