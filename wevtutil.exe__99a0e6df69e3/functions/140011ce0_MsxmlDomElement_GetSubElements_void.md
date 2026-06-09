# MsxmlDomElement::GetSubElements(void)

- ea: `0x140011ce0`
- end: `0x140011df3`
- name: `?GetSubElements@MsxmlDomElement@@UEAA?AV?$AutoRef@VAbstractDomElementList@@@wmi@@XZ`
- size: `275`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000116c`

## callees

- `0x140002bd0`
- `0x140011570`
- `0x140011ce0`
- `0x140011dfc`
- `0x140022cec`
- `0x140031810`
- `0x140034010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 *__fastcall MsxmlDomElement::GetSubElements(__int64 a1, __int64 *a2)
{
  int v3; // edi
  void *v4; // rax
  __int64 v5; // rcx
  __int64 v6; // rax
  _QWORD pExceptionObject[3]; // [rsp+28h] [rbp-28h] BYREF
  int v9; // [rsp+40h] [rbp-10h]
  __int64 v10; // [rsp+44h] [rbp-Ch]
  char v11; // [rsp+4Ch] [rbp-4h]
  __int64 v12; // [rsp+60h] [rbp+10h] BYREF
  __int64 v13; // [rsp+70h] [rbp+20h] BYREF

  v12 = 0;
  v3 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**(_QWORD **)(a1 + 32) + 96LL))(*(_QWORD *)(a1 + 32), &v12);
  if ( v3 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        12,
        WPP_fda289614a233b29151e0c0c410d9667_Traceguids,
        (unsigned int)v3);
    }
    pExceptionObject[0] = word_14003838A;
    pExceptionObject[1] = 0;
    pExceptionObject[2] = 0;
    v9 = v3;
    v10 = -1;
    v11 = 0;
    throw (EvtException *)pExceptionObject;
  }
  v4 = operator new(0x18u);
  v13 = (__int64)v4;
  if ( v4 )
  {
    v5 = v12;
    v12 = 0;
    v13 = v5;
    v6 = MsxmlDomElementList::MsxmlDomElementList(v4, &v13);
    *a2 = v6;
    if ( v6 )
      _InterlockedIncrement((volatile signed __int32 *)(v6 + 8));
  }
  else
  {
    *a2 = 0;
  }
  if ( v12 )
    winrt::com_ptr<IXMLDOMParseError>::unconditional_release_ref(&v12);
  return a2;
}

```

## disassembly

```asm
0x140011ce0  mov     [rsp-8+arg_8], rbx
0x140011ce5  mov     [rsp-8+arg_18], rdi
0x140011cea  push    rbp
0x140011ceb  mov     rbp, rsp
0x140011cee  sub     rsp, 50h
0x140011cf2  mov     rbx, rdx
0x140011cf5  mov     [rbp+arg_0], 0
0x140011cfd  mov     rcx, [rcx+20h]
0x140011d01  mov     rax, [rcx]
0x140011d04  lea     rdx, [rbp+arg_0]
0x140011d08  mov     rax, [rax+60h]
0x140011d0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011d11  mov     edi, eax
0x140011d13  test    eax, eax
0x140011d15  jns     short loc_140011D8C
0x140011d17  lea     rax, WPP_GLOBAL_Control
0x140011d1e  mov     rcx, cs:WPP_GLOBAL_Control
0x140011d25  cmp     rcx, rax
0x140011d28  jz      short loc_140011D51
0x140011d2a  test    dword ptr [rcx+1Ch], 400000h
0x140011d31  jz      short loc_140011D51
0x140011d33  cmp     byte ptr [rcx+19h], 2
0x140011d37  jb      short loc_140011D51
0x140011d39  mov     edx, 0Ch
0x140011d3e  mov     r9d, edi
0x140011d41  lea     r8, WPP_fda289614a233b29151e0c0c410d9667_Traceguids
0x140011d48  mov     rcx, [rcx+10h]
0x140011d4c  call    WPP_SF_d
0x140011d51  lea     rax, word_14003838A
0x140011d58  mov     [rbp+pExceptionObject], rax
0x140011d5c  mov     [rbp+var_20], 0
0x140011d64  mov     [rbp+var_18], 0
0x140011d6c  mov     [rbp+var_10], edi
0x140011d6f  mov     [rbp+var_C], 0FFFFFFFFFFFFFFFFh
0x140011d77  mov     [rbp+var_4], 0
0x140011d7b  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x140011d82  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x140011d86  call    _CxxThrowException_0
0x140011d8c  mov     ecx, 18h; dwBytes
0x140011d91  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140011d96  mov     [rbp+arg_10], rax
0x140011d9a  test    rax, rax
0x140011d9d  jz      short loc_140011DC9
0x140011d9f  mov     rcx, [rbp+arg_0]
0x140011da3  mov     [rbp+arg_0], 0
0x140011dab  mov     [rbp+arg_10], rcx
0x140011daf  lea     rdx, [rbp+arg_10]
0x140011db3  mov     rcx, rax
0x140011db6  call    ??0MsxmlDomElementList@@QEAA@U?$com_ptr@UIXMLDOMNodeList@@@winrt@@@Z; MsxmlDomElementList::MsxmlDomElementList(winrt::com_ptr<IXMLDOMNodeList>)
0x140011dbb  mov     [rbx], rax
0x140011dbe  test    rax, rax
0x140011dc1  jz      short loc_140011DD0
0x140011dc3  lock inc dword ptr [rax+8]
0x140011dc7  jmp     short loc_140011DD0
0x140011dc9  mov     qword ptr [rbx], 0
0x140011dd0  cmp     [rbp+arg_0], 0
0x140011dd5  jz      short loc_140011DE0
0x140011dd7  lea     rcx, [rbp+arg_0]
0x140011ddb  call    ?unconditional_release_ref@?$com_ptr@UIXMLDOMParseError@@@winrt@@AEAAXXZ; winrt::com_ptr<IXMLDOMParseError>::unconditional_release_ref(void)
0x140011de0  mov     rax, rbx
0x140011de3  mov     rbx, [rsp+50h+arg_8]
0x140011de8  mov     rdi, [rsp+50h+arg_18]
0x140011ded  add     rsp, 50h
0x140011df1  pop     rbp
0x140011df2  retn
```
