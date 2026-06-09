# GetSstpIsHttps

- ea: `0x180006168`
- end: `0x180006370`
- name: `GetSstpIsHttps`
- size: `520`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task`

## callers

- `0x180005ea0`

## callees

- `0x180006168`
- `0x18000a044`
- `0x18000acbc`
- `0x18000ae4e`
- `0x18000ae80`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800061fb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800061fb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006347`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006347`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800062b1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800062b1`

## string_xrefs

- `0x1800061d7`: `System\CurrentControlSet\Services\SstpSvc\Parameters`
- `0x180006249`: `Unable to open the parameter store for SSTPSVC: %d`

## pseudocode

```c
unsigned int __fastcall GetSstpIsHttps(__int64 a1, unsigned int *a2)
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
  if ( !a1 )
    a1 = -2147483646;
  v4 = RegOpenKeyExW((HKEY)a1, L"System\\CurrentControlSet\\Services\\SstpSvc\\Parameters", 0, 0x20019u, &hKey);
  v6 = v4;
  if ( v4 )
  {
    *a2 = 1;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 145, v5, v4);
    }
    if ( (_QWORD)xmmword_1800146E0 )
    {
      LOWORD(v14) = 0;
      FormatRRASErrorString(&v14, L"Unable to open the parameter store for SSTPSVC: %d", v6);
      ((void (__fastcall *)(__int64, _QWORD, int *))gSstpCfgTemplateFunc)(gSstpCfgEtwContext, xmmword_1800146E0, &v14);
    }
  }
  cbData = 4;
  result = RegQueryValueExW(hKey, L"UseHttps", 0, &Type, Data, &cbData);
  v9 = result;
  if ( result )
  {
    *a2 = 1;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      result = WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 146, v8, result);
    }
    if ( (_QWORD)xmmword_1800146E0 )
    {
      LOWORD(v14) = 0;
      FormatRRASErrorString(&v14, L"Unable to get UseHttps value - assuming enabled: %d", v9);
      result = ((__int64 (__fastcall *)(__int64, _QWORD, int *))gSstpCfgTemplateFunc)(
                 gSstpCfgEtwContext,
                 xmmword_1800146E0,
                 &v14);
    }
  }
  else
  {
    result = *(_DWORD *)Data != 0;
    *a2 = result;
  }
  if ( hKey )
    return RegCloseKey(hKey);
  return result;
}

```

## disassembly

