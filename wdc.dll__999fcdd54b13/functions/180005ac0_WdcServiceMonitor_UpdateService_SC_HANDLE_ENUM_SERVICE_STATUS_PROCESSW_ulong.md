# WdcServiceMonitor::UpdateService(SC_HANDLE__ *,_ENUM_SERVICE_STATUS_PROCESSW *,ulong)

- ea: `0x180005ac0`
- end: `0x180005fe4`
- name: `?UpdateService@WdcServiceMonitor@@AEAAJPEAUSC_HANDLE__@@PEAU_ENUM_SERVICE_STATUS_PROCESSW@@K@Z`
- size: `1316`
- prototype: `__int64 __fastcall(WdcServiceMonitor *__hidden this, struct SC_HANDLE__ *, struct _ENUM_SERVICE_STATUS_PROCESSW *, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, service_task, installer_update`

## callers

- `0x180036e80`

## callees

- `0x180004a20`
- `0x180004a90`
- `0x180005ac0`
- `0x1800065f0`
- `0x180006658`
- `0x180008ab0`
- `0x18000b854`
- `0x18003b0ac`
- `0x1800814f8`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180005c84`
- `OLEAUT32!__imp_SysAllocString` at `0x180005cc4`
- `OLEAUT32!__imp_SysAllocString` at `0x180005c84`
- `OLEAUT32!__imp_SysAllocString` at `0x180005cc4`
- `OLEAUT32!__imp_SysFreeString` at `0x180005efd`
- `OLEAUT32!__imp_SysFreeString` at `0x180005f41`
- `OLEAUT32!__imp_SysFreeString` at `0x180005efd`
- `OLEAUT32!__imp_SysFreeString` at `0x180005f41`

## string_xrefs

- `0x180005d1a`: `WdcServiceMonitor::UpdateService`
- `0x180005ee3`: `WdcServiceMonitor::UpdateService`
- `0x180005d21`: `base\diagnosis\pdui\perfmon\mon\service.cpp`
- `0x180005ec9`: `base\diagnosis\pdui\perfmon\mon\service.cpp`
- `0x180005eea`: `base\diagnosis\pdui\perfmon\mon\service.cpp`
- `0x180005ec2`: `WdcServiceMonitor::CreateEntry`

## pseudocode

```c
__int64 __fastcall WdcServiceMonitor::UpdateService(
        WdcServiceMonitor *this,
        SC_HANDLE a2,
        struct _ENUM_SERVICE_STATUS_PROCESSW *a3,
        unsigned int a4)
{
  __int64 v5; // rbp
  const char *v8; // rdx
  char *v9; // rdi
  int v10; // r8d
  char *i; // rbx
  char *v12; // rax
  WdcDataMonitor *v13; // rcx
  char *v14; // rax
  unsigned int v15; // ebp
  int v16; // eax
  char *v17; // rdi
  char *v18; // rax
  unsigned int v19; // edx
  __int64 v20; // rcx
  char *v21; // rax
  OLECHAR *v22; // rcx
  const OLECHAR *lpServiceName; // rdi
  BSTR v24; // rax
  _QWORD *v25; // rsi
  OLECHAR *v26; // rcx
  const OLECHAR *lpDisplayName; // rdi
  BSTR v28; // rax
  WdcServiceMonitor *v29; // rcx
  int v30; // eax
  __int64 v32; // rdx
  __int64 v33; // rdx
  _QWORD *v34; // rax
  __int64 v35; // rcx
  __int64 v36; // rax
  __int64 v37; // rax
  __int64 v38; // rcx
  __int64 v39; // rcx
  int v40; // r9d
  _QWORD *v41; // rax
  char *v42; // rcx
  int v43; // r9d
  double v44; // xmm1_8
  _QWORD *v45; // rax
  double dwProcessId; // xmm1_8
  _QWORD *v47; // rax
  __int64 v48; // [rsp+20h] [rbp-38h]
  __int64 v49; // [rsp+20h] [rbp-38h]

  v5 = a4;
  v9 = (char *)this + 16 * (int)WdcHashKey(a4) + 104;
  for ( i = *(char **)v9; ; i = *(char **)i )
  {
    if ( i == v9 )
    {
      v18 = (char *)WdcAlloc(0x148u, v8, v10);
      i = v18;
      if ( !v18 )
      {
        WdcDebugMessage(
          "base\\diagnosis\\pdui\\perfmon\\mon\\service.cpp",
          "WdcServiceMonitor::CreateEntry",
          0,
          L"FAILURE: 0x%08x",
          -2147024882);
        LODWORD(v49) = -2147024882;
        WdcDebugMessage(
          "base\\diagnosis\\pdui\\perfmon\\mon\\service.cpp",
          "WdcServiceMonitor::UpdateService",
          0,
          L"FAILURE: 0x%08x",
          v49);
        return (unsigned int)-2147024882;
      }
      memset_0(v18, 0, 0x148u);
      *((_DWORD *)i + 14) = 328;
      *((_QWORD *)i + 1) = i;
      *(_QWORD *)i = i;
      *((_QWORD *)i + 3) = i + 16;
      v19 = 0;
      *((_QWORD *)i + 2) = i + 16;
      *((_QWORD *)i + 5) = i + 32;
      *((_QWORD *)i + 4) = i + 32;
      *((_QWORD *)i + 10) = i + 88;
      *((_DWORD *)i + 22) = 0x10000000;
      *((_DWORD *)i + 16) = 458753;
      *((_DWORD *)i + 17) = 1;
      *((_DWORD *)i + 26) = 553713664;
      *((_DWORD *)i + 30) = 0x10000000;
      *((_DWORD *)i + 34) = 587202560;
      *((_DWORD *)i + 38) = 0x10000000;
      *((_DWORD *)i + 42) = 0x20000000;
      *((_DWORD *)i + 46) = 603979776;
      do
      {
        v20 = v19++;
        *(_DWORD *)(16 * v20 + *((_QWORD *)i + 10)) |= 3u;
      }
      while ( v19 < *((unsigned __int16 *)i + 33) );
      v21 = *(char **)v9;
      if ( *(char **)(*(_QWORD *)v9 + 8LL) != v9 )
        goto LABEL_10;
      *(_QWORD *)i = v21;
      *((_QWORD *)i + 1) = v9;
      *((_QWORD *)v21 + 1) = i;
      *(_QWORD *)v9 = i;
      *((_DWORD *)i + 80) = v5;
      *((_QWORD *)i + 6) = v5;
      goto LABEL_17;
    }
    v12 = *(char **)i;
    if ( *((_QWORD *)i + 6) == v5 )
      break;
  }
  if ( *((char **)v12 + 1) != i )
    goto LABEL_10;
  v13 = (WdcDataMonitor *)*((_QWORD *)i + 1);
  if ( *(char **)v13 != i )
    goto LABEL_10;
  *(_QWORD *)v13 = v12;
  *((_QWORD *)v12 + 1) = v13;
  v14 = *(char **)v9;
  if ( *(char **)(*(_QWORD *)v9 + 8LL) != v9 )
    goto LABEL_10;
  *(_QWORD *)i = v14;
  v15 = 0;
  *((_QWORD *)i + 1) = v9;
  *((_QWORD *)v14 + 1) = i;
  *(_QWORD *)v9 = i;
  v16 = *((_DWORD *)i + 17);
  if ( (v16 & 0x10000000) != 0 )
  {
    *((_DWORD *)i + 17) = v16 & 0xEFFFFFFF;
    WdcDataMonitor::SetRowDirty(v13, (struct _WDC_DATA_INFO *)i);
    *((_DWORD *)i + 17) &= 0xFCFFFFFF;
    v41 = i + 16;
    *((_DWORD *)i + 46) |= v40;
    v42 = (char *)this + 88;
    *((_QWORD *)i + 9) = 0;
    *((_QWORD *)i + 25) = 0;
    *((_QWORD *)i + 24) = 0;
    if ( (_QWORD *)*v41 == v41 )
    {
      v32 = *(_QWORD *)v42;
      if ( *(char **)(*(_QWORD *)v42 + 8LL) != v42 )
        goto LABEL_10;
      *v41 = v32;
      *((_QWORD *)i + 3) = v42;
      *(_QWORD *)(v32 + 8) = v41;
      *(_QWORD *)v42 = v41;
    }
    *((_DWORD *)i + 42) |= v40;
    *((_QWORD *)i + 22) = 0;
    if ( (_QWORD *)*v41 == v41 )
    {
      v33 = *(_QWORD *)v42;
      if ( *(char **)(*(_QWORD *)v42 + 8LL) != v42 )
        goto LABEL_10;
      *v41 = v33;
      *((_QWORD *)i + 3) = v42;
      *(_QWORD *)(v33 + 8) = v41;
      *(_QWORD *)v42 = v41;
    }
    *((_QWORD *)i + 26) = 0;
    *((_QWORD *)i + 27) = 0;
    memset_0(i + 232, 0, 0x58u);
LABEL_17:
    v22 = (OLECHAR *)*((_QWORD *)i + 12);
    lpServiceName = a3->lpServiceName;
    if ( v22 )
    {
      SysFreeString(v22);
      *((_QWORD *)i + 12) = 0;
    }
    v24 = SysAllocString(lpServiceName);
    if ( lpServiceName && !v24 )
      goto LABEL_52;
    *((_QWORD *)i + 12) = v24;
    *((_DWORD *)i + 22) |= 1u;
    v25 = i + 16;
    if ( (_QWORD *)*v25 == v25 )
    {
      v34 = (_QWORD *)((char *)this + 88);
      v35 = *((_QWORD *)this + 11);
      if ( *(WdcServiceMonitor **)(v35 + 8) != (WdcServiceMonitor *)((char *)this + 88) )
        goto LABEL_10;
      *v25 = v35;
      *((_QWORD *)i + 3) = v34;
      *(_QWORD *)(v35 + 8) = v25;
      *v34 = v25;
    }
    v26 = (OLECHAR *)*((_QWORD *)i + 16);
    lpDisplayName = a3->lpDisplayName;
    if ( v26 )
    {
      SysFreeString(v26);
      *((_QWORD *)i + 16) = 0;
    }
    v28 = SysAllocString(lpDisplayName);
    if ( lpDisplayName && !v28 )
    {
LABEL_52:
      WdcDebugMessage(
        "base\\diagnosis\\pdui\\perfmon\\mmc\\inline.cpp",
        "WdcAssignString",
        0,
        L"FAILURE: 0x%08x",
        -2147024882);
      v15 = -2147024882;
      LODWORD(v48) = -2147024882;
    }
    else
    {
      *((_QWORD *)i + 16) = v28;
      *((_DWORD *)i + 30) |= 1u;
      v17 = (char *)this + 88;
      if ( (_QWORD *)*v25 == v25 )
      {
        v36 = *(_QWORD *)v17;
        if ( *(char **)(*(_QWORD *)v17 + 8LL) != v17 )
          goto LABEL_10;
        *v25 = v36;
        *((_QWORD *)i + 3) = v17;
        *(_QWORD *)(v36 + 8) = v25;
        *(_QWORD *)v17 = v25;
      }
      v30 = WdcServiceMonitor::AssignGroupString(v29, a2, a3, (unsigned __int16 **)i + 20);
      v15 = v30;
      if ( v30 >= 0 )
      {
        *((_DWORD *)i + 38) |= 1u;
        if ( (_QWORD *)*v25 != v25 )
          goto LABEL_54;
        v37 = *(_QWORD *)v17;
        if ( *(char **)(*(_QWORD *)v17 + 8LL) == v17 )
        {
          *v25 = v37;
          *((_QWORD *)i + 3) = v17;
          *(_QWORD *)(v37 + 8) = v25;
          *(_QWORD *)v17 = v25;
          goto LABEL_54;
        }
        goto LABEL_10;
      }
      LODWORD(v48) = v30;
    }
    WdcDebugMessage(
      "base\\diagnosis\\pdui\\perfmon\\mon\\service.cpp",
      "WdcServiceMonitor::UpdateService",
      0,
      L"FAILURE: 0x%08x",
      v48);
    return v15;
  }
  v17 = (char *)this + 88;
LABEL_54:
  v44 = (double)(int)WdcServiceStateToRcid(a3->ServiceStatusProcess.dwCurrentState);
  if ( *((double *)i + 18) != v44 )
  {
    *((_DWORD *)i + 34) |= v43;
    v45 = i + 16;
    *((double *)i + 18) = v44;
    if ( (_QWORD *)*v45 == v45 )
    {
      v38 = *(_QWORD *)v17;
      if ( *(char **)(*(_QWORD *)v17 + 8LL) == v17 )
      {
        *v45 = v38;
        *((_QWORD *)i + 3) = v17;
        *(_QWORD *)(v38 + 8) = v45;
        *(_QWORD *)v17 = v45;
        goto LABEL_56;
      }
      goto LABEL_10;
    }
  }
LABEL_56:
  dwProcessId = (double)(int)a3->ServiceStatusProcess.dwProcessId;
  if ( *((double *)i + 14) != dwProcessId )
  {
    *((_DWORD *)i + 26) |= v43;
    v47 = i + 16;
    *((double *)i + 14) = dwProcessId;
    if ( (_QWORD *)*v47 == v47 )
    {
      v39 = *(_QWORD *)v17;
      if ( *(char **)(*(_QWORD *)v17 + 8LL) == v17 )
      {
        *v47 = v39;
        *((_QWORD *)i + 3) = v17;
        *(_QWORD *)(v39 + 8) = v47;
        *(_QWORD *)v17 = v47;
        goto LABEL_31;
      }
LABEL_10:
      __fastfail(3u);
    }
  }
LABEL_31:
  *((_DWORD *)i + 17) |= 8u;
  while ( MEMORY[0x7FFE0018] != MEMORY[0x7FFE001C] )
    ;
  WdcDataMonitor::UpdateTimeStamp(this, (struct _WDC_DATA_INFO *)i, MEMORY[0x7FFE0014]);
  return v15;
}

