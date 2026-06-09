# UpdateLastPesterTime(ErcCmdMode)

- ea: `0x140015f18`
- end: `0x140016059`
- name: `?UpdateLastPesterTime@@YAJW4ErcCmdMode@@@Z`
- size: `321`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, installer_update`

## callers

- `0x14000e49c`
- `0x140016060`

## callees

- `0x14000e340`
- `0x140015ddc`
- `0x140015f18`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140015f8e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140015f8e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140016006`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140016006`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140016049`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140016049`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140015ffc`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140015ffc`

## pseudocode

```c
__int64 __fastcall UpdateLastPesterTime(int a1)
{
  unsigned int v2; // ebx
  _QWORD *v3; // rcx
  __int64 v4; // rdx
  int v5; // edi
  int v6; // edi
  const WCHAR *v7; // rdx
  signed int LastError; // eax
  HKEY hKey; // [rsp+58h] [rbp+28h] BYREF
  struct _FILETIME Data; // [rsp+60h] [rbp+30h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+68h] [rbp+38h] BYREF

  hKey = 0;
  SystemTimeAsFileTime = 0;
  Data = 0;
  v2 = OpenLastPesterTimeKey(&hKey);
  if ( (v2 & 0x80000000) != 0 )
  {
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v4 = 14;
LABEL_5:
      WPP_SF_d(v3[2], v4, &WPP_ee8ab0a08c903b60dc8973945bca5c85_Traceguids, v2);
      goto LABEL_21;
    }
    goto LABEL_21;
  }
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  Data = SystemTimeAsFileTime;
  if ( a1 )
  {
    v5 = a1 - 1;
    if ( v5 )
    {
      v6 = v5 - 3;
      if ( v6 )
      {
        if ( v6 != 1 )
        {
LABEL_20:
          v2 = 0;
          goto LABEL_21;
        }
        v7 = L"LastLiveReportFlushTime";
      }
      else
      {
        v7 = L"LastQueueNoPesterTime";
      }
    }
    else
    {
      v7 = L"LastResponsePesterTime";
    }
  }
  else
  {
    v7 = L"LastQueuePesterTime";
  }
  if ( !RegSetValueExW(hKey, v7, 0, 0xBu, (const BYTE *)&Data, 8u) )
    goto LABEL_20;
  LastError = GetLastError();
  v2 = LastError;
  if ( LastError > 0 )
    v2 = (unsigned __int16)LastError | 0x80070000;
  v3 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v4 = 15;
    goto LABEL_5;
  }
LABEL_21:
  if ( hKey )
    RegCloseKey(hKey);
  return v2;
}

```

## disassembly

```asm
0x140015f18  push    rbp
0x140015f1a  push    rbx
0x140015f1b  push    rdi
0x140015f1c  mov     rbp, rsp
0x140015f1f  sub     rsp, 30h
0x140015f23  mov     edi, ecx
0x140015f25  mov     [rbp+hKey], 0
0x140015f2d  lea     rcx, [rbp+hKey]
0x140015f31  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x140015f39  mov     [rbp+Data], 0
0x140015f41  call    OpenLastPesterTimeKey
0x140015f46  mov     ebx, eax
0x140015f48  test    eax, eax
0x140015f4a  jns     short loc_140015F8A
0x140015f4c  mov     rcx, cs:WPP_GLOBAL_Control
0x140015f53  lea     rax, WPP_GLOBAL_Control
0x140015f5a  cmp     rcx, rax
0x140015f5d  jz      loc_140016040
0x140015f63  test    byte ptr [rcx+1Ch], 1
0x140015f67  jz      loc_140016040
0x140015f6d  mov     edx, 0Eh
0x140015f72  mov     rcx, [rcx+10h]
0x140015f76  lea     r8, WPP_ee8ab0a08c903b60dc8973945bca5c85_Traceguids
0x140015f7d  mov     r9d, ebx
0x140015f80  call    WPP_SF_d
0x140015f85  jmp     loc_140016040
0x140015f8a  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x140015f8e  call    cs:__imp_GetSystemTimeAsFileTime
0x140015f94  mov     ecx, [rbp+SystemTimeAsFileTime.dwHighDateTime]
0x140015f97  mov     eax, [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x140015f9a  shl     rcx, 20h
0x140015f9e  or      rcx, rax
0x140015fa1  mov     [rbp+Data], rcx
0x140015fa5  test    edi, edi
0x140015fa7  jz      short loc_140015FD7
0x140015fa9  sub     edi, 1
0x140015fac  jz      short loc_140015FCE
0x140015fae  sub     edi, 3
0x140015fb1  jz      short loc_140015FC5
0x140015fb3  cmp     edi, 1
0x140015fb6  jnz     loc_14001603E
0x140015fbc  lea     rdx, aLastlivereport; "LastLiveReportFlushTime"
0x140015fc3  jmp     short loc_140015FDE
0x140015fc5  lea     rdx, aLastqueuenopes; "LastQueueNoPesterTime"
0x140015fcc  jmp     short loc_140015FDE
0x140015fce  lea     rdx, aLastresponsepe; "LastResponsePesterTime"
0x140015fd5  jmp     short loc_140015FDE
0x140015fd7  lea     rdx, aLastqueuepeste; "LastQueuePesterTime"
0x140015fde  mov     rcx, [rbp+hKey]; hKey
0x140015fe2  lea     rax, [rbp+Data]
0x140015fe6  mov     [rsp+30h+cbData], 8; cbData
0x140015fee  mov     r9d, 0Bh; dwType
0x140015ff4  xor     r8d, r8d; Reserved
0x140015ff7  mov     [rsp+30h+lpData], rax; lpData
0x140015ffc  call    cs:__imp_RegSetValueExW
0x140016002  test    eax, eax
0x140016004  jz      short loc_14001603E
0x140016006  call    cs:__imp_GetLastError
0x14001600c  mov     ebx, eax
0x14001600e  test    eax, eax
0x140016010  jle     short loc_14001601B
0x140016012  movzx   ebx, ax
0x140016015  or      ebx, 80070000h
0x14001601b  mov     rcx, cs:WPP_GLOBAL_Control
0x140016022  lea     rax, WPP_GLOBAL_Control
0x140016029  cmp     rcx, rax
0x14001602c  jz      short loc_140016040
0x14001602e  test    byte ptr [rcx+1Ch], 1
0x140016032  jz      short loc_140016040
0x140016034  mov     edx, 0Fh
0x140016039  jmp     loc_140015F72
0x14001603e  xor     ebx, ebx
0x140016040  mov     rcx, [rbp+hKey]; hKey
0x140016044  test    rcx, rcx
0x140016047  jz      short loc_14001604F
0x140016049  call    cs:__imp_RegCloseKey
0x14001604f  mov     eax, ebx
0x140016051  add     rsp, 30h
0x140016055  pop     rdi
0x140016056  pop     rbx
0x140016057  pop     rbp
0x140016058  retn
```
