# HrGetTextValueFromElement(IXMLDOMNode *,ushort * *)

- ea: `0x18000af2c`
- end: `0x18000afae`
- name: `?HrGetTextValueFromElement@@YAJPEAUIXMLDOMNode@@PEAPEAG@Z`
- size: `130`
- prototype: `__int64 __fastcall(struct IXMLDOMNode *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000a6f4`
- `0x18000a8b4`

## callees

- `0x1800024c4`
- `0x18000af2c`
- `0x18000afb4`

## pseudocode

```c
__int64 __fastcall HrGetTextValueFromElement(struct IXMLDOMNode *a1, unsigned __int16 **a2)
{
  int TypedValueFromElement; // ebx
  struct tagVARIANT v5; // [rsp+20h] [rbp-28h] BYREF

  *a2 = 0;
  memset(&v5, 0, sizeof(v5));
  TypedValueFromElement = HrGetTypedValueFromElement(a1, (OLECHAR *)L"string", &v5);
  if ( TypedValueFromElement )
  {
    if ( TypedValueFromElement < 0
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        17,
        WPP_1663e5dd4df63ad0f4f5db840799a00c_Traceguids,
        (unsigned int)TypedValueFromElement);
    }
  }
  else
  {
    *a2 = v5.bstrVal;
  }
  return (unsigned int)TypedValueFromElement;
}

```

## disassembly

```asm
0x18000af2c  mov     [rsp+arg_0], rbx
0x18000af31  push    rdi
0x18000af32  sub     rsp, 40h
0x18000af36  xor     eax, eax
0x18000af38  lea     r8, [rsp+48h+var_28]; struct tagVARIANT *
0x18000af3d  mov     [rdx], rax
0x18000af40  mov     rdi, rdx
0x18000af43  xorps   xmm0, xmm0
0x18000af46  mov     qword ptr [rsp+48h+var_28+10h], rax
0x18000af4b  lea     rdx, aString; "string"
0x18000af52  movups  xmmword ptr [rsp+48h+var_28], xmm0
0x18000af57  call    ?HrGetTypedValueFromElement@@YAJPEAUIXMLDOMNode@@QEBGPEAUtagVARIANT@@@Z; HrGetTypedValueFromElement(IXMLDOMNode *,ushort const * const,tagVARIANT *)
0x18000af5c  mov     ebx, eax
0x18000af5e  test    eax, eax
0x18000af60  jnz     short loc_18000AF6C
0x18000af62  mov     rcx, qword ptr [rsp+48h+var_28+8]
0x18000af67  mov     [rdi], rcx
0x18000af6a  jmp     short loc_18000AFA1
0x18000af6c  test    ebx, ebx
0x18000af6e  jns     short loc_18000AFA1
0x18000af70  mov     rcx, cs:WPP_GLOBAL_Control
0x18000af77  lea     rax, WPP_GLOBAL_Control
0x18000af7e  cmp     rcx, rax
0x18000af81  jz      short loc_18000AFA1
0x18000af83  test    byte ptr [rcx+1Ch], 1
0x18000af87  jz      short loc_18000AFA1
0x18000af89  mov     rcx, [rcx+10h]
0x18000af8d  lea     r8, WPP_1663e5dd4df63ad0f4f5db840799a00c_Traceguids
0x18000af94  mov     edx, 11h
0x18000af99  mov     r9d, ebx
0x18000af9c  call    WPP_SF_d
0x18000afa1  mov     eax, ebx
0x18000afa3  mov     rbx, [rsp+48h+arg_0]
0x18000afa8  add     rsp, 40h
0x18000afac  pop     rdi
0x18000afad  retn
```
