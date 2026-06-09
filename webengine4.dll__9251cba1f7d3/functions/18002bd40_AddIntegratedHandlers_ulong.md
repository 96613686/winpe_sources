# AddIntegratedHandlers(ulong)

- ea: `0x18002bd40`
- end: `0x18002c252`
- name: `?AddIntegratedHandlers@@YAJK@Z`
- size: `1298`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18002c254`

## callees

- `0x18002b934`
- `0x18002bd40`
- `0x18002cf0c`
- `0x180031228`
- `0x180032c54`
- `0x18004d030`
- `0x180065b60`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18002bd87`
- `OLEAUT32!__imp_VariantInit` at `0x18002bd87`

## string_xrefs

- `0x18002bea2`: `WebServiceHandlerFactory-Integrated-4.0`
- `0x18002beb8`: `System.Web.Script.Services.ScriptHandlerFactory, System.Web.Extensions, Version=4.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35`
- `0x18002bdc6`: `System.Runtime.Remoting.Channels.Http.HttpRemotingHandlerFactory, System.Runtime.Remoting, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089`
- `0x18002bf51`: `System.ServiceModel.Activation.ServiceHttpHandlerFactory, System.ServiceModel.Activation, Version=4.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35`
- `0x18002bfaf`: `System.Xaml.Hosting.XamlHttpHandlerFactory, System.Xaml.Hosting, Version=4.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35`
- `0x18002c049`: `ScriptHandlerFactoryAppServices-Integrated-4.0`
- `0x18002c057`: `*_AppService.axd`
- `0x18002c065`: `System.Web.Script.Services.ScriptHandlerFactory, System.Web.Extensions, Version=4.0.0.0, Culture=neutral, PublicKeyToken=31BF3856AD364E35`
- `0x18002c0ab`: `System.Web.Handlers.ScriptResourceHandler, System.Web.Extensions, Version=4.0.0.0, Culture=neutral, PublicKeyToken=31BF3856AD364E35`
- `0x18002c1a8`: `ExtensionlessUrl-Integrated-4.0`
- `0x18002c1cd`: `ExtensionlessUrlHandler-Integrated-4.0`

## pseudocode

