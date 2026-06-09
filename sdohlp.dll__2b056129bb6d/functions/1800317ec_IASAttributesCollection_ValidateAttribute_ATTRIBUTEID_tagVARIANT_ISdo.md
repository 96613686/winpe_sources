# IASAttributesCollection::ValidateAttribute(_ATTRIBUTEID,tagVARIANT,ISdo *)

- ea: `0x1800317ec`
- end: `0x180031a59`
- name: `?ValidateAttribute@IASAttributesCollection@@QEAAJW4_ATTRIBUTEID@@UtagVARIANT@@PEAUISdo@@@Z`
- size: `621`
- prototype: `__int64 __fastcall(IASAttributesCollection *__hidden this, enum _ATTRIBUTEID, struct tagVARIANT *__struct_ptr, struct ISdo *)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x180031200`

## callees

- `0x180024cac`
- `0x18002844c`
- `0x18002cd00`
- `0x1800317ec`
- `0x180031a60`
- `0x180031ea8`
- `0x180031f38`
- `0x180042a80`
- `0x180058010`

## string_xrefs

- `0x180031870`: `IASSDOCreateItem(IASSERVICE) failed with 0x%x`
- `0x1800318ee`: `pItem->QI(IID_IIASService) failed with 0x%x`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall IASAttributesCollection::ValidateAttribute(
        IASAttributesCollection *this,
        enum _ATTRIBUTEID a2,
        struct tagVARIANT *a3,
        struct ISdo *a4)
{
  int v8; // eax
  char v9; // bl
  IASAttributesCollection *v10; // rcx
  int v11; // ebx
  struct tagVARIANT *v12; // r8
  int v13; // edx
  int v14; // eax
  struct IIASService *v16; // [rsp+20h] [rbp-68h]
  _QWORD v17[2]; // [rsp+30h] [rbp-58h] BYREF
  struct tagVARIANT v18; // [rsp+40h] [rbp-48h] BYREF
  struct IIASService *v19; // [rsp+90h] [rbp+8h] BYREF

