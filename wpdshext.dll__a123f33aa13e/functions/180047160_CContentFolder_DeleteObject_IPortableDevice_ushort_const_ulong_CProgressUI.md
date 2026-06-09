# CContentFolder::_DeleteObject(IPortableDevice *,ushort const *,ulong,CProgressUI *)

- ea: `0x180047160`
- end: `0x1800474af`
- name: `?_DeleteObject@CContentFolder@@AEAAJPEAUIPortableDevice@@PEBGKPEAVCProgressUI@@@Z`
- size: `847`
- prototype: `int(CContentFolder *__hidden this, struct IPortableDevice *, const unsigned __int16 *, unsigned int, struct CProgressUI *)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180016780`
- `0x18003b8e4`

## callees

- `0x180014b60`
- `0x180016200`
- `0x1800285c8`
- `0x18002ff5c`
- `0x180047160`
- `0x180054524`
- `0x1800545c8`
- `0x180078010`

## import_xrefs

- `KERNEL32!Sleep` at `0x180047270`
- `KERNEL32!Sleep` at `0x1800473e2`
- `KERNEL32!Sleep` at `0x180047270`
- `KERNEL32!Sleep` at `0x1800473e2`
- `ole32!PropVariantClear` at `0x1800473ae`
- `ole32!PropVariantClear` at `0x1800473ae`
- `ole32!CoCreateInstance` at `0x1800472ce`
- `ole32!CoCreateInstance` at `0x1800472ce`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CContentFolder::_DeleteObject(
        CContentFolder *this,
        struct IPortableDevice *a2,
        const unsigned __int16 *a3,
        unsigned int a4,
        struct CProgressUI *a5)
{
  int v8; // r14d
  struct CProgressUI *v9; // rdi
  LONG lVal; // ebx
  PVOID *v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // r9
  int v14; // esi
  HRESULT v15; // eax
  int v16; // esi
  __int64 v18; // [rsp+30h] [rbp-71h] BYREF
  __int64 v19; // [rsp+38h] [rbp-69h] BYREF
  PROPVARIANT pvar; // [rsp+40h] [rbp-61h] BYREF
  __int128 v21; // [rsp+58h] [rbp-49h] BYREF
  __int64 v22; // [rsp+68h] [rbp-39h]
  _QWORD v23[2]; // [rsp+70h] [rbp-31h] BYREF
  __int128 v24; // [rsp+80h] [rbp-21h]
  __int128 v25; // [rsp+90h] [rbp-11h]
  __int64 v26; // [rsp+A0h] [rbp-1h]
  char v27; // [rsp+A8h] [rbp+7h]
  LPVOID ppv; // [rsp+100h] [rbp+5Fh] BYREF

