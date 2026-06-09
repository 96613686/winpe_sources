# AtlAxCreateControl

- ea: `0x140009710`
- end: `0x1400098cf`
- name: `AtlAxCreateControl`
- size: `447`
- prototype: `__int64 __fastcall(OLECHAR *psz)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140002b10`

## callees

- `0x140001008`
- `0x140001014`
- `0x140001d88`
- `0x140002238`
- `0x140007c2c`
- `0x140009710`
- `0x1400098d8`
- `0x14000c818`
- `0x14000f010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x14000980c`
- `OLEAUT32!__imp_SysAllocString` at `0x14000980c`
- `OLEAUT32!__imp_SysFreeString` at `0x140009851`
- `OLEAUT32!__imp_SysFreeString` at `0x140009851`

## pseudocode

```c
__int64 __fastcall AtlAxCreateControl(OLECHAR *psz, __int64 a2, __int64 a3, _QWORD *a4)
{
  int v8; // esi
  void *v9; // rax
  __int64 v10; // rax
  _DWORD *v11; // rdi
  int v12; // eax
  CExeModule *v13; // rcx
  OLECHAR *v14; // rbx
  void (__fastcall ***v15)(_QWORD, GUID *, _QWORD *); // rcx
  __int64 v17; // [rsp+40h] [rbp-18h] BYREF
  __int64 v18; // [rsp+48h] [rbp-10h] BYREF
  void (__fastcall ***v19)(_QWORD, GUID *, __int64 *); // [rsp+B8h] [rbp+60h] BYREF

  AtlAxWinInit();
  v18 = 0;
  v19 = 0;
  v8 = -2147024882;
  v9 = operator new(0x168u);
  if ( v9 )
  {
    v10 = ATL::CComPolyObject<ATL::CAxHostWindow>::CComPolyObject<ATL::CAxHostWindow>(v9);
    v11 = (_DWORD *)v10;
    if ( v10 )
    {
      v12 = *(_DWORD *)(v10 + 8);
      if ( v12 != 0x7FFFFFFF )
      {
        v11[2] = v12 + 1;
        if ( v12 != 2147483646 )
          v11[2] = v12;
      }
      v8 = (**(__int64 (__fastcall ***)(void *, GUID *, _QWORD))v11)(v11, &IID_IUnknown, &v19);
      if ( v8 )
      {
        v11[2] = 1;
        *(_QWORD *)v11 = &ATL::CComPolyObject<ATL::CAxHostWindow>::`vftable';
        ATL::CAxHostWindow::ReleaseAll((ATL::CAxHostWindow *)(v11 + 4));
        CExeModule::Unlock(v13);
        ATL::CAxHostWindow::~CAxHostWindow((ATL::CAxHostWindow *)(v11 + 4));
        operator delete(v11);
      }
      if ( v8 >= 0 )
      {
        v17 = 0;
        (**v19)(v19, &IID_IAxWinHostWindow, &v17);
        v14 = SysAllocString(psz);
        v8 = (*(__int64 (__fastcall **)(__int64, OLECHAR *, __int64, __int64, __int64 *, GUID *, _QWORD))(*(_QWORD *)v17 + 32LL))(
               v17,
               v14,
               a2,
               a3,
               &v18,
               &GUID_NULL,
               0);
        SysFreeString(v14);
        if ( v17 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
      }
    }
  }
  if ( a4 )
  {
    if ( v8 >= 0 )
    {
      v15 = 0;
      *a4 = v19;
      v19 = 0;
      goto LABEL_16;
    }
    *a4 = 0;
  }
  v15 = v19;
