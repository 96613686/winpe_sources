# BINDING_TABLE::GetAppPoolsSection(INativeConfigurationSystem *,INativeConfigurationElement * *)

- ea: `0x180010508`
- end: `0x1800106d8`
- name: `?GetAppPoolsSection@BINDING_TABLE@@QEAAJPEAVINativeConfigurationSystem@@PEAPEAVINativeConfigurationElement@@@Z`
- size: `464`
- prototype: `__int64 __fastcall(BINDING_TABLE *__hidden this, struct INativeConfigurationSystem *, struct INativeConfigurationElement **)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000fad0`

## callees

- `0x180010508`
- `0x180017010`

## import_xrefs

- `iisutil!PuDbgPrintError` at `0x1800105ae`
- `iisutil!PuDbgPrintError` at `0x180010617`
- `iisutil!PuDbgPrintError` at `0x1800106a2`
- `iisutil!PuDbgPrintError` at `0x1800105ae`
- `iisutil!PuDbgPrintError` at `0x180010617`
- `iisutil!PuDbgPrintError` at `0x1800106a2`

## string_xrefs

- `0x18001059d`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3dt\binding_table.cxx`
- `0x180010607`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3dt\binding_table.cxx`
- `0x18001069b`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3dt\binding_table.cxx`

## pseudocode

```c
__int64 __fastcall BINDING_TABLE::GetAppPoolsSection(
        BINDING_TABLE *this,
        struct INativeConfigurationSystem *a2,
        struct INativeConfigurationElement **a3)
{
  unsigned int v3; // edi
  __int64 (__fastcall *v4)(struct INativeConfigurationSystem *, const wchar_t *, const wchar_t *, struct INativeConfigurationElement **, __int64 *, _QWORD, int); // rax
  int v5; // eax
  int v6; // ebx
  __int64 v7; // r8
  __int64 v9; // [rsp+40h] [rbp-10h] BYREF
  BINDING_TABLE *v10; // [rsp+70h] [rbp+20h] BYREF
  __int64 v11; // [rsp+78h] [rbp+28h] BYREF
  __int64 v12; // [rsp+88h] [rbp+38h] BYREF

  v10 = this;
  v3 = 0;
  v4 = *(__int64 (__fastcall **)(struct INativeConfigurationSystem *, const wchar_t *, const wchar_t *, struct INativeConfigurationElement **, __int64 *, _QWORD, int))(*(_QWORD *)a2 + 112LL);
  v11 = 0;
  LODWORD(v10) = 0;
  v12 = 0;
  v9 = 0;
  v5 = v4(a2, L"system.applicationHost/applicationPools", L"MACHINE/WEBROOT/APPHOST", a3, &v11, 0, 32);
  v6 = v5;
  if ( v5 < 0 )
  {
    v3 = v5;
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3dt\\binding_table.cxx",
        794,
        "BINDING_TABLE::GetAppPoolsSection",
        v5,
        " Failed to get section %S\n",
        L"system.applicationHost/applicationPools");
  }
  v7 = v11;
  if ( v11 )
  {
    v6 = (*(__int64 (__fastcall **)(__int64, BINDING_TABLE **))(*(_QWORD *)v11 + 32LL))(v11, &v10);
    if ( v6 >= 0 )
    {
      v6 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v11 + 40LL))(v11, &v12);
      if ( v6 >= 0 )
      {
        v6 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v11 + 24LL))(v11, &v9);
        if ( v6 < 0 && (g_dwDebugFlags & 0xF) != 0 )
          PuDbgPrintError(
            g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3dt\\binding_table.cxx",
            830,
            "BINDING_TABLE::GetAppPoolsSection",
            v6,
            " Failed to get error string for exception\n");
      }
      else if ( (g_dwDebugFlags & 0xF) != 0 )
      {
        PuDbgPrintError(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3dt\\binding_table.cxx",
          818,
          "BINDING_TABLE::GetAppPoolsSection",
          v6,
          " Failed to get error filename for exception in section %S\n",
          L"system.applicationHost/applicationPools");
      }
    }
    else if ( (g_dwDebugFlags & 0xF) != 0 )
    {
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3dt\\binding_table.cxx",
        806,
        "BINDING_TABLE::GetAppPoolsSection",
        v6,
        " Failed to get error line number for exception in section %S\n",
        L"system.applicationHost/applicationPools");
    }
    v7 = v11;
  }
  if ( !v3 )
    v3 = v6;
  if ( v7 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
  return v3;
}