  v8 = 0;
  v23[0] = 0;
  v23[1] = 0;
  v27 = 0;
  v24 = 0;
  v25 = 0;
  v26 = 0;
  memset(&pvar, 0, sizeof(pvar));
  v18 = 0;
  ppv = 0;
  v19 = 0;
  v21 = 0;
  v22 = 0;
  v9 = a5;
  if ( a5 )
  {
    v14 = 0;
    while ( !*((_DWORD *)v9 + 26) )
    {
      lVal = ((__int64 (__fastcall *)(struct IPortableDevice *, __int64 *))a2->lpVtbl->Content)(a2, &v18);
      if ( lVal != -2147024726 )
        goto LABEL_18;
      if ( !v8 )
      {
        v8 = 1;
        v14 = 1;
        CProgressUI::_StartMarquee(v9);
      }
      if ( *((_DWORD *)v9 + 26) )
        break;
      Sleep(0x5DCu);
    }
    lVal = -2147023673;
LABEL_18:
    if ( v14 )
      CProgressUI::_StopMarquee(v9);
    if ( *((_DWORD *)v9 + 26) )
    {
      lVal = -2147023673;
      goto LABEL_4;
    }
  }
  else
  {
    lVal = ((__int64 (__fastcall *)(struct IPortableDevice *, __int64 *))a2->lpVtbl->Content)(a2, &v18);
  }
  if ( lVal < 0 )
  {
LABEL_4:
    v11 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v12 = 237;
      goto LABEL_7;
    }
    goto LABEL_47;
  }
  v15 = CoCreateInstance(
          &CLSID_PortableDevicePropVariantCollection,
          0,
          1u,
          &GUID_89b2e422_4f1b_4316_bcef_a44afea83eb3,
          &ppv);
  lVal = v15;
  if ( v15 < 0 )
  {
    v11 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v12 = 238;
      v13 = (unsigned int)v15;
      goto LABEL_8;
    }
    goto LABEL_47;
  }
  LOWORD(v21) = 31;
  *((_QWORD *)&v21 + 1) = a3;
  (*(void (__fastcall **)(LPVOID, __int128 *))(*(_QWORD *)ppv + 40LL))(ppv, &v21);
  v16 = 0;
  while ( 1 )
  {
    CPerfTraceHelper::BeginOperation((CPerfTraceHelper *)v23, 0xAu);
    lVal = (*(__int64 (__fastcall **)(__int64, _QWORD, LPVOID, __int64 *))(*(_QWORD *)v18 + 64LL))(v18, a4, ppv, &v19);
    CPerfTraceHelper::ProcessPerformanceData((CPerfTraceHelper *)v23, 0xAu, lVal, a3);
    if ( lVal == 1 )
    {
      lVal = -2147467259;
      memset(&pvar, 0, sizeof(pvar));
      if ( (*(int (__fastcall **)(__int64, _QWORD, PROPVARIANT *))(*(_QWORD *)v19 + 32LL))(v19, 0, &pvar) >= 0
        && pvar.vt == 10
        && pvar.lVal < 0 )
      {
        lVal = pvar.lVal;
      }
      PropVariantClear(&pvar);
    }
    if ( lVal != -2147024726 )
      break;
    if ( v16 )
    {
      if ( !v9 )
        goto LABEL_39;
    }
    else
    {
      v16 = 1;
      if ( !v9 )
        goto LABEL_39;
      CProgressUI::_StartMarquee(v9);
    }
    if ( *((_DWORD *)v9 + 26) )
    {
      lVal = -2147023673;
      goto LABEL_43;
    }
LABEL_39:
    Sleep(0x5DCu);
  }
  if ( lVal >= 0 )
    goto LABEL_46;
LABEL_43:
  v11 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    v12 = 239;
LABEL_7:
    v13 = (unsigned int)lVal;
LABEL_8:
    WPP_SF_d(v11[2], v12, WPP_953c7f1870f230da5c3777fec273291e_Traceguids, v13);
LABEL_46:
    v11 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_47:
  if ( v9 )
  {
    if ( *((_DWORD *)v9 + 27) )
    {
      CProgressUI::_StopMarquee(v9);
      v11 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( *((_DWORD *)v9 + 26) )
    {
      lVal = -2147023673;
      goto LABEL_53;
    }
  }
  if ( lVal < 0 )
  {
LABEL_53:
    if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 2) != 0 )
      WPP_SF_d(v11[2], 240, WPP_953c7f1870f230da5c3777fec273291e_Traceguids, (unsigned int)lVal);
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v19);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppv);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v18);
  return (unsigned int)lVal;
}

