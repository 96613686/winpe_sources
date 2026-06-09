# CReportStore::GetMachineStoreDir(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)

- ea: `0x18000a9f0`
- end: `0x18000ac35`
- name: `?GetMachineStoreDir@CReportStore@@QEAAJPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z`
- size: `581`
- prototype: ``
- caller_count: `4`
- callee_count: `13`
- tags: `reparse_path, registry_config, loader_planting`

## callers

- `0x180009b78`
- `0x18000ac40`
- `0x18006aa00`
- `0x18006c310`

## callees

- `0x18000a9f0`
- `0x18000cf50`
- `0x18000db80`
- `0x1800170b0`
- `0x180025560`
- `0x180029e58`
- `0x18002ece4`
- `0x180031d00`
- `0x18003fb94`
- `0x1800459c0`
- `0x180053300`
- `0x180054568`
- `0x1800b2010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ab37`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000abc7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ab37`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000abc7`
- `ext-ms-win-wer-xbox-l1-1-0!XerGetMachineStorePath` at `0x18000aa56`
- `ext-ms-win-wer-xbox-l1-1-0!XerGetMachineStorePath` at `0x18000aa56`

## string_xrefs

- `0x18000aa70`: `onecore\windows\feedback\core\werdll\lib\reportstore.cpp`
- `0x18000ab9d`: `onecore\windows\feedback\core\werdll\lib\reportstore.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CReportStore::GetMachineStoreDir(__int64 (__fastcall ***a1)(_QWORD), _QWORD *a2)
{
  unsigned int v4; // ebx
  __int64 v5; // r9
  __int64 v6; // rdx
  int MachineStorePath; // eax
  const WCHAR *StorePath; // rax
  __int64 v9; // rax
  int v10; // eax
  LPCWSTR lpFileName[2]; // [rsp+20h] [rbp-E0h] BYREF
  char v13; // [rsp+30h] [rbp-D0h] BYREF
  LPVOID lpMem[2]; // [rsp+40h] [rbp-C0h] BYREF
  char v15; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR Src[264]; // [rsp+60h] [rbp-A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+198h]

  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(lpFileName);
  if ( !a2 )
  {
    v4 = -2147024809;
    v5 = 2147942487LL;
    v6 = 92;
LABEL_7:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecore\\windows\\feedback\\core\\werdll\\lib\\reportstore.cpp",
      (const char *)v5,
      (int)lpFileName[0]);
LABEL_29:
    utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(lpFileName);
    return v4;
  }
  if ( (unsigned __int8)IsXerGetMachineIdPresent() )
  {
    MachineStorePath = XerGetMachineStorePath(Src);
    v4 = MachineStorePath;
    if ( MachineStorePath < 0 )
    {
      v6 = 101;
LABEL_6:
      v5 = (unsigned int)MachineStorePath;
      goto LABEL_7;
    }
    MachineStorePath = UtilExpandEnvironmentStrings(Src);
    v4 = MachineStorePath;
    if ( MachineStorePath < 0 )
    {
      v6 = 102;
      goto LABEL_6;
    }
  }
  else
  {
    StorePath = CSettings::GetStorePath((CSettings *)(a1 + 9));
    MachineStorePath = UtilExpandEnvironmentStrings(StorePath);
    v4 = MachineStorePath;
    if ( MachineStorePath < 0 )
    {
      v6 = 109;
      goto LABEL_6;
    }
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_c7d90b7e9c5e35268a88cfd8be5fc765_Traceguids, lpFileName[0]);
  }
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(lpMem);
  if ( (unsigned int)UtilGetFinalPath(lpFileName[0]) )
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::operator=(lpFileName, lpMem);
  if ( lpMem[0] != &v15 )
    HeapFree(g_hWerheap, 0, lpMem[0]);
  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_c7d90b7e9c5e35268a88cfd8be5fc765_Traceguids, lpFileName[0]);
  v9 = (**a1)(a1);
  v10 = CPath::Append(lpFileName[0], v9, a2);
  v4 = v10;
  if ( v10 >= 0 )
  {
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_c7d90b7e9c5e35268a88cfd8be5fc765_Traceguids, *a2);
    v4 = 0;
    goto LABEL_29;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x7B,
    (unsigned int)"onecore\\windows\\feedback\\core\\werdll\\lib\\reportstore.cpp",
    (const char *)(unsigned int)v10,
    (int)lpFileName[0]);
  if ( (char *)lpFileName[0] != &v13 )
    HeapFree(g_hWerheap, 0, (LPVOID)lpFileName[0]);
  return v4;
}

```

