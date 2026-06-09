# ATL::CComTypeInfoHolder::GetTypeInfo(uint,ulong,ITypeInfo * *)

- ea: `0x180007304`
- end: `0x18000736f`
- name: `?GetTypeInfo@CComTypeInfoHolder@ATL@@QEAAJIKPEAPEAUITypeInfo@@@Z`
- size: `107`
- prototype: `__int64 __fastcall(ATL::CComTypeInfoHolder *__hidden this, unsigned int, unsigned int, struct ITypeInfo **)`
- caller_count: `20`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800072f0`
- `0x180008480`
- `0x180008ed0`
- `0x18000a630`
- `0x18000b990`
- `0x18000d180`
- `0x18000f5d0`
- `0x180010430`
- `0x180011d20`
- `0x180011d40`
- `0x180011d60`
- `0x180011d80`
- `0x180011da0`
- `0x180014c10`
- `0x180015840`
- `0x1800167a0`
- `0x1800178d0`
- `0x1800186f0`
- `0x180019080`
- `0x180019b00`

## callees

- `0x180007044`
- `0x180007304`
- `0x180020010`

## pseudocode

```c
__int64 __fastcall ATL::CComTypeInfoHolder::GetTypeInfo(
        ATL::CComTypeInfoHolder *this,
        int a2,
        LCID a3,
        struct ITypeInfo **a4)
{
  unsigned int TI; // ecx
  __int64 v8; // rdx

  if ( a2 )
    return 2147614731LL;
  if ( a4 )
  {
    TI = 0;
    if ( !*((_QWORD *)this + 3) )
      TI = ATL::CComTypeInfoHolder::GetTI(this, a3);
    *a4 = (struct ITypeInfo *)*((_QWORD *)this + 3);
    v8 = *((_QWORD *)this + 3);
    if ( v8 )
    {
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v8 + 8LL))(*((_QWORD *)this + 3));
      return 0;
    }
  }
  else
  {
    return (unsigned int)-2147467261;
  }
  return TI;
}

```

## disassembly

```asm
0x180007304  mov     [rsp+arg_0], rbx
0x180007309  push    rdi
0x18000730a  sub     rsp, 20h
0x18000730e  mov     rdi, r9
0x180007311  mov     rbx, rcx
0x180007314  test    edx, edx
0x180007316  jz      short loc_18000731F
0x180007318  mov     eax, 8002000Bh
0x18000731d  jmp     short loc_180007363
0x18000731f  test    rdi, rdi
0x180007322  jnz     short loc_18000732B
0x180007324  mov     ecx, 80004003h
0x180007329  jmp     short loc_180007361
0x18000732b  xor     ecx, ecx
0x18000732d  cmp     [rbx+18h], rcx
0x180007331  jnz     short loc_180007340
0x180007333  mov     edx, r8d; lcid
0x180007336  mov     rcx, rbx; this
0x180007339  call    ?GetTI@CComTypeInfoHolder@ATL@@QEAAJK@Z; ATL::CComTypeInfoHolder::GetTI(ulong)
0x18000733e  mov     ecx, eax
0x180007340  mov     rax, [rbx+18h]
0x180007344  mov     [rdi], rax
0x180007347  mov     rdx, [rbx+18h]
0x18000734b  test    rdx, rdx
0x18000734e  jz      short loc_180007361
0x180007350  mov     rax, [rdx]
0x180007353  mov     rcx, rdx
0x180007356  mov     rax, [rax+8]
0x18000735a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000735f  xor     ecx, ecx
0x180007361  mov     eax, ecx
0x180007363  mov     rbx, [rsp+28h+arg_0]
0x180007368  add     rsp, 20h
0x18000736c  pop     rdi
0x18000736d  retn
```
