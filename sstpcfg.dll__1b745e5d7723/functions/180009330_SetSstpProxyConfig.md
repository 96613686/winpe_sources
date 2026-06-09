# SetSstpProxyConfig

- ea: `0x180009330`
- end: `0x180009547`
- name: `SetSstpProxyConfig`
- size: `535`
- prototype: `__int64 __fastcall(__int64, int)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, service_task`

## callees

- `0x180009330`
- `0x18000a014`
- `0x18000a044`
- `0x18000acbc`
- `0x18000ae4e`
- `0x18000ae80`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800093b4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800093b4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800094f5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800094f5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180009470`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180009470`

## string_xrefs

- `0x180009390`: `System\CurrentControlSet\Services\SstpSvc\Parameters`
- `0x18000940b`: `Unable to open the SSTPSVC Params Key: %d`

## pseudocode

```c
__int64 __fastcall SetSstpProxyConfig(__int64 a1, int a2)
{
  unsigned int v4; // eax
  __int64 v5; // r8
  unsigned int v6; // ebx
  _QWORD *v7; // rcx
  unsigned int v8; // eax
  __int64 v9; // r8
  BYTE Data[8]; // [rsp+30h] [rbp-D0h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  int v13; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v14[2044]; // [rsp+44h] [rbp-BCh] BYREF

  hKey = 0;
  *(_DWORD *)Data = 1;
  v13 = 0;
  memset_0(v14, 0, sizeof(v14));
  if ( !a1 )
    a1 = -2147483646;
  v4 = RegOpenKeyExW((HKEY)a1, L"System\\CurrentControlSet\\Services\\SstpSvc\\Parameters", 0, 0x2001Fu, &hKey);
  v6 = v4;
  if ( !v4 )
  {
    *(_DWORD *)Data = a2;
    v8 = RegSetValueExW(hKey, L"ProxyEnabled", 0, 4u, Data, 4u);
    v6 = v8;
    if ( v8 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 203, v9, v8);
      }
      if ( (_QWORD)xmmword_1800146E0 )
      {
        LOWORD(v13) = 0;
        FormatRRASErrorString(&v13, L"Trying to store HTTP usage failed %d", v6);
        ((void (__fastcall *)(__int64, _QWORD, int *))gSstpCfgTemplateFunc)(gSstpCfgEtwContext, xmmword_1800146E0, &v13);
      }
    }
    RegCloseKey(hKey);
    goto LABEL_18;
  }
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 202, v5, v4);
    v7 = WPP_GLOBAL_Control;
  }
  if ( (_QWORD)xmmword_1800146E0 )
  {
    LOWORD(v13) = 0;
    FormatRRASErrorString(&v13, L"Unable to open the SSTPSVC Params Key: %d", v6);
    ((void (__fastcall *)(__int64, _QWORD, int *))gSstpCfgTemplateFunc)(gSstpCfgEtwContext, xmmword_1800146E0, &v13);
LABEL_18:
    v7 = WPP_GLOBAL_Control;
  }
  if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 0xC0) == 0xC0 )
    WPP_SF_(v7[2], 204);
  return v6;
}

```

## disassembly

