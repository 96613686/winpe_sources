# EdpHelpers::CanCallerAccessFileContents(IShellItem *)

- ea: `0x18002a05c`
- end: `0x18002a209`
- name: `?CanCallerAccessFileContents@EdpHelpers@@YAJPEAUIShellItem@@@Z`
- size: `429`
- prototype: `__int64 __fastcall(struct IShellItem *this, struct IShellItem *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180013a00`

## callees

- `0x180024a24`
- `0x18002a05c`
- `0x1800317d8`
- `0x180031e94`
- `0x1800352f8`
- `0x180036f50`
- `0x18003c824`
- `0x18003edd4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18002a0a3`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18002a0a3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002a0c4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002a0c4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002a1a6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002a1e3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002a1a6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002a1e3`
- `ext-ms-win-edputil-policy-l1-1-0!EdpGetIsManaged` at `0x18002a079`
- `ext-ms-win-edputil-policy-l1-1-0!EdpGetIsManaged` at `0x18002a079`
- `ext-ms-win-edputil-policy-l1-1-0!EdpGetContextForProcess` at `0x18002a0f6`
- `ext-ms-win-edputil-policy-l1-1-0!EdpGetContextForProcess` at `0x18002a0f6`
- `ext-ms-win-edputil-policy-l1-1-0!EdpIsContextExemptOrEnlightenedAllowed` at `0x18002a184`
- `ext-ms-win-edputil-policy-l1-1-0!EdpIsContextExemptOrEnlightenedAllowed` at `0x18002a184`
- `ext-ms-win-edputil-policy-l1-1-0!EdpCheckAccessForContext` at `0x18002a1b8`
- `ext-ms-win-edputil-policy-l1-1-0!EdpCheckAccessForContext` at `0x18002a1b8`
- `ext-ms-win-edputil-policy-l1-1-0!EdpFreeContext` at `0x18002a127`
- `ext-ms-win-edputil-policy-l1-1-0!EdpFreeContext` at `0x18002a127`

## pseudocode

```c
__int64 __fastcall EdpHelpers::CanCallerAccessFileContents(struct IShellItem *this, struct IShellItem *a2)
{
  __int64 v3; // rdx
  __int64 v4; // rcx
  DWORD ProcessId; // edi
  int CallingProcessHandle; // ebx
  char *v8; // rdx
  int ContextForProcess; // eax
  unsigned int v10; // ebx
  int EnterpriseId; // eax
  __int64 v12; // rdx
  HANDLE Process; // [rsp+20h] [rbp-38h] BYREF
  int v14; // [rsp+28h] [rbp-30h] BYREF
  LPVOID pv; // [rsp+30h] [rbp-28h] BYREF
  __int64 v16; // [rsp+38h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+20h]

  if ( !(unsigned int)EdpGetIsManaged(this, a2) )
    return 0;
  ProcessId = 0;
  Process = 0;
  CallingProcessHandle = CallerIdentity::GetCallingProcessHandle(v4, v3, &Process);
  if ( CallingProcessHandle >= 0 )
    ProcessId = GetProcessId(Process);
  v8 = (char *)Process;
  Process = 0;
  if ( (unsigned __int64)(v8 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v8);
  if ( CallingProcessHandle < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xDB,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\edphelpers.h",
      (const char *)(unsigned int)CallingProcessHandle,
      (int)Process);
    return 0;
  }
  v16 = 0;
  ContextForProcess = EdpGetContextForProcess(ProcessId, &v16);
  v10 = ContextForProcess;
  if ( ContextForProcess < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xE2,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\edphelpers.h",
      (const char *)(unsigned int)ContextForProcess);
    if ( v16 )
      EdpFreeContext(v16);
    return v10;
  }
  pv = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &pv,
    0);
  EnterpriseId = IShellItem_GetEnterpriseId(this, (unsigned __int16 **)&pv);
  v10 = EnterpriseId;
  if ( EnterpriseId < 0 )
  {
    v12 = 229;
LABEL_14:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\edphelpers.h",
      (const char *)(unsigned int)EnterpriseId);
    goto LABEL_24;
  }
  v14 = 0;
  EnterpriseId = EdpIsContextExemptOrEnlightenedAllowed(pv, v16, &v14);
  v10 = EnterpriseId;
  if ( EnterpriseId < 0 )
  {
    v12 = 232;
    goto LABEL_14;
  }
  if ( v14 == 1 )
  {
    if ( pv )
      CoTaskMemFree(pv);
    v10 = 0;
    goto LABEL_26;
  }
  EnterpriseId = EdpCheckAccessForContext(pv, v16, &v14);
  v10 = EnterpriseId;
  if ( EnterpriseId < 0 )
  {
    v12 = 239;
    goto LABEL_14;
  }
  v10 = v14 != 1 ? 0x80070005 : 0;
