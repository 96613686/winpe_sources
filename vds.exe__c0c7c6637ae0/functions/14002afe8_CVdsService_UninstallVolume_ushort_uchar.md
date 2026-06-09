# CVdsService::UninstallVolume(ushort *,uchar *)

- ea: `0x14002afe8`
- end: `0x14002b3f1`
- name: `?UninstallVolume@CVdsService@@AEAAJPEAGPEAE@Z`
- size: `1033`
- prototype: `int(CVdsService *__hidden this, unsigned __int16 *, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task, installer_update`

## callers

- `0x140022400`

## callees

- `0x14002afe8`
- `0x14002e123`
- `0x14003ce68`
- `0x14003d420`
- `0x140052e80`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x14002b27d`
- `msvcrt!_wcsnicmp` at `0x14002b27d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14002b1ab`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14002b1ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002b09b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002b0f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002b29d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002b30c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002b367`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002b09b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002b0f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002b29d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002b30c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002b367`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002b215`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002b215`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x14002b14e`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x14002b14e`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x14002b08c`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x14002b08c`
- `DEVOBJ!DevObjGetClassDevs` at `0x14002b0ec`
- `DEVOBJ!DevObjGetClassDevs` at `0x14002b0ec`
- `DEVOBJ!DevObjEnumDeviceInfo` at `0x14002b302`
- `DEVOBJ!DevObjEnumDeviceInfo` at `0x14002b302`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x14002b35d`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x14002b35d`
- `vdsutil!OpenDevice` at `0x14002b19c`
- `vdsutil!OpenDevice` at `0x14002b19c`
- `vdsutil!GetDeviceName` at `0x14002b1fb`
- `vdsutil!GetDeviceName` at `0x14002b1fb`
- `vdsutil!VdsHeapFree` at `0x14002b1b9`
- `vdsutil!VdsHeapFree` at `0x14002b1b9`
- `vdsutil!GetInterfaceDetailData` at `0x14002b169`
- `vdsutil!GetInterfaceDetailData` at `0x14002b169`
- `vdsutil!VdsTraceW` at `0x14002b05c`
- `vdsutil!VdsTraceW` at `0x14002b0bc`
- `vdsutil!VdsTraceW` at `0x14002b182`
- `vdsutil!VdsTraceW` at `0x14002b26b`
- `vdsutil!VdsTraceW` at `0x14002b2b6`
- `vdsutil!VdsTraceW` at `0x14002b2d7`
- `vdsutil!VdsTraceW` at `0x14002b34f`
- `vdsutil!VdsTraceW` at `0x14002b388`
- `vdsutil!VdsTraceW` at `0x14002b39d`
- `vdsutil!VdsTraceW` at `0x14002b3be`
- `vdsutil!VdsTraceW` at `0x14002b05c`
- `vdsutil!VdsTraceW` at `0x14002b0bc`
- `vdsutil!VdsTraceW` at `0x14002b182`
- `vdsutil!VdsTraceW` at `0x14002b26b`
- `vdsutil!VdsTraceW` at `0x14002b2b6`
- `vdsutil!VdsTraceW` at `0x14002b2d7`
- `vdsutil!VdsTraceW` at `0x14002b34f`
- `vdsutil!VdsTraceW` at `0x14002b388`
- `vdsutil!VdsTraceW` at `0x14002b39d`
- `vdsutil!VdsTraceW` at `0x14002b3be`

## string_xrefs

- `0x14002b0b3`: `CVdsService::UninstallVolume, 2, hr=%lX`
- `0x14002b324`: `CVdsService::UninstallVolume, 9, hr=%lX`
- `0x14002b10e`: `CVdsService::UninstallVolume, 3, hr=%lX`
- `0x14002b37f`: `CVdsService::UninstallVolume, 11, hr=%lX`
- `0x14002b391`: `EXIT CVdsService::UninstallVolume, hr=%lX`
- `0x14002b03a`: `CVdsService::UninstallVolume`
- `0x14002b3b2`: `CVdsService::UninstallVolume, 1, hr=%lX, pName=%p, pbRebootReq=%p`
- `0x14002b2ad`: `CVdsService::UninstallVolume, 4, error=%ld`
- `0x14002b173`: `CVdsService::UninstallVolume, 5, error=%ld, name=%s`
- `0x14002b1d0`: `CVdsService::UninstallVolume, 6, error=%ld, name=%s`
- `0x14002b22b`: `CVdsService::UninstallVolume, 7, error=%ld, name=%s`
- `0x14002b291`: `CVdsService::UninstallVolume, 7.5, hr=%lX, name=%s`
- `0x14002b262`: `CVdsService::UninstallVolume, 7.7,  name=%s`
- `0x14002b2c8`: `CVdsService::UninstallVolume, 8, error=%lX, name=%s`
- `0x14002b346`: `CVdsService::UninstallVolume, 10, hr=%lX`

## pseudocode

```c
__int64 __fastcall CVdsService::UninstallVolume(CVdsService *this, unsigned __int16 *a2, unsigned __int8 *a3)
{
  __int64 DeviceInfoList; // rax
  void *v6; // r14
  signed int LastError; // eax
  unsigned int v8; // ebx
  signed int v9; // eax
  unsigned int v10; // edi
  unsigned int InterfaceDetailData; // eax
  int v12; // eax
  __int64 v13; // rbx
  HANDLE ProcessHeap; // rax
  size_t v15; // rdx
  unsigned int DeviceName; // ebx
  HRESULT v17; // eax
  DWORD v18; // eax
  CVdsService *v19; // rcx
  signed int v20; // eax
  int v21; // eax
  signed int v22; // eax
  size_t pcchLength; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v25; // [rsp+38h] [rbp-C8h] BYREF
  HANDLE hObject; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v27; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v28; // [rsp+58h] [rbp-A8h]
  __int128 v29; // [rsp+68h] [rbp-98h] BYREF
  __int128 v30; // [rsp+78h] [rbp-88h]
  __int128 v31; // [rsp+88h] [rbp-78h]
  wchar_t String1[280]; // [rsp+A0h] [rbp-60h] BYREF

  hObject = 0;
  v25 = 0;
  v27 = 0;
  v28 = 0;
  v29 = 0;
  v30 = 0;
  v31 = 0;
  VdsTraceW(2, L"CVdsService::UninstallVolume");
  if ( !a2 || !a3 )
  {
    v8 = -2147024809;
    VdsTraceW(0, L"CVdsService::UninstallVolume, 1, hr=%lX, pName=%p, pbRebootReq=%p", 2147942487LL, a2, a3);
    return v8;
  }
  *a3 = 0;
  DeviceInfoList = DevObjCreateDeviceInfoList(0, 0, 0, 0, 0);
  v6 = (void *)DeviceInfoList;
  if ( DeviceInfoList == -1 )
  {
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError > 0 )
      v8 = (unsigned __int16)LastError | 0x80070000;
    VdsTraceW(0, L"CVdsService::UninstallVolume, 2, hr=%lX", v8);
    goto LABEL_38;
  }
  if ( !(unsigned int)DevObjGetClassDevs(DeviceInfoList, &GUID_DEVINTERFACE_DISK, 0, 18, 0, 0) )
  {
    v9 = GetLastError();
    v8 = v9;
    if ( v9 > 0 )
      v8 = (unsigned __int16)v9 | 0x80070000;
    VdsTraceW(0, L"CVdsService::UninstallVolume, 3, hr=%lX", v8);
    goto LABEL_37;
  }
  v10 = 0;
  while ( 1 )
  {
    v27 = 0;
    LODWORD(v27) = 32;
    v28 = 0;
    if ( !(unsigned int)DevObjEnumDeviceInterfaces(v6, 0, &GUID_DEVINTERFACE_VOLUME, v10, &v27) )
      break;
    InterfaceDetailData = GetInterfaceDetailData(v6, &v27, &v25);
    if ( InterfaceDetailData )
    {
      VdsTraceW(0, L"CVdsService::UninstallVolume, 5, error=%ld, name=%s", InterfaceDetailData, a2);
      goto LABEL_15;
    }
    v12 = OpenDevice(v25 + 4, 0, &hObject);
    v13 = v25;
    LODWORD(pcchLength) = v12;
    ProcessHeap = GetProcessHeap();
    VdsHeapFree(ProcessHeap, 0, v13);
    v25 = 0;
    if ( (_DWORD)pcchLength )
    {
      VdsTraceW(0, L"CVdsService::UninstallVolume, 6, error=%ld, name=%s", (unsigned int)pcchLength, a2);
      goto LABEL_15;
    }
    memset_0(String1, 0, 0x224u);
    DeviceName = GetDeviceName(hObject, 0, 274, String1);
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      CloseHandle(hObject);
      hObject = 0;
    }
    if ( DeviceName )
    {
      VdsTraceW(0, L"CVdsService::UninstallVolume, 7, error=%ld, name=%s", DeviceName, a2);
      goto LABEL_15;
    }
    pcchLength = 0;
    v17 = StringLengthWorkerW(a2, v15, &pcchLength);
    if ( v17 < 0 )
    {
      VdsTraceW(0, L"CVdsService::UninstallVolume, 7.5, hr=%lX, name=%s", (unsigned int)v17, a2);
LABEL_15:
      ++v10;
    }
    else
    {
      if ( !(2 * pcchLength) )
      {
        VdsTraceW(0, L"CVdsService::UninstallVolume, 7.7,  name=%s", a2);
        goto LABEL_15;
      }
      if ( !_wcsnicmp(String1, a2, 2 * pcchLength) )
      {
        v29 = 0;
        LODWORD(v29) = 48;
        v30 = 0;
        v31 = 0;
        if ( (unsigned int)DevObjEnumDeviceInfo(v6, v10, &v29) )
        {
          v21 = CVdsService::UninstallDevice(v19, v6, (struct _DO_DEVINFO_DATA *)&v29, a3);
          v8 = v21;
          if ( v21 < 0 )
            VdsTraceW(0, L"CVdsService::UninstallVolume, 10, hr=%lX", (unsigned int)v21);
        }
        else
        {
          v20 = GetLastError();
          v8 = v20;
          if ( v20 > 0 )
            v8 = (unsigned __int16)v20 | 0x80070000;
          VdsTraceW(0, L"CVdsService::UninstallVolume, 9, hr=%lX", v8);
        }
        goto LABEL_37;
      }
      ++v10;
    }
  }
  v18 = GetLastError();
  if ( v18 != 259 )
    VdsTraceW(0, L"CVdsService::UninstallVolume, 4, error=%ld", v18);
  v8 = -2147212283;
  VdsTraceW(0, L"CVdsService::UninstallVolume, 8, error=%lX, name=%s", 2147755013LL, a2);
