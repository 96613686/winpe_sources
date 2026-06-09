# ATL::CComClassFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x140003630`
- end: `0x140003692`
- name: `?CreateInstance@CComClassFactory@ATL@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `98`
- prototype: `__int64 __fastcall(unsigned int (__fastcall **this)(struct IUnknown *, const struct _GUID *, void **), struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140003630`
- `0x140007010`

## pseudocode

```c
__int64 __fastcall ATL::CComClassFactory::CreateInstance(
        unsigned int (__fastcall **this)(struct IUnknown *, const struct _GUID *, void **),
        struct IUnknown *a2,
        const struct _GUID *a3,
        void **a4)
{
  unsigned int v5; // r8d

  v5 = -2147467261;
  if ( a4 )
  {
    *a4 = 0;
    if ( a2
      && (a3->Data1 || *(_DWORD *)&a3->Data2 || *(_DWORD *)a3->Data4 != 192 || *(_DWORD *)&a3->Data4[4] != 1174405120) )
    {
      return (unsigned int)-2147221232;
    }
    else
    {
      return this[8](a2, a3, a4);
    }
  }
  return v5;
}

```

## disassembly

```asm
0x140003630  sub     rsp, 28h
0x140003634  mov     r11, rcx
0x140003637  mov     rax, r8
0x14000363a  xor     ecx, ecx
0x14000363c  mov     r10, rdx
0x14000363f  mov     r8d, 80004003h
0x140003645  test    r9, r9
0x140003648  jz      short loc_14000368A
0x14000364a  mov     [r9], rcx
0x14000364d  test    rdx, rdx
0x140003650  jz      short loc_140003675
0x140003652  cmp     [rax], ecx
0x140003654  jnz     short loc_14000366D
0x140003656  cmp     [rax+4], ecx
0x140003659  jnz     short loc_14000366D
0x14000365b  cmp     dword ptr [rax+8], 0C0h
0x140003662  jnz     short loc_14000366D
0x140003664  cmp     dword ptr [rax+0Ch], 46000000h
0x14000366b  jz      short loc_140003675
0x14000366d  mov     r8d, 80040110h
0x140003673  jmp     short loc_14000368A
0x140003675  mov     rdx, rax
0x140003678  mov     r8, r9
0x14000367b  mov     rax, [r11+40h]
0x14000367f  mov     rcx, r10
0x140003682  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003687  mov     r8d, eax
0x14000368a  mov     eax, r8d
0x14000368d  add     rsp, 28h
0x140003691  retn
```
