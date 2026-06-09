# DisableInterfaceUnconstrainedDnsLookup(_GUID const &,int)

- ea: `0x18001cfa8`
- end: `0x18001d1ee`
- name: `?DisableInterfaceUnconstrainedDnsLookup@@YAKAEBU_GUID@@H@Z`
- size: `582`
- prototype: `unsigned int __fastcall(GUID *rguid, int)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180060580`

## callees

- `0x1800137a0`
- `0x18001cfa8`
- `0x18001d1f4`
- `0x18001d2a0`
- `0x180049ba0`
- `0x180084f50`
- `0x180085bc4`
- `0x1800e6288`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18001d0b7`
- `ntdll!RtlNtStatusToDosError` at `0x18001d0b7`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18001d000`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18001d000`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x18001d031`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x18001d031`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x18001d0a6`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x18001d0a6`

## string_xrefs

- `0x18001d02a`: `Dnscache`
- `0x18001d023`: `SYSTEM\CurrentControlSet\Services\Dnscache\InterfaceSpecificParameters`

## pseudocode

```c
__int64 __fastcall DisableInterfaceUnconstrainedDnsLookup(GUID *rguid, int a2)
{
  NTSTATUS PersistedRegistryLocationW; // eax
  int v5; // edx
  ULONG v6; // ebx
  int v7; // r8d
  int v8; // r9d
  __int64 v9; // rcx
  ULONG v10; // eax
  __int64 v12; // rdx
  __int64 v13; // r9
  ULONG v14; // eax
  int v15; // [rsp+20h] [rbp-2C8h]
  unsigned int v16[4]; // [rsp+40h] [rbp-2A8h] BYREF
  OLECHAR sz[40]; // [rsp+50h] [rbp-298h] BYREF
  unsigned __int16 SubKey[264]; // [rsp+A0h] [rbp-248h] BYREF

  memset_0(SubKey, 0, 0x208u);
  memset_0(sz, 0, sizeof(sz));
  StringFromGUID2(rguid, sz, 39);
  v16[0] = 0;
  PersistedRegistryLocationW = GetPersistedRegistryLocationW(
                                 L"Dnscache",
                                 L"SYSTEM\\CurrentControlSet\\Services\\Dnscache\\InterfaceSpecificParameters",
                                 SubKey,
                                 520,
                                 v16);
  if ( PersistedRegistryLocationW < 0 )
  {
    v10 = RtlNtStatusToDosError(PersistedRegistryLocationW);
    v6 = v10;
    v9 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *(_BYTE *)(WPP_GLOBAL_Control + 25LL)
      && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 12, &WPP_6943d99de10d3e13072c2b067fe09511_Traceguids, v10);
      v9 = WPP_GLOBAL_Control;
    }
    if ( !v6 )
      goto LABEL_10;
  }
  else
  {
    v6 = StringCchPrintfW(&SubKey[(v16[0] >> 1) - 1], 260LL - ((v16[0] >> 1) - 1), L"\\%ws", sz);
    if ( (v6 & 0x1FFF0000) == 0x70000 )
      v6 = (unsigned __int16)v6;
    if ( v6 )
    {
      v9 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        return v6;
      if ( !*(_BYTE *)(WPP_GLOBAL_Control + 25LL) || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        goto LABEL_28;
      v12 = 13;
      v13 = v6;
      goto LABEL_27;
    }
    if ( !a2 )
    {
      RegDeleteKeyValueW(HKEY_LOCAL_MACHINE, SubKey, L"DisableUnConstrainedQueries");
LABEL_7:
      v9 = WPP_GLOBAL_Control;
LABEL_10:
      if ( (_UNKNOWN *)v9 != &WPP_GLOBAL_Control && *(_BYTE *)(v9 + 25) >= 4u && (*(_BYTE *)(v9 + 28) & 1) != 0 )
        WPP_SF_SD_guid_(*(_QWORD *)(v9 + 16), v5, v7, v8, a2, (__int64)rguid);
      return v6;
    }
    v14 = RegWriteDwordDataWithOptions(SubKey);
    v6 = v14;
    if ( !v14 )
      goto LABEL_7;
    v9 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return v6;
    if ( *(_BYTE *)(WPP_GLOBAL_Control + 25LL) && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      v12 = 14;
      v13 = v14;
LABEL_27:
      WPP_SF_d(*(_QWORD *)(v9 + 16), v12, &WPP_6943d99de10d3e13072c2b067fe09511_Traceguids, v13);
      v9 = WPP_GLOBAL_Control;
    }
  }
LABEL_28:
  if ( (_UNKNOWN *)v9 != &WPP_GLOBAL_Control && *(_BYTE *)(v9 + 25) >= 3u && (*(_BYTE *)(v9 + 28) & 1) != 0 )
    WPP_SF_DSD_guid_(*(_QWORD *)(v9 + 16), v5, v7, v6, v15, a2, (__int64)rguid);
  return v6;
}