```

## disassembly

```asm
0x180005ac0  mov     [rsp+arg_8], rbx
0x180005ac5  mov     [rsp+arg_10], rbp
0x180005aca  push    rsi
0x180005acb  push    rdi
0x180005acc  push    r12
0x180005ace  push    r14
0x180005ad0  push    r15
0x180005ad2  sub     rsp, 30h
0x180005ad6  mov     r14, rcx
0x180005ad9  mov     ebp, r9d
0x180005adc  mov     ecx, r9d; unsigned __int64
0x180005adf  mov     r15, r8
0x180005ae2  mov     r12, rdx
0x180005ae5  mov     qword ptr [rsp+58h+arg_0], 0
0x180005aee  call    ?WdcHashKey@@YAH_K@Z; WdcHashKey(unsigned __int64)
0x180005af3  movsxd  r10, eax
0x180005af6  lea     rdi, [r14+68h]
0x180005afa  shl     r10, 4
0x180005afe  add     rdi, r10
0x180005b01  mov     rbx, [rdi]
0x180005b04  mov     r9d, 1
0x180005b0a  cmp     rbx, rdi
0x180005b0d  jz      short loc_180005B69
0x180005b0f  mov     rax, [rbx]
0x180005b12  cmp     [rbx+30h], rbp
0x180005b16  jz      short loc_180005B1D
0x180005b18  mov     rbx, rax
0x180005b1b  jmp     short loc_180005B04
0x180005b1d  cmp     [rax+8], rbx
0x180005b21  jnz     short loc_180005B62
0x180005b23  mov     rcx, [rbx+8]; this
0x180005b27  cmp     [rcx], rbx
0x180005b2a  jnz     short loc_180005B62
0x180005b2c  mov     [rcx], rax
0x180005b2f  mov     [rax+8], rcx
0x180005b33  mov     rax, [rdi]
0x180005b36  cmp     [rax+8], rdi
0x180005b3a  jnz     short loc_180005B62
0x180005b3c  mov     [rbx], rax
0x180005b3f  xor     ebp, ebp
0x180005b41  mov     [rbx+8], rdi
0x180005b45  mov     [rax+8], rbx
0x180005b49  mov     [rdi], rbx
0x180005b4c  mov     eax, [rbx+44h]
0x180005b4f  bt      eax, 1Ch
0x180005b53  jb      loc_180005E53
0x180005b59  lea     rdi, [r14+58h]
0x180005b5d  jmp     loc_180005F6D
0x180005b62  mov     ecx, 3
0x180005b67  int     29h; Win8: RtlFailFast(ecx)
0x180005b69  mov     ecx, 148h; dwBytes
0x180005b6e  call    ?WdcAlloc@@YAPEAX_KPEBDH@Z; WdcAlloc(unsigned __int64,char const *,int)
0x180005b73  mov     rbx, rax
0x180005b76  test    rax, rax
0x180005b79  jz      loc_180005EAF
0x180005b7f  xor     edx, edx; Val
0x180005b81  mov     r8d, 148h; Size
0x180005b87  mov     rcx, rax; void *
0x180005b8a  call    memset_0
0x180005b8f  mov     dword ptr [rbx+38h], 148h
0x180005b96  lea     rax, [rbx+10h]
0x180005b9a  mov     [rbx+8], rbx
0x180005b9e  mov     ecx, 10000000h
0x180005ba3  mov     [rbx], rbx
0x180005ba6  mov     r8d, 1
0x180005bac  mov     [rax+8], rax
0x180005bb0  xor     edx, edx
0x180005bb2  mov     [rax], rax
0x180005bb5  lea     rax, [rbx+20h]
0x180005bb9  mov     [rax+8], rax
0x180005bbd  mov     [rax], rax
0x180005bc0  lea     rax, [rbx+58h]
0x180005bc4  mov     [rbx+50h], rax
0x180005bc8  mov     [rax], ecx
0x180005bca  mov     dword ptr [rbx+40h], 70001h
0x180005bd1  mov     [rbx+44h], r8d
0x180005bd5  mov     dword ptr [rbx+68h], 21010000h
0x180005bdc  mov     [rbx+78h], ecx
0x180005bdf  mov     dword ptr [rbx+88h], 23000000h
0x180005be9  mov     [rbx+98h], ecx
0x180005bef  mov     dword ptr [rbx+0A8h], 20000000h
0x180005bf9  mov     dword ptr [rbx+0B8h], 24000000h
0x180005c03  mov     rax, [rbx+50h]
0x180005c07  mov     ecx, edx
0x180005c09  add     edx, r8d
0x180005c0c  shl     rcx, 4
0x180005c10  or      dword ptr [rcx+rax], 3
0x180005c14  movzx   eax, word ptr [rbx+42h]
0x180005c18  cmp     edx, eax
0x180005c1a  jb      short loc_180005C03
0x180005c1c  mov     rax, [rdi]
0x180005c1f  cmp     [rax+8], rdi
0x180005c23  jnz     loc_180005B62
0x180005c29  mov     [rbx], rax
0x180005c2c  mov     [rbx+8], rdi
0x180005c30  mov     [rax+8], rbx
0x180005c34  mov     [rdi], rbx
0x180005c37  mov     [rbx+140h], ebp
0x180005c3d  mov     [rbx+30h], rbp
0x180005c41  jmp     short loc_180005C71
0x180005c43  mov     [rax], rdx
0x180005c46  mov     [rax+8], rcx
0x180005c4a  mov     [rdx+8], rax
0x180005c4e  mov     [rcx], rax
0x180005c51  xor     edx, edx; Val
0x180005c53  mov     [rbx+0D0h], rbp
0x180005c5a  lea     rcx, [rbx+0E8h]; void *
0x180005c61  mov     [rbx+0D8h], rbp
0x180005c68  lea     r8d, [rdx+58h]; Size
0x180005c6c  call    memset_0
0x180005c71  mov     rcx, [rbx+60h]; bstrString
0x180005c75  mov     rdi, [r15]
0x180005c78  test    rcx, rcx
0x180005c7b  jnz     loc_180005EFD
0x180005c81  mov     rcx, rdi; psz
0x180005c84  call    cs:__imp_SysAllocString
0x180005c8a  test    rdi, rdi
0x180005c8d  jz      short loc_180005C98
0x180005c8f  test    rax, rax
0x180005c92  jz      loc_180005F10
0x180005c98  mov     [rbx+60h], rax
0x180005c9c  or      dword ptr [rbx+58h], 1
0x180005ca0  lea     rsi, [rbx+10h]
0x180005ca4  cmp     [rsi], rsi
0x180005ca7  jz      loc_180005DBD
0x180005cad  mov     rcx, [rbx+80h]; bstrString
0x180005cb4  mov     rdi, [r15+8]
0x180005cb8  test    rcx, rcx
0x180005cbb  jnz     loc_180005F41
0x180005cc1  mov     rcx, rdi; psz
0x180005cc4  call    cs:__imp_SysAllocString
0x180005cca  test    rdi, rdi
0x180005ccd  jz      short loc_180005CD8
0x180005ccf  test    rax, rax
0x180005cd2  jz      loc_180005F10
0x180005cd8  mov     [rbx+80h], rax
0x180005cdf  or      dword ptr [rbx+78h], 1
0x180005ce3  lea     rdi, [r14+58h]
0x180005ce7  cmp     [rsi], rsi
0x180005cea  jz      loc_180005DE1
0x180005cf0  lea     r9, [rbx+0A0h]; unsigned __int16 **
0x180005cf7  mov     r8, r15; struct _ENUM_SERVICE_STATUS_PROCESSW *
0x180005cfa  mov     rdx, r12; struct SC_HANDLE__ *
0x180005cfd  call    ?AssignGroupString@WdcServiceMonitor@@AEAAJPEAUSC_HANDLE__@@PEAU_ENUM_SERVICE_STATUS_PROCESSW@@PEAPEAG@Z; WdcServiceMonitor::AssignGroupString(SC_HANDLE__ *,_ENUM_SERVICE_STATUS_PROCESSW *,ushort * *)
0x180005d02  mov     ebp, eax
0x180005d04  test    eax, eax
0x180005d06  jns     loc_180005F57
0x180005d0c  mov     dword ptr [rsp+58h+var_38], eax
0x180005d10  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x180005d17  xor     r8d, r8d; int
0x180005d1a  lea     rdx, aWdcservicemoni_9; "WdcServiceMonitor::UpdateService"
0x180005d21  lea     rcx, aBaseDiagnosisP_45; "base\\diagnosis\\pdui\\perfmon\\mon\\se"...
0x180005d28  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x180005d2d  mov     rbx, [rsp+58h+arg_8]
0x180005d32  mov     eax, ebp
0x180005d34  mov     rbp, [rsp+58h+arg_10]
0x180005d39  add     rsp, 30h
0x180005d3d  pop     r15
0x180005d3f  pop     r14
0x180005d41  pop     r12
0x180005d43  pop     rdi
0x180005d44  pop     rsi
0x180005d45  retn
0x180005d46  mov     [rax], rcx
0x180005d49  mov     [rax+8], rdi
0x180005d4d  mov     [rcx+8], rax
0x180005d51  mov     [rdi], rax
0x180005d54  or      dword ptr [rbx+44h], 8
0x180005d58  mov     ecx, ds:7FFE0018h
0x180005d5f  mov     eax, ds:7FFE0014h
0x180005d66  mov     dword ptr [rsp+58h+arg_0], eax
0x180005d6a  mov     eax, ds:7FFE001Ch
0x180005d71  mov     dword ptr [rsp+58h+arg_0+4], ecx
0x180005d75  cmp     ecx, eax
0x180005d77  jnz     short loc_180005D58
0x180005d79  mov     r8, qword ptr [rsp+58h+arg_0]; union _LARGE_INTEGER
0x180005d7e  mov     rdx, rbx; struct _WDC_DATA_INFO *
0x180005d81  mov     rcx, r14; this
0x180005d84  call    ?UpdateTimeStamp@WdcDataMonitor@@IEAAXPEAU_WDC_DATA_INFO@@T_LARGE_INTEGER@@@Z; WdcDataMonitor::UpdateTimeStamp(_WDC_DATA_INFO *,_LARGE_INTEGER)
0x180005d89  jmp     short loc_180005D2D
0x180005d8b  mov     rdx, [rcx]
0x180005d8e  cmp     [rdx+8], rcx
0x180005d92  jnz     loc_180005B62
0x180005d98  mov     [rax], rdx
0x180005d9b  mov     [rax+8], rcx
0x180005d9f  mov     [rdx+8], rax
0x180005da3  mov     [rcx], rax
0x180005da6  jmp     loc_180005E93
0x180005dab  mov     rdx, [rcx]
0x180005dae  cmp     [rdx+8], rcx
0x180005db2  jnz     loc_180005B62
0x180005db8  jmp     loc_180005C43
0x180005dbd  lea     rax, [r14+58h]
0x180005dc1  mov     rcx, [rax]
0x180005dc4  cmp     [rcx+8], rax
0x180005dc8  jnz     loc_180005B62
0x180005dce  mov     [rsi], rcx
0x180005dd1  mov     [rsi+8], rax
0x180005dd5  mov     [rcx+8], rsi
0x180005dd9  mov     [rax], rsi
0x180005ddc  jmp     loc_180005CAD
0x180005de1  mov     rax, [rdi]
0x180005de4  cmp     [rax+8], rdi
0x180005de8  jnz     loc_180005B62
0x180005dee  mov     [rsi], rax
0x180005df1  mov     [rsi+8], rdi
0x180005df5  mov     [rax+8], rsi
0x180005df9  mov     [rdi], rsi
0x180005dfc  jmp     loc_180005CF0
0x180005e01  mov     rax, [rdi]
0x180005e04  cmp     [rax+8], rdi
0x180005e08  jnz     loc_180005B62
0x180005e0e  mov     [rsi], rax
0x180005e11  mov     [rsi+8], rdi
0x180005e15  mov     [rax+8], rsi
0x180005e19  mov     [rdi], rsi
0x180005e1c  jmp     loc_180005F6D
0x180005e21  mov     rcx, [rdi]
0x180005e24  cmp     [rcx+8], rdi
0x180005e28  jnz     loc_180005B62
0x180005e2e  mov     [rax], rcx
0x180005e31  mov     [rax+8], rdi
0x180005e35  mov     [rcx+8], rax
0x180005e39  mov     [rdi], rax
0x180005e3c  jmp     loc_180005FAC
0x180005e41  mov     rcx, [rdi]
0x180005e44  cmp     [rcx+8], rdi
0x180005e48  jnz     loc_180005B62
0x180005e4e  jmp     loc_180005D46
0x180005e53  btr     eax, 1Ch
0x180005e57  mov     rdx, rbx; struct _WDC_DATA_INFO *
0x180005e5a  mov     [rbx+44h], eax
0x180005e5d  call    ?SetRowDirty@WdcDataMonitor@@QEAAJPEAU_WDC_DATA_INFO@@@Z; WdcDataMonitor::SetRowDirty(_WDC_DATA_INFO *)
0x180005e62  and     dword ptr [rbx+44h], 0FCFFFFFFh
0x180005e69  lea     rax, [rbx+10h]
0x180005e6d  or      [rbx+0B8h], r9d
0x180005e74  lea     rcx, [r14+58h]
0x180005e78  mov     [rbx+48h], rbp
0x180005e7c  mov     [rbx+0C8h], rbp
0x180005e83  mov     [rbx+0C0h], rbp
0x180005e8a  cmp     [rax], rax
0x180005e8d  jz      loc_180005D8B
0x180005e93  or      [rbx+0A8h], r9d
0x180005e9a  mov     [rbx+0B0h], rbp
0x180005ea1  cmp     [rax], rax
0x180005ea4  jnz     loc_180005C51
0x180005eaa  jmp     loc_180005DAB
0x180005eaf  mov     ebx, 8007000Eh
0x180005eb4  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x180005ebb  xor     r8d, r8d; int
0x180005ebe  mov     dword ptr [rsp+58h+var_38], ebx
0x180005ec2  lea     rdx, aWdcservicemoni; "WdcServiceMonitor::CreateEntry"
0x180005ec9  lea     rcx, aBaseDiagnosisP_45; "base\\diagnosis\\pdui\\perfmon\\mon\\se"...
0x180005ed0  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x180005ed5  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x180005edc  mov     dword ptr [rsp+58h+var_38], ebx
0x180005ee0  xor     r8d, r8d; int
0x180005ee3  lea     rdx, aWdcservicemoni_9; "WdcServiceMonitor::UpdateService"
0x180005eea  lea     rcx, aBaseDiagnosisP_45; "base\\diagnosis\\pdui\\perfmon\\mon\\se"...
0x180005ef1  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x180005ef6  mov     ebp, ebx
0x180005ef8  jmp     loc_180005D2D
0x180005efd  call    cs:__imp_SysFreeString
0x180005f03  mov     qword ptr [rbx+60h], 0
0x180005f0b  jmp     loc_180005C81
0x180005f10  mov     ebx, 8007000Eh
0x180005f15  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x180005f1c  xor     r8d, r8d; int
0x180005f1f  mov     dword ptr [rsp+58h+var_38], ebx
0x180005f23  lea     rdx, aWdcassignstrin; "WdcAssignString"
0x180005f2a  lea     rcx, aBaseDiagnosisP_52; "base\\diagnosis\\pdui\\perfmon\\mmc\\in"...
0x180005f31  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x180005f36  mov     ebp, ebx
0x180005f38  mov     dword ptr [rsp+58h+var_38], ebx
0x180005f3c  jmp     loc_180005D10
0x180005f41  call    cs:__imp_SysFreeString
0x180005f47  mov     qword ptr [rbx+80h], 0
0x180005f52  jmp     loc_180005CC1
0x180005f57  mov     r9d, 1
0x180005f5d  or      [rbx+98h], r9d
0x180005f64  cmp     [rsi], rsi
0x180005f67  jz      loc_180005E01
0x180005f6d  mov     ecx, [r15+14h]; unsigned int
0x180005f71  call    ?WdcServiceStateToRcid@@YAIK@Z; WdcServiceStateToRcid(ulong)
0x180005f76  movsd   xmm0, qword ptr [rbx+90h]
0x180005f7e  xorps   xmm1, xmm1
0x180005f81  mov     edx, eax
0x180005f83  cvtsi2sd xmm1, rdx
0x180005f88  ucomisd xmm0, xmm1
0x180005f8c  jp      short loc_180005F90
0x180005f8e  jz      short loc_180005FAC
0x180005f90  or      [rbx+88h], r9d
0x180005f97  lea     rax, [rbx+10h]
0x180005f9b  movsd   qword ptr [rbx+90h], xmm1
0x180005fa3  cmp     [rax], rax
0x180005fa6  jz      loc_180005E21
0x180005fac  mov     eax, [r15+2Ch]
0x180005fb0  xorps   xmm1, xmm1
0x180005fb3  movsd   xmm0, qword ptr [rbx+70h]
0x180005fb8  cvtsi2sd xmm1, rax
  ... truncated ...
```