```

## disassembly

```asm
0x180010508  mov     r11, rsp
0x18001050b  mov     [r11+18h], rbx
0x18001050f  mov     [r11+8], rcx
0x180010513  push    rbp
0x180010514  push    rdi
0x180010515  push    r13
0x180010517  mov     rbp, rsp
0x18001051a  sub     rsp, 50h
0x18001051e  mov     rax, [rdx]
0x180010521  lea     rcx, [rbp+arg_8]
0x180010525  xor     edi, edi
0x180010527  mov     dword ptr [rsp+50h+var_20], 20h ; ' '
0x18001052f  mov     r10, rdx
0x180010532  mov     [r11-40h], rdi
0x180010536  mov     [r11-48h], rcx
0x18001053a  lea     r13, aSystemApplicat_0; "system.applicationHost/applicationPools"
0x180010541  mov     rax, [rax+70h]
0x180010545  mov     r9, r8
0x180010548  lea     r8, aMachineWebroot; "MACHINE/WEBROOT/APPHOST"
0x18001054f  mov     [rbp+arg_8], 0
0x180010557  mov     rdx, r13
0x18001055a  mov     dword ptr [rbp+arg_0], edi
0x18001055d  mov     rcx, r10
0x180010560  mov     [rbp+arg_18], rdi
0x180010564  mov     [rbp+var_10], rdi
0x180010568  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001056d  mov     ebx, eax
0x18001056f  test    eax, eax
0x180010571  jns     short loc_1800105B4
0x180010573  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18001057a  mov     edi, eax
0x18001057c  jz      short loc_1800105B4
0x18001057e  mov     rcx, cs:g_pDebug
0x180010585  lea     rax, aFailedToGetSec; " Failed to get section %S\n"
0x18001058c  mov     [rsp+50h+var_20], r13
0x180010591  lea     r9, aBindingTableGe; "BINDING_TABLE::GetAppPoolsSection"
0x180010598  mov     [rsp+50h+var_28], rax
0x18001059d  lea     rdx, aServercommonIn_5; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x1800105a4  mov     r8d, 31Ah
0x1800105aa  mov     [rsp+50h+var_30], ebx
0x1800105ae  call    cs:__imp_PuDbgPrintError
0x1800105b4  mov     r8, [rbp+arg_8]
0x1800105b8  test    r8, r8
0x1800105bb  jz      loc_1800106AC
0x1800105c1  mov     rax, [r8]
0x1800105c4  lea     rdx, [rbp+arg_0]
0x1800105c8  mov     rcx, r8
0x1800105cb  mov     rax, [rax+20h]
0x1800105cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800105d4  mov     ebx, eax
0x1800105d6  test    eax, eax
0x1800105d8  jns     short loc_180010622
0x1800105da  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x1800105e1  jz      loc_1800106A8
0x1800105e7  lea     rax, aFailedToGetErr_1; " Failed to get error line number for ex"...
0x1800105ee  mov     r8d, 326h
0x1800105f4  mov     rcx, cs:g_pDebug
0x1800105fb  lea     r9, aBindingTableGe; "BINDING_TABLE::GetAppPoolsSection"
0x180010602  mov     [rsp+50h+var_20], r13
0x180010607  lea     rdx, aServercommonIn_5; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18001060e  mov     [rsp+50h+var_28], rax
0x180010613  mov     [rsp+50h+var_30], ebx
0x180010617  call    cs:__imp_PuDbgPrintError
0x18001061d  jmp     loc_1800106A8
0x180010622  mov     rcx, [rbp+arg_8]
0x180010626  lea     rdx, [rbp+arg_18]
0x18001062a  mov     rax, [rcx]
0x18001062d  mov     rax, [rax+28h]
0x180010631  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010636  mov     ebx, eax
0x180010638  test    eax, eax
0x18001063a  jns     short loc_180010654
0x18001063c  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180010643  jz      short loc_1800106A8
0x180010645  lea     rax, aFailedToGetErr_0; " Failed to get error filename for excep"...
0x18001064c  mov     r8d, 332h
0x180010652  jmp     short loc_1800105F4
0x180010654  mov     rcx, [rbp+arg_8]
0x180010658  lea     rdx, [rbp+var_10]
0x18001065c  mov     rax, [rcx]
0x18001065f  mov     rax, [rax+18h]
0x180010663  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010668  mov     ebx, eax
0x18001066a  test    eax, eax
0x18001066c  jns     short loc_1800106A8
0x18001066e  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180010675  jz      short loc_1800106A8
0x180010677  mov     rcx, cs:g_pDebug
0x18001067e  lea     rax, aFailedToGetErr; " Failed to get error string for excepti"...
0x180010685  mov     [rsp+50h+var_28], rax
0x18001068a  lea     r9, aBindingTableGe; "BINDING_TABLE::GetAppPoolsSection"
0x180010691  mov     r8d, 33Eh
0x180010697  mov     [rsp+50h+var_30], ebx
0x18001069b  lea     rdx, aServercommonIn_5; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x1800106a2  call    cs:__imp_PuDbgPrintError
0x1800106a8  mov     r8, [rbp+arg_8]
0x1800106ac  test    edi, edi
0x1800106ae  cmovz   edi, ebx
0x1800106b1  test    r8, r8
0x1800106b4  jz      short loc_1800106C5
0x1800106b6  mov     rcx, [r8]
0x1800106b9  mov     rax, [rcx+10h]
0x1800106bd  mov     rcx, r8
0x1800106c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800106c5  mov     rbx, [rsp+50h+arg_10]
0x1800106cd  mov     eax, edi
0x1800106cf  add     rsp, 50h
0x1800106d3  pop     r13
0x1800106d5  pop     rdi
0x1800106d6  pop     rbp
0x1800106d7  retn
```
