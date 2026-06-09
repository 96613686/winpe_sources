# CChangeTrackerWatcher::RefreshChangeTrackerEventIfNeeded(void)

- ea: `0x18003ed10`
- end: `0x18003efca`
- name: `?RefreshChangeTrackerEventIfNeeded@CChangeTrackerWatcher@@AEAAXXZ`
- size: `698`
- prototype: `void __fastcall(CChangeTrackerWatcher *__hidden this)`
- caller_count: `2`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x18003e9f0`
- `0x18003f0c0`

## callees

- `0x180003604`
- `0x180007e10`
- `0x180008b60`
- `0x180009158`
- `0x18000a694`
- `0x180011314`
- `0x18001133c`
- `0x18003e2ec`
- `0x18003e31c`
- `0x18003ed10`
- `0x1800644c4`
- `0x1800648c0`
- `0x1800649b4`
- `0x18013e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003efa9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003efa9`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003ee39`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003ee39`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall CChangeTrackerWatcher::RefreshChangeTrackerEventIfNeeded(struct IUnknown **this)
{
  _BYTE *v2; // rax
  char v3; // al
  struct IFileChangeTracker **v4; // rsi
  _QWORD *v5; // rcx
  __int64 v6; // rdx
  HRESULT Instance; // eax
  unsigned int v8; // edx
  __int64 v9; // rax
  __int64 v10; // rax
  struct IFileChangeTracker *v11; // r14
  struct IFileChangeTracker *ppv; // [rsp+30h] [rbp-D8h] BYREF
  int v13; // [rsp+38h] [rbp-D0h] BYREF
  int v14; // [rsp+3Ch] [rbp-CCh]
  char v15; // [rsp+40h] [rbp-C8h]
  const char *v16; // [rsp+48h] [rbp-C0h]
  __int64 v17; // [rsp+50h] [rbp-B8h]
  HRESULT pExceptionObject; // [rsp+58h] [rbp-B0h] BYREF
  struct IFileChangeTracker *v19; // [rsp+60h] [rbp-A8h] BYREF
  int v20; // [rsp+68h] [rbp-A0h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+70h] [rbp-98h] BYREF
  char v22; // [rsp+78h] [rbp-90h]
  const ATL::CAtlException *v23; // [rsp+80h] [rbp-88h] BYREF
  _BYTE v24[16]; // [rsp+88h] [rbp-80h] BYREF
  _BYTE v25[112]; // [rsp+98h] [rbp-70h] BYREF

  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) == 0 )
      goto LABEL_8;
    if ( *((_BYTE *)WPP_GLOBAL_Control + 65) >= 6u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 20, WPP_80060c42e9283c9fa2e2881e1fba40a3_Traceguids);
      v2 = WPP_GLOBAL_Control;
    }
  }
  if ( (v2[68] & 8) != 0 && v2[65] >= 6u )
  {
    v3 = 1;
    goto LABEL_9;
  }
LABEL_8:
  v3 = 0;
LABEL_9:
  v13 = 0;
  v14 = 172;
  v15 = v3;
  v16 = "CChangeTrackerWatcher::RefreshChangeTrackerEventIfNeeded";
  v17 = 0;
  CEcsExclusiveLock<CEcsCriticalSection>::CEcsExclusiveLock<CEcsCriticalSection>(&lpCriticalSection, this + 10);
  v4 = (struct IFileChangeTracker **)(this + 5);
  if ( !this[5] )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 65) < 4u )
    {
      goto LABEL_47;
    }
    v6 = 21;
LABEL_19:
    WPP_SF_(v5[7], v6, WPP_80060c42e9283c9fa2e2881e1fba40a3_Traceguids);
LABEL_47:
    try
    {
      ppv = 0;
      if ( *v4 )
        ATL::AtlComPtrAssign(this + 5, 0);
      Instance = CoCreateInstance(
                   &GUID_69f31c37_09e1_433b_aecb_ebc83e4065d9,
                   0,
                   1u,
                   &GUID_5c4c1c61_6779_4c4b_9c8a_da2653ce628d,
                   (LPVOID *)&ppv);
      v13 = Instance;
      if ( Instance < 0 )
      {
        HIWORD(v14) = 204;
        pExceptionObject = Instance;
        throw (long *)&pExceptionObject;
      }
      LOWORD(v14) = 204;
      v19 = 0;
      CChangeTrackerHelper::SetCapabilityOnInternalProxy(ppv, v8, &v19);
      v9 = lambda_e802c6b1f0e27491514118d2a7dcc519_::_lambda_e802c6b1f0e27491514118d2a7dcc519_(v24, this, &v19);
      v10 = std::function_long___cdecl_void__::function_long___cdecl_void____lambda_8b5e89ed821ea6cd3284d8f6b733287d__0_(
              v25,
              v9);
      CChangeTrackerHelper::CallChangeTrackerWithRetry(v10);
      v11 = ppv;
      ppv = 0;
      if ( *v4 )
        (*(void (__fastcall **)(struct IFileChangeTracker *))(*(_QWORD *)*v4 + 16LL))(*v4);
      *v4 = v11;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 24, WPP_80060c42e9283c9fa2e2881e1fba40a3_Traceguids);
      }
      ATL::CComPtr<ICloudFileInfoFromDisk>::~CComPtr<ICloudFileInfoFromDisk>(&v19);
      ATL::CComPtr<ICloudFileInfoFromDisk>::~CComPtr<ICloudFileInfoFromDisk>(&ppv);
    }
    catch ( long v20 )
    {
      v13 = v20;
    }
    catch ( std::bad_alloc )
    {
      HIWORD(v14) = 224;
      v13 = -2147024882;
    }
    catch ( std::exception )
    {
      HIWORD(v14) = 224;
      v13 = -2147418113;
    }
    catch ( const ATL::CAtlException *v23 )
    {
      HIWORD(v14) = 224;
      v13 = *(_DWORD *)v23;
    }
    if ( v13 < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 25, WPP_80060c42e9283c9fa2e2881e1fba40a3_Traceguids);
    }
    goto LABEL_40;
  }
  if ( !CChangeTrackerHelper::IsChangeTrackerProxyConnected(*v4) )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 65) < 4u )
    {
      goto LABEL_47;
    }
    v6 = 22;
    goto LABEL_19;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 23, WPP_80060c42e9283c9fa2e2881e1fba40a3_Traceguids);
  }
LABEL_40:
  if ( v22 )
  {
    LeaveCriticalSection(lpCriticalSection);
    v22 = 0;
  }
  CEcsFunctionTracer::~CEcsFunctionTracer((CEcsFunctionTracer *)&v13);
}

```

