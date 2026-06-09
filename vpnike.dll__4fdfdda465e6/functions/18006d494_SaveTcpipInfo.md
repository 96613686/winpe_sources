# SaveTcpipInfo

- ea: `0x18006d494`
- end: `0x18006d739`
- name: `SaveTcpipInfo`
- size: `677`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `3`
- callee_count: `8`
- tags: `registry_config, service_task`

## callers

- `0x18004971c`
- `0x18004baa8`
- `0x18004c488`

## callees

- `0x18006d494`
- `0x18006d740`
- `0x18006e2d4`
- `0x18006f864`
- `0x180076ccc`
- `0x18007755e`
- `0x180077590`
- `0x18007a010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006d6fd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006d70d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006d6fd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006d70d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006d5a7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006d655`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006d5a7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006d655`

## string_xrefs

- `0x18006d5e0`: `RegOpenKeyEx(%ws) failed and returned %d`
- `0x18006d60c`: `RegOpenKeyEx(%ws) failed and returned %d`
- `0x18006d599`: `System\CurrentControlSet\Services\Tcpip\Parameters`
- `0x18006d5d1`: `System\CurrentControlSet\Services\Tcpip\Parameters`
- `0x18006d605`: `System\CurrentControlSet\Services\Tcpip\Parameters`
- `0x18006d647`: `System\CurrentControlSet\Services\NetBT\Parameters\Interfaces`
- `0x18006d682`: `System\CurrentControlSet\Services\NetBT\Parameters\Interfaces`
- `0x18006d699`: `System\CurrentControlSet\Services\NetBT\Parameters\Interfaces`

## pseudocode

```c
__int64 __fastcall SaveTcpipInfo(__int64 a1)
{
  int v2; // eax
  unsigned int v3; // eax
  unsigned int v4; // ebx
  const WCHAR *v5; // r8
  __int64 v6; // r9
  __int64 v7; // rdx
  const wchar_t *v8; // r8
  unsigned int v9; // eax
  HKEY hKey; // [rsp+30h] [rbp-D0h] BYREF
  HKEY phkResult; // [rsp+38h] [rbp-C8h] BYREF
  int v13; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v14[2044]; // [rsp+44h] [rbp-BCh] BYREF

  hKey = 0;
  phkResult = 0;
  v13 = 0;
  memset_0(v14, 0, sizeof(v14));
  v2 = gIsIphlpEtwTracingAvailable;
  if ( gIsIphlpEtwTracingAvailable )
  {
    if ( !*((_QWORD *)&xmmword_1800AB320 + 1) )
      goto LABEL_8;
    ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gIphlpTemplateFunc)(
      gIphlpEtwContext,
      *((_QWORD *)&xmmword_1800AB320 + 1),
      L"SaveTcpipInfo");
  }
  else
  {
    TraceHlp("SaveTcpipInfo");
  }
  v2 = gIsIphlpEtwTracingAvailable;
  if ( !gIsIphlpEtwTracingAvailable )
  {
LABEL_9:
    TraceHlp("SaveTcpipInfo");
    goto LABEL_10;
  }
  if ( *((_QWORD *)&xmmword_1800AB320 + 1) )
  {
    ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gIphlpTemplateFunc)(
      gIphlpEtwContext,
      *((_QWORD *)&xmmword_1800AB320 + 1),
      L"SaveTcpipInfo");
LABEL_10:
    v2 = gIsIphlpEtwTracingAvailable;
    goto LABEL_11;
  }
LABEL_8:
  if ( !v2 )
    goto LABEL_9;
