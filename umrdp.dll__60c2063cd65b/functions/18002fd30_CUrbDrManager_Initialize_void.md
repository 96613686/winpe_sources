# CUrbDrManager::Initialize(void)

- ea: `0x18002fd30`
- end: `0x1800303bb`
- name: `?Initialize@CUrbDrManager@@EEAAJXZ`
- size: `1675`
- prototype: `__int64 __fastcall(CUrbDrManager *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops`

## callers

- `0x18002f27c`

## callees

- `0x18000adf8`
- `0x18000b8f8`
- `0x18000f75c`
- `0x18000f79c`
- `0x180019d80`
- `0x180019d90`
- `0x18002db68`
- `0x18002ed64`
- `0x18002f088`
- `0x18002fd30`
- `0x180031198`
- `0x180047ef0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fe0c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fe77`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fedf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ff4c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ffdf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800300af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030131`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003013c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800301ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030235`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800302ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fe0c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fe77`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fedf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ff4c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ffdf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800300af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030131`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003013c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800301ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030235`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800302ca`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002fdf5`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002fe65`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002fed0`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002fdf5`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002fe65`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002fed0`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x18002ff3d`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x18002ff3d`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x18003038b`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x18003038b`
- `DEVOBJ!DevObjGetClassDevs` at `0x18002ffd5`
- `DEVOBJ!DevObjGetClassDevs` at `0x18002ffd5`
- `DEVOBJ!DevObjEnumDeviceInfo` at `0x180030076`
- `DEVOBJ!DevObjEnumDeviceInfo` at `0x180030076`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x1800300a5`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x1800300a5`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x180030127`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x18003022b`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x180030127`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x18003022b`

## pseudocode

