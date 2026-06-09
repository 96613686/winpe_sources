# ComputeService::Vmwp::Details::LookupWorkerProcessInterface(_GUID const &,IUnknown * *)

- ea: `0x180061e88`
- end: `0x180062045`
- name: `?LookupWorkerProcessInterface@Details@Vmwp@ComputeService@@YA_NAEBU_GUID@@PEAPEAUIUnknown@@@Z`
- size: `445`
- prototype: `bool(ComputeService::Vmwp::Details *__hidden this, const struct _GUID *, struct IUnknown **)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180061cbc`

## callees

- `0x180002f50`
- `0x180006158`
- `0x180006660`
- `0x18000d108`
- `0x18005118c`
- `0x180061e88`
- `0x18006204c`
- `0x180086010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180061f43`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180061f43`
- `combase!__imp_RoGetMachineGlobalObjectTable` at `0x180061f5f`
- `combase!__imp_RoGetMachineGlobalObjectTable` at `0x180061f5f`

## string_xrefs

- `0x180062000`: `onecore\vm\compute\shared\vmwp\lib\workerprocess.cpp`
- `0x180062033`: `onecore\vm\compute\shared\vmwp\lib\workerprocess.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
bool __fastcall ComputeService::Vmwp::Details::LookupWorkerProcessInterface(
        ComputeService::Vmwp::Details *this,
        const struct _GUID *a2,
        struct IUnknown **a3)
{
  int v3; // ebx
  _QWORD *v4; // rax
  unsigned int v5; // r8d
  unsigned __int64 v6; // rdx
  HRESULT StringReference; // eax
  int v8; // edx
  unsigned int v9; // r8d
  int MachineGlobalObjectTable; // eax
  wil::details::in1diag3 *v11; // rcx
  int v12; // eax
  bool v13; // bl
  unsigned int v15; // eax
  int v16; // [rsp+20h] [rbp-69h]
  _QWORD v17[4]; // [rsp+30h] [rbp-59h] BYREF
  __int64 v18; // [rsp+50h] [rbp-39h] BYREF
  __int128 hstringHeader; // [rsp+58h] [rbp-31h] BYREF
  __int128 hstringHeader_16; // [rsp+68h] [rbp-21h] BYREF
  WCHAR sourceString[8]; // [rsp+80h] [rbp-9h] BYREF
  __int128 v22; // [rsp+90h] [rbp+7h]
  __int128 v23; // [rsp+A0h] [rbp+17h]
  __int128 v24; // [rsp+B0h] [rbp+27h]
  __int64 v25; // [rsp+C0h] [rbp+37h]
  __int16 v26; // [rsp+C8h] [rbp+3Fh]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  v3 = (int)a2;
  CommonUtilities::GuidToString(v17, this, a3);
  v4 = v17;
  if ( v17[3] > 7u )
    v4 = (_QWORD *)v17[0];
  *(_OWORD *)sourceString = *(_OWORD *)v4;
  v22 = *((_OWORD *)v4 + 1);
  v23 = *((_OWORD *)v4 + 2);
  v24 = *((_OWORD *)v4 + 3);
  v25 = v4[8];
  std::wstring::~wstring(v17);
  v26 = 0;
  hstringHeader = 0;
  hstringHeader_16 = 0;
  v6 = -1;
  do
    ++v6;
  while ( sourceString[v6] );
  if ( v6 > 0xFFFFFFFF )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v6, v5);
    __debugbreak();
  }
  if ( (int)v6 + 1 < (unsigned int)v6 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v6, v5);
    __debugbreak();
  }
  StringReference = WindowsCreateStringReference(
                      sourceString,
                      v6,
                      (HSTRING_HEADER *)&hstringHeader,
                      (HSTRING *)&hstringHeader_16 + 1);
  if ( StringReference < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)StringReference, v8, v9);
LABEL_19:
    wil::details::in1diag3::Throw_Hr(
      v11,
      (void *)0x11E,
      (unsigned int)"onecore\\vm\\compute\\shared\\vmwp\\lib\\workerprocess.cpp",
      (const char *)(unsigned int)MachineGlobalObjectTable,
      v16);
  }
  v18 = 0;
  MachineGlobalObjectTable = RoGetMachineGlobalObjectTable(&v18);
  v11 = retaddr;
  if ( MachineGlobalObjectTable < 0 )
    goto LABEL_19;
  v12 = (*(__int64 (__fastcall **)(__int64, GUID *, _QWORD, GUID *))(*(_QWORD *)v18 + 40LL))(
          v18,
          &CLSID_VmVirtualMachine,
          *((_QWORD *)&hstringHeader_16 + 1),
          &GUID_00000000_0000_0000_c000_000000000046);
  if ( v12 < 0 && v12 != -2147220997 && v12 != -2147221164 )
  {
    v15 = wil::verify_hresult<long>((unsigned int)v12);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x12B,
      (unsigned int)"onecore\\vm\\compute\\shared\\vmwp\\lib\\workerprocess.cpp",
      (const char *)v15,
      v3);
  }
  v13 = v12 >= 0;
  if ( v18 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
  return v13;
}