LABEL_11:
  if ( a1 && *(_QWORD *)(a1 + 8) )
  {
    v3 = RegOpenKeyExW(
           HKEY_LOCAL_MACHINE,
           L"System\\CurrentControlSet\\Services\\Tcpip\\Parameters",
           0,
           0x20006u,
           &hKey);
    v4 = v3;
    if ( v3 )
    {
      if ( v3 != 2 )
      {
        if ( gIsIphlpEtwTracingAvailable )
        {
          if ( !(_QWORD)xmmword_1800AB320 )
            goto LABEL_34;
          v5 = L"System\\CurrentControlSet\\Services\\Tcpip\\Parameters";
          LOWORD(v13) = 0;
          v6 = v3;
LABEL_18:
          FormatRRASErrorString(&v13, L"RegOpenKeyEx(%ws) failed and returned %d", v5, v6);
          v7 = xmmword_1800AB320;
          v8 = (const wchar_t *)&v13;
LABEL_32:
          ((void (__fastcall *)(__int64, __int64, const wchar_t *))gIphlpTemplateFunc)(gIphlpEtwContext, v7, v8);
          goto LABEL_34;
        }
        goto LABEL_19;
      }
    }
    else
    {
      v4 = SaveTcpipParam(hKey, a1);
      if ( v4 )
        goto LABEL_34;
    }
    v9 = RegOpenKeyExW(
           HKEY_LOCAL_MACHINE,
           L"System\\CurrentControlSet\\Services\\NetBT\\Parameters\\Interfaces",
           0,
           0x20006u,
           &phkResult);
    v4 = v9;
    if ( !v9 )
    {
      v4 = SaveWinsParam(phkResult, a1);
      goto LABEL_34;
    }
    if ( v9 == 2 )
    {
      v4 = 0;
      goto LABEL_34;
    }
    if ( gIsIphlpEtwTracingAvailable )
    {
      if ( !(_QWORD)xmmword_1800AB320 )
        goto LABEL_34;
      v5 = L"System\\CurrentControlSet\\Services\\NetBT\\Parameters\\Interfaces";
      LOWORD(v13) = 0;
      v6 = v9;
      goto LABEL_18;
    }
LABEL_19:
    TraceHlp("RegOpenKeyEx(%ws) failed and returned %d");
    goto LABEL_34;
  }
  v4 = 87;
  if ( v2 )
  {
    v7 = xmmword_1800AB320;
    if ( !(_QWORD)xmmword_1800AB320 )
      goto LABEL_34;
    v8 = L"pTcpipInfo or wszAdapterName is NULL";
    goto LABEL_32;
  }
  TraceHlp("pTcpipInfo or wszAdapterName is NULL");
LABEL_34:
  if ( hKey )
    RegCloseKey(hKey);
  if ( phkResult )
    RegCloseKey(phkResult);
  return v4;
}

