# WTL::CString::AssignCopy(int,ushort const *)

- ea: `0x180004a78`
- end: `0x180004ae6`
- name: `?AssignCopy@CString@WTL@@IEAAXHPEBG@Z`
- size: `110`
- prototype: `void __fastcall(WTL::CString *__hidden this, int, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x1800036fc`
- `0x18000d1d0`

## callees

- `0x1800048d4`
- `0x180004a78`
- `0x180004c00`
- `0x18000b810`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180004ac1`
- `msvcrt!memcpy_s` at `0x180004ac1`

## pseudocode

```c
void __fastcall WTL::CString::AssignCopy(void **this, int a2, const unsigned __int16 *a3)
{
  __int64 v4; // rsi
  errno_t v6; // eax

  v4 = a2;
  if ( *((int *)*this - 3) <= 1 && a2 <= *((_DWORD *)*this - 1)
    || (WTL::CString::Release((WTL::CString *)this), (unsigned int)WTL::CString::AllocBuffer((WTL::CString *)this, v4)) )
  {
    v6 = memcpy_s(*this, 2LL * ((int)v4 + 1), a3, 2 * v4);
    ATL::AtlCrtErrorCheck(v6);
    *((_DWORD *)*this - 2) = v4;
    *((_WORD *)*this + v4) = 0;
  }
}

```

## disassembly

```asm
0x180004a78  push    rbx
0x180004a7a  push    rbp
0x180004a7b  push    rsi
0x180004a7c  push    rdi
0x180004a7d  sub     rsp, 28h
0x180004a81  mov     rax, [rcx]
0x180004a84  mov     rbp, r8
0x180004a87  movsxd  rsi, edx
0x180004a8a  mov     rdi, rcx
0x180004a8d  cmp     dword ptr [rax-0Ch], 1
0x180004a91  jg      short loc_180004A98
0x180004a93  cmp     esi, [rax-4]
0x180004a96  jle     short loc_180004AAB
0x180004a98  call    ?Release@CString@WTL@@IEAAXXZ; WTL::CString::Release(void)
0x180004a9d  mov     edx, esi; int
0x180004a9f  mov     rcx, rdi; this
0x180004aa2  call    ?AllocBuffer@CString@WTL@@IEAAHH@Z; WTL::CString::AllocBuffer(int)
0x180004aa7  test    eax, eax
0x180004aa9  jz      short loc_180004ADD
0x180004aab  mov     rcx, [rdi]; Destination
0x180004aae  lea     eax, [rsi+1]
0x180004ab1  movsxd  rdx, eax
0x180004ab4  lea     rbx, [rsi+rsi]
0x180004ab8  add     rdx, rdx; DestinationSize
0x180004abb  mov     r9, rbx; SourceSize
0x180004abe  mov     r8, rbp; Source
0x180004ac1  call    cs:__imp_memcpy_s
0x180004ac7  mov     ecx, eax; int
0x180004ac9  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180004ace  mov     rax, [rdi]
0x180004ad1  mov     [rax-8], esi
0x180004ad4  xor     eax, eax
0x180004ad6  mov     rcx, [rdi]
0x180004ad9  mov     [rbx+rcx], ax
0x180004add  add     rsp, 28h
0x180004ae1  pop     rdi
0x180004ae2  pop     rsi
0x180004ae3  pop     rbp
0x180004ae4  pop     rbx
0x180004ae5  retn
```
