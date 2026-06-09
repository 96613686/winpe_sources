# IsProcessEDPExemptOrEnlightened(void *)

- ea: `0x180047568`
- end: `0x180047615`
- name: `?IsProcessEDPExemptOrEnlightened@@YA_NPEAX@Z`
- size: `173`
- prototype: `bool __fastcall(void *)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, service_task`

## callers

- `0x18000a300`
- `0x18002af34`

## callees

- `0x1800034f8`
- `0x18001f73c`
- `0x18002d4f8`
- `0x180035830`
- `0x180047548`
- `0x180047568`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18004758e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18004758e`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180047586`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180047586`
- `ext-ms-win-edputil-policy-l1-1-0!EdpGetContextForProcess` at `0x1800475d7`
- `ext-ms-win-edputil-policy-l1-1-0!EdpGetContextForProcess` at `0x1800475d7`
- `ext-ms-win-edputil-policy-l1-1-0!EdpFreeContext` at `0x1800475b7`
- `ext-ms-win-edputil-policy-l1-1-0!EdpFreeContext` at `0x1800475b7`

## pseudocode

```c
bool __fastcall IsProcessEDPExemptOrEnlightened(void *a1)
{
  DWORD ProcessId; // eax
  DWORD v2; // edi
  _BYTE *v3; // rbx
  bool v4; // bl
  _BYTE v6[8]; // [rsp+20h] [rbp-28h] BYREF
  _BYTE *v7; // [rsp+28h] [rbp-20h] BYREF

  if ( a1 )
    ProcessId = GetProcessId(a1);
  else
    ProcessId = GetCurrentProcessId();
  v2 = ProcessId;
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v7);
  v3 = v7;
  if ( v7 )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)v6);
    EdpFreeContext(v3);
    wil::last_error_context::~last_error_context((wil::last_error_context *)v6);
  }
  v7 = 0;
  v4 = (int)EdpGetContextForProcess(v2, &v7) >= 0 && (*v7 & 3) != 0;
  wil::details::unique_storage<wil::details::resource_policy<EDP_CONTEXT *,void (*)(EDP_CONTEXT *),&void EdpFreeContext(EDP_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,EDP_CONTEXT *,EDP_CONTEXT *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<EDP_CONTEXT *,void (*)(EDP_CONTEXT *),&void EdpFreeContext(EDP_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,EDP_CONTEXT *,EDP_CONTEXT *,0,std::nullptr_t>>(&v7);
  return v4;
}

```

## disassembly

```asm
0x180047568  mov     [rsp+arg_8], rbx
0x18004756d  push    rdi
0x18004756e  sub     rsp, 40h
0x180047572  mov     rax, cs:__security_cookie
0x180047579  xor     rax, rsp
0x18004757c  mov     [rsp+48h+var_18], rax
0x180047581  test    rcx, rcx
0x180047584  jz      short loc_18004758E
0x180047586  call    cs:__imp_GetProcessId
0x18004758c  jmp     short loc_180047594
0x18004758e  call    cs:__imp_GetCurrentProcessId
0x180047594  lea     rcx, [rsp+48h+var_20]
0x180047599  mov     edi, eax
0x18004759b  call    ??0?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800475a0  mov     rbx, [rsp+48h+var_20]
0x1800475a5  test    rbx, rbx
0x1800475a8  jz      short loc_1800475C7
0x1800475aa  lea     rcx, [rsp+48h+var_28]; this
0x1800475af  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800475b4  mov     rcx, rbx
0x1800475b7  call    cs:__imp_EdpFreeContext
0x1800475bd  lea     rcx, [rsp+48h+var_28]; this
0x1800475c2  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800475c7  lea     rdx, [rsp+48h+var_20]
0x1800475cc  mov     [rsp+48h+var_20], 0
0x1800475d5  mov     ecx, edi
0x1800475d7  call    cs:__imp_EdpGetContextForProcess
0x1800475dd  test    eax, eax
0x1800475df  js      short loc_1800475EF
0x1800475e1  mov     rax, [rsp+48h+var_20]
0x1800475e6  test    byte ptr [rax], 3
0x1800475e9  jz      short loc_1800475EF
0x1800475eb  mov     bl, 1
0x1800475ed  jmp     short loc_1800475F1
0x1800475ef  xor     bl, bl
0x1800475f1  lea     rcx, [rsp+48h+var_20]
0x1800475f6  call    ??1?$unique_storage@U?$resource_policy@PEAUEDP_CONTEXT@@P6AXPEAU1@@Z$1?EdpFreeContext@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<EDP_CONTEXT *,void (*)(EDP_CONTEXT *),&EdpFreeContext(EDP_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,EDP_CONTEXT *,EDP_CONTEXT *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<EDP_CONTEXT *,void (*)(EDP_CONTEXT *),&EdpFreeContext(EDP_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,EDP_CONTEXT *,EDP_CONTEXT *,0,std::nullptr_t>>(void)
0x1800475fb  mov     al, bl
0x1800475fd  mov     rcx, [rsp+48h+var_18]
0x180047602  xor     rcx, rsp; StackCookie
0x180047605  call    __security_check_cookie
0x18004760a  mov     rbx, [rsp+48h+arg_8]
0x18004760f  add     rsp, 40h
0x180047613  pop     rdi
0x180047614  retn
```
