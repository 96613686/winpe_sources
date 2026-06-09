# CHardwareManager::IsFingerprintSensor(ushort *,bool *)

- ea: `0x1800721f0`
- end: `0x1800723d6`
- name: `?IsFingerprintSensor@CHardwareManager@@AEAAJPEAGPEA_N@Z`
- size: `486`
- prototype: `__int64 __fastcall(CHardwareManager *this, unsigned __int16 *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x180041c14`

## callees

- `0x1800058ec`
- `0x1800549a0`
- `0x180056358`
- `0x180069cc8`
- `0x1800702a8`
- `0x180070e10`
- `0x1800721f0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800722e7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800722e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800722d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180072304`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800722d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180072304`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x1800722fe`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x1800722fe`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800722ce`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800722ce`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180072247`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180072247`

## string_xrefs

- `0x18007225e`: `onecore\ds\security\biometrics\service\server\hardwaremanager.cpp`
- `0x180072381`: `onecore\ds\security\biometrics\service\server\hardwaremanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CHardwareManager::IsFingerprintSensor(CHardwareManager *this, unsigned __int16 *a2, bool *a3)
{
  HANDLE FileW; // rbx
  const char *v6; // r9
  unsigned int LastError; // ebx
  unsigned __int64 v8; // rsi
  unsigned int *v9; // rdi
  DWORD v10; // eax
  const char *v11; // r9
  char *v12; // r14
  char *v13; // rax
  size_t v14; // rdi
  LPVOID lpOutBuffer; // [rsp+40h] [rbp-40h] BYREF
  void *v16; // [rsp+48h] [rbp-38h]
  __int64 v17; // [rsp+50h] [rbp-30h]
  struct _OVERLAPPED Overlapped; // [rsp+58h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]
  CHardwareManager *v20; // [rsp+B0h] [rbp+30h] BYREF
  DWORD BytesReturned; // [rsp+B8h] [rbp+38h] BYREF
  HANDLE v22; // [rsp+C8h] [rbp+48h] BYREF

  v20 = this;
  if ( !a2 )
    return 2148106284LL;
  FileW = CreateFileW(a2, 0xC0000000, 0, 0, 3u, 0x40000000u, 0);
  v22 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0xAB7,
                  (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\hardwaremanager.cpp",
                  v6);
    goto LABEL_22;
  }
  LODWORD(v8) = 1580;
  LOBYTE(v20) = 0;
  std::vector<unsigned char>::vector<unsigned char>(&lpOutBuffer, 1580, &v20);
  while ( 1 )
  {
    v9 = (unsigned int *)lpOutBuffer;
    memset(&Overlapped, 0, sizeof(Overlapped));
    BytesReturned = 0;
    if ( !DeviceIoControl(FileW, 0x440004u, 0, 0, lpOutBuffer, v8, &BytesReturned, &Overlapped) )
    {
      v10 = GetLastError();
      if ( v10 == 997 )
      {
        SetLastError(0);
        GetOverlappedResult(FileW, &Overlapped, &BytesReturned, 1);
        v10 = GetLastError();
      }
      if ( v10 )
      {
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0xADF,
                      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\hardwaremanager.cpp",
                      v11);
        std::vector<unsigned char>::_Tidy(&lpOutBuffer);
        goto LABEL_22;
      }
    }
    if ( BytesReturned != 4 )
      break;
    v8 = *v9;
    LOBYTE(v20) = 0;
    v12 = (char *)v16;
    if ( v8 < (_BYTE *)v16 - (_BYTE *)lpOutBuffer )
    {
      v13 = (char *)lpOutBuffer + v8;
      goto LABEL_17;
    }
    if ( v8 > (_BYTE *)v16 - (_BYTE *)lpOutBuffer )
    {
      if ( (unsigned int)v8 <= (unsigned __int64)(v17 - (_QWORD)lpOutBuffer) )
      {
        v14 = (unsigned int)v8 - ((_BYTE *)v16 - (_BYTE *)lpOutBuffer);
        memset_0(v16, 0, v14);
        v13 = &v12[v14];
LABEL_17:
        v16 = v13;
      }
      else
      {
        std::vector<unsigned char>::_Resize_reallocate<unsigned char>(&lpOutBuffer, (unsigned int)v8, &v20);
      }
    }
  }
  if ( v9[4] == 8 )
    *a3 = 1;
  std::vector<unsigned char>::_Tidy(&lpOutBuffer);
  LastError = 0;
