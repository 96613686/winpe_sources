# ATL::AtlComModuleGetClassObject(ATL::_ATL_COM_MODULE70 *,_GUID const &,_GUID const &,void * *)

- ea: `0x180002de8`
- end: `0x180002eee`
- name: `?AtlComModuleGetClassObject@ATL@@YAJPEAU_ATL_COM_MODULE70@1@AEBU_GUID@@1PEAPEAX@Z`
- size: `262`
- prototype: `__int64 __fastcall(struct ATL::_ATL_COM_MODULE70 *, const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180004b50`

## callees

- `0x180002de8`
- `0x180006010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002e85`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002e85`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002eb0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002eb0`

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
  for ( i = off_18000C010[0]; i < off_18000C018; ++i )
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
            EnterCriticalSection(&CriticalSection);
            if ( !*v12 )
              v8 = (*(__int64 (__fastcall **)(_QWORD, GUID *, __int64))(v10 + 16))(
                     *(_QWORD *)(v10 + 24),
                     &GUID_00000000_0000_0000_c000_000000000046,
                     v10 + 32);
            LeaveCriticalSection(&CriticalSection);
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
0x180002de8  push    rbx
0x180002dea  push    rbp
0x180002deb  push    rsi
0x180002dec  push    rdi
0x180002ded  push    r14
0x180002def  sub     rsp, 20h
0x180002df3  cmp     cs:?_AtlComModule@ATL@@3VCAtlComModule@1@A, 0; ATL::CAtlComModule ATL::_AtlComModule
0x180002dfa  mov     r14, r9
0x180002dfd  mov     r9, rdx
0x180002e00  mov     rbp, r8
0x180002e03  jnz     short loc_180002E0F
0x180002e05  mov     eax, 8000FFFFh
0x180002e0a  jmp     loc_180002EE3
0x180002e0f  test    r14, r14
0x180002e12  jnz     short loc_180002E1E
0x180002e14  mov     eax, 80004003h
0x180002e19  jmp     loc_180002EE3
0x180002e1e  mov     qword ptr [r14], 0
0x180002e25  xor     ebx, ebx
0x180002e27  mov     rcx, cs:off_18000C010
0x180002e2e  mov     r8, cs:off_18000C018
0x180002e35  jmp     short loc_180002E6E
0x180002e37  mov     rsi, [rcx]
0x180002e3a  test    rsi, rsi
0x180002e3d  jz      short loc_180002E6A
0x180002e3f  cmp     [rsi+10h], rbx
0x180002e43  jz      short loc_180002E6A
0x180002e45  mov     rdx, [rsi]
0x180002e48  mov     eax, [rdx]
0x180002e4a  cmp     [r9], eax
0x180002e4d  jnz     short loc_180002E6A
0x180002e4f  mov     eax, [rdx+4]
0x180002e52  cmp     [r9+4], eax
0x180002e56  jnz     short loc_180002E6A
0x180002e58  mov     eax, [rdx+8]
0x180002e5b  cmp     [r9+8], eax
0x180002e5f  jnz     short loc_180002E6A
0x180002e61  mov     eax, [rdx+0Ch]
0x180002e64  cmp     [r9+0Ch], eax
0x180002e68  jz      short loc_180002E75
0x180002e6a  add     rcx, 8
0x180002e6e  cmp     rcx, r8
0x180002e71  jb      short loc_180002E37
0x180002e73  jmp     short loc_180002ED1
0x180002e75  lea     rdi, [rsi+20h]
0x180002e79  cmp     [rdi], rbx
0x180002e7c  jnz     short loc_180002EB6
0x180002e7e  lea     rcx, CriticalSection; lpCriticalSection
0x180002e85  call    cs:__imp_EnterCriticalSection
0x180002e8b  cmp     [rdi], rbx
0x180002e8e  jnz     short loc_180002EA9
0x180002e90  mov     rcx, [rsi+18h]
0x180002e94  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x180002e9b  mov     rax, [rsi+10h]
0x180002e9f  mov     r8, rdi
0x180002ea2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ea7  mov     ebx, eax
0x180002ea9  lea     rcx, CriticalSection; lpCriticalSection
0x180002eb0  call    cs:__imp_LeaveCriticalSection
0x180002eb6  mov     rcx, [rdi]
0x180002eb9  test    rcx, rcx
0x180002ebc  jz      short loc_180002ED1
0x180002ebe  mov     rax, [rcx]
0x180002ec1  mov     r8, r14
0x180002ec4  mov     rdx, rbp
0x180002ec7  mov     rax, [rax]
0x180002eca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ecf  mov     ebx, eax
0x180002ed1  cmp     qword ptr [r14], 0
0x180002ed5  jnz     short loc_180002EE1
0x180002ed7  test    ebx, ebx
0x180002ed9  mov     eax, 80040111h
0x180002ede  cmovz   ebx, eax
0x180002ee1  mov     eax, ebx
0x180002ee3  add     rsp, 20h
0x180002ee7  pop     r14
0x180002ee9  pop     rdi
0x180002eea  pop     rsi
0x180002eeb  pop     rbp
0x180002eec  pop     rbx
0x180002eed  retn
```
