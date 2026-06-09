# GetRdisk0DeviceNumber(ulong *)

- ea: `0x140062210`
- end: `0x1400623d6`
- name: `?GetRdisk0DeviceNumber@@YAHPEAK@Z`
- size: `454`
- prototype: `__int64 __fastcall(unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x1400205d0`

## callees

- `0x14001f7b4`
- `0x140021ca0`
- `0x1400235a8`
- `0x140062210`
- `0x1400d257c`
- `0x1400d2c1c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400623c5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400623c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400622ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400622d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006231b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400622ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400622d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006231b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140062364`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140062364`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14006226b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14006226b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400623b1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400623b1`

## pseudocode

```c
__int64 __fastcall GetRdisk0DeviceNumber(unsigned int *a1)
{
  char *FileW; // rbx
  unsigned int v3; // ebp
  DWORD LastError; // edi
  DWORD v5; // eax
  LPVOID pv; // [rsp+70h] [rbp+8h] BYREF

  TraceFunctionEnter(L"GetRdisk0DeviceNumber");
  pv = 0;
  if ( a1 )
  {
    *a1 = -1;
    FileW = (char *)CreateFileW(
                      L"\\\\?\\GLOBALROOT\\arcname\\multi(0)disk(0)rdisk(0)",
                      0x80000000,
                      3u,
                      0,
                      3u,
                      0,
                      (HANDLE)0xFFFFFFFFFFFFFFFFLL);
    if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      if ( (unsigned int)DoDiskIoctlCall(FileW, 0x2D1080u, 0, 0, &pv, 0) )
      {
        LastError = 0;
        v3 = 1;
        *a1 = *((_DWORD *)pv + 1);
      }
      else
      {
        v3 = 0;
        LastError = GetLastError();
        if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
          && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
        {
          v5 = GetLastError();
          WPP_SF_Ds(
            *(_QWORD *)WPP_GLOBAL_Control->Gpt.DiskId.Data4,
            17,
            (unsigned int)WPP_bbfff7ea0df63369e2e67d0c2acae35a_Traceguids,
            v5,
            "DoStorageIoctlCall(hDisk, IOCTL_STORAGE_GET_DEVICE_NUMBER, NULL, 0, (void **)&pStorageDeviceNumber)");
        }
      }
LABEL_13:
      CloseHandle(FileW);
      goto LABEL_17;
    }
    v3 = 0;
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
    {
      WPP_SF_s(
        *(_QWORD *)WPP_GLOBAL_Control->Gpt.DiskId.Data4,
        16,
        WPP_bbfff7ea0df63369e2e67d0c2acae35a_Traceguids,
        "hDisk");
    }
    if ( FileW && FileW != (char *)-1LL )
      goto LABEL_13;
  }
  else
  {
    v3 = 0;
    LastError = 87;
    if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
    {
      WPP_SF_Ds(
        *(_QWORD *)WPP_GLOBAL_Control->Gpt.DiskId.Data4,
        15,
        (unsigned int)WPP_bbfff7ea0df63369e2e67d0c2acae35a_Traceguids,
        87,
        "pdwDeviceNumber");
    }
  }
LABEL_17:
  CoTaskMemFree(pv);
  TraceFunctionExit(L"GetRdisk0DeviceNumber");
  SetLastError(LastError);
  return v3;
}

```

## disassembly