LABEL_16:
  if ( v18 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    v15 = v19;
  }
  if ( v15 )
    ((void (__fastcall *)(void (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v15)[2])(v15);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x140009710  push    rbp
0x140009712  push    rbx
0x140009713  push    rsi
0x140009714  push    rdi
0x140009715  push    r12
0x140009717  push    r13
0x140009719  push    r14
0x14000971b  push    r15
0x14000971d  mov     rbp, rsp
0x140009720  sub     rsp, 58h
0x140009724  mov     r14, r9
0x140009727  mov     r15, r8
0x14000972a  mov     r12, rdx
0x14000972d  mov     r13, rcx
0x140009730  call    AtlAxWinInit
0x140009735  mov     ecx, 168h; Size
0x14000973a  mov     [rbp+var_10], 0
0x140009742  mov     [rbp+arg_18], 0
0x14000974a  mov     esi, 8007000Eh
0x14000974f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140009754  test    rax, rax
0x140009757  jz      loc_14000986C
0x14000975d  mov     rcx, rax
0x140009760  call    ??0?$CComPolyObject@VCAxHostWindow@ATL@@@ATL@@QEAA@PEAX@Z; ATL::CComPolyObject<ATL::CAxHostWindow>::CComPolyObject<ATL::CAxHostWindow>(void *)
0x140009765  mov     rdi, rax
0x140009768  test    rax, rax
0x14000976b  jz      loc_14000986C
0x140009771  mov     eax, [rax+8]
0x140009774  cmp     eax, 7FFFFFFFh
0x140009779  jz      short loc_14000978B
0x14000977b  lea     ecx, [rax+1]
0x14000977e  mov     [rdi+8], ecx
0x140009781  cmp     eax, 7FFFFFFEh
0x140009786  jz      short loc_14000978B
0x140009788  mov     [rdi+8], eax
0x14000978b  mov     rax, [rdi]
0x14000978e  lea     r8, [rbp+arg_18]
0x140009792  lea     rdx, IID_IUnknown
0x140009799  mov     rcx, rdi
0x14000979c  mov     rax, [rax]
0x14000979f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400097a4  mov     esi, eax
0x1400097a6  test    eax, eax
0x1400097a8  jz      short loc_1400097DF
0x1400097aa  lea     rax, ??_7?$CComPolyObject@VCAxHostWindow@ATL@@@ATL@@6B@; const ATL::CComPolyObject<ATL::CAxHostWindow>::`vftable'
0x1400097b1  mov     dword ptr [rdi+8], 1
0x1400097b8  lea     rcx, [rdi+10h]; this
0x1400097bc  mov     [rdi], rax
0x1400097bf  call    ?ReleaseAll@CAxHostWindow@ATL@@QEAAXXZ; ATL::CAxHostWindow::ReleaseAll(void)
0x1400097c4  call    ?Unlock@CExeModule@@QEAAJXZ; CExeModule::Unlock(void)
0x1400097c9  lea     rcx, [rdi+10h]; this
0x1400097cd  call    ??1CAxHostWindow@ATL@@QEAA@XZ; ATL::CAxHostWindow::~CAxHostWindow(void)
0x1400097d2  mov     edx, 168h; unsigned __int64
0x1400097d7  mov     rcx, rdi; void *
0x1400097da  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1400097df  test    esi, esi
0x1400097e1  js      loc_14000986C
0x1400097e7  mov     rcx, [rbp+arg_18]
0x1400097eb  lea     r8, [rbp+var_18]
0x1400097ef  mov     [rbp+var_18], 0
0x1400097f7  lea     rdx, IID_IAxWinHostWindow
0x1400097fe  mov     rax, [rcx]
0x140009801  mov     rax, [rax]
0x140009804  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009809  mov     rcx, r13; psz
0x14000980c  call    cs:__imp_SysAllocString
0x140009812  mov     rcx, [rbp+var_18]
0x140009816  lea     rdx, GUID_NULL
0x14000981d  mov     rbx, rax
0x140009820  mov     [rsp+58h+var_28], 0
0x140009829  mov     [rsp+58h+var_30], rdx
0x14000982e  mov     r9, r15
0x140009831  lea     rdx, [rbp+var_10]
0x140009835  mov     r8, r12
0x140009838  mov     rax, [rcx]
0x14000983b  mov     [rsp+58h+var_38], rdx
0x140009840  mov     rdx, rbx
0x140009843  mov     rax, [rax+20h]
0x140009847  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000984c  mov     rcx, rbx; bstrString
0x14000984f  mov     esi, eax
0x140009851  call    cs:__imp_SysFreeString
0x140009857  mov     rcx, [rbp+var_18]
0x14000985b  test    rcx, rcx
0x14000985e  jz      short loc_14000986C
0x140009860  mov     rdx, [rcx]
0x140009863  mov     rax, [rdx+10h]
0x140009867  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000986c  test    r14, r14
0x14000986f  jz      short loc_14000988B
0x140009871  test    esi, esi
0x140009873  js      short loc_140009884
0x140009875  mov     rax, [rbp+arg_18]
0x140009879  xor     ecx, ecx
0x14000987b  mov     [r14], rax
0x14000987e  mov     [rbp+arg_18], rcx
0x140009882  jmp     short loc_14000988F
0x140009884  mov     qword ptr [r14], 0
0x14000988b  mov     rcx, [rbp+arg_18]
0x14000988f  mov     rdx, [rbp+var_10]
0x140009893  test    rdx, rdx
0x140009896  jz      short loc_1400098AB
0x140009898  mov     rax, [rdx]
0x14000989b  mov     rcx, rdx
0x14000989e  mov     rax, [rax+10h]
0x1400098a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400098a7  mov     rcx, [rbp+arg_18]
0x1400098ab  test    rcx, rcx
0x1400098ae  jz      short loc_1400098BC
0x1400098b0  mov     rax, [rcx]
0x1400098b3  mov     rax, [rax+10h]
0x1400098b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400098bc  mov     eax, esi
0x1400098be  add     rsp, 58h
0x1400098c2  pop     r15
0x1400098c4  pop     r14
0x1400098c6  pop     r13
0x1400098c8  pop     r12
0x1400098ca  pop     rdi
0x1400098cb  pop     rsi
0x1400098cc  pop     rbx
0x1400098cd  pop     rbp
0x1400098ce  retn
```
