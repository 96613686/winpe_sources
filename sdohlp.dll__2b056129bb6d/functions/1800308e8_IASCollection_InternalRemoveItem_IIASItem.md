# IASCollection::InternalRemoveItem(IIASItem *)

- ea: `0x1800308e8`
- end: `0x1800309f1`
- name: `?InternalRemoveItem@IASCollection@@QEAAJPEAUIIASItem@@@Z`
- size: `265`
- prototype: `__int64 __fastcall(IASCollection *__hidden this, struct IIASItem *)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800303c0`
- `0x180030b00`

## callees

- `0x180024cac`
- `0x18002cd00`
- `0x1800308e8`
- `0x180042a80`
- `0x180058010`

## string_xrefs

- `0x1800309ab`: `pInternal->InternalRemove failed with 0x%x -- cannot remove item`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall IASCollection::InternalRemoveItem(IASCollection *this, struct IIASItem *a2)
{
  int v3; // ebx
  int v4; // edx
  IASCollection *v5; // [rsp+40h] [rbp+8h] BYREF

  v5 = this;
  if ( !a2 )
    return 2147500035LL;
  v5 = 0;
  v3 = (**(__int64 (__fastcall ***)(struct IIASItem *, GUID *, IASCollection **))a2)(a2, &IID_IIASItemInternal, &v5);
  if ( v3 >= 0 )
  {
    v3 = (*(__int64 (__fastcall **)(IASCollection *))(*(_QWORD *)v5 + 24LL))(v5);
    if ( v3 >= 0
      || WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) == 0 )
    {
      goto LABEL_14;
    }
    WppDbgPrint("pInternal->InternalRemove failed with 0x%x -- cannot remove item");
    v4 = 15;
  }
  else
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) == 0 )
    {
      goto LABEL_14;
    }
    WppDbgPrint("pItem->QI(IID_IIASItemInternal) failed with 0x%x");
    v4 = 14;
  }
  WPP_SF_sd(
    *((_QWORD *)WPP_GLOBAL_Control + 2),
    v4,
    (unsigned int)WPP_c2f236718121324f7e73e45b18920f9d_Traceguids,
    (unsigned int)"NPSSDO",
    v3);
LABEL_14:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v5);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800308e8  mov     [rsp+arg_0], rcx
0x1800308ed  push    rbx
0x1800308ee  sub     rsp, 30h
0x1800308f2  mov     r9, rdx
0x1800308f5  test    rdx, rdx
0x1800308f8  jnz     short loc_180030904
0x1800308fa  mov     eax, 80004003h
0x1800308ff  jmp     loc_1800309EB
0x180030904  mov     [rsp+38h+arg_0], 0
0x18003090d  mov     rax, [rdx]
0x180030910  lea     r8, [rsp+38h+arg_0]
0x180030915  lea     rdx, IID_IIASItemInternal
0x18003091c  mov     rcx, r9
0x18003091f  mov     rax, [rax]
0x180030922  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030927  mov     ebx, eax
0x180030929  test    eax, eax
0x18003092b  jns     short loc_180030970
0x18003092d  lea     rcx, WPP_GLOBAL_Control
0x180030934  mov     rax, cs:WPP_GLOBAL_Control
0x18003093b  cmp     rax, rcx
0x18003093e  jz      loc_1800309DF
0x180030944  cmp     byte ptr [rax+19h], 2
0x180030948  jb      loc_1800309DF
0x18003094e  test    dword ptr [rax+1Ch], 400h
0x180030955  jz      loc_1800309DF
0x18003095b  mov     edx, ebx
0x18003095d  lea     rcx, aPitemQiIidIias_2; "pItem->QI(IID_IIASItemInternal) failed "...
0x180030964  call    WppDbgPrint
0x180030969  mov     edx, 0Eh
0x18003096e  jmp     short loc_1800309BC
0x180030970  mov     rcx, [rsp+38h+arg_0]
0x180030975  mov     rax, [rcx]
0x180030978  mov     rax, [rax+18h]
0x18003097c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030981  mov     ebx, eax
0x180030983  test    eax, eax
0x180030985  jns     short loc_1800309DF
0x180030987  lea     rcx, WPP_GLOBAL_Control
0x18003098e  mov     rax, cs:WPP_GLOBAL_Control
0x180030995  cmp     rax, rcx
0x180030998  jz      short loc_1800309DF
0x18003099a  cmp     byte ptr [rax+19h], 2
0x18003099e  jb      short loc_1800309DF
0x1800309a0  test    dword ptr [rax+1Ch], 400h
0x1800309a7  jz      short loc_1800309DF
0x1800309a9  mov     edx, ebx
0x1800309ab  lea     rcx, aPinternalInter; "pInternal->InternalRemove failed with 0"...
0x1800309b2  call    WppDbgPrint
0x1800309b7  mov     edx, 0Fh
0x1800309bc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800309c3  mov     [rsp+38h+var_18], ebx
0x1800309c7  lea     r9, aNpssdo; "NPSSDO"
0x1800309ce  lea     r8, WPP_c2f236718121324f7e73e45b18920f9d_Traceguids
0x1800309d5  mov     rcx, [rcx+10h]
0x1800309d9  call    WPP_SF_sd
0x1800309de  nop
0x1800309df  lea     rcx, [rsp+38h+arg_0]
0x1800309e4  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800309e9  mov     eax, ebx
0x1800309eb  add     rsp, 30h
0x1800309ef  pop     rbx
0x1800309f0  retn
```
