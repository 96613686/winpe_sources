# WTL::CString::ConcatCopy(int,ushort const *,int,ushort const *)

- ea: `0x18000d98c`
- end: `0x18000da25`
- name: `?ConcatCopy@CString@WTL@@IEAAHHPEBGH0@Z`
- size: `153`
- prototype: `int(WTL::CString *__hidden this, int, const unsigned __int16 *, int, const unsigned __int16 *)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x18000d290`
- `0x18000d2e4`
- `0x18000da2c`
- `0x1800282f0`

## callees

- `0x1800048d4`
- `0x180004c00`
- `0x18000d98c`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000d9db`
- `msvcrt!memcpy_s` at `0x18000da05`
- `msvcrt!memcpy_s` at `0x18000d9db`
- `msvcrt!memcpy_s` at `0x18000da05`

## pseudocode

```c
__int64 __fastcall WTL::CString::ConcatCopy(
        WTL::CString *this,
        int a2,
        const unsigned __int16 *a3,
        int a4,
        const unsigned __int16 *Source)
{
  __int64 v5; // rbx
  __int64 v7; // rbp
  int v9; // esi
  unsigned int v10; // edi
  rsize_t v11; // rbx
  errno_t v12; // eax
  errno_t v13; // eax

  v5 = a2;
  v7 = a4;
  v9 = a2 + a4;
  if ( a2 + a4 < a2 || v9 < a4 )
  {
    return 0;
  }
  else
  {
    v10 = 1;
    if ( v9 )
    {
      v10 = WTL::CString::AllocBuffer(this, v9);
      if ( v10 )
      {
        v11 = 2 * v5;
        v12 = memcpy_s(*(void *const *)this, 2LL * (v9 + 1), a3, v11);
        ATL::AtlCrtErrorCheck(v12);
        v13 = memcpy_s((void *const)(v11 + *(_QWORD *)this), 2LL * ((int)v7 + 1), Source, 2 * v7);
        ATL::AtlCrtErrorCheck(v13);
      }
    }
  }
  return v10;
}

```

## disassembly

```asm
0x18000d98c  push    rbx
0x18000d98e  push    rbp
0x18000d98f  push    rsi
0x18000d990  push    rdi
0x18000d991  push    r14
0x18000d993  push    r15
0x18000d995  sub     rsp, 28h
0x18000d999  movsxd  rbx, edx
0x18000d99c  mov     r15, r8
0x18000d99f  movsxd  rbp, r9d
0x18000d9a2  mov     r14, rcx
0x18000d9a5  lea     esi, [rbx+rbp]
0x18000d9a8  cmp     esi, ebx
0x18000d9aa  jl      short loc_18000DA14
0x18000d9ac  cmp     esi, ebp
0x18000d9ae  jl      short loc_18000DA14
0x18000d9b0  mov     edi, 1
0x18000d9b5  test    esi, esi
0x18000d9b7  jz      short loc_18000DA16
0x18000d9b9  mov     edx, esi; int
0x18000d9bb  call    ?AllocBuffer@CString@WTL@@IEAAHH@Z; WTL::CString::AllocBuffer(int)
0x18000d9c0  mov     edi, eax
0x18000d9c2  test    eax, eax
0x18000d9c4  jz      short loc_18000DA16
0x18000d9c6  lea     ecx, [rsi+1]
0x18000d9c9  add     rbx, rbx
0x18000d9cc  movsxd  rdx, ecx
0x18000d9cf  mov     r9, rbx; SourceSize
0x18000d9d2  mov     rcx, [r14]; Destination
0x18000d9d5  add     rdx, rdx; DestinationSize
0x18000d9d8  mov     r8, r15; Source
0x18000d9db  call    cs:__imp_memcpy_s
0x18000d9e1  mov     ecx, eax; int
0x18000d9e3  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18000d9e8  mov     rcx, [r14]
0x18000d9eb  lea     eax, [rbp+1]
0x18000d9ee  mov     r8, [rsp+58h+Source]; Source
0x18000d9f6  mov     r9, rbp
0x18000d9f9  movsxd  rdx, eax
0x18000d9fc  add     r9, r9; SourceSize
0x18000d9ff  add     rdx, rdx; DestinationSize
0x18000da02  add     rcx, rbx; Destination
0x18000da05  call    cs:__imp_memcpy_s
0x18000da0b  mov     ecx, eax; int
0x18000da0d  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18000da12  jmp     short loc_18000DA16
0x18000da14  xor     edi, edi
0x18000da16  mov     eax, edi
0x18000da18  add     rsp, 28h
0x18000da1c  pop     r15
0x18000da1e  pop     r14
0x18000da20  pop     rdi
0x18000da21  pop     rsi
0x18000da22  pop     rbp
0x18000da23  pop     rbx
0x18000da24  retn
```
