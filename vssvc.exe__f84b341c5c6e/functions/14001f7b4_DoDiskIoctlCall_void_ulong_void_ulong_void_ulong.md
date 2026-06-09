# DoDiskIoctlCall(void *,ulong,void *,ulong,void * *,ulong *)

- ea: `0x14001f7b4`
- end: `0x14001f920`
- name: `?DoDiskIoctlCall@@YAHPEAXK0KPEAPEAXPEAK@Z`
- size: `364`
- prototype: `__int64 __fastcall(HANDLE hDevice, DWORD dwIoControlCode, void *lpInBuffer, DWORD nInBufferSize, void **, unsigned int *)`
- caller_count: `6`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1400205d0`
- `0x140021558`
- `0x140025b74`
- `0x14004fc3c`
- `0x140062210`
- `0x1400d685c`

## callees

- `0x14001f7b4`
- `0x1400921dc`
- `0x1400d257c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14001f909`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14001f909`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001f83d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001f83d`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x14001f833`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x14001f833`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14001f7e8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14001f7e8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001f7dc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001f901`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001f7dc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001f901`

## pseudocode

```c
__int64 __fastcall DoDiskIoctlCall(
        HANDLE hDevice,
        DWORD dwIoControlCode,
        void *lpInBuffer,
        DWORD nInBufferSize,
        void **a5,
        unsigned int *a6)
{
  void *lpOutBuffer; // rbx
  unsigned int v11; // edi
  void *v12; // rax
  unsigned int v13; // esi
  DWORD LastError; // eax
  DWORD v15; // edi
  unsigned int v16; // esi
  SIZE_T cb[9]; // [rsp+40h] [rbp-48h] BYREF

  LODWORD(cb[0]) = 100;
  lpOutBuffer = 0;
  while ( 1 )
  {
    CoTaskMemFree(lpOutBuffer);
    v11 = cb[0];
    v12 = CoTaskMemAlloc(LODWORD(cb[0]));
    lpOutBuffer = v12;
    if ( !v12 )
      break;
    memset_0(v12, 0, v11);
    v13 = cb[0];
    if ( DeviceIoControl(hDevice, dwIoControlCode, lpInBuffer, nInBufferSize, lpOutBuffer, cb[0], (LPDWORD)cb, 0) )
    {
      v15 = 0;
      v16 = 1;
      if ( a5 )
      {
        *a5 = lpOutBuffer;
        lpOutBuffer = 0;
      }
      if ( a6 )
        *a6 = cb[0];
      goto LABEL_18;
    }
    LastError = GetLastError();
    v15 = LastError;
    if ( LastError != 234 && LastError != 122 )
    {
      v16 = 0;
      if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
        && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
      {
        WPP_SF_Ds(
          *(_QWORD *)WPP_GLOBAL_Control->Gpt.DiskId.Data4,
          14,
          (unsigned int)WPP_66543fd9615e3bca5dcdd21770cabfe8_Traceguids,
          LastError,
          "dwLastError");
      }
      goto LABEL_18;
    }
    if ( LODWORD(cb[0]) <= v13 )
      LODWORD(cb[0]) = 2 * v13;
  }
  v16 = 0;
  v15 = 14;
  if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
  {
    WPP_SF_Ds(
      *(_QWORD *)WPP_GLOBAL_Control->Gpt.DiskId.Data4,
      13,
      (unsigned int)WPP_66543fd9615e3bca5dcdd21770cabfe8_Traceguids,
      14,
      "pIoctlOutputBuffer");
  }
LABEL_18:
  CoTaskMemFree(lpOutBuffer);
  SetLastError(v15);
  return v16;
}

