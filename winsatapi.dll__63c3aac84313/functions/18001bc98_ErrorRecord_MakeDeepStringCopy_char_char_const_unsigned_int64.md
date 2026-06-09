# ErrorRecord::MakeDeepStringCopy(char * &,char const *,unsigned __int64)

- ea: `0x18001bc98`
- end: `0x18001bd0c`
- name: `?MakeDeepStringCopy@ErrorRecord@@CAXAEAPEADPEBD_K@Z`
- size: `116`
- prototype: `static void(char **, const char *, unsigned __int64)`
- caller_count: `4`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18001bac4`
- `0x18001bbbc`
- `0x18001c21c`
- `0x18001c414`

## callees

- `0x180013370`
- `0x180013fb6`
- `0x18001bc5c`
- `0x18001bc98`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18001bcb9`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001bcb9`

## pseudocode

```c
void __fastcall ErrorRecord::MakeDeepStringCopy(char **a1, const char *a2)
{
  void *v4; // rcx
  __int64 v5; // rax
  size_t v6; // rsi
  void *v7; // r14

  v4 = *a1;
  if ( v4 )
  {
    operator delete(v4);
    *a1 = 0;
  }
  if ( a2 )
  {
    v5 = mlib::m_traits<char>::CStrlen(a2, 1023);
    if ( v5 )
    {
      v6 = v5 + 1;
      try
      {
        v7 = operator new[](v5 + 1);
        memcpy_0(v7, a2, v6);
        *a1 = (char *)v7;
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
0x18001bc98  push    rbx
0x18001bc9a  push    rsi
0x18001bc9b  push    rdi
0x18001bc9c  push    r14
0x18001bc9e  sub     rsp, 38h
0x18001bca2  mov     [rsp+58h+var_38], 0FFFFFFFFFFFFFFFEh
0x18001bcab  mov     rbx, rdx
0x18001bcae  mov     rdi, rcx
0x18001bcb1  mov     rcx, [rcx]
0x18001bcb4  test    rcx, rcx
0x18001bcb7  jz      short loc_18001BCC6
0x18001bcb9  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001bcbf  mov     qword ptr [rdi], 0
0x18001bcc6  test    rbx, rbx
0x18001bcc9  jz      short loc_18001BD01
0x18001bccb  mov     edx, 3FFh
0x18001bcd0  mov     rcx, rbx
0x18001bcd3  call    ?CStrlen@?$m_traits@D@mlib@@SA_KPEBD_K@Z; mlib::m_traits<char>::CStrlen(char const *,unsigned __int64)
0x18001bcd8  test    rax, rax
0x18001bcdb  jz      short loc_18001BD01
0x18001bcdd  lea     rsi, [rax+1]
0x18001bce1  mov     rcx, rsi; unsigned __int64
0x18001bce4  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18001bce9  mov     r14, rax
0x18001bcec  mov     r8, rsi; Size
0x18001bcef  mov     rdx, rbx; Src
0x18001bcf2  mov     rcx, rax; void *
0x18001bcf5  call    memcpy_0
0x18001bcfa  mov     [rdi], r14
0x18001bcfd  jmp     short loc_18001BD01
0x18001bcff  jmp     short $+2
0x18001bd01  add     rsp, 38h
0x18001bd05  pop     r14
0x18001bd07  pop     rdi
0x18001bd08  pop     rsi
0x18001bd09  pop     rbx
0x18001bd0a  retn
```
