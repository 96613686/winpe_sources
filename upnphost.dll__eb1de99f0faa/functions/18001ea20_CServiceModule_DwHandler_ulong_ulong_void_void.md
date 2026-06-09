# CServiceModule::_DwHandler(ulong,ulong,void *,void *)

- ea: `0x18001ea20`
- end: `0x18001ebf2`
- name: `?_DwHandler@CServiceModule@@CAKKKPEAX0@Z`
- size: `466`
- prototype: `__int64 __fastcall(DWORD dwControl, DWORD dwEventType, LPVOID lpEventData, LPVOID lpContext)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x18001ea20`
- `0x18001ef30`
- `0x180038ce4`
- `0x180039298`
- `0x180039a84`
- `0x180055010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001ebe7`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001ebe7`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001ea8f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001eb10`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001ea8f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001eb10`

## pseudocode

```c
__int64 __fastcall CServiceModule::_DwHandler(DWORD dwControl, DWORD dwEventType, LPVOID lpEventData, LPVOID lpContext)
{
  DWORD v4; // ecx
  DWORD v5; // ecx
  DWORD v6; // ecx
  DWORD v7; // edx
  DWORD v8; // edx
  DWORD v9; // edx
  int v10; // edx
  unsigned int Instance; // eax
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // r9
  unsigned int v16; // eax
  __int64 v17; // rdx
  __int64 v18; // r8
  STRSAFE_PCNZWCH v19; // rcx
  __int64 v20; // rdx
  struct IUnknown *ppv[3]; // [rsp+30h] [rbp-18h] BYREF

  ppv[0] = 0;
  v4 = dwControl - 1;
  if ( !v4 )
    goto LABEL_29;
  v5 = v4 - 3;
  if ( !v5 )
  {
    if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 0x40) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_2670124a663039e2f0c82c5e619b77a4_Traceguids);
    return 0;
  }
  v6 = v5 - 1;
  if ( !v6 )
  {
LABEL_29:
    if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 0x40) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_2670124a663039e2f0c82c5e619b77a4_Traceguids);
    CServiceModule::SetServiceStatus((CServiceModule *)&_Module, 3u);
    if ( hEvent )
      SetEvent(hEvent);
    return 0;
  }
  if ( v6 == 8 )
  {
    if ( !dwEventType )
      goto LABEL_17;
    v7 = dwEventType - 2;
    if ( !v7 )
    {
LABEL_10:
      Instance = CoCreateInstance(
                   &CLSID_UPnPRegistrar,
                   0,
                   1u,
                   &GUID_6d8ff8db_730d_11d4_bf42_00b0d0118b56,
                   (LPVOID *)ppv);
      v14 = Instance;
      if ( !Instance )
      {
        ((void (__fastcall *)(struct IUnknown *, __int64, __int64, _QWORD))ppv[0]->lpVtbl[2].QueryInterface)(
          ppv[0],
          v12,
          v13,
          0);
LABEL_12:
        ReleaseObj(ppv[0]);
        return 0;
      }
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_12;
      v20 = 13;
      goto LABEL_27;
    }
    v8 = v7 - 2;
    if ( !v8 )
    {
LABEL_17:
      v16 = CoCreateInstance(&CLSID_UPnPRegistrar, 0, 1u, &GUID_6d8ff8db_730d_11d4_bf42_00b0d0118b56, (LPVOID *)ppv);
      v14 = v16;
      if ( !v16 )
      {
        ((void (__fastcall *)(struct IUnknown *, __int64, __int64, _QWORD))ppv[0]->lpVtbl[1].Release)(
          ppv[0],
          v17,
          v18,
          0);
        goto LABEL_12;
      }
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_12;
      v20 = 12;
LABEL_27:
      WPP_SF_d(*((_QWORD *)v19 + 2), v20, WPP_2670124a663039e2f0c82c5e619b77a4_Traceguids, v14);
      goto LABEL_12;
    }
    v9 = v8 - 2;
    if ( !v9 )
      goto LABEL_10;
    v10 = v9 - 1;
    if ( !v10 || v10 == 11 )
      goto LABEL_10;
  }
  return 0;
}

