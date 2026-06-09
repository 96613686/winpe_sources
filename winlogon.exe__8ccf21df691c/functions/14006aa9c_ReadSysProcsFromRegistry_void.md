# ReadSysProcsFromRegistry(void)

- ea: `0x14006aa9c`
- end: `0x14006adcc`
- name: `?ReadSysProcsFromRegistry@@YAXXZ`
- size: `816`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x14006c2e0`

## callees

- `0x1400057f4`
- `0x1400198e0`
- `0x14004df08`
- `0x140053720`
- `0x140053c60`
- `0x14006905c`
- `0x14006aa9c`
- `0x14009cc54`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x14006ab92`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x14006ab92`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x14006ac83`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x14006ac83`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14006aaf4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14006aaf4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14006ada1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14009f5a3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14006ada1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14009f5a3`

## pseudocode

```c
void ReadSysProcsFromRegistry(void)
{
  int v0; // edi
  unsigned int InfoKeyW; // eax
  CUser *v2; // r10
  __int64 v3; // rdx
  __int64 v4; // r9
  __int64 v5; // rcx
  DWORD i; // ebx
  unsigned __int64 v7; // rdx
  __int64 v8; // rcx
  unsigned __int16 *v9; // rcx
  DWORD cchValueName; // [rsp+60h] [rbp-248h] BYREF
  int v11; // [rsp+64h] [rbp-244h]
  HKEY hKey; // [rsp+68h] [rbp-240h] BYREF
  DWORD v13; // [rsp+70h] [rbp-238h]
  WCHAR ValueName[264]; // [rsp+80h] [rbp-228h] BYREF

  hKey = 0;
  v0 = 0;
  v11 = 0;
  CleanupSysProcs();
  InfoKeyW = RegOpenKeyExW(
               HKEY_LOCAL_MACHINE,
               L"System\\CurrentControlSet\\Control\\Terminal Server\\SysProcs",
               0,
               0x20019u,
               &hKey);
  if ( (InfoKeyW & 0xFFFFFFFD) != 0 )
  {
    v2 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v3 = 159;
LABEL_6:
      v4 = InfoKeyW;
      v5 = *((_QWORD *)v2 + 2);
LABEL_7:
      WPP_SF_d(v5, v3, WPP_c5e4d7264d013ec9a3e90eef35698a72_Traceguids, v4);
    }
  }
  else if ( !InfoKeyW )
  {
    InfoKeyW = RegQueryInfoKeyW(hKey, 0, 0, 0, 0, 0, 0, &NumSysProcs, 0, 0, 0, 0);
    if ( InfoKeyW )
    {
      v2 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v3 = 160;
        goto LABEL_6;
      }
    }
    else if ( NumSysProcs )
    {
      SysProcs = (unsigned __int16 **)WLAlloc(8LL * NumSysProcs);
      if ( SysProcs )
      {
        for ( i = 0; ; ++i )
        {
          v13 = i;
          if ( i >= NumSysProcs
            || (cchValueName = 260,
                InfoKeyW = RegEnumValueW(hKey, i, ValueName, &cchValueName, 0, 0, 0, 0),
                InfoKeyW == 259) )
          {
            NumSysProcs = i;
            v0 = 1;
            v11 = 1;
            goto LABEL_37;
          }
          if ( InfoKeyW )
            break;
          v7 = cchValueName;
          v8 = ++cchValueName;
          if ( v7 >= 260 )
            _report_rangecheckfailure();
          ValueName[v7] = 0;
          SysProcs[i] = (unsigned __int16 *)WLAlloc(2 * v8);
          v9 = SysProcs[i];
          if ( !v9 )
          {
            if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_DD(*((_QWORD *)WPP_GLOBAL_Control + 2), 163, WPP_c5e4d7264d013ec9a3e90eef35698a72_Traceguids, i);
            }
            goto LABEL_37;
          }
          memcpy_0(v9, ValueName, 2LL * cchValueName);
        }
        v2 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v3 = 162;
          goto LABEL_6;
        }
      }
      else if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
             && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
             && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v3 = 161;
        v4 = 8;
        v5 = *((_QWORD *)WPP_GLOBAL_Control + 2);
        goto LABEL_7;
      }
    }
  }
LABEL_37:
  if ( !v0 )
    CleanupSysProcs();
  if ( hKey )
    RegCloseKey(hKey);
}

```

