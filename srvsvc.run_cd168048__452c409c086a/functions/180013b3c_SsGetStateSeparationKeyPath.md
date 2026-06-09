# SsGetStateSeparationKeyPath

- ea: `0x180013b3c`
- end: `0x180013d10`
- name: `SsGetStateSeparationKeyPath`
- size: `468`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180015500`

## callees

- `0x180005790`
- `0x180013b3c`
- `0x180020de8`

## import_xrefs

- `ntdll!RtlGetPersistedStateLocation` at `0x180013b83`
- `ntdll!RtlGetPersistedStateLocation` at `0x180013b83`
- `ntdll!RtlNtStatusToDosError` at `0x180013cf6`
- `ntdll!RtlNtStatusToDosError` at `0x180013cf6`

## string_xrefs

- `0x180013b68`: `\Registry\Machine\SYSTEM\CurrentControlSet\Services\LanmanServer`
- `0x180013c26`: `Shares\Security`

## pseudocode

```c
__int64 SsGetStateSeparationKeyPath()
{
  int PersistedStateLocation; // ebx
  _QWORD *v1; // r10
  __int64 v2; // rdx
  NTSTATUS v3; // ecx
  unsigned int v4; // ebx
  int v5; // eax
  NTSTATUS v6; // edi
  int v8; // [rsp+50h] [rbp+8h] BYREF

  v8 = 0;
  PersistedStateLocation = RtlGetPersistedStateLocation(
                             L"LanmanServer",
                             0,
                             L"\\Registry\\Machine\\SYSTEM\\CurrentControlSet\\Services\\LanmanServer",
                             0,
                             &dword_18005DBB4,
                             260,
                             &v8);
  if ( PersistedStateLocation < 0 )
  {
    v1 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0
      || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      goto LABEL_7;
    }
    v2 = 132;
LABEL_6:
    WPP_SF_d(v1[2], v2, WPP_6c51fa01af1134468f88fcdefbc326dc_Traceguids, (unsigned int)PersistedStateLocation);
LABEL_7:
    v3 = PersistedStateLocation;
    return RtlNtStatusToDosError(v3);
  }
  PersistedStateLocation = RtlStringCchPrintfW(&word_18005DDBC, 260, L"%ws\\%ws", &dword_18005DBB4, L"Shares");
  if ( PersistedStateLocation < 0 )
  {
    v1 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0
      || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      goto LABEL_7;
    }
    v2 = 133;
    goto LABEL_6;
  }
  PersistedStateLocation = RtlStringCchPrintfW(&word_18005DFC4, 260, L"%ws\\%ws", &dword_18005DBB4, L"Shares\\Security");
  if ( PersistedStateLocation < 0 )
  {
    v1 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0
      || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      goto LABEL_7;
    }
    v2 = 134;
    goto LABEL_6;
  }
  v4 = 0;
  v5 = RtlStringCchPrintfW(&word_18005E1CC, 260, L"%ws\\%ws", &dword_18005DBB4, L"Certs");
  v6 = v5;
  if ( v5 < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        135,
        WPP_6c51fa01af1134468f88fcdefbc326dc_Traceguids,
        (unsigned int)v5);
    }
    v3 = v6;
    return RtlNtStatusToDosError(v3);
  }
  return v4;
}