```c
__int64 __fastcall AddIntegratedHandlers(unsigned int a1)
{
  unsigned int CollectionForName; // ebx
  unsigned int v3; // esi
  __int128 *v4; // rdi
  const wchar_t *v5; // rcx
  __int128 v6; // xmm0
  int v7; // eax
  struct IAppHostElementCollection *v9; // [rsp+48h] [rbp-C0h] BYREF
  VARIANTARG pvarg; // [rsp+50h] [rbp-B8h] BYREF
  __int128 v11; // [rsp+68h] [rbp-A0h] BYREF
  __int128 v12; // [rsp+78h] [rbp-90h]
  const unsigned __int16 *v13; // [rsp+88h] [rbp-80h]
  unsigned __int16 *v14[5]; // [rsp+90h] [rbp-78h] BYREF
  _QWORD v15[76]; // [rsp+B8h] [rbp-50h] BYREF

  v9 = 0;
  VariantInit(&pvarg);
  v15[2] = 0;
  pvarg.vt = 3;
  v15[6] = L"GET,DEBUG";
  v14[0] = L"name";
  v15[10] = L"GET,DEBUG";
  v14[1] = L"path";
  v15[14] = 0;
  v14[2] = L"verb";
  v14[3] = L"type";
  v14[4] = L"preCondition";
  v13 = L"integratedMode,runtimeVersionv4.0";
  v15[0] = L"TraceHandler-Integrated-4.0";
  v15[1] = L"trace.axd";
  v15[3] = L"System.Web.Handlers.TraceHandler";
  v15[4] = L"WebAdminHandler-Integrated-4.0";
  v15[5] = L"WebAdmin.axd";
  v15[7] = L"System.Web.Handlers.WebAdminHandler";
  v15[8] = L"AssemblyResourceLoader-Integrated-4.0";
  v15[9] = L"WebResource.axd";
  v15[11] = L"System.Web.Handlers.AssemblyResourceLoader";
  v15[12] = L"PageHandlerFactory-Integrated-4.0";
  v15[13] = L"*.aspx";
  v15[15] = L"System.Web.UI.PageHandlerFactory";
  v15[16] = L"SimpleHandlerFactory-Integrated-4.0";
  v15[17] = L"*.ashx";
  v15[19] = L"System.Web.UI.SimpleHandlerFactory";
  v15[20] = L"WebServiceHandlerFactory-Integrated-4.0";
  v15[21] = L"*.asmx";
  v15[23] = L"System.Web.Script.Services.ScriptHandlerFactory, System.Web.Extensions, Version=4.0.0.0, Culture=neutral, Pu"
             "blicKeyToken=31bf3856ad364e35";
  v15[24] = L"HttpRemotingHandlerFactory-rem-Integrated-4.0";
  v15[25] = L"*.rem";
  v15[28] = L"HttpRemotingHandlerFactory-soap-Integrated-4.0";
  v15[29] = L"*.soap";
  v15[32] = L"svc-Integrated-4.0";
  v15[33] = L"*.svc";
  v15[18] = 0;
  v15[22] = 0;
  v15[26] = 0;
  v15[27] = L"System.Runtime.Remoting.Channels.Http.HttpRemotingHandlerFactory, System.Runtime.Remoting, Version=4.0.0.0, "
             "Culture=neutral, PublicKeyToken=b77a5c561934e089";
  v15[30] = 0;
  v15[31] = L"System.Runtime.Remoting.Channels.Http.HttpRemotingHandlerFactory, System.Runtime.Remoting, Version=4.0.0.0, "
             "Culture=neutral, PublicKeyToken=b77a5c561934e089";
  v15[34] = L"*";
  v15[38] = L"*";
  v15[36] = L"rules-Integrated-4.0";
  v15[35] = L"System.ServiceModel.Activation.ServiceHttpHandlerFactory, System.ServiceModel.Activation, Version=4.0.0.0, C"
             "ulture=neutral, PublicKeyToken=31bf3856ad364e35";
  v15[37] = L"*.rules";
  v15[39] = L"System.ServiceModel.Activation.ServiceHttpHandlerFactory, System.ServiceModel.Activation, Version=4.0.0.0, C"
             "ulture=neutral, PublicKeyToken=31bf3856ad364e35";
  v15[40] = L"xoml-Integrated-4.0";
  v15[41] = L"*.xoml";
  v15[44] = L"xamlx-Integrated-4.0";
  v15[45] = L"*.xamlx";
  v15[47] = L"System.Xaml.Hosting.XamlHttpHandlerFactory, System.Xaml.Hosting, Version=4.0.0.0, Culture=neutral, PublicKey"
             "Token=31bf3856ad364e35";
  v15[48] = L"aspq-Integrated-4.0";
  v15[49] = L"*.aspq";
  v15[52] = L"cshtm-Integrated-4.0";
  v15[53] = L"*.cshtm";
  v15[56] = L"cshtml-Integrated-4.0";
  v15[57] = L"*.cshtml";
  v15[60] = L"vbhtm-Integrated-4.0";
  v15[61] = L"*.vbhtm";
  v15[64] = L"vbhtml-Integrated-4.0";
  v15[65] = L"*.vbhtml";
  v15[68] = L"ScriptHandlerFactoryAppServices-Integrated-4.0";
  v15[69] = L"*_AppService.axd";
  v15[71] = L"System.Web.Script.Services.ScriptHandlerFactory, System.Web.Extensions, Version=4.0.0.0, Culture=neutral, Pu"
             "blicKeyToken=31BF3856AD364E35";
  v15[72] = L"ScriptResourceIntegrated-4.0";
  v15[73] = L"ScriptResource.axd";
  v15[43] = L"System.ServiceModel.Activation.ServiceHttpHandlerFactory, System.ServiceModel.Activation, Version=4.0.0.0, C"
             "ulture=neutral, PublicKeyToken=31bf3856ad364e35";
  v15[74] = L"GET,HEAD";
  v15[42] = L"*";
  v15[51] = L"System.Web.HttpForbiddenHandler";
  v15[55] = L"System.Web.HttpForbiddenHandler";
  v15[59] = L"System.Web.HttpForbiddenHandler";
  v15[63] = L"System.Web.HttpForbiddenHandler";
  v15[67] = L"System.Web.HttpForbiddenHandler";
  v15[70] = L"*";
  v15[75] = L"System.Web.Handlers.ScriptResourceHandler, System.Web.Extensions, Version=4.0.0.0, Culture=neutral, PublicKe"
             "yToken=31BF3856AD364E35";
  v15[46] = 0;
  v15[50] = 0;
  v15[54] = 0;
  v15[58] = 0;
  v15[62] = 0;
  v15[66] = 0;
  CollectionForName = GetCollectionForName(L"system.webServer/handlers", &v9, 0);
  if ( !CollectionForName )
  {
    v3 = 0;
    v4 = (__int128 *)v15;
    while ( 1 )
    {
      v5 = L"GET,HEAD,POST,DEBUG";
      v6 = *v4;
      v12 = v4[1];
      if ( (_QWORD)v12 )
        v5 = (const wchar_t *)v12;
      *(_QWORD *)&v12 = v5;
      v11 = v6;
      v7 = AddElementToCollectionIfDoesntExist(
             v9,
             5u,
             (const unsigned __int16 **)v14,
             (const unsigned __int16 **)&v11,
             a1++,
             1,
             0,
             0);
      CollectionForName = v7;
      if ( v7 )
        break;
      ++v3;
      v4 += 2;
      if ( v3 >= 0x13 )
      {
        CollectionForName = RemoveFromSection(
                              L"system.webServer/handlers",
                              (OLECHAR *)L"name",
                              L"ExtensionlessUrl-Integrated-4.0",
                              0);
        if ( !CollectionForName )
        {
          *(_QWORD *)&v11 = L"ExtensionlessUrlHandler-Integrated-4.0";
          *(_QWORD *)&v12 = L"GET,HEAD,POST,DEBUG";
          *((_QWORD *)&v11 + 1) = L"*.";
          *((_QWORD *)&v12 + 1) = L"System.Web.Handlers.TransferRequestHandler";
          CollectionForName = AddOrUpdateExtensionlessHandler(
                                v9,
                                5u,
                                (const unsigned __int16 **)v14,
                                (const unsigned __int16 **)&v11);
        }
        break;
      }
    }
  }
  if ( v9 )
    ((void (__fastcall *)(struct IAppHostElementCollection *))v9->lpVtbl->Release)(v9);
  return CollectionForName;
}

```

