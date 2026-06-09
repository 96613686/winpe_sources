# HrForcefullyRemoveAllWizardComponents(void)

- ea: `0x18000dd3c`
- end: `0x18000decd`
- name: `?HrForcefullyRemoveAllWizardComponents@@YAJXZ`
- size: `401`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180006ad0`

## callees

- `0x180007820`
- `0x18000dd3c`
- `0x18000ebc0`
- `0x1800107bc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000dd73`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000dd73`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000de55`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000de55`

## string_xrefs

- `0x18000dd8f`: `Components`

## pseudocode

```c
__int64 HrForcefullyRemoveAllWizardComponents(void)
{
  LSTATUS v0; // eax
  unsigned int v1; // ebx
  int v2; // eax
  _QWORD *v3; // rcx
  __int64 v4; // rdx
  _QWORD *v5; // rcx
  __int64 v6; // rdx
  PVOID *v7; // rcx
  HKEY hKey; // [rsp+40h] [rbp+8h] BYREF

  hKey = 0;
  v0 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Windows\\CurrentVersion\\XWizards\\",
         0,
         0x2000Eu,
         &hKey);
  v1 = v0;
  if ( !v0 )
  {
    v2 = HrRegDeleteSubKeyTree(hKey, L"Components");
    v1 = v2;
    if ( v2 < 0 )
    {
      if ( v2 == -2147024894 )
      {
        v1 = 1;
        v3 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
          goto LABEL_20;
        v4 = 73;
LABEL_15:
        WPP_SF_(v3[2], v4, &WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids);
LABEL_20:
        RegCloseKey(hKey);
        goto LABEL_26;
      }
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
        goto LABEL_20;
      v6 = 74;
    }
    else
    {
      v2 = HrRegDeleteSubKeyTree(hKey, L"Factory");
      v1 = v2;
      if ( v2 == -2147024894 )
      {
        v1 = 1;
        v3 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
          goto LABEL_20;
        v4 = 71;
        goto LABEL_15;
      }
      if ( v2 >= 0 )
        goto LABEL_20;
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
        goto LABEL_20;
      v6 = 72;
    }
    WPP_SF_D(v5[2], v6, &WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids, (unsigned int)v2);
    goto LABEL_20;
  }
  if ( v0 > 0 )
    v1 = (unsigned __int16)v0 | 0x80070000;
  v7 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
    {
LABEL_27:
      if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 0x10) != 0 )
        WPP_SF_D(v7[2], 76, &WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids, v1);
      return v1;
    }
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 75, &WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids, v1);
LABEL_26:
    v7 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_27;
  }
  return v1;
}

```

## disassembly

