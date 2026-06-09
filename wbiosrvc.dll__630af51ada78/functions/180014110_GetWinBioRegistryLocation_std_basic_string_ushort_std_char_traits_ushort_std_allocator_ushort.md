# GetWinBioRegistryLocation(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *)

- ea: `0x180014110`
- end: `0x180014236`
- name: `?GetWinBioRegistryLocation@@YAJPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `294`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `34`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180013230`
- `0x18001358c`
- `0x180013c78`
- `0x180015744`
- `0x180016650`
- `0x180016e10`
- `0x180026b28`
- `0x180028478`
- `0x1800288b4`
- `0x18003a39c`
- `0x18003f4b8`
- `0x180045044`
- `0x180046664`
- `0x180051284`
- `0x180053ff0`
- `0x1800579a0`
- `0x180063cf8`
- `0x18006561c`
- `0x1800687a8`
- `0x180071de8`
- `0x1800727a0`
- `0x1800730ec`
- `0x180073538`
- `0x180073c84`
- `0x180073dac`
- `0x180073ee4`
- `0x180077c7c`
- `0x180077d64`
- `0x180077fcc`
- `0x180078350`
- `0x180080924`
- `0x1800be168`
- `0x1800be44c`
- `0x1800be5e8`

## callees

- `0x1800058ec`
- `0x180011d90`
- `0x180014110`
- `0x18001423c`
- `0x1800148b4`
- `0x1800530c4`
- `0x18005388c`
- `0x180060254`

## import_xrefs

- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180014143`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x18001419c`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180014143`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x18001419c`

## string_xrefs

- `0x1800141fc`: `onecore\ds\security\biometrics\service\common\biostatesep.cpp`
- `0x180014217`: `onecore\ds\security\biometrics\service\common\biostatesep.cpp`

## pseudocode

```c
__int64 __fastcall GetWinBioRegistryLocation(__int64 a1)
{
  int PersistedRegistryLocationW; // eax
  unsigned int v3; // ebx
  __int64 v4; // rbx
  unsigned int v5; // eax
  __int128 v7; // [rsp+30h] [rbp-28h] BYREF
  __int64 v8; // [rsp+40h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  unsigned int v10; // [rsp+68h] [rbp+10h] BYREF

  v10 = 0;
  PersistedRegistryLocationW = GetPersistedRegistryLocationW(
                                 L"WinBio",
                                 L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\WinBio\\",
                                 0,
                                 0);
  v3 = PersistedRegistryLocationW;
  if ( PersistedRegistryLocationW != 234 )
  {
    if ( PersistedRegistryLocationW > 0 )
      v3 = (unsigned __int16)PersistedRegistryLocationW | 0x80070000;
    if ( (v3 & 0x80000000) != 0 )
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x14,
        (unsigned int)"onecore\\ds\\security\\biometrics\\service\\common\\biostatesep.cpp",
        (const char *)v3,
        (int)&v10);
    return v3;
  }
  v7 = 0;
  v8 = 0;
  std::vector<unsigned char>::_Construct_n<>(&v7, v10);
  v4 = v7;
  v5 = GetPersistedRegistryLocationW(L"WinBio", L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\WinBio\\", v7, v10);
  if ( v5 )
  {
    v3 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x1C,
           (unsigned int)"onecore\\ds\\security\\biometrics\\service\\common\\biostatesep.cpp",
           (const char *)v5,
           (unsigned int)&v10);
    std::vector<unsigned char>::_Tidy(&v7);
    return v3;
  }
  std::_WChar_traits<unsigned short>::length(v4);
  std::wstring::_Assign<unsigned short>(a1, v4);
  if ( v4 )
    std::_Deallocate<16>(v4, v8 - v4);
  return 0;
}

```

## disassembly

```asm
0x180014110  mov     [rsp+arg_0], rbx
0x180014115  push    rdi
0x180014116  sub     rsp, 50h
0x18001411a  mov     rdi, rcx
0x18001411d  mov     [rsp+58h+arg_8], 0
0x180014125  lea     rax, [rsp+58h+arg_8]
0x18001412a  mov     qword ptr [rsp+58h+var_38], rax; int
0x18001412f  xor     r9d, r9d
0x180014132  xor     r8d, r8d
0x180014135  lea     rdx, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18001413c  lea     rcx, aWinbio; "WinBio"
0x180014143  call    cs:__imp_GetPersistedRegistryLocationW
0x180014149  mov     ebx, eax
0x18001414b  cmp     eax, 0EAh
0x180014150  jnz     loc_1800141DF
0x180014156  xorps   xmm0, xmm0
0x180014159  movdqu  [rsp+58h+var_28], xmm0
0x18001415f  mov     [rsp+58h+var_18], 0
0x180014168  mov     edx, [rsp+58h+arg_8]
0x18001416c  lea     rcx, [rsp+58h+var_28]
0x180014171  call    ??$_Construct_n@$$V@?$vector@EV?$allocator@E@std@@@std@@AEAAX_K@Z; std::vector<uchar>::_Construct_n<>(unsigned __int64)
0x180014176  nop
0x180014177  lea     rax, [rsp+58h+arg_8]
0x18001417c  mov     qword ptr [rsp+58h+var_38], rax; unsigned int
0x180014181  mov     r9d, [rsp+58h+arg_8]
0x180014186  mov     rbx, qword ptr [rsp+58h+var_28]
0x18001418b  mov     r8, rbx
0x18001418e  lea     rdx, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180014195  lea     rcx, aWinbio; "WinBio"
0x18001419c  call    cs:__imp_GetPersistedRegistryLocationW
0x1800141a2  test    eax, eax
0x1800141a4  jnz     short loc_18001420F
0x1800141a6  mov     rcx, rbx
0x1800141a9  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x1800141ae  mov     r8, rax
0x1800141b1  mov     rdx, rbx
0x1800141b4  mov     rcx, rdi
0x1800141b7  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800141bc  nop
0x1800141bd  test    rbx, rbx
0x1800141c0  jz      short loc_1800141D2
0x1800141c2  mov     rdx, [rsp+58h+var_18]
0x1800141c7  sub     rdx, rbx
0x1800141ca  mov     rcx, rbx
0x1800141cd  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800141d2  xor     eax, eax
0x1800141d4  mov     rbx, [rsp+58h+arg_0]
0x1800141d9  add     rsp, 50h
0x1800141dd  pop     rdi
0x1800141de  retn
0x1800141df  test    eax, eax
0x1800141e1  jle     short loc_1800141EC
0x1800141e3  movzx   ebx, ax
0x1800141e6  or      ebx, 80070000h
0x1800141ec  test    ebx, ebx
0x1800141ee  js      short loc_1800141F4
0x1800141f0  mov     eax, ebx
0x1800141f2  jmp     short loc_1800141D4
0x1800141f4  mov     rcx, [rsp+58h]; this
0x1800141f9  mov     r9d, ebx; char *
0x1800141fc  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\biometrics\\serv"...
0x180014203  mov     edx, 14h; void *
0x180014208  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001420d  jmp     short loc_1800141F0
0x18001420f  mov     rcx, [rsp+58h]; this
0x180014214  mov     r9d, eax; char *
0x180014217  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\biometrics\\serv"...
0x18001421e  mov     edx, 1Ch; void *
0x180014223  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180014228  mov     ebx, eax
0x18001422a  lea     rcx, [rsp+58h+var_28]
0x18001422f  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180014234  jmp     short loc_1800141F0
```
