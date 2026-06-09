# CNodeFactory::XMLParser_Element_doc_configuration_windows_assemblyBinding_publisherPolicy(ushort,_SXS_NODE_INFO const *)

- ea: `0x180066140`
- end: `0x18006630d`
- name: `?XMLParser_Element_doc_configuration_windows_assemblyBinding_publisherPolicy@CNodeFactory@@QEAAHGPEBU_SXS_NODE_INFO@@@Z`
- size: `461`
- prototype: `__int64 __fastcall(CNodeFactory *__hidden this, unsigned __int16, const struct _SXS_NODE_INFO *)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x18000c000`
- `0x18000df40`
- `0x18000dffc`
- `0x18001c270`
- `0x180027160`
- `0x180066140`
- `0x18006a110`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800661e6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800661f9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006627c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800662c6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800661e6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800661f9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006627c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800662c6`

## string_xrefs

- `0x1800662ab`: `SXS.DLL: %s() app-level PublisherPolicy try to be set but there is no appcompat flags been set.\n`
- `0x1800661d0`: `CNodeFactory::XMLParser_Element_doc_configuration_windows_assemblyBinding_publisherPolicy`
- `0x1800661c9`: `SXS.DLL: %s() called but app-level PublisherPolicy has already been set.\n`

## pseudocode

```c
__int64 __fastcall CNodeFactory::XMLParser_Element_doc_configuration_windows_assemblyBinding_publisherPolicy(
        CNodeFactory *this,
        unsigned __int16 a2,
        const struct _SXS_NODE_INFO *a3)
{
  unsigned __int64 v3; // rdi
  __int64 v6; // rax
  __int64 v7; // rax
  int v8; // edx
  unsigned int v9; // ebx
  char v11; // [rsp+60h] [rbp-9h] BYREF
  _BYTE v12[3]; // [rsp+61h] [rbp-8h] BYREF
  int v13; // [rsp+64h] [rbp-5h] BYREF
  __int64 v14; // [rsp+68h] [rbp-1h] BYREF
  int v15; // [rsp+70h] [rbp+7h] BYREF
  __int64 v16; // [rsp+78h] [rbp+Fh]
  __int64 *v17; // [rsp+80h] [rbp+17h]
  __int64 v18; // [rsp+88h] [rbp+1Fh]
  int v19; // [rsp+90h] [rbp+27h]
  unsigned int *v20; // [rsp+98h] [rbp+2Fh]

  v3 = a2;
  v17 = &qword_180078EA8;
  v13 = 0;
  v20 = (unsigned int *)&v13;
  v15 = 1;
  v16 = 0;
  v18 = 544438355;
  v19 = 3078;
  CFrame::BaseEnter((CFrame *)&v15);
  v6 = *((_QWORD *)this + 2);
  v12[0] = 0;
  v14 = 0;
  v11 = 0;
  if ( !*(_DWORD *)(v6 + 1300) )
  {
    SetLastError(0);
    if ( !(unsigned int)SxspGetAttributeValue(
                          0,
                          (WCHAR **)qword_180079E50,
                          (__int64)a3,
                          v3,
                          (__int64)this + 400,
                          &v11,
                          1,
                          (__int64)v12,
                          &v14,
                          (unsigned int (__fastcall *)(_QWORD, void ***, char *, __int64, __int64, _QWORD *))SxspValidateBoolAttribute) )
    {
      *v20 = 0;
      FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_180078E88);
      goto LABEL_13;
    }
    if ( !v11 )
    {
      SetLastError(0x54Fu);
      *v20 = 0;
      goto LABEL_13;
    }
    v7 = *((_QWORD *)this + 2);
    if ( v12[0] )
    {
      v8 = 1;
    }
    else
    {
      v8 = 2;
      if ( (*(_BYTE *)(v7 + 1204) & 2) == 0 )
      {
        FusionpDbgPrintEx(
          0xC0000000,
          "SXS.DLL: %s() app-level PublisherPolicy try to be set but there is no appcompat flags been set.\n",
          "CNodeFactory::XMLParser_Element_doc_configuration_windows_assemblyBinding_publisherPolicy");
        goto LABEL_3;
      }
    }
    *(_DWORD *)(v7 + 1300) = v8;
    SetLastError(0);
    *v20 = 1;
    goto LABEL_13;
  }
  FusionpDbgPrintEx(
    0xC0000000,
    "SXS.DLL: %s() called but app-level PublisherPolicy has already been set.\n",
    "CNodeFactory::XMLParser_Element_doc_configuration_windows_assemblyBinding_publisherPolicy");
