# BlbEnableNetworkShare(void)

- ea: `0x14011e818`
- end: `0x14011eaa7`
- name: `?BlbEnableNetworkShare@@YAJXZ`
- size: `655`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x14004a690`
- `0x14004b420`

## callees

- `0x140007ad3`
- `0x14000bb24`
- `0x14000bb4c`
- `0x140014200`
- `0x14003c434`
- `0x140094084`
- `0x1400945d0`
- `0x14011e6a4`
- `0x14011e818`
- `0x14011eab0`

## import_xrefs

- `KERNEL32!SetFileAttributesW` at `0x14011e935`
- `KERNEL32!SetFileAttributesW` at `0x14011e935`
- `KERNEL32!CreateDirectoryW` at `0x14011e8a8`
- `KERNEL32!CreateDirectoryW` at `0x14011e8a8`
- `KERNEL32!GetFileAttributesW` at `0x14011e8ef`
- `KERNEL32!GetFileAttributesW` at `0x14011e8ef`
- `KERNEL32!GetLastError` at `0x14011e8b2`
- `KERNEL32!GetLastError` at `0x14011e8fc`
- `KERNEL32!GetLastError` at `0x14011e906`
- `KERNEL32!GetLastError` at `0x14011e925`
- `KERNEL32!GetLastError` at `0x14011e8b2`
- `KERNEL32!GetLastError` at `0x14011e8fc`
- `KERNEL32!GetLastError` at `0x14011e906`
- `KERNEL32!GetLastError` at `0x14011e925`
- `ole32!CoTaskMemFree` at `0x14011ea5d`
- `ole32!CoTaskMemFree` at `0x14011ea5d`
- `NETAPI32!NetShareAdd` at `0x14011e9cc`
- `NETAPI32!NetShareAdd` at `0x14011e9cc`

## string_xrefs

- `0x14011e985`: `WsbMountedVolumes`

## pseudocode

```c
__int64 BlbEnableNetworkShare(void)
{
  int DoesNetworkShareExist; // eax
  signed int v1; // ebx
  int NetworkSharePath; // eax
  WCHAR *v3; // rsi
  signed int LastError; // eax
  DWORD FileAttributesW; // eax
  int v6; // ebx
  signed int v7; // edi
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+30h] [rbp-39h] BYREF
  BYTE buf[8]; // [rsp+50h] [rbp-19h] BYREF
  unsigned int v11; // [rsp+58h] [rbp-11h]
  __int64 v12; // [rsp+60h] [rbp-9h]
  int v13; // [rsp+68h] [rbp-1h]
  int v14; // [rsp+6Ch] [rbp+3h]
  WCHAR *v15; // [rsp+78h] [rbp+Fh]
  __int64 v16; // [rsp+80h] [rbp+17h]
  LPVOID lpSecurityDescriptor; // [rsp+90h] [rbp+27h]
  unsigned __int8 v18; // [rsp+D0h] [rbp+67h] BYREF
  DWORD parm_err; // [rsp+D8h] [rbp+6Fh] BYREF
  LPCWSTR lpPathName; // [rsp+E0h] [rbp+77h] BYREF

  lpPathName = 0;
  memset_0(buf, 0, 0x48u);
  v18 = 0;
  DoesNetworkShareExist = BlbDoesNetworkShareExist(&v18);
  v1 = DoesNetworkShareExist;
  if ( v18 )
    goto LABEL_39;
  if ( DoesNetworkShareExist >= 0 )
  {
    NetworkSharePath = BlbGetNetworkSharePath((unsigned __int16 **)&lpPathName);
    v3 = (WCHAR *)lpPathName;
    v1 = NetworkSharePath;
    if ( NetworkSharePath < 0
      || (memset(&SecurityAttributes, 0, sizeof(SecurityAttributes)),
          v1 = BlbutilCreateSecurityDescriptorForAdminsAndBOs(&SecurityAttributes),
          v1 < 0) )
    {
LABEL_37:
      if ( v3 )
        CoTaskMemFree(v3);
LABEL_39:
      if ( v1 >= 0 )
        return (unsigned int)v1;
      goto LABEL_40;
    }
    if ( !CreateDirectoryW(v3, &SecurityAttributes) )
    {
      LastError = GetLastError();
      if ( LastError != 183 )
      {
        if ( LastError <= 0 )
          goto LABEL_14;
        goto LABEL_16;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_94c6ea76801837b238af0538cad4a1a5_Traceguids);
      }
    }
    FileAttributesW = GetFileAttributesW(v3);
    if ( FileAttributesW != -1 && SetFileAttributesW(v3, FileAttributesW | 2) )
    {
      memset_0(buf, 0, 0x48u);
      parm_err = 0;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_94c6ea76801837b238af0538cad4a1a5_Traceguids, v3);
      }
      v11 = 0x80000000;
      *(_QWORD *)buf = L"WsbMountedVolumes";
      lpSecurityDescriptor = SecurityAttributes.lpSecurityDescriptor;
      v12 = 0;
      v13 = 0;
      v14 = -1;
      v15 = v3;
      v16 = 0;
      v7 = NetShareAdd(0, 0x1F6u, buf, &parm_err);
      if ( !v7 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_94c6ea76801837b238af0538cad4a1a5_Traceguids);
        }
        goto LABEL_36;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_94c6ea76801837b238af0538cad4a1a5_Traceguids);
      }
      if ( v7 <= 0 )
      {
        v1 = v7;
        goto LABEL_36;
      }
      v6 = (unsigned __int16)v7;
      goto LABEL_17;
    }
    if ( (int)GetLastError() <= 0 )
    {
      LastError = GetLastError();
LABEL_14:
      v1 = LastError;
LABEL_36:
      BlbutilFreeSecurityDescriptor(&SecurityAttributes);
      goto LABEL_37;
    }
    LOWORD(LastError) = GetLastError();
