# CommonUtil::UtilRegGetValueInternal

- ea: `0x1800291b8`
- end: `0x1800292b4`
- name: `CommonUtil::UtilRegGetValueInternal`
- size: `252`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18003f254`

## callees

- `0x18001f97c`
- `0x1800291b8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180029206`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180029206`

## string_xrefs

- `0x1800291ff`: `InstallLocation`
- `0x180029271`: `InstallLocation`

## pseudocode

```c
__int64 __fastcall CommonUtil::UtilRegGetValueInternal(HKEY a1, __int64 a2, DWORD *a3, _DWORD *a4, LPBYTE lpData)
{
  __int64 result; // rax
  LPBYTE v7; // rsi
  LSTATUS Value; // eax
  signed int v9; // ebx
  __int64 cbData; // [rsp+48h] [rbp+10h] BYREF

  cbData = a2;
  LODWORD(cbData) = *a4;
  if ( (unsigned int)cbData != *(_QWORD *)a4 )
    return 2147942487LL;
  v7 = lpData;
  Value = RegQueryValueExW(a1, L"InstallLocation", 0, a3, lpData, (LPDWORD)&cbData);
  v9 = Value;
  if ( Value > 0 )
    v9 = (unsigned __int16)Value | 0x80070000;
  if ( v9 < 0 )
  {
    result = 2147942402LL;
    if ( v9 != -2147024894 )
    {
      result = 2147942634LL;
      if ( v9 == -2147024662 )
      {
        if ( *(_QWORD *)a4 < (unsigned __int64)(unsigned int)cbData )
          *(_QWORD *)a4 = (unsigned int)cbData;
        else
          return 2147549183LL;
      }
      else
      {
        if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            21,
            (unsigned int)WPP_206b02167db13a360b8041c753392543_Traceguids,
            (unsigned int)L"InstallLocation",
            v9);
        }
        return (unsigned int)v9;
      }
    }
  }
  else if ( v7 && (unsigned __int64)(unsigned int)cbData > *(_QWORD *)a4 )
  {
    *(_QWORD *)a4 = (unsigned int)cbData;
    return 2147942634LL;
  }
  else
  {
    *(_QWORD *)a4 = (unsigned int)cbData;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800291b8  mov     [rsp+arg_0], rbx
0x1800291bd  mov     [rsp+arg_10], rsi
0x1800291c2  mov     [rsp+cbData], rdx
0x1800291c7  push    rdi
0x1800291c8  sub     rsp, 30h
0x1800291cc  mov     eax, [r9]
0x1800291cf  mov     rdi, r9
0x1800291d2  mov     dword ptr [rsp+38h+cbData], eax
0x1800291d6  cmp     rax, [r9]
0x1800291d9  jz      short loc_1800291E5
0x1800291db  mov     eax, 80070057h
0x1800291e0  jmp     loc_1800292A4
0x1800291e5  mov     rsi, [rsp+38h+arg_20]
0x1800291ea  lea     rax, [rsp+38h+cbData]
0x1800291ef  mov     r9, r8; lpType
0x1800291f2  mov     [rsp+38h+lpcbData], rax; lpcbData
0x1800291f7  xor     r8d, r8d; lpReserved
0x1800291fa  mov     [rsp+38h+lpData], rsi; lpData
0x1800291ff  lea     rdx, aInstalllocatio; "InstallLocation"
0x180029206  call    cs:__imp_RegQueryValueExW
0x18002920c  mov     ebx, eax
0x18002920e  test    eax, eax
0x180029210  jle     short loc_18002921B
0x180029212  movzx   ebx, ax
0x180029215  or      ebx, 80070000h
0x18002921b  test    ebx, ebx
0x18002921d  js      short loc_180029242
0x18002921f  test    rsi, rsi
0x180029222  jz      short loc_180029237
0x180029224  mov     eax, dword ptr [rsp+38h+cbData]
0x180029228  cmp     rax, [rdi]
0x18002922b  jbe     short loc_180029237
0x18002922d  mov     [rdi], rax
0x180029230  mov     eax, 800700EAh
0x180029235  jmp     short loc_1800292A4
0x180029237  mov     eax, dword ptr [rsp+38h+cbData]
0x18002923b  mov     [rdi], rax
0x18002923e  xor     eax, eax
0x180029240  jmp     short loc_1800292A4
0x180029242  mov     eax, 80070002h
0x180029247  cmp     ebx, eax
0x180029249  jz      short loc_1800292A4
0x18002924b  mov     eax, 800700EAh
0x180029250  cmp     ebx, eax
0x180029252  jz      short loc_180029291
0x180029254  mov     rcx, cs:WPP_GLOBAL_Control
0x18002925b  lea     rax, WPP_GLOBAL_Control
0x180029262  cmp     rcx, rax
0x180029265  jz      short loc_18002928D
0x180029267  test    byte ptr [rcx+1Ch], 1
0x18002926b  jz      short loc_18002928D
0x18002926d  mov     rcx, [rcx+10h]
0x180029271  lea     r9, aInstalllocatio; "InstallLocation"
0x180029278  mov     edx, 15h
0x18002927d  mov     dword ptr [rsp+38h+lpData], ebx
0x180029281  lea     r8, WPP_206b02167db13a360b8041c753392543_Traceguids
0x180029288  call    WPP_SF_Sd
0x18002928d  mov     eax, ebx
0x18002928f  jmp     short loc_1800292A4
0x180029291  mov     ecx, dword ptr [rsp+38h+cbData]
0x180029295  cmp     [rdi], rcx
0x180029298  jb      short loc_1800292A1
0x18002929a  mov     eax, 8000FFFFh
0x18002929f  jmp     short loc_1800292A4
0x1800292a1  mov     [rdi], rcx
0x1800292a4  mov     rbx, [rsp+38h+arg_0]
0x1800292a9  mov     rsi, [rsp+38h+arg_10]
0x1800292ae  add     rsp, 30h
0x1800292b2  pop     rdi
0x1800292b3  retn
```
