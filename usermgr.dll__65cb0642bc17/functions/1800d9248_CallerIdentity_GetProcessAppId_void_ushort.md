# CallerIdentity::GetProcessAppId(void *,ushort * *)

- ea: `0x1800d9248`
- end: `0x1800d93d0`
- name: `?GetProcessAppId@CallerIdentity@@YAJPEAXPEAPEAG@Z`
- size: `392`
- prototype: `__int64 __fastcall(HANDLE ProcessHandle, void *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800d8eb0`
- `0x1800d9034`

## callees

- `0x1800088e8`
- `0x18004a9cc`
- `0x180067398`
- `0x1800d1e7c`
- `0x1800d8e50`
- `0x1800d8f24`
- `0x1800d9248`
- `0x1800d93d8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d932c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d9369`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d93b0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d932c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d9369`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d93b0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800d92ac`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800d92ac`

## pseudocode

```c
__int64 __fastcall CallerIdentity::GetProcessAppId(HANDLE ProcessHandle, _QWORD *a2, unsigned __int16 **a3)
{
  void **v5; // r8
  signed int v6; // edi
  const struct _TOKEN_SECURITY_ATTRIBUTE_V1 **v7; // r9
  __int64 v8; // rdx
  __int64 v9; // rdx
  SIZE_T v10; // rcx
  int v11; // eax
  void *v12; // rcx
  LPVOID v13; // rbx
  unsigned int AppUserModelId; // eax
  unsigned __int16 *v16; // [rsp+20h] [rbp-20h]
  unsigned __int16 *v17; // [rsp+20h] [rbp-20h]
  unsigned int v18; // [rsp+20h] [rbp-20h]
  struct _TOKEN_SECURITY_ATTRIBUTES_INFORMATION *v19[2]; // [rsp+30h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  HANDLE hObject; // [rsp+68h] [rbp+28h] BYREF
  LPVOID pv; // [rsp+70h] [rbp+30h] BYREF

  *a2 = 0;
  *(_OWORD *)v19 = 0;
  ARI::ProcessToken::AutoSysAppId::Close((ARI::ProcessToken::AutoSysAppId *)v19);
  hObject = 0;
  v6 = ARI::ProcessToken::SysAppId::OpenTokenForProcess(ProcessHandle, &hObject, v5);
  if ( !v6 )
  {
    v6 = ARI::ProcessToken::SysAppId::Open(hObject, v19, &v19[1], v7);
    if ( hObject != (HANDLE)-4LL )
      CloseHandle(hObject);
  }
  if ( v6 > 0 )
    v6 = (unsigned __int16)v6 | 0x80070000;
  if ( v6 != -2147023728 && v6 != -2147024891 )
  {
    if ( v6 < 0 )
    {
      v8 = 165;
LABEL_12:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v8,
        (unsigned int)"onecore\\shell\\lib\\calleridentity\\calleridentity.cpp",
        (const char *)(unsigned int)v6,
        (int)v16);
      goto LABEL_19;
    }
    LODWORD(hObject) = 0;
    if ( (unsigned int)ARI::ProcessToken::SysAppId::GetAppUserModelId(v19[1], 0, (unsigned int)&hObject, 0, v16) != 122 )
    {
      v6 = -2147418113;
      v8 = 168;
      goto LABEL_12;
    }
    pv = 0;
    CoTaskMemFree(0);
    v11 = _AllocStringWorker<CTCoAllocPolicy>(v10, v9, 0, (unsigned int)hObject, (__int64)v16, (wchar_t **)&pv);
    v6 = v11;
    if ( v11 >= 0 )
    {
      v13 = pv;
      AppUserModelId = ARI::ProcessToken::SysAppId::GetAppUserModelId(
                         v19[1],
                         (const struct _TOKEN_SECURITY_ATTRIBUTE_V1 *)(unsigned int)hObject,
                         (unsigned int)&hObject,
                         (unsigned int *)pv,
                         v17);
      if ( !AppUserModelId )
      {
        *a2 = v13;
        CoTaskMemFree(0);
        v6 = 0;
        goto LABEL_19;
      }
      v6 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0xAC,
             (unsigned int)"onecore\\shell\\lib\\calleridentity\\calleridentity.cpp",
             (const char *)AppUserModelId,
             v18);
      v12 = v13;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xAB,
        (unsigned int)"onecore\\shell\\lib\\calleridentity\\calleridentity.cpp",
        (const char *)(unsigned int)v11,
        (int)v17);
      v12 = pv;
    }
    CoTaskMemFree(v12);
  }