```asm
0x18000dd3c  mov     r11, rsp
0x18000dd3f  mov     [r11+10h], rbx
0x18000dd43  mov     [r11+18h], rsi
0x18000dd47  push    rdi
0x18000dd48  sub     rsp, 30h
0x18000dd4c  lea     rax, [r11+8]
0x18000dd50  mov     qword ptr [r11+8], 0
0x18000dd58  mov     r9d, 2000Eh; samDesired
0x18000dd5e  mov     [r11-18h], rax
0x18000dd62  xor     r8d, r8d; ulOptions
0x18000dd65  lea     rdx, SubKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18000dd6c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000dd73  call    cs:__imp_RegOpenKeyExW
0x18000dd79  lea     rsi, WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids
0x18000dd80  mov     ebx, eax
0x18000dd82  test    eax, eax
0x18000dd84  jnz     loc_18000DE5D
0x18000dd8a  mov     rcx, [rsp+38h+hKey]; HKEY
0x18000dd8f  lea     rdx, aComponents_0; "Components"
0x18000dd96  call    ?HrRegDeleteSubKeyTree@@YAJPEAUHKEY__@@PEAG@Z; HrRegDeleteSubKeyTree(HKEY__ *,ushort *)
0x18000dd9b  lea     rdi, WPP_GLOBAL_Control
0x18000dda2  mov     ebx, eax
0x18000dda4  test    eax, eax
0x18000dda6  js      short loc_18000DDFB
0x18000dda8  mov     rcx, [rsp+38h+hKey]; HKEY
0x18000ddad  lea     rdx, aFactory_1; "Factory"
0x18000ddb4  call    ?HrRegDeleteSubKeyTree@@YAJPEAUHKEY__@@PEAG@Z; HrRegDeleteSubKeyTree(HKEY__ *,ushort *)
0x18000ddb9  mov     ebx, eax
0x18000ddbb  cmp     eax, 80070002h
0x18000ddc0  jnz     short loc_18000DDDE
0x18000ddc2  mov     ebx, 1
0x18000ddc7  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ddce  cmp     rcx, rdi
0x18000ddd1  jz      short loc_18000DE50
0x18000ddd3  test    byte ptr [rcx+1Ch], 10h
0x18000ddd7  jz      short loc_18000DE50
0x18000ddd9  lea     edx, [rbx+46h]
0x18000dddc  jmp     short loc_18000DE1C
0x18000ddde  test    eax, eax
0x18000dde0  jns     short loc_18000DE50
0x18000dde2  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dde9  cmp     rcx, rdi
0x18000ddec  jz      short loc_18000DE50
0x18000ddee  test    byte ptr [rcx+1Ch], 4
0x18000ddf2  jz      short loc_18000DE50
0x18000ddf4  mov     edx, 48h ; 'H'
0x18000ddf9  jmp     short loc_18000DE41
0x18000ddfb  cmp     eax, 80070002h
0x18000de00  jnz     short loc_18000DE2A
0x18000de02  mov     ebx, 1
0x18000de07  mov     rcx, cs:WPP_GLOBAL_Control
0x18000de0e  cmp     rcx, rdi
0x18000de11  jz      short loc_18000DE50
0x18000de13  test    byte ptr [rcx+1Ch], 10h
0x18000de17  jz      short loc_18000DE50
0x18000de19  lea     edx, [rbx+48h]
0x18000de1c  mov     rcx, [rcx+10h]
0x18000de20  mov     r8, rsi
0x18000de23  call    WPP_SF_
0x18000de28  jmp     short loc_18000DE50
0x18000de2a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000de31  cmp     rcx, rdi
0x18000de34  jz      short loc_18000DE50
0x18000de36  test    byte ptr [rcx+1Ch], 4
0x18000de3a  jz      short loc_18000DE50
0x18000de3c  mov     edx, 4Ah ; 'J'
0x18000de41  mov     rcx, [rcx+10h]
0x18000de45  mov     r9d, eax
0x18000de48  mov     r8, rsi
0x18000de4b  call    WPP_SF_D
0x18000de50  mov     rcx, [rsp+38h+hKey]; hKey
0x18000de55  call    cs:__imp_RegCloseKey
0x18000de5b  jmp     short loc_18000DE95
0x18000de5d  jle     short loc_18000DE68
0x18000de5f  movzx   ebx, ax
0x18000de62  or      ebx, 80070000h
0x18000de68  mov     rcx, cs:WPP_GLOBAL_Control
0x18000de6f  lea     rdi, WPP_GLOBAL_Control
0x18000de76  cmp     rcx, rdi
0x18000de79  jz      short loc_18000DEBB
0x18000de7b  test    byte ptr [rcx+1Ch], 4
0x18000de7f  jz      short loc_18000DE9C
0x18000de81  mov     rcx, [rcx+10h]
0x18000de85  mov     edx, 4Bh ; 'K'
0x18000de8a  mov     r9d, ebx
0x18000de8d  mov     r8, rsi
0x18000de90  call    WPP_SF_D
0x18000de95  mov     rcx, cs:WPP_GLOBAL_Control
0x18000de9c  cmp     rcx, rdi
0x18000de9f  jz      short loc_18000DEBB
0x18000dea1  test    byte ptr [rcx+1Ch], 10h
0x18000dea5  jz      short loc_18000DEBB
0x18000dea7  mov     rcx, [rcx+10h]
0x18000deab  mov     edx, 4Ch ; 'L'
0x18000deb0  mov     r9d, ebx
0x18000deb3  mov     r8, rsi
0x18000deb6  call    WPP_SF_D
0x18000debb  mov     rsi, [rsp+38h+arg_10]
0x18000dec0  mov     eax, ebx
0x18000dec2  mov     rbx, [rsp+38h+arg_8]
0x18000dec7  add     rsp, 30h
0x18000decb  pop     rdi
0x18000decc  retn
```
