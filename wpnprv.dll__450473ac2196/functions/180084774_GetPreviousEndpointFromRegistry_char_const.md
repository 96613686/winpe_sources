# GetPreviousEndpointFromRegistry(char const *)

- ea: `0x180084774`
- end: `0x1800848dd`
- name: `?GetPreviousEndpointFromRegistry@@YA?BV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEBD@Z`
- size: `361`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180071e6c`

## callees

- `0x180008294`
- `0x18000fe0c`
- `0x180010698`
- `0x180045028`
- `0x18004e768`
- `0x180066964`
- `0x1800844a4`
- `0x180084774`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800847c3`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180084887`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800847c3`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180084887`

## string_xrefs

- `0x1800848c2`: `client.wns.windows.com`
- `0x1800847e5`: `onecoreuap\base\diagnosis\platform\notifications\common\wpnlib.cpp`
- `0x180084898`: `onecoreuap\base\diagnosis\platform\notifications\common\wpnlib.cpp`

## pseudocode

```c
__int64 __fastcall GetPreviousEndpointFromRegistry(__int64 a1, __int64 a2)
{
  char *v3; // rsi
  char *v4; // rax
  size_t v5; // rbx
  unsigned int ValueW; // eax
  int pdwType; // [rsp+20h] [rbp-48h]
  unsigned int pdwTypea; // [rsp+20h] [rbp-48h]
  PVOID pvData; // [rsp+48h] [rbp-20h] BYREF
  void *v11; // [rsp+50h] [rbp-18h]
  __int64 v12; // [rsp+58h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+20h]
  DWORD pcbData; // [rsp+98h] [rbp+30h] BYREF
  int v15; // [rsp+9Ch] [rbp+34h]

  v15 = HIDWORD(a2);
  pcbData = 0;
  if ( RegGetValueW(
         HKEY_CURRENT_USER,
         L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\PushNotifications\\DeviceInfo",
         L"PreviousEndpoint",
         2u,
         0,
         0,
         &pcbData) )
  {
    std::string::string(a1, "client.wns.windows.com");
    return a1;
  }
  if ( !pcbData )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x837,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\common\\wpnlib.cpp",
      (const char *)0x8000FFFFLL,
      pdwType);
  std::vector<std::wstring>::vector<std::wstring>(&pvData);
  v3 = (char *)v11;
  if ( pcbData < (unsigned __int64)((_BYTE *)v11 - (_BYTE *)pvData) )
  {
    v4 = (char *)pvData + pcbData;
LABEL_10:
    v11 = v4;
    goto LABEL_11;
  }
  if ( pcbData > (unsigned __int64)((_BYTE *)v11 - (_BYTE *)pvData) )
  {
    if ( pcbData <= (unsigned __int64)(v12 - (_QWORD)pvData) )
    {
      v5 = pcbData - ((_BYTE *)v11 - (_BYTE *)pvData);
      memset_0(v11, 0, v5);
      v4 = &v3[v5];
      goto LABEL_10;
    }
    std::vector<char>::_Resize_reallocate<std::_Value_init_tag>(&pvData, pcbData);
  }
LABEL_11:
  ValueW = RegGetValueW(
             HKEY_CURRENT_USER,
             L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\PushNotifications\\DeviceInfo",
             L"PreviousEndpoint",
             2u,
             0,
             pvData,
             &pcbData);
  if ( ValueW )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x83B,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\common\\wpnlib.cpp",
      (const char *)ValueW,
      pdwTypea);
  std::string::string(a1, pvData);
  std::vector<char>::_Tidy(&pvData);
  return a1;
}

