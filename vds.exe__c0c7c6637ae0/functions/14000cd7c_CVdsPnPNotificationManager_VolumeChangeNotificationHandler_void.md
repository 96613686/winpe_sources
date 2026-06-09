# CVdsPnPNotificationManager::VolumeChangeNotificationHandler(void *)

- ea: `0x14000cd7c`
- end: `0x14000cf5a`
- name: `?VolumeChangeNotificationHandler@CVdsPnPNotificationManager@@AEAAXPEAX@Z`
- size: `478`
- prototype: `void __fastcall(CVdsPnPNotificationManager *__hidden this, void *)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, service_task`

## callers

- `0x1400066a0`

## callees

- `0x140006a80`
- `0x14000cd7c`
- `0x14000cf60`
- `0x14000d0f0`
- `0x14000f930`
- `0x140028fc8`
- `0x14003c084`
- `0x14004fd20`
- `0x140052e46`
- `0x140052e80`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000cf10`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000cf10`
- `vdsutil!OpenDevice` at `0x14000ce04`
- `vdsutil!OpenDevice` at `0x14000ce04`
- `vdsutil!GetDeviceName` at `0x14000ce26`
- `vdsutil!GetDeviceName` at `0x14000ce26`
- `vdsutil!VdsHeapFree` at `0x14000cf1e`
- `vdsutil!VdsHeapFree` at `0x14000cf1e`
- `vdsutil!VdsTraceEx` at `0x14000ce40`
- `vdsutil!VdsTraceEx` at `0x14000ce78`
- `vdsutil!VdsTraceEx` at `0x14000ced7`
- `vdsutil!VdsTraceEx` at `0x14000cef9`
- `vdsutil!VdsTraceEx` at `0x14000ce40`
- `vdsutil!VdsTraceEx` at `0x14000ce78`
- `vdsutil!VdsTraceEx` at `0x14000ced7`
- `vdsutil!VdsTraceEx` at `0x14000cef9`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14000cdbd`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14000cdbd`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14000cf32`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14000cf32`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall CVdsPnPNotificationManager::VolumeChangeNotificationHandler(CVdsPnPNotificationManager *this, void *a2)
{
  unsigned __int16 *VolumeInMap; // rax
  const wchar_t *v5; // rdi
  int v6; // ebx
  int DeviceName; // eax
  int VolumeId; // eax
  unsigned int v9; // ecx
  int v10; // eax
  HANDLE ProcessHeap; // rax
  __int64 v12; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int16 *v13; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v14[16]; // [rsp+40h] [rbp-C0h] BYREF
  struct _GUID Buf1; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 v16[280]; // [rsp+60h] [rbp-A0h] BYREF

  CVdsCallTracer::CVdsCallTracer(
    (CVdsCallTracer *)v14,
    0x5Eu,
    "CVdsPnPNotificationManager::VolumeChangeNotificationHandler");
  VolumeInMap = CVdsPnPNotificationManager::FindVolumeInMap(this, a2);
  v5 = VolumeInMap;
  v13 = VolumeInMap;
  if ( VolumeInMap )
  {
    v12 = -1;
    Buf1 = 0;
    v6 = OpenDevice(VolumeInMap, 0, &v12);
    if ( !v6 )
    {
      DeviceName = GetDeviceName(v12, 0, 274, v16);
      v6 = DeviceName;
      if ( DeviceName )
        VdsTraceEx(94, 0, "CVdsPnPNotificationManager::VolumeChangeNotificationHandler, 1, error=%ld", DeviceName);
      CVdsHandleImpl<-1>::Close(&v12);
      if ( !v6 )
      {
        VolumeId = CVdsService::GetVolumeId(v16, &Buf1, 0);
        if ( VolumeId >= 0 )
        {
          if ( memcmp_0(&Buf1, &GUID_NULL, 0x10u) )
            CVdsService::SendVolumeNotification(v9, &Buf1);
        }
        else
        {
          VdsTraceEx(94, 0, "CVdsPnPNotificationManager::VolumeChangeNotificationHandler, 2, hr=%lX", VolumeId);
        }
        CVdsHandleImpl<-1>::~CVdsHandleImpl<-1>((void **)&v12);
        CVdsHeapPtr<_EXTEND_VOLUME_HANDLER_PARAMETER>::~CVdsHeapPtr<_EXTEND_VOLUME_HANDLER_PARAMETER>((__int64 *)&v13);
        goto LABEL_18;
      }
    }
    if ( v6 == 2 )
    {
      v10 = CVdsService::RemoveObsoleteDevNodes();
      if ( v10 < 0 )
        VdsTraceEx(94, 1, "CVdsPnPNotificationManager::VolumeChangeNotificationHandler, 3, hr=%lX", v10);
    }
    else
    {
      VdsTraceEx(94, 1, "VDS(0X02040015): failed to send volume change notification(%S): %X", v5, v6);
    }
    CVdsHandleImpl<-1>::~CVdsHandleImpl<-1>((void **)&v12);
  }
  if ( v5 )
  {
    ProcessHeap = GetProcessHeap();
    VdsHeapFree(ProcessHeap, 0, v5);
    v13 = 0;
  }
LABEL_18:
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v14);
}

