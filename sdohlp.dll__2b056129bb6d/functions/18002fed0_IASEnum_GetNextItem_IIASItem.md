# IASEnum::GetNextItem(IIASItem * *)

- ea: `0x18002fed0`
- end: `0x18003012e`
- name: `?GetNextItem@IASEnum@@UEAAJPEAPEAUIIASItem@@@Z`
- size: `606`
- prototype: `__int64 __fastcall(IASEnum *__hidden this, struct IIASItem **)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x180024cac`
- `0x18002844c`
- `0x18002cd00`
- `0x18002d278`
- `0x18002f14c`
- `0x18002fed0`
- `0x180042a80`
- `0x180054ffb`
- `0x180058010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18002ff0f`
- `OLEAUT32!__imp_VariantInit` at `0x18002ff0f`
- `OLEAUT32!__imp_VariantClear` at `0x180030119`
- `OLEAUT32!__imp_VariantClear` at `0x180030119`

## string_xrefs

- `0x180030030`: `IASSDOCreateItem %d failed with 0x%x`

## pseudocode

```c
__int64 __fastcall IASEnum::GetNextItem(IASEnum *this, struct IIASItem **a2)
{
  int v5; // ebx
  __int64 v6; // rax
  struct IUnknown *v7; // rdx
  VARIANTARG pvarg; // [rsp+30h] [rbp-20h] BYREF
  int v9; // [rsp+78h] [rbp+28h] BYREF
  struct ISdo *v10; // [rsp+80h] [rbp+30h] BYREF
  __int64 v11; // [rsp+88h] [rbp+38h] BYREF

  if ( !a2 )
    return 2147500035LL;
  *a2 = 0;
  v9 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  v5 = (*(__int64 (__fastcall **)(_QWORD, __int64, VARIANTARG *, int *))(**((_QWORD **)this + 14) + 24LL))(
         *((_QWORD *)this + 14),
         1,
         &pvarg,
         &v9);
  if ( !v5 )
  {
    if ( v9 )
    {
      v10 = 0;
      v11 = 0;
      v5 = (**(__int64 (__fastcall ***)(LONGLONG, GUID *, struct ISdo **))pvarg.llVal)(pvarg.llVal, &IID_ISdo, &v10);
      if ( v5 >= 0 )
      {
        v5 = IASSDOCreateItem(
               *((_DWORD *)this + 16),
               v10,
               *((struct ISdo **)this + 10),
               *((struct ISdoMachine **)this + 12),
               *((struct ISdoDictionaryOld **)this + 13),
               (__int64)a2);
        if ( v5 >= 0 )
        {
          if ( *((_DWORD *)this + 16) == 2 && *((_QWORD *)this + 11) )
          {
            v6 = _RTDynamicCast_0(*a2, 0, &IIASItem `RTTI Type Descriptor', &IASClient `RTTI Type Descriptor', 0);
            v7 = (struct IUnknown *)*((_QWORD *)this + 11);
            if ( *(struct IUnknown **)(v6 + 120) != v7 )
              ATL::AtlComPtrAssign((struct IUnknown **)(v6 + 120), v7);
            v5 = 0;
          }
        }
        else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
               && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
               && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
        {
          WppDbgPrint("IASSDOCreateItem %d failed with 0x%x");
          WPP_SF_sdD(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_466d9b0081703e3858f1044ece548e82_Traceguids);
        }
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
             && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
             && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
      {
        WppDbgPrint("QI(ISdo) failed with 0x%x");
        WPP_SF_sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          12,
          (unsigned int)WPP_466d9b0081703e3858f1044ece548e82_Traceguids,
          (unsigned int)"NPSSDO",
          v5);
      }
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v10);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v11);
      goto LABEL_26;
    }
LABEL_22:
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    {
      WppDbgPrint("m_pEnum->Next failed with 0x%x");
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        14,
        (unsigned int)WPP_466d9b0081703e3858f1044ece548e82_Traceguids,
        (unsigned int)"NPSSDO",
        v5);
    }
    goto LABEL_26;
  }
  if ( v5 != 1 )
    goto LABEL_22;
LABEL_26:
  VariantClear(&pvarg);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18002fed0  mov     [rsp-18h+arg_0], rbx
