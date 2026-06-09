# CNodeFactory::XMLParser_Element_doc_configuration_windows_assemblyBinding_assemblyIdentity(ushort,_SXS_NODE_INFO const *)

- ea: `0x180065520`
- end: `0x18006565b`
- name: `?XMLParser_Element_doc_configuration_windows_assemblyBinding_assemblyIdentity@CNodeFactory@@QEAAHGPEBU_SXS_NODE_INFO@@@Z`
- size: `315`
- prototype: `__int64 __fastcall(CNodeFactory *__hidden this, unsigned __int16, const struct _SXS_NODE_INFO *)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config`

## callees

- `0x18000df40`
- `0x18000dffc`
- `0x18001c270`
- `0x18002b580`
- `0x1800419e4`
- `0x180041f10`
- `0x180065520`
- `0x18006a110`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180065594`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800655dc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006560b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180065594`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800655dc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006560b`

## pseudocode

```c
__int64 __fastcall CNodeFactory::XMLParser_Element_doc_configuration_windows_assemblyBinding_assemblyIdentity(
        CNodeFactory *this,
        unsigned __int16 a2,
        const struct _SXS_NODE_INFO *a3)
{
  unsigned int v3; // ebx
  const struct _ACTCTXCTB_PARSE_CONTEXT *v6; // rdx
  __int64 v7; // rcx
  char **v8; // rcx
  unsigned int v9; // ebx
  struct _ASSEMBLY_IDENTITY *v11; // [rsp+30h] [rbp-50h] BYREF
  char v12; // [rsp+38h] [rbp-48h]
  int v13; // [rsp+40h] [rbp-40h] BYREF
  int v14; // [rsp+48h] [rbp-38h] BYREF
  __int64 v15; // [rsp+50h] [rbp-30h]
  __int64 *v16; // [rsp+58h] [rbp-28h]
  __int64 v17; // [rsp+60h] [rbp-20h]
  int v18; // [rsp+68h] [rbp-18h]
  unsigned int *v19; // [rsp+70h] [rbp-10h]

  v3 = a2;
  v16 = &qword_180079028;
  v13 = 0;
  v19 = (unsigned int *)&v13;
  v14 = 1;
  v15 = 0;
  v17 = 544438355;
  v18 = 2912;
  CFrame::BaseEnter((CFrame *)&v14);
  v11 = 0;
  SetLastError(0);
  v12 = 1;
  if ( (unsigned int)SxspCreateAssemblyIdentityFromIdentityElement(v7, v6, 2u, &v11, v3, a3) )
  {
    SetLastError(0);
    if ( (unsigned int)CNodeFactory::ValidateIdentity(this, 3, 2, v11) )
    {
      SetLastError(0);
      *v19 = 1;
      goto LABEL_7;
    }
    v8 = off_180078FE8;
  }
  else
  {
    v8 = off_180079008;
  }
  *v19 = 0;
  FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)v8);
LABEL_7:
  v9 = *v19;
  CSmartPtrWithNamedDestructor<_ASSEMBLY_IDENTITY,&void SxsDestroyAssemblyIdentity(_ASSEMBLY_IDENTITY *),CSmartPtrWithNamedDestructorHelper<_ASSEMBLY_IDENTITY,&void SxsDestroyAssemblyIdentity(_ASSEMBLY_IDENTITY *)>>::~CSmartPtrWithNamedDestructor<_ASSEMBLY_IDENTITY,&void SxsDestroyAssemblyIdentity(_ASSEMBLY_IDENTITY *),CSmartPtrWithNamedDestructorHelper<_ASSEMBLY_IDENTITY,&void SxsDestroyAssemblyIdentity(_ASSEMBLY_IDENTITY *)>>(&v11);
  CFnTracerWin32::~CFnTracerWin32((CFnTracerWin32 *)&v14);
  return v9;
}

