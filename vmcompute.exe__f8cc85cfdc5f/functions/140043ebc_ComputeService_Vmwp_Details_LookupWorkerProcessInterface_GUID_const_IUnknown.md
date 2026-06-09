# ComputeService::Vmwp::Details::LookupWorkerProcessInterface(_GUID const &,IUnknown * *)

- ea: `0x140043ebc`
- end: `0x14004403e`
- name: `?LookupWorkerProcessInterface@Details@Vmwp@ComputeService@@YA_NAEBU_GUID@@PEAPEAUIUnknown@@@Z`
- size: `386`
- prototype: `bool __fastcall(ComputeService::Vmwp::Details *__hidden this, const struct _GUID *, struct IUnknown **)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x140057e88`
- `0x1400b74d0`

## callees

- `0x14004387c`
- `0x140043ebc`
- `0x1400c40e0`
- `0x1401332f0`
- `0x1402c4010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x140043f50`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x140044031`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x140043f50`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x140044031`
- `combase!__imp_RoGetMachineGlobalObjectTable` at `0x140043f65`
- `combase!__imp_RoGetMachineGlobalObjectTable` at `0x140043f65`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140043f34`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140043f34`

## string_xrefs

- `0x140043f7c`: `onecore\vm\compute\shared\vmwp\lib\workerprocess.cpp`
- `0x140043fd0`: `onecore\vm\compute\shared\vmwp\lib\workerprocess.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
bool __fastcall ComputeService::Vmwp::Details::LookupWorkerProcessInterface(
        const struct _GUID *this,
        const struct _GUID *a2,
        struct IUnknown **a3)
{
  int v3; // ebx
  unsigned __int64 v4; // rdx
  HRESULT StringReference; // eax
  int MachineGlobalObjectTable; // eax
  int v7; // eax
  bool v8; // bl
  int v10; // [rsp+20h] [rbp-49h]
  __int64 v11; // [rsp+30h] [rbp-39h] BYREF
  __int128 hstringHeader; // [rsp+38h] [rbp-31h] BYREF
  __int128 hstringHeader_16; // [rsp+48h] [rbp-21h] BYREF
  WCHAR sourceString[40]; // [rsp+60h] [rbp-9h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  v3 = (int)a2;
  Vml::VmGuid::ToStringInternal(this, sourceString);
  sourceString[36] = 0;
  hstringHeader = 0;
  hstringHeader_16 = 0;
  v4 = -1;
  do
    ++v4;
  while ( sourceString[v4] );
  if ( v4 > 0xFFFFFFFF || (int)v4 + 1 < (unsigned int)v4 )
  {
    RaiseException(0x80070216, 1u, 0, 0);
    __debugbreak();
    JUMPOUT(0x14004403ELL);
  }
  StringReference = WindowsCreateStringReference(
                      sourceString,
                      v4,
                      (HSTRING_HEADER *)&hstringHeader,
                      (HSTRING *)&hstringHeader_16 + 1);
  if ( StringReference < 0 )
    RaiseException(StringReference, 1u, 0, 0);
  v11 = 0;
  MachineGlobalObjectTable = RoGetMachineGlobalObjectTable(&v11);
  if ( MachineGlobalObjectTable < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x11E,
      (unsigned int)"onecore\\vm\\compute\\shared\\vmwp\\lib\\workerprocess.cpp",
      (const char *)(unsigned int)MachineGlobalObjectTable,
      v10);
  v7 = (*(__int64 (__fastcall **)(__int64, GUID *, _QWORD, GUID *))(*(_QWORD *)v11 + 40LL))(
         v11,
         &CLSID_VmVirtualMachine,
         *((_QWORD *)&hstringHeader_16 + 1),
         &GUID_00000000_0000_0000_c000_000000000046);
  if ( v7 < 0 && v7 != -2147220997 && v7 != -2147221164 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x12B,
      (unsigned int)"onecore\\vm\\compute\\shared\\vmwp\\lib\\workerprocess.cpp",
      (const char *)(unsigned int)v7,
      v3);
  v8 = v7 >= 0;
  if ( v11 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
  return v8;
}

```

## disassembly

```asm
0x140043ebc  mov     [rsp-8+arg_10], rbx
0x140043ec1  mov     [rsp-8+arg_18], rdi
0x140043ec6  push    rbp
0x140043ec7  lea     rbp, [rsp-57h]
0x140043ecc  sub     rsp, 0C0h
0x140043ed3  mov     rax, cs:__security_cookie
0x140043eda  xor     rax, rsp
0x140043edd  mov     [rbp+57h+var_10], rax
0x140043ee1  mov     rbx, rdx
0x140043ee4  lea     rdx, [rbp+57h+sourceString]; unsigned __int16 *
0x140043ee8  call    ?ToStringInternal@VmGuid@Vml@@CAXAEBU_GUID@@PEAG@Z; Vml::VmGuid::ToStringInternal(_GUID const &,ushort *)
0x140043eed  xor     edi, edi
0x140043eef  mov     [rbp+57h+var_18], di
0x140043ef3  xorps   xmm0, xmm0
0x140043ef6  movups  xmmword ptr [rbp+57h+hstringHeader.Reserved], xmm0
0x140043efa  movups  xmmword ptr [rbp+57h+hstringHeader.Reserved+10h], xmm0
0x140043efe  lea     rax, [rbp+57h+sourceString]
0x140043f02  or      rdx, 0FFFFFFFFFFFFFFFFh
0x140043f06  inc     rdx; length
0x140043f09  cmp     [rax+rdx*2], di
0x140043f0d  jnz     short loc_140043F06
0x140043f0f  mov     eax, 0FFFFFFFFh
0x140043f14  cmp     rdx, rax
0x140043f17  ja      loc_140044022
0x140043f1d  lea     eax, [rdx+1]
0x140043f20  cmp     eax, edx
0x140043f22  jb      loc_140044022
0x140043f28  lea     r9, [rbp+57h+string]; string
0x140043f2c  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x140043f30  lea     rcx, [rbp+57h+sourceString]; sourceString
0x140043f34  call    cs:__imp_WindowsCreateStringReference
0x140043f3b  nop     dword ptr [rax+rax+00h]
0x140043f40  test    eax, eax
0x140043f42  jns     short loc_140043F5D
0x140043f44  xor     r9d, r9d; lpArguments
0x140043f47  xor     r8d, r8d; nNumberOfArguments
0x140043f4a  lea     edx, [r9+1]; dwExceptionFlags
0x140043f4e  mov     ecx, eax; dwExceptionCode
0x140043f50  call    cs:__imp_RaiseException
0x140043f57  nop     dword ptr [rax+rax+00h]
0x140043f5c  nop
0x140043f5d  mov     [rbp+57h+var_90], rdi
0x140043f61  lea     rcx, [rbp+57h+var_90]
0x140043f65  call    cs:__imp_RoGetMachineGlobalObjectTable
0x140043f6c  nop     dword ptr [rax+rax+00h]
0x140043f71  mov     rcx, [rbp+5Fh]; this
0x140043f75  test    eax, eax
0x140043f77  jns     short loc_140043F8E
0x140043f79  mov     r9d, eax; char *
0x140043f7c  lea     r8, aOnecoreVmCompu_62; "onecore\\vm\\compute\\shared\\vmwp\\lib"...
0x140043f83  mov     edx, 11Eh; void *
0x140043f88  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140043f8e  mov     rcx, [rbp+57h+var_90]
0x140043f92  mov     rax, [rcx]
0x140043f95  mov     qword ptr [rsp+0C0h+var_A0], rbx; int
0x140043f9a  lea     r9, _GUID_00000000_0000_0000_c000_000000000046
0x140043fa1  mov     r8, [rbp+57h+string]
0x140043fa5  lea     rdx, CLSID_VmVirtualMachine
0x140043fac  mov     rax, [rax+28h]
0x140043fb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140043fb5  mov     ebx, eax
0x140043fb7  test    eax, eax
0x140043fb9  jns     short loc_140043FE2
0x140043fbb  cmp     eax, 800401FBh
0x140043fc0  jz      short loc_140043FE2
0x140043fc2  cmp     eax, 80040154h
0x140043fc7  jz      short loc_140043FE2
0x140043fc9  mov     rcx, [rbp+5Fh]; this
0x140043fcd  mov     r9d, eax; char *
0x140043fd0  lea     r8, aOnecoreVmCompu_62; "onecore\\vm\\compute\\shared\\vmwp\\lib"...
0x140043fd7  mov     edx, 12Bh; void *
0x140043fdc  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140043fe2  shr     ebx, 1Fh
0x140043fe5  xor     bl, 1
0x140043fe8  mov     rcx, [rbp+57h+var_90]
0x140043fec  test    rcx, rcx
0x140043fef  jz      short loc_140043FFE
0x140043ff1  mov     rax, [rcx]
0x140043ff4  mov     rax, [rax+10h]
0x140043ff8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140043ffd  nop
0x140043ffe  mov     al, bl
0x140044000  mov     rcx, [rbp+57h+var_10]
0x140044004  xor     rcx, rsp; StackCookie
0x140044007  call    __security_check_cookie
0x14004400c  lea     r11, [rsp+0C0h+var_s0]
0x140044014  mov     rbx, [r11+20h]
0x140044018  mov     rdi, [r11+28h]
0x14004401c  mov     rsp, r11
0x14004401f  pop     rbp
0x140044020  retn
0x140044022  xor     r9d, r9d; lpArguments
0x140044025  xor     r8d, r8d; nNumberOfArguments
0x140044028  lea     edx, [r9+1]; dwExceptionFlags
0x14004402c  mov     ecx, 80070216h; dwExceptionCode
0x140044031  call    cs:__imp_RaiseException
0x140044038  nop     dword ptr [rax+rax+00h]
0x14004403d  int     3; Trap to Debugger
```
