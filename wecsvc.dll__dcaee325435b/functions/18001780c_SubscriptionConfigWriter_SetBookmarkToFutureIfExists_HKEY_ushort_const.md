# SubscriptionConfigWriter::SetBookmarkToFutureIfExists(HKEY__ *,ushort const *)

- ea: `0x18001780c`
- end: `0x1800178e7`
- name: `?SetBookmarkToFutureIfExists@SubscriptionConfigWriter@@AEAAXPEAUHKEY__@@PEBG@Z`
- size: `219`
- prototype: `void __fastcall(SubscriptionConfigWriter *this, HKEY, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18001718c`

## callees

- `0x180003810`
- `0x180003e6c`
- `0x1800062d4`
- `0x1800128c0`
- `0x180012b94`
- `0x18001780c`
- `0x18001fe50`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001784c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001784c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall SubscriptionConfigWriter::SetBookmarkToFutureIfExists(
        SubscriptionConfigWriter *this,
        HKEY a2,
        const unsigned __int16 *a3)
{
  HKEY phkResult; // [rsp+30h] [rbp-50h] BYREF
  _QWORD v4[4]; // [rsp+38h] [rbp-48h] BYREF
  __int64 v5[4]; // [rsp+58h] [rbp-28h] BYREF

  phkResult = 0;
  if ( RegOpenKeyExW(a2, a3, 0, 0x2001Fu, &phkResult) != 2 )
  {
    v4[3] = 7;
    v4[2] = 0;
    LOWORD(v4[0]) = 0;
    if ( RegReadStringValue(phkResult, L"Bookmark", (__int64)v4) )
    {
      std::wstring::wstring((__int64)v5, (__int64)&word_180026AD8);
      RegWriteStringValue(phkResult, L"Bookmark", v5);
      std::wstring::_Tidy(v5, 1, 0);
    }
    std::wstring::_Tidy(v4, 1, 0);
  }
  wmi::AutoRegKey::Close(&phkResult);
}

```

## disassembly

```asm
0x18001780c  push    rbp
0x18001780e  mov     rbp, rsp
0x180017811  sub     rsp, 80h
0x180017818  mov     rax, cs:__security_cookie
0x18001781f  xor     rax, rsp
0x180017822  mov     [rbp+var_8], rax
0x180017826  mov     r10, r8
0x180017829  mov     rax, rdx
0x18001782c  mov     [rbp+var_50], 0
0x180017834  lea     rcx, [rbp+var_50]
0x180017838  mov     [rsp+80h+phkResult], rcx; phkResult
0x18001783d  mov     r9d, 2001Fh; samDesired
0x180017843  xor     r8d, r8d; ulOptions
0x180017846  mov     rdx, r10; lpSubKey
0x180017849  mov     rcx, rax; hKey
0x18001784c  call    cs:__imp_RegOpenKeyExW
0x180017852  cmp     eax, 2
0x180017855  jz      short loc_1800178C9
0x180017857  mov     [rbp+var_30], 7
0x18001785f  mov     [rbp+var_38], 0
0x180017867  xor     eax, eax
0x180017869  mov     [rbp+var_48], ax
0x18001786d  lea     r8, [rbp+var_48]
0x180017871  lea     rdx, aBookmark; "Bookmark"
0x180017878  mov     rcx, [rbp+var_50]
0x18001787c  call    ?RegReadStringValue@@YA_NPEAUHKEY__@@PEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; RegReadStringValue(HKEY__ *,ushort const *,std::wstring &)
0x180017881  test    al, al
0x180017883  jz      short loc_1800178BA
0x180017885  lea     rdx, word_180026AD8
0x18001788c  lea     rcx, [rbp+var_28]
0x180017890  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180017895  nop
0x180017896  lea     r8, [rbp+var_28]
0x18001789a  lea     rdx, aBookmark; "Bookmark"
0x1800178a1  mov     rcx, [rbp+var_50]
0x1800178a5  call    ?RegWriteStringValue@@YAXPEAUHKEY__@@PEBGAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; RegWriteStringValue(HKEY__ *,ushort const *,std::wstring const &)
0x1800178aa  nop
0x1800178ab  xor     r8d, r8d
0x1800178ae  mov     dl, 1
0x1800178b0  lea     rcx, [rbp+var_28]
0x1800178b4  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800178b9  nop
0x1800178ba  xor     r8d, r8d
0x1800178bd  mov     dl, 1
0x1800178bf  lea     rcx, [rbp+var_48]
0x1800178c3  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800178c8  nop
0x1800178c9  lea     rcx, [rbp+var_50]; this
0x1800178cd  call    ?Close@AutoRegKey@wmi@@QEAAXXZ; wmi::AutoRegKey::Close(void)
0x1800178d2  mov     rcx, [rbp+var_8]
0x1800178d6  xor     rcx, rsp; StackCookie
0x1800178d9  call    __security_check_cookie
0x1800178de  add     rsp, 80h
0x1800178e5  pop     rbp
0x1800178e6  retn
```
