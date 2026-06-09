# CWorkspaceFileAssociation::SaveBackupDataToRegistry(void *,HKEY__ *)

- ea: `0x1800556e8`
- end: `0x180055a12`
- name: `?SaveBackupDataToRegistry@CWorkspaceFileAssociation@@IEAAJPEAXPEAUHKEY__@@@Z`
- size: `810`
- prototype: `int(CWorkspaceFileAssociation *__hidden this, void *, HKEY)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180053648`

## callees

- `0x18000b1d8`
- `0x18000d8d4`
- `0x18000ec94`
- `0x1800556e8`

## import_xrefs

- `ADVAPI32!RegCreateKeyTransactedW` at `0x180055771`
- `ADVAPI32!RegCreateKeyTransactedW` at `0x180055771`
- `ADVAPI32!RegCloseKey` at `0x1800559f3`
- `ADVAPI32!RegCloseKey` at `0x1800559f3`
- `ADVAPI32!RegSetValueExW` at `0x18005581e`
- `ADVAPI32!RegSetValueExW` at `0x1800558c6`
- `ADVAPI32!RegSetValueExW` at `0x180055966`
- `ADVAPI32!RegSetValueExW` at `0x18005581e`
- `ADVAPI32!RegSetValueExW` at `0x1800558c6`
- `ADVAPI32!RegSetValueExW` at `0x180055966`

## pseudocode

```c
// Hidden C++ exception states: #try_helpers=1
__int64 __fastcall CWorkspaceFileAssociation::SaveBackupDataToRegistry(
        CWorkspaceFileAssociation *this,
        void *a2,
        HKEY a3)
{
  const WCHAR *v6; // rax
  int v7; // ebx
  unsigned int v8; // edi
  unsigned int CurrentThreadActivityIdPrefix; // eax
  const BYTE *v10; // rax
  int v11; // ebx
  unsigned int v12; // edi
  unsigned int v13; // eax
  const BYTE *v14; // rax
  int v15; // ebx
  unsigned int v16; // edi
  unsigned int v17; // eax
  int v18; // ebx
  unsigned int v19; // edi
  unsigned int v20; // eax
  unsigned int v22; // [rsp+60h] [rbp-28h]
  HKEY hKey[3]; // [rsp+68h] [rbp-20h] BYREF
  DWORD dwDisposition; // [rsp+A8h] [rbp+20h] BYREF

  hKey[1] = HKEY_DYN_DATA|0x7FFFFFF8LL;
  hKey[0] = 0;
  dwDisposition = 0;
  v6 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 216);
  v7 = RegCreateKeyTransactedW(a3, v6, 0, 0, 0, 0x20006u, 0, hKey, &dwDisposition, a2, 0);
  if ( v7 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      if ( v7 > 0 )
        v8 = (unsigned __int16)v7 | 0x80070000;
      else
        v8 = v7;
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        45,
        WPP_1b4a91e28c533a877c5d59eaaa244463_Traceguids,
        CurrentThreadActivityIdPrefix,
        v8);
    }
    if ( v7 > 0 )
      v7 = (unsigned __int16)v7 | 0x80070000;
    v22 = v7;
  }
  else
  {
    v10 = (const BYTE *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 48);
    v11 = RegSetValueExW(hKey[0], L"TSWorkspaceAssocExtName", 0, 1u, v10, 2 * *((_DWORD *)this + 16) + 2);
    if ( v11 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        if ( v11 > 0 )
          v12 = (unsigned __int16)v11 | 0x80070000;
        else
          v12 = v11;
        v13 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, WPP_1b4a91e28c533a877c5d59eaaa244463_Traceguids, v13, v12);
      }
      if ( v11 > 0 )
        v11 = (unsigned __int16)v11 | 0x80070000;
      v22 = v11;
    }
    else
    {
      v14 = (const BYTE *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 80);
      v15 = RegSetValueExW(hKey[0], L"TSWorkspaceAssocAppAlias", 0, 1u, v14, 2 * *((_DWORD *)this + 24) + 2);
      if ( v15 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          if ( v15 > 0 )
            v16 = (unsigned __int16)v15 | 0x80070000;
          else
            v16 = v15;
          v17 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, WPP_1b4a91e28c533a877c5d59eaaa244463_Traceguids, v17, v16);
        }
        if ( v15 > 0 )
          v15 = (unsigned __int16)v15 | 0x80070000;
        v22 = v15;
      }
      else
      {
        v18 = RegSetValueExW(hKey[0], L"TSWorkspaceAssocAsPrimary", 0, 4u, (const BYTE *)this + 208, 4u);
        if ( v18 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            if ( v18 > 0 )
              v19 = (unsigned __int16)v18 | 0x80070000;
            else
              v19 = v18;
            v20 = RdpWppGetCurrentThreadActivityIdPrefix();
            WPP_SF_Dd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              48,
              WPP_1b4a91e28c533a877c5d59eaaa244463_Traceguids,
              v20,
              v19);
          }
          if ( v18 > 0 )
            v18 = (unsigned __int16)v18 | 0x80070000;
          v22 = v18;
        }
        else
        {
          v22 = 0;
        }
      }
    }
  }
  if ( hKey[0] )
    RegCloseKey(hKey[0]);
  return v22;
}

```

