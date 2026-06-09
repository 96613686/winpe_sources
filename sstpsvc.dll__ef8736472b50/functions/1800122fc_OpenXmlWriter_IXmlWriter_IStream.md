# OpenXmlWriter(IXmlWriter * *,IStream *)

- ea: `0x1800122fc`
- end: `0x18001251c`
- name: `?OpenXmlWriter@@YAKPEAPEAUIXmlWriter@@PEAUIStream@@@Z`
- size: `544`
- prototype: `unsigned int __fastcall(struct IXmlWriter **ppvObject, struct IStream *)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180014900`
- `0x180015500`

## callees

- `0x1800089dc`
- `0x180008b90`
- `0x1800122fc`
- `0x18001d1da`
- `0x18001d210`
- `0x18001e010`

## import_xrefs

- `XmlLite!CreateXmlWriter` at `0x180012356`
- `XmlLite!CreateXmlWriter` at `0x180012356`

## string_xrefs

- `0x180012377`: `OpenXmlWriter: Failed to create IXmlWriter object with error %d`
- `0x1800123b0`: `OpenXmlWriter: Failed to set the output stream for IXmlWriter object. Error %d`
- `0x1800123e6`: `OpenXmlWriter: Failed to set the XmlWriterProperty_Indent of IXmlWriter object. Error %d`
- `0x180012417`: `OpenXmlWriter: Failed to flush the output stream for IXmlWriter object. Error %d`
- `0x18001244a`: `OpenXmlWriter: WriteStartDocument of IXmlWriter object failed with error %d`
- `0x180012456`: `ProxyConfig`
- `0x1800124a4`: `OpenXmlWriter: WriteStartElement of IXmlWriter object failed with error %d`

## pseudocode

```c
__int64 __fastcall OpenXmlWriter(struct IXmlWriter **ppvObject, struct IStream *a2)
{
  unsigned int XmlWriter; // eax
  int v5; // ebx
  const wchar_t *v6; // rdx
  __int64 result; // rax
  int v8; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v9[2044]; // [rsp+34h] [rbp-CCh] BYREF

  v8 = 0;
  memset_0(v9, 0, sizeof(v9));
  *ppvObject = 0;
  XmlWriter = CreateXmlWriter(&GUID_7279fc88_709d_4095_b63d_69fe4b0d9030, (void **)ppvObject, 0);
  v5 = XmlWriter;
  if ( XmlWriter )
  {
    if ( (byte_18002E903 & 8) == 0 )
      goto LABEL_23;
    LOWORD(v8) = 0;
    FormatRRASErrorString(&v8, L"OpenXmlWriter: Failed to create IXmlWriter object with error %d", XmlWriter);
  }
  else
  {
    v5 = ((__int64 (__fastcall *)(_QWORD, struct IStream *))(*ppvObject)->lpVtbl->SetOutput)(*ppvObject, a2);
    if ( v5 )
    {
      if ( (byte_18002E903 & 8) == 0 )
        goto LABEL_23;
      v6 = L"OpenXmlWriter: Failed to set the output stream for IXmlWriter object. Error %d";
    }
    else
    {
      v5 = ((__int64 (__fastcall *)(_QWORD, __int64, __int64))(*ppvObject)->lpVtbl->SetProperty)(*ppvObject, 1, 1);
      if ( v5 )
      {
        if ( (byte_18002E903 & 8) == 0 )
          goto LABEL_23;
        v6 = L"OpenXmlWriter: Failed to set the XmlWriterProperty_Indent of IXmlWriter object. Error %d";
      }
      else
      {
        v5 = ((__int64 (__fastcall *)(_QWORD))(*ppvObject)->lpVtbl->Flush)(*ppvObject);
        if ( v5 )
        {
          if ( (byte_18002E903 & 8) == 0 )
            goto LABEL_23;
          v6 = L"OpenXmlWriter: Failed to flush the output stream for IXmlWriter object. Error %d";
        }
        else
        {
          v5 = ((__int64 (__fastcall *)(_QWORD, _QWORD))(*ppvObject)->lpVtbl->WriteStartDocument)(*ppvObject, 0);
          if ( v5 )
          {
            if ( (byte_18002E903 & 8) == 0 )
              goto LABEL_23;
            v6 = L"OpenXmlWriter: WriteStartDocument of IXmlWriter object failed with error %d";
          }
          else
          {
            v5 = ((__int64 (__fastcall *)(_QWORD, _QWORD, const wchar_t *, _QWORD))(*ppvObject)->lpVtbl->WriteStartElement)(
                   *ppvObject,
                   0,
                   L"ProxyConfig",
                   0);
            if ( !v5 )
            {
              v5 = ((__int64 (__fastcall *)(_QWORD, _QWORD, const wchar_t *, _QWORD))(*ppvObject)->lpVtbl->WriteStartElement)(
                     *ppvObject,
                     0,
                     L"TenantGatewayMap",
                     0);
              if ( !v5 )
                goto LABEL_23;
            }
            if ( (byte_18002E903 & 8) == 0 )
              goto LABEL_23;
            v6 = L"OpenXmlWriter: WriteStartElement of IXmlWriter object failed with error %d";
          }
        }
      }
    }
    LOWORD(v8) = 0;
    FormatRRASErrorString(&v8, v6, (unsigned int)v5);
  }
  if ( (byte_18002E903 & 8) != 0 )
    McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, &v8);
LABEL_23:
  result = 0;
  if ( v5 < 0 )
  {
    result = (unsigned __int16)v5;
    if ( (v5 & 0x1FFF0000) != 0x70000 )
      return (unsigned int)v5;
  }
  return result;
}

```