## disassembly

```asm
0x18003ed10  push    rbx
0x18003ed12  push    rsi
0x18003ed13  push    rdi
0x18003ed14  push    r14
0x18003ed16  sub     rsp, 0E8h
0x18003ed1d  mov     r14, rcx
0x18003ed20  lea     rdi, WPP_GLOBAL_Control
0x18003ed27  mov     rax, cs:WPP_GLOBAL_Control
0x18003ed2e  cmp     rax, rdi
0x18003ed31  jz      short loc_18003ED5B
0x18003ed33  test    byte ptr [rax+44h], 8
0x18003ed37  jz      short loc_18003ED6D
0x18003ed39  cmp     byte ptr [rax+41h], 6
0x18003ed3d  jb      short loc_18003ED5B
0x18003ed3f  mov     edx, 14h
0x18003ed44  lea     r8, WPP_80060c42e9283c9fa2e2881e1fba40a3_Traceguids
0x18003ed4b  mov     rcx, [rax+38h]
0x18003ed4f  call    WPP_SF_
0x18003ed54  mov     rax, cs:WPP_GLOBAL_Control
0x18003ed5b  test    byte ptr [rax+44h], 8
0x18003ed5f  jz      short loc_18003ED6D
0x18003ed61  cmp     byte ptr [rax+41h], 6
0x18003ed65  jb      short loc_18003ED6D
0x18003ed67  mov     al, 1
0x18003ed69  xor     ebx, ebx
0x18003ed6b  jmp     short loc_18003ED71
0x18003ed6d  xor     ebx, ebx
0x18003ed6f  mov     al, bl
0x18003ed71  mov     [rsp+108h+var_D0], ebx
0x18003ed75  mov     [rsp+108h+var_CC], 0ACh
0x18003ed7d  mov     [rsp+108h+var_C8], al
0x18003ed81  lea     rax, aCchangetracker_1; "CChangeTrackerWatcher::RefreshChangeTra"...
0x18003ed88  mov     [rsp+108h+var_C0], rax
0x18003ed8d  mov     [rsp+108h+var_B8], rbx
0x18003ed92  lea     rdx, [r14+50h]
0x18003ed96  lea     rcx, [rsp+108h+lpCriticalSection]
0x18003ed9b  call    ??0?$CEcsExclusiveLock@VCEcsCriticalSection@@@@QEAA@AEAVCEcsCriticalSection@@_N@Z; CEcsExclusiveLock<CEcsCriticalSection>::CEcsExclusiveLock<CEcsCriticalSection>(CEcsCriticalSection &,bool)
0x18003eda0  nop
0x18003eda1  lea     rsi, [r14+28h]
0x18003eda5  cmp     [rsi], rbx
0x18003eda8  jnz     short loc_18003EDC9
0x18003edaa  mov     rcx, cs:WPP_GLOBAL_Control
0x18003edb1  cmp     rcx, rdi
0x18003edb4  jz      short loc_18003EE07
0x18003edb6  test    byte ptr [rcx+44h], 8
0x18003edba  jz      short loc_18003EE07
0x18003edbc  cmp     byte ptr [rcx+41h], 4
0x18003edc0  jb      short loc_18003EE07
0x18003edc2  mov     edx, 15h
0x18003edc7  jmp     short loc_18003EDF6
0x18003edc9  mov     rcx, [rsi]; struct IFileChangeTracker *
0x18003edcc  call    ?IsChangeTrackerProxyConnected@CChangeTrackerHelper@@SA_NPEAUIFileChangeTracker@@@Z; CChangeTrackerHelper::IsChangeTrackerProxyConnected(IFileChangeTracker *)
0x18003edd1  test    al, al
0x18003edd3  jnz     loc_18003EF70
0x18003edd9  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ede0  cmp     rcx, rdi
0x18003ede3  jz      short loc_18003EE07
0x18003ede5  test    byte ptr [rcx+44h], 8
0x18003ede9  jz      short loc_18003EE07
0x18003edeb  cmp     byte ptr [rcx+41h], 4
0x18003edef  jb      short loc_18003EE07
0x18003edf1  mov     edx, 16h
0x18003edf6  lea     r8, WPP_80060c42e9283c9fa2e2881e1fba40a3_Traceguids
0x18003edfd  mov     rcx, [rcx+38h]
0x18003ee01  call    WPP_SF_
0x18003ee06  nop
0x18003ee07  mov     [rsp+108h+var_D8], rbx
0x18003ee0c  cmp     [rsi], rbx
0x18003ee0f  jz      short loc_18003EE1B
0x18003ee11  xor     edx, edx; struct IUnknown *
0x18003ee13  mov     rcx, rsi; struct IUnknown **
0x18003ee16  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x18003ee1b  lea     rax, [rsp+108h+var_D8]
0x18003ee20  mov     [rsp+108h+ppv], rax; ppv
0x18003ee25  lea     r9, _GUID_5c4c1c61_6779_4c4b_9c8a_da2653ce628d; riid
0x18003ee2c  xor     edx, edx; pUnkOuter
0x18003ee2e  lea     r8d, [rdx+1]; dwClsContext
0x18003ee32  lea     rcx, _GUID_69f31c37_09e1_433b_aecb_ebc83e4065d9; rclsid
0x18003ee39  call    cs:__imp_CoCreateInstance
0x18003ee3f  mov     [rsp+108h+var_D0], eax
0x18003ee43  mov     [rsp+108h+var_D0], eax
0x18003ee47  mov     ecx, 0CCh
0x18003ee4c  test    eax, eax
0x18003ee4e  jns     short loc_18003EE6A
0x18003ee50  mov     word ptr [rsp+108h+var_CC+2], cx
0x18003ee55  mov     [rsp+108h+pExceptionObject], eax
0x18003ee59  lea     rdx, _TI1J; pThrowInfo
0x18003ee60  lea     rcx, [rsp+108h+pExceptionObject]; pExceptionObject
0x18003ee65  call    _CxxThrowException_0
0x18003ee6a  mov     word ptr [rsp+108h+var_CC], cx
0x18003ee6f  mov     [rsp+108h+var_A8], rbx
0x18003ee74  lea     r8, [rsp+108h+var_A8]; struct IFileChangeTracker **
0x18003ee79  mov     rcx, [rsp+108h+var_D8]; struct IFileChangeTracker *
0x18003ee7e  call    ?SetCapabilityOnInternalProxy@CChangeTrackerHelper@@SAXPEAUIFileChangeTracker@@KPEAPEAU2@@Z; CChangeTrackerHelper::SetCapabilityOnInternalProxy(IFileChangeTracker *,ulong,IFileChangeTracker * *)
0x18003ee83  lea     rax, [rsp+108h+var_70]
0x18003ee8b  mov     [rsp+108h+arg_0], rax
0x18003ee93  lea     r8, [rsp+108h+var_A8]
0x18003ee98  mov     rdx, r14
0x18003ee9b  lea     rcx, [rsp+108h+var_80]
0x18003eea3  call    _lambda_e802c6b1f0e27491514118d2a7dcc519____lambda_e802c6b1f0e27491514118d2a7dcc519_
0x18003eea8  mov     rdx, rax
0x18003eeab  lea     rcx, [rsp+108h+var_70]
0x18003eeb3  call    std__function_long___cdecl_void____function_long___cdecl_void____lambda_8b5e89ed821ea6cd3284d8f6b733287d__0_
0x18003eeb8  nop
0x18003eeb9  mov     rcx, rax
0x18003eebc  call    ?CallChangeTrackerWithRetry@CChangeTrackerHelper@@SAXV?$function@$$A6AJXZ@std@@@Z; CChangeTrackerHelper::CallChangeTrackerWithRetry(std::function<long (void)>)
0x18003eec1  mov     r14, [rsp+108h+var_D8]
0x18003eec6  mov     [rsp+108h+var_D8], rbx
0x18003eecb  mov     rcx, [rsi]
0x18003eece  test    rcx, rcx
0x18003eed1  jz      short loc_18003EEDF
0x18003eed3  mov     rax, [rcx]
0x18003eed6  mov     rax, [rax+10h]
0x18003eeda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003eedf  mov     [rsi], r14
0x18003eee2  mov     rcx, cs:WPP_GLOBAL_Control
0x18003eee9  cmp     rcx, rdi
0x18003eeec  jz      short loc_18003EF10
0x18003eeee  test    byte ptr [rcx+44h], 8
0x18003eef2  jz      short loc_18003EF10
0x18003eef4  cmp     byte ptr [rcx+41h], 4
0x18003eef8  jb      short loc_18003EF10
0x18003eefa  mov     edx, 18h
0x18003eeff  lea     r8, WPP_80060c42e9283c9fa2e2881e1fba40a3_Traceguids
0x18003ef06  mov     rcx, [rcx+38h]
0x18003ef0a  call    WPP_SF_
0x18003ef0f  nop
0x18003ef10  lea     rcx, [rsp+108h+var_A8]
0x18003ef15  call    ??1?$CComPtr@UICloudFileInfoFromDisk@@@ATL@@QEAA@XZ; ATL::CComPtr<ICloudFileInfoFromDisk>::~CComPtr<ICloudFileInfoFromDisk>(void)
0x18003ef1a  nop
0x18003ef1b  lea     rcx, [rsp+108h+var_D8]
0x18003ef20  call    ??1?$CComPtr@UICloudFileInfoFromDisk@@@ATL@@QEAA@XZ; ATL::CComPtr<ICloudFileInfoFromDisk>::~CComPtr<ICloudFileInfoFromDisk>(void)
0x18003ef25  nop
0x18003ef26  jmp     short loc_18003EF37
0x18003ef28  jmp     short loc_18003EF2E
0x18003ef2a  jmp     short loc_18003EF2E
0x18003ef2c  jmp     short $+2
0x18003ef2e  xor     ebx, ebx
0x18003ef30  lea     rdi, WPP_GLOBAL_Control
0x18003ef37  mov     r9d, [rsp+108h+var_D0]
0x18003ef3c  test    r9d, r9d
0x18003ef3f  jns     short loc_18003EF9E
0x18003ef41  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ef48  cmp     rcx, rdi
0x18003ef4b  jz      short loc_18003EF9E
0x18003ef4d  test    byte ptr [rcx+44h], 8
0x18003ef51  jz      short loc_18003EF9E
0x18003ef53  cmp     byte ptr [rcx+41h], 2
0x18003ef57  jb      short loc_18003EF9E
0x18003ef59  mov     edx, 19h
0x18003ef5e  lea     r8, WPP_80060c42e9283c9fa2e2881e1fba40a3_Traceguids
0x18003ef65  mov     rcx, [rcx+38h]
0x18003ef69  call    WPP_SF_d
0x18003ef6e  jmp     short loc_18003EF9E
0x18003ef70  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ef77  cmp     rcx, rdi
0x18003ef7a  jz      short loc_18003EF9E
0x18003ef7c  test    byte ptr [rcx+44h], 8
0x18003ef80  jz      short loc_18003EF9E
0x18003ef82  cmp     byte ptr [rcx+41h], 4
0x18003ef86  jb      short loc_18003EF9E
0x18003ef88  mov     edx, 17h
0x18003ef8d  lea     r8, WPP_80060c42e9283c9fa2e2881e1fba40a3_Traceguids
0x18003ef94  mov     rcx, [rcx+38h]
0x18003ef98  call    WPP_SF_
0x18003ef9d  nop
0x18003ef9e  cmp     [rsp+108h+var_90], bl
0x18003efa2  jz      short loc_18003EFB3
0x18003efa4  mov     rcx, [rsp+108h+lpCriticalSection]; lpCriticalSection
0x18003efa9  call    cs:__imp_LeaveCriticalSection
0x18003efaf  mov     [rsp+108h+var_90], bl
0x18003efb3  lea     rcx, [rsp+108h+var_D0]; this
0x18003efb8  call    ??1CEcsFunctionTracer@@QEAA@XZ; CEcsFunctionTracer::~CEcsFunctionTracer(void)
0x18003efbd  add     rsp, 0E8h
0x18003efc4  pop     r14
0x18003efc6  pop     rdi
0x18003efc7  pop     rsi
0x18003efc8  pop     rbx
0x18003efc9  retn
```
