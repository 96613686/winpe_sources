# ATL::CAcl::GetPACL(void)

- ea: `0x180042e70`
- end: `0x180042fca`
- name: `?GetPACL@CAcl@ATL@@QEBAPEBU_ACL@@XZ`
- size: `346`
- prototype: `const struct _ACL *__fastcall(ATL::CAcl *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x180045490`

## callees

- `0x180006d14`
- `0x180007598`
- `0x180042e70`
- `0x1800a3010`

## import_xrefs

- `msvcrt!malloc` at `0x180042ede`
- `msvcrt!malloc` at `0x180042ede`
- `msvcrt!free` at `0x180042f16`
- `msvcrt!free` at `0x180042fa5`
- `msvcrt!free` at `0x180042f16`
- `msvcrt!free` at `0x180042fa5`
- `ADVAPI32!InitializeAcl` at `0x180042f01`
- `ADVAPI32!InitializeAcl` at `0x180042f01`
- `ADVAPI32!AddAce` at `0x180042f8c`
- `ADVAPI32!AddAce` at `0x180042f8c`

## pseudocode

```c
const struct _ACL *__fastcall ATL::CAcl::GetPACL(ATL::CAcl *this)
{
  DWORD v2; // esi
  unsigned int v3; // ebx
  unsigned int v4; // ebp
  __int64 v5; // rax
  struct _ACL *v6; // rax
  int Error; // ebx
  unsigned int i; // esi
  __int64 v9; // rax
  __int64 v10; // r14
  DWORD nAceListLength; // ebx
  void *v12; // rax
  int v13; // ebx

  if ( !*((_QWORD *)this + 1) && !*((_BYTE *)this + 16) )
  {
    v2 = 8;
    v3 = 0;
    v4 = (*(__int64 (__fastcall **)(ATL::CAcl *))(*(_QWORD *)this + 8LL))(this);
    if ( v4 )
    {
      do
      {
        v5 = (*(__int64 (__fastcall **)(ATL::CAcl *, _QWORD))(*(_QWORD *)this + 32LL))(this, v3);
        if ( v5 )
          v2 += (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
        ++v3;
      }
      while ( v3 < v4 );
    }
    v6 = (struct _ACL *)malloc(v2);
    *((_QWORD *)this + 1) = v6;
    if ( !v6 )
      ATL::AtlThrowImpl(-2147024882);
    if ( !InitializeAcl(v6, v2, *((_DWORD *)this + 5)) )
    {
      Error = ATL::AtlHresultFromLastError();
      free(*((void **)this + 1));
      *((_QWORD *)this + 1) = 0;
      ATL::AtlThrowImpl(Error);
    }
    (*(void (__fastcall **)(ATL::CAcl *))(*(_QWORD *)this + 40LL))(this);
    for ( i = 0; i < v4; ++i )
    {
      v9 = (*(__int64 (__fastcall **)(ATL::CAcl *, _QWORD))(*(_QWORD *)this + 32LL))(this, i);
      v10 = v9;
      if ( v9 )
      {
        nAceListLength = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
        v12 = (void *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v10 + 8LL))(v10);
        if ( AddAce(*((PACL *)this + 1), *((_DWORD *)this + 5), 0xFFFFFFFF, v12, nAceListLength) )
          continue;
      }
      v13 = ATL::AtlHresultFromLastError();
      free(*((void **)this + 1));
      *((_QWORD *)this + 1) = 0;
      ATL::AtlThrowImpl(v13);
    }
  }
  return (const struct _ACL *)*((_QWORD *)this + 1);
}

```

## disassembly