```

## disassembly

```asm
0x180047160  mov     [rsp-8+arg_0], rcx
0x180047165  push    rbp
0x180047166  push    rbx
0x180047167  push    rsi
0x180047168  push    rdi
0x180047169  push    r12
0x18004716b  push    r13
0x18004716d  push    r14
0x18004716f  push    r15
0x180047171  lea     rbp, [rsp-17h]
0x180047176  sub     rsp, 0B8h
0x18004717d  mov     r13d, r9d
0x180047180  mov     r12, r8
0x180047183  mov     r15, rdx
0x180047186  xor     r14d, r14d
0x180047189  mov     [rbp+4Fh+var_80], r14
0x18004718d  mov     [rbp+4Fh+var_78], r14
0x180047191  mov     [rbp+4Fh+var_48], r14b
0x180047195  xorps   xmm0, xmm0
0x180047198  movdqa  [rbp+4Fh+var_70], xmm0
0x18004719d  xorps   xmm1, xmm1
0x1800471a0  movdqa  [rbp+4Fh+var_60], xmm1
0x1800471a5  mov     [rbp+4Fh+var_50], r14
0x1800471a9  xor     eax, eax
0x1800471ab  movups  xmmword ptr [rbp+4Fh+pvar], xmm0
0x1800471af  mov     qword ptr [rbp+4Fh+pvar+10h], rax
0x1800471b3  mov     [rbp+4Fh+var_C0], r14
0x1800471b7  mov     [rbp+4Fh+arg_0], r14
0x1800471bb  mov     [rbp+4Fh+var_B8], r14
0x1800471bf  movups  [rbp+4Fh+var_98], xmm0
0x1800471c3  mov     [rbp+4Fh+var_88], rax
0x1800471c7  lea     rsi, WPP_GLOBAL_Control
0x1800471ce  mov     rdi, [rbp+4Fh+arg_20]
0x1800471d2  test    rdi, rdi
0x1800471d5  jnz     short loc_18004722B
0x1800471d7  mov     rax, [rdx]
0x1800471da  lea     rdx, [rbp+4Fh+var_C0]
0x1800471de  mov     rcx, r15
0x1800471e1  mov     rax, [rax+28h]
0x1800471e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800471ea  mov     ebx, eax
0x1800471ec  test    ebx, ebx
0x1800471ee  jns     loc_1800472AC
0x1800471f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800471fb  cmp     rcx, rsi
0x1800471fe  jz      loc_18004742D
0x180047204  test    byte ptr [rcx+1Ch], 2
0x180047208  jz      loc_18004742D
0x18004720e  mov     edx, 0EDh
0x180047213  mov     r9d, ebx
0x180047216  lea     r8, WPP_953c7f1870f230da5c3777fec273291e_Traceguids
0x18004721d  mov     rcx, [rcx+10h]
0x180047221  call    WPP_SF_d
0x180047226  jmp     loc_180047426
0x18004722b  xor     esi, esi
0x18004722d  cmp     dword ptr [rdi+68h], 0
0x180047231  jnz     short loc_18004727D
0x180047233  mov     rax, [r15]
0x180047236  lea     rdx, [rbp+4Fh+var_C0]
0x18004723a  mov     rcx, r15
0x18004723d  mov     rax, [rax+28h]
0x180047241  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047246  mov     ebx, eax
0x180047248  cmp     eax, 800700AAh
0x18004724d  jnz     short loc_180047282
0x18004724f  test    r14d, r14d
0x180047252  jnz     short loc_180047265
0x180047254  lea     eax, [r14+1]
0x180047258  mov     r14d, eax
0x18004725b  mov     esi, eax
0x18004725d  mov     rcx, rdi; this
0x180047260  call    ?_StartMarquee@CProgressUI@@QEAAJXZ; CProgressUI::_StartMarquee(void)
0x180047265  cmp     dword ptr [rdi+68h], 0
0x180047269  jnz     short loc_18004727D
0x18004726b  mov     ecx, 5DCh; dwMilliseconds
0x180047270  call    cs:__imp_Sleep
0x180047276  test    r14d, r14d
0x180047279  jz      short loc_180047282
0x18004727b  jmp     short loc_18004722D
0x18004727d  mov     ebx, 800704C7h
0x180047282  xor     r14d, r14d
0x180047285  test    esi, esi
0x180047287  jz      short loc_180047291
0x180047289  mov     rcx, rdi; this
0x18004728c  call    ?_StopMarquee@CProgressUI@@QEAAJXZ; CProgressUI::_StopMarquee(void)
0x180047291  lea     rsi, WPP_GLOBAL_Control
0x180047298  cmp     [rdi+68h], r14d
0x18004729c  jz      loc_1800471EC
0x1800472a2  mov     ebx, 800704C7h
0x1800472a7  jmp     loc_1800471F4
0x1800472ac  lea     rax, [rbp+4Fh+arg_0]
0x1800472b0  mov     [rsp+0F0h+ppv], rax; ppv
0x1800472b5  lea     r9, _GUID_89b2e422_4f1b_4316_bcef_a44afea83eb3; riid
0x1800472bc  mov     r15d, 1
0x1800472c2  mov     r8d, r15d; dwClsContext
0x1800472c5  xor     edx, edx; pUnkOuter
0x1800472c7  lea     rcx, CLSID_PortableDevicePropVariantCollection; rclsid
0x1800472ce  call    cs:__imp_CoCreateInstance
0x1800472d4  mov     ebx, eax
0x1800472d6  test    eax, eax
0x1800472d8  jns     short loc_180047301
0x1800472da  mov     rcx, cs:WPP_GLOBAL_Control
0x1800472e1  cmp     rcx, rsi
0x1800472e4  jz      loc_18004742D
0x1800472ea  test    byte ptr [rcx+1Ch], 2
0x1800472ee  jz      loc_18004742D
0x1800472f4  mov     edx, 0EEh
0x1800472f9  mov     r9d, eax
0x1800472fc  jmp     loc_180047216
0x180047301  mov     eax, 1Fh
0x180047306  mov     word ptr [rbp+4Fh+var_98], ax
0x18004730a  mov     qword ptr [rbp+4Fh+var_98+8], r12
0x18004730e  mov     rcx, [rbp+4Fh+arg_0]
0x180047312  mov     rax, [rcx]
0x180047315  lea     rdx, [rbp+4Fh+var_98]
0x180047319  mov     rax, [rax+28h]
0x18004731d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047322  mov     esi, r14d
0x180047325  mov     eax, 0Ah
0x18004732a  mov     edx, eax; unsigned int
0x18004732c  lea     rcx, [rbp+4Fh+var_80]; this
0x180047330  call    ?BeginOperation@CPerfTraceHelper@@QEAAXK@Z; CPerfTraceHelper::BeginOperation(ulong)
0x180047335  mov     rcx, [rbp+4Fh+var_C0]
0x180047339  mov     rax, [rcx]
0x18004733c  lea     r9, [rbp+4Fh+var_B8]
0x180047340  mov     r8, [rbp+4Fh+arg_0]
0x180047344  mov     edx, r13d
0x180047347  mov     rax, [rax+40h]
0x18004734b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047350  mov     ebx, eax
0x180047352  mov     r9, r12; unsigned __int16 *
0x180047355  mov     r8d, eax; int
0x180047358  mov     edx, 0Ah; unsigned int
0x18004735d  lea     rcx, [rbp+4Fh+var_80]; this
0x180047361  call    ?ProcessPerformanceData@CPerfTraceHelper@@QEAAXKJPEBG@Z; CPerfTraceHelper::ProcessPerformanceData(ulong,long,ushort const *)
0x180047366  cmp     ebx, r15d
0x180047369  jnz     short loc_1800473B4
0x18004736b  mov     ebx, 80004005h
0x180047370  xorps   xmm0, xmm0
0x180047373  xor     eax, eax
0x180047375  movups  xmmword ptr [rbp+4Fh+pvar], xmm0
0x180047379  mov     qword ptr [rbp+4Fh+pvar+10h], rax
0x18004737d  mov     rcx, [rbp+4Fh+var_B8]
0x180047381  mov     rax, [rcx]
0x180047384  lea     r8, [rbp+4Fh+pvar]
0x180047388  xor     edx, edx
0x18004738a  mov     rax, [rax+20h]
0x18004738e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047393  test    eax, eax
0x180047395  js      short loc_1800473AA
0x180047397  mov     eax, 0Ah
0x18004739c  cmp     ax, word ptr [rbp+4Fh+pvar]
0x1800473a0  jnz     short loc_1800473AA
0x1800473a2  mov     eax, dword ptr [rbp+4Fh+pvar+8]
0x1800473a5  test    eax, eax
0x1800473a7  cmovs   ebx, eax
0x1800473aa  lea     rcx, [rbp+4Fh+pvar]; pvar
0x1800473ae  call    cs:__imp_PropVariantClear
0x1800473b4  cmp     ebx, 800700AAh
0x1800473ba  jnz     short loc_1800473F8
0x1800473bc  test    esi, esi
0x1800473be  jnz     short loc_1800473D2
0x1800473c0  mov     esi, r15d
0x1800473c3  test    rdi, rdi
0x1800473c6  jz      short loc_1800473DD
0x1800473c8  mov     rcx, rdi; this
0x1800473cb  call    ?_StartMarquee@CProgressUI@@QEAAJXZ; CProgressUI::_StartMarquee(void)
0x1800473d0  jmp     short loc_1800473D7
0x1800473d2  test    rdi, rdi
0x1800473d5  jz      short loc_1800473DD
0x1800473d7  cmp     [rdi+68h], r14d
0x1800473db  jnz     short loc_1800473F1
0x1800473dd  mov     ecx, 5DCh; dwMilliseconds
0x1800473e2  call    cs:__imp_Sleep
0x1800473e8  test    esi, esi
0x1800473ea  jz      short loc_1800473FC
0x1800473ec  jmp     loc_180047325
0x1800473f1  mov     ebx, 800704C7h
0x1800473f6  jmp     short loc_1800473FC
0x1800473f8  test    ebx, ebx
0x1800473fa  jns     short loc_18004741F
0x1800473fc  mov     rcx, cs:WPP_GLOBAL_Control
0x180047403  lea     rsi, WPP_GLOBAL_Control
0x18004740a  cmp     rcx, rsi
0x18004740d  jz      short loc_18004742D
0x18004740f  test    byte ptr [rcx+1Ch], 2
0x180047413  jz      short loc_18004742D
0x180047415  mov     edx, 0EFh
0x18004741a  jmp     loc_180047213
0x18004741f  lea     rsi, WPP_GLOBAL_Control
0x180047426  mov     rcx, cs:WPP_GLOBAL_Control
0x18004742d  test    rdi, rdi
0x180047430  jz      short loc_180047454
0x180047432  cmp     [rdi+6Ch], r14d
0x180047436  jz      short loc_180047447
0x180047438  mov     rcx, rdi; this
0x18004743b  call    ?_StopMarquee@CProgressUI@@QEAAJXZ; CProgressUI::_StopMarquee(void)
0x180047440  mov     rcx, cs:WPP_GLOBAL_Control
0x180047447  cmp     [rdi+68h], r14d
0x18004744b  jz      short loc_180047454
0x18004744d  mov     ebx, 800704C7h
0x180047452  jmp     short loc_180047458
0x180047454  test    ebx, ebx
0x180047456  jns     short loc_18004747C
0x180047458  cmp     rcx, rsi
0x18004745b  jz      short loc_18004747C
0x18004745d  test    byte ptr [rcx+1Ch], 2
0x180047461  jz      short loc_18004747C
0x180047463  mov     edx, 0F0h
0x180047468  mov     r9d, ebx
0x18004746b  lea     r8, WPP_953c7f1870f230da5c3777fec273291e_Traceguids
0x180047472  mov     rcx, [rcx+10h]
0x180047476  call    WPP_SF_d
0x18004747b  nop
0x18004747c  lea     rcx, [rbp+4Fh+var_B8]
0x180047480  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180047485  nop
0x180047486  lea     rcx, [rbp+4Fh+arg_0]
0x18004748a  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18004748f  nop
0x180047490  lea     rcx, [rbp+4Fh+var_C0]
0x180047494  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180047499  mov     eax, ebx
0x18004749b  add     rsp, 0B8h
0x1800474a2  pop     r15
0x1800474a4  pop     r14
0x1800474a6  pop     r13
0x1800474a8  pop     r12
0x1800474aa  pop     rdi
0x1800474ab  pop     rsi
0x1800474ac  pop     rbx
0x1800474ad  pop     rbp
0x1800474ae  retn
```