LABEL_19:
  ARI::ProcessToken::AutoSysAppId::Close((ARI::ProcessToken::AutoSysAppId *)v19);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800d9248  mov     [rsp-18h+arg_0], rbx
0x1800d924d  push    rbp
0x1800d924e  push    rsi
0x1800d924f  push    rdi
0x1800d9250  mov     rbp, rsp
0x1800d9253  sub     rsp, 40h
0x1800d9257  mov     rbx, rcx
0x1800d925a  mov     qword ptr [rdx], 0
0x1800d9261  xorps   xmm0, xmm0
0x1800d9264  lea     rcx, [rbp+var_10]; this
0x1800d9268  movdqu  xmmword ptr [rbp+var_10], xmm0
0x1800d926d  mov     rsi, rdx
0x1800d9270  call    ?Close@AutoSysAppId@ProcessToken@ARI@@QEAAJXZ; ARI::ProcessToken::AutoSysAppId::Close(void)
0x1800d9275  lea     rdx, [rbp+hObject]; TokenHandle
0x1800d9279  mov     [rbp+hObject], 0
0x1800d9281  mov     rcx, rbx; ProcessHandle
0x1800d9284  call    ?OpenTokenForProcess@SysAppId@ProcessToken@ARI@@YAJPEAXPEAPEAX@Z; ARI::ProcessToken::SysAppId::OpenTokenForProcess(void *,void * *)
0x1800d9289  mov     edi, eax
0x1800d928b  test    eax, eax
0x1800d928d  jnz     short loc_1800D92B2
0x1800d928f  mov     rcx, [rbp+hObject]; TokenHandle
0x1800d9293  lea     r8, [rbp+var_10+8]; struct _TOKEN_SECURITY_ATTRIBUTES_INFORMATION **
0x1800d9297  lea     rdx, [rbp+var_10]; void *
0x1800d929b  call    ?Open@SysAppId@ProcessToken@ARI@@YAJPEAXPEAPEAU_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@PEAPEBU_TOKEN_SECURITY_ATTRIBUTE_V1@@PEA_N@Z; ARI::ProcessToken::SysAppId::Open(void *,_TOKEN_SECURITY_ATTRIBUTES_INFORMATION * *,_TOKEN_SECURITY_ATTRIBUTE_V1 const * *,bool *)
0x1800d92a0  mov     rcx, [rbp+hObject]; hObject
0x1800d92a4  mov     edi, eax
0x1800d92a6  cmp     rcx, 0FFFFFFFFFFFFFFFCh
0x1800d92aa  jz      short loc_1800D92B2
0x1800d92ac  call    cs:__imp_CloseHandle
0x1800d92b2  test    edi, edi
0x1800d92b4  jle     short loc_1800D92BF
0x1800d92b6  movzx   edi, di
0x1800d92b9  or      edi, 80070000h
0x1800d92bf  cmp     edi, 80070490h
0x1800d92c5  jz      loc_1800D93B8
0x1800d92cb  cmp     edi, 80070005h
0x1800d92d1  jz      loc_1800D93B8
0x1800d92d7  test    edi, edi
0x1800d92d9  jns     short loc_1800D92E2
0x1800d92db  mov     edx, 0A5h
0x1800d92e0  jmp     short loc_1800D930A
0x1800d92e2  mov     rcx, [rbp+var_10+8]; this
0x1800d92e6  lea     r8, [rbp+hObject]; unsigned int
0x1800d92ea  xor     r9d, r9d; unsigned int *
0x1800d92ed  mov     dword ptr [rbp+hObject], 0
0x1800d92f4  xor     edx, edx; struct _TOKEN_SECURITY_ATTRIBUTE_V1 *
0x1800d92f6  call    ?GetAppUserModelId@SysAppId@ProcessToken@ARI@@YAJPEBU_TOKEN_SECURITY_ATTRIBUTE_V1@@IPEAIPEAG@Z; ARI::ProcessToken::SysAppId::GetAppUserModelId(_TOKEN_SECURITY_ATTRIBUTE_V1 const *,uint,uint *,ushort *)
0x1800d92fb  cmp     eax, 7Ah ; 'z'
0x1800d92fe  jz      short loc_1800D9322
0x1800d9300  mov     edi, 8000FFFFh
0x1800d9305  mov     edx, 0A8h; void *
0x1800d930a  mov     rcx, [rbp+18h]; this
0x1800d930e  lea     r8, aOnecoreShellLi; "onecore\\shell\\lib\\calleridentity\\ca"...
0x1800d9315  mov     r9d, edi; char *
0x1800d9318  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d931d  jmp     loc_1800D93B8
0x1800d9322  xor     ecx, ecx; pv
0x1800d9324  mov     [rbp+pv], 0
0x1800d932c  call    cs:__imp_CoTaskMemFree
0x1800d9332  mov     r9d, dword ptr [rbp+hObject]
0x1800d9336  lea     rax, [rbp+pv]
0x1800d933a  xor     r8d, r8d
0x1800d933d  mov     [rsp+40h+var_18], rax
0x1800d9342  call    ??$_AllocStringWorker@VCTCoAllocPolicy@@@@YAJPEAXKPEBG_K2PEAPEAG@Z; _AllocStringWorker<CTCoAllocPolicy>(void *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort * *)
0x1800d9347  mov     edi, eax
0x1800d9349  test    eax, eax
0x1800d934b  jns     short loc_1800D9371
0x1800d934d  mov     rcx, [rbp+18h]; this
0x1800d9351  lea     r8, aOnecoreShellLi; "onecore\\shell\\lib\\calleridentity\\ca"...
0x1800d9358  mov     r9d, eax; char *
0x1800d935b  mov     edx, 0ABh; void *
0x1800d9360  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d9365  mov     rcx, [rbp+pv]; pv
0x1800d9369  call    cs:__imp_CoTaskMemFree
0x1800d936f  jmp     short loc_1800D93B8
0x1800d9371  mov     rbx, [rbp+pv]
0x1800d9375  lea     r8, [rbp+hObject]; unsigned int
0x1800d9379  mov     edx, dword ptr [rbp+hObject]; struct _TOKEN_SECURITY_ATTRIBUTE_V1 *
0x1800d937c  mov     r9, rbx; unsigned int *
0x1800d937f  mov     rcx, [rbp+var_10+8]; this
0x1800d9383  call    ?GetAppUserModelId@SysAppId@ProcessToken@ARI@@YAJPEBU_TOKEN_SECURITY_ATTRIBUTE_V1@@IPEAIPEAG@Z; ARI::ProcessToken::SysAppId::GetAppUserModelId(_TOKEN_SECURITY_ATTRIBUTE_V1 const *,uint,uint *,ushort *)
0x1800d9388  test    eax, eax
0x1800d938a  jz      short loc_1800D93AB
0x1800d938c  mov     rcx, [rbp+18h]; this
0x1800d9390  lea     r8, aOnecoreShellLi; "onecore\\shell\\lib\\calleridentity\\ca"...
0x1800d9397  mov     r9d, eax; char *
0x1800d939a  mov     edx, 0ACh; void *
0x1800d939f  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800d93a4  mov     edi, eax
0x1800d93a6  mov     rcx, rbx
0x1800d93a9  jmp     short loc_1800D9369
0x1800d93ab  xor     ecx, ecx; pv
0x1800d93ad  mov     [rsi], rbx
0x1800d93b0  call    cs:__imp_CoTaskMemFree
0x1800d93b6  xor     edi, edi
0x1800d93b8  lea     rcx, [rbp+var_10]; this
0x1800d93bc  call    ?Close@AutoSysAppId@ProcessToken@ARI@@QEAAJXZ; ARI::ProcessToken::AutoSysAppId::Close(void)
0x1800d93c1  mov     rbx, [rsp+40h+arg_0]
0x1800d93c6  mov     eax, edi
0x1800d93c8  add     rsp, 40h
0x1800d93cc  pop     rdi
0x1800d93cd  pop     rsi
0x1800d93ce  pop     rbp
0x1800d93cf  retn
```
