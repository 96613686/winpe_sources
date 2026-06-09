# MsxmlDomElementList::Next(void)

- ea: `0x1400115c0`
- end: `0x1400117cf`
- name: `?Next@MsxmlDomElementList@@UEAA?AV?$AutoRef@VAbstractDomElement@@@wmi@@XZ`
- size: `527`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140002bd0`
- `0x140011570`
- `0x1400115c0`
- `0x1400117d8`
- `0x1400128e8`
- `0x140021b00`
- `0x140022cec`
- `0x140031810`
- `0x140034010`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 *__fastcall MsxmlDomElementList::Next(__int64 a1, __int64 *a2)
{
  int v4; // eax
  int v5; // edi
  int v6; // edi
  __int64 *v7; // rcx
  __int64 v8; // rax
  __int64 v9; // rax
  __int64 *v11; // [rsp+20h] [rbp-60h] BYREF
  __int64 v12; // [rsp+28h] [rbp-58h] BYREF
  __int16 *pExceptionObject; // [rsp+30h] [rbp-50h] BYREF
  __int64 v14; // [rsp+38h] [rbp-48h]
  __int64 v15; // [rsp+40h] [rbp-40h]
  int v16; // [rsp+48h] [rbp-38h]
  __int64 v17; // [rsp+4Ch] [rbp-34h]
  char v18; // [rsp+54h] [rbp-2Ch]
  _BYTE v19[4]; // [rsp+5Ch] [rbp-24h] BYREF
  GUID v20; // [rsp+60h] [rbp-20h] BYREF

  v11 = a2;
  v12 = 0;
  while ( 1 )
  {
    v11 = 0;
    v4 = (*(__int64 (__fastcall **)(_QWORD, __int64 **))(**(_QWORD **)(a1 + 16) + 72LL))(*(_QWORD *)(a1 + 16), &v11);
    v5 = v4;
    if ( v4 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          19,
          WPP_fda289614a233b29151e0c0c410d9667_Traceguids,
          (unsigned int)v4);
      }
      pExceptionObject = word_14003838A;
      v14 = 0;
      v15 = 0;
      v16 = v5;
      v17 = -1;
      v18 = 0;
      throw (EvtException *)&pExceptionObject;
    }
    if ( v4 )
      break;
    if ( v12 )
      winrt::com_ptr<IXMLDOMParseError>::unconditional_release_ref(&v12);
    v20 = IID_IXMLDOMElement;
    v6 = *(_DWORD *)winrt::com_ptr<IXMLDOMNode>::as(&v11, v19, &v20, &v12);
    if ( v11 )
      winrt::com_ptr<IXMLDOMParseError>::unconditional_release_ref((__int64 *)&v11);
    if ( v6 != -2147467262 )
    {
      if ( v6 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            20,
            WPP_fda289614a233b29151e0c0c410d9667_Traceguids,
            (unsigned int)v6);
        }
        pExceptionObject = word_14003838A;
        v14 = 0;
        v15 = 0;
        v16 = v6;
        v17 = -1;
        v18 = 0;
        throw (EvtException *)&pExceptionObject;
      }
      v7 = (__int64 *)operator new(0x28u);
      v11 = v7;
      if ( v7 )
      {
        v8 = v12;
        v12 = 0;
        v11 = (__int64 *)v8;
        v9 = MsxmlDomElement::MsxmlDomElement(v7, &v11);
        *a2 = v9;
        if ( v9 )
          _InterlockedIncrement((volatile signed __int32 *)(v9 + 8));
      }
      else
      {
        *a2 = 0;
      }
      goto LABEL_21;
    }
  }
  *a2 = 0;
  if ( v11 )
    winrt::com_ptr<IXMLDOMParseError>::unconditional_release_ref((__int64 *)&v11);
LABEL_21:
  if ( v12 )
    winrt::com_ptr<IXMLDOMParseError>::unconditional_release_ref(&v12);
  return a2;
}

```

## disassembly

