# CUrbDrManager::GetDeviceInfoAndDeviceInfoData(_DEV_BROADCAST_DEVICEINTERFACE_W *,void * *,_DO_DEVINFO_DATA *)

- ea: `0x18002f980`
- end: `0x18002fbb6`
- name: `?GetDeviceInfoAndDeviceInfoData@CUrbDrManager@@AEAAJPEAU_DEV_BROADCAST_DEVICEINTERFACE_W@@PEAPEAXPEAU_DO_DEVINFO_DATA@@@Z`
- size: `566`
- prototype: `__int64 __fastcall(CUrbDrManager *__hidden this, struct _DEV_BROADCAST_DEVICEINTERFACE_W *, void **, struct _DO_DEVINFO_DATA *)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180002390`
- `0x180030488`

## callees

- `0x18000b8f8`
- `0x18000b98c`
- `0x18002f980`
- `0x180047ef0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f9f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fa8e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002faf8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f9f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fa8e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002faf8`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x18002f9e3`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x18002f9e3`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x18002fb6d`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x18002fb6d`
- `DEVOBJ!DevObjEnumDeviceInfo` at `0x18002faee`
- `DEVOBJ!DevObjEnumDeviceInfo` at `0x18002faee`
- `DEVOBJ!DevObjOpenDeviceInterface` at `0x18002fa84`
- `DEVOBJ!DevObjOpenDeviceInterface` at `0x18002fa84`

## string_xrefs

- `0x18002fb3a`: `DevObjOpenDeviceInterface failed`
- `0x18002fa3b`: `DevObjCreateDeviceInfoList failed`

## pseudocode

