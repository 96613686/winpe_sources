# CUwfRegKey::CreateSubKey(ushort const *,ulong,ulong,ulong *,CUwfRegKey *)

- ea: `0x18000da80`
- end: `0x18000db45`
- name: `?CreateSubKey@CUwfRegKey@@QEAAJPEBGKKPEAKPEAV1@@Z`
- size: `197`
- prototype: `LSTATUS __fastcall(HKEY *this, const unsigned __int16 *, DWORD, REGSAM samDesired, unsigned int *, struct CUwfRegKey *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180008730`

## callees

- `0x18000d5a0`
- `0x18000da80`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000dacb`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000dacb`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18000db33`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18000db33`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000daf6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000db1b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000daf6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000db1b`

## pseudocode

```c
LSTATUS __fastcall CUwfRegKey::CreateSubKey(
        HKEY *this,
        const unsigned __int16 *a2,
        DWORD a3,
        REGSAM samDesired,
        unsigned int *a5,
        struct CUwfRegKey *a6)
{
  __int16 v6; // di
  HKEY v8; // rcx
  LSTATUS result; // eax
  int v11; // ebx
  HKEY hKey; // [rsp+80h] [rbp+8h] BYREF

  v6 = samDesired;
  v8 = *this;
  hKey = 0;
  result = RegCreateKeyExW(v8, a2, 0, 0, a3, samDesired, 0, &hKey, a5);
  if ( result )
  {
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  else if ( a6 )
  {
    v11 = CUwfRegKey::Attach(a6, hKey);
    if ( v11 < 0 )
    {
      RegCloseKey(hKey);
      RegDeleteKeyExW(*this, a2, v6 & 0x300, 0);
    }
    return v11;
  }
  else
  {
    RegCloseKey(hKey);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18000da80  mov     r11, rsp
0x18000da83  push    rbx
0x18000da84  push    rsi
0x18000da85  push    rdi
0x18000da86  push    r14
0x18000da88  sub     rsp, 58h
0x18000da8c  mov     rax, [rsp+78h+arg_20]
0x18000da94  mov     edi, r9d
0x18000da97  mov     [r11-38h], rax
0x18000da9b  mov     r14, rcx
0x18000da9e  mov     rcx, [rcx]; hKey
0x18000daa1  lea     rax, [r11+8]
0x18000daa5  mov     [r11-40h], rax
0x18000daa9  mov     rsi, rdx
0x18000daac  mov     qword ptr [r11-48h], 0
0x18000dab4  mov     [rsp+78h+samDesired], r9d; samDesired
0x18000dab9  xor     r9d, r9d; lpClass
0x18000dabc  mov     [r11-58h], r8d
0x18000dac0  xor     r8d, r8d; Reserved
0x18000dac3  mov     qword ptr [r11+8], 0
0x18000dacb  call    cs:__imp_RegCreateKeyExW
0x18000dad1  test    eax, eax
0x18000dad3  jz      short loc_18000DAE1
0x18000dad5  jle     short loc_18000DB3B
0x18000dad7  movzx   eax, ax
0x18000dada  or      eax, 80070000h
0x18000dadf  jmp     short loc_18000DB3B
0x18000dae1  mov     rcx, [rsp+78h+arg_28]; this
0x18000dae9  test    rcx, rcx
0x18000daec  jnz     short loc_18000DB00
0x18000daee  mov     rcx, [rsp+78h+hKey]; hKey
0x18000daf6  call    cs:__imp_RegCloseKey
0x18000dafc  xor     eax, eax
0x18000dafe  jmp     short loc_18000DB3B
0x18000db00  mov     rdx, [rsp+78h+hKey]; HKEY
0x18000db08  call    ?Attach@CUwfRegKey@@QEAAJPEAUHKEY__@@@Z; CUwfRegKey::Attach(HKEY__ *)
0x18000db0d  mov     ebx, eax
0x18000db0f  test    eax, eax
0x18000db11  jns     short loc_18000DB39
0x18000db13  mov     rcx, [rsp+78h+hKey]; hKey
0x18000db1b  call    cs:__imp_RegCloseKey
0x18000db21  mov     rcx, [r14]; hKey
0x18000db24  and     edi, 300h
0x18000db2a  mov     r8d, edi; samDesired
0x18000db2d  xor     r9d, r9d; Reserved
0x18000db30  mov     rdx, rsi; lpSubKey
0x18000db33  call    cs:__imp_RegDeleteKeyExW
0x18000db39  mov     eax, ebx
0x18000db3b  add     rsp, 58h
0x18000db3f  pop     r14
0x18000db41  pop     rdi
0x18000db42  pop     rsi
0x18000db43  pop     rbx
0x18000db44  retn
```
