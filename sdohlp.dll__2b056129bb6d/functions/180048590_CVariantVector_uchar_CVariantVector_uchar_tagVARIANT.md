# CVariantVector<uchar>::CVariantVector<uchar>(tagVARIANT *)

- ea: `0x180048590`
- end: `0x180048696`
- name: `??0?$CVariantVector@E@@QEAA@PEAUtagVARIANT@@@Z`
- size: `262`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18004bdbc`

## callees

- `0x180024068`
- `0x180041148`
- `0x180048590`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayGetDim` at `0x1800485b5`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x1800485b5`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1800485f9`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1800485f9`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1800485db`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1800485db`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18004864b`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18004864b`

## pseudocode

```c
__int64 __fastcall CVariantVector<unsigned char>::CVariantVector<unsigned char>(__int64 a1, __int64 a2)
{
  SAFEARRAY *v3; // rcx
  SAFEARRAY *v4; // rcx
  HRESULT LBound; // eax
  HRESULT UBound; // eax
  bool v7; // sf
  HRESULT v8; // eax
  void **pExceptionObject; // [rsp+20h] [rbp-20h] BYREF
  int v11; // [rsp+28h] [rbp-18h]
  __int128 v12; // [rsp+30h] [rbp-10h]
  LONG plUbound; // [rsp+50h] [rbp+10h] BYREF
  LONG plLbound; // [rsp+58h] [rbp+18h] BYREF

  v3 = *(SAFEARRAY **)(a2 + 8);
  *(_QWORD *)a1 = v3;
  if ( *(_WORD *)a2 != 8209 || SafeArrayGetDim(v3) != 1 )
  {
    v11 = -2147352571;
    pExceptionObject = &_com_error::`vftable';
    v12 = 0;
    throw (_com_error *)&pExceptionObject;
  }
  v4 = *(SAFEARRAY **)a1;
  plLbound = 0;
  plUbound = 0;
  LBound = SafeArrayGetLBound(v4, 1u, &plLbound);
  if ( LBound < 0 )
    _com_issue_error(LBound);
  UBound = SafeArrayGetUBound(*(SAFEARRAY **)a1, 1u, &plUbound);
  if ( UBound < 0 )
    _com_issue_error(UBound);
  v7 = plUbound - plLbound + 1 < 0;
  *(_DWORD *)(a1 + 8) = plUbound - plLbound + 1;
  if ( v7 )
  {
    v11 = -2147352565;
    pExceptionObject = &_com_error::`vftable';
    v12 = 0;
    throw (_com_error *)&pExceptionObject;
  }
  v8 = SafeArrayAccessData(*(SAFEARRAY **)a1, (void **)(a1 + 16));
  if ( v8 < 0 )
    _com_issue_error(v8);
  return a1;
}

```

## disassembly

```asm
0x180048590  mov     [rsp-8+arg_10], rbx
0x180048595  push    rbp
0x180048596  mov     rbp, rsp
0x180048599  sub     rsp, 40h
0x18004859d  mov     rbx, rcx
0x1800485a0  mov     eax, 2011h
0x1800485a5  mov     rcx, [rdx+8]; psa
0x1800485a9  mov     [rbx], rcx
0x1800485ac  cmp     [rdx], ax
0x1800485af  jnz     loc_18004866B
0x1800485b5  call    cs:__imp_SafeArrayGetDim
0x1800485bb  cmp     eax, 1
0x1800485be  jnz     loc_18004866B
0x1800485c4  mov     rcx, [rbx]; psa
0x1800485c7  lea     r8, [rbp+plLbound]; plLbound
0x1800485cb  mov     edx, eax; nDim
0x1800485cd  mov     [rbp+plLbound], 0
0x1800485d4  mov     [rbp+plUbound], 0
0x1800485db  call    cs:__imp_SafeArrayGetLBound
0x1800485e1  test    eax, eax
0x1800485e3  jns     short loc_1800485ED
0x1800485e5  mov     ecx, eax; int
0x1800485e7  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x1800485ed  mov     rcx, [rbx]; psa
0x1800485f0  lea     r8, [rbp+plUbound]; plUbound
0x1800485f4  mov     edx, 1; nDim
0x1800485f9  call    cs:__imp_SafeArrayGetUBound
0x1800485ff  test    eax, eax
0x180048601  jns     short loc_18004860B
0x180048603  mov     ecx, eax; int
0x180048605  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x18004860b  mov     eax, [rbp+plUbound]
0x18004860e  sub     eax, [rbp+plLbound]
0x180048611  add     eax, 1
0x180048614  mov     [rbx+8], eax
0x180048617  jns     short loc_180048644
0x180048619  lea     rax, ??_7_com_error@@6B@; const _com_error::`vftable'
0x180048620  mov     [rbp+var_18], 8002000Bh
0x180048627  xorps   xmm0, xmm0
0x18004862a  mov     [rbp+pExceptionObject], rax
0x18004862e  lea     rdx, _TI1?AV_com_error@@; pThrowInfo
0x180048635  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180048639  movdqu  [rbp+var_10], xmm0
0x18004863e  call    _CxxThrowException_0
0x180048644  mov     rcx, [rbx]; psa
0x180048647  lea     rdx, [rbx+10h]; ppvData
0x18004864b  call    cs:__imp_SafeArrayAccessData
0x180048651  test    eax, eax
0x180048653  jns     short loc_18004865D
0x180048655  mov     ecx, eax; int
0x180048657  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x18004865d  mov     rax, rbx
0x180048660  mov     rbx, [rsp+40h+arg_10]
0x180048665  add     rsp, 40h
0x180048669  pop     rbp
0x18004866a  retn
0x18004866b  lea     rax, ??_7_com_error@@6B@; const _com_error::`vftable'
0x180048672  mov     [rbp+var_18], 80020005h
0x180048679  xorps   xmm0, xmm0
0x18004867c  mov     [rbp+pExceptionObject], rax
0x180048680  lea     rdx, _TI1?AV_com_error@@; pThrowInfo
0x180048687  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18004868b  movdqu  [rbp+var_10], xmm0
0x180048690  call    _CxxThrowException_0
```
