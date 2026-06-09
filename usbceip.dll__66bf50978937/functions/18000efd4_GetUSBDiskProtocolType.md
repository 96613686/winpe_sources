# GetUSBDiskProtocolType

- ea: `0x18000efd4`
- end: `0x18000f179`
- name: `GetUSBDiskProtocolType`
- size: `421`
- prototype: `__int64 __fastcall(int, _DWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000edec`

## callees

- `0x18000e640`
- `0x18000e928`
- `0x18000efd4`
- `0x18000f32c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f01a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f081`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f13f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f01a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f081`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f13f`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x18000f00b`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x18000f00b`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x18000f135`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x18000f135`
- `DEVOBJ!DevObjGetClassDevs` at `0x18000f070`
- `DEVOBJ!DevObjGetClassDevs` at `0x18000f070`

## pseudocode

```c
__int64 __fastcall GetUSBDiskProtocolType(int a1, _DWORD *a2)
{
  __int64 DeviceInfoList; // rax
  void *v5; // rbp
  DWORD LastError; // eax
  __int64 v7; // r8
  DWORD v8; // ebx
  _QWORD *v9; // rcx
  __int64 v10; // rdx
  DWORD MatchingDeviceInfoData; // eax
  __int64 v12; // r8
  _QWORD *v13; // rcx
  __int64 v14; // rdx
  __int128 v16; // [rsp+30h] [rbp-88h] BYREF
  __int128 v17; // [rsp+40h] [rbp-78h]
  __int128 v18; // [rsp+50h] [rbp-68h]
  _OWORD v19[5]; // [rsp+60h] [rbp-58h] BYREF

  v16 = 0;
  v17 = 0;
  v18 = 0;
  DeviceInfoList = DevObjCreateDeviceInfoList(0, 0, 0, 0, 0);
  v5 = (void *)DeviceInfoList;
  if ( DeviceInfoList == -1 )
  {
    LastError = GetLastError();
    v8 = LastError;
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v10 = 33;
LABEL_22:
      WPP_SF_D(v9[2], v10, v7, LastError);
      return v8;
    }
    return v8;
  }
  if ( (unsigned int)DevObjGetClassDevs(DeviceInfoList, &GUID_DEVINTERFACE_DISK, 0, 18, 0, 0) )
  {
    MatchingDeviceInfoData = FindMatchingDeviceInfoData(v5, a1, (struct _DO_DEVINFO_DATA *)&v16);
    v8 = MatchingDeviceInfoData;
    if ( MatchingDeviceInfoData )
    {
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v14 = 35;
        goto LABEL_17;
      }
    }
    else
    {
      v19[0] = v16;
      v19[1] = v17;
      v19[2] = v18;
      MatchingDeviceInfoData = DetermineUSBDiskType((__int64)v5, v19, a2);
      v8 = MatchingDeviceInfoData;
      if ( MatchingDeviceInfoData )
      {
        v13 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v14 = 36;
          goto LABEL_17;
        }
      }
    }
  }
  else
  {
    MatchingDeviceInfoData = GetLastError();
    v8 = MatchingDeviceInfoData;
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v14 = 34;
LABEL_17:
      WPP_SF_D(v13[2], v14, v12, MatchingDeviceInfoData);
    }
  }
  if ( !(unsigned int)DevObjDestroyDeviceInfoList(v5) )
  {
    LastError = GetLastError();
    v8 = LastError;
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v10 = 37;
      goto LABEL_22;
    }
  }
  return v8;
}

```

## disassembly

