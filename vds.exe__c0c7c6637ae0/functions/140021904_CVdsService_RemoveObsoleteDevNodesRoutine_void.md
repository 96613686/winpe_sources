# CVdsService::RemoveObsoleteDevNodesRoutine(void)

- ea: `0x140021904`
- end: `0x140021b43`
- name: `?RemoveObsoleteDevNodesRoutine@CVdsService@@CAKXZ`
- size: `575`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x14003c0d0`

## callees

- `0x140021904`
- `0x140052e80`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140021988`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400219d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140021a7c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140021aac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140021af0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140021988`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400219d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140021a7c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140021aac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140021af0`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x140021979`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x140021979`
- `DEVOBJ!DevObjGetClassDevs` at `0x1400219cf`
- `DEVOBJ!DevObjGetClassDevs` at `0x1400219cf`
- `DEVOBJ!DevObjEnumDeviceInfo` at `0x140021a33`
- `DEVOBJ!DevObjEnumDeviceInfo` at `0x140021a33`
- `DEVOBJ!DevObjDeleteDevice` at `0x140021a6f`
- `DEVOBJ!DevObjDeleteDevice` at `0x140021a6f`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x140021ae6`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x140021ae6`
- `api-ms-win-devices-config-l1-1-1!CM_Get_DevNode_Status` at `0x140021a52`
- `api-ms-win-devices-config-l1-1-1!CM_Get_DevNode_Status` at `0x140021a52`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14002195f`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14002195f`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140021b20`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140021b20`
- `vdsutil!VdsTraceW` at `0x140021aa1`
- `vdsutil!VdsTraceW` at `0x140021ad8`
- `vdsutil!VdsTraceW` at `0x140021b15`
- `vdsutil!VdsTraceW` at `0x140021aa1`
- `vdsutil!VdsTraceW` at `0x140021ad8`
- `vdsutil!VdsTraceW` at `0x140021b15`

## string_xrefs

- `0x140021b0c`: `CVdsService::RemoveObsoleteDevNodesRoutine, 6, hr=%lX`
- `0x140021acf`: `CVdsService::RemoveObsoleteDevNodesRoutine, 4, hr=%lX`
- `0x1400219a4`: `CVdsService::RemoveObsoleteDevNodesRoutine, 2, hr=%lX`
- `0x140021a98`: `CVdsService::RemoveObsoleteDevNodesRoutine, 5, hr=%lX`
- `0x1400219f5`: `CVdsService::RemoveObsoleteDevNodesRoutine, 3, hr=%lX`
- `0x14002194f`: `CVdsService::RemoveObsoleteDevNodesRoutine`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 CVdsService::RemoveObsoleteDevNodesRoutine(void)
{
  __int64 DeviceInfoList; // rax
  __int64 v1; // rsi
  signed int LastError; // eax
  unsigned int v3; // ebx
  __int64 v4; // r8
  signed int v5; // eax
  __int64 v6; // r8
  unsigned int v7; // r15d
  int v8; // r14d
  CONFIGRET DevNode_Status; // eax
  signed int v10; // eax
  __int64 v11; // r8
  signed int v12; // eax
  __int64 v13; // r8
  signed int v14; // eax
  __int64 v15; // r8
  ULONG pulProblemNumber; // [rsp+30h] [rbp-29h] BYREF
  ULONG pulStatus; // [rsp+34h] [rbp-25h] BYREF
  _BYTE v19[16]; // [rsp+38h] [rbp-21h] BYREF
  __int128 v20; // [rsp+48h] [rbp-11h] BYREF
  DEVINST dnDevInst[4]; // [rsp+58h] [rbp-1h]
  __int128 v22; // [rsp+68h] [rbp+Fh]
  GUID v23; // [rsp+78h] [rbp+1Fh] BYREF

  pulStatus = 0;
  pulProblemNumber = 0;
  v20 = 0;
  *(_OWORD *)dnDevInst = 0;
  v22 = 0;
  v23 = GUID_DEVCLASS_VOLUME;
  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v19, 0x5Eu, "CVdsService::RemoveObsoleteDevNodesRoutine");
  DeviceInfoList = DevObjCreateDeviceInfoList(0, 0, 0, 0, 0);
  v1 = DeviceInfoList;
  if ( DeviceInfoList == -1 )
  {
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    else
      v4 = (unsigned int)LastError;
    VdsTraceW(0, L"CVdsService::RemoveObsoleteDevNodesRoutine, 2, hr=%lX", v4);
  }
  else
  {
    if ( (unsigned int)DevObjGetClassDevs(DeviceInfoList, &v23, 0, 0, 0, 0) )
    {
      v7 = 0;
      v3 = 0;
      v8 = 1;
      v20 = 0;
      *(_OWORD *)dnDevInst = 0;
      v22 = 0;
      LODWORD(v20) = 48;
      while ( v8 )
      {
        v8 = DevObjEnumDeviceInfo(v1, v7, &v20);
        if ( !v8 )
        {
          v12 = GetLastError();
          v3 = v12;
          if ( v12 != 259 )
          {
            if ( v12 > 0 )
              v13 = (unsigned __int16)v12 | 0x80070000;
            else
              v13 = (unsigned int)v12;
            VdsTraceW(0, L"CVdsService::RemoveObsoleteDevNodesRoutine, 4, hr=%lX", v13);
          }
          break;
        }
        ++v7;
        DevNode_Status = CM_Get_DevNode_Status(&pulStatus, &pulProblemNumber, dnDevInst[1], 0);
        if ( DevNode_Status == 13 || DevNode_Status == 37 )
        {
          v8 = DevObjDeleteDevice(v1, &v20, 0, 0);
          if ( !v8 )
          {
            v10 = GetLastError();
            v3 = v10;
            if ( v10 > 0 )
              v11 = (unsigned __int16)v10 | 0x80070000;
            else
              v11 = (unsigned int)v10;
            VdsTraceW(0, L"CVdsService::RemoveObsoleteDevNodesRoutine, 5, hr=%lX", v11);
          }
        }
      }
    }
    else
    {
      v5 = GetLastError();
      v3 = v5;
      if ( v5 > 0 )
        v6 = (unsigned __int16)v5 | 0x80070000;
      else
        v6 = (unsigned int)v5;
      VdsTraceW(0, L"CVdsService::RemoveObsoleteDevNodesRoutine, 3, hr=%lX", v6);
    }
    if ( v1 && !(unsigned int)DevObjDestroyDeviceInfoList(v1) )
    {
      v14 = GetLastError();
      v3 = v14;
      if ( v14 > 0 )
        v15 = (unsigned __int16)v14 | 0x80070000;
      else
        v15 = (unsigned int)v14;
      VdsTraceW(0, L"CVdsService::RemoveObsoleteDevNodesRoutine, 6, hr=%lX", v15);
    }
  }
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v19);
  return v3;
}

