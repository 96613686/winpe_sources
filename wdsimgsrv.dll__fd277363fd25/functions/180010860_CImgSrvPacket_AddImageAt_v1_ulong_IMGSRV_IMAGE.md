# CImgSrvPacket::AddImageAt_v1(ulong,_IMGSRV_IMAGE *)

- ea: `0x180010860`
- end: `0x180010b7e`
- name: `?AddImageAt_v1@CImgSrvPacket@@AEAAKKPEAU_IMGSRV_IMAGE@@@Z`
- size: `798`
- prototype: `__int64 __fastcall(void **this, unsigned int, struct _IMGSRV_IMAGE *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800102a0`

## callees

- `0x18000fdf8`
- `0x18000fe8c`
- `0x180010860`
- `0x180010ef0`
- `0x180010f6c`
- `0x180016020`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180010af4`
- `KERNEL32!GetLastError` at `0x180010b12`
- `KERNEL32!GetLastError` at `0x180010af4`
- `KERNEL32!GetLastError` at `0x180010b12`
- `WDSCSL!WdsCpParameterAdd` at `0x180010ae3`
- `WDSCSL!WdsCpParameterAdd` at `0x180010ae3`
- `WdsCommonLib!?WIN32_FROM_HRESULT@@YAKJ@Z` at `0x180010b4f`
- `WdsCommonLib!?WIN32_FROM_HRESULT@@YAKJ@Z` at `0x180010b4f`

## string_xrefs

- `0x18001088c`: `XML_%d`
- `0x1800108eb`: `PATH_%d`
- `0x180010a3f`: `RESOURCEFILEPATH_%d`

## pseudocode

```c
__int64 __fastcall CImgSrvPacket::AddImageAt_v1(void **this, unsigned int a2, struct _IMGSRV_IMAGE *a3)
{
  unsigned int v6; // ebx
  __int64 v7; // r15
  __int64 v8; // rdx
  __int64 v9; // r8
  unsigned int v10; // ecx
  __int64 v11; // rdx
  __int64 v12; // r8
  __int64 v13; // rdx
  __int64 v14; // r8
  __int64 v15; // rdx
  __int64 v16; // r8
  __int64 v17; // rdx
  __int64 v18; // r8
  __int64 v19; // rdx
  __int64 v20; // r8
  __int64 v21; // rdx
  __int64 v22; // r8
  __int64 v23; // rdx
  __int64 v24; // r8
  __int64 v25; // rdx
  __int64 v26; // r8
  __int64 v27; // rdx
  __int64 v28; // r8
  __int64 v29; // rdx
  __int64 v30; // r8
  __int64 v31; // rdx
  __int64 v32; // r8
  __int64 v33; // r14
  __int64 v34; // rdx
  __int64 v35; // r8
  __int64 v36; // rdx
  __int64 v37; // r8
  void *v38; // rcx
  unsigned int v39; // edi
  __int64 v40; // rsi
  _QWORD *v41; // rax
  signed int LastError; // eax
  bool v43; // sf
  signed int v44; // eax
  unsigned __int16 v46[32]; // [rsp+30h] [rbp-50h] BYREF

  v6 = 0;
  v7 = (unsigned int)StringCbPrintfW(v46, 0x40u, L"XML_%d", a2);
  if ( (int)ElValidateHr_4(v7, v8, v9, 661) < 0 )
    goto LABEL_2;
  v7 = (unsigned int)WdsCliAddVarWstr(this[1], v46, *(unsigned __int16 **)a3);
  if ( (int)ElValidateHr_4(v7, v11, v12, 664) < 0 )
    goto LABEL_2;
  v7 = (unsigned int)StringCbPrintfW(v46, 0x40u, L"PATH_%d", a2);
  if ( (int)ElValidateHr_4(v7, v13, v14, 674) < 0 )
    goto LABEL_2;
  v7 = (unsigned int)WdsCliAddVarWstr(this[1], v46, *((unsigned __int16 **)a3 + 1));
  if ( (int)ElValidateHr_4(v7, v15, v16, 680) < 0 )
    goto LABEL_2;
  v7 = (unsigned int)StringCbPrintfW(v46, 0x40u, L"GROUP_%d", a2);
  if ( (int)ElValidateHr_4(v7, v17, v18, 690) < 0
    || (v7 = (unsigned int)WdsCliAddVarWstr(this[1], v46, *((unsigned __int16 **)a3 + 3)),
        (int)ElValidateHr_4(v7, v19, v20, 693) < 0)
    || (v7 = (unsigned int)StringCbPrintfW(v46, 0x40u, L"INDEX_%d", a2), (int)ElValidateHr_4(v7, v21, v22, 703) < 0)
    || (v7 = (unsigned int)WdsCliAddVarUlong(this[1], v46, *((_DWORD *)a3 + 8)),
        (int)ElValidateHr_4(v7, v23, v24, 706) < 0)
    || (v7 = (unsigned int)StringCbPrintfW(v46, 0x40u, L"NAMESPACE_%d", a2), (int)ElValidateHr_4(v7, v25, v26, 716) < 0)
    || (v7 = (unsigned int)WdsCliAddVarWstr(this[1], v46, *((unsigned __int16 **)a3 + 5)),
        (int)ElValidateHr_4(v7, v27, v28, 719) < 0)
    || (v7 = (unsigned int)StringCbPrintfW(v46, 0x40u, L"RESOURCEFILEPATH_%d", a2),
        (int)ElValidateHr_4(v7, v29, v30, 729) < 0)
    || (v7 = (unsigned int)WdsCliAddVarWstr(this[1], v46, *((unsigned __int16 **)a3 + 2)),
        (int)ElValidateHr_4(v7, v31, v32, 735) < 0) )
  {
LABEL_2:
    v10 = v7;
    return WIN32_FROM_HRESULT(v10);
  }
  v33 = (unsigned int)StringCbPrintfW(v46, 0x40u, L"NAMESPACE_SIZE_%d", a2);
  if ( (int)ElValidateHr_4(v33, v34, v35, 745) < 0 )
  {
    v10 = v33;
    return WIN32_FROM_HRESULT(v10);
  }
  v38 = this[1];
  v39 = 0;
  v40 = *((_QWORD *)a3 + 6);
  if ( v38 )
  {
    v41 = (_QWORD *)WdsCpParameterAdd(v38, v46, 8);
    if ( v41 )
    {
      *v41 = v40;
    }
    else
    {
      LastError = GetLastError();
      v43 = LastError < 0;
      if ( LastError > 0 )
        v43 = 1;
      if ( v43 )
      {
        v44 = GetLastError();
        v39 = v44;
        if ( v44 > 0 )
          v39 = (unsigned __int16)v44 | 0x80070000;
      }
      else
      {
        v39 = -2147467259;
      }
    }
  }
  else
  {
    v39 = -2147024809;
  }
  if ( (int)ElValidateHr_4(v39, v36, v37, 751) < 0 )
  {
    v10 = v39;
    return WIN32_FROM_HRESULT(v10);
  }
  return v6;
}

