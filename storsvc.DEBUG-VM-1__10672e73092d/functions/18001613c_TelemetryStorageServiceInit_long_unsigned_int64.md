# TelemetryStorageServiceInit(long,unsigned __int64)

- ea: `0x18001613c`
- end: `0x18001638b`
- name: `?TelemetryStorageServiceInit@@YAXJ_K@Z`
- size: `591`
- prototype: `void __fastcall(int, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `reparse_path, service_task`

## callers

- `0x180025420`

## callees

- `0x180001010`
- `0x180001148`
- `0x18000d030`
- `0x18000d450`
- `0x18000ddb0`
- `0x18001613c`
- `0x18001b7d4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18001626b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18001626b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800162bf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800162fa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800162bf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800162fa`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800162b6`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800162f1`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800162b6`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800162f1`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x1800161cd`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x180016222`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x1800161cd`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x180016222`

## pseudocode

```c
void __fastcall TelemetryStorageServiceInit(int a1, __int64 a2)
{
  __int64 v4; // rdi
  __int64 v5; // rax
  unsigned __int64 v6; // rcx
  __int64 v7; // rbx
  __int64 v8; // rcx
  unsigned __int64 v9; // rcx
  int v10; // ecx
  int v11; // r8d
  int v12; // r9d
  int v13; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v14; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v15; // [rsp+50h] [rbp-B0h] BYREF
  int OutBuffer; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v17; // [rsp+5Ch] [rbp-A4h]
  int v18; // [rsp+64h] [rbp-9Ch]
  int lpOutBuffer; // [rsp+68h] [rbp-98h] BYREF
  __int64 v20; // [rsp+6Ch] [rbp-94h]
  int v21; // [rsp+74h] [rbp-8Ch]
  WCHAR szVolumeName[264]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR v23[264]; // [rsp+290h] [rbp+190h] BYREF

  memset_0(szVolumeName, 0, 0x208u);
  memset_0(v23, 0, 0x208u);
  v17 = 0;
  v18 = 0;
  v20 = 0;
  v21 = 0;
  v4 = -1;
  OutBuffer = 0;
  lpOutBuffer = 0;
  if ( GetVolumeNameForVolumeMountPointW(L"C:\\", szVolumeName, 0x104u) )
  {
    v5 = -1;
    do
      ++v5;
    while ( szVolumeName[v5] );
    v6 = 2 * v5 - 2;
    if ( v6 >= 0x208 )
      goto LABEL_20;
    *(WCHAR *)((char *)szVolumeName + v6) = 0;
    v4 = (__int64)OpenVolumeHandle(szVolumeName);
  }
  v7 = -1;
  if ( !GetVolumeNameForVolumeMountPointW(L"C:\\Data\\", v23, 0x104u) )
    goto LABEL_12;
  v8 = -1;
  do
    ++v8;
  while ( v23[v8] );
  v9 = 2 * v8 - 2;
  if ( v9 >= 0x208 )
LABEL_20:
    _report_rangecheckfailure();
  *(WCHAR *)((char *)v23 + v9) = 0;
  if ( (unsigned int)_o__wcsnicmp(szVolumeName, v23, 260) )
    v7 = (__int64)OpenVolumeHandle(v23);
LABEL_12:
  if ( v4 != -1 )
  {
    DeviceIoControl((HANDLE)v4, 0x4D0018u, 0, 0, &OutBuffer, 0x10u, 0, 0);
    CloseHandle((HANDLE)v4);
  }
  if ( v7 != -1 )
  {
    DeviceIoControl((HANDLE)v7, 0x4D0018u, 0, 0, &lpOutBuffer, 0x10u, 0, 0);
    CloseHandle((HANDLE)v7);
  }
  if ( (unsigned int)dword_1800BF000 > 5 )
  {
    if ( (unsigned __int8)tlgKeywordOn(&dword_1800BF000, 0x400000000000LL) )
    {
      v14 = 0x1000000;
      v13 = a1;
      v15 = a2;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        v10,
        (unsigned int)byte_1800A5751,
        v11,
        v12,
        (__int64)&v15,
        (__int64)&v13,
        (__int64)&v14);
    }
  }
}