```asm
0x140062210  push    rbx
0x140062212  push    rbp
0x140062213  push    rsi
0x140062214  push    rdi
0x140062215  sub     rsp, 48h
0x140062219  mov     rsi, rcx
0x14006221c  lea     rcx, aGetrdisk0devic; "GetRdisk0DeviceNumber"
0x140062223  call    ?TraceFunctionEnter@@YAXPEAG@Z; TraceFunctionEnter(ushort *)
0x140062228  mov     [rsp+68h+pv], 0
0x140062231  test    rsi, rsi
0x140062234  jz      loc_14006236C
0x14006223a  mov     [rsp+68h+hTemplateFile], 0FFFFFFFFFFFFFFFFh; hTemplateFile
0x140062243  lea     rcx, aGlobalrootArcn; "\\\\?\\GLOBALROOT\\arcname\\multi(0)dis"...
0x14006224a  mov     r8d, 3; dwShareMode
0x140062250  mov     [rsp+68h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x140062258  xor     r9d, r9d; lpSecurityAttributes
0x14006225b  mov     [rsp+68h+dwCreationDisposition], r8d; dwCreationDisposition
0x140062260  mov     edx, 80000000h; dwDesiredAccess
0x140062265  mov     dword ptr [rsi], 0FFFFFFFFh
0x14006226b  call    cs:__imp_CreateFileW
0x140062271  mov     rbx, rax
0x140062274  lea     rcx, [rax-1]
0x140062278  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x14006227c  ja      loc_140062319
0x140062282  lea     rax, [rsp+68h+pv]
0x140062287  mov     qword ptr [rsp+68h+dwFlagsAndAttributes], 0; unsigned int *
0x140062290  xor     r9d, r9d; nInBufferSize
0x140062293  mov     qword ptr [rsp+68h+dwCreationDisposition], rax; void **
0x140062298  xor     r8d, r8d; lpInBuffer
0x14006229b  mov     edx, 2D1080h; dwIoControlCode
0x1400622a0  mov     rcx, rbx; hDevice
0x1400622a3  call    ?DoDiskIoctlCall@@YAHPEAXK0KPEAPEAXPEAK@Z; DoDiskIoctlCall(void *,ulong,void *,ulong,void * *,ulong *)
0x1400622a8  test    eax, eax
0x1400622aa  jnz     short loc_140062308
0x1400622ac  xor     ebp, ebp
0x1400622ae  call    cs:__imp_GetLastError
0x1400622b4  mov     edi, eax
0x1400622b6  mov     rax, cs:WPP_GLOBAL_Control
0x1400622bd  lea     rcx, WPP_GLOBAL_Control
0x1400622c4  cmp     rax, rcx
0x1400622c7  jz      loc_140062361
0x1400622cd  test    byte ptr [rax+1Ch], 8
0x1400622d1  jz      loc_140062361
0x1400622d7  call    cs:__imp_GetLastError
0x1400622dd  lea     rcx, aDostorageioctl; "DoStorageIoctlCall(hDisk, IOCTL_STORAGE"...
0x1400622e4  mov     r9d, eax
0x1400622e7  mov     qword ptr [rsp+68h+dwCreationDisposition], rcx
0x1400622ec  lea     edx, [rbp+11h]
0x1400622ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1400622f6  lea     r8, WPP_bbfff7ea0df63369e2e67d0c2acae35a_Traceguids
0x1400622fd  mov     rcx, [rcx+10h]
0x140062301  call    WPP_SF_Ds
0x140062306  jmp     short loc_140062361
0x140062308  mov     rax, [rsp+68h+pv]
0x14006230d  xor     edi, edi
0x14006230f  mov     ecx, [rax+4]
0x140062312  lea     ebp, [rdi+1]
0x140062315  mov     [rsi], ecx
0x140062317  jmp     short loc_140062361
0x140062319  xor     ebp, ebp
0x14006231b  call    cs:__imp_GetLastError
0x140062321  mov     edi, eax
0x140062323  mov     rax, cs:WPP_GLOBAL_Control
0x14006232a  lea     rcx, WPP_GLOBAL_Control
0x140062331  cmp     rax, rcx
0x140062334  jz      short loc_140062356
0x140062336  test    byte ptr [rax+1Ch], 8
0x14006233a  jz      short loc_140062356
0x14006233c  mov     rcx, [rax+10h]
0x140062340  lea     edx, [rbp+10h]
0x140062343  lea     r9, aHdisk; "hDisk"
0x14006234a  lea     r8, WPP_bbfff7ea0df63369e2e67d0c2acae35a_Traceguids
0x140062351  call    WPP_SF_s
0x140062356  test    rbx, rbx
0x140062359  jz      short loc_1400623AC
0x14006235b  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x14006235f  jz      short loc_1400623AC
0x140062361  mov     rcx, rbx; hObject
0x140062364  call    cs:__imp_CloseHandle
0x14006236a  jmp     short loc_1400623AC
0x14006236c  xor     ebp, ebp
0x14006236e  lea     edi, [rbp+57h]
0x140062371  mov     rax, cs:WPP_GLOBAL_Control
0x140062378  lea     rcx, WPP_GLOBAL_Control
0x14006237f  cmp     rax, rcx
0x140062382  jz      short loc_1400623AC
0x140062384  test    byte ptr [rax+1Ch], 8
0x140062388  jz      short loc_1400623AC
0x14006238a  mov     rcx, [rax+10h]
0x14006238e  lea     r8, aPdwdevicenumbe; "pdwDeviceNumber"
0x140062395  mov     qword ptr [rsp+68h+dwCreationDisposition], r8
0x14006239a  lea     edx, [rbp+0Fh]
0x14006239d  lea     r8, WPP_bbfff7ea0df63369e2e67d0c2acae35a_Traceguids
0x1400623a4  mov     r9d, edi
0x1400623a7  call    WPP_SF_Ds
0x1400623ac  mov     rcx, [rsp+68h+pv]; pv
0x1400623b1  call    cs:__imp_CoTaskMemFree
0x1400623b7  lea     rcx, aGetrdisk0devic; "GetRdisk0DeviceNumber"
0x1400623be  call    ?TraceFunctionExit@@YAXPEAG@Z; TraceFunctionExit(ushort *)
0x1400623c3  mov     ecx, edi; dwErrCode
0x1400623c5  call    cs:__imp_SetLastError
0x1400623cb  mov     eax, ebp
0x1400623cd  add     rsp, 48h
0x1400623d1  pop     rdi
0x1400623d2  pop     rsi
0x1400623d3  pop     rbp
0x1400623d4  pop     rbx
0x1400623d5  retn
```