```

## disassembly

```asm
0x18001ea20  sub     rsp, 48h
0x18001ea24  mov     [rsp+48h+var_18], 0
0x18001ea2d  sub     ecx, 1
0x18001ea30  jz      loc_18001EB98
0x18001ea36  sub     ecx, 3
0x18001ea39  jz      loc_18001EAC2
0x18001ea3f  sub     ecx, 1
0x18001ea42  jz      loc_18001EB98
0x18001ea48  cmp     ecx, 8
0x18001ea4b  jnz     short loc_18001EABB
0x18001ea4d  test    edx, edx
0x18001ea4f  jz      loc_18001EAF2
0x18001ea55  sub     edx, 2
0x18001ea58  jz      short loc_18001EA71
0x18001ea5a  sub     edx, 2
0x18001ea5d  jz      loc_18001EAF2
0x18001ea63  sub     edx, 2
0x18001ea66  jz      short loc_18001EA71
0x18001ea68  sub     edx, 1
0x18001ea6b  jnz     loc_18001EB2B
0x18001ea71  xor     edx, edx; pUnkOuter
0x18001ea73  lea     rax, [rsp+48h+var_18]
0x18001ea78  lea     r9, _GUID_6d8ff8db_730d_11d4_bf42_00b0d0118b56; riid
0x18001ea7f  mov     [rsp+48h+ppv], rax; ppv
0x18001ea84  lea     rcx, CLSID_UPnPRegistrar; rclsid
0x18001ea8b  lea     r8d, [rdx+1]; dwClsContext
0x18001ea8f  call    cs:__imp_CoCreateInstance
0x18001ea95  mov     r9d, eax
0x18001ea98  test    eax, eax
0x18001ea9a  jnz     loc_18001EB35
0x18001eaa0  mov     rcx, [rsp+48h+var_18]
0x18001eaa5  mov     rax, [rcx]
0x18001eaa8  mov     rax, [rax+30h]
0x18001eaac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eab1  mov     rcx, [rsp+48h+var_18]; struct IUnknown *
0x18001eab6  call    ?ReleaseObj@@YAKPEAUIUnknown@@@Z; ReleaseObj(IUnknown *)
0x18001eabb  xor     eax, eax
0x18001eabd  add     rsp, 48h
0x18001eac1  retn
0x18001eac2  mov     rcx, cs:WPP_GLOBAL_Control
0x18001eac9  lea     rax, WPP_GLOBAL_Control
0x18001ead0  cmp     rcx, rax
0x18001ead3  jz      short loc_18001EABB
0x18001ead5  test    byte ptr [rcx+1Ch], 40h
0x18001ead9  jz      short loc_18001EABB
0x18001eadb  mov     rcx, [rcx+10h]
0x18001eadf  lea     r8, WPP_2670124a663039e2f0c82c5e619b77a4_Traceguids
0x18001eae6  mov     edx, 0Bh
0x18001eaeb  call    WPP_SF_
0x18001eaf0  jmp     short loc_18001EABB
0x18001eaf2  xor     edx, edx; pUnkOuter
0x18001eaf4  lea     rax, [rsp+48h+var_18]
0x18001eaf9  lea     r9, _GUID_6d8ff8db_730d_11d4_bf42_00b0d0118b56; riid
0x18001eb00  mov     [rsp+48h+ppv], rax; ppv
0x18001eb05  lea     rcx, CLSID_UPnPRegistrar; rclsid
0x18001eb0c  lea     r8d, [rdx+1]; dwClsContext
0x18001eb10  call    cs:__imp_CoCreateInstance
0x18001eb16  mov     r9d, eax
0x18001eb19  test    eax, eax
0x18001eb1b  jnz     short loc_18001EB5D
0x18001eb1d  mov     rcx, [rsp+48h+var_18]
0x18001eb22  mov     rax, [rcx]
0x18001eb25  mov     rax, [rax+28h]
0x18001eb29  jmp     short loc_18001EAAC
0x18001eb2b  cmp     edx, 0Bh
0x18001eb2e  jnz     short loc_18001EABB
0x18001eb30  jmp     loc_18001EA71
0x18001eb35  mov     rcx, cs:WPP_GLOBAL_Control
0x18001eb3c  lea     rax, WPP_GLOBAL_Control
0x18001eb43  cmp     rcx, rax
0x18001eb46  jz      loc_18001EAB1
0x18001eb4c  test    byte ptr [rcx+1Ch], 1
0x18001eb50  jz      loc_18001EAB1
0x18001eb56  mov     edx, 0Dh
0x18001eb5b  jmp     short loc_18001EB83
0x18001eb5d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001eb64  lea     rax, WPP_GLOBAL_Control
0x18001eb6b  cmp     rcx, rax
0x18001eb6e  jz      loc_18001EAB1
0x18001eb74  test    byte ptr [rcx+1Ch], 1
0x18001eb78  jz      loc_18001EAB1
0x18001eb7e  mov     edx, 0Ch
0x18001eb83  mov     rcx, [rcx+10h]
0x18001eb87  lea     r8, WPP_2670124a663039e2f0c82c5e619b77a4_Traceguids
0x18001eb8e  call    WPP_SF_d
0x18001eb93  jmp     loc_18001EAB1
0x18001eb98  mov     rcx, cs:WPP_GLOBAL_Control
0x18001eb9f  lea     rax, WPP_GLOBAL_Control
0x18001eba6  cmp     rcx, rax
0x18001eba9  jz      short loc_18001EBC6
0x18001ebab  test    byte ptr [rcx+1Ch], 40h
0x18001ebaf  jz      short loc_18001EBC6
0x18001ebb1  mov     rcx, [rcx+10h]
0x18001ebb5  lea     r8, WPP_2670124a663039e2f0c82c5e619b77a4_Traceguids
0x18001ebbc  mov     edx, 0Ah
0x18001ebc1  call    WPP_SF_
0x18001ebc6  mov     edx, 3; unsigned int
0x18001ebcb  lea     rcx, ?_Module@@3VCServiceModule@@A; this
0x18001ebd2  call    ?SetServiceStatus@CServiceModule@@QEAAXK@Z; CServiceModule::SetServiceStatus(ulong)
0x18001ebd7  mov     rcx, cs:hEvent; hEvent
0x18001ebde  test    rcx, rcx
0x18001ebe1  jz      loc_18001EABB
0x18001ebe7  call    cs:__imp_SetEvent
0x18001ebed  jmp     loc_18001EABB
```