  v17[0] = 0;
  v19 = 0;
  v8 = IASSDOCreateItem(
         1,
         *((struct ISdo **)this + 4),
         *((struct ISdo **)this + 4),
         *((struct ISdoMachine **)this + 5),
         *((struct ISdoDictionaryOld **)this + 6),
         (__int64)v17);
  v9 = v8;
  if ( v8 < 0
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
  {
    WppDbgPrint("IASSDOCreateItem(IASSERVICE) failed with 0x%x");
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      11,
      (unsigned int)WPP_4b583fe665f33bdd9967a3ff271ecbd4_Traceguids,
      (unsigned int)"NPSSDO",
      v9);
  }
  v11 = (**(__int64 (__fastcall ***)(_QWORD, GUID *, struct IIASService **))v17[0])(v17[0], &IID_IIASService, &v19);
  if ( v11 >= 0 )
  {
    v14 = *((_DWORD *)this + 32);
    if ( v14 == 9 )
    {
      v11 = IASAttributesCollection::ValidateRAPAttribute(this, a2, v12, a4, v16);
      if ( v11 < 0
        && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
      {
        WppDbgPrint("ValidateRAPAttributes failed with 0x%x");
        v13 = 13;
        goto LABEL_28;
      }
    }
    else if ( v14 == 10 )
    {
      v18 = *a3;
      v11 = IASAttributesCollection::ValidateCRPAttribute(v10, a2, &v18, a4, v19);
      if ( v11 < 0
        && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
      {
        WppDbgPrint("ValidateCRPAttributes failed with 0x%x");
        v13 = 14;
        goto LABEL_28;
      }
    }
    else
    {
      v11 = IASAttributesCollection::ValidateIPFilterAttribute(v10, a2);
      if ( v11 < 0
        && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
      {
        WppDbgPrint("ValidateIPFilterAttributes failed with 0x%x");
        v13 = 15;
        goto LABEL_28;
      }
    }
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
         && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
  {
    WppDbgPrint("pItem->QI(IID_IIASService) failed with 0x%x");
    v13 = 12;
LABEL_28:
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v13,
      (unsigned int)WPP_4b583fe665f33bdd9967a3ff271ecbd4_Traceguids,
      (unsigned int)"NPSSDO",
      v11);
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v19);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v17);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1800317ec  mov     r11, rsp
0x1800317ef  mov     [r11+10h], rbx
0x1800317f3  mov     [r11+18h], rbp
0x1800317f7  push    rsi
0x1800317f8  push    rdi
0x1800317f9  push    r12
0x1800317fb  push    r13
0x1800317fd  push    r14
0x1800317ff  sub     rsp, 60h
0x180031803  mov     rbp, r9
0x180031806  mov     r14, r8
0x180031809  mov     esi, edx
0x18003180b  mov     rdi, rcx
0x18003180e  mov     qword ptr [r11-58h], 0
0x180031816  mov     qword ptr [r11+8], 0
0x18003181e  mov     rdx, [rcx+20h]
0x180031822  lea     rax, [r11-58h]
0x180031826  mov     [r11-60h], rax
0x18003182a  mov     rax, [rcx+30h]
0x18003182e  mov     [r11-68h], rax
0x180031832  mov     r9, [rcx+28h]
0x180031836  mov     r8, rdx
0x180031839  mov     ecx, 1
0x18003183e  call    ?IASSDOCreateItem@@YAJW4_ITEMTYPE@@PEAUISdo@@1PEAUISdoMachine@@PEAUISdoDictionaryOld@@PEAPEAUIIASItem@@@Z; IASSDOCreateItem(_ITEMTYPE,ISdo *,ISdo *,ISdoMachine *,ISdoDictionaryOld *,IIASItem * *)
0x180031843  mov     ebx, eax
0x180031845  mov     r12d, 400h
0x18003184b  lea     r13, WPP_GLOBAL_Control
0x180031852  test    eax, eax
0x180031854  jns     short loc_1800318A3
0x180031856  mov     rcx, cs:WPP_GLOBAL_Control
0x18003185d  cmp     rcx, r13
0x180031860  jz      short loc_1800318A3
0x180031862  cmp     byte ptr [rcx+19h], 2
0x180031866  jb      short loc_1800318A3
0x180031868  test    [rcx+1Ch], r12d
0x18003186c  jz      short loc_1800318A3
0x18003186e  mov     edx, eax
0x180031870  lea     rcx, aIassdocreateit; "IASSDOCreateItem(IASSERVICE) failed wit"...
0x180031877  call    WppDbgPrint
0x18003187c  mov     edx, 0Bh
0x180031881  mov     dword ptr [rsp+88h+var_68], ebx; struct IIASService *
0x180031885  lea     r9, aNpssdo; "NPSSDO"
0x18003188c  lea     r8, WPP_4b583fe665f33bdd9967a3ff271ecbd4_Traceguids
0x180031893  mov     rcx, cs:WPP_GLOBAL_Control
0x18003189a  mov     rcx, [rcx+10h]
0x18003189e  call    WPP_SF_sd
0x1800318a3  mov     rcx, [rsp+88h+var_58]
0x1800318a8  mov     rax, [rcx]
0x1800318ab  lea     r8, [rsp+88h+arg_0]
0x1800318b3  lea     rdx, IID_IIASService
0x1800318ba  mov     rax, [rax]
0x1800318bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800318c2  mov     ebx, eax
0x1800318c4  test    eax, eax
0x1800318c6  jns     short loc_180031904
0x1800318c8  mov     rax, cs:WPP_GLOBAL_Control
0x1800318cf  cmp     rax, r13
0x1800318d2  jz      loc_180031A26
0x1800318d8  cmp     byte ptr [rax+19h], 2
0x1800318dc  jb      loc_180031A26
0x1800318e2  test    [rax+1Ch], r12d
0x1800318e6  jz      loc_180031A26
0x1800318ec  mov     edx, ebx
0x1800318ee  lea     rcx, aPitemQiIidIias_0; "pItem->QI(IID_IIASService) failed with "...
0x1800318f5  call    WppDbgPrint
0x1800318fa  mov     edx, 0Ch
0x1800318ff  jmp     loc_180031A03
0x180031904  mov     eax, [rdi+80h]
0x18003190a  mov     edx, esi; enum _ATTRIBUTEID
0x18003190c  cmp     eax, 9
0x18003190f  jnz     short loc_180031962
0x180031911  mov     r9, rbp; struct ISdo *
0x180031914  mov     rcx, rdi; this
0x180031917  call    ?ValidateRAPAttribute@IASAttributesCollection@@QEAAJW4_ATTRIBUTEID@@UtagVARIANT@@PEAUISdo@@PEAUIIASService@@@Z; IASAttributesCollection::ValidateRAPAttribute(_ATTRIBUTEID,tagVARIANT,ISdo *,IIASService *)
0x18003191c  mov     ebx, eax
0x18003191e  test    eax, eax
0x180031920  jns     loc_180031A26
0x180031926  mov     rax, cs:WPP_GLOBAL_Control
0x18003192d  cmp     rax, r13
0x180031930  jz      loc_180031A26
0x180031936  cmp     byte ptr [rax+19h], 2
0x18003193a  jb      loc_180031A26
0x180031940  test    [rax+1Ch], r12d
0x180031944  jz      loc_180031A26
0x18003194a  mov     edx, ebx
0x18003194c  lea     rcx, aValidaterapatt; "ValidateRAPAttributes failed with 0x%x"
0x180031953  call    WppDbgPrint
0x180031958  mov     edx, 0Dh
0x18003195d  jmp     loc_180031A03
0x180031962  cmp     eax, 0Ah
0x180031965  jnz     short loc_1800319CD
0x180031967  mov     rax, [rsp+88h+arg_0]
0x18003196f  movaps  xmm0, xmmword ptr [r14]
0x180031973  movaps  xmmword ptr [rsp+88h+var_48], xmm0
0x180031978  movsd   xmm1, qword ptr [r14+10h]
0x18003197e  movsd   qword ptr [rsp+88h+var_48+10h], xmm1
0x180031984  mov     [rsp+88h+var_68], rax; struct IIASService *
0x180031989  mov     r9, rbp; struct ISdo *
0x18003198c  lea     r8, [rsp+88h+var_48]; struct tagVARIANT
0x180031991  call    ?ValidateCRPAttribute@IASAttributesCollection@@QEAAJW4_ATTRIBUTEID@@UtagVARIANT@@PEAUISdo@@PEAUIIASService@@@Z; IASAttributesCollection::ValidateCRPAttribute(_ATTRIBUTEID,tagVARIANT,ISdo *,IIASService *)
0x180031996  mov     ebx, eax
0x180031998  test    eax, eax
0x18003199a  jns     loc_180031A26
0x1800319a0  mov     rax, cs:WPP_GLOBAL_Control
0x1800319a7  cmp     rax, r13
0x1800319aa  jz      short loc_180031A26
0x1800319ac  cmp     byte ptr [rax+19h], 2
0x1800319b0  jb      short loc_180031A26
0x1800319b2  test    [rax+1Ch], r12d
0x1800319b6  jz      short loc_180031A26
0x1800319b8  mov     edx, ebx
0x1800319ba  lea     rcx, aValidatecrpatt; "ValidateCRPAttributes failed with 0x%x"
0x1800319c1  call    WppDbgPrint
0x1800319c6  mov     edx, 0Eh
0x1800319cb  jmp     short loc_180031A03
0x1800319cd  call    ?ValidateIPFilterAttribute@IASAttributesCollection@@QEAAJW4_ATTRIBUTEID@@@Z; IASAttributesCollection::ValidateIPFilterAttribute(_ATTRIBUTEID)
0x1800319d2  mov     ebx, eax
0x1800319d4  test    eax, eax
0x1800319d6  jns     short loc_180031A26
0x1800319d8  mov     rax, cs:WPP_GLOBAL_Control
0x1800319df  cmp     rax, r13
0x1800319e2  jz      short loc_180031A26
0x1800319e4  cmp     byte ptr [rax+19h], 2
0x1800319e8  jb      short loc_180031A26
0x1800319ea  test    [rax+1Ch], r12d
0x1800319ee  jz      short loc_180031A26
0x1800319f0  mov     edx, ebx
0x1800319f2  lea     rcx, aValidateipfilt; "ValidateIPFilterAttributes failed with "...
0x1800319f9  call    WppDbgPrint
0x1800319fe  mov     edx, 0Fh
0x180031a03  mov     rcx, cs:WPP_GLOBAL_Control
0x180031a0a  mov     dword ptr [rsp+88h+var_68], ebx
0x180031a0e  lea     r9, aNpssdo; "NPSSDO"
0x180031a15  lea     r8, WPP_4b583fe665f33bdd9967a3ff271ecbd4_Traceguids
0x180031a1c  mov     rcx, [rcx+10h]
0x180031a20  call    WPP_SF_sd
0x180031a25  nop
0x180031a26  lea     rcx, [rsp+88h+arg_0]
0x180031a2e  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180031a33  nop
0x180031a34  lea     rcx, [rsp+88h+var_58]
0x180031a39  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180031a3e  mov     eax, ebx
0x180031a40  lea     r11, [rsp+88h+var_28]
0x180031a45  mov     rbx, [r11+38h]
0x180031a49  mov     rbp, [r11+40h]
0x180031a4d  mov     rsp, r11
0x180031a50  pop     r14
0x180031a52  pop     r13
0x180031a54  pop     r12
0x180031a56  pop     rdi
0x180031a57  pop     rsi
0x180031a58  retn
```