```

## disassembly

```asm
0x180084774  mov     r11, rsp
0x180084777  mov     [r11+10h], rdx
0x18008477b  push    rbp
0x18008477c  push    rbx
0x18008477d  push    rsi
0x18008477e  push    rdi
0x18008477f  mov     rbp, rsp
0x180084782  sub     rsp, 68h
0x180084786  mov     rdi, rcx
0x180084789  mov     [rbp+arg_8], 0
0x180084790  lea     rax, [rbp+arg_8]
0x180084794  mov     [r11-58h], rax
0x180084798  mov     qword ptr [r11-60h], 0
0x1800847a0  mov     qword ptr [r11-68h], 0
0x1800847a8  mov     r9d, 2; dwFlags
0x1800847ae  lea     r8, aPreviousendpoi; "PreviousEndpoint"
0x1800847b5  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1800847bc  mov     rcx, 0FFFFFFFF80000001h; hkey
0x1800847c3  call    cs:__imp_RegGetValueW
0x1800847c9  test    eax, eax
0x1800847cb  jnz     loc_1800848C2
0x1800847d1  cmp     [rbp+arg_8], eax
0x1800847d4  setz    al
0x1800847d7  mov     rcx, [rbp+20h]; this
0x1800847db  test    al, al
0x1800847dd  jz      short loc_1800847F7
0x1800847df  mov     r9d, 8000FFFFh; char *
0x1800847e5  lea     r8, aOnecoreuapBase_5; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800847ec  mov     edx, 837h; void *
0x1800847f1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800847f7  lea     rcx, [rbp+var_20]
0x1800847fb  call    ??0?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::wstring>::vector<std::wstring>(void)
0x180084800  nop
0x180084801  mov     ebx, [rbp+arg_8]
0x180084804  mov     rdx, [rbp+var_20]
0x180084808  mov     rsi, [rbp+var_18]
0x18008480c  mov     rcx, rsi
0x18008480f  sub     rcx, rdx
0x180084812  cmp     rbx, rcx
0x180084815  jnb     short loc_18008481D
0x180084817  lea     rax, [rbx+rdx]
0x18008481b  jmp     short loc_18008484D
0x18008481d  jbe     short loc_180084851
0x18008481f  mov     rax, [rbp+var_10]
0x180084823  sub     rax, rdx
0x180084826  cmp     rbx, rax
0x180084829  jbe     short loc_180084839
0x18008482b  mov     rdx, rbx
0x18008482e  lea     rcx, [rbp+var_20]
0x180084832  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@DV?$allocator@D@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<char>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x180084837  jmp     short loc_180084851
0x180084839  sub     rbx, rcx
0x18008483c  mov     r8, rbx; Size
0x18008483f  xor     edx, edx; Val
0x180084841  mov     rcx, rsi; void *
0x180084844  call    memset_0
0x180084849  lea     rax, [rbx+rsi]
0x18008484d  mov     [rbp+var_18], rax
0x180084851  mov     rax, [rbp+var_20]
0x180084855  lea     r10, [rbp+arg_8]
0x180084859  mov     [rsp+68h+pcbData], r10; pcbData
0x18008485e  mov     [rsp+68h+pvData], rax; pvData
0x180084863  mov     [rsp+68h+pdwType], 0; unsigned int
0x18008486c  mov     r9d, 2; dwFlags
0x180084872  lea     r8, aPreviousendpoi; "PreviousEndpoint"
0x180084879  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180084880  mov     rcx, 0FFFFFFFF80000001h; hkey
0x180084887  call    cs:__imp_RegGetValueW
0x18008488d  mov     rcx, [rbp+20h]; this
0x180084891  test    eax, eax
0x180084893  jz      short loc_1800848AA
0x180084895  mov     r9d, eax; char *
0x180084898  lea     r8, aOnecoreuapBase_5; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18008489f  mov     edx, 83Bh; void *
0x1800848a4  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x1800848aa  mov     rdx, [rbp+var_20]
0x1800848ae  mov     rcx, rdi
0x1800848b1  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800848b6  nop
0x1800848b7  lea     rcx, [rbp+var_20]
0x1800848bb  call    ?_Tidy@?$vector@DV?$allocator@D@std@@@std@@AEAAXXZ; std::vector<char>::_Tidy(void)
0x1800848c0  jmp     short loc_1800848D1
0x1800848c2  lea     rdx, aClientWnsWindo_0; "client.wns.windows.com"
0x1800848c9  mov     rcx, rdi
0x1800848cc  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800848d1  mov     rax, rdi
0x1800848d4  add     rsp, 68h
0x1800848d8  pop     rdi
0x1800848d9  pop     rsi
0x1800848da  pop     rbx
0x1800848db  pop     rbp
0x1800848dc  retn
```
