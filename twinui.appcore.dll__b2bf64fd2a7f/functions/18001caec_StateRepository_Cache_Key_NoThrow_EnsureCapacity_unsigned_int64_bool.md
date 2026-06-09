# StateRepository::Cache::Key_NoThrow::EnsureCapacity(unsigned __int64,bool)

- ea: `0x18001caec`
- end: `0x18001cb89`
- name: `?EnsureCapacity@Key_NoThrow@Cache@StateRepository@@QEAAJ_K_N@Z`
- size: `157`
- prototype: `__int64 __fastcall(StateRepository::Cache::Key_NoThrow *__hidden this, unsigned __int64, bool)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18001c4b4`

## callees

- `0x18001caec`
- `0x18001cc38`
- `0x18002e495`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001cb60`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001cb60`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_AllocStringBuffer` at `0x18001cb0c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_AllocStringBuffer` at `0x18001cb0c`

## string_xrefs

- `0x18001cb1f`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Key.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Key_NoThrow::EnsureCapacity(
        const void **this,
        const void *a2,
        __int64 a3,
        __int64 a4)
{
  void *v6; // rax
  const void *v7; // rsi
  __int64 v9; // rdx
  const void *v10; // rcx
  int v11; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( a2 > this[66] )
  {
    v6 = (void *)SRCache_AllocStringBuffer((unsigned int)a2, a2, a3, a4);
    v7 = v6;
    if ( !v6 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x193,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Key.hpp",
        (const char *)0x8007000ELL,
        v11);
      return 2147942414LL;
    }
    memcpy_0(v6, this[67], 2LL * (_QWORD)this[66]);
    v10 = *this;
    *this = v7;
    if ( v10 )
      SRCache_Free(v10, v9);
    this[67] = *this;
    this[66] = a2;
  }
  return 0;
}

```

## disassembly

```asm
0x18001caec  mov     [rsp+arg_0], rbx
0x18001caf1  mov     [rsp+arg_8], rsi
0x18001caf6  push    rdi; int
0x18001caf7  sub     rsp, 20h
0x18001cafb  mov     rdi, rdx
0x18001cafe  mov     rbx, rcx
0x18001cb01  cmp     rdx, [rcx+210h]
0x18001cb08  jbe     short loc_18001CB77
0x18001cb0a  mov     ecx, edi
0x18001cb0c  call    cs:__imp_SRCache_AllocStringBuffer
0x18001cb12  mov     rsi, rax
0x18001cb15  test    rax, rax
0x18001cb18  jnz     short loc_18001CB3C
0x18001cb1a  mov     rcx, [rsp+28h]; this
0x18001cb1f  lea     r8, aOnecorePrivate; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001cb26  mov     ebx, 8007000Eh
0x18001cb2b  mov     edx, 193h; void *
0x18001cb30  mov     r9d, ebx; char *
0x18001cb33  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001cb38  mov     eax, ebx
0x18001cb3a  jmp     short loc_18001CB79
0x18001cb3c  mov     r8, [rbx+210h]
0x18001cb43  mov     rcx, rsi; void *
0x18001cb46  mov     rdx, [rbx+218h]; Src
0x18001cb4d  add     r8, r8; Size
0x18001cb50  call    memcpy_0
0x18001cb55  mov     rcx, [rbx]
0x18001cb58  mov     [rbx], rsi
0x18001cb5b  test    rcx, rcx
0x18001cb5e  jz      short loc_18001CB66
0x18001cb60  call    cs:__imp_SRCache_Free
0x18001cb66  mov     rax, [rbx]
0x18001cb69  mov     [rbx+218h], rax
0x18001cb70  mov     [rbx+210h], rdi
0x18001cb77  xor     eax, eax
0x18001cb79  mov     rbx, [rsp+28h+arg_0]
0x18001cb7e  mov     rsi, [rsp+28h+arg_8]
0x18001cb83  add     rsp, 20h
0x18001cb87  pop     rdi
0x18001cb88  retn
```
