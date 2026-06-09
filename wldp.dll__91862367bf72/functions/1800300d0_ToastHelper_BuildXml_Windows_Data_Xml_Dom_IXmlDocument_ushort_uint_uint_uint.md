# ToastHelper::BuildXml(Windows::Data::Xml::Dom::IXmlDocument *,ushort *,uint,uint,uint)

- ea: `0x1800300d0`
- end: `0x18003021c`
- name: `?BuildXml@ToastHelper@@SAJPEAUIXmlDocument@Dom@Xml@Data@Windows@@PEAGIII@Z`
- size: `332`
- prototype: `__int64 __fastcall(__int64 (__fastcall ***)(struct Windows::Data::Xml::Dom::IXmlDocument *, GUID *, int *), unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180030cb0`

## callees

- `0x18001f038`
- `0x180021ec0`
- `0x18002f964`
- `0x18002fb7c`
- `0x18002fc48`
- `0x1800300d0`
- `0x1800303d0`
- `0x180042010`

## string_xrefs

- `0x180030193`: `onecore\base\ngscb\wldp\dll\toasthelper.cpp`
- `0x1800300f2`: `<toast launch="https://go.microsoft.com/fwlink/?linkid=2187074" activationType="protocol"> <visual>  <binding template="ToastGeneric">   <text id="2001"></text>   <text id="3001"></text>  </binding> </visual> <actions>  <action id="4001" activationType="protocol" arguments="https://go.microsoft.com/fwlink/?linkid=2187074"/> </actions></toast>`

## pseudocode

```c
__int64 __fastcall ToastHelper::BuildXml(
        __int64 (__fastcall ***a1)(struct Windows::Data::Xml::Dom::IXmlDocument *, GUID *, int *),
        unsigned __int16 *a2)
{
  __int64 (__fastcall *v3)(struct Windows::Data::Xml::Dom::IXmlDocument *, GUID *, int *); // rbx
  int ResourceToXml; // eax
  unsigned int v5; // ebx
  __int64 v6; // rdx
  __int64 v7; // rdi
  __int64 (__fastcall *v8)(__int64, _QWORD); // rbx
  __int64 v9; // rax
  unsigned __int16 *v10; // rdx
  int v12[4]; // [rsp+20h] [rbp-58h] BYREF
  const wchar_t *v13; // [rsp+30h] [rbp-48h] BYREF
  _BYTE v14[24]; // [rsp+40h] [rbp-38h] BYREF
  __int64 v15; // [rsp+58h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  v13 = L"<toast launch=\"https://go.microsoft.com/fwlink/?linkid=2187074\" activationType=\"protocol\"> <visual>  <bindin"
         "g template=\"ToastGeneric\">   <text id=\"2001\"></text>   <text id=\"3001\"></text>  </binding> </visual> <act"
         "ions>  <action id=\"4001\" activationType=\"protocol\" arguments=\"https://go.microsoft.com/fwlink/?linkid=2187"
         "074\"/> </actions></toast>";
  *(_QWORD *)v12 = 0;
  v3 = **a1;
  *(_QWORD *)v12 = 0;
  ResourceToXml = v3(
                    (struct Windows::Data::Xml::Dom::IXmlDocument *)a1,
                    &GUID_6cd0e74e_ee65_4489_9ebf_ca43e87ba637,
                    v12);
  v5 = ResourceToXml;
  if ( ResourceToXml >= 0 )
  {
    v7 = *(_QWORD *)v12;
    v8 = *(__int64 (__fastcall **)(__int64, _QWORD))(**(_QWORD **)v12 + 48LL);
    v9 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v14, &v13);
    ResourceToXml = v8(v7, *(_QWORD *)(v9 + 24));
    v5 = ResourceToXml;
    v15 = 0;
    if ( ResourceToXml >= 0 )
    {
      ResourceToXml = ToastHelper::LoadResourceToXml(0x7D1u, (struct Windows::Data::Xml::Dom::IXmlDocument *)a1);
      v5 = ResourceToXml;
      if ( ResourceToXml >= 0 )
      {
        ResourceToXml = ToastHelper::LoadResourceToXml(0xBB9u, (struct Windows::Data::Xml::Dom::IXmlDocument *)a1);
        v5 = ResourceToXml;
        if ( ResourceToXml >= 0 )
        {
          ResourceToXml = ToastHelper::AddResourceAttributeToXml(
                            0xFA1u,
                            v10,
                            (struct Windows::Data::Xml::Dom::IXmlDocument *)a1);
          v5 = ResourceToXml;
          if ( ResourceToXml >= 0 )
          {
            v5 = 0;
            goto LABEL_13;
          }
          v6 = 222;
        }
        else
        {
          v6 = 220;
        }
      }
      else
      {
        v6 = 218;
      }
    }
    else
    {
      v6 = 216;
    }
  }
  else
  {
    v6 = 214;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v6,
    (unsigned int)"onecore\\base\\ngscb\\wldp\\dll\\toasthelper.cpp",
    (const char *)(unsigned int)ResourceToXml,
    v12[0]);
LABEL_13:
  wil::com_ptr_t<Windows::Data::Xml::Dom::IXmlDocumentIO,wil::err_exception_policy>::~com_ptr_t<Windows::Data::Xml::Dom::IXmlDocumentIO,wil::err_exception_policy>(v12);
  return v5;
}

```

## disassembly

