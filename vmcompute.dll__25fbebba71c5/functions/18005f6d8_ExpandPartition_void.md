# ExpandPartition(void *)

- ea: `0x18005f6d8`
- end: `0x18005fa42`
- name: `?ExpandPartition@@YA_JPEAX@Z`
- size: `874`
- prototype: `__int64 __fastcall(HANDLE hDevice)`
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002ee84`
- `0x18005fa48`

## callees

- `0x180002f50`
- `0x180003c78`
- `0x18000d0ec`
- `0x180022d10`
- `0x18002e898`
- `0x1800348e0`
- `0x18005f6d8`
- `0x18006083c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f771`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f771`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18005f75d`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18005f7ca`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18005f85d`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18005f981`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18005f75d`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18005f7ca`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18005f85d`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18005f981`

## string_xrefs

- `0x18005f9af`: `onecore\vm\compute\shared\storage\diskutilities.cpp`
- `0x18005f9ce`: `onecore\vm\compute\shared\storage\diskutilities.cpp`
- `0x18005f9e6`: `onecore\vm\compute\shared\storage\diskutilities.cpp`
- `0x18005f9ff`: `onecore\vm\compute\shared\storage\diskutilities.cpp`
- `0x18005fa11`: `onecore\vm\compute\shared\storage\diskutilities.cpp`
- `0x18005fa30`: `onecore\vm\compute\shared\storage\diskutilities.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ExpandPartition(HANDLE hDevice)
{
  DWORD LastError; // eax
  const char *v3; // r9
  const char *v4; // r9
  __int64 v5; // rbx
  const char *v7; // r9
  _BYTE *v8; // rcx
  int v9; // edx
  __int64 v10; // r9
  __int64 v11; // r8
  _BYTE *v12; // rdx
  __int64 v13; // rax
  __int64 v14; // r8
  __int64 v15; // rax
  __int64 v16; // rdi
  __int64 v17; // rdi
  const char *v18; // r9
  unsigned int lpOutBuffer; // [rsp+20h] [rbp-E0h]
  LPVOID v20[2]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v21; // [rsp+50h] [rbp-B0h]
  DWORD BytesReturned; // [rsp+58h] [rbp-A8h] BYREF
  DWORD lpBytesReturned; // [rsp+5Ch] [rbp-A4h] BYREF
  _QWORD InBuffer[2]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE OutBuffer[336]; // [rsp+70h] [rbp-90h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1F8h] [rbp+F8h]

  BytesReturned = 0;
  *(_OWORD *)v20 = 0;
  v21 = 0;
  memset_0(OutBuffer, 0, sizeof(OutBuffer));
  if ( DeviceIoControl(hDevice, 0x70050u, 0, 0, OutBuffer, 0x150u, &BytesReturned, 0) )
  {
    v8 = OutBuffer;
  }
  else
  {
    LastError = GetLastError();
    if ( LastError == 1 )
    {
      InBuffer[0] = 0;
      lpBytesReturned = 0;
      if ( !DeviceIoControl(hDevice, 0x7405Cu, 0, 0, InBuffer, 8u, &lpBytesReturned, 0) )
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0x2B2,
          (unsigned int)"onecore\\vm\\compute\\shared\\storage\\diskutilities.cpp",
          v4);
      v5 = InBuffer[0];
      goto LABEL_5;
    }
    if ( LastError != 122 )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x2B9,
        (unsigned int)"onecore\\vm\\compute\\shared\\storage\\diskutilities.cpp",
        v3);
    std::vector<unsigned char>::resize(v20, 4096);
    if ( !DeviceIoControl(hDevice, 0x70050u, 0, 0, v20[0], LODWORD(v20[1]) - LODWORD(v20[0]), &BytesReturned, 0) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x2C6,
        (unsigned int)"onecore\\vm\\compute\\shared\\storage\\diskutilities.cpp",
        v7);
    v8 = v20[0];
  }
  if ( *(_DWORD *)v8 != 1 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x2D5,
      (unsigned int)"onecore\\vm\\compute\\shared\\storage\\diskutilities.cpp",
      (const char *)0x57,
      lpOutBuffer);
  v9 = *((_DWORD *)v8 + 1) - 1;
  if ( v9 < 0 )
    goto LABEL_34;
  v10 = *(_QWORD *)PARTITION_BASIC_DATA_GUID.Data4;
  while ( 1 )
  {
    v11 = 144LL * v9;
    if ( *(_QWORD *)&v8[v11 + 80] == *(_QWORD *)&PARTITION_BASIC_DATA_GUID.Data1
      && *(_QWORD *)&v8[v11 + 88] == *(_QWORD *)PARTITION_BASIC_DATA_GUID.Data4 )
    {
      break;
    }
    if ( --v9 < 0 )
      goto LABEL_34;
  }
  v12 = &v8[v11 + 48];
  if ( !v12 )
LABEL_34:
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x2E4,
      (unsigned int)"onecore\\vm\\compute\\shared\\storage\\diskutilities.cpp",
      (const char *)0x57,
      lpOutBuffer);
  v13 = *((_QWORD *)v12 + 1);
  v5 = *((_QWORD *)v12 + 2);
  v14 = v5 + v13;
  if ( v13 < 0 )
  {
    if ( v5 < 0 && v14 > v13 )
      goto LABEL_35;
  }
  else if ( v5 >= 0 && v14 < v13 )
  {
    goto LABEL_35;
  }
  v15 = *((_QWORD *)v8 + 3);
  v10 = *((_QWORD *)v8 + 4);
  v16 = v10 + v15;
  if ( v15 >= 0 )
  {
    if ( v10 < 0 || v16 >= v15 )
      goto LABEL_27;
LABEL_35:
    SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v8, v12, v14, v10);
  }
  if ( v10 < 0 && v16 > v15 )
    goto LABEL_35;
LABEL_27:
  if ( v14 < v16 )
  {
    HIDWORD(InBuffer[0]) = 0;
    LODWORD(InBuffer[0]) = *((_DWORD *)v12 + 6);
    v17 = v16 - v14;
    InBuffer[1] = v17;
    if ( !DeviceIoControl(hDevice, 0x7C0D0u, InBuffer, 0x10u, 0, 0, &BytesReturned, 0) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x303,
        (unsigned int)"onecore\\vm\\compute\\shared\\storage\\diskutilities.cpp",
        v18);
    v5 += v17;
  }
LABEL_5:
  std::vector<unsigned char>::~vector<unsigned char>(v20);
  return v5;
}

```