```c
__int64 __fastcall CUrbDrManager::Initialize(CUrbDrManager *this)
{
  WCHAR *v2; // r13
  signed int HubDeviceEnumerator; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  __int64 v5; // rdx
  HANDLE EventW; // rax
  signed int LastError; // eax
  HANDLE v8; // rax
  signed int v9; // eax
  HANDLE v10; // rax
  signed int v11; // eax
  __int64 DeviceInfoList; // rax
  __int64 v13; // r15
  signed int v14; // esi
  unsigned int v15; // eax
  signed int v16; // eax
  unsigned int v17; // eax
  CUrbDrManager *v18; // r14
  unsigned int i; // r12d
  int v20; // ebx
  unsigned int v21; // eax
  __int64 v22; // rdx
  WCHAR *v23; // rax
  unsigned int v24; // eax
  DWORD v25; // eax
  CUrbDrManager *v26; // r14
  DWORD v27; // ebx
  unsigned int v28; // eax
  unsigned int v29; // eax
  size_t size; // [rsp+30h] [rbp-59h] BYREF
  CUrbDrManager *v32; // [rsp+38h] [rbp-51h]
  CUrbDrManager *v33; // [rsp+40h] [rbp-49h]
  _OWORD v34[2]; // [rsp+48h] [rbp-41h] BYREF
  _OWORD v35[3]; // [rsp+68h] [rbp-21h] BYREF

  v33 = this;
  memset(v34, 0, sizeof(v34));
  size = 0;
  v2 = 0;
  McGenEventRegister_EventRegister();
  if ( !(unsigned int)CTSCriticalSection::Initialize((CUrbDrManager *)((char *)this + 56)) )
  {
    HubDeviceEnumerator = -2147467259;
    if ( *(unsigned int **)&WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 1) == 0
      || *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) < 2u )
    {
      goto LABEL_94;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v5 = 12;
    goto LABEL_6;
  }
  EventW = CreateEventW(0, 1, 0, 0);
  v32 = (CUrbDrManager *)((char *)this - 8);
  *((_QWORD *)this + 12) = EventW;
  if ( !EventW )
  {
    LastError = GetLastError();
    HubDeviceEnumerator = LastError;
    if ( LastError > 0 )
      HubDeviceEnumerator = (unsigned __int16)LastError | 0x80070000;
    if ( *(unsigned int **)&WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 1) == 0
      || *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) < 2u )
    {
      goto LABEL_94;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v5 = 13;
    goto LABEL_6;
  }
  v8 = CreateEventW(0, 1, 0, 0);
  *((_QWORD *)this + 20) = v8;
  if ( !v8 )
  {
    v9 = GetLastError();
    HubDeviceEnumerator = v9;
    if ( v9 > 0 )
      HubDeviceEnumerator = (unsigned __int16)v9 | 0x80070000;
    if ( *(unsigned int **)&WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 1) == 0
      || *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) < 2u )
    {
      goto LABEL_94;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v5 = 14;
    goto LABEL_6;
  }
  v10 = CreateEventW(0, 1, 0, 0);
  *((_QWORD *)this + 13) = v10;
  if ( !v10 )
  {
    v11 = GetLastError();
    HubDeviceEnumerator = v11;
    if ( v11 > 0 )
      HubDeviceEnumerator = (unsigned __int16)v11 | 0x80070000;
    if ( *(unsigned int **)&WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 1) == 0
      || *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) < 2u )
    {
      goto LABEL_94;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v5 = 15;
LABEL_6:
    WPP_SF_D(
      *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
      v5,
      WPP_e96ad774d77a3b20501daafc53de2dbd_Traceguids,
      CurrentThreadActivityIdPrefix);
    goto LABEL_94;
  }
  DeviceInfoList = DevObjCreateDeviceInfoList(0, 0, 0, 0, 0);
  v13 = DeviceInfoList;
  if ( DeviceInfoList == -1 )
  {
    v14 = GetLastError();
    if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) != 0
      && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
    {
      v15 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(
        *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
        16,
        WPP_e96ad774d77a3b20501daafc53de2dbd_Traceguids,
        v15,
        v14);
    }
    if ( v14 > 0 )
      v14 = (unsigned __int16)v14 | 0x80070000;
    if ( v14 >= 0 )
      v14 = -2147467259;
    HubDeviceEnumerator = v14;
    goto LABEL_94;
  }
  if ( !(unsigned int)DevObjGetClassDevs(DeviceInfoList, &GUID_DEVINTERFACE_TSUSBHUB, 0, 16, 0, 0) )
  {
    v16 = GetLastError();
    HubDeviceEnumerator = v16;
    if ( v16 > 0 )
      HubDeviceEnumerator = (unsigned __int16)v16 | 0x80070000;
    if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 1) != 0
      && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
    {
      v17 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_D(
        *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
        17,
        WPP_e96ad774d77a3b20501daafc53de2dbd_Traceguids,
        v17);
    }
    goto LABEL_93;
  }
  v18 = v32;
  for ( i = 0; ; ++i )
  {
    memset(v35, 0, sizeof(v35));
    LODWORD(v35[0]) = 48;
    if ( !(unsigned int)DevObjEnumDeviceInfo(v13, i, v35) )
      break;
    LODWORD(v34[0]) = 32;
    if ( (unsigned int)DevObjEnumDeviceInterfaces(v13, v35, &GUID_DEVINTERFACE_TSUSBHUB, 0, v34) )
    {
      if ( (unsigned int)DevObjGetDeviceInterfaceDetail(v13, v34, 0, 0, &size, 0) || GetLastError() == 122 )
      {
        v20 = size;
        if ( (unsigned int)size > 4 )
        {
          operator delete(v2);
          v23 = (WCHAR *)MIDL_user_allocate((unsigned int)size);
          v2 = v23;
          if ( v23 )
          {
            *(_DWORD *)v23 = 8;
            if ( (unsigned int)DevObjGetDeviceInterfaceDetail(v13, v34, v23, (unsigned int)size, (char *)&size + 4, 0) )
            {
              v2[((unsigned int)(size - 4) >> 1) + 1] = 0;
              if ( (int)CUrbDrManager::AddDeviceToList(v18, v2 + 2) < 0
                && *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 1) != 0
                && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
              {
                v24 = RdpWppGetCurrentThreadActivityIdPrefix();
                WPP_SF_D(
                  *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
                  24,
                  WPP_e96ad774d77a3b20501daafc53de2dbd_Traceguids,
                  v24);
              }
            }
            else
            {
              v20 = GetLastError();
              if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 1) != 0
                && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
              {
                v21 = RdpWppGetCurrentThreadActivityIdPrefix();
                v22 = 23;
                goto LABEL_52;
              }
            }
          }
          else
          {
            GetLastError();
            if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 1) != 0
              && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
            {
              v20 = size;
              v21 = RdpWppGetCurrentThreadActivityIdPrefix();
              v22 = 22;
              goto LABEL_52;
            }
          }
        }
        else if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
               && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 1) != 0
               && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
        {
          v21 = RdpWppGetCurrentThreadActivityIdPrefix();
          v22 = 21;
          goto LABEL_52;
        }
      }
      else
      {
        v20 = GetLastError();
        if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 1) != 0
          && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
        {
          v21 = RdpWppGetCurrentThreadActivityIdPrefix();
          v22 = 20;
          goto LABEL_52;
        }
      }
    }
    else
    {
      v20 = GetLastError();
      if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 1) != 0
        && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
      {
        v21 = RdpWppGetCurrentThreadActivityIdPrefix();
        v22 = 19;
LABEL_52:
        WPP_SF_Dd(
          *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
          v22,
          WPP_e96ad774d77a3b20501daafc53de2dbd_Traceguids,
          v21,
          v20);
        continue;
      }
    }
  }
  v25 = GetLastError();
  v26 = v33;
  v27 = v25;
  if ( (v25 != 259 || !i)
    && *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 1) != 0
    && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
  {
    v28 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_Dd(
      *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
      18,
      WPP_e96ad774d77a3b20501daafc53de2dbd_Traceguids,
      v28,
      v27);
  }
  if ( *((_DWORD *)v26 + 11)
    || (HubDeviceEnumerator = CUrbDrManager::AllocateHubDeviceEnumerator((CUrbDrManager *)((char *)v26 - 8)),
        HubDeviceEnumerator >= 0) )
  {
    *((_DWORD *)v26 + 39) = IsRemoveTSUSBPhantomDevnodesEnabled();
    HubDeviceEnumerator = 0;
  }
  else if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 1) != 0
         && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
  {
    v29 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_Dd(
      *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
      25,
      WPP_e96ad774d77a3b20501daafc53de2dbd_Traceguids,
      v29,
      HubDeviceEnumerator);
  }
LABEL_93:
  DevObjDestroyDeviceInfoList(v13);
LABEL_94:
  operator delete(v2);
  return (unsigned int)HubDeviceEnumerator;
}

```