```

## disassembly

```asm
0x180013b3c  mov     r11, rsp
0x180013b3f  mov     [r11+10h], rbx
0x180013b43  mov     [r11+18h], rsi
0x180013b47  push    rdi
0x180013b48  sub     rsp, 40h
0x180013b4c  lea     rax, [r11+8]
0x180013b50  mov     [rsp+48h+arg_0], 0
0x180013b58  mov     [r11-18h], rax
0x180013b5c  lea     rsi, dword_18005DBB4
0x180013b63  mov     edi, 104h
0x180013b68  lea     r8, aRegistryMachin_2; "\\Registry\\Machine\\SYSTEM\\CurrentCon"...
0x180013b6f  mov     [rsp+48h+var_20], edi
0x180013b73  lea     rcx, Path; "LanmanServer"
0x180013b7a  xor     r9d, r9d
0x180013b7d  mov     [r11-28h], rsi
0x180013b81  xor     edx, edx
0x180013b83  call    cs:__imp_RtlGetPersistedStateLocation
0x180013b89  mov     ebx, eax
0x180013b8b  test    eax, eax
0x180013b8d  jns     short loc_180013BD0
0x180013b8f  mov     r10, cs:WPP_GLOBAL_Control
0x180013b96  lea     rcx, WPP_GLOBAL_Control
0x180013b9d  cmp     r10, rcx
0x180013ba0  jz      short loc_180013BC9
0x180013ba2  test    dword ptr [r10+1Ch], 100h
0x180013baa  jz      short loc_180013BC9
0x180013bac  cmp     byte ptr [r10+19h], 1
0x180013bb1  jb      short loc_180013BC9
0x180013bb3  lea     edx, [rdi-80h]
0x180013bb6  mov     rcx, [r10+10h]
0x180013bba  lea     r8, WPP_6c51fa01af1134468f88fcdefbc326dc_Traceguids
0x180013bc1  mov     r9d, ebx
0x180013bc4  call    WPP_SF_d
0x180013bc9  mov     ecx, ebx
0x180013bcb  jmp     loc_180013CF6
0x180013bd0  lea     rax, aShares; "Shares"
0x180013bd7  mov     r9, rsi
0x180013bda  lea     r8, aWsWs_0; "%ws\\%ws"
0x180013be1  mov     [rsp+48h+var_28], rax
0x180013be6  mov     rdx, rdi
0x180013be9  lea     rcx, word_18005DDBC
0x180013bf0  call    RtlStringCchPrintfW
0x180013bf5  mov     ebx, eax
0x180013bf7  test    eax, eax
0x180013bf9  jns     short loc_180013C26
0x180013bfb  mov     r10, cs:WPP_GLOBAL_Control
0x180013c02  lea     rcx, WPP_GLOBAL_Control
0x180013c09  cmp     r10, rcx
0x180013c0c  jz      short loc_180013BC9
0x180013c0e  test    dword ptr [r10+1Ch], 100h
0x180013c16  jz      short loc_180013BC9
0x180013c18  cmp     byte ptr [r10+19h], 1
0x180013c1d  jb      short loc_180013BC9
0x180013c1f  mov     edx, 85h
0x180013c24  jmp     short loc_180013BB6
0x180013c26  lea     rax, aSharesSecurity; "Shares\\Security"
0x180013c2d  mov     r9, rsi
0x180013c30  lea     r8, aWsWs_0; "%ws\\%ws"
0x180013c37  mov     [rsp+48h+var_28], rax
0x180013c3c  mov     rdx, rdi
0x180013c3f  lea     rcx, word_18005DFC4
0x180013c46  call    RtlStringCchPrintfW
0x180013c4b  mov     ebx, eax
0x180013c4d  test    eax, eax
0x180013c4f  jns     short loc_180013C8B
0x180013c51  mov     r10, cs:WPP_GLOBAL_Control
0x180013c58  lea     rcx, WPP_GLOBAL_Control
0x180013c5f  cmp     r10, rcx
0x180013c62  jz      loc_180013BC9
0x180013c68  test    dword ptr [r10+1Ch], 100h
0x180013c70  jz      loc_180013BC9
0x180013c76  cmp     byte ptr [r10+19h], 1
0x180013c7b  jb      loc_180013BC9
0x180013c81  mov     edx, 86h
0x180013c86  jmp     loc_180013BB6
0x180013c8b  lea     rax, aCerts; "Certs"
0x180013c92  mov     r9, rsi
0x180013c95  lea     r8, aWsWs_0; "%ws\\%ws"
0x180013c9c  mov     [rsp+48h+var_28], rax
0x180013ca1  mov     rdx, rdi
0x180013ca4  lea     rcx, word_18005E1CC
0x180013cab  xor     ebx, ebx
0x180013cad  call    RtlStringCchPrintfW
0x180013cb2  mov     edi, eax
0x180013cb4  test    eax, eax
0x180013cb6  jns     short loc_180013CFE
0x180013cb8  mov     r10, cs:WPP_GLOBAL_Control
0x180013cbf  lea     rcx, WPP_GLOBAL_Control
0x180013cc6  cmp     r10, rcx
0x180013cc9  jz      short loc_180013CF4
0x180013ccb  test    dword ptr [r10+1Ch], 100h
0x180013cd3  jz      short loc_180013CF4
0x180013cd5  cmp     byte ptr [r10+19h], 1
0x180013cda  jb      short loc_180013CF4
0x180013cdc  mov     rcx, [r10+10h]
0x180013ce0  lea     r8, WPP_6c51fa01af1134468f88fcdefbc326dc_Traceguids
0x180013ce7  mov     edx, 87h
0x180013cec  mov     r9d, eax
0x180013cef  call    WPP_SF_d
0x180013cf4  mov     ecx, edi; Status
0x180013cf6  call    cs:__imp_RtlNtStatusToDosError
0x180013cfc  mov     ebx, eax
0x180013cfe  mov     rsi, [rsp+48h+arg_10]
0x180013d03  mov     eax, ebx
0x180013d05  mov     rbx, [rsp+48h+arg_8]
0x180013d0a  add     rsp, 40h
0x180013d0e  pop     rdi
0x180013d0f  retn
```
