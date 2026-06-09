# ScHandleProviderChange(void *,uchar)

- ea: `0x140079d10`
- end: `0x14007a242`
- name: `?ScHandleProviderChange@@YAXPEAXE@Z`
- size: `1330`
- prototype: `void __stdcall(PVOID, BOOLEAN)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140039bd4`

## callees

- `0x140004c58`
- `0x14000bcc4`
- `0x14000c310`
- `0x140015b14`
- `0x140016318`
- `0x140016664`
- `0x1400188fc`
- `0x14001f99c`
- `0x14004af50`
- `0x140079d10`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x140079de8`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x140079de8`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x140079e2a`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x140079e2a`
- `ntdll!NtClose` at `0x14007a044`
- `ntdll!NtClose` at `0x14007a180`
- `ntdll!NtClose` at `0x14007a044`
- `ntdll!NtClose` at `0x14007a180`
- `ntdll!RtlNtStatusToDosError` at `0x14007a04c`
- `ntdll!RtlNtStatusToDosError` at `0x14007a188`
- `ntdll!RtlNtStatusToDosError` at `0x14007a04c`
- `ntdll!RtlNtStatusToDosError` at `0x14007a188`
- `ntdll!RtlFreeHeap` at `0x14007a0d0`
- `ntdll!RtlFreeHeap` at `0x14007a1c9`
- `ntdll!RtlFreeHeap` at `0x14007a0d0`
- `ntdll!RtlFreeHeap` at `0x14007a1c9`
- `ntdll!RtlRegisterWait` at `0x14007a1f3`
- `ntdll!RtlRegisterWait` at `0x14007a1f3`
- `ntdll!RtlDeleteSecurityObject` at `0x14007a03a`
- `ntdll!RtlDeleteSecurityObject` at `0x14007a03a`
- `ntdll!RtlDeregisterWait` at `0x140079db2`
- `ntdll!RtlDeregisterWait` at `0x140079db2`

## pseudocode