```

## disassembly

```asm
0x180065520  mov     [rsp-18h+arg_8], rbx
0x180065525  push    rbp
0x180065526  push    rsi
0x180065527  push    rdi
0x180065528  mov     rbp, rsp
0x18006552b  sub     rsp, 80h
0x180065532  mov     rax, cs:__security_cookie
0x180065539  xor     rax, rsp
0x18006553c  mov     [rbp+var_8], rax
0x180065540  lea     rax, qword_180079028
0x180065547  movzx   ebx, dx
0x18006554a  mov     [rbp+var_28], rax
0x18006554e  mov     rsi, rcx
0x180065551  lea     rax, [rbp+var_40]
0x180065555  mov     [rbp+var_40], 0
0x18006555c  lea     rcx, [rbp+var_38]; this
0x180065560  mov     [rbp+var_10], rax
0x180065564  mov     rdi, r8
0x180065567  mov     [rbp+var_38], 1
0x18006556e  mov     [rbp+var_30], 0
0x180065576  mov     [rbp+var_20], 20737853h
0x18006557e  mov     [rbp+var_18], 0B60h
0x180065585  call    ?BaseEnter@CFrame@@QEAAXXZ; CFrame::BaseEnter(void)
0x18006558a  xor     ecx, ecx; dwErrCode
0x18006558c  mov     [rbp+var_50], 0
0x180065594  call    cs:__imp_SetLastError
0x18006559b  nop     dword ptr [rax+rax+00h]
0x1800655a0  mov     [rsp+80h+var_58], rdi; struct _SXS_NODE_INFO *
0x1800655a5  lea     r9, [rbp+var_50]; struct _ASSEMBLY_IDENTITY **
0x1800655a9  mov     [rsp+80h+var_60], ebx; unsigned int
0x1800655ad  mov     ebx, 2
0x1800655b2  mov     r8d, ebx; unsigned int
0x1800655b5  mov     [rbp+var_48], 1
0x1800655b9  call    ?SxspCreateAssemblyIdentityFromIdentityElement@@YAHKPEBU_ACTCTXCTB_PARSE_CONTEXT@@KPEAPEAU_ASSEMBLY_IDENTITY@@KPEBU_SXS_NODE_INFO@@@Z; SxspCreateAssemblyIdentityFromIdentityElement(ulong,_ACTCTXCTB_PARSE_CONTEXT const *,ulong,_ASSEMBLY_IDENTITY * *,ulong,_SXS_NODE_INFO const *)
0x1800655be  test    eax, eax
0x1800655c0  jnz     short loc_1800655DA
0x1800655c2  lea     rcx, off_180079008; struct _CALL_SITE_INFO *
0x1800655c9  mov     rax, [rbp+var_10]
0x1800655cd  mov     dword ptr [rax], 0
0x1800655d3  call    ?FusionpTraceWin32LastErrorFailure@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailure(_CALL_SITE_INFO const &)
0x1800655d8  jmp     short loc_180065621
0x1800655da  xor     ecx, ecx; dwErrCode
0x1800655dc  call    cs:__imp_SetLastError
0x1800655e3  nop     dword ptr [rax+rax+00h]
0x1800655e8  mov     r9, [rbp+var_50]; struct _ASSEMBLY_IDENTITY *
0x1800655ec  mov     r8d, ebx; unsigned int
0x1800655ef  mov     edx, 3; unsigned int
0x1800655f4  mov     rcx, rsi; this
0x1800655f7  call    ?ValidateIdentity@CNodeFactory@@QEAAHKKPEBU_ASSEMBLY_IDENTITY@@@Z; CNodeFactory::ValidateIdentity(ulong,ulong,_ASSEMBLY_IDENTITY const *)
0x1800655fc  test    eax, eax
0x1800655fe  jnz     short loc_180065609
0x180065600  lea     rcx, off_180078FE8; "clientcore\\base\\win32\\fusion\\sxs\\n"...
0x180065607  jmp     short loc_1800655C9
0x180065609  xor     ecx, ecx; dwErrCode
0x18006560b  call    cs:__imp_SetLastError
0x180065612  nop     dword ptr [rax+rax+00h]
0x180065617  mov     rax, [rbp+var_10]
0x18006561b  mov     dword ptr [rax], 1
0x180065621  mov     rax, [rbp+var_10]
0x180065625  lea     rcx, [rbp+var_50]
0x180065629  mov     ebx, [rax]
0x18006562b  call    ??1?$CSmartPtrWithNamedDestructor@U_ASSEMBLY_IDENTITY@@$1?SxsDestroyAssemblyIdentity@@YAXPEAU1@@ZV?$CSmartPtrWithNamedDestructorHelper@U_ASSEMBLY_IDENTITY@@$1?SxsDestroyAssemblyIdentity@@YAXPEAU1@@Z@@@@QEAA@XZ; CSmartPtrWithNamedDestructor<_ASSEMBLY_IDENTITY,&SxsDestroyAssemblyIdentity(_ASSEMBLY_IDENTITY *),CSmartPtrWithNamedDestructorHelper<_ASSEMBLY_IDENTITY,&SxsDestroyAssemblyIdentity(_ASSEMBLY_IDENTITY *)>>::~CSmartPtrWithNamedDestructor<_ASSEMBLY_IDENTITY,&SxsDestroyAssemblyIdentity(_ASSEMBLY_IDENTITY *),CSmartPtrWithNamedDestructorHelper<_ASSEMBLY_IDENTITY,&SxsDestroyAssemblyIdentity(_ASSEMBLY_IDENTITY *)>>(void)
0x180065630  lea     rcx, [rbp+var_38]; this
0x180065634  call    ??1CFnTracerWin32@@QEAA@XZ; CFnTracerWin32::~CFnTracerWin32(void)
0x180065639  mov     eax, ebx
0x18006563b  mov     rcx, [rbp+var_8]
0x18006563f  xor     rcx, rsp; StackCookie
0x180065642  call    __security_check_cookie
0x180065647  mov     rbx, [rsp+80h+arg_8]
0x18006564f  add     rsp, 80h
0x180065656  pop     rdi
0x180065657  pop     rsi
0x180065658  pop     rbp
0x180065659  retn
```
