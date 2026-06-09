# CEcsHostServiceModule::Run(ushort const *)

- ea: `0x18000f958`
- end: `0x18000fb20`
- name: `?Run@CEcsHostServiceModule@@AEAAXPEBG@Z`
- size: `456`
- prototype: `void __fastcall(CEcsHostServiceModule *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18000ded0`

## callees

- `0x180002ab0`
- `0x180003604`
- `0x180007e10`
- `0x18000a694`
- `0x18000f958`
- `0x1800112c0`
- `0x180011314`
- `0x18013e010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18000faf3`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18000faf3`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000fa28`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000fa28`

## string_xrefs

- `0x18000f9d6`: `CEcsHostServiceModule::Run`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CEcsHostServiceModule::Run(CEcsHostServiceModule *this, const unsigned __int16 *a2)
{
  _BYTE *v2; // rax
  char v3; // cl
  HRESULT Instance; // eax
  int v5; // eax
  __int64 v6; // r8
  HRESULT pExceptionObject; // [rsp+40h] [rbp+7h] BYREF
  HRESULT v8; // [rsp+48h] [rbp+Fh] BYREF
  int v9; // [rsp+4Ch] [rbp+13h]
  char v10; // [rsp+50h] [rbp+17h]
  const char *v11; // [rsp+58h] [rbp+1Fh]
  __int64 v12; // [rsp+60h] [rbp+27h]
  HANDLE Handles; // [rsp+68h] [rbp+2Fh] BYREF
  _BYTE v14[16]; // [rsp+70h] [rbp+37h] BYREF

  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) == 0 )
      goto LABEL_8;
    if ( *((_BYTE *)WPP_GLOBAL_Control + 65) >= 6u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 48, WPP_152c595f472e31f48642c74f47fa958e_Traceguids);
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
  v8 = 0;
  v9 = 896;
  v10 = v3;
  v11 = "CEcsHostServiceModule::Run";
  v12 = 0;
  Handles = hEvent;
  if ( ppv )
    ATL::AtlComPtrAssign(&ppv, 0);
  Instance = CoCreateInstance(&CLSID_ContextSwitcher, 0, 1u, &GUID_000001da_0000_0000_c000_000000000046, (LPVOID *)&ppv);
  v8 = Instance;
  if ( Instance < 0 )
  {
    HIWORD(v9) = 906;
    pExceptionObject = Instance;
    throw (long *)&pExceptionObject;
  }
  LOWORD(v9) = 906;
  v5 = ((__int64 (__fastcall *)(struct IUnknown *, __int64 (__fastcall *)(struct tagComCallData *), _QWORD, GUID *, int, _QWORD))ppv->lpVtbl[1].QueryInterface)(
         ppv,
         CEcsHostServiceModule::RegisterClassObjectsCallback,
         0,
         &IID_ICallbackWithNoReentrancyToApplicationSTA,
         3,
         0);
  v8 = v5;
  if ( v5 < 0 )
  {
    HIWORD(v9) = 912;
    pExceptionObject = v5;
    throw (long *)&pExceptionObject;
  }
  LOWORD(v9) = 912;
  if ( (Microsoft_Windows_WorkFoldersEnableBits & 1) != 0 )
    McGenEventWrite_EventWriteTransfer(&ECSHOST_Context, ECSHOST_EVENT_PROCESS_RUNNING, v6, 1, v14);
  WaitForMultipleObjects(1u, &Handles, 0, 0xFFFFFFFF);
  CEcsFunctionTracer::~CEcsFunctionTracer((CEcsFunctionTracer *)&v8);
}

```

## disassembly