## disassembly

```asm
0x1800556e8  mov     rax, rsp
0x1800556eb  push    rdi
0x1800556ec  sub     rsp, 80h
0x1800556f3  mov     qword ptr [rax-18h], 0FFFFFFFFFFFFFFFEh
0x1800556fb  mov     [rax+8], rbx
0x1800556ff  mov     [rax+10h], rsi
0x180055703  mov     rbx, r8
0x180055706  mov     rsi, rdx
0x180055709  mov     rdi, rcx
0x18005570c  mov     qword ptr [rax-20h], 0
0x180055714  mov     dword ptr [rax+20h], 0
0x18005571b  add     rcx, 0D8h
0x180055722  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180055727  mov     [rsp+88h+pExtendedParemeter], 0; pExtendedParemeter
0x180055730  mov     [rsp+88h+hTransaction], rsi; hTransaction
0x180055735  lea     rcx, [rsp+88h+dwDisposition]
0x18005573d  mov     [rsp+88h+lpdwDisposition], rcx; lpdwDisposition
0x180055742  lea     rcx, [rsp+88h+hKey]
0x180055747  mov     [rsp+88h+phkResult], rcx; phkResult
0x18005574c  mov     [rsp+88h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180055755  mov     [rsp+88h+samDesired], 20006h; samDesired
0x18005575d  mov     [rsp+88h+dwOptions], 0; dwOptions
0x180055765  xor     r9d, r9d; lpClass
0x180055768  xor     r8d, r8d; Reserved
0x18005576b  mov     rdx, rax; lpSubKey
0x18005576e  mov     rcx, rbx; hKey
0x180055771  call    cs:__imp_RegCreateKeyTransactedW
0x180055777  mov     ebx, eax
0x180055779  test    eax, eax
0x18005577b  jz      short loc_1800557EB
0x18005577d  lea     rax, WPP_GLOBAL_Control
0x180055784  mov     rcx, cs:WPP_GLOBAL_Control
0x18005578b  cmp     rcx, rax
0x18005578e  jz      short loc_1800557D5
0x180055790  test    byte ptr [rcx+1Ch], 8
0x180055794  jz      short loc_1800557D5
0x180055796  cmp     byte ptr [rcx+19h], 2
0x18005579a  jb      short loc_1800557D5
0x18005579c  test    ebx, ebx
0x18005579e  jg      short loc_1800557A4
0x1800557a0  mov     edi, ebx
0x1800557a2  jmp     short loc_1800557AD
0x1800557a4  movzx   edi, bx
0x1800557a7  or      edi, 80070000h
0x1800557ad  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800557b2  mov     edx, 2Dh ; '-'
0x1800557b7  mov     [rsp+88h+dwOptions], edi
0x1800557bb  mov     r9d, eax
0x1800557be  lea     r8, WPP_1b4a91e28c533a877c5d59eaaa244463_Traceguids
0x1800557c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800557cc  mov     rcx, [rcx+10h]
0x1800557d0  call    WPP_SF_Dd
0x1800557d5  test    ebx, ebx
0x1800557d7  jle     short loc_1800557E2
0x1800557d9  movzx   ebx, bx
0x1800557dc  or      ebx, 80070000h
0x1800557e2  mov     [rsp+88h+var_28], ebx
0x1800557e6  jmp     loc_1800559E9
0x1800557eb  lea     rcx, [rdi+30h]
0x1800557ef  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800557f4  mov     edx, [rdi+40h]
0x1800557f7  lea     edx, ds:2[rdx*2]
0x1800557fe  mov     [rsp+88h+samDesired], edx; cbData
0x180055802  mov     qword ptr [rsp+88h+dwOptions], rax; lpData
0x180055807  mov     esi, 1
0x18005580c  mov     r9d, esi; dwType
0x18005580f  xor     r8d, r8d; Reserved
0x180055812  lea     rdx, aTsworkspaceass_0; "TSWorkspaceAssocExtName"
0x180055819  mov     rcx, [rsp+88h+hKey]; hKey
0x18005581e  call    cs:__imp_RegSetValueExW
0x180055824  mov     ebx, eax
0x180055826  test    eax, eax
0x180055828  jz      short loc_180055898
0x18005582a  lea     rax, WPP_GLOBAL_Control
0x180055831  mov     rcx, cs:WPP_GLOBAL_Control
0x180055838  cmp     rcx, rax
0x18005583b  jz      short loc_180055882
0x18005583d  test    byte ptr [rcx+1Ch], 8
0x180055841  jz      short loc_180055882
0x180055843  cmp     byte ptr [rcx+19h], 2
0x180055847  jb      short loc_180055882
0x180055849  test    ebx, ebx
0x18005584b  jg      short loc_180055851
0x18005584d  mov     edi, ebx
0x18005584f  jmp     short loc_18005585A
0x180055851  movzx   edi, bx
0x180055854  or      edi, 80070000h
0x18005585a  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18005585f  mov     edx, 2Eh ; '.'
0x180055864  mov     [rsp+88h+dwOptions], edi
0x180055868  mov     r9d, eax
0x18005586b  lea     r8, WPP_1b4a91e28c533a877c5d59eaaa244463_Traceguids
0x180055872  mov     rcx, cs:WPP_GLOBAL_Control
0x180055879  mov     rcx, [rcx+10h]
0x18005587d  call    WPP_SF_Dd
0x180055882  test    ebx, ebx
0x180055884  jle     short loc_18005588F
0x180055886  movzx   ebx, bx
0x180055889  or      ebx, 80070000h
0x18005588f  mov     [rsp+88h+var_28], ebx
0x180055893  jmp     loc_1800559E9
0x180055898  lea     rcx, [rdi+50h]
0x18005589c  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800558a1  mov     edx, [rdi+60h]
0x1800558a4  lea     edx, ds:2[rdx*2]
0x1800558ab  mov     [rsp+88h+samDesired], edx; cbData
0x1800558af  mov     qword ptr [rsp+88h+dwOptions], rax; lpData
0x1800558b4  mov     r9d, esi; dwType
0x1800558b7  xor     r8d, r8d; Reserved
0x1800558ba  lea     rdx, aTsworkspaceass_1; "TSWorkspaceAssocAppAlias"
0x1800558c1  mov     rcx, [rsp+88h+hKey]; hKey
0x1800558c6  call    cs:__imp_RegSetValueExW
0x1800558cc  mov     ebx, eax
0x1800558ce  test    eax, eax
0x1800558d0  jz      short loc_180055940
0x1800558d2  lea     rax, WPP_GLOBAL_Control
0x1800558d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800558e0  cmp     rcx, rax
0x1800558e3  jz      short loc_18005592A
0x1800558e5  test    byte ptr [rcx+1Ch], 8
0x1800558e9  jz      short loc_18005592A
0x1800558eb  cmp     byte ptr [rcx+19h], 2
0x1800558ef  jb      short loc_18005592A
0x1800558f1  test    ebx, ebx
0x1800558f3  jg      short loc_1800558F9
0x1800558f5  mov     edi, ebx
0x1800558f7  jmp     short loc_180055902
0x1800558f9  movzx   edi, bx
0x1800558fc  or      edi, 80070000h
0x180055902  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180055907  mov     edx, 2Fh ; '/'
0x18005590c  mov     [rsp+88h+dwOptions], edi
0x180055910  mov     r9d, eax
0x180055913  lea     r8, WPP_1b4a91e28c533a877c5d59eaaa244463_Traceguids
0x18005591a  mov     rcx, cs:WPP_GLOBAL_Control
0x180055921  mov     rcx, [rcx+10h]
0x180055925  call    WPP_SF_Dd
0x18005592a  test    ebx, ebx
0x18005592c  jle     short loc_180055937
0x18005592e  movzx   ebx, bx
0x180055931  or      ebx, 80070000h
0x180055937  mov     [rsp+88h+var_28], ebx
0x18005593b  jmp     loc_1800559E9
0x180055940  lea     rax, [rdi+0D0h]
0x180055947  mov     r9d, 4; dwType
0x18005594d  mov     [rsp+88h+samDesired], r9d; cbData
0x180055952  mov     qword ptr [rsp+88h+dwOptions], rax; lpData
0x180055957  xor     r8d, r8d; Reserved
0x18005595a  lea     rdx, aTsworkspaceass; "TSWorkspaceAssocAsPrimary"
0x180055961  mov     rcx, [rsp+88h+hKey]; hKey
0x180055966  call    cs:__imp_RegSetValueExW
0x18005596c  mov     ebx, eax
0x18005596e  test    eax, eax
0x180055970  jz      short loc_1800559DD
0x180055972  lea     rax, WPP_GLOBAL_Control
0x180055979  mov     rcx, cs:WPP_GLOBAL_Control
0x180055980  cmp     rcx, rax
0x180055983  jz      short loc_1800559CA
0x180055985  test    byte ptr [rcx+1Ch], 8
0x180055989  jz      short loc_1800559CA
0x18005598b  cmp     byte ptr [rcx+19h], 2
0x18005598f  jb      short loc_1800559CA
0x180055991  test    ebx, ebx
0x180055993  jg      short loc_180055999
0x180055995  mov     edi, ebx
0x180055997  jmp     short loc_1800559A2
0x180055999  movzx   edi, bx
0x18005599c  or      edi, 80070000h
0x1800559a2  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800559a7  mov     edx, 30h ; '0'
0x1800559ac  mov     [rsp+88h+dwOptions], edi
0x1800559b0  mov     r9d, eax
0x1800559b3  lea     r8, WPP_1b4a91e28c533a877c5d59eaaa244463_Traceguids
0x1800559ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1800559c1  mov     rcx, [rcx+10h]
0x1800559c5  call    WPP_SF_Dd
0x1800559ca  test    ebx, ebx
0x1800559cc  jle     short loc_1800559D7
0x1800559ce  movzx   ebx, bx
0x1800559d1  or      ebx, 80070000h
0x1800559d7  mov     [rsp+88h+var_28], ebx
0x1800559db  jmp     short loc_1800559E9
0x1800559dd  mov     [rsp+88h+var_28], 0
0x1800559e5  jmp     short loc_1800559E9
0x1800559e7  jmp     short $+2
0x1800559e9  mov     rcx, [rsp+88h+hKey]; hKey
0x1800559ee  test    rcx, rcx
0x1800559f1  jz      short loc_1800559F9
0x1800559f3  call    cs:__imp_RegCloseKey
0x1800559f9  mov     eax, [rsp+88h+var_28]
0x1800559fd  lea     r11, [rsp+88h+var_8]
0x180055a05  mov     rbx, [r11+10h]
0x180055a09  mov     rsi, [r11+18h]
0x180055a0d  mov     rsp, r11
0x180055a10  pop     rdi
0x180055a11  retn
```