```asm
0x180042e70  push    rbx
0x180042e72  push    rbp
0x180042e73  push    rsi
0x180042e74  push    rdi
0x180042e75  push    r14
0x180042e77  sub     rsp, 30h
0x180042e7b  cmp     qword ptr [rcx+8], 0
0x180042e80  mov     rdi, rcx
0x180042e83  jnz     loc_180042FBB
0x180042e89  cmp     byte ptr [rcx+10h], 0
0x180042e8d  jnz     loc_180042FBB
0x180042e93  mov     rax, [rcx]
0x180042e96  mov     esi, 8
0x180042e9b  mov     rax, [rax+8]
0x180042e9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042ea4  xor     ebx, ebx
0x180042ea6  mov     ebp, eax
0x180042ea8  test    eax, eax
0x180042eaa  jz      short loc_180042EDC
0x180042eac  mov     rcx, [rdi]
0x180042eaf  mov     edx, ebx
0x180042eb1  mov     rax, [rcx+20h]
0x180042eb5  mov     rcx, rdi
0x180042eb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042ebd  mov     rdx, rax
0x180042ec0  test    rax, rax
0x180042ec3  jz      short loc_180042ED6
0x180042ec5  mov     rcx, [rax]
0x180042ec8  mov     rax, [rcx+10h]
0x180042ecc  mov     rcx, rdx
0x180042ecf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042ed4  add     esi, eax
0x180042ed6  inc     ebx
0x180042ed8  cmp     ebx, ebp
0x180042eda  jb      short loc_180042EAC
0x180042edc  mov     ecx, esi; Size
0x180042ede  call    cs:__imp_malloc
0x180042ee4  mov     [rdi+8], rax
0x180042ee8  test    rax, rax
0x180042eeb  jnz     short loc_180042EF8
0x180042eed  mov     ecx, 8007000Eh; int
0x180042ef2  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180042ef8  mov     r8d, [rdi+14h]; dwAclRevision
0x180042efc  mov     edx, esi; nAclLength
0x180042efe  mov     rcx, rax; pAcl
0x180042f01  call    cs:__imp_InitializeAcl
0x180042f07  test    eax, eax
0x180042f09  jnz     short loc_180042F2C
0x180042f0b  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180042f10  mov     rcx, [rdi+8]; Block
0x180042f14  mov     ebx, eax
0x180042f16  call    cs:__imp_free
0x180042f1c  mov     ecx, ebx; int
0x180042f1e  mov     qword ptr [rdi+8], 0
0x180042f26  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180042f2c  mov     rax, [rdi]
0x180042f2f  mov     rcx, rdi
0x180042f32  mov     rax, [rax+28h]
0x180042f36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042f3b  xor     esi, esi
0x180042f3d  cmp     esi, ebp
0x180042f3f  jnb     short loc_180042FBB
0x180042f41  mov     rax, [rdi]
0x180042f44  mov     edx, esi
0x180042f46  mov     rcx, rdi
0x180042f49  mov     rax, [rax+20h]
0x180042f4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042f52  mov     r14, rax
0x180042f55  test    rax, rax
0x180042f58  jz      short loc_180042F9A
0x180042f5a  mov     rcx, [rax]
0x180042f5d  mov     rax, [rcx+10h]
0x180042f61  mov     rcx, r14
0x180042f64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042f69  mov     rcx, [r14]
0x180042f6c  mov     ebx, eax
0x180042f6e  mov     rax, [rcx+8]
0x180042f72  mov     rcx, r14
0x180042f75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042f7a  mov     edx, [rdi+14h]; dwAceRevision
0x180042f7d  mov     r9, rax; pAceList
0x180042f80  mov     rcx, [rdi+8]; pAcl
0x180042f84  or      r8d, 0FFFFFFFFh; dwStartingAceIndex
0x180042f88  mov     [rsp+58h+nAceListLength], ebx; nAceListLength
0x180042f8c  call    cs:__imp_AddAce
0x180042f92  test    eax, eax
0x180042f94  jz      short loc_180042F9A
0x180042f96  inc     esi
0x180042f98  jmp     short loc_180042F3D
0x180042f9a  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180042f9f  mov     rcx, [rdi+8]; Block
0x180042fa3  mov     ebx, eax
0x180042fa5  call    cs:__imp_free
0x180042fab  mov     ecx, ebx; int
0x180042fad  mov     qword ptr [rdi+8], 0
0x180042fb5  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180042fbb  mov     rax, [rdi+8]
0x180042fbf  add     rsp, 30h
0x180042fc3  pop     r14
0x180042fc5  pop     rdi
0x180042fc6  pop     rsi
0x180042fc7  pop     rbp
0x180042fc8  pop     rbx
0x180042fc9  retn
```
