# ResolveDiskNumber::GetDiskNumberFromGUID(_GUID)

- ea: `0x1800708a4`
- end: `0x1800709eb`
- name: `?GetDiskNumberFromGUID@ResolveDiskNumber@@SAHU_GUID@@@Z`
- size: `327`
- prototype: `__int64 __fastcall(struct _GUID *Buf2)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, registry_config`

## callers

- `0x18006fd7c`

## callees

- `0x18000d030`
- `0x18000dd8c`
- `0x180019d4c`
- `0x18001c130`
- `0x1800343b4`
- `0x180057218`
- `0x1800701c0`
- `0x180070704`
- `0x1800708a4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180070965`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180070965`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18007095b`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18007095b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180070906`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180070906`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ResolveDiskNumber::GetDiskNumberFromGUID(struct _GUID *Buf2)
{
  __int64 i; // rdi
  const WCHAR *v3; // rax
  HANDLE FileW; // rax
  DWORD LastError; // ebx
  __int64 v6; // rax
  unsigned int v7; // ebx
  DWORD BytesReturned; // [rsp+40h] [rbp-49h] BYREF
  HANDLE v10; // [rsp+48h] [rbp-41h] BYREF
  _QWORD v11[4]; // [rsp+50h] [rbp-39h] BYREF
  _BYTE v12[32]; // [rsp+70h] [rbp-19h] BYREF
  __int128 OutBuffer; // [rsp+90h] [rbp+7h] BYREF
  __int128 Buf1; // [rsp+A0h] [rbp+17h] BYREF
  __int64 v15; // [rsp+B0h] [rbp+27h]

  ResolveDiskNumber::GetAllDeviceInterfaces(v11);
  for ( i = v11[0]; ; i += 32 )
  {
    if ( i == v11[1] )
    {
      v7 = -1;
      goto LABEL_9;
    }
    v3 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(i);
    FileW = CreateFileW(v3, 0, 3u, 0, 3u, 0, 0);
    v10 = FileW;
    if ( FileW != (HANDLE)-1LL )
    {
      OutBuffer = 0;
      Buf1 = 0;
      v15 = 0;
      BytesReturned = 0;
      if ( !DeviceIoControl(FileW, 0x2D1084u, 0, 0, &OutBuffer, 0x28u, &BytesReturned, 0) )
      {
        LastError = GetLastError();
        v6 = std::string::string(v12, "Failed to send I/O request to get disk number");
        StorageHealthMonitorTelemetry::TraceLoggingWriteEventWithOneParam(v6, LastError);
        goto LABEL_6;
      }
      if ( !memcmp_0((char *)&Buf1 + 4, Buf2, 0x10u) )
        break;
    }
LABEL_6:
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v10);
  }
  v7 = Buf1;
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v10);
LABEL_9:
  std::vector<std::wstring>::_Tidy(v11);
  return v7;
}