```asm
0x180009330  mov     [rsp-8+arg_10], rbx
0x180009335  mov     [rsp-8+arg_18], rdi
0x18000933a  push    rbp
0x18000933b  lea     rbp, [rsp-750h]
0x180009343  sub     rsp, 850h
0x18000934a  mov     rax, cs:__security_cookie
0x180009351  xor     rax, rsp
0x180009354  mov     [rbp+750h+var_10], rax
0x18000935b  mov     edi, edx
0x18000935d  mov     [rsp+850h+hKey], 0
0x180009366  mov     rbx, rcx
0x180009369  mov     dword ptr [rsp+850h+Data], 1
0x180009371  xor     eax, eax
0x180009373  lea     rcx, [rsp+850h+var_80C]; void *
0x180009378  xor     edx, edx; Val
0x18000937a  mov     [rsp+850h+var_810], eax
0x18000937e  mov     r8d, 7FCh; Size
0x180009384  call    memset_0
0x180009389  mov     rax, 0FFFFFFFF80000002h
0x180009390  lea     rdx, SubKey; "System\\CurrentControlSet\\Services\\Ss"...
0x180009397  test    rbx, rbx
0x18000939a  mov     r9d, 2001Fh; samDesired
0x1800093a0  cmovz   rbx, rax
0x1800093a4  lea     rax, [rsp+850h+hKey]
0x1800093a9  mov     rcx, rbx; hKey
0x1800093ac  mov     [rsp+850h+phkResult], rax; phkResult
0x1800093b1  xor     r8d, r8d; ulOptions
0x1800093b4  call    cs:__imp_RegOpenKeyExW
0x1800093ba  mov     ebx, eax
0x1800093bc  test    eax, eax
0x1800093be  jz      loc_180009448
0x1800093c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800093cb  lea     rdi, WPP_GLOBAL_Control
0x1800093d2  cmp     rcx, rdi
0x1800093d5  jz      short loc_1800093FB
0x1800093d7  test    byte ptr [rcx+1Ch], 40h
0x1800093db  jz      short loc_1800093FB
0x1800093dd  cmp     byte ptr [rcx+19h], 1
0x1800093e1  jb      short loc_1800093FB
0x1800093e3  mov     rcx, [rcx+10h]
0x1800093e7  mov     edx, 0CAh
0x1800093ec  mov     r9d, eax
0x1800093ef  call    WPP_SF_d
0x1800093f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800093fb  cmp     qword ptr cs:xmmword_1800146E0, 0
0x180009403  jz      loc_180009502
0x180009409  xor     eax, eax
0x18000940b  lea     rdx, aUnableToOpenTh; "Unable to open the SSTPSVC Params Key: "...
0x180009412  mov     r8d, ebx
0x180009415  mov     word ptr [rsp+850h+var_810], ax
0x18000941a  lea     rcx, [rsp+850h+var_810]
0x18000941f  call    FormatRRASErrorString
0x180009424  mov     rdx, qword ptr cs:xmmword_1800146E0
0x18000942b  lea     r8, [rsp+850h+var_810]
0x180009430  mov     rcx, cs:gSstpCfgEtwContext
0x180009437  mov     rax, cs:gSstpCfgTemplateFunc
0x18000943e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009443  jmp     loc_1800094FB
0x180009448  mov     rcx, [rsp+850h+hKey]; hKey
0x18000944d  lea     rax, [rsp+850h+Data]
0x180009452  mov     r9d, 4; dwType
0x180009458  mov     dword ptr [rsp+850h+Data], edi
0x18000945c  mov     [rsp+850h+cbData], r9d; cbData
0x180009461  lea     rdx, aProxyenabled; "ProxyEnabled"
0x180009468  xor     r8d, r8d; Reserved
0x18000946b  mov     [rsp+850h+phkResult], rax; lpData
0x180009470  call    cs:__imp_RegSetValueExW
0x180009476  lea     rdi, WPP_GLOBAL_Control
0x18000947d  mov     ebx, eax
0x18000947f  test    eax, eax
0x180009481  jz      short loc_1800094F0
0x180009483  mov     rcx, cs:WPP_GLOBAL_Control
0x18000948a  cmp     rcx, rdi
0x18000948d  jz      short loc_1800094AC
0x18000948f  test    byte ptr [rcx+1Ch], 40h
0x180009493  jz      short loc_1800094AC
0x180009495  cmp     byte ptr [rcx+19h], 2
0x180009499  jb      short loc_1800094AC
0x18000949b  mov     rcx, [rcx+10h]
0x18000949f  mov     edx, 0CBh
0x1800094a4  mov     r9d, eax
0x1800094a7  call    WPP_SF_d
0x1800094ac  cmp     qword ptr cs:xmmword_1800146E0, 0
0x1800094b4  jz      short loc_1800094F0
0x1800094b6  xor     eax, eax
0x1800094b8  lea     rdx, aTryingToStoreH_0; "Trying to store HTTP usage failed %d"
0x1800094bf  mov     r8d, ebx
0x1800094c2  mov     word ptr [rsp+850h+var_810], ax
0x1800094c7  lea     rcx, [rsp+850h+var_810]
0x1800094cc  call    FormatRRASErrorString
0x1800094d1  mov     rdx, qword ptr cs:xmmword_1800146E0
0x1800094d8  lea     r8, [rsp+850h+var_810]
0x1800094dd  mov     rcx, cs:gSstpCfgEtwContext
0x1800094e4  mov     rax, cs:gSstpCfgTemplateFunc
0x1800094eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800094f0  mov     rcx, [rsp+850h+hKey]; hKey
0x1800094f5  call    cs:__imp_RegCloseKey
0x1800094fb  mov     rcx, cs:WPP_GLOBAL_Control
0x180009502  cmp     rcx, rdi
0x180009505  jz      short loc_180009521
0x180009507  mov     eax, [rcx+1Ch]
0x18000950a  and     eax, 0C0h
0x18000950f  cmp     al, 0C0h
0x180009511  jnz     short loc_180009521
0x180009513  mov     rcx, [rcx+10h]
0x180009517  mov     edx, 0CCh
0x18000951c  call    WPP_SF_
0x180009521  mov     eax, ebx
0x180009523  mov     rcx, [rbp+750h+var_10]
0x18000952a  xor     rcx, rsp; StackCookie
0x18000952d  call    __security_check_cookie
0x180009532  lea     r11, [rsp+850h+var_s0]
0x18000953a  mov     rbx, [r11+20h]
0x18000953e  mov     rdi, [r11+28h]
0x180009542  mov     rsp, r11
0x180009545  pop     rbp
0x180009546  retn
```
