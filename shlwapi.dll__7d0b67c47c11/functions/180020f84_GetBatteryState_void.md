# GetBatteryState(void)

- ea: `0x180020f84`
- end: `0x180021249`
- name: `?GetBatteryState@@YAKXZ`
- size: `709`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, installer_update`

## callers

- `0x1800212c0`

## callees

- `0x180012550`
- `0x180020f84`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021041`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800211ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021041`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800211ff`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180020fd7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180020fd7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800211ee`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800211ee`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180021056`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180021056`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800211f7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800211f7`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800210c5`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800210c5`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180021116`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180021172`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800211d8`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180021116`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180021172`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800211d8`
- `SETUPAPI!SetupDiGetDeviceInterfaceDetailW` at `0x18002103b`
- `SETUPAPI!SetupDiGetDeviceInterfaceDetailW` at `0x18002108e`
- `SETUPAPI!SetupDiGetDeviceInterfaceDetailW` at `0x18002103b`
- `SETUPAPI!SetupDiGetDeviceInterfaceDetailW` at `0x18002108e`
- `SETUPAPI!SetupDiDestroyDeviceInfoList` at `0x18002121c`
- `SETUPAPI!SetupDiDestroyDeviceInfoList` at `0x18002121c`
- `SETUPAPI!SetupDiEnumDeviceInterfaces` at `0x180021007`
- `SETUPAPI!SetupDiEnumDeviceInterfaces` at `0x180021007`
- `SETUPAPI!SetupDiGetClassDevsW` at `0x180020fbc`
- `SETUPAPI!SetupDiGetClassDevsW` at `0x180020fbc`

## pseudocode

```c
__int64 GetBatteryState(void)
{
  unsigned int v0; // ebx
  HDEVINFO ClassDevsW; // rdi
  signed int i; // r14d
  struct _SP_DEVICE_INTERFACE_DETAIL_DATA_W *v3; // rax
  WCHAR *v4; // rsi
  HANDLE FileW; // r15
  int v6; // eax
  __int64 result; // rax
  DWORD RequiredSize; // [rsp+40h] [rbp-79h] BYREF
  DWORD BytesReturned; // [rsp+44h] [rbp-75h] BYREF
  __int64 OutBuffer; // [rsp+48h] [rbp-71h] BYREF
  int v11; // [rsp+50h] [rbp-69h]
  int InBuffer; // [rsp+58h] [rbp-61h] BYREF
  __int128 v13; // [rsp+60h] [rbp-59h] BYREF
  struct _SP_DEVICE_INTERFACE_DATA DeviceInterfaceData; // [rsp+70h] [rbp-49h] BYREF
  int v15; // [rsp+90h] [rbp-29h] BYREF
  __int128 v16; // [rsp+94h] [rbp-25h]
  _OWORD v17[2]; // [rsp+A8h] [rbp-11h] BYREF
  int v18; // [rsp+C8h] [rbp+Fh]

  v0 = 2;
  ClassDevsW = SetupDiGetClassDevsW(&GUID_DEVICE_BATTERY, 0, 0, 0x12u);
  if ( ClassDevsW != (HDEVINFO)-1LL )
  {
    for ( i = 0; i < 100; ++i )
    {
      SetLastError(0x103u);
      memset(&DeviceInterfaceData, 0, sizeof(DeviceInterfaceData));
      DeviceInterfaceData.cbSize = 32;
      if ( SetupDiEnumDeviceInterfaces(ClassDevsW, 0, &GUID_DEVICE_BATTERY, i, &DeviceInterfaceData) )
      {
        RequiredSize = 0;
        SetupDiGetDeviceInterfaceDetailW(ClassDevsW, &DeviceInterfaceData, 0, 0, &RequiredSize, 0);
        if ( GetLastError() == 122 )
        {
          v3 = (struct _SP_DEVICE_INTERFACE_DETAIL_DATA_W *)LocalAlloc(0x40u, RequiredSize);
          v4 = (WCHAR *)v3;
          if ( v3 )
          {
            v3->cbSize = 8;
            if ( SetupDiGetDeviceInterfaceDetailW(ClassDevsW, &DeviceInterfaceData, v3, RequiredSize, &RequiredSize, 0) )
            {
              FileW = CreateFileW(v4 + 2, 0xC0000000, 3u, 0, 3u, 0x80u, 0);
              if ( FileW != (HANDLE)-1LL )
              {
                OutBuffer = 0;
                v11 = 0;
                InBuffer = 0;
                BytesReturned = 0;
                if ( DeviceIoControl(FileW, 0x294040u, &InBuffer, 4u, &OutBuffer, 4u, &BytesReturned, 0) )
                {
                  if ( (_DWORD)OutBuffer )
                  {
                    v18 = 0;
                    HIDWORD(OutBuffer) = 0;
                    memset(v17, 0, sizeof(v17));
                    if ( DeviceIoControl(FileW, 0x294044u, &OutBuffer, 0xCu, v17, 0x24u, &BytesReturned, 0) )
                    {
                      if ( SLODWORD(v17[0]) < 0 )
                      {
                        v6 = v0 | 1;
                        if ( (v17[0] & 0x20000000) != 0 )
                          v6 = v0;
                        v0 = v6;
                        v15 = OutBuffer;
                        v16 = 0;
                        v13 = 0;
                        if ( DeviceIoControl(FileW, 0x29404Cu, &v15, 0x14u, &v13, 0x10u, &BytesReturned, 0)
                          && (v13 & 1) != 0 )
                        {
                          v0 &= ~2u;
                        }
                      }
                    }
                  }
                }
                CloseHandle(FileW);
              }
            }
            LocalFree(v4);
          }
        }
      }
      else if ( GetLastError() == 259 )
      {
        break;
      }
    }
    SetupDiDestroyDeviceInfoList(ClassDevsW);
  }
  result = v0 & 0xFFFFFFFD;
  if ( (v0 & 1) != 0 )
    return v0;
  return result;
}

