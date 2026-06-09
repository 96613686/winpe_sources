# mlib::MSError::MakeStringCopy(ushort const *)

- ea: `0x1800104e4`
- end: `0x180010556`
- name: `?MakeStringCopy@MSError@mlib@@CAPEAGPEBG@Z`
- size: `114`
- prototype: `unsigned __int16 *__fastcall(const unsigned __int16 *Src)`
- caller_count: `6`
- callee_count: `3`
- tags: ``

## callers

- `0x18000b460`
- `0x18000bf30`
- `0x1800104b0`
- `0x18001d7d8`
- `0x18002e4d0`
- `0x18002f0e0`

## callees

- `0x18000ac70`
- `0x1800104e4`
- `0x180013fb6`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001051a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001051a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180010528`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180010528`

## pseudocode

```c
unsigned __int16 *__fastcall mlib::MSError::MakeStringCopy(const unsigned __int16 *Src)
{
  SIZE_T v2; // rsi
  HANDLE ProcessHeap; // rax
  unsigned __int16 *result; // rax
  unsigned __int16 *v5; // rdi

  if ( !Src || *Src )
    return 0;
  try
  {
    v2 = 2 * mlib::m_traits<unsigned short>::CStrlen(Src, 0x10000) + 2;
    ProcessHeap = GetProcessHeap();
    result = (unsigned __int16 *)HeapAlloc(ProcessHeap, 0, v2);
    v5 = result;
    if ( result )
    {
      memcpy_0(result, Src, v2);
      result = v5;
    }
  }
  catch ( ... )
  {
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800104e4  push    rbx
0x1800104e6  push    rsi
0x1800104e7  push    rdi
0x1800104e8  push    r14
0x1800104ea  sub     rsp, 38h
0x1800104ee  mov     [rsp+58h+var_38], 0FFFFFFFFFFFFFFFEh
0x1800104f7  mov     rbx, rcx
0x1800104fa  xor     r14d, r14d
0x1800104fd  test    rcx, rcx
0x180010500  jz      short loc_180010549
0x180010502  cmp     [rcx], r14w
0x180010506  jnz     short loc_180010549
0x180010508  mov     edx, 10000h
0x18001050d  call    ?CStrlen@?$m_traits@G@mlib@@SA_KPEBG_K@Z; mlib::m_traits<ushort>::CStrlen(ushort const *,unsigned __int64)
0x180010512  lea     rsi, ds:2[rax*2]
0x18001051a  call    cs:__imp_GetProcessHeap
0x180010520  mov     rcx, rax; hHeap
0x180010523  mov     r8, rsi; dwBytes
0x180010526  xor     edx, edx; dwFlags
0x180010528  call    cs:__imp_HeapAlloc
0x18001052e  mov     rdi, rax
0x180010531  test    rax, rax
0x180010534  jz      short loc_18001054B
0x180010536  mov     r8, rsi; Size
0x180010539  mov     rdx, rbx; Src
0x18001053c  mov     rcx, rdi; void *
0x18001053f  call    memcpy_0
0x180010544  mov     rax, rdi
0x180010547  jmp     short loc_18001054B
0x180010549  xor     eax, eax
0x18001054b  add     rsp, 38h
0x18001054f  pop     r14
0x180010551  pop     rdi
0x180010552  pop     rsi
0x180010553  pop     rbx
0x180010554  retn
```
