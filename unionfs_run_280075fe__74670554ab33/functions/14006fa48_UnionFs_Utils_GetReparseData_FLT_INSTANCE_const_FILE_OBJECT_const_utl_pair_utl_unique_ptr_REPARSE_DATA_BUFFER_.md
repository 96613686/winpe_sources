# UnionFs::Utils::GetReparseData(_FLT_INSTANCE const &,_FILE_OBJECT const &,utl::pair<utl::unique_ptr<_REPARSE_DATA_BUFFER,utl::default_delete<_REPARSE_DATA_BUFFER>>,ulong> &,UnionFs::StackEventTracer &,ulong)

- ea: `0x14006fa48`
- end: `0x14006fc7d`
- name: `?GetReparseData@Utils@UnionFs@@YAJAEBU_FLT_INSTANCE@@AEBU_FILE_OBJECT@@AEAU?$pair@V?$unique_ptr@U_REPARSE_DATA_BUFFER@@U?$default_delete@U_REPARSE_DATA_BUFFER@@@utl@@@utl@@K@utl@@AEAVStackEventTracer@2@K@Z`
- size: `565`
- prototype: `__int64 __usercall@<rax>(PFLT_INSTANCE Instance@<rcx>, PFILE_OBJECT FileObject@<rdx>, ULONG)`
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path, installer_update, broker_com_uri`

## callers

- `0x14006c1fc`

## callees

- `0x140001008`
- `0x140056a50`
- `0x140056ac4`
- `0x140067958`
- `0x14006fa48`
- `0x14007af90`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14006fa91`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006faa8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006fb82`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006fc2f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006fa91`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006faa8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006fb82`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006fc2f`
- `FLTMGR!FltFsControlFile` at `0x14006fae6`
- `FLTMGR!FltFsControlFile` at `0x14006fae6`

## string_xrefs

- `0x14006fc3d`: `ORIGIN: Allocating reparse info buffer`
- `0x14006fb54`: `UnionFs::Utils::GetReparseData`
- `0x14006fbad`: `UnionFs::Utils::GetReparseData`
- `0x14006fbe2`: `UnionFs::Utils::GetReparseData`
- `0x14006fc50`: `UnionFs::Utils::GetReparseData`
- `0x14006fb9c`: `API: Getting reparse point`
- `0x14006fbe9`: `File is not a reparse point`
- `0x14006fb41`: `ORIGIN: Corrupt reparse data`

## pseudocode

