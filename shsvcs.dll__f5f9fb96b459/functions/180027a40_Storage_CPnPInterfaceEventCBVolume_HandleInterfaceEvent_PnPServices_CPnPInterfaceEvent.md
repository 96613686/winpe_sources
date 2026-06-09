# Storage::CPnPInterfaceEventCBVolume::HandleInterfaceEvent(PnPServices::CPnPInterfaceEvent *)

- ea: `0x180027a40`
- end: `0x180027c69`
- name: `?HandleInterfaceEvent@CPnPInterfaceEventCBVolume@Storage@@UEAAJPEAVCPnPInterfaceEvent@PnPServices@@@Z`
- size: `553`
- prototype: `__int64 __fastcall(Storage::CPnPInterfaceEventCBVolume *__hidden this, struct PnPServices::CPnPInterfaceEvent *)`
- caller_count: `0`
- callee_count: `13`
- tags: `file_ops, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180003570`
- `0x180007b04`
- `0x180007b20`
- `0x180018d28`
- `0x18001bc64`
- `0x18001bcd4`
- `0x18002656c`
- `0x180026774`
- `0x180027970`
- `0x180027a40`
- `0x180027c70`
- `0x180028a28`
- `0x180032c90`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180027a73`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180027b82`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180027a73`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180027b82`
- `api-ms-win-devices-query-l1-1-0!DevGetObjectProperties` at `0x180027b2d`
- `api-ms-win-devices-query-l1-1-0!DevGetObjectProperties` at `0x180027b2d`

## pseudocode

