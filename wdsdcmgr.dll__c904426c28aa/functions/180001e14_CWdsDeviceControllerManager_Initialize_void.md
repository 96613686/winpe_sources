# CWdsDeviceControllerManager::Initialize(void *)

- ea: `0x180001e14`
- end: `0x18000225f`
- name: `?Initialize@CWdsDeviceControllerManager@@QEAAKPEAX@Z`
- size: `1099`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection, void *)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config`

## callers

- `0x180007570`

## callees

- `0x180001e14`
- `0x180002268`
- `0x1800036dc`
- `0x18000752c`
- `0x18000a5e8`
- `0x18000c774`
- `0x18000d494`
- `0x18000d540`
- `0x18000d7bc`
- `0x1800130dc`
- `0x180014d58`
- `0x180014ee0`
- `0x180015660`
- `0x180015c9d`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180001e51`
- `KERNEL32!EnterCriticalSection` at `0x180001e51`
- `KERNEL32!LeaveCriticalSection` at `0x180002227`
- `KERNEL32!LeaveCriticalSection` at `0x180002227`
- `KERNEL32!GetCurrentThreadId` at `0x180001f01`
- `KERNEL32!GetCurrentThreadId` at `0x180001f01`
- `KERNEL32!FreeLibrary` at `0x18000221e`
- `KERNEL32!FreeLibrary` at `0x18000221e`
- `WDSSRV!WdsEndpointOpen` at `0x180001fd4`
- `WDSSRV!WdsEndpointOpen` at `0x18000206b`
- `WDSSRV!WdsEndpointOpen` at `0x180001fd4`
- `WDSSRV!WdsEndpointOpen` at `0x18000206b`
- `ole32!CoInitializeEx` at `0x180001f11`
- `ole32!CoInitializeEx` at `0x180001f11`

## pseudocode

