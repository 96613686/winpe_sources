# CSdRestoreServiceModule::Initialize(void)

- ea: `0x18000ac34`
- end: `0x18000add7`
- name: `?Initialize@CSdRestoreServiceModule@@AEAAJXZ`
- size: `419`
- prototype: `__int64 __fastcall(CSdRestoreServiceModule *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000d0a0`

## callees

- `0x18000ac34`
- `0x18000ade0`
- `0x18000be4c`
- `0x18000e108`
- `0x18001586c`
- `0x180015974`
- `0x18001c58c`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ad54`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ad54`
- `api-ms-win-core-synch-l1-2-1!CreateWaitableTimerW` at `0x18000ad3a`
- `api-ms-win-core-synch-l1-2-1!CreateWaitableTimerW` at `0x18000ad3a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000acc6`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000acc6`

## string_xrefs

- `0x18000ac50`: `CSdRestoreServiceModule::Initialize`

## pseudocode

```c
__int64 __fastcall CSdRestoreServiceModule::Initialize(CSdRestoreServiceModule *this)
{
  CSdRestoreServiceModule *v1; // rcx
  CSdRestoreServiceModule *v2; // rcx
  HRESULT inited; // ebx
  __int16 v4; // ax
  HANDLE WaitableTimerW; // rax
  unsigned int v6; // edx
  unsigned int v7; // r8d
  ATL::CComModule *v8; // rcx
  void *v9; // rbx
  HRESULT v11; // [rsp+30h] [rbp-40h] BYREF
  __int16 v12; // [rsp+34h] [rbp-3Ch]
  __int16 v13; // [rsp+36h] [rbp-3Ah]
  LPVOID ppv; // [rsp+80h] [rbp+10h] BYREF

  ppv = this;
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v11, "CSdRestoreServiceModule::Initialize", 537, 1);
  ppv = 0;
  inited = CSdRestoreServiceModule::InitializeCOM(v1, 0);
  v11 = inited;
  v4 = 541;
  if ( inited < 0 )
    goto LABEL_2;
  v12 = 541;
  inited = CSdRestoreServiceModule::_InitComSecurity(v2);
  v11 = inited;
  v4 = 543;
  if ( inited < 0 )
    goto LABEL_2;
  v12 = 543;
  inited = CoCreateInstance(&CLSID_GlobalOptions, 0, 1u, &IID_IGlobalOptions, &ppv);
  v11 = inited;
  v4 = 549;
  if ( inited < 0 )
    goto LABEL_2;
  v12 = 549;
  inited = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64))(*(_QWORD *)ppv + 24LL))(ppv, 1, 1);
  v11 = inited;
  v4 = 550;
  if ( inited < 0 )
    goto LABEL_2;
  v12 = 550;
  inited = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64))(*(_QWORD *)ppv + 24LL))(ppv, 5, 1);
  v11 = inited;
  v4 = 551;
  if ( inited < 0 )
    goto LABEL_2;
  v12 = 551;
  WaitableTimerW = CreateWaitableTimerW(0, 1, 0);
  v8 = (ATL::CComModule *)hTimer;
  v9 = WaitableTimerW;
  if ( (char *)hTimer - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(hTimer);
  hTimer = v9;
  if ( !v9 )
  {
    inited = GetLastFailureAsHRESULT(v8);
    v11 = inited;
    v4 = 555;
LABEL_2:
    v13 = v4;
    goto LABEL_13;
  }
  v11 = 0;
  v12 = 555;
  inited = ATL::CComModule::RegisterClassObjects(v8, v6, v7);
  v11 = inited;
  v4 = 558;
  if ( inited < 0 )
    goto LABEL_2;
  v12 = 558;
LABEL_13:
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v11);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x18000ac34  mov     [rsp-8+arg_8], rbx
0x18000ac39  mov     [rsp-8+arg_10], rdi
0x18000ac3e  mov     [rsp-8+arg_0], rcx
0x18000ac43  push    rbp
0x18000ac44  mov     rbp, rsp
0x18000ac47  sub     rsp, 70h
0x18000ac4b  mov     edi, 1
0x18000ac50  lea     rdx, aCsdrestoreserv_0; "CSdRestoreServiceModule::Initialize"
0x18000ac57  mov     r9d, edi; unsigned __int16
0x18000ac5a  lea     rcx, [rbp+var_40]; this
0x18000ac5e  mov     r8d, 219h; unsigned __int16
0x18000ac64  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18000ac69  xor     edx, edx; int
0x18000ac6b  mov     [rbp+arg_0], 0
0x18000ac73  call    ?InitializeCOM@CSdRestoreServiceModule@@QEAAJH@Z; CSdRestoreServiceModule::InitializeCOM(int)
0x18000ac78  mov     ebx, eax
0x18000ac7a  mov     [rbp+var_40], eax
0x18000ac7d  test    eax, eax
0x18000ac7f  mov     eax, 21Dh
0x18000ac84  jns     short loc_18000AC8F
0x18000ac86  mov     [rbp+var_3A], ax
0x18000ac8a  jmp     loc_18000ADA5
0x18000ac8f  mov     [rbp+var_3C], ax
0x18000ac93  call    ?_InitComSecurity@CSdRestoreServiceModule@@AEAAJXZ; CSdRestoreServiceModule::_InitComSecurity(void)
0x18000ac98  mov     ebx, eax
0x18000ac9a  mov     [rbp+var_40], eax
0x18000ac9d  test    eax, eax
0x18000ac9f  mov     eax, 21Fh
0x18000aca4  js      short loc_18000AC86
0x18000aca6  mov     [rbp+var_3C], ax
0x18000acaa  lea     r9, IID_IGlobalOptions; riid
0x18000acb1  lea     rax, [rbp+arg_0]
0x18000acb5  mov     r8d, edi; dwClsContext
0x18000acb8  xor     edx, edx; pUnkOuter
0x18000acba  mov     [rsp+70h+ppv], rax; ppv
0x18000acbf  lea     rcx, CLSID_GlobalOptions; rclsid
0x18000acc6  call    cs:__imp_CoCreateInstance
0x18000accc  mov     ebx, eax
0x18000acce  mov     [rbp+var_40], eax
0x18000acd1  test    eax, eax
0x18000acd3  mov     eax, 225h
0x18000acd8  js      short loc_18000AC86
0x18000acda  mov     rcx, [rbp+arg_0]
0x18000acde  mov     r8, rdi
0x18000ace1  mov     [rbp+var_3C], ax
0x18000ace5  mov     edx, edi
0x18000ace7  mov     rax, [rcx]
0x18000acea  mov     rax, [rax+18h]
0x18000acee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000acf3  mov     ebx, eax
0x18000acf5  mov     [rbp+var_40], eax
0x18000acf8  test    eax, eax
0x18000acfa  mov     eax, 226h
0x18000acff  js      short loc_18000AC86
0x18000ad01  mov     rcx, [rbp+arg_0]
0x18000ad05  mov     r8, rdi
0x18000ad08  mov     [rbp+var_3C], ax
0x18000ad0c  mov     edx, 5
0x18000ad11  mov     rax, [rcx]
0x18000ad14  mov     rax, [rax+18h]
0x18000ad18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ad1d  mov     ebx, eax
0x18000ad1f  mov     [rbp+var_40], eax
0x18000ad22  test    eax, eax
0x18000ad24  mov     eax, 227h
0x18000ad29  js      loc_18000AC86
0x18000ad2f  xor     r8d, r8d; lpTimerName
0x18000ad32  mov     [rbp+var_3C], ax
0x18000ad36  mov     edx, edi; bManualReset
0x18000ad38  xor     ecx, ecx; lpTimerAttributes
0x18000ad3a  call    cs:__imp_CreateWaitableTimerW
0x18000ad40  mov     rcx, cs:hTimer; hObject
0x18000ad47  mov     rbx, rax
0x18000ad4a  lea     rax, [rcx-1]
0x18000ad4e  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000ad52  ja      short loc_18000AD5A
0x18000ad54  call    cs:__imp_CloseHandle
0x18000ad5a  mov     cs:hTimer, rbx
0x18000ad61  test    rbx, rbx
0x18000ad64  jnz     short loc_18000AD7A
0x18000ad66  call    GetLastFailureAsHRESULT
0x18000ad6b  mov     ebx, eax
0x18000ad6d  mov     [rbp+var_40], eax
0x18000ad70  mov     eax, 22Bh
0x18000ad75  jmp     loc_18000AC86
0x18000ad7a  mov     eax, 22Bh
0x18000ad7f  mov     [rbp+var_40], 0
0x18000ad86  mov     [rbp+var_3C], ax
0x18000ad8a  call    ?RegisterClassObjects@CComModule@ATL@@QEAAJKK@Z; ATL::CComModule::RegisterClassObjects(ulong,ulong)
0x18000ad8f  mov     ebx, eax
0x18000ad91  mov     [rbp+var_40], eax
0x18000ad94  test    eax, eax
0x18000ad96  mov     eax, 22Eh
0x18000ad9b  js      loc_18000AC86
0x18000ada1  mov     [rbp+var_3C], ax
0x18000ada5  mov     rcx, [rbp+arg_0]
0x18000ada9  test    rcx, rcx
0x18000adac  jz      short loc_18000ADBA
0x18000adae  mov     rdx, [rcx]
0x18000adb1  mov     rax, [rdx+10h]
0x18000adb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000adba  lea     rcx, [rbp+var_40]; this
0x18000adbe  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18000adc3  lea     r11, [rsp+70h+var_s0]
0x18000adc8  mov     eax, ebx
0x18000adca  mov     rbx, [r11+18h]
0x18000adce  mov     rdi, [r11+20h]
0x18000add2  mov     rsp, r11
0x18000add5  pop     rbp
0x18000add6  retn
```
