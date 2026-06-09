# CExtensionStateManager::_LoadExtensionState(ushort const *,EXTENSION_STATE *)

- ea: `0x18007f020`
- end: `0x18007f13a`
- name: `?_LoadExtensionState@CExtensionStateManager@@AEAAJPEBGPEAUEXTENSION_STATE@@@Z`
- size: `282`
- prototype: `int(CExtensionStateManager *__hidden this, const unsigned __int16 *, struct EXTENSION_STATE *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180079ed0`
- `0x18007f140`

## callees

- `0x180024418`
- `0x18002bc68`
- `0x18007f020`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007f124`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007f124`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18007f0e6`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18007f119`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18007f0e6`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18007f119`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007f0a2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007f0a2`

## pseudocode

```c
__int64 __fastcall CExtensionStateManager::_LoadExtensionState(
        CExtensionStateManager *this,
        const unsigned __int16 *a2,
        struct EXTENSION_STATE *a3)
{
  int v6; // ebx
  HKEY v7; // rcx
  DWORD pcbData; // [rsp+60h] [rbp+8h] BYREF
  HKEY hkey; // [rsp+70h] [rbp+18h] BYREF

  memset_0(a3, 0, 0x20Cu);
  *((_DWORD *)a3 + 131) = -1;
  if ( *((_QWORD *)this + 2) )
  {
    v6 = StringCchCopyW((unsigned __int16 *)a3, 0x104u, a2);
    if ( v6 >= 0 )
    {
      v7 = (HKEY)*((_QWORD *)this + 2);
      hkey = 0;
      if ( !RegOpenKeyExW(v7, (LPCWSTR)a3, 0, 0x20019u, &hkey) )
      {
        pcbData = 4;
        RegGetValueW(hkey, 0, L"State", 0x10u, 0, (char *)a3 + 520, &pcbData);
        pcbData = 4;
        RegGetValueW(hkey, 0, L"PinnedOrder", 0x10u, 0, (char *)a3 + 524, &pcbData);
        RegCloseKey(hkey);
      }
    }
  }
  else
  {
    return (unsigned int)-2147418113;
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18007f020  mov     [rsp+arg_8], rbx
0x18007f025  push    rsi
0x18007f026  push    rdi
0x18007f027  push    r14
0x18007f029  sub     rsp, 40h
0x18007f02d  mov     rdi, r8
0x18007f030  mov     rbx, rdx
0x18007f033  mov     rsi, rcx
0x18007f036  xor     edx, edx; Val
0x18007f038  mov     rcx, rdi; void *
0x18007f03b  mov     r8d, 20Ch; Size
0x18007f041  call    memset_0
0x18007f046  lea     r14, [rdi+20Ch]
0x18007f04d  mov     dword ptr [r14], 0FFFFFFFFh
0x18007f054  cmp     qword ptr [rsi+10h], 0
0x18007f059  jnz     short loc_18007F065
0x18007f05b  mov     ebx, 8000FFFFh
0x18007f060  jmp     loc_18007F12A
0x18007f065  mov     r8, rbx; unsigned __int16 *
0x18007f068  mov     edx, 104h; unsigned __int64
0x18007f06d  mov     rcx, rdi; unsigned __int16 *
0x18007f070  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18007f075  mov     ebx, eax
0x18007f077  test    eax, eax
0x18007f079  js      loc_18007F12A
0x18007f07f  mov     rcx, [rsi+10h]; hKey
0x18007f083  lea     rax, [rsp+58h+hkey]
0x18007f088  mov     r9d, 20019h; samDesired
0x18007f08e  mov     [rsp+58h+phkResult], rax; phkResult
0x18007f093  xor     r8d, r8d; ulOptions
0x18007f096  mov     [rsp+58h+hkey], 0
0x18007f09f  mov     rdx, rdi; lpSubKey
0x18007f0a2  call    cs:__imp_RegOpenKeyExW
0x18007f0a8  test    eax, eax
0x18007f0aa  jnz     short loc_18007F12A
0x18007f0ac  lea     esi, [rax+4]
0x18007f0af  xor     edx, edx; lpSubKey
0x18007f0b1  lea     rax, [rdi+208h]
0x18007f0b8  mov     [rsp+58h+arg_0], esi
0x18007f0bc  lea     rcx, [rsp+58h+arg_0]
0x18007f0c1  mov     [rsp+58h+pcbData], rcx; pcbData
0x18007f0c6  lea     edi, [rsi+0Ch]
0x18007f0c9  mov     rcx, [rsp+58h+hkey]; hkey
0x18007f0ce  lea     r8, ValueName; "State"
0x18007f0d5  mov     [rsp+58h+pvData], rax; pvData
0x18007f0da  mov     r9d, edi; dwFlags
0x18007f0dd  mov     [rsp+58h+phkResult], 0; pdwType
0x18007f0e6  call    cs:__imp_RegGetValueW
0x18007f0ec  mov     rcx, [rsp+58h+hkey]; hkey
0x18007f0f1  lea     rax, [rsp+58h+arg_0]
0x18007f0f6  mov     [rsp+58h+pcbData], rax; pcbData
0x18007f0fb  lea     r8, aPinnedorder; "PinnedOrder"
0x18007f102  mov     [rsp+58h+pvData], r14; pvData
0x18007f107  mov     r9d, edi; dwFlags
0x18007f10a  xor     edx, edx; lpSubKey
0x18007f10c  mov     [rsp+58h+phkResult], 0; pdwType
0x18007f115  mov     [rsp+58h+arg_0], esi
0x18007f119  call    cs:__imp_RegGetValueW
0x18007f11f  mov     rcx, [rsp+58h+hkey]; hKey
0x18007f124  call    cs:__imp_RegCloseKey
0x18007f12a  mov     eax, ebx
0x18007f12c  mov     rbx, [rsp+58h+arg_8]
0x18007f131  add     rsp, 40h
0x18007f135  pop     r14
0x18007f137  pop     rdi
0x18007f138  pop     rsi
0x18007f139  retn
```
