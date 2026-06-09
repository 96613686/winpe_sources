# CVdsService::UninstallOneDisk(ushort *,uchar *)

- ea: `0x140020590`
- end: `0x140020962`
- name: `?UninstallOneDisk@CVdsService@@AEAAJPEAGPEAE@Z`
- size: `978`
- prototype: `int(CVdsService *__hidden this, unsigned __int16 *, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, service_task, installer_update`

## callers

- `0x140022400`

## callees

- `0x140020590`
- `0x14003d420`
- `0x140052e80`

## import_xrefs

- `msvcrt!_wtol` at `0x14002078b`
- `msvcrt!_wtol` at `0x14002078b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14002072a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400208b0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14002072a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400208b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002064a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002069d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400207c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140020862`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400208da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002064a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002069d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400207c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140020862`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400208da`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140020775`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140020775`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x1400206e8`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x1400206e8`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x14002063b`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x14002063b`
- `DEVOBJ!DevObjGetClassDevs` at `0x140020693`
- `DEVOBJ!DevObjGetClassDevs` at `0x140020693`
- `DEVOBJ!DevObjEnumDeviceInfo` at `0x1400207bc`
- `DEVOBJ!DevObjEnumDeviceInfo` at `0x1400207bc`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x1400208d0`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x1400208d0`
- `vdsutil!OpenDevice` at `0x14002071d`
- `vdsutil!OpenDevice` at `0x14002071d`
- `vdsutil!GetDeviceNumber` at `0x14002075c`
- `vdsutil!GetDeviceNumber` at `0x14002075c`
- `vdsutil!VdsHeapFree` at `0x140020738`
- `vdsutil!VdsHeapFree` at `0x1400208be`
- `vdsutil!VdsHeapFree` at `0x140020738`
- `vdsutil!VdsHeapFree` at `0x1400208be`
- `vdsutil!GetInterfaceDetailData` at `0x140020701`
- `vdsutil!GetInterfaceDetailData` at `0x140020701`
- `vdsutil!VdsTraceW` at `0x1400205f8`
- `vdsutil!VdsTraceW` at `0x14002066b`
- `vdsutil!VdsTraceW` at `0x1400208a6`
- `vdsutil!VdsTraceW` at `0x1400208fb`
- `vdsutil!VdsTraceW` at `0x140020910`
- `vdsutil!VdsTraceW` at `0x140020933`
- `vdsutil!VdsTraceW` at `0x1400205f8`
- `vdsutil!VdsTraceW` at `0x14002066b`
- `vdsutil!VdsTraceW` at `0x1400208a6`
- `vdsutil!VdsTraceW` at `0x1400208fb`
- `vdsutil!VdsTraceW` at `0x140020910`
- `vdsutil!VdsTraceW` at `0x140020933`

## string_xrefs

- `0x1400206b2`: `CVdsService::UninstallOneDisk, 3, hr=%lX`
- `0x140020904`: `EXIT CVdsService::UninstallOneDisk, hr=%lX`
- `0x1400207db`: `CVdsService::UninstallOneDisk, 9, hr=%lX`
- `0x1400208f2`: `CVdsService::UninstallOneDisk, 11, hr=%lX`
- `0x140020883`: `CVdsService::UninstallOneDisk, 4, error=%ld`
- `0x14002083e`: `CVdsService::UninstallOneDisk, 6, error=%ld, name=%s`
- `0x140020821`: `CVdsService::UninstallOneDisk, 7, error=%ld, name=%s`
- `0x14002065f`: `CVdsService::UninstallOneDisk, 2, hr=%lX`
- `0x140020859`: `CVdsService::UninstallOneDisk, 5, error=%ld, name=%s`
- `0x1400205cf`: `CVdsService::UninstallOneDisk`
- `0x140020927`: `CVdsService::UninstallOneDisk, 1, hr=%lX, pName=%p, pbRebootReq=%p`
- `0x140020894`: `CVdsService::UninstallOneDisk, 8, error=%lX, name=%s`
- `0x140020803`: `CVdsService::UninstallOneDisk, 10, hr=%lX`

## pseudocode

