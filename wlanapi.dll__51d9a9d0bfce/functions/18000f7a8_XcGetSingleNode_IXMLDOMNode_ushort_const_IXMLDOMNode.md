# XcGetSingleNode(IXMLDOMNode *,ushort const *,IXMLDOMNode * *)

- ea: `0x18000f7a8`
- end: `0x18000f8eb`
- name: `?XcGetSingleNode@@YAKPEAUIXMLDOMNode@@PEBGPEAPEAU1@@Z`
- size: `323`
- prototype: `unsigned int(struct IXMLDOMNode *, const unsigned __int16 *, struct IXMLDOMNode **)`
- caller_count: `23`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000d660`
- `0x18000dafc`
- `0x18000e9e0`
- `0x18000f66c`
- `0x18000fc48`
- `0x180044470`
- `0x1800455c4`
- `0x1800461b0`
- `0x180046490`
- `0x180046614`
- `0x1800468c8`
- `0x180046a18`
- `0x180046c64`
- `0x180047bb4`
- `0x180047db4`
- `0x1800481f0`
- `0x180048310`
- `0x180048e00`
- `0x1800490d4`
- `0x180049530`
- `0x18004f200`
- `0x18004f954`
- `0x18004fc68`

## callees

- `0x180009654`
- `0x18000f7a8`
- `0x180062010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18000f7dd`
- `OLEAUT32!__imp_SysAllocString` at `0x18000f7dd`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f7d4`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f7f1`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f882`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f7d4`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f7f1`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f882`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall XcGetSingleNode(struct IXMLDOMNode *a1, const unsigned __int16 *a2, struct IXMLDOMNode **a3)
{
  __int64 v6; // rbx
  int v7; // r14d
  OLECHAR *v8; // rdi
  int v9; // eax
  unsigned int v10; // esi
  int v11; // eax
  int v12; // eax
  __int64 v14; // [rsp+20h] [rbp-18h] BYREF
  __int64 v15; // [rsp+28h] [rbp-10h] BYREF
  int v16; // [rsp+88h] [rbp+50h] BYREF

  v6 = 0;
  v15 = 0;
  v7 = 0;
  v14 = 0;
  v16 = 0;
  SysFreeString(0);
  v8 = SysAllocString(a2);
  if ( v8 )
  {
    SysFreeString(0);
    v9 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, OLECHAR *, __int64 *))a1->lpVtbl->selectNodes)(a1, v8, &v14);
    v10 = v9;
    if ( v9 >= 0 )
      goto LABEL_6;
    if ( (v9 & 0x1FFF0000) == 0x70000 )
      v10 = (unsigned __int16)v9;
    if ( !v10 )
    {
LABEL_6:
      v11 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v14 + 64LL))(v14, &v16);
      v10 = v11;
      if ( v11 >= 0 )
      {
        v10 = 0;
LABEL_11:
        v6 = v14;
        v14 = 0;
        v15 = v6;
        v7 = v16;
        goto LABEL_13;
      }
      if ( (v11 & 0x1FFF0000) == 0x70000 )
        v10 = (unsigned __int16)v11;
      if ( !v10 )
        goto LABEL_11;
    }
  }
  else
  {
    v8 = 0;
    v10 = 14;
  }
LABEL_13:
  ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v14);
  SysFreeString(v8);
  if ( !v10 )
  {
    if ( v7 > 0 )
    {
      if ( v7 <= 1 )
      {
        v12 = (*(__int64 (__fastcall **)(__int64, _QWORD, struct IXMLDOMNode **))(*(_QWORD *)v6 + 56LL))(v6, 0, a3);
        v10 = v12;
        if ( v12 < 0 )
        {
          if ( (v12 & 0x1FFF0000) == 0x70000 )
            v10 = (unsigned __int16)v12;
        }
        else
        {
          v10 = 0;
        }
      }
      else
      {
        v10 = 1206;
      }
    }
    else
    {
      v10 = 1168;
    }
  }
  ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v15);
  return v10;
}

```

## disassembly