```c
__int64 __fastcall UnionFs::Utils::GetReparseData(
        PFLT_INSTANCE Instance,
        PFILE_OBJECT FileObject,
        __int64 a3,
        int a4,
        ULONG LengthReturned)
{
  unsigned __int16 *v5; // rbx
  ULONG OutputBufferLength; // esi
  unsigned __int16 **v11; // rax
  unsigned __int16 *v12; // rdi
  unsigned int v13; // ebx
  int v14; // r8d
  ULONG v15; // ecx
  void *v16; // rax
  const char *OutputBuffer; // [rsp+28h] [rbp-40h]
  PVOID P; // [rsp+40h] [rbp-28h] BYREF
  const char *v20; // [rsp+48h] [rbp-20h] BYREF
  const char *v21; // [rsp+50h] [rbp-18h] BYREF
  const char *v22; // [rsp+58h] [rbp-10h] BYREF

  v5 = 0;
  LengthReturned = 0;
  for ( OutputBufferLength = 520; ; OutputBufferLength = v12[2] + 8 )
  {
    v11 = (unsigned __int16 **)utl::make_unique_pool<enum gsl::byte [0],256,1651656277,0>(&P, OutputBufferLength);
    v12 = *v11;
    *v11 = 0;
    if ( v5 )
      ExFreePoolWithTag(v5, 0);
    if ( P )
      ExFreePoolWithTag(P, 0);
    if ( !v12 )
    {
      v13 = -1073741670;
      UnionFs::ProcessTraceStatusOrigin(
        (UnionFs *)0xC000009ALL,
        a4,
        (struct UnionFs::StackEventTracer *)0x286002118AELL,
        (unsigned __int64)"UnionFs::Utils::GetReparseData",
        "ORIGIN: Allocating reparse info buffer",
        OutputBuffer);
      return v13;
    }
    v13 = FltFsControlFile(Instance, FileObject, 0x900A8u, 0, 0, v12, OutputBufferLength, &LengthReturned);
    if ( v13 == 259 )
      MicrosoftTelemetryAssertTriggeredMsgKM("status != STATUS_PENDING");
    v15 = LengthReturned;
    if ( LengthReturned < 8 || v13 != -2147483643 )
      break;
    v5 = v12;
  }
  if ( v13 == -1073741195 )
  {
    if ( (unsigned int)dword_14009E178 > 4 )
    {
      LODWORD(P) = 6338;
      v20 = "onecore\\base\\fs\\unionfs\\sys\\unionfsproc.cpp";
      v21 = "UnionFs::Utils::GetReparseData";
      v22 = "File is not a reparse point";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        LengthReturned,
        (unsigned int)&byte_14009A30F,
        v14,
        (unsigned int)"UnionFs::Utils::GetReparseData",
        (__int64)&v22,
        (__int64)&v21,
        (__int64)&v20,
        (__int64)&P);
    }
    v13 = 0;
    goto LABEL_23;
  }
  if ( (v13 & 0x80000000) != 0 )
  {
    UnionFs::ProcessTraceStatusFromApi(
      (UnionFs *)v13,
      a4,
      (struct UnionFs::StackEventTracer *)0x287002118C7LL,
      (unsigned __int64)"UnionFs::Utils::GetReparseData",
      "API: Getting reparse point",
      OutputBuffer);
LABEL_23:
    ExFreePoolWithTag(v12, 0);
    return v13;
  }
  if ( LengthReturned < (unsigned int)v12[2] + 8 )
  {
    v13 = -1073741566;
    UnionFs::ProcessTraceStatusOrigin(
      (UnionFs *)0xC0000102LL,
      a4,
      (struct UnionFs::StackEventTracer *)0x288002118CFLL,
      (unsigned __int64)"UnionFs::Utils::GetReparseData",
      "ORIGIN: Corrupt reparse data",
      OutputBuffer);
    goto LABEL_23;
  }
  v16 = *(void **)a3;
  *(_QWORD *)a3 = v12;
  if ( v16 )
  {
    ExFreePoolWithTag(v16, 0);
    v15 = LengthReturned;
  }
  *(_DWORD *)(a3 + 8) = v15;
  return 0;
}

```

## disassembly