```asm
0x1400115c0  mov     [rsp-18h+arg_10], rbx
0x1400115c5  mov     [rsp-18h+arg_18], rsi
0x1400115ca  push    rbp
0x1400115cb  push    rdi
0x1400115cc  push    r14
0x1400115ce  mov     rbp, rsp
0x1400115d1  sub     rsp, 80h
0x1400115d8  mov     rax, cs:__security_cookie
0x1400115df  xor     rax, rsp
0x1400115e2  mov     [rbp+var_10], rax
0x1400115e6  mov     rbx, rdx
0x1400115e9  mov     rsi, rcx
0x1400115ec  mov     [rbp+var_60], rdx
0x1400115f0  xor     r14d, r14d
0x1400115f3  mov     [rbp+var_58], r14
0x1400115f7  mov     [rbp+var_60], r14
0x1400115fb  mov     rcx, [rsi+10h]
0x1400115ff  mov     rax, [rcx]
0x140011602  lea     rdx, [rbp+var_60]
0x140011606  mov     rax, [rax+48h]
0x14001160a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001160f  mov     edi, eax
0x140011611  test    eax, eax
0x140011613  js      loc_140011762
0x140011619  test    eax, eax
0x14001161b  jnz     loc_140011719
0x140011621  cmp     [rbp+var_58], r14
0x140011625  jz      short loc_140011630
0x140011627  lea     rcx, [rbp+var_58]
0x14001162b  call    ?unconditional_release_ref@?$com_ptr@UIXMLDOMParseError@@@winrt@@AEAAXXZ; winrt::com_ptr<IXMLDOMParseError>::unconditional_release_ref(void)
0x140011630  movups  xmm0, xmmword ptr cs:IID_IXMLDOMElement.Data1
0x140011637  movdqu  [rbp+var_20], xmm0
0x14001163c  lea     r9, [rbp+var_58]
0x140011640  lea     r8, [rbp+var_20]
0x140011644  lea     rdx, [rbp+var_24]
0x140011648  lea     rcx, [rbp+var_60]
0x14001164c  call    ?as@?$com_ptr@UIXMLDOMNode@@@winrt@@QEBA?AUhresult@2@AEBUguid@2@PEAPEAX@Z; winrt::com_ptr<IXMLDOMNode>::as(winrt::guid const &,void * *)
0x140011651  mov     edi, [rax]
0x140011653  cmp     [rbp+var_60], r14
0x140011657  jz      short loc_140011662
0x140011659  lea     rcx, [rbp+var_60]
0x14001165d  call    ?unconditional_release_ref@?$com_ptr@UIXMLDOMParseError@@@winrt@@AEAAXXZ; winrt::com_ptr<IXMLDOMParseError>::unconditional_release_ref(void)
0x140011662  cmp     edi, 80004002h
0x140011668  jz      short loc_1400115F7
0x14001166a  test    edi, edi
0x14001166c  jns     short loc_1400116DB
0x14001166e  lea     rax, WPP_GLOBAL_Control
0x140011675  mov     rcx, cs:WPP_GLOBAL_Control
0x14001167c  cmp     rcx, rax
0x14001167f  jz      short loc_1400116A8
0x140011681  test    dword ptr [rcx+1Ch], 400000h
0x140011688  jz      short loc_1400116A8
0x14001168a  cmp     byte ptr [rcx+19h], 2
0x14001168e  jb      short loc_1400116A8
0x140011690  mov     edx, 14h
0x140011695  mov     r9d, edi
0x140011698  lea     r8, WPP_fda289614a233b29151e0c0c410d9667_Traceguids
0x14001169f  mov     rcx, [rcx+10h]
0x1400116a3  call    WPP_SF_d
0x1400116a8  lea     rax, word_14003838A
0x1400116af  mov     [rbp+pExceptionObject], rax
0x1400116b3  mov     [rbp+var_48], r14
0x1400116b7  mov     [rbp+var_40], r14
0x1400116bb  mov     [rbp+var_38], edi
0x1400116be  mov     [rbp+var_34], 0FFFFFFFFFFFFFFFFh
0x1400116c6  mov     [rbp+var_2C], r14b
0x1400116ca  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1400116d1  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1400116d5  call    _CxxThrowException_0
0x1400116db  mov     ecx, 28h ; '('; dwBytes
0x1400116e0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400116e5  mov     rcx, rax
0x1400116e8  mov     [rbp+var_60], rax
0x1400116ec  test    rax, rax
0x1400116ef  jz      short loc_140011714
0x1400116f1  mov     rax, [rbp+var_58]
0x1400116f5  mov     [rbp+var_58], r14
0x1400116f9  mov     [rbp+var_60], rax
0x1400116fd  lea     rdx, [rbp+var_60]
0x140011701  call    ??0MsxmlDomElement@@QEAA@U?$com_ptr@UIXMLDOMElement@@@winrt@@@Z; MsxmlDomElement::MsxmlDomElement(winrt::com_ptr<IXMLDOMElement>)
0x140011706  mov     [rbx], rax
0x140011709  test    rax, rax
0x14001170c  jz      short loc_14001172C
0x14001170e  lock inc dword ptr [rax+8]
0x140011712  jmp     short loc_14001172C
0x140011714  mov     [rbx], r14
0x140011717  jmp     short loc_14001172C
0x140011719  mov     [rbx], r14
0x14001171c  cmp     [rbp+var_60], r14
0x140011720  jz      short loc_14001172C
0x140011722  lea     rcx, [rbp+var_60]
0x140011726  call    ?unconditional_release_ref@?$com_ptr@UIXMLDOMParseError@@@winrt@@AEAAXXZ; winrt::com_ptr<IXMLDOMParseError>::unconditional_release_ref(void)
0x14001172b  nop
0x14001172c  cmp     [rbp+var_58], r14
0x140011730  jz      short loc_14001173B
0x140011732  lea     rcx, [rbp+var_58]
0x140011736  call    ?unconditional_release_ref@?$com_ptr@UIXMLDOMParseError@@@winrt@@AEAAXXZ; winrt::com_ptr<IXMLDOMParseError>::unconditional_release_ref(void)
0x14001173b  mov     rax, rbx
0x14001173e  mov     rcx, [rbp+var_10]
0x140011742  xor     rcx, rsp; StackCookie
0x140011745  call    __security_check_cookie
0x14001174a  lea     r11, [rsp+80h+var_s0]
0x140011752  mov     rbx, [r11+30h]
0x140011756  mov     rsi, [r11+38h]
0x14001175a  mov     rsp, r11
0x14001175d  pop     r14
0x14001175f  pop     rdi
0x140011760  pop     rbp
0x140011761  retn
0x140011762  lea     rax, WPP_GLOBAL_Control
0x140011769  mov     rcx, cs:WPP_GLOBAL_Control
0x140011770  cmp     rcx, rax
0x140011773  jz      short loc_14001179C
0x140011775  test    dword ptr [rcx+1Ch], 400000h
0x14001177c  jz      short loc_14001179C
0x14001177e  cmp     byte ptr [rcx+19h], 2
0x140011782  jb      short loc_14001179C
0x140011784  mov     edx, 13h
0x140011789  mov     r9d, edi
0x14001178c  lea     r8, WPP_fda289614a233b29151e0c0c410d9667_Traceguids
0x140011793  mov     rcx, [rcx+10h]
0x140011797  call    WPP_SF_d
0x14001179c  lea     rax, word_14003838A
0x1400117a3  mov     [rbp+pExceptionObject], rax
0x1400117a7  mov     [rbp+var_48], r14
0x1400117ab  mov     [rbp+var_40], r14
0x1400117af  mov     [rbp+var_38], edi
0x1400117b2  mov     [rbp+var_34], 0FFFFFFFFFFFFFFFFh
0x1400117ba  mov     [rbp+var_2C], r14b
0x1400117be  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1400117c5  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1400117c9  call    _CxxThrowException_0
```