```

## disassembly

```asm
0x140021904  push    rbp
0x140021906  push    rbx
0x140021907  push    rsi
0x140021908  push    r14
0x14002190a  push    r15
0x14002190c  lea     rbp, [rsp-37h]
0x140021911  sub     rsp, 90h
0x140021918  mov     rax, cs:__security_cookie
0x14002191f  xor     rax, rsp
0x140021922  mov     [rbp+57h+var_28], rax
0x140021926  mov     [rbp+57h+pulStatus], 0
0x14002192d  mov     [rbp+57h+pulProblemNumber], 0
0x140021934  xorps   xmm0, xmm0
0x140021937  movups  [rbp+57h+var_68], xmm0
0x14002193b  movups  xmmword ptr [rbp+57h+dnDevInst], xmm0
0x14002193f  movups  [rbp+57h+var_48], xmm0
0x140021943  movups  xmm0, xmmword ptr cs:GUID_DEVCLASS_VOLUME.Data1
0x14002194a  movdqu  [rbp+57h+var_38], xmm0
0x14002194f  lea     r8, aCvdsserviceRem_29; "CVdsService::RemoveObsoleteDevNodesRout"...
0x140021956  mov     edx, 5Eh ; '^'
0x14002195b  lea     rcx, [rbp+57h+var_78]
0x14002195f  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x140021965  nop
0x140021966  mov     [rsp+0B0h+var_90], 0
0x14002196f  xor     r9d, r9d
0x140021972  xor     r8d, r8d
0x140021975  xor     edx, edx
0x140021977  xor     ecx, ecx
0x140021979  call    cs:__imp_DevObjCreateDeviceInfoList
0x14002197f  mov     rsi, rax
0x140021982  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140021986  jnz     short loc_1400219B0
0x140021988  call    cs:__imp_GetLastError
0x14002198e  mov     ebx, eax
0x140021990  test    eax, eax
0x140021992  jg      short loc_140021999
0x140021994  mov     r8d, eax
0x140021997  jmp     short loc_1400219A4
0x140021999  movzx   r8d, ax
0x14002199d  or      r8d, 80070000h
0x1400219a4  lea     rdx, aCvdsserviceRem_11; "CVdsService::RemoveObsoleteDevNodesRout"...
0x1400219ab  jmp     loc_140021B13
0x1400219b0  mov     [rsp+0B0h+var_88], 0
0x1400219b9  mov     [rsp+0B0h+var_90], 0
0x1400219c2  xor     r9d, r9d
0x1400219c5  xor     r8d, r8d
0x1400219c8  lea     rdx, [rbp+57h+var_38]
0x1400219cc  mov     rcx, rsi
0x1400219cf  call    cs:__imp_DevObjGetClassDevs
0x1400219d5  test    eax, eax
0x1400219d7  jnz     short loc_140021A01
0x1400219d9  call    cs:__imp_GetLastError
0x1400219df  mov     ebx, eax
0x1400219e1  test    eax, eax
0x1400219e3  jg      short loc_1400219EA
0x1400219e5  mov     r8d, eax
0x1400219e8  jmp     short loc_1400219F5
0x1400219ea  movzx   r8d, ax
0x1400219ee  or      r8d, 80070000h
0x1400219f5  lea     rdx, aCvdsserviceRem_31; "CVdsService::RemoveObsoleteDevNodesRout"...
0x1400219fc  jmp     loc_140021AD6
0x140021a01  xor     r15d, r15d
0x140021a04  xor     ebx, ebx
0x140021a06  lea     r14d, [r15+1]
0x140021a0a  xorps   xmm0, xmm0
0x140021a0d  movups  [rbp+57h+var_68], xmm0
0x140021a11  movups  xmmword ptr [rbp+57h+dnDevInst], xmm0
0x140021a15  movups  [rbp+57h+var_48], xmm0
0x140021a19  mov     dword ptr [rbp+57h+var_68], 30h ; '0'
0x140021a20  test    r14d, r14d
0x140021a23  jz      loc_140021ADE
0x140021a29  lea     r8, [rbp+57h+var_68]
0x140021a2d  mov     edx, r15d
0x140021a30  mov     rcx, rsi
0x140021a33  call    cs:__imp_DevObjEnumDeviceInfo
0x140021a39  mov     r14d, eax
0x140021a3c  test    eax, eax
0x140021a3e  jz      short loc_140021AAC
0x140021a40  inc     r15d
0x140021a43  xor     r9d, r9d; ulFlags
0x140021a46  mov     r8d, [rbp+57h+dnDevInst+4]; dnDevInst
0x140021a4a  lea     rdx, [rbp+57h+pulProblemNumber]; pulProblemNumber
0x140021a4e  lea     rcx, [rbp+57h+pulStatus]; pulStatus
0x140021a52  call    cs:__imp_CM_Get_DevNode_Status
0x140021a58  cmp     eax, 0Dh
0x140021a5b  jz      short loc_140021A62
0x140021a5d  cmp     eax, 25h ; '%'
0x140021a60  jnz     short loc_140021A20
0x140021a62  xor     r9d, r9d
0x140021a65  xor     r8d, r8d
0x140021a68  lea     rdx, [rbp+57h+var_68]
0x140021a6c  mov     rcx, rsi
0x140021a6f  call    cs:__imp_DevObjDeleteDevice
0x140021a75  mov     r14d, eax
0x140021a78  test    eax, eax
0x140021a7a  jnz     short loc_140021A20
0x140021a7c  call    cs:__imp_GetLastError
0x140021a82  mov     ebx, eax
0x140021a84  test    eax, eax
0x140021a86  jg      short loc_140021A8D
0x140021a88  mov     r8d, eax
0x140021a8b  jmp     short loc_140021A98
0x140021a8d  movzx   r8d, ax
0x140021a91  or      r8d, 80070000h
0x140021a98  lea     rdx, aCvdsserviceRem_19; "CVdsService::RemoveObsoleteDevNodesRout"...
0x140021a9f  xor     ecx, ecx
0x140021aa1  call    cs:__imp_VdsTraceW
0x140021aa7  jmp     loc_140021A20
0x140021aac  call    cs:__imp_GetLastError
0x140021ab2  mov     ebx, eax
0x140021ab4  cmp     eax, 103h
0x140021ab9  jz      short loc_140021ADE
0x140021abb  test    eax, eax
0x140021abd  jg      short loc_140021AC4
0x140021abf  mov     r8d, eax
0x140021ac2  jmp     short loc_140021ACF
0x140021ac4  movzx   r8d, ax
0x140021ac8  or      r8d, 80070000h
0x140021acf  lea     rdx, aCvdsserviceRem; "CVdsService::RemoveObsoleteDevNodesRout"...
0x140021ad6  xor     ecx, ecx
0x140021ad8  call    cs:__imp_VdsTraceW
0x140021ade  test    rsi, rsi
0x140021ae1  jz      short loc_140021B1C
0x140021ae3  mov     rcx, rsi
0x140021ae6  call    cs:__imp_DevObjDestroyDeviceInfoList
0x140021aec  test    eax, eax
0x140021aee  jnz     short loc_140021B1C
0x140021af0  call    cs:__imp_GetLastError
0x140021af6  mov     ebx, eax
0x140021af8  test    eax, eax
0x140021afa  jg      short loc_140021B01
0x140021afc  mov     r8d, eax
0x140021aff  jmp     short loc_140021B0C
0x140021b01  movzx   r8d, ax
0x140021b05  or      r8d, 80070000h
0x140021b0c  lea     rdx, aCvdsserviceRem_16; "CVdsService::RemoveObsoleteDevNodesRout"...
0x140021b13  xor     ecx, ecx
0x140021b15  call    cs:__imp_VdsTraceW
0x140021b1b  nop
0x140021b1c  lea     rcx, [rbp+57h+var_78]
0x140021b20  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x140021b26  mov     eax, ebx
0x140021b28  mov     rcx, [rbp+57h+var_28]
0x140021b2c  xor     rcx, rsp; StackCookie
0x140021b2f  call    __security_check_cookie
0x140021b34  add     rsp, 90h
0x140021b3b  pop     r15
0x140021b3d  pop     r14
0x140021b3f  pop     rsi
0x140021b40  pop     rbx
0x140021b41  pop     rbp
0x140021b42  retn
```