```c
__int64 __fastcall CUrbDrManager::GetDeviceInfoAndDeviceInfoData(
        CUrbDrManager *this,
        struct _DEV_BROADCAST_DEVICEINTERFACE_W *a2,
        void **a3,
        struct _DO_DEVINFO_DATA *a4)
{
  void *DeviceInfoList; // rdi
  signed int LastError; // eax
  signed int v9; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  signed int v11; // eax
  unsigned int v12; // eax
  int v13; // edx
  signed int v14; // eax
  __int128 v15; // xmm0
  __int128 v16; // xmm1
  __int128 v17; // xmm0
  __int128 v19; // [rsp+30h] [rbp-29h] BYREF
  __int128 v20; // [rsp+40h] [rbp-19h]
  __int128 v21; // [rsp+50h] [rbp-9h]
  _OWORD v22[2]; // [rsp+60h] [rbp+7h] BYREF

  *a3 = (void *)-1LL;
  memset(v22, 0, sizeof(v22));
  v19 = 0;
  v20 = 0;
  v21 = 0;
  DeviceInfoList = (void *)DevObjCreateDeviceInfoList(0, 0, 0, 0, 0);
  if ( DeviceInfoList == (void *)-1LL )
  {
    LastError = GetLastError();
    v9 = LastError;
    if ( LastError > 0 )
      v9 = (unsigned __int16)LastError | 0x80070000;
    if ( v9 < 0 )
    {
      if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) != 0
        && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DsD(
          *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
          44,
          (unsigned int)WPP_e96ad774d77a3b20501daafc53de2dbd_Traceguids,
          CurrentThreadActivityIdPrefix,
          (__int64)"DevObjCreateDeviceInfoList failed",
          v9);
      }
      return (unsigned int)v9;
    }
  }
  LODWORD(v22[0]) = 32;
  if ( (unsigned int)DevObjOpenDeviceInterface(DeviceInfoList, a2->dbcc_name, 0, v22) )
    goto LABEL_17;
  v11 = GetLastError();
  v9 = v11;
  if ( v11 > 0 )
    v9 = (unsigned __int16)v11 | 0x80070000;
  if ( v9 >= 0 )
  {
LABEL_17:
    LODWORD(v19) = 48;
    if ( (unsigned int)DevObjEnumDeviceInfo(DeviceInfoList, 0, &v19) )
      goto LABEL_28;
    v14 = GetLastError();
    v9 = v14;
    if ( v14 > 0 )
      v9 = (unsigned __int16)v14 | 0x80070000;
    if ( v9 >= 0 )
    {
LABEL_28:
      v15 = v19;
      *a3 = DeviceInfoList;
      v9 = 0;
      v16 = v20;
      *(_OWORD *)a4 = v15;
      v17 = v21;
      *((_OWORD *)a4 + 1) = v16;
      *((_OWORD *)a4 + 2) = v17;
      return (unsigned int)v9;
    }
    if ( *(unsigned int **)&WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) == 0
      || *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) < 2u )
    {
      goto LABEL_26;
    }
    v12 = RdpWppGetCurrentThreadActivityIdPrefix();
    v13 = 46;
    goto LABEL_25;
  }
  if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) != 0
    && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
  {
    v12 = RdpWppGetCurrentThreadActivityIdPrefix();
    v13 = 45;
LABEL_25:
    WPP_SF_DsD(
      *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
      v13,
      (unsigned int)WPP_e96ad774d77a3b20501daafc53de2dbd_Traceguids,
      v12,
      (__int64)"DevObjOpenDeviceInterface failed",
      v9);
  }
LABEL_26:
  if ( DeviceInfoList != (void *)-1LL )
    DevObjDestroyDeviceInfoList(DeviceInfoList);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18002f980  mov     [rsp-8+arg_0], rbx
0x18002f985  push    rbp
0x18002f986  push    rsi
0x18002f987  push    rdi
0x18002f988  push    r14
0x18002f98a  push    r15
0x18002f98c  lea     rbp, [rsp-37h]
0x18002f991  sub     rsp, 90h
0x18002f998  mov     rax, cs:__security_cookie
0x18002f99f  xor     rax, rsp
0x18002f9a2  mov     [rbp+57h+var_30], rax
0x18002f9a6  xorps   xmm1, xmm1
0x18002f9a9  mov     qword ptr [r8], 0FFFFFFFFFFFFFFFFh
0x18002f9b0  xorps   xmm0, xmm0
0x18002f9b3  mov     [rsp+0B0h+var_90], 0
0x18002f9bc  mov     rsi, r9
0x18002f9bf  mov     r15, r8
0x18002f9c2  mov     r14, rdx
0x18002f9c5  xor     r9d, r9d
0x18002f9c8  xor     r8d, r8d
0x18002f9cb  xor     edx, edx
0x18002f9cd  xor     ecx, ecx
0x18002f9cf  movups  [rbp+57h+var_50], xmm0
0x18002f9d3  movups  [rbp+57h+var_40], xmm0
0x18002f9d7  movups  [rbp+57h+var_80], xmm1
0x18002f9db  movups  [rbp+57h+var_70], xmm1
0x18002f9df  movups  [rbp+57h+var_60], xmm1
0x18002f9e3  call    cs:__imp_DevObjCreateDeviceInfoList
0x18002f9e9  mov     rdi, rax
0x18002f9ec  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002f9f0  jnz     short loc_18002FA6F
0x18002f9f2  call    cs:__imp_GetLastError
0x18002f9f8  mov     ebx, eax
0x18002f9fa  test    eax, eax
0x18002f9fc  jle     short loc_18002FA07
0x18002f9fe  movzx   ebx, ax
0x18002fa01  or      ebx, 80070000h
0x18002fa07  test    ebx, ebx
0x18002fa09  jns     short loc_18002FA6F
0x18002fa0b  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fa12  lea     rax, WPP_GLOBAL_Control
0x18002fa19  cmp     rcx, rax
0x18002fa1c  jz      loc_18002FB91
0x18002fa22  test    byte ptr [rcx+1Ch], 8
0x18002fa26  jz      loc_18002FB91
0x18002fa2c  cmp     byte ptr [rcx+19h], 2
0x18002fa30  jb      loc_18002FB91
0x18002fa36  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18002fa3b  lea     rcx, aDevobjcreatede_1; "DevObjCreateDeviceInfoList failed"
0x18002fa42  mov     [rsp+0B0h+var_88], ebx
0x18002fa46  mov     [rsp+0B0h+var_90], rcx
0x18002fa4b  lea     r8, WPP_e96ad774d77a3b20501daafc53de2dbd_Traceguids
0x18002fa52  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fa59  mov     edx, 2Ch ; ','
0x18002fa5e  mov     r9d, eax
0x18002fa61  mov     rcx, [rcx+10h]
0x18002fa65  call    WPP_SF_DsD
0x18002fa6a  jmp     loc_18002FB91
0x18002fa6f  lea     rdx, [r14+1Ch]
0x18002fa73  mov     dword ptr [rbp+57h+var_50], 20h ; ' '
0x18002fa7a  lea     r9, [rbp+57h+var_50]
0x18002fa7e  xor     r8d, r8d
0x18002fa81  mov     rcx, rdi
0x18002fa84  call    cs:__imp_DevObjOpenDeviceInterface
0x18002fa8a  test    eax, eax
0x18002fa8c  jnz     short loc_18002FADE
0x18002fa8e  call    cs:__imp_GetLastError
0x18002fa94  mov     ebx, eax
0x18002fa96  test    eax, eax
0x18002fa98  jle     short loc_18002FAA3
0x18002fa9a  movzx   ebx, ax
0x18002fa9d  or      ebx, 80070000h
0x18002faa3  test    ebx, ebx
0x18002faa5  jns     short loc_18002FADE
0x18002faa7  mov     rcx, cs:WPP_GLOBAL_Control
0x18002faae  lea     rax, WPP_GLOBAL_Control
0x18002fab5  cmp     rcx, rax
0x18002fab8  jz      loc_18002FB64
0x18002fabe  test    byte ptr [rcx+1Ch], 8
0x18002fac2  jz      loc_18002FB64
0x18002fac8  cmp     byte ptr [rcx+19h], 2
0x18002facc  jb      loc_18002FB64
0x18002fad2  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18002fad7  mov     edx, 2Dh ; '-'
0x18002fadc  jmp     short loc_18002FB3A
0x18002fade  lea     r8, [rbp+57h+var_80]
0x18002fae2  mov     dword ptr [rbp+57h+var_80], 30h ; '0'
0x18002fae9  xor     edx, edx
0x18002faeb  mov     rcx, rdi
0x18002faee  call    cs:__imp_DevObjEnumDeviceInfo
0x18002faf4  test    eax, eax
0x18002faf6  jnz     short loc_18002FB75
0x18002faf8  call    cs:__imp_GetLastError
0x18002fafe  mov     ebx, eax
0x18002fb00  test    eax, eax
0x18002fb02  jle     short loc_18002FB0D
0x18002fb04  movzx   ebx, ax
0x18002fb07  or      ebx, 80070000h
0x18002fb0d  test    ebx, ebx
0x18002fb0f  jns     short loc_18002FB75
0x18002fb11  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fb18  lea     rax, WPP_GLOBAL_Control
0x18002fb1f  cmp     rcx, rax
0x18002fb22  jz      short loc_18002FB64
0x18002fb24  test    byte ptr [rcx+1Ch], 8
0x18002fb28  jz      short loc_18002FB64
0x18002fb2a  cmp     byte ptr [rcx+19h], 2
0x18002fb2e  jb      short loc_18002FB64
0x18002fb30  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18002fb35  mov     edx, 2Eh ; '.'
0x18002fb3a  lea     rcx, aDevobjopendevi_1; "DevObjOpenDeviceInterface failed"
0x18002fb41  mov     [rsp+0B0h+var_88], ebx
0x18002fb45  mov     [rsp+0B0h+var_90], rcx
0x18002fb4a  lea     r8, WPP_e96ad774d77a3b20501daafc53de2dbd_Traceguids
0x18002fb51  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fb58  mov     r9d, eax
0x18002fb5b  mov     rcx, [rcx+10h]
0x18002fb5f  call    WPP_SF_DsD
0x18002fb64  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18002fb68  jz      short loc_18002FB91
0x18002fb6a  mov     rcx, rdi
0x18002fb6d  call    cs:__imp_DevObjDestroyDeviceInfoList
0x18002fb73  jmp     short loc_18002FB91
0x18002fb75  movups  xmm0, [rbp+57h+var_80]
0x18002fb79  mov     [r15], rdi
0x18002fb7c  xor     ebx, ebx
0x18002fb7e  movups  xmm1, [rbp+57h+var_70]
0x18002fb82  movups  xmmword ptr [rsi], xmm0
0x18002fb85  movups  xmm0, [rbp+57h+var_60]
0x18002fb89  movups  xmmword ptr [rsi+10h], xmm1
0x18002fb8d  movups  xmmword ptr [rsi+20h], xmm0
0x18002fb91  mov     eax, ebx
0x18002fb93  mov     rcx, [rbp+57h+var_30]
0x18002fb97  xor     rcx, rsp; StackCookie
0x18002fb9a  call    __security_check_cookie
0x18002fb9f  mov     rbx, [rsp+0B0h+arg_0]
0x18002fba7  add     rsp, 90h
0x18002fbae  pop     r15
0x18002fbb0  pop     r14
0x18002fbb2  pop     rdi
0x18002fbb3  pop     rsi
0x18002fbb4  pop     rbp
0x18002fbb5  retn
```
