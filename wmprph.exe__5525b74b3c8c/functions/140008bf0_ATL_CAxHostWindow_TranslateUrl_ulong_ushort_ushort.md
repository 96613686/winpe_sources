# ATL::CAxHostWindow::TranslateUrl(ulong,ushort *,ushort * *)

- ea: `0x140008bf0`
- end: `0x140008ce4`
- name: `?TranslateUrl@CAxHostWindow@ATL@@UEAAJKPEAGPEAPEAG@Z`
- size: `244`
- prototype: `int(ATL::CAxHostWindow *__hidden this, unsigned int, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x140008bf0`
- `0x14000e3e0`
- `0x14000f010`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x140008c8d`
- `ole32!CoTaskMemAlloc` at `0x140008c8d`
- `OLEAUT32!__imp_SysAllocString` at `0x140008c45`
- `OLEAUT32!__imp_SysAllocString` at `0x140008c45`
- `OLEAUT32!__imp_SysFreeString` at `0x140008c68`
- `OLEAUT32!__imp_SysFreeString` at `0x140008ca0`
- `OLEAUT32!__imp_SysFreeString` at `0x140008cc9`
- `OLEAUT32!__imp_SysFreeString` at `0x140008c68`
- `OLEAUT32!__imp_SysFreeString` at `0x140008ca0`
- `OLEAUT32!__imp_SysFreeString` at `0x140008cc9`
- `OLEAUT32!__imp_SysStringLen` at `0x140008c7c`
- `OLEAUT32!__imp_SysStringLen` at `0x140008c7c`

## pseudocode

```c
__int64 __fastcall ATL::CAxHostWindow::TranslateUrl(
        ATL::CAxHostWindow *this,
        unsigned int a2,
        unsigned __int16 *a3,
        unsigned __int16 **a4)
{
  int v7; // edi
  __int64 v8; // r14
  __int64 (__fastcall *v9)(__int64, _QWORD, OLECHAR *, BSTR *); // rdi
  OLECHAR *v10; // rbx
  OLECHAR *v11; // rcx
  SIZE_T v12; // rbx
  unsigned __int16 *v13; // rax
  BSTR pbstr; // [rsp+68h] [rbp+20h] BYREF

  if ( !a4 )
    return 2147500035LL;
  *a4 = 0;
  v7 = 1;
  v8 = *((_QWORD *)this + 10);
  if ( v8 )
  {
    pbstr = 0;
    v9 = *(__int64 (__fastcall **)(__int64, _QWORD, OLECHAR *, BSTR *))(*(_QWORD *)v8 + 160LL);
    v10 = SysAllocString(a3);
    v7 = v9(v8, a2, v10, &pbstr);
    SysFreeString(v10);
    v11 = pbstr;
    if ( v7 >= 0 && pbstr )
    {
      v12 = 2 * SysStringLen(pbstr) + 2;
      v13 = (unsigned __int16 *)CoTaskMemAlloc(v12);
      *a4 = v13;
      if ( !v13 )
      {
        SysFreeString(pbstr);
        return 2147942414LL;
      }
      memcpy_0(v13, pbstr, v12);
      v11 = pbstr;
    }
    else
    {
      v7 = 1;
    }
    SysFreeString(v11);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x140008bf0  mov     [rsp+arg_0], rbx
0x140008bf5  mov     [rsp+arg_8], rbp
0x140008bfa  push    rsi
0x140008bfb  push    rdi
0x140008bfc  push    r14
0x140008bfe  sub     rsp, 30h
0x140008c02  mov     rsi, r9
0x140008c05  mov     ebp, edx
0x140008c07  test    r9, r9
0x140008c0a  jnz     short loc_140008C16
0x140008c0c  mov     eax, 80004003h
0x140008c11  jmp     loc_140008CD1
0x140008c16  mov     qword ptr [r9], 0
0x140008c1d  mov     edi, 1
0x140008c22  mov     r14, [rcx+50h]
0x140008c26  test    r14, r14
0x140008c29  jz      loc_140008CCF
0x140008c2f  mov     [rsp+48h+pbstr], 0
0x140008c38  mov     rcx, r8; psz
0x140008c3b  mov     rax, [r14]
0x140008c3e  mov     rdi, [rax+0A0h]
0x140008c45  call    cs:__imp_SysAllocString
0x140008c4b  lea     r9, [rsp+48h+pbstr]
0x140008c50  mov     edx, ebp
0x140008c52  mov     rbx, rax
0x140008c55  mov     r8, rax
0x140008c58  mov     rax, rdi
0x140008c5b  mov     rcx, r14
0x140008c5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008c63  mov     rcx, rbx; bstrString
0x140008c66  mov     edi, eax
0x140008c68  call    cs:__imp_SysFreeString
0x140008c6e  mov     rcx, [rsp+48h+pbstr]; bstrString
0x140008c73  test    edi, edi
0x140008c75  js      short loc_140008CC4
0x140008c77  test    rcx, rcx
0x140008c7a  jz      short loc_140008CC4
0x140008c7c  call    cs:__imp_SysStringLen
0x140008c82  lea     eax, ds:2[rax*2]
0x140008c89  mov     ecx, eax; cb
0x140008c8b  mov     ebx, eax
0x140008c8d  call    cs:__imp_CoTaskMemAlloc
0x140008c93  mov     [rsi], rax
0x140008c96  test    rax, rax
0x140008c99  jnz     short loc_140008CAD
0x140008c9b  mov     rcx, [rsp+48h+pbstr]; bstrString
0x140008ca0  call    cs:__imp_SysFreeString
0x140008ca6  mov     eax, 8007000Eh
0x140008cab  jmp     short loc_140008CD1
0x140008cad  mov     rdx, [rsp+48h+pbstr]; Src
0x140008cb2  mov     r8, rbx; Size
0x140008cb5  mov     rcx, rax; void *
0x140008cb8  call    memcpy_0
0x140008cbd  mov     rcx, [rsp+48h+pbstr]
0x140008cc2  jmp     short loc_140008CC9
0x140008cc4  mov     edi, 1
0x140008cc9  call    cs:__imp_SysFreeString
0x140008ccf  mov     eax, edi
0x140008cd1  mov     rbx, [rsp+48h+arg_0]
0x140008cd6  mov     rbp, [rsp+48h+arg_8]
0x140008cdb  add     rsp, 30h
0x140008cdf  pop     r14
0x140008ce1  pop     rdi
0x140008ce2  pop     rsi
0x140008ce3  retn
```
