# CUrbDrManager::OnDeviceEvent_GUID_DEVINTERFACE_TSUSBHUB(ulong,_DEV_BROADCAST_DEVICEINTERFACE_W *)

- ea: `0x180030710`
- end: `0x180030b33`
- name: `?OnDeviceEvent_GUID_DEVINTERFACE_TSUSBHUB@CUrbDrManager@@QEAAXKPEAU_DEV_BROADCAST_DEVICEINTERFACE_W@@@Z`
- size: `1059`
- prototype: `void __fastcall(CUrbDrManager *__hidden this, unsigned int, struct _DEV_BROADCAST_DEVICEINTERFACE_W *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x180002170`

## callees

- `0x18000b8f8`
- `0x18000b98c`
- `0x18000f75c`
- `0x180019d80`
- `0x180019d90`
- `0x18001ba64`
- `0x18002ed64`
- `0x180030710`
- `0x180047ef0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003079d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030836`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800308ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003093f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003094a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030a47`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003079d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030836`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800308ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003093f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003094a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030a47`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x180030788`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x180030788`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x180030afd`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x180030afd`
- `DEVOBJ!DevObjEnumDeviceInfo` at `0x1800308c0`
- `DEVOBJ!DevObjEnumDeviceInfo` at `0x1800308c0`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x180030935`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x180030a3d`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x180030935`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x180030a3d`
- `DEVOBJ!DevObjOpenDeviceInterface` at `0x18003082c`
- `DEVOBJ!DevObjOpenDeviceInterface` at `0x18003082c`

## string_xrefs

- `0x180030881`: `DevObjOpenDeviceInterface failed`
- `0x1800307e3`: `DevObjCreateDeviceInfoList failed`

## pseudocode

```c
void __fastcall CUrbDrManager::OnDeviceEvent_GUID_DEVINTERFACE_TSUSBHUB(
        CUrbDrManager *this,
        int a2,
        struct _DEV_BROADCAST_DEVICEINTERFACE_W *a3)
{
  WCHAR *v3; // r14
  __int64 DeviceInfoList; // rdi
  signed int LastError; // eax
  signed int v8; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  signed int v10; // eax
  signed int v11; // ebx
  unsigned int v12; // eax
  int v13; // edx
  const char *v14; // rcx
  signed int v15; // eax
  signed int v16; // eax
  WCHAR *v17; // rax
  unsigned int v18; // eax
  signed int v19; // eax
  unsigned int v20; // eax
  size_t size; // [rsp+30h] [rbp-29h] BYREF
  _OWORD v22[2]; // [rsp+38h] [rbp-21h] BYREF
  _OWORD v23[3]; // [rsp+58h] [rbp-1h] BYREF

