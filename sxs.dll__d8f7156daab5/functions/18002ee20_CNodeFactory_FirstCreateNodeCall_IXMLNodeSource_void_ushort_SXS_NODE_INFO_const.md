# CNodeFactory::FirstCreateNodeCall(IXMLNodeSource *,void *,ushort,_SXS_NODE_INFO const *)

- ea: `0x18002ee20`
- end: `0x18002f280`
- name: `?FirstCreateNodeCall@CNodeFactory@@QEAAJPEAUIXMLNodeSource@@PEAXGPEBU_SXS_NODE_INFO@@@Z`
- size: `1120`
- prototype: `__int64 __usercall@<rax>(CNodeFactory *__hidden this@<rcx>, struct IXMLNodeSource *@<rdx>, void *@<r8>, unsigned __int16@<r9w>, const struct _SXS_NODE_INFO *)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180031260`

## callees

- `0x18000a804`
- `0x18000df40`
- `0x18000dffc`
- `0x180027160`
- `0x18002e98c`
- `0x18002ee20`
- `0x18002ff90`
- `0x180030148`
- `0x180030820`
- `0x18004d2d0`
- `0x1800515ec`
- `0x18005bf78`
- `0x18005cc58`
- `0x18006a110`

## import_xrefs

- `ntdll!RtlCompareUnicodeString` at `0x18002f024`
- `ntdll!RtlCompareUnicodeString` at `0x18002f024`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002ef0b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002f056`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002f105`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002f16a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002f1c4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002ef0b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002f056`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002f105`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002f16a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002f1c4`

## string_xrefs

- `0x18002f086`: `manifestVersion`
- `0x18002f141`: `configuration`

## pseudocode

```c
__int64 __fastcall CNodeFactory::FirstCreateNodeCall(
        CNodeFactory *this,
        struct IXMLNodeSource *a2,
        void *a3,
        unsigned __int16 a4,
        const struct _SXS_NODE_INFO *a5)
{
  unsigned __int64 v6; // r13
  char v7; // r12
  char v8; // r15
  __int64 i; // r14
  __int64 v10; // rbx
  unsigned int v11; // ebx
  unsigned int v13; // edx
  unsigned int v14; // r8d
  __int64 v15; // rax
  unsigned int v16; // edx
  unsigned int v17; // r8d
  int v18; // ebx
  struct _UNICODE_STRING *v19; // [rsp+30h] [rbp-110h]
  struct _UNICODE_STRING *v20; // [rsp+30h] [rbp-110h]
  struct _UNICODE_STRING *v21; // [rsp+38h] [rbp-108h]
  struct _UNICODE_STRING *v22; // [rsp+38h] [rbp-108h]
  struct _UNICODE_STRING *v23; // [rsp+40h] [rbp-100h]
  struct _UNICODE_STRING *v24; // [rsp+40h] [rbp-100h]
  struct _UNICODE_STRING *v25; // [rsp+48h] [rbp-F8h]
  struct _UNICODE_STRING *v26; // [rsp+48h] [rbp-F8h]
  const struct _UNICODE_STRING *v27; // [rsp+50h] [rbp-F0h]
  const struct _UNICODE_STRING *v28; // [rsp+58h] [rbp-E8h]
  const struct _UNICODE_STRING *v29; // [rsp+60h] [rbp-E0h]
  const struct _UNICODE_STRING *v30; // [rsp+68h] [rbp-D8h]
  const struct _UNICODE_STRING *v31; // [rsp+70h] [rbp-D0h]
  const struct _UNICODE_STRING *v32; // [rsp+78h] [rbp-C8h]
  const struct _UNICODE_STRING *v33; // [rsp+80h] [rbp-C0h]
  const struct _UNICODE_STRING *v34; // [rsp+88h] [rbp-B8h]
  const struct _UNICODE_STRING *v35; // [rsp+90h] [rbp-B0h]
  const struct _UNICODE_STRING *v36; // [rsp+98h] [rbp-A8h]
  const struct _UNICODE_STRING *v37; // [rsp+A0h] [rbp-A0h]
  const struct _UNICODE_STRING *v38; // [rsp+A8h] [rbp-98h]
  const struct _UNICODE_STRING *v39; // [rsp+B0h] [rbp-90h]
  _BYTE v40[8]; // [rsp+C0h] [rbp-80h] BYREF
  UNICODE_STRING String2; // [rsp+C8h] [rbp-78h] BYREF
  UNICODE_STRING String1; // [rsp+D8h] [rbp-68h] BYREF
  struct _UNICODE_STRING v43; // [rsp+E8h] [rbp-58h] BYREF
  __int64 v44; // [rsp+F8h] [rbp-48h]
  __int64 *v45; // [rsp+100h] [rbp-40h]
  __int64 v46; // [rsp+108h] [rbp-38h]
  int v47; // [rsp+110h] [rbp-30h]
  int *v48; // [rsp+118h] [rbp-28h]
  struct _UNICODE_STRING v49; // [rsp+120h] [rbp-20h] BYREF

  v45 = &qword_18006E1C8;
  v6 = a4;
  v48 = (int *)(&v43.MaximumLength + 1);
  *(_DWORD *)(&v43.MaximumLength + 1) = -1;
  LODWORD(v43.Buffer) = 1;
  v44 = 0;
  v46 = 544438355;
  v47 = 1489;
  CFrame::BaseEnter((CFrame *)&v43.Buffer);
  v7 = 0;
  *(_QWORD *)&v49.Length = 0;
  v8 = 0;
  LOBYTE(v43.Length) = 0;
  v40[0] = 0;
  for ( i = 0; (unsigned int)i < (unsigned int)v6; i = (unsigned int)(i + 1) )
  {
    v10 = 192 * i;
    if ( *((_DWORD *)a5 + 48 * i + 1) != 1 )
    {
      if ( *(_DWORD *)((char *)a5 + v10 + 4) == 2
        && !*(_QWORD *)((char *)a5 + v10 + 40)
        && FusionpEqualStrings(
             *(const unsigned __int16 **)((char *)a5 + v10 + 176),
             *(_QWORD *)((char *)a5 + v10 + 184),
             L"manifestVersion",
             0xFu,
             0) )
      {
        v15 = (unsigned int)(i + 1);
        v7 = 1;
        if ( (unsigned int)v15 < (unsigned int)v6
          && *((_DWORD *)a5 + 48 * v15 + 1) == 13
          && FusionpEqualStrings(
               *((const unsigned __int16 **)a5 + 24 * v15 + 22),
               *((_QWORD *)a5 + 24 * v15 + 23),
               L"1.0",
               3u,
               0) )
        {
          v8 = 1;
        }
      }
      continue;
    }
    if ( (_DWORD)i )
      goto LABEL_29;
    if ( *((_DWORD *)this + 94) == 1 || *((_DWORD *)this + 94) == 2 )
    {
      if ( SxspIsNamespaceInAsmEquivalenceSet(*(WCHAR **)((char *)a5 + v10 + 24), *(_QWORD *)((char *)a5 + v10 + 40))
        && *(_QWORD *)((char *)a5 + v10 + 184) == 8 )
      {
        String1.Buffer = *(PWSTR *)((char *)a5 + v10 + 176);
        *(_QWORD *)&String1.Length = 1048592;
        String2.Buffer = L"assembly";
        *(_QWORD *)&String2.Length = 1048592;
        if ( !RtlCompareUnicodeString(&String1, &String2, 0) )
          continue;
      }
      SetLastError(0);
      v16 = -1056899063;
      v17 = 124;
    }
    else
    {
      if ( *((_DWORD *)this + 94) != 3 )
      {
LABEL_29:
        *v48 = -2147023537;
        goto LABEL_10;
      }
      if ( !*(_QWORD *)((char *)a5 + v10 + 40)
        && FusionpEqualStrings(
             *(const unsigned __int16 **)((char *)a5 + v10 + 176),
             *(_QWORD *)((char *)a5 + v10 + 184),
             L"configuration",
             0xDu,
             0) )
      {
        continue;
      }
      SetLastError(0);
      v16 = -1056899062;
      v17 = 144;
    }
    v18 = CNodeFactory::LogParseError(
            this,
            v16,
            v17,
            0,
            0,
            0,
            v19,
            v21,
            v23,
            v25,
            v27,
            v28,
            v29,
            v30,
            v31,
            v32,
            v33,
            v34,
            v35,
            v36,
            v37,
            v38,
            v39);
    if ( v18 < 0 )
      goto LABEL_35;
  }
  if ( (unsigned int)(*((_DWORD *)this + 94) - 1) > 1 )
    goto LABEL_7;
  if ( !v7 )
  {
    SetLastError(0);
    v13 = -1056899061;
    v14 = 126;
    goto LABEL_37;
  }
  if ( !v8 )
  {
    SetLastError(0);
    v13 = -1056899060;
    v14 = 125;
LABEL_37:
    v18 = CNodeFactory::LogParseError(
            this,
            v13,
            v14,
            0,
            0,
            0,
            v19,
            v21,
            v23,
            v25,
            v27,
            v28,
            v29,
            v30,
            v31,
            v32,
            v33,
            v34,
            v35,
            v36,
            v37,
            v38,
            v39);
    if ( v18 < 0 )
    {
LABEL_35:
      FusionpTraceCOMFailure(v18, byte_18008517D);
      CFnTracerHR::MarkCOMFailure((CFnTracerHR *)&v43.Buffer, v18);
      goto LABEL_10;
    }
  }
LABEL_7:
  *(_DWORD *)(*((_QWORD *)this + 3) + 860LL) = 1;
  *(_DWORD *)(*((_QWORD *)this + 3) + 864LL) = 0;
  SetLastError(0);
  if ( (unsigned int)SxspGetAttributeValue(
                       0,
                       (WCHAR **)qword_18006F850,
                       (__int64)a5,
                       v6,
                       (__int64)this + 400,
                       v40,
                       1,
                       (__int64)&v43,
                       &v49,
                       (unsigned int (__fastcall *)(_QWORD, void ***, char *, __int64, __int64, _QWORD *))SxspValidateBoolAttribute) )
  {
    if ( v40[0] && LOBYTE(v43.Length) && (**((_BYTE **)this + 49) & 8) != 0 )
    {
      CNodeFactory::LogParseError(
        this,
        0xC101004D,
        0x96u,
        0,
        0,
        0,
        v20,
        v22,
        v24,
        v26,
        v27,
        v28,
        v29,
        v30,
        v31,
        v32,
        v33,
        v34,
        v35,
        v36,
        v37,
        v38,
        v39);
      *v48 = -2147010895;
      FusionpConvertCOMFailure(v48);
      FusionpTraceWin32LastErrorFailureOrigination((const struct _CALL_SITE_INFO *)off_180079548);
    }
    else
    {
      *v48 = 0;
    }
  }
  else
  {
    CFnTracerHR::MarkWin32LastErrorFailure((CFnTracerHR *)&v43.Buffer);
    FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_180079568);
  }