```

## disassembly

```asm
0x14000cd7c  mov     [rsp-8+arg_10], rbx
0x14000cd81  push    rbp
0x14000cd82  push    rsi
0x14000cd83  push    rdi
0x14000cd84  lea     rbp, [rsp-1A0h]
0x14000cd8c  sub     rsp, 2A0h
0x14000cd93  mov     rax, cs:__security_cookie
0x14000cd9a  xor     rax, rsp
0x14000cd9d  mov     [rbp+1B0h+var_20], rax
0x14000cda4  mov     rdi, rdx
0x14000cda7  mov     rbx, rcx
0x14000cdaa  lea     r8, aCvdspnpnotific_27; "CVdsPnPNotificationManager::VolumeChang"...
0x14000cdb1  mov     esi, 5Eh ; '^'
0x14000cdb6  mov     edx, esi
0x14000cdb8  lea     rcx, [rsp+2B0h+var_270]
0x14000cdbd  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x14000cdc3  nop
0x14000cdc4  mov     [rsp+2B0h+var_278], 0
0x14000cdcd  mov     rdx, rdi; void *
0x14000cdd0  mov     rcx, rbx; this
0x14000cdd3  call    ?FindVolumeInMap@CVdsPnPNotificationManager@@AEAAPEAGPEAX@Z; CVdsPnPNotificationManager::FindVolumeInMap(void *)
0x14000cdd8  mov     rdi, rax
0x14000cddb  mov     [rsp+2B0h+var_278], rax
0x14000cde0  test    rax, rax
0x14000cde3  jz      loc_14000CF0B
0x14000cde9  mov     [rsp+2B0h+var_280], 0FFFFFFFFFFFFFFFFh
0x14000cdf2  xorps   xmm0, xmm0
0x14000cdf5  movups  [rsp+2B0h+Buf1], xmm0
0x14000cdfa  lea     r8, [rsp+2B0h+var_280]
0x14000cdff  xor     edx, edx
0x14000ce01  mov     rcx, rax
0x14000ce04  call    cs:__imp_OpenDevice
0x14000ce0a  mov     ebx, eax
0x14000ce0c  test    eax, eax
0x14000ce0e  jnz     loc_14000CEBD
0x14000ce14  lea     r9, [rsp+2B0h+var_250]
0x14000ce19  xor     edx, edx
0x14000ce1b  mov     r8d, 112h
0x14000ce21  mov     rcx, [rsp+2B0h+var_280]
0x14000ce26  call    cs:__imp_GetDeviceName
0x14000ce2c  mov     ebx, eax
0x14000ce2e  test    eax, eax
0x14000ce30  jz      short loc_14000CE46
0x14000ce32  mov     r9d, eax
0x14000ce35  lea     r8, aCvdspnpnotific_36; "CVdsPnPNotificationManager::VolumeChang"...
0x14000ce3c  xor     edx, edx
0x14000ce3e  mov     ecx, esi
0x14000ce40  call    cs:__imp_VdsTraceEx
0x14000ce46  lea     rcx, [rsp+2B0h+var_280]
0x14000ce4b  call    ?Close@?$CVdsHandleImpl@$0?0@@QEAAXXZ; CVdsHandleImpl<-1>::Close(void)
0x14000ce50  test    ebx, ebx
0x14000ce52  jnz     short loc_14000CEBD
0x14000ce54  xor     r8d, r8d; int *
0x14000ce57  lea     rdx, [rsp+2B0h+Buf1]; struct _GUID *
0x14000ce5c  lea     rcx, [rsp+2B0h+var_250]; unsigned __int16 *
0x14000ce61  call    ?GetVolumeId@CVdsService@@SAJPEAGPEAU_GUID@@PEAH@Z; CVdsService::GetVolumeId(ushort *,_GUID *,int *)
0x14000ce66  test    eax, eax
0x14000ce68  jns     short loc_14000CE80
0x14000ce6a  mov     r9d, eax
0x14000ce6d  lea     r8, aCvdspnpnotific_8; "CVdsPnPNotificationManager::VolumeChang"...
0x14000ce74  xor     edx, edx
0x14000ce76  mov     ecx, esi
0x14000ce78  call    cs:__imp_VdsTraceEx
0x14000ce7e  jmp     short loc_14000CEA6
0x14000ce80  mov     r8d, 10h; Size
0x14000ce86  lea     rdx, GUID_NULL; Buf2
0x14000ce8d  lea     rcx, [rsp+2B0h+Buf1]; Buf1
0x14000ce92  call    memcmp_0
0x14000ce97  test    eax, eax
0x14000ce99  jz      short loc_14000CEA6
0x14000ce9b  lea     rdx, [rsp+2B0h+Buf1]; struct _GUID *
0x14000cea0  call    ?SendVolumeNotification@CVdsService@@SAXKAEAU_GUID@@@Z; CVdsService::SendVolumeNotification(ulong,_GUID &)
0x14000cea5  nop
0x14000cea6  lea     rcx, [rsp+2B0h+var_280]
0x14000ceab  call    ??1?$CVdsHandleImpl@$0?0@@QEAA@XZ; CVdsHandleImpl<-1>::~CVdsHandleImpl<-1>(void)
0x14000ceb0  nop
0x14000ceb1  lea     rcx, [rsp+2B0h+var_278]
0x14000ceb6  call    ??1?$CVdsHeapPtr@U_EXTEND_VOLUME_HANDLER_PARAMETER@@@@QEAA@XZ; CVdsHeapPtr<_EXTEND_VOLUME_HANDLER_PARAMETER>::~CVdsHeapPtr<_EXTEND_VOLUME_HANDLER_PARAMETER>(void)
0x14000cebb  jmp     short loc_14000CF2D
0x14000cebd  cmp     ebx, 2
0x14000cec0  jz      short loc_14000CEDF
0x14000cec2  mov     [rsp+2B0h+var_290], ebx
0x14000cec6  mov     r9, rdi
0x14000cec9  lea     r8, aVds0x02040015F; "VDS(0X02040015): failed to send volume "...
0x14000ced0  mov     edx, 1
0x14000ced5  mov     ecx, esi
0x14000ced7  call    cs:__imp_VdsTraceEx
0x14000cedd  jmp     short loc_14000CF00
0x14000cedf  call    ?RemoveObsoleteDevNodes@CVdsService@@SAJXZ; CVdsService::RemoveObsoleteDevNodes(void)
0x14000cee4  test    eax, eax
0x14000cee6  jns     short loc_14000CF00
0x14000cee8  mov     r9d, eax
0x14000ceeb  lea     r8, aCvdspnpnotific_33; "CVdsPnPNotificationManager::VolumeChang"...
0x14000cef2  mov     edx, 1
0x14000cef7  mov     ecx, esi
0x14000cef9  call    cs:__imp_VdsTraceEx
0x14000ceff  nop
0x14000cf00  lea     rcx, [rsp+2B0h+var_280]
0x14000cf05  call    ??1?$CVdsHandleImpl@$0?0@@QEAA@XZ; CVdsHandleImpl<-1>::~CVdsHandleImpl<-1>(void)
0x14000cf0a  nop
0x14000cf0b  test    rdi, rdi
0x14000cf0e  jz      short loc_14000CF2D
0x14000cf10  call    cs:__imp_GetProcessHeap
0x14000cf16  mov     r8, rdi
0x14000cf19  xor     edx, edx
0x14000cf1b  mov     rcx, rax
0x14000cf1e  call    cs:__imp_VdsHeapFree
0x14000cf24  mov     [rsp+2B0h+var_278], 0
0x14000cf2d  lea     rcx, [rsp+2B0h+var_270]
0x14000cf32  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x14000cf38  mov     rcx, [rbp+1B0h+var_20]
0x14000cf3f  xor     rcx, rsp; StackCookie
0x14000cf42  call    __security_check_cookie
0x14000cf47  mov     rbx, [rsp+2B0h+arg_10]
0x14000cf4f  add     rsp, 2A0h
0x14000cf56  pop     rdi
0x14000cf57  pop     rsi
0x14000cf58  pop     rbp
0x14000cf59  retn
```
