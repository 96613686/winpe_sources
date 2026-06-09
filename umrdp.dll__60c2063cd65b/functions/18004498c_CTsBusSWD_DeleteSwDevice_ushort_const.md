# CTsBusSWD::DeleteSwDevice(ushort const *)

- ea: `0x18004498c`
- end: `0x180044b5f`
- name: `?DeleteSwDevice@CTsBusSWD@@KAJPEBG@Z`
- size: `467`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800443c4`

## callees

- `0x18000b8f8`
- `0x18000f79c`
- `0x18004498c`
- `0x180047ef0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800449ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044a71`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044add`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800449ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044a71`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044add`
- `DEVOBJ!DevObjDeleteDevice` at `0x180044ad3`
- `DEVOBJ!DevObjDeleteDevice` at `0x180044ad3`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x1800449bb`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x1800449bb`
- `DEVOBJ!DevObjOpenDeviceInfo` at `0x180044a67`
- `DEVOBJ!DevObjOpenDeviceInfo` at `0x180044a67`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x180044b3c`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x180044b3c`

## pseudocode

```c
__int64 __fastcall CTsBusSWD::DeleteSwDevice(const unsigned __int16 *a1)
{
  __int64 DeviceInfoList; // rdi
  signed int v3; // eax
  unsigned int v4; // ebx
  unsigned int v5; // eax
  signed int v6; // eax
  unsigned int CurrentThreadActivityIdPrefix; // eax
  __int64 v8; // rdx
  signed int LastError; // eax
  int v11; // [rsp+30h] [rbp-48h] BYREF
  _OWORD v12[3]; // [rsp+38h] [rbp-40h] BYREF

  DeviceInfoList = DevObjCreateDeviceInfoList(0, 0, 0, 0, 0);
  if ( DeviceInfoList != -1 )
  {
    memset(v12, 0, sizeof(v12));
    LODWORD(v12[0]) = 48;
    if ( (unsigned int)DevObjOpenDeviceInfo(DeviceInfoList, a1, 0, 0, v12) )
    {
      v4 = 0;
      v11 = 0;
      if ( (unsigned int)DevObjDeleteDevice(DeviceInfoList, v12, 0, &v11) )
        goto LABEL_23;
      LastError = GetLastError();
      v4 = LastError;
      if ( LastError > 0 )
        v4 = (unsigned __int16)LastError | 0x80070000;
      if ( *(unsigned int **)&WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 1) == 0
        || *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) < 2u )
      {
        goto LABEL_23;
      }
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v8 = 20;
    }
    else
    {
      v6 = GetLastError();
      v4 = v6;
      if ( v6 > 0 )
        v4 = (unsigned __int16)v6 | 0x80070000;
      if ( *(unsigned int **)&WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 1) == 0
        || *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) < 2u )
      {
        goto LABEL_23;
      }
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v8 = 19;
    }
    WPP_SF_Dd(
      *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
      v8,
      WPP_cedcbb68cb9f31051550b3e4d62132eb_Traceguids,
      CurrentThreadActivityIdPrefix,
      v4);
LABEL_23:
    DevObjDestroyDeviceInfoList(DeviceInfoList);
    return v4;
  }
  v3 = GetLastError();
  v4 = v3;
  if ( v3 > 0 )
    v4 = (unsigned __int16)v3 | 0x80070000;
  if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 1) != 0
    && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
  {
    v5 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_Dd(
      *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
      18,
      WPP_cedcbb68cb9f31051550b3e4d62132eb_Traceguids,
      v5,
      v4);
  }
  return v4;
}

```

## disassembly