```

## disassembly

```asm
0x180020f84  push    rbp
0x180020f86  push    rbx
0x180020f87  push    rsi
0x180020f88  push    rdi
0x180020f89  push    r14
0x180020f8b  push    r15
0x180020f8d  lea     rbp, [rsp-2Fh]
0x180020f92  sub     rsp, 0E8h
0x180020f99  mov     rax, cs:__security_cookie
0x180020fa0  xor     rax, rsp
0x180020fa3  mov     [rbp+57h+var_40], rax
0x180020fa7  mov     ebx, 2
0x180020fac  lea     rcx, GUID_DEVICE_BATTERY; ClassGuid
0x180020fb3  xor     r8d, r8d; hwndParent
0x180020fb6  xor     edx, edx; Enumerator
0x180020fb8  lea     r9d, [rbx+10h]; Flags
0x180020fbc  call    cs:__imp_SetupDiGetClassDevsW
0x180020fc2  mov     rdi, rax
0x180020fc5  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180020fc9  jz      loc_180021222
0x180020fcf  xor     r14d, r14d
0x180020fd2  mov     ecx, 103h; dwErrCode
0x180020fd7  call    cs:__imp_SetLastError
0x180020fdd  xorps   xmm0, xmm0
0x180020fe0  lea     rax, [rbp+57h+var_A0]
0x180020fe4  movups  xmmword ptr [rbp+57h+var_A0.cbSize], xmm0
0x180020fe8  mov     r9d, r14d; MemberIndex
0x180020feb  mov     [rbp+57h+var_A0.cbSize], 20h ; ' '
0x180020ff2  lea     r8, GUID_DEVICE_BATTERY; InterfaceClassGuid
0x180020ff9  mov     [rsp+110h+DeviceInterfaceData], rax; DeviceInterfaceData
0x180020ffe  xor     edx, edx; DeviceInfoData
0x180021000  mov     rcx, rdi; DeviceInfoSet
0x180021003  movups  xmmword ptr [rbp+57h+var_A0.InterfaceClassGuid.Data4+4], xmm0
0x180021007  call    cs:__imp_SetupDiEnumDeviceInterfaces
0x18002100d  test    eax, eax
0x18002100f  jz      loc_1800211FF
0x180021015  lea     rax, [rbp+57h+RequiredSize]
0x180021019  mov     [rsp+110h+DeviceInfoData], 0; DeviceInfoData
0x180021022  xor     r9d, r9d; DeviceInterfaceDetailDataSize
0x180021025  mov     [rsp+110h+DeviceInterfaceData], rax; RequiredSize
0x18002102a  xor     r8d, r8d; DeviceInterfaceDetailData
0x18002102d  mov     [rbp+57h+RequiredSize], 0
0x180021034  lea     rdx, [rbp+57h+var_A0]; DeviceInterfaceData
0x180021038  mov     rcx, rdi; DeviceInfoSet
0x18002103b  call    cs:__imp_SetupDiGetDeviceInterfaceDetailW
0x180021041  call    cs:__imp_GetLastError
0x180021047  cmp     eax, 7Ah ; 'z'
0x18002104a  jnz     loc_18002120C
0x180021050  mov     edx, [rbp+57h+RequiredSize]; uBytes
0x180021053  lea     ecx, [rax-3Ah]; uFlags
0x180021056  call    cs:__imp_LocalAlloc
0x18002105c  mov     rsi, rax
0x18002105f  test    rax, rax
0x180021062  jz      loc_18002120C
0x180021068  mov     dword ptr [rax], 8
0x18002106e  lea     rdx, [rbp+57h+var_A0]; DeviceInterfaceData
0x180021072  mov     r9d, [rbp+57h+RequiredSize]; DeviceInterfaceDetailDataSize
0x180021076  lea     rax, [rbp+57h+RequiredSize]
0x18002107a  mov     [rsp+110h+DeviceInfoData], 0; DeviceInfoData
0x180021083  mov     r8, rsi; DeviceInterfaceDetailData
0x180021086  mov     rcx, rdi; DeviceInfoSet
0x180021089  mov     [rsp+110h+DeviceInterfaceData], rax; RequiredSize
0x18002108e  call    cs:__imp_SetupDiGetDeviceInterfaceDetailW
0x180021094  test    eax, eax
0x180021096  jz      loc_1800211F4
0x18002109c  xor     r9d, r9d; lpSecurityAttributes
0x18002109f  mov     [rsp+110h+hTemplateFile], 0; hTemplateFile
0x1800210a8  lea     rcx, [rsi+4]; lpFileName
0x1800210ac  mov     dword ptr [rsp+110h+DeviceInfoData], 80h; dwFlagsAndAttributes
0x1800210b4  mov     edx, 0C0000000h; dwDesiredAccess
0x1800210b9  mov     dword ptr [rsp+110h+DeviceInterfaceData], 3; dwCreationDisposition
0x1800210c1  lea     r8d, [r9+3]; dwShareMode
0x1800210c5  call    cs:__imp_CreateFileW
0x1800210cb  mov     r15, rax
0x1800210ce  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800210d2  jz      loc_1800211F4
0x1800210d8  xor     eax, eax
0x1800210da  lea     r8, [rbp+57h+InBuffer]; lpInBuffer
0x1800210de  mov     [rsp+110h+lpOverlapped], rax; lpOverlapped
0x1800210e3  mov     ecx, 4
0x1800210e8  mov     [rbp+57h+OutBuffer], rax
0x1800210ec  mov     r9d, ecx; nInBufferSize
0x1800210ef  mov     [rbp+57h+var_C0], eax
0x1800210f2  mov     edx, 294040h; dwIoControlCode
0x1800210f7  mov     [rbp+57h+InBuffer], eax
0x1800210fa  mov     [rbp+57h+BytesReturned], eax
0x1800210fd  lea     rax, [rbp+57h+BytesReturned]
0x180021101  mov     [rsp+110h+hTemplateFile], rax; lpBytesReturned
0x180021106  lea     rax, [rbp+57h+OutBuffer]
0x18002110a  mov     dword ptr [rsp+110h+DeviceInfoData], ecx; nOutBufferSize
0x18002110e  mov     rcx, r15; hDevice
0x180021111  mov     [rsp+110h+DeviceInterfaceData], rax; lpOutBuffer
0x180021116  call    cs:__imp_DeviceIoControl
0x18002111c  test    eax, eax
0x18002111e  jz      loc_1800211EB
0x180021124  cmp     dword ptr [rbp+57h+OutBuffer], 0
0x180021128  jz      loc_1800211EB
0x18002112e  xor     eax, eax
0x180021130  lea     r8, [rbp+57h+OutBuffer]; lpInBuffer
0x180021134  mov     [rsp+110h+lpOverlapped], rax; lpOverlapped
0x180021139  xorps   xmm0, xmm0
0x18002113c  mov     [rbp+57h+var_48], eax
0x18002113f  mov     r9d, 0Ch; nInBufferSize
0x180021145  mov     dword ptr [rbp+57h+OutBuffer+4], eax
0x180021148  mov     edx, 294044h; dwIoControlCode
0x18002114d  lea     rax, [rbp+57h+BytesReturned]
0x180021151  mov     rcx, r15; hDevice
0x180021154  mov     [rsp+110h+hTemplateFile], rax; lpBytesReturned
0x180021159  lea     rax, [rbp+57h+var_68]
0x18002115d  mov     dword ptr [rsp+110h+DeviceInfoData], 24h ; '$'; nOutBufferSize
0x180021165  mov     [rsp+110h+DeviceInterfaceData], rax; lpOutBuffer
0x18002116a  movups  [rbp+57h+var_68], xmm0
0x18002116e  movups  [rbp+57h+var_58], xmm0
0x180021172  call    cs:__imp_DeviceIoControl
0x180021178  test    eax, eax
0x18002117a  jz      short loc_1800211EB
0x18002117c  mov     ecx, dword ptr [rbp+57h+var_68]
0x18002117f  test    ecx, ecx
0x180021181  jns     short loc_1800211EB
0x180021183  mov     eax, ebx
0x180021185  mov     [rsp+110h+lpOverlapped], 0; lpOverlapped
0x18002118e  or      eax, 1
0x180021191  lea     r8, [rbp+57h+var_80]; lpInBuffer
0x180021195  bt      ecx, 1Dh
0x180021199  xorps   xmm0, xmm0
0x18002119c  mov     r9d, 14h; nInBufferSize
0x1800211a2  mov     edx, 29404Ch; dwIoControlCode
0x1800211a7  cmovb   eax, ebx
0x1800211aa  mov     rcx, r15; hDevice
0x1800211ad  mov     ebx, eax
0x1800211af  mov     eax, dword ptr [rbp+57h+OutBuffer]
0x1800211b2  mov     [rbp+57h+var_80], eax
0x1800211b5  lea     rax, [rbp+57h+BytesReturned]
0x1800211b9  mov     [rsp+110h+hTemplateFile], rax; lpBytesReturned
0x1800211be  lea     rax, [rbp+57h+var_B0]
0x1800211c2  mov     dword ptr [rsp+110h+DeviceInfoData], 10h; nOutBufferSize
0x1800211ca  mov     [rsp+110h+DeviceInterfaceData], rax; lpOutBuffer
0x1800211cf  movdqu  [rbp+57h+var_7C], xmm0
0x1800211d4  movups  [rbp+57h+var_B0], xmm0
0x1800211d8  call    cs:__imp_DeviceIoControl
0x1800211de  test    eax, eax
0x1800211e0  jz      short loc_1800211EB
0x1800211e2  test    byte ptr [rbp+57h+var_B0], 1
0x1800211e6  jz      short loc_1800211EB
0x1800211e8  and     ebx, 0FFFFFFFDh
0x1800211eb  mov     rcx, r15; hObject
0x1800211ee  call    cs:__imp_CloseHandle
0x1800211f4  mov     rcx, rsi; hMem
0x1800211f7  call    cs:__imp_LocalFree
0x1800211fd  jmp     short loc_18002120C
0x1800211ff  call    cs:__imp_GetLastError
0x180021205  cmp     eax, 103h
0x18002120a  jz      short loc_180021219
0x18002120c  inc     r14d
0x18002120f  cmp     r14d, 64h ; 'd'
0x180021213  jl      loc_180020FD2
0x180021219  mov     rcx, rdi; DeviceInfoSet
0x18002121c  call    cs:__imp_SetupDiDestroyDeviceInfoList
0x180021222  mov     eax, ebx
0x180021224  and     eax, 0FFFFFFFDh
0x180021227  test    bl, 1
0x18002122a  cmovnz  eax, ebx
0x18002122d  mov     rcx, [rbp+57h+var_40]
0x180021231  xor     rcx, rsp; StackCookie
0x180021234  call    __security_check_cookie
0x180021239  add     rsp, 0E8h
0x180021240  pop     r15
0x180021242  pop     r14
0x180021244  pop     rdi
0x180021245  pop     rsi
0x180021246  pop     rbx
0x180021247  pop     rbp
0x180021248  retn
```
