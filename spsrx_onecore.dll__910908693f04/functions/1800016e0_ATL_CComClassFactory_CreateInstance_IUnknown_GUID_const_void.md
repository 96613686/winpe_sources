# ATL::CComClassFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x1800016e0`
- end: `0x180001755`
- name: `?CreateInstance@CComClassFactory@ATL@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `117`
- prototype: `__int64 __fastcall(ATL::CComClassFactory *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1800016e0`
- `0x180001760`
- `0x180010010`

## pseudocode

```c
__int64 __fastcall ATL::CComClassFactory::CreateInstance(
        ATL::CComClassFactory *this,
        struct IUnknown *a2,
        const struct _GUID *a3,
        void **a4)
{
  __int64 (__fastcall *v4)(__int64); // r11

  if ( !a4 )
    return 2147500035LL;
  *a4 = 0;
  if ( a2
    && (a3->Data1 || *(_DWORD *)&a3->Data2 || *(_DWORD *)a3->Data4 != 192 || *(_DWORD *)&a3->Data4[4] != 1174405120) )
  {
    return 2147746064LL;
  }
  v4 = (__int64 (__fastcall *)(__int64))*((_QWORD *)this + 8);
  if ( v4 == ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CRecoExt>>,ATL::CComCreator<ATL::CComAggObject<CRecoExt>>>::CreateInstance )
    return ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CRecoExt>>,ATL::CComCreator<ATL::CComAggObject<CRecoExt>>>::CreateInstance((__int64)a2);
  else
    return ((__int64 (__fastcall *)(struct IUnknown *, const struct _GUID *, void **))v4)(a2, a3, a4);
}

```

## disassembly

```asm
0x1800016e0  sub     rsp, 28h
0x1800016e4  mov     rax, r8
0x1800016e7  mov     r10, rdx
0x1800016ea  test    r9, r9
0x1800016ed  jz      short loc_18000174E
0x1800016ef  mov     qword ptr [r9], 0
0x1800016f6  test    rdx, rdx
0x1800016f9  jz      short loc_18000171C
0x1800016fb  cmp     dword ptr [r8], 0
0x1800016ff  jnz     short loc_180001747
0x180001701  cmp     dword ptr [r8+4], 0
0x180001706  jnz     short loc_180001747
0x180001708  cmp     dword ptr [r8+8], 0C0h
0x180001710  jnz     short loc_180001747
0x180001712  cmp     dword ptr [r8+0Ch], 46000000h
0x18000171a  jnz     short loc_180001747
0x18000171c  mov     r11, [rcx+40h]
0x180001720  mov     r8, r9
0x180001723  lea     rcx, ?CreateInstance@?$CComCreator2@V?$CComCreator@V?$CComObject@VCRecoExt@@@ATL@@@ATL@@V?$CComCreator@V?$CComAggObject@VCRecoExt@@@ATL@@@2@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CRecoExt>>,ATL::CComCreator<ATL::CComAggObject<CRecoExt>>>::CreateInstance(void *,_GUID const &,void * *)
0x18000172a  mov     rdx, rax
0x18000172d  cmp     r11, rcx
0x180001730  mov     rcx, r10
0x180001733  jnz     loc_1800036CC
0x180001739  add     rsp, 28h
0x18000173d  jmp     ?CreateInstance@?$CComCreator2@V?$CComCreator@V?$CComObject@VCRecoExt@@@ATL@@@ATL@@V?$CComCreator@V?$CComAggObject@VCRecoExt@@@ATL@@@2@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CRecoExt>>,ATL::CComCreator<ATL::CComAggObject<CRecoExt>>>::CreateInstance(void *,_GUID const &,void * *)
0x180001742  add     rsp, 28h
0x180001746  retn
0x180001747  mov     eax, 80040110h
0x18000174c  jmp     short loc_180001742
0x18000174e  mov     eax, 80004003h
0x180001753  jmp     short loc_180001742
0x1800036cc  mov     rax, r11
0x1800036cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800036d4  nop
0x1800036d5  jmp     loc_180001742
```
