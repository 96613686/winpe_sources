# SsSaveSrvComment

- ea: `0x180026220`
- end: `0x18002651d`
- name: `SsSaveSrvComment`
- size: `765`
- prototype: `__int64 __fastcall(BYTE *lpData)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180024db8`

## callees

- `0x180020de8`
- `0x1800215e8`
- `0x180026220`
- `0x180026958`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18002640a`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18002640a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800264a7`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800264a7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180026501`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180026501`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002642d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002642d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002632c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002632c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800264f1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800264f1`
- `ntdll!RtlGetPersistedStateLocation` at `0x1800262ce`
- `ntdll!RtlGetPersistedStateLocation` at `0x18002639a`
- `ntdll!RtlGetPersistedStateLocation` at `0x1800262ce`
- `ntdll!RtlGetPersistedStateLocation` at `0x18002639a`
- `ntdll!RtlNtStatusToDosError` at `0x180026316`
- `ntdll!RtlNtStatusToDosError` at `0x1800263df`
- `ntdll!RtlNtStatusToDosError` at `0x180026316`
- `ntdll!RtlNtStatusToDosError` at `0x1800263df`

## string_xrefs

- `0x18002648e`: `srvcomment`
- `0x1800262b4`: `SYSTEM\CurrentControlSet\Services\LanmanServer\Parameters`
- `0x180026379`: `SYSTEM\CurrentControlSet\Services\LanmanServer\Parameters`

## pseudocode

```c
__int64 __fastcall SsSaveSrvComment(BYTE *lpData)
{
  __int64 v1; // rsi
  __int64 v3; // rax
  unsigned int PersistedStateLocation; // ebx
  ULONG v6; // ebx
  WCHAR *v7; // rbp
  __int64 v8; // r8
  NTSTATUS v9; // ebx
  _QWORD *v10; // rcx
  int v11; // edx
  int v12; // r9d
  DWORD cbData; // esi
  SIZE_T uBytes; // [rsp+70h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+78h] [rbp+10h] BYREF

  v1 = -1;
  LODWORD(uBytes) = 0;
  hKey = 0;
  if ( lpData )
  {
    v3 = -1;
    do
      ++v3;
    while ( *(_WORD *)&lpData[2 * v3] );
    if ( (unsigned int)v3 > 0x100 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
      {
        if ( *((_BYTE *)WPP_GLOBAL_Control + 25) )
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            117,
            (unsigned int)WPP_6c51fa01af1134468f88fcdefbc326dc_Traceguids,
            (_DWORD)lpData,
            0);
      }
      return 87;
    }
  }
  PersistedStateLocation = RtlGetPersistedStateLocation(
                             L"SrvParameters",
                             0,
                             L"SYSTEM\\CurrentControlSet\\Services\\LanmanServer\\Parameters",
                             0,
                             0,
                             0,
                             &uBytes);
  if ( PersistedStateLocation == -2147483643 )
  {
    v7 = (WCHAR *)LocalAlloc(0x40u, (unsigned int)uBytes);
    if ( !v7 )
    {
      PersistedStateLocation = -1073741670;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        WPP_SF_Ld(*((_QWORD *)WPP_GLOBAL_Control + 2), 119, v8, (unsigned int)uBytes, -1073741670);
      }
      goto LABEL_15;
    }
    v9 = RtlGetPersistedStateLocation(
           L"SrvParameters",
           0,
           L"SYSTEM\\CurrentControlSet\\Services\\LanmanServer\\Parameters",
           0,
           v7,
           uBytes,
           0);
    if ( v9 < 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          120,
          WPP_6c51fa01af1134468f88fcdefbc326dc_Traceguids,
          (unsigned int)v9);
      }
      v6 = RtlNtStatusToDosError(v9);
      goto LABEL_45;
    }
    if ( lpData )
      _o_wcscpy_s(word_18005D560, 257);
    else
      word_18005D560[0] = 0;
    v6 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v7, 0, 0x20006u, &hKey);
    if ( v6 )
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0
        || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        goto LABEL_45;
      }
      v11 = 121;
      v12 = (int)v7;
    }
    else
    {
      if ( lpData )
      {
        do
          ++v1;
        while ( *(_WORD *)&lpData[2 * v1] );
        cbData = 2 * v1 + 2;
      }
      else
      {
        cbData = 0;
      }
      v6 = RegSetValueExW(hKey, L"srvcomment", 0, 1u, lpData, cbData);
      if ( !v6 )
        goto LABEL_45;
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0
        || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        goto LABEL_45;
      }
      v11 = 122;
      v12 = (int)lpData;
    }
    WPP_SF_Sd(v10[2], v11, (unsigned int)WPP_6c51fa01af1134468f88fcdefbc326dc_Traceguids, v12, v6);