```

## disassembly

```asm
0x18001cfa8  push    rbx
0x18001cfaa  push    rbp
0x18001cfab  push    rsi
0x18001cfac  push    rdi
0x18001cfad  sub     rsp, 2C8h
0x18001cfb4  mov     rax, cs:__security_cookie
0x18001cfbb  xor     rax, rsp
0x18001cfbe  mov     [rsp+2E8h+var_38], rax
0x18001cfc6  mov     edi, edx
0x18001cfc8  mov     rsi, rcx
0x18001cfcb  mov     ebx, 208h
0x18001cfd0  lea     rcx, [rsp+2E8h+SubKey]; void *
0x18001cfd8  mov     r8d, ebx; Size
0x18001cfdb  xor     edx, edx; Val
0x18001cfdd  call    memset_0
0x18001cfe2  xor     edx, edx; Val
0x18001cfe4  lea     rcx, [rsp+2E8h+sz]; void *
0x18001cfe9  lea     r8d, [rdx+50h]; Size
0x18001cfed  call    memset_0
0x18001cff2  mov     r8d, 27h ; '''; cchMax
0x18001cff8  lea     rdx, [rsp+2E8h+sz]; lpsz
0x18001cffd  mov     rcx, rsi; rguid
0x18001d000  call    cs:__imp_StringFromGUID2
0x18001d006  lea     rax, [rsp+2E8h+var_2A8]
0x18001d00b  mov     [rsp+2E8h+var_2A8], 0
0x18001d013  mov     r9d, ebx
0x18001d016  mov     [rsp+2E8h+var_2C8], rax
0x18001d01b  lea     r8, [rsp+2E8h+SubKey]
0x18001d023  lea     rdx, aSystemCurrentc_1; "SYSTEM\\CurrentControlSet\\Services\\Dn"...
0x18001d02a  lea     rcx, aDnscache; "Dnscache"
0x18001d031  call    cs:__imp_GetPersistedRegistryLocationW
0x18001d037  lea     rbp, WPP_GLOBAL_Control
0x18001d03e  test    eax, eax
0x18001d040  js      short loc_18001D0B5
0x18001d042  mov     eax, [rsp+2E8h+var_2A8]
0x18001d046  lea     rcx, [rsp+2E8h+SubKey]
0x18001d04e  shr     eax, 1
0x18001d050  lea     r9, [rsp+2E8h+sz]
0x18001d055  dec     eax
0x18001d057  lea     r8, aWs; "\\%ws"
0x18001d05e  mov     edx, 104h
0x18001d063  sub     rdx, rax; unsigned __int64
0x18001d066  lea     rcx, [rcx+rax*2]; unsigned __int16 *
0x18001d06a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001d06f  mov     ebx, eax
0x18001d071  and     eax, 1FFF0000h
0x18001d076  cmp     eax, 70000h
0x18001d07b  jnz     short loc_18001D080
0x18001d07d  movzx   ebx, bx
0x18001d080  test    ebx, ebx
0x18001d082  jnz     loc_18001D143
0x18001d088  test    edi, edi
0x18001d08a  jnz     loc_18001D165
0x18001d090  lea     r8, ValueName; "DisableUnConstrainedQueries"
0x18001d097  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001d09e  lea     rdx, [rsp+2E8h+SubKey]; lpSubKey
0x18001d0a6  call    cs:__imp_RegDeleteKeyValueW
0x18001d0ac  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d0b3  jmp     short loc_18001D0D3
0x18001d0b5  mov     ecx, eax; Status
0x18001d0b7  call    cs:__imp_RtlNtStatusToDosError
0x18001d0bd  mov     ebx, eax
0x18001d0bf  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d0c6  cmp     rcx, rbp
0x18001d0c9  jnz     short loc_18001D116
0x18001d0cb  test    ebx, ebx
0x18001d0cd  jnz     loc_18001D1B7
0x18001d0d3  cmp     rcx, rbp
0x18001d0d6  jnz     short loc_18001D0F6
0x18001d0d8  mov     eax, ebx
0x18001d0da  mov     rcx, [rsp+2E8h+var_38]
0x18001d0e2  xor     rcx, rsp; StackCookie
0x18001d0e5  call    __security_check_cookie
0x18001d0ea  add     rsp, 2C8h
0x18001d0f1  pop     rdi
0x18001d0f2  pop     rsi
0x18001d0f3  pop     rbp
0x18001d0f4  pop     rbx
0x18001d0f5  retn
0x18001d0f6  cmp     byte ptr [rcx+19h], 4
0x18001d0fa  jb      short loc_18001D0D8
0x18001d0fc  test    byte ptr [rcx+1Ch], 1
0x18001d100  jz      short loc_18001D0D8
0x18001d102  mov     rcx, [rcx+10h]
0x18001d106  mov     [rsp+2E8h+var_2C0], rsi
0x18001d10b  mov     dword ptr [rsp+2E8h+var_2C8], edi
0x18001d10f  call    WPP_SF_SD_guid_
0x18001d114  jmp     short loc_18001D0D8
0x18001d116  cmp     byte ptr [rcx+19h], 1
0x18001d11a  jb      short loc_18001D0CB
0x18001d11c  test    byte ptr [rcx+1Ch], 1
0x18001d120  jz      short loc_18001D0CB
0x18001d122  mov     rcx, [rcx+10h]
0x18001d126  lea     r8, WPP_6943d99de10d3e13072c2b067fe09511_Traceguids
0x18001d12d  mov     edx, 0Ch
0x18001d132  mov     r9d, ebx
0x18001d135  call    WPP_SF_d
0x18001d13a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d141  jmp     short loc_18001D0CB
0x18001d143  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d14a  cmp     rcx, rbp
0x18001d14d  jz      short loc_18001D0D8
0x18001d14f  cmp     byte ptr [rcx+19h], 1
0x18001d153  jb      short loc_18001D1B7
0x18001d155  test    byte ptr [rcx+1Ch], 1
0x18001d159  jz      short loc_18001D1B7
0x18001d15b  mov     edx, 0Dh
0x18001d160  mov     r9d, ebx
0x18001d163  jmp     short loc_18001D1A0
0x18001d165  lea     rcx, [rsp+2E8h+SubKey]; lpSubKey
0x18001d16d  call    RegWriteDwordDataWithOptions
0x18001d172  mov     ebx, eax
0x18001d174  test    eax, eax
0x18001d176  jz      loc_18001D0AC
0x18001d17c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d183  cmp     rcx, rbp
0x18001d186  jz      loc_18001D0D8
0x18001d18c  cmp     byte ptr [rcx+19h], 1
0x18001d190  jb      short loc_18001D1B7
0x18001d192  test    byte ptr [rcx+1Ch], 1
0x18001d196  jz      short loc_18001D1B7
0x18001d198  mov     edx, 0Eh
0x18001d19d  mov     r9d, eax
0x18001d1a0  mov     rcx, [rcx+10h]
0x18001d1a4  lea     r8, WPP_6943d99de10d3e13072c2b067fe09511_Traceguids
0x18001d1ab  call    WPP_SF_d
0x18001d1b0  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d1b7  cmp     rcx, rbp
0x18001d1ba  jz      loc_18001D0D8
0x18001d1c0  cmp     byte ptr [rcx+19h], 3
0x18001d1c4  jb      loc_18001D0D8
0x18001d1ca  test    byte ptr [rcx+1Ch], 1
0x18001d1ce  jz      loc_18001D0D8
0x18001d1d4  mov     rcx, [rcx+10h]
0x18001d1d8  mov     r9d, ebx
0x18001d1db  mov     [rsp+2E8h+var_2B8], rsi
0x18001d1e0  mov     dword ptr [rsp+2E8h+var_2C0], edi
0x18001d1e4  call    WPP_SF_DSD_guid_
0x18001d1e9  jmp     loc_18001D0D8
```
