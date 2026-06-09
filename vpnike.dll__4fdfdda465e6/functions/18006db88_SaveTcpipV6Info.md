# SaveTcpipV6Info

- ea: `0x18006db88`
- end: `0x18006de06`
- name: `SaveTcpipV6Info`
- size: `638`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, service_task`

## callers

- `0x18004e5bc`
- `0x180050068`

## callees

- `0x18006db88`
- `0x18006de0c`
- `0x18006f864`
- `0x180076ccc`
- `0x18007755e`
- `0x180077590`
- `0x18007a010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006ddca`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006ddda`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006ddca`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006ddda`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006dc9a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006dd2c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006dc9a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006dd2c`

## string_xrefs

- `0x18006dcce`: `RegOpenKeyEx(%ws) failed and returned %d`
- `0x18006dcfa`: `RegOpenKeyEx(%ws) failed and returned %d`
- `0x18006dd1e`: `System\CurrentControlSet\Services\Tcpip\Parameters`
- `0x18006dd4d`: `System\CurrentControlSet\Services\Tcpip\Parameters`
- `0x18006dd64`: `System\CurrentControlSet\Services\Tcpip\Parameters`
- `0x18006dc8c`: `System\CurrentControlSet\Services\Tcpip6\Parameters`
- `0x18006dcbf`: `System\CurrentControlSet\Services\Tcpip6\Parameters`
- `0x18006dcf3`: `System\CurrentControlSet\Services\Tcpip6\Parameters`

## pseudocode

```c
__int64 __fastcall SaveTcpipV6Info(_QWORD *a1)
{
  int v2; // eax
  unsigned int v3; // eax
  unsigned int v4; // ebx
  const WCHAR *v5; // r8
  __int64 v6; // r9
  __int64 v7; // rdx
  const wchar_t *v8; // r8
  HKEY hKey; // [rsp+30h] [rbp-D0h] BYREF
  HKEY phkResult; // [rsp+38h] [rbp-C8h] BYREF
  int v12; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v13[2044]; // [rsp+44h] [rbp-BCh] BYREF

  hKey = 0;
  phkResult = 0;
  v12 = 0;
  memset_0(v13, 0, sizeof(v13));
  v2 = gIsIphlpEtwTracingAvailable;
  if ( gIsIphlpEtwTracingAvailable )
  {
    if ( !*((_QWORD *)&xmmword_1800AB320 + 1) )
      goto LABEL_8;
    ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gIphlpTemplateFunc)(
      gIphlpEtwContext,
      *((_QWORD *)&xmmword_1800AB320 + 1),
      L"SaveTcpipV6Info");
  }
  else
  {
    TraceHlp("SaveTcpipV6Info");
  }
  v2 = gIsIphlpEtwTracingAvailable;
  if ( !gIsIphlpEtwTracingAvailable )
  {
LABEL_9:
    TraceHlp("SaveTcpipV6Info");
    goto LABEL_10;
  }
  if ( *((_QWORD *)&xmmword_1800AB320 + 1) )
  {
    ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gIphlpTemplateFunc)(
      gIphlpEtwContext,
      *((_QWORD *)&xmmword_1800AB320 + 1),
      L"SaveTcpipV6Info");
LABEL_10:
    v2 = gIsIphlpEtwTracingAvailable;
    goto LABEL_11;
  }
LABEL_8:
  if ( !v2 )
    goto LABEL_9;
LABEL_11:
  if ( a1 && *a1 )
  {
    v3 = RegOpenKeyExW(
           HKEY_LOCAL_MACHINE,
           L"System\\CurrentControlSet\\Services\\Tcpip6\\Parameters",
           0,
           0x20006u,
           &hKey);
    v4 = v3;
    if ( v3 )
    {
      if ( gIsIphlpEtwTracingAvailable )
      {
        if ( !(_QWORD)xmmword_1800AB320 )
          goto LABEL_30;
        v5 = L"System\\CurrentControlSet\\Services\\Tcpip6\\Parameters";
        LOWORD(v12) = 0;
        v6 = v3;
LABEL_17:
        FormatRRASErrorString(&v12, L"RegOpenKeyEx(%ws) failed and returned %d", v5, v6);
        v7 = xmmword_1800AB320;
        v8 = (const wchar_t *)&v12;
LABEL_28:
        ((void (__fastcall *)(__int64, __int64, const wchar_t *))gIphlpTemplateFunc)(gIphlpEtwContext, v7, v8);
        goto LABEL_30;
      }
    }
    else
    {
      v4 = RegOpenKeyExW(
             HKEY_LOCAL_MACHINE,
             L"System\\CurrentControlSet\\Services\\Tcpip\\Parameters",
             0,
             0x20006u,
             &phkResult);
      if ( !v4 )
      {
        v4 = SaveTcpipV6Param(phkResult, hKey, (__int64)a1);
        goto LABEL_30;
      }
      if ( gIsIphlpEtwTracingAvailable )
      {
        if ( !(_QWORD)xmmword_1800AB320 )
          goto LABEL_30;
        v5 = L"System\\CurrentControlSet\\Services\\Tcpip\\Parameters";
        LOWORD(v12) = 0;
        v6 = v4;
        goto LABEL_17;
      }
    }
    TraceHlp("RegOpenKeyEx(%ws) failed and returned %d");
    goto LABEL_30;
  }
  v4 = 87;
  if ( v2 )
  {
    v7 = xmmword_1800AB320;
    if ( !(_QWORD)xmmword_1800AB320 )
      goto LABEL_30;
    v8 = L"pTcpipInfo or wszAdapterName is NULL";
    goto LABEL_28;
  }
  TraceHlp("pTcpipInfo or wszAdapterName is NULL");