LABEL_45:
    LocalFree(v7);
    goto LABEL_46;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      118,
      WPP_6c51fa01af1134468f88fcdefbc326dc_Traceguids,
      PersistedStateLocation);
  }
LABEL_15:
  v6 = RtlNtStatusToDosError(PersistedStateLocation);
LABEL_46:
  if ( hKey )
    RegCloseKey(hKey);
  return v6;
}

```

## disassembly

```asm
0x180026220  mov     [rsp+arg_10], rbx
0x180026225  push    rbp
0x180026226  push    rsi
0x180026227  push    rdi
0x180026228  push    r14
0x18002622a  push    r15
0x18002622c  sub     rsp, 40h
0x180026230  xor     r14d, r14d
0x180026233  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180026237  mov     dword ptr [rsp+68h+uBytes], r14d
0x18002623c  mov     rdi, rcx
0x18002623f  mov     [rsp+68h+hKey], r14
0x180026244  mov     r15d, 100h
0x18002624a  test    rcx, rcx
0x18002624d  jz      short loc_1800262A7
0x18002624f  mov     rax, rsi
0x180026252  inc     rax
0x180026255  cmp     [rcx+rax*2], r14w
0x18002625a  jnz     short loc_180026252
0x18002625c  cmp     eax, r15d
0x18002625f  jbe     short loc_1800262A7
0x180026261  mov     rcx, cs:WPP_GLOBAL_Control
0x180026268  lea     rax, WPP_GLOBAL_Control
0x18002626f  cmp     rcx, rax
0x180026272  jz      short loc_18002629D
0x180026274  test    [rcx+1Ch], r15d
0x180026278  jz      short loc_18002629D
0x18002627a  cmp     byte ptr [rcx+19h], 1
0x18002627e  jb      short loc_18002629D
0x180026280  mov     rcx, [rcx+10h]
0x180026284  lea     r8, WPP_6c51fa01af1134468f88fcdefbc326dc_Traceguids
0x18002628b  mov     edx, 75h ; 'u'
0x180026290  mov     dword ptr [rsp+68h+phkResult], r15d
0x180026295  mov     r9, rdi
0x180026298  call    WPP_SF_Sd
0x18002629d  mov     eax, 57h ; 'W'
0x1800262a2  jmp     loc_180026509
0x1800262a7  lea     rax, [rsp+68h+uBytes]
0x1800262ac  xor     r9d, r9d
0x1800262af  mov     [rsp+68h+var_38], rax
0x1800262b4  lea     r8, SubKey; "SYSTEM\\CurrentControlSet\\Services\\La"...
0x1800262bb  mov     [rsp+68h+cbData], r14d
0x1800262c0  lea     rcx, aSrvparameters; "SrvParameters"
0x1800262c7  xor     edx, edx
0x1800262c9  mov     [rsp+68h+phkResult], r14
0x1800262ce  call    cs:__imp_RtlGetPersistedStateLocation
0x1800262d4  mov     ebx, eax
0x1800262d6  cmp     eax, 80000005h
0x1800262db  jz      short loc_180026323
0x1800262dd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800262e4  lea     rax, WPP_GLOBAL_Control
0x1800262eb  cmp     rcx, rax
0x1800262ee  jz      short loc_180026314
0x1800262f0  test    [rcx+1Ch], r15d
0x1800262f4  jz      short loc_180026314
0x1800262f6  cmp     byte ptr [rcx+19h], 1
0x1800262fa  jb      short loc_180026314
0x1800262fc  mov     rcx, [rcx+10h]
0x180026300  lea     r8, WPP_6c51fa01af1134468f88fcdefbc326dc_Traceguids
0x180026307  mov     edx, 76h ; 'v'
0x18002630c  mov     r9d, ebx
0x18002630f  call    WPP_SF_d
0x180026314  mov     ecx, ebx; Status
0x180026316  call    cs:__imp_RtlNtStatusToDosError
0x18002631c  mov     ebx, eax
0x18002631e  jmp     loc_1800264F7
0x180026323  mov     edx, dword ptr [rsp+68h+uBytes]; uBytes
0x180026327  mov     ecx, 40h ; '@'; uFlags
0x18002632c  call    cs:__imp_LocalAlloc
0x180026332  mov     rbp, rax
0x180026335  test    rax, rax
0x180026338  jnz     short loc_180026375
0x18002633a  mov     rcx, cs:WPP_GLOBAL_Control
0x180026341  lea     rax, WPP_GLOBAL_Control
0x180026348  mov     ebx, 0C000009Ah
0x18002634d  cmp     rcx, rax
0x180026350  jz      short loc_180026314
0x180026352  test    [rcx+1Ch], r15d
0x180026356  jz      short loc_180026314
0x180026358  cmp     byte ptr [rcx+19h], 1
0x18002635c  jb      short loc_180026314
0x18002635e  mov     r9d, dword ptr [rsp+68h+uBytes]
0x180026363  lea     edx, [rbp+77h]
0x180026366  mov     rcx, [rcx+10h]
0x18002636a  mov     dword ptr [rsp+68h+phkResult], ebx
0x18002636e  call    WPP_SF_Ld
0x180026373  jmp     short loc_180026314
0x180026375  mov     eax, dword ptr [rsp+68h+uBytes]
0x180026379  lea     r8, SubKey; "SYSTEM\\CurrentControlSet\\Services\\La"...
0x180026380  mov     [rsp+68h+var_38], r14
0x180026385  lea     rcx, aSrvparameters; "SrvParameters"
0x18002638c  mov     [rsp+68h+cbData], eax
0x180026390  xor     r9d, r9d
0x180026393  xor     edx, edx
0x180026395  mov     [rsp+68h+phkResult], rbp
0x18002639a  call    cs:__imp_RtlGetPersistedStateLocation
0x1800263a0  mov     ebx, eax
0x1800263a2  test    eax, eax
0x1800263a4  jns     short loc_1800263EC
0x1800263a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800263ad  lea     rax, WPP_GLOBAL_Control
0x1800263b4  cmp     rcx, rax
0x1800263b7  jz      short loc_1800263DD
0x1800263b9  test    [rcx+1Ch], r15d
0x1800263bd  jz      short loc_1800263DD
0x1800263bf  cmp     byte ptr [rcx+19h], 1
0x1800263c3  jb      short loc_1800263DD
0x1800263c5  mov     rcx, [rcx+10h]
0x1800263c9  lea     r8, WPP_6c51fa01af1134468f88fcdefbc326dc_Traceguids
0x1800263d0  mov     edx, 78h ; 'x'
0x1800263d5  mov     r9d, ebx
0x1800263d8  call    WPP_SF_d
0x1800263dd  mov     ecx, ebx; Status
0x1800263df  call    cs:__imp_RtlNtStatusToDosError
0x1800263e5  mov     ebx, eax
0x1800263e7  jmp     loc_1800264EE
0x1800263ec  test    rdi, rdi
0x1800263ef  jnz     short loc_1800263FB
0x1800263f1  mov     cs:word_18005D560, r14w
0x1800263f9  jmp     short loc_180026410
0x1800263fb  mov     r8, rdi
0x1800263fe  lea     rcx, word_18005D560
0x180026405  mov     edx, 101h
0x18002640a  call    cs:__imp__o_wcscpy_s
0x180026410  lea     rax, [rsp+68h+hKey]
0x180026415  mov     r9d, 20006h; samDesired
0x18002641b  xor     r8d, r8d; ulOptions
0x18002641e  mov     [rsp+68h+phkResult], rax; phkResult
0x180026423  mov     rdx, rbp; lpSubKey
0x180026426  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002642d  call    cs:__imp_RegOpenKeyExW
0x180026433  mov     ebx, eax
0x180026435  test    eax, eax
0x180026437  jz      short loc_18002646E
0x180026439  mov     rcx, cs:WPP_GLOBAL_Control
0x180026440  lea     rax, WPP_GLOBAL_Control
0x180026447  cmp     rcx, rax
0x18002644a  jz      loc_1800264EE
0x180026450  test    [rcx+1Ch], r15d
0x180026454  jz      loc_1800264EE
0x18002645a  cmp     byte ptr [rcx+19h], 1
0x18002645e  jb      loc_1800264EE
0x180026464  mov     edx, 79h ; 'y'
0x180026469  mov     r9, rbp
0x18002646c  jmp     short loc_1800264DA
0x18002646e  test    rdi, rdi
0x180026471  jnz     short loc_180026478
0x180026473  mov     esi, r14d
0x180026476  jmp     short loc_180026489
0x180026478  inc     rsi
0x18002647b  cmp     [rdi+rsi*2], r14w
0x180026480  jnz     short loc_180026478
0x180026482  lea     esi, ds:2[rsi*2]
0x180026489  mov     rcx, [rsp+68h+hKey]; hKey
0x18002648e  lea     rdx, aSrvcomment; "srvcomment"
0x180026495  mov     [rsp+68h+cbData], esi; cbData
0x180026499  mov     r9d, 1; dwType
0x18002649f  xor     r8d, r8d; Reserved
0x1800264a2  mov     [rsp+68h+phkResult], rdi; lpData
0x1800264a7  call    cs:__imp_RegSetValueExW
0x1800264ad  mov     ebx, eax
0x1800264af  test    eax, eax
0x1800264b1  jz      short loc_1800264EE
0x1800264b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800264ba  lea     rax, WPP_GLOBAL_Control
0x1800264c1  cmp     rcx, rax
0x1800264c4  jz      short loc_1800264EE
0x1800264c6  test    [rcx+1Ch], r15d
0x1800264ca  jz      short loc_1800264EE
0x1800264cc  cmp     byte ptr [rcx+19h], 1
0x1800264d0  jb      short loc_1800264EE
0x1800264d2  mov     edx, 7Ah ; 'z'
0x1800264d7  mov     r9, rdi
0x1800264da  mov     rcx, [rcx+10h]
0x1800264de  lea     r8, WPP_6c51fa01af1134468f88fcdefbc326dc_Traceguids
0x1800264e5  mov     dword ptr [rsp+68h+phkResult], ebx
0x1800264e9  call    WPP_SF_Sd
0x1800264ee  mov     rcx, rbp; hMem
0x1800264f1  call    cs:__imp_LocalFree
0x1800264f7  mov     rcx, [rsp+68h+hKey]; hKey
0x1800264fc  test    rcx, rcx
0x1800264ff  jz      short loc_180026507
0x180026501  call    cs:__imp_RegCloseKey
0x180026507  mov     eax, ebx
0x180026509  mov     rbx, [rsp+68h+arg_10]
0x180026511  add     rsp, 40h
0x180026515  pop     r15
0x180026517  pop     r14
0x180026519  pop     rdi
0x18002651a  pop     rsi
0x18002651b  pop     rbp
0x18002651c  retn
```
