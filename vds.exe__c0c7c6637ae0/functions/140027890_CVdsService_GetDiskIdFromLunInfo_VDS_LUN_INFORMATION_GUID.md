# CVdsService::GetDiskIdFromLunInfo(_VDS_LUN_INFORMATION *,_GUID *)

- ea: `0x140027890`
- end: `0x140027cd0`
- name: `?GetDiskIdFromLunInfo@CVdsService@@UEAAJPEAU_VDS_LUN_INFORMATION@@PEAU_GUID@@@Z`
- size: `1088`
- prototype: `__int64 __fastcall(CVdsService *__hidden this, struct _VDS_LUN_INFORMATION *, struct _GUID *)`
- caller_count: `0`
- callee_count: `12`
- tags: `service_task`

## callees

- `0x140003710`
- `0x140004360`
- `0x14001b958`
- `0x140021e60`
- `0x140025e20`
- `0x140027890`
- `0x14002cadc`
- `0x14002e123`
- `0x14003a80c`
- `0x14003d730`
- `0x140052e80`
- `0x140056010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140027c96`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140027c96`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140027942`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140027942`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140027a8f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140027c38`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140027a8f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140027c38`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140027991`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400279f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140027a56`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140027991`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400279f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140027a56`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x140027a49`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x140027a49`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x140027982`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x140027982`
- `DEVOBJ!DevObjGetClassDevs` at `0x1400279e7`
- `DEVOBJ!DevObjGetClassDevs` at `0x1400279e7`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x140027c5d`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x140027c5d`
- `vdsutil!VdsHeapFree` at `0x140027a9d`
- `vdsutil!VdsHeapFree` at `0x140027c46`
- `vdsutil!VdsHeapFree` at `0x140027a9d`
- `vdsutil!VdsHeapFree` at `0x140027c46`
- `vdsutil!VdsTraceW` at `0x1400278fe`
- `vdsutil!VdsTraceW` at `0x1400279b2`
- `vdsutil!VdsTraceW` at `0x140027a7f`
- `vdsutil!VdsTraceW` at `0x140027b19`
- `vdsutil!VdsTraceW` at `0x140027ba8`
- `vdsutil!VdsTraceW` at `0x140027bc7`
- `vdsutil!VdsTraceW` at `0x140027bff`
- `vdsutil!VdsTraceW` at `0x140027c2d`
- `vdsutil!VdsTraceW` at `0x140027c73`
- `vdsutil!VdsTraceW` at `0x140027c88`
- `vdsutil!VdsTraceW` at `0x1400278fe`
- `vdsutil!VdsTraceW` at `0x1400279b2`
- `vdsutil!VdsTraceW` at `0x140027a7f`
- `vdsutil!VdsTraceW` at `0x140027b19`
- `vdsutil!VdsTraceW` at `0x140027ba8`
- `vdsutil!VdsTraceW` at `0x140027bc7`
- `vdsutil!VdsTraceW` at `0x140027bff`
- `vdsutil!VdsTraceW` at `0x140027c2d`
- `vdsutil!VdsTraceW` at `0x140027c73`
- `vdsutil!VdsTraceW` at `0x140027c88`

## string_xrefs

- `0x140027a73`: `CVdsService::GetDiskIdFromLunInfo, 4, hr=%lX`
- `0x1400279a6`: `CVdsService::GetDiskIdFromLunInfo, 2, hr=%lX`
- `0x140027a06`: `CVdsService::GetDiskIdFromLunInfo, 3, hr=%lX`
- `0x1400278f2`: `CVdsService::GetDiskIdFromLunInfo`
- `0x140027c24`: `CVdsService::GetDiskIdFromLunInfo, 1, hr=%lX, pLunInfo=%p, pDiskId=%p`
- `0x140027ac1`: `CVdsService::GetDiskIdFromLunInfo, 5, hr=%lX`
- `0x140027b01`: `CVdsService::GetDiskIdFromLunInfo, 6, hr=%lX`
- `0x140027bbe`: `CVdsService::GetDiskIdFromLunInfo, 7, hr=%lX`
- `0x140027bf6`: `CVdsService::GetDiskIdFromLunInfo, 8, hr=%lX`
- `0x140027c6a`: `CVdsService::GetDiskIdFromLunInfo, 9, hr=%lX`
- `0x140027c7c`: `EXIT CVdsService::GetDiskIdFromLunInfo, hr=%lX`
- `0x140027b0d`: `CVdsService::IsMatchLun`
- `0x140027b9c`: `EXIT CVdsService::IsMatchLun, return=%d`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CVdsService::GetDiskIdFromLunInfo(
        CVdsService *this,
        struct _VDS_LUN_INFORMATION *a2,
        struct _GUID *a3)
{
  __int64 result; // rax
  unsigned int v7; // edi
  __int64 DeviceInfoList; // rax
  void *v9; // r14
  signed int LastError; // eax
  signed int v11; // eax
  int v12; // r13d
  unsigned int i; // r12d
  signed int DeviceDetailData; // eax
  const wchar_t *v15; // rdx
  struct _DO_DEVICE_INTERFACE_DETAIL_DATA *v16; // rbx
  HANDLE v17; // rax
  unsigned __int8 v18; // bl
  CVdsService *v19; // rcx
  int LunInformationForDisk; // eax
  CVdsService *v21; // rcx
  char IsMatchDeviceIdDescriptor; // al
  CVdsService *v23; // rcx
  CVdsService *v24; // rcx
  CVdsService *v25; // rcx
  int DiskId; // eax
  struct _DO_DEVICE_INTERFACE_DETAIL_DATA *v27; // rbx
  HANDLE ProcessHeap; // rax
  struct _DO_DEVICE_INTERFACE_DETAIL_DATA *v29; // [rsp+30h] [rbp-99h] BYREF
  unsigned int v30; // [rsp+38h] [rbp-91h] BYREF
  __int64 v31; // [rsp+40h] [rbp-89h] BYREF
  int v32; // [rsp+48h] [rbp-81h]
  struct _GUID v33; // [rsp+50h] [rbp-79h] BYREF
  __int128 v34; // [rsp+60h] [rbp-69h] BYREF
  __int128 v35; // [rsp+70h] [rbp-59h]
  _VDS_LUN_INFORMATION v36; // [rsp+80h] [rbp-49h] BYREF

  memset_0(&v36, 0, sizeof(v36));
  v33 = 0;
  v30 = 0;
  v34 = 0;
  v35 = 0;
  v29 = 0;
  VdsTraceW(2, L"CVdsService::GetDiskIdFromLunInfo");
  result = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this - 5) + 32LL))((char *)this - 40);
  if ( (int)result >= 0 )
  {
    v31 = 0;
    v32 = 0;
    v7 = CVdsOperationEntry::BeginOperation((CVdsOperationEntry *)&v31);
    if ( (v7 & 0x80000000) != 0 )
    {
LABEL_52:
      CVdsOperationEntry::~CVdsOperationEntry((CVdsOperationEntry *)&v31);
      return v7;
    }
    EnterCriticalSection(&g_GlobalCriticalSection);
    if ( !a2 || !a3 )
    {
      v9 = 0;
      v7 = -2147024809;
      VdsTraceW(0, L"CVdsService::GetDiskIdFromLunInfo, 1, hr=%lX, pLunInfo=%p, pDiskId=%p", a2, a3, -2147024809);
LABEL_48:
      v27 = v29;
      ProcessHeap = GetProcessHeap();
      VdsHeapFree(ProcessHeap, 0, v27);
      v29 = 0;
      if ( v9 )
      {
        if ( !(unsigned int)DevObjDestroyDeviceInfoList(v9) )
          VdsTraceW(0, L"CVdsService::GetDiskIdFromLunInfo, 9, hr=%lX", v7);
      }
      VdsTraceW(2, L"EXIT CVdsService::GetDiskIdFromLunInfo, hr=%lX", v7);
      LeaveCriticalSection(&g_GlobalCriticalSection);
      goto LABEL_52;
    }
    *a3 = GUID_NULL;
    v33 = GUID_NULL;
    DeviceInfoList = DevObjCreateDeviceInfoList(0, 0, 0, 0, 0);
    v9 = (void *)DeviceInfoList;
    if ( DeviceInfoList == -1 )
    {
      LastError = GetLastError();
      v7 = LastError;
      if ( LastError > 0 )
        v7 = (unsigned __int16)LastError | 0x80070000;
      VdsTraceW(0, L"CVdsService::GetDiskIdFromLunInfo, 2, hr=%lX", v7);
LABEL_9:
      if ( (v7 & 0x80000000) == 0 )
        v7 = -2147212283;
      goto LABEL_48;
    }
    if ( !(unsigned int)DevObjGetClassDevs(DeviceInfoList, &GUID_DEVINTERFACE_DISK, 0, 18, 0, 0) )
    {
      v11 = GetLastError();
      v7 = v11;
      if ( v11 > 0 )
        v7 = (unsigned __int16)v11 | 0x80070000;
      VdsTraceW(0, L"CVdsService::GetDiskIdFromLunInfo, 3, hr=%lX", v7);
      goto LABEL_9;
    }
    v7 = 0;
    v12 = 1;
    for ( i = 0; ; ++i )
    {
      if ( !v12 )
        goto LABEL_9;
      v34 = 0;
      v35 = 0;
      LODWORD(v34) = 32;
      v12 = DevObjEnumDeviceInterfaces(v9, 0, &GUID_DEVINTERFACE_DISK, i, &v34);
      if ( !v12 )
      {
        DeviceDetailData = GetLastError();
        if ( DeviceDetailData == 259 )
          goto LABEL_9;
        if ( DeviceDetailData > 0 )
          DeviceDetailData = (unsigned __int16)DeviceDetailData | 0x80070000;
        v15 = L"CVdsService::GetDiskIdFromLunInfo, 4, hr=%lX";
        goto LABEL_22;
      }
      v16 = v29;
      v17 = GetProcessHeap();
      VdsHeapFree(v17, 0, v16);
      v18 = 0;
      v29 = 0;
      DeviceDetailData = CVdsService::GetDeviceDetailData(v19, v9, (struct _DO_DEVICE_INTERFACE_DATA *)&v34, &v29);
      v7 = DeviceDetailData;
      if ( DeviceDetailData < 0 )
      {
        v15 = L"CVdsService::GetDiskIdFromLunInfo, 5, hr=%lX";
LABEL_22:
        VdsTraceW(0, v15, (unsigned int)DeviceDetailData);
        continue;
      }
      memset_0(&v36, 0, sizeof(v36));
      v30 = 999999;
      LunInformationForDisk = CVdsService::GetLunInformationForDisk((LPCWSTR)v29 + 2, &v36, &v30);
      v7 = LunInformationForDisk;
      if ( LunInformationForDisk < 0 )
      {
        VdsTraceW(0, L"CVdsService::GetDiskIdFromLunInfo, 6, hr=%lX", (unsigned int)LunInformationForDisk);
        continue;
      }
      VdsTraceW(2, L"CVdsService::IsMatchLun");
      IsMatchDeviceIdDescriptor = 0;
      if ( a2->m_deviceIdDescriptor.m_cIdentifiers && v36.m_deviceIdDescriptor.m_cIdentifiers )
        IsMatchDeviceIdDescriptor = CVdsService::IsMatchDeviceIdDescriptor(
                                      v21,
                                      &a2->m_deviceIdDescriptor,
                                      &v36.m_deviceIdDescriptor);
      if ( !a2->m_deviceIdDescriptor.m_cIdentifiers && !v36.m_deviceIdDescriptor.m_cIdentifiers )
      {
        if ( a2->m_DeviceType != v36.m_DeviceType
          || a2->m_DeviceTypeModifier != v36.m_DeviceTypeModifier
          || !CVdsService::cmp_str_eq(v21, a2->m_szVendorId, v36.m_szVendorId)
          || !CVdsService::cmp_str_eq(v23, a2->m_szProductId, v36.m_szProductId)
          || !CVdsService::cmp_str_eq(v24, a2->m_szProductRevision, v36.m_szProductRevision) )
        {
          goto LABEL_40;
        }
        IsMatchDeviceIdDescriptor = CVdsService::cmp_str_eq(v25, a2->m_szSerialNumber, v36.m_szSerialNumber);
      }
      if ( IsMatchDeviceIdDescriptor )
        v18 = 1;
LABEL_40:
      VdsTraceW(2, L"EXIT CVdsService::IsMatchLun, return=%d", v18);
      if ( (int)CVdsService::EmptyLunInformation(&v36) < 0 )
        VdsTraceW(0, L"CVdsService::GetDiskIdFromLunInfo, 7, hr=%lX", v7);
      if ( v18 )
      {
        DiskId = CVdsService::GetDiskId((wchar_t *)v29 + 2, &v33);
        v7 = DiskId;
        if ( DiskId >= 0 )
          *a3 = v33;
        else
          VdsTraceW(0, L"CVdsService::GetDiskIdFromLunInfo, 8, hr=%lX", (unsigned int)DiskId);
        goto LABEL_48;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x140027890  mov     [rsp-8+arg_18], rbx
0x140027895  push    rbp
0x140027896  push    rsi
0x140027897  push    rdi
0x140027898  push    r12
0x14002789a  push    r13
0x14002789c  push    r14
0x14002789e  push    r15
0x1400278a0  lea     rbp, [rsp-27h]
0x1400278a5  sub     rsp, 0F0h
0x1400278ac  mov     rax, cs:__security_cookie
0x1400278b3  xor     rax, rsp
0x1400278b6  mov     [rbp+57h+var_38], rax
0x1400278ba  mov     r15, r8
0x1400278bd  mov     rsi, rdx
0x1400278c0  mov     rbx, rcx
0x1400278c3  xor     edx, edx; Val
0x1400278c5  lea     r8d, [rdx+60h]; Size
0x1400278c9  lea     rcx, [rbp+57h+var_A0]; void *
0x1400278cd  call    memset_0
0x1400278d2  xorps   xmm0, xmm0
0x1400278d5  movups  xmmword ptr [rbp+57h+var_D0.Data1], xmm0
0x1400278d9  mov     [rsp+120h+var_E8], 0
0x1400278e1  movups  [rbp+57h+var_C0], xmm0
0x1400278e5  movups  [rbp+57h+var_B0], xmm0
0x1400278e9  mov     [rsp+120h+var_F0], 0
0x1400278f2  lea     rdx, aCvdsserviceGet_47; "CVdsService::GetDiskIdFromLunInfo"
0x1400278f9  mov     ecx, 2
0x1400278fe  call    cs:__imp_VdsTraceW
0x140027904  lea     rcx, [rbx-28h]
0x140027908  mov     rax, [rcx]
0x14002790b  mov     rax, [rax+20h]
0x14002790f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140027914  xor     ebx, ebx
0x140027916  test    eax, eax
0x140027918  js      loc_140027CA9
0x14002791e  mov     [rsp+120h+var_E0], rbx
0x140027923  mov     [rsp+120h+var_D8], ebx
0x140027927  lea     rcx, [rsp+120h+var_E0]; this
0x14002792c  call    ?BeginOperation@CVdsOperationEntry@@QEAAJXZ; CVdsOperationEntry::BeginOperation(void)
0x140027931  mov     edi, eax
0x140027933  test    eax, eax
0x140027935  js      loc_140027C9D
0x14002793b  lea     rcx, ?g_GlobalCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140027942  call    cs:__imp_EnterCriticalSection
0x140027948  nop
0x140027949  test    rsi, rsi
0x14002794c  jz      loc_140027C12
0x140027952  test    r15, r15
0x140027955  jz      loc_140027C12
0x14002795b  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x140027962  movdqu  xmmword ptr [r15], xmm0
0x140027967  movups  xmm1, xmmword ptr cs:GUID_NULL.Data1
0x14002796e  movdqu  xmmword ptr [rbp+57h+var_D0.Data1], xmm1
0x140027973  mov     [rsp+120h+var_100], rbx
0x140027978  xor     r9d, r9d
0x14002797b  xor     r8d, r8d
0x14002797e  xor     edx, edx
0x140027980  xor     ecx, ecx
0x140027982  call    cs:__imp_DevObjCreateDeviceInfoList
0x140027988  mov     r14, rax
0x14002798b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14002798f  jnz     short loc_1400279CA
0x140027991  call    cs:__imp_GetLastError
0x140027997  mov     edi, eax
0x140027999  test    eax, eax
0x14002799b  jle     short loc_1400279A6
0x14002799d  movzx   edi, ax
0x1400279a0  or      edi, 80070000h
0x1400279a6  lea     rdx, aCvdsserviceGet_135; "CVdsService::GetDiskIdFromLunInfo, 2, h"...
0x1400279ad  mov     r8d, edi
0x1400279b0  xor     ecx, ecx
0x1400279b2  call    cs:__imp_VdsTraceW
0x1400279b8  test    edi, edi
0x1400279ba  js      loc_140027C33
0x1400279c0  mov     edi, 80042405h
0x1400279c5  jmp     loc_140027C33
0x1400279ca  mov     [rsp+120h+var_F8], rbx
0x1400279cf  mov     [rsp+120h+var_100], rbx
0x1400279d4  mov     r9d, 12h
0x1400279da  xor     r8d, r8d
0x1400279dd  lea     rdx, GUID_DEVINTERFACE_DISK
0x1400279e4  mov     rcx, r14
0x1400279e7  call    cs:__imp_DevObjGetClassDevs
0x1400279ed  test    eax, eax
0x1400279ef  jnz     short loc_140027A0F
0x1400279f1  call    cs:__imp_GetLastError
0x1400279f7  mov     edi, eax
0x1400279f9  test    eax, eax
0x1400279fb  jle     short loc_140027A06
0x1400279fd  movzx   edi, ax
0x140027a00  or      edi, 80070000h
0x140027a06  lea     rdx, aCvdsserviceGet_9; "CVdsService::GetDiskIdFromLunInfo, 3, h"...
0x140027a0d  jmp     short loc_1400279AD
0x140027a0f  mov     edi, ebx
0x140027a11  mov     r13d, 1
0x140027a17  mov     r12d, ebx
0x140027a1a  test    r13d, r13d
0x140027a1d  jz      short loc_1400279B8
0x140027a1f  xorps   xmm0, xmm0
0x140027a22  movups  [rbp+57h+var_C0], xmm0
0x140027a26  movups  [rbp+57h+var_B0], xmm0
0x140027a2a  mov     dword ptr [rbp+57h+var_C0], 20h ; ' '
0x140027a31  lea     rax, [rbp+57h+var_C0]
0x140027a35  mov     [rsp+120h+var_100], rax
0x140027a3a  mov     r9d, r12d
0x140027a3d  lea     r8, GUID_DEVINTERFACE_DISK
0x140027a44  xor     edx, edx
0x140027a46  mov     rcx, r14
0x140027a49  call    cs:__imp_DevObjEnumDeviceInterfaces
0x140027a4f  mov     r13d, eax
0x140027a52  test    eax, eax
0x140027a54  jnz     short loc_140027A8A
0x140027a56  call    cs:__imp_GetLastError
0x140027a5c  cmp     eax, 103h
0x140027a61  jz      loc_1400279B8
0x140027a67  test    eax, eax
0x140027a69  jle     short loc_140027A73
0x140027a6b  movzx   eax, ax
0x140027a6e  or      eax, 80070000h
0x140027a73  lea     rdx, aCvdsserviceGet_122; "CVdsService::GetDiskIdFromLunInfo, 4, h"...
0x140027a7a  mov     r8d, eax
0x140027a7d  xor     ecx, ecx
0x140027a7f  call    cs:__imp_VdsTraceW
0x140027a85  jmp     loc_140027BD3
0x140027a8a  mov     rbx, [rsp+120h+var_F0]
0x140027a8f  call    cs:__imp_GetProcessHeap
0x140027a95  mov     r8, rbx
0x140027a98  xor     edx, edx
0x140027a9a  mov     rcx, rax
0x140027a9d  call    cs:__imp_VdsHeapFree
0x140027aa3  xor     ebx, ebx
0x140027aa5  mov     [rsp+120h+var_F0], rbx
0x140027aaa  lea     r9, [rsp+120h+var_F0]; struct _DO_DEVICE_INTERFACE_DETAIL_DATA **
0x140027aaf  lea     r8, [rbp+57h+var_C0]; struct _DO_DEVICE_INTERFACE_DATA *
0x140027ab3  mov     rdx, r14; void *
0x140027ab6  call    ?GetDeviceDetailData@CVdsService@@AEAAJPEAXPEAU_DO_DEVICE_INTERFACE_DATA@@PEAPEAU_DO_DEVICE_INTERFACE_DETAIL_DATA@@@Z; CVdsService::GetDeviceDetailData(void *,_DO_DEVICE_INTERFACE_DATA *,_DO_DEVICE_INTERFACE_DETAIL_DATA * *)
0x140027abb  mov     edi, eax
0x140027abd  test    eax, eax
0x140027abf  jns     short loc_140027ACA
0x140027ac1  lea     rdx, aCvdsserviceGet_19; "CVdsService::GetDiskIdFromLunInfo, 5, h"...
0x140027ac8  jmp     short loc_140027A7A
0x140027aca  xor     edx, edx; Val
0x140027acc  lea     r8d, [rdx+60h]; Size
0x140027ad0  lea     rcx, [rbp+57h+var_A0]; void *
0x140027ad4  call    memset_0
0x140027ad9  mov     [rsp+120h+var_E8], 0F423Fh
0x140027ae1  mov     rcx, [rsp+120h+var_F0]
0x140027ae6  add     rcx, 4; lpFileName
0x140027aea  lea     r8, [rsp+120h+var_E8]; unsigned int *
0x140027aef  lea     rdx, [rbp+57h+var_A0]; struct _VDS_LUN_INFORMATION *
0x140027af3  call    ?GetLunInformationForDisk@CVdsService@@SAJPEBGPEAU_VDS_LUN_INFORMATION@@PEAK@Z; CVdsService::GetLunInformationForDisk(ushort const *,_VDS_LUN_INFORMATION *,ulong *)
0x140027af8  mov     edi, eax
0x140027afa  test    eax, eax
0x140027afc  jns     short loc_140027B0D
0x140027afe  mov     r8d, eax
0x140027b01  lea     rdx, aCvdsserviceGet_15; "CVdsService::GetDiskIdFromLunInfo, 6, h"...
0x140027b08  jmp     loc_140027A7D
0x140027b0d  lea     rdx, aCvdsserviceIsm_2; "CVdsService::IsMatchLun"
0x140027b14  mov     ecx, 2
0x140027b19  call    cs:__imp_VdsTraceW
0x140027b1f  xor     al, al
0x140027b21  lea     rdx, [rsi+40h]; struct _VDS_STORAGE_DEVICE_ID_DESCRIPTOR *
0x140027b25  cmp     [rdx+4], ebx
0x140027b28  jbe     short loc_140027B38
0x140027b2a  cmp     [rbp+57h+var_A0.m_deviceIdDescriptor.m_cIdentifiers], ebx
0x140027b2d  jbe     short loc_140027B38
0x140027b2f  lea     r8, [rbp+57h+var_A0.m_deviceIdDescriptor]; struct _VDS_STORAGE_DEVICE_ID_DESCRIPTOR *
0x140027b33  call    ?IsMatchDeviceIdDescriptor@CVdsService@@AEAAEPEBU_VDS_STORAGE_DEVICE_ID_DESCRIPTOR@@0@Z; CVdsService::IsMatchDeviceIdDescriptor(_VDS_STORAGE_DEVICE_ID_DESCRIPTOR const *,_VDS_STORAGE_DEVICE_ID_DESCRIPTOR const *)
0x140027b38  cmp     [rsi+44h], ebx
0x140027b3b  jnz     short loc_140027B92
0x140027b3d  cmp     [rbp+57h+var_A0.m_deviceIdDescriptor.m_cIdentifiers], ebx
0x140027b40  jnz     short loc_140027B92
0x140027b42  mov     al, [rbp+57h+var_A0.m_DeviceType]
0x140027b45  cmp     [rsi+4], al
0x140027b48  jnz     short loc_140027B98
0x140027b4a  mov     al, [rbp+57h+var_A0.m_DeviceTypeModifier]
0x140027b4d  cmp     [rsi+5], al
0x140027b50  jnz     short loc_140027B98
0x140027b52  mov     r8, [rbp+57h+var_A0.m_szVendorId]; char *
0x140027b56  mov     rdx, [rsi+10h]; char *
0x140027b5a  call    ?cmp_str_eq@CVdsService@@AEAAEPEBD0@Z; CVdsService::cmp_str_eq(char const *,char const *)
0x140027b5f  test    al, al
0x140027b61  jz      short loc_140027B98
0x140027b63  mov     r8, [rbp+57h+var_A0.m_szProductId]; char *
0x140027b67  mov     rdx, [rsi+18h]; char *
0x140027b6b  call    ?cmp_str_eq@CVdsService@@AEAAEPEBD0@Z; CVdsService::cmp_str_eq(char const *,char const *)
0x140027b70  test    al, al
0x140027b72  jz      short loc_140027B98
0x140027b74  mov     r8, [rbp+57h+var_A0.m_szProductRevision]; char *
0x140027b78  mov     rdx, [rsi+20h]; char *
0x140027b7c  call    ?cmp_str_eq@CVdsService@@AEAAEPEBD0@Z; CVdsService::cmp_str_eq(char const *,char const *)
0x140027b81  test    al, al
0x140027b83  jz      short loc_140027B98
0x140027b85  mov     r8, [rbp+57h+var_A0.m_szSerialNumber]; char *
0x140027b89  mov     rdx, [rsi+28h]; char *
0x140027b8d  call    ?cmp_str_eq@CVdsService@@AEAAEPEBD0@Z; CVdsService::cmp_str_eq(char const *,char const *)
0x140027b92  test    al, al
0x140027b94  jz      short loc_140027B98
0x140027b96  mov     bl, 1
0x140027b98  movzx   r8d, bl
0x140027b9c  lea     rdx, aExitCvdsservic_3; "EXIT CVdsService::IsMatchLun, return=%d"
0x140027ba3  mov     ecx, 2
0x140027ba8  call    cs:__imp_VdsTraceW
0x140027bae  lea     rcx, [rbp+57h+var_A0]; struct _VDS_LUN_INFORMATION *
0x140027bb2  call    ?EmptyLunInformation@CVdsService@@CAJPEAU_VDS_LUN_INFORMATION@@@Z; CVdsService::EmptyLunInformation(_VDS_LUN_INFORMATION *)
0x140027bb7  test    eax, eax
0x140027bb9  jns     short loc_140027BCD
0x140027bbb  mov     r8d, edi
0x140027bbe  lea     rdx, aCvdsserviceGet_80; "CVdsService::GetDiskIdFromLunInfo, 7, h"...
0x140027bc5  xor     ecx, ecx
0x140027bc7  call    cs:__imp_VdsTraceW
0x140027bcd  test    bl, bl
0x140027bcf  jnz     short loc_140027BDB
0x140027bd1  xor     ebx, ebx
0x140027bd3  inc     r12d
0x140027bd6  jmp     loc_140027A1A
0x140027bdb  mov     rcx, [rsp+120h+var_F0]
0x140027be0  add     rcx, 4; String1
0x140027be4  lea     rdx, [rbp+57h+var_D0]; struct _GUID *
0x140027be8  call    ?GetDiskId@CVdsService@@SAJPEAGPEAU_GUID@@@Z; CVdsService::GetDiskId(ushort *,_GUID *)
0x140027bed  mov     edi, eax
0x140027bef  test    eax, eax
0x140027bf1  jns     short loc_140027C07
0x140027bf3  mov     r8d, eax
0x140027bf6  lea     rdx, aCvdsserviceGet_117; "CVdsService::GetDiskIdFromLunInfo, 8, h"...
0x140027bfd  xor     ecx, ecx
0x140027bff  call    cs:__imp_VdsTraceW
0x140027c05  jmp     short loc_140027C33
0x140027c07  movups  xmm0, xmmword ptr [rbp+57h+var_D0.Data1]
0x140027c0b  movdqu  xmmword ptr [r15], xmm0
0x140027c10  jmp     short loc_140027C33
0x140027c12  mov     r14, rbx
0x140027c15  mov     edi, 80070057h
0x140027c1a  mov     dword ptr [rsp+120h+var_100], edi
0x140027c1e  mov     r9, r15
0x140027c21  mov     r8, rsi
0x140027c24  lea     rdx, aCvdsserviceGet_37; "CVdsService::GetDiskIdFromLunInfo, 1, h"...
0x140027c2b  xor     ecx, ecx
0x140027c2d  call    cs:__imp_VdsTraceW
0x140027c33  mov     rbx, [rsp+120h+var_F0]
0x140027c38  call    cs:__imp_GetProcessHeap
0x140027c3e  mov     r8, rbx
0x140027c41  xor     edx, edx
0x140027c43  mov     rcx, rax
0x140027c46  call    cs:__imp_VdsHeapFree
0x140027c4c  mov     [rsp+120h+var_F0], 0
0x140027c55  test    r14, r14
0x140027c58  jz      short loc_140027C79
0x140027c5a  mov     rcx, r14
0x140027c5d  call    cs:__imp_DevObjDestroyDeviceInfoList
0x140027c63  test    eax, eax
0x140027c65  jnz     short loc_140027C79
0x140027c67  mov     r8d, edi
0x140027c6a  lea     rdx, aCvdsserviceGet_33; "CVdsService::GetDiskIdFromLunInfo, 9, h"...
0x140027c71  xor     ecx, ecx
0x140027c73  call    cs:__imp_VdsTraceW
0x140027c79  mov     r8d, edi
0x140027c7c  lea     rdx, aExitCvdsservic_7; "EXIT CVdsService::GetDiskIdFromLunInfo,"...
0x140027c83  mov     ecx, 2
0x140027c88  call    cs:__imp_VdsTraceW
0x140027c8e  nop
0x140027c8f  lea     rcx, ?g_GlobalCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140027c96  call    cs:__imp_LeaveCriticalSection
0x140027c9c  nop
0x140027c9d  lea     rcx, [rsp+120h+var_E0]; this
0x140027ca2  call    ??1CVdsOperationEntry@@QEAA@XZ; CVdsOperationEntry::~CVdsOperationEntry(void)
0x140027ca7  mov     eax, edi
0x140027ca9  mov     rcx, [rbp+57h+var_38]
0x140027cad  xor     rcx, rsp; StackCookie
0x140027cb0  call    __security_check_cookie
0x140027cb5  mov     rbx, [rsp+120h+arg_18]
0x140027cbd  add     rsp, 0F0h
0x140027cc4  pop     r15
0x140027cc6  pop     r14
0x140027cc8  pop     r13
0x140027cca  pop     r12
0x140027ccc  pop     rdi
0x140027ccd  pop     rsi
0x140027cce  pop     rbp
0x140027ccf  retn
```