  size = 0;
  v3 = 0;
  memset(v22, 0, sizeof(v22));
  memset(v23, 0, sizeof(v23));
  if ( a2 != 0x8000 )
    goto LABEL_58;
  DeviceInfoList = DevObjCreateDeviceInfoList(0, 0, 0, 0, 0);
  if ( DeviceInfoList == -1 )
  {
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError > 0 )
      v8 = (unsigned __int16)LastError | 0x80070000;
    if ( v8 < 0 )
    {
      if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) != 0
        && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DsD(
          *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
          33,
          (unsigned int)WPP_e96ad774d77a3b20501daafc53de2dbd_Traceguids,
          CurrentThreadActivityIdPrefix,
          (__int64)"DevObjCreateDeviceInfoList failed",
          v8);
      }
      goto LABEL_58;
    }
  }
  LODWORD(v22[0]) = 32;
  if ( (unsigned int)DevObjOpenDeviceInterface(DeviceInfoList, a3->dbcc_name, 0, v22) )
    goto LABEL_20;
  v10 = GetLastError();
  v11 = v10;
  if ( v10 > 0 )
    v11 = (unsigned __int16)v10 | 0x80070000;
  if ( v11 >= 0 )
  {
LABEL_20:
    LODWORD(v23[0]) = 48;
    if ( (unsigned int)DevObjEnumDeviceInfo(DeviceInfoList, 0, v23) )
      goto LABEL_32;
    v15 = GetLastError();
    v11 = v15;
    if ( v15 > 0 )
      v11 = (unsigned __int16)v15 | 0x80070000;
    if ( v11 >= 0 )
    {
LABEL_32:
      if ( (unsigned int)DevObjGetDeviceInterfaceDetail(DeviceInfoList, v22, 0, 0, &size, 0) || GetLastError() == 122 )
        goto LABEL_38;
      v16 = GetLastError();
      v11 = v16;
      if ( v16 > 0 )
        v11 = (unsigned __int16)v16 | 0x80070000;
      if ( v11 >= 0 )
      {
LABEL_38:
        operator delete(0);
        v17 = (WCHAR *)MIDL_user_allocate((unsigned int)size);
        v3 = v17;
        if ( !v17 )
        {
          if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) != 0
            && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
          {
            v18 = RdpWppGetCurrentThreadActivityIdPrefix();
            WPP_SF_Ds(
              *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
              37,
              (unsigned int)WPP_e96ad774d77a3b20501daafc53de2dbd_Traceguids,
              v18,
              (__int64)"CHAR");
          }
          goto LABEL_56;
        }
        *(_DWORD *)v17 = 8;
        if ( (unsigned int)DevObjGetDeviceInterfaceDetail(
                             DeviceInfoList,
                             v22,
                             v17,
                             (unsigned int)size,
                             (char *)&size + 4,
                             0) )
          goto LABEL_51;
        v19 = GetLastError();
        v11 = v19;
        if ( v19 > 0 )
          v11 = (unsigned __int16)v19 | 0x80070000;
        if ( v11 >= 0 )
        {
LABEL_51:
          v3[((unsigned int)(size - 4) >> 1) + 1] = 0;
          if ( (int)CUrbDrManager::AddDeviceToList(this, v3 + 2) < 0
            && *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 1) != 0
            && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
          {
            v20 = RdpWppGetCurrentThreadActivityIdPrefix();
            WPP_SF_D(
              *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
              39,
              WPP_e96ad774d77a3b20501daafc53de2dbd_Traceguids,
              v20);
          }
          goto LABEL_56;
        }
        if ( *(unsigned int **)&WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) == 0
          || *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) < 2u )
        {
          goto LABEL_56;
        }
        v12 = RdpWppGetCurrentThreadActivityIdPrefix();
        v13 = 38;
      }
      else
      {
        if ( *(unsigned int **)&WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) == 0
          || *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) < 2u )
        {
          goto LABEL_56;
        }
        v12 = RdpWppGetCurrentThreadActivityIdPrefix();
        v13 = 36;
      }
      v14 = "DevObjGetDeviceInterfaceDetail failed";
      goto LABEL_19;
    }
    if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) != 0
      && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
    {
      v12 = RdpWppGetCurrentThreadActivityIdPrefix();
      v13 = 35;
      goto LABEL_18;
    }
  }
  else if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) != 0
         && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
  {
    v12 = RdpWppGetCurrentThreadActivityIdPrefix();
    v13 = 34;
LABEL_18:
    v14 = "DevObjOpenDeviceInterface failed";
LABEL_19:
    WPP_SF_DsD(
      *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
      v13,
      (unsigned int)WPP_e96ad774d77a3b20501daafc53de2dbd_Traceguids,
      v12,
      (__int64)v14,
      v11);
  }
LABEL_56:
  if ( DeviceInfoList != -1 )
    DevObjDestroyDeviceInfoList(DeviceInfoList);
LABEL_58:
  operator delete(v3);
}

