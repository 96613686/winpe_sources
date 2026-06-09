# WFDSConMgr::CMaUsbDriverShim::CreateOpenSessionParams(sockaddr_in const &,WFDSConMgr::MaUsbTelemetryInfo const &,ulong &)

- ea: `0x18004cc90`
- end: `0x18004cee4`
- name: `?CreateOpenSessionParams@CMaUsbDriverShim@WFDSConMgr@@AEBA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@AEBUsockaddr_in@@AEBUMaUsbTelemetryInfo@2@AEAK@Z`
- size: `596`
- prototype: `__int64 __usercall@<rax>(void *@<rcx>, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18004e4a0`

## callees

- `0x180004260`
- `0x18000444e`
- `0x18000665c`
- `0x180009ff4`
- `0x18004cc90`
- `0x18005c888`

## string_xrefs

- `0x18004ccfa`: `WFDSConMgr::CMaUsbDriverShim::CreateOpenSessionParams`
- `0x18004cd42`: `WFDSConMgr::CMaUsbDriverShim::CreateOpenSessionParams`
- `0x18004cd8b`: `WFDSConMgr::CMaUsbDriverShim::CreateOpenSessionParams`
- `0x18004ce77`: `WFDSConMgr::CMaUsbDriverShim::CreateOpenSessionParams`
- `0x18004cea7`: `WFDSConMgr::CMaUsbDriverShim::CreateOpenSessionParams`
- `0x18004ced7`: `WFDSConMgr::CMaUsbDriverShim::CreateOpenSessionParams`

## pseudocode

```c
_QWORD *__fastcall WFDSConMgr::CMaUsbDriverShim::CreateOpenSessionParams(
        void *a1,
        _QWORD *a2,
        _OWORD *a3,
        __int128 *a4,
        unsigned int *a5)
{
  unsigned __int64 v7; // rbx
  unsigned int v8; // eax
  unsigned __int64 v9; // r14
  unsigned int v10; // edx
  unsigned __int64 v11; // r15
  unsigned int v12; // r12d
  _DWORD *v13; // rbp
  __int128 v14; // xmm1
  const void *v15; // rax
  char *v16; // rdi
  const void *v17; // rax
  const void *v18; // rax
  size_t v19; // r8
  unsigned int *v20; // rax

  *a5 = 0;
  v7 = 2LL * *((unsigned int *)a4 + 8);
  if ( v7 > 0xFFFFFFFF )
    WFDSConMgr::CException::Throw(
      22,
      "WFDSConMgr::CMaUsbDriverShim::CreateOpenSessionParams",
      "onecoreuap\\net\\wlan\\wfdsconmgr\\conmgr\\src\\mausbhelper.cpp",
      206,
      L"Overflow in manufacturer string",
      a1);
  v8 = v7 + 48;
  if ( (unsigned int)v7 >= 0xFFFFFFD0 )
    WFDSConMgr::CException::Throw(
      22,
      "WFDSConMgr::CMaUsbDriverShim::CreateOpenSessionParams",
      "onecoreuap\\net\\wlan\\wfdsconmgr\\conmgr\\src\\mausbhelper.cpp",
      208,
      L"Overflow in adding manufacturer string",
      a1);
  v9 = 2LL * *((unsigned int *)a4 + 16);
  if ( v9 > 0xFFFFFFFF )
    WFDSConMgr::CException::Throw(
      22,
      "WFDSConMgr::CMaUsbDriverShim::CreateOpenSessionParams",
      "onecoreuap\\net\\wlan\\wfdsconmgr\\conmgr\\src\\mausbhelper.cpp",
      211,
      L"Overflow in model name string",
      a1);
  v10 = v8 + v9;
  if ( v8 + (unsigned int)v9 < v8 )
    WFDSConMgr::CException::Throw(
      22,
      "WFDSConMgr::CMaUsbDriverShim::CreateOpenSessionParams",
      "onecoreuap\\net\\wlan\\wfdsconmgr\\conmgr\\src\\mausbhelper.cpp",
      213,
      L"Overflow in adding model name string",
      a1);
  v11 = 2LL * *((unsigned int *)a4 + 24);
  if ( v11 > 0xFFFFFFFF )
    WFDSConMgr::CException::Throw(
      22,
      "WFDSConMgr::CMaUsbDriverShim::CreateOpenSessionParams",
      "onecoreuap\\net\\wlan\\wfdsconmgr\\conmgr\\src\\mausbhelper.cpp",
      216,
      L"Overflow in model number string",
      a1);
  v12 = v10 + v11;
  if ( v10 + (unsigned int)v11 < v10 )
    WFDSConMgr::CException::Throw(
      22,
      "WFDSConMgr::CMaUsbDriverShim::CreateOpenSessionParams",
      "onecoreuap\\net\\wlan\\wfdsconmgr\\conmgr\\src\\mausbhelper.cpp",
      218,
      L"Overflow in adding model number string",
      a1);
  v13 = operator new[](v12);
  *(_OWORD *)v13 = *a3;
  v14 = *a4;
  v13[8] = v7;
  v13[9] = v9;
  *((_OWORD *)v13 + 1) = v14;
  v13[10] = v11;
  v15 = (const void *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a4 + 1);
  memcpy_0(v13 + 11, v15, (unsigned int)v7);
  v16 = (char *)v13 + (unsigned int)v7 + 44;
  v17 = (const void *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a4 + 3);
  memcpy_0(v16, v17, (unsigned int)v9);
  v18 = (const void *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a4 + 1);
  memcpy_0(&v16[(unsigned int)v9], v18, v19);
  v20 = a5;
  a5 = 0;
  *v20 = v12;
  *a2 = v13;
  std::unique_ptr<_CEREMONY [0]>::~unique_ptr<_CEREMONY [0]>((void **)&a5);
  return a2;
}

```

