# HrProcessPropertiesXML(IXMLDOMElement *,tagXW_XML_ONERROR_TYPE,IPXWizardPropertyBag * *)

- ea: `0x1800128a8`
- end: `0x180012a5b`
- name: `?HrProcessPropertiesXML@@YAJPEAUIXMLDOMElement@@W4tagXW_XML_ONERROR_TYPE@@PEAPEAUIPXWizardPropertyBag@@@Z`
- size: `435`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x180014c80`

## callees

- `0x18000addc`
- `0x18000ae04`
- `0x18000ae90`
- `0x1800128a8`
- `0x180012a64`
- `0x18001a27c`
- `0x18001a2cc`
- `0x18001a4b4`
- `0x180034010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180012922`
- `msvcrt!_wcsicmp` at `0x180012922`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall HrProcessPropertiesXML(struct IXMLDOMElement *a1, int a2, struct IPXWizardPropertyBag **a3)
{
  int v5; // edi
  int v6; // eax
  unsigned int v7; // esi
  int v8; // eax
  int v9; // ebx
  unsigned int v10; // eax
  PVOID *v11; // rcx
  wchar_t *String2; // [rsp+30h] [rbp-20h] BYREF
  _BYTE v14[24]; // [rsp+38h] [rbp-18h] BYREF
  struct IXMLDOMElement *v15; // [rsp+98h] [rbp+48h] BYREF

  v5 = 0;
  CTagEnum::CTagEnum((CTagEnum *)v14, a1);
  v15 = 0;
  String2 = 0;
  v6 = CTagEnum::HrNext((CTagEnum *)v14, &v15);
  v7 = 1;
  while ( 1 )
  {
    v9 = v6;
    if ( v6 )
      break;
    v8 = ((__int64 (__fastcall *)(struct IXMLDOMElement *, wchar_t **))v15->lpVtbl->get_tagName)(v15, &String2);
    v9 = v8;
    if ( v8 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          81,
          &WPP_92b4ede73d0c3990e751819403b3312f_Traceguids,
          (unsigned int)v8);
    }
    else if ( _wcsicmp(L"property", String2) )
    {
      v9 = -2147418113;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_SD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          80,
          (unsigned int)&WPP_92b4ede73d0c3990e751819403b3312f_Traceguids,
          (_DWORD)String2,
          255);
    }
    else
    {
      v9 = HrProcessPropertyXML(v15, a2, a3);
    }
    ((void (__fastcall *)(struct IXMLDOMElement *))v15->lpVtbl->Release)(v15);
    if ( v9 == 1 )
    {
      v5 = 1;
    }
    else if ( v9 < 0 )
    {
      break;
    }
    v6 = CTagEnum::HrNext((CTagEnum *)v14, &v15);
  }
  v10 = 0;
  if ( v9 != 1 )
    v10 = v9;
  if ( !v5 )
  {
    v7 = v10;
    goto LABEL_23;
  }
  v11 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    goto LABEL_27;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 82, &WPP_92b4ede73d0c3990e751819403b3312f_Traceguids);
LABEL_23:
    v11 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 0x10) != 0 )
    WPP_SF_d(v11[2], 83, &WPP_92b4ede73d0c3990e751819403b3312f_Traceguids, v7);
LABEL_27:
  CTagEnum::~CTagEnum((CTagEnum *)v14);
  return v7;
}

```

## disassembly

