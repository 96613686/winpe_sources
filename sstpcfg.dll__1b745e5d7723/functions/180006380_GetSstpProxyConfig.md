# GetSstpProxyConfig

- ea: `0x180006380`
- end: `0x180006584`
- name: `GetSstpProxyConfig`
- size: `516`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, service_task`

## callees

- `0x180006380`
- `0x18000a044`
- `0x18000acbc`
- `0x18000ae4e`
- `0x18000ae80`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180006419`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180006419`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000655b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000655b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800064c9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800064c9`

## string_xrefs

- `0x1800063f8`: `System\CurrentControlSet\Services\SstpSvc\Parameters`
- `0x180006461`: `Unable to open the parameter store for SSTPSVC: %d`

## pseudocode

```c
unsigned int __fastcall GetSstpProxyConfig(__int64 a1, _DWORD *a2)
{
  unsigned int v4; // eax
  __int64 v5; // r8
  unsigned int v6; // ebx
  unsigned int result; // eax
  __int64 v8; // r8
  unsigned int v9; // ebx
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  BYTE Data[4]; // [rsp+34h] [rbp-CCh] BYREF
  DWORD Type; // [rsp+38h] [rbp-C8h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-C0h] BYREF
  int v14; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v15[2044]; // [rsp+54h] [rbp-ACh] BYREF

  hKey = 0;
  Type = 0;
  cbData = 0;
  v14 = 0;
  *(_DWORD *)Data = 0;
  memset_0(v15, 0, sizeof(v15));
  *a2 = 0;
  if ( !a1 )
    a1 = -2147483646;
  v4 = RegOpenKeyExW((HKEY)a1, L"System\\CurrentControlSet\\Services\\SstpSvc\\Parameters", 0, 0x20019u, &hKey);
  v6 = v4;
  if ( v4 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 205, v5, v4);
    }
    if ( (_QWORD)xmmword_1800146E0 )
    {
      LOWORD(v14) = 0;
      FormatRRASErrorString(&v14, L"Unable to open the parameter store for SSTPSVC: %d", v6);
      ((void (__fastcall *)(__int64, _QWORD, int *))gSstpCfgTemplateFunc)(gSstpCfgEtwContext, xmmword_1800146E0, &v14);
    }
  }
  cbData = 4;
  result = RegQueryValueExW(hKey, L"ProxyEnabled", 0, &Type, Data, &cbData);
  v9 = result;
  if ( result )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      result = WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 206, v8, result);
    }
    if ( (_QWORD)xmmword_1800146E0 )
    {
      LOWORD(v14) = 0;
      FormatRRASErrorString(&v14, L"Unable to get ProxyEnabled value - assuming disabled: %d", v9);
      result = ((__int64 (__fastcall *)(__int64, _QWORD, int *))gSstpCfgTemplateFunc)(
                 gSstpCfgEtwContext,
                 xmmword_1800146E0,
                 &v14);
    }
  }
  else if ( *(_DWORD *)Data )
  {
    *a2 = 1;
  }
  if ( hKey )
    return RegCloseKey(hKey);
  return result;
}

```

## disassembly