## disassembly

```asm
0x18004cc90  mov     [rsp+arg_8], rdx
0x18004cc95  push    rbx
0x18004cc96  push    rbp
0x18004cc97  push    rsi
0x18004cc98  push    rdi
0x18004cc99  push    r12
0x18004cc9b  push    r13
0x18004cc9d  push    r14
0x18004cc9f  push    r15
0x18004cca1  sub     rsp, 48h
0x18004cca5  mov     rax, [rsp+88h+arg_20]
0x18004ccad  mov     rdi, r8
0x18004ccb0  mov     r8d, 0FFFFFFFFh
0x18004ccb6  mov     r13, r9
0x18004ccb9  mov     dword ptr [rax], 0
0x18004ccbf  mov     ebx, [r9+20h]
0x18004ccc3  add     rbx, rbx
0x18004ccc6  cmp     rbx, r8
0x18004ccc9  ja      loc_18004CEB4
0x18004cccf  lea     eax, [rbx+30h]
0x18004ccd2  cmp     eax, 30h ; '0'
0x18004ccd5  jnb     short loc_18004CD07
0x18004ccd7  mov     [rsp+88h+var_60], rcx; void *
0x18004ccdc  lea     rax, aOverflowInAddi_1; "Overflow in adding manufacturer string"
0x18004cce3  mov     ecx, 80070216h; char
0x18004cce8  mov     [rsp+88h+var_68], rax; unsigned __int16 *
0x18004cced  mov     r9d, 0D0h; char
0x18004ccf3  lea     r8, aOnecoreuapNetW_16; "onecoreuap\\net\\wlan\\wfdsconmgr\\conm"...
0x18004ccfa  lea     rdx, aWfdsconmgrCmau_3; "WFDSConMgr::CMaUsbDriverShim::CreateOpe"...
0x18004cd01  call    ?Throw@CException@WFDSConMgr@@SAXJPEBD0KPEBGPEBX@Z; WFDSConMgr::CException::Throw(long,char const *,char const *,ulong,ushort const *,void const *)
0x18004cd07  mov     r14d, [r9+40h]
0x18004cd0b  add     r14, r14
0x18004cd0e  cmp     r14, r8
0x18004cd11  ja      loc_18004CE84
0x18004cd17  lea     edx, [rax+r14]
0x18004cd1b  cmp     edx, eax
0x18004cd1d  jnb     short loc_18004CD4F
0x18004cd1f  mov     [rsp+88h+var_60], rcx; void *
0x18004cd24  lea     rax, aOverflowInAddi_0; "Overflow in adding model name string"
0x18004cd2b  mov     ecx, 80070216h; char
0x18004cd30  mov     [rsp+88h+var_68], rax; unsigned __int16 *
0x18004cd35  mov     r9d, 0D5h; char
0x18004cd3b  lea     r8, aOnecoreuapNetW_16; "onecoreuap\\net\\wlan\\wfdsconmgr\\conm"...
0x18004cd42  lea     rdx, aWfdsconmgrCmau_3; "WFDSConMgr::CMaUsbDriverShim::CreateOpe"...
0x18004cd49  call    ?Throw@CException@WFDSConMgr@@SAXJPEBD0KPEBGPEBX@Z; WFDSConMgr::CException::Throw(long,char const *,char const *,ulong,ushort const *,void const *)
0x18004cd4f  mov     r15d, [r9+60h]
0x18004cd53  add     r15, r15
0x18004cd56  cmp     r15, r8
0x18004cd59  ja      loc_18004CE54
0x18004cd5f  lea     r12d, [rdx+r15]
0x18004cd63  cmp     r12d, edx
0x18004cd66  jnb     short loc_18004CD98
0x18004cd68  mov     [rsp+88h+var_60], rcx; void *
0x18004cd6d  lea     rax, aOverflowInAddi; "Overflow in adding model number string"
0x18004cd74  mov     ecx, 80070216h; char
0x18004cd79  mov     [rsp+88h+var_68], rax; unsigned __int16 *
0x18004cd7e  mov     r9d, 0DAh; char
0x18004cd84  lea     r8, aOnecoreuapNetW_16; "onecoreuap\\net\\wlan\\wfdsconmgr\\conm"...
0x18004cd8b  lea     rdx, aWfdsconmgrCmau_3; "WFDSConMgr::CMaUsbDriverShim::CreateOpe"...
0x18004cd92  call    ?Throw@CException@WFDSConMgr@@SAXJPEBD0KPEBGPEBX@Z; WFDSConMgr::CException::Throw(long,char const *,char const *,ulong,ushort const *,void const *)
0x18004cd98  mov     ecx, r12d; unsigned __int64
0x18004cd9b  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18004cda0  movups  xmm0, xmmword ptr [rdi]
0x18004cda3  lea     rcx, [r13+10h]
0x18004cda7  mov     rbp, rax
0x18004cdaa  movdqu  xmmword ptr [rax], xmm0
0x18004cdae  lea     rdi, [rax+2Ch]
0x18004cdb2  movups  xmm1, xmmword ptr [r13+0]
0x18004cdb7  mov     [rax+20h], ebx
0x18004cdba  mov     [rax+24h], r14d
0x18004cdbe  movdqu  xmmword ptr [rax+10h], xmm1
0x18004cdc3  mov     [rax+28h], r15d
0x18004cdc7  mov     ebx, ebx
0x18004cdc9  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18004cdce  mov     rdx, rax; Src
0x18004cdd1  mov     rcx, rdi; void *
0x18004cdd4  mov     r8d, ebx; Size
0x18004cdd7  call    memcpy_0
0x18004cddc  lea     rcx, [r13+30h]
0x18004cde0  add     rdi, rbx
0x18004cde3  mov     ebx, r14d
0x18004cde6  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18004cdeb  mov     rdx, rax; Src
0x18004cdee  mov     r8d, r14d; Size
0x18004cdf1  mov     rcx, rdi; void *
0x18004cdf4  call    memcpy_0
0x18004cdf9  lea     rcx, [r13+10h]
0x18004cdfd  mov     r8d, r15d
0x18004ce00  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18004ce05  mov     rdx, rax; Src
0x18004ce08  lea     rcx, [rbx+rdi]; void *
0x18004ce0c  call    memcpy_0
0x18004ce11  mov     rax, [rsp+88h+arg_20]
0x18004ce19  lea     rcx, [rsp+88h+arg_20]
0x18004ce21  mov     rbx, [rsp+88h+arg_8]
0x18004ce29  mov     [rsp+88h+arg_20], 0
0x18004ce35  mov     [rax], r12d
0x18004ce38  mov     [rbx], rbp
0x18004ce3b  call    ??1?$unique_ptr@$$BY0A@U_CEREMONY@@U?$default_delete@$$BY0A@U_CEREMONY@@@std@@@std@@QEAA@XZ; std::unique_ptr<_CEREMONY [0]>::~unique_ptr<_CEREMONY [0]>(void)
0x18004ce40  mov     rax, rbx
0x18004ce43  add     rsp, 48h
0x18004ce47  pop     r15
0x18004ce49  pop     r14
0x18004ce4b  pop     r13
0x18004ce4d  pop     r12
0x18004ce4f  pop     rdi
0x18004ce50  pop     rsi
0x18004ce51  pop     rbp
0x18004ce52  pop     rbx
0x18004ce53  retn
0x18004ce54  mov     [rsp+88h+var_60], rcx; void *
0x18004ce59  lea     rax, aOverflowInMode_0; "Overflow in model number string"
0x18004ce60  mov     ecx, 80070216h; char
0x18004ce65  mov     [rsp+88h+var_68], rax; unsigned __int16 *
0x18004ce6a  mov     r9d, 0D8h; char
0x18004ce70  lea     r8, aOnecoreuapNetW_16; "onecoreuap\\net\\wlan\\wfdsconmgr\\conm"...
0x18004ce77  lea     rdx, aWfdsconmgrCmau_3; "WFDSConMgr::CMaUsbDriverShim::CreateOpe"...
0x18004ce7e  call    ?Throw@CException@WFDSConMgr@@SAXJPEBD0KPEBGPEBX@Z; WFDSConMgr::CException::Throw(long,char const *,char const *,ulong,ushort const *,void const *)
0x18004ce84  mov     [rsp+88h+var_60], rcx; void *
0x18004ce89  lea     rax, aOverflowInMode; "Overflow in model name string"
0x18004ce90  mov     ecx, 80070216h; char
0x18004ce95  mov     [rsp+88h+var_68], rax; unsigned __int16 *
0x18004ce9a  mov     r9d, 0D3h; char
0x18004cea0  lea     r8, aOnecoreuapNetW_16; "onecoreuap\\net\\wlan\\wfdsconmgr\\conm"...
0x18004cea7  lea     rdx, aWfdsconmgrCmau_3; "WFDSConMgr::CMaUsbDriverShim::CreateOpe"...
0x18004ceae  call    ?Throw@CException@WFDSConMgr@@SAXJPEBD0KPEBGPEBX@Z; WFDSConMgr::CException::Throw(long,char const *,char const *,ulong,ushort const *,void const *)
0x18004ceb4  mov     [rsp+88h+var_60], rcx; void *
0x18004ceb9  lea     rax, aOverflowInManu; "Overflow in manufacturer string"
0x18004cec0  mov     ecx, 80070216h; char
0x18004cec5  mov     [rsp+88h+var_68], rax; unsigned __int16 *
0x18004ceca  mov     r9d, 0CEh; char
0x18004ced0  lea     r8, aOnecoreuapNetW_16; "onecoreuap\\net\\wlan\\wfdsconmgr\\conm"...
0x18004ced7  lea     rdx, aWfdsconmgrCmau_3; "WFDSConMgr::CMaUsbDriverShim::CreateOpe"...
0x18004cede  call    ?Throw@CException@WFDSConMgr@@SAXJPEBD0KPEBGPEBX@Z; WFDSConMgr::CException::Throw(long,char const *,char const *,ulong,ushort const *,void const *)
```
