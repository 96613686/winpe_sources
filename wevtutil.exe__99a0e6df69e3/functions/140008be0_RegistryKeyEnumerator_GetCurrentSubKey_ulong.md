# RegistryKeyEnumerator::GetCurrentSubKey(ulong)

- ea: `0x140008be0`
- end: `0x140008cd4`
- name: `?GetCurrentSubKey@RegistryKeyEnumerator@@QEBA?AV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@K@Z`
- size: `244`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x140008bc0`
- `0x14001e458`

## callees

- `0x140008be0`
- `0x140022cec`
- `0x140031810`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140008c41`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140008c41`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyTransactedW` at `0x140008c34`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyTransactedW` at `0x140008c34`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
HKEY *__fastcall RegistryKeyEnumerator::GetCurrentSubKey(HKEY *a1, HKEY *a2)
{
  HKEY hTransaction; // rax
  const WCHAR *v4; // rdx
  HKEY v5; // rcx
  unsigned int v6; // eax
  unsigned int v7; // edi
  _QWORD pExceptionObject[3]; // [rsp+48h] [rbp-30h] BYREF
  unsigned int v10; // [rsp+60h] [rbp-18h]
  __int64 v11; // [rsp+64h] [rbp-14h]
  char v12; // [rsp+6Ch] [rbp-Ch]

  *a2 = 0;
  hTransaction = a1[1];
  *a2 = 0;
  v4 = (const WCHAR *)a1[2];
  v5 = *a1;
  if ( hTransaction == HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
    v6 = RegOpenKeyExW(v5, v4, 0, 0x20019u, a2);
  else
    v6 = RegOpenKeyTransactedW(v5, v4, 0, 0x20019u, a2, hTransaction, 0);
  v7 = v6;
  if ( v6 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_50ea671b4016364e45441d7df5fd8e94_Traceguids, v6);
    }
    pExceptionObject[0] = word_14003838A;
    pExceptionObject[1] = 0;
    pExceptionObject[2] = 0;
    v10 = v7;
    v11 = -1;
    v12 = 0;
    throw (EvtException *)pExceptionObject;
  }
  return a2;
}

```

## disassembly

```asm
0x140008be0  mov     [rsp+arg_0], rbx
0x140008be5  mov     [rsp+arg_10], rsi
0x140008bea  mov     [rsp+arg_8], rdx
0x140008bef  push    rdi
0x140008bf0  sub     rsp, 70h
0x140008bf4  mov     rbx, rdx
0x140008bf7  xor     esi, esi
0x140008bf9  mov     [rsp+78h+var_38], esi
0x140008bfd  mov     [rdx], rsi
0x140008c00  mov     [rsp+78h+var_38], 1
0x140008c08  mov     rax, [rcx+8]
0x140008c0c  mov     [rdx], rsi
0x140008c0f  mov     rdx, [rcx+10h]; lpSubKey
0x140008c13  mov     rcx, [rcx]; hKey
0x140008c16  mov     r9d, 20019h; samDesired
0x140008c1c  xor     r8d, r8d; ulOptions
0x140008c1f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140008c23  jz      short loc_140008C3C
0x140008c25  mov     [rsp+78h+pExtendedParemeter], rsi; pExtendedParemeter
0x140008c2a  mov     [rsp+78h+hTransaction], rax; hTransaction
0x140008c2f  mov     [rsp+78h+phkResult], rbx; phkResult
0x140008c34  call    cs:__imp_RegOpenKeyTransactedW
0x140008c3a  jmp     short loc_140008C47
0x140008c3c  mov     [rsp+78h+phkResult], rbx; phkResult
0x140008c41  call    cs:__imp_RegOpenKeyExW
0x140008c47  mov     edi, eax
0x140008c49  test    eax, eax
0x140008c4b  jz      short loc_140008CBE
0x140008c4d  lea     rax, WPP_GLOBAL_Control
0x140008c54  mov     rcx, cs:WPP_GLOBAL_Control
0x140008c5b  cmp     rcx, rax
0x140008c5e  jz      short loc_140008C84
0x140008c60  test    byte ptr [rcx+1Ch], 1
0x140008c64  jz      short loc_140008C84
0x140008c66  cmp     byte ptr [rcx+19h], 2
0x140008c6a  jb      short loc_140008C84
0x140008c6c  mov     edx, 0Dh
0x140008c71  mov     r9d, edi
0x140008c74  lea     r8, WPP_50ea671b4016364e45441d7df5fd8e94_Traceguids
0x140008c7b  mov     rcx, [rcx+10h]
0x140008c7f  call    WPP_SF_d
0x140008c84  lea     rax, word_14003838A
0x140008c8b  mov     [rsp+78h+pExceptionObject], rax
0x140008c90  mov     [rsp+78h+var_28], rsi
0x140008c95  mov     [rsp+78h+var_20], rsi
0x140008c9a  mov     [rsp+78h+var_18], edi
0x140008c9e  mov     [rsp+78h+var_14], 0FFFFFFFFFFFFFFFFh
0x140008ca7  mov     [rsp+78h+var_C], 0
0x140008cac  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x140008cb3  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x140008cb8  call    _CxxThrowException_0
0x140008cbe  mov     rax, rbx
0x140008cc1  lea     r11, [rsp+78h+var_8]
0x140008cc6  mov     rbx, [r11+10h]
0x140008cca  mov     rsi, [r11+20h]
0x140008cce  mov     rsp, r11
0x140008cd1  pop     rdi
0x140008cd2  retn
```
