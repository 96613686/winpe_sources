# LOG_SVC_ADMIN::InitializeConfigSystem(void)

- ea: `0x18000be20`
- end: `0x18000bfb8`
- name: `?InitializeConfigSystem@LOG_SVC_ADMIN@@AEAAJXZ`
- size: `408`
- prototype: `__int64 __fastcall(LOG_SVC_ADMIN *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000bfc0`

## callees

- `0x180001008`
- `0x18000be20`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000be6e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000be6e`
- `OLEAUT32!__imp_SysAllocString` at `0x18000bec6`
- `OLEAUT32!__imp_SysAllocString` at `0x18000bec6`
- `OLEAUT32!__imp_SysFreeString` at `0x18000bf6a`
- `OLEAUT32!__imp_SysFreeString` at `0x18000bf6a`
- `OLEAUT32!__imp_VariantInit` at `0x18000be41`
- `OLEAUT32!__imp_VariantInit` at `0x18000be41`
- `OLEAUT32!__imp_VariantClear` at `0x18000bf5c`
- `OLEAUT32!__imp_VariantClear` at `0x18000bf5c`
- `iisutil!PuDbgPrintError` at `0x18000beb4`
- `iisutil!PuDbgPrintError` at `0x18000beb4`

## string_xrefs

- `0x18000bead`: `servercommon\inetsrv\iis\iisrearc\core\ap\logsvc\dll\logsvcadmin.cpp`
- `0x18000be90`: `Could not initialize app host config reader\n`
- `0x18000be9c`: `LOG_SVC_ADMIN::InitializeConfigSystem`
- `0x18000bebf`: `pathMapper`

## pseudocode

```c
__int64 __fastcall LOG_SVC_ADMIN::InitializeConfigSystem(LOG_SVC_ADMIN *this)
{
  __int64 **v2; // r14
  HRESULT Instance; // ebx
  OLECHAR *v4; // rdi
  _DWORD *v5; // rcx
  __int64 *v6; // rcx
  __int64 v7; // rax
  __int64 v8; // rcx
  VARIANTARG pvarg; // [rsp+30h] [rbp-68h] BYREF
  VARIANTARG v11; // [rsp+50h] [rbp-48h] BYREF

  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  v2 = (__int64 **)((char *)this + 16);
  pvarg.vt = 13;
  Instance = CoCreateInstance(&CLSID_AppHostAdminManager, 0, 1u, &IID_IAppHostAdminManager, (LPVOID *)this + 2);
  if ( Instance >= 0 )
  {
    v4 = SysAllocString(L"pathMapper");
    if ( v4
      && ((v5 = operator new(0x10u)) == 0
        ? (v5 = 0)
        : (_DWORD *)(v5[2] = 1, *(_QWORD *)v5 = &LOG_SVC_CONFIG_PATH_MAPPER::`vftable'),
          (*((_QWORD *)this + 3) = v5) != 0) )
    {
      (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v5 + 8LL))(v5);
      v6 = *v2;
      pvarg.llVal = *((_QWORD *)this + 3);
      v7 = *v6;
      v11 = pvarg;
      Instance = (*(__int64 (__fastcall **)(__int64 *, OLECHAR *, VARIANTARG *))(v7 + 40))(v6, v4, &v11);
    }
    else
    {
      Instance = -2147024882;
    }
  }
  else
  {
    v4 = 0;
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\logsvc\\dll\\logsvcadmin.cpp",
        775,
        "LOG_SVC_ADMIN::InitializeConfigSystem",
        Instance,
        "Could not initialize app host config reader\n");
  }
  VariantClear(&pvarg);
  if ( v4 )
    SysFreeString(v4);
  if ( Instance < 0 )
  {
    v8 = *((_QWORD *)this + 3);
    if ( v8 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
      *((_QWORD *)this + 3) = 0;
    }
    if ( *v2 )
    {
      (*(void (__fastcall **)(__int64 *))(**v2 + 16))(*v2);
      *v2 = 0;
    }
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x18000be20  push    rbx
0x18000be22  push    rsi
0x18000be23  push    rdi
0x18000be24  push    r14
0x18000be26  sub     rsp, 78h
0x18000be2a  mov     rsi, rcx
0x18000be2d  xorps   xmm0, xmm0
0x18000be30  xor     eax, eax
0x18000be32  lea     rcx, [rsp+98h+pvarg]; pvarg
0x18000be37  movups  xmmword ptr [rsp+98h+pvarg], xmm0
0x18000be3c  mov     qword ptr [rsp+98h+pvarg+10h], rax
0x18000be41  call    cs:__imp_VariantInit
0x18000be47  mov     eax, 0Dh
0x18000be4c  lea     r14, [rsi+10h]
0x18000be50  lea     r9, IID_IAppHostAdminManager; riid
0x18000be57  mov     word ptr [rsp+98h+pvarg], ax
0x18000be5c  xor     edx, edx; pUnkOuter
0x18000be5e  mov     [rsp+98h+ppv], r14; ppv
0x18000be63  lea     rcx, CLSID_AppHostAdminManager; rclsid
0x18000be6a  lea     r8d, [rax-0Ch]; dwClsContext
0x18000be6e  call    cs:__imp_CoCreateInstance
0x18000be74  mov     ebx, eax
0x18000be76  test    eax, eax
0x18000be78  jns     short loc_18000BEBF
0x18000be7a  xor     edi, edi
0x18000be7c  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18000be83  jz      loc_18000BF57
0x18000be89  mov     rcx, cs:g_pDebug
0x18000be90  lea     rax, aCouldNotInitia; "Could not initialize app host config re"...
0x18000be97  mov     [rsp+98h+var_70], rax
0x18000be9c  lea     r9, aLogSvcAdminIni; "LOG_SVC_ADMIN::InitializeConfigSystem"
0x18000bea3  mov     r8d, 307h
0x18000bea9  mov     dword ptr [rsp+98h+ppv], ebx
0x18000bead  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18000beb4  call    cs:__imp_PuDbgPrintError
0x18000beba  jmp     loc_18000BF57
0x18000bebf  lea     rcx, aPathmapper; "pathMapper"
0x18000bec6  call    cs:__imp_SysAllocString
0x18000becc  mov     rdi, rax
0x18000becf  test    rax, rax
0x18000bed2  jnz     short loc_18000BEDB
0x18000bed4  mov     ebx, 8007000Eh
0x18000bed9  jmp     short loc_18000BF57
0x18000bedb  mov     ecx, 10h; Size
0x18000bee0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000bee5  mov     [rsp+98h+arg_0], rax
0x18000beed  mov     rcx, rax
0x18000bef0  test    rax, rax
0x18000bef3  jz      short loc_18000BF08
0x18000bef5  lea     rax, ??_7LOG_SVC_CONFIG_PATH_MAPPER@@6B@; const LOG_SVC_CONFIG_PATH_MAPPER::`vftable'
0x18000befc  mov     dword ptr [rcx+8], 1
0x18000bf03  mov     [rcx], rax
0x18000bf06  jmp     short loc_18000BF0A
0x18000bf08  xor     ecx, ecx
0x18000bf0a  mov     [rsi+18h], rcx
0x18000bf0e  test    rcx, rcx
0x18000bf11  jz      short loc_18000BED4
0x18000bf13  mov     rax, [rcx]
0x18000bf16  mov     rax, [rax+8]
0x18000bf1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bf1f  mov     rax, [rsi+18h]
0x18000bf23  lea     r8, [rsp+98h+var_48]
0x18000bf28  mov     rcx, [r14]
0x18000bf2b  mov     rdx, rdi
0x18000bf2e  movsd   xmm1, qword ptr [rsp+98h+pvarg+10h]
0x18000bf34  mov     qword ptr [rsp+98h+pvarg+8], rax
0x18000bf39  movups  xmm0, xmmword ptr [rsp+98h+pvarg]
0x18000bf3e  mov     rax, [rcx]
0x18000bf41  movsd   [rsp+98h+var_38], xmm1
0x18000bf47  movaps  [rsp+98h+var_48], xmm0
0x18000bf4c  mov     rax, [rax+28h]
0x18000bf50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bf55  mov     ebx, eax
0x18000bf57  lea     rcx, [rsp+98h+pvarg]; pvarg
0x18000bf5c  call    cs:__imp_VariantClear
0x18000bf62  test    rdi, rdi
0x18000bf65  jz      short loc_18000BF70
0x18000bf67  mov     rcx, rdi; bstrString
0x18000bf6a  call    cs:__imp_SysFreeString
0x18000bf70  test    ebx, ebx
0x18000bf72  jns     short loc_18000BFAC
0x18000bf74  mov     rcx, [rsi+18h]
0x18000bf78  test    rcx, rcx
0x18000bf7b  jz      short loc_18000BF91
0x18000bf7d  mov     rax, [rcx]
0x18000bf80  mov     rax, [rax+10h]
0x18000bf84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bf89  mov     qword ptr [rsi+18h], 0
0x18000bf91  mov     rcx, [r14]
0x18000bf94  test    rcx, rcx
0x18000bf97  jz      short loc_18000BFAC
0x18000bf99  mov     rax, [rcx]
0x18000bf9c  mov     rax, [rax+10h]
0x18000bfa0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bfa5  mov     qword ptr [r14], 0
0x18000bfac  mov     eax, ebx
0x18000bfae  add     rsp, 78h
0x18000bfb2  pop     r14
0x18000bfb4  pop     rdi
0x18000bfb5  pop     rsi
0x18000bfb6  pop     rbx
0x18000bfb7  retn
```
