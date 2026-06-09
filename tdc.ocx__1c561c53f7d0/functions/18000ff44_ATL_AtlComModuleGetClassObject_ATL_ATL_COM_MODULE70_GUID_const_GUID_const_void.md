# ATL::AtlComModuleGetClassObject(ATL::_ATL_COM_MODULE70 *,_GUID const &,_GUID const &,void * *)

- ea: `0x18000ff44`
- end: `0x18001004a`
- name: `?AtlComModuleGetClassObject@ATL@@YAJPEAU_ATL_COM_MODULE70@1@AEBU_GUID@@1PEAPEAX@Z`
- size: `262`
- prototype: `__int64 __fastcall(struct ATL::_ATL_COM_MODULE70 *, const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180013570`

## callees

- `0x18000ff44`
- `0x180015010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18001000c`
- `KERNEL32!LeaveCriticalSection` at `0x18001000c`
- `KERNEL32!EnterCriticalSection` at `0x18000ffe1`
- `KERNEL32!EnterCriticalSection` at `0x18000ffe1`

## pseudocode

```c
__int64 __fastcall ATL::AtlComModuleGetClassObject(
        struct ATL::_ATL_COM_MODULE70 *a1,
        const struct _GUID *a2,
        const struct _GUID *a3,
        void **a4)
{
  unsigned int v8; // ebx
  __int64 *i; // rcx
  __int64 v10; // rsi
  _DWORD *v11; // rdx
  _QWORD *v12; // rdi

  if ( !ATL::_AtlComModule )
    return 2147549183LL;
  if ( !a4 )
    return 2147500035LL;
  *a4 = 0;
  v8 = 0;
  for ( i = (__int64 *)off_18001B630[0]; i < (__int64 *)off_18001B638; ++i )
  {
    v10 = *i;
    if ( *i )
    {
      if ( *(_QWORD *)(v10 + 16) )
      {
        v11 = *(_DWORD **)v10;
        if ( a2->Data1 == **(_DWORD **)v10
          && *(_DWORD *)&a2->Data2 == v11[1]
          && *(_DWORD *)a2->Data4 == v11[2]
          && *(_DWORD *)&a2->Data4[4] == v11[3] )
        {
          v12 = (_QWORD *)(v10 + 32);
          if ( !*(_QWORD *)(v10 + 32) )
          {
            EnterCriticalSection(&stru_18001B640);
            if ( !*v12 )
              v8 = (*(__int64 (__fastcall **)(_QWORD, GUID *, __int64))(v10 + 16))(
                     *(_QWORD *)(v10 + 24),
                     &GUID_00000000_0000_0000_c000_000000000046,
                     v10 + 32);
            LeaveCriticalSection(&stru_18001B640);
          }
          if ( *v12 )
            v8 = (**(__int64 (__fastcall ***)(_QWORD, const struct _GUID *, void **))*v12)(*v12, a3, a4);
          break;
        }
      }
    }
  }
  if ( !*a4 && !v8 )
    return (unsigned int)-2147221231;
  return v8;
}

```

## disassembly

```asm
0x18000ff44  push    rbx
0x18000ff46  push    rbp
0x18000ff47  push    rsi
0x18000ff48  push    rdi
0x18000ff49  push    r14
0x18000ff4b  sub     rsp, 20h
0x18000ff4f  cmp     cs:?_AtlComModule@ATL@@3VCAtlComModule@1@A, 0; ATL::CAtlComModule ATL::_AtlComModule
0x18000ff56  mov     r14, r9
0x18000ff59  mov     r9, rdx
0x18000ff5c  mov     rbp, r8
0x18000ff5f  jnz     short loc_18000FF6B
0x18000ff61  mov     eax, 8000FFFFh
0x18000ff66  jmp     loc_18001003F
0x18000ff6b  test    r14, r14
0x18000ff6e  jnz     short loc_18000FF7A
0x18000ff70  mov     eax, 80004003h
0x18000ff75  jmp     loc_18001003F
0x18000ff7a  mov     qword ptr [r14], 0
0x18000ff81  xor     ebx, ebx
0x18000ff83  mov     rcx, cs:off_18001B630
0x18000ff8a  mov     r8, cs:off_18001B638
0x18000ff91  jmp     short loc_18000FFCA
0x18000ff93  mov     rsi, [rcx]
0x18000ff96  test    rsi, rsi
0x18000ff99  jz      short loc_18000FFC6
0x18000ff9b  cmp     [rsi+10h], rbx
0x18000ff9f  jz      short loc_18000FFC6
0x18000ffa1  mov     rdx, [rsi]
0x18000ffa4  mov     eax, [rdx]
0x18000ffa6  cmp     [r9], eax
0x18000ffa9  jnz     short loc_18000FFC6
0x18000ffab  mov     eax, [rdx+4]
0x18000ffae  cmp     [r9+4], eax
0x18000ffb2  jnz     short loc_18000FFC6
0x18000ffb4  mov     eax, [rdx+8]
0x18000ffb7  cmp     [r9+8], eax
0x18000ffbb  jnz     short loc_18000FFC6
0x18000ffbd  mov     eax, [rdx+0Ch]
0x18000ffc0  cmp     [r9+0Ch], eax
0x18000ffc4  jz      short loc_18000FFD1
0x18000ffc6  add     rcx, 8
0x18000ffca  cmp     rcx, r8
0x18000ffcd  jb      short loc_18000FF93
0x18000ffcf  jmp     short loc_18001002D
0x18000ffd1  lea     rdi, [rsi+20h]
0x18000ffd5  cmp     [rdi], rbx
0x18000ffd8  jnz     short loc_180010012
0x18000ffda  lea     rcx, stru_18001B640; lpCriticalSection
0x18000ffe1  call    cs:__imp_EnterCriticalSection
0x18000ffe7  cmp     [rdi], rbx
0x18000ffea  jnz     short loc_180010005
0x18000ffec  mov     rcx, [rsi+18h]
0x18000fff0  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x18000fff7  mov     rax, [rsi+10h]
0x18000fffb  mov     r8, rdi
0x18000fffe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010003  mov     ebx, eax
0x180010005  lea     rcx, stru_18001B640; lpCriticalSection
0x18001000c  call    cs:__imp_LeaveCriticalSection
0x180010012  mov     rcx, [rdi]
0x180010015  test    rcx, rcx
0x180010018  jz      short loc_18001002D
0x18001001a  mov     rax, [rcx]
0x18001001d  mov     r8, r14
0x180010020  mov     rdx, rbp
0x180010023  mov     rax, [rax]
0x180010026  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001002b  mov     ebx, eax
0x18001002d  cmp     qword ptr [r14], 0
0x180010031  jnz     short loc_18001003D
0x180010033  test    ebx, ebx
0x180010035  mov     eax, 80040111h
0x18001003a  cmovz   ebx, eax
0x18001003d  mov     eax, ebx
0x18001003f  add     rsp, 20h
0x180010043  pop     r14
0x180010045  pop     rdi
0x180010046  pop     rsi
0x180010047  pop     rbp
0x180010048  pop     rbx
0x180010049  retn
```