```asm
0x180006380  mov     [rsp-8+arg_10], rbx
0x180006385  push    rbp
0x180006386  push    rdi
0x180006387  push    r14
0x180006389  lea     rbp, [rsp-760h]
0x180006391  sub     rsp, 860h
0x180006398  mov     rax, cs:__security_cookie
0x18000639f  xor     rax, rsp
0x1800063a2  mov     [rbp+770h+var_20], rax
0x1800063a9  mov     rdi, rdx
0x1800063ac  mov     [rsp+870h+hKey], 0
0x1800063b5  mov     rbx, rcx
0x1800063b8  mov     [rsp+870h+Type], 0
0x1800063c0  xor     eax, eax
0x1800063c2  mov     [rsp+870h+cbData], 0
0x1800063ca  xor     edx, edx; Val
0x1800063cc  mov     [rsp+870h+var_820], eax
0x1800063d0  lea     rcx, [rsp+870h+var_81C]; void *
0x1800063d5  mov     dword ptr [rsp+870h+Data], 0
0x1800063dd  mov     r8d, 7FCh; Size
0x1800063e3  call    memset_0
0x1800063e8  mov     rax, 0FFFFFFFF80000002h
0x1800063ef  mov     dword ptr [rdi], 0
0x1800063f5  test    rbx, rbx
0x1800063f8  lea     rdx, SubKey; "System\\CurrentControlSet\\Services\\Ss"...
0x1800063ff  mov     r9d, 20019h; samDesired
0x180006405  cmovz   rbx, rax
0x180006409  lea     rax, [rsp+870h+hKey]
0x18000640e  mov     rcx, rbx; hKey
0x180006411  mov     [rsp+870h+phkResult], rax; phkResult
0x180006416  xor     r8d, r8d; ulOptions
0x180006419  call    cs:__imp_RegOpenKeyExW
0x18000641f  lea     r14, WPP_GLOBAL_Control
0x180006426  mov     ebx, eax
0x180006428  test    eax, eax
0x18000642a  jz      short loc_180006499
0x18000642c  mov     rcx, cs:WPP_GLOBAL_Control
0x180006433  cmp     rcx, r14
0x180006436  jz      short loc_180006455
0x180006438  test    byte ptr [rcx+1Ch], 40h
0x18000643c  jz      short loc_180006455
0x18000643e  cmp     byte ptr [rcx+19h], 1
0x180006442  jb      short loc_180006455
0x180006444  mov     rcx, [rcx+10h]
0x180006448  mov     edx, 0CDh
0x18000644d  mov     r9d, eax
0x180006450  call    WPP_SF_d
0x180006455  cmp     qword ptr cs:xmmword_1800146E0, 0
0x18000645d  jz      short loc_180006499
0x18000645f  xor     eax, eax
0x180006461  lea     rdx, aUnableToOpenTh_1; "Unable to open the parameter store for "...
0x180006468  mov     r8d, ebx
0x18000646b  mov     word ptr [rsp+870h+var_820], ax
0x180006470  lea     rcx, [rsp+870h+var_820]
0x180006475  call    FormatRRASErrorString
0x18000647a  mov     rdx, qword ptr cs:xmmword_1800146E0
0x180006481  lea     r8, [rsp+870h+var_820]
0x180006486  mov     rcx, cs:gSstpCfgEtwContext
0x18000648d  mov     rax, cs:gSstpCfgTemplateFunc
0x180006494  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006499  mov     rcx, [rsp+870h+hKey]; hKey
0x18000649e  lea     rax, [rsp+870h+cbData]
0x1800064a3  mov     [rsp+870h+lpcbData], rax; lpcbData
0x1800064a8  lea     r9, [rsp+870h+Type]; lpType
0x1800064ad  lea     rax, [rsp+870h+Data]
0x1800064b2  mov     [rsp+870h+cbData], 4
0x1800064ba  xor     r8d, r8d; lpReserved
0x1800064bd  mov     [rsp+870h+phkResult], rax; lpData
0x1800064c2  lea     rdx, aProxyenabled; "ProxyEnabled"
0x1800064c9  call    cs:__imp_RegQueryValueExW
0x1800064cf  mov     ebx, eax
0x1800064d1  test    eax, eax
0x1800064d3  jz      short loc_180006544
0x1800064d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800064dc  cmp     rcx, r14
0x1800064df  jz      short loc_1800064FE
0x1800064e1  test    byte ptr [rcx+1Ch], 40h
0x1800064e5  jz      short loc_1800064FE
0x1800064e7  cmp     byte ptr [rcx+19h], 1
0x1800064eb  jb      short loc_1800064FE
0x1800064ed  mov     rcx, [rcx+10h]
0x1800064f1  mov     edx, 0CEh
0x1800064f6  mov     r9d, eax
0x1800064f9  call    WPP_SF_d
0x1800064fe  cmp     qword ptr cs:xmmword_1800146E0, 0
0x180006506  jz      short loc_180006551
0x180006508  xor     eax, eax
0x18000650a  lea     rdx, aUnableToGetPro; "Unable to get ProxyEnabled value - assu"...
0x180006511  mov     r8d, ebx
0x180006514  mov     word ptr [rsp+870h+var_820], ax
0x180006519  lea     rcx, [rsp+870h+var_820]
0x18000651e  call    FormatRRASErrorString
0x180006523  mov     rdx, qword ptr cs:xmmword_1800146E0
0x18000652a  lea     r8, [rsp+870h+var_820]
0x18000652f  mov     rcx, cs:gSstpCfgEtwContext
0x180006536  mov     rax, cs:gSstpCfgTemplateFunc
0x18000653d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006542  jmp     short loc_180006551
0x180006544  cmp     dword ptr [rsp+870h+Data], 0
0x180006549  jz      short loc_180006551
0x18000654b  mov     dword ptr [rdi], 1
0x180006551  mov     rcx, [rsp+870h+hKey]; hKey
0x180006556  test    rcx, rcx
0x180006559  jz      short loc_180006561
0x18000655b  call    cs:__imp_RegCloseKey
0x180006561  mov     rcx, [rbp+770h+var_20]
0x180006568  xor     rcx, rsp; StackCookie
0x18000656b  call    __security_check_cookie
0x180006570  mov     rbx, [rsp+870h+arg_10]
0x180006578  add     rsp, 860h
0x18000657f  pop     r14
0x180006581  pop     rdi
0x180006582  pop     rbp
0x180006583  retn
```
