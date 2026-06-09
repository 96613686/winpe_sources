# _anonymous_namespace_::StartMonitoringTask_0

- ea: `0x140018050`
- end: `0x140018131`
- name: `_anonymous_namespace_::StartMonitoringTask_0`
- size: `225`
- prototype: `void()`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x14001f8b8`

## callees

- `0x140006338`
- `0x140017c78`
- `0x140018050`
- `0x14001f6b4`
- `0x140060f58`
- `0x140061310`
- `0x1400a8010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1400180d6`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1400180d6`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14001808d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14001808d`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x1400180ce`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x1400180ce`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void anonymous_namespace_::StartMonitoringTask_0()
{
  HRESULT v0; // ebx
  LPVOID v1; // rcx
  _BYTE pExceptionObject[56]; // [rsp+30h] [rbp-38h] BYREF
  int v3; // [rsp+70h] [rbp+8h] BYREF
  LPVOID ppv; // [rsp+78h] [rbp+10h] BYREF

  ComInitialize::ComInitialize(&v3, 2);
  ppv = 0;
  v0 = CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85, &ppv);
  if ( v0 < 0 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        30,
        &WPP_a6cd8b416fde3d696d6e4fad87c378e4_Traceguids,
        (unsigned int)v0);
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, v0);
    throw (ErrorCodeException *)pExceptionObject;
  }
  anonymous_namespace_::StartMonitoringTask((__int64)ppv);
  v1 = ppv;
  if ( ppv )
  {
    ppv = 0;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v1 + 16LL))(v1);
  }
  if ( (v3 & 0xFFFFFFFD) != 0 )
    RoUninitialize();
  else
    CoUninitialize();
}

```

## disassembly

```asm
0x140018050  push    rbx
0x140018052  sub     rsp, 60h
0x140018056  mov     edx, 2
0x14001805b  lea     rcx, [rsp+68h+arg_0]
0x140018060  call    ??0ComInitialize@@QEAA@W4ComApartment@ComApartments@@_N@Z; ComInitialize::ComInitialize(ComApartments::ComApartment,bool)
0x140018065  nop
0x140018066  mov     [rsp+68h+arg_8], 0
0x14001806f  lea     rax, [rsp+68h+arg_8]
0x140018074  mov     [rsp+68h+ppv], rax; ppv
0x140018079  lea     r9, _GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85; riid
0x140018080  xor     edx, edx; pUnkOuter
0x140018082  lea     r8d, [rdx+1]; dwClsContext
0x140018086  lea     rcx, CLSID_TaskScheduler; rclsid
0x14001808d  call    cs:__imp_CoCreateInstance
0x140018093  mov     ebx, eax
0x140018095  test    eax, eax
0x140018097  js      short loc_1400180E2
0x140018099  mov     rcx, [rsp+68h+arg_8]
0x14001809e  call    _anonymous_namespace___StartMonitoringTask
0x1400180a3  nop
0x1400180a4  mov     rcx, [rsp+68h+arg_8]
0x1400180a9  test    rcx, rcx
0x1400180ac  jz      short loc_1400180C4
0x1400180ae  mov     [rsp+68h+arg_8], 0
0x1400180b7  mov     rax, [rcx]
0x1400180ba  mov     rax, [rax+10h]
0x1400180be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400180c3  nop
0x1400180c4  test    [rsp+68h+arg_0], 0FFFFFFFDh
0x1400180cc  jz      short loc_1400180D6
0x1400180ce  call    cs:__imp_RoUninitialize
0x1400180d4  jmp     short loc_1400180DC
0x1400180d6  call    cs:__imp_CoUninitialize
0x1400180dc  add     rsp, 60h
0x1400180e0  pop     rbx
0x1400180e1  retn
0x1400180e2  lea     rax, WPP_GLOBAL_Control
0x1400180e9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400180f0  cmp     rcx, rax
0x1400180f3  jz      short loc_140018113
0x1400180f5  test    byte ptr [rcx+1Ch], 1
0x1400180f9  jz      short loc_140018113
0x1400180fb  mov     edx, 1Eh
0x140018100  mov     r9d, ebx
0x140018103  lea     r8, WPP_a6cd8b416fde3d696d6e4fad87c378e4_Traceguids
0x14001810a  mov     rcx, [rcx+10h]
0x14001810e  call    WPP_SF_d
0x140018113  mov     edx, ebx; int
0x140018115  lea     rcx, [rsp+68h+pExceptionObject]; this
0x14001811a  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x14001811f  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x140018126  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x14001812b  call    _CxxThrowException_0
```
