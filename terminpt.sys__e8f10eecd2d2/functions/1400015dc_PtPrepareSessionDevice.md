# PtPrepareSessionDevice

- ea: `0x1400015dc`
- end: `0x14000171c`
- name: `PtPrepareSessionDevice`
- size: `320`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1400092f0`

## callees

- `0x1400015dc`
- `0x14000173c`
- `0x1400017e8`
- `0x140001a80`
- `0x140002a7c`

## import_xrefs

- `ntoskrnl!IoGetDevicePropertyData` at `0x14000166b`
- `ntoskrnl!IoGetDevicePropertyData` at `0x14000166b`

## pseudocode

```c
__int64 __fastcall PtPrepareSessionDevice(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v4; // rdx
  int DevicePropertyData; // ebx
  __int64 v6; // r8
  PVOID Data; // [rsp+28h] [rbp-30h]
  int v9; // [rsp+60h] [rbp+8h] BYREF
  ULONG Type; // [rsp+68h] [rbp+10h] BYREF
  ULONG RequiredSize; // [rsp+70h] [rbp+18h] BYREF

  v9 = 0;
  RequiredSize = 0;
  Type = 0;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_s(
      (__int64)WPP_GLOBAL_Control->DeviceExtension,
      a2,
      a3,
      0x31u,
      (__int64)WPP_75fd79d40e58354b8c24f648881272a9_Traceguids);
  DevicePropertyData = IoGetDevicePropertyData(
                         *(PDEVICE_OBJECT *)(a1 + 16),
                         &P_DEVPKEY_Device_SessionId,
                         0,
                         0,
                         4u,
                         &v9,
                         &RequiredSize,
                         &Type);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_sD(
      (__int64)WPP_GLOBAL_Control->DeviceExtension,
      v4,
      v6,
      0x32u,
      (__int64)WPP_75fd79d40e58354b8c24f648881272a9_Traceguids,
      (__int64)Data);
  if ( DevicePropertyData >= 0 )
  {
    DevicePropertyData = TiAddDeviceToSession(v9, (_QWORD *)a1, v6);
    if ( DevicePropertyData < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        return (unsigned int)DevicePropertyData;
      WPP_RECORDER_SF_s(
        (__int64)WPP_GLOBAL_Control->DeviceExtension,
        v4,
        v6,
        0x33u,
        (__int64)WPP_75fd79d40e58354b8c24f648881272a9_Traceguids);
    }
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_sqd(
      (__int64)WPP_GLOBAL_Control->DeviceExtension,
      v4,
      v6,
      0x34u,
      (__int64)WPP_75fd79d40e58354b8c24f648881272a9_Traceguids,
      (__int64)Data);
  return (unsigned int)DevicePropertyData;
}

```

## disassembly

```asm
0x1400015dc  mov     rax, rsp
0x1400015df  mov     [rax+20h], rbx
0x1400015e3  push    rbp
0x1400015e4  push    rdi
0x1400015e5  push    r14
0x1400015e7  sub     rsp, 40h
0x1400015eb  mov     rdi, rcx
0x1400015ee  mov     dword ptr [rax+8], 0
0x1400015f5  mov     dword ptr [rax+18h], 0
0x1400015fc  mov     dword ptr [rax+10h], 0
0x140001603  lea     rbp, WPP_RECORDER_INITIALIZED
0x14000160a  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x140001611  lea     r14, WPP_75fd79d40e58354b8c24f648881272a9_Traceguids
0x140001618  jz      short loc_140001634
0x14000161a  mov     rcx, cs:WPP_GLOBAL_Control
0x140001621  mov     r9d, 31h ; '1'
0x140001627  mov     [rax-38h], r14
0x14000162b  mov     rcx, [rcx+40h]
0x14000162f  call    WPP_RECORDER_SF_s
0x140001634  mov     rcx, [rdi+10h]; Pdo
0x140001638  lea     rax, [rsp+58h+arg_8]
0x14000163d  mov     [rsp+58h+Type], rax; Type
0x140001642  lea     rdx, P_DEVPKEY_Device_SessionId; PropertyKey
0x140001649  lea     rax, [rsp+58h+arg_10]
0x14000164e  xor     r9d, r9d; Flags
0x140001651  mov     [rsp+58h+RequiredSize], rax; RequiredSize
0x140001656  xor     r8d, r8d; Lcid
0x140001659  lea     rax, [rsp+58h+arg_0]
0x14000165e  mov     [rsp+58h+Data], rax; Data
0x140001663  mov     [rsp+58h+Size], 4; Size
0x14000166b  call    cs:__imp_IoGetDevicePropertyData
0x140001672  nop     dword ptr [rax+rax+00h]
0x140001677  mov     ebx, eax
0x140001679  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x140001680  jz      short loc_1400016A1
0x140001682  mov     rcx, cs:WPP_GLOBAL_Control
0x140001689  mov     r9d, 32h ; '2'
0x14000168f  mov     dword ptr [rsp+58h+RequiredSize], eax
0x140001693  mov     qword ptr [rsp+58h+Size], r14
0x140001698  mov     rcx, [rcx+40h]
0x14000169c  call    WPP_RECORDER_SF_sD
0x1400016a1  test    ebx, ebx
0x1400016a3  js      short loc_1400016DB
0x1400016a5  mov     ecx, [rsp+58h+arg_0]
0x1400016a9  mov     rdx, rdi
0x1400016ac  call    TiAddDeviceToSession
0x1400016b1  mov     ebx, eax
0x1400016b3  test    eax, eax
0x1400016b5  jns     short loc_1400016DB
0x1400016b7  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x1400016be  jz      short loc_14000170B
0x1400016c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400016c7  mov     r9d, 33h ; '3'
0x1400016cd  mov     qword ptr [rsp+58h+Size], r14
0x1400016d2  mov     rcx, [rcx+40h]
0x1400016d6  call    WPP_RECORDER_SF_s
0x1400016db  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x1400016e2  jz      short loc_14000170B
0x1400016e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400016eb  mov     r9d, 34h ; '4'
0x1400016f1  mov     rax, [rdi]
0x1400016f4  mov     dword ptr [rsp+58h+Type], ebx
0x1400016f8  mov     [rsp+58h+RequiredSize], rax
0x1400016fd  mov     rcx, [rcx+40h]
0x140001701  mov     qword ptr [rsp+58h+Size], r14
0x140001706  call    WPP_RECORDER_SF_sqd
0x14000170b  mov     eax, ebx
0x14000170d  mov     rbx, [rsp+58h+arg_18]
0x140001712  add     rsp, 40h
0x140001716  pop     r14
0x140001718  pop     rdi
0x140001719  pop     rbp
0x14000171a  retn
```
