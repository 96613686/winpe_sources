# ToastHelper::BuildBlockToastXml(Windows::Data::Xml::Dom::IXmlDocument *,ushort *,uint,uint,uint,ushort const *,ushort const *)

- ea: `0x18002ff7c`
- end: `0x1800300c9`
- name: `?BuildBlockToastXml@ToastHelper@@SAJPEAUIXmlDocument@Dom@Xml@Data@Windows@@PEAGIIIPEBG2@Z`
- size: `333`
- prototype: `__int64 __fastcall(__int64 (__fastcall ***)(struct Windows::Data::Xml::Dom::IXmlDocument *, GUID *, int *), unsigned __int16 *, unsigned int, unsigned int, unsigned int, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180030b0c`
- `0x180030e24`

## callees

- `0x18001f038`
- `0x180021ec0`
- `0x18002f964`
- `0x18002fb7c`
- `0x18002fc48`
- `0x18002ff7c`
- `0x1800303d0`
- `0x180030688`
- `0x180042010`

## string_xrefs

- `0x180030043`: `onecore\base\ngscb\wldp\dll\toasthelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall ToastHelper::BuildBlockToastXml(
        __int64 (__fastcall ***a1)(struct Windows::Data::Xml::Dom::IXmlDocument *, GUID *, int *),
        unsigned __int16 *a2,
        unsigned int a3,
        unsigned int a4,
        unsigned int a5,
        const unsigned __int16 *a6,
        const unsigned __int16 *a7)
{
  __int64 (__fastcall *v10)(struct Windows::Data::Xml::Dom::IXmlDocument *, GUID *, int *); // rbx
  int ResourceToXml; // eax
  unsigned int v12; // ebx
  __int64 v13; // rdx
  __int64 v14; // rdi
  __int64 (__fastcall *v15)(__int64, _QWORD); // rbx
  __int64 v16; // rax
  unsigned __int16 *v17; // rdx
  int v19[4]; // [rsp+20h] [rbp-58h] BYREF
  unsigned __int16 *v20; // [rsp+30h] [rbp-48h] BYREF
  _BYTE v21[24]; // [rsp+40h] [rbp-38h] BYREF
  __int64 v22; // [rsp+58h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+40h]

  v20 = a2;
  *(_QWORD *)v19 = 0;
  v10 = **a1;
  *(_QWORD *)v19 = 0;
  ResourceToXml = v10(
                    (struct Windows::Data::Xml::Dom::IXmlDocument *)a1,
                    &GUID_6cd0e74e_ee65_4489_9ebf_ca43e87ba637,
                    v19);
  v12 = ResourceToXml;
  if ( ResourceToXml >= 0 )
  {
    v14 = *(_QWORD *)v19;
    v15 = *(__int64 (__fastcall **)(__int64, _QWORD))(**(_QWORD **)v19 + 48LL);
    v16 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v21, &v20);
    ResourceToXml = v15(v14, *(_QWORD *)(v16 + 24));
    v12 = ResourceToXml;
    v22 = 0;
    if ( ResourceToXml >= 0 )
    {
      ResourceToXml = ToastHelper::LoadResourceToXml(a3, (struct Windows::Data::Xml::Dom::IXmlDocument *)a1);
      v12 = ResourceToXml;
      if ( ResourceToXml >= 0 )
      {
        ResourceToXml = ToastHelper::LoadSmartAppControlToastBodyResourceToXml(
                          a4,
                          (struct Windows::Data::Xml::Dom::IXmlDocument *)a1,
                          a6,
                          a7);
        v12 = ResourceToXml;
        if ( ResourceToXml >= 0 )
        {
          ResourceToXml = ToastHelper::AddResourceAttributeToXml(
                            a5,
                            v17,
                            (struct Windows::Data::Xml::Dom::IXmlDocument *)a1);
          v12 = ResourceToXml;
          if ( ResourceToXml >= 0 )
          {
            v12 = 0;
            goto LABEL_13;
          }
          v13 = 259;
        }
        else
        {
          v13 = 257;
        }
      }
      else
      {
        v13 = 255;
      }
    }
    else
    {
      v13 = 253;
    }
  }
  else
  {
    v13 = 251;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v13,
    (unsigned int)"onecore\\base\\ngscb\\wldp\\dll\\toasthelper.cpp",
    (const char *)(unsigned int)ResourceToXml,
    v19[0]);
LABEL_13:
  wil::com_ptr_t<Windows::Data::Xml::Dom::IXmlDocumentIO,wil::err_exception_policy>::~com_ptr_t<Windows::Data::Xml::Dom::IXmlDocumentIO,wil::err_exception_policy>(v19);
  return v12;
}

```

## disassembly

