# GetSstpServerConfig

- ea: `0x180006590`
- end: `0x18000678b`
- name: `GetSstpServerConfig`
- size: `507`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, service_task`

## callees

- `0x180006590`
- `0x180006794`
- `0x18000a014`
- `0x18000a044`
- `0x18000a338`
- `0x18000acbc`
- `0x18000ae4e`
- `0x18000ae80`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180006631`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180006631`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000664f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000664f`

## string_xrefs

- `0x180006610`: `System\CurrentControlSet\Services\SstpSvc\Parameters`
- `0x180006693`: `GetServerConfig: Unable to open the config store: %d`
- `0x18000670e`: `Server ConfigInfo: UseHttps: %!bool! Port: %d`

## pseudocode

```c
unsigned int __fastcall GetSstpServerConfig(unsigned __int8 *a1)
{
  unsigned int result; // eax
  __int64 v3; // rdx
  __int64 v4; // r8
  unsigned int v5; // edi
  _QWORD *v6; // rcx
  __int64 v7; // r9
  __int64 v8; // r8
  HKEY hKey; // [rsp+30h] [rbp-D0h] BYREF
  int v10; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v11[2044]; // [rsp+44h] [rbp-BCh] BYREF

  hKey = 0;
  v10 = 0;
  memset_0(v11, 0, sizeof(v11));
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0xC0) == 0xC0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 160);
  *a1 = 1;
  *((_WORD *)a1 + 1) = 0;
  result = RegOpenKeyExW(
             HKEY_LOCAL_MACHINE,
             L"System\\CurrentControlSet\\Services\\SstpSvc\\Parameters",
             0,
             0x20019u,
             &hKey);
  v5 = result;
  if ( !result )
  {
    GetSstpServerConfigp(hKey);
    result = RegCloseKey(hKey);
LABEL_12:
    v6 = WPP_GLOBAL_Control;
    goto LABEL_13;
  }
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) )
  {
    result = WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 161, v4, result);
    v6 = WPP_GLOBAL_Control;
  }
  if ( (_QWORD)xmmword_1800146E0 )
  {
    LOWORD(v10) = 0;
    FormatRRASErrorString(&v10, L"GetServerConfig: Unable to open the config store: %d", v5);
    result = ((__int64 (__fastcall *)(__int64, _QWORD, int *))gSstpCfgTemplateFunc)(
               gSstpCfgEtwContext,
               xmmword_1800146E0,
               &v10);
    goto LABEL_12;
  }
LABEL_13:
  if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 0x40) != 0 && *((_BYTE *)v6 + 25) >= 2u )
  {
    result = WPP_SF_ld(v6[2], v3, v4, *a1, *((unsigned __int16 *)a1 + 1));
    v6 = WPP_GLOBAL_Control;
  }
  if ( *((_QWORD *)&xmmword_1800146E0 + 1) )
  {
    v7 = *((unsigned __int16 *)a1 + 1);
    v8 = *a1;
    LOWORD(v10) = 0;
    FormatRRASErrorString(&v10, L"Server ConfigInfo: UseHttps: %!bool! Port: %d", v8, v7);
    result = ((__int64 (__fastcall *)(__int64, _QWORD, int *))gSstpCfgTemplateFunc)(
               gSstpCfgEtwContext,
               *((_QWORD *)&xmmword_1800146E0 + 1),
               &v10);
    v6 = WPP_GLOBAL_Control;
  }
  if ( v6 != &WPP_GLOBAL_Control )
  {
    result = *((_DWORD *)v6 + 7) & 0xC0;
    if ( (*((_BYTE *)v6 + 28) & 0xC0) == 0xC0 )
      return WPP_SF_(v6[2], 163);
  }
  return result;
}

```

## disassembly

