# WriteLeapSecondListToRegistry(_LEAP_SECOND_DATA_REGISTRY_ENTRY *,ulong)

- ea: `0x18004fedc`
- end: `0x18004ffb4`
- name: `?WriteLeapSecondListToRegistry@@YAJPEAU_LEAP_SECOND_DATA_REGISTRY_ENTRY@@K@Z`
- size: `216`
- prototype: `__int64 __fastcall(BYTE *lpData, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18004f97c`

## callees

- `0x18002aa10`
- `0x18004fedc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004ff20`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004ff20`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004ff95`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006a32a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004ff95`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006a32a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004ff79`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004ff79`

## pseudocode

```c
__int64 __fastcall WriteLeapSecondListToRegistry(BYTE *lpData, unsigned int a2)
{
  unsigned __int64 v2; // rdi
  LSTATUS v4; // eax
  signed int v5; // ebx
  bool v6; // cc
  HKEY hKey; // [rsp+50h] [rbp+18h] BYREF
  unsigned __int64 cbData; // [rsp+58h] [rbp+20h] BYREF

  v2 = a2;
  cbData = 0;
  hKey = 0;
  v4 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"System\\CurrentControlSet\\Control\\LeapSecondInformation",
         0,
         0x20006u,
         &hKey);
  v5 = v4;
  v6 = v4 <= 0;
  if ( v4
    || (v5 = ULongLongMult(0xCu, v2, &cbData), v5 >= 0)
    && (v4 = RegSetValueExW(hKey, L"LeapSeconds", 0, 3u, lpData, cbData), v5 = v4, v6 = v4 <= 0, v4) )
  {
    if ( !v6 )
      v5 = (unsigned __int16)v4 | 0x80070000;
  }
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18004fedc  mov     r11, rsp
0x18004fedf  mov     [r11+8], rbx
0x18004fee3  mov     [r11+10h], rsi
0x18004fee7  push    rdi
0x18004fee8  sub     rsp, 30h
0x18004feec  mov     edi, edx
0x18004feee  mov     rsi, rcx
0x18004fef1  mov     qword ptr [r11+20h], 0
0x18004fef9  mov     qword ptr [r11+18h], 0
0x18004ff01  lea     rax, [r11+18h]
0x18004ff05  mov     [r11-18h], rax
0x18004ff09  mov     r9d, 20006h; samDesired
0x18004ff0f  xor     r8d, r8d; ulOptions
0x18004ff12  lea     rdx, aSystemCurrentc_1; "System\\CurrentControlSet\\Control\\Lea"...
0x18004ff19  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18004ff20  call    cs:__imp_RegOpenKeyExW
0x18004ff27  nop     dword ptr [rax+rax+00h]
0x18004ff2c  mov     ebx, eax
0x18004ff2e  test    eax, eax
0x18004ff30  jz      short loc_18004FF3F
0x18004ff32  jle     short loc_18004FF8B
0x18004ff34  movzx   ebx, ax
0x18004ff37  or      ebx, 80070000h
0x18004ff3d  jmp     short loc_18004FF8B
0x18004ff3f  mov     rdx, rdi; unsigned __int64
0x18004ff42  lea     r8, [rsp+38h+arg_18]; unsigned __int64 *
0x18004ff47  mov     ecx, 0Ch; unsigned __int64
0x18004ff4c  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18004ff51  mov     ebx, eax
0x18004ff53  test    eax, eax
0x18004ff55  js      short loc_18004FF8B
0x18004ff57  mov     eax, dword ptr [rsp+38h+arg_18]
0x18004ff5b  mov     [rsp+38h+cbData], eax; cbData
0x18004ff5f  mov     [rsp+38h+lpData], rsi; lpData
0x18004ff64  mov     r9d, 3; dwType
0x18004ff6a  xor     r8d, r8d; Reserved
0x18004ff6d  lea     rdx, aLeapseconds; "LeapSeconds"
0x18004ff74  mov     rcx, [rsp+38h+hKey]; hKey
0x18004ff79  call    cs:__imp_RegSetValueExW
0x18004ff80  nop     dword ptr [rax+rax+00h]
0x18004ff85  mov     ebx, eax
0x18004ff87  test    eax, eax
0x18004ff89  jnz     short loc_18004FF32
0x18004ff8b  mov     rcx, [rsp+38h+hKey]; hKey
0x18004ff90  test    rcx, rcx
0x18004ff93  jz      short loc_18004FFA1
0x18004ff95  call    cs:__imp_RegCloseKey
0x18004ff9c  nop     dword ptr [rax+rax+00h]
0x18004ffa1  mov     eax, ebx
0x18004ffa3  mov     rbx, [rsp+38h+arg_0]
0x18004ffa8  mov     rsi, [rsp+38h+arg_8]
0x18004ffad  add     rsp, 30h
0x18004ffb1  pop     rdi
0x18004ffb2  retn
0x18006a318  push    rbp
0x18006a31a  sub     rsp, 30h
0x18006a31e  mov     rbp, rdx
0x18006a321  mov     rcx, [rbp+50h]; hKey
0x18006a325  test    rcx, rcx
0x18006a328  jz      short loc_18006A337
0x18006a32a  call    cs:__imp_RegCloseKey
0x18006a331  nop     dword ptr [rax+rax+00h]
0x18006a336  nop
0x18006a337  add     rsp, 30h
0x18006a33b  pop     rbp
0x18006a33c  retn
```