```

## disassembly

```asm
0x180061e88  mov     [rsp-8+arg_10], rbx
0x180061e8d  mov     [rsp-8+arg_18], rdi
0x180061e92  push    rbp
0x180061e93  lea     rbp, [rsp-57h]
0x180061e98  sub     rsp, 0E0h
0x180061e9f  mov     rax, cs:__security_cookie
0x180061ea6  xor     rax, rsp
0x180061ea9  mov     [rbp+57h+var_10], rax
0x180061ead  mov     rbx, rdx
0x180061eb0  mov     rdx, rcx
0x180061eb3  lea     rcx, [rbp+57h+var_B0]
0x180061eb7  call    ?GuidToString@CommonUtilities@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBU_GUID@@_N@Z; CommonUtilities::GuidToString(_GUID const &,bool)
0x180061ebc  lea     rax, [rbp+57h+var_B0]
0x180061ec0  cmp     [rbp+57h+var_98], 7
0x180061ec5  cmova   rax, [rbp+57h+var_B0]
0x180061eca  movups  xmm0, xmmword ptr [rax]
0x180061ecd  movaps  xmmword ptr [rbp+57h+sourceString], xmm0
0x180061ed1  movups  xmm1, xmmword ptr [rax+10h]
0x180061ed5  movaps  [rbp+57h+var_50], xmm1
0x180061ed9  movups  xmm0, xmmword ptr [rax+20h]
0x180061edd  movaps  [rbp+57h+var_40], xmm0
0x180061ee1  movups  xmm1, xmmword ptr [rax+30h]
0x180061ee5  movaps  [rbp+57h+var_30], xmm1
0x180061ee9  movsd   xmm0, qword ptr [rax+40h]
0x180061eee  movsd   [rbp+57h+var_20], xmm0
0x180061ef3  lea     rcx, [rbp+57h+var_B0]
0x180061ef7  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180061efc  xor     edi, edi
0x180061efe  mov     [rbp+57h+var_18], di
0x180061f02  xorps   xmm0, xmm0
0x180061f05  movups  xmmword ptr [rbp+57h+hstringHeader.Reserved], xmm0
0x180061f09  movups  xmmword ptr [rbp+57h+hstringHeader.Reserved+10h], xmm0
0x180061f0d  lea     rax, [rbp+57h+sourceString]
0x180061f11  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180061f15  inc     rdx; int
0x180061f18  cmp     [rax+rdx*2], di
0x180061f1c  jnz     short loc_180061F15
0x180061f1e  mov     eax, 0FFFFFFFFh
0x180061f23  cmp     rdx, rax
0x180061f26  ja      loc_180062012
0x180061f2c  lea     eax, [rdx+1]
0x180061f2f  cmp     eax, edx
0x180061f31  jb      loc_18006201D
0x180061f37  lea     r9, [rbp+57h+string]; string
0x180061f3b  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x180061f3f  lea     rcx, [rbp+57h+sourceString]; sourceString
0x180061f43  call    cs:__imp_WindowsCreateStringReference
0x180061f4a  nop     dword ptr [rax+rax+00h]
0x180061f4f  test    eax, eax
0x180061f51  js      loc_180062028
0x180061f57  mov     [rbp+57h+var_90], rdi
0x180061f5b  lea     rcx, [rbp+57h+var_90]
0x180061f5f  call    cs:__imp_RoGetMachineGlobalObjectTable
0x180061f66  nop     dword ptr [rax+rax+00h]
0x180061f6b  mov     rcx, [rbp+5Fh]
0x180061f6f  test    eax, eax
0x180061f71  js      loc_180062030
0x180061f77  mov     rcx, [rbp+57h+var_90]
0x180061f7b  mov     rax, [rcx]
0x180061f7e  mov     qword ptr [rsp+0E0h+var_C0], rbx; int
0x180061f83  lea     r9, _GUID_00000000_0000_0000_c000_000000000046
0x180061f8a  mov     r8, [rbp+57h+string]
0x180061f8e  lea     rdx, CLSID_VmVirtualMachine
0x180061f95  mov     rax, [rax+28h]
0x180061f99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061f9e  mov     ebx, eax
0x180061fa0  test    eax, eax
0x180061fa2  jns     short loc_180061FB2
0x180061fa4  cmp     eax, 800401FBh
0x180061fa9  jz      short loc_180061FB2
0x180061fab  cmp     eax, 80040154h
0x180061fb0  jnz     short loc_180061FF2
0x180061fb2  shr     ebx, 1Fh
0x180061fb5  xor     bl, 1
0x180061fb8  mov     rcx, [rbp+57h+var_90]
0x180061fbc  test    rcx, rcx
0x180061fbf  jz      short loc_180061FCE
0x180061fc1  mov     rax, [rcx]
0x180061fc4  mov     rax, [rax+10h]
0x180061fc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061fcd  nop
0x180061fce  mov     al, bl
0x180061fd0  mov     rcx, [rbp+57h+var_10]
0x180061fd4  xor     rcx, rsp; StackCookie
0x180061fd7  call    __security_check_cookie
0x180061fdc  lea     r11, [rsp+0E0h+var_s0]
0x180061fe4  mov     rbx, [r11+20h]
0x180061fe8  mov     rdi, [r11+28h]
0x180061fec  mov     rsp, r11
0x180061fef  pop     rbp
0x180061ff0  retn
0x180061ff2  mov     ecx, ebx
0x180061ff4  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x180061ff9  mov     r9d, eax; char *
0x180061ffc  mov     rcx, [rbp+5Fh]; this
0x180062000  lea     r8, aOnecoreVmCompu_7; "onecore\\vm\\compute\\shared\\vmwp\\lib"...
0x180062007  mov     edx, 12Bh; void *
0x18006200c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180062012  mov     ecx, 80070216h; this
0x180062017  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18006201c  int     3; Trap to Debugger
0x18006201d  mov     ecx, 80070216h; this
0x180062022  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x180062027  int     3; Trap to Debugger
0x180062028  mov     ecx, eax; this
0x18006202a  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18006202f  nop
0x180062030  mov     r9d, eax; char *
0x180062033  lea     r8, aOnecoreVmCompu_7; "onecore\\vm\\compute\\shared\\vmwp\\lib"...
0x18006203a  mov     edx, 11Eh; void *
0x18006203f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
