# ExpandPartition(void *)

- ea: `0x140040878`
- end: `0x140040bbc`
- name: `?ExpandPartition@@YA_JPEAX@Z`
- size: `836`
- prototype: `__int64 __fastcall(HANDLE hDevice)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140040bc4`

## callees

- `0x140005360`
- `0x140006098`
- `0x14000ddac`
- `0x14002c0a8`
- `0x1400341ac`
- `0x14003ac0c`
- `0x140040878`
- `0x14004153c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004090b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004090b`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1400408fd`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x14004095e`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1400409ea`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x140040b04`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1400408fd`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x14004095e`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1400409ea`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x140040b04`

## string_xrefs

- `0x140040b29`: `onecore\vm\compute\shared\storage\diskutilities.cpp`
- `0x140040b48`: `onecore\vm\compute\shared\storage\diskutilities.cpp`
- `0x140040b60`: `onecore\vm\compute\shared\storage\diskutilities.cpp`
- `0x140040b79`: `onecore\vm\compute\shared\storage\diskutilities.cpp`
- `0x140040b8b`: `onecore\vm\compute\shared\storage\diskutilities.cpp`
- `0x140040baa`: `onecore\vm\compute\shared\storage\diskutilities.cpp`

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
0x140040878  push    rbp
0x14004087a  push    rbx
0x14004087b  push    rsi
0x14004087c  push    rdi
0x14004087d  lea     rbp, [rsp-0D8h]
0x140040885  sub     rsp, 1D8h
0x14004088c  mov     rax, cs:__security_cookie
0x140040893  xor     rax, rsp
0x140040896  mov     [rbp+0F0h+var_30], rax
0x14004089d  mov     rsi, rcx
0x1400408a0  mov     [rsp+1F0h+BytesReturned], 0
0x1400408a8  xor     eax, eax
0x1400408aa  xorps   xmm1, xmm1
0x1400408ad  movdqu  xmmword ptr [rsp+1F0h+var_1B0], xmm1
0x1400408b3  mov     [rsp+1F0h+var_1A0], rax
0x1400408b8  mov     ebx, 150h
0x1400408bd  mov     r8d, ebx; Size
0x1400408c0  xor     edx, edx; Val
0x1400408c2  lea     rcx, [rsp+1F0h+OutBuffer]; void *
0x1400408c7  call    memset_0
0x1400408cc  mov     [rsp+1F0h+lpOverlapped], 0; lpOverlapped
0x1400408d5  lea     rax, [rsp+1F0h+BytesReturned]
0x1400408da  mov     [rsp+1F0h+lpBytesReturned], rax; lpBytesReturned
0x1400408df  mov     [rsp+1F0h+nOutBufferSize], ebx; nOutBufferSize
0x1400408e3  lea     rax, [rsp+1F0h+OutBuffer]
0x1400408e8  mov     [rsp+1F0h+lpOutBuffer], rax; unsigned int
0x1400408ed  xor     r9d, r9d; nInBufferSize
0x1400408f0  xor     r8d, r8d; lpInBuffer
0x1400408f3  mov     ebx, 70050h
0x1400408f8  mov     edx, ebx; dwIoControlCode
0x1400408fa  mov     rcx, rsi; hDevice
0x1400408fd  call    cs:__imp_DeviceIoControl
0x140040903  test    eax, eax
0x140040905  jnz     loc_140040A06
0x14004090b  call    cs:__imp_GetLastError
0x140040911  cmp     eax, 1
0x140040914  jnz     loc_1400409A0
0x14004091a  mov     [rsp+1F0h+InBuffer], 0
0x140040923  mov     [rsp+1F0h+var_194], 0
0x14004092b  mov     [rsp+1F0h+lpOverlapped], 0; lpOverlapped
0x140040934  lea     rax, [rsp+1F0h+var_194]
0x140040939  mov     [rsp+1F0h+lpBytesReturned], rax; lpBytesReturned
0x14004093e  mov     [rsp+1F0h+nOutBufferSize], 8; nOutBufferSize
0x140040946  lea     rax, [rsp+1F0h+InBuffer]
0x14004094b  mov     [rsp+1F0h+lpOutBuffer], rax; lpOutBuffer
0x140040950  xor     r9d, r9d; nInBufferSize
0x140040953  xor     r8d, r8d; lpInBuffer
0x140040956  mov     edx, 7405Ch; dwIoControlCode
0x14004095b  mov     rcx, rsi; hDevice
0x14004095e  call    cs:__imp_DeviceIoControl
0x140040964  mov     rcx, [rbp+0F8h]; this
0x14004096b  test    eax, eax
0x14004096d  jz      loc_140040B60
0x140040973  mov     rbx, [rsp+1F0h+InBuffer]
0x140040978  lea     rcx, [rsp+1F0h+var_1B0]
0x14004097d  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x140040982  mov     rax, rbx
0x140040985  mov     rcx, [rbp+0F0h+var_30]
0x14004098c  xor     rcx, rsp; StackCookie
0x14004098f  call    __security_check_cookie
0x140040994  add     rsp, 1D8h
0x14004099b  pop     rdi
0x14004099c  pop     rsi
0x14004099d  pop     rbx
0x14004099e  pop     rbp
0x14004099f  retn
0x1400409a0  cmp     eax, 7Ah ; 'z'
0x1400409a3  jnz     loc_140040B72
0x1400409a9  mov     edx, 1000h
0x1400409ae  lea     rcx, [rsp+1F0h+var_1B0]
0x1400409b3  call    ?resize@?$vector@EV?$allocator@E@std@@@std@@QEAAX_K@Z; std::vector<uchar>::resize(unsigned __int64)
0x1400409b8  mov     rcx, [rsp+1F0h+var_1B0]
0x1400409bd  mov     eax, dword ptr [rsp+1F0h+var_1B0+8]
0x1400409c1  sub     eax, ecx
0x1400409c3  mov     [rsp+1F0h+lpOverlapped], 0; lpOverlapped
0x1400409cc  lea     r8, [rsp+1F0h+BytesReturned]
0x1400409d1  mov     [rsp+1F0h+lpBytesReturned], r8; lpBytesReturned
0x1400409d6  mov     [rsp+1F0h+nOutBufferSize], eax; nOutBufferSize
0x1400409da  mov     [rsp+1F0h+lpOutBuffer], rcx; lpOutBuffer
0x1400409df  xor     r9d, r9d; nInBufferSize
0x1400409e2  xor     r8d, r8d; lpInBuffer
0x1400409e5  mov     edx, ebx; dwIoControlCode
0x1400409e7  mov     rcx, rsi; hDevice
0x1400409ea  call    cs:__imp_DeviceIoControl
0x1400409f0  mov     rcx, [rbp+0F8h]; this
0x1400409f7  test    eax, eax
0x1400409f9  jz      loc_140040B8B
0x1400409ff  mov     rcx, [rsp+1F0h+var_1B0]
0x140040a04  jmp     short loc_140040A0B
0x140040a06  lea     rcx, [rsp+1F0h+OutBuffer]
0x140040a0b  cmp     dword ptr [rcx], 1
0x140040a0e  jnz     loc_140040B9D
0x140040a14  mov     edx, [rcx+4]
0x140040a17  sub     edx, 1
0x140040a1a  js      loc_140040B3B
0x140040a20  mov     r9, qword ptr cs:PARTITION_BASIC_DATA_GUID.Data4
0x140040a27  mov     r10, qword ptr cs:PARTITION_BASIC_DATA_GUID.Data1
0x140040a2e  movsxd  rax, edx
0x140040a31  lea     r8, [rax+rax*8]
0x140040a35  shl     r8, 4
0x140040a39  cmp     [r8+rcx+50h], r10
0x140040a3e  jnz     short loc_140040A47
0x140040a40  cmp     [r8+rcx+58h], r9
0x140040a45  jz      short loc_140040A52
0x140040a47  sub     edx, 1
0x140040a4a  js      loc_140040B3B
0x140040a50  jmp     short loc_140040A2E
0x140040a52  lea     rdx, [rcx+30h]
0x140040a56  add     rdx, r8
0x140040a59  jz      loc_140040B3B
0x140040a5f  mov     rax, [rdx+8]
0x140040a63  mov     rbx, [rdx+10h]
0x140040a67  lea     r8, [rbx+rax]
0x140040a6b  test    rax, rax
0x140040a6e  js      short loc_140040A80
0x140040a70  test    rbx, rbx
0x140040a73  js      short loc_140040A8E
0x140040a75  cmp     r8, rax
0x140040a78  jl      loc_140040B5A
0x140040a7e  jmp     short loc_140040A8E
0x140040a80  test    rbx, rbx
0x140040a83  jns     short loc_140040A8E
0x140040a85  cmp     r8, rax
0x140040a88  jg      loc_140040B5A
0x140040a8e  mov     rax, [rcx+18h]
0x140040a92  mov     r9, [rcx+20h]
0x140040a96  lea     rdi, [r9+rax]
0x140040a9a  test    rax, rax
0x140040a9d  js      short loc_140040B1D
0x140040a9f  test    r9, r9
0x140040aa2  js      short loc_140040AAD
0x140040aa4  cmp     rdi, rax
0x140040aa7  jl      loc_140040B5A
0x140040aad  cmp     r8, rdi
0x140040ab0  jge     loc_140040978
0x140040ab6  mov     dword ptr [rsp+1F0h+InBuffer+4], 0
0x140040abe  mov     eax, [rdx+18h]
0x140040ac1  mov     dword ptr [rsp+1F0h+InBuffer], eax
0x140040ac5  sub     rdi, r8
0x140040ac8  mov     [rsp+1F0h+var_188], rdi
0x140040acd  mov     [rsp+1F0h+lpOverlapped], 0; lpOverlapped
0x140040ad6  lea     rax, [rsp+1F0h+BytesReturned]
0x140040adb  mov     [rsp+1F0h+lpBytesReturned], rax; lpBytesReturned
0x140040ae0  mov     [rsp+1F0h+nOutBufferSize], 0; nOutBufferSize
0x140040ae8  mov     [rsp+1F0h+lpOutBuffer], 0; lpOutBuffer
0x140040af1  mov     r9d, 10h; nInBufferSize
0x140040af7  lea     r8, [rsp+1F0h+InBuffer]; lpInBuffer
0x140040afc  mov     edx, 7C0D0h; dwIoControlCode
0x140040b01  mov     rcx, rsi; hDevice
0x140040b04  call    cs:__imp_DeviceIoControl
0x140040b0a  mov     rcx, [rbp+0F8h]; this
0x140040b11  test    eax, eax
0x140040b13  jz      short loc_140040B29
0x140040b15  add     rbx, rdi
0x140040b18  jmp     loc_140040978
0x140040b1d  test    r9, r9
0x140040b20  jns     short loc_140040AAD
0x140040b22  cmp     rdi, rax
0x140040b25  jg      short loc_140040B5A
0x140040b27  jmp     short loc_140040AAD
0x140040b29  lea     r8, aOnecoreVmCompu_41; "onecore\\vm\\compute\\shared\\storage\\"...
0x140040b30  mov     edx, 303h; void *
0x140040b35  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x140040b3b  mov     rcx, [rbp+0F8h]; this
0x140040b42  mov     r9d, 57h ; 'W'; char *
0x140040b48  lea     r8, aOnecoreVmCompu_41; "onecore\\vm\\compute\\shared\\storage\\"...
0x140040b4f  mov     edx, 2E4h; void *
0x140040b54  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x140040b5a  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@SAXXZ; SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(void)
0x140040b60  lea     r8, aOnecoreVmCompu_41; "onecore\\vm\\compute\\shared\\storage\\"...
0x140040b67  mov     edx, 2B2h; void *
0x140040b6c  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x140040b72  mov     rcx, [rbp+0F8h]; this
0x140040b79  lea     r8, aOnecoreVmCompu_41; "onecore\\vm\\compute\\shared\\storage\\"...
0x140040b80  mov     edx, 2B9h; void *
0x140040b85  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x140040b8b  lea     r8, aOnecoreVmCompu_41; "onecore\\vm\\compute\\shared\\storage\\"...
0x140040b92  mov     edx, 2C6h; void *
0x140040b97  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x140040b9d  mov     rcx, [rbp+0F8h]; this
0x140040ba4  mov     r9d, 57h ; 'W'; char *
0x140040baa  lea     r8, aOnecoreVmCompu_41; "onecore\\vm\\compute\\shared\\storage\\"...
0x140040bb1  mov     edx, 2D5h; void *
0x140040bb6  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