0x18002fed5  push    rbp
0x18002fed6  push    rsi
0x18002fed7  push    rdi
0x18002fed8  mov     rbp, rsp
0x18002fedb  sub     rsp, 50h
0x18002fedf  mov     rsi, rdx
0x18002fee2  mov     rdi, rcx
0x18002fee5  test    rdx, rdx
0x18002fee8  jnz     short loc_18002FEF4
0x18002feea  mov     eax, 80004003h
0x18002feef  jmp     loc_180030121
0x18002fef4  xor     eax, eax
0x18002fef6  mov     qword ptr [rdx], 0
0x18002fefd  xorps   xmm0, xmm0
0x18002ff00  mov     qword ptr [rbp+pvarg+10h], rax
0x18002ff04  lea     rcx, [rbp+pvarg]; pvarg
0x18002ff08  mov     [rbp+arg_8], eax
0x18002ff0b  movups  xmmword ptr [rbp+pvarg], xmm0
0x18002ff0f  call    cs:__imp_VariantInit
0x18002ff15  mov     rcx, [rdi+70h]
0x18002ff19  lea     r9, [rbp+arg_8]
0x18002ff1d  lea     r8, [rbp+pvarg]
0x18002ff21  mov     edx, 1
0x18002ff26  mov     rax, [rcx]
0x18002ff29  mov     rax, [rax+18h]
0x18002ff2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ff32  mov     ebx, eax
0x18002ff34  test    eax, eax
0x18002ff36  jnz     loc_1800300B9
0x18002ff3c  cmp     [rbp+arg_8], eax
0x18002ff3f  jz      loc_1800300BE
0x18002ff45  mov     rcx, qword ptr [rbp+pvarg+8]
0x18002ff49  lea     r8, [rbp+arg_10]
0x18002ff4d  mov     [rbp+arg_10], 0
0x18002ff55  lea     rdx, IID_ISdo
0x18002ff5c  mov     [rbp+arg_18], 0
0x18002ff64  mov     rax, [rcx]
0x18002ff67  mov     rax, [rax]
0x18002ff6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ff6f  mov     ebx, eax
0x18002ff71  test    eax, eax
0x18002ff73  jns     short loc_18002FFE3
0x18002ff75  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ff7c  lea     rax, WPP_GLOBAL_Control
0x18002ff83  cmp     rcx, rax
0x18002ff86  jz      short loc_18002FFCC
0x18002ff88  cmp     byte ptr [rcx+19h], 2
0x18002ff8c  jb      short loc_18002FFCC
0x18002ff8e  test    dword ptr [rcx+1Ch], 400h
0x18002ff95  jz      short loc_18002FFCC
0x18002ff97  mov     edx, ebx
0x18002ff99  lea     rcx, aQiIsdoFailedWi; "QI(ISdo) failed with 0x%x"
0x18002ffa0  call    WppDbgPrint
0x18002ffa5  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ffac  lea     r9, aNpssdo; "NPSSDO"
0x18002ffb3  mov     edx, 0Ch
0x18002ffb8  mov     dword ptr [rsp+50h+var_30], ebx
0x18002ffbc  lea     r8, WPP_466d9b0081703e3858f1044ece548e82_Traceguids
0x18002ffc3  mov     rcx, [rcx+10h]
0x18002ffc7  call    WPP_SF_sd
0x18002ffcc  lea     rcx, [rbp+arg_10]
0x18002ffd0  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18002ffd5  lea     rcx, [rbp+arg_18]
0x18002ffd9  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18002ffde  jmp     loc_180030115
0x18002ffe3  mov     rax, [rdi+68h]
0x18002ffe7  mov     r9, [rdi+60h]
0x18002ffeb  mov     r8, [rdi+50h]
0x18002ffef  mov     rdx, [rbp+arg_10]
0x18002fff3  mov     ecx, [rdi+40h]
0x18002fff6  mov     [rsp+50h+var_28], rsi
0x18002fffb  mov     [rsp+50h+var_30], rax
0x180030000  call    ?IASSDOCreateItem@@YAJW4_ITEMTYPE@@PEAUISdo@@1PEAUISdoMachine@@PEAUISdoDictionaryOld@@PEAPEAUIIASItem@@@Z; IASSDOCreateItem(_ITEMTYPE,ISdo *,ISdo *,ISdoMachine *,ISdoDictionaryOld *,IIASItem * *)
0x180030005  mov     ebx, eax
0x180030007  test    eax, eax
0x180030009  jns     short loc_18003006B
0x18003000b  mov     rcx, cs:WPP_GLOBAL_Control
0x180030012  lea     rax, WPP_GLOBAL_Control
0x180030019  cmp     rcx, rax
0x18003001c  jz      short loc_18002FFCC
0x18003001e  cmp     byte ptr [rcx+19h], 2
0x180030022  jb      short loc_18002FFCC
0x180030024  test    dword ptr [rcx+1Ch], 400h
0x18003002b  jz      short loc_18002FFCC
0x18003002d  mov     edx, [rdi+40h]
0x180030030  lea     rcx, aIassdocreateit_0; "IASSDOCreateItem %d failed with 0x%x"
0x180030037  mov     r8d, ebx
0x18003003a  call    WppDbgPrint
0x18003003f  mov     rcx, cs:WPP_GLOBAL_Control
0x180030046  lea     r8, WPP_466d9b0081703e3858f1044ece548e82_Traceguids
0x18003004d  mov     eax, [rdi+40h]
0x180030050  mov     edx, 0Dh
0x180030055  mov     dword ptr [rsp+50h+var_28], ebx
0x180030059  mov     dword ptr [rsp+50h+var_30], eax
0x18003005d  mov     rcx, [rcx+10h]
0x180030061  call    WPP_SF_sdD
0x180030066  jmp     loc_18002FFCC
0x18003006b  cmp     dword ptr [rdi+40h], 2
0x18003006f  jnz     loc_18002FFCC
0x180030075  cmp     qword ptr [rdi+58h], 0
0x18003007a  jz      loc_18002FFCC
0x180030080  mov     rcx, [rsi]
0x180030083  lea     r9, ??_R0?AVIASClient@@@8; IASClient `RTTI Type Descriptor'
0x18003008a  lea     r8, ??_R0?AUIIASItem@@@8; IIASItem `RTTI Type Descriptor'
0x180030091  mov     dword ptr [rsp+50h+var_30], 0
0x180030099  xor     edx, edx
0x18003009b  call    __RTDynamicCast_0
0x1800300a0  mov     rdx, [rdi+58h]; struct IUnknown *
0x1800300a4  lea     rcx, [rax+78h]; struct IUnknown **
0x1800300a8  cmp     [rcx], rdx
0x1800300ab  jz      short loc_1800300B2
0x1800300ad  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x1800300b2  xor     ebx, ebx
0x1800300b4  jmp     loc_18002FFCC
0x1800300b9  cmp     ebx, 1
0x1800300bc  jz      short loc_180030115
0x1800300be  mov     rcx, cs:WPP_GLOBAL_Control
0x1800300c5  lea     rax, WPP_GLOBAL_Control
0x1800300cc  cmp     rcx, rax
0x1800300cf  jz      short loc_180030115
0x1800300d1  cmp     byte ptr [rcx+19h], 2
0x1800300d5  jb      short loc_180030115
0x1800300d7  test    dword ptr [rcx+1Ch], 400h
0x1800300de  jz      short loc_180030115
0x1800300e0  mov     edx, ebx
0x1800300e2  lea     rcx, aMPenumNextFail; "m_pEnum->Next failed with 0x%x"
0x1800300e9  call    WppDbgPrint
0x1800300ee  mov     rcx, cs:WPP_GLOBAL_Control
0x1800300f5  lea     r9, aNpssdo; "NPSSDO"
0x1800300fc  mov     edx, 0Eh
0x180030101  mov     dword ptr [rsp+50h+var_30], ebx
0x180030105  lea     r8, WPP_466d9b0081703e3858f1044ece548e82_Traceguids
0x18003010c  mov     rcx, [rcx+10h]
0x180030110  call    WPP_SF_sd
0x180030115  lea     rcx, [rbp+pvarg]; pvarg
0x180030119  call    cs:__imp_VariantClear
0x18003011f  mov     eax, ebx
0x180030121  mov     rbx, [rsp+50h+arg_0]
0x180030126  add     rsp, 50h
0x18003012a  pop     rdi
0x18003012b  pop     rsi
0x18003012c  pop     rbp
0x18003012d  retn
```