```c
void __fastcall ScHandleProviderChange(PVOID a1)
{
  NTSTATUS v2; // eax
  unsigned int v3; // eax
  ULONG v4; // eax
  wchar_t *v5; // rsi
  PRPC_ASYNC_STATE v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // r9
  unsigned int v9; // ebx
  unsigned int v10; // ecx
  unsigned int v11; // eax
  __int64 v12; // r8
  wchar_t v13; // dx
  int v14; // eax
  int v15; // eax
  __int64 v16; // r8
  const unsigned __int16 *v17; // r9
  HANDLE v18; // rcx
  unsigned int v19; // edi
  NTSTATUS v20; // eax
  unsigned int v21; // r8d
  BOOL v22; // edi
  unsigned int v23; // eax
  NTSTATUS v24; // eax
  NTSTATUS v25; // eax
  HANDLE Handle; // [rsp+50h] [rbp-39h] BYREF
  HANDLE v27; // [rsp+58h] [rbp-31h] BYREF
  PSECURITY_DESCRIPTOR ObjectDescriptor; // [rsp+60h] [rbp-29h] BYREF
  wchar_t *String1; // [rsp+68h] [rbp-21h] BYREF
  wchar_t *String2; // [rsp+70h] [rbp-19h] BYREF
  __int16 v31; // [rsp+78h] [rbp-11h] BYREF
  char v32; // [rsp+7Ah] [rbp-Fh]
  int v33; // [rsp+7Ch] [rbp-Dh]
  PSID *v34; // [rsp+80h] [rbp-9h]
  __int16 v35; // [rsp+88h] [rbp-1h]
  char v36; // [rsp+8Ah] [rbp+1h]
  unsigned int v37; // [rsp+8Ch] [rbp+3h]
  PSID *v38; // [rsp+90h] [rbp+7h]
  struct _SECURITY_ATTRIBUTES v39; // [rsp+98h] [rbp+Fh] BYREF
  unsigned int v40; // [rsp+100h] [rbp+77h] BYREF
  unsigned int v41; // [rsp+108h] [rbp+7Fh] BYREF

  v31 = 512;
  v34 = &LocalSystemSid;
  String2 = 0;
  v38 = &WorldSid;
  v40 = 0;
  String1 = 0;
  v27 = 0;
  Handle = 0;
  v41 = 0;
  *(&v39.nLength + 1) = 0;
  *(&v39.bInheritHandle + 1) = 0;
  ObjectDescriptor = 0;
  v32 = 0;
  v33 = 0x10000000;
  v35 = 512;
  v36 = 0;
  v37 = 0x80000000;
  if ( ScShutdownInProgress )
    return;
  if ( phNewWaitObject )
  {
    v2 = RtlDeregisterWait(phNewWaitObject);
    if ( v2 < 0
      && WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control->StubInfo, 117, WPP_e5a68143c9d03da933de77b1bc511594_Traceguids, (unsigned int)v2);
    }
  }
  ResetEvent(a1);
  if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 4) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->StubInfo, 118, WPP_e5a68143c9d03da933de77b1bc511594_Traceguids);
  v3 = RegNotifyChangeKeyValue(g_hProviderKey, 0, 4u, a1, 1);
  if ( v3
    && WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
    && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
  {
    WPP_SF_d(WPP_GLOBAL_Control->StubInfo, 119, WPP_e5a68143c9d03da933de77b1bc511594_Traceguids, v3);
  }
  v4 = ScAllocateAndReadConfigValue(g_hProviderKey, L"ProviderOrder", &String2, &v40);
  v5 = String2;
  if ( v4 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
    {
      v7 = 120;
LABEL_18:
      v8 = v4;
LABEL_19:
      WPP_SF_d(v6->StubInfo, v7, WPP_e5a68143c9d03da933de77b1bc511594_Traceguids, v8);
    }
  }
  else
  {
    v9 = v40;
    if ( (v40 & 1) != 0 || v40 < 2 || String2[((unsigned __int64)v40 >> 1) - 1] )
    {
      if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
        WPP_SF_(WPP_GLOBAL_Control->StubInfo, 121, WPP_e5a68143c9d03da933de77b1bc511594_Traceguids);
      goto LABEL_65;
    }
    v10 = 0;
    v11 = 0;
    do
    {
      v12 = v10;
      v13 = v5[v10];
      if ( v13 == 44 || !v13 )
        v5[v10] = v13;
      ++v10;
      v11 += 2;
    }
    while ( v11 < v9 );
    v14 = 1;
    if ( v10 )
      v14 = v10;
    v5[v14 - 1] = 0;
    if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 4) != 0 )
      WPP_SF_S(WPP_GLOBAL_Control->StubInfo, 122, WPP_e5a68143c9d03da933de77b1bc511594_Traceguids, v5);
    v4 = ScRegOpenKeyExW(
           HKEY_LOCAL_MACHINE,
           L"System\\CurrentControlSet\\Control\\NetworkProvider",
           v12,
           0x2001Fu,
           (HKEY *)&Handle);
    if ( !v4 )
    {
      v15 = ScCreateAndSetSD((__int64)&v31, 2u, LocalSystemSid, LocalSystemSid, (struct _ACL **)&ObjectDescriptor);
      if ( v15 >= 0 )
      {
        v39.lpSecurityDescriptor = ObjectDescriptor;
        v39.nLength = 24;
        v39.bInheritHandle = 0;
        v19 = ScRegCreateKeyExW((HKEY)Handle, L"HwOrder", v16, v17, 1u, 3u, &v39, (HKEY *)&v27, &v41);
        RtlDeleteSecurityObject(&ObjectDescriptor);
        v20 = NtClose(Handle);
        RtlNtStatusToDosError(v20);
        if ( v19 )
        {
          v6 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
            && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
          {
            v7 = 125;
            v8 = v19;
            goto LABEL_19;
          }
          goto LABEL_65;
        }
        if ( ScAllocateAndReadConfigValue((HKEY)v27, L"ProviderOrder", &String1, &v40) )
          goto LABEL_54;
        v22 = 1;
        if ( v40 == v9 )
          v22 = wcsnicmp(String1, v5, (unsigned __int64)v40 >> 1) != 0;
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, String1);
        if ( v22 )
        {
LABEL_54:
          if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
            && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 4) != 0 )
          {
            WPP_SF_(WPP_GLOBAL_Control->StubInfo, 126, WPP_e5a68143c9d03da933de77b1bc511594_Traceguids);
          }
          v23 = ScRegSetValueExW((HKEY)v27, L"ProviderOrder", v21, 1u, v5, v9);
          if ( v23
            && WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
            && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
          {
            WPP_SF_d(WPP_GLOBAL_Control->StubInfo, 127, WPP_e5a68143c9d03da933de77b1bc511594_Traceguids, v23);
          }
        }
        else if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
               && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 4) != 0 )
        {
          WPP_SF_(WPP_GLOBAL_Control->StubInfo, 128, WPP_e5a68143c9d03da933de77b1bc511594_Traceguids);
        }
        v18 = v27;
      }
      else
      {
        if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
          && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->StubInfo,
            124,
            WPP_e5a68143c9d03da933de77b1bc511594_Traceguids,
            (unsigned int)v15);
        }
        v18 = Handle;
      }
      v24 = NtClose(v18);
      RtlNtStatusToDosError(v24);
      goto LABEL_65;
    }
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
    {
      v7 = 123;
      goto LABEL_18;
    }
  }
LABEL_65:
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v5);
  v25 = RtlRegisterWait(&phNewWaitObject, a1, ScHandleProviderChange, a1, 0xFFFFFFFF, 0x48u);
  if ( v25 < 0
    && WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
    && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
  {
    WPP_SF_d(WPP_GLOBAL_Control->StubInfo, 129, WPP_e5a68143c9d03da933de77b1bc511594_Traceguids, (unsigned int)v25);
  }
}

```