```

## disassembly

```asm
0x18001613c  push    rbp
0x18001613e  push    rbx
0x18001613f  push    rsi
0x180016140  push    rdi
0x180016141  push    r12
0x180016143  push    r13
0x180016145  push    r14
0x180016147  push    r15
0x180016149  lea     rbp, [rsp-3B8h]
0x180016151  sub     rsp, 4B8h
0x180016158  mov     rax, cs:__security_cookie
0x18001615f  xor     rax, rsp
0x180016162  mov     [rbp+3F0h+var_50], rax
0x180016169  mov     rsi, rdx
0x18001616c  mov     r14d, ecx
0x18001616f  mov     r13d, 208h
0x180016175  lea     rcx, [rbp+3F0h+szVolumeName]; void *
0x180016179  mov     r8d, r13d; Size
0x18001617c  xor     edx, edx; Val
0x18001617e  call    memset_0
0x180016183  mov     r8d, r13d; Size
0x180016186  lea     rcx, [rbp+3F0h+var_260]; void *
0x18001618d  xor     edx, edx; Val
0x18001618f  call    memset_0
0x180016194  xor     eax, eax
0x180016196  lea     rdx, [rbp+3F0h+szVolumeName]; lpszVolumeName
0x18001619a  xor     r15d, r15d
0x18001619d  mov     [rsp+4F0h+var_494], rax
0x1800161a2  or      r12, 0FFFFFFFFFFFFFFFFh
0x1800161a6  mov     [rsp+4F0h+var_48C], eax
0x1800161aa  mov     r8d, 104h; cchBufferLength
0x1800161b0  mov     [rsp+4F0h+var_484], rax
0x1800161b5  lea     rcx, szVolumeMountPoint; "C:\\"
0x1800161bc  mov     [rsp+4F0h+var_47C], eax
0x1800161c0  mov     rdi, r12
0x1800161c3  mov     [rsp+4F0h+OutBuffer], r15d
0x1800161c8  mov     [rsp+4F0h+var_488], r15d
0x1800161cd  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x1800161d3  test    eax, eax
0x1800161d5  jz      short loc_18001620B
0x1800161d7  lea     rcx, [rbp+3F0h+szVolumeName]
0x1800161db  mov     rax, r12
0x1800161de  inc     rax
0x1800161e1  cmp     [rcx+rax*2], r15w
0x1800161e6  jnz     short loc_1800161DE
0x1800161e8  lea     rcx, ds:0FFFFFFFFFFFFFFFEh[rax*2]
0x1800161f0  cmp     rcx, r13
0x1800161f3  jnb     loc_180016385
0x1800161f9  mov     [rbp+rcx+3F0h+szVolumeName], r15w
0x1800161ff  lea     rcx, [rbp+3F0h+szVolumeName]; unsigned __int16 *
0x180016203  call    ?OpenVolumeHandle@@YAPEAXPEBG@Z; OpenVolumeHandle(ushort const *)
0x180016208  mov     rdi, rax
0x18001620b  mov     r8d, 104h; cchBufferLength
0x180016211  lea     rdx, [rbp+3F0h+var_260]; lpszVolumeName
0x180016218  lea     rcx, aCData; "C:\\Data\\"
0x18001621f  mov     rbx, r12
0x180016222  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x180016228  test    eax, eax
0x18001622a  jz      short loc_180016284
0x18001622c  lea     rax, [rbp+3F0h+var_260]
0x180016233  mov     rcx, r12
0x180016236  inc     rcx
0x180016239  cmp     [rax+rcx*2], r15w
0x18001623e  jnz     short loc_180016236
0x180016240  lea     rcx, ds:0FFFFFFFFFFFFFFFEh[rcx*2]
0x180016248  cmp     rcx, r13
0x18001624b  jnb     loc_180016385
0x180016251  mov     [rbp+rcx+3F0h+var_260], r15w
0x18001625a  lea     rdx, [rbp+3F0h+var_260]
0x180016261  lea     rcx, [rbp+3F0h+szVolumeName]
0x180016265  mov     r8d, 104h
0x18001626b  call    cs:__imp__o__wcsnicmp
0x180016271  test    eax, eax
0x180016273  jz      short loc_180016284
0x180016275  lea     rcx, [rbp+3F0h+var_260]; unsigned __int16 *
0x18001627c  call    ?OpenVolumeHandle@@YAPEAXPEBG@Z; OpenVolumeHandle(ushort const *)
0x180016281  mov     rbx, rax
0x180016284  mov     r13d, 10h
0x18001628a  cmp     rdi, r12
0x18001628d  jz      short loc_1800162C5
0x18001628f  mov     [rsp+4F0h+lpOverlapped], r15; lpOverlapped
0x180016294  lea     rax, [rsp+4F0h+OutBuffer]
0x180016299  mov     [rsp+4F0h+lpBytesReturned], r15; lpBytesReturned
0x18001629e  xor     r9d, r9d; nInBufferSize
0x1800162a1  mov     [rsp+4F0h+nOutBufferSize], r13d; nOutBufferSize
0x1800162a6  xor     r8d, r8d; lpInBuffer
0x1800162a9  mov     edx, 4D0018h; dwIoControlCode
0x1800162ae  mov     [rsp+4F0h+lpOutBuffer], rax; lpOutBuffer
0x1800162b3  mov     rcx, rdi; hDevice
0x1800162b6  call    cs:__imp_DeviceIoControl
0x1800162bc  mov     rcx, rdi; hObject
0x1800162bf  call    cs:__imp_CloseHandle
0x1800162c5  cmp     rbx, r12
0x1800162c8  jz      short loc_180016300
0x1800162ca  mov     [rsp+4F0h+lpOverlapped], r15; lpOverlapped
0x1800162cf  lea     rax, [rsp+4F0h+var_488]
0x1800162d4  mov     [rsp+4F0h+lpBytesReturned], r15; lpBytesReturned
0x1800162d9  xor     r9d, r9d; nInBufferSize
0x1800162dc  mov     [rsp+4F0h+nOutBufferSize], r13d; nOutBufferSize
0x1800162e1  xor     r8d, r8d; lpInBuffer
0x1800162e4  mov     edx, 4D0018h; dwIoControlCode
0x1800162e9  mov     [rsp+4F0h+lpOutBuffer], rax; lpOutBuffer
0x1800162ee  mov     rcx, rbx; hDevice
0x1800162f1  call    cs:__imp_DeviceIoControl
0x1800162f7  mov     rcx, rbx; hObject
0x1800162fa  call    cs:__imp_CloseHandle
0x180016300  mov     eax, cs:dword_1800BF000
0x180016306  cmp     eax, 5
0x180016309  jbe     short loc_180016362
0x18001630b  mov     rdx, 400000000000h
0x180016315  lea     rcx, dword_1800BF000
0x18001631c  call    _tlgKeywordOn
0x180016321  test    al, al
0x180016323  jz      short loc_180016362
0x180016325  lea     rax, [rsp+4F0h+var_4A8]
0x18001632a  mov     [rsp+4F0h+var_4A8], 1000000h
0x180016333  mov     [rsp+4F0h+lpBytesReturned], rax
0x180016338  lea     rdx, byte_1800A5751
0x18001633f  lea     rax, [rsp+4F0h+var_4B0]
0x180016344  mov     [rsp+4F0h+var_4B0], r14d
0x180016349  mov     qword ptr [rsp+4F0h+nOutBufferSize], rax
0x18001634e  lea     rax, [rsp+4F0h+var_4A0]
0x180016353  mov     [rsp+4F0h+lpOutBuffer], rax
0x180016358  mov     [rsp+4F0h+var_4A0], rsi
0x18001635d  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x180016362  mov     rcx, [rbp+3F0h+var_50]
0x180016369  xor     rcx, rsp; StackCookie
0x18001636c  call    __security_check_cookie
0x180016371  add     rsp, 4B8h
0x180016378  pop     r15
0x18001637a  pop     r14
0x18001637c  pop     r13
0x18001637e  pop     r12
0x180016380  pop     rdi
0x180016381  pop     rsi
0x180016382  pop     rbx
0x180016383  pop     rbp
0x180016384  retn
0x180016385  call    __report_rangecheckfailure
```
