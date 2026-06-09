# CWdsDeviceControllerManager::QueryMetadataWithSelectedControllers<CDeallocateNone>(ATL::CComObject<CWdsDeviceControllerRequest> *,CDynArray<CWdsDeviceControllerManager::CQueryEntry *,CDeallocateNone> &,CWdsDeviceControllerManager::QueryMetadataType,ATL::CComObject<CWdsComMetadata> *,ATL::CComObject<CWdsComMetadataBuilder> *)

- ea: `0x180006dfc`
- end: `0x180006fe8`
- name: `??$QueryMetadataWithSelectedControllers@VCDeallocateNone@@@CWdsDeviceControllerManager@@AEAAKPEAV?$CComObject@VCWdsDeviceControllerRequest@@@ATL@@AEAV?$CDynArray@PEAUCQueryEntry@CWdsDeviceControllerManager@@VCDeallocateNone@@@@W4QueryMetadataType@0@PEAV?$CComObject@VCWdsComMetadata@@@2@PEAV?$CComObject@VCWdsComMetadataBuilder@@@2@@Z`
- size: `492`
- prototype: `__int64 __fastcall(__int64, CWdsDeviceControllerRequest *, __int64, int, __int64, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1800042f4`

## callees

- `0x1800013d0`
- `0x180004dbc`
- `0x180006dfc`
- `0x180007310`
- `0x1800134f4`
- `0x180014d58`
- `0x180014ee0`
- `0x180015cc0`

## pseudocode

```c
__int64 __fastcall CWdsDeviceControllerManager::QueryMetadataWithSelectedControllers<CDeallocateNone>(
        __int64 a1,
        CWdsDeviceControllerRequest *a2,
        __int64 a3,
        int a4,
        __int64 a5,
        __int64 a6)
{
  unsigned int v6; // eax
  unsigned int v7; // esi
  int v8; // edi
  __int64 v9; // r14
  CWdsDeviceControllerRequest *v12; // rbx
  _QWORD *v13; // r15
  __int64 v14; // rcx
  int v15; // eax
  int v16; // ebx
  const char *v17; // rdx
  const char *v18; // rdx
  bool v19; // zf
  CMRSWLock *v21; // [rsp+30h] [rbp-38h] BYREF
  int v22; // [rsp+38h] [rbp-30h]
  __int64 v23; // [rsp+70h] [rbp+8h] BYREF
  CWdsDeviceControllerRequest *v24; // [rsp+78h] [rbp+10h]

  v24 = a2;
  v23 = a1;
  v6 = *(_DWORD *)(a3 + 12);
  v7 = 0;
  v8 = 0;
  v9 = 0;
  v12 = a2;
  if ( !v6 )
    return v7;
  while ( 1 )
  {
    v13 = 0;
    v7 = 0;
    LODWORD(v23) = 0;
    if ( (unsigned int)v9 < v6 )
      v13 = *(_QWORD **)(*(_QWORD *)a3 + 8 * v9);
    else
      v7 = 1413;
    if ( ElValidateWin32(
           v7,
           (const char *)a2,
           "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp",
           0x59Bu) )
    {
      return v7;
    }
    v22 = 0;
    v21 = (CMRSWLock *)(v13 + 3);
    CAutoReaderLock::Lock((CAutoReaderLock *)&v21);
    if ( !a4 )
    {
      v15 = (*(__int64 (__fastcall **)(_QWORD, CWdsDeviceControllerRequest *, __int64, __int64, __int64 *))(*(_QWORD *)*v13 + 24LL))(
              *v13,
              v12,
              a5,
              a6,
              &v23);
      goto LABEL_10;
    }
    if ( a4 == 1 )
    {
      v15 = (*(__int64 (__fastcall **)(_QWORD, CWdsDeviceControllerRequest *, __int64, __int64, __int64 *))(*(_QWORD *)*v13 + 32LL))(
              *v13,
              v12,
              a5,
              a6,
              &v23);
LABEL_10:
      v8 = v15;
    }
    v16 = v22;
    if ( v22 )
    {
      v16 = v22 - 1;
      if ( v22 == 1 )
        CMRSWLock::ReaderRelease(v21);
    }
    CWdsDeviceControllerManager::LogProviderMetadataQuery(v14, (unsigned int)v8, v13, a5, a6, v23);
    if ( (int)ElValidateHr(v8, v17, "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp", 0x5B8u) < 0 )
      break;
    v8 = CWdsDeviceControllerRequest::CleanupImpersonation(v24);
    if ( (int)ElValidateHr(v8, v18, "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp", 0x5BBu) < 0 )
    {
      if ( v8 >= 0 || (v7 = (unsigned __int16)v8, (v8 & 0x1FFF0000) != 0x70000) )
        v7 = v8;
LABEL_21:
      if ( !v16 )
        return v7;
      v19 = v16 == 1;
LABEL_31:
      if ( v19 )
        CMRSWLock::ReaderRelease(v21);
      return v7;
    }
    if ( (_DWORD)v23 == 1 )
      goto LABEL_21;
    if ( v16 == 1 )
      CMRSWLock::ReaderRelease(v21);
    v6 = *(_DWORD *)(a3 + 12);
    v9 = (unsigned int)(v9 + 1);
    v12 = v24;
    if ( (unsigned int)v9 >= v6 )
      return v7;
  }
  if ( v8 >= 0 || (v7 = (unsigned __int16)v8, (v8 & 0x1FFF0000) != 0x70000) )
    v7 = v8;
  if ( v16 )
  {
    v19 = v16 == 1;
    goto LABEL_31;
  }
  return v7;
}

```

