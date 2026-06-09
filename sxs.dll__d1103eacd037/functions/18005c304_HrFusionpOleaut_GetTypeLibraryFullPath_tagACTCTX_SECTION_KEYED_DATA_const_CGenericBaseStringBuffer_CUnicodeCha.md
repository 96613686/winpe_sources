# HrFusionpOleaut_GetTypeLibraryFullPath(tagACTCTX_SECTION_KEYED_DATA const *,CGenericBaseStringBuffer<CUnicodeCharTraits> &)

- ea: `0x18005c304`
- end: `0x18005c47b`
- name: `?HrFusionpOleaut_GetTypeLibraryFullPath@@YAJPEBUtagACTCTX_SECTION_KEYED_DATA@@AEAV?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@@Z`
- size: `375`
- prototype: `__int64 __fastcall(struct tagACTCTX_SECTION_KEYED_DATA *)`
- caller_count: `2`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001fe0`
- `0x18001e620`

## callees

- `0x18000df40`
- `0x18000dffc`
- `0x18002e98c`
- `0x18002ff90`
- `0x180030148`
- `0x18004f220`
- `0x18005aaf0`
- `0x18005ad08`
- `0x18005c304`
- `0x18005cc58`
- `0x18006a110`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005c387`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005c3d2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005c407`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005c387`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005c3d2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005c407`

## pseudocode

```c
__int64 __fastcall HrFusionpOleaut_GetTypeLibraryFullPath(struct tagACTCTX_SECTION_KEYED_DATA *a1, __int64 a2)
{
  int TypeLibraryName; // eax
  int v5; // ebx
  char **v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // rcx
  __int64 v9; // r9
  unsigned int v10; // ebx
  __int64 v12; // [rsp+28h] [rbp-31h]
  void *v13; // [rsp+40h] [rbp-19h] BYREF
  unsigned __int16 *v14; // [rsp+48h] [rbp-11h] BYREF
  unsigned __int64 v15; // [rsp+50h] [rbp-9h] BYREF
  int v16; // [rsp+58h] [rbp-1h] BYREF
  int v17; // [rsp+60h] [rbp+7h] BYREF
  __int64 v18; // [rsp+68h] [rbp+Fh]
  __int64 *v19; // [rsp+70h] [rbp+17h]
  __int64 v20; // [rsp+78h] [rbp+1Fh]
  int v21; // [rsp+80h] [rbp+27h]
  int *v22; // [rsp+88h] [rbp+2Fh]

  v16 = -1;
  v19 = &qword_180072FE0;
  v17 = 1;
  v22 = &v16;
  v18 = 0;
  v20 = 544438355;
  v21 = 150;
  CFrame::BaseEnter((CFrame *)&v17);
  v14 = 0;
  v15 = 0;
  v13 = 0;
  SetLastError(0);
  TypeLibraryName = HrFusionpOleaut_GetTypeLibraryName(a1, (const unsigned __int16 **)&v14, &v15);
  v5 = TypeLibraryName;
  if ( TypeLibraryName >= 0 )
  {
    SetLastError(0);
    if ( (unsigned int)FusionpGetActivationContextFromFindResult(a1, &v13) )
    {
      SetLastError(0);
      if ( (unsigned int)FusionpSearchPath(v8, v7, v14, v9, a2, v12, v13) )
      {
        *v22 = 0;
        goto LABEL_9;
      }
      CFnTracerHR::MarkWin32LastErrorFailure((CFnTracerHR *)&v17);
      v6 = off_180076840;
    }
    else
    {
      CFnTracerHR::MarkWin32LastErrorFailure((CFnTracerHR *)&v17);
      v6 = off_180076860;
    }
    FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)v6);
  }
  else
  {
    FusionpTraceCOMFailure(TypeLibraryName, byte_18008517D);
    LODWORD(v13) = v5;
    FusionpConvertCOMFailure((unsigned int *)&v13);
    *v22 = (int)v13;
  }
LABEL_9:
  v10 = *v22;
  CFnTracerHR::~CFnTracerHR((CFnTracerHR *)&v17);
  return v10;
}

