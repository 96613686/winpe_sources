# CVdsService::GetNameByIdForRaw(_GUID *,ushort * *,unsigned __int64 &)

- ea: `0x140023f58`
- end: `0x140024351`
- name: `?GetNameByIdForRaw@CVdsService@@AEAAJPEAU_GUID@@PEAPEAGAEA_K@Z`
- size: `1017`
- prototype: `__int64 __fastcall(CVdsService *__hidden this, struct _GUID *, unsigned __int16 **, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task`

## callers

- `0x140038c64`

## callees

- `0x1400069e8`
- `0x14001b958`
- `0x140021e60`
- `0x140023f58`
- `0x140052e80`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140024175`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140024247`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400242e3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140024175`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140024247`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400242e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140023ffd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140024058`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400240cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140023ffd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140024058`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400240cd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002430d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002430d`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x1400240be`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x1400240be`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x140023fee`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x140023fee`
- `DEVOBJ!DevObjGetClassDevs` at `0x14002404e`
- `DEVOBJ!DevObjGetClassDevs` at `0x14002404e`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x1400242a7`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x1400242a7`
- `vdsutil!OpenDevice` at `0x1400241aa`
- `vdsutil!OpenDevice` at `0x1400241aa`
- `vdsutil!GetDeviceNumber` at `0x140024201`
- `vdsutil!GetDeviceNumber` at `0x140024201`
- `vdsutil!VdsHeapAlloc` at `0x140024259`
- `vdsutil!VdsHeapAlloc` at `0x140024259`
- `vdsutil!VdsHeapFree` at `0x140024183`
- `vdsutil!VdsHeapFree` at `0x1400242f1`
- `vdsutil!VdsHeapFree` at `0x140024183`
- `vdsutil!VdsHeapFree` at `0x1400242f1`
- `vdsutil!VdsTraceW` at `0x140023fb7`
- `vdsutil!VdsTraceW` at `0x14002401e`
- `vdsutil!VdsTraceW` at `0x140024079`
- `vdsutil!VdsTraceW` at `0x1400240fb`
- `vdsutil!VdsTraceW` at `0x140024128`
- `vdsutil!VdsTraceW` at `0x140024153`
- `vdsutil!VdsTraceW` at `0x1400241e5`
- `vdsutil!VdsTraceW` at `0x14002423f`
- `vdsutil!VdsTraceW` at `0x140024276`
- `vdsutil!VdsTraceW` at `0x1400242bd`
- `vdsutil!VdsTraceW` at `0x1400242d9`
- `vdsutil!VdsTraceW` at `0x14002432a`
- `vdsutil!VdsTraceW` at `0x140023fb7`
- `vdsutil!VdsTraceW` at `0x14002401e`
- `vdsutil!VdsTraceW` at `0x140024079`
- `vdsutil!VdsTraceW` at `0x1400240fb`
- `vdsutil!VdsTraceW` at `0x140024128`
- `vdsutil!VdsTraceW` at `0x140024153`
- `vdsutil!VdsTraceW` at `0x1400241e5`
- `vdsutil!VdsTraceW` at `0x14002423f`
- `vdsutil!VdsTraceW` at `0x140024276`
- `vdsutil!VdsTraceW` at `0x1400242bd`
- `vdsutil!VdsTraceW` at `0x1400242d9`
- `vdsutil!VdsTraceW` at `0x14002432a`

## string_xrefs

- `0x1400240f2`: `CVdsService::GetNameByIdForRaw, 4, hr=%lX`
- `0x140024015`: `CVdsService::GetNameByIdForRaw, 2, hr=%lX`
- `0x14002422f`: `CVdsService::GetNameByIdForRaw, 8, error=%ld, name=%s`
- `0x140024070`: `CVdsService::GetNameByIdForRaw, 3, hr=%lX`
- `0x1400241d8`: `CVdsService::GetNameByIdForRaw, 7, error=%ld, name=%s`
- `0x140023f95`: `CVdsService::GetNameByIdForRaw`
- `0x1400242c8`: `CVdsService::GetNameByIdForRaw, 1, pDiskId=%p, ppName=%p`
- `0x14002411a`: `CVdsService::GetNameByIdForRaw, 5`
- `0x14002414a`: `CVdsService::GetNameByIdForRaw, 6, hr=%lX`
- `0x140024268`: `CVdsService::GetNameByIdForRaw, 9`
- `0x1400242b4`: `CVdsService::GetNameByIdForRaw, 10, hr=%lX`
- `0x14002431e`: `EXIT CVdsService::GetNameByIdForRaw, hr=%lX`

## pseudocode

```c
__int64 __fastcall CVdsService::GetNameByIdForRaw(
        CVdsService *this,
        struct _GUID *a2,
        unsigned __int16 **a3,
        unsigned __int64 *a4)
{
  __int64 DeviceInfoList; // rax
  void *v7; // r14
  signed int LastError; // eax
  unsigned int v9; // edi
  signed int v10; // eax
  unsigned int v11; // r13d
  int v12; // ebx
  CVdsService *v13; // rcx
  signed int v14; // eax
  int DiskId; // eax
  __int64 v16; // rax
  struct _DO_DEVICE_INTERFACE_DETAIL_DATA *v17; // rbx
  HANDLE v18; // rax
  int v19; // eax
  const wchar_t *v20; // r9
  int DeviceNumber; // eax
  const wchar_t *v22; // r9
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v24; // rax
  struct _DO_DEVICE_INTERFACE_DETAIL_DATA *v25; // rbx
  HANDLE v26; // rax
  struct _DO_DEVICE_INTERFACE_DETAIL_DATA *v28; // [rsp+30h] [rbp-49h] BYREF
  int v29; // [rsp+38h] [rbp-41h]
  HANDLE hObject; // [rsp+40h] [rbp-39h] BYREF
  unsigned __int64 *v31; // [rsp+48h] [rbp-31h]
  __int64 v32; // [rsp+50h] [rbp-29h] BYREF
  int v33; // [rsp+58h] [rbp-21h]
  struct _GUID v34; // [rsp+60h] [rbp-19h] BYREF
  __int128 v35; // [rsp+70h] [rbp-9h] BYREF
  __int128 v36; // [rsp+80h] [rbp+7h]

  v31 = a4;
  v32 = 0;
  v33 = 0;
  hObject = 0;
  v28 = 0;
  *a4 = 0;
  v34 = 0;
  v35 = 0;
  v36 = 0;
  VdsTraceW(2, L"CVdsService::GetNameByIdForRaw");
  if ( !a2 || !a3 )
  {
    v9 = -2147024809;
    VdsTraceW(0, L"CVdsService::GetNameByIdForRaw, 1, pDiskId=%p, ppName=%p", a2, a3);
    goto LABEL_49;
  }
  v34 = GUID_NULL;
  DeviceInfoList = DevObjCreateDeviceInfoList(0, 0, 0, 0, 0);
  v7 = (void *)DeviceInfoList;
  if ( DeviceInfoList == -1 )
  {
    LastError = GetLastError();
    v9 = LastError;
    if ( LastError > 0 )
      v9 = (unsigned __int16)LastError | 0x80070000;
    VdsTraceW(0, L"CVdsService::GetNameByIdForRaw, 2, hr=%lX", v9);
LABEL_46:
    if ( !(unsigned int)DevObjDestroyDeviceInfoList(v7) )
      VdsTraceW(0, L"CVdsService::GetNameByIdForRaw, 10, hr=%lX", v9);
    goto LABEL_49;
  }
  if ( (unsigned int)DevObjGetClassDevs(DeviceInfoList, &GUID_DEVINTERFACE_DISK, 0, 18, 0, 0) )
  {
    v9 = 0;
    v11 = 0;
    v12 = 1;
    while ( v12 )
    {
      v35 = 0;
      LODWORD(v35) = 32;
      v36 = 0;
      v29 = DevObjEnumDeviceInterfaces(v7, 0, &GUID_DEVINTERFACE_DISK, v11, &v35);
      v12 = v29;
      if ( v29 )
      {
        if ( (int)CVdsService::GetDeviceDetailData(v13, v7, (struct _DO_DEVICE_INTERFACE_DATA *)&v35, &v28) >= 0 )
        {
          DiskId = CVdsService::GetDiskId((wchar_t *)v28 + 2, &v34);
          v9 = DiskId;
          if ( DiskId >= 0 )
          {
            v16 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&v34.Data1;
            if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&v34.Data1 )
              v16 = *(_QWORD *)a2->Data4 - *(_QWORD *)v34.Data4;
            if ( !v16 )
            {
              v19 = OpenDevice((char *)v28 + 4, 0, &hObject);
              if ( v19 )
              {
                if ( v19 > 0 )
                  v9 = (unsigned __int16)v19 | 0x80070000;
                else
                  v9 = v19;
                v20 = L"UNKNOWN";
                if ( v28 != (struct _DO_DEVICE_INTERFACE_DETAIL_DATA *)-4LL )
                  v20 = (const wchar_t *)((char *)v28 + 4);
                VdsTraceW(0, L"CVdsService::GetNameByIdForRaw, 7, error=%ld, name=%s", (unsigned int)v19, v20);
              }
              else
              {
                v32 = 0;
                v33 = 0;
                DeviceNumber = GetDeviceNumber(hObject, &v32);
                if ( DeviceNumber )
                {
                  if ( DeviceNumber > 0 )
                    v9 = (unsigned __int16)DeviceNumber | 0x80070000;
                  else
                    v9 = DeviceNumber;
                  v22 = L"UNKNOWN";
                  if ( v28 != (struct _DO_DEVICE_INTERFACE_DETAIL_DATA *)-4LL )
                    v22 = (const wchar_t *)((char *)v28 + 4);
                  VdsTraceW(
                    1,
                    L"CVdsService::GetNameByIdForRaw, 8, error=%ld, name=%s",
                    (unsigned int)DeviceNumber,
                    v22);
                }
                else
                {
                  ProcessHeap = GetProcessHeap();
                  v24 = (unsigned __int16 *)VdsHeapAlloc(ProcessHeap, 8, 64);
                  *a3 = v24;
                  if ( v24 )
                  {
                    StringCchPrintfW(v24, 0x20u, L"\\\\?\\PhysicalDrive%lu", HIDWORD(v32));
                    *v31 = 32;
                  }
                  else
                  {
                    v9 = -2147024882;
                    VdsTraceW(0, L"CVdsService::GetNameByIdForRaw, 9");
                  }
                }
              }
              break;
            }
          }
          else
          {
            VdsTraceW(0, L"CVdsService::GetNameByIdForRaw, 6, hr=%lX", (unsigned int)DiskId);
          }
          v17 = v28;
          v18 = GetProcessHeap();
          VdsHeapFree(v18, 0, v17);
          v12 = v29;
          v28 = 0;
        }
        else
        {
          v9 = -2147211505;
          VdsTraceW(0, L"CVdsService::GetNameByIdForRaw, 5");
        }
      }
      else
      {
        v14 = GetLastError();
        if ( v14 == 259 )
          break;
        if ( v14 > 0 )
          v9 = (unsigned __int16)v14 | 0x80070000;
        else
          v9 = v14;
        VdsTraceW(0, L"CVdsService::GetNameByIdForRaw, 4, hr=%lX", v9);
      }
      ++v11;
    }
  }
  else
  {
    v10 = GetLastError();
    v9 = v10;
    if ( v10 > 0 )
      v9 = (unsigned __int16)v10 | 0x80070000;
    VdsTraceW(0, L"CVdsService::GetNameByIdForRaw, 3, hr=%lX", v9);
  }
  if ( v7 )
    goto LABEL_46;