## disassembly

```asm
0x18000a9f0  mov     [rsp-8+arg_10], rbx
0x18000a9f5  mov     [rsp-8+arg_18], rsi
0x18000a9fa  push    rbp
0x18000a9fb  push    rdi
0x18000a9fc  push    r15
0x18000a9fe  lea     rbp, [rsp-180h]
0x18000aa06  sub     rsp, 280h
0x18000aa0d  mov     rax, cs:__security_cookie
0x18000aa14  xor     rax, rsp
0x18000aa17  mov     [rbp+190h+var_20], rax
0x18000aa1e  mov     rdi, rdx
0x18000aa21  mov     rsi, rcx
0x18000aa24  lea     rcx, [rsp+290h+lpFileName]; void *
0x18000aa29  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x18000aa2e  nop
0x18000aa2f  test    rdi, rdi
0x18000aa32  jnz     short loc_18000AA41
0x18000aa34  mov     ebx, 80070057h
0x18000aa39  mov     r9d, ebx
0x18000aa3c  lea     edx, [rdi+5Ch]
0x18000aa3f  jmp     short loc_18000AA70
0x18000aa41  call    IsXerGetMachineIdPresent
0x18000aa46  lea     r15, WPP_GLOBAL_Control
0x18000aa4d  test    al, al
0x18000aa4f  jz      short loc_18000AAA4
0x18000aa51  lea     rcx, [rsp+290h+Src]
0x18000aa56  call    cs:__imp_XerGetMachineStorePath
0x18000aa5d  nop     dword ptr [rax+rax+00h]
0x18000aa62  mov     ebx, eax
0x18000aa64  test    eax, eax
0x18000aa66  jns     short loc_18000AA88
0x18000aa68  mov     edx, 65h ; 'e'; void *
0x18000aa6d  mov     r9d, eax; char *
0x18000aa70  lea     r8, aOnecoreWindows_2; "onecore\\windows\\feedback\\core\\werdl"...
0x18000aa77  mov     rcx, [rbp+198h]; this
0x18000aa7e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000aa83  jmp     loc_18000AC01
0x18000aa88  lea     rdx, [rsp+290h+lpFileName]
0x18000aa8d  lea     rcx, [rsp+290h+Src]; lpSrc
0x18000aa92  call    ?UtilExpandEnvironmentStrings@@YAJPEB_WPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; UtilExpandEnvironmentStrings(wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x18000aa97  mov     ebx, eax
0x18000aa99  test    eax, eax
0x18000aa9b  jns     short loc_18000AAF3
0x18000aa9d  mov     edx, 66h ; 'f'
0x18000aaa2  jmp     short loc_18000AA6D
0x18000aaa4  lea     rcx, [rsi+48h]; this
0x18000aaa8  call    ?GetStorePath@CSettings@@QEBAPEB_WXZ; CSettings::GetStorePath(void)
0x18000aaad  mov     rcx, rax; lpSrc
0x18000aab0  lea     rdx, [rsp+290h+lpFileName]
0x18000aab5  call    ?UtilExpandEnvironmentStrings@@YAJPEB_WPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; UtilExpandEnvironmentStrings(wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x18000aaba  mov     ebx, eax
0x18000aabc  test    eax, eax
0x18000aabe  jns     short loc_18000AAC7
0x18000aac0  mov     edx, 6Dh ; 'm'
0x18000aac5  jmp     short loc_18000AA6D
0x18000aac7  mov     rcx, cs:WPP_GLOBAL_Control
0x18000aace  cmp     rcx, r15
0x18000aad1  jz      short loc_18000AAF3
0x18000aad3  test    byte ptr [rcx+1Ch], 4
0x18000aad7  jz      short loc_18000AAF3
0x18000aad9  mov     edx, 0Ah
0x18000aade  mov     r9, [rsp+290h+lpFileName]
0x18000aae3  lea     r8, WPP_c7d90b7e9c5e35268a88cfd8be5fc765_Traceguids
0x18000aaea  mov     rcx, [rcx+10h]
0x18000aaee  call    WPP_SF_S
0x18000aaf3  lea     rcx, [rsp+290h+lpMem]; void *
0x18000aaf8  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x18000aafd  lea     rdx, [rsp+290h+lpMem]
0x18000ab02  mov     rcx, [rsp+290h+lpFileName]; lpFileName
0x18000ab07  call    ?UtilGetFinalPath@@YAHPEB_WAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; UtilGetFinalPath(wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)
0x18000ab0c  test    eax, eax
0x18000ab0e  jz      short loc_18000AB1F
0x18000ab10  lea     rdx, [rsp+290h+lpMem]
0x18000ab15  lea     rcx, [rsp+290h+lpFileName]
0x18000ab1a  call    ??4?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::operator=(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &&)
0x18000ab1f  lea     rax, [rsp+290h+var_240]
0x18000ab24  mov     r8, [rsp+290h+lpMem]; lpMem
0x18000ab29  cmp     r8, rax
0x18000ab2c  jz      short loc_18000AB43
0x18000ab2e  xor     edx, edx; dwFlags
0x18000ab30  mov     rcx, cs:?g_hWerheap@@3PEAXEA; hHeap
0x18000ab37  call    cs:__imp_HeapFree
0x18000ab3e  nop     dword ptr [rax+rax+00h]
0x18000ab43  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ab4a  cmp     rcx, r15
0x18000ab4d  jz      short loc_18000AB6F
0x18000ab4f  test    byte ptr [rcx+1Ch], 4
0x18000ab53  jz      short loc_18000AB6F
0x18000ab55  mov     edx, 0Bh
0x18000ab5a  mov     r9, [rsp+290h+lpFileName]
0x18000ab5f  lea     r8, WPP_c7d90b7e9c5e35268a88cfd8be5fc765_Traceguids
0x18000ab66  mov     rcx, [rcx+10h]
0x18000ab6a  call    WPP_SF_S
0x18000ab6f  mov     rax, [rsi]
0x18000ab72  mov     rcx, rsi
0x18000ab75  mov     rax, [rax]
0x18000ab78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ab7d  mov     r8, rdi
0x18000ab80  mov     rdx, rax
0x18000ab83  mov     rcx, [rsp+290h+lpFileName]
0x18000ab88  call    ?Append@CPath@@SAJPEB_W0PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; CPath::Append(wchar_t const *,wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x18000ab8d  mov     ebx, eax
0x18000ab8f  test    eax, eax
0x18000ab91  jns     short loc_18000ABD5
0x18000ab93  mov     rcx, [rbp+198h]; this
0x18000ab9a  mov     r9d, eax; char *
0x18000ab9d  lea     r8, aOnecoreWindows_2; "onecore\\windows\\feedback\\core\\werdl"...
0x18000aba4  mov     edx, 7Bh ; '{'; void *
0x18000aba9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000abae  nop
0x18000abaf  lea     rax, [rsp+290h+var_260]
0x18000abb4  mov     r8, [rsp+290h+lpFileName]; lpMem
0x18000abb9  cmp     r8, rax
0x18000abbc  jz      short loc_18000AC0B
0x18000abbe  xor     edx, edx; dwFlags
0x18000abc0  mov     rcx, cs:?g_hWerheap@@3PEAXEA; hHeap
0x18000abc7  call    cs:__imp_HeapFree
0x18000abce  nop     dword ptr [rax+rax+00h]
0x18000abd3  jmp     short loc_18000AC0B
0x18000abd5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000abdc  cmp     rcx, r15
0x18000abdf  jz      short loc_18000ABFF
0x18000abe1  test    byte ptr [rcx+1Ch], 4
0x18000abe5  jz      short loc_18000ABFF
0x18000abe7  mov     edx, 0Ch
0x18000abec  mov     r9, [rdi]
0x18000abef  lea     r8, WPP_c7d90b7e9c5e35268a88cfd8be5fc765_Traceguids
0x18000abf6  mov     rcx, [rcx+10h]
0x18000abfa  call    WPP_SF_S
0x18000abff  xor     ebx, ebx
0x18000ac01  lea     rcx, [rsp+290h+lpFileName]; void *
0x18000ac06  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x18000ac0b  mov     eax, ebx
0x18000ac0d  mov     rcx, [rbp+190h+var_20]
0x18000ac14  xor     rcx, rsp; StackCookie
0x18000ac17  call    __security_check_cookie
0x18000ac1c  lea     r11, [rsp+290h+var_10]
0x18000ac24  mov     rbx, [r11+30h]
0x18000ac28  mov     rsi, [r11+38h]
0x18000ac2c  mov     rsp, r11
0x18000ac2f  pop     r15
0x18000ac31  pop     rdi
0x18000ac32  pop     rbp
0x18000ac33  retn
```