```

## disassembly

```asm
0x18005c304  mov     [rsp-8+arg_10], rbx
0x18005c309  push    rbp
0x18005c30a  push    rsi
0x18005c30b  push    rdi
0x18005c30c  lea     rbp, [rsp-47h]
0x18005c311  sub     rsp, 0A0h
0x18005c318  mov     rax, cs:__security_cookie
0x18005c31f  xor     rax, rsp
0x18005c322  mov     [rbp+57h+var_20], rax
0x18005c326  lea     rax, qword_180072FE0
0x18005c32d  mov     [rbp+57h+var_58], 0FFFFFFFFh
0x18005c334  mov     [rbp+57h+var_40], rax
0x18005c338  mov     rdi, rcx
0x18005c33b  lea     rax, [rbp+57h+var_58]
0x18005c33f  mov     [rbp+57h+var_50], 1
0x18005c346  lea     rcx, [rbp+57h+var_50]; this
0x18005c34a  mov     [rbp+57h+var_28], rax
0x18005c34e  mov     rsi, rdx
0x18005c351  mov     [rbp+57h+var_48], 0
0x18005c359  mov     [rbp+57h+var_38], 20737853h
0x18005c361  mov     [rbp+57h+var_30], 96h
0x18005c368  call    ?BaseEnter@CFrame@@QEAAXXZ; CFrame::BaseEnter(void)
0x18005c36d  xor     ecx, ecx; dwErrCode
0x18005c36f  mov     [rbp+57h+var_68], 0
0x18005c377  mov     [rbp+57h+var_60], 0
0x18005c37f  mov     [rbp+57h+var_70], 0
0x18005c387  call    cs:__imp_SetLastError
0x18005c38e  nop     dword ptr [rax+rax+00h]
0x18005c393  lea     r8, [rbp+57h+var_60]; unsigned __int64 *
0x18005c397  mov     rcx, rdi; struct tagACTCTX_SECTION_KEYED_DATA *
0x18005c39a  lea     rdx, [rbp+57h+var_68]; unsigned __int16 **
0x18005c39e  call    ?HrFusionpOleaut_GetTypeLibraryName@@YAJPEBUtagACTCTX_SECTION_KEYED_DATA@@PEAPEBGPEA_K@Z; HrFusionpOleaut_GetTypeLibraryName(tagACTCTX_SECTION_KEYED_DATA const *,ushort const * *,unsigned __int64 *)
0x18005c3a3  mov     ebx, eax
0x18005c3a5  test    eax, eax
0x18005c3a7  jns     short loc_18005C3D0
0x18005c3a9  lea     rdx, byte_18008517D; char *
0x18005c3b0  mov     ecx, eax; int
0x18005c3b2  call    ?FusionpTraceCOMFailure@@YAXJPEBDZZ; FusionpTraceCOMFailure(long,char const *,...)
0x18005c3b7  lea     rcx, [rbp+57h+var_70]; int *
0x18005c3bb  mov     dword ptr [rbp+57h+var_70], ebx
0x18005c3be  call    ?FusionpConvertCOMFailure@@YAXAEAJ@Z; FusionpConvertCOMFailure(long &)
0x18005c3c3  mov     rax, [rbp+57h+var_28]
0x18005c3c7  mov     r9d, dword ptr [rbp+57h+var_70]
0x18005c3cb  mov     [rax], r9d
0x18005c3ce  jmp     short loc_18005C44A
0x18005c3d0  xor     ecx, ecx; dwErrCode
0x18005c3d2  call    cs:__imp_SetLastError
0x18005c3d9  nop     dword ptr [rax+rax+00h]
0x18005c3de  lea     rdx, [rbp+57h+var_70]; void **
0x18005c3e2  mov     rcx, rdi; struct tagACTCTX_SECTION_KEYED_DATA *
0x18005c3e5  call    ?FusionpGetActivationContextFromFindResult@@YAHPEBUtagACTCTX_SECTION_KEYED_DATA@@PEAPEAX@Z; FusionpGetActivationContextFromFindResult(tagACTCTX_SECTION_KEYED_DATA const *,void * *)
0x18005c3ea  test    eax, eax
0x18005c3ec  jnz     short loc_18005C405
0x18005c3ee  lea     rcx, [rbp+57h+var_50]; this
0x18005c3f2  call    ?MarkWin32LastErrorFailure@CFnTracerHR@@QEAAXXZ; CFnTracerHR::MarkWin32LastErrorFailure(void)
0x18005c3f7  lea     rcx, off_180076860; struct _CALL_SITE_INFO *
0x18005c3fe  call    ?FusionpTraceWin32LastErrorFailure@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailure(_CALL_SITE_INFO const &)
0x18005c403  jmp     short loc_18005C44A
0x18005c405  xor     ecx, ecx; dwErrCode
0x18005c407  call    cs:__imp_SetLastError
0x18005c40e  nop     dword ptr [rax+rax+00h]
0x18005c413  mov     rax, [rbp+57h+var_70]
0x18005c417  mov     r8, [rbp+57h+var_68]
0x18005c41b  mov     [rsp+0B0h+var_80], rax
0x18005c420  mov     [rsp+0B0h+var_90], rsi
0x18005c425  call    ?FusionpSearchPath@@YAHKPEBG00AEAV?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@PEA_KPEAX@Z; FusionpSearchPath(ulong,ushort const *,ushort const *,ushort const *,CGenericBaseStringBuffer<CUnicodeCharTraits> &,unsigned __int64 *,void *)
0x18005c42a  test    eax, eax
0x18005c42c  jnz     short loc_18005C440
0x18005c42e  lea     rcx, [rbp+57h+var_50]; this
0x18005c432  call    ?MarkWin32LastErrorFailure@CFnTracerHR@@QEAAXXZ; CFnTracerHR::MarkWin32LastErrorFailure(void)
0x18005c437  lea     rcx, off_180076840; "clientcore\\base\\win32\\fusion\\sxs\\s"...
0x18005c43e  jmp     short loc_18005C3FE
0x18005c440  mov     rax, [rbp+57h+var_28]
0x18005c444  mov     dword ptr [rax], 0
0x18005c44a  mov     rax, [rbp+57h+var_28]
0x18005c44e  lea     rcx, [rbp+57h+var_50]; this
0x18005c452  mov     ebx, [rax]
0x18005c454  call    ??1CFnTracerHR@@QEAA@XZ; CFnTracerHR::~CFnTracerHR(void)
0x18005c459  mov     eax, ebx
0x18005c45b  mov     rcx, [rbp+57h+var_20]
0x18005c45f  xor     rcx, rsp; StackCookie
0x18005c462  call    __security_check_cookie
0x18005c467  mov     rbx, [rsp+0B0h+arg_10]
0x18005c46f  add     rsp, 0A0h
0x18005c476  pop     rdi
0x18005c477  pop     rsi
0x18005c478  pop     rbp
0x18005c479  retn
```
