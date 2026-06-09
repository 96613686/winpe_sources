# ScOpenSecurityKey(HKEY__ *,ulong,int,HKEY__ * *)

- ea: `0x140015ba4`
- end: `0x140015de7`
- name: `?ScOpenSecurityKey@@YAKPEAUHKEY__@@KHPEAPEAU1@@Z`
- size: `579`
- prototype: `unsigned int __fastcall(HKEY, unsigned int, int, HKEY *)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140015900`
- `0x14007b0e8`

## callees

- `0x140003e54`
- `0x140004c58`
- `0x14000bcc4`
- `0x140015ba4`
- `0x140016318`
- `0x140016664`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x140015cf3`
- `ntdll!RtlNtStatusToDosError` at `0x140015cf3`
- `ntdll!RtlSetControlSecurityDescriptor` at `0x140015c58`
- `ntdll!RtlSetControlSecurityDescriptor` at `0x140015c58`
- `ntdll!RtlDeleteSecurityObject` at `0x140015cb6`
- `ntdll!RtlDeleteSecurityObject` at `0x140015dba`
- `ntdll!RtlDeleteSecurityObject` at `0x140015cb6`
- `ntdll!RtlDeleteSecurityObject` at `0x140015dba`

## string_xrefs

- `0x140015c6c`: `Security`
- `0x140015d03`: `Security`
- `0x140015d44`: `Security`

## pseudocode

```c
ULONG __fastcall ScOpenSecurityKey(HKEY a1, ACCESS_MASK a2, __int64 a3, HKEY *a4)
{
  int v7; // eax
  NTSTATUS v8; // ebx
  NTSTATUS v9; // eax
  __int64 v10; // r8
  const unsigned __int16 *v11; // r9
  int v12; // ebx
  PRPC_ASYNC_STATE v14; // rcx
  int v15; // edx
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+50h] [rbp+7h] BYREF
  struct _SECURITY_ATTRIBUTES v17; // [rsp+58h] [rbp+Fh] BYREF
  __int16 v18; // [rsp+70h] [rbp+27h] BYREF
  char v19; // [rsp+72h] [rbp+29h]
  int v20; // [rsp+74h] [rbp+2Bh]
  PSID *v21; // [rsp+78h] [rbp+2Fh]
  __int16 v22; // [rsp+80h] [rbp+37h]
  char v23; // [rsp+82h] [rbp+39h]
  int v24; // [rsp+84h] [rbp+3Bh]
  __int64 *v25; // [rsp+88h] [rbp+3Fh]
  unsigned int v26; // [rsp+C0h] [rbp+77h] BYREF

  v26 = 0;
  v21 = &LocalSystemSid;
  *(&v17.nLength + 1) = 0;
  *(&v17.bInheritHandle + 1) = 0;
  v25 = &AliasAdminsSid;
  SecurityDescriptor = 0;
  v18 = 512;
  v19 = 0;
  v20 = 0x10000000;
  v22 = 512;
  v23 = 0;
  v24 = 0x10000000;
  if ( (_DWORD)a3 )
  {
    v7 = ScCreateAndSetSD((__int64)&v18, 2u, LocalSystemSid, LocalSystemSid, (struct _ACL **)&SecurityDescriptor);
    v8 = v7;
    if ( v7 < 0 )
    {
      if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
        WPP_SF_d(WPP_GLOBAL_Control->StubInfo, 160, WPP_e5a68143c9d03da933de77b1bc511594_Traceguids, (unsigned int)v7);
    }
    else
    {
      v9 = RtlSetControlSecurityDescriptor(SecurityDescriptor, 0x1000u, 0x1000u);
      v8 = v9;
      if ( v9 >= 0 )
      {
        v17.lpSecurityDescriptor = SecurityDescriptor;
        v17.nLength = 24;
        v17.bInheritHandle = 0;
        v12 = ScRegCreateKeyExW(a1, L"Security", v10, v11, 0, a2, &v17, a4, &v26);
        RtlDeleteSecurityObject(&SecurityDescriptor);
        if ( !v12 )
          return 0;
        v14 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
          || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) == 0 )
        {
          return v12;
        }
        v15 = 162;
        goto LABEL_12;
      }
      if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
        WPP_SF_d(WPP_GLOBAL_Control->StubInfo, 161, WPP_e5a68143c9d03da933de77b1bc511594_Traceguids, (unsigned int)v9);
      RtlDeleteSecurityObject(&SecurityDescriptor);
    }
    return RtlNtStatusToDosError(v8);
  }
  v12 = ScRegOpenKeyExW(a1, L"Security", a3, a2, a4);
  if ( (v12 & 0xFFFFFFFD) == 0 )
    return v12;
  v14 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 4) == 0 )
    return v12;
  v15 = 159;