```c
__int64 __fastcall CVdsService::UninstallOneDisk(CVdsService *this, unsigned __int16 *a2, unsigned __int8 *a3)
{
  unsigned __int64 v5; // rax
  __int64 DeviceInfoList; // rax
  void *v7; // r15
  signed int LastError; // eax
  unsigned int v9; // edi
  const wchar_t *v10; // rdx
  signed int v11; // eax
  unsigned int i; // edi
  int InterfaceDetailData; // eax
  int v14; // eax
  __int64 v15; // rbx
  int v16; // r14d
  HANDLE ProcessHeap; // rax
  int DeviceNumber; // ebx
  int v19; // eax
  CVdsService *v20; // rcx
  signed int v21; // eax
  int v22; // eax
  signed int v23; // eax
  __int64 v24; // rbx
  HANDLE v25; // rax
  signed int v26; // eax
  __int64 v28; // [rsp+30h] [rbp-59h] BYREF
  HANDLE hObject; // [rsp+38h] [rbp-51h] BYREF
  __int64 v30; // [rsp+40h] [rbp-49h] BYREF
  int v31; // [rsp+48h] [rbp-41h]
  __int128 v32; // [rsp+50h] [rbp-39h] BYREF
  __int128 v33; // [rsp+60h] [rbp-29h]
  __int128 v34; // [rsp+70h] [rbp-19h] BYREF
  __int128 v35; // [rsp+80h] [rbp-9h]
  __int128 v36; // [rsp+90h] [rbp+7h]

  v30 = 0;
  v31 = 0;
  hObject = 0;
  v28 = 0;
  v32 = 0;
  v33 = 0;
  v34 = 0;
  v35 = 0;
  v36 = 0;
  VdsTraceW(2, L"CVdsService::UninstallOneDisk");
  if ( !a2 )
    goto LABEL_55;
  if ( !a3 )
    goto LABEL_55;
  v5 = -1;
  do
    ++v5;
  while ( a2[v5] );
  if ( v5 < 0x12 )
  {
LABEL_55:
    VdsTraceW(0, L"CVdsService::UninstallOneDisk, 1, hr=%lX, pName=%p, pbRebootReq=%p", 2147942487LL, a2, a3);
    return 2147942487LL;
  }
  *a3 = 0;
  DeviceInfoList = DevObjCreateDeviceInfoList(0, 0, 0, 0, 0);
  v7 = (void *)DeviceInfoList;
  if ( DeviceInfoList == -1 )
  {
    LastError = GetLastError();
    v9 = LastError;
    if ( LastError > 0 )
      v9 = (unsigned __int16)LastError | 0x80070000;
    v10 = L"CVdsService::UninstallOneDisk, 2, hr=%lX";
  }
  else if ( (unsigned int)DevObjGetClassDevs(DeviceInfoList, &GUID_DEVINTERFACE_DISK, 0, 18, 0, 0) )
  {
    for ( i = 0; ; ++i )
    {
      v32 = 0;
      LODWORD(v32) = 32;
      v33 = 0;
      if ( !(unsigned int)DevObjEnumDeviceInterfaces(v7, 0, &GUID_DEVINTERFACE_DISK, i, &v32) )
      {
        v23 = GetLastError();
        if ( v23 == 259 )
        {
          v9 = -2147212283;
          VdsTraceW(1, L"CVdsService::UninstallOneDisk, 8, error=%lX, name=%s", 2147755013LL, a2);
        }
        else
        {
          if ( v23 > 0 )
            v9 = (unsigned __int16)v23 | 0x80070000;
          else
            v9 = v23;
          VdsTraceW(0, L"CVdsService::UninstallOneDisk, 4, error=%ld", (unsigned int)v23);
        }
        goto LABEL_49;
      }
      InterfaceDetailData = GetInterfaceDetailData(v7, &v32, &v28);
      if ( InterfaceDetailData )
      {
        if ( InterfaceDetailData > 0 )
          v9 = (unsigned __int16)InterfaceDetailData | 0x80070000;
        else
          v9 = InterfaceDetailData;
        VdsTraceW(1, L"CVdsService::UninstallOneDisk, 5, error=%ld, name=%s", (unsigned int)InterfaceDetailData, a2);
        goto LABEL_49;
      }
      v14 = OpenDevice(v28 + 4, 0, &hObject);
      v15 = v28;
      v16 = v14;
      ProcessHeap = GetProcessHeap();
      VdsHeapFree(ProcessHeap, 0, v15);
      v28 = 0;
      if ( v16 )
      {
        if ( v16 > 0 )
          v9 = (unsigned __int16)v16 | 0x80070000;
        else
          v9 = v16;
        VdsTraceW(1, L"CVdsService::UninstallOneDisk, 6, error=%ld, name=%s", (unsigned int)v16, a2);
        goto LABEL_49;
      }
      v30 = 0;
      v31 = 0;
      DeviceNumber = GetDeviceNumber(hObject, &v30);
      if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      {
        CloseHandle(hObject);
        hObject = 0;
      }
      if ( DeviceNumber )
      {
        if ( DeviceNumber > 0 )
          v9 = (unsigned __int16)DeviceNumber | 0x80070000;
        else
          v9 = DeviceNumber;
        VdsTraceW(1, L"CVdsService::UninstallOneDisk, 7, error=%ld, name=%s", (unsigned int)DeviceNumber, a2);
        goto LABEL_49;
      }
      v19 = _wtol(a2 + 17);
      if ( v19 == HIDWORD(v30) )
        break;
    }
    v34 = 0;
    LODWORD(v34) = 48;
    v35 = 0;
    v36 = 0;
    if ( (unsigned int)DevObjEnumDeviceInfo(v7, i, &v34) )
    {
      v22 = CVdsService::UninstallDevice(v20, v7, (struct _DO_DEVINFO_DATA *)&v34, a3);
      v9 = v22;
      if ( v22 < 0 )
        VdsTraceW(0, L"CVdsService::UninstallOneDisk, 10, hr=%lX", (unsigned int)v22);
      goto LABEL_49;
    }
    v21 = GetLastError();
    v9 = v21;
    if ( v21 > 0 )
      v9 = (unsigned __int16)v21 | 0x80070000;
    v10 = L"CVdsService::UninstallOneDisk, 9, hr=%lX";
  }
  else
  {
    v11 = GetLastError();
    v9 = v11;
    if ( v11 > 0 )
      v9 = (unsigned __int16)v11 | 0x80070000;
    v10 = L"CVdsService::UninstallOneDisk, 3, hr=%lX";
  }
  VdsTraceW(0, v10, v9);
LABEL_49:
  v24 = v28;
  v25 = GetProcessHeap();
  VdsHeapFree(v25, 0, v24);
  v28 = 0;
  if ( v7 && !(unsigned int)DevObjDestroyDeviceInfoList(v7) )
  {
    v26 = GetLastError();
    v9 = v26;
    if ( v26 > 0 )
      v9 = (unsigned __int16)v26 | 0x80070000;
    VdsTraceW(0, L"CVdsService::UninstallOneDisk, 11, hr=%lX", v9);
  }
  VdsTraceW(2, L"EXIT CVdsService::UninstallOneDisk, hr=%lX", v9);
  return v9;
}

```

