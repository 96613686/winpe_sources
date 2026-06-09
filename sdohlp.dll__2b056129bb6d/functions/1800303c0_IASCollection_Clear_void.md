# IASCollection::Clear(void)

- ea: `0x1800303c0`
- end: `0x180030534`
- name: `?Clear@IASCollection@@UEAAJXZ`
- size: `372`
- prototype: `__int64 __fastcall(IASCollection *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18002f2e0`

## callees

- `0x180024cac`
- `0x18002cd00`
- `0x1800303c0`
- `0x1800308e8`
- `0x180042a80`
- `0x180058010`

## string_xrefs

- `0x1800304ad`: `InternalRemoveItem failed with 0x%x`

## pseudocode

```c
__int64 __fastcall IASCollection::Clear(IASCollection *this)
{
  _QWORD *v1; // rax
  int v3; // ebx
  int v4; // edx
  IASCollection *v5; // rcx
  struct IIASItem *v7; // [rsp+40h] [rbp+8h] BYREF
  __int64 v8; // [rsp+48h] [rbp+10h] BYREF

  v1 = *(_QWORD **)this;
  v8 = 0;
  v7 = 0;
  v3 = ((__int64 (__fastcall *)(IASCollection *, __int64 *))v1[3])(this, &v8);
  if ( v3 >= 0 )
  {
    while ( 1 )
    {
      v3 = (*(__int64 (__fastcall **)(__int64, struct IIASItem **))(*(_QWORD *)v8 + 64LL))(v8, &v7);
      if ( v3 )
        break;
      v3 = IASCollection::InternalRemoveItem(v5, v7);
      if ( v3 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
        {
          WppDbgPrint("InternalRemoveItem failed with 0x%x");
          v4 = 21;
          goto LABEL_6;
        }
        goto LABEL_19;
      }
    }
    if ( v3 >= 0 )
    {
      v3 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 2) + 80LL))(*((_QWORD *)this + 2));
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
           && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    {
      WppDbgPrint("pEnum->GetNextItem returned 0x%x");
      v4 = 22;
      goto LABEL_6;
    }
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
         && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
  {
    WppDbgPrint("pColl->get_Enumerator returned 0x%x");
    v4 = 20;
LABEL_6:
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v4,
      (unsigned int)WPP_c2f236718121324f7e73e45b18920f9d_Traceguids,
      (unsigned int)"NPSSDO",
      v3);
  }
LABEL_19:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v7);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v8);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800303c0  mov     r11, rsp
0x1800303c3  mov     [r11+18h], rbx
0x1800303c7  push    rdi
0x1800303c8  sub     rsp, 30h
0x1800303cc  mov     rax, [rcx]
0x1800303cf  lea     rdx, [r11+10h]
0x1800303d3  mov     rdi, rcx
0x1800303d6  mov     qword ptr [r11+10h], 0
0x1800303de  mov     qword ptr [r11+8], 0
0x1800303e6  mov     rax, [rax+18h]
0x1800303ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800303ef  mov     ebx, eax
0x1800303f1  test    eax, eax
0x1800303f3  jns     short loc_18003045D
0x1800303f5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800303fc  lea     rax, WPP_GLOBAL_Control
0x180030403  cmp     rcx, rax
0x180030406  jz      loc_180030513
0x18003040c  cmp     byte ptr [rcx+19h], 2
0x180030410  jb      loc_180030513
0x180030416  test    dword ptr [rcx+1Ch], 400h
0x18003041d  jz      loc_180030513
0x180030423  mov     edx, ebx
0x180030425  lea     rcx, aPcollGetEnumer; "pColl->get_Enumerator returned 0x%x"
0x18003042c  call    WppDbgPrint
0x180030431  mov     edx, 14h
0x180030436  mov     rcx, cs:WPP_GLOBAL_Control
0x18003043d  lea     r9, aNpssdo; "NPSSDO"
0x180030444  lea     r8, WPP_c2f236718121324f7e73e45b18920f9d_Traceguids
0x18003044b  mov     [rsp+38h+var_18], ebx
0x18003044f  mov     rcx, [rcx+10h]
0x180030453  call    WPP_SF_sd
0x180030458  jmp     loc_180030513
0x18003045d  mov     rcx, [rsp+38h+arg_8]
0x180030462  lea     rdx, [rsp+38h+arg_0]
0x180030467  mov     rax, [rcx]
0x18003046a  mov     rax, [rax+40h]
0x18003046e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030473  mov     ebx, eax
0x180030475  test    eax, eax
0x180030477  jnz     short loc_1800304C3
0x180030479  mov     rdx, [rsp+38h+arg_0]; struct IIASItem *
0x18003047e  call    ?InternalRemoveItem@IASCollection@@QEAAJPEAUIIASItem@@@Z; IASCollection::InternalRemoveItem(IIASItem *)
0x180030483  mov     ebx, eax
0x180030485  test    eax, eax
0x180030487  jns     short loc_18003045D
0x180030489  mov     rcx, cs:WPP_GLOBAL_Control
0x180030490  lea     rax, WPP_GLOBAL_Control
0x180030497  cmp     rcx, rax
0x18003049a  jz      short loc_180030513
0x18003049c  cmp     byte ptr [rcx+19h], 2
0x1800304a0  jb      short loc_180030513
0x1800304a2  test    dword ptr [rcx+1Ch], 400h
0x1800304a9  jz      short loc_180030513
0x1800304ab  mov     edx, ebx
0x1800304ad  lea     rcx, aInternalremove; "InternalRemoveItem failed with 0x%x"
0x1800304b4  call    WppDbgPrint
0x1800304b9  mov     edx, 15h
0x1800304be  jmp     loc_180030436
0x1800304c3  test    ebx, ebx
0x1800304c5  jns     short loc_180030501
0x1800304c7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800304ce  lea     rax, WPP_GLOBAL_Control
0x1800304d5  cmp     rcx, rax
0x1800304d8  jz      short loc_180030513
0x1800304da  cmp     byte ptr [rcx+19h], 2
0x1800304de  jb      short loc_180030513
0x1800304e0  test    dword ptr [rcx+1Ch], 400h
0x1800304e7  jz      short loc_180030513
0x1800304e9  mov     edx, ebx
0x1800304eb  lea     rcx, aPenumGetnextit; "pEnum->GetNextItem returned 0x%x"
0x1800304f2  call    WppDbgPrint
0x1800304f7  mov     edx, 16h
0x1800304fc  jmp     loc_180030436
0x180030501  mov     rcx, [rdi+10h]
0x180030505  mov     rax, [rcx]
0x180030508  mov     rax, [rax+50h]
0x18003050c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030511  mov     ebx, eax
0x180030513  lea     rcx, [rsp+38h+arg_0]
0x180030518  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18003051d  lea     rcx, [rsp+38h+arg_8]
0x180030522  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180030527  mov     eax, ebx
0x180030529  mov     rbx, [rsp+38h+arg_10]
0x18003052e  add     rsp, 30h
0x180030532  pop     rdi
0x180030533  retn
```
