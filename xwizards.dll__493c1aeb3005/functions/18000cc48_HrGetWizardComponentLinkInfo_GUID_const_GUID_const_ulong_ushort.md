# HrGetWizardComponentLinkInfo(_GUID const *,_GUID const *,ulong *,ushort * *)

- ea: `0x18000cc48`
- end: `0x18000d023`
- name: `?HrGetWizardComponentLinkInfo@@YAJPEBU_GUID@@0PEAKPEAPEAG@Z`
- size: `987`
- prototype: `__int64 __fastcall(GUID *rguid, GUID *, LPBYTE lpData, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000f860`

## callees

- `0x1800085a8`
- `0x180008634`
- `0x18000ae04`
- `0x18000ae90`
- `0x18000cc48`
- `0x180032a02`
- `0x180032a30`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000cf65`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000cf65`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000cde4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000ceed`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000cde4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000ceed`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000cd9b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000cd9b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000ce09`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000ce09`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000cd13`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000cd76`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000cd13`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000cd76`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000cf86`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000cf86`

## string_xrefs

- `0x18000cdcb`: `Command Line`
- `0x18000ccc3`: `Components`

## pseudocode

```c
__int64 __fastcall HrGetWizardComponentLinkInfo(GUID *rguid, GUID *a2, LPBYTE lpData, unsigned __int16 **a4)
{
  __int64 v8; // rbx
  __int64 v9; // rax
  LSTATUS v10; // eax
  signed int v11; // ebx
  LSTATUS v12; // eax
  DWORD v13; // r14d
  unsigned __int16 *v14; // rax
  PVOID *v15; // rcx
  LSTATUS v16; // eax
  PVOID *v17; // rcx
  bool v18; // sf
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR SubKey[160]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 Data[264]; // [rsp+180h] [rbp+80h] BYREF

  hKey = 0;
  memset_0(Data, 0, 0x20Au);
  cbData = 522;
  SubKey[0] = 0;
  StringCchCopyW(SubKey, 0x9Du, L"Software\\Microsoft\\Windows\\CurrentVersion\\XWizards\\");
  StringCchCatW(SubKey, 0x9Du, L"Components");
  StringCchCatW(SubKey, 0x9Du, &qword_18003C618);
  v8 = -1;
  v9 = -1;
  do
    ++v9;
  while ( SubKey[v9] );
  StringFromGUID2(rguid, &SubKey[v9], 39);
  StringCchCatW(SubKey, 0x9Du, &qword_18003C618);
  StringCchCatW(SubKey, 0x9Du, L"Children");
  StringCchCatW(SubKey, 0x9Du, &qword_18003C618);
  do
    ++v8;
  while ( SubKey[v8] );
  StringFromGUID2(a2, &SubKey[v8], 39);
  v10 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, &hKey);
  v11 = v10;
  if ( !v10 )
  {
    v12 = RegQueryValueExW(hKey, L"Command Line", 0, 0, (LPBYTE)Data, &cbData);
    v11 = v12;
    v13 = cbData >> 1;
    if ( v12 )
    {
      if ( v12 != 2 && v13 )
        goto LABEL_23;
    }
    else if ( v13 )
    {
      v14 = (unsigned __int16 *)CoTaskMemAlloc(cbData);
      *a4 = v14;
      if ( v14 )
      {
        *v14 = 0;
        StringCchCopyW(*a4, v13, Data);
        goto LABEL_18;
      }
      v11 = 8;
      v15 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        goto LABEL_27;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      {
LABEL_24:
        if ( v15 != &WPP_GLOBAL_Control && (*((_BYTE *)v15 + 28) & 0x10) != 0 )
          WPP_SF_SD(
            (unsigned int)v15[2],
            104,
            (unsigned int)&WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids,
            (unsigned int)SubKey,
            v11);
        goto LABEL_27;
      }
      WPP_SF_SD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        101,
        (unsigned int)&WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids,
        (unsigned int)Data,
        8);
LABEL_23:
      v15 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_24;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_SD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        102,
        (unsigned int)&WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids,
        (unsigned int)SubKey,
        0);
LABEL_18:
    cbData = 4;
    v16 = RegQueryValueExW(hKey, L"User Flags", 0, 0, lpData, &cbData);
    v11 = v16;
    if ( v16 == 2 )
    {
      v11 = 0;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        WPP_SF_SD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          103,
          (unsigned int)&WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids,
          (unsigned int)SubKey,
          0);
      goto LABEL_27;
    }
    if ( v16 )
      goto LABEL_23;
LABEL_27:
    RegCloseKey(hKey);
    goto LABEL_28;
  }
  if ( v10 == 2 )
  {
    v17 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      WPP_SF_SD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        105,
        (unsigned int)&WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids,
        (unsigned int)SubKey,
        2);
      v17 = (PVOID *)WPP_GLOBAL_Control;
    }
    v11 = 0;
    goto LABEL_30;
  }
LABEL_28:
  v17 = (PVOID *)WPP_GLOBAL_Control;
  v18 = v11 < 0;
  if ( v11 <= 0 )
    goto LABEL_31;
  v11 = (unsigned __int16)v11 | 0x80070000;
LABEL_30:
  v18 = v11 < 0;
LABEL_31:
  if ( v18 )
  {
    CoTaskMemFree(*a4);
    *a4 = 0;
    v17 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v17 != &WPP_GLOBAL_Control && (*((_BYTE *)v17 + 28) & 0x10) != 0 )
    WPP_SF_d(v17[2], 106, &WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids, (unsigned int)v11);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18000cc48  push    rbp
0x18000cc4a  push    rbx
0x18000cc4b  push    rsi
0x18000cc4c  push    rdi
0x18000cc4d  push    r12
0x18000cc4f  push    r13
0x18000cc51  push    r14
0x18000cc53  push    r15
0x18000cc55  lea     rbp, [rsp-2A8h]
0x18000cc5d  sub     rsp, 3A8h
0x18000cc64  mov     rax, cs:__security_cookie
0x18000cc6b  xor     rax, rsp
0x18000cc6e  mov     [rbp+2E0h+var_50], rax
0x18000cc75  mov     r12, r8
0x18000cc78  mov     rsi, rdx
0x18000cc7b  mov     rdi, rcx
0x18000cc7e  mov     ebx, 20Ah
0x18000cc83  xor     r13d, r13d
0x18000cc86  lea     rcx, [rbp+2E0h+Data]; void *
0x18000cc8d  mov     r8d, ebx; Size
0x18000cc90  mov     [rsp+3E0h+hKey], r13
0x18000cc95  xor     edx, edx; Val
0x18000cc97  mov     r15, r9
0x18000cc9a  call    memset_0
0x18000cc9f  mov     r14d, 9Dh
0x18000cca5  mov     [rsp+3E0h+cbData], ebx
0x18000cca9  mov     edx, r14d; unsigned __int64
0x18000ccac  mov     [rsp+3E0h+SubKey], r13w
0x18000ccb2  lea     r8, aSoftwareMicros_0; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18000ccb9  lea     rcx, [rsp+3E0h+SubKey]; unsigned __int16 *
0x18000ccbe  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000ccc3  lea     r8, aComponents; "Components"
0x18000ccca  mov     edx, r14d; unsigned __int64
0x18000cccd  lea     rcx, [rsp+3E0h+SubKey]; unsigned __int16 *
0x18000ccd2  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000ccd7  lea     r8, qword_18003C618; unsigned __int16 *
0x18000ccde  mov     edx, r14d; unsigned __int64
0x18000cce1  lea     rcx, [rsp+3E0h+SubKey]; unsigned __int16 *
0x18000cce6  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000cceb  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000ccef  lea     rcx, [rsp+3E0h+SubKey]
0x18000ccf4  mov     rax, rbx
0x18000ccf7  inc     rax
0x18000ccfa  cmp     [rcx+rax*2], r13w
0x18000ccff  jnz     short loc_18000CCF7
0x18000cd01  lea     rdx, [rsp+3E0h+SubKey]
0x18000cd06  mov     r8d, 27h ; '''; cchMax
0x18000cd0c  lea     rdx, [rdx+rax*2]; lpsz
0x18000cd10  mov     rcx, rdi; rguid
0x18000cd13  call    cs:__imp_StringFromGUID2
0x18000cd19  lea     r8, qword_18003C618; unsigned __int16 *
0x18000cd20  mov     rdx, r14; unsigned __int64
0x18000cd23  lea     rcx, [rsp+3E0h+SubKey]; unsigned __int16 *
0x18000cd28  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000cd2d  lea     r8, aChildren; "Children"
0x18000cd34  mov     rdx, r14; unsigned __int64
0x18000cd37  lea     rcx, [rsp+3E0h+SubKey]; unsigned __int16 *
0x18000cd3c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000cd41  lea     r8, qword_18003C618; unsigned __int16 *
0x18000cd48  mov     rdx, r14; unsigned __int64
0x18000cd4b  lea     rcx, [rsp+3E0h+SubKey]; unsigned __int16 *
0x18000cd50  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000cd55  lea     rax, [rsp+3E0h+SubKey]
0x18000cd5a  inc     rbx
0x18000cd5d  cmp     [rax+rbx*2], r13w
0x18000cd62  jnz     short loc_18000CD5A
0x18000cd64  lea     rdx, [rsp+3E0h+SubKey]
0x18000cd69  mov     r8d, 27h ; '''; cchMax
0x18000cd6f  lea     rdx, [rdx+rbx*2]; lpsz
0x18000cd73  mov     rcx, rsi; rguid
0x18000cd76  call    cs:__imp_StringFromGUID2
0x18000cd7c  lea     rax, [rsp+3E0h+hKey]
0x18000cd81  mov     r9d, 20019h; samDesired
0x18000cd87  xor     r8d, r8d; ulOptions
0x18000cd8a  mov     [rsp+3E0h+phkResult], rax; phkResult
0x18000cd8f  lea     rdx, [rsp+3E0h+SubKey]; lpSubKey
0x18000cd94  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000cd9b  call    cs:__imp_RegOpenKeyExW
0x18000cda1  lea     r14, WPP_GLOBAL_Control
0x18000cda8  mov     sil, 10h
0x18000cdab  lea     rdi, WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids
0x18000cdb2  mov     ebx, eax
0x18000cdb4  test    eax, eax
0x18000cdb6  jnz     loc_18000CFDA
0x18000cdbc  mov     rcx, [rsp+3E0h+hKey]; hKey
0x18000cdc1  lea     rax, [rsp+3E0h+cbData]
0x18000cdc6  mov     [rsp+3E0h+lpcbData], rax; lpcbData
0x18000cdcb  lea     rdx, aCommandLine; "Command Line"
0x18000cdd2  lea     rax, [rbp+2E0h+Data]
0x18000cdd9  xor     r9d, r9d; lpType
0x18000cddc  xor     r8d, r8d; lpReserved
0x18000cddf  mov     [rsp+3E0h+phkResult], rax; lpData
0x18000cde4  call    cs:__imp_RegQueryValueExW
0x18000cdea  mov     r14d, [rsp+3E0h+cbData]
0x18000cdef  mov     ebx, eax
0x18000cdf1  shr     r14d, 1
0x18000cdf4  test    eax, eax
0x18000cdf6  jnz     loc_18000CE82
0x18000cdfc  test    r14d, r14d
0x18000cdff  jz      loc_18000CE90
0x18000ce05  mov     ecx, [rsp+3E0h+cbData]; cb
0x18000ce09  call    cs:__imp_CoTaskMemAlloc
0x18000ce0f  mov     [r15], rax
0x18000ce12  test    rax, rax
0x18000ce15  jz      short loc_18000CE39
0x18000ce17  mov     [rax], r13w
0x18000ce1b  lea     r8, [rbp+2E0h+Data]; unsigned __int16 *
0x18000ce22  mov     rcx, [r15]; unsigned __int16 *
0x18000ce25  mov     edx, r14d; unsigned __int64
0x18000ce28  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000ce2d  lea     r14, WPP_GLOBAL_Control
0x18000ce34  jmp     loc_18000CEC4
0x18000ce39  mov     ebx, 8
0x18000ce3e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ce45  lea     r14, WPP_GLOBAL_Control
0x18000ce4c  cmp     rcx, r14
0x18000ce4f  jz      loc_18000CF60
0x18000ce55  test    byte ptr [rcx+1Ch], 4
0x18000ce59  jz      loc_18000CF2B
0x18000ce5f  mov     rcx, [rcx+10h]
0x18000ce63  lea     edx, [rbx+5Dh]
0x18000ce66  lea     r9, [rbp+2E0h+Data]
0x18000ce6d  mov     dword ptr [rsp+3E0h+phkResult], 80070008h
0x18000ce75  mov     r8, rdi
0x18000ce78  call    WPP_SF_SD
0x18000ce7d  jmp     loc_18000CF24
0x18000ce82  cmp     eax, 2
0x18000ce85  jz      short loc_18000CE90
0x18000ce87  test    r14d, r14d
0x18000ce8a  jnz     loc_18000CF1D
0x18000ce90  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ce97  lea     r14, WPP_GLOBAL_Control
0x18000ce9e  cmp     rcx, r14
0x18000cea1  jz      short loc_18000CEC4
0x18000cea3  test    [rcx+1Ch], sil
0x18000cea7  jz      short loc_18000CEC4
0x18000cea9  mov     rcx, [rcx+10h]
0x18000cead  lea     r9, [rsp+3E0h+SubKey]
0x18000ceb2  mov     edx, 66h ; 'f'
0x18000ceb7  mov     dword ptr [rsp+3E0h+phkResult], r13d
0x18000cebc  mov     r8, rdi
0x18000cebf  call    WPP_SF_SD
0x18000cec4  mov     rcx, [rsp+3E0h+hKey]; hKey
0x18000cec9  lea     rax, [rsp+3E0h+cbData]
0x18000cece  mov     [rsp+3E0h+lpcbData], rax; lpcbData
0x18000ced3  lea     rdx, aUserFlags; "User Flags"
0x18000ceda  xor     r9d, r9d; lpType
0x18000cedd  mov     [rsp+3E0h+phkResult], r12; lpData
0x18000cee2  xor     r8d, r8d; lpReserved
0x18000cee5  mov     [rsp+3E0h+cbData], 4
0x18000ceed  call    cs:__imp_RegQueryValueExW
0x18000cef3  mov     ebx, eax
0x18000cef5  cmp     eax, 2
0x18000cef8  jnz     short loc_18000CF19
0x18000cefa  mov     ebx, r13d
0x18000cefd  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cf04  cmp     rcx, r14
0x18000cf07  jz      short loc_18000CF60
0x18000cf09  test    [rcx+1Ch], sil
0x18000cf0d  jz      short loc_18000CF60
0x18000cf0f  lea     edx, [rax+65h]
0x18000cf12  mov     dword ptr [rsp+3E0h+phkResult], r13d
0x18000cf17  jmp     short loc_18000CF4F
0x18000cf19  test    eax, eax
0x18000cf1b  jz      short loc_18000CF60
0x18000cf1d  lea     r14, WPP_GLOBAL_Control
0x18000cf24  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cf2b  cmp     rcx, r14
0x18000cf2e  jz      short loc_18000CF60
0x18000cf30  test    [rcx+1Ch], sil
0x18000cf34  jz      short loc_18000CF60
0x18000cf36  test    ebx, ebx
0x18000cf38  jg      short loc_18000CF3E
0x18000cf3a  mov     eax, ebx
0x18000cf3c  jmp     short loc_18000CF46
0x18000cf3e  movzx   eax, bx
0x18000cf41  or      eax, 80070000h
0x18000cf46  mov     edx, 68h ; 'h'
0x18000cf4b  mov     dword ptr [rsp+3E0h+phkResult], eax
0x18000cf4f  mov     rcx, [rcx+10h]
0x18000cf53  lea     r9, [rsp+3E0h+SubKey]
0x18000cf58  mov     r8, rdi
0x18000cf5b  call    WPP_SF_SD
0x18000cf60  mov     rcx, [rsp+3E0h+hKey]; hKey
0x18000cf65  call    cs:__imp_RegCloseKey
0x18000cf6b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cf72  test    ebx, ebx
0x18000cf74  jle     short loc_18000CF81
0x18000cf76  movzx   ebx, bx
0x18000cf79  or      ebx, 80070000h
0x18000cf7f  test    ebx, ebx
0x18000cf81  jns     short loc_18000CF96
0x18000cf83  mov     rcx, [r15]; pv
0x18000cf86  call    cs:__imp_CoTaskMemFree
0x18000cf8c  mov     [r15], r13
0x18000cf8f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cf96  cmp     rcx, r14
0x18000cf99  jz      short loc_18000CFB5
0x18000cf9b  test    [rcx+1Ch], sil
0x18000cf9f  jz      short loc_18000CFB5
0x18000cfa1  mov     rcx, [rcx+10h]
0x18000cfa5  mov     edx, 6Ah ; 'j'
0x18000cfaa  mov     r9d, ebx
0x18000cfad  mov     r8, rdi
0x18000cfb0  call    WPP_SF_d
0x18000cfb5  mov     eax, ebx
0x18000cfb7  mov     rcx, [rbp+2E0h+var_50]
0x18000cfbe  xor     rcx, rsp; StackCookie
0x18000cfc1  call    __security_check_cookie
0x18000cfc6  add     rsp, 3A8h
0x18000cfcd  pop     r15
0x18000cfcf  pop     r14
0x18000cfd1  pop     r13
0x18000cfd3  pop     r12
0x18000cfd5  pop     rdi
0x18000cfd6  pop     rsi
0x18000cfd7  pop     rbx
0x18000cfd8  pop     rbp
0x18000cfd9  retn
0x18000cfda  cmp     eax, 2
0x18000cfdd  jnz     short loc_18000CF6B
0x18000cfdf  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cfe6  lea     rdi, WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids
0x18000cfed  cmp     rcx, r14
0x18000cff0  jz      short loc_18000D01B
0x18000cff2  test    [rcx+1Ch], sil
0x18000cff6  jz      short loc_18000D01B
0x18000cff8  mov     rcx, [rcx+10h]
0x18000cffc  lea     edx, [rax+67h]
0x18000cfff  lea     r9, [rsp+3E0h+SubKey]
0x18000d004  mov     dword ptr [rsp+3E0h+phkResult], 80070002h
0x18000d00c  mov     r8, rdi
0x18000d00f  call    WPP_SF_SD
0x18000d014  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d01b  mov     ebx, r13d
0x18000d01e  jmp     loc_18000CF7F
```