LABEL_10:
  v11 = *v48;
  CFnTracerHR::~CFnTracerHR((CFnTracerHR *)&v43.Buffer);
  return v11;
}

```

## disassembly

```asm
0x18002ee20  push    rbp
0x18002ee22  push    rbx
0x18002ee23  push    rsi
0x18002ee24  push    rdi
0x18002ee25  push    r12
0x18002ee27  push    r13
0x18002ee29  push    r14
0x18002ee2b  push    r15
0x18002ee2d  lea     rbp, [rsp+8]
0x18002ee32  sub     rsp, 138h
0x18002ee39  mov     rax, cs:__security_cookie
0x18002ee40  xor     rax, rsp
0x18002ee43  mov     [rbp+30h+var_50.Buffer], rax
0x18002ee47  mov     rsi, [rbp+30h+arg_20]
0x18002ee4b  lea     rax, qword_18006E1C8
0x18002ee52  mov     [rbp+30h+var_70], rax
0x18002ee56  mov     rdi, rcx
0x18002ee59  lea     rax, [rbp+30h+var_88+4]
0x18002ee5d  movzx   r13d, r9w
0x18002ee61  lea     rcx, [rbp+30h+var_88.Buffer]; this
0x18002ee65  mov     [rbp+30h+var_58], rax
0x18002ee69  mov     dword ptr [rbp+30h+var_88+4], 0FFFFFFFFh
0x18002ee70  mov     dword ptr [rbp+30h+var_88.Buffer], 1
0x18002ee77  mov     [rbp+30h+var_78], 0
0x18002ee7f  mov     [rbp+30h+var_68], 20737853h
0x18002ee87  mov     [rbp+30h+var_60], 5D1h
0x18002ee8e  call    ?BaseEnter@CFrame@@QEAAXXZ; CFrame::BaseEnter(void)
0x18002ee93  xor     r12b, r12b
0x18002ee96  mov     qword ptr [rbp+30h+var_50.Length], 0
0x18002ee9e  xor     r15b, r15b
0x18002eea1  mov     byte ptr [rbp+30h+var_88.Length], r12b
0x18002eea5  mov     [rbp+30h+var_B0], r12b
0x18002eea9  xor     r14d, r14d
0x18002eeac  cmp     r14d, r13d
0x18002eeaf  jnb     short loc_18002EED8
0x18002eeb1  lea     rbx, [r14+r14*2]
0x18002eeb5  mov     eax, 1
0x18002eeba  shl     rbx, 6
0x18002eebe  cmp     [rbx+rsi+4], eax
0x18002eec2  jz      loc_18002EFB1
0x18002eec8  cmp     dword ptr [rbx+rsi+4], 2
0x18002eecd  jz      loc_18002F072
0x18002eed3  add     r14d, eax
0x18002eed6  jmp     short loc_18002EEAC
0x18002eed8  mov     eax, [rdi+178h]
0x18002eede  mov     r14d, 1
0x18002eee4  sub     eax, r14d
0x18002eee7  cmp     eax, r14d
0x18002eeea  jbe     loc_18002F042
0x18002eef0  mov     rax, [rdi+18h]
0x18002eef4  xor     ecx, ecx; dwErrCode
0x18002eef6  mov     [rax+35Ch], r14d
0x18002eefd  mov     rax, [rdi+18h]
0x18002ef01  mov     dword ptr [rax+360h], 0
0x18002ef0b  call    cs:__imp_SetLastError
0x18002ef12  nop     dword ptr [rax+rax+00h]
0x18002ef17  lea     rcx, ?SxspValidateBoolAttribute@@YAHKAEBV?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@AEA_N_KPEAXAEA_K@Z; SxspValidateBoolAttribute(ulong,CGenericBaseStringBuffer<CUnicodeCharTraits> const &,bool &,unsigned __int64,void *,unsigned __int64 &)
0x18002ef1e  mov     r9, r13
0x18002ef21  mov     [rsp+170h+var_128], rcx; struct _UNICODE_STRING *
0x18002ef26  lea     rax, [rdi+190h]
0x18002ef2d  lea     rcx, [rbp+30h+var_50]
0x18002ef31  mov     r8, rsi
0x18002ef34  mov     [rsp+170h+var_130], rcx; struct _UNICODE_STRING *
0x18002ef39  lea     rdx, qword_18006F850
0x18002ef40  lea     rcx, [rbp+30h+var_88]
0x18002ef44  mov     [rsp+170h+var_138], rcx; struct _UNICODE_STRING *
0x18002ef49  lea     rcx, [rbp+30h+var_B0]
0x18002ef4d  mov     [rsp+170h+var_140], r14; struct _UNICODE_STRING *
0x18002ef52  mov     [rsp+170h+var_148], rcx
0x18002ef57  xor     ecx, ecx
0x18002ef59  mov     [rsp+170h+var_150], rax
0x18002ef5e  call    ?SxspGetAttributeValue@@YAHKPEBU_ATTRIBUTE_NAME_DESCRIPTOR@@PEBU_SXS_NODE_INFO@@_KPEBU_ACTCTXCTB_PARSE_CONTEXT@@AEA_N2PEAXAEA_KP6AHKAEBV?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@4256@ZK@Z; SxspGetAttributeValue(ulong,_ATTRIBUTE_NAME_DESCRIPTOR const *,_SXS_NODE_INFO const *,unsigned __int64,_ACTCTXCTB_PARSE_CONTEXT const *,bool &,unsigned __int64,void *,unsigned __int64 &,int (*)(ulong,CGenericBaseStringBuffer<CUnicodeCharTraits> const &,bool &,unsigned __int64,void *,unsigned __int64 &),ulong)
0x18002ef63  test    eax, eax
0x18002ef65  jz      loc_18002F200
0x18002ef6b  cmp     [rbp+30h+var_B0], 0
0x18002ef6f  jnz     loc_18002F21A
0x18002ef75  mov     rax, [rbp+30h+var_58]
0x18002ef79  mov     dword ptr [rax], 0
0x18002ef7f  mov     rax, [rbp+30h+var_58]
0x18002ef83  lea     rcx, [rbp+30h+var_88.Buffer]; this
0x18002ef87  mov     ebx, [rax]
0x18002ef89  call    ??1CFnTracerHR@@QEAA@XZ; CFnTracerHR::~CFnTracerHR(void)
0x18002ef8e  mov     eax, ebx
0x18002ef90  mov     rcx, [rbp+30h+var_50.Buffer]
0x18002ef94  xor     rcx, rsp; StackCookie
0x18002ef97  call    __security_check_cookie
0x18002ef9c  add     rsp, 138h
0x18002efa3  pop     r15
0x18002efa5  pop     r14
0x18002efa7  pop     r13
0x18002efa9  pop     r12
0x18002efab  pop     rdi
0x18002efac  pop     rsi
0x18002efad  pop     rbx
0x18002efae  pop     rbp
0x18002efaf  retn
0x18002efb1  test    r14d, r14d
0x18002efb4  jnz     loc_18002F11E
0x18002efba  mov     ecx, [rdi+178h]
0x18002efc0  sub     ecx, eax
0x18002efc2  jz      short loc_18002EFCC
0x18002efc4  sub     ecx, eax
0x18002efc6  jnz     loc_18002F12D
0x18002efcc  mov     rdx, [rbx+rsi+28h]; unsigned __int64
0x18002efd1  mov     rcx, [rbx+rsi+18h]; unsigned __int16 *
0x18002efd6  call    ?SxspIsNamespaceInAsmEquivalenceSet@@YA_NPEBG_K@Z; SxspIsNamespaceInAsmEquivalenceSet(ushort const *,unsigned __int64)
0x18002efdb  test    al, al
0x18002efdd  jz      loc_18002F103
0x18002efe3  cmp     qword ptr [rbx+rsi+0B8h], 8
0x18002efec  jnz     loc_18002F103
0x18002eff2  mov     rax, [rbx+rsi+0B0h]
0x18002effa  lea     rdx, [rbp+30h+String2]; String2
0x18002effe  mov     [rbp+30h+String1.Buffer], rax
0x18002f002  lea     rcx, [rbp+30h+String1]; String1
0x18002f006  lea     rax, aAssembly; "assembly"
0x18002f00d  mov     qword ptr [rbp+30h+String1.Length], 100010h
0x18002f015  xor     r8d, r8d; CaseInsensitive
0x18002f018  mov     [rbp+30h+String2.Buffer], rax
0x18002f01c  mov     qword ptr [rbp+30h+String2.Length], 100010h
0x18002f024  call    cs:__imp_RtlCompareUnicodeString
0x18002f02b  nop     dword ptr [rax+rax+00h]
0x18002f030  test    eax, eax
0x18002f032  jnz     loc_18002F103
0x18002f038  mov     eax, 1
0x18002f03d  jmp     loc_18002EED3
0x18002f042  test    r12b, r12b
0x18002f045  jz      loc_18002F1C2
0x18002f04b  test    r15b, r15b
0x18002f04e  jnz     loc_18002EEF0
0x18002f054  xor     ecx, ecx; dwErrCode
0x18002f056  call    cs:__imp_SetLastError
0x18002f05d  nop     dword ptr [rax+rax+00h]
0x18002f062  mov     edx, 0C101000Ch
0x18002f067  mov     r8d, 7Dh ; '}'
0x18002f06d  jmp     loc_18002F1DB
0x18002f072  cmp     qword ptr [rbx+rsi+28h], 0
0x18002f078  jnz     loc_18002EED3
0x18002f07e  mov     rdx, [rbx+rsi+0B8h]; unsigned __int64
0x18002f086  lea     r8, aManifestversio; "manifestVersion"
0x18002f08d  mov     rcx, [rbx+rsi+0B0h]; unsigned __int16 *
0x18002f095  mov     r9d, 0Fh; unsigned __int64
0x18002f09b  mov     byte ptr [rsp+170h+var_150], 0; bool
0x18002f0a0  call    ?FusionpEqualStrings@@YA_NPEBG_K01_N@Z; FusionpEqualStrings(ushort const *,unsigned __int64,ushort const *,unsigned __int64,bool)
0x18002f0a5  test    al, al
0x18002f0a7  jz      short loc_18002F038
0x18002f0a9  lea     eax, [r14+1]
0x18002f0ad  mov     r12b, 1
0x18002f0b0  cmp     eax, r13d
0x18002f0b3  jnb     short loc_18002F038
0x18002f0b5  lea     rcx, [rax+rax*2]
0x18002f0b9  shl     rcx, 6
0x18002f0bd  cmp     dword ptr [rcx+rsi+4], 0Dh
0x18002f0c2  jnz     loc_18002F038
0x18002f0c8  mov     rdx, [rcx+rsi+0B8h]; unsigned __int64
0x18002f0d0  lea     r8, a10; "1.0"
0x18002f0d7  mov     rcx, [rcx+rsi+0B0h]; unsigned __int16 *
0x18002f0df  mov     r9d, 3; unsigned __int64
0x18002f0e5  mov     byte ptr [rsp+170h+var_150], 0; bool
0x18002f0ea  call    ?FusionpEqualStrings@@YA_NPEBG_K01_N@Z; FusionpEqualStrings(ushort const *,unsigned __int64,ushort const *,unsigned __int64,bool)
0x18002f0ef  test    al, al
0x18002f0f1  movzx   r15d, r15b
0x18002f0f5  mov     eax, 1
0x18002f0fa  cmovnz  r15d, eax
0x18002f0fe  jmp     loc_18002EED3
0x18002f103  xor     ecx, ecx; dwErrCode
0x18002f105  call    cs:__imp_SetLastError
0x18002f10c  nop     dword ptr [rax+rax+00h]
0x18002f111  mov     edx, 0C1010009h
0x18002f116  mov     r8d, 7Ch ; '|'
0x18002f11c  jmp     short loc_18002F181
0x18002f11e  mov     rax, [rbp+30h+var_58]
0x18002f122  mov     dword ptr [rax], 8007054Fh
0x18002f128  jmp     loc_18002EF7F
0x18002f12d  cmp     ecx, eax
0x18002f12f  jnz     short loc_18002F11E
0x18002f131  cmp     qword ptr [rbx+rsi+28h], 0
0x18002f137  jnz     short loc_18002F168
0x18002f139  mov     rdx, [rbx+rsi+0B8h]; unsigned __int64
0x18002f141  lea     r8, aConfiguration; "configuration"
0x18002f148  mov     rcx, [rbx+rsi+0B0h]; unsigned __int16 *
0x18002f150  mov     r9d, 0Dh; unsigned __int64
0x18002f156  mov     byte ptr [rsp+170h+var_150], 0; bool
0x18002f15b  call    ?FusionpEqualStrings@@YA_NPEBG_K01_N@Z; FusionpEqualStrings(ushort const *,unsigned __int64,ushort const *,unsigned __int64,bool)
0x18002f160  test    al, al
0x18002f162  jnz     loc_18002F038
0x18002f168  xor     ecx, ecx; dwErrCode
0x18002f16a  call    cs:__imp_SetLastError
0x18002f171  nop     dword ptr [rax+rax+00h]
0x18002f176  mov     edx, 0C101000Ah; unsigned int
0x18002f17b  mov     r8d, 90h; unsigned int
0x18002f181  xor     r9d, r9d; struct _UNICODE_STRING *
0x18002f184  mov     [rsp+170h+var_148], 0; struct _UNICODE_STRING *
0x18002f18d  mov     rcx, rdi; this
0x18002f190  mov     [rsp+170h+var_150], r9; struct _UNICODE_STRING *
0x18002f195  call    ?LogParseError@CNodeFactory@@QEAAJKKPEBU_UNICODE_STRING@@0000000000000000000@Z; CNodeFactory::LogParseError(ulong,ulong,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *)
0x18002f19a  mov     ebx, eax
0x18002f19c  test    eax, eax
0x18002f19e  jns     loc_18002F038
0x18002f1a4  lea     rdx, byte_18008517D; char *
0x18002f1ab  mov     ecx, ebx; int
0x18002f1ad  call    ?FusionpTraceCOMFailure@@YAXJPEBDZZ; FusionpTraceCOMFailure(long,char const *,...)
0x18002f1b2  mov     edx, ebx; int
0x18002f1b4  lea     rcx, [rbp+30h+var_88.Buffer]; this
0x18002f1b8  call    ?MarkCOMFailure@CFnTracerHR@@QEAAXJ@Z; CFnTracerHR::MarkCOMFailure(long)
0x18002f1bd  jmp     loc_18002EF7F
0x18002f1c2  xor     ecx, ecx; dwErrCode
0x18002f1c4  call    cs:__imp_SetLastError
0x18002f1cb  nop     dword ptr [rax+rax+00h]
0x18002f1d0  mov     edx, 0C101000Bh; unsigned int
0x18002f1d5  mov     r8d, 7Eh ; '~'; unsigned int
0x18002f1db  xor     r9d, r9d; struct _UNICODE_STRING *
0x18002f1de  mov     [rsp+170h+var_148], 0; struct _UNICODE_STRING *
0x18002f1e7  mov     rcx, rdi; this
0x18002f1ea  mov     [rsp+170h+var_150], r9; struct _UNICODE_STRING *
0x18002f1ef  call    ?LogParseError@CNodeFactory@@QEAAJKKPEBU_UNICODE_STRING@@0000000000000000000@Z; CNodeFactory::LogParseError(ulong,ulong,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *)
0x18002f1f4  mov     ebx, eax
0x18002f1f6  test    eax, eax
0x18002f1f8  jns     loc_18002EEF0
0x18002f1fe  jmp     short loc_18002F1A4
0x18002f200  lea     rcx, [rbp+30h+var_88.Buffer]; this
0x18002f204  call    ?MarkWin32LastErrorFailure@CFnTracerHR@@QEAAXXZ; CFnTracerHR::MarkWin32LastErrorFailure(void)
0x18002f209  lea     rcx, off_180079568; struct _CALL_SITE_INFO *
0x18002f210  call    ?FusionpTraceWin32LastErrorFailure@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailure(_CALL_SITE_INFO const &)
0x18002f215  jmp     loc_18002EF7F
0x18002f21a  cmp     byte ptr [rbp+30h+var_88.Length], 0
0x18002f21e  jz      loc_18002EF75
0x18002f224  mov     rax, [rdi+188h]
0x18002f22b  test    byte ptr [rax], 8
0x18002f22e  jz      loc_18002EF75
0x18002f234  mov     [rsp+170h+var_148], 0; struct _UNICODE_STRING *
0x18002f23d  xor     r9d, r9d; struct _UNICODE_STRING *
0x18002f240  mov     edx, 0C101004Dh; unsigned int
0x18002f245  mov     [rsp+170h+var_150], 0; struct _UNICODE_STRING *
0x18002f24e  mov     r8d, 96h; unsigned int
0x18002f254  mov     rcx, rdi; this
0x18002f257  call    ?LogParseError@CNodeFactory@@QEAAJKKPEBU_UNICODE_STRING@@0000000000000000000@Z; CNodeFactory::LogParseError(ulong,ulong,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *)
0x18002f25c  mov     rax, [rbp+30h+var_58]
0x18002f260  mov     dword ptr [rax], 800736B1h
0x18002f266  mov     rcx, [rbp+30h+var_58]; int *
0x18002f26a  call    ?FusionpConvertCOMFailure@@YAXAEAJ@Z; FusionpConvertCOMFailure(long &)
0x18002f26f  lea     rcx, off_180079548; struct _CALL_SITE_INFO *
0x18002f276  call    ?FusionpTraceWin32LastErrorFailureOrigination@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailureOrigination(_CALL_SITE_INFO const &)
0x18002f27b  jmp     loc_18002EF7F
```
