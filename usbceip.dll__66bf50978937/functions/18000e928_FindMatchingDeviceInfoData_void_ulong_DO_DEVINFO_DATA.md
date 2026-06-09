# FindMatchingDeviceInfoData(void *,ulong,_DO_DEVINFO_DATA *)

- ea: `0x18000e928`
- end: `0x18000ec10`
- name: `?FindMatchingDeviceInfoData@@YAKPEAXKPEAU_DO_DEVINFO_DATA@@@Z`
- size: `744`
- prototype: `__int64 __fastcall(void *, int, struct _DO_DEVINFO_DATA *)`
- caller_count: `4`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x18000efd4`
- `0x18000f180`
- `0x18000f74c`
- `0x18000f9ec`

## callees

- `0x180002410`
- `0x180002e4a`
- `0x180002e56`
- `0x18000e928`
- `0x18000f32c`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ea67`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ebe1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ea67`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ebe1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ea20`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ea2b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000eb49`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000eb71`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000eb99`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ea20`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ea2b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000eb49`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000eb71`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000eb99`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000ea93`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000ea93`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18000ead7`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18000ead7`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x18000e9ba`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x18000e9ba`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x18000ea16`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x18000ea16`

## pseudocode

```c
__int64 __fastcall FindMatchingDeviceInfoData(void *a1, int a2, struct _DO_DEVINFO_DATA *a3)
{
  size_t v3; // rbx
  __int64 FileW; // rsi
  unsigned int v5; // r15d
  WCHAR *v9; // rdi
  __int64 v10; // r8
  DWORD LastError; // ebx
  __int64 v12; // r8
  _QWORD *v13; // rcx
  __int64 v14; // rdx
  __int128 v15; // xmm1
  __int128 v16; // xmm0
  size_t Size; // [rsp+40h] [rbp-49h] BYREF
  __int64 OutBuffer; // [rsp+48h] [rbp-41h] BYREF
  int v20; // [rsp+50h] [rbp-39h]
  __int128 v21; // [rsp+58h] [rbp-31h] BYREF
  __int128 v22; // [rsp+68h] [rbp-21h]
  __int128 v23; // [rsp+78h] [rbp-11h]
  _OWORD v24[2]; // [rsp+88h] [rbp-1h] BYREF

  Size = 8;
  LODWORD(v3) = 0;
  OutBuffer = 0;
  FileW = -1;
  v20 = 0;
  v5 = 0;
  v21 = 0;
  LODWORD(v21) = 48;
  memset(v24, 0, sizeof(v24));
  LODWORD(v24[0]) = 32;
  v22 = 0;
  v9 = 0;
  v23 = 0;
  while ( 2 )
  {
    if ( (unsigned int)DevObjEnumDeviceInterfaces(a1, 0, &GUID_DEVINTERFACE_DISK, v5, v24) )
    {
      while ( 1 )
      {
        if ( (_DWORD)Size != (_DWORD)v3 )
        {
          v3 = (unsigned int)Size;
          if ( v9 )
            free(v9);
          v9 = (WCHAR *)o_malloc_0(v3);
          if ( !v9 )
          {
            LastError = 14;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, v10, 14);
            goto LABEL_34;
          }
        }
        *(_DWORD *)v9 = 8;
        if ( (unsigned int)DevObjGetDeviceInterfaceDetail(a1, v24, v9, (unsigned int)v3, &Size, &v21) )
          break;
        if ( GetLastError() != 122 )
        {
          LastError = GetLastError();
          v13 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v14 = 15;
            goto LABEL_31;
          }
          goto LABEL_32;
        }
      }
      if ( FileW != -1 )
        CloseHandle((HANDLE)FileW);
      FileW = (__int64)CreateFileW(v9 + 2, 0, 3u, 0, 3u, 0, 0);
      if ( FileW == -1 )
      {
        LastError = GetLastError();
        v13 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v14 = 16;
          goto LABEL_31;
        }
      }
      else if ( DeviceIoControl((HANDLE)FileW, 0x2D1080u, 0, 0, &OutBuffer, 0xCu, (LPDWORD)&Size + 1, 0) )
      {
        if ( HIDWORD(OutBuffer) != a2 )
        {
          ++v5;
          continue;
        }
        LastError = 0;
        v15 = v22;
        *(_OWORD *)a3 = v21;
        v16 = v23;
        *((_OWORD *)a3 + 1) = v15;
        *((_OWORD *)a3 + 2) = v16;
      }
      else
      {
        LastError = GetLastError();
        v13 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v14 = 17;
          goto LABEL_31;
        }
      }
    }
    else
    {
      LastError = GetLastError();
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v14 = 13;
LABEL_31:
        WPP_SF_D(v13[2], v14, v12, LastError);
      }
    }
    break;
  }