```asm
0x1800300d0  mov     r11, rsp
0x1800300d3  mov     [r11+10h], rbx
0x1800300d7  mov     [r11+18h], rsi
0x1800300db  push    rdi
0x1800300dc  sub     rsp, 70h
0x1800300e0  mov     rax, cs:__security_cookie
0x1800300e7  xor     rax, rsp
0x1800300ea  mov     [rsp+78h+var_18], rax
0x1800300ef  mov     rsi, rcx
0x1800300f2  lea     rax, aToastLaunchHtt_1; "<toast launch=\"https://go.microsoft.co"...
0x1800300f9  mov     [r11-48h], rax
0x1800300fd  mov     qword ptr [r11-58h], 0
0x180030105  mov     rax, [rcx]
0x180030108  mov     rbx, [rax]
0x18003010b  mov     rcx, [r11-58h]
0x18003010f  mov     qword ptr [r11-58h], 0
0x180030117  test    rcx, rcx
0x18003011a  jz      short loc_180030128
0x18003011c  mov     rax, [rcx]
0x18003011f  mov     rax, [rax+10h]
0x180030123  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030128  lea     r8, [rsp+78h+var_58]
0x18003012d  lea     rdx, _GUID_6cd0e74e_ee65_4489_9ebf_ca43e87ba637
0x180030134  mov     rcx, rsi
0x180030137  mov     rax, rbx
0x18003013a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003013f  mov     ebx, eax
0x180030141  test    eax, eax
0x180030143  jns     short loc_18003014C
0x180030145  mov     edx, 0D6h
0x18003014a  jmp     short loc_18003018B
0x18003014c  mov     rdi, qword ptr [rsp+78h+var_58]
0x180030151  mov     rax, [rdi]
0x180030154  mov     rbx, [rax+30h]
0x180030158  lea     rdx, [rsp+78h+var_48]
0x18003015d  lea     rcx, [rsp+78h+var_38]
0x180030162  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180030167  nop
0x180030168  mov     rdx, [rax+18h]
0x18003016c  mov     rcx, rdi
0x18003016f  mov     rax, rbx
0x180030172  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030177  mov     ebx, eax
0x180030179  mov     [rsp+78h+var_20], 0
0x180030182  test    eax, eax
0x180030184  jns     short loc_1800301A1
0x180030186  mov     edx, 0D8h; void *
0x18003018b  mov     rcx, [rsp+78h]; this
0x180030190  mov     r9d, eax; char *
0x180030193  lea     r8, aOnecoreBaseNgs_7; "onecore\\base\\ngscb\\wldp\\dll\\toasth"...
0x18003019a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003019f  jmp     short loc_1800301F1
0x1800301a1  mov     rdx, rsi; struct Windows::Data::Xml::Dom::IXmlDocument *
0x1800301a4  mov     ecx, 7D1h; unsigned int
0x1800301a9  call    ?LoadResourceToXml@ToastHelper@@CAJIPEAUIXmlDocument@Dom@Xml@Data@Windows@@@Z; ToastHelper::LoadResourceToXml(uint,Windows::Data::Xml::Dom::IXmlDocument *)
0x1800301ae  mov     ebx, eax
0x1800301b0  test    eax, eax
0x1800301b2  jns     short loc_1800301BB
0x1800301b4  mov     edx, 0DAh
0x1800301b9  jmp     short loc_18003018B
0x1800301bb  mov     rdx, rsi; struct Windows::Data::Xml::Dom::IXmlDocument *
0x1800301be  mov     ecx, 0BB9h; unsigned int
0x1800301c3  call    ?LoadResourceToXml@ToastHelper@@CAJIPEAUIXmlDocument@Dom@Xml@Data@Windows@@@Z; ToastHelper::LoadResourceToXml(uint,Windows::Data::Xml::Dom::IXmlDocument *)
0x1800301c8  mov     ebx, eax
0x1800301ca  test    eax, eax
0x1800301cc  jns     short loc_1800301D5
0x1800301ce  mov     edx, 0DCh
0x1800301d3  jmp     short loc_18003018B
0x1800301d5  mov     r8, rsi; struct Windows::Data::Xml::Dom::IXmlDocument *
0x1800301d8  mov     ecx, 0FA1h; unsigned int
0x1800301dd  call    ?AddResourceAttributeToXml@ToastHelper@@CAJIPEAGPEAUIXmlDocument@Dom@Xml@Data@Windows@@@Z; ToastHelper::AddResourceAttributeToXml(uint,ushort *,Windows::Data::Xml::Dom::IXmlDocument *)
0x1800301e2  mov     ebx, eax
0x1800301e4  test    eax, eax
0x1800301e6  jns     short loc_1800301EF
0x1800301e8  mov     edx, 0DEh
0x1800301ed  jmp     short loc_18003018B
0x1800301ef  xor     ebx, ebx
0x1800301f1  lea     rcx, [rsp+78h+var_58]
0x1800301f6  call    ??1?$com_ptr_t@UIXmlDocumentIO@Dom@Xml@Data@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Data::Xml::Dom::IXmlDocumentIO,wil::err_exception_policy>::~com_ptr_t<Windows::Data::Xml::Dom::IXmlDocumentIO,wil::err_exception_policy>(void)
0x1800301fb  mov     eax, ebx
0x1800301fd  mov     rcx, [rsp+78h+var_18]
0x180030202  xor     rcx, rsp; StackCookie
0x180030205  call    __security_check_cookie
0x18003020a  lea     r11, [rsp+78h+var_8]
0x18003020f  mov     rbx, [r11+18h]
0x180030213  mov     rsi, [r11+20h]
0x180030217  mov     rsp, r11
0x18003021a  pop     rdi
0x18003021b  retn
```