```asm
0x18000f958  mov     [rsp-8+arg_0], rsi
0x18000f95d  push    rbp
0x18000f95e  lea     rbp, [rsp-57h]
0x18000f963  sub     rsp, 90h
0x18000f96a  mov     rax, cs:__security_cookie
0x18000f971  xor     rax, rsp
0x18000f974  mov     [rbp+57h+var_10], rax
0x18000f978  lea     rcx, WPP_GLOBAL_Control
0x18000f97f  mov     rax, cs:WPP_GLOBAL_Control
0x18000f986  cmp     rax, rcx
0x18000f989  jz      short loc_18000F9B3
0x18000f98b  test    byte ptr [rax+44h], 8
0x18000f98f  jz      short loc_18000F9C3
0x18000f991  cmp     byte ptr [rax+41h], 6
0x18000f995  jb      short loc_18000F9B3
0x18000f997  mov     edx, 30h ; '0'
0x18000f99c  lea     r8, WPP_152c595f472e31f48642c74f47fa958e_Traceguids
0x18000f9a3  mov     rcx, [rax+38h]
0x18000f9a7  call    WPP_SF_
0x18000f9ac  mov     rax, cs:WPP_GLOBAL_Control
0x18000f9b3  test    byte ptr [rax+44h], 8
0x18000f9b7  jz      short loc_18000F9C3
0x18000f9b9  cmp     byte ptr [rax+41h], 6
0x18000f9bd  jb      short loc_18000F9C3
0x18000f9bf  mov     cl, 1
0x18000f9c1  jmp     short loc_18000F9C5
0x18000f9c3  xor     cl, cl
0x18000f9c5  mov     [rbp+57h+var_48], 0
0x18000f9cc  mov     [rbp+57h+var_44], 380h
0x18000f9d3  mov     [rbp+57h+var_40], cl
0x18000f9d6  lea     rax, aCecshostservic; "CEcsHostServiceModule::Run"
0x18000f9dd  mov     [rbp+57h+var_38], rax
0x18000f9e1  mov     [rbp+57h+var_30], 0
0x18000f9e9  mov     rax, cs:hEvent
0x18000f9f0  mov     [rbp+57h+Handles], rax
0x18000f9f4  lea     rsi, ppv
0x18000f9fb  cmp     cs:ppv, 0
0x18000fa03  jz      short loc_18000FA0F
0x18000fa05  xor     edx, edx; struct IUnknown *
0x18000fa07  mov     rcx, rsi; struct IUnknown **
0x18000fa0a  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x18000fa0f  mov     [rsp+90h+ppv], rsi; ppv
0x18000fa14  lea     r9, _GUID_000001da_0000_0000_c000_000000000046; riid
0x18000fa1b  xor     edx, edx; pUnkOuter
0x18000fa1d  lea     r8d, [rdx+1]; dwClsContext
0x18000fa21  lea     rcx, CLSID_ContextSwitcher; rclsid
0x18000fa28  call    cs:__imp_CoCreateInstance
0x18000fa2e  mov     [rbp+57h+var_48], eax
0x18000fa31  mov     [rbp+57h+var_48], eax
0x18000fa34  mov     ecx, 38Ah
0x18000fa39  test    eax, eax
0x18000fa3b  jns     short loc_18000FA55
0x18000fa3d  mov     word ptr [rbp+57h+var_44+2], cx
0x18000fa41  mov     [rbp+57h+pExceptionObject], eax
0x18000fa44  lea     rdx, _TI1J; pThrowInfo
0x18000fa4b  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18000fa4f  call    _CxxThrowException_0
0x18000fa55  mov     word ptr [rbp+57h+var_44], cx
0x18000fa59  mov     rcx, cs:ppv
0x18000fa60  mov     rax, [rcx]
0x18000fa63  mov     [rsp+90h+var_68], 0
0x18000fa6c  mov     dword ptr [rsp+90h+ppv], 3
0x18000fa74  lea     r9, IID_ICallbackWithNoReentrancyToApplicationSTA
0x18000fa7b  xor     r8d, r8d
0x18000fa7e  lea     rdx, ?RegisterClassObjectsCallback@CEcsHostServiceModule@@CAJPEAUtagComCallData@@@Z; CEcsHostServiceModule::RegisterClassObjectsCallback(tagComCallData *)
0x18000fa85  mov     rax, [rax+18h]
0x18000fa89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fa8e  mov     [rbp+57h+var_48], eax
0x18000fa91  mov     [rbp+57h+var_48], eax
0x18000fa94  mov     ecx, 390h
0x18000fa99  test    eax, eax
0x18000fa9b  jns     short loc_18000FAB5
0x18000fa9d  mov     word ptr [rbp+57h+var_44+2], cx
0x18000faa1  mov     [rbp+57h+pExceptionObject], eax
0x18000faa4  lea     rdx, _TI1J; pThrowInfo
0x18000faab  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18000faaf  call    _CxxThrowException_0
0x18000fab5  mov     word ptr [rbp+57h+var_44], cx
0x18000fab9  test    byte ptr cs:Microsoft_Windows_WorkFoldersEnableBits, 1
0x18000fac0  jz      short loc_18000FAE4
0x18000fac2  lea     rax, [rbp+57h+var_20]
0x18000fac6  mov     [rsp+90h+ppv], rax
0x18000facb  mov     r9d, 1
0x18000fad1  lea     rdx, ECSHOST_EVENT_PROCESS_RUNNING
0x18000fad8  lea     rcx, ECSHOST_Context
0x18000fadf  call    McGenEventWrite_EventWriteTransfer
0x18000fae4  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x18000fae8  xor     r8d, r8d; bWaitAll
0x18000faeb  lea     rdx, [rbp+57h+Handles]; lpHandles
0x18000faef  lea     ecx, [r8+1]; nCount
0x18000faf3  call    cs:__imp_WaitForMultipleObjects
0x18000faf9  nop
0x18000fafa  lea     rcx, [rbp+57h+var_48]; this
0x18000fafe  call    ??1CEcsFunctionTracer@@QEAA@XZ; CEcsFunctionTracer::~CEcsFunctionTracer(void)
0x18000fb03  mov     rcx, [rbp+57h+var_10]
0x18000fb07  xor     rcx, rsp; StackCookie
0x18000fb0a  call    __security_check_cookie
0x18000fb0f  mov     rsi, [rsp+90h+arg_0]
0x18000fb17  add     rsp, 90h
0x18000fb1e  pop     rbp
0x18000fb1f  retn
```