## disassembly

```asm
0x140079d10  mov     [rsp-8+arg_0], rbx
0x140079d15  push    rbp
0x140079d16  push    rsi
0x140079d17  push    rdi
0x140079d18  push    r12
0x140079d1a  push    r13
0x140079d1c  push    r14
0x140079d1e  push    r15
0x140079d20  lea     rbp, [rsp-27h]
0x140079d25  sub     rsp, 0B0h
0x140079d2c  xor     r15d, r15d
0x140079d2f  mov     [rbp+57h+var_68], 200h
0x140079d35  cmp     cs:?ScShutdownInProgress@@3KA, r15d; ulong ScShutdownInProgress
0x140079d3c  lea     rax, LocalSystemSid
0x140079d43  mov     [rbp+57h+var_60], rax
0x140079d47  mov     r14, rcx
0x140079d4a  lea     rax, WorldSid
0x140079d51  mov     [rbp+57h+String2], r15
0x140079d55  mov     [rbp+57h+var_50], rax
0x140079d59  mov     [rbp+57h+arg_10], r15d
0x140079d5d  mov     [rbp+57h+String1], r15
0x140079d61  mov     [rbp+57h+var_88], r15
0x140079d65  mov     [rbp+57h+Handle], r15
0x140079d69  mov     [rbp+57h+arg_18], r15d
0x140079d6d  mov     dword ptr [rbp+57h+var_48+4], r15d
0x140079d71  mov     dword ptr [rbp+57h+var_48+14h], r15d
0x140079d75  mov     [rbp+57h+ObjectDescriptor], r15
0x140079d79  mov     [rbp+57h+var_66], r15b
0x140079d7d  mov     [rbp+57h+var_64], 10000000h
0x140079d84  mov     [rbp+57h+var_58], 200h
0x140079d8a  mov     [rbp+57h+var_56], r15b
0x140079d8e  mov     [rbp+57h+var_54], 80000000h
0x140079d95  jnz     loc_14007A227
0x140079d9b  mov     rcx, cs:phNewWaitObject; hWaitHandle
0x140079da2  lea     r12d, [r15+1]
0x140079da6  lea     r13, WPP_GLOBAL_Control
0x140079dad  test    rcx, rcx
0x140079db0  jz      short loc_140079DE5
0x140079db2  call    cs:__imp_RtlDeregisterWait
0x140079db8  test    eax, eax
0x140079dba  jns     short loc_140079DE5
0x140079dbc  mov     rcx, cs:WPP_GLOBAL_Control
0x140079dc3  cmp     rcx, r13
0x140079dc6  jz      short loc_140079DE5
0x140079dc8  test    [rcx+1Ch], r12b
0x140079dcc  jz      short loc_140079DE5
0x140079dce  mov     rcx, [rcx+10h]
0x140079dd2  lea     edx, [r15+75h]
0x140079dd6  mov     r9d, eax
0x140079dd9  lea     r8, WPP_e5a68143c9d03da933de77b1bc511594_Traceguids
0x140079de0  call    WPP_SF_d
0x140079de5  mov     rcx, r14; hEvent
0x140079de8  call    cs:__imp_ResetEvent
0x140079dee  mov     rcx, cs:WPP_GLOBAL_Control
0x140079df5  cmp     rcx, r13
0x140079df8  jz      short loc_140079E15
0x140079dfa  test    byte ptr [rcx+1Ch], 4
0x140079dfe  jz      short loc_140079E15
0x140079e00  mov     rcx, [rcx+10h]
0x140079e04  lea     r8, WPP_e5a68143c9d03da933de77b1bc511594_Traceguids
0x140079e0b  mov     edx, 76h ; 'v'
0x140079e10  call    WPP_SF_
0x140079e15  mov     rcx, cs:?g_hProviderKey@@3PEAUHKEY__@@EA; hKey
0x140079e1c  xor     edx, edx; bWatchSubtree
0x140079e1e  mov     r9, r14; hEvent
0x140079e21  mov     [rsp+0E0h+fAsynchronous], r12d; fAsynchronous
0x140079e26  lea     r8d, [rdx+4]; dwNotifyFilter
0x140079e2a  call    cs:__imp_RegNotifyChangeKeyValue
0x140079e30  test    eax, eax
0x140079e32  jz      short loc_140079E5E
0x140079e34  mov     rcx, cs:WPP_GLOBAL_Control
0x140079e3b  cmp     rcx, r13
0x140079e3e  jz      short loc_140079E5E
0x140079e40  test    [rcx+1Ch], r12b
0x140079e44  jz      short loc_140079E5E
0x140079e46  mov     rcx, [rcx+10h]
0x140079e4a  lea     r8, WPP_e5a68143c9d03da933de77b1bc511594_Traceguids
0x140079e51  mov     edx, 77h ; 'w'
0x140079e56  mov     r9d, eax
0x140079e59  call    WPP_SF_d
0x140079e5e  mov     rcx, cs:?g_hProviderKey@@3PEAUHKEY__@@EA; KeyHandle
0x140079e65  lea     r9, [rbp+57h+arg_10]; unsigned int *
0x140079e69  lea     r8, [rbp+57h+String2]; unsigned __int16 **
0x140079e6d  lea     rdx, aProviderorder; "ProviderOrder"
0x140079e74  call    ?ScAllocateAndReadConfigValue@@YAKPEAUHKEY__@@PEBGPEAPEAGPEAK@Z; ScAllocateAndReadConfigValue(HKEY__ *,ushort const *,ushort * *,ulong *)
0x140079e79  mov     rsi, [rbp+57h+String2]
0x140079e7d  test    eax, eax
0x140079e7f  jz      short loc_140079EB8
0x140079e81  mov     rcx, cs:WPP_GLOBAL_Control
0x140079e88  cmp     rcx, r13
0x140079e8b  jz      loc_14007A1B7
0x140079e91  test    [rcx+1Ch], r12b
0x140079e95  jz      loc_14007A1B7
0x140079e9b  mov     edx, 78h ; 'x'
0x140079ea0  mov     r9d, eax
0x140079ea3  mov     rcx, [rcx+10h]
0x140079ea7  lea     r8, WPP_e5a68143c9d03da933de77b1bc511594_Traceguids
0x140079eae  call    WPP_SF_d
0x140079eb3  jmp     loc_14007A1B7
0x140079eb8  mov     ebx, [rbp+57h+arg_10]
0x140079ebb  test    r12b, bl
0x140079ebe  jnz     loc_14007A190
0x140079ec4  cmp     ebx, 2
0x140079ec7  jb      loc_14007A190
0x140079ecd  mov     eax, ebx
0x140079ecf  shr     rax, 1
0x140079ed2  cmp     [rsi+rax*2-2], r15w
0x140079ed8  jnz     loc_14007A190
0x140079ede  mov     [rbp+57h+arg_10], ebx
0x140079ee1  mov     ecx, r15d
0x140079ee4  mov     eax, r15d
0x140079ee7  test    ebx, ebx
0x140079ee9  jz      short loc_140079F0D
0x140079eeb  mov     r8d, ecx
0x140079eee  movzx   edx, word ptr [rsi+r8*2]
0x140079ef3  cmp     dx, 2Ch ; ','
0x140079ef7  jz      short loc_140079EFE
0x140079ef9  test    dx, dx
0x140079efc  jnz     short loc_140079F03
0x140079efe  mov     [rsi+r8*2], dx
0x140079f03  add     ecx, r12d
0x140079f06  add     eax, 2
0x140079f09  cmp     eax, ebx
0x140079f0b  jb      short loc_140079EEB
0x140079f0d  test    ecx, ecx
0x140079f0f  mov     eax, r12d
0x140079f12  cmovnz  eax, ecx
0x140079f15  sub     eax, r12d
0x140079f18  mov     [rsi+rax*2], r15w
0x140079f1d  mov     rcx, cs:WPP_GLOBAL_Control
0x140079f24  cmp     rcx, r13
0x140079f27  jz      short loc_140079F47
0x140079f29  test    byte ptr [rcx+1Ch], 4
0x140079f2d  jz      short loc_140079F47
0x140079f2f  mov     rcx, [rcx+10h]
0x140079f33  lea     r8, WPP_e5a68143c9d03da933de77b1bc511594_Traceguids
0x140079f3a  mov     edx, 7Ah ; 'z'
0x140079f3f  mov     r9, rsi
0x140079f42  call    WPP_SF_S
0x140079f47  lea     rax, [rbp+57h+Handle]
0x140079f4b  mov     r9d, 2001Fh; unsigned int
0x140079f51  lea     rdx, aSystemCurrentc_9; "System\\CurrentControlSet\\Control\\Net"...
0x140079f58  mov     qword ptr [rsp+0E0h+fAsynchronous], rax; HKEY *
0x140079f5d  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x140079f64  call    ?ScRegOpenKeyExW@@YAKPEAUHKEY__@@PEBGKKPEAPEAU1@@Z; ScRegOpenKeyExW(HKEY__ *,ushort const *,ulong,ulong,HKEY__ * *)
0x140079f69  test    eax, eax
0x140079f6b  jz      short loc_140079F91
0x140079f6d  mov     rcx, cs:WPP_GLOBAL_Control
0x140079f74  cmp     rcx, r13
0x140079f77  jz      loc_14007A1B7
0x140079f7d  test    [rcx+1Ch], r12b
0x140079f81  jz      loc_14007A1B7
0x140079f87  mov     edx, 7Bh ; '{'
0x140079f8c  jmp     loc_140079EA0
0x140079f91  mov     r8, cs:LocalSystemSid
0x140079f98  lea     rax, [rbp+57h+ObjectDescriptor]
0x140079f9c  mov     r9, r8
0x140079f9f  mov     qword ptr [rsp+0E0h+fAsynchronous], rax
0x140079fa4  mov     edx, 2
0x140079fa9  lea     rcx, [rbp+57h+var_68]
0x140079fad  call    ScCreateAndSetSD
0x140079fb2  test    eax, eax
0x140079fb4  jns     short loc_140079FE9
0x140079fb6  mov     rcx, cs:WPP_GLOBAL_Control
0x140079fbd  cmp     rcx, r13
0x140079fc0  jz      short loc_140079FE0
0x140079fc2  test    [rcx+1Ch], r12b
0x140079fc6  jz      short loc_140079FE0
0x140079fc8  mov     rcx, [rcx+10h]
0x140079fcc  lea     r8, WPP_e5a68143c9d03da933de77b1bc511594_Traceguids
0x140079fd3  mov     edx, 7Ch ; '|'
0x140079fd8  mov     r9d, eax
0x140079fdb  call    WPP_SF_d
0x140079fe0  mov     rcx, [rbp+57h+Handle]
0x140079fe4  jmp     loc_14007A180
0x140079fe9  mov     rax, [rbp+57h+ObjectDescriptor]
0x140079fed  lea     rdx, aHworder; "HwOrder"
0x140079ff4  mov     rcx, [rbp+57h+Handle]; HKEY
0x140079ff8  mov     [rbp+57h+var_48.lpSecurityDescriptor], rax
0x140079ffc  lea     rax, [rbp+57h+arg_18]
0x14007a000  mov     [rsp+0E0h+var_A0], rax; unsigned int *
0x14007a005  lea     rax, [rbp+57h+var_88]
0x14007a009  mov     [rsp+0E0h+var_A8], rax; HKEY *
0x14007a00e  lea     rax, [rbp+57h+var_48]
0x14007a012  mov     [rsp+0E0h+var_B0], rax; struct _SECURITY_ATTRIBUTES *
0x14007a017  mov     [rsp+0E0h+ulFlags], 3; unsigned int
0x14007a01f  mov     [rsp+0E0h+fAsynchronous], r12d; unsigned int
0x14007a024  mov     [rbp+57h+var_48.nLength], 18h
0x14007a02b  mov     [rbp+57h+var_48.bInheritHandle], r15d
0x14007a02f  call    ?ScRegCreateKeyExW@@YAKPEAUHKEY__@@PEBGK1KKPEAU_SECURITY_ATTRIBUTES@@PEAPEAU1@PEAK@Z; ScRegCreateKeyExW(HKEY__ *,ushort const *,ulong,ushort const *,ulong,ulong,_SECURITY_ATTRIBUTES *,HKEY__ * *,ulong *)
0x14007a034  lea     rcx, [rbp+57h+ObjectDescriptor]; ObjectDescriptor
0x14007a038  mov     edi, eax
0x14007a03a  call    cs:__imp_RtlDeleteSecurityObject
0x14007a040  mov     rcx, [rbp+57h+Handle]; Handle
0x14007a044  call    cs:__imp_NtClose
0x14007a04a  mov     ecx, eax; Status
0x14007a04c  call    cs:__imp_RtlNtStatusToDosError
0x14007a052  test    edi, edi
0x14007a054  jz      short loc_14007A07D
0x14007a056  mov     rcx, cs:WPP_GLOBAL_Control
0x14007a05d  cmp     rcx, r13
0x14007a060  jz      loc_14007A1B7
0x14007a066  test    [rcx+1Ch], r12b
0x14007a06a  jz      loc_14007A1B7
0x14007a070  mov     edx, 7Dh ; '}'
0x14007a075  mov     r9d, edi
0x14007a078  jmp     loc_140079EA3
0x14007a07d  mov     rcx, [rbp+57h+var_88]; KeyHandle
0x14007a081  lea     r9, [rbp+57h+arg_10]; unsigned int *
0x14007a085  lea     r8, [rbp+57h+String1]; unsigned __int16 **
0x14007a089  lea     rdx, aProviderorder; "ProviderOrder"
0x14007a090  call    ?ScAllocateAndReadConfigValue@@YAKPEAUHKEY__@@PEBGPEAPEAGPEAK@Z; ScAllocateAndReadConfigValue(HKEY__ *,ushort const *,ushort * *,ulong *)
0x14007a095  test    eax, eax
0x14007a097  jnz     short loc_14007A10B
0x14007a099  mov     edi, r12d
0x14007a09c  cmp     [rbp+57h+arg_10], ebx
0x14007a09f  jnz     short loc_14007A0BD
0x14007a0a1  mov     r8d, [rbp+57h+arg_10]
0x14007a0a5  mov     rdx, rsi; String2
0x14007a0a8  mov     rcx, [rbp+57h+String1]; String1
0x14007a0ac  shr     r8, 1; MaxCount
0x14007a0af  call    _wcsnicmp
0x14007a0b4  test    eax, eax
0x14007a0b6  mov     edi, r15d
0x14007a0b9  setnz   dil
0x14007a0bd  mov     rcx, gs:60h
0x14007a0c6  xor     edx, edx; Flags
0x14007a0c8  mov     r8, [rbp+57h+String1]; P
0x14007a0cc  mov     rcx, [rcx+30h]; HeapHandle
0x14007a0d0  call    cs:__imp_RtlFreeHeap
0x14007a0d6  test    edi, edi
0x14007a0d8  jnz     short loc_14007A10B
0x14007a0da  mov     rcx, cs:WPP_GLOBAL_Control
0x14007a0e1  cmp     rcx, r13
0x14007a0e4  jz      loc_14007A17C
0x14007a0ea  test    byte ptr [rcx+1Ch], 4
0x14007a0ee  jz      loc_14007A17C
0x14007a0f4  mov     rcx, [rcx+10h]
0x14007a0f8  lea     r8, WPP_e5a68143c9d03da933de77b1bc511594_Traceguids
0x14007a0ff  mov     edx, 80h
0x14007a104  call    WPP_SF_
0x14007a109  jmp     short loc_14007A17C
0x14007a10b  mov     rcx, cs:WPP_GLOBAL_Control
0x14007a112  cmp     rcx, r13
0x14007a115  jz      short loc_14007A132
0x14007a117  test    byte ptr [rcx+1Ch], 4
0x14007a11b  jz      short loc_14007A132
0x14007a11d  mov     rcx, [rcx+10h]
0x14007a121  lea     r8, WPP_e5a68143c9d03da933de77b1bc511594_Traceguids
0x14007a128  mov     edx, 7Eh ; '~'
0x14007a12d  call    WPP_SF_
0x14007a132  mov     rcx, [rbp+57h+var_88]; KeyHandle
0x14007a136  lea     rdx, aProviderorder; "ProviderOrder"
0x14007a13d  mov     [rsp+0E0h+ulFlags], ebx; unsigned int
0x14007a141  mov     r9d, r12d; unsigned int
0x14007a144  mov     qword ptr [rsp+0E0h+fAsynchronous], rsi; void *
0x14007a149  call    ?ScRegSetValueExW@@YAKPEAUHKEY__@@PEBGKKPEAXK@Z; ScRegSetValueExW(HKEY__ *,ushort const *,ulong,ulong,void *,ulong)
0x14007a14e  test    eax, eax
0x14007a150  jz      short loc_14007A17C
0x14007a152  mov     rcx, cs:WPP_GLOBAL_Control
0x14007a159  cmp     rcx, r13
0x14007a15c  jz      short loc_14007A17C
0x14007a15e  test    [rcx+1Ch], r12b
0x14007a162  jz      short loc_14007A17C
0x14007a164  mov     rcx, [rcx+10h]
0x14007a168  lea     r8, WPP_e5a68143c9d03da933de77b1bc511594_Traceguids
0x14007a16f  mov     edx, 7Fh
0x14007a174  mov     r9d, eax
0x14007a177  call    WPP_SF_d
0x14007a17c  mov     rcx, [rbp+57h+var_88]; Handle
0x14007a180  call    cs:__imp_NtClose
0x14007a186  mov     ecx, eax; Status
0x14007a188  call    cs:__imp_RtlNtStatusToDosError
0x14007a18e  jmp     short loc_14007A1B7
0x14007a190  mov     rcx, cs:WPP_GLOBAL_Control
0x14007a197  cmp     rcx, r13
0x14007a19a  jz      short loc_14007A1B7
0x14007a19c  test    [rcx+1Ch], r12b
0x14007a1a0  jz      short loc_14007A1B7
0x14007a1a2  mov     rcx, [rcx+10h]
0x14007a1a6  lea     r8, WPP_e5a68143c9d03da933de77b1bc511594_Traceguids
0x14007a1ad  mov     edx, 79h ; 'y'
0x14007a1b2  call    WPP_SF_
0x14007a1b7  mov     rcx, gs:60h
0x14007a1c0  mov     r8, rsi; P
0x14007a1c3  xor     edx, edx; Flags
0x14007a1c5  mov     rcx, [rcx+30h]; HeapHandle
0x14007a1c9  call    cs:__imp_RtlFreeHeap
0x14007a1cf  mov     r9, r14; pvContext
0x14007a1d2  mov     [rsp+0E0h+ulFlags], 48h ; 'H'; ulFlags
0x14007a1da  lea     r8, ?ScHandleProviderChange@@YAXPEAXE@Z; Callback
0x14007a1e1  mov     [rsp+0E0h+fAsynchronous], 0FFFFFFFFh; ulMilliseconds
0x14007a1e9  mov     rdx, r14; hObject
0x14007a1ec  lea     rcx, phNewWaitObject; phNewWaitObject
0x14007a1f3  call    cs:__imp_RtlRegisterWait
0x14007a1f9  test    eax, eax
0x14007a1fb  jns     short loc_14007A227
0x14007a1fd  mov     rcx, cs:WPP_GLOBAL_Control
0x14007a204  cmp     rcx, r13
0x14007a207  jz      short loc_14007A227
  ... truncated ...
```
