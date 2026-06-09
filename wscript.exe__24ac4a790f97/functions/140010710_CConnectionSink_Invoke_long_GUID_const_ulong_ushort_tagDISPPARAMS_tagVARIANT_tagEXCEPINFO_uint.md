# CConnectionSink::Invoke(long,_GUID const &,ulong,ushort,tagDISPPARAMS *,tagVARIANT *,tagEXCEPINFO *,uint *)

- ea: `0x140010710`
- end: `0x140010ab8`
- name: `?Invoke@CConnectionSink@@UEAAJJAEBU_GUID@@KGPEAUtagDISPPARAMS@@PEAUtagVARIANT@@PEAUtagEXCEPINFO@@PEAI@Z`
- size: `936`
- prototype: `__int64 __fastcall(CConnectionSink *__hidden this, int, const struct _GUID *, unsigned int, unsigned __int16, struct tagDISPPARAMS *, struct tagVARIANT *, struct tagEXCEPINFO *, unsigned int *)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, installer_update`

## callees

- `0x140001008`
- `0x140001048`
- `0x140007ac8`
- `0x140010710`
- `0x140018010`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x140010820`
- `msvcrt!wcscpy_s` at `0x140010820`
- `msvcrt!wcscat_s` at `0x140010831`
- `msvcrt!wcscat_s` at `0x140010831`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x1400107f6`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x1400107f6`
- `OLEAUT32!__imp_SysFreeString` at `0x140010a72`
- `OLEAUT32!__imp_SysFreeString` at `0x140010a81`
- `OLEAUT32!__imp_SysFreeString` at `0x140010a72`
- `OLEAUT32!__imp_SysFreeString` at `0x140010a81`
- `OLEAUT32!__imp_VariantInit` at `0x140010925`
- `OLEAUT32!__imp_VariantInit` at `0x140010925`
- `OLEAUT32!__imp_VariantClear` at `0x140010a44`
- `OLEAUT32!__imp_VariantClear` at `0x140010a44`
- `OLEAUT32!__imp_VariantCopy` at `0x140010959`
- `OLEAUT32!__imp_VariantCopy` at `0x140010959`
- `OLEAUT32!__imp_SetErrorInfo` at `0x1400109d4`
- `OLEAUT32!__imp_SetErrorInfo` at `0x1400109d4`

## pseudocode

```c
__int64 __fastcall CConnectionSink::Invoke(
        CConnectionSink *this,
        __int64 a2,
        const struct _GUID *a3,
        unsigned int a4,
        unsigned __int16 a5,
        struct tagDISPPARAMS *a6,
        struct tagVARIANT *a7,
        struct tagEXCEPINFO *a8,
        unsigned int *a9)
{
  bool v9; // zf
  struct IDispatch *v12; // rsi
  HRESULT v13; // ebx
  __int64 v14; // rax
  __int64 v15; // rcx
  __int64 v16; // rax
  int v17; // ebx
  int ScriptDispatch; // eax
  int v19; // eax
  struct tagDISPPARAMS *v20; // r14
  UINT cNamedArgs; // edx
  unsigned __int64 v22; // rcx
  _WORD *v23; // rax
  unsigned int v24; // eax
  unsigned int i; // ebx
  unsigned int v26; // edi
  _DWORD *v27; // rax
  unsigned int j; // r8d
  __int64 v29; // rcx
  __int64 v30; // rdx
  unsigned int k; // edi
  int v33; // [rsp+20h] [rbp-71h]
  unsigned int v34; // [rsp+50h] [rbp-41h] BYREF
  int v35; // [rsp+54h] [rbp-3Dh] BYREF
  wchar_t *Destination; // [rsp+58h] [rbp-39h] BYREF
  wchar_t *Source; // [rsp+60h] [rbp-31h] BYREF
  struct IDispatch *v38; // [rsp+68h] [rbp-29h] BYREF
  void *Block[2]; // [rsp+70h] [rbp-21h] BYREF
  __int64 v40; // [rsp+80h] [rbp-11h]

  v9 = *(_QWORD *)&a3->Data1 == *(_QWORD *)&GUID_NULL.Data1;
  v35 = 0;
  v34 = 0;
  *(_OWORD *)Block = 0;
  v40 = 0;
  v12 = 0;
  Source = 0;
  Destination = 0;
  v38 = 0;
  if ( !v9 || *(_QWORD *)a3->Data4 != *(_QWORD *)GUID_NULL.Data4 )
    return (unsigned int)-2147024809;
  v13 = (*(__int64 (__fastcall **)(_QWORD, __int64, wchar_t **, __int64, int *))(**((_QWORD **)this + 3) + 56LL))(
          *((_QWORD *)this + 3),
          a2,
          &Source,
          1,
          &v35);
  if ( v13 >= 0 )
  {
    if ( !v35 )
    {
      v13 = -2147418113;
      goto LABEL_35;
    }
    v14 = *((_QWORD *)this + 2);
    if ( v14 )
    {
      v15 = -1;
      do
        ++v15;
      while ( *(_WORD *)(v14 + 2 * v15) );
    }
    else
    {
      LODWORD(v15) = 0;
    }
    if ( Source )
    {
      v16 = -1;
      do
        ++v16;
      while ( Source[v16] );
    }
    else
    {
      LODWORD(v16) = 0;
    }
    v17 = v16 + v15;
    Destination = SysAllocStringLen(0, (int)v16 + (int)v15);
    if ( !Destination )
    {
LABEL_17:
      v13 = -2147024882;
      goto LABEL_35;
    }
    wcscpy_s(Destination, v17 + 1, *((const wchar_t **)this + 2));
    wcscat_s(Destination, v17 + 1, Source);
    ScriptDispatch = CHost::GetScriptDispatch(g_pHost, &v38);
    v12 = v38;
    v13 = ScriptDispatch;
    if ( ScriptDispatch < 0 )
      goto LABEL_35;
    v34 = 0;
    v19 = ((__int64 (__fastcall *)(struct IDispatch *, GUID *, wchar_t **, __int64, unsigned int, unsigned int *))v38->lpVtbl->GetIDsOfNames)(
            v38,
            &GUID_NULL,
            &Destination,
            1,
            a4,
            &v34);
    if ( v19 < 0 )
    {
      v13 = 0;
      if ( v19 != -2147352570 )
        v13 = v19;
      goto LABEL_35;
    }
    v20 = a6;
    cNamedArgs = a6->cNamedArgs;
    if ( !cNamedArgs || *a6->rgdispidNamedArgs != -613 )
    {
      v22 = a6->cArgs + 1;
      HIDWORD(v40) = cNamedArgs + 1;
      LODWORD(v40) = v22;
      v23 = operator new(saturated_mul(v22, 0x18u));
      Block[0] = v23;
      if ( !v23 )
        goto LABEL_17;
      *v23 = 9;
      *((_QWORD *)Block[0] + 1) = *((_QWORD *)this + 1);
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 8LL))(*((_QWORD *)this + 1));
      v24 = v40;
      for ( i = 1; i < (unsigned int)v40; ++i )
      {
        VariantInit((VARIANTARG *)Block[0] + i);
        v24 = v40;
      }
      v26 = 1;
      if ( v24 > 1 )
      {
        do
        {
          v13 = VariantCopy((VARIANTARG *)Block[0] + v26, &a6->rgvarg[v26 - 1]);
          if ( v13 < 0 )
            goto LABEL_35;
        }
        while ( ++v26 < (unsigned int)v40 );
      }
      v27 = operator new(saturated_mul(HIDWORD(v40), 4u));
      Block[1] = v27;
      if ( !v27 )
        goto LABEL_17;
      *v27 = -613;
      v20 = (struct tagDISPPARAMS *)Block;
      for ( j = 1; j < HIDWORD(v40); *((_DWORD *)Block[1] + v30) = a6->rgdispidNamedArgs[v29] )
      {
        v29 = j - 1;
        v30 = j++;
      }
    }
    SetErrorInfo(0, 0);
    LOWORD(v33) = a5;
    v13 = ((__int64 (__fastcall *)(struct IDispatch *, _QWORD, GUID *, _QWORD, int, struct tagDISPPARAMS *, struct tagVARIANT *, struct tagEXCEPINFO *, unsigned int *))v12->lpVtbl->Invoke)(
            v12,
            v34,
            &GUID_NULL,
            a4,
            v33,
            v20,
            a7,
            a8,
            a9);
  }