```

## disassembly

```asm
0x180030710  mov     [rsp-8+arg_8], rbx
0x180030715  mov     [rsp-8+arg_18], rsi
0x18003071a  push    rbp
0x18003071b  push    rdi
0x18003071c  push    r13
0x18003071e  push    r14
0x180030720  push    r15
0x180030722  lea     rbp, [rsp-37h]
0x180030727  sub     rsp, 90h
0x18003072e  mov     rax, cs:__security_cookie
0x180030735  xor     rax, rsp
0x180030738  mov     [rbp+57h+var_28], rax
0x18003073c  xorps   xmm1, xmm1
0x18003073f  mov     dword ptr [rbp+57h+size], 0
0x180030746  xorps   xmm0, xmm0
0x180030749  mov     dword ptr [rbp+57h+size+4], 0
0x180030750  xor     r14d, r14d
0x180030753  mov     rsi, r8
0x180030756  mov     r15, rcx
0x180030759  movups  [rbp+57h+var_78], xmm0
0x18003075d  movups  [rbp+57h+var_68], xmm0
0x180030761  movups  [rbp+57h+var_58], xmm1
0x180030765  movups  [rbp+57h+var_48], xmm1
0x180030769  movups  [rbp+57h+var_38], xmm1
0x18003076d  cmp     edx, 8000h
0x180030773  jnz     loc_180030B03
0x180030779  xor     r9d, r9d
0x18003077c  mov     [rsp+0B0h+var_90], r14
0x180030781  xor     r8d, r8d
0x180030784  xor     edx, edx
0x180030786  xor     ecx, ecx
0x180030788  call    cs:__imp_DevObjCreateDeviceInfoList
0x18003078e  mov     rdi, rax
0x180030791  mov     r13d, 80070000h
0x180030797  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18003079b  jnz     short loc_180030817
0x18003079d  call    cs:__imp_GetLastError
0x1800307a3  mov     ebx, eax
0x1800307a5  test    eax, eax
0x1800307a7  jle     short loc_1800307AF
0x1800307a9  movzx   ebx, ax
0x1800307ac  or      ebx, r13d
0x1800307af  test    ebx, ebx
0x1800307b1  jns     short loc_180030817
0x1800307b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800307ba  lea     rax, WPP_GLOBAL_Control
0x1800307c1  cmp     rcx, rax
0x1800307c4  jz      loc_180030B03
0x1800307ca  test    byte ptr [rcx+1Ch], 8
0x1800307ce  jz      loc_180030B03
0x1800307d4  cmp     byte ptr [rcx+19h], 2
0x1800307d8  jb      loc_180030B03
0x1800307de  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800307e3  lea     rcx, aDevobjcreatede_1; "DevObjCreateDeviceInfoList failed"
0x1800307ea  mov     dword ptr [rsp+0B0h+var_88], ebx
0x1800307ee  mov     [rsp+0B0h+var_90], rcx
0x1800307f3  lea     r8, WPP_e96ad774d77a3b20501daafc53de2dbd_Traceguids
0x1800307fa  mov     rcx, cs:WPP_GLOBAL_Control
0x180030801  mov     edx, 21h ; '!'
0x180030806  mov     r9d, eax
0x180030809  mov     rcx, [rcx+10h]
0x18003080d  call    WPP_SF_DsD
0x180030812  jmp     loc_180030B03
0x180030817  lea     rdx, [rsi+1Ch]
0x18003081b  mov     dword ptr [rbp+57h+var_78], 20h ; ' '
0x180030822  lea     r9, [rbp+57h+var_78]
0x180030826  xor     r8d, r8d
0x180030829  mov     rcx, rdi
0x18003082c  call    cs:__imp_DevObjOpenDeviceInterface
0x180030832  test    eax, eax
0x180030834  jnz     short loc_1800308B0
0x180030836  call    cs:__imp_GetLastError
0x18003083c  mov     ebx, eax
0x18003083e  test    eax, eax
0x180030840  jle     short loc_180030848
0x180030842  movzx   ebx, ax
0x180030845  or      ebx, r13d
0x180030848  test    ebx, ebx
0x18003084a  jns     short loc_1800308B0
0x18003084c  mov     rcx, cs:WPP_GLOBAL_Control
0x180030853  lea     rax, WPP_GLOBAL_Control
0x18003085a  cmp     rcx, rax
0x18003085d  jz      loc_180030AF4
0x180030863  test    byte ptr [rcx+1Ch], 8
0x180030867  jz      loc_180030AF4
0x18003086d  cmp     byte ptr [rcx+19h], 2
0x180030871  jb      loc_180030AF4
0x180030877  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18003087c  mov     edx, 22h ; '"'
0x180030881  lea     rcx, aDevobjopendevi_1; "DevObjOpenDeviceInterface failed"
0x180030888  mov     dword ptr [rsp+0B0h+var_88], ebx
0x18003088c  lea     r8, WPP_e96ad774d77a3b20501daafc53de2dbd_Traceguids
0x180030893  mov     [rsp+0B0h+var_90], rcx
0x180030898  mov     r9d, eax
0x18003089b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800308a2  mov     rcx, [rcx+10h]
0x1800308a6  call    WPP_SF_DsD
0x1800308ab  jmp     loc_180030AF4
0x1800308b0  lea     r8, [rbp+57h+var_58]
0x1800308b4  mov     dword ptr [rbp+57h+var_58], 30h ; '0'
0x1800308bb  xor     edx, edx
0x1800308bd  mov     rcx, rdi
0x1800308c0  call    cs:__imp_DevObjEnumDeviceInfo
0x1800308c6  test    eax, eax
0x1800308c8  jnz     short loc_18003091A
0x1800308ca  call    cs:__imp_GetLastError
0x1800308d0  mov     ebx, eax
0x1800308d2  test    eax, eax
0x1800308d4  jle     short loc_1800308DC
0x1800308d6  movzx   ebx, ax
0x1800308d9  or      ebx, r13d
0x1800308dc  test    ebx, ebx
0x1800308de  jns     short loc_18003091A
0x1800308e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800308e7  lea     rax, WPP_GLOBAL_Control
0x1800308ee  cmp     rcx, rax
0x1800308f1  jz      loc_180030AF4
0x1800308f7  test    byte ptr [rcx+1Ch], 8
0x1800308fb  jz      loc_180030AF4
0x180030901  cmp     byte ptr [rcx+19h], 2
0x180030905  jb      loc_180030AF4
0x18003090b  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180030910  mov     edx, 23h ; '#'
0x180030915  jmp     loc_180030881
0x18003091a  lea     rax, [rbp+57h+size]
0x18003091e  mov     [rsp+0B0h+var_88], r14
0x180030923  xor     r9d, r9d
0x180030926  mov     [rsp+0B0h+var_90], rax
0x18003092b  xor     r8d, r8d
0x18003092e  lea     rdx, [rbp+57h+var_78]
0x180030932  mov     rcx, rdi
0x180030935  call    cs:__imp_DevObjGetDeviceInterfaceDetail
0x18003093b  test    eax, eax
0x18003093d  jnz     short loc_1800309A1
0x18003093f  call    cs:__imp_GetLastError
0x180030945  cmp     eax, 7Ah ; 'z'
0x180030948  jz      short loc_1800309A1
0x18003094a  call    cs:__imp_GetLastError
0x180030950  mov     ebx, eax
0x180030952  test    eax, eax
0x180030954  jle     short loc_18003095C
0x180030956  movzx   ebx, ax
0x180030959  or      ebx, r13d
0x18003095c  test    ebx, ebx
0x18003095e  jns     short loc_1800309A1
0x180030960  mov     rcx, cs:WPP_GLOBAL_Control
0x180030967  lea     rax, WPP_GLOBAL_Control
0x18003096e  cmp     rcx, rax
0x180030971  jz      loc_180030AF4
0x180030977  test    byte ptr [rcx+1Ch], 8
0x18003097b  jz      loc_180030AF4
0x180030981  cmp     byte ptr [rcx+19h], 2
0x180030985  jb      loc_180030AF4
0x18003098b  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180030990  mov     edx, 24h ; '$'
0x180030995  lea     rcx, aDevobjgetdevic_3; "DevObjGetDeviceInterfaceDetail failed"
0x18003099c  jmp     loc_180030888
0x1800309a1  xor     ecx, ecx; Block
0x1800309a3  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800309a8  mov     ecx, dword ptr [rbp+57h+size]; size
0x1800309ab  call    MIDL_user_allocate
0x1800309b0  mov     r14, rax
0x1800309b3  test    rax, rax
0x1800309b6  jnz     short loc_180030A17
0x1800309b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800309bf  lea     rax, WPP_GLOBAL_Control
0x1800309c6  cmp     rcx, rax
0x1800309c9  jz      loc_180030AF4
0x1800309cf  test    byte ptr [rcx+1Ch], 8
0x1800309d3  jz      loc_180030AF4
0x1800309d9  cmp     byte ptr [rcx+19h], 2
0x1800309dd  jb      loc_180030AF4
0x1800309e3  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800309e8  lea     rcx, aChar; "CHAR"
0x1800309ef  mov     r9d, eax
0x1800309f2  mov     [rsp+0B0h+var_90], rcx
0x1800309f7  lea     edx, [r14+25h]
0x1800309fb  mov     rcx, cs:WPP_GLOBAL_Control
0x180030a02  lea     r8, WPP_e96ad774d77a3b20501daafc53de2dbd_Traceguids
0x180030a09  mov     rcx, [rcx+10h]
0x180030a0d  call    WPP_SF_Ds
0x180030a12  jmp     loc_180030AF4
0x180030a17  mov     dword ptr [rax], 8
0x180030a1d  lea     rdx, [rbp+57h+var_78]
0x180030a21  mov     r9d, dword ptr [rbp+57h+size]
0x180030a25  lea     rax, [rbp+57h+size+4]
0x180030a29  mov     [rsp+0B0h+var_88], 0
0x180030a32  mov     r8, r14
0x180030a35  mov     rcx, rdi
0x180030a38  mov     [rsp+0B0h+var_90], rax
0x180030a3d  call    cs:__imp_DevObjGetDeviceInterfaceDetail
0x180030a43  test    eax, eax
0x180030a45  jnz     short loc_180030A8F
0x180030a47  call    cs:__imp_GetLastError
0x180030a4d  mov     ebx, eax
0x180030a4f  test    eax, eax
0x180030a51  jle     short loc_180030A59
0x180030a53  movzx   ebx, ax
0x180030a56  or      ebx, r13d
0x180030a59  test    ebx, ebx
0x180030a5b  jns     short loc_180030A8F
0x180030a5d  mov     rcx, cs:WPP_GLOBAL_Control
0x180030a64  lea     rax, WPP_GLOBAL_Control
0x180030a6b  cmp     rcx, rax
0x180030a6e  jz      loc_180030AF4
0x180030a74  test    byte ptr [rcx+1Ch], 8
0x180030a78  jz      short loc_180030AF4
0x180030a7a  cmp     byte ptr [rcx+19h], 2
0x180030a7e  jb      short loc_180030AF4
0x180030a80  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180030a85  mov     edx, 26h ; '&'
0x180030a8a  jmp     loc_180030995
0x180030a8f  mov     edx, dword ptr [rbp+57h+size]
0x180030a92  xor     eax, eax
0x180030a94  add     edx, 0FFFFFFFCh
0x180030a97  mov     rcx, r15; this
0x180030a9a  shr     edx, 1
0x180030a9c  dec     edx
0x180030a9e  mov     [r14+rdx*2+4], ax
0x180030aa4  lea     rdx, [r14+4]; lpFileName
0x180030aa8  call    ?AddDeviceToList@CUrbDrManager@@AEAAJPEBG@Z; CUrbDrManager::AddDeviceToList(ushort const *)
0x180030aad  test    eax, eax
0x180030aaf  jns     short loc_180030AF4
0x180030ab1  mov     rcx, cs:WPP_GLOBAL_Control
0x180030ab8  lea     rax, WPP_GLOBAL_Control
0x180030abf  cmp     rcx, rax
0x180030ac2  jz      short loc_180030AF4
0x180030ac4  test    byte ptr [rcx+1Ch], 1
0x180030ac8  jz      short loc_180030AF4
0x180030aca  cmp     byte ptr [rcx+19h], 2
0x180030ace  jb      short loc_180030AF4
0x180030ad0  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180030ad5  mov     rcx, cs:WPP_GLOBAL_Control
0x180030adc  lea     r8, WPP_e96ad774d77a3b20501daafc53de2dbd_Traceguids
0x180030ae3  mov     edx, 27h ; '''
0x180030ae8  mov     r9d, eax
0x180030aeb  mov     rcx, [rcx+10h]
0x180030aef  call    WPP_SF_D
0x180030af4  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x180030af8  jz      short loc_180030B03
0x180030afa  mov     rcx, rdi
0x180030afd  call    cs:__imp_DevObjDestroyDeviceInfoList
0x180030b03  mov     rcx, r14; Block
0x180030b06  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180030b0b  mov     rcx, [rbp+57h+var_28]
0x180030b0f  xor     rcx, rsp; StackCookie
0x180030b12  call    __security_check_cookie
0x180030b17  lea     r11, [rsp+0B0h+var_20]
0x180030b1f  mov     rbx, [r11+38h]
0x180030b23  mov     rsi, [r11+48h]
0x180030b27  mov     rsp, r11
0x180030b2a  pop     r15
0x180030b2c  pop     r14
0x180030b2e  pop     r13
0x180030b30  pop     rdi
0x180030b31  pop     rbp
0x180030b32  retn
```