LABEL_24:
  if ( pv )
    CoTaskMemFree(pv);
LABEL_26:
  wil::details::unique_storage<wil::details::resource_policy<EDP_CONTEXT *,void (*)(EDP_CONTEXT *),&void EdpFreeContext(EDP_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,EDP_CONTEXT *,EDP_CONTEXT *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<EDP_CONTEXT *,void (*)(EDP_CONTEXT *),&void EdpFreeContext(EDP_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,EDP_CONTEXT *,EDP_CONTEXT *,0,std::nullptr_t>>(&v16);
  return v10;
}

```

## disassembly

```asm
0x18002a05c  push    rbp
0x18002a05e  push    rbx
0x18002a05f  push    rsi
0x18002a060  push    rdi
0x18002a061  mov     rbp, rsp
0x18002a064  sub     rsp, 58h
0x18002a068  mov     rax, cs:__security_cookie
0x18002a06f  xor     rax, rsp
0x18002a072  mov     [rbp+var_18], rax
0x18002a076  mov     rsi, rcx
0x18002a079  call    cs:__imp_EdpGetIsManaged
0x18002a07f  test    eax, eax
0x18002a081  jnz     short loc_18002A08A
0x18002a083  xor     eax, eax
0x18002a085  jmp     loc_18002A1F4
0x18002a08a  xor     edi, edi
0x18002a08c  lea     r8, [rbp+Process]
0x18002a090  mov     [rbp+Process], rdi
0x18002a094  call    ?GetCallingProcessHandle@CallerIdentity@@YAJKW4RUNTIMEBROKER_CALLERIDENTITY_CHECK@@PEAPEAX@Z; CallerIdentity::GetCallingProcessHandle(ulong,RUNTIMEBROKER_CALLERIDENTITY_CHECK,void * *)
0x18002a099  mov     ebx, eax
0x18002a09b  test    eax, eax
0x18002a09d  js      short loc_18002A0AB
0x18002a09f  mov     rcx, [rbp+Process]; Process
0x18002a0a3  call    cs:__imp_GetProcessId
0x18002a0a9  mov     edi, eax
0x18002a0ab  mov     rdx, [rbp+Process]
0x18002a0af  mov     [rbp+Process], 0
0x18002a0b7  lea     rcx, [rdx-1]
0x18002a0bb  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18002a0bf  ja      short loc_18002A0CA
0x18002a0c1  mov     rcx, rdx; hObject
0x18002a0c4  call    cs:__imp_CloseHandle
0x18002a0ca  test    ebx, ebx
0x18002a0cc  jns     short loc_18002A0E8
0x18002a0ce  mov     rcx, [rbp+20h]; this
0x18002a0d2  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\shell\\inc\\priva"...
0x18002a0d9  mov     r9d, ebx; char *
0x18002a0dc  mov     edx, 0DBh; void *
0x18002a0e1  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002a0e6  jmp     short loc_18002A083
0x18002a0e8  lea     rdx, [rbp+var_20]
0x18002a0ec  mov     [rbp+var_20], 0
0x18002a0f4  mov     ecx, edi
0x18002a0f6  call    cs:__imp_EdpGetContextForProcess
0x18002a0fc  mov     ebx, eax
0x18002a0fe  test    eax, eax
0x18002a100  jns     short loc_18002A132
0x18002a102  mov     rcx, [rbp+20h]
0x18002a106  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\shell\\inc\\priva"...
0x18002a10d  mov     r9d, eax
0x18002a110  mov     edx, 0E2h
0x18002a115  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002a11a  mov     rcx, [rbp+var_20]
0x18002a11e  test    rcx, rcx
0x18002a121  jz      loc_18002A1F2
0x18002a127  call    cs:__imp_EdpFreeContext
0x18002a12d  jmp     loc_18002A1F2
0x18002a132  xor     edx, edx
0x18002a134  mov     [rbp+pv], 0
0x18002a13c  lea     rcx, [rbp+pv]
0x18002a140  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18002a145  lea     rdx, [rbp+pv]; unsigned __int16 **
0x18002a149  mov     rcx, rsi; struct IShellItem *
0x18002a14c  call    ?IShellItem_GetEnterpriseId@@YAJPEAUIShellItem@@PEAPEAG@Z; IShellItem_GetEnterpriseId(IShellItem *,ushort * *)
0x18002a151  mov     ebx, eax
0x18002a153  test    eax, eax
0x18002a155  jns     short loc_18002A171
0x18002a157  mov     edx, 0E5h
0x18002a15c  mov     rcx, [rbp+20h]
0x18002a160  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\shell\\inc\\priva"...
0x18002a167  mov     r9d, eax
0x18002a16a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002a16f  jmp     short loc_18002A1DA
0x18002a171  mov     rdx, [rbp+var_20]
0x18002a175  lea     r8, [rbp+var_30]
0x18002a179  mov     rcx, [rbp+pv]
0x18002a17d  mov     [rbp+var_30], 0
0x18002a184  call    cs:__imp_EdpIsContextExemptOrEnlightenedAllowed
0x18002a18a  mov     ebx, eax
0x18002a18c  test    eax, eax
0x18002a18e  jns     short loc_18002A197
0x18002a190  mov     edx, 0E8h
0x18002a195  jmp     short loc_18002A15C
0x18002a197  cmp     [rbp+var_30], 1
0x18002a19b  mov     rcx, [rbp+pv]; pv
0x18002a19f  jnz     short loc_18002A1B0
0x18002a1a1  test    rcx, rcx
0x18002a1a4  jz      short loc_18002A1AC
0x18002a1a6  call    cs:__imp_CoTaskMemFree
0x18002a1ac  xor     ebx, ebx
0x18002a1ae  jmp     short loc_18002A1E9
0x18002a1b0  mov     rdx, [rbp+var_20]
0x18002a1b4  lea     r8, [rbp+var_30]
0x18002a1b8  call    cs:__imp_EdpCheckAccessForContext
0x18002a1be  mov     ebx, eax
0x18002a1c0  test    eax, eax
0x18002a1c2  jns     short loc_18002A1CB
0x18002a1c4  mov     edx, 0EFh
0x18002a1c9  jmp     short loc_18002A15C
0x18002a1cb  mov     eax, [rbp+var_30]
0x18002a1ce  dec     eax
0x18002a1d0  neg     eax
0x18002a1d2  sbb     ebx, ebx
0x18002a1d4  and     ebx, 80070005h
0x18002a1da  mov     rcx, [rbp+pv]; pv
0x18002a1de  test    rcx, rcx
0x18002a1e1  jz      short loc_18002A1E9
0x18002a1e3  call    cs:__imp_CoTaskMemFree
0x18002a1e9  lea     rcx, [rbp+var_20]
0x18002a1ed  call    ??1?$unique_storage@U?$resource_policy@PEAUEDP_CONTEXT@@P6AXPEAU1@@Z$1?EdpFreeContext@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<EDP_CONTEXT *,void (*)(EDP_CONTEXT *),&EdpFreeContext(EDP_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,EDP_CONTEXT *,EDP_CONTEXT *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<EDP_CONTEXT *,void (*)(EDP_CONTEXT *),&EdpFreeContext(EDP_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,EDP_CONTEXT *,EDP_CONTEXT *,0,std::nullptr_t>>(void)
0x18002a1f2  mov     eax, ebx
0x18002a1f4  mov     rcx, [rbp+var_18]
0x18002a1f8  xor     rcx, rsp; StackCookie
0x18002a1fb  call    __security_check_cookie
0x18002a200  add     rsp, 58h
0x18002a204  pop     rdi
0x18002a205  pop     rsi
0x18002a206  pop     rbx
0x18002a207  pop     rbp
0x18002a208  retn
```
