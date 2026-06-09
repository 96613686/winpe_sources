# CreateMiracastDisplayCommandChannel

- ea: `0x180061b70`
- end: `0x180061cc0`
- name: `CreateMiracastDisplayCommandChannel`
- size: `336`
- prototype: `signed int __fastcall(DEVINSTID_W pDeviceID, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180061f68`

## callees

- `0x180061b70`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061c83`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061c83`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180061ca2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180061ca2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180061be8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180061be8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180061bd7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180061c94`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180061bd7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180061c94`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180061c6b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180061c6b`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x180061bb5`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x180061c30`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x180061bb5`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x180061c30`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_Interface_ListW` at `0x180061c1a`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_Interface_ListW` at `0x180061c1a`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_Interface_List_SizeW` at `0x180061ba4`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_Interface_List_SizeW` at `0x180061ba4`

## pseudocode

```c
signed int __fastcall CreateMiracastDisplayCommandChannel(DEVINSTID_W pDeviceID, __int64 a2, _QWORD *a3)
{
  CONFIGRET Device_Interface_List_SizeW; // eax
  signed int result; // eax
  SIZE_T v7; // rbx
  HANDLE ProcessHeap; // rax
  WCHAR *v9; // rax
  WCHAR *v10; // rbp
  CONFIGRET Device_Interface_ListW; // eax
  signed int v12; // ebx
  signed int v13; // eax
  HANDLE FileW; // rsi
  signed int LastError; // eax
  HANDLE v16; // rax
  ULONG BufferLen; // [rsp+68h] [rbp+10h] BYREF

  BufferLen = 0;
  Device_Interface_List_SizeW = CM_Get_Device_Interface_List_SizeW(
                                  &BufferLen,
                                  &GUID_DEVINTERFACE_MIRACAST_PRIVATE_CMD_INTERFACE,
                                  pDeviceID,
                                  0);
  if ( Device_Interface_List_SizeW )
  {
    result = CM_MapCrToWin32Err(Device_Interface_List_SizeW, 0x57u);
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  else
  {
    v7 = 2LL * BufferLen;
    ProcessHeap = GetProcessHeap();
    v9 = (WCHAR *)HeapAlloc(ProcessHeap, 8u, v7);
    v10 = v9;
    if ( v9 )
    {
      Device_Interface_ListW = CM_Get_Device_Interface_ListW(
                                 &GUID_DEVINTERFACE_MIRACAST_PRIVATE_CMD_INTERFACE,
                                 pDeviceID,
                                 v9,
                                 BufferLen,
                                 0);
      v12 = 0;
      if ( Device_Interface_ListW )
      {
        v13 = CM_MapCrToWin32Err(Device_Interface_ListW, 0x57u);
        v12 = v13;
        if ( v13 > 0 )
          v12 = (unsigned __int16)v13 | 0x80070000;
      }
      FileW = 0;
      if ( v12 >= 0 )
      {
        FileW = CreateFileW(v10, 0x10000000u, 3u, 0, 4u, 0x40120000u, 0);
        if ( (((unsigned __int64)FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
        {
          FileW = 0;
          LastError = GetLastError();
          v12 = LastError;
          if ( LastError > 0 )
            v12 = (unsigned __int16)LastError | 0x80070000;
        }
      }
      v16 = GetProcessHeap();
      HeapFree(v16, 0, v10);
      result = v12;
      *a3 = FileW;
    }
    else
    {
      return -2147024882;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180061b70  mov     rax, rsp
0x180061b73  mov     [rax+8], rbx
0x180061b77  mov     [rax+18h], rbp
0x180061b7b  mov     [rax+10h], edx
0x180061b7e  push    rsi
0x180061b7f  push    rdi
0x180061b80  push    r14
0x180061b82  sub     rsp, 40h
0x180061b86  mov     r14, r8
0x180061b89  mov     dword ptr [rax+10h], 0
0x180061b90  mov     r8, rcx; pDeviceID
0x180061b93  lea     rdx, GUID_DEVINTERFACE_MIRACAST_PRIVATE_CMD_INTERFACE; InterfaceClassGuid
0x180061b9a  mov     rdi, rcx
0x180061b9d  xor     r9d, r9d; ulFlags
0x180061ba0  lea     rcx, [rax+10h]; pulLen
0x180061ba4  call    cs:__imp_CM_Get_Device_Interface_List_SizeW
0x180061baa  test    eax, eax
0x180061bac  jz      short loc_180061BD0
0x180061bae  mov     edx, 57h ; 'W'; DefaultErr
0x180061bb3  mov     ecx, eax; CmReturnCode
0x180061bb5  call    cs:__imp_CM_MapCrToWin32Err
0x180061bbb  test    eax, eax
0x180061bbd  jle     loc_180061CAD
0x180061bc3  movzx   eax, ax
0x180061bc6  or      eax, 80070000h
0x180061bcb  jmp     loc_180061CAD
0x180061bd0  mov     ebx, [rsp+58h+BufferLen]
0x180061bd4  add     rbx, rbx
0x180061bd7  call    cs:__imp_GetProcessHeap
0x180061bdd  mov     r8, rbx; dwBytes
0x180061be0  mov     edx, 8; dwFlags
0x180061be5  mov     rcx, rax; hHeap
0x180061be8  call    cs:__imp_HeapAlloc
0x180061bee  mov     rbp, rax
0x180061bf1  test    rax, rax
0x180061bf4  jnz     short loc_180061C00
0x180061bf6  mov     eax, 8007000Eh
0x180061bfb  jmp     loc_180061CAD
0x180061c00  mov     r9d, [rsp+58h+BufferLen]; BufferLen
0x180061c05  lea     rcx, GUID_DEVINTERFACE_MIRACAST_PRIVATE_CMD_INTERFACE; InterfaceClassGuid
0x180061c0c  mov     r8, rbp; Buffer
0x180061c0f  mov     [rsp+58h+ulFlags], 0; ulFlags
0x180061c17  mov     rdx, rdi; pDeviceID
0x180061c1a  call    cs:__imp_CM_Get_Device_Interface_ListW
0x180061c20  xor     ebx, ebx
0x180061c22  mov     edi, 80070000h
0x180061c27  test    eax, eax
0x180061c29  jz      short loc_180061C41
0x180061c2b  lea     edx, [rbx+57h]; DefaultErr
0x180061c2e  mov     ecx, eax; CmReturnCode
0x180061c30  call    cs:__imp_CM_MapCrToWin32Err
0x180061c36  mov     ebx, eax
0x180061c38  test    eax, eax
0x180061c3a  jle     short loc_180061C41
0x180061c3c  movzx   ebx, ax
0x180061c3f  or      ebx, edi
0x180061c41  xor     esi, esi
0x180061c43  test    ebx, ebx
0x180061c45  js      short loc_180061C94
0x180061c47  mov     [rsp+58h+hTemplateFile], rsi; hTemplateFile
0x180061c4c  lea     r8d, [rsi+3]; dwShareMode
0x180061c50  mov     [rsp+58h+dwFlagsAndAttributes], 40120000h; dwFlagsAndAttributes
0x180061c58  xor     r9d, r9d; lpSecurityAttributes
0x180061c5b  mov     edx, 10000000h; dwDesiredAccess
0x180061c60  mov     [rsp+58h+ulFlags], 4; dwCreationDisposition
0x180061c68  mov     rcx, rbp; lpFileName
0x180061c6b  call    cs:__imp_CreateFileW
0x180061c71  mov     rsi, rax
0x180061c74  lea     rcx, [rax+1]
0x180061c78  test    rcx, 0FFFFFFFFFFFFFFFEh
0x180061c7f  jnz     short loc_180061C94
0x180061c81  xor     esi, esi
0x180061c83  call    cs:__imp_GetLastError
0x180061c89  mov     ebx, eax
0x180061c8b  test    eax, eax
0x180061c8d  jle     short loc_180061C94
0x180061c8f  movzx   ebx, ax
0x180061c92  or      ebx, edi
0x180061c94  call    cs:__imp_GetProcessHeap
0x180061c9a  mov     r8, rbp; lpMem
0x180061c9d  xor     edx, edx; dwFlags
0x180061c9f  mov     rcx, rax; hHeap
0x180061ca2  call    cs:__imp_HeapFree
0x180061ca8  mov     eax, ebx
0x180061caa  mov     [r14], rsi
0x180061cad  mov     rbx, [rsp+58h+arg_0]
0x180061cb2  mov     rbp, [rsp+58h+arg_10]
0x180061cb7  add     rsp, 40h
0x180061cbb  pop     r14
0x180061cbd  pop     rdi
0x180061cbe  pop     rsi
0x180061cbf  retn
```
