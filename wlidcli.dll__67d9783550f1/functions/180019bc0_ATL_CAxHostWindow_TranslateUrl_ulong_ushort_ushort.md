# ATL::CAxHostWindow::TranslateUrl(ulong,ushort *,ushort * *)

- ea: `0x180019bc0`
- end: `0x180019ccc`
- name: `?TranslateUrl@CAxHostWindow@ATL@@UEAAJKPEAGPEAPEAG@Z`
- size: `268`
- prototype: `int(ATL::CAxHostWindow *__hidden this, unsigned int, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000a1a8`
- `0x18000ac9c`
- `0x180013384`
- `0x180019bc0`
- `0x180063010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180019c37`
- `OLEAUT32!__imp_SysFreeString` at `0x180019c82`
- `OLEAUT32!__imp_SysFreeString` at `0x180019cbb`
- `OLEAUT32!__imp_SysFreeString` at `0x180019c37`
- `OLEAUT32!__imp_SysFreeString` at `0x180019c82`
- `OLEAUT32!__imp_SysFreeString` at `0x180019cbb`
- `OLEAUT32!__imp_SysStringLen` at `0x180019c49`
- `OLEAUT32!__imp_SysStringLen` at `0x180019c5b`
- `OLEAUT32!__imp_SysStringLen` at `0x180019c49`
- `OLEAUT32!__imp_SysStringLen` at `0x180019c5b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180019c6c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180019c6c`

## pseudocode

```c
__int64 __fastcall ATL::CAxHostWindow::TranslateUrl(
        ATL::CAxHostWindow *this,
        unsigned int a2,
        unsigned __int16 *a3,
        unsigned __int16 **a4)
{
  __int64 v7; // rsi
  int v8; // ebx
  __int64 (__fastcall *v9)(__int64, _QWORD, _QWORD, BSTR *); // rbx
  ATL::CComBSTR *v10; // rax
  SIZE_T v11; // rsi
  unsigned __int16 *v12; // rax
  errno_t v13; // eax
  BSTR bstrString[7]; // [rsp+30h] [rbp-38h] BYREF
  BSTR pbstr; // [rsp+88h] [rbp+20h] BYREF

  if ( !a4 )
    return 2147500035LL;
  *a4 = 0;
  v7 = *((_QWORD *)this + 13);
  if ( v7 )
  {
    pbstr = 0;
    v9 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, BSTR *))(*(_QWORD *)v7 + 160LL);
    v10 = ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)bstrString, a3);
    v8 = v9(v7, a2, *(_QWORD *)v10, &pbstr);
    SysFreeString(bstrString[0]);
    if ( v8 >= 0 && SysStringLen(pbstr) )
    {
      v11 = 2 * SysStringLen(pbstr) + 2;
      v12 = (unsigned __int16 *)CoTaskMemAlloc(v11);
      *a4 = v12;
      if ( !v12 )
      {
        SysFreeString(pbstr);
        return 2147942414LL;
      }
      v13 = memcpy_s_0(v12, v11, pbstr, v11);
      ATL::AtlCrtErrorCheck(v13);
    }
    else
    {
      v8 = 1;
    }
    SysFreeString(pbstr);
  }
  else
  {
    return 1;
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180019bc0  push    rbx
0x180019bc2  push    rbp
0x180019bc3  push    rsi
0x180019bc4  push    rdi
0x180019bc5  sub     rsp, 48h
0x180019bc9  mov     rdi, r9
0x180019bcc  mov     ebp, edx
0x180019bce  test    r9, r9
0x180019bd1  jnz     short loc_180019BDD
0x180019bd3  mov     eax, 80004003h
0x180019bd8  jmp     loc_180019CC3
0x180019bdd  mov     qword ptr [r9], 0
0x180019be4  mov     rsi, [rcx+68h]
0x180019be8  test    rsi, rsi
0x180019beb  jnz     short loc_180019BF5
0x180019bed  lea     ebx, [rsi+1]
0x180019bf0  jmp     loc_180019CC1
0x180019bf5  mov     [rsp+68h+pbstr], 0
0x180019c01  lea     rcx, [rsp+68h+bstrString]; this
0x180019c06  mov     rax, [rsi]
0x180019c09  mov     rdx, r8; unsigned __int16 *
0x180019c0c  mov     rbx, [rax+0A0h]
0x180019c13  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x180019c18  lea     r9, [rsp+68h+pbstr]
0x180019c20  mov     edx, ebp
0x180019c22  mov     rcx, rsi
0x180019c25  mov     r8, [rax]
0x180019c28  mov     rax, rbx
0x180019c2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019c30  mov     rcx, [rsp+68h+bstrString]; bstrString
0x180019c35  mov     ebx, eax
0x180019c37  call    cs:__imp_SysFreeString
0x180019c3d  test    ebx, ebx
0x180019c3f  js      short loc_180019CAE
0x180019c41  mov     rcx, [rsp+68h+pbstr]; pbstr
0x180019c49  call    cs:__imp_SysStringLen
0x180019c4f  test    eax, eax
0x180019c51  jz      short loc_180019CAE
0x180019c53  mov     rcx, [rsp+68h+pbstr]; pbstr
0x180019c5b  call    cs:__imp_SysStringLen
0x180019c61  lea     eax, ds:2[rax*2]
0x180019c68  mov     ecx, eax; cb
0x180019c6a  mov     esi, eax
0x180019c6c  call    cs:__imp_CoTaskMemAlloc
0x180019c72  mov     [rdi], rax
0x180019c75  test    rax, rax
0x180019c78  jnz     short loc_180019C8F
0x180019c7a  mov     rcx, [rsp+68h+pbstr]; bstrString
0x180019c82  call    cs:__imp_SysFreeString
0x180019c88  mov     eax, 8007000Eh
0x180019c8d  jmp     short loc_180019CC3
0x180019c8f  mov     r8, [rsp+68h+pbstr]; Source
0x180019c97  mov     r9, rsi; SourceSize
0x180019c9a  mov     rdx, rsi; DestinationSize
0x180019c9d  mov     rcx, rax; Destination
0x180019ca0  call    memcpy_s_0
0x180019ca5  mov     ecx, eax; int
0x180019ca7  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180019cac  jmp     short loc_180019CB3
0x180019cae  mov     ebx, 1
0x180019cb3  mov     rcx, [rsp+68h+pbstr]; bstrString
0x180019cbb  call    cs:__imp_SysFreeString
0x180019cc1  mov     eax, ebx
0x180019cc3  add     rsp, 48h
0x180019cc7  pop     rdi
0x180019cc8  pop     rsi
0x180019cc9  pop     rbp
0x180019cca  pop     rbx
0x180019ccb  retn
```