LABEL_49:
  v25 = v28;
  v26 = GetProcessHeap();
  VdsHeapFree(v26, 0, v25);
  v28 = 0;
  if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    CloseHandle(hObject);
    hObject = 0;
  }
  VdsTraceW(2, L"EXIT CVdsService::GetNameByIdForRaw, hr=%lX", v9);
  return v9;
}

```

## disassembly

```asm
0x140023f58  push    rbp
0x140023f5a  push    rbx
0x140023f5b  push    rdi
0x140023f5c  push    r12
0x140023f5e  push    r13
0x140023f60  push    r14
0x140023f62  push    r15
0x140023f64  lea     rbp, [rsp-27h]
0x140023f69  sub     rsp, 0A0h
0x140023f70  mov     rax, cs:__security_cookie
0x140023f77  xor     rax, rsp
0x140023f7a  mov     [rbp+57h+var_40], rax
0x140023f7e  xor     ecx, ecx
0x140023f80  mov     [rbp+57h+var_88], r9
0x140023f84  xorps   xmm0, xmm0
0x140023f87  mov     [rbp+57h+var_80], rcx
0x140023f8b  mov     [rbp+57h+var_78], ecx
0x140023f8e  mov     r15, rdx
0x140023f91  mov     [rbp+57h+hObject], rcx
0x140023f95  lea     rdx, aCvdsserviceGet_130; "CVdsService::GetNameByIdForRaw"
0x140023f9c  mov     [rbp+57h+var_A0], rcx
0x140023fa0  mov     r12, r8
0x140023fa3  mov     [r9], rcx
0x140023fa6  mov     ecx, 2
0x140023fab  movups  xmmword ptr [rbp+57h+var_70.Data1], xmm0
0x140023faf  movups  [rbp+57h+var_60], xmm0
0x140023fb3  movups  [rbp+57h+var_50], xmm0
0x140023fb7  call    cs:__imp_VdsTraceW
0x140023fbd  test    r15, r15
0x140023fc0  jz      loc_1400242C5
0x140023fc6  test    r12, r12
0x140023fc9  jz      loc_1400242C5
0x140023fcf  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x140023fd6  xor     r9d, r9d
0x140023fd9  mov     [rsp+0D0h+var_B0], 0
0x140023fe2  xor     r8d, r8d
0x140023fe5  xor     edx, edx
0x140023fe7  xor     ecx, ecx
0x140023fe9  movdqu  xmmword ptr [rbp+57h+var_70.Data1], xmm0
0x140023fee  call    cs:__imp_DevObjCreateDeviceInfoList
0x140023ff4  mov     r14, rax
0x140023ff7  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140023ffb  jnz     short loc_140024029
0x140023ffd  call    cs:__imp_GetLastError
0x140024003  mov     edi, eax
0x140024005  test    eax, eax
0x140024007  jle     short loc_140024012
0x140024009  movzx   edi, ax
0x14002400c  or      edi, 80070000h
0x140024012  mov     r8d, edi
0x140024015  lea     rdx, aCvdsserviceGet_25; "CVdsService::GetNameByIdForRaw, 2, hr=%"...
0x14002401c  xor     ecx, ecx
0x14002401e  call    cs:__imp_VdsTraceW
0x140024024  jmp     loc_1400242A4
0x140024029  mov     [rsp+0D0h+var_A8], 0
0x140024032  lea     rdx, GUID_DEVINTERFACE_DISK
0x140024039  mov     r9d, 12h
0x14002403f  mov     [rsp+0D0h+var_B0], 0
0x140024048  xor     r8d, r8d
0x14002404b  mov     rcx, r14
0x14002404e  call    cs:__imp_DevObjGetClassDevs
0x140024054  test    eax, eax
0x140024056  jnz     short loc_140024084
0x140024058  call    cs:__imp_GetLastError
0x14002405e  mov     edi, eax
0x140024060  test    eax, eax
0x140024062  jle     short loc_14002406D
0x140024064  movzx   edi, ax
0x140024067  or      edi, 80070000h
0x14002406d  mov     r8d, edi
0x140024070  lea     rdx, aCvdsserviceGet_21; "CVdsService::GetNameByIdForRaw, 3, hr=%"...
0x140024077  xor     ecx, ecx
0x140024079  call    cs:__imp_VdsTraceW
0x14002407f  jmp     loc_14002429F
0x140024084  xor     edi, edi
0x140024086  xor     r13d, r13d
0x140024089  lea     ebx, [rdi+1]
0x14002408c  test    ebx, ebx
0x14002408e  jz      loc_14002429F
0x140024094  xorps   xmm0, xmm0
0x140024097  lea     rax, [rbp+57h+var_60]
0x14002409b  movups  [rbp+57h+var_60], xmm0
0x14002409f  mov     r9d, r13d
0x1400240a2  mov     dword ptr [rbp+57h+var_60], 20h ; ' '
0x1400240a9  lea     r8, GUID_DEVINTERFACE_DISK
0x1400240b0  mov     [rsp+0D0h+var_B0], rax
0x1400240b5  xor     edx, edx
0x1400240b7  mov     rcx, r14
0x1400240ba  movups  [rbp+57h+var_50], xmm0
0x1400240be  call    cs:__imp_DevObjEnumDeviceInterfaces
0x1400240c4  mov     [rbp+57h+var_98], eax
0x1400240c7  mov     ebx, eax
0x1400240c9  test    eax, eax
0x1400240cb  jnz     short loc_140024106
0x1400240cd  call    cs:__imp_GetLastError
0x1400240d3  cmp     eax, 103h
0x1400240d8  jz      loc_14002429F
0x1400240de  test    eax, eax
0x1400240e0  jg      short loc_1400240E6
0x1400240e2  mov     edi, eax
0x1400240e4  jmp     short loc_1400240EF
0x1400240e6  movzx   edi, ax
0x1400240e9  or      edi, 80070000h
0x1400240ef  mov     r8d, edi
0x1400240f2  lea     rdx, aCvdsserviceGet_7; "CVdsService::GetNameByIdForRaw, 4, hr=%"...
0x1400240f9  xor     ecx, ecx
0x1400240fb  call    cs:__imp_VdsTraceW
0x140024101  jmp     loc_140024194
0x140024106  lea     r9, [rbp+57h+var_A0]; struct _DO_DEVICE_INTERFACE_DETAIL_DATA **
0x14002410a  mov     rdx, r14; void *
0x14002410d  lea     r8, [rbp+57h+var_60]; struct _DO_DEVICE_INTERFACE_DATA *
0x140024111  call    ?GetDeviceDetailData@CVdsService@@AEAAJPEAXPEAU_DO_DEVICE_INTERFACE_DATA@@PEAPEAU_DO_DEVICE_INTERFACE_DETAIL_DATA@@@Z; CVdsService::GetDeviceDetailData(void *,_DO_DEVICE_INTERFACE_DATA *,_DO_DEVICE_INTERFACE_DETAIL_DATA * *)
0x140024116  test    eax, eax
0x140024118  jns     short loc_140024130
0x14002411a  lea     rdx, aCvdsserviceGet_100; "CVdsService::GetNameByIdForRaw, 5"
0x140024121  xor     ecx, ecx
0x140024123  mov     edi, 8004270Fh
0x140024128  call    cs:__imp_VdsTraceW
0x14002412e  jmp     short loc_140024194
0x140024130  mov     rcx, [rbp+57h+var_A0]
0x140024134  lea     rdx, [rbp+57h+var_70]; struct _GUID *
0x140024138  add     rcx, 4; String1
0x14002413c  call    ?GetDiskId@CVdsService@@SAJPEAGPEAU_GUID@@@Z; CVdsService::GetDiskId(ushort *,_GUID *)
0x140024141  mov     edi, eax
0x140024143  test    eax, eax
0x140024145  jns     short loc_14002415B
0x140024147  mov     r8d, eax
0x14002414a  lea     rdx, aCvdsserviceGet_1; "CVdsService::GetNameByIdForRaw, 6, hr=%"...
0x140024151  xor     ecx, ecx
0x140024153  call    cs:__imp_VdsTraceW
0x140024159  jmp     short loc_140024171
0x14002415b  mov     rax, [r15]
0x14002415e  sub     rax, qword ptr [rbp+57h+var_70.Data1]
0x140024162  jnz     short loc_14002416C
0x140024164  mov     rax, [r15+8]
0x140024168  sub     rax, qword ptr [rbp+57h+var_70.Data4]
0x14002416c  test    rax, rax
0x14002416f  jz      short loc_14002419C
0x140024171  mov     rbx, [rbp+57h+var_A0]
0x140024175  call    cs:__imp_GetProcessHeap
0x14002417b  mov     r8, rbx
0x14002417e  xor     edx, edx
0x140024180  mov     rcx, rax
0x140024183  call    cs:__imp_VdsHeapFree
0x140024189  mov     ebx, [rbp+57h+var_98]
0x14002418c  mov     [rbp+57h+var_A0], 0
0x140024194  inc     r13d
0x140024197  jmp     loc_14002408C
0x14002419c  mov     rcx, [rbp+57h+var_A0]
0x1400241a0  lea     r8, [rbp+57h+hObject]
0x1400241a4  add     rcx, 4
0x1400241a8  xor     edx, edx
0x1400241aa  call    cs:__imp_OpenDevice
0x1400241b0  mov     r8d, eax
0x1400241b3  test    eax, eax
0x1400241b5  jz      short loc_1400241F0
0x1400241b7  test    eax, eax
0x1400241b9  jg      short loc_1400241BF
0x1400241bb  mov     edi, eax
0x1400241bd  jmp     short loc_1400241C9
0x1400241bf  movzx   edi, r8w
0x1400241c3  or      edi, 80070000h
0x1400241c9  mov     rax, [rbp+57h+var_A0]
0x1400241cd  lea     r9, aUnknown_0; "UNKNOWN"
0x1400241d4  add     rax, 4
0x1400241d8  lea     rdx, aCvdsserviceGet_78; "CVdsService::GetNameByIdForRaw, 7, erro"...
0x1400241df  cmovnz  r9, rax
0x1400241e3  xor     ecx, ecx
0x1400241e5  call    cs:__imp_VdsTraceW
0x1400241eb  jmp     loc_14002429F
0x1400241f0  mov     rcx, [rbp+57h+hObject]
0x1400241f4  lea     rdx, [rbp+57h+var_80]
0x1400241f8  xor     eax, eax
0x1400241fa  mov     [rbp+57h+var_80], rax
0x1400241fe  mov     [rbp+57h+var_78], eax
0x140024201  call    cs:__imp_GetDeviceNumber
0x140024207  mov     r8d, eax
0x14002420a  test    eax, eax
0x14002420c  jz      short loc_140024247
0x14002420e  test    eax, eax
0x140024210  jg      short loc_140024216
0x140024212  mov     edi, eax
0x140024214  jmp     short loc_140024220
0x140024216  movzx   edi, r8w
0x14002421a  or      edi, 80070000h
0x140024220  mov     rax, [rbp+57h+var_A0]
0x140024224  lea     r9, aUnknown_0; "UNKNOWN"
0x14002422b  add     rax, 4
0x14002422f  lea     rdx, aCvdsserviceGet_91; "CVdsService::GetNameByIdForRaw, 8, erro"...
0x140024236  mov     ecx, 1
0x14002423b  cmovnz  r9, rax
0x14002423f  call    cs:__imp_VdsTraceW
0x140024245  jmp     short loc_14002429F
0x140024247  call    cs:__imp_GetProcessHeap
0x14002424d  mov     edx, 8
0x140024252  mov     rcx, rax
0x140024255  lea     r8d, [rdx+38h]
0x140024259  call    cs:__imp_VdsHeapAlloc
0x14002425f  mov     [r12], rax
0x140024263  test    rax, rax
0x140024266  jnz     short loc_14002427E
0x140024268  lea     rdx, aCvdsserviceGet; "CVdsService::GetNameByIdForRaw, 9"
0x14002426f  xor     ecx, ecx
0x140024271  mov     edi, 8007000Eh
0x140024276  call    cs:__imp_VdsTraceW
0x14002427c  jmp     short loc_14002429F
0x14002427e  mov     r9d, dword ptr [rbp+57h+var_80+4]
0x140024282  lea     r8, aPhysicaldriveL; "\\\\?\\PhysicalDrive%lu"
0x140024289  mov     ebx, 20h ; ' '
0x14002428e  mov     rcx, rax; unsigned __int16 *
0x140024291  mov     edx, ebx; unsigned __int64
0x140024293  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140024298  mov     rax, [rbp+57h+var_88]
0x14002429c  mov     [rax], rbx
0x14002429f  test    r14, r14
0x1400242a2  jz      short loc_1400242DF
0x1400242a4  mov     rcx, r14
0x1400242a7  call    cs:__imp_DevObjDestroyDeviceInfoList
0x1400242ad  test    eax, eax
0x1400242af  jnz     short loc_1400242DF
0x1400242b1  mov     r8d, edi
0x1400242b4  lea     rdx, aCvdsserviceGet_103; "CVdsService::GetNameByIdForRaw, 10, hr="...
0x1400242bb  xor     ecx, ecx
0x1400242bd  call    cs:__imp_VdsTraceW
0x1400242c3  jmp     short loc_1400242DF
0x1400242c5  mov     r9, r12
0x1400242c8  lea     rdx, aCvdsserviceGet_73; "CVdsService::GetNameByIdForRaw, 1, pDis"...
0x1400242cf  mov     r8, r15
0x1400242d2  xor     ecx, ecx
0x1400242d4  mov     edi, 80070057h
0x1400242d9  call    cs:__imp_VdsTraceW
0x1400242df  mov     rbx, [rbp+57h+var_A0]
0x1400242e3  call    cs:__imp_GetProcessHeap
0x1400242e9  mov     r8, rbx
0x1400242ec  xor     edx, edx
0x1400242ee  mov     rcx, rax
0x1400242f1  call    cs:__imp_VdsHeapFree
0x1400242f7  mov     rcx, [rbp+57h+hObject]; hObject
0x1400242fb  mov     [rbp+57h+var_A0], 0
0x140024303  lea     rax, [rcx-1]
0x140024307  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14002430b  ja      short loc_14002431B
0x14002430d  call    cs:__imp_CloseHandle
0x140024313  mov     [rbp+57h+hObject], 0
0x14002431b  mov     r8d, edi
0x14002431e  lea     rdx, aExitCvdsservic_4; "EXIT CVdsService::GetNameByIdForRaw, hr"...
0x140024325  mov     ecx, 2
0x14002432a  call    cs:__imp_VdsTraceW
0x140024330  mov     eax, edi
0x140024332  mov     rcx, [rbp+57h+var_40]
0x140024336  xor     rcx, rsp; StackCookie
0x140024339  call    __security_check_cookie
0x14002433e  add     rsp, 0A0h
0x140024345  pop     r15
0x140024347  pop     r14
0x140024349  pop     r13
0x14002434b  pop     r12
0x14002434d  pop     rdi
0x14002434e  pop     rbx
0x14002434f  pop     rbp
0x140024350  retn
```