## disassembly

```asm
0x1800122fc  mov     [rsp-8+arg_10], rbx
0x180012301  push    rbp
0x180012302  push    rsi
0x180012303  push    rdi
0x180012304  lea     rbp, [rsp-740h]
0x18001230c  sub     rsp, 840h
0x180012313  mov     rax, cs:__security_cookie
0x18001231a  xor     rax, rsp
0x18001231d  mov     [rbp+750h+var_20], rax
0x180012324  mov     rsi, rdx
0x180012327  mov     rdi, rcx
0x18001232a  xor     eax, eax
0x18001232c  lea     rcx, [rsp+850h+var_81C]; void *
0x180012331  xor     edx, edx; Val
0x180012333  mov     [rsp+850h+var_820], eax
0x180012337  mov     r8d, 7FCh; Size
0x18001233d  call    memset_0
0x180012342  xor     r8d, r8d; pMalloc
0x180012345  mov     qword ptr [rdi], 0
0x18001234c  mov     rdx, rdi; ppvObject
0x18001234f  lea     rcx, _GUID_7279fc88_709d_4095_b63d_69fe4b0d9030; riid
0x180012356  call    cs:__imp_CreateXmlWriter
0x18001235d  nop     dword ptr [rax+rax+00h]
0x180012362  mov     ebx, eax
0x180012364  test    eax, eax
0x180012366  jz      short loc_18001238B
0x180012368  test    cs:byte_18002E903, 8
0x18001236f  jz      loc_1800124E0
0x180012375  xor     ecx, ecx
0x180012377  lea     rdx, aOpenxmlwriterF_2; "OpenXmlWriter: Failed to create IXmlWri"...
0x18001237e  mov     word ptr [rsp+850h+var_820], cx
0x180012383  mov     r8d, eax
0x180012386  jmp     loc_1800124B5
0x18001238b  mov     rcx, [rdi]
0x18001238e  mov     rdx, rsi
0x180012391  mov     rax, [rcx]
0x180012394  mov     rax, [rax+18h]
0x180012398  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001239d  mov     ebx, eax
0x18001239f  test    eax, eax
0x1800123a1  jz      short loc_1800123BC
0x1800123a3  test    cs:byte_18002E903, 8
0x1800123aa  jz      loc_1800124E0
0x1800123b0  lea     rdx, aOpenxmlwriterF_1; "OpenXmlWriter: Failed to set the output"...
0x1800123b7  jmp     loc_1800124AB
0x1800123bc  mov     rcx, [rdi]
0x1800123bf  mov     edx, 1
0x1800123c4  mov     r8d, edx
0x1800123c7  mov     rax, [rcx]
0x1800123ca  mov     rax, [rax+28h]
0x1800123ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800123d3  mov     ebx, eax
0x1800123d5  test    eax, eax
0x1800123d7  jz      short loc_1800123F2
0x1800123d9  test    cs:byte_18002E903, 8
0x1800123e0  jz      loc_1800124E0
0x1800123e6  lea     rdx, aOpenxmlwriterF; "OpenXmlWriter: Failed to set the XmlWri"...
0x1800123ed  jmp     loc_1800124AB
0x1800123f2  mov     rcx, [rdi]
0x1800123f5  mov     rax, [rcx]
0x1800123f8  mov     rax, [rax+0F8h]
0x1800123ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012404  mov     ebx, eax
0x180012406  test    eax, eax
0x180012408  jz      short loc_180012423
0x18001240a  test    cs:byte_18002E903, 8
0x180012411  jz      loc_1800124E0
0x180012417  lea     rdx, aOpenxmlwriterF_0; "OpenXmlWriter: Failed to flush the outp"...
0x18001241e  jmp     loc_1800124AB
0x180012423  mov     rcx, [rdi]
0x180012426  xor     edx, edx
0x180012428  mov     rax, [rcx]
0x18001242b  mov     rax, [rax+0D0h]
0x180012432  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012437  mov     ebx, eax
0x180012439  test    eax, eax
0x18001243b  jz      short loc_180012453
0x18001243d  test    cs:byte_18002E903, 8
0x180012444  jz      loc_1800124E0
0x18001244a  lea     rdx, aOpenxmlwriterW; "OpenXmlWriter: WriteStartDocument of IX"...
0x180012451  jmp     short loc_1800124AB
0x180012453  mov     rcx, [rdi]
0x180012456  lea     r8, aProxyconfig; "ProxyConfig"
0x18001245d  xor     r9d, r9d
0x180012460  xor     edx, edx
0x180012462  mov     rax, [rcx]
0x180012465  mov     rax, [rax+0D8h]
0x18001246c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012471  mov     ebx, eax
0x180012473  test    eax, eax
0x180012475  jnz     short loc_18001249B
0x180012477  mov     rcx, [rdi]
0x18001247a  lea     r8, aTenantgatewaym; "TenantGatewayMap"
0x180012481  xor     r9d, r9d
0x180012484  xor     edx, edx
0x180012486  mov     rax, [rcx]
0x180012489  mov     rax, [rax+0D8h]
0x180012490  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012495  mov     ebx, eax
0x180012497  test    eax, eax
0x180012499  jz      short loc_1800124E0
0x18001249b  test    cs:byte_18002E903, 8
0x1800124a2  jz      short loc_1800124E0
0x1800124a4  lea     rdx, aOpenxmlwriterW_0; "OpenXmlWriter: WriteStartElement of IXm"...
0x1800124ab  xor     eax, eax
0x1800124ad  mov     r8d, ebx
0x1800124b0  mov     word ptr [rsp+850h+var_820], ax
0x1800124b5  lea     rcx, [rsp+850h+var_820]
0x1800124ba  call    FormatRRASErrorString
0x1800124bf  test    cs:byte_18002E903, 8
0x1800124c6  jz      short loc_1800124E0
0x1800124c8  lea     r8, [rsp+850h+var_820]
0x1800124cd  lea     rdx, RasSSTPSvcTraceError
0x1800124d4  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800124db  call    McTemplateU0z_EventWriteTransfer
0x1800124e0  xor     eax, eax
0x1800124e2  test    ebx, ebx
0x1800124e4  jns     short loc_1800124F9
0x1800124e6  mov     eax, ebx
0x1800124e8  and     eax, 1FFF0000h
0x1800124ed  cmp     eax, 70000h
0x1800124f2  movzx   eax, bx
0x1800124f5  jz      short loc_1800124F9
0x1800124f7  mov     eax, ebx
0x1800124f9  mov     rcx, [rbp+750h+var_20]
0x180012500  xor     rcx, rsp; StackCookie
0x180012503  call    __security_check_cookie
0x180012508  mov     rbx, [rsp+850h+arg_10]
0x180012510  add     rsp, 840h
0x180012517  pop     rdi
0x180012518  pop     rsi
0x180012519  pop     rbp
0x18001251a  retn
```
