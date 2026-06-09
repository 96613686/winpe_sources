# ATL::AtlInternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)

- ea: `0x1800019a0`
- end: `0x180001ae8`
- name: `?AtlInternalQueryInterface@ATL@@YAJPEAXPEBU_ATL_INTMAP_ENTRY@1@AEBU_GUID@@PEAPEAX@Z`
- size: `328`
- prototype: `__int64 __fastcall(void *, const struct ATL::_ATL_INTMAP_ENTRY *, const struct _GUID *, void **)`
- caller_count: `6`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180001310`
- `0x180001b80`
- `0x180005630`
- `0x180007390`
- `0x18000df20`
- `0x18000df40`

## callees

- `0x1800019a0`
- `0x180001af0`
- `0x180010010`

## pseudocode

```c
__int64 __fastcall ATL::AtlInternalQueryInterface(
        char *a1,
        const struct ATL::_ATL_INTMAP_ENTRY *a2,
        const struct _GUID *a3,
        char **a4)
{
  const struct ATL::_ATL_INTMAP_ENTRY *v6; // rbx
  _DWORD *v8; // rcx
  __int64 result; // rax
  int v10; // esi
  __int64 (__fastcall *v11)(char *, const struct _GUID *, char **, _QWORD); // rax
  char *v12; // rbx
  unsigned int (__fastcall *v13)(__int64); // rax
  char *v14; // rbx
  unsigned int (__fastcall *v15)(__int64); // rax

  v6 = a2;
  if ( !a1 || !a2 )
    return 2147942487LL;
  if ( !a4 )
    return 2147500035LL;
  *a4 = 0;
  if ( !*(_QWORD *)&a3->Data1 && *(_DWORD *)a3->Data4 == 192 && *(_DWORD *)&a3->Data4[4] == 1174405120 )
  {
    v14 = &a1[*((_QWORD *)a2 + 1)];
    v15 = *(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v14 + 8LL);
    if ( v15 == ATL::CComObjectCached<ATL::CComClassFactory>::AddRef )
      ATL::CComObjectCached<ATL::CComClassFactory>::AddRef((__int64)v14);
    else
      v15((__int64)v14);
    *a4 = v14;
    return 0;
  }
  if ( !*((_QWORD *)a2 + 2) )
    return 2147500034LL;
  while ( 1 )
  {
    v8 = *(_DWORD **)v6;
    if ( *(_QWORD *)v6 )
    {
      if ( *v8 != a3->Data1
        || v8[1] != *(_DWORD *)&a3->Data2
        || v8[2] != *(_DWORD *)a3->Data4
        || v8[3] != *(_DWORD *)&a3->Data4[4] )
      {
        goto LABEL_8;
      }
      v10 = 0;
    }
    else
    {
      v10 = 1;
    }
    v11 = (__int64 (__fastcall *)(char *, const struct _GUID *, char **, _QWORD))*((_QWORD *)v6 + 2);
    if ( v11 == (__int64 (__fastcall *)(char *, const struct _GUID *, char **, _QWORD))1 )
      break;
    result = v11(a1, a3, a4, *((_QWORD *)v6 + 1));
    if ( !(_DWORD)result || !v10 && (int)result < 0 )
      return result;
LABEL_8:
    v6 = (const struct ATL::_ATL_INTMAP_ENTRY *)((char *)v6 + 24);
    if ( !*((_QWORD *)v6 + 2) )
      return 2147500034LL;
  }
  v12 = &a1[*((_QWORD *)v6 + 1)];
  v13 = *(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v12 + 8LL);
  if ( v13 == ATL::CComObjectCached<ATL::CComClassFactory>::AddRef )
    ATL::CComObjectCached<ATL::CComClassFactory>::AddRef((__int64)v12);
  else
    v13((__int64)v12);
  *a4 = v12;
  return 0;
}

