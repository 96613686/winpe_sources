# CDataLinkDialog_Connect::GetCatalogData(IRowset *,HWND__ *)

- ea: `0x3839dadc0`
- end: `0x3839db061`
- name: `?GetCatalogData@CDataLinkDialog_Connect@@AEAAJPEAUIRowset@@PEAUHWND__@@@Z`
- size: `673`
- prototype: `int(CDataLinkDialog_Connect *__hidden this, struct IRowset *, HWND)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x3839da820`

## callees

- `0x3838435e0`
- `0x38391aed0`
- `0x3839dadc0`
- `0x383ade150`

## import_xrefs

- `USER32!SendMessageW` at `0x3839dae17`
- `USER32!SendMessageW` at `0x3839dafee`
- `USER32!SendMessageW` at `0x3839dae17`
- `USER32!SendMessageW` at `0x3839dafee`
- `ole32!CoTaskMemFree` at `0x3839daff9`
- `ole32!CoTaskMemFree` at `0x3839daff9`

## pseudocode

```c
__int64 __fastcall CDataLinkDialog_Connect::GetCatalogData(CDataLinkDialog_Connect *this, struct IRowset *a2, HWND a3)
{
  int v5; // ebx
  int v6; // ebx
  int v7; // ebx
  int v9; // eax
  unsigned int v10; // [rsp+40h] [rbp-C8h] BYREF
  __int64 v11; // [rsp+48h] [rbp-C0h] BYREF
  LPARAM lParam; // [rsp+50h] [rbp-B8h]
  int pExceptionObject; // [rsp+58h] [rbp-B0h] BYREF
  int v14; // [rsp+5Ch] [rbp-ACh] BYREF
  __int64 *v15; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v16; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v17; // [rsp+70h] [rbp-98h] BYREF
  __int64 v18; // [rsp+78h] [rbp-90h]
  __int64 v19; // [rsp+80h] [rbp-88h]
  _QWORD v20[15]; // [rsp+90h] [rbp-78h] BYREF
  int v21; // [rsp+110h] [rbp+8h]
  __int64 v22; // [rsp+120h] [rbp+18h] BYREF
  __int64 v23; // [rsp+128h] [rbp+20h] BYREF

  v19 = -2;
  v22 = 0;
  v23 = 0;
  v15 = &v17;
  v18 = 0;
  try
  {
    v11 = 0;
    lParam = 0;
    SendMessageW((HWND)a2, 0x14Bu, 0, 0);
    v5 = (**(__int64 (__fastcall ***)(CDataLinkDialog_Connect *, GUID *, __int64 *))this)(this, &IID_IAccessor, &v22);
    if ( v5 < 0 )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        if ( off_383B49120[0] )
          bidTraceW(off_383B432A8[0], 2465801, off_383B49120[0], 2408);
      }
      pExceptionObject = v5;
      throw (long *)&pExceptionObject;
    }
    memset(v20, 0, 0x58u);
    v20[0] = 1;
    v20[1] = 8;
    v20[3] = 0;
    LODWORD(v20[7]) = 5;
    WORD2(v20[10]) = 16514;
    v6 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, _QWORD *, __int64, __int64 *, _QWORD))(*(_QWORD *)v22 + 32LL))(
           v22,
           2,
           1,
           v20,
           16,
           &v23,
           0);
    if ( v6 < 0 )
    {
      if ( (bidGblFlags & 2) != 0 && off_383B49120[0] )
        bidTraceW(off_383B432A8[0], 2481161, off_383B49120[0], 2423);
      v14 = v6;
      throw (long *)&v14;
    }
    do
    {
      v7 = (*(__int64 (__fastcall **)(CDataLinkDialog_Connect *, _QWORD, _QWORD, __int64, __int64 *, __int64 **))(*(_QWORD *)this + 40LL))(
             this,
             0,
             0,
             1,
             &v16,
             &v15);
      if ( !v16 )
        break;
      v7 = (*(__int64 (__fastcall **)(CDataLinkDialog_Connect *, __int64, __int64, __int64 *))(*(_QWORD *)this + 32LL))(
             this,
             v17,
             v23,
             &v11);
      (*(void (__fastcall **)(CDataLinkDialog_Connect *, __int64, __int64 *))(*(_QWORD *)this + 48LL))(this, 1, v15);
      if ( v7 >= 0 && !(_DWORD)v11 && lParam )
      {
        SendMessageW((HWND)a2, 0x143u, 0, lParam);
        CoTaskMemFree((LPVOID)lParam);
        lParam = 0;
      }
    }
    while ( v7 != 265926 );
  }
  catch ( long v10 )
  {
    if ( (bidGblFlags & 2) != 0 )
      v9 = bidTraceHR(off_383B432A8[0], 2514953, v10);
    else
      v9 = v10;
    v21 = v9;
    if ( v18 )
      ((void (__fastcall *)(struct IMalloc *))g_pMO->lpVtbl[1].DidAlloc)(g_pMO);
    if ( lParam )
      CoTaskMemFree((LPVOID)lParam);
    v7 = v21;
  }
  if ( v23 )
    (*(void (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v22 + 48LL))(v22, v23, 0);
  if ( v22 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x3839dadc0  mov     rax, rsp
0x3839dadc3  push    rsi
0x3839dadc4  push    rdi
0x3839dadc5  push    r14
0x3839dadc7  sub     rsp, 0F0h
0x3839dadce  mov     qword ptr [rax-88h], 0FFFFFFFFFFFFFFFEh
0x3839dadd9  mov     [rax+10h], rbx
0x3839daddd  mov     rsi, rdx
0x3839dade0  mov     rdi, rcx
0x3839dade3  xor     r14d, r14d
0x3839dade6  mov     [rax+18h], r14
0x3839dadea  mov     [rax+20h], r14
0x3839dadee  lea     rax, [rsp+108h+var_98]
0x3839dadf3  mov     [rsp+108h+var_A8], rax
0x3839dadf8  mov     [rsp+108h+var_90], r14
0x3839dadfd  xor     eax, eax
0x3839dadff  mov     [rsp+108h+var_C0], rax
0x3839dae04  mov     [rsp+108h+lParam], rax
0x3839dae09  xor     r9d, r9d; lParam
0x3839dae0c  xor     r8d, r8d; wParam
0x3839dae0f  mov     edx, 14Bh; Msg
0x3839dae14  mov     rcx, rsi; hWnd
0x3839dae17  call    cs:__imp_SendMessageW
0x3839dae1d  mov     r11, [rdi]
0x3839dae20  lea     r8, [rsp+108h+arg_10]
0x3839dae28  lea     rdx, IID_IAccessor
0x3839dae2f  mov     rcx, rdi
0x3839dae32  call    qword ptr [r11]
0x3839dae35  mov     ebx, eax
0x3839dae37  test    eax, eax
0x3839dae39  jns     short loc_3839DAE83
0x3839dae3b  test    byte ptr cs:_bidGblFlags, 2
0x3839dae42  jz      short loc_3839DAE6E
0x3839dae44  mov     rcx, cs:off_383B432A8; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x3839dae4b  mov     rdx, cs:off_383B49120; "<Trace|MARK> line %d\n"
0x3839dae52  test    rdx, rdx
0x3839dae55  jz      short loc_3839DAE6E
0x3839dae57  mov     r9d, 968h
0x3839dae5d  mov     r8, cs:off_383B49120; "<Trace|MARK> line %d\n"
0x3839dae64  mov     edx, 25A009h
0x3839dae69  call    _bidTraceW
0x3839dae6e  mov     [rsp+108h+pExceptionObject], ebx
0x3839dae72  lea     rdx, _TI1J; pThrowInfo
0x3839dae79  lea     rcx, [rsp+108h+pExceptionObject]; pExceptionObject
0x3839dae7e  call    _CxxThrowException
0x3839dae83  xor     edx, edx; Val
0x3839dae85  lea     r8d, [rdx+58h]; Size
0x3839dae89  lea     rcx, [rsp+108h+var_78]; void *
0x3839dae91  call    memset
0x3839dae96  mov     [rsp+108h+var_78], 1
0x3839daea2  mov     [rsp+108h+var_70], 8
0x3839daeae  mov     [rsp+108h+var_60], r14
0x3839daeb6  mov     [rsp+108h+var_40], 5
0x3839daec1  mov     eax, 4082h
0x3839daec6  mov     [rsp+108h+var_24], ax
0x3839daece  mov     rcx, [rsp+108h+arg_10]
0x3839daed6  mov     rax, [rcx]
0x3839daed9  mov     [rsp+108h+var_D8], r14
0x3839daede  lea     rdx, [rsp+108h+arg_18]
0x3839daee6  mov     [rsp+108h+var_E0], rdx
0x3839daeeb  mov     [rsp+108h+var_E8], 10h
0x3839daef4  lea     r9, [rsp+108h+var_78]
0x3839daefc  mov     edx, 2
0x3839daf01  lea     r8d, [rdx-1]
0x3839daf05  call    qword ptr [rax+20h]
0x3839daf08  mov     ebx, eax
0x3839daf0a  test    eax, eax
0x3839daf0c  jns     short loc_3839DAF60
0x3839daf0e  test    byte ptr cs:_bidGblFlags, 2
0x3839daf15  jz      short loc_3839DAF41
0x3839daf17  mov     rcx, cs:off_383B432A8; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x3839daf1e  mov     rdx, cs:off_383B49120; "<Trace|MARK> line %d\n"
0x3839daf25  test    rdx, rdx
0x3839daf28  jz      short loc_3839DAF41
0x3839daf2a  mov     r9d, 977h
0x3839daf30  mov     r8, cs:off_383B49120; "<Trace|MARK> line %d\n"
0x3839daf37  mov     edx, 25DC09h
0x3839daf3c  call    _bidTraceW
0x3839daf41  mov     [rsp+108h+var_AC], ebx
0x3839daf45  lea     rdx, _TI1J; pThrowInfo
0x3839daf4c  lea     rcx, [rsp+108h+var_AC]; pExceptionObject
0x3839daf51  call    _CxxThrowException
0x3839daf60  mov     rax, [rdi]
0x3839daf63  lea     rcx, [rsp+108h+var_A8]
0x3839daf68  mov     [rsp+108h+var_E0], rcx
0x3839daf6d  lea     rcx, [rsp+108h+var_A0]
0x3839daf72  mov     [rsp+108h+var_E8], rcx
0x3839daf77  mov     r9d, 1
0x3839daf7d  xor     r8d, r8d
0x3839daf80  xor     edx, edx
0x3839daf82  mov     rcx, rdi
0x3839daf85  call    qword ptr [rax+28h]
0x3839daf88  mov     ebx, eax
0x3839daf8a  cmp     [rsp+108h+var_A0], 0
0x3839daf90  jz      short loc_3839DB010
0x3839daf92  mov     rax, [rdi]
0x3839daf95  lea     r9, [rsp+108h+var_C0]
0x3839daf9a  mov     r8, [rsp+108h+arg_18]
0x3839dafa2  mov     rdx, [rsp+108h+var_98]
0x3839dafa7  mov     rcx, rdi
0x3839dafaa  call    qword ptr [rax+20h]
0x3839dafad  mov     ebx, eax
0x3839dafaf  mov     rax, [rdi]
0x3839dafb2  mov     [rsp+108h+var_E0], r14
0x3839dafb7  mov     [rsp+108h+var_E8], r14
0x3839dafbc  xor     r9d, r9d
0x3839dafbf  mov     r8, [rsp+108h+var_A8]
0x3839dafc4  lea     edx, [r9+1]
0x3839dafc8  mov     rcx, rdi
0x3839dafcb  call    qword ptr [rax+30h]
0x3839dafce  test    ebx, ebx
0x3839dafd0  js      short loc_3839DB004
0x3839dafd2  cmp     dword ptr [rsp+108h+var_C0], 0
0x3839dafd7  jnz     short loc_3839DB004
0x3839dafd9  mov     r9, [rsp+108h+lParam]; lParam
0x3839dafde  test    r9, r9
0x3839dafe1  jz      short loc_3839DB004
0x3839dafe3  xor     r8d, r8d; wParam
0x3839dafe6  mov     edx, 143h; Msg
0x3839dafeb  mov     rcx, rsi; hWnd
0x3839dafee  call    cs:__imp_SendMessageW
0x3839daff4  mov     rcx, [rsp+108h+lParam]; pv
0x3839daff9  call    cs:__imp_CoTaskMemFree
0x3839dafff  mov     [rsp+108h+lParam], r14
0x3839db004  cmp     ebx, 40EC6h
0x3839db00a  jnz     loc_3839DAF60
0x3839db010  jmp     short loc_3839DB019
0x3839db012  mov     ebx, [rsp+108h+arg_0]
0x3839db019  mov     rdx, [rsp+108h+arg_18]
0x3839db021  test    rdx, rdx
0x3839db024  jz      short loc_3839DB038
0x3839db026  mov     rcx, [rsp+108h+arg_10]
0x3839db02e  mov     r9, [rcx]
0x3839db031  xor     r8d, r8d
0x3839db034  call    qword ptr [r9+30h]
0x3839db038  mov     rcx, [rsp+108h+arg_10]
0x3839db040  test    rcx, rcx
0x3839db043  jz      short loc_3839DB04B
0x3839db045  mov     rdx, [rcx]
0x3839db048  call    qword ptr [rdx+10h]
0x3839db04b  mov     eax, ebx
0x3839db04d  mov     rbx, [rsp+108h+arg_8]
0x3839db055  add     rsp, 0F0h
0x3839db05c  pop     r14
0x3839db05e  pop     rdi
0x3839db05f  pop     rsi
0x3839db060  retn
```
