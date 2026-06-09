# ErrorRecord::MakeDeepStringCopy(ushort * &,ushort const *,unsigned __int64)

- ea: `0x18001bd14`
- end: `0x18001bda7`
- name: `?MakeDeepStringCopy@ErrorRecord@@CAXAEAPEAGPEBG_K@Z`
- size: `147`
- prototype: `static void(unsigned __int16 **, const unsigned __int16 *, unsigned __int64)`
- caller_count: `4`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18001bac4`
- `0x18001bbbc`
- `0x18001c21c`
- `0x18001c414`

## callees

- `0x18000ac70`
- `0x180013370`
- `0x180013fb6`
- `0x18001bd14`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18001bd38`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001bd38`

## pseudocode

```c
void __fastcall ErrorRecord::MakeDeepStringCopy(unsigned __int16 **a1, const unsigned __int16 *a2, __int64 a3)
{
  void *v6; // rcx
  size_t v7; // rax
  void *v8; // r14

  v6 = *a1;
  if ( v6 )
  {
    operator delete(v6);
    *a1 = 0;
  }
  if ( a2 )
  {
    if ( a3 == -1 )
      a3 = mlib::m_traits<unsigned short>::CStrlen(a2, 1023);
    if ( a3 )
    {
      v7 = 2 * (a3 + 1);
      if ( !is_mul_ok(a3 + 1, 2u) )
        v7 = -1;
      try
      {
        v8 = operator new[](v7);
        memcpy_0(v8, a2, 2 * a3 + 2);
        *a1 = (unsigned __int16 *)v8;
      }
      catch ( mlib::CStringTooBig )
      {
        return;
      }
      catch ( std::bad_alloc )
      {
      }
    }
  }
}

```

## disassembly

```asm
0x18001bd14  push    rbx
0x18001bd16  push    rsi
0x18001bd17  push    rdi
0x18001bd18  push    r14
0x18001bd1a  sub     rsp, 38h
0x18001bd1e  mov     [rsp+58h+var_38], 0FFFFFFFFFFFFFFFEh
0x18001bd27  mov     rbx, r8
0x18001bd2a  mov     rdi, rdx
0x18001bd2d  mov     rsi, rcx
0x18001bd30  mov     rcx, [rcx]
0x18001bd33  test    rcx, rcx
0x18001bd36  jz      short loc_18001BD45
0x18001bd38  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001bd3e  mov     qword ptr [rsi], 0
0x18001bd45  test    rdi, rdi
0x18001bd48  jz      short loc_18001BD9D
0x18001bd4a  or      r14, 0FFFFFFFFFFFFFFFFh
0x18001bd4e  cmp     rbx, r14
0x18001bd51  jnz     short loc_18001BD63
0x18001bd53  mov     edx, 3FFh
0x18001bd58  mov     rcx, rdi
0x18001bd5b  call    ?CStrlen@?$m_traits@G@mlib@@SA_KPEBG_K@Z; mlib::m_traits<ushort>::CStrlen(ushort const *,unsigned __int64)
0x18001bd60  mov     rbx, rax
0x18001bd63  test    rbx, rbx
0x18001bd66  jz      short loc_18001BD9D
0x18001bd68  lea     rcx, [rbx+1]
0x18001bd6c  mov     eax, 2
0x18001bd71  mul     rcx
0x18001bd74  cmovb   rax, r14
0x18001bd78  mov     rcx, rax; unsigned __int64
0x18001bd7b  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18001bd80  mov     r14, rax
0x18001bd83  lea     r8, ds:2[rbx*2]; Size
0x18001bd8b  mov     rdx, rdi; Src
0x18001bd8e  mov     rcx, rax; void *
0x18001bd91  call    memcpy_0
0x18001bd96  mov     [rsi], r14
0x18001bd99  jmp     short loc_18001BD9D
0x18001bd9b  jmp     short $+2
0x18001bd9d  add     rsp, 38h
0x18001bda1  pop     r14
0x18001bda3  pop     rdi
0x18001bda4  pop     rsi
0x18001bda5  pop     rbx
0x18001bda6  retn
```
