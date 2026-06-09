# GetVolumeNameFromNtVolumeName

- ea: `0x180009934`
- end: `0x180009b81`
- name: `GetVolumeNameFromNtVolumeName`
- size: `589`
- prototype: `HRESULT __fastcall(void *Src, size_t Size, WCHAR *)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, reparse_path, broker_com_uri`

## callers

- `0x180001010`
- `0x180001a40`

## callees

- `0x180005730`
- `0x180005770`
- `0x180009934`
- `0x18000ba11`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x180009ab2`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x180009ab2`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180009a8d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180009a8d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009ad3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009ae4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009ad3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009ae4`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x180009987`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x1800099a9`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x1800099cb`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x180009987`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x1800099a9`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x1800099cb`
- `FLTLIB!FilterGetDosName` at `0x180009b25`
- `FLTLIB!FilterGetDosName` at `0x180009b25`

## pseudocode

```c
HRESULT __fastcall GetVolumeNameFromNtVolumeName(void *Src, size_t Size, WCHAR *a3)
{
  size_t v3; // rbx
  HRESULT result; // eax
  size_t v7; // r12
  size_t v8; // r14
  unsigned __int64 v9; // rax
  HANDLE FileW; // rax
  void *v11; // r15
  DWORD FinalPathNameByHandleW; // eax
  __int64 v13; // rcx
  wchar_t FileName[14]; // [rsp+40h] [rbp-C0h] BYREF
  _WORD v15[250]; // [rsp+5Ch] [rbp-A4h] BYREF

  v3 = (unsigned int)Size;
  result = Size - 1;
  if ( (unsigned int)(Size - 1) > 0x1E8 )
  {
    *a3 = 0;
    return result;
  }
  if ( RtlCompareMemory(Src, L"\\Device\\Harddisk", 0x20u) == 32
    || RtlCompareMemory(Src, L"\\Device\\CdRom", 0x1Au) == 26
    || RtlCompareMemory(Src, L"\\Device\\CSVVolume", 0x22u) == 34 )
  {
    v7 = v3;
    wmemcpy(FileName, L"\\\\?\\OBALROOT", 12);
    memcpy_0(v15, Src, v3);
    v8 = v3 >> 1;
    v15[v8] = 92;
    v9 = v8 * 2 + 30;
  }
  else
  {
    v7 = (unsigned int)v3;
    memcpy_0(FileName, Src, (unsigned int)v3);
    v8 = (unsigned __int64)(unsigned int)v3 >> 1;
    FileName[v8] = 92;
    v9 = v8 * 2 + 2;
  }
  if ( v9 >= 0x208 )
    goto LABEL_17;
  *(wchar_t *)((char *)FileName + v9) = 0;
  FileW = CreateFileW(FileName, 0x100080u, 7u, 0, 3u, 0x2000000u, 0);
  v11 = FileW;
  if ( FileW != (HANDLE)-1LL )
  {
    FinalPathNameByHandleW = GetFinalPathNameByHandleW(FileW, a3, 0x104u, 1u);
    if ( FinalPathNameByHandleW )
    {
      v13 = FinalPathNameByHandleW - 1;
      if ( a3[v13] == 92 )
        a3[v13] = 0;
      return CloseHandle(v11);
    }
    CloseHandle(v11);
  }
  memcpy_0(FileName, Src, v7);
  FileName[v8] = 92;
  if ( v8 * 2 + 2 >= 0x208 )
LABEL_17:
    _report_rangecheckfailure();
  FileName[v8 + 1] = 0;
  result = FilterGetDosName(FileName, a3, 0x104u);
  if ( result )
  {
    result = (unsigned int)memcpy_0(a3, Src, v7);
    a3[v8] = 0;
  }
  return result;
}

