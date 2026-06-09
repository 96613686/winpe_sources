# CClientUtils::ReadPolicyString(UT_REGREAD_LOCATION,ushort const *,ushort const *,ushort *,ulong)

- ea: `0x180008810`
- end: `0x180008981`
- name: `?ReadPolicyString@CClientUtils@@UEAAJW4UT_REGREAD_LOCATION@@PEBG1PEAGK@Z`
- size: `369`
- prototype: `int __high(enum UT_REGREAD_LOCATION, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 *, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x180003970`
- `0x1800053ec`
- `0x180008810`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x180008907`
- `ADVAPI32!RegQueryValueExW` at `0x180008907`
- `ADVAPI32!RegOpenKeyExW` at `0x18000885b`
- `ADVAPI32!RegOpenKeyExW` at `0x18000885b`
- `ADVAPI32!RegCloseKey` at `0x180008914`
- `ADVAPI32!RegCloseKey` at `0x180008914`

## pseudocode

```c
__int64 __fastcall CClientUtils::ReadPolicyString(
        __int64 a1,
        int a2,
        const WCHAR *a3,
        const WCHAR *a4,
        LPBYTE lpcbData,
        int a6)
{
  BYTE *lpData; // rdi
  LSTATUS v8; // eax
  LSTATUS v9; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  __int64 v11; // rdx
  HKEY hKey; // [rsp+30h] [rbp-18h] BYREF
  DWORD Type; // [rsp+58h] [rbp+10h] BYREF

  lpData = lpcbData;
  hKey = 0;
  *(_WORD *)lpcbData = 0;
  v8 = RegOpenKeyExW((HKEY)((a2 != 0) - 0x7FFFFFFFLL), a3, 0, 0x20019u, &hKey);
  v9 = v8;
  if ( v8 == 2 || v8 == 5 )
    return 1;
  if ( v8 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v11 = 47;
LABEL_8:
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v11,
        &WPP_72aaf7d92de938e37e89151f64d0d640_Traceguids,
        CurrentThreadActivityIdPrefix,
        v9);
      goto LABEL_9;
    }
    goto LABEL_9;
  }
  LODWORD(lpcbData) = 2 * a6;
  Type = 0;
  v9 = RegQueryValueExW(hKey, a4, 0, &Type, lpData, (LPDWORD)&lpcbData);
  RegCloseKey(hKey);
  if ( v9 == 2 || v9 == 5 )
    return 1;
  if ( !v9 )
    return Type != 1;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v11 = 48;
    goto LABEL_8;
  }
LABEL_9:
  if ( v9 > 0 )
    return (unsigned __int16)v9 | 0x80070000;
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180008810  mov     r11, rsp
0x180008813  mov     [r11+8], rbx
0x180008817  mov     [r11+18h], rsi
0x18000881b  push    rdi
0x18000881c  sub     rsp, 40h
0x180008820  mov     rdi, [rsp+48h+arg_20]
0x180008825  xor     eax, eax
0x180008827  neg     edx
0x180008829  mov     qword ptr [r11-18h], 0
0x180008831  mov     r10, r8
0x180008834  mov     rsi, r9
0x180008837  sbb     rcx, rcx
0x18000883a  mov     r9d, 20019h; samDesired
0x180008840  neg     rcx
0x180008843  mov     [rdi], ax
0x180008846  lea     rax, [r11-18h]
0x18000884a  add     rcx, 0FFFFFFFF80000001h; hKey
0x180008851  xor     r8d, r8d; ulOptions
0x180008854  mov     [r11-28h], rax
0x180008858  mov     rdx, r10; lpSubKey
0x18000885b  call    cs:__imp_RegOpenKeyExW
0x180008861  mov     ebx, eax
0x180008863  cmp     eax, 2
0x180008866  jz      loc_18000896A
0x18000886c  cmp     eax, 5
0x18000886f  jz      loc_18000896A
0x180008875  test    eax, eax
0x180008877  jz      short loc_1800088D6
0x180008879  mov     rax, cs:WPP_GLOBAL_Control
0x180008880  lea     rcx, WPP_GLOBAL_Control
0x180008887  cmp     rax, rcx
0x18000888a  jz      short loc_1800088C0
0x18000888c  test    byte ptr [rax+1Ch], 8
0x180008890  jz      short loc_1800088C0
0x180008892  cmp     byte ptr [rax+19h], 2
0x180008896  jb      short loc_1800088C0
0x180008898  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18000889d  mov     edx, 2Fh ; '/'
0x1800088a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800088a9  lea     r8, WPP_72aaf7d92de938e37e89151f64d0d640_Traceguids
0x1800088b0  mov     r9d, eax
0x1800088b3  mov     dword ptr [rsp+48h+lpData], ebx
0x1800088b7  mov     rcx, [rcx+10h]
0x1800088bb  call    WPP_SF_Dd
0x1800088c0  test    ebx, ebx
0x1800088c2  jle     loc_18000896F
0x1800088c8  movzx   ebx, bx
0x1800088cb  or      ebx, 80070000h
0x1800088d1  jmp     loc_18000896F
0x1800088d6  mov     eax, [rsp+48h+arg_28]
0x1800088da  lea     r9, [rsp+48h+Type]; lpType
0x1800088df  mov     rcx, [rsp+48h+hKey]; hKey
0x1800088e4  add     eax, eax
0x1800088e6  mov     dword ptr [rsp+48h+arg_20], eax
0x1800088ea  xor     r8d, r8d; lpReserved
0x1800088ed  lea     rax, [rsp+48h+arg_20]
0x1800088f2  mov     [rsp+48h+Type], 0
0x1800088fa  mov     [rsp+48h+lpcbData], rax; lpcbData
0x1800088ff  mov     rdx, rsi; lpValueName
0x180008902  mov     [rsp+48h+lpData], rdi; lpData
0x180008907  call    cs:__imp_RegQueryValueExW
0x18000890d  mov     rcx, [rsp+48h+hKey]; hKey
0x180008912  mov     ebx, eax
0x180008914  call    cs:__imp_RegCloseKey
0x18000891a  cmp     ebx, 2
0x18000891d  jz      short loc_18000896A
0x18000891f  cmp     ebx, 5
0x180008922  jz      short loc_18000896A
0x180008924  test    ebx, ebx
0x180008926  jz      short loc_18000895E
0x180008928  mov     rax, cs:WPP_GLOBAL_Control
0x18000892f  lea     rcx, WPP_GLOBAL_Control
0x180008936  cmp     rax, rcx
0x180008939  jz      short loc_1800088C0
0x18000893b  test    byte ptr [rax+1Ch], 8
0x18000893f  jz      loc_1800088C0
0x180008945  cmp     byte ptr [rax+19h], 2
0x180008949  jb      loc_1800088C0
0x18000894f  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180008954  mov     edx, 30h ; '0'
0x180008959  jmp     loc_1800088A2
0x18000895e  xor     ebx, ebx
0x180008960  cmp     [rsp+48h+Type], 1
0x180008965  setnz   bl
0x180008968  jmp     short loc_18000896F
0x18000896a  mov     ebx, 1
0x18000896f  mov     rsi, [rsp+48h+arg_10]
0x180008974  mov     eax, ebx
0x180008976  mov     rbx, [rsp+48h+arg_0]
0x18000897b  add     rsp, 40h
0x18000897f  pop     rdi
0x180008980  retn
```