```

## disassembly

```asm
0x1800019a0  push    rbx
0x1800019a2  push    rdi
0x1800019a3  push    r14
0x1800019a5  push    r15
0x1800019a7  sub     rsp, 38h
0x1800019ab  mov     r14, r9
0x1800019ae  mov     rdi, r8
0x1800019b1  mov     rbx, rdx
0x1800019b4  mov     r15, rcx
0x1800019b7  test    rcx, rcx
0x1800019ba  jz      loc_18000371D
0x1800019c0  test    rdx, rdx
0x1800019c3  jz      loc_18000371D
0x1800019c9  test    r9, r9
0x1800019cc  jz      loc_1800036DA
0x1800019d2  mov     qword ptr [r9], 0
0x1800019d9  cmp     dword ptr [r8], 0
0x1800019dd  jz      loc_180001A88
0x1800019e3  cmp     qword ptr [rdx+10h], 0
0x1800019e8  mov     [rsp+58h+arg_0], rsi
0x1800019ed  jz      short loc_180001A0D
0x1800019ef  nop
0x1800019f0  mov     rcx, [rbx]
0x1800019f3  test    rcx, rcx
0x1800019f6  jz      loc_1800036E4
0x1800019fc  mov     eax, [rdi]
0x1800019fe  cmp     [rcx], eax
0x180001a00  jz      short loc_180001A22
0x180001a02  add     rbx, 18h
0x180001a06  cmp     qword ptr [rbx+10h], 0
0x180001a0b  jnz     short loc_1800019F0
0x180001a0d  mov     rsi, [rsp+58h+arg_0]
0x180001a12  mov     eax, 80004002h
0x180001a17  add     rsp, 38h
0x180001a1b  pop     r15
0x180001a1d  pop     r14
0x180001a1f  pop     rdi
0x180001a20  pop     rbx
0x180001a21  retn
0x180001a22  mov     eax, [rdi+4]
0x180001a25  cmp     [rcx+4], eax
0x180001a28  jnz     short loc_180001A02
0x180001a2a  mov     eax, [rdi+8]
0x180001a2d  cmp     [rcx+8], eax
0x180001a30  jnz     short loc_180001A02
0x180001a32  mov     eax, [rdi+0Ch]
0x180001a35  cmp     [rcx+0Ch], eax
0x180001a38  jnz     short loc_180001A02
0x180001a3a  xor     esi, esi
0x180001a3c  mov     rax, [rbx+10h]
0x180001a40  cmp     rax, 1
0x180001a44  jnz     loc_1800036EE
0x180001a4a  mov     rbx, [rbx+8]
0x180001a4e  lea     rcx, ?AddRef@?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@UEAAKXZ; ATL::CComObjectCached<ATL::CComClassFactory>::AddRef(void)
0x180001a55  add     rbx, r15
0x180001a58  mov     rax, [rbx]
0x180001a5b  mov     rax, [rax+8]
0x180001a5f  cmp     rax, rcx
0x180001a62  mov     rcx, rbx
0x180001a65  jz      short loc_180001A81
0x180001a67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001a6c  mov     [r14], rbx
0x180001a6f  xor     eax, eax
0x180001a71  mov     rsi, [rsp+58h+arg_0]
0x180001a76  add     rsp, 38h
0x180001a7a  pop     r15
0x180001a7c  pop     r14
0x180001a7e  pop     rdi
0x180001a7f  pop     rbx
0x180001a80  retn
0x180001a81  call    ?AddRef@?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@UEAAKXZ; ATL::CComObjectCached<ATL::CComClassFactory>::AddRef(void)
0x180001a86  jmp     short loc_180001A6C
0x180001a88  cmp     dword ptr [r8+4], 0
0x180001a8d  jnz     loc_1800019E3
0x180001a93  cmp     dword ptr [r8+8], 0C0h
0x180001a9b  jnz     loc_1800019E3
0x180001aa1  cmp     dword ptr [r8+0Ch], 46000000h
0x180001aa9  jnz     loc_1800019E3
0x180001aaf  mov     rbx, [rdx+8]
0x180001ab3  lea     rcx, ?AddRef@?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@UEAAKXZ; ATL::CComObjectCached<ATL::CComClassFactory>::AddRef(void)
0x180001aba  add     rbx, r15
0x180001abd  mov     rax, [rbx]
0x180001ac0  mov     rax, [rax+8]
0x180001ac4  cmp     rax, rcx
0x180001ac7  mov     rcx, rbx
0x180001aca  jnz     short loc_180001AE1
0x180001acc  call    ?AddRef@?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@UEAAKXZ; ATL::CComObjectCached<ATL::CComClassFactory>::AddRef(void)
0x180001ad1  mov     [r14], rbx
0x180001ad4  xor     eax, eax
0x180001ad6  add     rsp, 38h
0x180001ada  pop     r15
0x180001adc  pop     r14
0x180001ade  pop     rdi
0x180001adf  pop     rbx
0x180001ae0  retn
0x180001ae1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001ae6  jmp     short loc_180001AD1
0x1800036da  mov     eax, 80004003h
0x1800036df  jmp     loc_180001A76
0x1800036e4  mov     esi, 1
0x1800036e9  jmp     loc_180001A3C
0x1800036ee  mov     r9, [rbx+8]
0x1800036f2  mov     r8, r14
0x1800036f5  mov     rdx, rdi
0x1800036f8  mov     rcx, r15
0x1800036fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003700  test    eax, eax
0x180003702  jz      loc_180001A71
0x180003708  test    esi, esi
0x18000370a  jnz     loc_180001A02
0x180003710  test    eax, eax
0x180003712  js      loc_180001A71
0x180003718  jmp     loc_180001A02
0x18000371d  mov     eax, 80070057h
0x180003722  jmp     loc_180001A76
```