```asm
0x18004498c  mov     [rsp+arg_8], rbx
0x180044991  push    rdi
0x180044992  sub     rsp, 70h
0x180044996  mov     rax, cs:__security_cookie
0x18004499d  xor     rax, rsp
0x1800449a0  mov     [rsp+78h+var_10], rax
0x1800449a5  mov     rbx, rcx
0x1800449a8  mov     [rsp+78h+var_58], 0
0x1800449b1  xor     ecx, ecx
0x1800449b3  xor     r9d, r9d
0x1800449b6  xor     r8d, r8d
0x1800449b9  xor     edx, edx
0x1800449bb  call    cs:__imp_DevObjCreateDeviceInfoList
0x1800449c1  mov     rdi, rax
0x1800449c4  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800449c8  jnz     short loc_180044A37
0x1800449ca  call    cs:__imp_GetLastError
0x1800449d0  mov     ebx, eax
0x1800449d2  test    eax, eax
0x1800449d4  jle     short loc_1800449DF
0x1800449d6  movzx   ebx, ax
0x1800449d9  or      ebx, 80070000h
0x1800449df  mov     rcx, cs:WPP_GLOBAL_Control
0x1800449e6  lea     rax, WPP_GLOBAL_Control
0x1800449ed  cmp     rcx, rax
0x1800449f0  jz      loc_180044B42
0x1800449f6  test    byte ptr [rcx+1Ch], 1
0x1800449fa  jz      loc_180044B42
0x180044a00  cmp     byte ptr [rcx+19h], 2
0x180044a04  jb      loc_180044B42
0x180044a0a  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180044a0f  mov     rcx, cs:WPP_GLOBAL_Control
0x180044a16  lea     r8, WPP_cedcbb68cb9f31051550b3e4d62132eb_Traceguids
0x180044a1d  mov     edx, 12h
0x180044a22  mov     dword ptr [rsp+78h+var_58], ebx
0x180044a26  mov     r9d, eax
0x180044a29  mov     rcx, [rcx+10h]
0x180044a2d  call    WPP_SF_Dd
0x180044a32  jmp     loc_180044B42
0x180044a37  xorps   xmm0, xmm0
0x180044a3a  lea     rax, [rsp+78h+var_40]
0x180044a3f  movups  [rsp+78h+var_40], xmm0
0x180044a44  xor     r9d, r9d
0x180044a47  mov     dword ptr [rsp+78h+var_40], 30h ; '0'
0x180044a4f  xor     r8d, r8d
0x180044a52  mov     [rsp+78h+var_58], rax
0x180044a57  mov     rdx, rbx
0x180044a5a  mov     rcx, rdi
0x180044a5d  movups  [rsp+78h+var_30], xmm0
0x180044a62  movups  [rsp+78h+var_20], xmm0
0x180044a67  call    cs:__imp_DevObjOpenDeviceInfo
0x180044a6d  test    eax, eax
0x180044a6f  jnz     short loc_180044ABD
0x180044a71  call    cs:__imp_GetLastError
0x180044a77  mov     ebx, eax
0x180044a79  test    eax, eax
0x180044a7b  jle     short loc_180044A86
0x180044a7d  movzx   ebx, ax
0x180044a80  or      ebx, 80070000h
0x180044a86  mov     rcx, cs:WPP_GLOBAL_Control
0x180044a8d  lea     rax, WPP_GLOBAL_Control
0x180044a94  cmp     rcx, rax
0x180044a97  jz      loc_180044B39
0x180044a9d  test    byte ptr [rcx+1Ch], 1
0x180044aa1  jz      loc_180044B39
0x180044aa7  cmp     byte ptr [rcx+19h], 2
0x180044aab  jb      loc_180044B39
0x180044ab1  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180044ab6  mov     edx, 13h
0x180044abb  jmp     short loc_180044B1B
0x180044abd  xor     ebx, ebx
0x180044abf  lea     r9, [rsp+78h+var_48]
0x180044ac4  xor     r8d, r8d
0x180044ac7  mov     [rsp+78h+var_48], ebx
0x180044acb  lea     rdx, [rsp+78h+var_40]
0x180044ad0  mov     rcx, rdi
0x180044ad3  call    cs:__imp_DevObjDeleteDevice
0x180044ad9  test    eax, eax
0x180044adb  jnz     short loc_180044B39
0x180044add  call    cs:__imp_GetLastError
0x180044ae3  mov     ebx, eax
0x180044ae5  test    eax, eax
0x180044ae7  jle     short loc_180044AF2
0x180044ae9  movzx   ebx, ax
0x180044aec  or      ebx, 80070000h
0x180044af2  mov     rcx, cs:WPP_GLOBAL_Control
0x180044af9  lea     rax, WPP_GLOBAL_Control
0x180044b00  cmp     rcx, rax
0x180044b03  jz      short loc_180044B39
0x180044b05  test    byte ptr [rcx+1Ch], 1
0x180044b09  jz      short loc_180044B39
0x180044b0b  cmp     byte ptr [rcx+19h], 2
0x180044b0f  jb      short loc_180044B39
0x180044b11  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180044b16  mov     edx, 14h
0x180044b1b  mov     rcx, cs:WPP_GLOBAL_Control
0x180044b22  lea     r8, WPP_cedcbb68cb9f31051550b3e4d62132eb_Traceguids
0x180044b29  mov     r9d, eax
0x180044b2c  mov     dword ptr [rsp+78h+var_58], ebx
0x180044b30  mov     rcx, [rcx+10h]
0x180044b34  call    WPP_SF_Dd
0x180044b39  mov     rcx, rdi
0x180044b3c  call    cs:__imp_DevObjDestroyDeviceInfoList
0x180044b42  mov     eax, ebx
0x180044b44  mov     rcx, [rsp+78h+var_10]
0x180044b49  xor     rcx, rsp; StackCookie
0x180044b4c  call    __security_check_cookie
0x180044b51  mov     rbx, [rsp+78h+arg_8]
0x180044b59  add     rsp, 70h
0x180044b5d  pop     rdi
0x180044b5e  retn
```
