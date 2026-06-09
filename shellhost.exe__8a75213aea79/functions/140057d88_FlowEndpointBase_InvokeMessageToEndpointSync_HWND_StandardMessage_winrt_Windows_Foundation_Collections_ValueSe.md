# FlowEndpointBase::InvokeMessageToEndpointSync(HWND__ *,StandardMessage,winrt::Windows::Foundation::Collections::ValueSet const &)

- ea: `0x140057d88`
- end: `0x140057e2c`
- name: `?InvokeMessageToEndpointSync@FlowEndpointBase@@QEAA_NPEAUHWND__@@W4StandardMessage@@AEBUValueSet@Collections@Foundation@Windows@winrt@@@Z`
- size: `164`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x14005bd30`

## callees

- `0x1400505a0`
- `0x140057d88`
- `0x14005ec1c`

## import_xrefs

- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x140057df2`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x140057df2`
- `faultrep!ReportCoreHang` at `0x140057e13`
- `faultrep!ReportCoreHang` at `0x140057e13`

## pseudocode

```c
char __fastcall FlowEndpointBase::InvokeMessageToEndpointSync(__int64 a1, HWND a2, __int64 a3, __int64 a4)
{
  __int64 v6; // rcx
  HWND v7; // rsi
  char v8; // di
  DWORD WindowThreadProcessId; // eax
  DWORD v11; // [rsp+40h] [rbp+8h] BYREF
  DWORD dwProcessId; // [rsp+50h] [rbp+18h] BYREF

  dwProcessId = a3;
  v6 = *(unsigned int *)(a1 + 88);
  v7 = a2;
  if ( (_DWORD)v6 == -1 )
  {
    LOBYTE(a2) = 0;
    wil::init_once<_lambda_8e4368fb547587b2dd84ae7e04fbdf86_>(v6, a2);
    LODWORD(v6) = FlowEndpointBase::s_defaultTimeoutMs;
  }
  v8 = FlowEndpointBase::s_InvokeMessageToEndpointSync(*(_QWORD *)(a1 + 8), v7, a3, a4, a1 + 72, v6);
  if ( !v8 )
  {
    if ( *(_BYTE *)(a1 + 92) )
    {
      dwProcessId = 0;
      WindowThreadProcessId = GetWindowThreadProcessId(v7, &dwProcessId);
      if ( WindowThreadProcessId )
      {
        v11 = dwProcessId;
        ReportCoreHang(&v11, 1, WindowThreadProcessId, 0);
      }
    }
  }
  return v8;
}

```

## disassembly

```asm
0x140057d88  mov     [rsp+arg_8], rbx
0x140057d8d  mov     [rsp+arg_18], rsi
0x140057d92  mov     [rsp+dwProcessId], r8d
0x140057d97  push    rdi
0x140057d98  sub     rsp, 30h
0x140057d9c  mov     rbx, rcx
0x140057d9f  mov     rdi, r9
0x140057da2  mov     ecx, [rcx+58h]
0x140057da5  mov     rsi, rdx
0x140057da8  cmp     ecx, 0FFFFFFFFh
0x140057dab  jnz     short loc_140057DBA
0x140057dad  xor     dl, dl
0x140057daf  call    ??$init_once@V_lambda_8e4368fb547587b2dd84ae7e04fbdf86_@@@wil@@YA_NAEAT_RTL_RUN_ONCE@@V_lambda_8e4368fb547587b2dd84ae7e04fbdf86_@@@Z; wil::init_once<_lambda_8e4368fb547587b2dd84ae7e04fbdf86_>(_RTL_RUN_ONCE &,_lambda_8e4368fb547587b2dd84ae7e04fbdf86_)
0x140057db4  mov     ecx, cs:?s_defaultTimeoutMs@FlowEndpointBase@@1KA; ulong FlowEndpointBase::s_defaultTimeoutMs
0x140057dba  mov     [rsp+38h+var_10], ecx
0x140057dbe  lea     rax, [rbx+48h]
0x140057dc2  mov     rcx, [rbx+8]
0x140057dc6  mov     r9, rdi
0x140057dc9  mov     rdx, rsi
0x140057dcc  mov     [rsp+38h+var_18], rax
0x140057dd1  call    ?s_InvokeMessageToEndpointSync@FlowEndpointBase@@KA_NPEAUHWND__@@0W4StandardMessage@@AEBUValueSet@Collections@Foundation@Windows@winrt@@AEBUIPropertySetSerializer@Streams@Storage@78@K@Z; FlowEndpointBase::s_InvokeMessageToEndpointSync(HWND__ *,HWND__ *,StandardMessage,winrt::Windows::Foundation::Collections::ValueSet const &,winrt::Windows::Storage::Streams::IPropertySetSerializer const &,ulong)
0x140057dd6  mov     dil, al
0x140057dd9  test    al, al
0x140057ddb  jnz     short loc_140057E19
0x140057ddd  cmp     [rbx+5Ch], al
0x140057de0  jz      short loc_140057E19
0x140057de2  lea     rdx, [rsp+38h+dwProcessId]; lpdwProcessId
0x140057de7  mov     [rsp+38h+dwProcessId], 0
0x140057def  mov     rcx, rsi; hWnd
0x140057df2  call    cs:__imp_GetWindowThreadProcessId
0x140057df8  test    eax, eax
0x140057dfa  jz      short loc_140057E19
0x140057dfc  mov     ecx, [rsp+38h+dwProcessId]
0x140057e00  xor     r9d, r9d
0x140057e03  mov     [rsp+38h+arg_0], ecx
0x140057e07  mov     r8d, eax
0x140057e0a  lea     rcx, [rsp+38h+arg_0]
0x140057e0f  lea     edx, [r9+1]
0x140057e13  call    cs:__imp_ReportCoreHang
0x140057e19  mov     rbx, [rsp+38h+arg_8]
0x140057e1e  mov     al, dil
0x140057e21  mov     rsi, [rsp+38h+arg_18]
0x140057e26  add     rsp, 30h
0x140057e2a  pop     rdi
0x140057e2b  retn
```
