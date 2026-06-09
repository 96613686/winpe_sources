# CNodeFactory::XMLParser_Element_doc_assembly_trustInfo_security_requestedPrivileges_requestedExecutionLevel(ushort,_SXS_NODE_INFO const *)

- ea: `0x180051030`
- end: `0x1800515e5`
- name: `?XMLParser_Element_doc_assembly_trustInfo_security_requestedPrivileges_requestedExecutionLevel@CNodeFactory@@QEAAHGPEBU_SXS_NODE_INFO@@@Z`
- size: `1461`
- prototype: `__int64 __fastcall(CNodeFactory *__hidden this, unsigned __int16, const struct _SXS_NODE_INFO *)`
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800075a0`
- `0x18000a804`
- `0x18000df40`
- `0x18000dffc`
- `0x180020820`
- `0x180027160`
- `0x180051030`
- `0x1800515ec`
- `0x18005d38c`
- `0x180067548`
- `0x180067680`
- `0x18006a110`

## import_xrefs

- `ntdll!RtlCompareUnicodeString` at `0x1800511c2`
- `ntdll!RtlCompareUnicodeString` at `0x1800512e6`
- `ntdll!RtlCompareUnicodeString` at `0x1800511c2`
- `ntdll!RtlCompareUnicodeString` at `0x1800512e6`
- `ntdll!RtlPopFrame` at `0x1800513b8`
- `ntdll!RtlPopFrame` at `0x1800513b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800515cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800515cb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800510e2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180051219`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180051461`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180051519`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800510e2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180051219`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180051461`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180051519`

## string_xrefs

- `0x180051540`: `uiAccess`

## pseudocode