LABEL_37:
  if ( v6 )
  {
LABEL_38:
    if ( !(unsigned int)DevObjDestroyDeviceInfoList(v6) )
    {
      v22 = GetLastError();
      v8 = v22;
      if ( v22 > 0 )
        v8 = (unsigned __int16)v22 | 0x80070000;
      VdsTraceW(0, L"CVdsService::UninstallVolume, 11, hr=%lX", v8);
    }
  }
  VdsTraceW(2, L"EXIT CVdsService::UninstallVolume, hr=%lX", v8);
  return v8;
}

```

## disassembly

```asm
0x14002afe8  mov     [rsp-8+arg_0], rbx
0x14002afed  mov     [rsp-8+arg_18], rsi
0x14002aff2  push    rbp
0x14002aff3  push    rdi
0x14002aff4  push    r12
0x14002aff6  push    r13
0x14002aff8  push    r14
0x14002affa  lea     rbp, [rsp-1E0h]
0x14002b002  sub     rsp, 2E0h
0x14002b009  mov     rax, cs:__security_cookie
0x14002b010  xor     rax, rsp
0x14002b013  mov     [rbp+200h+var_30], rax
0x14002b01a  xorps   xmm1, xmm1
0x14002b01d  mov     [rsp+300h+hObject], 0
0x14002b026  xorps   xmm0, xmm0
0x14002b029  mov     [rsp+300h+var_2C8], 0
0x14002b032  mov     rsi, rdx
0x14002b035  mov     ecx, 2
0x14002b03a  lea     rdx, aCvdsserviceUni_31; "CVdsService::UninstallVolume"
0x14002b041  mov     r12, r8
0x14002b044  movups  [rsp+300h+var_2B8], xmm0
0x14002b049  movups  [rsp+300h+var_2A8], xmm0
0x14002b04e  movups  [rsp+300h+var_298], xmm1
0x14002b053  movups  [rsp+300h+var_288], xmm1
0x14002b058  movups  [rbp+200h+var_278], xmm1
0x14002b05c  call    cs:__imp_VdsTraceW
0x14002b062  test    rsi, rsi
0x14002b065  jz      loc_14002B3A5
0x14002b06b  test    r12, r12
0x14002b06e  jz      loc_14002B3A5
0x14002b074  xor     r9d, r9d
0x14002b077  mov     byte ptr [r12], 0
0x14002b07c  xor     r8d, r8d
0x14002b07f  mov     [rsp+300h+var_2E0], 0
0x14002b088  xor     edx, edx
0x14002b08a  xor     ecx, ecx
0x14002b08c  call    cs:__imp_DevObjCreateDeviceInfoList
0x14002b092  mov     r14, rax
0x14002b095  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14002b099  jnz     short loc_14002B0C7
0x14002b09b  call    cs:__imp_GetLastError
0x14002b0a1  mov     ebx, eax
0x14002b0a3  test    eax, eax
0x14002b0a5  jle     short loc_14002B0B0
0x14002b0a7  movzx   ebx, ax
0x14002b0aa  or      ebx, 80070000h
0x14002b0b0  mov     r8d, ebx
0x14002b0b3  lea     rdx, aCvdsserviceUni_22; "CVdsService::UninstallVolume, 2, hr=%lX"
0x14002b0ba  xor     ecx, ecx
0x14002b0bc  call    cs:__imp_VdsTraceW
0x14002b0c2  jmp     loc_14002B35A
0x14002b0c7  mov     [rsp+300h+var_2D8], 0
0x14002b0d0  lea     rdx, GUID_DEVINTERFACE_DISK
0x14002b0d7  mov     r9d, 12h
0x14002b0dd  mov     [rsp+300h+var_2E0], 0
0x14002b0e6  xor     r8d, r8d
0x14002b0e9  mov     rcx, r14
0x14002b0ec  call    cs:__imp_DevObjGetClassDevs
0x14002b0f2  test    eax, eax
0x14002b0f4  jnz     short loc_14002B11A
0x14002b0f6  call    cs:__imp_GetLastError
0x14002b0fc  mov     ebx, eax
0x14002b0fe  test    eax, eax
0x14002b100  jle     short loc_14002B10B
0x14002b102  movzx   ebx, ax
0x14002b105  or      ebx, 80070000h
0x14002b10b  mov     r8d, ebx
0x14002b10e  lea     rdx, aCvdsserviceUni_2; "CVdsService::UninstallVolume, 3, hr=%lX"
0x14002b115  jmp     loc_14002B34D
0x14002b11a  xor     edi, edi
0x14002b11c  lea     r13d, [rdi+0Fh]
0x14002b120  xorps   xmm0, xmm0
0x14002b123  lea     rax, [rsp+300h+var_2B8]
0x14002b128  movups  [rsp+300h+var_2B8], xmm0
0x14002b12d  mov     r9d, edi
0x14002b130  mov     dword ptr [rsp+300h+var_2B8], 20h ; ' '
0x14002b138  lea     r8, GUID_DEVINTERFACE_VOLUME
0x14002b13f  mov     [rsp+300h+var_2E0], rax
0x14002b144  xor     edx, edx
0x14002b146  mov     rcx, r14
0x14002b149  movups  [rsp+300h+var_2A8], xmm0
0x14002b14e  call    cs:__imp_DevObjEnumDeviceInterfaces
0x14002b154  test    eax, eax
0x14002b156  jz      loc_14002B29D
0x14002b15c  lea     r8, [rsp+300h+var_2C8]
0x14002b161  mov     rcx, r14
0x14002b164  lea     rdx, [rsp+300h+var_2B8]
0x14002b169  call    cs:__imp_GetInterfaceDetailData
0x14002b16f  test    eax, eax
0x14002b171  jz      short loc_14002B18C
0x14002b173  lea     rdx, aCvdsserviceUni_1; "CVdsService::UninstallVolume, 5, error="...
0x14002b17a  mov     r8d, eax
0x14002b17d  mov     r9, rsi
0x14002b180  xor     ecx, ecx
0x14002b182  call    cs:__imp_VdsTraceW
0x14002b188  inc     edi
0x14002b18a  jmp     short loc_14002B120
0x14002b18c  mov     rcx, [rsp+300h+var_2C8]
0x14002b191  lea     r8, [rsp+300h+hObject]
0x14002b196  add     rcx, 4
0x14002b19a  xor     edx, edx
0x14002b19c  call    cs:__imp_OpenDevice
0x14002b1a2  mov     rbx, [rsp+300h+var_2C8]
0x14002b1a7  mov     dword ptr [rsp+300h+pcchLength], eax
0x14002b1ab  call    cs:__imp_GetProcessHeap
0x14002b1b1  mov     r8, rbx
0x14002b1b4  xor     edx, edx
0x14002b1b6  mov     rcx, rax
0x14002b1b9  call    cs:__imp_VdsHeapFree
0x14002b1bf  mov     eax, dword ptr [rsp+300h+pcchLength]
0x14002b1c3  mov     [rsp+300h+var_2C8], 0
0x14002b1cc  test    eax, eax
0x14002b1ce  jz      short loc_14002B1D9
0x14002b1d0  lea     rdx, aCvdsserviceUni_29; "CVdsService::UninstallVolume, 6, error="...
0x14002b1d7  jmp     short loc_14002B17A
0x14002b1d9  xor     edx, edx; Val
0x14002b1db  lea     rcx, [rbp+200h+String1]; void *
0x14002b1df  mov     r8d, 224h; Size
0x14002b1e5  call    memset_0
0x14002b1ea  mov     rcx, [rsp+300h+hObject]
0x14002b1ef  lea     r9, [rbp+200h+String1]
0x14002b1f3  xor     edx, edx
0x14002b1f5  mov     r8d, 112h
0x14002b1fb  call    cs:__imp_GetDeviceName
0x14002b201  mov     ebx, eax
0x14002b203  mov     rax, [rsp+300h+hObject]
0x14002b208  lea     rcx, [rax-1]
0x14002b20c  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x14002b210  ja      short loc_14002B224
0x14002b212  mov     rcx, rax; hObject
0x14002b215  call    cs:__imp_CloseHandle
0x14002b21b  mov     [rsp+300h+hObject], 0
0x14002b224  test    ebx, ebx
0x14002b226  jz      short loc_14002B237
0x14002b228  mov     r8d, ebx
0x14002b22b  lea     rdx, aCvdsserviceUni_20; "CVdsService::UninstallVolume, 7, error="...
0x14002b232  jmp     loc_14002B17D
0x14002b237  lea     r8, [rsp+300h+pcchLength]; pcchLength
0x14002b23c  mov     [rsp+300h+pcchLength], 0
0x14002b245  mov     rcx, rsi; psz
0x14002b248  call    StringLengthWorkerW
0x14002b24d  test    eax, eax
0x14002b24f  js      short loc_14002B291
0x14002b251  mov     rax, [rsp+300h+pcchLength]
0x14002b256  lea     r8, [rax+rax]; MaxCount
0x14002b25a  test    r8, r8
0x14002b25d  jnz     short loc_14002B276
0x14002b25f  mov     r8, rsi
0x14002b262  lea     rdx, aCvdsserviceUni_4; "CVdsService::UninstallVolume, 7.7,  nam"...
0x14002b269  xor     ecx, ecx
0x14002b26b  call    cs:__imp_VdsTraceW
0x14002b271  jmp     loc_14002B188
0x14002b276  mov     rdx, rsi; String2
0x14002b279  lea     rcx, [rbp+200h+String1]; String1
0x14002b27d  call    cs:__imp__wcsnicmp
0x14002b283  mov     r13d, eax
0x14002b286  test    eax, eax
0x14002b288  jz      short loc_14002B2DF
0x14002b28a  inc     edi
0x14002b28c  jmp     loc_14002B120
0x14002b291  lea     rdx, aCvdsserviceUni_28; "CVdsService::UninstallVolume, 7.5, hr=%"...
0x14002b298  jmp     loc_14002B17A
0x14002b29d  call    cs:__imp_GetLastError
0x14002b2a3  cmp     eax, 103h
0x14002b2a8  jz      short loc_14002B2BE
0x14002b2aa  mov     r8d, eax
0x14002b2ad  lea     rdx, aCvdsserviceUni_30; "CVdsService::UninstallVolume, 4, error="...
0x14002b2b4  xor     ecx, ecx
0x14002b2b6  call    cs:__imp_VdsTraceW
0x14002b2bc  inc     edi
0x14002b2be  test    r13d, r13d
0x14002b2c1  jz      short loc_14002B2DF
0x14002b2c3  mov     ebx, 80042405h
0x14002b2c8  lea     rdx, aCvdsserviceUni_32; "CVdsService::UninstallVolume, 8, error="...
0x14002b2cf  mov     r8d, ebx
0x14002b2d2  mov     r9, rsi
0x14002b2d5  xor     ecx, ecx
0x14002b2d7  call    cs:__imp_VdsTraceW
0x14002b2dd  jmp     short loc_14002B355
0x14002b2df  xorps   xmm0, xmm0
0x14002b2e2  lea     r8, [rsp+300h+var_298]
0x14002b2e7  movups  [rsp+300h+var_298], xmm0
0x14002b2ec  mov     edx, edi
0x14002b2ee  mov     dword ptr [rsp+300h+var_298], 30h ; '0'
0x14002b2f6  mov     rcx, r14
0x14002b2f9  movups  [rsp+300h+var_288], xmm0
0x14002b2fe  movups  [rbp+200h+var_278], xmm0
0x14002b302  call    cs:__imp_DevObjEnumDeviceInfo
0x14002b308  test    eax, eax
0x14002b30a  jnz     short loc_14002B32D
0x14002b30c  call    cs:__imp_GetLastError
0x14002b312  mov     ebx, eax
0x14002b314  test    eax, eax
0x14002b316  jle     short loc_14002B321
0x14002b318  movzx   ebx, ax
0x14002b31b  or      ebx, 80070000h
0x14002b321  mov     r8d, ebx
0x14002b324  lea     rdx, aCvdsserviceUni_16; "CVdsService::UninstallVolume, 9, hr=%lX"
0x14002b32b  jmp     short loc_14002B34D
0x14002b32d  mov     r9, r12; unsigned __int8 *
0x14002b330  lea     r8, [rsp+300h+var_298]; struct _DO_DEVINFO_DATA *
0x14002b335  mov     rdx, r14; void *
0x14002b338  call    ?UninstallDevice@CVdsService@@AEAAJPEAXPEAU_DO_DEVINFO_DATA@@PEAE@Z; CVdsService::UninstallDevice(void *,_DO_DEVINFO_DATA *,uchar *)
0x14002b33d  mov     ebx, eax
0x14002b33f  test    eax, eax
0x14002b341  jns     short loc_14002B355
0x14002b343  mov     r8d, eax
0x14002b346  lea     rdx, aCvdsserviceUni_40; "CVdsService::UninstallVolume, 10, hr=%l"...
0x14002b34d  xor     ecx, ecx
0x14002b34f  call    cs:__imp_VdsTraceW
0x14002b355  test    r14, r14
0x14002b358  jz      short loc_14002B38E
0x14002b35a  mov     rcx, r14
0x14002b35d  call    cs:__imp_DevObjDestroyDeviceInfoList
0x14002b363  test    eax, eax
0x14002b365  jnz     short loc_14002B38E
0x14002b367  call    cs:__imp_GetLastError
0x14002b36d  mov     ebx, eax
0x14002b36f  test    eax, eax
0x14002b371  jle     short loc_14002B37C
0x14002b373  movzx   ebx, ax
0x14002b376  or      ebx, 80070000h
0x14002b37c  mov     r8d, ebx
0x14002b37f  lea     rdx, aCvdsserviceUni_8; "CVdsService::UninstallVolume, 11, hr=%l"...
0x14002b386  xor     ecx, ecx
0x14002b388  call    cs:__imp_VdsTraceW
0x14002b38e  mov     r8d, ebx
0x14002b391  lea     rdx, aExitCvdsservic_1; "EXIT CVdsService::UninstallVolume, hr=%"...
0x14002b398  mov     ecx, 2
0x14002b39d  call    cs:__imp_VdsTraceW
0x14002b3a3  jmp     short loc_14002B3C4
0x14002b3a5  mov     ebx, 80070057h
0x14002b3aa  mov     [rsp+300h+var_2E0], r12
0x14002b3af  mov     r8d, ebx
0x14002b3b2  lea     rdx, aCvdsserviceUni_41; "CVdsService::UninstallVolume, 1, hr=%lX"...
0x14002b3b9  mov     r9, rsi
0x14002b3bc  xor     ecx, ecx
0x14002b3be  call    cs:__imp_VdsTraceW
0x14002b3c4  mov     eax, ebx
0x14002b3c6  mov     rcx, [rbp+200h+var_30]
0x14002b3cd  xor     rcx, rsp; StackCookie
0x14002b3d0  call    __security_check_cookie
0x14002b3d5  lea     r11, [rsp+300h+var_20]
0x14002b3dd  mov     rbx, [r11+30h]
0x14002b3e1  mov     rsi, [r11+48h]
0x14002b3e5  mov     rsp, r11
0x14002b3e8  pop     r14
0x14002b3ea  pop     r13
0x14002b3ec  pop     r12
0x14002b3ee  pop     rdi
0x14002b3ef  pop     rbp
0x14002b3f0  retn
```