LABEL_16:
    v6 = (unsigned __int16)LastError;
LABEL_17:
    v1 = v6 | 0x80070000;
    goto LABEL_36;
  }
LABEL_40:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_94c6ea76801837b238af0538cad4a1a5_Traceguids);
  }
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x14011e818  push    rbp
0x14011e81a  push    rbx
0x14011e81b  push    rsi
0x14011e81c  push    rdi
0x14011e81d  push    r13
0x14011e81f  lea     rbp, [rsp-37h]
0x14011e824  sub     rsp, 0A0h
0x14011e82b  xor     edx, edx; Val
0x14011e82d  mov     [rbp+57h+lpPathName], 0
0x14011e835  lea     rcx, [rbp+57h+buf]; void *
0x14011e839  lea     r8d, [rdx+48h]; Size
0x14011e83d  call    memset_0
0x14011e842  lea     rcx, [rbp+57h+arg_0]; unsigned __int8 *
0x14011e846  mov     [rbp+57h+arg_0], 0
0x14011e84a  call    ?BlbDoesNetworkShareExist@@YAJPEAE@Z; BlbDoesNetworkShareExist(uchar *)
0x14011e84f  cmp     [rbp+57h+arg_0], 0
0x14011e853  lea     r13, WPP_GLOBAL_Control
0x14011e85a  mov     ebx, eax
0x14011e85c  jnz     loc_14011EA63
0x14011e862  test    eax, eax
0x14011e864  js      loc_14011EA67
0x14011e86a  lea     rcx, [rbp+57h+lpPathName]; unsigned __int16 **
0x14011e86e  call    ?BlbGetNetworkSharePath@@YAJPEAPEAG@Z; BlbGetNetworkSharePath(ushort * *)
0x14011e873  mov     rsi, [rbp+57h+lpPathName]
0x14011e877  mov     ebx, eax
0x14011e879  test    eax, eax
0x14011e87b  js      loc_14011EA55
0x14011e881  xorps   xmm0, xmm0
0x14011e884  lea     rcx, [rbp+57h+SecurityAttributes]; struct _SECURITY_ATTRIBUTES *
0x14011e888  xor     eax, eax
0x14011e88a  movups  xmmword ptr [rbp+57h+SecurityAttributes.nLength], xmm0
0x14011e88e  mov     qword ptr [rbp+57h+SecurityAttributes.bInheritHandle], rax
0x14011e892  call    ?BlbutilCreateSecurityDescriptorForAdminsAndBOs@@YAJPEAU_SECURITY_ATTRIBUTES@@@Z; BlbutilCreateSecurityDescriptorForAdminsAndBOs(_SECURITY_ATTRIBUTES *)
0x14011e897  mov     ebx, eax
0x14011e899  test    eax, eax
0x14011e89b  js      loc_14011EA55
0x14011e8a1  lea     rdx, [rbp+57h+SecurityAttributes]; lpSecurityAttributes
0x14011e8a5  mov     rcx, rsi; lpPathName
0x14011e8a8  call    cs:__imp_CreateDirectoryW
0x14011e8ae  test    eax, eax
0x14011e8b0  jnz     short loc_14011E8EC
0x14011e8b2  call    cs:__imp_GetLastError
0x14011e8b8  cmp     eax, 0B7h
0x14011e8bd  jnz     short loc_14011E913
0x14011e8bf  mov     rcx, cs:WPP_GLOBAL_Control
0x14011e8c6  cmp     rcx, r13
0x14011e8c9  jz      short loc_14011E8EC
0x14011e8cb  test    byte ptr [rcx+1Ch], 1
0x14011e8cf  jz      short loc_14011E8EC
0x14011e8d1  cmp     byte ptr [rcx+19h], 5
0x14011e8d5  jb      short loc_14011E8EC
0x14011e8d7  mov     rcx, [rcx+10h]
0x14011e8db  lea     r8, WPP_94c6ea76801837b238af0538cad4a1a5_Traceguids
0x14011e8e2  mov     edx, 12h
0x14011e8e7  call    WPP_SF_
0x14011e8ec  mov     rcx, rsi; lpFileName
0x14011e8ef  call    cs:__imp_GetFileAttributesW
0x14011e8f5  or      edi, 0FFFFFFFFh
0x14011e8f8  cmp     eax, edi
0x14011e8fa  jnz     short loc_14011E92D
0x14011e8fc  call    cs:__imp_GetLastError
0x14011e902  test    eax, eax
0x14011e904  jg      short loc_14011E925
0x14011e906  call    cs:__imp_GetLastError
0x14011e90c  mov     ebx, eax
0x14011e90e  jmp     loc_14011EA4C
0x14011e913  test    eax, eax
0x14011e915  jle     short loc_14011E90C
0x14011e917  movzx   ebx, ax
0x14011e91a  or      ebx, 80070000h
0x14011e920  jmp     loc_14011EA4C
0x14011e925  call    cs:__imp_GetLastError
0x14011e92b  jmp     short loc_14011E917
0x14011e92d  or      eax, 2
0x14011e930  mov     rcx, rsi; lpFileName
0x14011e933  mov     edx, eax; dwFileAttributes
0x14011e935  call    cs:__imp_SetFileAttributesW
0x14011e93b  test    eax, eax
0x14011e93d  jz      short loc_14011E8FC
0x14011e93f  xor     edx, edx; Val
0x14011e941  lea     rcx, [rbp+57h+buf]; void *
0x14011e945  lea     r8d, [rdx+48h]; Size
0x14011e949  call    memset_0
0x14011e94e  mov     [rbp+57h+parm_err], 0
0x14011e955  mov     rcx, cs:WPP_GLOBAL_Control
0x14011e95c  cmp     rcx, r13
0x14011e95f  jz      short loc_14011E985
0x14011e961  test    byte ptr [rcx+1Ch], 1
0x14011e965  jz      short loc_14011E985
0x14011e967  cmp     byte ptr [rcx+19h], 5
0x14011e96b  jb      short loc_14011E985
0x14011e96d  mov     rcx, [rcx+10h]
0x14011e971  lea     r8, WPP_94c6ea76801837b238af0538cad4a1a5_Traceguids
0x14011e978  mov     edx, 13h
0x14011e97d  mov     r9, rsi
0x14011e980  call    WPP_SF_S
0x14011e985  lea     rax, netname; "WsbMountedVolumes"
0x14011e98c  mov     [rbp+57h+var_68], 80000000h
0x14011e993  mov     qword ptr [rbp+57h+buf], rax
0x14011e997  lea     r9, [rbp+57h+parm_err]; parm_err
0x14011e99b  mov     rax, [rbp+57h+SecurityAttributes.lpSecurityDescriptor]
0x14011e99f  lea     r8, [rbp+57h+buf]; buf
0x14011e9a3  mov     edx, 1F6h; level
0x14011e9a8  mov     [rbp+57h+var_30], rax
0x14011e9ac  xor     ecx, ecx; servername
0x14011e9ae  mov     [rbp+57h+var_60], 0
0x14011e9b6  mov     [rbp+57h+var_58], 0
0x14011e9bd  mov     [rbp+57h+var_54], edi
0x14011e9c0  mov     [rbp+57h+var_48], rsi
0x14011e9c4  mov     [rbp+57h+var_40], 0
0x14011e9cc  call    cs:__imp_NetShareAdd
0x14011e9d2  mov     edi, eax
0x14011e9d4  test    eax, eax
0x14011e9d6  jz      short loc_14011EA1F
0x14011e9d8  mov     rcx, cs:WPP_GLOBAL_Control
0x14011e9df  cmp     rcx, r13
0x14011e9e2  jz      short loc_14011EA0F
0x14011e9e4  test    byte ptr [rcx+1Ch], 1
0x14011e9e8  jz      short loc_14011EA0F
0x14011e9ea  cmp     byte ptr [rcx+19h], 2
0x14011e9ee  jb      short loc_14011EA0F
0x14011e9f0  mov     eax, [rbp+57h+parm_err]
0x14011e9f3  lea     r8, WPP_94c6ea76801837b238af0538cad4a1a5_Traceguids
0x14011e9fa  mov     rcx, [rcx+10h]
0x14011e9fe  mov     edx, 14h
0x14011ea03  mov     r9d, edi
0x14011ea06  mov     [rsp+0C0h+var_A0], eax
0x14011ea0a  call    WPP_SF_dd
0x14011ea0f  test    edi, edi
0x14011ea11  jg      short loc_14011EA17
0x14011ea13  mov     ebx, edi
0x14011ea15  jmp     short loc_14011EA4C
0x14011ea17  movzx   ebx, di
0x14011ea1a  jmp     loc_14011E91A
0x14011ea1f  mov     rcx, cs:WPP_GLOBAL_Control
0x14011ea26  cmp     rcx, r13
0x14011ea29  jz      short loc_14011EA4C
0x14011ea2b  test    byte ptr [rcx+1Ch], 1
0x14011ea2f  jz      short loc_14011EA4C
0x14011ea31  cmp     byte ptr [rcx+19h], 5
0x14011ea35  jb      short loc_14011EA4C
0x14011ea37  mov     rcx, [rcx+10h]
0x14011ea3b  lea     r8, WPP_94c6ea76801837b238af0538cad4a1a5_Traceguids
0x14011ea42  mov     edx, 15h
0x14011ea47  call    WPP_SF_
0x14011ea4c  lea     rcx, [rbp+57h+SecurityAttributes]; struct _SECURITY_ATTRIBUTES *
0x14011ea50  call    ?BlbutilFreeSecurityDescriptor@@YAXPEAU_SECURITY_ATTRIBUTES@@@Z; BlbutilFreeSecurityDescriptor(_SECURITY_ATTRIBUTES *)
0x14011ea55  test    rsi, rsi
0x14011ea58  jz      short loc_14011EA63
0x14011ea5a  mov     rcx, rsi; pv
0x14011ea5d  call    cs:__imp_CoTaskMemFree
0x14011ea63  test    ebx, ebx
0x14011ea65  jns     short loc_14011EA97
0x14011ea67  mov     rcx, cs:WPP_GLOBAL_Control
0x14011ea6e  cmp     rcx, r13
0x14011ea71  jz      short loc_14011EA97
0x14011ea73  test    byte ptr [rcx+1Ch], 1
0x14011ea77  jz      short loc_14011EA97
0x14011ea79  cmp     byte ptr [rcx+19h], 2
0x14011ea7d  jb      short loc_14011EA97
0x14011ea7f  mov     rcx, [rcx+10h]
0x14011ea83  lea     r8, WPP_94c6ea76801837b238af0538cad4a1a5_Traceguids
0x14011ea8a  mov     edx, 16h
0x14011ea8f  mov     r9d, ebx
0x14011ea92  call    WPP_SF_d
0x14011ea97  mov     eax, ebx
0x14011ea99  add     rsp, 0A0h
0x14011eaa0  pop     r13
0x14011eaa2  pop     rdi
0x14011eaa3  pop     rsi
0x14011eaa4  pop     rbx
0x14011eaa5  pop     rbp
0x14011eaa6  retn
```