## disassembly

```asm
0x18005f6d8  push    rbp
0x18005f6da  push    rbx
0x18005f6db  push    rsi
0x18005f6dc  push    rdi
0x18005f6dd  lea     rbp, [rsp-0D8h]
0x18005f6e5  sub     rsp, 1D8h
0x18005f6ec  mov     rax, cs:__security_cookie
0x18005f6f3  xor     rax, rsp
0x18005f6f6  mov     [rbp+0F0h+var_30], rax
0x18005f6fd  mov     rsi, rcx
0x18005f700  mov     [rsp+1F0h+BytesReturned], 0
0x18005f708  xor     eax, eax
0x18005f70a  xorps   xmm1, xmm1
0x18005f70d  movdqu  xmmword ptr [rsp+1F0h+var_1B0], xmm1
0x18005f713  mov     [rsp+1F0h+var_1A0], rax
0x18005f718  mov     ebx, 150h
0x18005f71d  mov     r8d, ebx; Size
0x18005f720  xor     edx, edx; Val
0x18005f722  lea     rcx, [rsp+1F0h+OutBuffer]; void *
0x18005f727  call    memset_0
0x18005f72c  mov     [rsp+1F0h+lpOverlapped], 0; lpOverlapped
0x18005f735  lea     rax, [rsp+1F0h+BytesReturned]
0x18005f73a  mov     [rsp+1F0h+lpBytesReturned], rax; lpBytesReturned
0x18005f73f  mov     [rsp+1F0h+nOutBufferSize], ebx; nOutBufferSize
0x18005f743  lea     rax, [rsp+1F0h+OutBuffer]
0x18005f748  mov     [rsp+1F0h+lpOutBuffer], rax; unsigned int
0x18005f74d  xor     r9d, r9d; nInBufferSize
0x18005f750  xor     r8d, r8d; lpInBuffer
0x18005f753  mov     ebx, 70050h
0x18005f758  mov     edx, ebx; dwIoControlCode
0x18005f75a  mov     rcx, rsi; hDevice
0x18005f75d  call    cs:__imp_DeviceIoControl
0x18005f764  nop     dword ptr [rax+rax+00h]
0x18005f769  test    eax, eax
0x18005f76b  jnz     loc_18005F87F
0x18005f771  call    cs:__imp_GetLastError
0x18005f778  nop     dword ptr [rax+rax+00h]
0x18005f77d  cmp     eax, 1
0x18005f780  jnz     loc_18005F813
0x18005f786  mov     [rsp+1F0h+InBuffer], 0
0x18005f78f  mov     [rsp+1F0h+var_194], 0
0x18005f797  mov     [rsp+1F0h+lpOverlapped], 0; lpOverlapped
0x18005f7a0  lea     rax, [rsp+1F0h+var_194]
0x18005f7a5  mov     [rsp+1F0h+lpBytesReturned], rax; lpBytesReturned
0x18005f7aa  mov     [rsp+1F0h+nOutBufferSize], 8; nOutBufferSize
0x18005f7b2  lea     rax, [rsp+1F0h+InBuffer]
0x18005f7b7  mov     [rsp+1F0h+lpOutBuffer], rax; lpOutBuffer
0x18005f7bc  xor     r9d, r9d; nInBufferSize
0x18005f7bf  xor     r8d, r8d; lpInBuffer
0x18005f7c2  mov     edx, 7405Ch; dwIoControlCode
0x18005f7c7  mov     rcx, rsi; hDevice
0x18005f7ca  call    cs:__imp_DeviceIoControl
0x18005f7d1  nop     dword ptr [rax+rax+00h]
0x18005f7d6  mov     rcx, [rbp+0F8h]; this
0x18005f7dd  test    eax, eax
0x18005f7df  jz      loc_18005F9E6
0x18005f7e5  mov     rbx, [rsp+1F0h+InBuffer]
0x18005f7ea  lea     rcx, [rsp+1F0h+var_1B0]
0x18005f7ef  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x18005f7f4  mov     rax, rbx
0x18005f7f7  mov     rcx, [rbp+0F0h+var_30]
0x18005f7fe  xor     rcx, rsp; StackCookie
0x18005f801  call    __security_check_cookie
0x18005f806  add     rsp, 1D8h
0x18005f80d  pop     rdi
0x18005f80e  pop     rsi
0x18005f80f  pop     rbx
0x18005f810  pop     rbp
0x18005f811  retn
0x18005f813  cmp     eax, 7Ah ; 'z'
0x18005f816  jnz     loc_18005F9F8
0x18005f81c  mov     edx, 1000h
0x18005f821  lea     rcx, [rsp+1F0h+var_1B0]
0x18005f826  call    ?resize@?$vector@EV?$allocator@E@std@@@std@@QEAAX_K@Z; std::vector<uchar>::resize(unsigned __int64)
0x18005f82b  mov     rcx, [rsp+1F0h+var_1B0]
0x18005f830  mov     eax, dword ptr [rsp+1F0h+var_1B0+8]
0x18005f834  sub     eax, ecx
0x18005f836  mov     [rsp+1F0h+lpOverlapped], 0; lpOverlapped
0x18005f83f  lea     r8, [rsp+1F0h+BytesReturned]
0x18005f844  mov     [rsp+1F0h+lpBytesReturned], r8; lpBytesReturned
0x18005f849  mov     [rsp+1F0h+nOutBufferSize], eax; nOutBufferSize
0x18005f84d  mov     [rsp+1F0h+lpOutBuffer], rcx; lpOutBuffer
0x18005f852  xor     r9d, r9d; nInBufferSize
0x18005f855  xor     r8d, r8d; lpInBuffer
0x18005f858  mov     edx, ebx; dwIoControlCode
0x18005f85a  mov     rcx, rsi; hDevice
0x18005f85d  call    cs:__imp_DeviceIoControl
0x18005f864  nop     dword ptr [rax+rax+00h]
0x18005f869  mov     rcx, [rbp+0F8h]; this
0x18005f870  test    eax, eax
0x18005f872  jz      loc_18005FA11
0x18005f878  mov     rcx, [rsp+1F0h+var_1B0]
0x18005f87d  jmp     short loc_18005F884
0x18005f87f  lea     rcx, [rsp+1F0h+OutBuffer]
0x18005f884  cmp     dword ptr [rcx], 1
0x18005f887  jnz     loc_18005FA23
0x18005f88d  mov     edx, [rcx+4]
0x18005f890  sub     edx, 1
0x18005f893  js      loc_18005F9C1
0x18005f899  mov     r9, qword ptr cs:PARTITION_BASIC_DATA_GUID.Data4
0x18005f8a0  mov     r10, qword ptr cs:PARTITION_BASIC_DATA_GUID.Data1
0x18005f8a7  movsxd  rax, edx
0x18005f8aa  lea     r8, [rax+rax*8]
0x18005f8ae  shl     r8, 4
0x18005f8b2  cmp     [r8+rcx+50h], r10
0x18005f8b7  jnz     short loc_18005F8C0
0x18005f8b9  cmp     [r8+rcx+58h], r9
0x18005f8be  jz      short loc_18005F8CB
0x18005f8c0  sub     edx, 1
0x18005f8c3  js      loc_18005F9C1
0x18005f8c9  jmp     short loc_18005F8A7
0x18005f8cb  lea     rdx, [rcx+30h]
0x18005f8cf  add     rdx, r8
0x18005f8d2  jz      loc_18005F9C1
0x18005f8d8  mov     rax, [rdx+8]
0x18005f8dc  mov     rbx, [rdx+10h]
0x18005f8e0  lea     r8, [rbx+rax]
0x18005f8e4  test    rax, rax
0x18005f8e7  js      short loc_18005F8F9
0x18005f8e9  test    rbx, rbx
0x18005f8ec  js      short loc_18005F907
0x18005f8ee  cmp     r8, rax
0x18005f8f1  jl      loc_18005F9E0
0x18005f8f7  jmp     short loc_18005F907
0x18005f8f9  test    rbx, rbx
0x18005f8fc  jns     short loc_18005F907
0x18005f8fe  cmp     r8, rax
0x18005f901  jg      loc_18005F9E0
0x18005f907  mov     rax, [rcx+18h]
0x18005f90b  mov     r9, [rcx+20h]
0x18005f90f  lea     rdi, [r9+rax]
0x18005f913  test    rax, rax
0x18005f916  js      loc_18005F9A0
0x18005f91c  test    r9, r9
0x18005f91f  js      short loc_18005F92A
0x18005f921  cmp     rdi, rax
0x18005f924  jl      loc_18005F9E0
0x18005f92a  cmp     r8, rdi
0x18005f92d  jge     loc_18005F7EA
0x18005f933  mov     dword ptr [rsp+1F0h+InBuffer+4], 0
0x18005f93b  mov     eax, [rdx+18h]
0x18005f93e  mov     dword ptr [rsp+1F0h+InBuffer], eax
0x18005f942  sub     rdi, r8
0x18005f945  mov     [rsp+1F0h+var_188], rdi
0x18005f94a  mov     [rsp+1F0h+lpOverlapped], 0; lpOverlapped
0x18005f953  lea     rax, [rsp+1F0h+BytesReturned]
0x18005f958  mov     [rsp+1F0h+lpBytesReturned], rax; lpBytesReturned
0x18005f95d  mov     [rsp+1F0h+nOutBufferSize], 0; nOutBufferSize
0x18005f965  mov     [rsp+1F0h+lpOutBuffer], 0; lpOutBuffer
0x18005f96e  mov     r9d, 10h; nInBufferSize
0x18005f974  lea     r8, [rsp+1F0h+InBuffer]; lpInBuffer
0x18005f979  mov     edx, 7C0D0h; dwIoControlCode
0x18005f97e  mov     rcx, rsi; hDevice
0x18005f981  call    cs:__imp_DeviceIoControl
0x18005f988  nop     dword ptr [rax+rax+00h]
0x18005f98d  mov     rcx, [rbp+0F8h]; this
0x18005f994  test    eax, eax
0x18005f996  jz      short loc_18005F9AF
0x18005f998  add     rbx, rdi
0x18005f99b  jmp     loc_18005F7EA
0x18005f9a0  test    r9, r9
0x18005f9a3  jns     short loc_18005F92A
0x18005f9a5  cmp     rdi, rax
0x18005f9a8  jg      short loc_18005F9E0
0x18005f9aa  jmp     loc_18005F92A
0x18005f9af  lea     r8, aOnecoreVmCompu_15; "onecore\\vm\\compute\\shared\\storage\\"...
0x18005f9b6  mov     edx, 303h; void *
0x18005f9bb  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18005f9c1  mov     rcx, [rbp+0F8h]; this
0x18005f9c8  mov     r9d, 57h ; 'W'; char *
0x18005f9ce  lea     r8, aOnecoreVmCompu_15; "onecore\\vm\\compute\\shared\\storage\\"...
0x18005f9d5  mov     edx, 2E4h; void *
0x18005f9da  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18005f9e0  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@SAXXZ; SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(void)
0x18005f9e6  lea     r8, aOnecoreVmCompu_15; "onecore\\vm\\compute\\shared\\storage\\"...
0x18005f9ed  mov     edx, 2B2h; void *
0x18005f9f2  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18005f9f8  mov     rcx, [rbp+0F8h]; this
0x18005f9ff  lea     r8, aOnecoreVmCompu_15; "onecore\\vm\\compute\\shared\\storage\\"...
0x18005fa06  mov     edx, 2B9h; void *
0x18005fa0b  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18005fa11  lea     r8, aOnecoreVmCompu_15; "onecore\\vm\\compute\\shared\\storage\\"...
0x18005fa18  mov     edx, 2C6h; void *
0x18005fa1d  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18005fa23  mov     rcx, [rbp+0F8h]; this
0x18005fa2a  mov     r9d, 57h ; 'W'; char *
0x18005fa30  lea     r8, aOnecoreVmCompu_15; "onecore\\vm\\compute\\shared\\storage\\"...
0x18005fa37  mov     edx, 2D5h; void *
0x18005fa3c  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