```asm
0x18000f7a8  push    rbp
0x18000f7aa  push    rbx
0x18000f7ab  push    rsi
0x18000f7ac  push    rdi
0x18000f7ad  push    r14
0x18000f7af  push    r15
0x18000f7b1  mov     rbp, rsp
0x18000f7b4  sub     rsp, 38h
0x18000f7b8  mov     r15, r8
0x18000f7bb  mov     rdi, rdx
0x18000f7be  mov     rsi, rcx
0x18000f7c1  xor     ebx, ebx
0x18000f7c3  mov     [rbp+var_10], rbx
0x18000f7c7  xor     r14d, r14d
0x18000f7ca  mov     [rbp+var_18], r14
0x18000f7ce  mov     [rbp+arg_18], r14d
0x18000f7d2  xor     ecx, ecx; bstrString
0x18000f7d4  call    cs:__imp_SysFreeString
0x18000f7da  mov     rcx, rdi; psz
0x18000f7dd  call    cs:__imp_SysAllocString
0x18000f7e3  mov     rdi, rax
0x18000f7e6  test    rax, rax
0x18000f7e9  jz      loc_18000F870
0x18000f7ef  xor     ecx, ecx; bstrString
0x18000f7f1  call    cs:__imp_SysFreeString
0x18000f7f7  mov     rax, [rsi]
0x18000f7fa  lea     r8, [rbp+var_18]
0x18000f7fe  mov     rdx, rdi
0x18000f801  mov     rcx, rsi
0x18000f804  mov     rax, [rax+120h]
0x18000f80b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f810  mov     esi, eax
0x18000f812  test    eax, eax
0x18000f814  jns     short loc_18000F829
0x18000f816  and     eax, 1FFF0000h
0x18000f81b  cmp     eax, 70000h
0x18000f820  jnz     short loc_18000F825
0x18000f822  movzx   esi, si
0x18000f825  test    esi, esi
0x18000f827  jnz     short loc_18000F875
0x18000f829  mov     rcx, [rbp+var_18]
0x18000f82d  mov     rax, [rcx]
0x18000f830  lea     rdx, [rbp+arg_18]
0x18000f834  mov     rax, [rax+40h]
0x18000f838  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f83d  mov     esi, eax
0x18000f83f  test    eax, eax
0x18000f841  js      short loc_18000F847
0x18000f843  xor     esi, esi
0x18000f845  jmp     short loc_18000F85A
0x18000f847  and     eax, 1FFF0000h
0x18000f84c  cmp     eax, 70000h
0x18000f851  jnz     short loc_18000F856
0x18000f853  movzx   esi, si
0x18000f856  test    esi, esi
0x18000f858  jnz     short loc_18000F875
0x18000f85a  mov     rbx, [rbp+var_18]
0x18000f85e  mov     [rbp+var_18], 0
0x18000f866  mov     [rbp+var_10], rbx
0x18000f86a  mov     r14d, [rbp+arg_18]
0x18000f86e  jmp     short loc_18000F875
0x18000f870  xor     edi, edi
0x18000f872  lea     esi, [rdi+0Eh]
0x18000f875  lea     rcx, [rbp+var_18]
0x18000f879  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x18000f87e  nop
0x18000f87f  mov     rcx, rdi; bstrString
0x18000f882  call    cs:__imp_SysFreeString
0x18000f888  test    esi, esi
0x18000f88a  jnz     short loc_18000F8D2
0x18000f88c  test    r14d, r14d
0x18000f88f  jg      short loc_18000F898
0x18000f891  mov     esi, 490h
0x18000f896  jmp     short loc_18000F8D2
0x18000f898  cmp     r14d, 1
0x18000f89c  jle     short loc_18000F8A5
0x18000f89e  mov     esi, 4B6h
0x18000f8a3  jmp     short loc_18000F8D2
0x18000f8a5  mov     rax, [rbx]
0x18000f8a8  mov     r8, r15
0x18000f8ab  xor     edx, edx
0x18000f8ad  mov     rcx, rbx
0x18000f8b0  mov     rax, [rax+38h]
0x18000f8b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f8b9  mov     esi, eax
0x18000f8bb  test    eax, eax
0x18000f8bd  js      short loc_18000F8C3
0x18000f8bf  xor     esi, esi
0x18000f8c1  jmp     short loc_18000F8D2
0x18000f8c3  and     eax, 1FFF0000h
0x18000f8c8  cmp     eax, 70000h
0x18000f8cd  jnz     short loc_18000F8D2
0x18000f8cf  movzx   esi, si
0x18000f8d2  lea     rcx, [rbp+var_10]
0x18000f8d6  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x18000f8db  nop
0x18000f8dc  mov     eax, esi
0x18000f8de  add     rsp, 38h
0x18000f8e2  pop     r15
0x18000f8e4  pop     r14
0x18000f8e6  pop     rdi
0x18000f8e7  pop     rsi
0x18000f8e8  pop     rbx
0x18000f8e9  pop     rbp
0x18000f8ea  retn
```
