# CServiceModule::_DwHandler(ulong,ulong,void *,void *)

- ea: `0x180013ae0`
- end: `0x180013cc8`
- name: `?_DwHandler@CServiceModule@@CAKKKPEAX0@Z`
- size: `488`
- prototype: `DWORD __stdcall(DWORD dwControl, DWORD dwEventType, LPVOID lpEventData, LPVOID lpContext)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x180013ae0`
- `0x180014038`
- `0x18003b1cc`
- `0x18003b800`
- `0x18003c018`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180013cb7`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180013cb7`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180013b4f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180013bd7`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180013b4f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180013bd7`

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
0x180013ae0  sub     rsp, 48h
0x180013ae4  mov     [rsp+48h+var_18], 0
0x180013aed  sub     ecx, 1
0x180013af0  jz      loc_180013C68
0x180013af6  sub     ecx, 3
0x180013af9  jz      loc_180013B89
0x180013aff  sub     ecx, 1
0x180013b02  jz      loc_180013C68
0x180013b08  cmp     ecx, 8
0x180013b0b  jnz     short loc_180013B81
0x180013b0d  test    edx, edx
0x180013b0f  jz      loc_180013BB9
0x180013b15  sub     edx, 2
0x180013b18  jz      short loc_180013B31
0x180013b1a  sub     edx, 2
0x180013b1d  jz      loc_180013BB9
0x180013b23  sub     edx, 2
0x180013b26  jz      short loc_180013B31
0x180013b28  sub     edx, 1
0x180013b2b  jnz     loc_180013BFB
0x180013b31  xor     edx, edx; pUnkOuter
0x180013b33  lea     rax, [rsp+48h+var_18]
0x180013b38  lea     r9, _GUID_6d8ff8db_730d_11d4_bf42_00b0d0118b56; riid
0x180013b3f  mov     [rsp+48h+ppv], rax; ppv
0x180013b44  lea     rcx, CLSID_UPnPRegistrar; rclsid
0x180013b4b  lea     r8d, [rdx+1]; dwClsContext
0x180013b4f  call    cs:__imp_CoCreateInstance
0x180013b56  nop     dword ptr [rax+rax+00h]
0x180013b5b  mov     r9d, eax
0x180013b5e  test    eax, eax
0x180013b60  jnz     loc_180013C05
0x180013b66  mov     rcx, [rsp+48h+var_18]
0x180013b6b  mov     rax, [rcx]
0x180013b6e  mov     rax, [rax+30h]
0x180013b72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013b77  mov     rcx, [rsp+48h+var_18]; struct IUnknown *
0x180013b7c  call    ?ReleaseObj@@YAKPEAUIUnknown@@@Z; ReleaseObj(IUnknown *)
0x180013b81  xor     eax, eax
0x180013b83  add     rsp, 48h
0x180013b87  retn
0x180013b89  mov     rcx, cs:WPP_GLOBAL_Control
0x180013b90  lea     rax, WPP_GLOBAL_Control
0x180013b97  cmp     rcx, rax
0x180013b9a  jz      short loc_180013B81
0x180013b9c  test    byte ptr [rcx+1Ch], 40h
0x180013ba0  jz      short loc_180013B81
0x180013ba2  mov     rcx, [rcx+10h]
0x180013ba6  lea     r8, WPP_2670124a663039e2f0c82c5e619b77a4_Traceguids
0x180013bad  mov     edx, 0Bh
0x180013bb2  call    WPP_SF_
0x180013bb7  jmp     short loc_180013B81
0x180013bb9  xor     edx, edx; pUnkOuter
0x180013bbb  lea     rax, [rsp+48h+var_18]
0x180013bc0  lea     r9, _GUID_6d8ff8db_730d_11d4_bf42_00b0d0118b56; riid
0x180013bc7  mov     [rsp+48h+ppv], rax; ppv
0x180013bcc  lea     rcx, CLSID_UPnPRegistrar; rclsid
0x180013bd3  lea     r8d, [rdx+1]; dwClsContext
0x180013bd7  call    cs:__imp_CoCreateInstance
0x180013bde  nop     dword ptr [rax+rax+00h]
0x180013be3  mov     r9d, eax
0x180013be6  test    eax, eax
0x180013be8  jnz     short loc_180013C2D
0x180013bea  mov     rcx, [rsp+48h+var_18]
0x180013bef  mov     rax, [rcx]
0x180013bf2  mov     rax, [rax+28h]
0x180013bf6  jmp     loc_180013B72
0x180013bfb  cmp     edx, 0Bh
0x180013bfe  jnz     short loc_180013B81
0x180013c00  jmp     loc_180013B31
0x180013c05  mov     rcx, cs:WPP_GLOBAL_Control
0x180013c0c  lea     rax, WPP_GLOBAL_Control
0x180013c13  cmp     rcx, rax
0x180013c16  jz      loc_180013B77
0x180013c1c  test    byte ptr [rcx+1Ch], 1
0x180013c20  jz      loc_180013B77
0x180013c26  mov     edx, 0Dh
0x180013c2b  jmp     short loc_180013C53
0x180013c2d  mov     rcx, cs:WPP_GLOBAL_Control
0x180013c34  lea     rax, WPP_GLOBAL_Control
0x180013c3b  cmp     rcx, rax
0x180013c3e  jz      loc_180013B77
0x180013c44  test    byte ptr [rcx+1Ch], 1
0x180013c48  jz      loc_180013B77
0x180013c4e  mov     edx, 0Ch
0x180013c53  mov     rcx, [rcx+10h]
0x180013c57  lea     r8, WPP_2670124a663039e2f0c82c5e619b77a4_Traceguids
0x180013c5e  call    WPP_SF_d
0x180013c63  jmp     loc_180013B77
0x180013c68  mov     rcx, cs:WPP_GLOBAL_Control
0x180013c6f  lea     rax, WPP_GLOBAL_Control
0x180013c76  cmp     rcx, rax
0x180013c79  jz      short loc_180013C96
0x180013c7b  test    byte ptr [rcx+1Ch], 40h
0x180013c7f  jz      short loc_180013C96
0x180013c81  mov     rcx, [rcx+10h]
0x180013c85  lea     r8, WPP_2670124a663039e2f0c82c5e619b77a4_Traceguids
0x180013c8c  mov     edx, 0Ah
0x180013c91  call    WPP_SF_
0x180013c96  mov     edx, 3; unsigned int
0x180013c9b  lea     rcx, ?_Module@@3VCServiceModule@@A; this
0x180013ca2  call    ?SetServiceStatus@CServiceModule@@QEAAXK@Z; CServiceModule::SetServiceStatus(ulong)
0x180013ca7  mov     rcx, cs:hEvent; hEvent
0x180013cae  test    rcx, rcx
0x180013cb1  jz      loc_180013B81
0x180013cb7  call    cs:__imp_SetEvent
0x180013cbe  nop     dword ptr [rax+rax+00h]
0x180013cc3  jmp     loc_180013B81
```