## disassembly

```asm
0x180006dfc  mov     rax, rsp
0x180006dff  mov     [rax+18h], rbx
0x180006e03  mov     [rax+20h], rsi
0x180006e07  mov     [rax+10h], rdx
0x180006e0b  mov     [rax+8], rcx
0x180006e0f  push    rdi
0x180006e10  push    r12
0x180006e12  push    r13
0x180006e14  push    r14
0x180006e16  push    r15
0x180006e18  sub     rsp, 40h
0x180006e1c  mov     eax, [r8+0Ch]
0x180006e20  xor     esi, esi
0x180006e22  xor     edi, edi
0x180006e24  xor     r14d, r14d
0x180006e27  mov     r13d, r9d
0x180006e2a  mov     r12, r8
0x180006e2d  mov     rbx, rdx
0x180006e30  test    eax, eax
0x180006e32  jz      loc_180006FCC
0x180006e38  xor     r15d, r15d
0x180006e3b  xor     esi, esi
0x180006e3d  and     dword ptr [rsp+68h+arg_0], r15d
0x180006e42  cmp     r14d, eax
0x180006e45  jb      short loc_180006E4E
0x180006e47  mov     esi, 585h
0x180006e4c  jmp     short loc_180006E56
0x180006e4e  mov     rax, [r12]
0x180006e52  mov     r15, [rax+r14*8]
0x180006e56  mov     r9d, 59Bh; unsigned int
0x180006e5c  lea     r8, aBaseEcoWdsWdss_1; "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\"...
0x180006e63  mov     ecx, esi; unsigned int
0x180006e65  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180006e6a  test    eax, eax
0x180006e6c  jnz     loc_180006FCC
0x180006e72  and     [rsp+68h+var_30], 0
0x180006e77  lea     rax, [r15+18h]
0x180006e7b  lea     rcx, [rsp+68h+var_38]; this
0x180006e80  mov     [rsp+68h+var_38], rax
0x180006e85  call    ?Lock@CAutoReaderLock@@QEAAXXZ; CAutoReaderLock::Lock(void)
0x180006e8a  test    r13d, r13d
0x180006e8d  jz      short loc_180006EA1
0x180006e8f  cmp     r13d, 1
0x180006e93  jnz     short loc_180006ED0
0x180006e95  mov     rcx, [r15]
0x180006e98  mov     rax, [rcx]
0x180006e9b  mov     rax, [rax+20h]
0x180006e9f  jmp     short loc_180006EAB
0x180006ea1  mov     rcx, [r15]
0x180006ea4  mov     rax, [rcx]
0x180006ea7  mov     rax, [rax+18h]
0x180006eab  mov     r9, [rsp+68h+arg_28]
0x180006eb3  lea     rdx, [rsp+68h+arg_0]
0x180006eb8  mov     r8, [rsp+68h+arg_20]
0x180006ec0  mov     [rsp+68h+var_48], rdx
0x180006ec5  mov     rdx, rbx
0x180006ec8  call    cs:__guard_dispatch_icall_fptr
0x180006ece  mov     edi, eax
0x180006ed0  mov     ebx, [rsp+68h+var_30]
0x180006ed4  test    ebx, ebx
0x180006ed6  jz      short loc_180006EE7
0x180006ed8  add     ebx, 0FFFFFFFFh
0x180006edb  jnz     short loc_180006EE7
0x180006edd  mov     rcx, [rsp+68h+var_38]; this
0x180006ee2  call    ?ReaderRelease@CMRSWLock@@QEAAXXZ; CMRSWLock::ReaderRelease(void)
0x180006ee7  mov     eax, dword ptr [rsp+68h+arg_0]
0x180006eeb  mov     r8, r15
0x180006eee  mov     r9, [rsp+68h+arg_20]
0x180006ef6  mov     edx, edi
0x180006ef8  mov     [rsp+68h+var_40], eax
0x180006efc  mov     rax, [rsp+68h+arg_28]
0x180006f04  mov     [rsp+68h+var_48], rax
0x180006f09  call    ?LogProviderMetadataQuery@CWdsDeviceControllerManager@@AEAAXJPEAUCQueryEntry@1@PEAVCWdsComMetadata@@PEAVCWdsComMetadataBuilder@@W4__MIDL___MIDL_itf_wdsmetadata_0000_0000_0001@@@Z; CWdsDeviceControllerManager::LogProviderMetadataQuery(long,CWdsDeviceControllerManager::CQueryEntry *,CWdsComMetadata *,CWdsComMetadataBuilder *,__MIDL___MIDL_itf_wdsmetadata_0000_0000_0001)
0x180006f0e  mov     r9d, 5B8h; unsigned int
0x180006f14  lea     r8, aBaseEcoWdsWdss_1; "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\"...
0x180006f1b  mov     ecx, edi; int
0x180006f1d  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x180006f22  test    eax, eax
0x180006f24  js      short loc_180006FA0
0x180006f26  mov     rcx, [rsp+68h+arg_8]; this
0x180006f2b  call    ?CleanupImpersonation@CWdsDeviceControllerRequest@@QEAAJXZ; CWdsDeviceControllerRequest::CleanupImpersonation(void)
0x180006f30  mov     r9d, 5BBh; unsigned int
0x180006f36  lea     r8, aBaseEcoWdsWdss_1; "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\"...
0x180006f3d  mov     ecx, eax; int
0x180006f3f  mov     edi, eax
0x180006f41  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x180006f46  test    eax, eax
0x180006f48  js      short loc_180006F87
0x180006f4a  cmp     dword ptr [rsp+68h+arg_0], 1
0x180006f4f  jz      short loc_180006F7C
0x180006f51  test    ebx, ebx
0x180006f53  jz      short loc_180006F64
0x180006f55  add     ebx, 0FFFFFFFFh
0x180006f58  jnz     short loc_180006F64
0x180006f5a  mov     rcx, [rsp+68h+var_38]; this
0x180006f5f  call    ?ReaderRelease@CMRSWLock@@QEAAXXZ; CMRSWLock::ReaderRelease(void)
0x180006f64  mov     eax, [r12+0Ch]
0x180006f69  inc     r14d
0x180006f6c  mov     rbx, [rsp+68h+arg_8]
0x180006f71  cmp     r14d, eax
0x180006f74  jb      loc_180006E38
0x180006f7a  jmp     short loc_180006FCC
0x180006f7c  test    ebx, ebx
0x180006f7e  jz      short loc_180006FCC
0x180006f80  lea     eax, [rbx-1]
0x180006f83  test    eax, eax
0x180006f85  jmp     short loc_180006FC0
0x180006f87  test    edi, edi
0x180006f89  jns     short loc_180006F9C
0x180006f8b  mov     eax, edi
0x180006f8d  movzx   esi, di
0x180006f90  and     eax, 1FFF0000h
0x180006f95  cmp     eax, 70000h
0x180006f9a  jz      short loc_180006F7C
0x180006f9c  mov     esi, edi
0x180006f9e  jmp     short loc_180006F7C
0x180006fa0  test    edi, edi
0x180006fa2  jns     short loc_180006FB5
0x180006fa4  mov     eax, edi
0x180006fa6  movzx   esi, di
0x180006fa9  and     eax, 1FFF0000h
0x180006fae  cmp     eax, 70000h
0x180006fb3  jz      short loc_180006FB7
0x180006fb5  mov     esi, edi
0x180006fb7  test    ebx, ebx
0x180006fb9  jz      short loc_180006FCC
0x180006fbb  lea     ecx, [rbx-1]
0x180006fbe  test    ecx, ecx
0x180006fc0  jnz     short loc_180006FCC
0x180006fc2  mov     rcx, [rsp+68h+var_38]; this
0x180006fc7  call    ?ReaderRelease@CMRSWLock@@QEAAXXZ; CMRSWLock::ReaderRelease(void)
0x180006fcc  lea     r11, [rsp+68h+var_28]
0x180006fd1  mov     eax, esi
0x180006fd3  mov     rbx, [r11+40h]
0x180006fd7  mov     rsi, [r11+48h]
0x180006fdb  mov     rsp, r11
0x180006fde  pop     r15
0x180006fe0  pop     r14
0x180006fe2  pop     r13
0x180006fe4  pop     r12
0x180006fe6  pop     rdi
0x180006fe7  retn
```