```

## disassembly

```asm
0x1800708a4  push    rbp
0x1800708a6  push    rbx
0x1800708a7  push    rsi
0x1800708a8  push    rdi
0x1800708a9  lea     rbp, [rsp-3Fh]
0x1800708ae  sub     rsp, 0C8h
0x1800708b5  mov     rax, cs:__security_cookie
0x1800708bc  xor     rax, rsp
0x1800708bf  mov     [rbp+57h+var_28], rax
0x1800708c3  mov     rsi, rcx
0x1800708c6  lea     rcx, [rbp+57h+var_90]
0x1800708ca  call    ?GetAllDeviceInterfaces@ResolveDiskNumber@@SA?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@PEAU_GUID@@@Z; ResolveDiskNumber::GetAllDeviceInterfaces(_GUID *)
0x1800708cf  nop
0x1800708d0  mov     rdi, [rbp+57h+var_90]
0x1800708d4  jmp     loc_1800709AC
0x1800708d9  mov     rcx, rdi
0x1800708dc  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800708e1  mov     [rsp+0E0h+hTemplateFile], 0; hTemplateFile
0x1800708ea  mov     [rsp+0E0h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x1800708f2  mov     [rsp+0E0h+dwCreationDisposition], 3; dwCreationDisposition
0x1800708fa  xor     r9d, r9d; lpSecurityAttributes
0x1800708fd  xor     edx, edx; dwDesiredAccess
0x1800708ff  lea     r8d, [r9+3]; dwShareMode
0x180070903  mov     rcx, rax; lpFileName
0x180070906  call    cs:__imp_CreateFileW
0x18007090c  mov     [rbp+57h+var_98], rax
0x180070910  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180070914  jz      loc_18007099F
0x18007091a  xorps   xmm0, xmm0
0x18007091d  xor     ecx, ecx
0x18007091f  movups  [rbp+57h+OutBuffer], xmm0
0x180070923  movups  [rbp+57h+Buf1], xmm0
0x180070927  mov     [rbp+57h+var_30], rcx
0x18007092b  mov     [rbp+57h+BytesReturned], ecx
0x18007092e  mov     [rsp+0E0h+lpOverlapped], rcx; lpOverlapped
0x180070933  lea     rcx, [rbp+57h+BytesReturned]
0x180070937  mov     [rsp+0E0h+hTemplateFile], rcx; lpBytesReturned
0x18007093c  mov     [rsp+0E0h+dwFlagsAndAttributes], 28h ; '('; nOutBufferSize
0x180070944  lea     rcx, [rbp+57h+OutBuffer]
0x180070948  mov     qword ptr [rsp+0E0h+dwCreationDisposition], rcx; lpOutBuffer
0x18007094d  xor     r9d, r9d; nInBufferSize
0x180070950  xor     r8d, r8d; lpInBuffer
0x180070953  mov     edx, 2D1084h; dwIoControlCode
0x180070958  mov     rcx, rax; hDevice
0x18007095b  call    cs:__imp_DeviceIoControl
0x180070961  test    eax, eax
0x180070963  jnz     short loc_180070989
0x180070965  call    cs:__imp_GetLastError
0x18007096b  mov     ebx, eax
0x18007096d  lea     rdx, aFailedToSendIO; "Failed to send I/O request to get disk "...
0x180070974  lea     rcx, [rbp+57h+var_70]
0x180070978  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18007097d  mov     edx, ebx
0x18007097f  mov     rcx, rax
0x180070982  call    ?TraceLoggingWriteEventWithOneParam@StorageHealthMonitorTelemetry@@SAXV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@K@Z; StorageHealthMonitorTelemetry::TraceLoggingWriteEventWithOneParam(std::string,ulong)
0x180070987  jmp     short loc_18007099F
0x180070989  mov     r8d, 10h; Size
0x18007098f  mov     rdx, rsi; Buf2
0x180070992  lea     rcx, [rbp+57h+Buf1+4]; Buf1
0x180070996  call    memcmp_0
0x18007099b  test    eax, eax
0x18007099d  jz      short loc_1800709DC
0x18007099f  lea     rcx, [rbp+57h+var_98]
0x1800709a3  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800709a8  add     rdi, 20h ; ' '
0x1800709ac  cmp     rdi, [rbp+57h+var_88]
0x1800709b0  jnz     loc_1800708D9
0x1800709b6  or      ebx, 0FFFFFFFFh
0x1800709b9  lea     rcx, [rbp+57h+var_90]
0x1800709bd  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1800709c2  mov     eax, ebx
0x1800709c4  mov     rcx, [rbp+57h+var_28]
0x1800709c8  xor     rcx, rsp; StackCookie
0x1800709cb  call    __security_check_cookie
0x1800709d0  add     rsp, 0C8h
0x1800709d7  pop     rdi
0x1800709d8  pop     rsi
0x1800709d9  pop     rbx
0x1800709da  pop     rbp
0x1800709db  retn
0x1800709dc  mov     ebx, dword ptr [rbp+57h+Buf1]
0x1800709df  lea     rcx, [rbp+57h+var_98]
0x1800709e3  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800709e8  jmp     short loc_1800709B9
```