```asm
0x14006fa48  push    rbp
0x14006fa4a  push    rbx
0x14006fa4b  push    rsi
0x14006fa4c  push    rdi
0x14006fa4d  push    r12
0x14006fa4f  push    r13
0x14006fa51  push    r14
0x14006fa53  push    r15
0x14006fa55  mov     rbp, rsp
0x14006fa58  sub     rsp, 68h
0x14006fa5c  xor     ebx, ebx
0x14006fa5e  mov     r15, r9
0x14006fa61  mov     [rbp+arg_20], ebx
0x14006fa64  mov     r14, r8
0x14006fa67  mov     r12, rdx
0x14006fa6a  mov     r13, rcx
0x14006fa6d  mov     esi, 208h
0x14006fa72  mov     edx, esi
0x14006fa74  lea     rcx, [rbp+P]
0x14006fa78  call    ??$make_unique_pool@$$BY0A@W4byte@gsl@@$0BAA@$0GCHCEGFF@$0A@@utl@@YA?AV?$unique_ptr@$$BY0A@W4byte@gsl@@U?$default_delete@$$BY0A@W4byte@gsl@@@utl@@@0@_K@Z; utl::make_unique_pool<gsl::byte [0],256,1651656277,0>(unsigned __int64)
0x14006fa7d  mov     rdi, [rax]
0x14006fa80  mov     qword ptr [rax], 0
0x14006fa87  test    rbx, rbx
0x14006fa8a  jz      short loc_14006FA9D
0x14006fa8c  xor     edx, edx; Tag
0x14006fa8e  mov     rcx, rbx; P
0x14006fa91  call    cs:__imp_ExFreePoolWithTag
0x14006fa98  nop     dword ptr [rax+rax+00h]
0x14006fa9d  mov     rcx, [rbp+P]; P
0x14006faa1  test    rcx, rcx
0x14006faa4  jz      short loc_14006FAB4
0x14006faa6  xor     edx, edx; Tag
0x14006faa8  call    cs:__imp_ExFreePoolWithTag
0x14006faaf  nop     dword ptr [rax+rax+00h]
0x14006fab4  test    rdi, rdi
0x14006fab7  jz      loc_14006FC3D
0x14006fabd  lea     rax, [rbp+arg_20]
0x14006fac1  xor     r9d, r9d; InputBuffer
0x14006fac4  mov     [rsp+68h+LengthReturned], rax; LengthReturned
0x14006fac9  mov     r8d, 900A8h; FsControlCode
0x14006facf  mov     [rsp+68h+OutputBufferLength], esi; OutputBufferLength
0x14006fad3  mov     rdx, r12; FileObject
0x14006fad6  mov     [rsp+68h+OutputBuffer], rdi; char *
0x14006fadb  mov     rcx, r13; Instance
0x14006fade  mov     [rsp+68h+InputBufferLength], 0; InputBufferLength
0x14006fae6  call    cs:__imp_FltFsControlFile
0x14006faed  nop     dword ptr [rax+rax+00h]
0x14006faf2  mov     ebx, eax
0x14006faf4  cmp     eax, 103h
0x14006faf9  jnz     short loc_14006FB07
0x14006fafb  lea     rcx, aStatusStatusPe; "status != STATUS_PENDING"
0x14006fb02  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x14006fb07  mov     ecx, [rbp+arg_20]
0x14006fb0a  cmp     ecx, 8
0x14006fb0d  jb      short loc_14006FB26
0x14006fb0f  cmp     ebx, 80000005h
0x14006fb15  jnz     short loc_14006FB26
0x14006fb17  movzx   esi, word ptr [rdi+4]
0x14006fb1b  mov     rbx, rdi
0x14006fb1e  add     esi, 8
0x14006fb21  jmp     loc_14006FA72
0x14006fb26  cmp     ebx, 0C0000275h
0x14006fb2c  jz      loc_14006FBC5
0x14006fb32  test    ebx, ebx
0x14006fb34  js      short loc_14006FB9C
0x14006fb36  movzx   eax, word ptr [rdi+4]
0x14006fb3a  add     eax, 8
0x14006fb3d  cmp     ecx, eax
0x14006fb3f  jnb     short loc_14006FB72
0x14006fb41  lea     rax, aOriginCorruptR; "ORIGIN: Corrupt reparse data"
0x14006fb48  mov     ebx, 0C0000102h
0x14006fb4d  mov     ecx, ebx; this
0x14006fb4f  mov     qword ptr [rsp+68h+InputBufferLength], rax; char *
0x14006fb54  lea     r9, aUnionfsUtilsGe_6; "UnionFs::Utils::GetReparseData"
0x14006fb5b  mov     r8, 288002118CFh; struct UnionFs::StackEventTracer *
0x14006fb65  mov     rdx, r15; int
0x14006fb68  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14006fb6d  jmp     loc_14006FC2A
0x14006fb72  mov     rax, [r14]
0x14006fb75  mov     [r14], rdi
0x14006fb78  test    rax, rax
0x14006fb7b  jz      short loc_14006FB91
0x14006fb7d  xor     edx, edx; Tag
0x14006fb7f  mov     rcx, rax; P
0x14006fb82  call    cs:__imp_ExFreePoolWithTag
0x14006fb89  nop     dword ptr [rax+rax+00h]
0x14006fb8e  mov     ecx, [rbp+arg_20]
0x14006fb91  mov     [r14+8], ecx
0x14006fb95  xor     eax, eax
0x14006fb97  jmp     loc_14006FC6B
0x14006fb9c  lea     rax, aApiGettingRepa; "API: Getting reparse point"
0x14006fba3  mov     r8, 287002118C7h; struct UnionFs::StackEventTracer *
0x14006fbad  lea     r9, aUnionfsUtilsGe_6; "UnionFs::Utils::GetReparseData"
0x14006fbb4  mov     qword ptr [rsp+68h+InputBufferLength], rax; char *
0x14006fbb9  mov     rdx, r15; int
0x14006fbbc  mov     ecx, ebx; this
0x14006fbbe  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14006fbc3  jmp     short loc_14006FC2A
0x14006fbc5  mov     eax, cs:dword_14009E178
0x14006fbcb  cmp     eax, 4
0x14006fbce  jbe     short loc_14006FC28
0x14006fbd0  lea     rax, aOnecoreBaseFsU_3; "onecore\\base\\fs\\unionfs\\sys\\unionf"...
0x14006fbd7  mov     dword ptr [rbp+P], 18C2h
0x14006fbde  mov     [rbp+var_20], rax
0x14006fbe2  lea     r9, aUnionfsUtilsGe_6; "UnionFs::Utils::GetReparseData"
0x14006fbe9  lea     rax, aFileIsNotARepa; "File is not a reparse point"
0x14006fbf0  mov     [rbp+var_18], r9
0x14006fbf4  mov     [rbp+var_10], rax
0x14006fbf8  lea     rdx, byte_14009A30F
0x14006fbff  lea     rax, [rbp+P]
0x14006fc03  mov     [rsp+68h+LengthReturned], rax
0x14006fc08  lea     rax, [rbp+var_20]
0x14006fc0c  mov     qword ptr [rsp+68h+OutputBufferLength], rax
0x14006fc11  lea     rax, [rbp+var_18]
0x14006fc15  mov     [rsp+68h+OutputBuffer], rax
0x14006fc1a  lea     rax, [rbp+var_10]
0x14006fc1e  mov     qword ptr [rsp+68h+InputBufferLength], rax
0x14006fc23  call    ??$Write@U?$_tlgWrapSz@D@@U1@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@33AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x14006fc28  xor     ebx, ebx
0x14006fc2a  xor     edx, edx; Tag
0x14006fc2c  mov     rcx, rdi; P
0x14006fc2f  call    cs:__imp_ExFreePoolWithTag
0x14006fc36  nop     dword ptr [rax+rax+00h]
0x14006fc3b  jmp     short loc_14006FC69
0x14006fc3d  lea     rax, aOriginAllocati_40; "ORIGIN: Allocating reparse info buffer"
0x14006fc44  mov     ebx, 0C000009Ah
0x14006fc49  mov     ecx, ebx; this
0x14006fc4b  mov     qword ptr [rsp+68h+InputBufferLength], rax; char *
0x14006fc50  lea     r9, aUnionfsUtilsGe_6; "UnionFs::Utils::GetReparseData"
0x14006fc57  mov     r8, 286002118AEh; struct UnionFs::StackEventTracer *
0x14006fc61  mov     rdx, r15; int
0x14006fc64  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14006fc69  mov     eax, ebx
0x14006fc6b  add     rsp, 68h
0x14006fc6f  pop     r15
0x14006fc71  pop     r14
0x14006fc73  pop     r13
0x14006fc75  pop     r12
0x14006fc77  pop     rdi
0x14006fc78  pop     rsi
0x14006fc79  pop     rbx
0x14006fc7a  pop     rbp
0x14006fc7b  retn
```