## disassembly

```asm
0x18002fd30  push    rbp
0x18002fd32  push    rbx
0x18002fd33  push    rsi
0x18002fd34  push    rdi
0x18002fd35  push    r12
0x18002fd37  push    r13
0x18002fd39  push    r14
0x18002fd3b  push    r15
0x18002fd3d  lea     rbp, [rsp-1Fh]
0x18002fd42  sub     rsp, 0A8h
0x18002fd49  mov     rax, cs:__security_cookie
0x18002fd50  xor     rax, rsp
0x18002fd53  mov     [rbp+57h+var_48], rax
0x18002fd57  xorps   xmm0, xmm0
0x18002fd5a  mov     [rbp+57h+var_A0], rcx
0x18002fd5e  movups  [rbp+57h+var_98], xmm0
0x18002fd62  mov     r14, rcx
0x18002fd65  mov     dword ptr [rbp+57h+size], 0
0x18002fd6c  movups  [rbp+57h+var_88], xmm0
0x18002fd70  mov     dword ptr [rbp+57h+size+4], 0
0x18002fd77  xor     r13d, r13d
0x18002fd7a  call    McGenEventRegister_EventRegister
0x18002fd7f  lea     rcx, [r14+38h]; this
0x18002fd83  call    ?Initialize@CTSCriticalSection@@QEAAHXZ; CTSCriticalSection::Initialize(void)
0x18002fd88  test    eax, eax
0x18002fd8a  jnz     short loc_18002FDE7
0x18002fd8c  mov     ebx, 80004005h
0x18002fd91  mov     rax, cs:WPP_GLOBAL_Control
0x18002fd98  lea     rdi, WPP_GLOBAL_Control
0x18002fd9f  cmp     rax, rdi
0x18002fda2  jz      loc_180030391
0x18002fda8  lea     esi, [r13+1]
0x18002fdac  test    [rax+1Ch], sil
0x18002fdb0  jz      loc_180030391
0x18002fdb6  cmp     byte ptr [rax+19h], 2
0x18002fdba  jb      loc_180030391
0x18002fdc0  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18002fdc5  lea     edx, [rsi+0Bh]
0x18002fdc8  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fdcf  lea     r8, WPP_e96ad774d77a3b20501daafc53de2dbd_Traceguids
0x18002fdd6  mov     r9d, eax
0x18002fdd9  mov     rcx, [rcx+10h]
0x18002fddd  call    WPP_SF_D
0x18002fde2  jmp     loc_180030391
0x18002fde7  xor     r9d, r9d; lpName
0x18002fdea  xor     r8d, r8d; bInitialState
0x18002fded  xor     ecx, ecx; lpEventAttributes
0x18002fdef  lea     esi, [r9+1]
0x18002fdf3  mov     edx, esi; bManualReset
0x18002fdf5  call    cs:__imp_CreateEventW
0x18002fdfb  lea     rcx, [r14-8]
0x18002fdff  mov     [rbp+57h+var_A8], rcx
0x18002fe03  mov     [rcx+68h], rax
0x18002fe07  test    rax, rax
0x18002fe0a  jnz     short loc_18002FE5B
0x18002fe0c  call    cs:__imp_GetLastError
0x18002fe12  mov     ebx, eax
0x18002fe14  test    eax, eax
0x18002fe16  jle     short loc_18002FE21
0x18002fe18  movzx   ebx, ax
0x18002fe1b  or      ebx, 80070000h
0x18002fe21  mov     rax, cs:WPP_GLOBAL_Control
0x18002fe28  lea     rdi, WPP_GLOBAL_Control
0x18002fe2f  cmp     rax, rdi
0x18002fe32  jz      loc_180030391
0x18002fe38  test    [rax+1Ch], sil
0x18002fe3c  jz      loc_180030391
0x18002fe42  cmp     byte ptr [rax+19h], 2
0x18002fe46  jb      loc_180030391
0x18002fe4c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18002fe51  mov     edx, 0Dh
0x18002fe56  jmp     loc_18002FDC8
0x18002fe5b  xor     r9d, r9d; lpName
0x18002fe5e  xor     r8d, r8d; bInitialState
0x18002fe61  mov     edx, esi; bManualReset
0x18002fe63  xor     ecx, ecx; lpEventAttributes
0x18002fe65  call    cs:__imp_CreateEventW
0x18002fe6b  mov     [r14+0A0h], rax
0x18002fe72  test    rax, rax
0x18002fe75  jnz     short loc_18002FEC6
0x18002fe77  call    cs:__imp_GetLastError
0x18002fe7d  mov     ebx, eax
0x18002fe7f  test    eax, eax
0x18002fe81  jle     short loc_18002FE8C
0x18002fe83  movzx   ebx, ax
0x18002fe86  or      ebx, 80070000h
0x18002fe8c  mov     rax, cs:WPP_GLOBAL_Control
0x18002fe93  lea     rdi, WPP_GLOBAL_Control
0x18002fe9a  cmp     rax, rdi
0x18002fe9d  jz      loc_180030391
0x18002fea3  test    [rax+1Ch], sil
0x18002fea7  jz      loc_180030391
0x18002fead  cmp     byte ptr [rax+19h], 2
0x18002feb1  jb      loc_180030391
0x18002feb7  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18002febc  mov     edx, 0Eh
0x18002fec1  jmp     loc_18002FDC8
0x18002fec6  xor     r9d, r9d; lpName
0x18002fec9  xor     r8d, r8d; bInitialState
0x18002fecc  mov     edx, esi; bManualReset
0x18002fece  xor     ecx, ecx; lpEventAttributes
0x18002fed0  call    cs:__imp_CreateEventW
0x18002fed6  mov     [r14+68h], rax
0x18002feda  test    rax, rax
0x18002fedd  jnz     short loc_18002FF2E
0x18002fedf  call    cs:__imp_GetLastError
0x18002fee5  mov     ebx, eax
0x18002fee7  test    eax, eax
0x18002fee9  jle     short loc_18002FEF4
0x18002feeb  movzx   ebx, ax
0x18002feee  or      ebx, 80070000h
0x18002fef4  mov     rax, cs:WPP_GLOBAL_Control
0x18002fefb  lea     rdi, WPP_GLOBAL_Control
0x18002ff02  cmp     rax, rdi
0x18002ff05  jz      loc_180030391
0x18002ff0b  test    [rax+1Ch], sil
0x18002ff0f  jz      loc_180030391
0x18002ff15  cmp     byte ptr [rax+19h], 2
0x18002ff19  jb      loc_180030391
0x18002ff1f  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18002ff24  mov     edx, 0Fh
0x18002ff29  jmp     loc_18002FDC8
0x18002ff2e  xor     r9d, r9d
0x18002ff31  mov     [rsp+0E0h+var_C0], r13
0x18002ff36  xor     r8d, r8d
0x18002ff39  xor     edx, edx
0x18002ff3b  xor     ecx, ecx
0x18002ff3d  call    cs:__imp_DevObjCreateDeviceInfoList
0x18002ff43  mov     r15, rax
0x18002ff46  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002ff4a  jnz     short loc_18002FFB8
0x18002ff4c  call    cs:__imp_GetLastError
0x18002ff52  mov     esi, eax
0x18002ff54  mov     rax, cs:WPP_GLOBAL_Control
0x18002ff5b  lea     rdi, WPP_GLOBAL_Control
0x18002ff62  cmp     rax, rdi
0x18002ff65  jz      short loc_18002FF9A
0x18002ff67  test    byte ptr [rax+1Ch], 8
0x18002ff6b  jz      short loc_18002FF9A
0x18002ff6d  cmp     byte ptr [rax+19h], 2
0x18002ff71  jb      short loc_18002FF9A
0x18002ff73  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18002ff78  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ff7f  lea     edx, [r15+11h]
0x18002ff83  mov     r9d, eax
0x18002ff86  mov     dword ptr [rsp+0E0h+var_C0], esi
0x18002ff8a  lea     r8, WPP_e96ad774d77a3b20501daafc53de2dbd_Traceguids
0x18002ff91  mov     rcx, [rcx+10h]
0x18002ff95  call    WPP_SF_Dd
0x18002ff9a  test    esi, esi
0x18002ff9c  jle     short loc_18002FFA7
0x18002ff9e  movzx   esi, si
0x18002ffa1  or      esi, 80070000h
0x18002ffa7  mov     ebx, 80004005h
0x18002ffac  test    esi, esi
0x18002ffae  cmovns  esi, ebx
0x18002ffb1  mov     ebx, esi
0x18002ffb3  jmp     loc_180030391
0x18002ffb8  mov     [rsp+0E0h+var_B8], r13
0x18002ffbd  lea     rdx, GUID_DEVINTERFACE_TSUSBHUB
0x18002ffc4  mov     r9d, 10h
0x18002ffca  mov     [rsp+0E0h+var_C0], r13
0x18002ffcf  xor     r8d, r8d
0x18002ffd2  mov     rcx, r15
0x18002ffd5  call    cs:__imp_DevObjGetClassDevs
0x18002ffdb  test    eax, eax
0x18002ffdd  jnz     short loc_180030048
0x18002ffdf  call    cs:__imp_GetLastError
0x18002ffe5  mov     ebx, eax
0x18002ffe7  test    eax, eax
0x18002ffe9  jle     short loc_18002FFF4
0x18002ffeb  movzx   ebx, ax
0x18002ffee  or      ebx, 80070000h
0x18002fff4  mov     rax, cs:WPP_GLOBAL_Control
0x18002fffb  lea     rdi, WPP_GLOBAL_Control
0x180030002  cmp     rax, rdi
0x180030005  jz      loc_180030388
0x18003000b  test    [rax+1Ch], sil
0x18003000f  jz      loc_180030388
0x180030015  cmp     byte ptr [rax+19h], 2
0x180030019  jb      loc_180030388
0x18003001f  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180030024  mov     rcx, cs:WPP_GLOBAL_Control
0x18003002b  lea     r8, WPP_e96ad774d77a3b20501daafc53de2dbd_Traceguids
0x180030032  mov     edx, 11h
0x180030037  mov     r9d, eax
0x18003003a  mov     rcx, [rcx+10h]
0x18003003e  call    WPP_SF_D
0x180030043  jmp     loc_180030388
0x180030048  mov     r14, [rbp+57h+var_A8]
0x18003004c  lea     rdi, WPP_GLOBAL_Control
0x180030053  xor     r12d, r12d
0x180030056  xorps   xmm0, xmm0
0x180030059  lea     r8, [rbp+57h+var_78]
0x18003005d  movups  [rbp+57h+var_78], xmm0
0x180030061  mov     edx, r12d
0x180030064  mov     dword ptr [rbp+57h+var_78], 30h ; '0'
0x18003006b  mov     rcx, r15
0x18003006e  movups  [rbp+57h+var_68], xmm0
0x180030072  movups  [rbp+57h+var_58], xmm0
0x180030076  call    cs:__imp_DevObjEnumDeviceInfo
0x18003007c  test    eax, eax
0x18003007e  jz      loc_1800302CA
0x180030084  lea     rax, [rbp+57h+var_98]
0x180030088  mov     dword ptr [rbp+57h+var_98], 20h ; ' '
0x18003008f  xor     r9d, r9d
0x180030092  mov     [rsp+0E0h+var_C0], rax
0x180030097  lea     r8, GUID_DEVINTERFACE_TSUSBHUB
0x18003009e  mov     rcx, r15
0x1800300a1  lea     rdx, [rbp+57h+var_78]
0x1800300a5  call    cs:__imp_DevObjEnumDeviceInterfaces
0x1800300ab  test    eax, eax
0x1800300ad  jnz     short loc_180030108
0x1800300af  call    cs:__imp_GetLastError
0x1800300b5  mov     ebx, eax
0x1800300b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800300be  cmp     rcx, rdi
0x1800300c1  jz      loc_1800302C2
0x1800300c7  test    [rcx+1Ch], sil
0x1800300cb  jz      loc_1800302C2
0x1800300d1  cmp     byte ptr [rcx+19h], 2
0x1800300d5  jb      loc_1800302C2
0x1800300db  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800300e0  mov     edx, 13h
0x1800300e5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800300ec  lea     r8, WPP_e96ad774d77a3b20501daafc53de2dbd_Traceguids
0x1800300f3  mov     r9d, eax
0x1800300f6  mov     dword ptr [rsp+0E0h+var_C0], ebx
0x1800300fa  mov     rcx, [rcx+10h]
0x1800300fe  call    WPP_SF_Dd
0x180030103  jmp     loc_1800302C2
0x180030108  lea     rax, [rbp+57h+size]
0x18003010c  mov     [rsp+0E0h+var_B8], 0
0x180030115  xor     r9d, r9d
0x180030118  mov     [rsp+0E0h+var_C0], rax
0x18003011d  xor     r8d, r8d
0x180030120  lea     rdx, [rbp+57h+var_98]
0x180030124  mov     rcx, r15
0x180030127  call    cs:__imp_DevObjGetDeviceInterfaceDetail
0x18003012d  test    eax, eax
0x18003012f  jnz     short loc_180030177
0x180030131  call    cs:__imp_GetLastError
0x180030137  cmp     eax, 7Ah ; 'z'
0x18003013a  jz      short loc_180030177
0x18003013c  call    cs:__imp_GetLastError
0x180030142  mov     ebx, eax
0x180030144  mov     rcx, cs:WPP_GLOBAL_Control
0x18003014b  cmp     rcx, rdi
0x18003014e  jz      loc_1800302C2
0x180030154  test    [rcx+1Ch], sil
0x180030158  jz      loc_1800302C2
0x18003015e  cmp     byte ptr [rcx+19h], 2
0x180030162  jb      loc_1800302C2
0x180030168  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18003016d  mov     edx, 14h
0x180030172  jmp     loc_1800300E5
0x180030177  mov     ebx, dword ptr [rbp+57h+size]
0x18003017a  cmp     ebx, 4
0x18003017d  ja      short loc_1800301B2
0x18003017f  mov     rax, cs:WPP_GLOBAL_Control
0x180030186  cmp     rax, rdi
0x180030189  jz      loc_1800302C2
0x18003018f  test    [rax+1Ch], sil
0x180030193  jz      loc_1800302C2
0x180030199  cmp     byte ptr [rax+19h], 2
0x18003019d  jb      loc_1800302C2
0x1800301a3  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800301a8  mov     edx, 15h
0x1800301ad  jmp     loc_1800300E5
0x1800301b2  mov     rcx, r13; Block
0x1800301b5  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800301ba  mov     ecx, dword ptr [rbp+57h+size]; size
0x1800301bd  call    MIDL_user_allocate
0x1800301c2  mov     r13, rax
0x1800301c5  test    rax, rax
0x1800301c8  jnz     short loc_180030205
0x1800301ca  call    cs:__imp_GetLastError
0x1800301d0  mov     rax, cs:WPP_GLOBAL_Control
0x1800301d7  cmp     rax, rdi
0x1800301da  jz      loc_1800302C2
0x1800301e0  test    [rax+1Ch], sil
0x1800301e4  jz      loc_1800302C2
0x1800301ea  cmp     byte ptr [rax+19h], 2
0x1800301ee  jb      loc_1800302C2
0x1800301f4  mov     ebx, dword ptr [rbp+57h+size]
0x1800301f7  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800301fc  lea     edx, [r13+16h]
0x180030200  jmp     loc_1800300E5
0x180030205  mov     dword ptr [rax], 8
0x18003020b  lea     rdx, [rbp+57h+var_98]
0x18003020f  mov     r9d, dword ptr [rbp+57h+size]
0x180030213  lea     rax, [rbp+57h+size+4]
0x180030217  mov     [rsp+0E0h+var_B8], 0
0x180030220  mov     r8, r13
0x180030223  mov     rcx, r15
0x180030226  mov     [rsp+0E0h+var_C0], rax
0x18003022b  call    cs:__imp_DevObjGetDeviceInterfaceDetail
0x180030231  test    eax, eax
0x180030233  jnz     short loc_180030264
0x180030235  call    cs:__imp_GetLastError
  ... truncated ...
```