## disassembly

```asm
0x14006aa9c  mov     [rsp+arg_0], rbx
0x14006aaa1  mov     [rsp+arg_8], rsi
0x14006aaa6  push    rdi
0x14006aaa7  sub     rsp, 2A0h
0x14006aaae  mov     rax, cs:__security_cookie
0x14006aab5  xor     rax, rsp
0x14006aab8  mov     [rsp+2A8h+var_18], rax
0x14006aac0  xor     esi, esi
0x14006aac2  mov     [rsp+2A8h+hKey], rsi
0x14006aac7  mov     edi, esi
0x14006aac9  mov     [rsp+2A8h+var_244], esi
0x14006aacd  call    ?CleanupSysProcs@@YAXXZ; CleanupSysProcs(void)
0x14006aad2  nop
0x14006aad3  lea     rax, [rsp+2A8h+hKey]
0x14006aad8  mov     [rsp+2A8h+phkResult], rax; phkResult
0x14006aadd  mov     r9d, 20019h; samDesired
0x14006aae3  xor     r8d, r8d; ulOptions
0x14006aae6  lea     rdx, aSystemCurrentc_3; "System\\CurrentControlSet\\Control\\Ter"...
0x14006aaed  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14006aaf4  call    cs:__imp_RegOpenKeyExW
0x14006aafa  test    eax, 0FFFFFFFDh
0x14006aaff  jz      short loc_14006AB4E
0x14006ab01  lea     rcx, WPP_GLOBAL_Control
0x14006ab08  mov     r10, cs:WPP_GLOBAL_Control
0x14006ab0f  cmp     r10, rcx
0x14006ab12  jz      loc_14006AD8E
0x14006ab18  test    dword ptr [r10+1Ch], 1000h
0x14006ab20  jz      loc_14006AD8E
0x14006ab26  cmp     byte ptr [r10+19h], 2
0x14006ab2b  jb      loc_14006AD8E
0x14006ab31  mov     edx, 9Fh
0x14006ab36  mov     r9d, eax
0x14006ab39  mov     rcx, [r10+10h]
0x14006ab3d  lea     r8, WPP_c5e4d7264d013ec9a3e90eef35698a72_Traceguids
0x14006ab44  call    WPP_SF_d
0x14006ab49  jmp     loc_14006AD8E
0x14006ab4e  test    eax, eax
0x14006ab50  jnz     loc_14006AD8E
0x14006ab56  mov     [rsp+2A8h+lpftLastWriteTime], rsi; lpftLastWriteTime
0x14006ab5b  mov     [rsp+2A8h+lpcbSecurityDescriptor], rsi; lpcbSecurityDescriptor
0x14006ab60  mov     [rsp+2A8h+lpcbMaxValueLen], rsi; lpcbMaxValueLen
0x14006ab65  mov     [rsp+2A8h+lpcbMaxValueNameLen], rsi; lpcbMaxValueNameLen
0x14006ab6a  lea     rax, ?NumSysProcs@@3KA; ulong NumSysProcs
0x14006ab71  mov     [rsp+2A8h+lpcValues], rax; lpcValues
0x14006ab76  mov     [rsp+2A8h+lpcbMaxClassLen], rsi; lpcbMaxClassLen
0x14006ab7b  mov     [rsp+2A8h+lpcbMaxSubKeyLen], rsi; lpcbMaxSubKeyLen
0x14006ab80  mov     [rsp+2A8h+phkResult], rsi; lpcSubKeys
0x14006ab85  xor     r9d, r9d; lpReserved
0x14006ab88  xor     r8d, r8d; lpcchClass
0x14006ab8b  xor     edx, edx; lpClass
0x14006ab8d  mov     rcx, [rsp+2A8h+hKey]; hKey
0x14006ab92  call    cs:__imp_RegQueryInfoKeyW
0x14006ab98  test    eax, eax
0x14006ab9a  jz      short loc_14006ABD6
0x14006ab9c  lea     rcx, WPP_GLOBAL_Control
0x14006aba3  mov     r10, cs:WPP_GLOBAL_Control
0x14006abaa  cmp     r10, rcx
0x14006abad  jz      loc_14006AD8E
0x14006abb3  test    dword ptr [r10+1Ch], 1000h
0x14006abbb  jz      loc_14006AD8E
0x14006abc1  cmp     byte ptr [r10+19h], 2
0x14006abc6  jb      loc_14006AD8E
0x14006abcc  mov     edx, 0A0h
0x14006abd1  jmp     loc_14006AB36
0x14006abd6  mov     eax, cs:?NumSysProcs@@3KA; ulong NumSysProcs
0x14006abdc  test    eax, eax
0x14006abde  jz      loc_14006AD8E
0x14006abe4  mov     ecx, eax
0x14006abe6  shl     rcx, 3; unsigned __int64
0x14006abea  call    ?WLAlloc@@YAPEAX_K@Z; WLAlloc(unsigned __int64)
0x14006abef  mov     cs:?SysProcs@@3PEAPEAGEA, rax; ushort * * SysProcs
0x14006abf6  test    rax, rax
0x14006abf9  jnz     short loc_14006AC3D
0x14006abfb  lea     rcx, WPP_GLOBAL_Control
0x14006ac02  mov     rax, cs:WPP_GLOBAL_Control
0x14006ac09  cmp     rax, rcx
0x14006ac0c  jz      loc_14006AD8E
0x14006ac12  test    dword ptr [rax+1Ch], 1000h
0x14006ac19  jz      loc_14006AD8E
0x14006ac1f  cmp     byte ptr [rax+19h], 2
0x14006ac23  jb      loc_14006AD8E
0x14006ac29  mov     edx, 0A1h
0x14006ac2e  mov     r9d, 8
0x14006ac34  mov     rcx, [rax+10h]
0x14006ac38  jmp     loc_14006AB3D
0x14006ac3d  mov     ebx, esi
0x14006ac3f  mov     [rsp+2A8h+var_238], ebx
0x14006ac43  cmp     ebx, cs:?NumSysProcs@@3KA; ulong NumSysProcs
0x14006ac49  jnb     loc_14006AD7F
0x14006ac4f  mov     [rsp+2A8h+cchValueName], esi
0x14006ac53  mov     [rsp+2A8h+cchValueName], 104h
0x14006ac5b  mov     [rsp+2A8h+lpcValues], rsi; lpcbData
0x14006ac60  mov     [rsp+2A8h+lpcbMaxClassLen], rsi; lpData
0x14006ac65  mov     [rsp+2A8h+lpcbMaxSubKeyLen], rsi; lpType
0x14006ac6a  mov     [rsp+2A8h+phkResult], rsi; lpReserved
0x14006ac6f  lea     r9, [rsp+2A8h+cchValueName]; lpcchValueName
0x14006ac74  lea     r8, [rsp+2A8h+ValueName]; lpValueName
0x14006ac7c  mov     edx, ebx; dwIndex
0x14006ac7e  mov     rcx, [rsp+2A8h+hKey]; hKey
0x14006ac83  call    cs:__imp_RegEnumValueW
0x14006ac89  cmp     eax, 103h
0x14006ac8e  jz      loc_14006AD7F
0x14006ac94  test    eax, eax
0x14006ac96  jz      short loc_14006ACD2
0x14006ac98  lea     rcx, WPP_GLOBAL_Control
0x14006ac9f  mov     r10, cs:WPP_GLOBAL_Control
0x14006aca6  cmp     r10, rcx
0x14006aca9  jz      loc_14006AD8E
0x14006acaf  test    dword ptr [r10+1Ch], 1000h
0x14006acb7  jz      loc_14006AD8E
0x14006acbd  cmp     byte ptr [r10+19h], 2
0x14006acc2  jb      loc_14006AD8E
0x14006acc8  mov     edx, 0A2h
0x14006accd  jmp     loc_14006AB36
0x14006acd2  mov     ecx, [rsp+2A8h+cchValueName]
0x14006acd6  lea     rdx, [rcx+rcx]
0x14006acda  inc     ecx
0x14006acdc  mov     [rsp+2A8h+cchValueName], ecx
0x14006ace0  cmp     rdx, 208h
0x14006ace7  jnb     loc_14006AD7A
0x14006aced  mov     [rsp+rdx+2A8h+ValueName], si
0x14006acf5  add     rcx, rcx; unsigned __int64
0x14006acf8  call    ?WLAlloc@@YAPEAX_K@Z; WLAlloc(unsigned __int64)
0x14006acfd  mov     edx, ebx
0x14006acff  mov     rcx, cs:?SysProcs@@3PEAPEAGEA; ushort * * SysProcs
0x14006ad06  mov     [rcx+rdx*8], rax
0x14006ad0a  mov     rax, cs:?SysProcs@@3PEAPEAGEA; ushort * * SysProcs
0x14006ad11  mov     rcx, [rax+rdx*8]; void *
0x14006ad15  test    rcx, rcx
0x14006ad18  jnz     short loc_14006AD5E
0x14006ad1a  lea     rcx, WPP_GLOBAL_Control
0x14006ad21  mov     rax, cs:WPP_GLOBAL_Control
0x14006ad28  cmp     rax, rcx
0x14006ad2b  jz      short loc_14006AD8E
0x14006ad2d  test    dword ptr [rax+1Ch], 1000h
0x14006ad34  jz      short loc_14006AD8E
0x14006ad36  cmp     byte ptr [rax+19h], 2
0x14006ad3a  jb      short loc_14006AD8E
0x14006ad3c  mov     edx, 0A3h
0x14006ad41  mov     dword ptr [rsp+2A8h+phkResult], 8
0x14006ad49  mov     r9d, ebx
0x14006ad4c  lea     r8, WPP_c5e4d7264d013ec9a3e90eef35698a72_Traceguids
0x14006ad53  mov     rcx, [rax+10h]
0x14006ad57  call    WPP_SF_DD
0x14006ad5c  jmp     short loc_14006AD8E
0x14006ad5e  mov     r8d, [rsp+2A8h+cchValueName]
0x14006ad63  add     r8, r8; Size
0x14006ad66  lea     rdx, [rsp+2A8h+ValueName]; Src
0x14006ad6e  call    memcpy_0
0x14006ad73  inc     ebx
0x14006ad75  jmp     loc_14006AC3F
0x14006ad7a  call    __report_rangecheckfailure
0x14006ad7f  mov     cs:?NumSysProcs@@3KA, ebx; ulong NumSysProcs
0x14006ad85  mov     edi, 1
0x14006ad8a  mov     [rsp+2A8h+var_244], edi
0x14006ad8e  test    edi, edi
0x14006ad90  jnz     short loc_14006AD97
0x14006ad92  call    ?CleanupSysProcs@@YAXXZ; CleanupSysProcs(void)
0x14006ad97  mov     rcx, [rsp+2A8h+hKey]; hKey
0x14006ad9c  test    rcx, rcx
0x14006ad9f  jz      short loc_14006ADA7
0x14006ada1  call    cs:__imp_RegCloseKey
0x14006ada7  mov     rcx, [rsp+2A8h+var_18]
0x14006adaf  xor     rcx, rsp; StackCookie
0x14006adb2  call    __security_check_cookie
0x14006adb7  lea     r11, [rsp+2A8h+var_8]
0x14006adbf  mov     rbx, [r11+10h]
0x14006adc3  mov     rsi, [r11+18h]
0x14006adc7  mov     rsp, r11
0x14006adca  pop     rdi
0x14006adcb  retn
0x14009f585  push    rbp
0x14009f587  sub     rsp, 60h
0x14009f58b  mov     rbp, rdx
0x14009f58e  cmp     dword ptr [rbp+64h], 0
0x14009f592  jnz     short loc_14009F59A
0x14009f594  call    ?CleanupSysProcs@@YAXXZ; CleanupSysProcs(void)
0x14009f599  nop
0x14009f59a  mov     rcx, [rbp+68h]; hKey
0x14009f59e  test    rcx, rcx
0x14009f5a1  jz      short loc_14009F5AA
0x14009f5a3  call    cs:__imp_RegCloseKey
0x14009f5a9  nop
0x14009f5aa  add     rsp, 60h
0x14009f5ae  pop     rbp
0x14009f5af  retn
```
