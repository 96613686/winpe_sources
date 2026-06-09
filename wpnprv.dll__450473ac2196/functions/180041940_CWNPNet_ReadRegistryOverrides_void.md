# CWNPNet::ReadRegistryOverrides(void)

- ea: `0x180041940`
- end: `0x180041aa8`
- name: `?ReadRegistryOverrides@CWNPNet@@AEAAXXZ`
- size: `360`
- prototype: `void __fastcall(CWNPNet *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800332b4`

## callees

- `0x18000fe2c`
- `0x18000fe54`
- `0x18002f808`
- `0x180041940`
- `0x1800852d4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180041a63`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180041a63`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800419b3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800419b3`

## pseudocode

```c
void __fastcall CWNPNet::ReadRegistryOverrides(CWNPNet *this)
{
  int v2; // eax
  __int64 v3; // r9
  PVOID *v4; // rcx
  unsigned int v5; // [rsp+48h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+50h] [rbp+18h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, &WPP_4e47059d20e03c0ffeb37878b8bdc70f_Traceguids);
  }
  hKey = 0;
  v5 = 0;
  v2 = RegOpenKeyExA(
         HKEY_LOCAL_MACHINE,
         "Software\\Microsoft\\Windows\\CurrentVersion\\PushNotifications",
         0,
         1u,
         &hKey);
  if ( !v2 )
  {
    if ( (int)WpnRegLoadDWord(hKey, L"EnableDormancyOnReceive", &v5) < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, &WPP_4e47059d20e03c0ffeb37878b8bdc70f_Traceguids);
      }
    }
    else
    {
      *((_BYTE *)this + 1598) = v5 != 0;
    }
    RegCloseKey(hKey);
    goto LABEL_19;
  }
  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    if ( v2 > 0 )
      v2 = (unsigned __int16)v2 | 0x80070000;
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      41,
      &WPP_4e47059d20e03c0ffeb37878b8bdc70f_Traceguids,
      (unsigned int)v2);
LABEL_19:
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 4) != 0 && *((_BYTE *)v4 + 25) >= 6u )
  {
    LOBYTE(v3) = *((_BYTE *)this + 1598);
    WPP_SF_c(v4[2], 43, &WPP_4e47059d20e03c0ffeb37878b8bdc70f_Traceguids, v3);
  }
}

```

## disassembly

```asm
0x180041940  mov     [rsp+arg_0], rbx
0x180041945  push    rbp
0x180041946  sub     rsp, 30h
0x18004194a  mov     rbx, rcx
0x18004194d  mov     rcx, cs:WPP_GLOBAL_Control
0x180041954  lea     rbp, WPP_GLOBAL_Control
0x18004195b  cmp     rcx, rbp
0x18004195e  jz      short loc_180041981
0x180041960  test    byte ptr [rcx+1Ch], 4
0x180041964  jz      short loc_180041981
0x180041966  cmp     byte ptr [rcx+19h], 6
0x18004196a  jb      short loc_180041981
0x18004196c  mov     rcx, [rcx+10h]
0x180041970  lea     r8, WPP_4e47059d20e03c0ffeb37878b8bdc70f_Traceguids
0x180041977  mov     edx, 28h ; '('
0x18004197c  call    WPP_SF_
0x180041981  lea     rax, [rsp+38h+hKey]
0x180041986  mov     [rsp+38h+hKey], 0
0x18004198f  mov     r9d, 1; samDesired
0x180041995  mov     [rsp+38h+phkResult], rax; phkResult
0x18004199a  xor     r8d, r8d; ulOptions
0x18004199d  mov     [rsp+38h+arg_8], 0
0x1800419a5  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800419ac  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800419b3  call    cs:__imp_RegOpenKeyExA
0x1800419b9  test    eax, eax
0x1800419bb  jz      short loc_180041A07
0x1800419bd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800419c4  cmp     rcx, rbp
0x1800419c7  jz      loc_180041A9D
0x1800419cd  test    byte ptr [rcx+1Ch], 4
0x1800419d1  jz      loc_180041A70
0x1800419d7  cmp     byte ptr [rcx+19h], 2
0x1800419db  jb      loc_180041A70
0x1800419e1  test    eax, eax
0x1800419e3  jle     short loc_1800419ED
0x1800419e5  movzx   eax, ax
0x1800419e8  or      eax, 80070000h
0x1800419ed  mov     rcx, [rcx+10h]
0x1800419f1  lea     r8, WPP_4e47059d20e03c0ffeb37878b8bdc70f_Traceguids
0x1800419f8  mov     edx, 29h ; ')'
0x1800419fd  mov     r9d, eax
0x180041a00  call    WPP_SF_d
0x180041a05  jmp     short loc_180041A69
0x180041a07  mov     rcx, [rsp+38h+hKey]; hKey
0x180041a0c  lea     r8, [rsp+38h+arg_8]; unsigned int *
0x180041a11  lea     rdx, ?g_cszEnableDormancyOnReceive@@3QBGB; "EnableDormancyOnReceive"
0x180041a18  call    ?WpnRegLoadDWord@@YAJPEAUHKEY__@@PEBGPEAK@Z; WpnRegLoadDWord(HKEY__ *,ushort const *,ulong *)
0x180041a1d  test    eax, eax
0x180041a1f  js      short loc_180041A31
0x180041a21  cmp     [rsp+38h+arg_8], 0
0x180041a26  setnz   al
0x180041a29  mov     [rbx+63Eh], al
0x180041a2f  jmp     short loc_180041A5E
0x180041a31  mov     rcx, cs:WPP_GLOBAL_Control
0x180041a38  cmp     rcx, rbp
0x180041a3b  jz      short loc_180041A5E
0x180041a3d  test    byte ptr [rcx+1Ch], 4
0x180041a41  jz      short loc_180041A5E
0x180041a43  cmp     byte ptr [rcx+19h], 3
0x180041a47  jb      short loc_180041A5E
0x180041a49  mov     rcx, [rcx+10h]
0x180041a4d  lea     r8, WPP_4e47059d20e03c0ffeb37878b8bdc70f_Traceguids
0x180041a54  mov     edx, 2Ah ; '*'
0x180041a59  call    WPP_SF_
0x180041a5e  mov     rcx, [rsp+38h+hKey]; hKey
0x180041a63  call    cs:__imp_RegCloseKey
0x180041a69  mov     rcx, cs:WPP_GLOBAL_Control
0x180041a70  cmp     rcx, rbp
0x180041a73  jz      short loc_180041A9D
0x180041a75  test    byte ptr [rcx+1Ch], 4
0x180041a79  jz      short loc_180041A9D
0x180041a7b  cmp     byte ptr [rcx+19h], 6
0x180041a7f  jb      short loc_180041A9D
0x180041a81  mov     r9b, [rbx+63Eh]
0x180041a88  lea     r8, WPP_4e47059d20e03c0ffeb37878b8bdc70f_Traceguids
0x180041a8f  mov     rcx, [rcx+10h]
0x180041a93  mov     edx, 2Bh ; '+'
0x180041a98  call    WPP_SF_c
0x180041a9d  mov     rbx, [rsp+38h+arg_0]
0x180041aa2  add     rsp, 30h
0x180041aa6  pop     rbp
0x180041aa7  retn
```
