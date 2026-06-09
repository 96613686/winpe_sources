# ATL::AtlComModuleGetClassObject(ATL::_ATL_COM_MODULE70 *,_GUID const &,_GUID const &,void * *)

- ea: `0x180010adc`
- end: `0x180010be2`
- name: `?AtlComModuleGetClassObject@ATL@@YAJPEAU_ATL_COM_MODULE70@1@AEBU_GUID@@1PEAPEAX@Z`
- size: `262`
- prototype: `__int64 __fastcall(struct ATL::_ATL_COM_MODULE70 *, const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800138a0`

## callees

- `0x180010adc`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180010ba4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180010ba4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180010b79`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180010b79`

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
  for ( i = off_180021270[0]; i < off_180021278; ++i )
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
            EnterCriticalSection(&stru_180021280);
            if ( !*v12 )
              v8 = (*(__int64 (__fastcall **)(_QWORD, GUID *, __int64))(v10 + 16))(
                     *(_QWORD *)(v10 + 24),
                     &GUID_00000000_0000_0000_c000_000000000046,
                     v10 + 32);
            LeaveCriticalSection(&stru_180021280);
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
0x180010adc  push    rbx
0x180010ade  push    rbp
0x180010adf  push    rsi
0x180010ae0  push    rdi
0x180010ae1  push    r14
0x180010ae3  sub     rsp, 20h
0x180010ae7  cmp     cs:?_AtlComModule@ATL@@3VCAtlComModule@1@A, 0; ATL::CAtlComModule ATL::_AtlComModule
0x180010aee  mov     r14, r9
0x180010af1  mov     r9, rdx
0x180010af4  mov     rbp, r8
0x180010af7  jnz     short loc_180010B03
0x180010af9  mov     eax, 8000FFFFh
0x180010afe  jmp     loc_180010BD7
0x180010b03  test    r14, r14
0x180010b06  jnz     short loc_180010B12
0x180010b08  mov     eax, 80004003h
0x180010b0d  jmp     loc_180010BD7
0x180010b12  mov     qword ptr [r14], 0
0x180010b19  xor     ebx, ebx
0x180010b1b  mov     rcx, cs:off_180021270
0x180010b22  mov     r8, cs:off_180021278
0x180010b29  jmp     short loc_180010B62
0x180010b2b  mov     rsi, [rcx]
0x180010b2e  test    rsi, rsi
0x180010b31  jz      short loc_180010B5E
0x180010b33  cmp     [rsi+10h], rbx
0x180010b37  jz      short loc_180010B5E
0x180010b39  mov     rdx, [rsi]
0x180010b3c  mov     eax, [rdx]
0x180010b3e  cmp     [r9], eax
0x180010b41  jnz     short loc_180010B5E
0x180010b43  mov     eax, [rdx+4]
0x180010b46  cmp     [r9+4], eax
0x180010b4a  jnz     short loc_180010B5E
0x180010b4c  mov     eax, [rdx+8]
0x180010b4f  cmp     [r9+8], eax
0x180010b53  jnz     short loc_180010B5E
0x180010b55  mov     eax, [rdx+0Ch]
0x180010b58  cmp     [r9+0Ch], eax
0x180010b5c  jz      short loc_180010B69
0x180010b5e  add     rcx, 8
0x180010b62  cmp     rcx, r8
0x180010b65  jb      short loc_180010B2B
0x180010b67  jmp     short loc_180010BC5
0x180010b69  lea     rdi, [rsi+20h]
0x180010b6d  cmp     [rdi], rbx
0x180010b70  jnz     short loc_180010BAA
0x180010b72  lea     rcx, stru_180021280; lpCriticalSection
0x180010b79  call    cs:__imp_EnterCriticalSection
0x180010b7f  cmp     [rdi], rbx
0x180010b82  jnz     short loc_180010B9D
0x180010b84  mov     rcx, [rsi+18h]
0x180010b88  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x180010b8f  mov     rax, [rsi+10h]
0x180010b93  mov     r8, rdi
0x180010b96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010b9b  mov     ebx, eax
0x180010b9d  lea     rcx, stru_180021280; lpCriticalSection
0x180010ba4  call    cs:__imp_LeaveCriticalSection
0x180010baa  mov     rcx, [rdi]
0x180010bad  test    rcx, rcx
0x180010bb0  jz      short loc_180010BC5
0x180010bb2  mov     rax, [rcx]
0x180010bb5  mov     r8, r14
0x180010bb8  mov     rdx, rbp
0x180010bbb  mov     rax, [rax]
0x180010bbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010bc3  mov     ebx, eax
0x180010bc5  cmp     qword ptr [r14], 0
0x180010bc9  jnz     short loc_180010BD5
0x180010bcb  test    ebx, ebx
0x180010bcd  mov     eax, 80040111h
0x180010bd2  cmovz   ebx, eax
0x180010bd5  mov     eax, ebx
0x180010bd7  add     rsp, 20h
0x180010bdb  pop     r14
0x180010bdd  pop     rdi
0x180010bde  pop     rsi
0x180010bdf  pop     rbp
0x180010be0  pop     rbx
0x180010be1  retn
```
