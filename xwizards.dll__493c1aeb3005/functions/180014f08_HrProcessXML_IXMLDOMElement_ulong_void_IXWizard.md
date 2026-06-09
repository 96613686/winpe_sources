# HrProcessXML(IXMLDOMElement *,ulong,void *,IXWizard *)

- ea: `0x180014f08`
- end: `0x180015165`
- name: `?HrProcessXML@@YAJPEAUIXMLDOMElement@@KPEAXPEAUIXWizard@@@Z`
- size: `605`
- prototype: `__int64 __fastcall(struct IXMLDOMElement *, unsigned int, void *, struct IXWizard *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x180016dd4`

## callees

- `0x18000ae04`
- `0x180014248`
- `0x180014c80`
- `0x180014f08`
- `0x18001a27c`
- `0x18001a2cc`
- `0x18001a308`
- `0x18001a4b4`
- `0x180034010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180014f8c`
- `msvcrt!_wcsicmp` at `0x180015048`
- `msvcrt!_wcsicmp` at `0x180015071`
- `msvcrt!_wcsicmp` at `0x180014f8c`
- `msvcrt!_wcsicmp` at `0x180015048`
- `msvcrt!_wcsicmp` at `0x180015071`
- `OLEAUT32!__imp_SysFreeString` at `0x180014fcb`
- `OLEAUT32!__imp_SysFreeString` at `0x180014fdf`
- `OLEAUT32!__imp_SysFreeString` at `0x18001508d`
- `OLEAUT32!__imp_SysFreeString` at `0x180014fcb`
- `OLEAUT32!__imp_SysFreeString` at `0x180014fdf`
- `OLEAUT32!__imp_SysFreeString` at `0x18001508d`

## string_xrefs

- `0x180015041`: `registry`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall HrProcessXML(struct IXMLDOMElement *a1, int a2, void *a3, struct IXWizard *a4)
{
  int NamedAttributeValue; // eax
  unsigned int v9; // ebx
  int v11; // eax
  unsigned int v12; // eax
  __int64 v13; // rdx
  bool v14; // zf
  PVOID *v15; // rcx
  struct IXMLDOMElement *v16; // [rsp+20h] [rbp-38h] BYREF
  wchar_t *String2; // [rsp+28h] [rbp-30h] BYREF
  BSTR bstrString; // [rsp+30h] [rbp-28h] BYREF
  _BYTE v19[32]; // [rsp+38h] [rbp-20h] BYREF

  String2 = 0;
  NamedAttributeValue = HrGetNamedAttributeValue(a1, L"version", &String2);
  v9 = NamedAttributeValue;
  if ( NamedAttributeValue < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        99,
        &WPP_92b4ede73d0c3990e751819403b3312f_Traceguids,
        (unsigned int)NamedAttributeValue);
    return v9;
  }
  if ( !_wcsicmp(L"1.0", String2) )
  {
    SysFreeString(String2);
    CTagEnum::CTagEnum((CTagEnum *)v19, a1);
    v16 = 0;
    bstrString = 0;
    v9 = CTagEnum::HrNext((CTagEnum *)v19, &v16);
    if ( !v9 )
    {
      while ( 1 )
      {
        v11 = ((__int64 (__fastcall *)(struct IXMLDOMElement *, BSTR *))v16->lpVtbl->get_tagName)(v16, &bstrString);
        v9 = v11;
        if ( v11 < 0 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              101,
              &WPP_92b4ede73d0c3990e751819403b3312f_Traceguids,
              (unsigned int)v11);
          goto LABEL_21;
        }
        if ( !_wcsicmp(L"registry", bstrString) )
          break;
        if ( !_wcsicmp(L"run", bstrString) )
        {
          v12 = HrProcessRunXML(v16, v13, a4);
          goto LABEL_16;
        }
LABEL_17:
        SysFreeString(bstrString);
LABEL_21:
        ((void (__fastcall *)(struct IXMLDOMElement *))v16->lpVtbl->Release)(v16);
        v14 = v9 == 0;
        if ( (v9 & 0x80000000) == 0 )
        {
          v9 = CTagEnum::HrNext((CTagEnum *)v19, &v16);
          v14 = v9 == 0;
        }
        if ( !v14 )
          goto LABEL_24;
      }
      v12 = HrProcessRegistryXML(v16, a2, a3, a4);
LABEL_16:
      v9 = v12;
      goto LABEL_17;
    }
LABEL_24:
    if ( v9 == 1 )
    {
      v9 = 0;
    }
    else if ( (v9 & 0x80000000) != 0 )
    {
      v15 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      {
LABEL_34:
        CTagEnum::~CTagEnum((CTagEnum *)v19);
        return v9;
      }
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      {
LABEL_31:
        if ( v15 != &WPP_GLOBAL_Control && (*((_BYTE *)v15 + 28) & 0x10) != 0 )
          WPP_SF_d(v15[2], 103, &WPP_92b4ede73d0c3990e751819403b3312f_Traceguids, v9);
        goto LABEL_34;
      }
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 102, &WPP_92b4ede73d0c3990e751819403b3312f_Traceguids, v9);
    }
    v15 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_31;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 100, &WPP_92b4ede73d0c3990e751819403b3312f_Traceguids, v9);
  SysFreeString(String2);
  return 2147942487LL;
}