LABEL_35:
  if ( Block[0] )
  {
    for ( k = 0; k < (unsigned int)v40; ++k )
      VariantClear((VARIANTARG *)Block[0] + k);
    operator delete(Block[0]);
  }
  if ( Block[1] )
    operator delete(Block[1]);
  if ( Source )
    SysFreeString(Source);
  if ( Destination )
    SysFreeString(Destination);
  if ( v12 )
    ((void (__fastcall *)(struct IDispatch *))v12->lpVtbl->Release)(v12);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x140010710  push    rbp
0x140010712  push    rbx
0x140010713  push    rsi
0x140010714  push    rdi
0x140010715  push    r12
0x140010717  push    r13
0x140010719  push    r14
0x14001071b  push    r15
0x14001071d  lea     rbp, [rsp-7]
0x140010722  sub     rsp, 98h
0x140010729  mov     rax, [r8]
0x14001072c  xor     r12d, r12d
0x14001072f  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x140010736  xorps   xmm0, xmm0
0x140010739  mov     r15d, r9d
0x14001073c  mov     [rbp+3Fh+var_7C], r12d
0x140010740  mov     rdi, rcx
0x140010743  mov     [rbp+3Fh+var_80], r12d
0x140010747  movdqu  xmmword ptr [rbp+3Fh+Block], xmm0
0x14001074c  mov     [rbp+3Fh+var_50], r12
0x140010750  mov     esi, r12d
0x140010753  mov     [rbp+3Fh+Source], r12
0x140010757  mov     [rbp+3Fh+Destination], r12
0x14001075b  mov     [rbp+3Fh+var_68], r12
0x14001075f  jnz     loc_140010A9D
0x140010765  mov     rax, [r8+8]
0x140010769  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x140010770  jnz     loc_140010A9D
0x140010776  mov     rcx, [rcx+18h]
0x14001077a  lea     r8, [rbp+3Fh+var_7C]
0x14001077e  mov     [rsp+0D0h+var_B0], r8
0x140010783  lea     r13d, [r12+1]
0x140010788  mov     r9d, r13d
0x14001078b  lea     r8, [rbp+3Fh+Source]
0x14001078f  mov     rax, [rcx]
0x140010792  mov     rax, [rax+38h]
0x140010796  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001079b  mov     ebx, eax
0x14001079d  test    eax, eax
0x14001079f  js      loc_140010A27
0x1400107a5  cmp     [rbp+3Fh+var_7C], r12d
0x1400107a9  jnz     short loc_1400107B5
0x1400107ab  mov     ebx, 8000FFFFh
0x1400107b0  jmp     loc_140010A27
0x1400107b5  mov     rax, [rdi+10h]
0x1400107b9  or      r8, 0FFFFFFFFFFFFFFFFh
0x1400107bd  test    rax, rax
0x1400107c0  jz      short loc_1400107D1
0x1400107c2  mov     rcx, r8
0x1400107c5  inc     rcx
0x1400107c8  cmp     [rax+rcx*2], r12w
0x1400107cd  jnz     short loc_1400107C5
0x1400107cf  jmp     short loc_1400107D4
0x1400107d1  mov     rcx, r12
0x1400107d4  mov     rdx, [rbp+3Fh+Source]
0x1400107d8  test    rdx, rdx
0x1400107db  jz      short loc_1400107EC
0x1400107dd  mov     rax, r8
0x1400107e0  inc     rax
0x1400107e3  cmp     [rdx+rax*2], r12w
0x1400107e8  jnz     short loc_1400107E0
0x1400107ea  jmp     short loc_1400107EF
0x1400107ec  mov     rax, r12
0x1400107ef  lea     ebx, [rax+rcx]
0x1400107f2  xor     ecx, ecx; strIn
0x1400107f4  mov     edx, ebx; ui
0x1400107f6  call    cs:__imp_SysAllocStringLen
0x1400107fc  mov     [rbp+3Fh+Destination], rax
0x140010800  test    rax, rax
0x140010803  jnz     short loc_14001080F
0x140010805  mov     ebx, 8007000Eh
0x14001080a  jmp     loc_140010A27
0x14001080f  mov     r8, [rdi+10h]; Source
0x140010813  lea     eax, [rbx+1]
0x140010816  mov     rcx, [rbp+3Fh+Destination]; Destination
0x14001081a  movsxd  rbx, eax
0x14001081d  mov     rdx, rbx; SizeInWords
0x140010820  call    cs:__imp_wcscpy_s
0x140010826  mov     r8, [rbp+3Fh+Source]; Source
0x14001082a  mov     rdx, rbx; SizeInWords
0x14001082d  mov     rcx, [rbp+3Fh+Destination]; Destination
0x140010831  call    cs:__imp_wcscat_s
0x140010837  mov     rcx, cs:?g_pHost@@3PEAVCHost@@EA; this
0x14001083e  lea     rdx, [rbp+3Fh+var_68]; struct IDispatch **
0x140010842  call    ?GetScriptDispatch@CHost@@QEAAJPEAPEAUIDispatch@@@Z; CHost::GetScriptDispatch(IDispatch * *)
0x140010847  mov     rsi, [rbp+3Fh+var_68]
0x14001084b  mov     ebx, eax
0x14001084d  test    eax, eax
0x14001084f  js      loc_140010A27
0x140010855  mov     [rbp+3Fh+var_80], r12d
0x140010859  lea     rcx, [rbp+3Fh+var_80]
0x14001085d  mov     rax, [rsi]
0x140010860  lea     r8, [rbp+3Fh+Destination]
0x140010864  mov     [rsp+0D0h+var_A8], rcx
0x140010869  lea     rdx, GUID_NULL
0x140010870  mov     r9d, r13d
0x140010873  mov     dword ptr [rsp+0D0h+var_B0], r15d
0x140010878  mov     rcx, rsi
0x14001087b  mov     rax, [rax+28h]
0x14001087f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010884  test    eax, eax
0x140010886  jns     short loc_140010898
0x140010888  cmp     eax, 80020006h
0x14001088d  mov     ebx, r12d
0x140010890  cmovnz  ebx, eax
0x140010893  jmp     loc_140010A27
0x140010898  mov     r14, [rbp+3Fh+arg_28]
0x14001089c  mov     edx, [r14+14h]
0x1400108a0  test    edx, edx
0x1400108a2  jz      short loc_1400108B4
0x1400108a4  mov     rax, [r14+8]
0x1400108a8  cmp     dword ptr [rax], 0FFFFFD9Bh
0x1400108ae  jz      loc_1400109D0
0x1400108b4  mov     ecx, [r14+10h]
0x1400108b8  lea     eax, [rdx+1]
0x1400108bb  inc     ecx
0x1400108bd  mov     dword ptr [rbp+3Fh+var_50+4], eax
0x1400108c0  mov     dword ptr [rbp+3Fh+var_50], ecx
0x1400108c3  mov     eax, 18h
0x1400108c8  mul     rcx
0x1400108cb  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1400108d2  cmovb   rax, rcx
0x1400108d6  mov     rcx, rax; Size
0x1400108d9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400108de  mov     [rbp+3Fh+Block], rax
0x1400108e2  test    rax, rax
0x1400108e5  jz      loc_140010805
0x1400108eb  mov     word ptr [rax], 9
0x1400108f0  mov     rax, [rbp+3Fh+Block]
0x1400108f4  mov     rcx, [rdi+8]
0x1400108f8  mov     [rax+8], rcx
0x1400108fc  mov     rcx, [rdi+8]
0x140010900  mov     rax, [rcx]
0x140010903  mov     rax, [rax+8]
0x140010907  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001090c  mov     eax, dword ptr [rbp+3Fh+var_50]
0x14001090f  mov     ebx, r13d
0x140010912  cmp     eax, r13d
0x140010915  jbe     short loc_140010935
0x140010917  mov     eax, ebx
0x140010919  lea     rcx, [rax+rax*2]
0x14001091d  mov     rax, [rbp+3Fh+Block]
0x140010921  lea     rcx, [rax+rcx*8]; pvarg
0x140010925  call    cs:__imp_VariantInit
0x14001092b  mov     eax, dword ptr [rbp+3Fh+var_50]
0x14001092e  add     ebx, r13d
0x140010931  cmp     ebx, eax
0x140010933  jb      short loc_140010917
0x140010935  mov     edi, r13d
0x140010938  cmp     eax, r13d
0x14001093b  jbe     short loc_140010971
0x14001093d  lea     eax, [rdi-1]
0x140010940  lea     rdx, [rax+rax*2]
0x140010944  mov     rax, [r14]
0x140010947  lea     rdx, [rax+rdx*8]; pvargSrc
0x14001094b  mov     eax, edi
0x14001094d  lea     rcx, [rax+rax*2]
0x140010951  mov     rax, [rbp+3Fh+Block]
0x140010955  lea     rcx, [rax+rcx*8]; pvargDest
0x140010959  call    cs:__imp_VariantCopy
0x14001095f  mov     ebx, eax
0x140010961  test    eax, eax
0x140010963  js      loc_140010A27
0x140010969  add     edi, r13d
0x14001096c  cmp     edi, dword ptr [rbp+3Fh+var_50]
0x14001096f  jb      short loc_14001093D
0x140010971  mov     ecx, dword ptr [rbp+3Fh+var_50+4]
0x140010974  mov     eax, 4
0x140010979  mul     rcx
0x14001097c  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x140010983  cmovb   rax, rcx
0x140010987  mov     rcx, rax; Size
0x14001098a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14001098f  mov     [rbp+3Fh+Block+8], rax
0x140010993  test    rax, rax
0x140010996  jz      loc_140010805
0x14001099c  mov     dword ptr [rax], 0FFFFFD9Bh
0x1400109a2  mov     r9, r14
0x1400109a5  lea     r14, [rbp+3Fh+Block]
0x1400109a9  mov     r8d, r13d
0x1400109ac  cmp     dword ptr [rbp+3Fh+var_50+4], r13d
0x1400109b0  jbe     short loc_1400109D0
0x1400109b2  mov     rax, [r9+8]
0x1400109b6  lea     ecx, [r8-1]
0x1400109ba  mov     edx, r8d
0x1400109bd  add     r8d, r13d
0x1400109c0  mov     ecx, [rax+rcx*4]
0x1400109c3  mov     rax, [rbp+3Fh+Block+8]
0x1400109c7  mov     [rax+rdx*4], ecx
0x1400109ca  cmp     r8d, dword ptr [rbp+3Fh+var_50+4]
0x1400109ce  jb      short loc_1400109B2
0x1400109d0  xor     edx, edx; perrinfo
0x1400109d2  xor     ecx, ecx; dwReserved
0x1400109d4  call    cs:__imp_SetErrorInfo
0x1400109da  mov     rcx, [rbp+3Fh+arg_40]
0x1400109e1  lea     r8, GUID_NULL
0x1400109e8  mov     rax, [rsi]
0x1400109eb  mov     r9d, r15d
0x1400109ee  mov     edx, [rbp+3Fh+var_80]
0x1400109f1  mov     [rsp+0D0h+var_90], rcx
0x1400109f6  mov     rcx, [rbp+3Fh+arg_38]
0x1400109fd  mov     rax, [rax+30h]
0x140010a01  mov     [rsp+0D0h+var_98], rcx
0x140010a06  mov     rcx, [rbp+3Fh+arg_30]
0x140010a0a  mov     [rsp+0D0h+var_A0], rcx
0x140010a0f  movzx   ecx, [rbp+3Fh+arg_20]
0x140010a13  mov     [rsp+0D0h+var_A8], r14
0x140010a18  mov     word ptr [rsp+0D0h+var_B0], cx
0x140010a1d  mov     rcx, rsi
0x140010a20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010a25  mov     ebx, eax
0x140010a27  cmp     [rbp+3Fh+Block], r12
0x140010a2b  jz      short loc_140010A5B
0x140010a2d  mov     edi, r12d
0x140010a30  cmp     dword ptr [rbp+3Fh+var_50], r12d
0x140010a34  jbe     short loc_140010A52
0x140010a36  mov     eax, edi
0x140010a38  lea     rcx, [rax+rax*2]
0x140010a3c  mov     rax, [rbp+3Fh+Block]
0x140010a40  lea     rcx, [rax+rcx*8]; pvarg
0x140010a44  call    cs:__imp_VariantClear
0x140010a4a  add     edi, r13d
0x140010a4d  cmp     edi, dword ptr [rbp+3Fh+var_50]
0x140010a50  jb      short loc_140010A36
0x140010a52  mov     rcx, [rbp+3Fh+Block]; Block
0x140010a56  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140010a5b  mov     rcx, [rbp+3Fh+Block+8]; Block
0x140010a5f  test    rcx, rcx
0x140010a62  jz      short loc_140010A69
0x140010a64  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140010a69  mov     rcx, [rbp+3Fh+Source]; bstrString
0x140010a6d  test    rcx, rcx
0x140010a70  jz      short loc_140010A78
0x140010a72  call    cs:__imp_SysFreeString
0x140010a78  mov     rcx, [rbp+3Fh+Destination]; bstrString
0x140010a7c  test    rcx, rcx
0x140010a7f  jz      short loc_140010A87
0x140010a81  call    cs:__imp_SysFreeString
0x140010a87  test    rsi, rsi
0x140010a8a  jz      short loc_140010AA2
0x140010a8c  mov     rax, [rsi]
0x140010a8f  mov     rcx, rsi
0x140010a92  mov     rax, [rax+10h]
0x140010a96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010a9b  jmp     short loc_140010AA2
0x140010a9d  mov     ebx, 80070057h
0x140010aa2  mov     eax, ebx
0x140010aa4  add     rsp, 98h
0x140010aab  pop     r15
0x140010aad  pop     r14
0x140010aaf  pop     r13
0x140010ab1  pop     r12
0x140010ab3  pop     rdi
0x140010ab4  pop     rsi
0x140010ab5  pop     rbx
0x140010ab6  pop     rbp
0x140010ab7  retn
```