```

## disassembly

```asm
0x180009934  mov     [rsp-8+arg_18], rbx
0x180009939  push    rbp
0x18000993a  push    rsi
0x18000993b  push    rdi
0x18000993c  push    r12
0x18000993e  push    r13
0x180009940  push    r14
0x180009942  push    r15
0x180009944  lea     rbp, [rsp-160h]
0x18000994c  sub     rsp, 260h
0x180009953  mov     rax, cs:__security_cookie
0x18000995a  xor     rax, rsp
0x18000995d  mov     [rbp+190h+var_40], rax
0x180009964  mov     ebx, edx
0x180009966  mov     rdi, r8
0x180009969  mov     rsi, rcx
0x18000996c  lea     eax, [rbx-1]
0x18000996f  cmp     eax, 1E8h
0x180009974  ja      loc_180009B50
0x18000997a  mov     r8d, 20h ; ' '; Length
0x180009980  lea     rdx, aDeviceHarddisk; "\\Device\\Harddisk"
0x180009987  call    cs:__imp_RtlCompareMemory
0x18000998e  nop     dword ptr [rax+rax+00h]
0x180009993  cmp     rax, 20h ; ' '
0x180009997  jz      short loc_180009A0B
0x180009999  mov     r8d, 1Ah; Length
0x18000999f  lea     rdx, aDeviceCdrom; "\\Device\\CdRom"
0x1800099a6  mov     rcx, rsi; Source1
0x1800099a9  call    cs:__imp_RtlCompareMemory
0x1800099b0  nop     dword ptr [rax+rax+00h]
0x1800099b5  cmp     rax, 1Ah
0x1800099b9  jz      short loc_180009A0B
0x1800099bb  mov     r8d, 22h ; '"'; Length
0x1800099c1  lea     rdx, aDeviceCsvvolum; "\\Device\\CSVVolume"
0x1800099c8  mov     rcx, rsi; Source1
0x1800099cb  call    cs:__imp_RtlCompareMemory
0x1800099d2  nop     dword ptr [rax+rax+00h]
0x1800099d7  cmp     rax, 22h ; '"'
0x1800099db  jz      short loc_180009A0B
0x1800099dd  mov     r8d, ebx; Size
0x1800099e0  lea     rcx, [rsp+290h+FileName]; void *
0x1800099e5  mov     rdx, rsi; Src
0x1800099e8  mov     r12d, ebx
0x1800099eb  call    memcpy_0
0x1800099f0  mov     eax, ebx
0x1800099f2  mov     r13d, 5Ch ; '\'
0x1800099f8  shr     rax, 1
0x1800099fb  lea     r14, [rax+rax]
0x1800099ff  mov     [rsp+r14+290h+FileName], r13w
0x180009a05  lea     rax, [r14+2]
0x180009a09  jmp     short loc_180009A54
0x180009a0b  movups  xmm0, xmmword ptr cs:aGlobalroot; "\\\\?\\GLOBALROOT"
0x180009a12  mov     r8, rbx; Size
0x180009a15  mov     rdx, rsi; Src
0x180009a18  movups  xmm1, xmmword ptr cs:aGlobalroot+0Ch; "OBALROOT"
0x180009a1f  lea     rcx, [rsp+290h+var_234]; void *
0x180009a24  mov     r12, rbx
0x180009a27  movaps  xmmword ptr [rsp+290h+FileName], xmm0
0x180009a2c  movups  xmmword ptr [rsp+290h+FileName+0Ch], xmm1
0x180009a31  call    memcpy_0
0x180009a36  mov     rax, rbx
0x180009a39  mov     r13d, 5Ch ; '\'
0x180009a3f  shr     rax, 1
0x180009a42  lea     r14, [rax+rax]
0x180009a46  mov     [rsp+r14+290h+var_234], r13w
0x180009a4c  lea     rax, ds:1Eh[rax*2]
0x180009a54  cmp     rax, 208h
0x180009a5a  jnb     loc_180009B4A
0x180009a60  xor     ebx, ebx
0x180009a62  lea     rcx, [rsp+290h+FileName]; lpFileName
0x180009a67  mov     [rsp+290h+hTemplateFile], rbx; hTemplateFile
0x180009a6c  xor     r9d, r9d; lpSecurityAttributes
0x180009a6f  mov     [rsp+290h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x180009a77  mov     edx, 100080h; dwDesiredAccess
0x180009a7c  mov     [rsp+rax+290h+FileName], bx
0x180009a81  lea     r8d, [rbx+7]; dwShareMode
0x180009a85  mov     [rsp+290h+dwCreationDisposition], 3; dwCreationDisposition
0x180009a8d  call    cs:__imp_CreateFileW
0x180009a94  nop     dword ptr [rax+rax+00h]
0x180009a99  mov     r15, rax
0x180009a9c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180009aa0  jz      short loc_180009AF0
0x180009aa2  lea     r9d, [rbx+1]; dwFlags
0x180009aa6  mov     r8d, 104h; cchFilePath
0x180009aac  mov     rdx, rdi; lpszFilePath
0x180009aaf  mov     rcx, rax; hFile
0x180009ab2  call    cs:__imp_GetFinalPathNameByHandleW
0x180009ab9  nop     dword ptr [rax+rax+00h]
0x180009abe  test    eax, eax
0x180009ac0  jz      short loc_180009AE1
0x180009ac2  lea     ecx, [rax-1]
0x180009ac5  cmp     [rdi+rcx*2], r13w
0x180009aca  jnz     short loc_180009AD0
0x180009acc  mov     [rdi+rcx*2], bx
0x180009ad0  mov     rcx, r15; hObject
0x180009ad3  call    cs:__imp_CloseHandle
0x180009ada  nop     dword ptr [rax+rax+00h]
0x180009adf  jmp     short loc_180009B56
0x180009ae1  mov     rcx, r15; hObject
0x180009ae4  call    cs:__imp_CloseHandle
0x180009aeb  nop     dword ptr [rax+rax+00h]
0x180009af0  mov     r8, r12; Size
0x180009af3  lea     rcx, [rsp+290h+FileName]; void *
0x180009af8  mov     rdx, rsi; Src
0x180009afb  call    memcpy_0
0x180009b00  lea     rax, [r14+2]
0x180009b04  mov     [rsp+r14+290h+FileName], r13w
0x180009b0a  cmp     rax, 208h
0x180009b10  jnb     short loc_180009B4A
0x180009b12  mov     r8d, 104h; dwDosNameBufferSize
0x180009b18  mov     [rsp+rax+290h+FileName], bx
0x180009b1d  mov     rdx, rdi; lpDosName
0x180009b20  lea     rcx, [rsp+290h+FileName]; lpVolumeName
0x180009b25  call    cs:__imp_FilterGetDosName
0x180009b2c  nop     dword ptr [rax+rax+00h]
0x180009b31  test    eax, eax
0x180009b33  jz      short loc_180009B56
0x180009b35  mov     r8, r12; Size
0x180009b38  mov     rdx, rsi; Src
0x180009b3b  mov     rcx, rdi; void *
0x180009b3e  call    memcpy_0
0x180009b43  mov     [r14+rdi], bx
0x180009b48  jmp     short loc_180009B56
0x180009b4a  call    __report_rangecheckfailure
0x180009b50  xor     ebx, ebx
0x180009b52  mov     [r8], bx
0x180009b56  mov     rcx, [rbp+190h+var_40]
0x180009b5d  xor     rcx, rsp; StackCookie
0x180009b60  call    __security_check_cookie
0x180009b65  mov     rbx, [rsp+290h+arg_18]
0x180009b6d  add     rsp, 260h
0x180009b74  pop     r15
0x180009b76  pop     r14
0x180009b78  pop     r13
0x180009b7a  pop     r12
0x180009b7c  pop     rdi
0x180009b7d  pop     rsi
0x180009b7e  pop     rbp
0x180009b7f  retn
```