```

## disassembly

```asm
0x180014f08  push    rbp
0x180014f0a  push    rbx
0x180014f0b  push    rdi
0x180014f0c  push    r12
0x180014f0e  push    r14
0x180014f10  push    r15
0x180014f12  mov     rbp, rsp
0x180014f15  sub     rsp, 58h
0x180014f19  mov     r14, r9
0x180014f1c  mov     r15, r8
0x180014f1f  mov     r12d, edx
0x180014f22  mov     rdi, rcx
0x180014f25  mov     [rbp+String2], 0
0x180014f2d  lea     r8, [rbp+String2]; unsigned __int16 **
0x180014f31  lea     rdx, aVersion; "version"
0x180014f38  call    ?HrGetNamedAttributeValue@@YAJPEAUIXMLDOMElement@@PEAGPEAPEAG@Z; HrGetNamedAttributeValue(IXMLDOMElement *,ushort *,ushort * *)
0x180014f3d  mov     ebx, eax
0x180014f3f  test    eax, eax
0x180014f41  jns     short loc_180014F81
0x180014f43  lea     rdi, WPP_GLOBAL_Control
0x180014f4a  mov     rcx, cs:WPP_GLOBAL_Control
0x180014f51  cmp     rcx, rdi
0x180014f54  jz      loc_180015155
0x180014f5a  test    byte ptr [rcx+1Ch], 4
0x180014f5e  jz      loc_180015155
0x180014f64  mov     edx, 63h ; 'c'
0x180014f69  mov     r9d, eax
0x180014f6c  lea     r8, WPP_92b4ede73d0c3990e751819403b3312f_Traceguids
0x180014f73  mov     rcx, [rcx+10h]
0x180014f77  call    WPP_SF_d
0x180014f7c  jmp     loc_180015155
0x180014f81  mov     rdx, [rbp+String2]; String2
0x180014f85  lea     rcx, a10; "1.0"
0x180014f8c  call    cs:__imp__wcsicmp
0x180014f92  test    eax, eax
0x180014f94  jz      short loc_180014FDB
0x180014f96  lea     rdi, WPP_GLOBAL_Control
0x180014f9d  mov     rcx, cs:WPP_GLOBAL_Control
0x180014fa4  cmp     rcx, rdi
0x180014fa7  jz      short loc_180014FC7
0x180014fa9  test    byte ptr [rcx+1Ch], 8
0x180014fad  jz      short loc_180014FC7
0x180014faf  mov     edx, 64h ; 'd'
0x180014fb4  mov     r9d, ebx
0x180014fb7  lea     r8, WPP_92b4ede73d0c3990e751819403b3312f_Traceguids
0x180014fbe  mov     rcx, [rcx+10h]
0x180014fc2  call    WPP_SF_d
0x180014fc7  mov     rcx, [rbp+String2]; bstrString
0x180014fcb  call    cs:__imp_SysFreeString
0x180014fd1  mov     eax, 80070057h
0x180014fd6  jmp     loc_180015157
0x180014fdb  mov     rcx, [rbp+String2]; bstrString
0x180014fdf  call    cs:__imp_SysFreeString
0x180014fe5  mov     rdx, rdi; struct IXMLDOMElement *
0x180014fe8  lea     rcx, [rbp+var_20]; this
0x180014fec  call    ??0CTagEnum@@QEAA@PEAUIXMLDOMElement@@@Z; CTagEnum::CTagEnum(IXMLDOMElement *)
0x180014ff1  nop
0x180014ff2  mov     [rbp+var_38], 0
0x180014ffa  mov     [rbp+bstrString], 0
0x180015002  lea     rdx, [rbp+var_38]; struct IXMLDOMElement **
0x180015006  lea     rcx, [rbp+var_20]; this
0x18001500a  call    ?HrNext@CTagEnum@@QEAAJPEAPEAUIXMLDOMElement@@@Z; CTagEnum::HrNext(IXMLDOMElement * *)
0x18001500f  mov     ebx, eax
0x180015011  lea     rdi, WPP_GLOBAL_Control
0x180015018  test    eax, eax
0x18001501a  jnz     loc_1800150EA
0x180015020  mov     rcx, [rbp+var_38]
0x180015024  mov     rax, [rcx]
0x180015027  lea     rdx, [rbp+bstrString]
0x18001502b  mov     rax, [rax+158h]
0x180015032  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015037  mov     ebx, eax
0x180015039  test    eax, eax
0x18001503b  js      short loc_180015095
0x18001503d  mov     rdx, [rbp+bstrString]; String2
0x180015041  lea     rcx, aRegistry; "registry"
0x180015048  call    cs:__imp__wcsicmp
0x18001504e  test    eax, eax
0x180015050  jnz     short loc_180015066
0x180015052  mov     r9, r14; struct IXWizard *
0x180015055  mov     r8, r15; void *
0x180015058  mov     edx, r12d; unsigned int
0x18001505b  mov     rcx, [rbp+var_38]; struct IXMLDOMElement *
0x18001505f  call    ?HrProcessRegistryXML@@YAJPEAUIXMLDOMElement@@KPEAXPEAUIXWizard@@@Z; HrProcessRegistryXML(IXMLDOMElement *,ulong,void *,IXWizard *)
0x180015064  jmp     short loc_180015087
0x180015066  mov     rdx, [rbp+bstrString]; String2
0x18001506a  lea     rcx, aRun; "run"
0x180015071  call    cs:__imp__wcsicmp
0x180015077  test    eax, eax
0x180015079  jnz     short loc_180015089
0x18001507b  mov     r8, r14; struct IXWizard *
0x18001507e  mov     rcx, [rbp+var_38]; struct IXMLDOMElement *
0x180015082  call    ?HrProcessRunXML@@YAJPEAUIXMLDOMElement@@KPEAUIXWizard@@@Z; HrProcessRunXML(IXMLDOMElement *,ulong,IXWizard *)
0x180015087  mov     ebx, eax
0x180015089  mov     rcx, [rbp+bstrString]; bstrString
0x18001508d  call    cs:__imp_SysFreeString
0x180015093  jmp     short loc_1800150BF
0x180015095  mov     rcx, cs:WPP_GLOBAL_Control
0x18001509c  cmp     rcx, rdi
0x18001509f  jz      short loc_1800150BF
0x1800150a1  test    byte ptr [rcx+1Ch], 4
0x1800150a5  jz      short loc_1800150BF
0x1800150a7  mov     edx, 65h ; 'e'
0x1800150ac  mov     r9d, eax
0x1800150af  lea     r8, WPP_92b4ede73d0c3990e751819403b3312f_Traceguids
0x1800150b6  mov     rcx, [rcx+10h]
0x1800150ba  call    WPP_SF_d
0x1800150bf  mov     rcx, [rbp+var_38]
0x1800150c3  mov     rax, [rcx]
0x1800150c6  mov     rax, [rax+10h]
0x1800150ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800150cf  test    ebx, ebx
0x1800150d1  js      short loc_1800150E4
0x1800150d3  lea     rdx, [rbp+var_38]; struct IXMLDOMElement **
0x1800150d7  lea     rcx, [rbp+var_20]; this
0x1800150db  call    ?HrNext@CTagEnum@@QEAAJPEAPEAUIXMLDOMElement@@@Z; CTagEnum::HrNext(IXMLDOMElement * *)
0x1800150e0  mov     ebx, eax
0x1800150e2  test    eax, eax
0x1800150e4  jz      loc_180015020
0x1800150ea  cmp     ebx, 1
0x1800150ed  jnz     short loc_1800150F3
0x1800150ef  xor     ebx, ebx
0x1800150f1  jmp     short loc_180015121
0x1800150f3  test    ebx, ebx
0x1800150f5  jns     short loc_180015121
0x1800150f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800150fe  cmp     rcx, rdi
0x180015101  jz      short loc_18001514C
0x180015103  test    byte ptr [rcx+1Ch], 4
0x180015107  jz      short loc_180015128
0x180015109  mov     edx, 66h ; 'f'
0x18001510e  mov     r9d, ebx
0x180015111  lea     r8, WPP_92b4ede73d0c3990e751819403b3312f_Traceguids
0x180015118  mov     rcx, [rcx+10h]
0x18001511c  call    WPP_SF_d
0x180015121  mov     rcx, cs:WPP_GLOBAL_Control
0x180015128  cmp     rcx, rdi
0x18001512b  jz      short loc_18001514C
0x18001512d  test    byte ptr [rcx+1Ch], 10h
0x180015131  jz      short loc_18001514C
0x180015133  mov     edx, 67h ; 'g'
0x180015138  mov     r9d, ebx
0x18001513b  lea     r8, WPP_92b4ede73d0c3990e751819403b3312f_Traceguids
0x180015142  mov     rcx, [rcx+10h]
0x180015146  call    WPP_SF_d
0x18001514b  nop
0x18001514c  lea     rcx, [rbp+var_20]; this
0x180015150  call    ??1CTagEnum@@QEAA@XZ; CTagEnum::~CTagEnum(void)
0x180015155  mov     eax, ebx
0x180015157  add     rsp, 58h
0x18001515b  pop     r15
0x18001515d  pop     r14
0x18001515f  pop     r12
0x180015161  pop     rdi
0x180015162  pop     rbx
0x180015163  pop     rbp
0x180015164  retn
```
