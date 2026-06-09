# IASCollection::CreateNewEnumerator(void)

- ea: `0x180030644`
- end: `0x1800307d8`
- name: `?CreateNewEnumerator@IASCollection@@QEAAJXZ`
- size: `404`
- prototype: `__int64 __fastcall(IASCollection *__hidden this)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180030814`
- `0x180030d20`

## callees

- `0x18002cd00`
- `0x180030134`
- `0x18003053c`
- `0x180030644`
- `0x180042a80`
- `0x180058010`

## string_xrefs

- `0x1800306bf`: `CreateInstance(IASEnum) failed with 0x%x`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall IASCollection::CreateNewEnumerator(IASCollection *this)
{
  _QWORD *v2; // rsi
  __int64 v3; // rcx
  int v4; // ebx
  int v5; // edx
  __int64 v6; // r9
  __int64 v7; // r8
  __int64 v8; // rdx
  __int64 (__fastcall ***v9)(_QWORD, GUID *, _QWORD *); // rdi
  __int64 v11; // [rsp+20h] [rbp-28h]
  __int64 v12; // [rsp+28h] [rbp-20h]
  __int64 v13; // [rsp+30h] [rbp-18h]
  __int64 (__fastcall ***v14)(_QWORD, GUID *, _QWORD *); // [rsp+50h] [rbp+8h] BYREF

  v2 = (_QWORD *)((char *)this + 48);
  v3 = *((_QWORD *)this + 6);
  if ( v3 )
  {
    *v2 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  }
  v14 = 0;
  v4 = ATL::CComObject<IASEnum>::CreateInstance(&v14);
  if ( v4 >= 0 )
  {
    v13 = *((_QWORD *)this + 5);
    v12 = *((_QWORD *)this + 4);
    v11 = *((_QWORD *)this + 7);
    v6 = *((_QWORD *)this + 3);
    v7 = *((_QWORD *)this + 2);
    v8 = *((unsigned int *)this + 2);
    v9 = v14;
    v4 = IASEnum::Initialize(v14, v8, v7, v6, v11, v12, v13);
    if ( v4 >= 0 )
    {
      v4 = (**v9)(v9, &IID_IIASEnum, v2);
      if ( v4 < 0
        && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
      {
        WppDbgPrint("QI(IIASEnum) failed with 0x%x");
        v5 = 12;
        goto LABEL_18;
      }
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
           && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    {
      WppDbgPrint("pEnum->Initialize failed with 0x%x");
      v5 = 11;
      goto LABEL_18;
    }
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
         && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
  {
    WppDbgPrint("CreateInstance(IASEnum) failed with 0x%x");
    v5 = 10;
LABEL_18:
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v5,
      (unsigned int)WPP_c2f236718121324f7e73e45b18920f9d_Traceguids,
      (unsigned int)"NPSSDO",
      v4);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180030644  mov     [rsp+arg_8], rbx
0x180030649  mov     [rsp+arg_10], rsi
0x18003064e  push    rdi
0x18003064f  sub     rsp, 40h
0x180030653  mov     rdi, rcx
0x180030656  lea     rsi, [rcx+30h]
0x18003065a  mov     rcx, [rsi]
0x18003065d  test    rcx, rcx
0x180030660  jz      short loc_180030676
0x180030662  mov     qword ptr [rsi], 0
0x180030669  mov     rax, [rcx]
0x18003066c  mov     rax, [rax+10h]
0x180030670  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030675  nop
0x180030676  mov     [rsp+48h+arg_0], 0
0x18003067f  lea     rcx, [rsp+48h+arg_0]
0x180030684  call    ?CreateInstance@?$CComObject@VIASEnum@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<IASEnum>::CreateInstance(ATL::CComObject<IASEnum> * *)
0x180030689  mov     ebx, eax
0x18003068b  test    eax, eax
0x18003068d  jns     short loc_1800306D5
0x18003068f  lea     rax, WPP_GLOBAL_Control
0x180030696  mov     rcx, cs:WPP_GLOBAL_Control
0x18003069d  cmp     rcx, rax
0x1800306a0  jz      loc_1800307C6
0x1800306a6  cmp     byte ptr [rcx+19h], 2
0x1800306aa  jb      loc_1800307C6
0x1800306b0  test    dword ptr [rcx+1Ch], 400h
0x1800306b7  jz      loc_1800307C6
0x1800306bd  mov     edx, ebx
0x1800306bf  lea     rcx, aCreateinstance_2; "CreateInstance(IASEnum) failed with 0x%"...
0x1800306c6  call    WppDbgPrint
0x1800306cb  mov     edx, 0Ah
0x1800306d0  jmp     loc_1800307A4
0x1800306d5  mov     rax, [rdi+28h]
0x1800306d9  mov     [rsp+48h+var_18], rax
0x1800306de  mov     rax, [rdi+20h]
0x1800306e2  mov     [rsp+48h+var_20], rax
0x1800306e7  mov     rax, [rdi+38h]
0x1800306eb  mov     [rsp+48h+var_28], rax
0x1800306f0  mov     r9, [rdi+18h]
0x1800306f4  mov     r8, [rdi+10h]
0x1800306f8  mov     edx, [rdi+8]
0x1800306fb  mov     rdi, [rsp+48h+arg_0]
0x180030700  mov     rcx, rdi
0x180030703  call    ?Initialize@IASEnum@@QEAAJW4_ITEMTYPE@@PEAUISdoCollection@@PEAUISdo@@2PEAUISdoMachine@@PEAUISdoDictionaryOld@@@Z; IASEnum::Initialize(_ITEMTYPE,ISdoCollection *,ISdo *,ISdo *,ISdoMachine *,ISdoDictionaryOld *)
0x180030708  mov     ebx, eax
0x18003070a  test    eax, eax
0x18003070c  jns     short loc_180030751
0x18003070e  lea     rax, WPP_GLOBAL_Control
0x180030715  mov     rcx, cs:WPP_GLOBAL_Control
0x18003071c  cmp     rcx, rax
0x18003071f  jz      loc_1800307C6
0x180030725  cmp     byte ptr [rcx+19h], 2
0x180030729  jb      loc_1800307C6
0x18003072f  test    dword ptr [rcx+1Ch], 400h
0x180030736  jz      loc_1800307C6
0x18003073c  mov     edx, ebx
0x18003073e  lea     rcx, aPenumInitializ; "pEnum->Initialize failed with 0x%x"
0x180030745  call    WppDbgPrint
0x18003074a  mov     edx, 0Bh
0x18003074f  jmp     short loc_1800307A4
0x180030751  mov     rax, [rdi]
0x180030754  mov     r8, rsi
0x180030757  lea     rdx, IID_IIASEnum
0x18003075e  mov     rcx, rdi
0x180030761  mov     rax, [rax]
0x180030764  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030769  mov     ebx, eax
0x18003076b  test    eax, eax
0x18003076d  jns     short loc_1800307C6
0x18003076f  lea     rax, WPP_GLOBAL_Control
0x180030776  mov     rcx, cs:WPP_GLOBAL_Control
0x18003077d  cmp     rcx, rax
0x180030780  jz      short loc_1800307C6
0x180030782  cmp     byte ptr [rcx+19h], 2
0x180030786  jb      short loc_1800307C6
0x180030788  test    dword ptr [rcx+1Ch], 400h
0x18003078f  jz      short loc_1800307C6
0x180030791  mov     edx, ebx
0x180030793  lea     rcx, aQiIiasenumFail; "QI(IIASEnum) failed with 0x%x"
0x18003079a  call    WppDbgPrint
0x18003079f  mov     edx, 0Ch
0x1800307a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800307ab  mov     dword ptr [rsp+48h+var_28], ebx
0x1800307af  lea     r9, aNpssdo; "NPSSDO"
0x1800307b6  lea     r8, WPP_c2f236718121324f7e73e45b18920f9d_Traceguids
0x1800307bd  mov     rcx, [rcx+10h]
0x1800307c1  call    WPP_SF_sd
0x1800307c6  mov     eax, ebx
0x1800307c8  mov     rbx, [rsp+48h+arg_8]
0x1800307cd  mov     rsi, [rsp+48h+arg_10]
0x1800307d2  add     rsp, 40h
0x1800307d6  pop     rdi
0x1800307d7  retn
```