```asm
0x180006168  mov     [rsp-8+arg_10], rbx
0x18000616d  push    rbp
0x18000616e  push    rdi
0x18000616f  push    r15
0x180006171  lea     rbp, [rsp-760h]
0x180006179  sub     rsp, 860h
0x180006180  mov     rax, cs:__security_cookie
0x180006187  xor     rax, rsp
0x18000618a  mov     [rbp+770h+var_20], rax
0x180006191  mov     rdi, rdx
0x180006194  mov     [rsp+870h+hKey], 0
0x18000619d  mov     rbx, rcx
0x1800061a0  mov     [rsp+870h+Type], 0
0x1800061a8  xor     eax, eax
0x1800061aa  mov     [rsp+870h+cbData], 0
0x1800061b2  xor     edx, edx; Val
0x1800061b4  mov     [rsp+870h+var_820], eax
0x1800061b8  lea     rcx, [rsp+870h+var_81C]; void *
0x1800061bd  mov     dword ptr [rsp+870h+Data], 0
0x1800061c5  mov     r8d, 7FCh; Size
0x1800061cb  call    memset_0
0x1800061d0  mov     rax, 0FFFFFFFF80000002h
0x1800061d7  lea     rdx, SubKey; "System\\CurrentControlSet\\Services\\Ss"...
0x1800061de  test    rbx, rbx
0x1800061e1  mov     r9d, 20019h; samDesired
0x1800061e7  cmovz   rbx, rax
0x1800061eb  lea     rax, [rsp+870h+hKey]
0x1800061f0  mov     rcx, rbx; hKey
0x1800061f3  mov     [rsp+870h+phkResult], rax; phkResult
0x1800061f8  xor     r8d, r8d; ulOptions
0x1800061fb  call    cs:__imp_RegOpenKeyExW
0x180006201  lea     r15, WPP_GLOBAL_Control
0x180006208  mov     ebx, eax
0x18000620a  test    eax, eax
0x18000620c  jz      short loc_180006281
0x18000620e  mov     dword ptr [rdi], 1
0x180006214  mov     rcx, cs:WPP_GLOBAL_Control
0x18000621b  cmp     rcx, r15
0x18000621e  jz      short loc_18000623D
0x180006220  test    byte ptr [rcx+1Ch], 40h
0x180006224  jz      short loc_18000623D
0x180006226  cmp     byte ptr [rcx+19h], 1
0x18000622a  jb      short loc_18000623D
0x18000622c  mov     rcx, [rcx+10h]
0x180006230  mov     edx, 91h
0x180006235  mov     r9d, eax
0x180006238  call    WPP_SF_d
0x18000623d  cmp     qword ptr cs:xmmword_1800146E0, 0
0x180006245  jz      short loc_180006281
0x180006247  xor     eax, eax
0x180006249  lea     rdx, aUnableToOpenTh_1; "Unable to open the parameter store for "...
0x180006250  mov     r8d, ebx
0x180006253  mov     word ptr [rsp+870h+var_820], ax
0x180006258  lea     rcx, [rsp+870h+var_820]
0x18000625d  call    FormatRRASErrorString
0x180006262  mov     rdx, qword ptr cs:xmmword_1800146E0
0x180006269  lea     r8, [rsp+870h+var_820]
0x18000626e  mov     rcx, cs:gSstpCfgEtwContext
0x180006275  mov     rax, cs:gSstpCfgTemplateFunc
0x18000627c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006281  mov     rcx, [rsp+870h+hKey]; hKey
0x180006286  lea     rax, [rsp+870h+cbData]
0x18000628b  mov     [rsp+870h+lpcbData], rax; lpcbData
0x180006290  lea     r9, [rsp+870h+Type]; lpType
0x180006295  lea     rax, [rsp+870h+Data]
0x18000629a  mov     [rsp+870h+cbData], 4
0x1800062a2  xor     r8d, r8d; lpReserved
0x1800062a5  mov     [rsp+870h+phkResult], rax; lpData
0x1800062aa  lea     rdx, aUsehttps; "UseHttps"
0x1800062b1  call    cs:__imp_RegQueryValueExW
0x1800062b7  mov     ebx, eax
0x1800062b9  test    eax, eax
0x1800062bb  jz      short loc_180006332
0x1800062bd  mov     dword ptr [rdi], 1
0x1800062c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800062ca  cmp     rcx, r15
0x1800062cd  jz      short loc_1800062EC
0x1800062cf  test    byte ptr [rcx+1Ch], 40h
0x1800062d3  jz      short loc_1800062EC
0x1800062d5  cmp     byte ptr [rcx+19h], 1
0x1800062d9  jb      short loc_1800062EC
0x1800062db  mov     rcx, [rcx+10h]
0x1800062df  mov     edx, 92h
0x1800062e4  mov     r9d, eax
0x1800062e7  call    WPP_SF_d
0x1800062ec  cmp     qword ptr cs:xmmword_1800146E0, 0
0x1800062f4  jz      short loc_18000633D
0x1800062f6  xor     eax, eax
0x1800062f8  lea     rdx, aUnableToGetUse; "Unable to get UseHttps value - assuming"...
0x1800062ff  mov     r8d, ebx
0x180006302  mov     word ptr [rsp+870h+var_820], ax
0x180006307  lea     rcx, [rsp+870h+var_820]
0x18000630c  call    FormatRRASErrorString
0x180006311  mov     rdx, qword ptr cs:xmmword_1800146E0
0x180006318  lea     r8, [rsp+870h+var_820]
0x18000631d  mov     rcx, cs:gSstpCfgEtwContext
0x180006324  mov     rax, cs:gSstpCfgTemplateFunc
0x18000632b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006330  jmp     short loc_18000633D
0x180006332  xor     eax, eax
0x180006334  cmp     dword ptr [rsp+870h+Data], eax
0x180006338  setnz   al
0x18000633b  mov     [rdi], eax
0x18000633d  mov     rcx, [rsp+870h+hKey]; hKey
0x180006342  test    rcx, rcx
0x180006345  jz      short loc_18000634D
0x180006347  call    cs:__imp_RegCloseKey
0x18000634d  mov     rcx, [rbp+770h+var_20]
0x180006354  xor     rcx, rsp; StackCookie
0x180006357  call    __security_check_cookie
0x18000635c  mov     rbx, [rsp+870h+arg_10]
0x180006364  add     rsp, 860h
0x18000636b  pop     r15
0x18000636d  pop     rdi
0x18000636e  pop     rbp
0x18000636f  retn
```
