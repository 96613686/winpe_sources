# IsDiskExternal

- ea: `0x18000f9ec`
- end: `0x18000fb1a`
- name: `IsDiskExternal`
- size: `302`
- prototype: `__int64 __fastcall(int, _BYTE *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000edec`

## callees

- `0x180002410`
- `0x18000e928`
- `0x18000f9ec`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fa41`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000faef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fa41`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000faef`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x18000fa32`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x18000fa32`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x18000fafa`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x18000fafa`
- `DEVOBJ!DevObjGetDeviceProperty` at `0x18000facc`
- `DEVOBJ!DevObjGetDeviceProperty` at `0x18000facc`
- `DEVOBJ!DevObjGetClassDevs` at `0x18000fa73`
- `DEVOBJ!DevObjGetClassDevs` at `0x18000fa73`

## pseudocode

```c
__int64 __fastcall IsDiskExternal(int a1, _BYTE *a2)
{
  __int64 DeviceInfoList; // rax
  void *v5; // rdi
  unsigned int MatchingDeviceInfoData; // ebx
  _BYTE v8[4]; // [rsp+40h] [rbp-19h] BYREF
  int v9; // [rsp+44h] [rbp-15h] BYREF
  int v10; // [rsp+48h] [rbp-11h] BYREF
  _OWORD v11[3]; // [rsp+50h] [rbp-9h] BYREF

  memset(v11, 0, sizeof(v11));
  DeviceInfoList = DevObjCreateDeviceInfoList(0, 0, 0, 0, 0);
  v5 = (void *)DeviceInfoList;
  if ( DeviceInfoList != -1 )
  {
    if ( (unsigned int)DevObjGetClassDevs(DeviceInfoList, &GUID_DEVINTERFACE_DISK, 0, 18, 0, 0) )
    {
      MatchingDeviceInfoData = FindMatchingDeviceInfoData(v5, a1, (struct _DO_DEVINFO_DATA *)v11);
      if ( MatchingDeviceInfoData )
      {
LABEL_12:
        DevObjDestroyDeviceInfoList(v5);
        return MatchingDeviceInfoData;
      }
      *a2 = 0;
      v8[0] = 0;
      v9 = 0;
      v10 = 0;
      if ( (unsigned int)DevObjGetDeviceProperty(v5, v11, &DEVPKEY_Device_InLocalMachineContainer, &v9, v8, 1, &v10, 0) )
      {
        if ( v9 == 17 && v10 == 1 && v8[0] != 0xFF )
          *a2 = 1;
        MatchingDeviceInfoData = 0;
        goto LABEL_12;
      }
    }
    MatchingDeviceInfoData = GetLastError();
    goto LABEL_12;
  }
  return GetLastError();
}

```

## disassembly

```asm
0x18000f9ec  push    rbp
0x18000f9ee  push    rbx
0x18000f9ef  push    rsi
0x18000f9f0  push    rdi
0x18000f9f1  lea     rbp, [rsp-3Fh]
0x18000f9f6  sub     rsp, 98h
0x18000f9fd  mov     rax, cs:__security_cookie
0x18000fa04  xor     rax, rsp
0x18000fa07  mov     [rbp+57h+var_30], rax
0x18000fa0b  xorps   xmm0, xmm0
0x18000fa0e  mov     [rsp+0B0h+var_90], 0
0x18000fa17  mov     rsi, rdx
0x18000fa1a  mov     ebx, ecx
0x18000fa1c  xor     edx, edx
0x18000fa1e  xor     ecx, ecx
0x18000fa20  xor     r9d, r9d
0x18000fa23  xor     r8d, r8d
0x18000fa26  movups  [rbp+57h+var_60], xmm0
0x18000fa2a  movups  [rbp+57h+var_50], xmm0
0x18000fa2e  movups  [rbp+57h+var_40], xmm0
0x18000fa32  call    cs:__imp_DevObjCreateDeviceInfoList
0x18000fa38  mov     rdi, rax
0x18000fa3b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000fa3f  jnz     short loc_18000FA4E
0x18000fa41  call    cs:__imp_GetLastError
0x18000fa47  mov     ebx, eax
0x18000fa49  jmp     loc_18000FB00
0x18000fa4e  mov     [rsp+0B0h+var_88], 0
0x18000fa57  lea     rdx, GUID_DEVINTERFACE_DISK
0x18000fa5e  mov     r9d, 12h
0x18000fa64  mov     [rsp+0B0h+var_90], 0
0x18000fa6d  xor     r8d, r8d
0x18000fa70  mov     rcx, rdi
0x18000fa73  call    cs:__imp_DevObjGetClassDevs
0x18000fa79  test    eax, eax
0x18000fa7b  jz      short loc_18000FAEF
0x18000fa7d  lea     r8, [rbp+57h+var_60]; struct _DO_DEVINFO_DATA *
0x18000fa81  mov     edx, ebx; unsigned int
0x18000fa83  mov     rcx, rdi; void *
0x18000fa86  call    ?FindMatchingDeviceInfoData@@YAKPEAXKPEAU_DO_DEVINFO_DATA@@@Z; FindMatchingDeviceInfoData(void *,ulong,_DO_DEVINFO_DATA *)
0x18000fa8b  mov     ebx, eax
0x18000fa8d  test    eax, eax
0x18000fa8f  jnz     short loc_18000FAF7
0x18000fa91  mov     [rsp+0B0h+var_78], eax
0x18000fa95  lea     r9, [rbp+57h+var_6C]
0x18000fa99  mov     [rsi], al
0x18000fa9b  lea     r8, DEVPKEY_Device_InLocalMachineContainer
0x18000faa2  mov     [rbp+57h+var_70], al
0x18000faa5  lea     rdx, [rbp+57h+var_60]
0x18000faa9  mov     [rbp+57h+var_6C], eax
0x18000faac  mov     rcx, rdi
0x18000faaf  mov     [rbp+57h+var_68], eax
0x18000fab2  lea     rax, [rbp+57h+var_68]
0x18000fab6  mov     [rsp+0B0h+var_80], rax
0x18000fabb  lea     rax, [rbp+57h+var_70]
0x18000fabf  mov     dword ptr [rsp+0B0h+var_88], 1
0x18000fac7  mov     [rsp+0B0h+var_90], rax
0x18000facc  call    cs:__imp_DevObjGetDeviceProperty
0x18000fad2  test    eax, eax
0x18000fad4  jz      short loc_18000FAEF
0x18000fad6  cmp     [rbp+57h+var_6C], 11h
0x18000fada  jnz     short loc_18000FAEB
0x18000fadc  cmp     [rbp+57h+var_68], 1
0x18000fae0  jnz     short loc_18000FAEB
0x18000fae2  cmp     [rbp+57h+var_70], 0FFh
0x18000fae6  jz      short loc_18000FAEB
0x18000fae8  mov     byte ptr [rsi], 1
0x18000faeb  xor     ebx, ebx
0x18000faed  jmp     short loc_18000FAF7
0x18000faef  call    cs:__imp_GetLastError
0x18000faf5  mov     ebx, eax
0x18000faf7  mov     rcx, rdi
0x18000fafa  call    cs:__imp_DevObjDestroyDeviceInfoList
0x18000fb00  mov     eax, ebx
0x18000fb02  mov     rcx, [rbp+57h+var_30]
0x18000fb06  xor     rcx, rsp; StackCookie
0x18000fb09  call    __security_check_cookie
0x18000fb0e  add     rsp, 98h
0x18000fb15  pop     rdi
0x18000fb16  pop     rsi
0x18000fb17  pop     rbx
0x18000fb18  pop     rbp
0x18000fb19  retn
```