```c
__int64 __fastcall CNodeFactory::XMLParser_Element_doc_assembly_trustInfo_security_requestedPrivileges_requestedExecutionLevel(
        CNodeFactory *this,
        unsigned __int16 a2,
        const struct _SXS_NODE_INFO *a3)
{
  int v3; // edi
  int v5; // r15d
  __int64 v6; // rax
  int v7; // r12d
  __int64 v8; // rcx
  unsigned int i; // edi
  __int64 v10; // rdx
  WCHAR *v11; // rax
  __int64 v12; // rcx
  int v13; // eax
  __int64 v14; // rcx
  unsigned int j; // edi
  __int64 v16; // rdx
  WCHAR *v17; // rax
  unsigned int v18; // ebx
  __int16 v20; // ax
  char **v21; // rcx
  char **v22; // rcx
  __int16 v23; // ax
  DWORD LastError; // eax
  struct _UNICODE_STRING *v25; // [rsp+30h] [rbp-110h]
  struct _UNICODE_STRING *v26; // [rsp+30h] [rbp-110h]
  struct _UNICODE_STRING *v27; // [rsp+30h] [rbp-110h]
  struct _UNICODE_STRING *v28; // [rsp+38h] [rbp-108h]
  struct _UNICODE_STRING *v29; // [rsp+38h] [rbp-108h]
  struct _UNICODE_STRING *v30; // [rsp+38h] [rbp-108h]
  struct _UNICODE_STRING *v31; // [rsp+40h] [rbp-100h]
  struct _UNICODE_STRING *v32; // [rsp+40h] [rbp-100h]
  struct _UNICODE_STRING *v33; // [rsp+40h] [rbp-100h]
  struct _UNICODE_STRING *v34; // [rsp+48h] [rbp-F8h]
  struct _UNICODE_STRING *v35; // [rsp+48h] [rbp-F8h]
  struct _UNICODE_STRING *v36; // [rsp+48h] [rbp-F8h]
  const struct _UNICODE_STRING *v37; // [rsp+50h] [rbp-F0h]
  const struct _UNICODE_STRING *v38; // [rsp+58h] [rbp-E8h]
  const struct _UNICODE_STRING *v39; // [rsp+60h] [rbp-E0h]
  const struct _UNICODE_STRING *v40; // [rsp+68h] [rbp-D8h]
  const struct _UNICODE_STRING *v41; // [rsp+70h] [rbp-D0h]
  const struct _UNICODE_STRING *v42; // [rsp+78h] [rbp-C8h]
  const struct _UNICODE_STRING *v43; // [rsp+80h] [rbp-C0h]
  const struct _UNICODE_STRING *v44; // [rsp+88h] [rbp-B8h]
  const struct _UNICODE_STRING *v45; // [rsp+90h] [rbp-B0h]
  const struct _UNICODE_STRING *v46; // [rsp+98h] [rbp-A8h]
  const struct _UNICODE_STRING *v47; // [rsp+A0h] [rbp-A0h]
  const struct _UNICODE_STRING *v48; // [rsp+A8h] [rbp-98h]
  const struct _UNICODE_STRING *v49; // [rsp+B0h] [rbp-90h]
  char v50[8]; // [rsp+C0h] [rbp-80h] BYREF
  struct _UNICODE_STRING v51; // [rsp+C8h] [rbp-78h] BYREF
  UNICODE_STRING String2; // [rsp+D8h] [rbp-68h] BYREF
  UNICODE_STRING String1; // [rsp+E8h] [rbp-58h] BYREF
  int v54; // [rsp+F8h] [rbp-48h] BYREF
  struct _UNICODE_STRING v55; // [rsp+100h] [rbp-40h] BYREF
  __int64 v56; // [rsp+110h] [rbp-30h]
  __int64 *v57; // [rsp+118h] [rbp-28h]
  __int64 v58; // [rsp+120h] [rbp-20h]
  int v59; // [rsp+128h] [rbp-18h]
  int *v60; // [rsp+130h] [rbp-10h]
  struct _UNICODE_STRING v61; // [rsp+140h] [rbp+0h] BYREF
  WCHAR *v62; // [rsp+150h] [rbp+10h]
  __int64 v63; // [rsp+158h] [rbp+18h]
  __int64 v64; // [rsp+160h] [rbp+20h]
  char v65; // [rsp+168h] [rbp+28h] BYREF
  struct _UNICODE_STRING v66; // [rsp+1F0h] [rbp+B0h] BYREF
  WCHAR *v67; // [rsp+200h] [rbp+C0h]
  __int64 v68; // [rsp+208h] [rbp+C8h]
  __int64 v69; // [rsp+210h] [rbp+D0h]
  char v70; // [rsp+218h] [rbp+D8h] BYREF

  v3 = a2;
  v54 = 0;
  v57 = &qword_1800721C0;
  v56 = 0;
  v58 = 544438355;
  LODWORD(v55.Buffer) = 1;
  v5 = (int)a3;
  v59 = 3259;
  v60 = &v54;
  CFrame::BaseEnter((CFrame *)&v55.Buffer);
  CGenericStringBuffer<64,CUnicodeCharTraits>::CGenericStringBuffer<64,CUnicodeCharTraits>(&v66);
  CGenericStringBuffer<64,CUnicodeCharTraits>::CGenericStringBuffer<64,CUnicodeCharTraits>(&v61);
  v6 = *((_QWORD *)this + 49);
  *(_QWORD *)&v55.Length = 0;
  v50[0] = 0;
  if ( (*(_BYTE *)v6 & 4) == 0 )
  {
    CNodeFactory::LogParseError(
      this,
      0xC101004A,
      0x87u,
      0,
      0,
      0,
      v25,
      v28,
      v31,
      v34,
      v37,
      v38,
      v39,
      v40,
      v41,
      v42,
      v43,
      v44,
      v45,
      v46,
      v47,
      v48,
      v49);
    CFnTracerWin32::MarkWin32Failure((CFnTracerWin32 *)&v55.Buffer, 0x36B5u);
    v21 = off_180078D48;
LABEL_29:
    FusionpTraceWin32LastErrorFailureOrigination((const struct _CALL_SITE_INFO *)v21);
    goto LABEL_22;
  }
  if ( *(_DWORD *)(v6 + 128) )
  {
    CNodeFactory::LogParseError(
      this,
      0xC101004B,
      0x88u,
      0,
      0,
      0,
      v25,
      v28,
      v31,
      v34,
      v37,
      v38,
      v39,
      v40,
      v41,
      v42,
      v43,
      v44,
      v45,
      v46,
      v47,
      v48,
      v49);
    CFnTracerWin32::MarkWin32Failure((CFnTracerWin32 *)&v55.Buffer, 0x36B5u);
    v21 = off_180078D28;
    goto LABEL_29;
  }
  SetLastError(0);
  v7 = v3;
  if ( !(unsigned int)SxspGetAttributeValue(
                        1,
                        (unsigned int)qword_1800721A0,
                        v5,
                        v3,
                        (__int64)this + 400,
                        (__int64)v50,
                        168,
                        (__int64)&v66,
                        (__int64)&v55,
                        0) )
  {
    v22 = off_180078D08;
LABEL_34:
    *v60 = 0;
    FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)v22);
    goto LABEL_22;
  }
  if ( !v50[0] )
  {
    SetLastError(0x54Fu);
    *v60 = 0;
    goto LABEL_22;
  }
  v8 = v69;
  for ( i = 0; ; ++i )
  {
    if ( i >= 3 )
    {
      v51.Buffer = v67;
      v51.Length = 2 * v8;
      String1.Buffer = L"level";
      String2.Buffer = (PWSTR)*((_QWORD *)this + 52);
      v20 = *((_WORD *)this + 212);
      v51.MaximumLength = 2 * v8;
      String2.Length = 2 * v20;
      String2.MaximumLength = 2 * v20;
      *(_DWORD *)&String1.Length = 655370;
      CNodeFactory::LogParseError(
        this,
        0xC101003F,
        0x79u,
        &String2,
        &String1,
        &v51,
        v26,
        v29,
        v32,
        v35,
        v37,
        v38,
        v39,
        v40,
        v41,
        v42,
        v43,
        v44,
        v45,
        v46,
        v47,
        v48,
        v49);
      SetLastError(0x36B5u);
      v21 = off_180072200;
      *v60 = 0;
      goto LABEL_29;
    }
    v10 = (unsigned int)dword_180078DB0[6 * i];
    if ( v8 == v10 )
      break;
LABEL_10:
    ;
  }
  *(_QWORD *)&String1.Length = 0;
  String1.Buffer = v67;
  v11 = (&off_180078DA8)[3 * i];
  *(&String2.MaximumLength + 2) = 0;
  *(_QWORD *)&String1.Length = (unsigned __int16)(2 * v8);
  *(_DWORD *)&String1.MaximumLength = (unsigned __int16)(2 * v8);
  String2.Length = 2 * v10;
  *(_DWORD *)&String2.MaximumLength = (unsigned __int16)(2 * v10);
  String2.Buffer = v11;
  if ( RtlCompareUnicodeString(&String1, &String2, 1u) )
  {
    v8 = v69;
    goto LABEL_10;
  }
  v12 = *((_QWORD *)this + 49);
  v13 = dword_180078DA0[6 * i];
  v50[0] = 0;
  *(_DWORD *)(v12 + 128) = v13;
  *(_DWORD *)(*((_QWORD *)this + 2) + 4284LL) = dword_180078DA0[6 * i];
  SetLastError(0);
  if ( !(unsigned int)SxspGetAttributeValue(
                        0,
                        (unsigned int)qword_1800721E0,
                        v5,
                        v7,
                        (__int64)this + 400,
                        (__int64)v50,
                        168,
                        (__int64)&v61,
                        (__int64)&v55,
                        0) )
  {
    v22 = off_180078CE8;
    goto LABEL_34;
  }
  if ( v50[0] )
  {
    v14 = v64;
    for ( j = 0; j < 2; ++j )
    {
      v16 = (unsigned int)dword_180078D78[6 * j];
      if ( v14 == v16 )
      {
        *(_QWORD *)&String2.Length = 0;
        String2.Buffer = v62;
        v17 = (&off_180078D70)[3 * j];
        *(&String1.MaximumLength + 2) = 0;
        *(_QWORD *)&String2.Length = (unsigned __int16)(2 * v14);
        *(_DWORD *)&String2.MaximumLength = (unsigned __int16)(2 * v14);
        String1.Length = 2 * v16;
        *(_DWORD *)&String1.MaximumLength = (unsigned __int16)(2 * v16);
        String1.Buffer = v17;
        if ( !RtlCompareUnicodeString(&String2, &String1, 1u) )
        {
          *(_DWORD *)(*((_QWORD *)this + 49) + 132LL) = dword_180078D68[6 * j];
          *(_DWORD *)(*((_QWORD *)this + 2) + 4288LL) = dword_180078D68[6 * j];
          break;
        }
        v14 = v64;
      }
      if ( j == 1 )
      {
        String1.Buffer = v62;
        String1.Length = 2 * v14;
        String2.Buffer = L"uiAccess";
        v51.Buffer = (PWSTR)*((_QWORD *)this + 52);
        v23 = *((_WORD *)this + 212);
        String1.MaximumLength = 2 * v14;
        v51.Length = 2 * v23;
        v51.MaximumLength = 2 * v23;
        *(_DWORD *)&String2.Length = 1048592;
        CNodeFactory::LogParseError(
          this,
          0xC101003F,
          0x79u,
          &v51,
          &String2,
          &String1,
          v27,
          v30,
          v33,
          v36,
          v37,
          v38,
          v39,
          v40,
          v41,
          v42,
          v43,
          v44,
          v45,
          v46,
          v47,
          v48,
          v49);
        CFnTracerWin32::MarkWin32Failure((CFnTracerWin32 *)&v55.Buffer, 0x36B5u);
        v21 = off_180078CC8;
        goto LABEL_29;
      }
    }
  }
  v54 = 1;
LABEL_22:
  v18 = v54;
  *(_QWORD *)&v61.Length = &CGenericStringBuffer<64,CUnicodeCharTraits>::`vftable';
  if ( v62 != (WCHAR *)&v65 )
    CGenericStringBuffer<64,CUnicodeCharTraits>::DeallocateBuffer(&v61);
  v62 = 0;
  v63 = 0;
  *(_QWORD *)&v61.Length = &CGenericBaseStringBuffer<CUnicodeCharTraits>::`vftable';
  *(_QWORD *)&v66.Length = &CGenericStringBuffer<64,CUnicodeCharTraits>::`vftable';
  if ( v67 != (WCHAR *)&v70 )
    CGenericStringBuffer<64,CUnicodeCharTraits>::DeallocateBuffer(&v66);
  v67 = 0;
  v68 = 0;
  *(_QWORD *)&v66.Length = &CGenericBaseStringBuffer<CUnicodeCharTraits>::`vftable';
  if ( g_FusionEnterExitTracingEnabled )
  {
    if ( *v60 )
    {
      FusionpTraceCallSuccessfulExit(0);
    }
    else
    {
      LastError = GetLastError();
      FusionpTraceCallWin32UnsuccessfulExit(LastError, 0);
    }
  }
  RtlPopFrame((PTEB_ACTIVE_FRAME)&v55.Buffer);
  return v18;
}

```

