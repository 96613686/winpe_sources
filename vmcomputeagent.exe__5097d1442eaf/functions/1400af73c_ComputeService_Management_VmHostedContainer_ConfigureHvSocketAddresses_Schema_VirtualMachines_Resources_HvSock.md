# ComputeService::Management::VmHostedContainer::ConfigureHvSocketAddresses(Schema::VirtualMachines::Resources::HvSocketAddress const &)

- ea: `0x1400af73c`
- end: `0x1400af8c1`
- name: `?ConfigureHvSocketAddresses@VmHostedContainer@Management@ComputeService@@YAXAEBUHvSocketAddress@Resources@VirtualMachines@Schema@@@Z`
- size: `389`
- prototype: `void __fastcall(ComputeService::Management::VmHostedContainer *__hidden this, const struct Schema::VirtualMachines::Resources::HvSocketAddress *)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x14009a630`
- `0x1400a5de0`

## callees

- `0x140005360`
- `0x1400056c4`
- `0x1400068e0`
- `0x140008760`
- `0x14000ddac`
- `0x14001e4f4`
- `0x1400af73c`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400af872`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400af872`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1400af7be`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1400af7be`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1400af852`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1400af852`

## string_xrefs

- `0x1400af89a`: `onecore\vm\compute\management\orchestration\vmhostedcontainer\vmhostedcontainerresources.cpp`
- `0x1400af8af`: `onecore\vm\compute\management\orchestration\vmhostedcontainer\vmhostedcontainerresources.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall ComputeService::Management::VmHostedContainer::ConfigureHvSocketAddresses(
        ComputeService::Management::VmHostedContainer *this,
        const struct Schema::VirtualMachines::Resources::HvSocketAddress *a2)
{
  const WCHAR *v3; // rcx
  char *FileW; // rbx
  const char *v5; // r9
  _DWORD *v6; // rdi
  unsigned __int64 v7; // rdx
  const char *v8; // r9
  DWORD BytesReturned; // [rsp+50h] [rbp+7h] BYREF
  LPCWSTR lpFileName[2]; // [rsp+58h] [rbp+Fh] BYREF
  __int64 v11; // [rsp+68h] [rbp+1Fh]
  unsigned __int64 v12; // [rsp+70h] [rbp+27h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+5Fh]

  *(_OWORD *)lpFileName = 0;
  v11 = 0;
  v12 = 0;
  std::wstring::_Construct<1,unsigned short const *>(
    (__int64)lpFileName,
    L"\\\\.\\HvSocketSystem\\HvSocketControl",
    0x22u);
  v3 = (const WCHAR *)lpFileName;
  if ( v12 > 7 )
    v3 = lpFileName[0];
  FileW = (char *)CreateFileW(v3, 0xC0000000, 0, 0, 1u, 0, 0);
  if ( ((unsigned __int64)(FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x36,
      (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\vmhostedcontainer\\vmhostedcontainerresources.cpp",
      v5);
  v6 = operator new[](0x40u);
  v6[8] = 0;
  *(_OWORD *)v6 = *(_OWORD *)this;
  *((_OWORD *)v6 + 1) = *((_OWORD *)this + 1);
  BytesReturned = 0;
  if ( !DeviceIoControl(FileW, 0x21C018u, v6, 0x40u, 0, 0, &BytesReturned, 0) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x4F,
      (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\vmhostedcontainer\\vmhostedcontainerresources.cpp",
      v8);
  operator delete(v6, v7);
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(FileW);
  std::wstring::~wstring(lpFileName);
}

```

## disassembly

