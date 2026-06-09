# DirectUI::ElementProviderManager::GetProvider<IRawElementProviderSimple>(DirectUI::Element *,DirectUI::InvokeHelper *,IRawElementProviderSimple * *)

- ea: `0x1800689a0`
- end: `0x180068ac2`
- name: `??$GetProvider@UIRawElementProviderSimple@@@ElementProviderManager@DirectUI@@SAJPEAVElement@1@PEAVInvokeHelper@1@PEAPEAUIRawElementProviderSimple@@@Z`
- size: `290`
- prototype: `__int64 __fastcall(struct DirectUI::Element *, struct DirectUI::InvokeHelper *, _QWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180068ac8`

## callees

- `0x1800689a0`
- `0x180078010`

## import_xrefs

- `DUI70!?Create@ElementProvider@DirectUI@@SAJPEAVElement@2@PEAVInvokeHelper@2@PEAPEAV12@@Z` at `0x180068a6c`
- `DUI70!?Create@ElementProvider@DirectUI@@SAJPEAVElement@2@PEAVInvokeHelper@2@PEAPEAV12@@Z` at `0x180068a6c`
- `DUI70!?Create@HWNDElementProvider@DirectUI@@SAJPEAVHWNDElement@2@PEAVInvokeHelper@2@PEAPEAV12@@Z` at `0x180068a64`
- `DUI70!?Create@HWNDElementProvider@DirectUI@@SAJPEAVHWNDElement@2@PEAVInvokeHelper@2@PEAPEAV12@@Z` at `0x180068a64`
- `DUI70!?Find@ElementProviderManager@DirectUI@@SAPEAVElementProvider@2@PEAVElement@2@@Z` at `0x1800689f5`
- `DUI70!?Find@ElementProviderManager@DirectUI@@SAPEAVElementProvider@2@PEAVElement@2@@Z` at `0x1800689f5`
- `DUI70!?GetClassInfoPtr@HWNDElement@DirectUI@@SAPEAUIClassInfo@2@XZ` at `0x180068a41`
- `DUI70!?GetClassInfoPtr@HWNDElement@DirectUI@@SAPEAUIClassInfo@2@XZ` at `0x180068a41`

## pseudocode

