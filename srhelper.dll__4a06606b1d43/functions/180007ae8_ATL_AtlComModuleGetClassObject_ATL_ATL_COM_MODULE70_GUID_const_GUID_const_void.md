# ATL::AtlComModuleGetClassObject(ATL::_ATL_COM_MODULE70 *,_GUID const &,_GUID const &,void * *)

- ea: `0x180007ae8`
- end: `0x180007bee`
- name: `?AtlComModuleGetClassObject@ATL@@YAJPEAU_ATL_COM_MODULE70@1@AEBU_GUID@@1PEAPEAX@Z`
- size: `262`
- prototype: `__int64 __fastcall(struct ATL::_ATL_COM_MODULE70 *, const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800083ec`

## callees

- `0x180007ae8`
- `0x180016010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180007bb0`
- `KERNEL32!LeaveCriticalSection` at `0x180007bb0`
- `KERNEL32!EnterCriticalSection` at `0x180007b85`
- `KERNEL32!EnterCriticalSection` at `0x180007b85`

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
  for ( i = off_18001D120[0]; i < off_18001D128; ++i )
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
            EnterCriticalSection(&stru_18001D130);
            if ( !*v12 )
              v8 = (*(__int64 (__fastcall **)(_QWORD, GUID *, __int64))(v10 + 16))(
                     *(_QWORD *)(v10 + 24),
                     &GUID_00000000_0000_0000_c000_000000000046,
                     v10 + 32);
            LeaveCriticalSection(&stru_18001D130);
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
0x180007ae8  push    rbx
0x180007aea  push    rbp
0x180007aeb  push    rsi
0x180007aec  push    rdi
0x180007aed  push    r14
0x180007aef  sub     rsp, 20h
0x180007af3  cmp     cs:?_AtlComModule@ATL@@3VCAtlComModule@1@A, 0; ATL::CAtlComModule ATL::_AtlComModule
0x180007afa  mov     r14, r9
0x180007afd  mov     r9, rdx
0x180007b00  mov     rbp, r8
0x180007b03  jnz     short loc_180007B0F
0x180007b05  mov     eax, 8000FFFFh
0x180007b0a  jmp     loc_180007BE3
0x180007b0f  test    r14, r14
0x180007b12  jnz     short loc_180007B1E
0x180007b14  mov     eax, 80004003h
0x180007b19  jmp     loc_180007BE3
0x180007b1e  mov     qword ptr [r14], 0
0x180007b25  xor     ebx, ebx
0x180007b27  mov     rcx, cs:off_18001D120
0x180007b2e  mov     r8, cs:off_18001D128
0x180007b35  jmp     short loc_180007B6E
0x180007b37  mov     rsi, [rcx]
0x180007b3a  test    rsi, rsi
0x180007b3d  jz      short loc_180007B6A
0x180007b3f  cmp     [rsi+10h], rbx
0x180007b43  jz      short loc_180007B6A
0x180007b45  mov     rdx, [rsi]
0x180007b48  mov     eax, [rdx]
0x180007b4a  cmp     [r9], eax
0x180007b4d  jnz     short loc_180007B6A
0x180007b4f  mov     eax, [rdx+4]
0x180007b52  cmp     [r9+4], eax
0x180007b56  jnz     short loc_180007B6A
0x180007b58  mov     eax, [rdx+8]
0x180007b5b  cmp     [r9+8], eax
0x180007b5f  jnz     short loc_180007B6A
0x180007b61  mov     eax, [rdx+0Ch]
0x180007b64  cmp     [r9+0Ch], eax
0x180007b68  jz      short loc_180007B75
0x180007b6a  add     rcx, 8
0x180007b6e  cmp     rcx, r8
0x180007b71  jb      short loc_180007B37
0x180007b73  jmp     short loc_180007BD1
0x180007b75  lea     rdi, [rsi+20h]
0x180007b79  cmp     [rdi], rbx
0x180007b7c  jnz     short loc_180007BB6
0x180007b7e  lea     rcx, stru_18001D130; lpCriticalSection
0x180007b85  call    cs:__imp_EnterCriticalSection
0x180007b8b  cmp     [rdi], rbx
0x180007b8e  jnz     short loc_180007BA9
0x180007b90  mov     rcx, [rsi+18h]
0x180007b94  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x180007b9b  mov     rax, [rsi+10h]
0x180007b9f  mov     r8, rdi
0x180007ba2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007ba7  mov     ebx, eax
0x180007ba9  lea     rcx, stru_18001D130; lpCriticalSection
0x180007bb0  call    cs:__imp_LeaveCriticalSection
0x180007bb6  mov     rcx, [rdi]
0x180007bb9  test    rcx, rcx
0x180007bbc  jz      short loc_180007BD1
0x180007bbe  mov     rax, [rcx]
0x180007bc1  mov     r8, r14
0x180007bc4  mov     rdx, rbp
0x180007bc7  mov     rax, [rax]
0x180007bca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007bcf  mov     ebx, eax
0x180007bd1  cmp     qword ptr [r14], 0
0x180007bd5  jnz     short loc_180007BE1
0x180007bd7  test    ebx, ebx
0x180007bd9  mov     eax, 80040111h
0x180007bde  cmovz   ebx, eax
0x180007be1  mov     eax, ebx
0x180007be3  add     rsp, 20h
0x180007be7  pop     r14
0x180007be9  pop     rdi
0x180007bea  pop     rsi
0x180007beb  pop     rbp
0x180007bec  pop     rbx
0x180007bed  retn
```