## disassembly

```asm
0x180051030  mov     [rsp-8+arg_8], rbx
0x180051035  push    rbp
0x180051036  push    rsi
0x180051037  push    rdi
0x180051038  push    r12
0x18005103a  push    r13
0x18005103c  push    r14
0x18005103e  push    r15
0x180051040  lea     rbp, [rsp-170h]
0x180051048  sub     rsp, 2B0h
0x18005104f  mov     rax, cs:__security_cookie
0x180051056  xor     rax, rsp
0x180051059  mov     [rbp+1A0h+var_40], rax
0x180051060  xor     r13d, r13d
0x180051063  movzx   edi, dx
0x180051066  lea     rax, qword_1800721C0
0x18005106d  mov     [rbp+1A0h+var_1E8], r13d
0x180051071  mov     [rbp+1A0h+var_1C8], rax
0x180051075  mov     rbx, rcx
0x180051078  lea     rax, [rbp+1A0h+var_1E8]
0x18005107c  mov     [rbp+1A0h+var_1D0], r13
0x180051080  lea     esi, [r13+1]
0x180051084  mov     [rbp+1A0h+var_1C0], 20737853h
0x18005108c  lea     rcx, [rbp+1A0h+var_1E0.Buffer]; this
0x180051090  mov     dword ptr [rbp+1A0h+var_1E0.Buffer], esi
0x180051093  mov     r15, r8
0x180051096  mov     [rbp+1A0h+var_1B8], 0CBBh
0x18005109d  mov     [rbp+1A0h+var_1B0], rax
0x1800510a1  call    ?BaseEnter@CFrame@@QEAAXXZ; CFrame::BaseEnter(void)
0x1800510a6  lea     rcx, [rbp+1A0h+var_F0]
0x1800510ad  call    ??0?$CGenericStringBuffer@$0EA@VCUnicodeCharTraits@@@@QEAA@XZ; CGenericStringBuffer<64,CUnicodeCharTraits>::CGenericStringBuffer<64,CUnicodeCharTraits>(void)
0x1800510b2  lea     rcx, [rbp+1A0h+var_1A0]
0x1800510b6  call    ??0?$CGenericStringBuffer@$0EA@VCUnicodeCharTraits@@@@QEAA@XZ; CGenericStringBuffer<64,CUnicodeCharTraits>::CGenericStringBuffer<64,CUnicodeCharTraits>(void)
0x1800510bb  mov     rax, [rbx+188h]
0x1800510c2  mov     qword ptr [rbp+1A0h+var_1E0.Length], r13
0x1800510c6  mov     [rbp+1A0h+var_220], r13b
0x1800510ca  test    byte ptr [rax], 4
0x1800510cd  jz      loc_180051485
0x1800510d3  cmp     [rax+80h], r13d
0x1800510da  jnz     loc_1800514BC
0x1800510e0  xor     ecx, ecx; dwErrCode
0x1800510e2  call    cs:__imp_SetLastError
0x1800510e9  nop     dword ptr [rax+rax+00h]
0x1800510ee  mov     [rsp+2E0h+var_298], r13; struct _UNICODE_STRING *
0x1800510f3  lea     rax, [rbp+1A0h+var_1E0]
0x1800510f7  mov     [rsp+2E0h+var_2A0], rax; struct _UNICODE_STRING *
0x1800510fc  lea     r14, [rbx+190h]
0x180051103  lea     rax, [rbp+1A0h+var_F0]
0x18005110a  mov     r9d, edi
0x18005110d  mov     [rsp+2E0h+var_2A8], rax; struct _UNICODE_STRING *
0x180051112  lea     rdx, qword_1800721A0
0x180051119  lea     rax, [rbp+1A0h+var_220]
0x18005111d  mov     [rsp+2E0h+var_2B0], 0A8h; struct _UNICODE_STRING *
0x180051126  mov     [rsp+2E0h+var_2B8], rax
0x18005112b  mov     r8, r15
0x18005112e  mov     ecx, esi
0x180051130  mov     [rsp+2E0h+var_2C0], r14
0x180051135  mov     r12d, edi
0x180051138  call    ?SxspGetAttributeValue@@YAHKPEBU_ATTRIBUTE_NAME_DESCRIPTOR@@PEBU_SXS_NODE_INFO@@_KPEBU_ACTCTXCTB_PARSE_CONTEXT@@AEA_N2PEAXAEA_KP6AHKAEBV?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@4256@ZK@Z; SxspGetAttributeValue(ulong,_ATTRIBUTE_NAME_DESCRIPTOR const *,_SXS_NODE_INFO const *,unsigned __int64,_ACTCTXCTB_PARSE_CONTEXT const *,bool &,unsigned __int64,void *,unsigned __int64 &,int (*)(ulong,CGenericBaseStringBuffer<CUnicodeCharTraits> const &,bool &,unsigned __int64,void *,unsigned __int64 &),ulong)
0x18005113d  test    eax, eax
0x18005113f  jz      loc_1800514F3
0x180051145  cmp     [rbp+1A0h+var_220], r13b
0x180051149  jz      loc_180051514
0x18005114f  mov     rcx, [rbp+1A0h+var_D0]
0x180051156  lea     r8, __ImageBase
0x18005115d  mov     edi, r13d
0x180051160  cmp     edi, 3
0x180051163  jnb     loc_1800513F1
0x180051169  mov     eax, edi
0x18005116b  lea     rsi, [rax+rax*2]
0x18005116f  mov     edx, ds:rva dword_180078DB0[r8+rsi*8]
0x180051177  cmp     rcx, rdx
0x18005117a  jnz     short loc_1800511E0
0x18005117c  mov     rax, [rbp+1A0h+var_E0]
0x180051183  add     cx, cx
0x180051186  add     dx, dx
0x180051189  xorps   xmm0, xmm0
0x18005118c  movups  xmmword ptr [rbp+1A0h+String1.Length], xmm0
0x180051190  mov     [rbp+1A0h+String1.Buffer], rax
0x180051194  mov     rax, ds:rva off_180078DA8[r8+rsi*8]; "asInvoker" ...
0x18005119c  xorps   xmm1, xmm1
0x18005119f  movups  xmmword ptr [rbp+1A0h+String2.Length], xmm1
0x1800511a3  mov     [rbp+1A0h+String1.Length], cx
0x1800511a7  mov     r8b, 1; CaseInsensitive
0x1800511aa  mov     [rbp+1A0h+String1.MaximumLength], cx
0x1800511ae  lea     rcx, [rbp+1A0h+String1]; String1
0x1800511b2  mov     [rbp+1A0h+String2.Length], dx
0x1800511b6  mov     [rbp+1A0h+String2.MaximumLength], dx
0x1800511ba  lea     rdx, [rbp+1A0h+String2]; String2
0x1800511be  mov     [rbp+1A0h+String2.Buffer], rax
0x1800511c2  call    cs:__imp_RtlCompareUnicodeString
0x1800511c9  nop     dword ptr [rax+rax+00h]
0x1800511ce  test    eax, eax
0x1800511d0  jz      short loc_1800511E7
0x1800511d2  mov     rcx, [rbp+1A0h+var_D0]
0x1800511d9  lea     r8, __ImageBase
0x1800511e0  inc     edi
0x1800511e2  jmp     loc_180051160
0x1800511e7  mov     rcx, [rbx+188h]
0x1800511ee  lea     rdx, __ImageBase
0x1800511f5  mov     eax, ds:rva dword_180078DA0[rdx+rsi*8]
0x1800511fc  mov     [rbp+1A0h+var_220], r13b
0x180051200  mov     [rcx+80h], eax
0x180051206  mov     rcx, [rbx+10h]
0x18005120a  mov     eax, ds:rva dword_180078DA0[rdx+rsi*8]
0x180051211  mov     [rcx+10BCh], eax
0x180051217  xor     ecx, ecx; dwErrCode
0x180051219  call    cs:__imp_SetLastError
0x180051220  nop     dword ptr [rax+rax+00h]
0x180051225  mov     [rsp+2E0h+var_298], r13; struct _UNICODE_STRING *
0x18005122a  lea     rax, [rbp+1A0h+var_1E0]
0x18005122e  mov     [rsp+2E0h+var_2A0], rax; struct _UNICODE_STRING *
0x180051233  lea     rdx, qword_1800721E0
0x18005123a  lea     rax, [rbp+1A0h+var_1A0]
0x18005123e  mov     r9, r12
0x180051241  mov     [rsp+2E0h+var_2A8], rax; struct _UNICODE_STRING *
0x180051246  mov     r8, r15
0x180051249  lea     rax, [rbp+1A0h+var_220]
0x18005124d  mov     [rsp+2E0h+var_2B0], 0A8h; struct _UNICODE_STRING *
0x180051256  mov     [rsp+2E0h+var_2B8], rax
0x18005125b  xor     ecx, ecx
0x18005125d  mov     [rsp+2E0h+var_2C0], r14
0x180051262  call    ?SxspGetAttributeValue@@YAHKPEBU_ATTRIBUTE_NAME_DESCRIPTOR@@PEBU_SXS_NODE_INFO@@_KPEBU_ACTCTXCTB_PARSE_CONTEXT@@AEA_N2PEAXAEA_KP6AHKAEBV?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@4256@ZK@Z; SxspGetAttributeValue(ulong,_ATTRIBUTE_NAME_DESCRIPTOR const *,_SXS_NODE_INFO const *,unsigned __int64,_ACTCTXCTB_PARSE_CONTEXT const *,bool &,unsigned __int64,void *,unsigned __int64 &,int (*)(ulong,CGenericBaseStringBuffer<CUnicodeCharTraits> const &,bool &,unsigned __int64,void *,unsigned __int64 &),ulong)
0x180051267  test    eax, eax
0x180051269  jz      loc_1800514FC
0x18005126f  cmp     [rbp+1A0h+var_220], r13b
0x180051273  jz      loc_18005132E
0x180051279  mov     rcx, [rbp+1A0h+var_180]
0x18005127d  lea     r14, __ImageBase
0x180051284  mov     edi, r13d
0x180051287  cmp     edi, 2
0x18005128a  jnb     loc_18005132E
0x180051290  mov     eax, edi
0x180051292  lea     rsi, [rax+rax*2]
0x180051296  mov     edx, ds:rva dword_180078D78[r14+rsi*8]
0x18005129e  cmp     rcx, rdx
0x1800512a1  jnz     short loc_1800512FA
0x1800512a3  mov     rax, [rbp+1A0h+var_190]
0x1800512a7  add     cx, cx
0x1800512aa  add     dx, dx
0x1800512ad  xorps   xmm0, xmm0
0x1800512b0  movups  xmmword ptr [rbp+1A0h+String2.Length], xmm0
0x1800512b4  mov     [rbp+1A0h+String2.Buffer], rax
0x1800512b8  mov     r8b, 1; CaseInsensitive
0x1800512bb  mov     rax, ds:rva off_180078D70[r14+rsi*8]; "TRUE" ...
0x1800512c3  xorps   xmm1, xmm1
0x1800512c6  movups  xmmword ptr [rbp+1A0h+String1.Length], xmm1
0x1800512ca  mov     [rbp+1A0h+String2.Length], cx
0x1800512ce  mov     [rbp+1A0h+String2.MaximumLength], cx
0x1800512d2  lea     rcx, [rbp+1A0h+String2]; String1
0x1800512d6  mov     [rbp+1A0h+String1.Length], dx
0x1800512da  mov     [rbp+1A0h+String1.MaximumLength], dx
0x1800512de  lea     rdx, [rbp+1A0h+String1]; String2
0x1800512e2  mov     [rbp+1A0h+String1.Buffer], rax
0x1800512e6  call    cs:__imp_RtlCompareUnicodeString
0x1800512ed  nop     dword ptr [rax+rax+00h]
0x1800512f2  test    eax, eax
0x1800512f4  jz      short loc_180051307
0x1800512f6  mov     rcx, [rbp+1A0h+var_180]
0x1800512fa  cmp     edi, 1
0x1800512fd  jz      loc_180051531
0x180051303  inc     edi
0x180051305  jmp     short loc_180051287
0x180051307  mov     rcx, [rbx+188h]
0x18005130e  mov     eax, ds:rva dword_180078D68[r14+rsi*8]
0x180051316  mov     [rcx+84h], eax
0x18005131c  mov     rcx, [rbx+10h]
0x180051320  mov     eax, ds:rva dword_180078D68[r14+rsi*8]
0x180051328  mov     [rcx+10C0h], eax
0x18005132e  mov     [rbp+1A0h+var_1E8], 1
0x180051335  mov     rdx, [rbp+1A0h+var_190]
0x180051339  lea     rax, [rbp+1A0h+var_178]
0x18005133d  mov     ebx, [rbp+1A0h+var_1E8]
0x180051340  lea     rsi, ??_7?$CGenericStringBuffer@$0EA@VCUnicodeCharTraits@@@@6B@; const CGenericStringBuffer<64,CUnicodeCharTraits>::`vftable'
0x180051347  mov     qword ptr [rbp+1A0h+var_1A0.Length], rsi
0x18005134b  cmp     rdx, rax
0x18005134e  jz      short loc_180051359
0x180051350  lea     rcx, [rbp+1A0h+var_1A0]
0x180051354  call    ?DeallocateBuffer@?$CGenericStringBuffer@$0EA@VCUnicodeCharTraits@@@@MEBAXPEAG@Z; CGenericStringBuffer<64,CUnicodeCharTraits>::DeallocateBuffer(ushort *)
0x180051359  mov     rdx, [rbp+1A0h+var_E0]
0x180051360  lea     rax, [rbp+1A0h+var_C8]
0x180051367  mov     [rbp+1A0h+var_190], r13
0x18005136b  lea     rdi, ??_7?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@6B@; const CGenericBaseStringBuffer<CUnicodeCharTraits>::`vftable'
0x180051372  mov     [rbp+1A0h+var_188], r13
0x180051376  mov     qword ptr [rbp+1A0h+var_1A0.Length], rdi
0x18005137a  mov     qword ptr [rbp+1A0h+var_F0.Length], rsi
0x180051381  cmp     rdx, rax
0x180051384  jz      short loc_180051392
0x180051386  lea     rcx, [rbp+1A0h+var_F0]
0x18005138d  call    ?DeallocateBuffer@?$CGenericStringBuffer@$0EA@VCUnicodeCharTraits@@@@MEBAXPEAG@Z; CGenericStringBuffer<64,CUnicodeCharTraits>::DeallocateBuffer(ushort *)
0x180051392  cmp     cs:g_FusionEnterExitTracingEnabled, r13b
0x180051399  mov     [rbp+1A0h+var_E0], r13
0x1800513a0  mov     [rbp+1A0h+var_D8], r13
0x1800513a7  mov     qword ptr [rbp+1A0h+var_F0.Length], rdi
0x1800513ae  jnz     loc_1800515B6
0x1800513b4  lea     rcx, [rbp+1A0h+var_1E0.Buffer]; Frame
0x1800513b8  call    cs:__imp_RtlPopFrame
0x1800513bf  nop     dword ptr [rax+rax+00h]
0x1800513c4  mov     eax, ebx
0x1800513c6  mov     rcx, [rbp+1A0h+var_40]
0x1800513cd  xor     rcx, rsp; StackCookie
0x1800513d0  call    __security_check_cookie
0x1800513d5  mov     rbx, [rsp+2E0h+arg_8]
0x1800513dd  add     rsp, 2B0h
0x1800513e4  pop     r15
0x1800513e6  pop     r14
0x1800513e8  pop     r13
0x1800513ea  pop     r12
0x1800513ec  pop     rdi
0x1800513ed  pop     rsi
0x1800513ee  pop     rbp
0x1800513ef  retn
0x1800513f1  mov     rax, [rbp+1A0h+var_E0]
0x1800513f8  lea     r9, [rbp+1A0h+String2]; struct _UNICODE_STRING *
0x1800513fc  mov     [rbp+1A0h+var_218.Buffer], rax
0x180051400  add     cx, cx
0x180051403  lea     rax, aLevel; "level"
0x18005140a  mov     [rbp+1A0h+var_218.Length], cx
0x18005140e  mov     [rbp+1A0h+String1.Buffer], rax
0x180051412  mov     edx, 0C101003Fh; unsigned int
0x180051417  mov     rax, [r14+10h]
0x18005141b  mov     r8d, 79h ; 'y'; unsigned int
0x180051421  mov     [rbp+1A0h+String2.Buffer], rax
0x180051425  movzx   eax, word ptr [rbx+1A8h]
0x18005142c  add     ax, ax
0x18005142f  mov     [rbp+1A0h+var_218.MaximumLength], cx
0x180051433  mov     [rbp+1A0h+String2.Length], ax
0x180051437  mov     rcx, rbx; this
0x18005143a  mov     [rbp+1A0h+String2.MaximumLength], ax
0x18005143e  lea     rax, [rbp+1A0h+var_218]
0x180051442  mov     [rsp+2E0h+var_2B8], rax; struct _UNICODE_STRING *
0x180051447  lea     rax, [rbp+1A0h+String1]
0x18005144b  mov     [rsp+2E0h+var_2C0], rax; struct _UNICODE_STRING *
0x180051450  mov     dword ptr [rbp+1A0h+String1.Length], 0A000Ah
0x180051457  call    ?LogParseError@CNodeFactory@@QEAAJKKPEBU_UNICODE_STRING@@0000000000000000000@Z; CNodeFactory::LogParseError(ulong,ulong,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *)
0x18005145c  mov     ecx, 36B5h; dwErrCode
0x180051461  call    cs:__imp_SetLastError
0x180051468  nop     dword ptr [rax+rax+00h]
0x18005146d  mov     rax, [rbp+1A0h+var_1B0]
0x180051471  lea     rcx, off_180072200; struct _CALL_SITE_INFO *
0x180051478  mov     [rax], r13d
0x18005147b  call    ?FusionpTraceWin32LastErrorFailureOrigination@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailureOrigination(_CALL_SITE_INFO const &)
0x180051480  jmp     loc_180051335
0x180051485  mov     [rsp+2E0h+var_2B8], r13; struct _UNICODE_STRING *
0x18005148a  xor     r9d, r9d; struct _UNICODE_STRING *
0x18005148d  mov     edx, 0C101004Ah; unsigned int
0x180051492  mov     [rsp+2E0h+var_2C0], r13; struct _UNICODE_STRING *
0x180051497  mov     r8d, 87h; unsigned int
0x18005149d  mov     rcx, rbx; this
0x1800514a0  call    ?LogParseError@CNodeFactory@@QEAAJKKPEBU_UNICODE_STRING@@0000000000000000000@Z; CNodeFactory::LogParseError(ulong,ulong,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *)
0x1800514a5  mov     edx, 36B5h; unsigned int
0x1800514aa  lea     rcx, [rbp+1A0h+var_1E0.Buffer]; this
0x1800514ae  call    ?MarkWin32Failure@CFnTracerWin32@@QEAAXK@Z; CFnTracerWin32::MarkWin32Failure(ulong)
0x1800514b3  lea     rcx, off_180078D48; "clientcore\\base\\win32\\fusion\\sxs\\n"...
0x1800514ba  jmp     short loc_18005147B
0x1800514bc  mov     [rsp+2E0h+var_2B8], r13; struct _UNICODE_STRING *
0x1800514c1  xor     r9d, r9d; struct _UNICODE_STRING *
0x1800514c4  mov     edx, 0C101004Bh; unsigned int
0x1800514c9  mov     [rsp+2E0h+var_2C0], r13; struct _UNICODE_STRING *
0x1800514ce  mov     r8d, 88h; unsigned int
0x1800514d4  mov     rcx, rbx; this
0x1800514d7  call    ?LogParseError@CNodeFactory@@QEAAJKKPEBU_UNICODE_STRING@@0000000000000000000@Z; CNodeFactory::LogParseError(ulong,ulong,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *)
0x1800514dc  mov     edx, 36B5h; unsigned int
0x1800514e1  lea     rcx, [rbp+1A0h+var_1E0.Buffer]; this
0x1800514e5  call    ?MarkWin32Failure@CFnTracerWin32@@QEAAXK@Z; CFnTracerWin32::MarkWin32Failure(ulong)
0x1800514ea  lea     rcx, off_180078D28; "clientcore\\base\\win32\\fusion\\sxs\\n"...
0x1800514f1  jmp     short loc_18005147B
0x1800514f3  lea     rcx, off_180078D08; "clientcore\\base\\win32\\fusion\\sxs\\n"...
0x1800514fa  jmp     short loc_180051503
0x1800514fc  lea     rcx, off_180078CE8; struct _CALL_SITE_INFO *
0x180051503  mov     rax, [rbp+1A0h+var_1B0]
0x180051507  mov     [rax], r13d
0x18005150a  call    ?FusionpTraceWin32LastErrorFailure@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailure(_CALL_SITE_INFO const &)
0x18005150f  jmp     loc_180051335
0x180051514  mov     ecx, 54Fh; dwErrCode
0x180051519  call    cs:__imp_SetLastError
0x180051520  nop     dword ptr [rax+rax+00h]
0x180051525  mov     rax, [rbp+1A0h+var_1B0]
0x180051529  mov     [rax], r13d
0x18005152c  jmp     loc_180051335
0x180051531  mov     rax, [rbp+1A0h+var_190]
0x180051535  lea     r9, [rbp+1A0h+var_218]; struct _UNICODE_STRING *
0x180051539  mov     [rbp+1A0h+String1.Buffer], rax
0x18005153d  add     cx, cx
0x180051540  lea     rax, aUiaccess; "uiAccess"
0x180051547  mov     [rbp+1A0h+String1.Length], cx
0x18005154b  mov     [rbp+1A0h+String2.Buffer], rax
0x18005154f  mov     edx, 0C101003Fh; unsigned int
0x180051554  mov     rax, [rbx+1A0h]
0x18005155b  mov     r8d, 79h ; 'y'; unsigned int
0x180051561  mov     [rbp+1A0h+var_218.Buffer], rax
0x180051565  movzx   eax, word ptr [rbx+1A8h]
0x18005156c  add     ax, ax
0x18005156f  mov     [rbp+1A0h+String1.MaximumLength], cx
0x180051573  mov     [rbp+1A0h+var_218.Length], ax
0x180051577  mov     rcx, rbx; this
0x18005157a  mov     [rbp+1A0h+var_218.MaximumLength], ax
0x18005157e  lea     rax, [rbp+1A0h+String1]
0x180051582  mov     [rsp+2E0h+var_2B8], rax; struct _UNICODE_STRING *
0x180051587  lea     rax, [rbp+1A0h+String2]
  ... truncated ...
```