## disassembly

```asm
0x140020590  mov     [rsp-8+arg_0], rbx
0x140020595  push    rbp
0x140020596  push    rsi
0x140020597  push    rdi
0x140020598  push    r12
0x14002059a  push    r13
0x14002059c  push    r14
0x14002059e  push    r15
0x1400205a0  lea     rbp, [rsp-27h]
0x1400205a5  sub     rsp, 0B0h
0x1400205ac  mov     rax, cs:__security_cookie
0x1400205b3  xor     rax, rsp
0x1400205b6  mov     [rbp+57h+var_40], rax
0x1400205ba  xor     eax, eax
0x1400205bc  xorps   xmm1, xmm1
0x1400205bf  xorps   xmm0, xmm0
0x1400205c2  mov     [rbp+57h+var_A0], rax
0x1400205c6  mov     rsi, rdx
0x1400205c9  mov     [rbp+57h+var_98], eax
0x1400205cc  xor     r13d, r13d
0x1400205cf  lea     rdx, aCvdsserviceUni_12; "CVdsService::UninstallOneDisk"
0x1400205d6  lea     ecx, [rax+2]
0x1400205d9  mov     [rbp+57h+hObject], r13
0x1400205dd  mov     r12, r8
0x1400205e0  mov     [rbp+57h+var_B0], r13
0x1400205e4  movups  [rbp+57h+var_90], xmm0
0x1400205e8  movups  [rbp+57h+var_80], xmm0
0x1400205ec  movups  [rbp+57h+var_70], xmm1
0x1400205f0  movups  [rbp+57h+var_60], xmm1
0x1400205f4  movups  [rbp+57h+var_50], xmm1
0x1400205f8  call    cs:__imp_VdsTraceW
0x1400205fe  test    rsi, rsi
0x140020601  jz      loc_14002091A
0x140020607  test    r12, r12
0x14002060a  jz      loc_14002091A
0x140020610  or      rax, 0FFFFFFFFFFFFFFFFh
0x140020614  inc     rax
0x140020617  cmp     [rsi+rax*2], r13w
0x14002061c  jnz     short loc_140020614
0x14002061e  cmp     rax, 12h
0x140020622  jb      loc_14002091A
0x140020628  xor     r9d, r9d
0x14002062b  mov     [r12], r13b
0x14002062f  xor     r8d, r8d
0x140020632  mov     [rsp+0E0h+var_C0], r13
0x140020637  xor     edx, edx
0x140020639  xor     ecx, ecx
0x14002063b  call    cs:__imp_DevObjCreateDeviceInfoList
0x140020641  mov     r15, rax
0x140020644  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140020648  jnz     short loc_140020676
0x14002064a  call    cs:__imp_GetLastError
0x140020650  mov     edi, eax
0x140020652  test    eax, eax
0x140020654  jle     short loc_14002065F
0x140020656  movzx   edi, ax
0x140020659  or      edi, 80070000h
0x14002065f  lea     rdx, aCvdsserviceUni_26; "CVdsService::UninstallOneDisk, 2, hr=%l"...
0x140020666  mov     r8d, edi
0x140020669  xor     ecx, ecx
0x14002066b  call    cs:__imp_VdsTraceW
0x140020671  jmp     loc_1400208AC
0x140020676  mov     [rsp+0E0h+var_B8], r13
0x14002067b  lea     rdx, GUID_DEVINTERFACE_DISK
0x140020682  mov     r9d, 12h
0x140020688  mov     [rsp+0E0h+var_C0], r13
0x14002068d  xor     r8d, r8d
0x140020690  mov     rcx, r15
0x140020693  call    cs:__imp_DevObjGetClassDevs
0x140020699  test    eax, eax
0x14002069b  jnz     short loc_1400206BB
0x14002069d  call    cs:__imp_GetLastError
0x1400206a3  mov     edi, eax
0x1400206a5  test    eax, eax
0x1400206a7  jle     short loc_1400206B2
0x1400206a9  movzx   edi, ax
0x1400206ac  or      edi, 80070000h
0x1400206b2  lea     rdx, aCvdsserviceUni_6; "CVdsService::UninstallOneDisk, 3, hr=%l"...
0x1400206b9  jmp     short loc_140020666
0x1400206bb  mov     edi, r13d
0x1400206be  xorps   xmm0, xmm0
0x1400206c1  lea     rax, [rbp+57h+var_90]
0x1400206c5  movups  [rbp+57h+var_90], xmm0
0x1400206c9  mov     r9d, edi
0x1400206cc  mov     dword ptr [rbp+57h+var_90], 20h ; ' '
0x1400206d3  lea     r8, GUID_DEVINTERFACE_DISK
0x1400206da  mov     [rsp+0E0h+var_C0], rax
0x1400206df  xor     edx, edx
0x1400206e1  mov     rcx, r15
0x1400206e4  movups  [rbp+57h+var_80], xmm0
0x1400206e8  call    cs:__imp_DevObjEnumDeviceInterfaces
0x1400206ee  test    eax, eax
0x1400206f0  jz      loc_140020862
0x1400206f6  lea     r8, [rbp+57h+var_B0]
0x1400206fa  mov     rcx, r15
0x1400206fd  lea     rdx, [rbp+57h+var_90]
0x140020701  call    cs:__imp_GetInterfaceDetailData
0x140020707  test    eax, eax
0x140020709  jnz     loc_140020847
0x14002070f  mov     rcx, [rbp+57h+var_B0]
0x140020713  lea     r8, [rbp+57h+hObject]
0x140020717  add     rcx, 4
0x14002071b  xor     edx, edx
0x14002071d  call    cs:__imp_OpenDevice
0x140020723  mov     rbx, [rbp+57h+var_B0]
0x140020727  mov     r14d, eax
0x14002072a  call    cs:__imp_GetProcessHeap
0x140020730  mov     r8, rbx
0x140020733  xor     edx, edx
0x140020735  mov     rcx, rax
0x140020738  call    cs:__imp_VdsHeapFree
0x14002073e  mov     [rbp+57h+var_B0], r13
0x140020742  test    r14d, r14d
0x140020745  jnz     loc_14002082A
0x14002074b  mov     rcx, [rbp+57h+hObject]
0x14002074f  lea     rdx, [rbp+57h+var_A0]
0x140020753  xor     eax, eax
0x140020755  mov     [rbp+57h+var_A0], rax
0x140020759  mov     [rbp+57h+var_98], eax
0x14002075c  call    cs:__imp_GetDeviceNumber
0x140020762  mov     ebx, eax
0x140020764  mov     rax, [rbp+57h+hObject]
0x140020768  lea     rcx, [rax-1]
0x14002076c  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x140020770  ja      short loc_14002077F
0x140020772  mov     rcx, rax; hObject
0x140020775  call    cs:__imp_CloseHandle
0x14002077b  mov     [rbp+57h+hObject], r13
0x14002077f  test    ebx, ebx
0x140020781  jnz     loc_14002080F
0x140020787  lea     rcx, [rsi+22h]; String
0x14002078b  call    cs:__imp__wtol
0x140020791  cmp     eax, dword ptr [rbp+57h+var_A0+4]
0x140020794  jz      short loc_14002079D
0x140020796  inc     edi
0x140020798  jmp     loc_1400206BE
0x14002079d  xorps   xmm0, xmm0
0x1400207a0  lea     r8, [rbp+57h+var_70]
0x1400207a4  movups  [rbp+57h+var_70], xmm0
0x1400207a8  mov     edx, edi
0x1400207aa  mov     dword ptr [rbp+57h+var_70], 30h ; '0'
0x1400207b1  mov     rcx, r15
0x1400207b4  movups  [rbp+57h+var_60], xmm0
0x1400207b8  movups  [rbp+57h+var_50], xmm0
0x1400207bc  call    cs:__imp_DevObjEnumDeviceInfo
0x1400207c2  test    eax, eax
0x1400207c4  jnz     short loc_1400207E7
0x1400207c6  call    cs:__imp_GetLastError
0x1400207cc  mov     edi, eax
0x1400207ce  test    eax, eax
0x1400207d0  jle     short loc_1400207DB
0x1400207d2  movzx   edi, ax
0x1400207d5  or      edi, 80070000h
0x1400207db  lea     rdx, aCvdsserviceUni_17; "CVdsService::UninstallOneDisk, 9, hr=%l"...
0x1400207e2  jmp     loc_140020666
0x1400207e7  mov     r9, r12; unsigned __int8 *
0x1400207ea  lea     r8, [rbp+57h+var_70]; struct _DO_DEVINFO_DATA *
0x1400207ee  mov     rdx, r15; void *
0x1400207f1  call    ?UninstallDevice@CVdsService@@AEAAJPEAXPEAU_DO_DEVINFO_DATA@@PEAE@Z; CVdsService::UninstallDevice(void *,_DO_DEVINFO_DATA *,uchar *)
0x1400207f6  mov     edi, eax
0x1400207f8  test    eax, eax
0x1400207fa  jns     loc_1400208AC
0x140020800  mov     r8d, eax
0x140020803  lea     rdx, aCvdsserviceUni_23; "CVdsService::UninstallOneDisk, 10, hr=%"...
0x14002080a  jmp     loc_140020669
0x14002080f  jg      short loc_140020815
0x140020811  mov     edi, ebx
0x140020813  jmp     short loc_14002081E
0x140020815  movzx   edi, bx
0x140020818  or      edi, 80070000h
0x14002081e  mov     r8d, ebx
0x140020821  lea     rdx, aCvdsserviceUni_5; "CVdsService::UninstallOneDisk, 7, error"...
0x140020828  jmp     short loc_14002089E
0x14002082a  jg      short loc_140020831
0x14002082c  mov     edi, r14d
0x14002082f  jmp     short loc_14002083B
0x140020831  movzx   edi, r14w
0x140020835  or      edi, 80070000h
0x14002083b  mov     r8d, r14d
0x14002083e  lea     rdx, aCvdsserviceUni_34; "CVdsService::UninstallOneDisk, 6, error"...
0x140020845  jmp     short loc_14002089E
0x140020847  jg      short loc_14002084D
0x140020849  mov     edi, eax
0x14002084b  jmp     short loc_140020856
0x14002084d  movzx   edi, ax
0x140020850  or      edi, 80070000h
0x140020856  mov     r8d, eax
0x140020859  lea     rdx, aCvdsserviceUni_21; "CVdsService::UninstallOneDisk, 5, error"...
0x140020860  jmp     short loc_14002089E
0x140020862  call    cs:__imp_GetLastError
0x140020868  cmp     eax, 103h
0x14002086d  jz      short loc_14002088F
0x14002086f  test    eax, eax
0x140020871  jg      short loc_140020877
0x140020873  mov     edi, eax
0x140020875  jmp     short loc_140020880
0x140020877  movzx   edi, ax
0x14002087a  or      edi, 80070000h
0x140020880  mov     r8d, eax
0x140020883  lea     rdx, aCvdsserviceUni_38; "CVdsService::UninstallOneDisk, 4, error"...
0x14002088a  jmp     loc_140020669
0x14002088f  mov     edi, 80042405h
0x140020894  lea     rdx, aCvdsserviceUni_39; "CVdsService::UninstallOneDisk, 8, error"...
0x14002089b  mov     r8d, edi
0x14002089e  mov     r9, rsi
0x1400208a1  mov     ecx, 1
0x1400208a6  call    cs:__imp_VdsTraceW
0x1400208ac  mov     rbx, [rbp+57h+var_B0]
0x1400208b0  call    cs:__imp_GetProcessHeap
0x1400208b6  mov     r8, rbx
0x1400208b9  xor     edx, edx
0x1400208bb  mov     rcx, rax
0x1400208be  call    cs:__imp_VdsHeapFree
0x1400208c4  mov     [rbp+57h+var_B0], r13
0x1400208c8  test    r15, r15
0x1400208cb  jz      short loc_140020901
0x1400208cd  mov     rcx, r15
0x1400208d0  call    cs:__imp_DevObjDestroyDeviceInfoList
0x1400208d6  test    eax, eax
0x1400208d8  jnz     short loc_140020901
0x1400208da  call    cs:__imp_GetLastError
0x1400208e0  mov     edi, eax
0x1400208e2  test    eax, eax
0x1400208e4  jle     short loc_1400208EF
0x1400208e6  movzx   edi, ax
0x1400208e9  or      edi, 80070000h
0x1400208ef  mov     r8d, edi
0x1400208f2  lea     rdx, aCvdsserviceUni_10; "CVdsService::UninstallOneDisk, 11, hr=%"...
0x1400208f9  xor     ecx, ecx
0x1400208fb  call    cs:__imp_VdsTraceW
0x140020901  mov     r8d, edi
0x140020904  lea     rdx, aExitCvdsservic; "EXIT CVdsService::UninstallOneDisk, hr="...
0x14002090b  mov     ecx, 2
0x140020910  call    cs:__imp_VdsTraceW
0x140020916  mov     eax, edi
0x140020918  jmp     short loc_14002093B
0x14002091a  mov     ebx, 80070057h
0x14002091f  mov     [rsp+0E0h+var_C0], r12
0x140020924  mov     r8d, ebx
0x140020927  lea     rdx, aCvdsserviceUni_37; "CVdsService::UninstallOneDisk, 1, hr=%l"...
0x14002092e  mov     r9, rsi
0x140020931  xor     ecx, ecx
0x140020933  call    cs:__imp_VdsTraceW
0x140020939  mov     eax, ebx
0x14002093b  mov     rcx, [rbp+57h+var_40]
0x14002093f  xor     rcx, rsp; StackCookie
0x140020942  call    __security_check_cookie
0x140020947  mov     rbx, [rsp+0E0h+arg_0]
0x14002094f  add     rsp, 0B0h
0x140020956  pop     r15
0x140020958  pop     r14
0x14002095a  pop     r13
0x14002095c  pop     r12
0x14002095e  pop     rdi
0x14002095f  pop     rsi
0x140020960  pop     rbp
0x140020961  retn
```
