# IASSDOHelper::GetIasTemplatesRoot(IIASTemplatesRoot * *)

- ea: `0x18002da80`
- end: `0x18002dd1a`
- name: `?GetIasTemplatesRoot@IASSDOHelper@@UEAAJPEAPEAUIIASTemplatesRoot@@@Z`
- size: `666`
- prototype: `__int64 __fastcall(IASSDOHelper *__hidden this, struct IIASTemplatesRoot **)`
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x180024cac`
- `0x18002cd00`
- `0x18002d08c`
- `0x18002d278`
- `0x18002d2d0`
- `0x18002da80`
- `0x18002ee50`
- `0x18002efa0`
- `0x18002f904`
- `0x180042a80`
- `0x180058010`

## string_xrefs

- `0x18002db6e`: `Failed to get templates SDO in Sdo helper, %!hresult!`
- `0x18002dcad`: `pTemplatesRoot->Initialize failed with %!hresult!`

## pseudocode

```c
__int64 __fastcall IASSDOHelper::GetIasTemplatesRoot(IASSDOHelper *this, struct IIASTemplatesRoot **a2)
{
  struct IIASTemplatesRoot *v3; // r15
  int Instance; // edi
  struct IUnknown *v7; // rdi
  __int64 v8; // r14
  __int64 (__fastcall *v9)(__int64, _QWORD *, char *); // r13
  _QWORD *v10; // rdx
  int v11; // r14d
  int v12; // esi
  struct IUnknown *v13; // rdx
  struct ISdoDictionaryOld *v14; // rsi
  struct ISdoMachine *v15; // r14
  struct ISdo *v16; // rbx
  int v17; // ebx
  struct IUnknown *v18[2]; // [rsp+30h] [rbp-10h] BYREF
  struct IUnknown *v19; // [rsp+90h] [rbp+50h] BYREF
  struct ISdo *v20; // [rsp+98h] [rbp+58h] BYREF

  v19 = 0;
  v3 = 0;
  v20 = 0;
  v18[0] = 0;
  Instance = ATL::CComObject<IASTemplatesRoot>::CreateInstance(v18);
  if ( Instance >= 0 )
  {
    v7 = v18[0];
    if ( v18[0] )
    {
      ATL::AtlComPtrAssign(&v19, v18[0]);
      v3 = (struct IIASTemplatesRoot *)v19;
    }
    if ( *((_QWORD *)this + 12) )
      ATL::CComPtrBase<IIASItem>::Release((char *)this + 96);
    v8 = *((_QWORD *)this + 10);
    v9 = *(__int64 (__fastcall **)(__int64, _QWORD *, char *))(*(_QWORD *)v8 + 128LL);
    v10 = *(_QWORD **)_bstr_t::_bstr_t((_bstr_t *)v18, L"IAS");
    if ( v10 )
      v10 = (_QWORD *)*v10;
    v11 = v9(v8, v10, (char *)this + 96);
    _bstr_t::_Free((_bstr_t *)v18);
    if ( v11 >= 0 )
    {
      v12 = (***((__int64 (__fastcall ****)(_QWORD, GUID *, struct ISdo **))this + 12))(
              *((_QWORD *)this + 12),
              &IID_ISdo,
              &v20);
      if ( v12 >= 0 )
      {
        v13 = (struct IUnknown *)*((_QWORD *)this + 11);
        v14 = (struct ISdoDictionaryOld *)*((_QWORD *)this + 13);
        v15 = (struct ISdoMachine *)*((_QWORD *)this + 9);
        v16 = v20;
        if ( (struct IUnknown *)v7[21].lpVtbl != v13 )
          ATL::AtlComPtrAssign((struct IUnknown **)&v7[21], v13);
        v17 = IASItem::Initialize((IASItem *)&v7[2], v16, v16, v15, v14);
        if ( v17 >= 0 )
        {
          v19 = 0;
          *a2 = v3;
        }
        else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
               && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
               && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
        {
          WppDbgPrint("pTemplatesRoot->Initialize failed with %!hresult!");
          WPP_SF_sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            23,
            (unsigned int)WPP_b2e5ba8d027733d341583b07c20330d3_Traceguids,
            (unsigned int)"NPSSDO",
            v17);
        }
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v20);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v19);
        return (unsigned int)v17;
      }
      else
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
        {
          WppDbgPrint("QI(ISdo) failed in SDO helper Initialize() with %!hresult!");
          WPP_SF_sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            22,
            (unsigned int)WPP_b2e5ba8d027733d341583b07c20330d3_Traceguids,
            (unsigned int)"NPSSDO",
            v12);
        }
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v20);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v19);
        return (unsigned int)v12;
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
      {
        WppDbgPrint("Failed to get templates SDO in Sdo helper, %!hresult!");
        WPP_SF_sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          21,
          (unsigned int)WPP_b2e5ba8d027733d341583b07c20330d3_Traceguids,
          (unsigned int)"NPSSDO",
          v11);
      }
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v20);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v19);
      return (unsigned int)v11;
    }
  }
  else
  {
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v20);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v19);
    return (unsigned int)Instance;
  }
}