```c
__int64 __fastcall Storage::CPnPInterfaceEventCBVolume::HandleInterfaceEvent(
        Storage::CPnPInterfaceEventCBVolume *this,
        struct PnPServices::CPnPInterfaceEvent *a2)
{
  char *v3; // rsi
  int v4; // edi
  __int64 v5; // rax
  __int64 v6; // rcx
  __int64 v7; // rbx
  CRefCounted *v8; // rcx
  CRefCounted *v9; // rbx
  int v11; // [rsp+40h] [rbp-49h] BYREF
  __int64 v12; // [rsp+48h] [rbp-41h] BYREF
  GUID rguid; // [rsp+50h] [rbp-39h] BYREF
  OLECHAR sz[40]; // [rsp+60h] [rbp-29h] BYREF

  StringFromGUID2(&GUID_NULL, sz, 39);
  if ( __TSS0__1__HandleInterfaceEvent_CPnPInterfaceEventCBVolume_Storage__UEAAJPEAVCPnPInterfaceEvent_PnPServices___Z_4HA > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index) + 4LL) )
  {
    Init_thread_header(&__TSS0__1__HandleInterfaceEvent_CPnPInterfaceEventCBVolume_Storage__UEAAJPEAVCPnPInterfaceEvent_PnPServices___Z_4HA);
    if ( __TSS0__1__HandleInterfaceEvent_CPnPInterfaceEventCBVolume_Storage__UEAAJPEAVCPnPInterfaceEvent_PnPServices___Z_4HA == -1 )
    {
      *(DEVPROPKEY *)`Storage::CPnPInterfaceEventCBVolume::HandleInterfaceEvent'::`2'::Keys = DEVPKEY_Device_ContainerId;
      dword_18003F7FC = 0;
      qword_18003F800 = 0;
      Init_thread_footer(&__TSS0__1__HandleInterfaceEvent_CPnPInterfaceEventCBVolume_Storage__UEAAJPEAVCPnPInterfaceEvent_PnPServices___Z_4HA);
    }
  }
  v11 = 0;
  v3 = (char *)a2 + 20;
  v12 = 0;
  v4 = 1;
  if ( (int)DevGetObjectProperties(
              1,
              (char *)a2 + 20,
              0,
              1,
              `Storage::CPnPInterfaceEventCBVolume::HandleInterfaceEvent'::`2'::Keys,
              &v11,
              &v12) >= 0
    && v11 == 1
    && *(_DWORD *)(v12 + 16) == 2 )
  {
    v5 = *(_QWORD *)v12 - *(_QWORD *)&DEVPKEY_Device_ContainerId.fmtid.Data1;
    if ( *(_QWORD *)v12 == *(_QWORD *)&DEVPKEY_Device_ContainerId.fmtid.Data1 )
      v5 = *(_QWORD *)(v12 + 8) - *(_QWORD *)DEVPKEY_Device_ContainerId.fmtid.Data4;
    if ( !v5 && *(_DWORD *)(v12 + 32) == 13 )
    {
      rguid = *(GUID *)*(_QWORD *)(v12 + 40);
      StringFromGUID2(&rguid, sz, 39);
    }
  }
  v6 = (unsigned int)(*((_DWORD *)a2 + 4) - 0x8000);
  if ( *((_DWORD *)a2 + 4) == 0x8000 )
  {
    if ( (Microsoft_Windows_ShsvcsEnableBits & 1) != 0 )
      McTemplateU0zz_EtwEventWriteTransfer(v6, ShellTraceId_HDSrv_Volume_Arrived_Updated_Start, sz, (char *)a2 + 20);
    v9 = Storage::g_pnelVolumeInfo;
    *(_QWORD *)&rguid.Data1 = 0;
    CCritSectWithResource<CNamedElemList<PnPServices::CHandleNotif>>::Enter(*((_QWORD *)Storage::g_pnelVolumeInfo + 3));
    v4 = CNamedElemList<Storage::CVolumeInfo>::_Add<int *,unsigned short const *>(v9, v3, &rguid);
    CCritSectWithResource<CDummyResource>::Leave(*((_QWORD *)v9 + 3));
    if ( v4 >= 0 )
    {
      v7 = *(_QWORD *)&rguid.Data1;
      Storage::CVolumeInfo::HandleArrivalEvent(*(Storage::CVolumeInfo **)&rguid.Data1);
      goto LABEL_22;
    }
  }
  else if ( *((_DWORD *)a2 + 4) == 32772 )
  {
    if ( (Microsoft_Windows_ShsvcsEnableBits & 1) != 0 )
      McTemplateU0zz_EtwEventWriteTransfer(v6, ShellTraceId_HDSrv_Volume_Removed_Start, sz, (char *)a2 + 20);
    *(_QWORD *)&rguid.Data1 = 0;
    v4 = CNamedElemList<Storage::CVolumeInfo>::Get<unsigned short const *>(v6, (char *)a2 + 20, &rguid);
    if ( v4 >= 0 )
    {
      v7 = *(_QWORD *)&rguid.Data1;
      Storage::CVolumeInfo::HandleRemovalEvent(*(Storage::CVolumeInfo **)&rguid.Data1);
      CNamedElemList<Storage::CVolumeInfo>::Remove<unsigned short const *>(v8, (__int64)v3);
LABEL_22:
      CRefCounted::Release((CRefCounted *)(v7 + 16));
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180027a40  push    rbp
0x180027a42  push    rbx
0x180027a43  push    rsi
0x180027a44  push    rdi
0x180027a45  lea     rbp, [rsp-3Fh]
0x180027a4a  sub     rsp, 0C8h
0x180027a51  mov     rax, cs:__security_cookie
0x180027a58  xor     rax, rsp
0x180027a5b  mov     [rbp+57h+var_30], rax
0x180027a5f  mov     rbx, rdx
0x180027a62  lea     rcx, GUID_NULL; rguid
0x180027a69  lea     rdx, [rbp+57h+sz]; lpsz
0x180027a6d  mov     r8d, 27h ; '''; cchMax
0x180027a73  call    cs:__imp_StringFromGUID2
0x180027a79  mov     ecx, cs:_tls_index
0x180027a7f  mov     rax, gs:58h
0x180027a88  mov     edx, 4
0x180027a8d  mov     rax, [rax+rcx*8]
0x180027a91  mov     eax, [rdx+rax]
0x180027a94  cmp     cs:?$TSS0@?1??HandleInterfaceEvent@CPnPInterfaceEventCBVolume@Storage@@UEAAJPEAVCPnPInterfaceEvent@PnPServices@@@Z@4HA, eax
0x180027a9a  jle     short loc_180027AEC
0x180027a9c  lea     rcx, ?$TSS0@?1??HandleInterfaceEvent@CPnPInterfaceEventCBVolume@Storage@@UEAAJPEAVCPnPInterfaceEvent@PnPServices@@@Z@4HA
0x180027aa3  call    _Init_thread_header
0x180027aa8  cmp     cs:?$TSS0@?1??HandleInterfaceEvent@CPnPInterfaceEventCBVolume@Storage@@UEAAJPEAVCPnPInterfaceEvent@PnPServices@@@Z@4HA, 0FFFFFFFFh
0x180027aaf  jnz     short loc_180027AEC
0x180027ab1  movups  xmm0, xmmword ptr cs:DEVPKEY_Device_ContainerId.fmtid.Data1
0x180027ab8  mov     eax, cs:DEVPKEY_Device_ContainerId.pid
0x180027abe  lea     rcx, ?$TSS0@?1??HandleInterfaceEvent@CPnPInterfaceEventCBVolume@Storage@@UEAAJPEAVCPnPInterfaceEvent@PnPServices@@@Z@4HA
0x180027ac5  mov     dword ptr cs:?Keys@?1??HandleInterfaceEvent@CPnPInterfaceEventCBVolume@Storage@@UEAAJPEAVCPnPInterfaceEvent@PnPServices@@@Z@4QBU_DEVPROPCOMPKEY@@B+10h, eax; _DEVPROPCOMPKEY const near * const `Storage::CPnPInterfaceEventCBVolume::HandleInterfaceEvent(PnPServices::CPnPInterfaceEvent *)'::`2'::Keys
0x180027acb  movups  xmmword ptr cs:?Keys@?1??HandleInterfaceEvent@CPnPInterfaceEventCBVolume@Storage@@UEAAJPEAVCPnPInterfaceEvent@PnPServices@@@Z@4QBU_DEVPROPCOMPKEY@@B, xmm0; _DEVPROPCOMPKEY const near * const `Storage::CPnPInterfaceEventCBVolume::HandleInterfaceEvent(PnPServices::CPnPInterfaceEvent *)'::`2'::Keys
0x180027ad2  mov     cs:dword_18003F7FC, 0
0x180027adc  mov     cs:qword_18003F800, 0
0x180027ae7  call    _Init_thread_footer
0x180027aec  lea     rax, [rbp+57h+var_98]
0x180027af0  mov     [rbp+57h+var_A0], 0
0x180027af7  mov     [rsp+0E0h+var_B0], rax
0x180027afc  lea     rsi, [rbx+14h]
0x180027b00  lea     rax, [rbp+57h+var_A0]
0x180027b04  mov     [rbp+57h+var_98], 0
0x180027b0c  mov     [rsp+0E0h+var_B8], rax
0x180027b11  mov     edi, 1
0x180027b16  lea     rax, ?Keys@?1??HandleInterfaceEvent@CPnPInterfaceEventCBVolume@Storage@@UEAAJPEAVCPnPInterfaceEvent@PnPServices@@@Z@4QBU_DEVPROPCOMPKEY@@B; _DEVPROPCOMPKEY const near * const `Storage::CPnPInterfaceEventCBVolume::HandleInterfaceEvent(PnPServices::CPnPInterfaceEvent *)'::`2'::Keys
0x180027b1d  mov     r9d, edi
0x180027b20  xor     r8d, r8d
0x180027b23  mov     [rsp+0E0h+var_C0], rax
0x180027b28  mov     rdx, rsi
0x180027b2b  mov     ecx, edi
0x180027b2d  call    cs:__imp_DevGetObjectProperties
0x180027b33  test    eax, eax
0x180027b35  js      short loc_180027B88
0x180027b37  cmp     [rbp+57h+var_A0], edi
0x180027b3a  jnz     short loc_180027B88
0x180027b3c  mov     rcx, [rbp+57h+var_98]
0x180027b40  cmp     dword ptr [rcx+10h], 2
0x180027b44  jnz     short loc_180027B88
0x180027b46  mov     rax, [rcx]
0x180027b49  sub     rax, qword ptr cs:DEVPKEY_Device_ContainerId.fmtid.Data1
0x180027b50  jnz     short loc_180027B5D
0x180027b52  mov     rax, [rcx+8]
0x180027b56  sub     rax, qword ptr cs:DEVPKEY_Device_ContainerId.fmtid.Data4
0x180027b5d  test    rax, rax
0x180027b60  jnz     short loc_180027B88
0x180027b62  cmp     dword ptr [rcx+20h], 0Dh
0x180027b66  jnz     short loc_180027B88
0x180027b68  mov     rax, [rcx+28h]
0x180027b6c  lea     rdx, [rbp+57h+sz]; lpsz
0x180027b70  mov     r8d, 27h ; '''; cchMax
0x180027b76  lea     rcx, [rbp+57h+rguid]; rguid
0x180027b7a  movups  xmm0, xmmword ptr [rax]
0x180027b7d  movdqu  xmmword ptr [rbp+57h+rguid.Data1], xmm0
0x180027b82  call    cs:__imp_StringFromGUID2
0x180027b88  mov     ecx, [rbx+10h]
0x180027b8b  sub     ecx, 8000h
0x180027b91  jz      short loc_180027BE8
0x180027b93  cmp     ecx, 4
0x180027b96  jnz     loc_180027C4F
0x180027b9c  test    cs:Microsoft_Windows_ShsvcsEnableBits, dil
0x180027ba3  jz      short loc_180027BB8
0x180027ba5  mov     r9, rsi
0x180027ba8  lea     r8, [rbp+57h+sz]
0x180027bac  lea     rdx, ShellTraceId_HDSrv_Volume_Removed_Start
0x180027bb3  call    McTemplateU0zz_EtwEventWriteTransfer
0x180027bb8  lea     r8, [rbp+57h+rguid]
0x180027bbc  mov     qword ptr [rbp+57h+rguid.Data1], 0
0x180027bc4  mov     rdx, rsi
0x180027bc7  call    ??$Get@PEBG@?$CNamedElemList@VCVolumeInfo@Storage@@@@QEAAJQEBGPEAPEAVCVolumeInfo@Storage@@@Z; CNamedElemList<Storage::CVolumeInfo>::Get<ushort const *>(ushort const * const,Storage::CVolumeInfo * *)
0x180027bcc  mov     edi, eax
0x180027bce  test    eax, eax
0x180027bd0  js      short loc_180027C4F
0x180027bd2  mov     rbx, qword ptr [rbp+57h+rguid.Data1]
0x180027bd6  mov     rcx, rbx; this
0x180027bd9  call    ?HandleRemovalEvent@CVolumeInfo@Storage@@QEAAJXZ; Storage::CVolumeInfo::HandleRemovalEvent(void)
0x180027bde  mov     rdx, rsi
0x180027be1  call    ??$Remove@PEBG@?$CNamedElemList@VCVolumeInfo@Storage@@@@QEAAJQEBG@Z; CNamedElemList<Storage::CVolumeInfo>::Remove<ushort const *>(ushort const * const)
0x180027be6  jmp     short loc_180027C46
0x180027be8  test    cs:Microsoft_Windows_ShsvcsEnableBits, dil
0x180027bef  jz      short loc_180027C04
0x180027bf1  mov     r9, rsi
0x180027bf4  lea     r8, [rbp+57h+sz]
0x180027bf8  lea     rdx, ShellTraceId_HDSrv_Volume_Arrived_Updated_Start
0x180027bff  call    McTemplateU0zz_EtwEventWriteTransfer
0x180027c04  mov     rbx, cs:?g_pnelVolumeInfo@Storage@@3PEAV?$CNamedElemList@VCVolumeInfo@Storage@@@@EA; CNamedElemList<Storage::CVolumeInfo> * Storage::g_pnelVolumeInfo
0x180027c0b  mov     qword ptr [rbp+57h+rguid.Data1], 0
0x180027c13  mov     rcx, [rbx+18h]
0x180027c17  call    ?Enter@?$CCritSectWithResource@V?$CNamedElemList@VCHandleNotif@PnPServices@@@@@@QEAAXXZ; CCritSectWithResource<CNamedElemList<PnPServices::CHandleNotif>>::Enter(void)
0x180027c1c  lea     r8, [rbp+57h+rguid]
0x180027c20  mov     rdx, rsi
0x180027c23  mov     rcx, rbx
0x180027c26  call    ??$_Add@PEAHPEBG@?$CNamedElemList@VCVolumeInfo@Storage@@@@AEAAJQEBGPEAPEAVCVolumeInfo@Storage@@QEAH@Z; CNamedElemList<Storage::CVolumeInfo>::_Add<int *,ushort const *>(ushort const * const,Storage::CVolumeInfo * *,int * const)
0x180027c2b  mov     rcx, [rbx+18h]
0x180027c2f  mov     edi, eax
0x180027c31  call    ?Leave@?$CCritSectWithResource@VCDummyResource@@@@QEAAXXZ; CCritSectWithResource<CDummyResource>::Leave(void)
0x180027c36  test    edi, edi
0x180027c38  js      short loc_180027C4F
0x180027c3a  mov     rbx, qword ptr [rbp+57h+rguid.Data1]
0x180027c3e  mov     rcx, rbx; this
0x180027c41  call    ?HandleArrivalEvent@CVolumeInfo@Storage@@QEAAJXZ; Storage::CVolumeInfo::HandleArrivalEvent(void)
0x180027c46  lea     rcx, [rbx+10h]; this
0x180027c4a  call    ?Release@CRefCounted@@QEBAKXZ; CRefCounted::Release(void)
0x180027c4f  mov     eax, edi
0x180027c51  mov     rcx, [rbp+57h+var_30]
0x180027c55  xor     rcx, rsp; StackCookie
0x180027c58  call    __security_check_cookie
0x180027c5d  add     rsp, 0C8h
0x180027c64  pop     rdi
0x180027c65  pop     rsi
0x180027c66  pop     rbx
0x180027c67  pop     rbp
0x180027c68  retn
```
