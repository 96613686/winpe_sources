# IsWindowsSetupComplete(void)

- ea: `0x14003c444`
- end: `0x14003c588`
- name: `?IsWindowsSetupComplete@@YAHXZ`
- size: `324`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x140052250`

## callees

- `0x140036d88`
- `0x14003c444`
- `0x140045f20`
- `0x140047798`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x14003c55b`
- `ADVAPI32!RegCloseKey` at `0x14003c55b`
- `ADVAPI32!RegOpenKeyExW` at `0x14003c4cd`
- `ADVAPI32!RegOpenKeyExW` at `0x14003c4cd`
- `KERNEL32!CompareStringOrdinal` at `0x14003c51f`
- `KERNEL32!CompareStringOrdinal` at `0x14003c51f`

## string_xrefs

- `0x14003c510`: `IMAGE_STATE_COMPLETE`

## pseudocode

```c
__int64 IsWindowsSetupComplete(void)
{
  HKEY v0; // rbx
  unsigned int v1; // edi
  HKEY phkResult; // [rsp+30h] [rbp-68h] BYREF
  _QWORD v4[3]; // [rsp+38h] [rbp-60h] BYREF
  WCHAR String1[24]; // [rsp+50h] [rbp-48h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, &WPP_2bf5d2a285bb3b5db5446f7e5dd5f28b_Traceguids);
  v0 = 0;
  v4[1] = 0;
  v4[2] = 0;
  phkResult = 0;
  v1 = 1;
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Setup\\State",
          0,
          0x20019u,
          &phkResult) )
  {
    v0 = phkResult;
    v4[0] = phkResult;
    LODWORD(phkResult) = 21;
    if ( (unsigned int)ATL::CRegKey::QueryStringValue(
                         (ATL::CRegKey *)v4,
                         L"ImageState",
                         String1,
                         (unsigned int *)&phkResult)
      || CompareStringOrdinal(String1, -1, L"IMAGE_STATE_COMPLETE", 20, 0) != 2 )
    {
      v1 = 0;
    }
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, &WPP_2bf5d2a285bb3b5db5446f7e5dd5f28b_Traceguids);
  if ( v0 )
    RegCloseKey(v0);
  return v1;
}

```

## disassembly

```asm
0x14003c444  mov     [rsp+arg_0], rbx
0x14003c449  mov     [rsp+arg_8], rbp
0x14003c44e  push    rdi
0x14003c44f  sub     rsp, 90h
0x14003c456  mov     rax, cs:__security_cookie
0x14003c45d  xor     rax, rsp
0x14003c460  mov     [rsp+98h+var_18], rax
0x14003c468  mov     rcx, cs:WPP_GLOBAL_Control
0x14003c46f  lea     rbp, WPP_GLOBAL_Control
0x14003c476  cmp     rcx, rbp
0x14003c479  jz      short loc_14003C496
0x14003c47b  test    byte ptr [rcx+1Ch], 1
0x14003c47f  jz      short loc_14003C496
0x14003c481  mov     rcx, [rcx+10h]
0x14003c485  lea     r8, WPP_2bf5d2a285bb3b5db5446f7e5dd5f28b_Traceguids
0x14003c48c  mov     edx, 26h ; '&'
0x14003c491  call    WPP_SF_
0x14003c496  xor     ebx, ebx
0x14003c498  lea     rax, [rsp+98h+var_68]
0x14003c49d  mov     r9d, 20019h; samDesired
0x14003c4a3  mov     [rsp+98h+var_58], rbx
0x14003c4a8  xor     r8d, r8d; ulOptions
0x14003c4ab  mov     [rsp+98h+var_50], rbx
0x14003c4b0  lea     rdx, aSoftwareMicros_6; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x14003c4b7  mov     [rsp+98h+var_68], rbx
0x14003c4bc  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14003c4c3  mov     [rsp+98h+phkResult], rax; phkResult
0x14003c4c8  mov     edi, 1
0x14003c4cd  call    cs:__imp_RegOpenKeyExW
0x14003c4d3  test    eax, eax
0x14003c4d5  jnz     short loc_14003C52C
0x14003c4d7  mov     rbx, [rsp+98h+var_68]
0x14003c4dc  lea     r9, [rsp+98h+var_68]; unsigned int *
0x14003c4e1  lea     r8, [rsp+98h+String1]; unsigned __int16 *
0x14003c4e6  mov     [rsp+98h+var_60], rbx
0x14003c4eb  lea     rdx, aImagestate; "ImageState"
0x14003c4f2  mov     dword ptr [rsp+98h+var_68], 15h
0x14003c4fa  lea     rcx, [rsp+98h+var_60]; this
0x14003c4ff  call    ?QueryStringValue@CRegKey@ATL@@QEAAJPEBGPEAGPEAK@Z; ATL::CRegKey::QueryStringValue(ushort const *,ushort *,ulong *)
0x14003c504  test    eax, eax
0x14003c506  jnz     short loc_14003C52A
0x14003c508  lea     r9d, [rdi+13h]; cchCount2
0x14003c50c  mov     dword ptr [rsp+98h+phkResult], eax; bIgnoreCase
0x14003c510  lea     r8, aImageStateComp; "IMAGE_STATE_COMPLETE"
0x14003c517  or      edx, 0FFFFFFFFh; cchCount1
0x14003c51a  lea     rcx, [rsp+98h+String1]; lpString1
0x14003c51f  call    cs:__imp_CompareStringOrdinal
0x14003c525  cmp     eax, 2
0x14003c528  jz      short loc_14003C52C
0x14003c52a  xor     edi, edi
0x14003c52c  mov     rcx, cs:WPP_GLOBAL_Control
0x14003c533  cmp     rcx, rbp
0x14003c536  jz      short loc_14003C553
0x14003c538  test    byte ptr [rcx+1Ch], 1
0x14003c53c  jz      short loc_14003C553
0x14003c53e  mov     rcx, [rcx+10h]
0x14003c542  lea     r8, WPP_2bf5d2a285bb3b5db5446f7e5dd5f28b_Traceguids
0x14003c549  mov     edx, 27h ; '''
0x14003c54e  call    WPP_SF_
0x14003c553  test    rbx, rbx
0x14003c556  jz      short loc_14003C561
0x14003c558  mov     rcx, rbx; hKey
0x14003c55b  call    cs:__imp_RegCloseKey
0x14003c561  mov     eax, edi
0x14003c563  mov     rcx, [rsp+98h+var_18]
0x14003c56b  xor     rcx, rsp; StackCookie
0x14003c56e  call    __security_check_cookie
0x14003c573  lea     r11, [rsp+98h+var_8]
0x14003c57b  mov     rbx, [r11+10h]
0x14003c57f  mov     rbp, [r11+18h]
0x14003c583  mov     rsp, r11
0x14003c586  pop     rdi
0x14003c587  retn
```