```asm
0x18002ff7c  push    rbp
0x18002ff7e  push    rbx
0x18002ff7f  push    rsi
0x18002ff80  push    rdi
0x18002ff81  push    r12
0x18002ff83  push    r13
0x18002ff85  push    r14
0x18002ff87  push    r15
0x18002ff89  mov     rbp, rsp
0x18002ff8c  sub     rsp, 78h
0x18002ff90  mov     rax, cs:__security_cookie
0x18002ff97  xor     rax, rsp
0x18002ff9a  mov     [rbp+var_18], rax
0x18002ff9e  mov     r15d, r9d
0x18002ffa1  mov     r14d, r8d
0x18002ffa4  mov     rsi, rcx
0x18002ffa7  mov     [rbp+var_48], rdx
0x18002ffab  mov     r12, [rbp+arg_28]
0x18002ffaf  mov     r13, [rbp+arg_30]
0x18002ffb3  mov     qword ptr [rbp+var_58], 0
0x18002ffbb  mov     rax, [rcx]
0x18002ffbe  mov     rbx, [rax]
0x18002ffc1  mov     rcx, qword ptr [rbp+var_58]
0x18002ffc5  mov     qword ptr [rbp+var_58], 0
0x18002ffcd  test    rcx, rcx
0x18002ffd0  jz      short loc_18002FFDE
0x18002ffd2  mov     rax, [rcx]
0x18002ffd5  mov     rax, [rax+10h]
0x18002ffd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ffde  lea     r8, [rbp+var_58]
0x18002ffe2  lea     rdx, _GUID_6cd0e74e_ee65_4489_9ebf_ca43e87ba637
0x18002ffe9  mov     rcx, rsi
0x18002ffec  mov     rax, rbx
0x18002ffef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fff4  mov     ebx, eax
0x18002fff6  test    eax, eax
0x18002fff8  jns     short loc_180030001
0x18002fffa  mov     edx, 0FBh
0x18002ffff  jmp     short loc_18003003C
0x180030001  mov     rdi, qword ptr [rbp+var_58]
0x180030005  mov     rax, [rdi]
0x180030008  mov     rbx, [rax+30h]
0x18003000c  lea     rdx, [rbp+var_48]
0x180030010  lea     rcx, [rbp+var_38]
0x180030014  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180030019  nop
0x18003001a  mov     rdx, [rax+18h]
0x18003001e  mov     rcx, rdi
0x180030021  mov     rax, rbx
0x180030024  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030029  mov     ebx, eax
0x18003002b  mov     [rbp+var_20], 0
0x180030033  test    eax, eax
0x180030035  jns     short loc_180030051
0x180030037  mov     edx, 0FDh; void *
0x18003003c  mov     rcx, [rbp+40h]; this
0x180030040  mov     r9d, eax; char *
0x180030043  lea     r8, aOnecoreBaseNgs_7; "onecore\\base\\ngscb\\wldp\\dll\\toasth"...
0x18003004a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003004f  jmp     short loc_1800300A1
0x180030051  mov     rdx, rsi; struct Windows::Data::Xml::Dom::IXmlDocument *
0x180030054  mov     ecx, r14d; unsigned int
0x180030057  call    ?LoadResourceToXml@ToastHelper@@CAJIPEAUIXmlDocument@Dom@Xml@Data@Windows@@@Z; ToastHelper::LoadResourceToXml(uint,Windows::Data::Xml::Dom::IXmlDocument *)
0x18003005c  mov     ebx, eax
0x18003005e  test    eax, eax
0x180030060  jns     short loc_180030069
0x180030062  mov     edx, 0FFh
0x180030067  jmp     short loc_18003003C
0x180030069  mov     r9, r13; unsigned __int16 *
0x18003006c  mov     r8, r12; unsigned __int16 *
0x18003006f  mov     rdx, rsi; struct Windows::Data::Xml::Dom::IXmlDocument *
0x180030072  mov     ecx, r15d; unsigned int
0x180030075  call    ?LoadSmartAppControlToastBodyResourceToXml@ToastHelper@@CAJIPEAUIXmlDocument@Dom@Xml@Data@Windows@@PEBG1@Z; ToastHelper::LoadSmartAppControlToastBodyResourceToXml(uint,Windows::Data::Xml::Dom::IXmlDocument *,ushort const *,ushort const *)
0x18003007a  mov     ebx, eax
0x18003007c  test    eax, eax
0x18003007e  jns     short loc_180030087
0x180030080  mov     edx, 101h
0x180030085  jmp     short loc_18003003C
0x180030087  mov     r8, rsi; struct Windows::Data::Xml::Dom::IXmlDocument *
0x18003008a  mov     ecx, [rbp+arg_20]; unsigned int
0x18003008d  call    ?AddResourceAttributeToXml@ToastHelper@@CAJIPEAGPEAUIXmlDocument@Dom@Xml@Data@Windows@@@Z; ToastHelper::AddResourceAttributeToXml(uint,ushort *,Windows::Data::Xml::Dom::IXmlDocument *)
0x180030092  mov     ebx, eax
0x180030094  test    eax, eax
0x180030096  jns     short loc_18003009F
0x180030098  mov     edx, 103h
0x18003009d  jmp     short loc_18003003C
0x18003009f  xor     ebx, ebx
0x1800300a1  lea     rcx, [rbp+var_58]
0x1800300a5  call    ??1?$com_ptr_t@UIXmlDocumentIO@Dom@Xml@Data@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Data::Xml::Dom::IXmlDocumentIO,wil::err_exception_policy>::~com_ptr_t<Windows::Data::Xml::Dom::IXmlDocumentIO,wil::err_exception_policy>(void)
0x1800300aa  mov     eax, ebx
0x1800300ac  mov     rcx, [rbp+var_18]
0x1800300b0  xor     rcx, rsp; StackCookie
0x1800300b3  call    __security_check_cookie
0x1800300b8  add     rsp, 78h
0x1800300bc  pop     r15
0x1800300be  pop     r14
0x1800300c0  pop     r13
0x1800300c2  pop     r12
0x1800300c4  pop     rdi
0x1800300c5  pop     rsi
0x1800300c6  pop     rbx
0x1800300c7  pop     rbp
0x1800300c8  retn
```
