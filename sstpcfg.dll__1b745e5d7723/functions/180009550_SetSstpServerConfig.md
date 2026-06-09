# SetSstpServerConfig

- ea: `0x180009550`
- end: `0x180009715`
- name: `SetSstpServerConfig`
- size: `453`
- prototype: `__int64 __fastcall(HKEY hKey)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180007450`

## callees

- `0x180009550`
- `0x18000a044`
- `0x18000acbc`
- `0x18000ae4e`
- `0x18000ae80`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800095c8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180009675`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800095c8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180009675`

## pseudocode

```c
unsigned int __fastcall SetSstpServerConfig(HKEY hKey, unsigned __int8 *a2)
{
  unsigned int v4; // eax
  __int64 v5; // r8
  unsigned int v6; // ebx
  unsigned int result; // eax
  __int64 v8; // r8
  unsigned int v9; // ebx
  BYTE Data[16]; // [rsp+30h] [rbp-D0h] BYREF
  int v11; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v12[2044]; // [rsp+44h] [rbp-BCh] BYREF

  v11 = 0;
  memset_0(v12, 0, sizeof(v12));
  *(_DWORD *)Data = *a2;
  v4 = RegSetValueExW(hKey, L"UseHttps", 0, 4u, Data, 4u);
  v6 = v4;
  if ( v4 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 164, v5, v4);
    }
    if ( (_QWORD)xmmword_1800146E0 )
    {
      LOWORD(v11) = 0;
      FormatRRASErrorString(&v11, L"Error while writing UseHttps flag: %d", v6);
      ((void (__fastcall *)(__int64, _QWORD, int *))gSstpCfgTemplateFunc)(gSstpCfgEtwContext, xmmword_1800146E0, &v11);
    }
  }
  *(_DWORD *)Data = *((unsigned __int16 *)a2 + 1);
  result = RegSetValueExW(hKey, L"ListenerPort", 0, 4u, Data, 4u);
  v9 = result;
  if ( result )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      result = WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 165, v8, result);
    }
    if ( (_QWORD)xmmword_1800146E0 )
    {
      LOWORD(v11) = 0;
      FormatRRASErrorString(&v11, L"Error while writing Listener Port value: %d", v9);
      return ((__int64 (__fastcall *)(__int64, _QWORD, int *))gSstpCfgTemplateFunc)(
               gSstpCfgEtwContext,
               xmmword_1800146E0,
               &v11);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180009550  mov     [rsp-8+arg_10], rbx
0x180009555  mov     [rsp-8+arg_18], rsi
0x18000955a  push    rbp
0x18000955b  push    rdi
0x18000955c  push    r14
0x18000955e  lea     rbp, [rsp-750h]
0x180009566  sub     rsp, 850h
0x18000956d  mov     rax, cs:__security_cookie
0x180009574  xor     rax, rsp
0x180009577  mov     [rbp+760h+var_20], rax
0x18000957e  mov     rsi, rdx
0x180009581  mov     rdi, rcx
0x180009584  xor     eax, eax
0x180009586  lea     rcx, [rsp+860h+var_81C]; void *
0x18000958b  xor     edx, edx; Val
0x18000958d  mov     [rsp+860h+var_820], eax
0x180009591  mov     r8d, 7FCh; Size
0x180009597  call    memset_0
0x18000959c  movzx   eax, byte ptr [rsi]
0x18000959f  lea     rdx, aUsehttps; "UseHttps"
0x1800095a6  mov     dword ptr [rsp+860h+Data], eax
0x1800095aa  mov     r9d, 4; dwType
0x1800095b0  lea     rax, [rsp+860h+Data]
0x1800095b5  mov     [rsp+860h+cbData], 4; cbData
0x1800095bd  xor     r8d, r8d; Reserved
0x1800095c0  mov     [rsp+860h+lpData], rax; lpData
0x1800095c5  mov     rcx, rdi; hKey
0x1800095c8  call    cs:__imp_RegSetValueExW
0x1800095ce  lea     r14, WPP_GLOBAL_Control
0x1800095d5  mov     ebx, eax
0x1800095d7  test    eax, eax
0x1800095d9  jz      short loc_180009648
0x1800095db  mov     rcx, cs:WPP_GLOBAL_Control
0x1800095e2  cmp     rcx, r14
0x1800095e5  jz      short loc_180009604
0x1800095e7  test    byte ptr [rcx+1Ch], 40h
0x1800095eb  jz      short loc_180009604
0x1800095ed  cmp     byte ptr [rcx+19h], 1
0x1800095f1  jb      short loc_180009604
0x1800095f3  mov     rcx, [rcx+10h]
0x1800095f7  mov     edx, 0A4h
0x1800095fc  mov     r9d, eax
0x1800095ff  call    WPP_SF_d
0x180009604  cmp     qword ptr cs:xmmword_1800146E0, 0
0x18000960c  jz      short loc_180009648
0x18000960e  xor     eax, eax
0x180009610  lea     rdx, aErrorWhileWrit; "Error while writing UseHttps flag: %d"
0x180009617  mov     r8d, ebx
0x18000961a  mov     word ptr [rsp+860h+var_820], ax
0x18000961f  lea     rcx, [rsp+860h+var_820]
0x180009624  call    FormatRRASErrorString
0x180009629  mov     rdx, qword ptr cs:xmmword_1800146E0
0x180009630  lea     r8, [rsp+860h+var_820]
0x180009635  mov     rcx, cs:gSstpCfgEtwContext
0x18000963c  mov     rax, cs:gSstpCfgTemplateFunc
0x180009643  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009648  movzx   eax, word ptr [rsi+2]
0x18000964c  lea     rdx, ValueName; "ListenerPort"
0x180009653  mov     dword ptr [rsp+860h+Data], eax
0x180009657  mov     r9d, 4; dwType
0x18000965d  lea     rax, [rsp+860h+Data]
0x180009662  mov     [rsp+860h+cbData], 4; cbData
0x18000966a  xor     r8d, r8d; Reserved
0x18000966d  mov     [rsp+860h+lpData], rax; lpData
0x180009672  mov     rcx, rdi; hKey
0x180009675  call    cs:__imp_RegSetValueExW
0x18000967b  mov     ebx, eax
0x18000967d  test    eax, eax
0x18000967f  jz      short loc_1800096EE
0x180009681  mov     rcx, cs:WPP_GLOBAL_Control
0x180009688  cmp     rcx, r14
0x18000968b  jz      short loc_1800096AA
0x18000968d  test    byte ptr [rcx+1Ch], 40h
0x180009691  jz      short loc_1800096AA
0x180009693  cmp     byte ptr [rcx+19h], 1
0x180009697  jb      short loc_1800096AA
0x180009699  mov     rcx, [rcx+10h]
0x18000969d  mov     edx, 0A5h
0x1800096a2  mov     r9d, eax
0x1800096a5  call    WPP_SF_d
0x1800096aa  cmp     qword ptr cs:xmmword_1800146E0, 0
0x1800096b2  jz      short loc_1800096EE
0x1800096b4  xor     eax, eax
0x1800096b6  lea     rdx, aErrorWhileWrit_0; "Error while writing Listener Port value"...
0x1800096bd  mov     r8d, ebx
0x1800096c0  mov     word ptr [rsp+860h+var_820], ax
0x1800096c5  lea     rcx, [rsp+860h+var_820]
0x1800096ca  call    FormatRRASErrorString
0x1800096cf  mov     rdx, qword ptr cs:xmmword_1800146E0
0x1800096d6  lea     r8, [rsp+860h+var_820]
0x1800096db  mov     rcx, cs:gSstpCfgEtwContext
0x1800096e2  mov     rax, cs:gSstpCfgTemplateFunc
0x1800096e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800096ee  mov     rcx, [rbp+760h+var_20]
0x1800096f5  xor     rcx, rsp; StackCookie
0x1800096f8  call    __security_check_cookie
0x1800096fd  lea     r11, [rsp+860h+var_10]
0x180009705  mov     rbx, [r11+30h]
0x180009709  mov     rsi, [r11+38h]
0x18000970d  mov     rsp, r11
0x180009710  pop     r14
0x180009712  pop     rdi
0x180009713  pop     rbp
0x180009714  retn
```
