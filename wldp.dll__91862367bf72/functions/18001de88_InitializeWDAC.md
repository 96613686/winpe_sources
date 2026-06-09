# InitializeWDAC

- ea: `0x18001de88`
- end: `0x18001dffb`
- name: `InitializeWDAC`
- size: `371`
- prototype: `__int64(void)`
- caller_count: `3`
- callee_count: `7`
- tags: `registry_config, loader_planting`

## callers

- `0x1800351e0`
- `0x180035500`
- `0x180035800`

## callees

- `0x180018260`
- `0x180018aa4`
- `0x180019e74`
- `0x18001de88`
- `0x18001f038`
- `0x180020578`
- `0x1800206f4`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001df1f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001df9b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001dfeb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001df1f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001df9b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001dfeb`
- `ntdll!NtQuerySystemInformation` at `0x18001deba`
- `ntdll!NtQuerySystemInformation` at `0x18001df67`
- `ntdll!NtQuerySystemInformation` at `0x18001deba`
- `ntdll!NtQuerySystemInformation` at `0x18001df67`

## string_xrefs

- `0x18001ded5`: `onecore\base\ngscb\wldp\dll\applicationsetting.cpp`
- `0x18001df3a`: `onecore\base\ngscb\wldp\dll\applicationsetting.cpp`
- `0x18001df7d`: `onecore\base\ngscb\wldp\dll\applicationsetting.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
int InitializeWDAC()
{
  unsigned int v0; // eax
  const char *v1; // r9
  int result; // eax
  __int64 unique_hlocal; // rax
  HLOCAL v4; // rcx
  PVOID v5; // rbx
  NTSTATUS TestsigningPolicy; // eax
  __int64 v7; // rdx
  int v8; // edi
  __int64 v9; // r8
  __int64 v10; // r9
  ULONG ReturnLength; // [rsp+20h] [rbp-10h] BYREF
  PVOID SystemInformation; // [rsp+28h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+18h]
  char v14; // [rsp+50h] [rbp+20h] BYREF
  char v15; // [rsp+58h] [rbp+28h] BYREF
  HLOCAL hMem; // [rsp+60h] [rbp+30h] BYREF

  ReturnLength = 0;
  v15 = 0;
  v14 = 0;
  SystemInformation = 0;
  v0 = NtQuerySystemInformation(SystemProcessorPowerInformation|0x80, 0, 0, &ReturnLength);
  v1 = 0;
  if ( v0 != -1073741820 )
    v1 = (const char *)v0;
  if ( (int)v1 < 0 )
  {
    result = wil::details::in1diag3::Return_NtStatus(
               retaddr,
               (void *)0xA6,
               (unsigned int)"onecore\\base\\ngscb\\wldp\\dll\\applicationsetting.cpp",
               v1,
               ReturnLength);
LABEL_11:
    SystemInformation = 0;
    return result;
  }
  if ( !ReturnLength )
  {
    result = -2147023728;
    goto LABEL_11;
  }
  unique_hlocal = wil::make_unique_hlocal_nothrow<unsigned char [0]>(&hMem, ReturnLength);
  wistd::unique_ptr<unsigned char [0],wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::operator=(
    &SystemInformation,
    unique_hlocal);
  v4 = hMem;
  hMem = 0;
  if ( v4 )
    LocalFree(v4);
  v5 = SystemInformation;
  if ( !SystemInformation )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xAE,
      (unsigned int)"onecore\\base\\ngscb\\wldp\\dll\\applicationsetting.cpp",
      (const char *)0x8007000ELL,
      ReturnLength);
    result = -2147024882;
    goto LABEL_11;
  }
  TestsigningPolicy = NtQuerySystemInformation(
                        SystemProcessorPowerInformation|0x80,
                        SystemInformation,
                        ReturnLength,
                        &ReturnLength);
  if ( TestsigningPolicy < 0 )
  {
    v7 = 179;
LABEL_14:
    v8 = wil::details::in1diag3::Return_NtStatus(
           retaddr,
           (void *)v7,
           (unsigned int)"onecore\\base\\ngscb\\wldp\\dll\\applicationsetting.cpp",
           (const char *)(unsigned int)TestsigningPolicy,
           ReturnLength);
    SystemInformation = 0;
    if ( v5 )
      LocalFree(v5);
    return v8;
  }
  TestsigningPolicy = SIPolicyGetTestsigningPolicy(&v15, &v14);
  if ( TestsigningPolicy < 0 )
  {
    v7 = 181;
    goto LABEL_14;
  }
  LOBYTE(v10) = v14;
  LOBYTE(v9) = v15;
  TestsigningPolicy = SIPolicyInitializeFromSerializedPolicies(v5, ReturnLength, v9, v10);
  if ( TestsigningPolicy < 0 )
  {
    v7 = 186;
    goto LABEL_14;
  }
  SystemInformation = 0;
  if ( v5 )
    LocalFree(v5);
  return 0;
}