```

## disassembly

```asm
0x180010860  push    rbp
0x180010862  push    rbx
0x180010863  push    rsi
0x180010864  push    rdi
0x180010865  push    r12
0x180010867  push    r14
0x180010869  push    r15
0x18001086b  mov     rbp, rsp
0x18001086e  sub     rsp, 80h
0x180010875  mov     rax, cs:__security_cookie
0x18001087c  xor     rax, rsp
0x18001087f  mov     [rbp+var_10], rax
0x180010883  mov     rsi, r8
0x180010886  mov     r14d, edx
0x180010889  mov     rdi, rcx
0x18001088c  lea     r8, aXmlD; "XML_%d"
0x180010893  mov     r9d, edx
0x180010896  lea     rcx, [rbp+var_50]; unsigned __int16 *
0x18001089a  xor     ebx, ebx
0x18001089c  lea     r12d, [rbx+40h]
0x1800108a0  mov     edx, r12d; unsigned __int64
0x1800108a3  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800108a8  mov     r9d, 295h
0x1800108ae  mov     ecx, eax
0x1800108b0  mov     r15d, eax
0x1800108b3  call    ElValidateHr_4
0x1800108b8  test    eax, eax
0x1800108ba  jns     short loc_1800108C4
0x1800108bc  mov     ecx, r15d
0x1800108bf  jmp     loc_180010B4F
0x1800108c4  mov     r8, [rsi]; unsigned __int16 *
0x1800108c7  lea     rdx, [rbp+var_50]; unsigned __int16 *
0x1800108cb  mov     rcx, [rdi+8]; void *
0x1800108cf  call    ?WdsCliAddVarWstr@@YAJPEAXPEAG1@Z; WdsCliAddVarWstr(void *,ushort *,ushort *)
0x1800108d4  mov     r9d, 298h
0x1800108da  mov     ecx, eax
0x1800108dc  mov     r15d, eax
0x1800108df  call    ElValidateHr_4
0x1800108e4  test    eax, eax
0x1800108e6  js      short loc_1800108BC
0x1800108e8  mov     r9d, r14d
0x1800108eb  lea     r8, aPathD; "PATH_%d"
0x1800108f2  mov     rdx, r12; unsigned __int64
0x1800108f5  lea     rcx, [rbp+var_50]; unsigned __int16 *
0x1800108f9  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800108fe  mov     r9d, 2A2h
0x180010904  mov     ecx, eax
0x180010906  mov     r15d, eax
0x180010909  call    ElValidateHr_4
0x18001090e  test    eax, eax
0x180010910  js      short loc_1800108BC
0x180010912  mov     r8, [rsi+8]; unsigned __int16 *
0x180010916  lea     rdx, [rbp+var_50]; unsigned __int16 *
0x18001091a  mov     rcx, [rdi+8]; void *
0x18001091e  call    ?WdsCliAddVarWstr@@YAJPEAXPEAG1@Z; WdsCliAddVarWstr(void *,ushort *,ushort *)
0x180010923  mov     r9d, 2A8h
0x180010929  mov     ecx, eax
0x18001092b  mov     r15d, eax
0x18001092e  call    ElValidateHr_4
0x180010933  test    eax, eax
0x180010935  js      short loc_1800108BC
0x180010937  mov     r9d, r14d
0x18001093a  lea     r8, aGroupD; "GROUP_%d"
0x180010941  mov     rdx, r12; unsigned __int64
0x180010944  lea     rcx, [rbp+var_50]; unsigned __int16 *
0x180010948  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001094d  mov     r9d, 2B2h
0x180010953  mov     ecx, eax
0x180010955  mov     r15d, eax
0x180010958  call    ElValidateHr_4
0x18001095d  test    eax, eax
0x18001095f  js      loc_1800108BC
0x180010965  mov     r8, [rsi+18h]; unsigned __int16 *
0x180010969  lea     rdx, [rbp+var_50]; unsigned __int16 *
0x18001096d  mov     rcx, [rdi+8]; void *
0x180010971  call    ?WdsCliAddVarWstr@@YAJPEAXPEAG1@Z; WdsCliAddVarWstr(void *,ushort *,ushort *)
0x180010976  mov     r9d, 2B5h
0x18001097c  mov     ecx, eax
0x18001097e  mov     r15d, eax
0x180010981  call    ElValidateHr_4
0x180010986  test    eax, eax
0x180010988  js      loc_1800108BC
0x18001098e  mov     r9d, r14d
0x180010991  lea     r8, aIndexD; "INDEX_%d"
0x180010998  mov     rdx, r12; unsigned __int64
0x18001099b  lea     rcx, [rbp+var_50]; unsigned __int16 *
0x18001099f  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800109a4  mov     r9d, 2BFh
0x1800109aa  mov     ecx, eax
0x1800109ac  mov     r15d, eax
0x1800109af  call    ElValidateHr_4
0x1800109b4  test    eax, eax
0x1800109b6  js      loc_1800108BC
0x1800109bc  mov     r8d, [rsi+20h]; unsigned int
0x1800109c0  lea     rdx, [rbp+var_50]; unsigned __int16 *
0x1800109c4  mov     rcx, [rdi+8]; void *
0x1800109c8  call    ?WdsCliAddVarUlong@@YAJPEAXPEAGK@Z; WdsCliAddVarUlong(void *,ushort *,ulong)
0x1800109cd  mov     r9d, 2C2h
0x1800109d3  mov     ecx, eax
0x1800109d5  mov     r15d, eax
0x1800109d8  call    ElValidateHr_4
0x1800109dd  test    eax, eax
0x1800109df  js      loc_1800108BC
0x1800109e5  mov     r9d, r14d
0x1800109e8  lea     r8, aNamespaceD; "NAMESPACE_%d"
0x1800109ef  mov     rdx, r12; unsigned __int64
0x1800109f2  lea     rcx, [rbp+var_50]; unsigned __int16 *
0x1800109f6  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800109fb  mov     r9d, 2CCh
0x180010a01  mov     ecx, eax
0x180010a03  mov     r15d, eax
0x180010a06  call    ElValidateHr_4
0x180010a0b  test    eax, eax
0x180010a0d  js      loc_1800108BC
0x180010a13  mov     r8, [rsi+28h]; unsigned __int16 *
0x180010a17  lea     rdx, [rbp+var_50]; unsigned __int16 *
0x180010a1b  mov     rcx, [rdi+8]; void *
0x180010a1f  call    ?WdsCliAddVarWstr@@YAJPEAXPEAG1@Z; WdsCliAddVarWstr(void *,ushort *,ushort *)
0x180010a24  mov     r9d, 2CFh
0x180010a2a  mov     ecx, eax
0x180010a2c  mov     r15d, eax
0x180010a2f  call    ElValidateHr_4
0x180010a34  test    eax, eax
0x180010a36  js      loc_1800108BC
0x180010a3c  mov     r9d, r14d
0x180010a3f  lea     r8, aResourcefilepa; "RESOURCEFILEPATH_%d"
0x180010a46  mov     rdx, r12; unsigned __int64
0x180010a49  lea     rcx, [rbp+var_50]; unsigned __int16 *
0x180010a4d  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180010a52  mov     r9d, 2D9h
0x180010a58  mov     ecx, eax
0x180010a5a  mov     r15d, eax
0x180010a5d  call    ElValidateHr_4
0x180010a62  test    eax, eax
0x180010a64  js      loc_1800108BC
0x180010a6a  mov     r8, [rsi+10h]; unsigned __int16 *
0x180010a6e  lea     rdx, [rbp+var_50]; unsigned __int16 *
0x180010a72  mov     rcx, [rdi+8]; void *
0x180010a76  call    ?WdsCliAddVarWstr@@YAJPEAXPEAG1@Z; WdsCliAddVarWstr(void *,ushort *,ushort *)
0x180010a7b  mov     r9d, 2DFh
0x180010a81  mov     ecx, eax
0x180010a83  mov     r15d, eax
0x180010a86  call    ElValidateHr_4
0x180010a8b  test    eax, eax
0x180010a8d  js      loc_1800108BC
0x180010a93  mov     r9d, r14d
0x180010a96  lea     r8, aNamespaceSizeD; "NAMESPACE_SIZE_%d"
0x180010a9d  mov     rdx, r12; unsigned __int64
0x180010aa0  lea     rcx, [rbp+var_50]; unsigned __int16 *
0x180010aa4  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180010aa9  mov     r9d, 2E9h
0x180010aaf  mov     ecx, eax
0x180010ab1  mov     r14d, eax
0x180010ab4  call    ElValidateHr_4
0x180010ab9  test    eax, eax
0x180010abb  jns     short loc_180010AC5
0x180010abd  mov     ecx, r14d
0x180010ac0  jmp     loc_180010B4F
0x180010ac5  mov     rcx, [rdi+8]
0x180010ac9  mov     edi, ebx
0x180010acb  mov     rsi, [rsi+30h]
0x180010acf  test    rcx, rcx
0x180010ad2  jz      short loc_180010B37
0x180010ad4  xor     r9d, r9d
0x180010ad7  mov     [rsp+80h+var_60], ebx
0x180010adb  lea     rdx, [rbp+var_50]
0x180010adf  lea     r8d, [r9+8]
0x180010ae3  call    cs:__imp_WdsCpParameterAdd
0x180010aea  nop     dword ptr [rax+rax+00h]
0x180010aef  test    rax, rax
0x180010af2  jnz     short loc_180010B32
0x180010af4  call    cs:__imp_GetLastError
0x180010afb  nop     dword ptr [rax+rax+00h]
0x180010b00  mov     esi, 80070000h
0x180010b05  test    eax, eax
0x180010b07  jle     short loc_180010B10
0x180010b09  movzx   eax, ax
0x180010b0c  or      eax, esi
0x180010b0e  test    eax, eax
0x180010b10  jns     short loc_180010B2B
0x180010b12  call    cs:__imp_GetLastError
0x180010b19  nop     dword ptr [rax+rax+00h]
0x180010b1e  mov     edi, eax
0x180010b20  test    eax, eax
0x180010b22  jle     short loc_180010B3C
0x180010b24  movzx   edi, ax
0x180010b27  or      edi, esi
0x180010b29  jmp     short loc_180010B3C
0x180010b2b  mov     edi, 80004005h
0x180010b30  jmp     short loc_180010B3C
0x180010b32  mov     [rax], rsi
0x180010b35  jmp     short loc_180010B3C
0x180010b37  mov     edi, 80070057h
0x180010b3c  mov     r9d, 2EFh
0x180010b42  mov     ecx, edi
0x180010b44  call    ElValidateHr_4
0x180010b49  test    eax, eax
0x180010b4b  jns     short loc_180010B5D
0x180010b4d  mov     ecx, edi
0x180010b4f  call    cs:__imp_?WIN32_FROM_HRESULT@@YAKJ@Z; WIN32_FROM_HRESULT(long)
0x180010b56  nop     dword ptr [rax+rax+00h]
0x180010b5b  mov     ebx, eax
0x180010b5d  mov     eax, ebx
0x180010b5f  mov     rcx, [rbp+var_10]
0x180010b63  xor     rcx, rsp; StackCookie
0x180010b66  call    __security_check_cookie
0x180010b6b  add     rsp, 80h
0x180010b72  pop     r15
0x180010b74  pop     r14
0x180010b76  pop     r12
0x180010b78  pop     rdi
0x180010b79  pop     rsi
0x180010b7a  pop     rbx
0x180010b7b  pop     rbp
0x180010b7c  retn
```
