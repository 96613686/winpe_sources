# CClientUtils::ReadPolicyDWORD(UT_REGREAD_LOCATION,ushort const *,ushort const *,ulong *)

- ea: `0x180008690`
- end: `0x180008803`
- name: `?ReadPolicyDWORD@CClientUtils@@UEAAJW4UT_REGREAD_LOCATION@@PEBG1PEAK@Z`
- size: `371`
- prototype: `int __high(enum UT_REGREAD_LOCATION, const unsigned __int16 *, const unsigned __int16 *, unsigned int *)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x180003970`
- `0x1800053ec`
- `0x180008690`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x18000877c`
- `ADVAPI32!RegQueryValueExW` at `0x18000877c`
- `ADVAPI32!RegOpenKeyExW` at `0x1800086cd`
- `ADVAPI32!RegOpenKeyExW` at `0x1800086cd`
- `ADVAPI32!RegCloseKey` at `0x180008789`
- `ADVAPI32!RegCloseKey` at `0x180008789`

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
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
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
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
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
0x180008690  mov     r11, rsp
0x180008693  mov     [r11+8], rbx
0x180008697  push    rdi
0x180008698  sub     rsp, 40h
0x18000869c  neg     edx
0x18000869e  mov     qword ptr [r11-10h], 0
0x1800086a6  lea     rdx, [r11-10h]
0x1800086aa  mov     rax, r8
0x1800086ad  sbb     rcx, rcx
0x1800086b0  mov     [r11-28h], rdx
0x1800086b4  neg     rcx
0x1800086b7  mov     rdi, r9
0x1800086ba  add     rcx, 0FFFFFFFF80000001h; hKey
0x1800086c1  mov     r9d, 20019h; samDesired
0x1800086c7  xor     r8d, r8d; ulOptions
0x1800086ca  mov     rdx, rax; lpSubKey
0x1800086cd  call    cs:__imp_RegOpenKeyExW
0x1800086d3  mov     ebx, eax
0x1800086d5  cmp     eax, 2
0x1800086d8  jz      loc_1800087F1
0x1800086de  cmp     eax, 5
0x1800086e1  jz      loc_1800087F1
0x1800086e7  test    eax, eax
0x1800086e9  jz      short loc_180008748
0x1800086eb  mov     rax, cs:WPP_GLOBAL_Control
0x1800086f2  lea     rcx, WPP_GLOBAL_Control
0x1800086f9  cmp     rax, rcx
0x1800086fc  jz      short loc_180008732
0x1800086fe  test    byte ptr [rax+1Ch], 8
0x180008702  jz      short loc_180008732
0x180008704  cmp     byte ptr [rax+19h], 2
0x180008708  jb      short loc_180008732
0x18000870a  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18000870f  mov     edx, 2Dh ; '-'
0x180008714  mov     rcx, cs:WPP_GLOBAL_Control
0x18000871b  lea     r8, WPP_72aaf7d92de938e37e89151f64d0d640_Traceguids
0x180008722  mov     r9d, eax
0x180008725  mov     dword ptr [rsp+48h+lpData], ebx
0x180008729  mov     rcx, [rcx+10h]
0x18000872d  call    WPP_SF_Dd
0x180008732  test    ebx, ebx
0x180008734  jle     loc_1800087F6
0x18000873a  movzx   ebx, bx
0x18000873d  or      ebx, 80070000h
0x180008743  jmp     loc_1800087F6
0x180008748  mov     rcx, [rsp+48h+hKey]; hKey
0x18000874d  lea     rax, [rsp+48h+cbData]
0x180008752  mov     [rsp+48h+lpcbData], rax; lpcbData
0x180008757  lea     r9, [rsp+48h+Type]; lpType
0x18000875c  mov     rax, [rsp+48h+arg_20]
0x180008761  xor     r8d, r8d; lpReserved
0x180008764  mov     rdx, rdi; lpValueName
0x180008767  mov     [rsp+48h+lpData], rax; lpData
0x18000876c  mov     [rsp+48h+Type], 0
0x180008774  mov     [rsp+48h+cbData], 4
0x18000877c  call    cs:__imp_RegQueryValueExW
0x180008782  mov     rcx, [rsp+48h+hKey]; hKey
0x180008787  mov     ebx, eax
0x180008789  call    cs:__imp_RegCloseKey
0x18000878f  cmp     ebx, 2
0x180008792  jz      short loc_1800087F1
0x180008794  cmp     ebx, 5
0x180008797  jz      short loc_1800087F1
0x180008799  cmp     ebx, 0EAh
0x18000879f  jz      short loc_1800087F1
0x1800087a1  test    ebx, ebx
0x1800087a3  jz      short loc_1800087DF
0x1800087a5  mov     rax, cs:WPP_GLOBAL_Control
0x1800087ac  lea     rcx, WPP_GLOBAL_Control
0x1800087b3  cmp     rax, rcx
0x1800087b6  jz      loc_180008732
0x1800087bc  test    byte ptr [rax+1Ch], 8
0x1800087c0  jz      loc_180008732
0x1800087c6  cmp     byte ptr [rax+19h], 2
0x1800087ca  jb      loc_180008732
0x1800087d0  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800087d5  mov     edx, 2Eh ; '.'
0x1800087da  jmp     loc_180008714
0x1800087df  cmp     [rsp+48h+Type], 4
0x1800087e4  jnz     short loc_1800087F1
0x1800087e6  cmp     [rsp+48h+cbData], 4
0x1800087eb  jnz     short loc_1800087F1
0x1800087ed  xor     ebx, ebx
0x1800087ef  jmp     short loc_1800087F6
0x1800087f1  mov     ebx, 1
0x1800087f6  mov     eax, ebx
0x1800087f8  mov     rbx, [rsp+48h+arg_0]
0x1800087fd  add     rsp, 40h
0x180008801  pop     rdi
0x180008802  retn
```