## disassembly

```asm
0x18002bd40  mov     rax, rsp
0x18002bd43  mov     [rax+8], rbx
0x18002bd47  mov     [rax+10h], rsi
0x18002bd4b  mov     [rax+18h], rdi
0x18002bd4f  mov     [rax+20h], r12
0x18002bd53  push    rbp
0x18002bd54  push    r14
0x18002bd56  push    r15
0x18002bd58  lea     rbp, [rax-238h]
0x18002bd5f  sub     rsp, 320h
0x18002bd66  mov     rax, cs:__security_cookie
0x18002bd6d  xor     rax, rsp
0x18002bd70  mov     [rbp+230h+var_20], rax
0x18002bd77  mov     r14d, ecx
0x18002bd7a  xor     r15d, r15d
0x18002bd7d  lea     rcx, [rsp+330h+pvarg]; pvarg
0x18002bd82  mov     [rsp+330h+var_2F0], r15
0x18002bd87  call    cs:__imp_VariantInit
0x18002bd8d  lea     eax, [r15+3]
0x18002bd91  mov     [rbp+230h+var_270], r15
0x18002bd95  mov     word ptr [rsp+330h+pvarg], ax
0x18002bd9a  lea     rcx, aGetDebug; "GET,DEBUG"
0x18002bda1  lea     rax, aName; "name"
0x18002bda8  mov     [rbp+230h+var_250], rcx
0x18002bdac  mov     [rbp+230h+var_2A8], rax
0x18002bdb0  lea     rdx, asc_180070068; "*"
0x18002bdb7  lea     rax, aPath_0; "path"
0x18002bdbe  mov     [rbp+230h+var_230], rcx
0x18002bdc2  mov     [rbp+230h+var_2A0], rax
0x18002bdc6  lea     rcx, aSystemRuntimeR; "System.Runtime.Remoting.Channels.Http.H"...
0x18002bdcd  lea     rax, aVerb; "verb"
0x18002bdd4  mov     [rbp+230h+var_210], r15
0x18002bdd8  mov     [rbp+230h+var_298], rax
0x18002bddc  lea     rax, aType; "type"
0x18002bde3  mov     [rbp+230h+var_290], rax
0x18002bde7  lea     rax, aPrecondition; "preCondition"
0x18002bdee  mov     [rbp+230h+var_288], rax
0x18002bdf2  lea     rax, aIntegratedmode_0; "integratedMode,runtimeVersionv4.0"
0x18002bdf9  mov     [rbp+230h+var_2B0], rax
0x18002bdfd  lea     rax, aTracehandlerIn; "TraceHandler-Integrated-4.0"
0x18002be04  mov     [rbp+230h+var_280], rax
0x18002be08  lea     rax, aTraceAxd; "trace.axd"
0x18002be0f  mov     [rbp+230h+var_278], rax
0x18002be13  lea     rax, aSystemWebHandl_1; "System.Web.Handlers.TraceHandler"
0x18002be1a  mov     [rbp+230h+var_268], rax
0x18002be1e  lea     rax, aWebadminhandle; "WebAdminHandler-Integrated-4.0"
0x18002be25  mov     [rbp+230h+var_260], rax
0x18002be29  lea     rax, aWebadminAxd; "WebAdmin.axd"
0x18002be30  mov     [rbp+230h+var_258], rax
0x18002be34  lea     rax, aSystemWebHandl; "System.Web.Handlers.WebAdminHandler"
0x18002be3b  mov     [rbp+230h+var_248], rax
0x18002be3f  lea     rax, aAssemblyresour; "AssemblyResourceLoader-Integrated-4.0"
0x18002be46  mov     [rbp+230h+var_240], rax
0x18002be4a  lea     rax, aWebresourceAxd; "WebResource.axd"
0x18002be51  mov     [rbp+230h+var_238], rax
0x18002be55  lea     rax, aSystemWebHandl_0; "System.Web.Handlers.AssemblyResourceLoa"...
0x18002be5c  mov     [rbp+230h+var_228], rax
0x18002be60  lea     rax, aPagehandlerfac_0; "PageHandlerFactory-Integrated-4.0"
0x18002be67  mov     [rbp+230h+var_220], rax
0x18002be6b  lea     rax, aAspx; "*.aspx"
0x18002be72  mov     [rbp+230h+var_218], rax
0x18002be76  lea     rax, aSystemWebUiPag; "System.Web.UI.PageHandlerFactory"
0x18002be7d  mov     [rbp+230h+var_208], rax
0x18002be81  lea     rax, aSimplehandlerf_1; "SimpleHandlerFactory-Integrated-4.0"
0x18002be88  mov     [rbp+230h+var_200], rax
0x18002be8c  lea     rax, aAshx_0; "*.ashx"
0x18002be93  mov     [rbp+230h+var_1F8], rax
0x18002be97  lea     rax, aSystemWebUiSim; "System.Web.UI.SimpleHandlerFactory"
0x18002be9e  mov     [rbp+230h+var_1E8], rax
0x18002bea2  lea     rax, aWebservicehand_0; "WebServiceHandlerFactory-Integrated-4.0"
0x18002bea9  mov     [rbp+230h+var_1E0], rax
0x18002bead  lea     rax, aAsmx_0; "*.asmx"
0x18002beb4  mov     [rbp+230h+var_1D8], rax
0x18002beb8  lea     rax, aSystemWebScrip; "System.Web.Script.Services.ScriptHandle"...
0x18002bebf  mov     [rbp+230h+var_1C8], rax
0x18002bec3  lea     rax, aHttpremotingha_1; "HttpRemotingHandlerFactory-rem-Integrat"...
0x18002beca  mov     [rbp+230h+var_1C0], rax
0x18002bece  lea     rax, aRem; "*.rem"
0x18002bed5  mov     [rbp+230h+var_1B8], rax
0x18002bed9  lea     rax, aHttpremotingha_4; "HttpRemotingHandlerFactory-soap-Integra"...
0x18002bee0  mov     [rbp+230h+var_1A0], rax
0x18002bee7  lea     rax, aSoap_0; "*.soap"
0x18002beee  mov     [rbp+230h+var_198], rax
0x18002bef5  lea     rax, aSvcIntegrated4; "svc-Integrated-4.0"
0x18002befc  mov     [rbp+230h+var_180], rax
0x18002bf03  lea     rax, aSvc_0; "*.svc"
0x18002bf0a  mov     [rbp+230h+var_178], rax
0x18002bf11  mov     [rbp+230h+var_1F0], r15
0x18002bf15  mov     [rbp+230h+var_1D0], r15
0x18002bf19  mov     [rbp+230h+var_1B0], r15
0x18002bf20  mov     [rbp+230h+var_1A8], rcx
0x18002bf27  mov     [rbp+230h+var_190], r15
0x18002bf2e  mov     [rbp+230h+var_188], rcx
0x18002bf35  mov     [rbp+230h+var_170], rdx
0x18002bf3c  lea     rax, aRulesIntegrate; "rules-Integrated-4.0"
0x18002bf43  mov     [rbp+230h+var_150], rdx
0x18002bf4a  mov     [rbp+230h+var_160], rax
0x18002bf51  lea     rcx, aSystemServicem; "System.ServiceModel.Activation.ServiceH"...
0x18002bf58  lea     rax, aRules_1; "*.rules"
0x18002bf5f  mov     [rbp+230h+var_168], rcx
0x18002bf66  mov     [rbp+230h+var_158], rax
0x18002bf6d  xor     r8d, r8d; unsigned __int16 *
0x18002bf70  lea     rax, aXomlIntegrated; "xoml-Integrated-4.0"
0x18002bf77  mov     [rbp+230h+var_148], rcx
0x18002bf7e  mov     [rbp+230h+var_140], rax
0x18002bf85  lea     rax, aXoml_0; "*.xoml"
0x18002bf8c  mov     [rbp+230h+var_138], rax
0x18002bf93  lea     rax, aXamlxIntegrate; "xamlx-Integrated-4.0"
0x18002bf9a  mov     [rbp+230h+var_120], rax
0x18002bfa1  lea     rax, aXamlx_0; "*.xamlx"
0x18002bfa8  mov     [rbp+230h+var_118], rax
0x18002bfaf  lea     rax, aSystemXamlHost; "System.Xaml.Hosting.XamlHttpHandlerFact"...
0x18002bfb6  mov     [rbp+230h+var_108], rax
0x18002bfbd  lea     rax, aAspqIntegrated; "aspq-Integrated-4.0"
0x18002bfc4  mov     [rbp+230h+var_100], rax
0x18002bfcb  lea     rax, aAspq_0; "*.aspq"
0x18002bfd2  mov     [rbp+230h+var_F8], rax
0x18002bfd9  lea     rax, aCshtmIntegrate; "cshtm-Integrated-4.0"
0x18002bfe0  mov     [rbp+230h+var_E0], rax
0x18002bfe7  lea     rax, aCshtm_0; "*.cshtm"
0x18002bfee  mov     [rbp+230h+var_D8], rax
0x18002bff5  lea     rax, aCshtmlIntegrat; "cshtml-Integrated-4.0"
0x18002bffc  mov     [rbp+230h+var_C0], rax
0x18002c003  lea     rax, aCshtml; "*.cshtml"
0x18002c00a  mov     [rbp+230h+var_B8], rax
0x18002c011  lea     rax, aVbhtmIntegrate; "vbhtm-Integrated-4.0"
0x18002c018  mov     [rbp+230h+var_A0], rax
0x18002c01f  lea     rax, aVbhtm_0; "*.vbhtm"
0x18002c026  mov     [rbp+230h+var_98], rax
0x18002c02d  lea     rax, aVbhtmlIntegrat; "vbhtml-Integrated-4.0"
0x18002c034  mov     [rbp+230h+var_80], rax
0x18002c03b  lea     rax, aVbhtml_0; "*.vbhtml"
0x18002c042  mov     [rbp+230h+var_78], rax
0x18002c049  lea     rax, aScripthandlerf; "ScriptHandlerFactoryAppServices-Integra"...
0x18002c050  mov     [rbp+230h+var_60], rax
0x18002c057  lea     rax, aAppserviceAxd; "*_AppService.axd"
0x18002c05e  mov     [rbp+230h+var_58], rax
0x18002c065  lea     rax, aSystemWebScrip_0; "System.Web.Script.Services.ScriptHandle"...
0x18002c06c  mov     [rbp+230h+var_48], rax
0x18002c073  lea     rax, aScriptresource_0; "ScriptResourceIntegrated-4.0"
0x18002c07a  mov     [rbp+230h+var_40], rax
0x18002c081  lea     rax, aScriptresource; "ScriptResource.axd"
0x18002c088  mov     [rbp+230h+var_38], rax
0x18002c08f  lea     rax, aGetHead; "GET,HEAD"
0x18002c096  mov     [rbp+230h+var_128], rcx
0x18002c09d  lea     rcx, aSystemWebHttpf; "System.Web.HttpForbiddenHandler"
0x18002c0a4  mov     [rbp+230h+var_30], rax
0x18002c0ab  lea     rax, aSystemWebHandl_2; "System.Web.Handlers.ScriptResourceHandl"...
0x18002c0b2  mov     [rbp+230h+var_130], rdx
0x18002c0b9  mov     [rbp+230h+var_E8], rcx
0x18002c0c0  mov     [rbp+230h+var_C8], rcx
0x18002c0c7  mov     [rbp+230h+var_A8], rcx
0x18002c0ce  mov     [rbp+230h+var_88], rcx
0x18002c0d5  mov     [rbp+230h+var_68], rcx
0x18002c0dc  lea     rcx, aSystemWebserve_7; "system.webServer/handlers"
0x18002c0e3  mov     [rbp+230h+var_50], rdx
0x18002c0ea  lea     rdx, [rsp+330h+var_2F0]; struct IAppHostElementCollection **
0x18002c0ef  mov     [rbp+230h+var_28], rax
0x18002c0f6  mov     [rbp+230h+var_110], r15
0x18002c0fd  mov     [rbp+230h+var_F0], r15
0x18002c104  mov     [rbp+230h+var_D0], r15
0x18002c10b  mov     [rbp+230h+var_B0], r15
0x18002c112  mov     [rbp+230h+var_90], r15
0x18002c119  mov     [rbp+230h+var_70], r15
0x18002c120  call    ?GetCollectionForName@@YAJPEBGPEAPEAUIAppHostElementCollection@@PEAG@Z; GetCollectionForName(ushort const *,IAppHostElementCollection * *,ushort *)
0x18002c125  mov     ebx, eax
0x18002c127  test    eax, eax
0x18002c129  jnz     loc_18002C209
0x18002c12f  mov     esi, r15d
0x18002c132  lea     rdi, [rbp+230h+var_280]
0x18002c136  lea     r12, aGetHeadPostDeb_0; "GET,HEAD,POST,DEBUG"
0x18002c13d  movups  xmm1, xmmword ptr [rdi+10h]
0x18002c141  mov     [rsp+330h+var_2F8], r15d; int
0x18002c146  mov     rcx, r12
0x18002c149  movups  xmm0, xmmword ptr [rdi]
0x18002c14c  mov     [rsp+330h+var_300], r15; unsigned __int16 *
0x18002c151  lea     r9, [rsp+330h+var_2D0]; unsigned __int16 **
0x18002c156  movq    rax, xmm1
0x18002c15b  mov     [rsp+330h+var_308], 1; int
0x18002c163  test    rax, rax
0x18002c166  mov     [rsp+330h+var_310], r14d; unsigned int
0x18002c16b  movups  [rsp+330h+var_2C8+8], xmm1
0x18002c170  cmovnz  rcx, rax
0x18002c174  lea     r8, [rbp+230h+var_2A8]; unsigned __int16 **
0x18002c178  mov     qword ptr [rsp+330h+var_2C8+8], rcx
0x18002c17d  mov     edx, 5; unsigned int
0x18002c182  mov     rcx, [rsp+330h+var_2F0]; struct IAppHostElementCollection *
0x18002c187  movups  xmmword ptr [rsp+330h+var_2D0], xmm0
0x18002c18c  call    ?AddElementToCollectionIfDoesntExist@@YAJPEAUIAppHostElementCollection@@KPEAPEBG1KHPEAGH@Z; AddElementToCollectionIfDoesntExist(IAppHostElementCollection *,ulong,ushort const * *,ushort const * *,ulong,int,ushort *,int)
0x18002c191  inc     r14d
0x18002c194  mov     ebx, eax
0x18002c196  test    eax, eax
0x18002c198  jnz     short loc_18002C209
0x18002c19a  inc     esi
0x18002c19c  add     rdi, 20h ; ' '
0x18002c1a0  cmp     esi, 13h
0x18002c1a3  jb      short loc_18002C13D
0x18002c1a5  xor     r9d, r9d; int
0x18002c1a8  lea     r8, aExtensionlessu_0; "ExtensionlessUrl-Integrated-4.0"
0x18002c1af  lea     rdx, aName; "name"
0x18002c1b6  lea     rcx, aSystemWebserve_7; "system.webServer/handlers"
0x18002c1bd  call    ?RemoveFromSection@@YAJPEBG00H@Z; RemoveFromSection(ushort const *,ushort const *,ushort const *,int)
0x18002c1c2  mov     ebx, eax
0x18002c1c4  test    eax, eax
0x18002c1c6  jnz     short loc_18002C209
0x18002c1c8  mov     rcx, [rsp+330h+var_2F0]; struct IAppHostElementCollection *
0x18002c1cd  lea     rax, aExtensionlessu_3; "ExtensionlessUrlHandler-Integrated-4.0"
0x18002c1d4  mov     [rsp+330h+var_2D0], rax
0x18002c1d9  lea     r9, [rsp+330h+var_2D0]; unsigned __int16 **
0x18002c1de  lea     rax, asc_180070650; "*."
0x18002c1e5  mov     qword ptr [rsp+330h+var_2C8+8], r12
0x18002c1ea  mov     qword ptr [rsp+330h+var_2C8], rax
0x18002c1ef  lea     r8, [rbp+230h+var_2A8]; unsigned __int16 **
0x18002c1f3  lea     rax, aSystemWebHandl_4; "System.Web.Handlers.TransferRequestHand"...
0x18002c1fa  lea     edx, [rbx+5]; unsigned int
0x18002c1fd  mov     [rsp+330h+var_2B8], rax
0x18002c202  call    ?AddOrUpdateExtensionlessHandler@@YAJPEAUIAppHostElementCollection@@KPEAPEBG1@Z; AddOrUpdateExtensionlessHandler(IAppHostElementCollection *,ulong,ushort const * *,ushort const * *)
0x18002c207  mov     ebx, eax
0x18002c209  mov     rcx, [rsp+330h+var_2F0]
0x18002c20e  test    rcx, rcx
0x18002c211  jz      short loc_18002C220
0x18002c213  mov     rax, [rcx]
0x18002c216  mov     rax, [rax+10h]
0x18002c21a  call    cs:__guard_dispatch_icall_fptr
0x18002c220  mov     eax, ebx
0x18002c222  mov     rcx, [rbp+230h+var_20]
0x18002c229  xor     rcx, rsp; StackCookie
0x18002c22c  call    __security_check_cookie
0x18002c231  lea     r11, [rsp+330h+var_10]
0x18002c239  mov     rbx, [r11+20h]
0x18002c23d  mov     rsi, [r11+28h]
0x18002c241  mov     rdi, [r11+30h]
0x18002c245  mov     r12, [r11+38h]
0x18002c249  mov     rsp, r11
0x18002c24c  pop     r15
0x18002c24e  pop     r14
0x18002c250  pop     rbp
0x18002c251  retn
```
