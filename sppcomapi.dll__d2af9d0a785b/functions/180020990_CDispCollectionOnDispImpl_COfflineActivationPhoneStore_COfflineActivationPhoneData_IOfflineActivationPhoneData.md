# CDispCollectionOnDispImpl<COfflineActivationPhoneStore,COfflineActivationPhoneData,IOfflineActivationPhoneData,IOfflineActivationPhoneList,&_GUID const IID_IOfflineActivationPhoneList,1,0,&_GUID const LIBID_SppComApiLib>::_InternalQueryInterface(_GUID const &,void * *)

- ea: `0x180020990`
- end: `0x180020a10`
- name: `?_InternalQueryInterface@?$CDispCollectionOnDispImpl@VCOfflineActivationPhoneStore@@VCOfflineActivationPhoneData@@UIOfflineActivationPhoneData@@UIOfflineActivationPhoneList@@$1?IID_IOfflineActivationPhoneList@@3U_GUID@@B$00$0A@$1?LIBID_SppComApiLib@@3U6@B@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `128`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180003520`
- `0x180020990`
- `0x18003d010`

## pseudocode

```c
__int64 __fastcall CDispCollectionOnDispImpl<COfflineActivationPhoneStore,COfflineActivationPhoneData,IOfflineActivationPhoneData,IOfflineActivationPhoneList,&_GUID const IID_IOfflineActivationPhoneList,1,0,&_GUID const LIBID_SppComApiLib>::_InternalQueryInterface(
        __int64 a1,
        _QWORD *a2,
        _QWORD *a3)
{
  __int64 v5; // rcx
  unsigned int v6; // ecx

  if ( !a3 )
  {
    v5 = 2147500035LL;
LABEL_9:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v5);
    return v6;
  }
  if ( (*a2 != *(_QWORD *)&GUID_00020400_0000_0000_c000_000000000046.Data1
     || a2[1] != *(_QWORD *)GUID_00020400_0000_0000_c000_000000000046.Data4)
    && (*a2 != *(_QWORD *)&GUID_d2dc9cb6_6181_4d16_b69f_c8022cc417c0.Data1
     || a2[1] != *(_QWORD *)GUID_d2dc9cb6_6181_4d16_b69f_c8022cc417c0.Data4) )
  {
    v5 = 2147500034LL;
    *a3 = 0;
    goto LABEL_9;
  }
  (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
  v6 = 0;
  *a3 = a1;
  return v6;
}

```

## disassembly

```asm
0x180020990  mov     [rsp+arg_0], rbx
0x180020995  push    rdi
0x180020996  sub     rsp, 20h
0x18002099a  mov     rdi, r8
0x18002099d  mov     rbx, rcx
0x1800209a0  test    r8, r8
0x1800209a3  jnz     short loc_1800209AC
0x1800209a5  mov     ecx, 80004003h
0x1800209aa  jmp     short loc_1800209FD
0x1800209ac  mov     rax, [rdx]
0x1800209af  cmp     rax, qword ptr cs:_GUID_00020400_0000_0000_c000_000000000046.Data1
0x1800209b6  jnz     short loc_1800209D8
0x1800209b8  mov     rax, [rdx+8]
0x1800209bc  cmp     rax, qword ptr cs:_GUID_00020400_0000_0000_c000_000000000046.Data4
0x1800209c3  jnz     short loc_1800209D8
0x1800209c5  mov     rax, [rcx]
0x1800209c8  mov     rax, [rax+8]
0x1800209cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800209d1  xor     ecx, ecx
0x1800209d3  mov     [rdi], rbx
0x1800209d6  jmp     short loc_180020A02
0x1800209d8  mov     rax, [rdx]
0x1800209db  cmp     rax, qword ptr cs:_GUID_d2dc9cb6_6181_4d16_b69f_c8022cc417c0.Data1
0x1800209e2  jnz     short loc_1800209F1
0x1800209e4  mov     rax, [rdx+8]
0x1800209e8  cmp     rax, qword ptr cs:_GUID_d2dc9cb6_6181_4d16_b69f_c8022cc417c0.Data4
0x1800209ef  jz      short loc_1800209C5
0x1800209f1  mov     ecx, 80004002h
0x1800209f6  mov     qword ptr [r8], 0
0x1800209fd  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180020a02  mov     rbx, [rsp+28h+arg_0]
0x180020a07  mov     eax, ecx
0x180020a09  add     rsp, 20h
0x180020a0d  pop     rdi
0x180020a0e  retn
```