```

## disassembly

```asm
0x14001f7b4  push    rbx
0x14001f7b6  push    rbp
0x14001f7b7  push    rsi
0x14001f7b8  push    rdi
0x14001f7b9  push    r12
0x14001f7bb  push    r14
0x14001f7bd  push    r15
0x14001f7bf  sub     rsp, 50h
0x14001f7c3  mov     ebp, r9d
0x14001f7c6  mov     r14, r8
0x14001f7c9  mov     r15d, edx
0x14001f7cc  mov     r12, rcx
0x14001f7cf  mov     dword ptr [rsp+88h+cb], 64h ; 'd'
0x14001f7d7  xor     ebx, ebx
0x14001f7d9  mov     rcx, rbx; pv
0x14001f7dc  call    cs:__imp_CoTaskMemFree
0x14001f7e2  mov     edi, dword ptr [rsp+88h+cb]
0x14001f7e6  mov     ecx, edi; cb
0x14001f7e8  call    cs:__imp_CoTaskMemAlloc
0x14001f7ee  mov     rbx, rax
0x14001f7f1  test    rax, rax
0x14001f7f4  jz      loc_14001F8BD
0x14001f7fa  mov     r8d, edi; Size
0x14001f7fd  xor     edx, edx; Val
0x14001f7ff  mov     rcx, rax; void *
0x14001f802  call    memset_0
0x14001f807  mov     esi, dword ptr [rsp+88h+cb]
0x14001f80b  lea     rax, [rsp+88h+cb]
0x14001f810  mov     [rsp+88h+lpOverlapped], 0; lpOverlapped
0x14001f819  mov     r9d, ebp; nInBufferSize
0x14001f81c  mov     [rsp+88h+lpBytesReturned], rax; lpBytesReturned
0x14001f821  mov     r8, r14; lpInBuffer
0x14001f824  mov     [rsp+88h+nOutBufferSize], esi; nOutBufferSize
0x14001f828  mov     edx, r15d; dwIoControlCode
0x14001f82b  mov     rcx, r12; hDevice
0x14001f82e  mov     [rsp+88h+lpOutBuffer], rbx; lpOutBuffer
0x14001f833  call    cs:__imp_DeviceIoControl
0x14001f839  test    eax, eax
0x14001f83b  jnz     short loc_14001F891
0x14001f83d  call    cs:__imp_GetLastError
0x14001f843  mov     edi, eax
0x14001f845  cmp     eax, 0EAh
0x14001f84a  jz      short loc_14001F851
0x14001f84c  cmp     eax, 7Ah ; 'z'
0x14001f84f  jnz     short loc_14001F863
0x14001f851  cmp     dword ptr [rsp+88h+cb], esi
0x14001f855  ja      short loc_14001F7D9
0x14001f857  lea     eax, [rsi+rsi]
0x14001f85a  mov     dword ptr [rsp+88h+cb], eax
0x14001f85e  jmp     loc_14001F7D9
0x14001f863  xor     esi, esi
0x14001f865  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f86c  lea     rax, WPP_GLOBAL_Control
0x14001f873  cmp     rcx, rax
0x14001f876  jz      loc_14001F8FE
0x14001f87c  test    byte ptr [rcx+1Ch], 8
0x14001f880  jz      short loc_14001F8FE
0x14001f882  lea     edx, [rsi+0Eh]
0x14001f885  mov     r9d, edi
0x14001f888  lea     rax, aDwlasterror; "dwLastError"
0x14001f88f  jmp     short loc_14001F8E9
0x14001f891  mov     rax, [rsp+88h+arg_20]
0x14001f899  xor     edi, edi
0x14001f89b  lea     esi, [rdi+1]
0x14001f89e  test    rax, rax
0x14001f8a1  jz      short loc_14001F8A8
0x14001f8a3  mov     [rax], rbx
0x14001f8a6  xor     ebx, ebx
0x14001f8a8  mov     rcx, [rsp+88h+arg_28]
0x14001f8b0  test    rcx, rcx
0x14001f8b3  jz      short loc_14001F8FE
0x14001f8b5  mov     eax, dword ptr [rsp+88h+cb]
0x14001f8b9  mov     [rcx], eax
0x14001f8bb  jmp     short loc_14001F8FE
0x14001f8bd  xor     esi, esi
0x14001f8bf  lea     r9d, [rsi+0Eh]
0x14001f8c3  mov     edi, r9d
0x14001f8c6  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f8cd  lea     rax, WPP_GLOBAL_Control
0x14001f8d4  cmp     rcx, rax
0x14001f8d7  jz      short loc_14001F8FE
0x14001f8d9  test    byte ptr [rcx+1Ch], 8
0x14001f8dd  jz      short loc_14001F8FE
0x14001f8df  lea     edx, [rsi+0Dh]
0x14001f8e2  lea     rax, aPioctloutputbu; "pIoctlOutputBuffer"
0x14001f8e9  mov     rcx, [rcx+10h]
0x14001f8ed  lea     r8, WPP_66543fd9615e3bca5dcdd21770cabfe8_Traceguids
0x14001f8f4  mov     [rsp+88h+lpOutBuffer], rax
0x14001f8f9  call    WPP_SF_Ds
0x14001f8fe  mov     rcx, rbx; pv
0x14001f901  call    cs:__imp_CoTaskMemFree
0x14001f907  mov     ecx, edi; dwErrCode
0x14001f909  call    cs:__imp_SetLastError
0x14001f90f  mov     eax, esi
0x14001f911  add     rsp, 50h
0x14001f915  pop     r15
0x14001f917  pop     r14
0x14001f919  pop     r12
0x14001f91b  pop     rdi
0x14001f91c  pop     rsi
0x14001f91d  pop     rbp
0x14001f91e  pop     rbx
0x14001f91f  retn
```