```c
__int64 __fastcall CWdsDeviceControllerManager::Initialize(LPCRITICAL_SECTION lpCriticalSection, void *a2)
{
  unsigned int v4; // edx
  HRESULT ProvidersFromRegistry; // edi
  const char *v6; // rdx
  const char *v7; // rdx
  const char *v8; // rdx
  HANDLE OwningThread; // rcx
  const char *v10; // rdx
  HANDLE v11; // rcx
  const char *v12; // rdx
  const char *v13; // rdx
  const char *v14; // rdx
  const unsigned __int16 *v15; // rdx
  const char *v16; // rdx
  const unsigned __int16 *v17; // r8
  int v18; // r9d
  const char *v19; // rdx
  unsigned int v20; // ebx
  const char *v21; // rdx
  struct _GUID *v23; // [rsp+28h] [rbp-E0h]
  int v24[2]; // [rsp+58h] [rbp-B0h] BYREF
  HMODULE hLibModule[2]; // [rsp+60h] [rbp-A8h] BYREF
  _QWORD v26[3]; // [rsp+70h] [rbp-98h] BYREF
  _QWORD v27[10]; // [rsp+88h] [rbp-80h] BYREF
  _QWORD v28[10]; // [rsp+D8h] [rbp-30h] BYREF
  _QWORD v29[10]; // [rsp+128h] [rbp+20h] BYREF
  _DWORD v30[3]; // [rsp+178h] [rbp+70h] BYREF
  GUID v31; // [rsp+184h] [rbp+7Ch]
  _DWORD v32[3]; // [rsp+598h] [rbp+490h] BYREF
  GUID v33; // [rsp+5A4h] [rbp+49Ch]
  int v34; // [rsp+9B8h] [rbp+8B0h] BYREF
  _QWORD v35[7]; // [rsp+9C0h] [rbp+8B8h] BYREF
  int v36; // [rsp+9F8h] [rbp+8F0h] BYREF
  _DWORD v37[14]; // [rsp+A00h] [rbp+8F8h] BYREF
  unsigned int (__fastcall *v38)(void *, void *, struct tagWDS_ENDPOINT *, struct tagWDS_ENDPOINT *, void *, unsigned int); // [rsp+A38h] [rbp+930h]
  LPCRITICAL_SECTION v39; // [rsp+A40h] [rbp+938h]

  EnterCriticalSection(lpCriticalSection);
  memset_0(v30, 0, 0x41Cu);
  v34 = 0;
  memset_0(v35, 0, 0x30u);
  memset_0(v32, 0, 0x41Cu);
  v36 = 0;
  memset_0(v37, 0, 0x68u);
  hLibModule[0] = 0;
  hLibModule[1] = 0;
  v24[0] = 0;
  McGenEventRegister();
  lpCriticalSection[5].OwningThread = a2;
  ProvidersFromRegistry = CMRSWLock::Initialize((CMRSWLock *)&lpCriticalSection[1], v4);
  if ( ElValidateWin32(
         ProvidersFromRegistry,
         v6,
         "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp",
         0x94u) )
  {
    goto LABEL_19;
  }
  LODWORD(lpCriticalSection[6].DebugInfo) = 1;
  lpCriticalSection[8].RecursionCount = GetCurrentThreadId();
  ProvidersFromRegistry = CoInitializeEx(0, 0);
  if ( (int)ElValidateHr(
              ProvidersFromRegistry,
              v7,
              "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp",
              0x9Eu) < 0 )
  {
    if ( ProvidersFromRegistry < 0 && (ProvidersFromRegistry & 0x1FFF0000) == 0x70000 )
      ProvidersFromRegistry = (unsigned __int16)ProvidersFromRegistry;
    goto LABEL_19;
  }
  LODWORD(lpCriticalSection[8].OwningThread) = 1;
  ProvidersFromRegistry = CWdsDeviceControllerManager::LoadProvidersFromRegistry((CWdsDeviceControllerManager *)lpCriticalSection);
  if ( ElValidateWin32(
         ProvidersFromRegistry,
         v8,
         "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp",
         0xA3u) )
  {
    goto LABEL_19;
  }
  OwningThread = lpCriticalSection[5].OwningThread;
  v35[0] = CWdsDeviceControllerManager::_QueryRequest;
  v30[0] = 1052;
  v30[1] = 1;
  v30[2] = 3;
  v31 = WDSDCMGR_QUERY_ENDPOINT_GUID;
  v34 = 66567;
  v35[1] = lpCriticalSection;
  ProvidersFromRegistry = WdsEndpointOpen(OwningThread, v30, 1, &v34, &lpCriticalSection[5].LockSemaphore);
  if ( ElValidateWin32(
         ProvidersFromRegistry,
         v10,
         "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp",
         0xB7u) )
  {
    goto LABEL_19;
  }
  v11 = lpCriticalSection[5].OwningThread;
  v38 = CWdsDeviceControllerManager::_ManagementRequest;
  v32[0] = 1052;
  v32[1] = 1;
  v32[2] = 1;
  v33 = WDSDCMGR_MANAGEMENT_ENDPOINT_GUID;
  v36 = 197124;
  v37[0] = 1;
  v37[12] = 66567;
  v39 = lpCriticalSection;
  ProvidersFromRegistry = WdsEndpointOpen(v11, v32, 2, &v36, &lpCriticalSection[5].SpinCount);
  if ( ElValidateWin32(
         ProvidersFromRegistry,
         v12,
         "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp",
         0xCDu) )
  {
    goto LABEL_19;
  }
  ProvidersFromRegistry = CWdsMetadataStoreManagementClient::Initialize((CWdsMetadataStoreManagementClient *)hLibModule);
  if ( !ElValidateWin32(
          ProvidersFromRegistry,
          v13,
          "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp",
          0xD3u) )
  {
    *(_OWORD *)&v26[1] = xmmword_180018730;
    ProvidersFromRegistry = CWdsMetadataStoreManagementClient::CheckRegistration(
                              (CWdsMetadataStoreManagementClient *)hLibModule,
                              (struct _GUID *)&v26[1],
                              v24);
    if ( !ElValidateWin32(
            ProvidersFromRegistry,
            v14,
            "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp",
            0xD7u) )
    {
      if ( v24[0] )
        goto LABEL_15;
      v28[0] = 0;
      v28[1] = 0;
      v28[3] = 0;
      v28[4] = 0;
      v28[6] = 0;
      v28[7] = 0;
      v27[0] = 0;
      v27[1] = 0;
      v27[3] = 0;
      v27[4] = 0;
      v27[6] = 0;
      v27[7] = 0;
      v29[0] = 0;
      v29[1] = 0;
      v29[3] = 0;
      v29[4] = 0;
      v29[6] = 0;
      v29[7] = 0;
      ProvidersFromRegistry = CWdsMetadata::AppendExclusionFilter((CWdsMetadata *)v27, v15);
      if ( ElValidateWin32(
             ProvidersFromRegistry,
             v16,
             "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp",
             0xE6u) )
      {
        CWdsMetadata::~CWdsMetadata((CWdsMetadata *)v29);
        CWdsMetadata::~CWdsMetadata((CWdsMetadata *)v27);
        CWdsMetadata::~CWdsMetadata((CWdsMetadata *)v28);
        goto LABEL_17;
      }
      *(_OWORD *)&v26[1] = xmmword_180018730;
      ProvidersFromRegistry = CWdsMetadataStoreManagementClient::Register(
                                (CWdsMetadataStoreManagementClient *)hLibModule,
                                (struct _GUID *)&v26[1],
                                v17,
                                v18,
                                v23,
                                (const struct CWdsMetadata *)v28,
                                (const struct CWdsMetadata *)v28,
                                (const struct CWdsMetadata *)v27,
                                (const struct CWdsMetadata *)v29);
      v20 = ElValidateWin32(
              ProvidersFromRegistry,
              v19,
              "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp",
              0xF0u);
      CWdsMetadata::~CWdsMetadata((CWdsMetadata *)v29);
      CWdsMetadata::~CWdsMetadata((CWdsMetadata *)v27);
      CWdsMetadata::~CWdsMetadata((CWdsMetadata *)v28);
      if ( !v20 )
      {
LABEL_15:
        ProvidersFromRegistry = CWdsDeviceControllerManager::RefreshSettings(lpCriticalSection);
        if ( !ElValidateWin32(
                ProvidersFromRegistry,
                v21,
                "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicecontrollermanager.cpp",
                0xF8u) )
          lpCriticalSection[5].LockCount = 1;
      }
    }
  }
LABEL_17:
  if ( hLibModule[0] )
    FreeLibrary(hLibModule[0]);
LABEL_19:
  LeaveCriticalSection(lpCriticalSection);
  return (unsigned int)ProvidersFromRegistry;
}

```