LABEL_30:
  if ( hKey )
    RegCloseKey(hKey);
  if ( phkResult )
    RegCloseKey(phkResult);
  return v4;
}

```

## disassembly

```asm
0x18006db88  mov     [rsp-8+arg_8], rbx
0x18006db8d  mov     [rsp-8+arg_10], rdi
0x18006db92  push    rbp
0x18006db93  lea     rbp, [rsp-750h]
0x18006db9b  sub     rsp, 850h
0x18006dba2  mov     rax, cs:__security_cookie
0x18006dba9  xor     rax, rsp
0x18006dbac  mov     [rbp+750h+var_10], rax
0x18006dbb3  mov     rdi, rcx
0x18006dbb6  mov     [rsp+850h+hKey], 0
0x18006dbbf  xor     eax, eax
0x18006dbc1  mov     [rsp+850h+var_818], 0
0x18006dbca  lea     rcx, [rsp+850h+var_80C]; void *
0x18006dbcf  mov     [rsp+850h+var_810], eax
0x18006dbd3  xor     edx, edx; Val
0x18006dbd5  mov     r8d, 7FCh; Size
0x18006dbdb  call    memset_0
0x18006dbe0  mov     eax, cs:gIsIphlpEtwTracingAvailable
0x18006dbe6  test    eax, eax
0x18006dbe8  jz      short loc_18006DC12
0x18006dbea  mov     rdx, qword ptr cs:xmmword_1800AB328
0x18006dbf1  test    rdx, rdx
0x18006dbf4  jz      short loc_18006DC50
0x18006dbf6  mov     rcx, cs:gIphlpEtwContext
0x18006dbfd  lea     r8, aSavetcpipv6inf; "SaveTcpipV6Info"
0x18006dc04  mov     rax, cs:gIphlpTemplateFunc
0x18006dc0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006dc10  jmp     short loc_18006DC1E
0x18006dc12  lea     rcx, aSavetcpipv6inf_0; "SaveTcpipV6Info"
0x18006dc19  call    TraceHlp
0x18006dc1e  mov     eax, cs:gIsIphlpEtwTracingAvailable
0x18006dc24  test    eax, eax
0x18006dc26  jz      short loc_18006DC54
0x18006dc28  mov     rdx, qword ptr cs:xmmword_1800AB328
0x18006dc2f  test    rdx, rdx
0x18006dc32  jz      short loc_18006DC50
0x18006dc34  mov     rcx, cs:gIphlpEtwContext
0x18006dc3b  lea     r8, aSavetcpipv6inf; "SaveTcpipV6Info"
0x18006dc42  mov     rax, cs:gIphlpTemplateFunc
0x18006dc49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006dc4e  jmp     short loc_18006DC60
0x18006dc50  test    eax, eax
0x18006dc52  jnz     short loc_18006DC66
0x18006dc54  lea     rcx, aSavetcpipv6inf_0; "SaveTcpipV6Info"
0x18006dc5b  call    TraceHlp
0x18006dc60  mov     eax, cs:gIsIphlpEtwTracingAvailable
0x18006dc66  test    rdi, rdi
0x18006dc69  jz      loc_18006DD83
0x18006dc6f  cmp     qword ptr [rdi], 0
0x18006dc73  jz      loc_18006DD83
0x18006dc79  lea     rax, [rsp+850h+hKey]
0x18006dc7e  mov     r9d, 20006h; samDesired
0x18006dc84  xor     r8d, r8d; ulOptions
0x18006dc87  mov     [rsp+850h+phkResult], rax; phkResult
0x18006dc8c  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Services\\Tc"...
0x18006dc93  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18006dc9a  call    cs:__imp_RegOpenKeyExW
0x18006dca0  mov     ebx, eax
0x18006dca2  test    eax, eax
0x18006dca4  jz      short loc_18006DD0B
0x18006dca6  cmp     cs:gIsIphlpEtwTracingAvailable, 0
0x18006dcad  jz      short loc_18006DCF0
0x18006dcaf  cmp     qword ptr cs:unk_1800AB320, 0
0x18006dcb7  jz      loc_18006DDC0
0x18006dcbd  xor     ecx, ecx
0x18006dcbf  lea     r8, aSystemCurrentc; "System\\CurrentControlSet\\Services\\Tc"...
0x18006dcc6  mov     word ptr [rsp+850h+var_810], cx
0x18006dccb  mov     r9d, eax
0x18006dcce  lea     rdx, aRegopenkeyexWs; "RegOpenKeyEx(%ws) failed and returned %"...
0x18006dcd5  lea     rcx, [rsp+850h+var_810]
0x18006dcda  call    FormatRRASErrorString
0x18006dcdf  mov     rdx, qword ptr cs:unk_1800AB320
0x18006dce6  lea     r8, [rsp+850h+var_810]
0x18006dceb  jmp     loc_18006DD9F
0x18006dcf0  mov     r8d, eax
0x18006dcf3  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Services\\Tc"...
0x18006dcfa  lea     rcx, aRegopenkeyexWs_2; "RegOpenKeyEx(%ws) failed and returned %"...
0x18006dd01  call    TraceHlp
0x18006dd06  jmp     loc_18006DDC0
0x18006dd0b  lea     rax, [rsp+850h+var_818]
0x18006dd10  mov     r9d, 20006h; samDesired
0x18006dd16  xor     r8d, r8d; ulOptions
0x18006dd19  mov     [rsp+850h+phkResult], rax; phkResult
0x18006dd1e  lea     rdx, aSystemCurrentc_4; "System\\CurrentControlSet\\Services\\Tc"...
0x18006dd25  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18006dd2c  call    cs:__imp_RegOpenKeyExW
0x18006dd32  mov     ebx, eax
0x18006dd34  test    eax, eax
0x18006dd36  jz      short loc_18006DD6D
0x18006dd38  cmp     cs:gIsIphlpEtwTracingAvailable, 0
0x18006dd3f  jz      short loc_18006DD61
0x18006dd41  cmp     qword ptr cs:unk_1800AB320, 0
0x18006dd49  jz      short loc_18006DDC0
0x18006dd4b  xor     eax, eax
0x18006dd4d  lea     r8, aSystemCurrentc_4; "System\\CurrentControlSet\\Services\\Tc"...
0x18006dd54  mov     word ptr [rsp+850h+var_810], ax
0x18006dd59  mov     r9d, ebx
0x18006dd5c  jmp     loc_18006DCCE
0x18006dd61  mov     r8d, ebx
0x18006dd64  lea     rdx, aSystemCurrentc_4; "System\\CurrentControlSet\\Services\\Tc"...
0x18006dd6b  jmp     short loc_18006DCFA
0x18006dd6d  mov     rdx, [rsp+850h+hKey]; HKEY
0x18006dd72  mov     r8, rdi
0x18006dd75  mov     rcx, [rsp+850h+var_818]; hKey
0x18006dd7a  call    SaveTcpipV6Param
0x18006dd7f  mov     ebx, eax
0x18006dd81  jmp     short loc_18006DDC0
0x18006dd83  mov     ebx, 57h ; 'W'
0x18006dd88  test    eax, eax
0x18006dd8a  jz      short loc_18006DDB4
0x18006dd8c  mov     rdx, qword ptr cs:unk_1800AB320
0x18006dd93  test    rdx, rdx
0x18006dd96  jz      short loc_18006DDC0
0x18006dd98  lea     r8, aPtcpipinfoOrWs; "pTcpipInfo or wszAdapterName is NULL"
0x18006dd9f  mov     rcx, cs:gIphlpEtwContext
0x18006dda6  mov     rax, cs:gIphlpTemplateFunc
0x18006ddad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ddb2  jmp     short loc_18006DDC0
0x18006ddb4  lea     rcx, aPtcpipinfoOrWs_0; "pTcpipInfo or wszAdapterName is NULL"
0x18006ddbb  call    TraceHlp
0x18006ddc0  mov     rcx, [rsp+850h+hKey]; hKey
0x18006ddc5  test    rcx, rcx
0x18006ddc8  jz      short loc_18006DDD0
0x18006ddca  call    cs:__imp_RegCloseKey
0x18006ddd0  mov     rcx, [rsp+850h+var_818]; hKey
0x18006ddd5  test    rcx, rcx
0x18006ddd8  jz      short loc_18006DDE0
0x18006ddda  call    cs:__imp_RegCloseKey
0x18006dde0  mov     eax, ebx
0x18006dde2  mov     rcx, [rbp+750h+var_10]
0x18006dde9  xor     rcx, rsp; StackCookie
0x18006ddec  call    __security_check_cookie
0x18006ddf1  lea     r11, [rsp+850h+var_s0]
0x18006ddf9  mov     rbx, [r11+18h]
0x18006ddfd  mov     rdi, [r11+20h]
0x18006de01  mov     rsp, r11
0x18006de04  pop     rbp
0x18006de05  retn
```