LABEL_32:
  if ( v9 )
    free(v9);
LABEL_34:
  if ( FileW != -1 )
    CloseHandle((HANDLE)FileW);
  return LastError;
}

```

## disassembly

```asm
0x18000e928  mov     [rsp-8+arg_8], rbx
0x18000e92d  push    rbp
0x18000e92e  push    rsi
0x18000e92f  push    rdi
0x18000e930  push    r12
0x18000e932  push    r13
0x18000e934  push    r14
0x18000e936  push    r15
0x18000e938  lea     rbp, [rsp-27h]
0x18000e93d  sub     rsp, 0B0h
0x18000e944  mov     rax, cs:__security_cookie
0x18000e94b  xor     rax, rsp
0x18000e94e  mov     [rbp+57h+var_38], rax
0x18000e952  xorps   xmm0, xmm0
0x18000e955  mov     dword ptr [rbp+57h+Size+4], 0
0x18000e95c  xor     eax, eax
0x18000e95e  mov     dword ptr [rbp+57h+Size], 8
0x18000e965  xor     ebx, ebx
0x18000e967  mov     [rbp+57h+OutBuffer], rax
0x18000e96b  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18000e96f  mov     [rbp+57h+var_90], eax
0x18000e972  xor     r15d, r15d
0x18000e975  mov     r14, r8
0x18000e978  movups  [rbp+57h+var_88], xmm0
0x18000e97c  mov     dword ptr [rbp+57h+var_88], 30h ; '0'
0x18000e983  mov     r13d, edx
0x18000e986  movups  [rbp+57h+var_58], xmm0
0x18000e98a  mov     dword ptr [rbp+57h+var_58], 20h ; ' '
0x18000e991  mov     r12, rcx
0x18000e994  movups  [rbp+57h+var_78], xmm0
0x18000e998  xor     edi, edi
0x18000e99a  movups  [rbp+57h+var_68], xmm0
0x18000e99e  movups  [rbp+57h+var_48], xmm0
0x18000e9a2  lea     rax, [rbp+57h+var_58]
0x18000e9a6  mov     r9d, r15d
0x18000e9a9  lea     r8, GUID_DEVINTERFACE_DISK
0x18000e9b0  mov     qword ptr [rsp+0E0h+dwCreationDisposition], rax
0x18000e9b5  xor     edx, edx
0x18000e9b7  mov     rcx, r12
0x18000e9ba  call    cs:__imp_DevObjEnumDeviceInterfaces
0x18000e9c0  test    eax, eax
0x18000e9c2  jz      loc_18000EB99
0x18000e9c8  cmp     dword ptr [rbp+57h+Size], ebx
0x18000e9cb  jz      short loc_18000E9F1
0x18000e9cd  mov     ebx, dword ptr [rbp+57h+Size]
0x18000e9d0  test    rdi, rdi
0x18000e9d3  jz      short loc_18000E9DD
0x18000e9d5  mov     rcx, rdi; Block
0x18000e9d8  call    free
0x18000e9dd  mov     rcx, rbx; Size
0x18000e9e0  call    _o_malloc_0
0x18000e9e5  mov     rdi, rax
0x18000e9e8  test    rax, rax
0x18000e9eb  jz      loc_18000EAEF
0x18000e9f1  lea     rax, [rbp+57h+var_88]
0x18000e9f5  mov     dword ptr [rdi], 8
0x18000e9fb  mov     qword ptr [rsp+0E0h+dwFlagsAndAttributes], rax
0x18000ea00  lea     rdx, [rbp+57h+var_58]
0x18000ea04  lea     rax, [rbp+57h+Size]
0x18000ea08  mov     r9d, ebx
0x18000ea0b  mov     r8, rdi
0x18000ea0e  mov     qword ptr [rsp+0E0h+dwCreationDisposition], rax
0x18000ea13  mov     rcx, r12
0x18000ea16  call    cs:__imp_DevObjGetDeviceInterfaceDetail
0x18000ea1c  test    eax, eax
0x18000ea1e  jnz     short loc_18000EA5E
0x18000ea20  call    cs:__imp_GetLastError
0x18000ea26  cmp     eax, 7Ah ; 'z'
0x18000ea29  jz      short loc_18000E9C8
0x18000ea2b  call    cs:__imp_GetLastError
0x18000ea31  mov     ebx, eax
0x18000ea33  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ea3a  lea     rax, WPP_GLOBAL_Control
0x18000ea41  cmp     rcx, rax
0x18000ea44  jz      loc_18000EBCB
0x18000ea4a  test    byte ptr [rcx+1Ch], 1
0x18000ea4e  jz      loc_18000EBCB
0x18000ea54  mov     edx, 0Fh
0x18000ea59  jmp     loc_18000EBBF
0x18000ea5e  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x18000ea62  jz      short loc_18000EA6D
0x18000ea64  mov     rcx, rsi; hObject
0x18000ea67  call    cs:__imp_CloseHandle
0x18000ea6d  mov     eax, 3
0x18000ea72  mov     [rsp+0E0h+hTemplateFile], 0; hTemplateFile
0x18000ea7b  mov     r8d, eax; dwShareMode
0x18000ea7e  mov     [rsp+0E0h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x18000ea86  lea     rcx, [rdi+4]; lpFileName
0x18000ea8a  mov     [rsp+0E0h+dwCreationDisposition], eax; dwCreationDisposition
0x18000ea8e  xor     r9d, r9d; lpSecurityAttributes
0x18000ea91  xor     edx, edx; dwDesiredAccess
0x18000ea93  call    cs:__imp_CreateFileW
0x18000ea99  mov     rsi, rax
0x18000ea9c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000eaa0  jz      loc_18000EB71
0x18000eaa6  mov     [rsp+0E0h+lpOverlapped], 0; lpOverlapped
0x18000eaaf  lea     rax, [rbp+57h+Size+4]
0x18000eab3  mov     [rsp+0E0h+hTemplateFile], rax; lpBytesReturned
0x18000eab8  xor     r9d, r9d; nInBufferSize
0x18000eabb  lea     rax, [rbp+57h+OutBuffer]
0x18000eabf  mov     [rsp+0E0h+dwFlagsAndAttributes], 0Ch; nOutBufferSize
0x18000eac7  xor     r8d, r8d; lpInBuffer
0x18000eaca  mov     qword ptr [rsp+0E0h+dwCreationDisposition], rax; lpOutBuffer
0x18000eacf  mov     edx, 2D1080h; dwIoControlCode
0x18000ead4  mov     rcx, rsi; hDevice
0x18000ead7  call    cs:__imp_DeviceIoControl
0x18000eadd  test    eax, eax
0x18000eadf  jz      short loc_18000EB49
0x18000eae1  cmp     dword ptr [rbp+57h+OutBuffer+4], r13d
0x18000eae5  jz      short loc_18000EB28
0x18000eae7  inc     r15d
0x18000eaea  jmp     loc_18000E9A2
0x18000eaef  mov     ebx, 0Eh
0x18000eaf4  mov     rcx, cs:WPP_GLOBAL_Control
0x18000eafb  lea     rax, WPP_GLOBAL_Control
0x18000eb02  cmp     rcx, rax
0x18000eb05  jz      loc_18000EBD8
0x18000eb0b  test    byte ptr [rcx+1Ch], 1
0x18000eb0f  jz      loc_18000EBD8
0x18000eb15  mov     rcx, [rcx+10h]
0x18000eb19  mov     edx, ebx
0x18000eb1b  mov     r9d, ebx
0x18000eb1e  call    WPP_SF_D
0x18000eb23  jmp     loc_18000EBD8
0x18000eb28  movups  xmm0, [rbp+57h+var_88]
0x18000eb2c  xor     ebx, ebx
0x18000eb2e  movups  xmm1, [rbp+57h+var_78]
0x18000eb32  movups  xmmword ptr [r14], xmm0
0x18000eb36  movups  xmm0, [rbp+57h+var_68]
0x18000eb3a  movups  xmmword ptr [r14+10h], xmm1
0x18000eb3f  movups  xmmword ptr [r14+20h], xmm0
0x18000eb44  jmp     loc_18000EBCB
0x18000eb49  call    cs:__imp_GetLastError
0x18000eb4f  mov     ebx, eax
0x18000eb51  mov     rcx, cs:WPP_GLOBAL_Control
0x18000eb58  lea     rax, WPP_GLOBAL_Control
0x18000eb5f  cmp     rcx, rax
0x18000eb62  jz      short loc_18000EBCB
0x18000eb64  test    byte ptr [rcx+1Ch], 1
0x18000eb68  jz      short loc_18000EBCB
0x18000eb6a  mov     edx, 11h
0x18000eb6f  jmp     short loc_18000EBBF
0x18000eb71  call    cs:__imp_GetLastError
0x18000eb77  mov     ebx, eax
0x18000eb79  mov     rcx, cs:WPP_GLOBAL_Control
0x18000eb80  lea     rax, WPP_GLOBAL_Control
0x18000eb87  cmp     rcx, rax
0x18000eb8a  jz      short loc_18000EBCB
0x18000eb8c  test    byte ptr [rcx+1Ch], 1
0x18000eb90  jz      short loc_18000EBCB
0x18000eb92  mov     edx, 10h
0x18000eb97  jmp     short loc_18000EBBF
0x18000eb99  call    cs:__imp_GetLastError
0x18000eb9f  mov     ebx, eax
0x18000eba1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000eba8  lea     rax, WPP_GLOBAL_Control
0x18000ebaf  cmp     rcx, rax
0x18000ebb2  jz      short loc_18000EBCB
0x18000ebb4  test    byte ptr [rcx+1Ch], 1
0x18000ebb8  jz      short loc_18000EBCB
0x18000ebba  mov     edx, 0Dh
0x18000ebbf  mov     rcx, [rcx+10h]
0x18000ebc3  mov     r9d, ebx
0x18000ebc6  call    WPP_SF_D
0x18000ebcb  test    rdi, rdi
0x18000ebce  jz      short loc_18000EBD8
0x18000ebd0  mov     rcx, rdi; Block
0x18000ebd3  call    free
0x18000ebd8  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x18000ebdc  jz      short loc_18000EBE7
0x18000ebde  mov     rcx, rsi; hObject
0x18000ebe1  call    cs:__imp_CloseHandle
0x18000ebe7  mov     eax, ebx
0x18000ebe9  mov     rcx, [rbp+57h+var_38]
0x18000ebed  xor     rcx, rsp; StackCookie
0x18000ebf0  call    __security_check_cookie
0x18000ebf5  mov     rbx, [rsp+0E0h+arg_8]
0x18000ebfd  add     rsp, 0B0h
0x18000ec04  pop     r15
0x18000ec06  pop     r14
0x18000ec08  pop     r13
0x18000ec0a  pop     r12
0x18000ec0c  pop     rdi
0x18000ec0d  pop     rsi
0x18000ec0e  pop     rbp
0x18000ec0f  retn
```