## disassembly

```asm
0x180001e14  mov     rax, rsp
0x180001e17  mov     [rax+10h], rbx
0x180001e1b  mov     [rax+18h], rsi
0x180001e1f  mov     [rax+20h], rdi
0x180001e23  push    rbp
0x180001e24  push    r12
0x180001e26  push    r13
0x180001e28  push    r14
0x180001e2a  push    r15
0x180001e2c  lea     rbp, [rax-998h]
0x180001e33  sub     rsp, 0A70h
0x180001e3a  mov     rax, cs:__security_cookie
0x180001e41  xor     rax, rsp
0x180001e44  mov     [rbp+990h+var_30], rax
0x180001e4b  mov     rbx, rdx
0x180001e4e  mov     rsi, rcx
0x180001e51  call    cs:__imp_EnterCriticalSection
0x180001e57  mov     r13d, 41Ch
0x180001e5d  lea     rcx, [rbp+990h+var_920]; void *
0x180001e61  mov     r8d, r13d; Size
0x180001e64  xor     edx, edx; Val
0x180001e66  call    memset_0
0x180001e6b  xor     r14d, r14d
0x180001e6e  lea     rcx, [rbp+990h+var_D8]; void *
0x180001e75  xor     edx, edx; Val
0x180001e77  mov     [rbp+990h+var_E0], r14d
0x180001e7e  lea     r8d, [r14+30h]; Size
0x180001e82  call    memset_0
0x180001e87  mov     r8d, r13d; Size
0x180001e8a  lea     rcx, [rbp+990h+var_500]; void *
0x180001e91  xor     edx, edx; Val
0x180001e93  call    memset_0
0x180001e98  xor     edx, edx; Val
0x180001e9a  mov     [rbp+990h+var_A0], r14d
0x180001ea1  lea     r8d, [r14+68h]; Size
0x180001ea5  lea     rcx, [rbp+990h+var_98]; void *
0x180001eac  call    memset_0
0x180001eb1  mov     [rsp+0A90h+hLibModule], r14
0x180001eb6  mov     [rsp+0A90h+var_A30], r14
0x180001ebb  mov     [rsp+0A90h+var_A40], r14d
0x180001ec0  call    McGenEventRegister
0x180001ec5  lea     rcx, [rsi+28h]; this
0x180001ec9  mov     [rsi+0D8h], rbx
0x180001ed0  call    ?Initialize@CMRSWLock@@QEAAKK@Z; CMRSWLock::Initialize(ulong)
0x180001ed5  lea     r15, aBaseEcoWdsWdss_1; "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\"...
0x180001edc  mov     r9d, 94h; unsigned int
0x180001ee2  mov     r8, r15; char *
0x180001ee5  mov     ecx, eax; unsigned int
0x180001ee7  mov     edi, eax
0x180001ee9  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180001eee  test    eax, eax
0x180001ef0  jnz     loc_180002224
0x180001ef6  lea     r12d, [r14+1]
0x180001efa  mov     [rsi+0F0h], r12d
0x180001f01  call    cs:__imp_GetCurrentThreadId
0x180001f07  xor     edx, edx; dwCoInit
0x180001f09  xor     ecx, ecx; pvReserved
0x180001f0b  mov     [rsi+14Ch], eax
0x180001f11  call    cs:__imp_CoInitializeEx
0x180001f17  mov     r9d, 9Eh; unsigned int
0x180001f1d  mov     r8, r15; char *
0x180001f20  mov     ecx, eax; int
0x180001f22  mov     edi, eax
0x180001f24  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x180001f29  test    eax, eax
0x180001f2b  jns     short loc_180001F4F
0x180001f2d  test    edi, edi
0x180001f2f  jns     loc_180002224
0x180001f35  mov     eax, edi
0x180001f37  and     eax, 1FFF0000h
0x180001f3c  cmp     eax, 70000h
0x180001f41  jnz     loc_180002224
0x180001f47  movzx   edi, di
0x180001f4a  jmp     loc_180002224
0x180001f4f  mov     rcx, rsi; this
0x180001f52  mov     [rsi+150h], r12d
0x180001f59  call    ?LoadProvidersFromRegistry@CWdsDeviceControllerManager@@AEAAKXZ; CWdsDeviceControllerManager::LoadProvidersFromRegistry(void)
0x180001f5e  mov     r9d, 0A3h; unsigned int
0x180001f64  mov     r8, r15; char *
0x180001f67  mov     ecx, eax; unsigned int
0x180001f69  mov     edi, eax
0x180001f6b  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180001f70  test    eax, eax
0x180001f72  jnz     loc_180002224
0x180001f78  movups  xmm0, xmmword ptr cs:?WDSDCMGR_QUERY_ENDPOINT_GUID@@3U_GUID@@B.Data1; _GUID const WDSDCMGR_QUERY_ENDPOINT_GUID ...
0x180001f7f  mov     rcx, [rsi+0D8h]
0x180001f86  lea     rax, ?_QueryRequest@CWdsDeviceControllerManager@@CAKPEAX0PEAUtagWDS_ENDPOINT@@10K@Z; CWdsDeviceControllerManager::_QueryRequest(void *,void *,tagWDS_ENDPOINT *,tagWDS_ENDPOINT *,void *,ulong)
0x180001f8d  mov     [rbp+990h+var_D8], rax
0x180001f94  lea     r9, [rbp+990h+var_E0]
0x180001f9b  lea     rax, [rsi+0E0h]
0x180001fa2  mov     [rbp+990h+var_920], r13d
0x180001fa6  mov     ebx, 10407h
0x180001fab  mov     [rsp+0A90h+var_A70], rax
0x180001fb0  mov     r8d, r12d
0x180001fb3  mov     [rbp+990h+var_91C], r12d
0x180001fb7  lea     rdx, [rbp+990h+var_920]
0x180001fbb  mov     [rbp+990h+var_918], 3
0x180001fc2  movdqu  [rbp+990h+var_914], xmm0
0x180001fc7  mov     [rbp+990h+var_E0], ebx
0x180001fcd  mov     [rbp+990h+var_D0], rsi
0x180001fd4  call    cs:__imp_WdsEndpointOpen
0x180001fda  mov     r9d, 0B7h; unsigned int
0x180001fe0  mov     r8, r15; char *
0x180001fe3  mov     ecx, eax; unsigned int
0x180001fe5  mov     edi, eax
0x180001fe7  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180001fec  test    eax, eax
0x180001fee  jnz     loc_180002224
0x180001ff4  movups  xmm0, xmmword ptr cs:?WDSDCMGR_MANAGEMENT_ENDPOINT_GUID@@3U_GUID@@B.Data1; _GUID const WDSDCMGR_MANAGEMENT_ENDPOINT_GUID ...
0x180001ffb  mov     rcx, [rsi+0D8h]
0x180002002  lea     rax, ?_ManagementRequest@CWdsDeviceControllerManager@@CAKPEAX0PEAUtagWDS_ENDPOINT@@10K@Z; CWdsDeviceControllerManager::_ManagementRequest(void *,void *,tagWDS_ENDPOINT *,tagWDS_ENDPOINT *,void *,ulong)
0x180002009  mov     [rbp+990h+var_60], rax
0x180002010  lea     r9, [rbp+990h+var_A0]
0x180002017  lea     rax, [rsi+0E8h]
0x18000201e  mov     [rbp+990h+var_500], r13d
0x180002025  mov     r8d, 2
0x18000202b  mov     [rsp+0A90h+var_A70], rax; struct _GUID *
0x180002030  lea     rdx, [rbp+990h+var_500]
0x180002037  mov     [rbp+990h+var_4FC], r12d
0x18000203e  mov     [rbp+990h+var_4F8], r12d
0x180002045  movdqu  [rbp+990h+var_4F4], xmm0
0x18000204d  mov     [rbp+990h+var_A0], 30204h
0x180002057  mov     [rbp+990h+var_98], r12d
0x18000205e  mov     [rbp+990h+var_68], ebx
0x180002064  mov     [rbp+990h+var_58], rsi
0x18000206b  call    cs:__imp_WdsEndpointOpen
0x180002071  mov     r9d, 0CDh; unsigned int
0x180002077  mov     r8, r15; char *
0x18000207a  mov     ecx, eax; unsigned int
0x18000207c  mov     edi, eax
0x18000207e  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180002083  test    eax, eax
0x180002085  jnz     loc_180002224
0x18000208b  lea     rcx, [rsp+0A90h+hLibModule]; this
0x180002090  call    ?Initialize@CWdsMetadataStoreManagementClient@@QEAAKXZ; CWdsMetadataStoreManagementClient::Initialize(void)
0x180002095  mov     r9d, 0D3h; unsigned int
0x18000209b  mov     r8, r15; char *
0x18000209e  mov     ecx, eax; unsigned int
0x1800020a0  mov     edi, eax
0x1800020a2  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x1800020a7  test    eax, eax
0x1800020a9  jnz     loc_180002214
0x1800020af  movups  xmm0, cs:xmmword_180018730
0x1800020b6  lea     r8, [rsp+0A90h+var_A40]; int *
0x1800020bb  lea     rdx, [rsp+0A90h+var_A28+8]; struct _GUID
0x1800020c0  lea     rcx, [rsp+0A90h+hLibModule]; this
0x1800020c5  movdqu  xmmword ptr [rsp+0A90h+var_A28+8], xmm0
0x1800020cb  call    ?CheckRegistration@CWdsMetadataStoreManagementClient@@QEAAKU_GUID@@PEAH@Z; CWdsMetadataStoreManagementClient::CheckRegistration(_GUID,int *)
0x1800020d0  mov     r9d, 0D7h; unsigned int
0x1800020d6  mov     r8, r15; char *
0x1800020d9  mov     ecx, eax; unsigned int
0x1800020db  mov     edi, eax
0x1800020dd  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x1800020e2  test    eax, eax
0x1800020e4  jnz     loc_180002214
0x1800020ea  cmp     [rsp+0A90h+var_A40], r14d
0x1800020ef  jnz     loc_1800021EF
0x1800020f5  lea     rcx, [rbp+990h+var_A10]; this
0x1800020f9  mov     [rbp+990h+var_9C0], r14
0x1800020fd  mov     [rbp+990h+var_9B8], r14
0x180002101  mov     [rbp+990h+var_9A8], r14
0x180002105  mov     [rbp+990h+var_9A0], r14
0x180002109  mov     [rbp+990h+var_990], r14
0x18000210d  mov     [rbp+990h+var_988], r14
0x180002111  mov     [rbp+990h+var_A10], r14
0x180002115  mov     [rbp+990h+var_A08], r14
0x180002119  mov     [rbp+990h+var_9F8], r14
0x18000211d  mov     [rbp+990h+var_9F0], r14
0x180002121  mov     [rbp+990h+var_9E0], r14
0x180002125  mov     [rbp+990h+var_9D8], r14
0x180002129  mov     [rbp+990h+var_970], r14
0x18000212d  mov     [rbp+990h+var_968], r14
0x180002131  mov     [rbp+990h+var_958], r14
0x180002135  mov     [rbp+990h+var_950], r14
0x180002139  mov     [rbp+990h+var_940], r14
0x18000213d  mov     [rbp+990h+var_938], r14
0x180002141  call    ?AppendExclusionFilter@CWdsMetadata@@QEAAKPEBG@Z; CWdsMetadata::AppendExclusionFilter(ushort const *)
0x180002146  mov     r9d, 0E6h; unsigned int
0x18000214c  mov     r8, r15; char *
0x18000214f  mov     ecx, eax; unsigned int
0x180002151  mov     edi, eax
0x180002153  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180002158  test    eax, eax
0x18000215a  jz      short loc_18000217C
0x18000215c  lea     rcx, [rbp+990h+var_970]; this
0x180002160  call    ??1CWdsMetadata@@QEAA@XZ; CWdsMetadata::~CWdsMetadata(void)
0x180002165  lea     rcx, [rbp+990h+var_A10]; this
0x180002169  call    ??1CWdsMetadata@@QEAA@XZ; CWdsMetadata::~CWdsMetadata(void)
0x18000216e  lea     rcx, [rbp+990h+var_9C0]; this
0x180002172  call    ??1CWdsMetadata@@QEAA@XZ; CWdsMetadata::~CWdsMetadata(void)
0x180002177  jmp     loc_180002214
0x18000217c  movups  xmm0, cs:xmmword_180018730
0x180002183  lea     rax, [rbp+990h+var_970]
0x180002187  mov     [rsp+0A90h+var_A50], rax; struct CWdsMetadata *
0x18000218c  lea     rdx, [rsp+0A90h+var_A28+8]; struct _GUID *
0x180002191  lea     rax, [rbp+990h+var_A10]
0x180002195  mov     [rsp+0A90h+var_A58], rax; struct CWdsMetadata *
0x18000219a  lea     rcx, [rsp+0A90h+hLibModule]; this
0x18000219f  lea     rax, [rbp+990h+var_9C0]
0x1800021a3  mov     [rsp+0A90h+var_A60], rax; struct CWdsMetadata *
0x1800021a8  lea     rax, [rbp+990h+var_9C0]
0x1800021ac  mov     [rsp+0A90h+var_A68], rax; struct CWdsMetadata *
0x1800021b1  movdqu  xmmword ptr [rsp+0A90h+var_A28+8], xmm0
0x1800021b7  call    ?Register@CWdsMetadataStoreManagementClient@@QEAAKU_GUID@@PEBGH0PEBVCWdsMetadata@@222@Z; CWdsMetadataStoreManagementClient::Register(_GUID,ushort const *,int,_GUID,CWdsMetadata const *,CWdsMetadata const *,CWdsMetadata const *,CWdsMetadata const *)
0x1800021bc  mov     r9d, 0F0h; unsigned int
0x1800021c2  mov     r8, r15; char *
0x1800021c5  mov     ecx, eax; unsigned int
0x1800021c7  mov     edi, eax
0x1800021c9  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x1800021ce  lea     rcx, [rbp+990h+var_970]; this
0x1800021d2  mov     ebx, eax
0x1800021d4  call    ??1CWdsMetadata@@QEAA@XZ; CWdsMetadata::~CWdsMetadata(void)
0x1800021d9  lea     rcx, [rbp+990h+var_A10]; this
0x1800021dd  call    ??1CWdsMetadata@@QEAA@XZ; CWdsMetadata::~CWdsMetadata(void)
0x1800021e2  lea     rcx, [rbp+990h+var_9C0]; this
0x1800021e6  call    ??1CWdsMetadata@@QEAA@XZ; CWdsMetadata::~CWdsMetadata(void)
0x1800021eb  test    ebx, ebx
0x1800021ed  jnz     short loc_180002214
0x1800021ef  mov     rcx, rsi; lpCriticalSection
0x1800021f2  call    ?RefreshSettings@CWdsDeviceControllerManager@@AEAAKXZ; CWdsDeviceControllerManager::RefreshSettings(void)
0x1800021f7  mov     r9d, 0F8h; unsigned int
0x1800021fd  mov     r8, r15; char *
0x180002200  mov     ecx, eax; unsigned int
0x180002202  mov     edi, eax
0x180002204  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180002209  test    eax, eax
0x18000220b  jnz     short loc_180002214
0x18000220d  mov     [rsi+0D0h], r12d
0x180002214  mov     rcx, [rsp+0A90h+hLibModule]; hLibModule
0x180002219  test    rcx, rcx
0x18000221c  jz      short loc_180002224
0x18000221e  call    cs:__imp_FreeLibrary
0x180002224  mov     rcx, rsi; lpCriticalSection
0x180002227  call    cs:__imp_LeaveCriticalSection
0x18000222d  mov     eax, edi
0x18000222f  mov     rcx, [rbp+990h+var_30]
0x180002236  xor     rcx, rsp; StackCookie
0x180002239  call    __security_check_cookie
0x18000223e  lea     r11, [rsp+0A90h+var_20]
0x180002246  mov     rbx, [r11+38h]
0x18000224a  mov     rsi, [r11+40h]
0x18000224e  mov     rdi, [r11+48h]
0x180002252  mov     rsp, r11
0x180002255  pop     r15
0x180002257  pop     r14
0x180002259  pop     r13
0x18000225b  pop     r12
0x18000225d  pop     rbp
0x18000225e  retn
```