```asm
0x18000efd4  push    rbx
0x18000efd6  push    rbp
0x18000efd7  push    rsi
0x18000efd8  push    r14
0x18000efda  sub     rsp, 98h
0x18000efe1  xorps   xmm0, xmm0
0x18000efe4  mov     [rsp+0B8h+var_98], 0
0x18000efed  mov     r14, rdx
0x18000eff0  mov     ebx, ecx
0x18000eff2  xor     edx, edx
0x18000eff4  xor     ecx, ecx
0x18000eff6  xor     r9d, r9d
0x18000eff9  xor     r8d, r8d
0x18000effc  movups  [rsp+0B8h+var_88], xmm0
0x18000f001  movups  [rsp+0B8h+var_78], xmm0
0x18000f006  movups  [rsp+0B8h+var_68], xmm0
0x18000f00b  call    cs:__imp_DevObjCreateDeviceInfoList
0x18000f011  mov     rbp, rax
0x18000f014  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000f018  jnz     short loc_18000F04B
0x18000f01a  call    cs:__imp_GetLastError
0x18000f020  mov     ebx, eax
0x18000f022  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f029  lea     rsi, WPP_GLOBAL_Control
0x18000f030  cmp     rcx, rsi
0x18000f033  jz      loc_18000F16A
0x18000f039  test    byte ptr [rcx+1Ch], 1
0x18000f03d  jz      loc_18000F16A
0x18000f043  lea     edx, [rbp+22h]
0x18000f046  jmp     loc_18000F15E
0x18000f04b  mov     [rsp+0B8h+var_90], 0
0x18000f054  lea     rdx, GUID_DEVINTERFACE_DISK
0x18000f05b  mov     r9d, 12h
0x18000f061  mov     [rsp+0B8h+var_98], 0
0x18000f06a  xor     r8d, r8d
0x18000f06d  mov     rcx, rbp
0x18000f070  call    cs:__imp_DevObjGetClassDevs
0x18000f076  lea     rsi, WPP_GLOBAL_Control
0x18000f07d  test    eax, eax
0x18000f07f  jnz     short loc_18000F0AA
0x18000f081  call    cs:__imp_GetLastError
0x18000f087  mov     ebx, eax
0x18000f089  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f090  cmp     rcx, rsi
0x18000f093  jz      loc_18000F132
0x18000f099  test    byte ptr [rcx+1Ch], 1
0x18000f09d  jz      loc_18000F132
0x18000f0a3  mov     edx, 22h ; '"'
0x18000f0a8  jmp     short loc_18000F126
0x18000f0aa  lea     r8, [rsp+0B8h+var_88]; struct _DO_DEVINFO_DATA *
0x18000f0af  mov     edx, ebx; unsigned int
0x18000f0b1  mov     rcx, rbp; void *
0x18000f0b4  call    ?FindMatchingDeviceInfoData@@YAKPEAXKPEAU_DO_DEVINFO_DATA@@@Z; FindMatchingDeviceInfoData(void *,ulong,_DO_DEVINFO_DATA *)
0x18000f0b9  mov     ebx, eax
0x18000f0bb  test    eax, eax
0x18000f0bd  jz      short loc_18000F0D8
0x18000f0bf  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f0c6  cmp     rcx, rsi
0x18000f0c9  jz      short loc_18000F132
0x18000f0cb  test    byte ptr [rcx+1Ch], 1
0x18000f0cf  jz      short loc_18000F132
0x18000f0d1  mov     edx, 23h ; '#'
0x18000f0d6  jmp     short loc_18000F126
0x18000f0d8  movups  xmm0, [rsp+0B8h+var_88]
0x18000f0dd  mov     r8, r14
0x18000f0e0  lea     rdx, [rsp+0B8h+var_58]
0x18000f0e5  movups  xmm1, [rsp+0B8h+var_78]
0x18000f0ea  mov     rcx, rbp
0x18000f0ed  movaps  [rsp+0B8h+var_58], xmm0
0x18000f0f2  movups  xmm0, [rsp+0B8h+var_68]
0x18000f0f7  movaps  [rsp+0B8h+var_48], xmm1
0x18000f0fc  movaps  [rsp+0B8h+var_38], xmm0
0x18000f104  call    ?DetermineUSBDiskType@@YAKPEAXU_DO_DEVINFO_DATA@@PEAW4_USB_BOOT_INFORMATION_DISK_TYPE@@@Z; DetermineUSBDiskType(void *,_DO_DEVINFO_DATA,_USB_BOOT_INFORMATION_DISK_TYPE *)
0x18000f109  mov     ebx, eax
0x18000f10b  test    eax, eax
0x18000f10d  jz      short loc_18000F132
0x18000f10f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f116  cmp     rcx, rsi
0x18000f119  jz      short loc_18000F132
0x18000f11b  test    byte ptr [rcx+1Ch], 1
0x18000f11f  jz      short loc_18000F132
0x18000f121  mov     edx, 24h ; '$'
0x18000f126  mov     rcx, [rcx+10h]
0x18000f12a  mov     r9d, eax
0x18000f12d  call    WPP_SF_D
0x18000f132  mov     rcx, rbp
0x18000f135  call    cs:__imp_DevObjDestroyDeviceInfoList
0x18000f13b  test    eax, eax
0x18000f13d  jnz     short loc_18000F16A
0x18000f13f  call    cs:__imp_GetLastError
0x18000f145  mov     ebx, eax
0x18000f147  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f14e  cmp     rcx, rsi
0x18000f151  jz      short loc_18000F16A
0x18000f153  test    byte ptr [rcx+1Ch], 1
0x18000f157  jz      short loc_18000F16A
0x18000f159  mov     edx, 25h ; '%'
0x18000f15e  mov     rcx, [rcx+10h]
0x18000f162  mov     r9d, eax
0x18000f165  call    WPP_SF_D
0x18000f16a  mov     eax, ebx
0x18000f16c  add     rsp, 98h
0x18000f173  pop     r14
0x18000f175  pop     rsi
0x18000f176  pop     rbp
0x18000f177  pop     rbx
0x18000f178  retn
```