LABEL_12:
  WPP_SF_Sd(
    v14->StubInfo,
    v15,
    (unsigned int)WPP_e5a68143c9d03da933de77b1bc511594_Traceguids,
    (unsigned int)L"Security",
    v12);
  return v12;
}

```

## disassembly

```asm
0x140015ba4  mov     [rsp-8+arg_0], rbx
0x140015ba9  mov     [rsp-8+arg_8], rsi
0x140015bae  push    rbp
0x140015baf  push    rdi
0x140015bb0  push    r14
0x140015bb2  lea     rbp, [rsp-47h]
0x140015bb7  sub     rsp, 90h
0x140015bbe  mov     [rbp+57h+arg_10], 0
0x140015bc5  lea     rax, LocalSystemSid
0x140015bcc  mov     [rbp+57h+var_28], rax
0x140015bd0  mov     r14, rcx
0x140015bd3  mov     dword ptr [rbp+57h+var_48+4], 0
0x140015bda  mov     ecx, 10000000h
0x140015bdf  mov     dword ptr [rbp+57h+var_48+14h], 0
0x140015be6  lea     rax, AliasAdminsSid
0x140015bed  mov     [rbp+57h+var_18], rax
0x140015bf1  mov     rdi, r9
0x140015bf4  mov     [rbp+57h+SecurityDescriptor], 0
0x140015bfc  mov     esi, edx
0x140015bfe  mov     [rbp+57h+var_30], 200h
0x140015c04  mov     [rbp+57h+var_2E], 0
0x140015c08  mov     [rbp+57h+var_2C], ecx
0x140015c0b  mov     [rbp+57h+var_20], 200h
0x140015c11  mov     [rbp+57h+var_1E], 0
0x140015c15  mov     [rbp+57h+var_1C], ecx
0x140015c18  test    r8d, r8d
0x140015c1b  jz      loc_140015CFB
0x140015c21  mov     r8, cs:LocalSystemSid
0x140015c28  lea     rax, [rbp+57h+SecurityDescriptor]
0x140015c2c  mov     r9, r8
0x140015c2f  mov     [rsp+0A0h+var_80], rax
0x140015c34  mov     edx, 2
0x140015c39  lea     rcx, [rbp+57h+var_30]
0x140015c3d  call    ScCreateAndSetSD
0x140015c42  mov     ebx, eax
0x140015c44  test    eax, eax
0x140015c46  js      loc_140015CDE
0x140015c4c  mov     rcx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x140015c50  mov     edx, 1000h; ControlBitsOfInterest
0x140015c55  mov     r8d, edx; ControlBitsToSet
0x140015c58  call    cs:__imp_RtlSetControlSecurityDescriptor
0x140015c5e  mov     ebx, eax
0x140015c60  test    eax, eax
0x140015c62  js      loc_140015D85
0x140015c68  mov     rax, [rbp+57h+SecurityDescriptor]
0x140015c6c  lea     rdx, aSecurity; "Security"
0x140015c73  mov     [rbp+57h+var_48.lpSecurityDescriptor], rax
0x140015c77  mov     rcx, r14; HKEY
0x140015c7a  lea     rax, [rbp+57h+arg_10]
0x140015c7e  mov     [rbp+57h+var_48.nLength], 18h
0x140015c85  mov     [rsp+0A0h+var_60], rax; unsigned int *
0x140015c8a  lea     rax, [rbp+57h+var_48]
0x140015c8e  mov     [rsp+0A0h+var_68], rdi; HKEY *
0x140015c93  mov     [rsp+0A0h+var_70], rax; struct _SECURITY_ATTRIBUTES *
0x140015c98  mov     [rsp+0A0h+var_78], esi; unsigned int
0x140015c9c  mov     dword ptr [rsp+0A0h+var_80], 0; unsigned int
0x140015ca4  mov     [rbp+57h+var_48.bInheritHandle], 0
0x140015cab  call    ?ScRegCreateKeyExW@@YAKPEAUHKEY__@@PEBGK1KKPEAU_SECURITY_ATTRIBUTES@@PEAPEAU1@PEAK@Z; ScRegCreateKeyExW(HKEY__ *,ushort const *,ulong,ushort const *,ulong,ulong,_SECURITY_ATTRIBUTES *,HKEY__ * *,ulong *)
0x140015cb0  lea     rcx, [rbp+57h+SecurityDescriptor]; ObjectDescriptor
0x140015cb4  mov     ebx, eax
0x140015cb6  call    cs:__imp_RtlDeleteSecurityObject
0x140015cbc  test    ebx, ebx
0x140015cbe  jnz     loc_140015DC5
0x140015cc4  xor     eax, eax
0x140015cc6  lea     r11, [rsp+0A0h+var_10]
0x140015cce  mov     rbx, [r11+20h]
0x140015cd2  mov     rsi, [r11+28h]
0x140015cd6  mov     rsp, r11
0x140015cd9  pop     r14
0x140015cdb  pop     rdi
0x140015cdc  pop     rbp
0x140015cdd  retn
0x140015cde  mov     rcx, cs:WPP_GLOBAL_Control
0x140015ce5  lea     rdx, WPP_GLOBAL_Control
0x140015cec  cmp     rcx, rdx
0x140015cef  jnz     short loc_140015D62
0x140015cf1  mov     ecx, ebx; Status
0x140015cf3  call    cs:__imp_RtlNtStatusToDosError
0x140015cf9  jmp     short loc_140015CC6
0x140015cfb  mov     r9d, esi; unsigned int
0x140015cfe  mov     [rsp+0A0h+var_80], rdi; HKEY *
0x140015d03  lea     rdx, aSecurity; "Security"
0x140015d0a  mov     rcx, r14; HKEY
0x140015d0d  call    ?ScRegOpenKeyExW@@YAKPEAUHKEY__@@PEBGKKPEAPEAU1@@Z; ScRegOpenKeyExW(HKEY__ *,ushort const *,ulong,ulong,HKEY__ * *)
0x140015d12  mov     ebx, eax
0x140015d14  test    eax, 0FFFFFFFDh
0x140015d19  jz      short loc_140015D5B
0x140015d1b  mov     rcx, cs:WPP_GLOBAL_Control
0x140015d22  lea     rdx, WPP_GLOBAL_Control
0x140015d29  cmp     rcx, rdx
0x140015d2c  jz      short loc_140015D5B
0x140015d2e  test    byte ptr [rcx+1Ch], 4
0x140015d32  jz      short loc_140015D5B
0x140015d34  mov     edx, 9Fh
0x140015d39  jmp     short loc_140015D40
0x140015d3b  mov     edx, 0A2h
0x140015d40  mov     rcx, [rcx+10h]
0x140015d44  lea     r9, aSecurity; "Security"
0x140015d4b  lea     r8, WPP_e5a68143c9d03da933de77b1bc511594_Traceguids
0x140015d52  mov     dword ptr [rsp+0A0h+var_80], ebx
0x140015d56  call    WPP_SF_Sd
0x140015d5b  mov     eax, ebx
0x140015d5d  jmp     loc_140015CC6
0x140015d62  test    byte ptr [rcx+1Ch], 1
0x140015d66  jz      short loc_140015CF1
0x140015d68  mov     rcx, [rcx+10h]
0x140015d6c  lea     r8, WPP_e5a68143c9d03da933de77b1bc511594_Traceguids
0x140015d73  mov     edx, 0A0h
0x140015d78  mov     r9d, ebx
0x140015d7b  call    WPP_SF_d
0x140015d80  jmp     loc_140015CF1
0x140015d85  mov     rcx, cs:WPP_GLOBAL_Control
0x140015d8c  lea     rdx, WPP_GLOBAL_Control
0x140015d93  cmp     rcx, rdx
0x140015d96  jz      short loc_140015DB6
0x140015d98  test    byte ptr [rcx+1Ch], 1
0x140015d9c  jz      short loc_140015DB6
0x140015d9e  mov     rcx, [rcx+10h]
0x140015da2  lea     r8, WPP_e5a68143c9d03da933de77b1bc511594_Traceguids
0x140015da9  mov     edx, 0A1h
0x140015dae  mov     r9d, ebx
0x140015db1  call    WPP_SF_d
0x140015db6  lea     rcx, [rbp+57h+SecurityDescriptor]; ObjectDescriptor
0x140015dba  call    cs:__imp_RtlDeleteSecurityObject
0x140015dc0  jmp     loc_140015CF1
0x140015dc5  mov     rcx, cs:WPP_GLOBAL_Control
0x140015dcc  lea     rdx, WPP_GLOBAL_Control
0x140015dd3  cmp     rcx, rdx
0x140015dd6  jz      short loc_140015D5B
0x140015dd8  test    byte ptr [rcx+1Ch], 1
0x140015ddc  jz      loc_140015D5B
0x140015de2  jmp     loc_140015D3B
```