```asm
0x180006590  push    rbp
0x180006592  push    rbx
0x180006593  push    rdi
0x180006594  push    r15
0x180006596  lea     rbp, [rsp-758h]
0x18000659e  sub     rsp, 858h
0x1800065a5  mov     rax, cs:__security_cookie
0x1800065ac  xor     rax, rsp
0x1800065af  mov     [rbp+770h+var_30], rax
0x1800065b6  mov     rbx, rcx
0x1800065b9  mov     [rsp+870h+hKey], 0
0x1800065c2  xor     eax, eax
0x1800065c4  lea     rcx, [rsp+870h+var_82C]; void *
0x1800065c9  xor     edx, edx; Val
0x1800065cb  mov     [rsp+870h+var_830], eax
0x1800065cf  mov     r8d, 7FCh; Size
0x1800065d5  call    memset_0
0x1800065da  mov     rcx, cs:WPP_GLOBAL_Control
0x1800065e1  lea     r15, WPP_GLOBAL_Control
0x1800065e8  cmp     rcx, r15
0x1800065eb  jz      short loc_180006607
0x1800065ed  mov     eax, [rcx+1Ch]
0x1800065f0  and     eax, 0C0h
0x1800065f5  cmp     al, 0C0h
0x1800065f7  jnz     short loc_180006607
0x1800065f9  mov     rcx, [rcx+10h]
0x1800065fd  mov     edx, 0A0h
0x180006602  call    WPP_SF_
0x180006607  xor     eax, eax
0x180006609  mov     byte ptr [rbx], 1
0x18000660c  mov     [rbx+2], ax
0x180006610  lea     rdx, SubKey; "System\\CurrentControlSet\\Services\\Ss"...
0x180006617  lea     rax, [rsp+870h+hKey]
0x18000661c  mov     r9d, 20019h; samDesired
0x180006622  xor     r8d, r8d; ulOptions
0x180006625  mov     [rsp+870h+phkResult], rax; phkResult
0x18000662a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180006631  call    cs:__imp_RegOpenKeyExW
0x180006637  mov     edi, eax
0x180006639  test    eax, eax
0x18000663b  jnz     short loc_180006657
0x18000663d  mov     rcx, [rsp+870h+hKey]; hKey
0x180006642  mov     rdx, rbx
0x180006645  call    GetSstpServerConfigp
0x18000664a  mov     rcx, [rsp+870h+hKey]; hKey
0x18000664f  call    cs:__imp_RegCloseKey
0x180006655  jmp     short loc_1800066CB
0x180006657  mov     rcx, cs:WPP_GLOBAL_Control
0x18000665e  cmp     rcx, r15
0x180006661  jz      short loc_180006687
0x180006663  test    byte ptr [rcx+1Ch], 40h
0x180006667  jz      short loc_180006687
0x180006669  cmp     byte ptr [rcx+19h], 1
0x18000666d  jb      short loc_180006687
0x18000666f  mov     rcx, [rcx+10h]
0x180006673  mov     edx, 0A1h
0x180006678  mov     r9d, edi
0x18000667b  call    WPP_SF_d
0x180006680  mov     rcx, cs:WPP_GLOBAL_Control
0x180006687  cmp     qword ptr cs:xmmword_1800146E0, 0
0x18000668f  jz      short loc_1800066D2
0x180006691  xor     eax, eax
0x180006693  lea     rdx, aGetserverconfi; "GetServerConfig: Unable to open the con"...
0x18000669a  mov     r8d, edi
0x18000669d  mov     word ptr [rsp+870h+var_830], ax
0x1800066a2  lea     rcx, [rsp+870h+var_830]
0x1800066a7  call    FormatRRASErrorString
0x1800066ac  mov     rdx, qword ptr cs:xmmword_1800146E0
0x1800066b3  lea     r8, [rsp+870h+var_830]
0x1800066b8  mov     rcx, cs:gSstpCfgEtwContext
0x1800066bf  mov     rax, cs:gSstpCfgTemplateFunc
0x1800066c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800066cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800066d2  cmp     rcx, r15
0x1800066d5  jz      short loc_1800066FF
0x1800066d7  test    byte ptr [rcx+1Ch], 40h
0x1800066db  jz      short loc_1800066FF
0x1800066dd  cmp     byte ptr [rcx+19h], 2
0x1800066e1  jb      short loc_1800066FF
0x1800066e3  movzx   eax, word ptr [rbx+2]
0x1800066e7  movzx   r9d, byte ptr [rbx]
0x1800066eb  mov     rcx, [rcx+10h]
0x1800066ef  mov     dword ptr [rsp+870h+phkResult], eax
0x1800066f3  call    WPP_SF_ld
0x1800066f8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800066ff  cmp     qword ptr cs:xmmword_1800146E0+8, 0
0x180006707  jz      short loc_180006750
0x180006709  movzx   r9d, word ptr [rbx+2]
0x18000670e  lea     rdx, aServerConfigin; "Server ConfigInfo: UseHttps: %!bool! Po"...
0x180006715  movzx   r8d, byte ptr [rbx]
0x180006719  lea     rcx, [rsp+870h+var_830]
0x18000671e  xor     eax, eax
0x180006720  mov     word ptr [rsp+870h+var_830], ax
0x180006725  call    FormatRRASErrorString
0x18000672a  mov     rdx, qword ptr cs:xmmword_1800146E0+8
0x180006731  lea     r8, [rsp+870h+var_830]
0x180006736  mov     rcx, cs:gSstpCfgEtwContext
0x18000673d  mov     rax, cs:gSstpCfgTemplateFunc
0x180006744  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006749  mov     rcx, cs:WPP_GLOBAL_Control
0x180006750  cmp     rcx, r15
0x180006753  jz      short loc_18000676F
0x180006755  mov     eax, [rcx+1Ch]
0x180006758  and     eax, 0C0h
0x18000675d  cmp     al, 0C0h
0x18000675f  jnz     short loc_18000676F
0x180006761  mov     rcx, [rcx+10h]
0x180006765  mov     edx, 0A3h
0x18000676a  call    WPP_SF_
0x18000676f  mov     rcx, [rbp+770h+var_30]
0x180006776  xor     rcx, rsp; StackCookie
0x180006779  call    __security_check_cookie
0x18000677e  add     rsp, 858h
0x180006785  pop     r15
0x180006787  pop     rdi
0x180006788  pop     rbx
0x180006789  pop     rbp
0x18000678a  retn
```