```

## disassembly

```asm
0x18001de88  push    rbp
0x18001de8a  push    rbx
0x18001de8b  push    rdi
0x18001de8c  mov     rbp, rsp
0x18001de8f  sub     rsp, 30h
0x18001de93  mov     [rbp+ReturnLength], 0
0x18001de9a  mov     [rbp+arg_8], 0
0x18001de9e  mov     [rbp+arg_0], 0
0x18001dea2  mov     [rbp+SystemInformation], 0
0x18001deaa  lea     r9, [rbp+ReturnLength]; ReturnLength
0x18001deae  xor     r8d, r8d; SystemInformationLength
0x18001deb1  xor     edx, edx; SystemInformation
0x18001deb3  mov     edi, 0BDh
0x18001deb8  mov     ecx, edi; SystemInformationClass
0x18001deba  call    cs:__imp_NtQuerySystemInformation
0x18001dec0  xor     r9d, r9d
0x18001dec3  cmp     eax, 0C0000004h
0x18001dec8  cmovnz  r9d, eax; char *
0x18001decc  test    r9d, r9d
0x18001decf  jns     short loc_18001DEE6
0x18001ded1  mov     rcx, [rbp+18h]; this
0x18001ded5  lea     r8, aOnecoreBaseNgs_9; "onecore\\base\\ngscb\\wldp\\dll\\applic"...
0x18001dedc  lea     edx, [rdi-17h]; void *
0x18001dedf  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18001dee4  jmp     short loc_18001DF4D
0x18001dee6  mov     eax, [rbp+ReturnLength]
0x18001dee9  test    eax, eax
0x18001deeb  jnz     short loc_18001DEF4
0x18001deed  mov     eax, 80070490h
0x18001def2  jmp     short loc_18001DF4D
0x18001def4  mov     rdx, rax
0x18001def7  lea     rcx, [rbp+hMem]
0x18001defb  call    ??$make_unique_hlocal_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_hlocal_nothrow<uchar [0]>(unsigned __int64)
0x18001df00  nop
0x18001df01  mov     rdx, rax
0x18001df04  lea     rcx, [rbp+SystemInformation]
0x18001df08  call    ??4?$unique_ptr@$$BY0A@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<uchar [0],wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::operator=(wistd::unique_ptr<uchar [0],wil::function_deleter<void * (*)(void *),&LocalFree(void *)>> &&)
0x18001df0d  nop
0x18001df0e  mov     rcx, [rbp+hMem]; hMem
0x18001df12  mov     [rbp+hMem], 0
0x18001df1a  test    rcx, rcx
0x18001df1d  jz      short loc_18001DF25
0x18001df1f  call    cs:__imp_LocalFree
0x18001df25  mov     rbx, [rbp+SystemInformation]
0x18001df29  test    rbx, rbx
0x18001df2c  jnz     short loc_18001DF5A
0x18001df2e  mov     rcx, [rbp+18h]; this
0x18001df32  mov     ebx, 8007000Eh
0x18001df37  mov     r9d, ebx; char *
0x18001df3a  lea     r8, aOnecoreBaseNgs_9; "onecore\\base\\ngscb\\wldp\\dll\\applic"...
0x18001df41  mov     edx, 0AEh; void *
0x18001df46  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001df4b  mov     eax, ebx
0x18001df4d  mov     [rbp+SystemInformation], 0
0x18001df55  jmp     loc_18001DFF3
0x18001df5a  lea     r9, [rbp+ReturnLength]; ReturnLength
0x18001df5e  mov     r8d, [rbp+ReturnLength]; SystemInformationLength
0x18001df62  mov     rdx, rbx; SystemInformation
0x18001df65  mov     ecx, edi; SystemInformationClass
0x18001df67  call    cs:__imp_NtQuerySystemInformation
0x18001df6d  test    eax, eax
0x18001df6f  jns     short loc_18001DFA5
0x18001df71  mov     edx, 0B3h; void *
0x18001df76  mov     rcx, [rbp+18h]; this
0x18001df7a  mov     r9d, eax; char *
0x18001df7d  lea     r8, aOnecoreBaseNgs_9; "onecore\\base\\ngscb\\wldp\\dll\\applic"...
0x18001df84  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18001df89  mov     edi, eax
0x18001df8b  mov     [rbp+SystemInformation], 0
0x18001df93  test    rbx, rbx
0x18001df96  jz      short loc_18001DFA1
0x18001df98  mov     rcx, rbx; hMem
0x18001df9b  call    cs:__imp_LocalFree
0x18001dfa1  mov     eax, edi
0x18001dfa3  jmp     short loc_18001DFF3
0x18001dfa5  lea     rdx, [rbp+arg_0]
0x18001dfa9  lea     rcx, [rbp+arg_8]
0x18001dfad  call    SIPolicyGetTestsigningPolicy
0x18001dfb2  test    eax, eax
0x18001dfb4  jns     short loc_18001DFBD
0x18001dfb6  mov     edx, 0B5h
0x18001dfbb  jmp     short loc_18001DF76
0x18001dfbd  mov     r9b, [rbp+arg_0]
0x18001dfc1  mov     r8b, [rbp+arg_8]
0x18001dfc5  mov     edx, [rbp+ReturnLength]
0x18001dfc8  mov     rcx, rbx
0x18001dfcb  call    SIPolicyInitializeFromSerializedPolicies
0x18001dfd0  test    eax, eax
0x18001dfd2  jns     short loc_18001DFDB
0x18001dfd4  mov     edx, 0BAh
0x18001dfd9  jmp     short loc_18001DF76
0x18001dfdb  mov     [rbp+SystemInformation], 0
0x18001dfe3  test    rbx, rbx
0x18001dfe6  jz      short loc_18001DFF1
0x18001dfe8  mov     rcx, rbx; hMem
0x18001dfeb  call    cs:__imp_LocalFree
0x18001dff1  xor     eax, eax
0x18001dff3  add     rsp, 30h
0x18001dff7  pop     rdi
0x18001dff8  pop     rbx
0x18001dff9  pop     rbp
0x18001dffa  retn
```