```

## disassembly

```asm
0x18006d494  mov     [rsp-8+arg_8], rbx
0x18006d499  mov     [rsp-8+arg_10], rdi
0x18006d49e  push    rbp
0x18006d49f  lea     rbp, [rsp-750h]
0x18006d4a7  sub     rsp, 850h
0x18006d4ae  mov     rax, cs:__security_cookie
0x18006d4b5  xor     rax, rsp
0x18006d4b8  mov     [rbp+750h+var_10], rax
0x18006d4bf  mov     rdi, rcx
0x18006d4c2  mov     [rsp+850h+hKey], 0
0x18006d4cb  xor     eax, eax
0x18006d4cd  mov     [rsp+850h+var_818], 0
0x18006d4d6  lea     rcx, [rsp+850h+var_80C]; void *
0x18006d4db  mov     [rsp+850h+var_810], eax
0x18006d4df  xor     edx, edx; Val
0x18006d4e1  mov     r8d, 7FCh; Size
0x18006d4e7  call    memset_0
0x18006d4ec  mov     eax, cs:gIsIphlpEtwTracingAvailable
0x18006d4f2  test    eax, eax
0x18006d4f4  jz      short loc_18006D51E
0x18006d4f6  mov     rdx, qword ptr cs:xmmword_1800AB328
0x18006d4fd  test    rdx, rdx
0x18006d500  jz      short loc_18006D55C
0x18006d502  mov     rcx, cs:gIphlpEtwContext
0x18006d509  lea     r8, aSavetcpipinfo_1; "SaveTcpipInfo"
0x18006d510  mov     rax, cs:gIphlpTemplateFunc
0x18006d517  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d51c  jmp     short loc_18006D52A
0x18006d51e  lea     rcx, aSavetcpipinfo_0; "SaveTcpipInfo"
0x18006d525  call    TraceHlp
0x18006d52a  mov     eax, cs:gIsIphlpEtwTracingAvailable
0x18006d530  test    eax, eax
0x18006d532  jz      short loc_18006D560
0x18006d534  mov     rdx, qword ptr cs:xmmword_1800AB328
0x18006d53b  test    rdx, rdx
0x18006d53e  jz      short loc_18006D55C
0x18006d540  mov     rcx, cs:gIphlpEtwContext
0x18006d547  lea     r8, aSavetcpipinfo_1; "SaveTcpipInfo"
0x18006d54e  mov     rax, cs:gIphlpTemplateFunc
0x18006d555  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d55a  jmp     short loc_18006D56C
0x18006d55c  test    eax, eax
0x18006d55e  jnz     short loc_18006D572
0x18006d560  lea     rcx, aSavetcpipinfo_0; "SaveTcpipInfo"
0x18006d567  call    TraceHlp
0x18006d56c  mov     eax, cs:gIsIphlpEtwTracingAvailable
0x18006d572  test    rdi, rdi
0x18006d575  jz      loc_18006D6B6
0x18006d57b  cmp     qword ptr [rdi+8], 0
0x18006d580  jz      loc_18006D6B6
0x18006d586  lea     rax, [rsp+850h+hKey]
0x18006d58b  mov     r9d, 20006h; samDesired
0x18006d591  xor     r8d, r8d; ulOptions
0x18006d594  mov     [rsp+850h+phkResult], rax; phkResult
0x18006d599  lea     rdx, aSystemCurrentc_4; "System\\CurrentControlSet\\Services\\Tc"...
0x18006d5a0  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18006d5a7  call    cs:__imp_RegOpenKeyExW
0x18006d5ad  mov     ebx, eax
0x18006d5af  test    eax, eax
0x18006d5b1  jz      short loc_18006D61D
0x18006d5b3  cmp     eax, 2
0x18006d5b6  jz      short loc_18006D634
0x18006d5b8  cmp     cs:gIsIphlpEtwTracingAvailable, 0
0x18006d5bf  jz      short loc_18006D602
0x18006d5c1  cmp     qword ptr cs:unk_1800AB320, 0
0x18006d5c9  jz      loc_18006D6F3
0x18006d5cf  xor     ecx, ecx
0x18006d5d1  lea     r8, aSystemCurrentc_4; "System\\CurrentControlSet\\Services\\Tc"...
0x18006d5d8  mov     word ptr [rsp+850h+var_810], cx
0x18006d5dd  mov     r9d, eax
0x18006d5e0  lea     rdx, aRegopenkeyexWs; "RegOpenKeyEx(%ws) failed and returned %"...
0x18006d5e7  lea     rcx, [rsp+850h+var_810]
0x18006d5ec  call    FormatRRASErrorString
0x18006d5f1  mov     rdx, qword ptr cs:unk_1800AB320
0x18006d5f8  lea     r8, [rsp+850h+var_810]
0x18006d5fd  jmp     loc_18006D6D2
0x18006d602  mov     r8d, eax
0x18006d605  lea     rdx, aSystemCurrentc_4; "System\\CurrentControlSet\\Services\\Tc"...
0x18006d60c  lea     rcx, aRegopenkeyexWs_2; "RegOpenKeyEx(%ws) failed and returned %"...
0x18006d613  call    TraceHlp
0x18006d618  jmp     loc_18006D6F3
0x18006d61d  mov     rcx, [rsp+850h+hKey]; hKey
0x18006d622  mov     rdx, rdi
0x18006d625  call    SaveTcpipParam
0x18006d62a  mov     ebx, eax
0x18006d62c  test    eax, eax
0x18006d62e  jnz     loc_18006D6F3
0x18006d634  lea     rax, [rsp+850h+var_818]
0x18006d639  mov     r9d, 20006h; samDesired
0x18006d63f  xor     r8d, r8d; ulOptions
0x18006d642  mov     [rsp+850h+phkResult], rax; phkResult
0x18006d647  lea     rdx, aSystemCurrentc_2; "System\\CurrentControlSet\\Services\\Ne"...
0x18006d64e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18006d655  call    cs:__imp_RegOpenKeyExW
0x18006d65b  mov     ebx, eax
0x18006d65d  test    eax, eax
0x18006d65f  jz      short loc_18006D6A5
0x18006d661  cmp     eax, 2
0x18006d664  jnz     short loc_18006D66D
0x18006d666  xor     ebx, ebx
0x18006d668  jmp     loc_18006D6F3
0x18006d66d  cmp     cs:gIsIphlpEtwTracingAvailable, 0
0x18006d674  jz      short loc_18006D696
0x18006d676  cmp     qword ptr cs:unk_1800AB320, 0
0x18006d67e  jz      short loc_18006D6F3
0x18006d680  xor     eax, eax
0x18006d682  lea     r8, aSystemCurrentc_2; "System\\CurrentControlSet\\Services\\Ne"...
0x18006d689  mov     word ptr [rsp+850h+var_810], ax
0x18006d68e  mov     r9d, ebx
0x18006d691  jmp     loc_18006D5E0
0x18006d696  mov     r8d, ebx
0x18006d699  lea     rdx, aSystemCurrentc_2; "System\\CurrentControlSet\\Services\\Ne"...
0x18006d6a0  jmp     loc_18006D60C
0x18006d6a5  mov     rcx, [rsp+850h+var_818]; hKey
0x18006d6aa  mov     rdx, rdi
0x18006d6ad  call    SaveWinsParam
0x18006d6b2  mov     ebx, eax
0x18006d6b4  jmp     short loc_18006D6F3
0x18006d6b6  mov     ebx, 57h ; 'W'
0x18006d6bb  test    eax, eax
0x18006d6bd  jz      short loc_18006D6E7
0x18006d6bf  mov     rdx, qword ptr cs:unk_1800AB320
0x18006d6c6  test    rdx, rdx
0x18006d6c9  jz      short loc_18006D6F3
0x18006d6cb  lea     r8, aPtcpipinfoOrWs; "pTcpipInfo or wszAdapterName is NULL"
0x18006d6d2  mov     rcx, cs:gIphlpEtwContext
0x18006d6d9  mov     rax, cs:gIphlpTemplateFunc
0x18006d6e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d6e5  jmp     short loc_18006D6F3
0x18006d6e7  lea     rcx, aPtcpipinfoOrWs_0; "pTcpipInfo or wszAdapterName is NULL"
0x18006d6ee  call    TraceHlp
0x18006d6f3  mov     rcx, [rsp+850h+hKey]; hKey
0x18006d6f8  test    rcx, rcx
0x18006d6fb  jz      short loc_18006D703
0x18006d6fd  call    cs:__imp_RegCloseKey
0x18006d703  mov     rcx, [rsp+850h+var_818]; hKey
0x18006d708  test    rcx, rcx
0x18006d70b  jz      short loc_18006D713
0x18006d70d  call    cs:__imp_RegCloseKey
0x18006d713  mov     eax, ebx
0x18006d715  mov     rcx, [rbp+750h+var_10]
0x18006d71c  xor     rcx, rsp; StackCookie
0x18006d71f  call    __security_check_cookie
0x18006d724  lea     r11, [rsp+850h+var_s0]
0x18006d72c  mov     rbx, [r11+18h]
0x18006d730  mov     rdi, [r11+20h]
0x18006d734  mov     rsp, r11
0x18006d737  pop     rbp
0x18006d738  retn
```
