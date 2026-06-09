# ATL::CComCreator<ATL::CComObjectCached<ATL::CComClassFactory>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180002b40`
- end: `0x180002c84`
- name: `?CreateInstance@?$CComCreator@V?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `324`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001040`
- `0x180001494`
- `0x180002b40`
- `0x180002dcc`
- `0x180006010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180002c44`
- `KERNEL32!DeleteCriticalSection` at `0x180002c58`
- `KERNEL32!DeleteCriticalSection` at `0x180002c44`
- `KERNEL32!DeleteCriticalSection` at `0x180002c58`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObjectCached<ATL::CComClassFactory>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  unsigned int v7; // esi
  char *v8; // rax
  char *v9; // rbx
  int v10; // eax
  _BYTE *v11; // r14

  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  v7 = -2147024882;
  v8 = (char *)operator new(0x78u);
  v9 = v8;
  if ( v8 )
  {
    *((_DWORD *)v8 + 2) = 0;
    *((_OWORD *)v8 + 1) = 0;
    *((_OWORD *)v8 + 2) = 0;
    *((_QWORD *)v8 + 6) = 0;
    v8[56] = 0;
    *(_QWORD *)v8 = &ATL::CComObjectCached<ATL::CComClassFactory>::`vftable';
    *(_OWORD *)(v8 + 72) = 0;
    *(_OWORD *)(v8 + 88) = 0;
    *((_QWORD *)v8 + 13) = 0;
    v8[112] = 0;
    *((_QWORD *)v8 + 8) = a1;
    v10 = ATL::CComCriticalSection::Init((ATL::CComCriticalSection *)(v8 + 16));
    v11 = v9 + 56;
    if ( v10 >= 0 )
    {
      *v11 = 1;
      v10 = ATL::CComCriticalSection::Init((ATL::CComCriticalSection *)(v9 + 72));
      if ( v10 >= 0 )
        v9[112] = 1;
    }
    v7 = 0;
    if ( v10 < 0 )
      v7 = v10;
    if ( v7 || (v7 = (**(__int64 (__fastcall ***)(void *, __int64, _QWORD *))v9)(v9, a2, a3)) != 0 )
    {
      *((_DWORD *)v9 + 2) = 1;
      *(_QWORD *)v9 = &ATL::CComObjectCached<ATL::CComClassFactory>::`vftable';
      if ( v9[112] )
      {
        v9[112] = 0;
        DeleteCriticalSection((LPCRITICAL_SECTION)(v9 + 72));
      }
      if ( *v11 )
      {
        *v11 = 0;
        DeleteCriticalSection((LPCRITICAL_SECTION)(v9 + 16));
      }
      operator delete(v9);
    }
  }
  return v7;
}

```

## disassembly

```asm
0x180002b40  mov     [rsp+arg_0], rbx
0x180002b45  mov     [rsp+arg_8], rbp
0x180002b4a  push    rsi
0x180002b4b  push    rdi
0x180002b4c  push    r12
0x180002b4e  push    r14
0x180002b50  push    r15
0x180002b52  sub     rsp, 20h
0x180002b56  mov     r15, r8
0x180002b59  mov     r12, rdx
0x180002b5c  mov     rdi, rcx
0x180002b5f  test    r8, r8
0x180002b62  jnz     short loc_180002B6E
0x180002b64  mov     eax, 80004003h
0x180002b69  jmp     loc_180002C6D
0x180002b6e  mov     ecx, 78h ; 'x'; Size
0x180002b73  mov     qword ptr [r8], 0
0x180002b7a  mov     esi, 8007000Eh
0x180002b7f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180002b84  mov     [rsp+48h+arg_10], rax
0x180002b89  mov     rbx, rax
0x180002b8c  test    rax, rax
0x180002b8f  jz      loc_180002C6B
0x180002b95  mov     dword ptr [rax+8], 0
0x180002b9c  xorps   xmm0, xmm0
0x180002b9f  movups  xmmword ptr [rbx+10h], xmm0
0x180002ba3  xor     eax, eax
0x180002ba5  movups  xmmword ptr [rbx+20h], xmm0
0x180002ba9  mov     [rbx+30h], rax
0x180002bad  mov     [rbx+38h], al
0x180002bb0  lea     rax, ??_7?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@6B@; const ATL::CComObjectCached<ATL::CComClassFactory>::`vftable'
0x180002bb7  mov     [rbx], rax
0x180002bba  xor     eax, eax
0x180002bbc  movups  xmmword ptr [rbx+48h], xmm0
0x180002bc0  movups  xmmword ptr [rbx+58h], xmm0
0x180002bc4  mov     [rbx+68h], rax
0x180002bc8  mov     [rbx+70h], al
0x180002bcb  test    rbx, rbx
0x180002bce  jz      loc_180002C6B
0x180002bd4  lea     rcx, [rbx+10h]; this
0x180002bd8  mov     [rbx+40h], rdi
0x180002bdc  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180002be1  lea     r14, [rbx+38h]
0x180002be5  lea     rdi, [rbx+48h]
0x180002be9  test    eax, eax
0x180002beb  js      short loc_180002C01
0x180002bed  mov     rcx, rdi; this
0x180002bf0  mov     byte ptr [r14], 1
0x180002bf4  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180002bf9  test    eax, eax
0x180002bfb  js      short loc_180002C01
0x180002bfd  mov     byte ptr [rdi+28h], 1
0x180002c01  xor     esi, esi
0x180002c03  test    eax, eax
0x180002c05  cmovs   esi, eax
0x180002c08  test    esi, esi
0x180002c0a  jnz     short loc_180002C26
0x180002c0c  mov     rax, [rbx]
0x180002c0f  mov     r8, r15
0x180002c12  mov     rdx, r12
0x180002c15  mov     rcx, rbx
0x180002c18  mov     rax, [rax]
0x180002c1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c20  mov     esi, eax
0x180002c22  test    eax, eax
0x180002c24  jz      short loc_180002C6B
0x180002c26  lea     rax, ??_7?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@6B@; const ATL::CComObjectCached<ATL::CComClassFactory>::`vftable'
0x180002c2d  mov     dword ptr [rbx+8], 1
0x180002c34  mov     [rbx], rax
0x180002c37  cmp     byte ptr [rdi+28h], 0
0x180002c3b  jz      short loc_180002C4A
0x180002c3d  mov     rcx, rdi; lpCriticalSection
0x180002c40  mov     byte ptr [rdi+28h], 0
0x180002c44  call    cs:__imp_DeleteCriticalSection
0x180002c4a  cmp     byte ptr [r14], 0
0x180002c4e  jz      short loc_180002C5E
0x180002c50  lea     rcx, [rbx+10h]; lpCriticalSection
0x180002c54  mov     byte ptr [r14], 0
0x180002c58  call    cs:__imp_DeleteCriticalSection
0x180002c5e  mov     edx, 78h ; 'x'; unsigned __int64
0x180002c63  mov     rcx, rbx; void *
0x180002c66  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180002c6b  mov     eax, esi
0x180002c6d  mov     rbx, [rsp+48h+arg_0]
0x180002c72  mov     rbp, [rsp+48h+arg_8]
0x180002c77  add     rsp, 20h
0x180002c7b  pop     r15
0x180002c7d  pop     r14
0x180002c7f  pop     r12
0x180002c81  pop     rdi
0x180002c82  pop     rsi
0x180002c83  retn
```
