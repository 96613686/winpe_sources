# IASConditionsCollection::ValidateCondition(_ATTRIBUTEID,ushort *)

- ea: `0x180036eec`
- end: `0x18003707a`
- name: `?ValidateCondition@IASConditionsCollection@@QEAAJW4_ATTRIBUTEID@@PEAG@Z`
- size: `398`
- prototype: `__int64 __fastcall(IASConditionsCollection *__hidden this, enum _ATTRIBUTEID, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800360c0`

## callees

- `0x180024cac`
- `0x18002844c`
- `0x18002cd00`
- `0x180036eec`
- `0x180042a80`
- `0x180058010`

## string_xrefs

- `0x180036f64`: `IASSDOCreateItem(IASSERVICE) failed with 0x%x`
- `0x180036fdc`: `pItem->QI(IID_IIASService) failed with 0x%x`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall IASConditionsCollection::ValidateCondition(
        IASConditionsCollection *this,
        enum _ATTRIBUTEID a2,
        unsigned __int16 *a3)
{
  int v4; // eax
  char v5; // bl
  int v6; // ebx
  __int64 (__fastcall ***v8)(_QWORD, GUID *, __int64 *); // [rsp+50h] [rbp+20h] BYREF
  __int64 v9; // [rsp+60h] [rbp+30h] BYREF
  __int64 v10; // [rsp+68h] [rbp+38h] BYREF

  v8 = 0;
  v9 = 0;
  v4 = IASSDOCreateItem(
         1,
         *((struct ISdo **)this + 4),
         *((struct ISdo **)this + 4),
         *((struct ISdoMachine **)this + 5),
         *((struct ISdoDictionaryOld **)this + 6),
         (__int64)&v8);
  v5 = v4;
  if ( v4 < 0
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
  {
    WppDbgPrint("IASSDOCreateItem(IASSERVICE) failed with 0x%x");
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      16,
      (unsigned int)WPP_d784a1b6d1803fc8648a97fdfe4f82a5_Traceguids,
      (unsigned int)"NPSSDO",
      v5);
  }
  v6 = (**v8)(v8, &IID_IIASService, &v9);
  if ( v6 >= 0 )
  {
    if ( *((_DWORD *)this + 32) == 9 )
    {
      v10 = v9;
      if ( v9 )
        (*(void (**)(void))(*(_QWORD *)v9 + 8LL))();
    }
    else
    {
      v10 = v9;
      if ( v9 )
        (*(void (**)(void))(*(_QWORD *)v9 + 8LL))();
    }
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v10);
    v6 = 0;
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
         && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
  {
    WppDbgPrint("pItem->QI(IID_IIASService) failed with 0x%x");
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      17,
      (unsigned int)WPP_d784a1b6d1803fc8648a97fdfe4f82a5_Traceguids,
      (unsigned int)"NPSSDO",
      v6);
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v9);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v8);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180036eec  mov     r11, rsp
0x180036eef  mov     [r11+10h], rbx
0x180036ef3  mov     [r11+18h], r8
0x180036ef7  push    rbp
0x180036ef8  push    rdi
0x180036ef9  push    r14
0x180036efb  mov     rbp, rsp
0x180036efe  sub     rsp, 30h
0x180036f02  mov     rdi, rcx
0x180036f05  mov     [rbp+arg_0], 0
0x180036f0d  mov     [rbp+arg_10], 0
0x180036f15  mov     rdx, [rcx+20h]
0x180036f19  lea     rax, [rbp+arg_0]
0x180036f1d  mov     [r11-20h], rax
0x180036f21  mov     rax, [rcx+30h]
0x180036f25  mov     [r11-28h], rax
0x180036f29  mov     r9, [rcx+28h]
0x180036f2d  mov     r8, rdx
0x180036f30  mov     ecx, 1
0x180036f35  call    ?IASSDOCreateItem@@YAJW4_ITEMTYPE@@PEAUISdo@@1PEAUISdoMachine@@PEAUISdoDictionaryOld@@PEAPEAUIIASItem@@@Z; IASSDOCreateItem(_ITEMTYPE,ISdo *,ISdo *,ISdoMachine *,ISdoDictionaryOld *,IIASItem * *)
0x180036f3a  mov     ebx, eax
0x180036f3c  lea     r14, WPP_GLOBAL_Control
0x180036f43  test    eax, eax
0x180036f45  jns     short loc_180036F97
0x180036f47  mov     rcx, cs:WPP_GLOBAL_Control
0x180036f4e  cmp     rcx, r14
0x180036f51  jz      short loc_180036F97
0x180036f53  cmp     byte ptr [rcx+19h], 2
0x180036f57  jb      short loc_180036F97
0x180036f59  test    dword ptr [rcx+1Ch], 400h
0x180036f60  jz      short loc_180036F97
0x180036f62  mov     edx, eax
0x180036f64  lea     rcx, aIassdocreateit; "IASSDOCreateItem(IASSERVICE) failed wit"...
0x180036f6b  call    WppDbgPrint
0x180036f70  mov     edx, 10h
0x180036f75  mov     [rsp+30h+var_10], ebx
0x180036f79  lea     r9, aNpssdo; "NPSSDO"
0x180036f80  lea     r8, WPP_d784a1b6d1803fc8648a97fdfe4f82a5_Traceguids
0x180036f87  mov     rcx, cs:WPP_GLOBAL_Control
0x180036f8e  mov     rcx, [rcx+10h]
0x180036f92  call    WPP_SF_sd
0x180036f97  mov     rcx, [rbp+arg_0]
0x180036f9b  mov     rax, [rcx]
0x180036f9e  lea     r8, [rbp+arg_10]
0x180036fa2  lea     rdx, IID_IIASService
0x180036fa9  mov     rax, [rax]
0x180036fac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036fb1  mov     ebx, eax
0x180036fb3  test    eax, eax
0x180036fb5  jns     short loc_180037011
0x180036fb7  mov     rax, cs:WPP_GLOBAL_Control
0x180036fbe  cmp     rax, r14
0x180036fc1  jz      loc_180037057
0x180036fc7  cmp     byte ptr [rax+19h], 2
0x180036fcb  jb      loc_180037057
0x180036fd1  test    dword ptr [rax+1Ch], 400h
0x180036fd8  jz      short loc_180037057
0x180036fda  mov     edx, ebx
0x180036fdc  lea     rcx, aPitemQiIidIias_0; "pItem->QI(IID_IIASService) failed with "...
0x180036fe3  call    WppDbgPrint
0x180036fe8  mov     edx, 11h
0x180036fed  mov     [rsp+30h+var_10], ebx
0x180036ff1  lea     r9, aNpssdo; "NPSSDO"
0x180036ff8  lea     r8, WPP_d784a1b6d1803fc8648a97fdfe4f82a5_Traceguids
0x180036fff  mov     rcx, cs:WPP_GLOBAL_Control
0x180037006  mov     rcx, [rcx+10h]
0x18003700a  call    WPP_SF_sd
0x18003700f  jmp     short loc_180037057
0x180037011  mov     rcx, [rbp+arg_10]
0x180037015  cmp     dword ptr [rdi+80h], 9
0x18003701c  jnz     short loc_180037036
0x18003701e  mov     [rbp+arg_18], rcx
0x180037022  test    rcx, rcx
0x180037025  jz      short loc_180037034
0x180037027  mov     rax, [rcx]
0x18003702a  mov     rax, [rax+8]
0x18003702e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037033  nop
0x180037034  jmp     short loc_18003704C
0x180037036  mov     [rbp+arg_18], rcx
0x18003703a  test    rcx, rcx
0x18003703d  jz      short loc_18003704C
0x18003703f  mov     rax, [rcx]
0x180037042  mov     rax, [rax+8]
0x180037046  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003704b  nop
0x18003704c  lea     rcx, [rbp+arg_18]
0x180037050  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180037055  xor     ebx, ebx
0x180037057  lea     rcx, [rbp+arg_10]
0x18003705b  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180037060  nop
0x180037061  lea     rcx, [rbp+arg_0]
0x180037065  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18003706a  mov     eax, ebx
0x18003706c  mov     rbx, [rsp+30h+arg_8]
0x180037071  add     rsp, 30h
0x180037075  pop     r14
0x180037077  pop     rdi
0x180037078  pop     rbp
0x180037079  retn
```
