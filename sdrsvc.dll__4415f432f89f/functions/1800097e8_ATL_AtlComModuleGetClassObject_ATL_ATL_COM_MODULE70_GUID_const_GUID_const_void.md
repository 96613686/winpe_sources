# ATL::AtlComModuleGetClassObject(ATL::_ATL_COM_MODULE70 *,_GUID const &,_GUID const &,void * *)

- ea: `0x1800097e8`
- end: `0x1800098ee`
- name: `?AtlComModuleGetClassObject@ATL@@YAJPEAU_ATL_COM_MODULE70@1@AEBU_GUID@@1PEAPEAX@Z`
- size: `262`
- prototype: `__int64 __fastcall(struct ATL::_ATL_COM_MODULE70 *, const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000e510`

## callees

- `0x1800097e8`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800098b0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800098b0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180009885`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180009885`

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
  for ( i = off_18002D3B0[0]; i < off_18002D3B8; ++i )
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
            EnterCriticalSection(&stru_18002D3C0);
            if ( !*v12 )
              v8 = (*(__int64 (__fastcall **)(_QWORD, GUID *, __int64))(v10 + 16))(
                     *(_QWORD *)(v10 + 24),
                     &GUID_00000000_0000_0000_c000_000000000046,
                     v10 + 32);
            LeaveCriticalSection(&stru_18002D3C0);
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
0x1800097e8  push    rbx
0x1800097ea  push    rbp
0x1800097eb  push    rsi
0x1800097ec  push    rdi
0x1800097ed  push    r14
0x1800097ef  sub     rsp, 20h
0x1800097f3  cmp     cs:?_AtlComModule@ATL@@3VCAtlComModule@1@A, 0; ATL::CAtlComModule ATL::_AtlComModule
0x1800097fa  mov     r14, r9
0x1800097fd  mov     r9, rdx
0x180009800  mov     rbp, r8
0x180009803  jnz     short loc_18000980F
0x180009805  mov     eax, 8000FFFFh
0x18000980a  jmp     loc_1800098E3
0x18000980f  test    r14, r14
0x180009812  jnz     short loc_18000981E
0x180009814  mov     eax, 80004003h
0x180009819  jmp     loc_1800098E3
0x18000981e  mov     qword ptr [r14], 0
0x180009825  xor     ebx, ebx
0x180009827  mov     rcx, cs:off_18002D3B0
0x18000982e  mov     r8, cs:off_18002D3B8
0x180009835  jmp     short loc_18000986E
0x180009837  mov     rsi, [rcx]
0x18000983a  test    rsi, rsi
0x18000983d  jz      short loc_18000986A
0x18000983f  cmp     [rsi+10h], rbx
0x180009843  jz      short loc_18000986A
0x180009845  mov     rdx, [rsi]
0x180009848  mov     eax, [rdx]
0x18000984a  cmp     [r9], eax
0x18000984d  jnz     short loc_18000986A
0x18000984f  mov     eax, [rdx+4]
0x180009852  cmp     [r9+4], eax
0x180009856  jnz     short loc_18000986A
0x180009858  mov     eax, [rdx+8]
0x18000985b  cmp     [r9+8], eax
0x18000985f  jnz     short loc_18000986A
0x180009861  mov     eax, [rdx+0Ch]
0x180009864  cmp     [r9+0Ch], eax
0x180009868  jz      short loc_180009875
0x18000986a  add     rcx, 8
0x18000986e  cmp     rcx, r8
0x180009871  jb      short loc_180009837
0x180009873  jmp     short loc_1800098D1
0x180009875  lea     rdi, [rsi+20h]
0x180009879  cmp     [rdi], rbx
0x18000987c  jnz     short loc_1800098B6
0x18000987e  lea     rcx, stru_18002D3C0; lpCriticalSection
0x180009885  call    cs:__imp_EnterCriticalSection
0x18000988b  cmp     [rdi], rbx
0x18000988e  jnz     short loc_1800098A9
0x180009890  mov     rcx, [rsi+18h]
0x180009894  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x18000989b  mov     rax, [rsi+10h]
0x18000989f  mov     r8, rdi
0x1800098a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800098a7  mov     ebx, eax
0x1800098a9  lea     rcx, stru_18002D3C0; lpCriticalSection
0x1800098b0  call    cs:__imp_LeaveCriticalSection
0x1800098b6  mov     rcx, [rdi]
0x1800098b9  test    rcx, rcx
0x1800098bc  jz      short loc_1800098D1
0x1800098be  mov     rax, [rcx]
0x1800098c1  mov     r8, r14
0x1800098c4  mov     rdx, rbp
0x1800098c7  mov     rax, [rax]
0x1800098ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800098cf  mov     ebx, eax
0x1800098d1  cmp     qword ptr [r14], 0
0x1800098d5  jnz     short loc_1800098E1
0x1800098d7  test    ebx, ebx
0x1800098d9  mov     eax, 80040111h
0x1800098de  cmovz   ebx, eax
0x1800098e1  mov     eax, ebx
0x1800098e3  add     rsp, 20h
0x1800098e7  pop     r14
0x1800098e9  pop     rdi
0x1800098ea  pop     rsi
0x1800098eb  pop     rbp
0x1800098ec  pop     rbx
0x1800098ed  retn
```