```asm
0x1800128a8  mov     [rsp-28h+arg_0], rbx
0x1800128ad  mov     [rsp-28h+arg_8], rsi
0x1800128b2  push    rbp
0x1800128b3  push    rdi
0x1800128b4  push    r12
0x1800128b6  push    r14
0x1800128b8  push    r15
0x1800128ba  mov     rbp, rsp
0x1800128bd  sub     rsp, 50h
0x1800128c1  mov     r14, r8
0x1800128c4  mov     r15d, edx
0x1800128c7  xor     edi, edi
0x1800128c9  mov     rdx, rcx; struct IXMLDOMElement *
0x1800128cc  lea     rcx, [rbp+var_18]; this
0x1800128d0  call    ??0CTagEnum@@QEAA@PEAUIXMLDOMElement@@@Z; CTagEnum::CTagEnum(IXMLDOMElement *)
0x1800128d5  nop
0x1800128d6  mov     [rbp+arg_18], rdi
0x1800128da  mov     [rbp+String2], rdi
0x1800128de  lea     rdx, [rbp+arg_18]; struct IXMLDOMElement **
0x1800128e2  lea     rcx, [rbp+var_18]; this
0x1800128e6  call    ?HrNext@CTagEnum@@QEAAJPEAPEAUIXMLDOMElement@@@Z; CTagEnum::HrNext(IXMLDOMElement * *)
0x1800128eb  lea     r12, WPP_GLOBAL_Control
0x1800128f2  lea     esi, [rdi+1]
0x1800128f5  jmp     loc_1800129CC
0x1800128fa  mov     rcx, [rbp+arg_18]
0x1800128fe  mov     rax, [rcx]
0x180012901  lea     rdx, [rbp+String2]
0x180012905  mov     rax, [rax+158h]
0x18001290c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012911  mov     ebx, eax
0x180012913  test    eax, eax
0x180012915  js      short loc_180012979
0x180012917  mov     rdx, [rbp+String2]; String2
0x18001291b  lea     rcx, aProperty; "property"
0x180012922  call    cs:__imp__wcsicmp
0x180012928  test    eax, eax
0x18001292a  jnz     short loc_18001293F
0x18001292c  mov     r8, r14
0x18001292f  mov     edx, r15d
0x180012932  mov     rcx, [rbp+arg_18]
0x180012936  call    ?HrProcessPropertyXML@@YAJPEAUIXMLDOMElement@@W4tagXW_XML_ONERROR_TYPE@@PEAPEAUIPXWizardPropertyBag@@@Z; HrProcessPropertyXML(IXMLDOMElement *,tagXW_XML_ONERROR_TYPE,IPXWizardPropertyBag * *)
0x18001293b  mov     ebx, eax
0x18001293d  jmp     short loc_1800129A3
0x18001293f  mov     ebx, 8000FFFFh
0x180012944  mov     rcx, cs:WPP_GLOBAL_Control
0x18001294b  cmp     rcx, r12
0x18001294e  jz      short loc_1800129A3
0x180012950  test    byte ptr [rcx+1Ch], 8
0x180012954  jz      short loc_1800129A3
0x180012956  mov     edx, 50h ; 'P'
0x18001295b  mov     [rsp+50h+var_30], 8000FFFFh
0x180012963  mov     r9, [rbp+String2]
0x180012967  lea     r8, WPP_92b4ede73d0c3990e751819403b3312f_Traceguids
0x18001296e  mov     rcx, [rcx+10h]
0x180012972  call    WPP_SF_SD
0x180012977  jmp     short loc_1800129A3
0x180012979  mov     rcx, cs:WPP_GLOBAL_Control
0x180012980  cmp     rcx, r12
0x180012983  jz      short loc_1800129A3
0x180012985  test    byte ptr [rcx+1Ch], 4
0x180012989  jz      short loc_1800129A3
0x18001298b  mov     edx, 51h ; 'Q'
0x180012990  mov     r9d, eax
0x180012993  lea     r8, WPP_92b4ede73d0c3990e751819403b3312f_Traceguids
0x18001299a  mov     rcx, [rcx+10h]
0x18001299e  call    WPP_SF_d
0x1800129a3  mov     rcx, [rbp+arg_18]
0x1800129a7  mov     rax, [rcx]
0x1800129aa  mov     rax, [rax+10h]
0x1800129ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800129b3  cmp     ebx, esi
0x1800129b5  jnz     short loc_1800129BB
0x1800129b7  mov     edi, esi
0x1800129b9  jmp     short loc_1800129BF
0x1800129bb  test    ebx, ebx
0x1800129bd  js      short loc_1800129D6
0x1800129bf  lea     rdx, [rbp+arg_18]; struct IXMLDOMElement **
0x1800129c3  lea     rcx, [rbp+var_18]; this
0x1800129c7  call    ?HrNext@CTagEnum@@QEAAJPEAPEAUIXMLDOMElement@@@Z; CTagEnum::HrNext(IXMLDOMElement * *)
0x1800129cc  test    eax, eax
0x1800129ce  mov     ebx, eax
0x1800129d0  jz      loc_1800128FA
0x1800129d6  xor     eax, eax
0x1800129d8  cmp     ebx, esi
0x1800129da  cmovnz  eax, ebx
0x1800129dd  test    edi, edi
0x1800129df  jz      short loc_180012A0A
0x1800129e1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800129e8  cmp     rcx, r12
0x1800129eb  jz      short loc_180012A37
0x1800129ed  test    byte ptr [rcx+1Ch], 10h
0x1800129f1  jz      short loc_180012A13
0x1800129f3  mov     edx, 52h ; 'R'
0x1800129f8  lea     r8, WPP_92b4ede73d0c3990e751819403b3312f_Traceguids
0x1800129ff  mov     rcx, [rcx+10h]
0x180012a03  call    WPP_SF_
0x180012a08  jmp     short loc_180012A0C
0x180012a0a  mov     esi, eax
0x180012a0c  mov     rcx, cs:WPP_GLOBAL_Control
0x180012a13  cmp     rcx, r12
0x180012a16  jz      short loc_180012A37
0x180012a18  test    byte ptr [rcx+1Ch], 10h
0x180012a1c  jz      short loc_180012A37
0x180012a1e  mov     edx, 53h ; 'S'
0x180012a23  mov     r9d, esi
0x180012a26  lea     r8, WPP_92b4ede73d0c3990e751819403b3312f_Traceguids
0x180012a2d  mov     rcx, [rcx+10h]
0x180012a31  call    WPP_SF_d
0x180012a36  nop
0x180012a37  lea     rcx, [rbp+var_18]; this
0x180012a3b  call    ??1CTagEnum@@QEAA@XZ; CTagEnum::~CTagEnum(void)
0x180012a40  mov     eax, esi
0x180012a42  lea     r11, [rsp+50h+var_s0]
0x180012a47  mov     rbx, [r11+30h]
0x180012a4b  mov     rsi, [r11+38h]
0x180012a4f  mov     rsp, r11
0x180012a52  pop     r15
0x180012a54  pop     r14
0x180012a56  pop     r12
0x180012a58  pop     rdi
0x180012a59  pop     rbp
0x180012a5a  retn
```
