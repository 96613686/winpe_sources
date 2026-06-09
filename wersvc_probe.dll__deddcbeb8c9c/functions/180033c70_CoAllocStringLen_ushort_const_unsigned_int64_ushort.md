# CoAllocStringLen(ushort const *,unsigned __int64,ushort * *)

- ea: `0x180033c70`
- end: `0x180033d76`
- name: `?CoAllocStringLen@@YAJPEBG_KPEAPEAG@Z`
- size: `262`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int64, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180033ea8`

## callees

- `0x1800035e8`
- `0x180033c70`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180033ca3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180033ca3`

## pseudocode

```c
__int64 __fastcall CoAllocStringLen(const unsigned __int16 *a1, unsigned __int64 a2, unsigned __int16 **a3)
{
  unsigned __int64 v3; // rbx
  unsigned __int16 *v6; // rax
  unsigned int v7; // edi

  v3 = a2 + 1;
  *a3 = 0;
  if ( a2 + 1 < a2 || !is_mul_ok(v3, 2u) )
    return (unsigned int)-2147024362;
  v6 = (unsigned __int16 *)CoTaskMemAlloc(2 * v3);
  *a3 = v6;
  v7 = v6 == 0 ? 0x8007000E : 0;
  if ( v6 )
  {
    if ( v3 > 0x7FFFFFFF )
    {
LABEL_7:
      *v6 = 0;
      return v7;
    }
    if ( a2 < 0x7FFFFFFF )
    {
      if ( v3 )
      {
        *v6 = 0;
        if ( v3 > 1 && 2 * v3 > 2 )
          memset_0(v6 + 1, 0, 2 * v3 - 2);
      }
    }
    else if ( v3 )
    {
      goto LABEL_7;
    }
  }
  return v7;
}

```

## disassembly

```asm
0x180033c70  push    rbx
0x180033c72  push    rbp
0x180033c73  push    rsi
0x180033c74  push    rdi
0x180033c75  sub     rsp, 28h
0x180033c79  xor     ebp, ebp
0x180033c7b  lea     rbx, [rdx+1]
0x180033c7f  mov     [r8], rbp
0x180033c82  mov     rdi, r8
0x180033c85  mov     rsi, rdx
0x180033c88  cmp     rbx, rdx
0x180033c8b  jb      loc_180033D66
0x180033c91  lea     eax, [rbp+2]
0x180033c94  mul     rbx
0x180033c97  test    rdx, rdx
0x180033c9a  jnz     loc_180033D66
0x180033ca0  mov     rcx, rax; cb
0x180033ca3  call    cs:__imp_CoTaskMemAlloc
0x180033ca9  mov     [rdi], rax
0x180033cac  mov     rcx, rax
0x180033caf  neg     rcx
0x180033cb2  mov     rdx, rax
0x180033cb5  sbb     edi, edi
0x180033cb7  not     edi
0x180033cb9  and     edi, 8007000Eh
0x180033cbf  test    rax, rax
0x180033cc2  jz      loc_180033D6B
0x180033cc8  mov     eax, 7FFFFFFFh
0x180033ccd  cmp     rbx, rax
0x180033cd0  ja      short loc_180033CE0
0x180033cd2  cmp     rsi, rax
0x180033cd5  jb      short loc_180033CE8
0x180033cd7  test    rbx, rbx
0x180033cda  jz      loc_180033D6B
0x180033ce0  mov     [rdx], bp
0x180033ce3  jmp     loc_180033D6B
0x180033ce8  test    rbx, rbx
0x180033ceb  jz      short loc_180033D6B
0x180033ced  mov     rcx, rbp
0x180033cf0  lea     r9, unk_180039414
0x180033cf7  mov     r8, rbx
0x180033cfa  mov     rax, rdx
0x180033cfd  mov     r10, rbp
0x180033d00  test    rcx, rcx
0x180033d03  jz      short loc_180033D27
0x180033d05  movzx   r11d, word ptr [r9]
0x180033d09  test    r11w, r11w
0x180033d0d  jz      short loc_180033D27
0x180033d0f  mov     [rax], r11w
0x180033d13  add     r9, 2
0x180033d17  add     rax, 2
0x180033d1b  dec     rcx
0x180033d1e  inc     r10
0x180033d21  sub     r8, 1
0x180033d25  jnz     short loc_180033D00
0x180033d27  test    r8, r8
0x180033d2a  lea     rcx, [rax-2]
0x180033d2e  lea     r9, [r10-1]
0x180033d32  cmovnz  rcx, rax
0x180033d36  cmovnz  r9, r10
0x180033d3a  mov     [rcx], bp
0x180033d3d  jz      short loc_180033D6B
0x180033d3f  sub     rbx, r9
0x180033d42  cmp     rbx, 1
0x180033d46  jbe     short loc_180033D6B
0x180033d48  lea     r8, [rbx+rbx]
0x180033d4c  cmp     r8, 2
0x180033d50  jbe     short loc_180033D6B
0x180033d52  inc     r9
0x180033d55  add     r8, 0FFFFFFFFFFFFFFFEh; Size
0x180033d59  lea     rcx, [rdx+r9*2]; void *
0x180033d5d  xor     edx, edx; Val
0x180033d5f  call    memset_0
0x180033d64  jmp     short loc_180033D6B
0x180033d66  mov     edi, 80070216h
0x180033d6b  mov     eax, edi
0x180033d6d  add     rsp, 28h
0x180033d71  pop     rdi
0x180033d72  pop     rsi
0x180033d73  pop     rbp
0x180033d74  pop     rbx
0x180033d75  retn
```
