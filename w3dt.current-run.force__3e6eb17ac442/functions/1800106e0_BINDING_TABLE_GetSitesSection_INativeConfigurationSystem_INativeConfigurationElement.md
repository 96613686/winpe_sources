# BINDING_TABLE::GetSitesSection(INativeConfigurationSystem *,INativeConfigurationElement * *)

- ea: `0x1800106e0`
- end: `0x1800108b0`
- name: `?GetSitesSection@BINDING_TABLE@@QEAAJPEAVINativeConfigurationSystem@@PEAPEAVINativeConfigurationElement@@@Z`
- size: `464`
- prototype: `__int64 __fastcall(BINDING_TABLE *__hidden this, struct INativeConfigurationSystem *, struct INativeConfigurationElement **)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000fad0`

## callees

- `0x1800106e0`
- `0x180017010`

## import_xrefs

- `iisutil!PuDbgPrintError` at `0x180010786`
- `iisutil!PuDbgPrintError` at `0x1800107ef`
- `iisutil!PuDbgPrintError` at `0x18001087a`
- `iisutil!PuDbgPrintError` at `0x180010786`
- `iisutil!PuDbgPrintError` at `0x1800107ef`
- `iisutil!PuDbgPrintError` at `0x18001087a`

## string_xrefs

- `0x180010775`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3dt\binding_table.cxx`
- `0x1800107df`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3dt\binding_table.cxx`
- `0x180010873`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3dt\binding_table.cxx`

## pseudocode

```c
__int64 __fastcall BINDING_TABLE::GetSitesSection(
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
  v5 = v4(a2, L"system.applicationHost/sites", L"MACHINE/WEBROOT/APPHOST", a3, &v11, 0, 32);
  v6 = v5;
  if ( v5 < 0 )
  {
    v3 = v5;
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3dt\\binding_table.cxx",
        902,
        "BINDING_TABLE::GetSitesSection",
        v5,
        " Failed to get section %S\n",
        L"system.applicationHost/sites");
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
            938,
            "BINDING_TABLE::GetSitesSection",
            v6,
            " Failed to get error string for exception\n");
      }
      else if ( (g_dwDebugFlags & 0xF) != 0 )
      {
        PuDbgPrintError(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3dt\\binding_table.cxx",
          926,
          "BINDING_TABLE::GetSitesSection",
          v6,
          " Failed to get error filename for exception in section %S\n",
          L"system.applicationHost/sites");
      }
    }
    else if ( (g_dwDebugFlags & 0xF) != 0 )
    {
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3dt\\binding_table.cxx",
        914,
        "BINDING_TABLE::GetSitesSection",
        v6,
        " Failed to get error line number for exception in section %S\n",
        L"system.applicationHost/sites");
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
0x1800106e0  mov     r11, rsp
0x1800106e3  mov     [r11+18h], rbx
0x1800106e7  mov     [r11+8], rcx
0x1800106eb  push    rbp
0x1800106ec  push    rdi
0x1800106ed  push    r13
0x1800106ef  mov     rbp, rsp
0x1800106f2  sub     rsp, 50h
0x1800106f6  mov     rax, [rdx]
0x1800106f9  lea     rcx, [rbp+arg_8]
0x1800106fd  xor     edi, edi
0x1800106ff  mov     dword ptr [rsp+50h+var_20], 20h ; ' '
0x180010707  mov     r10, rdx
0x18001070a  mov     [r11-40h], rdi
0x18001070e  mov     [r11-48h], rcx
0x180010712  lea     r13, aSystemApplicat; "system.applicationHost/sites"
0x180010719  mov     rax, [rax+70h]
0x18001071d  mov     r9, r8
0x180010720  lea     r8, aMachineWebroot; "MACHINE/WEBROOT/APPHOST"
0x180010727  mov     [rbp+arg_8], 0
0x18001072f  mov     rdx, r13
0x180010732  mov     dword ptr [rbp+arg_0], edi
0x180010735  mov     rcx, r10
0x180010738  mov     [rbp+arg_18], rdi
0x18001073c  mov     [rbp+var_10], rdi
0x180010740  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010745  mov     ebx, eax
0x180010747  test    eax, eax
0x180010749  jns     short loc_18001078C
0x18001074b  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180010752  mov     edi, eax
0x180010754  jz      short loc_18001078C
0x180010756  mov     rcx, cs:g_pDebug
0x18001075d  lea     rax, aFailedToGetSec; " Failed to get section %S\n"
0x180010764  mov     [rsp+50h+var_20], r13
0x180010769  lea     r9, aBindingTableGe_0; "BINDING_TABLE::GetSitesSection"
0x180010770  mov     [rsp+50h+var_28], rax
0x180010775  lea     rdx, aServercommonIn_5; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18001077c  mov     r8d, 386h
0x180010782  mov     [rsp+50h+var_30], ebx
0x180010786  call    cs:__imp_PuDbgPrintError
0x18001078c  mov     r8, [rbp+arg_8]
0x180010790  test    r8, r8
0x180010793  jz      loc_180010884
0x180010799  mov     rax, [r8]
0x18001079c  lea     rdx, [rbp+arg_0]
0x1800107a0  mov     rcx, r8
0x1800107a3  mov     rax, [rax+20h]
0x1800107a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800107ac  mov     ebx, eax
0x1800107ae  test    eax, eax
0x1800107b0  jns     short loc_1800107FA
0x1800107b2  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x1800107b9  jz      loc_180010880
0x1800107bf  lea     rax, aFailedToGetErr_1; " Failed to get error line number for ex"...
0x1800107c6  mov     r8d, 392h
0x1800107cc  mov     rcx, cs:g_pDebug
0x1800107d3  lea     r9, aBindingTableGe_0; "BINDING_TABLE::GetSitesSection"
0x1800107da  mov     [rsp+50h+var_20], r13
0x1800107df  lea     rdx, aServercommonIn_5; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x1800107e6  mov     [rsp+50h+var_28], rax
0x1800107eb  mov     [rsp+50h+var_30], ebx
0x1800107ef  call    cs:__imp_PuDbgPrintError
0x1800107f5  jmp     loc_180010880
0x1800107fa  mov     rcx, [rbp+arg_8]
0x1800107fe  lea     rdx, [rbp+arg_18]
0x180010802  mov     rax, [rcx]
0x180010805  mov     rax, [rax+28h]
0x180010809  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001080e  mov     ebx, eax
0x180010810  test    eax, eax
0x180010812  jns     short loc_18001082C
0x180010814  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18001081b  jz      short loc_180010880
0x18001081d  lea     rax, aFailedToGetErr_0; " Failed to get error filename for excep"...
0x180010824  mov     r8d, 39Eh
0x18001082a  jmp     short loc_1800107CC
0x18001082c  mov     rcx, [rbp+arg_8]
0x180010830  lea     rdx, [rbp+var_10]
0x180010834  mov     rax, [rcx]
0x180010837  mov     rax, [rax+18h]
0x18001083b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010840  mov     ebx, eax
0x180010842  test    eax, eax
0x180010844  jns     short loc_180010880
0x180010846  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18001084d  jz      short loc_180010880
0x18001084f  mov     rcx, cs:g_pDebug
0x180010856  lea     rax, aFailedToGetErr; " Failed to get error string for excepti"...
0x18001085d  mov     [rsp+50h+var_28], rax
0x180010862  lea     r9, aBindingTableGe_0; "BINDING_TABLE::GetSitesSection"
0x180010869  mov     r8d, 3AAh
0x18001086f  mov     [rsp+50h+var_30], ebx
0x180010873  lea     rdx, aServercommonIn_5; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18001087a  call    cs:__imp_PuDbgPrintError
0x180010880  mov     r8, [rbp+arg_8]
0x180010884  test    edi, edi
0x180010886  cmovz   edi, ebx
0x180010889  test    r8, r8
0x18001088c  jz      short loc_18001089D
0x18001088e  mov     rcx, [r8]
0x180010891  mov     rax, [rcx+10h]
0x180010895  mov     rcx, r8
0x180010898  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001089d  mov     rbx, [rsp+50h+arg_10]
0x1800108a5  mov     eax, edi
0x1800108a7  add     rsp, 50h
0x1800108ab  pop     r13
0x1800108ad  pop     rdi
0x1800108ae  pop     rbp
0x1800108af  retn
```