```asm
0x1400af73c  push    rbp
0x1400af73e  push    rbx
0x1400af73f  push    rsi
0x1400af740  push    rdi
0x1400af741  lea     rbp, [rsp-3Fh]
0x1400af746  sub     rsp, 88h
0x1400af74d  mov     rax, cs:__security_cookie
0x1400af754  xor     rax, rsp
0x1400af757  mov     [rbp+57h+var_28], rax
0x1400af75b  mov     rsi, rcx
0x1400af75e  xorps   xmm0, xmm0
0x1400af761  movups  xmmword ptr [rbp+57h+lpFileName], xmm0
0x1400af765  mov     [rbp+57h+var_38], 0
0x1400af76d  mov     [rbp+57h+var_30], 0
0x1400af775  mov     r8d, 22h ; '"'
0x1400af77b  lea     rdx, aHvsocketsystem; "\\\\.\\HvSocketSystem\\HvSocketControl"
0x1400af782  lea     rcx, [rbp+57h+lpFileName]
0x1400af786  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1400af78b  nop
0x1400af78c  lea     rcx, [rbp+57h+lpFileName]
0x1400af790  cmp     [rbp+57h+var_30], 7
0x1400af795  cmova   rcx, [rbp+57h+lpFileName]; lpFileName
0x1400af79a  mov     [rsp+0A0h+hTemplateFile], 0; hTemplateFile
0x1400af7a3  mov     [rsp+0A0h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x1400af7ab  mov     [rsp+0A0h+dwCreationDisposition], 1; dwCreationDisposition
0x1400af7b3  xor     r9d, r9d; lpSecurityAttributes
0x1400af7b6  xor     r8d, r8d; dwShareMode
0x1400af7b9  mov     edx, 0C0000000h; dwDesiredAccess
0x1400af7be  call    cs:__imp_CreateFileW
0x1400af7c4  mov     rbx, rax
0x1400af7c7  mov     [rbp+57h+var_58], rax
0x1400af7cb  inc     rax
0x1400af7ce  test    rax, 0FFFFFFFFFFFFFFFEh
0x1400af7d4  setz    al
0x1400af7d7  mov     rcx, [rbp+5Fh]; this
0x1400af7db  test    al, al
0x1400af7dd  jnz     loc_1400AF8AF
0x1400af7e3  mov     [rbp+57h+var_60], 0
0x1400af7eb  mov     ecx, 40h ; '@'; unsigned __int64
0x1400af7f0  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1400af7f5  mov     rdi, rax
0x1400af7f8  mov     [rbp+57h+var_60], rax
0x1400af7fc  mov     dword ptr [rax+20h], 0
0x1400af803  movups  xmm0, xmmword ptr [rsi]
0x1400af806  movdqu  xmmword ptr [rax], xmm0
0x1400af80a  movups  xmm1, xmmword ptr [rsi+10h]
0x1400af80e  movdqu  xmmword ptr [rax+10h], xmm1
0x1400af813  mov     [rbp+57h+BytesReturned], 0
0x1400af81a  mov     rsi, [rbp+5Fh]
0x1400af81e  mov     [rsp+0A0h+lpOverlapped], 0; lpOverlapped
0x1400af827  lea     rax, [rbp+57h+BytesReturned]
0x1400af82b  mov     [rsp+0A0h+hTemplateFile], rax; lpBytesReturned
0x1400af830  mov     [rsp+0A0h+dwFlagsAndAttributes], 0; nOutBufferSize
0x1400af838  mov     qword ptr [rsp+0A0h+dwCreationDisposition], 0; lpOutBuffer
0x1400af841  mov     r9d, 40h ; '@'; nInBufferSize
0x1400af847  mov     r8, rdi; lpInBuffer
0x1400af84a  mov     edx, 21C018h; dwIoControlCode
0x1400af84f  mov     rcx, rbx; hDevice
0x1400af852  call    cs:__imp_DeviceIoControl
0x1400af858  test    eax, eax
0x1400af85a  jz      short loc_1400AF89A
0x1400af85c  mov     rcx, rdi; void *
0x1400af85f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1400af864  nop
0x1400af865  lea     rax, [rbx-1]
0x1400af869  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400af86d  ja      short loc_1400AF879
0x1400af86f  mov     rcx, rbx; hObject
0x1400af872  call    cs:__imp_CloseHandle
0x1400af878  nop
0x1400af879  lea     rcx, [rbp+57h+lpFileName]; void *
0x1400af87d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400af882  mov     rcx, [rbp+57h+var_28]
0x1400af886  xor     rcx, rsp; StackCookie
0x1400af889  call    __security_check_cookie
0x1400af88e  add     rsp, 88h
0x1400af895  pop     rdi
0x1400af896  pop     rsi
0x1400af897  pop     rbx
0x1400af898  pop     rbp
0x1400af899  retn
0x1400af89a  lea     r8, aOnecoreVmCompu_15; "onecore\\vm\\compute\\management\\orche"...
0x1400af8a1  mov     edx, 4Fh ; 'O'; void *
0x1400af8a6  mov     rcx, rsi; this
0x1400af8a9  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1400af8af  lea     r8, aOnecoreVmCompu_15; "onecore\\vm\\compute\\management\\orche"...
0x1400af8b6  mov     edx, 36h ; '6'; void *
0x1400af8bb  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
