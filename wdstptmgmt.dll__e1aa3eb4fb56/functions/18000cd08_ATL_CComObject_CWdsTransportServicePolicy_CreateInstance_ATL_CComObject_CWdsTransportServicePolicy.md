# ATL::CComObject<CWdsTransportServicePolicy>::CreateInstance(ATL::CComObject<CWdsTransportServicePolicy> * *)

- ea: `0x18000cd08`
- end: `0x18000cdea`
- name: `?CreateInstance@?$CComObject@VCWdsTransportServicePolicy@@@ATL@@SAJPEAPEAV12@@Z`
- size: `226`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000cdf0`

## callees

- `0x1800011bc`
- `0x18000452c`
- `0x18000c66c`
- `0x18000cd08`
- `0x180018310`
- `0x180018348`
- `0x180020010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CWdsTransportServicePolicy>::CreateInstance(CWdsTransportServicePolicy **a1)
{
  CWdsTransportServicePolicy **v1; // r14
  unsigned int v3; // esi
  CWdsTransportServicePolicy *v4; // rax
  CWdsTransportServicePolicy *v5; // rdi
  int v6; // eax
  int v7; // edx
  CWdsTransportServicePolicy *v9; // [rsp+50h] [rbp+18h]

  v1 = a1;
  if ( !a1 )
    return 2147500035LL;
  try
  {
    *a1 = 0;
    v3 = -2147024882;
    v4 = (CWdsTransportServicePolicy *)operator new(0xC8u);
    v5 = v4;
    if ( v4 )
    {
      CWdsTransportServicePolicy::CWdsTransportServicePolicy(v4);
      *(_QWORD *)v5 = &ATL::CComObject<CWdsTransportServicePolicy>::`vftable';
      (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    }
    v9 = v5;
  }
  catch ( ... )
  {
    v1 = a1;
    v3 = -2147024882;
    v5 = v9;
  }
  if ( v5 )
  {
    CWdsTransportServerComObjectRoot::InternalAddRef((CWdsTransportServicePolicy *)((char *)v5 + 8));
    v6 = ATL::CComSafeDeleteCriticalSection::Init((CWdsTransportServicePolicy *)((char *)v5 + 16));
    v7 = 0;
    if ( v6 < 0 )
      v7 = v6;
    v3 = 0;
    if ( v7 < 0 )
      v3 = v7;
    CWdsTransportServerComObjectRoot::InternalRelease((CWdsTransportServicePolicy *)((char *)v5 + 8));
    if ( v3 )
    {
      (*(void (__fastcall **)(CWdsTransportServicePolicy *, __int64))(*(_QWORD *)v5 + 232LL))(v5, 1);
      v5 = 0;
    }
  }
  *v1 = v5;
  return v3;
}

```

## disassembly

```asm
0x18000cd08  mov     [rsp+arg_18], rbx
0x18000cd0d  mov     [rsp+arg_0], rcx
0x18000cd12  push    rsi
0x18000cd13  push    rdi
0x18000cd14  push    r14
0x18000cd16  sub     rsp, 20h
0x18000cd1a  mov     r14, rcx
0x18000cd1d  test    rcx, rcx
0x18000cd20  jnz     short loc_18000CD2C
0x18000cd22  mov     eax, 80004003h
0x18000cd27  jmp     loc_18000CDDB
0x18000cd2c  and     qword ptr [rcx], 0
0x18000cd30  mov     esi, 8007000Eh
0x18000cd35  mov     [rsp+38h+arg_8], esi
0x18000cd39  and     [rsp+38h+arg_10], 0
0x18000cd3f  mov     ecx, 0C8h; Size
0x18000cd44  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000cd49  mov     rdi, rax
0x18000cd4c  test    rdi, rdi
0x18000cd4f  jz      short loc_18000CD76
0x18000cd51  mov     rcx, rax; this
0x18000cd54  call    ??0CWdsTransportServicePolicy@@QEAA@XZ; CWdsTransportServicePolicy::CWdsTransportServicePolicy(void)
0x18000cd59  lea     rax, ??_7?$CComObject@VCWdsTransportServicePolicy@@@ATL@@6B@; const ATL::CComObject<CWdsTransportServicePolicy>::`vftable'
0x18000cd60  mov     [rdi], rax
0x18000cd63  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000cd6a  mov     rax, [rcx]
0x18000cd6d  mov     rax, [rax+8]
0x18000cd71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cd76  mov     [rsp+38h+arg_10], rdi
0x18000cd7b  jmp     short loc_18000CD8B
0x18000cd7d  mov     r14, [rsp+38h+arg_0]
0x18000cd82  mov     esi, [rsp+38h+arg_8]
0x18000cd86  mov     rdi, [rsp+38h+arg_10]
0x18000cd8b  test    rdi, rdi
0x18000cd8e  jz      short loc_18000CDD6
0x18000cd90  lea     rcx, [rdi+8]; this
0x18000cd94  call    ?InternalAddRef@CWdsTransportServerComObjectRoot@@QEAAKXZ; CWdsTransportServerComObjectRoot::InternalAddRef(void)
0x18000cd99  lea     rcx, [rdi+10h]; this
0x18000cd9d  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x18000cda2  xor     edx, edx
0x18000cda4  test    eax, eax
0x18000cda6  cmovs   edx, eax
0x18000cda9  xor     esi, esi
0x18000cdab  test    edx, edx
0x18000cdad  cmovs   esi, edx
0x18000cdb0  lea     rcx, [rdi+8]; this
0x18000cdb4  call    ?InternalRelease@CWdsTransportServerComObjectRoot@@QEAAKXZ; CWdsTransportServerComObjectRoot::InternalRelease(void)
0x18000cdb9  test    esi, esi
0x18000cdbb  jz      short loc_18000CDD6
0x18000cdbd  mov     rdx, [rdi]
0x18000cdc0  mov     rax, [rdx+0E8h]
0x18000cdc7  mov     edx, 1
0x18000cdcc  mov     rcx, rdi
0x18000cdcf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cdd4  xor     edi, edi
0x18000cdd6  mov     [r14], rdi
0x18000cdd9  mov     eax, esi
0x18000cddb  mov     rbx, [rsp+38h+arg_18]
0x18000cde0  add     rsp, 20h
0x18000cde4  pop     r14
0x18000cde6  pop     rdi
0x18000cde7  pop     rsi
0x18000cde8  retn
```
