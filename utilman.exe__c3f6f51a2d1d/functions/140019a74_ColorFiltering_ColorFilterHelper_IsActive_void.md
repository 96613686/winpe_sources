# ColorFiltering::ColorFilterHelper::IsActive(void)

- ea: `0x140019a74`
- end: `0x140019b61`
- name: `?IsActive@ColorFilterHelper@ColorFiltering@@SA_NXZ`
- size: `237`
- prototype: `bool(void)`
- caller_count: `4`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x14001aa78`
- `0x14001b2ec`
- `0x14001b470`
- `0x14001b5f4`

## callees

- `0x14000d75c`
- `0x14000ea8c`
- `0x14000eb0c`
- `0x140019a74`
- `0x14001b16c`

## string_xrefs

- `0x140019a98`: `Software\Microsoft\Windows NT\CurrentVersion\Accessibility\ATConfig\colorfiltering`

## pseudocode

```c
char ColorFiltering::ColorFilterHelper::IsActive(void)
{
  char v0; // bl
  _QWORD v2[3]; // [rsp+20h] [rbp-30h] BYREF
  _QWORD v3[3]; // [rsp+38h] [rbp-18h] BYREF
  unsigned int v4; // [rsp+60h] [rbp+10h] BYREF

  v0 = 1;
  v4 = 0;
  memset(v2, 0, sizeof(v2));
  if ( (unsigned int)ATL::CRegKey::Open(
                       (ATL::CRegKey *)v2,
                       HKEY_CURRENT_USER,
                       L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Accessibility\\ATConfig\\colorfiltering",
                       1u)
    || (unsigned int)ATL::CRegKey::QueryDWORDValue((ATL::CRegKey *)v2, L"Active", &v4)
    || !v4 )
  {
    memset(v3, 0, sizeof(v3));
    if ( (unsigned int)ATL::CRegKey::Open(
                         (ATL::CRegKey *)v3,
                         HKEY_CURRENT_USER,
                         L"Software\\Microsoft\\ColorFiltering",
                         1u)
      || (unsigned int)ATL::CRegKey::QueryDWORDValue((ATL::CRegKey *)v3, L"Active", &v4)
      || (ColorFiltering::ColorFilterHelper::UpdateTransferSettingsActive(v4 != 0), !v4) )
    {
      v0 = 0;
    }
    ATL::CRegKey::Close((ATL::CRegKey *)v3);
  }
  ATL::CRegKey::Close((ATL::CRegKey *)v2);
  return v0;
}

```

## disassembly

```asm
0x140019a74  mov     [rsp-8+arg_8], rbx
0x140019a79  push    rbp
0x140019a7a  mov     rbp, rsp
0x140019a7d  sub     rsp, 50h
0x140019a81  mov     ebx, 1
0x140019a86  mov     [rbp+arg_0], 0
0x140019a8d  mov     r9d, ebx; unsigned int
0x140019a90  mov     [rbp+var_30], 0
0x140019a98  lea     r8, aSoftwareMicros_12; "Software\\Microsoft\\Windows NT\\Curren"...
0x140019a9f  mov     [rbp+var_28], 0
0x140019aa7  mov     rdx, 0FFFFFFFF80000001h; hKey
0x140019aae  mov     [rbp+var_20], 0
0x140019ab6  lea     rcx, [rbp+var_30]; this
0x140019aba  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x140019abf  test    eax, eax
0x140019ac1  jnz     short loc_140019AE0
0x140019ac3  lea     r8, [rbp+arg_0]; unsigned int *
0x140019ac7  lea     rdx, aActive_0; "Active"
0x140019ace  lea     rcx, [rbp+var_30]; this
0x140019ad2  call    ?QueryDWORDValue@CRegKey@ATL@@QEAAJPEBGAEAK@Z; ATL::CRegKey::QueryDWORDValue(ushort const *,ulong &)
0x140019ad7  test    eax, eax
0x140019ad9  jnz     short loc_140019AE0
0x140019adb  cmp     [rbp+arg_0], eax
0x140019ade  jnz     short loc_140019B4A
0x140019ae0  mov     r9d, ebx; unsigned int
0x140019ae3  mov     [rbp+var_18], 0
0x140019aeb  lea     r8, aSoftwareMicros_13; "Software\\Microsoft\\ColorFiltering"
0x140019af2  mov     [rbp+var_10], 0
0x140019afa  mov     rdx, 0FFFFFFFF80000001h; hKey
0x140019b01  mov     [rbp+var_8], 0
0x140019b09  lea     rcx, [rbp+var_18]; this
0x140019b0d  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x140019b12  test    eax, eax
0x140019b14  jnz     short loc_140019B3F
0x140019b16  lea     r8, [rbp+arg_0]; unsigned int *
0x140019b1a  lea     rdx, aActive_0; "Active"
0x140019b21  lea     rcx, [rbp+var_18]; this
0x140019b25  call    ?QueryDWORDValue@CRegKey@ATL@@QEAAJPEBGAEAK@Z; ATL::CRegKey::QueryDWORDValue(ushort const *,ulong &)
0x140019b2a  test    eax, eax
0x140019b2c  jnz     short loc_140019B3F
0x140019b2e  cmp     [rbp+arg_0], eax
0x140019b31  setnz   cl; bool
0x140019b34  call    ?UpdateTransferSettingsActive@ColorFilterHelper@ColorFiltering@@SAX_N@Z; ColorFiltering::ColorFilterHelper::UpdateTransferSettingsActive(bool)
0x140019b39  cmp     [rbp+arg_0], 0
0x140019b3d  jnz     short loc_140019B41
0x140019b3f  xor     bl, bl
0x140019b41  lea     rcx, [rbp+var_18]; this
0x140019b45  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x140019b4a  lea     rcx, [rbp+var_30]; this
0x140019b4e  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x140019b53  mov     al, bl
0x140019b55  mov     rbx, [rsp+50h+arg_8]
0x140019b5a  add     rsp, 50h
0x140019b5e  pop     rbp
0x140019b5f  retn
```
