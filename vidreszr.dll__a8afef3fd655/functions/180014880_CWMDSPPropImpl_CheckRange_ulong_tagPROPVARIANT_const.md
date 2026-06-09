# CWMDSPPropImpl::CheckRange(ulong,tagPROPVARIANT const &)

- ea: `0x180014880`
- end: `0x18001490d`
- name: `?CheckRange@CWMDSPPropImpl@@MEAAHKAEBUtagPROPVARIANT@@@Z`
- size: `141`
- prototype: `__int64 __fastcall(CWMDSPPropImpl *__hidden this, unsigned int, const struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x180014880`
- `0x1800150a0`
- `0x180016010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1800148f5`
- `OLEAUT32!__imp_SysFreeString` at `0x1800148f5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800148e8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800148e8`

## pseudocode

```c
__int64 __fastcall CWMDSPPropImpl::CheckRange(CWMDSPPropImpl *this, unsigned int a2, const struct tagPROPVARIANT *a3)
{
  unsigned int v7; // edi
  BSTR pv[3]; // [rsp+20h] [rbp-18h] BYREF

  if ( a3->vt == 8 )
    return 1;
  *(_OWORD *)pv = 0;
  WMDSPPropValFromVar((__int64)a3, pv);
  v7 = (*(__int64 (__fastcall **)(CWMDSPPropImpl *, _QWORD, BSTR *))(*(_QWORD *)this + 88LL))(this, a2, pv);
  if ( a3->vt == 8 )
  {
    SysFreeString(pv[0]);
  }
  else if ( a3->vt == 65 )
  {
    if ( pv[1] )
      CoTaskMemFree(pv[1]);
  }
  return v7;
}

```

## disassembly

```asm
0x180014880  mov     [rsp+arg_0], rbx
0x180014885  mov     [rsp+arg_8], rsi
0x18001488a  push    rdi
0x18001488b  sub     rsp, 30h
0x18001488f  cmp     word ptr [r8], 8
0x180014894  mov     rbx, r8
0x180014897  mov     esi, edx
0x180014899  mov     rdi, rcx
0x18001489c  jnz     short loc_1800148A5
0x18001489e  mov     eax, 1
0x1800148a3  jmp     short loc_1800148FD
0x1800148a5  xorps   xmm0, xmm0
0x1800148a8  lea     rdx, [rsp+38h+pv]
0x1800148ad  mov     rcx, rbx
0x1800148b0  movups  xmmword ptr [rsp+38h+pv], xmm0
0x1800148b5  call    WMDSPPropValFromVar
0x1800148ba  mov     rax, [rdi]
0x1800148bd  lea     r8, [rsp+38h+pv]
0x1800148c2  mov     edx, esi
0x1800148c4  mov     rcx, rdi
0x1800148c7  mov     rax, [rax+58h]
0x1800148cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800148d0  cmp     word ptr [rbx], 8
0x1800148d4  mov     edi, eax
0x1800148d6  jz      short loc_1800148F0
0x1800148d8  cmp     word ptr [rbx], 41h ; 'A'
0x1800148dc  jnz     short loc_1800148FB
0x1800148de  mov     rcx, [rsp+38h+pv+8]; pv
0x1800148e3  test    rcx, rcx
0x1800148e6  jz      short loc_1800148FB
0x1800148e8  call    cs:__imp_CoTaskMemFree
0x1800148ee  jmp     short loc_1800148FB
0x1800148f0  mov     rcx, [rsp+38h+pv]; bstrString
0x1800148f5  call    cs:__imp_SysFreeString
0x1800148fb  mov     eax, edi
0x1800148fd  mov     rbx, [rsp+38h+arg_0]
0x180014902  mov     rsi, [rsp+38h+arg_8]
0x180014907  add     rsp, 30h
0x18001490b  pop     rdi
0x18001490c  retn
```
