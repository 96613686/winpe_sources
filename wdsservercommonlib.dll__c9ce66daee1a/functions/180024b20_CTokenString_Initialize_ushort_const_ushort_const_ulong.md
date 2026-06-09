# CTokenString::Initialize(ushort const *,ushort const *,ulong)

- ea: `0x180024b20`
- end: `0x180024bd3`
- name: `?Initialize@CTokenString@@QEAAKPEBG0K@Z`
- size: `179`
- prototype: `unsigned int __fastcall(unsigned __int16 **this, const unsigned __int16 *, const unsigned __int16 *, unsigned int)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x18001a440`
- `0x18001c810`

## callees

- `0x180014b10`
- `0x180016450`
- `0x180024b20`
- `0x180024be0`

## import_xrefs

- `msvcrt!iswspace` at `0x180024b91`
- `msvcrt!iswspace` at `0x180024b91`

## pseudocode

```c
__int64 __fastcall CTokenString::Initialize(
        unsigned __int16 **this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        int a4)
{
  unsigned int v8; // ebx
  wint_t *v9; // rax
  wint_t v10; // ax

  CTokenString::Shutdown((CTokenString *)this);
  v8 = DuplicateStringWBom(a2, 0, this);
  if ( !v8 )
  {
    if ( (a4 & 1) != 0 )
      TrimInline(*this);
    v8 = DuplicateStringWBom(a3, 0, this + 1);
    if ( !v8 )
    {
      v9 = *this;
      this[2] = *this;
      if ( (a4 & 2) != 0 )
      {
        while ( 1 )
        {
          v10 = *v9;
          if ( !v10 || !iswspace(v10) )
            break;
          v9 = ++this[2];
        }
      }
      *((_DWORD *)this + 6) = a4;
    }
  }
  return v8;
}

```

## disassembly

```asm
0x180024b20  mov     rax, rsp
0x180024b23  mov     [rax+8], rbx
0x180024b27  mov     [rax+10h], rbp
0x180024b2b  mov     [rax+18h], rsi
0x180024b2f  mov     [rax+20h], rdi
0x180024b33  push    r14
0x180024b35  sub     rsp, 20h
0x180024b39  mov     esi, r9d
0x180024b3c  mov     rbp, r8
0x180024b3f  mov     rbx, rdx
0x180024b42  mov     rdi, rcx
0x180024b45  call    ?Shutdown@CTokenString@@QEAAKXZ; CTokenString::Shutdown(void)
0x180024b4a  mov     r8, rdi; unsigned __int16 **
0x180024b4d  xor     edx, edx; int
0x180024b4f  mov     rcx, rbx; unsigned __int16 *
0x180024b52  call    ?DuplicateStringWBom@@YAKPEBGHPEAPEAG@Z; DuplicateStringWBom(ushort const *,int,ushort * *)
0x180024b57  mov     ebx, eax
0x180024b59  test    eax, eax
0x180024b5b  jnz     short loc_180024BB5
0x180024b5d  test    sil, 1
0x180024b61  jz      short loc_180024B6B
0x180024b63  mov     rcx, [rdi]; unsigned __int16 *
0x180024b66  call    ?TrimInline@@YAXPEAG@Z; TrimInline(ushort *)
0x180024b6b  lea     r8, [rdi+8]; unsigned __int16 **
0x180024b6f  xor     edx, edx; int
0x180024b71  mov     rcx, rbp; unsigned __int16 *
0x180024b74  call    ?DuplicateStringWBom@@YAKPEBGHPEAPEAG@Z; DuplicateStringWBom(ushort const *,int,ushort * *)
0x180024b79  mov     ebx, eax
0x180024b7b  test    eax, eax
0x180024b7d  jnz     short loc_180024BB5
0x180024b7f  mov     rax, [rdi]
0x180024b82  mov     [rdi+10h], rax
0x180024b86  test    sil, 2
0x180024b8a  jz      short loc_180024BB2
0x180024b8c  jmp     short loc_180024BAA
0x180024b8e  movzx   ecx, ax; C
0x180024b91  call    cs:__imp_iswspace
0x180024b98  nop     dword ptr [rax+rax+00h]
0x180024b9d  test    eax, eax
0x180024b9f  jz      short loc_180024BB2
0x180024ba1  add     qword ptr [rdi+10h], 2
0x180024ba6  mov     rax, [rdi+10h]
0x180024baa  movzx   eax, word ptr [rax]
0x180024bad  test    ax, ax
0x180024bb0  jnz     short loc_180024B8E
0x180024bb2  mov     [rdi+18h], esi
0x180024bb5  mov     rbp, [rsp+28h+arg_8]
0x180024bba  mov     eax, ebx
0x180024bbc  mov     rbx, [rsp+28h+arg_0]
0x180024bc1  mov     rsi, [rsp+28h+arg_10]
0x180024bc6  mov     rdi, [rsp+28h+arg_18]
0x180024bcb  add     rsp, 20h
0x180024bcf  pop     r14
0x180024bd1  retn
```