```

## disassembly

```asm
0x18002da80  mov     [rsp-38h+arg_0], rbx
0x18002da85  push    rbp
0x18002da86  push    rsi
0x18002da87  push    rdi
0x18002da88  push    r12
0x18002da8a  push    r13
0x18002da8c  push    r14
0x18002da8e  push    r15
0x18002da90  mov     rbp, rsp
0x18002da93  sub     rsp, 40h
0x18002da97  xor     r14d, r14d
0x18002da9a  mov     rbx, rcx
0x18002da9d  lea     rcx, [rbp+var_10]
0x18002daa1  mov     [rbp+arg_10], r14
0x18002daa5  mov     r15d, r14d
0x18002daa8  mov     [rbp+arg_18], r14
0x18002daac  mov     [rbp+var_10], r14
0x18002dab0  mov     r12, rdx
0x18002dab3  call    ?CreateInstance@?$CComObject@VIASTemplatesRoot@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<IASTemplatesRoot>::CreateInstance(ATL::CComObject<IASTemplatesRoot> * *)
0x18002dab8  mov     edi, eax
0x18002daba  test    eax, eax
0x18002dabc  jns     short loc_18002DAD7
0x18002dabe  lea     rcx, [rbp+arg_18]
0x18002dac2  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18002dac7  lea     rcx, [rbp+arg_10]
0x18002dacb  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18002dad0  mov     eax, edi
0x18002dad2  jmp     loc_18002DD02
0x18002dad7  mov     rdi, [rbp+var_10]
0x18002dadb  test    rdi, rdi
0x18002dade  jz      short loc_18002DAF0
0x18002dae0  mov     rdx, rdi; struct IUnknown *
0x18002dae3  lea     rcx, [rbp+arg_10]; struct IUnknown **
0x18002dae7  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x18002daec  mov     r15, [rbp+arg_10]
0x18002daf0  lea     rsi, [rbx+60h]
0x18002daf4  cmp     [rsi], r14
0x18002daf7  jz      short loc_18002DB01
0x18002daf9  mov     rcx, rsi
0x18002dafc  call    ?Release@?$CComPtrBase@UIIASItem@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IIASItem>::Release(void)
0x18002db01  mov     r14, [rbx+50h]
0x18002db05  lea     rdx, aIas; "IAS"
0x18002db0c  lea     rcx, [rbp+var_10]; this
0x18002db10  mov     rax, [r14]
0x18002db13  mov     r13, [rax+80h]
0x18002db1a  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18002db1f  mov     rdx, [rax]
0x18002db22  test    rdx, rdx
0x18002db25  jz      short loc_18002DB2A
0x18002db27  mov     rdx, [rdx]
0x18002db2a  mov     r8, rsi
0x18002db2d  mov     rcx, r14
0x18002db30  mov     rax, r13
0x18002db33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002db38  lea     rcx, [rbp+var_10]; this
0x18002db3c  mov     r14d, eax
0x18002db3f  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18002db44  test    r14d, r14d
0x18002db47  jns     short loc_18002DBBC
0x18002db49  mov     rdx, cs:WPP_GLOBAL_Control
0x18002db50  lea     rcx, WPP_GLOBAL_Control
0x18002db57  cmp     rdx, rcx
0x18002db5a  jz      short loc_18002DBA2
0x18002db5c  cmp     byte ptr [rdx+19h], 2
0x18002db60  jb      short loc_18002DBA2
0x18002db62  test    dword ptr [rdx+1Ch], 400h
0x18002db69  jz      short loc_18002DBA2
0x18002db6b  mov     edx, r14d
0x18002db6e  lea     rcx, aFailedToGetTem_0; "Failed to get templates SDO in Sdo help"...
0x18002db75  call    WppDbgPrint
0x18002db7a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002db81  lea     r9, aNpssdo; "NPSSDO"
0x18002db88  mov     edx, 15h
0x18002db8d  mov     dword ptr [rsp+40h+var_20], r14d
0x18002db92  lea     r8, WPP_b2e5ba8d027733d341583b07c20330d3_Traceguids
0x18002db99  mov     rcx, [rcx+10h]
0x18002db9d  call    WPP_SF_sd
0x18002dba2  lea     rcx, [rbp+arg_18]
0x18002dba6  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18002dbab  lea     rcx, [rbp+arg_10]
0x18002dbaf  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18002dbb4  mov     eax, r14d
0x18002dbb7  jmp     loc_18002DD02
0x18002dbbc  mov     rcx, [rsi]
0x18002dbbf  lea     r8, [rbp+arg_18]
0x18002dbc3  lea     rdx, IID_ISdo
0x18002dbca  mov     rax, [rcx]
0x18002dbcd  mov     rax, [rax]
0x18002dbd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dbd5  mov     esi, eax
0x18002dbd7  test    eax, eax
0x18002dbd9  jns     short loc_18002DC4B
0x18002dbdb  mov     rdx, cs:WPP_GLOBAL_Control
0x18002dbe2  lea     rcx, WPP_GLOBAL_Control
0x18002dbe9  cmp     rdx, rcx
0x18002dbec  jz      short loc_18002DC32
0x18002dbee  cmp     byte ptr [rdx+19h], 2
0x18002dbf2  jb      short loc_18002DC32
0x18002dbf4  test    dword ptr [rdx+1Ch], 400h
0x18002dbfb  jz      short loc_18002DC32
0x18002dbfd  mov     edx, eax
0x18002dbff  lea     rcx, aQiIsdoFailedIn; "QI(ISdo) failed in SDO helper Initializ"...
0x18002dc06  call    WppDbgPrint
0x18002dc0b  mov     rcx, cs:WPP_GLOBAL_Control
0x18002dc12  lea     r9, aNpssdo; "NPSSDO"
0x18002dc19  mov     edx, 16h
0x18002dc1e  mov     dword ptr [rsp+40h+var_20], esi
0x18002dc22  lea     r8, WPP_b2e5ba8d027733d341583b07c20330d3_Traceguids
0x18002dc29  mov     rcx, [rcx+10h]
0x18002dc2d  call    WPP_SF_sd
0x18002dc32  lea     rcx, [rbp+arg_18]
0x18002dc36  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18002dc3b  lea     rcx, [rbp+arg_10]
0x18002dc3f  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18002dc44  mov     eax, esi
0x18002dc46  jmp     loc_18002DD02
0x18002dc4b  mov     rdx, [rbx+58h]; struct IUnknown *
0x18002dc4f  lea     rcx, [rdi+0A8h]; struct IUnknown **
0x18002dc56  mov     rsi, [rbx+68h]
0x18002dc5a  mov     r14, [rbx+48h]
0x18002dc5e  mov     rbx, [rbp+arg_18]
0x18002dc62  cmp     [rcx], rdx
0x18002dc65  jz      short loc_18002DC6C
0x18002dc67  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x18002dc6c  lea     rcx, [rdi+10h]; this
0x18002dc70  mov     [rsp+40h+var_20], rsi; struct ISdoDictionaryOld *
0x18002dc75  mov     r9, r14; struct ISdoMachine *
0x18002dc78  mov     r8, rbx; struct ISdo *
0x18002dc7b  mov     rdx, rbx; struct ISdo *
0x18002dc7e  call    ?Initialize@IASItem@@QEAAJPEAUISdo@@0PEAUISdoMachine@@PEAUISdoDictionaryOld@@@Z; IASItem::Initialize(ISdo *,ISdo *,ISdoMachine *,ISdoDictionaryOld *)
0x18002dc83  mov     ebx, eax
0x18002dc85  test    eax, eax
0x18002dc87  jns     short loc_18002DCE2
0x18002dc89  mov     rax, cs:WPP_GLOBAL_Control
0x18002dc90  lea     rcx, WPP_GLOBAL_Control
0x18002dc97  cmp     rax, rcx
0x18002dc9a  jz      short loc_18002DCEE
0x18002dc9c  cmp     byte ptr [rax+19h], 2
0x18002dca0  jb      short loc_18002DCEE
0x18002dca2  test    dword ptr [rax+1Ch], 400h
0x18002dca9  jz      short loc_18002DCEE
0x18002dcab  mov     edx, ebx
0x18002dcad  lea     rcx, aPtemplatesroot; "pTemplatesRoot->Initialize failed with "...
0x18002dcb4  call    WppDbgPrint
0x18002dcb9  mov     rcx, cs:WPP_GLOBAL_Control
0x18002dcc0  lea     r9, aNpssdo; "NPSSDO"
0x18002dcc7  mov     edx, 17h
0x18002dccc  mov     dword ptr [rsp+40h+var_20], ebx
0x18002dcd0  lea     r8, WPP_b2e5ba8d027733d341583b07c20330d3_Traceguids
0x18002dcd7  mov     rcx, [rcx+10h]
0x18002dcdb  call    WPP_SF_sd
0x18002dce0  jmp     short loc_18002DCEE
0x18002dce2  mov     [rbp+arg_10], 0
0x18002dcea  mov     [r12], r15
0x18002dcee  lea     rcx, [rbp+arg_18]
0x18002dcf2  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18002dcf7  lea     rcx, [rbp+arg_10]
0x18002dcfb  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18002dd00  mov     eax, ebx
0x18002dd02  mov     rbx, [rsp+40h+arg_0]
0x18002dd0a  add     rsp, 40h
0x18002dd0e  pop     r15
0x18002dd10  pop     r14
0x18002dd12  pop     r13
0x18002dd14  pop     r12
0x18002dd16  pop     rdi
0x18002dd17  pop     rsi
0x18002dd18  pop     rbp
0x18002dd19  retn
```
