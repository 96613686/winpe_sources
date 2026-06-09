# IsDiskOnUSB

- ea: `0x18000f180`
- end: `0x18000f325`
- name: `IsDiskOnUSB`
- size: `421`
- prototype: `__int64 __fastcall(int, _DWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000edec`

## callees

- `0x18000e360`
- `0x18000e928`
- `0x18000f180`
- `0x18000f32c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f1c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f22d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f2eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f1c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f22d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f2eb`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x18000f1b7`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x18000f1b7`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x18000f2e1`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x18000f2e1`
- `DEVOBJ!DevObjGetClassDevs` at `0x18000f21c`
- `DEVOBJ!DevObjGetClassDevs` at `0x18000f21c`

## pseudocode

```c
__int64 __fastcall IsDiskOnUSB(int a1, _DWORD *a2)
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
      v10 = 23;
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
        v14 = 25;
        goto LABEL_17;
      }
    }
    else
    {
      v19[0] = v16;
      v19[1] = v17;
      v19[2] = v18;
      MatchingDeviceInfoData = DetermineIfControllerIsUSB((__int64)v5, v19, a2);
      v8 = MatchingDeviceInfoData;
      if ( MatchingDeviceInfoData )
      {
        v13 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v14 = 26;
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
      v14 = 24;
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
      v10 = 27;
      goto LABEL_22;
    }
  }
  return v8;
}

```

## disassembly

```asm
0x18000f180  push    rbx
0x18000f182  push    rbp
0x18000f183  push    rsi
0x18000f184  push    r14
0x18000f186  sub     rsp, 98h
0x18000f18d  xorps   xmm0, xmm0
0x18000f190  mov     [rsp+0B8h+var_98], 0
0x18000f199  mov     r14, rdx
0x18000f19c  mov     ebx, ecx
0x18000f19e  xor     edx, edx
0x18000f1a0  xor     ecx, ecx
0x18000f1a2  xor     r9d, r9d
0x18000f1a5  xor     r8d, r8d
0x18000f1a8  movups  [rsp+0B8h+var_88], xmm0
0x18000f1ad  movups  [rsp+0B8h+var_78], xmm0
0x18000f1b2  movups  [rsp+0B8h+var_68], xmm0
0x18000f1b7  call    cs:__imp_DevObjCreateDeviceInfoList
0x18000f1bd  mov     rbp, rax
0x18000f1c0  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000f1c4  jnz     short loc_18000F1F7
0x18000f1c6  call    cs:__imp_GetLastError
0x18000f1cc  mov     ebx, eax
0x18000f1ce  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f1d5  lea     rsi, WPP_GLOBAL_Control
0x18000f1dc  cmp     rcx, rsi
0x18000f1df  jz      loc_18000F316
0x18000f1e5  test    byte ptr [rcx+1Ch], 1
0x18000f1e9  jz      loc_18000F316
0x18000f1ef  lea     edx, [rbp+18h]
0x18000f1f2  jmp     loc_18000F30A
0x18000f1f7  mov     [rsp+0B8h+var_90], 0
0x18000f200  lea     rdx, GUID_DEVINTERFACE_DISK
0x18000f207  mov     r9d, 12h
0x18000f20d  mov     [rsp+0B8h+var_98], 0
0x18000f216  xor     r8d, r8d
0x18000f219  mov     rcx, rbp
0x18000f21c  call    cs:__imp_DevObjGetClassDevs
0x18000f222  lea     rsi, WPP_GLOBAL_Control
0x18000f229  test    eax, eax
0x18000f22b  jnz     short loc_18000F256
0x18000f22d  call    cs:__imp_GetLastError
0x18000f233  mov     ebx, eax
0x18000f235  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f23c  cmp     rcx, rsi
0x18000f23f  jz      loc_18000F2DE
0x18000f245  test    byte ptr [rcx+1Ch], 1
0x18000f249  jz      loc_18000F2DE
0x18000f24f  mov     edx, 18h
0x18000f254  jmp     short loc_18000F2D2
0x18000f256  lea     r8, [rsp+0B8h+var_88]; struct _DO_DEVINFO_DATA *
0x18000f25b  mov     edx, ebx; unsigned int
0x18000f25d  mov     rcx, rbp; void *
0x18000f260  call    ?FindMatchingDeviceInfoData@@YAKPEAXKPEAU_DO_DEVINFO_DATA@@@Z; FindMatchingDeviceInfoData(void *,ulong,_DO_DEVINFO_DATA *)
0x18000f265  mov     ebx, eax
0x18000f267  test    eax, eax
0x18000f269  jz      short loc_18000F284
0x18000f26b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f272  cmp     rcx, rsi
0x18000f275  jz      short loc_18000F2DE
0x18000f277  test    byte ptr [rcx+1Ch], 1
0x18000f27b  jz      short loc_18000F2DE
0x18000f27d  mov     edx, 19h
0x18000f282  jmp     short loc_18000F2D2
0x18000f284  movups  xmm0, [rsp+0B8h+var_88]
0x18000f289  mov     r8, r14
0x18000f28c  lea     rdx, [rsp+0B8h+var_58]
0x18000f291  movups  xmm1, [rsp+0B8h+var_78]
0x18000f296  mov     rcx, rbp
0x18000f299  movaps  [rsp+0B8h+var_58], xmm0
0x18000f29e  movups  xmm0, [rsp+0B8h+var_68]
0x18000f2a3  movaps  [rsp+0B8h+var_48], xmm1
0x18000f2a8  movaps  [rsp+0B8h+var_38], xmm0
0x18000f2b0  call    ?DetermineIfControllerIsUSB@@YAKPEAXU_DO_DEVINFO_DATA@@PEAW4_USB_BOOT_INFORMATION_CONTROLLER_TYPE@@@Z; DetermineIfControllerIsUSB(void *,_DO_DEVINFO_DATA,_USB_BOOT_INFORMATION_CONTROLLER_TYPE *)
0x18000f2b5  mov     ebx, eax
0x18000f2b7  test    eax, eax
0x18000f2b9  jz      short loc_18000F2DE
0x18000f2bb  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f2c2  cmp     rcx, rsi
0x18000f2c5  jz      short loc_18000F2DE
0x18000f2c7  test    byte ptr [rcx+1Ch], 1
0x18000f2cb  jz      short loc_18000F2DE
0x18000f2cd  mov     edx, 1Ah
0x18000f2d2  mov     rcx, [rcx+10h]
0x18000f2d6  mov     r9d, eax
0x18000f2d9  call    WPP_SF_D
0x18000f2de  mov     rcx, rbp
0x18000f2e1  call    cs:__imp_DevObjDestroyDeviceInfoList
0x18000f2e7  test    eax, eax
0x18000f2e9  jnz     short loc_18000F316
0x18000f2eb  call    cs:__imp_GetLastError
0x18000f2f1  mov     ebx, eax
0x18000f2f3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f2fa  cmp     rcx, rsi
0x18000f2fd  jz      short loc_18000F316
0x18000f2ff  test    byte ptr [rcx+1Ch], 1
0x18000f303  jz      short loc_18000F316
0x18000f305  mov     edx, 1Bh
0x18000f30a  mov     rcx, [rcx+10h]
0x18000f30e  mov     r9d, eax
0x18000f311  call    WPP_SF_D
0x18000f316  mov     eax, ebx
0x18000f318  add     rsp, 98h
0x18000f31f  pop     r14
0x18000f321  pop     rsi
0x18000f322  pop     rbp
0x18000f323  pop     rbx
0x18000f324  retn
```
