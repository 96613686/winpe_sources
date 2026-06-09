# CClientUtils::ReadPolicyDWORD(UT_REGREAD_LOCATION,ushort const *,ushort const *,ulong *)

- ea: `0x180082570`
- end: `0x1800826e3`
- name: `?ReadPolicyDWORD@CClientUtils@@UEAAJW4UT_REGREAD_LOCATION@@PEBG1PEAK@Z`
- size: `371`
- prototype: `int __high(enum UT_REGREAD_LOCATION, const unsigned __int16 *, const unsigned __int16 *, unsigned int *)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x18000b1d8`
- `0x18000ec94`
- `0x180082570`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x18008265c`
- `ADVAPI32!RegQueryValueExW` at `0x18008265c`
- `ADVAPI32!RegCloseKey` at `0x180082669`
- `ADVAPI32!RegCloseKey` at `0x180082669`
- `ADVAPI32!RegOpenKeyExW` at `0x1800825ad`
- `ADVAPI32!RegOpenKeyExW` at `0x1800825ad`

## pseudocode

```c
__int64 __fastcall CClientUtils::ReadPolicyDWORD(__int64 a1, int a2, const WCHAR *a3, const WCHAR *a4, LPBYTE lpData)
{
  LSTATUS v6; // eax
  LSTATUS v7; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  __int64 v9; // rdx
  DWORD cbData; // [rsp+30h] [rbp-18h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-10h] BYREF
  DWORD Type; // [rsp+58h] [rbp+10h] BYREF

  hKey = 0;
  v6 = RegOpenKeyExW((HKEY)((a2 != 0) - 0x7FFFFFFFLL), a3, 0, 0x20019u, &hKey);
  v7 = v6;
  if ( v6 == 2 || v6 == 5 )
    return 1;
  if ( v6 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v9 = 45;
LABEL_8:
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v9,
        &WPP_72aaf7d92de938e37e89151f64d0d640_Traceguids,
        CurrentThreadActivityIdPrefix,
        v7);
      goto LABEL_9;
    }
    goto LABEL_9;
  }
  Type = 0;
  cbData = 4;
  v7 = RegQueryValueExW(hKey, a4, 0, &Type, lpData, &cbData);
  RegCloseKey(hKey);
  if ( v7 == 2 || v7 == 5 || v7 == 234 )
    return 1;
  if ( !v7 )
    return Type != 4 || cbData != 4;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v9 = 46;
    goto LABEL_8;
  }
LABEL_9:
  if ( v7 > 0 )
    return (unsigned __int16)v7 | 0x80070000;
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180082570  mov     r11, rsp
0x180082573  mov     [r11+8], rbx
0x180082577  push    rdi
0x180082578  sub     rsp, 40h
0x18008257c  neg     edx
0x18008257e  mov     qword ptr [r11-10h], 0
0x180082586  lea     rdx, [r11-10h]
0x18008258a  mov     rax, r8
0x18008258d  sbb     rcx, rcx
0x180082590  mov     [r11-28h], rdx
0x180082594  neg     rcx
0x180082597  mov     rdi, r9
0x18008259a  add     rcx, 0FFFFFFFF80000001h; hKey
0x1800825a1  mov     r9d, 20019h; samDesired
0x1800825a7  xor     r8d, r8d; ulOptions
0x1800825aa  mov     rdx, rax; lpSubKey
0x1800825ad  call    cs:__imp_RegOpenKeyExW
0x1800825b3  mov     ebx, eax
0x1800825b5  cmp     eax, 2
0x1800825b8  jz      loc_1800826D1
0x1800825be  cmp     eax, 5
0x1800825c1  jz      loc_1800826D1
0x1800825c7  test    eax, eax
0x1800825c9  jz      short loc_180082628
0x1800825cb  mov     rax, cs:WPP_GLOBAL_Control
0x1800825d2  lea     rcx, WPP_GLOBAL_Control
0x1800825d9  cmp     rax, rcx
0x1800825dc  jz      short loc_180082612
0x1800825de  test    byte ptr [rax+1Ch], 8
0x1800825e2  jz      short loc_180082612
0x1800825e4  cmp     byte ptr [rax+19h], 2
0x1800825e8  jb      short loc_180082612
0x1800825ea  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800825ef  mov     edx, 2Dh ; '-'
0x1800825f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800825fb  lea     r8, WPP_72aaf7d92de938e37e89151f64d0d640_Traceguids
0x180082602  mov     r9d, eax
0x180082605  mov     dword ptr [rsp+48h+lpData], ebx
0x180082609  mov     rcx, [rcx+10h]
0x18008260d  call    WPP_SF_Dd
0x180082612  test    ebx, ebx
0x180082614  jle     loc_1800826D6
0x18008261a  movzx   ebx, bx
0x18008261d  or      ebx, 80070000h
0x180082623  jmp     loc_1800826D6
0x180082628  mov     rcx, [rsp+48h+hKey]; hKey
0x18008262d  lea     rax, [rsp+48h+cbData]
0x180082632  mov     [rsp+48h+lpcbData], rax; lpcbData
0x180082637  lea     r9, [rsp+48h+Type]; lpType
0x18008263c  mov     rax, [rsp+48h+arg_20]
0x180082641  xor     r8d, r8d; lpReserved
0x180082644  mov     rdx, rdi; lpValueName
0x180082647  mov     [rsp+48h+lpData], rax; lpData
0x18008264c  mov     [rsp+48h+Type], 0
0x180082654  mov     [rsp+48h+cbData], 4
0x18008265c  call    cs:__imp_RegQueryValueExW
0x180082662  mov     rcx, [rsp+48h+hKey]; hKey
0x180082667  mov     ebx, eax
0x180082669  call    cs:__imp_RegCloseKey
0x18008266f  cmp     ebx, 2
0x180082672  jz      short loc_1800826D1
0x180082674  cmp     ebx, 5
0x180082677  jz      short loc_1800826D1
0x180082679  cmp     ebx, 0EAh
0x18008267f  jz      short loc_1800826D1
0x180082681  test    ebx, ebx
0x180082683  jz      short loc_1800826BF
0x180082685  mov     rax, cs:WPP_GLOBAL_Control
0x18008268c  lea     rcx, WPP_GLOBAL_Control
0x180082693  cmp     rax, rcx
0x180082696  jz      loc_180082612
0x18008269c  test    byte ptr [rax+1Ch], 8
0x1800826a0  jz      loc_180082612
0x1800826a6  cmp     byte ptr [rax+19h], 2
0x1800826aa  jb      loc_180082612
0x1800826b0  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800826b5  mov     edx, 2Eh ; '.'
0x1800826ba  jmp     loc_1800825F4
0x1800826bf  cmp     [rsp+48h+Type], 4
0x1800826c4  jnz     short loc_1800826D1
0x1800826c6  cmp     [rsp+48h+cbData], 4
0x1800826cb  jnz     short loc_1800826D1
0x1800826cd  xor     ebx, ebx
0x1800826cf  jmp     short loc_1800826D6
0x1800826d1  mov     ebx, 1
0x1800826d6  mov     eax, ebx
0x1800826d8  mov     rbx, [rsp+48h+arg_0]
0x1800826dd  add     rsp, 40h
0x1800826e1  pop     rdi
0x1800826e2  retn
```