```c
__int64 __fastcall DirectUI::ElementProviderManager::GetProvider<IRawElementProviderSimple>(
        struct DirectUI::Element *a1,
        struct DirectUI::InvokeHelper *a2,
        _QWORD *a3)
{
  int v3; // ebx
  struct DirectUI::ElementProvider *v7; // rax
  __int64 v8; // rdi
  unsigned __int8 (__fastcall *v9)(__int64, __int64); // rbx
  __int64 ClassInfoPtr; // rax
  int v11; // eax
  struct DirectUI::ElementProvider *v13; // [rsp+40h] [rbp+8h] BYREF

  v3 = 0;
  *a3 = 0;
  if ( a1 )
  {
    v3 = (*(__int64 (__fastcall **)(struct DirectUI::Element *, GUID *))(*(_QWORD *)a1 + 304LL))(
           a1,
           &GUID_d6dd68d1_86fd_4332_8666_9abedea2d24c);
    if ( v3 == -2147467263 )
    {
      v7 = DirectUI::ElementProviderManager::Find(a1);
      v13 = v7;
      if ( v7 )
      {
LABEL_11:
        v3 = (**((__int64 (__fastcall ***)(__int64, GUID *, _QWORD *))v7 + 2))(
               (__int64)v7 + 16,
               &GUID_d6dd68d1_86fd_4332_8666_9abedea2d24c,
               a3);
        (*(void (__fastcall **)(char *))(*((_QWORD *)v13 + 2) + 16LL))((char *)v13 + 16);
        return (unsigned int)v3;
      }
      v3 = (*(__int64 (__fastcall **)(struct DirectUI::Element *, struct DirectUI::InvokeHelper *, struct DirectUI::ElementProvider **))(*(_QWORD *)a1 + 312LL))(
             a1,
             a2,
             &v13);
      if ( v3 == -2147467263 )
      {
        v8 = (*(__int64 (__fastcall **)(struct DirectUI::Element *))(*(_QWORD *)a1 + 280LL))(a1);
        v9 = *(unsigned __int8 (__fastcall **)(__int64, __int64))(*(_QWORD *)v8 + 80LL);
        ClassInfoPtr = DirectUI::HWNDElement::GetClassInfoPtr();
        if ( v9(v8, ClassInfoPtr) )
          v11 = DirectUI::HWNDElementProvider::Create(a1, a2, &v13);
        else
          v11 = DirectUI::ElementProvider::Create(a1, a2, &v13);
        v3 = v11;
      }
      if ( v3 >= 0 )
      {
        v7 = v13;
        goto LABEL_11;
      }
    }
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800689a0  mov     [rsp+arg_8], rbx
0x1800689a5  mov     [rsp+arg_10], rbp
0x1800689aa  push    rsi
0x1800689ab  push    rdi
0x1800689ac  push    r14
0x1800689ae  sub     rsp, 20h
0x1800689b2  xor     ebx, ebx
0x1800689b4  mov     qword ptr [r8], 0
0x1800689bb  mov     r14, r8
0x1800689be  mov     rbp, rdx
0x1800689c1  mov     rsi, rcx
0x1800689c4  test    rcx, rcx
0x1800689c7  jz      loc_180068AAD
0x1800689cd  mov     rax, [rcx]
0x1800689d0  lea     rdx, _GUID_d6dd68d1_86fd_4332_8666_9abedea2d24c
0x1800689d7  mov     rax, [rax+130h]
0x1800689de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800689e3  mov     edi, 80004001h
0x1800689e8  mov     ebx, eax
0x1800689ea  cmp     eax, edi
0x1800689ec  jnz     loc_180068AAD
0x1800689f2  mov     rcx, rsi
0x1800689f5  call    cs:__imp_?Find@ElementProviderManager@DirectUI@@SAPEAVElementProvider@2@PEAVElement@2@@Z; DirectUI::ElementProviderManager::Find(DirectUI::Element *)
0x1800689fb  mov     [rsp+38h+arg_0], rax
0x180068a00  test    rax, rax
0x180068a03  jnz     short loc_180068A7D
0x180068a05  mov     rax, [rsi]
0x180068a08  lea     r8, [rsp+38h+arg_0]
0x180068a0d  mov     rdx, rbp
0x180068a10  mov     rcx, rsi
0x180068a13  mov     rax, [rax+138h]
0x180068a1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068a1f  mov     ebx, eax
0x180068a21  cmp     eax, edi
0x180068a23  jnz     short loc_180068A74
0x180068a25  mov     rax, [rsi]
0x180068a28  mov     rcx, rsi
0x180068a2b  mov     rax, [rax+118h]
0x180068a32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068a37  mov     rdi, rax
0x180068a3a  mov     rcx, [rax]
0x180068a3d  mov     rbx, [rcx+50h]
0x180068a41  call    cs:__imp_?GetClassInfoPtr@HWNDElement@DirectUI@@SAPEAUIClassInfo@2@XZ; DirectUI::HWNDElement::GetClassInfoPtr(void)
0x180068a47  mov     rdx, rax
0x180068a4a  mov     rcx, rdi
0x180068a4d  mov     rax, rbx
0x180068a50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068a55  lea     r8, [rsp+38h+arg_0]
0x180068a5a  mov     rdx, rbp
0x180068a5d  mov     rcx, rsi
0x180068a60  test    al, al
0x180068a62  jz      short loc_180068A6C
0x180068a64  call    cs:__imp_?Create@HWNDElementProvider@DirectUI@@SAJPEAVHWNDElement@2@PEAVInvokeHelper@2@PEAPEAV12@@Z; DirectUI::HWNDElementProvider::Create(DirectUI::HWNDElement *,DirectUI::InvokeHelper *,DirectUI::HWNDElementProvider * *)
0x180068a6a  jmp     short loc_180068A72
0x180068a6c  call    cs:__imp_?Create@ElementProvider@DirectUI@@SAJPEAVElement@2@PEAVInvokeHelper@2@PEAPEAV12@@Z; DirectUI::ElementProvider::Create(DirectUI::Element *,DirectUI::InvokeHelper *,DirectUI::ElementProvider * *)
0x180068a72  mov     ebx, eax
0x180068a74  test    ebx, ebx
0x180068a76  js      short loc_180068AAD
0x180068a78  mov     rax, [rsp+38h+arg_0]
0x180068a7d  lea     rcx, [rax+10h]
0x180068a81  mov     r8, r14
0x180068a84  mov     rax, [rcx]
0x180068a87  lea     rdx, _GUID_d6dd68d1_86fd_4332_8666_9abedea2d24c
0x180068a8e  mov     rax, [rax]
0x180068a91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068a96  mov     rcx, [rsp+38h+arg_0]
0x180068a9b  mov     ebx, eax
0x180068a9d  add     rcx, 10h
0x180068aa1  mov     rax, [rcx]
0x180068aa4  mov     rax, [rax+10h]
0x180068aa8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068aad  mov     rbp, [rsp+38h+arg_10]
0x180068ab2  mov     eax, ebx
0x180068ab4  mov     rbx, [rsp+38h+arg_8]
0x180068ab9  add     rsp, 20h
0x180068abd  pop     r14
0x180068abf  pop     rdi
0x180068ac0  pop     rsi
0x180068ac1  retn
```