LABEL_22:
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v22);
  return LastError;
}

```

## disassembly

```asm
0x1800721f0  mov     [rsp-28h+arg_10], rbx
0x1800721f5  mov     [rsp-28h+arg_0], rcx
0x1800721fa  push    rbp
0x1800721fb  push    rsi
0x1800721fc  push    rdi
0x1800721fd  push    r14
0x1800721ff  push    r15
0x180072201  mov     rbp, rsp
0x180072204  sub     rsp, 80h
0x18007220b  mov     r15, r8
0x18007220e  mov     rax, rdx
0x180072211  test    rdx, rdx
0x180072214  jnz     short loc_180072220
0x180072216  mov     eax, 8009802Ch
0x18007221b  jmp     loc_1800723BF
0x180072220  mov     [rsp+80h+hTemplateFile], 0; hTemplateFile
0x180072229  mov     [rsp+80h+dwFlagsAndAttributes], 40000000h; dwFlagsAndAttributes
0x180072231  mov     [rsp+80h+dwCreationDisposition], 3; dwCreationDisposition
0x180072239  xor     r9d, r9d; lpSecurityAttributes
0x18007223c  xor     r8d, r8d; dwShareMode
0x18007223f  mov     edx, 0C0000000h; dwDesiredAccess
0x180072244  mov     rcx, rax; lpFileName
0x180072247  call    cs:__imp_CreateFileW
0x18007224d  mov     rbx, rax
0x180072250  mov     [rbp+arg_18], rax
0x180072254  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180072258  jnz     short loc_180072276
0x18007225a  mov     rcx, [rbp+28h]; this
0x18007225e  lea     r8, aOnecoreDsSecur_25; "onecore\\ds\\security\\biometrics\\serv"...
0x180072265  mov     edx, 0AB7h; void *
0x18007226a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18007226f  mov     ebx, eax
0x180072271  jmp     loc_1800723B4
0x180072276  mov     esi, 62Ch
0x18007227b  mov     byte ptr [rbp+arg_0], 0
0x18007227f  lea     r8, [rbp+arg_0]
0x180072283  mov     edx, esi
0x180072285  lea     rcx, [rbp+lpOutBuffer]
0x180072289  call    ??$?0V?$allocator@E@std@@$0A@@?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBEAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,uchar const &,std::allocator<uchar> const &)
0x18007228e  nop
0x18007228f  mov     rdi, [rbp+lpOutBuffer]
0x180072293  xorps   xmm0, xmm0
0x180072296  movups  xmmword ptr [rbp+Overlapped.Internal], xmm0
0x18007229a  movups  xmmword ptr [rbp+Overlapped.10h], xmm0
0x18007229e  mov     [rbp+BytesReturned], 0
0x1800722a5  lea     rax, [rbp+Overlapped]
0x1800722a9  mov     [rsp+80h+lpOverlapped], rax; lpOverlapped
0x1800722ae  lea     rax, [rbp+BytesReturned]
0x1800722b2  mov     [rsp+80h+hTemplateFile], rax; lpBytesReturned
0x1800722b7  mov     [rsp+80h+dwFlagsAndAttributes], esi; nOutBufferSize
0x1800722bb  mov     qword ptr [rsp+80h+dwCreationDisposition], rdi; lpOutBuffer
0x1800722c0  xor     r9d, r9d; nInBufferSize
0x1800722c3  xor     r8d, r8d; lpInBuffer
0x1800722c6  mov     edx, 440004h; dwIoControlCode
0x1800722cb  mov     rcx, rbx; hDevice
0x1800722ce  call    cs:__imp_DeviceIoControl
0x1800722d4  test    eax, eax
0x1800722d6  jnz     short loc_18007230E
0x1800722d8  call    cs:__imp_GetLastError
0x1800722de  cmp     eax, 3E5h
0x1800722e3  jnz     short loc_18007230A
0x1800722e5  xor     ecx, ecx; dwErrCode
0x1800722e7  call    cs:__imp_SetLastError
0x1800722ed  mov     r9d, 1; bWait
0x1800722f3  lea     r8, [rbp+BytesReturned]; lpNumberOfBytesTransferred
0x1800722f7  lea     rdx, [rbp+Overlapped]; lpOverlapped
0x1800722fb  mov     rcx, rbx; hFile
0x1800722fe  call    cs:__imp_GetOverlappedResult
0x180072304  call    cs:__imp_GetLastError
0x18007230a  test    eax, eax
0x18007230c  jnz     short loc_18007237D
0x18007230e  cmp     [rbp+BytesReturned], 4
0x180072312  jnz     loc_18007239F
0x180072318  mov     esi, [rdi]
0x18007231a  mov     byte ptr [rbp+arg_0], 0
0x18007231e  mov     rdx, [rbp+lpOutBuffer]
0x180072322  mov     r14, [rbp+var_38]
0x180072326  mov     rcx, r14
0x180072329  sub     rcx, rdx
0x18007232c  mov     edi, esi
0x18007232e  cmp     rsi, rcx
0x180072331  jnb     short loc_180072339
0x180072333  lea     rax, [rsi+rdx]
0x180072337  jmp     short loc_180072374
0x180072339  jbe     loc_18007228F
0x18007233f  mov     rax, [rbp+var_30]
0x180072343  sub     rax, rdx
0x180072346  cmp     rdi, rax
0x180072349  jbe     short loc_180072360
0x18007234b  lea     r8, [rbp+arg_0]
0x18007234f  mov     rdx, rdi
0x180072352  lea     rcx, [rbp+lpOutBuffer]
0x180072356  call    ??$_Resize_reallocate@E@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBE@Z; std::vector<uchar>::_Resize_reallocate<uchar>(unsigned __int64,uchar const &)
0x18007235b  jmp     loc_18007228F
0x180072360  sub     rdi, rcx
0x180072363  mov     r8, rdi; Size
0x180072366  xor     edx, edx; Val
0x180072368  mov     rcx, r14; void *
0x18007236b  call    memset_0
0x180072370  lea     rax, [rdi+r14]
0x180072374  mov     [rbp+var_38], rax
0x180072378  jmp     loc_18007228F
0x18007237d  mov     rcx, [rbp+28h]; this
0x180072381  lea     r8, aOnecoreDsSecur_25; "onecore\\ds\\security\\biometrics\\serv"...
0x180072388  mov     edx, 0ADFh; void *
0x18007238d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180072392  mov     ebx, eax
0x180072394  lea     rcx, [rbp+lpOutBuffer]
0x180072398  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18007239d  jmp     short loc_1800723B4
0x18007239f  cmp     dword ptr [rdi+10h], 8
0x1800723a3  jnz     short loc_1800723A9
0x1800723a5  mov     byte ptr [r15], 1
0x1800723a9  lea     rcx, [rbp+lpOutBuffer]
0x1800723ad  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1800723b2  xor     ebx, ebx
0x1800723b4  lea     rcx, [rbp+arg_18]
0x1800723b8  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800723bd  mov     eax, ebx
0x1800723bf  mov     rbx, [rsp+80h+arg_10]
0x1800723c7  add     rsp, 80h
0x1800723ce  pop     r15
0x1800723d0  pop     r14
0x1800723d2  pop     rdi
0x1800723d3  pop     rsi
0x1800723d4  pop     rbp
0x1800723d5  retn
```