LABEL_3:
  SetLastError(0x36B5u);
LABEL_13:
  v9 = *v20;
  CFnTracerWin32::~CFnTracerWin32((CFnTracerWin32 *)&v15);
  return v9;
}

```

## disassembly

```asm
0x180066140  mov     [rsp-8+arg_8], rbx
0x180066145  push    rbp
0x180066146  push    rsi
0x180066147  push    rdi
0x180066148  lea     rbp, [rsp-47h]
0x18006614d  sub     rsp, 0B0h
0x180066154  mov     rax, cs:__security_cookie
0x18006615b  xor     rax, rsp
0x18006615e  mov     [rbp+57h+var_20], rax
0x180066162  lea     rax, qword_180078EA8
0x180066169  movzx   edi, dx
0x18006616c  mov     [rbp+57h+var_40], rax
0x180066170  mov     rbx, rcx
0x180066173  lea     rax, [rbp+57h+var_5C]
0x180066177  mov     [rbp+57h+var_5C], 0
0x18006617e  lea     rcx, [rbp+57h+var_50]; this
0x180066182  mov     [rbp+57h+var_28], rax
0x180066186  mov     rsi, r8
0x180066189  mov     [rbp+57h+var_50], 1
0x180066190  mov     [rbp+57h+var_48], 0
0x180066198  mov     [rbp+57h+var_38], 20737853h
0x1800661a0  mov     [rbp+57h+var_30], 0C06h
0x1800661a7  call    ?BaseEnter@CFrame@@QEAAXXZ; CFrame::BaseEnter(void)
0x1800661ac  mov     rax, [rbx+10h]
0x1800661b0  mov     [rbp+57h+var_5F], 0
0x1800661b4  mov     [rbp+57h+var_58], 0
0x1800661bc  mov     [rbp+57h+var_60], 0
0x1800661c0  cmp     dword ptr [rax+514h], 0
0x1800661c7  jz      short loc_1800661F7
0x1800661c9  lea     rdx, aSxsDllSCalledB; "SXS.DLL: %s() called but app-level Publ"...
0x1800661d0  lea     r8, aCnodefactoryXm_4; "CNodeFactory::XMLParser_Element_doc_con"...
0x1800661d7  mov     ecx, 0C0000000h; unsigned int
0x1800661dc  call    ?FusionpDbgPrintEx@@YAKKPEBDZZ; FusionpDbgPrintEx(ulong,char const *,...)
0x1800661e1  mov     ecx, 36B5h; dwErrCode
0x1800661e6  call    cs:__imp_SetLastError
0x1800661ed  nop     dword ptr [rax+rax+00h]
0x1800661f2  jmp     loc_1800662DC
0x1800661f7  xor     ecx, ecx; dwErrCode
0x1800661f9  call    cs:__imp_SetLastError
0x180066200  nop     dword ptr [rax+rax+00h]
0x180066205  lea     rcx, ?SxspValidateBoolAttribute@@YAHKAEBV?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@AEA_N_KPEAXAEA_K@Z; SxspValidateBoolAttribute(ulong,CGenericBaseStringBuffer<CUnicodeCharTraits> const &,bool &,unsigned __int64,void *,unsigned __int64 &)
0x18006620c  mov     r9, rdi
0x18006620f  mov     [rsp+0C0h+var_78], rcx
0x180066214  lea     rax, [rbx+190h]
0x18006621b  lea     rcx, [rbp+57h+var_58]
0x18006621f  mov     r8, rsi
0x180066222  mov     [rsp+0C0h+var_80], rcx
0x180066227  lea     rdx, qword_180079E50
0x18006622e  lea     rcx, [rbp+57h+var_5F]
0x180066232  mov     [rsp+0C0h+var_88], rcx
0x180066237  lea     rcx, [rbp+57h+var_60]
0x18006623b  mov     [rsp+0C0h+var_90], 1
0x180066244  mov     [rsp+0C0h+var_98], rcx
0x180066249  xor     ecx, ecx
0x18006624b  mov     [rsp+0C0h+var_A0], rax
0x180066250  call    ?SxspGetAttributeValue@@YAHKPEBU_ATTRIBUTE_NAME_DESCRIPTOR@@PEBU_SXS_NODE_INFO@@_KPEBU_ACTCTXCTB_PARSE_CONTEXT@@AEA_N2PEAXAEA_KP6AHKAEBV?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@4256@ZK@Z; SxspGetAttributeValue(ulong,_ATTRIBUTE_NAME_DESCRIPTOR const *,_SXS_NODE_INFO const *,unsigned __int64,_ACTCTXCTB_PARSE_CONTEXT const *,bool &,unsigned __int64,void *,unsigned __int64 &,int (*)(ulong,CGenericBaseStringBuffer<CUnicodeCharTraits> const &,bool &,unsigned __int64,void *,unsigned __int64 &),ulong)
0x180066255  test    eax, eax
0x180066257  jnz     short loc_180066271
0x180066259  mov     rax, [rbp+57h+var_28]
0x18006625d  lea     rcx, off_180078E88; struct _CALL_SITE_INFO *
0x180066264  mov     dword ptr [rax], 0
0x18006626a  call    ?FusionpTraceWin32LastErrorFailure@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailure(_CALL_SITE_INFO const &)
0x18006626f  jmp     short loc_1800662DC
0x180066271  cmp     [rbp+57h+var_60], 0
0x180066275  jnz     short loc_180066294
0x180066277  mov     ecx, 54Fh; dwErrCode
0x18006627c  call    cs:__imp_SetLastError
0x180066283  nop     dword ptr [rax+rax+00h]
0x180066288  mov     rax, [rbp+57h+var_28]
0x18006628c  mov     dword ptr [rax], 0
0x180066292  jmp     short loc_1800662DC
0x180066294  cmp     [rbp+57h+var_5F], 0
0x180066298  mov     rax, [rbx+10h]
0x18006629c  jnz     short loc_1800662B7
0x18006629e  mov     edx, 2
0x1800662a3  test    [rax+4B4h], dl
0x1800662a9  jnz     short loc_1800662BC
0x1800662ab  lea     rdx, aSxsDllSAppLeve; "SXS.DLL: %s() app-level PublisherPolicy"...
0x1800662b2  jmp     loc_1800661D0
0x1800662b7  mov     edx, 1
0x1800662bc  mov     ecx, 514h
0x1800662c1  mov     [rax+rcx], edx
0x1800662c4  xor     ecx, ecx; dwErrCode
0x1800662c6  call    cs:__imp_SetLastError
0x1800662cd  nop     dword ptr [rax+rax+00h]
0x1800662d2  mov     rax, [rbp+57h+var_28]
0x1800662d6  mov     dword ptr [rax], 1
0x1800662dc  mov     rax, [rbp+57h+var_28]
0x1800662e0  lea     rcx, [rbp+57h+var_50]; this
0x1800662e4  mov     ebx, [rax]
0x1800662e6  call    ??1CFnTracerWin32@@QEAA@XZ; CFnTracerWin32::~CFnTracerWin32(void)
0x1800662eb  mov     eax, ebx
0x1800662ed  mov     rcx, [rbp+57h+var_20]
0x1800662f1  xor     rcx, rsp; StackCookie
0x1800662f4  call    __security_check_cookie
0x1800662f9  mov     rbx, [rsp+0C0h+arg_8]
0x180066301  add     rsp, 0B0h
0x180066308  pop     rdi
0x180066309  pop     rsi
0x18006630a  pop     rbp
0x18006630b  retn
```
