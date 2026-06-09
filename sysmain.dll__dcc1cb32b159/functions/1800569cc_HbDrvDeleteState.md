# HbDrvDeleteState

- ea: `0x1800569cc`
- end: `0x180056afd`
- name: `HbDrvDeleteState`
- size: `305`
- prototype: `__int64 __fastcall(HKEY hKey)`
- caller_count: `2`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800564d0`
- `0x180083b00`

## callees

- `0x1800569cc`

## import_xrefs

- `ntdll!NtOpenKey` at `0x180056a9b`
- `ntdll!NtOpenKey` at `0x180056a9b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180056a1a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180056ade`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180056a1a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180056ade`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180056aae`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180056aae`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x180056acf`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x180056acf`

## pseudocode

```c
LSTATUS __fastcall HbDrvDeleteState(HKEY hKey)
{
  HKEY v2; // rcx
  __int64 v3; // rbx
  wchar_t *v4; // rdx
  __int64 v5; // rcx
  wchar_t *v6; // rax
  __int16 v7; // cx
  LSTATUS result; // eax
  __int128 v9; // [rsp+20h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+30h] [rbp-30h] BYREF
  void *KeyHandle; // [rsp+98h] [rbp+38h] BYREF

  v2 = 0;
  v3 = 0;
  KeyHandle = 0;
  v9 = 0;
  memset(&ObjectAttributes, 0, 44);
  while ( 1 )
  {
    if ( v2 )
    {
      RegCloseKey(v2);
      KeyHandle = 0;
    }
    v4 = off_1800B8000[3 * v3];
    v9 = 0;
    if ( v4 )
    {
      v5 = 0x7FFF;
      v6 = v4;
      while ( *v6 )
      {
        ++v6;
        if ( !--v5 )
          goto LABEL_10;
      }
      v7 = 2 * v5;
      *((_QWORD *)&v9 + 1) = v4;
      LOWORD(v9) = -2 - v7;
      WORD1(v9) = -v7;
    }
LABEL_10:
    ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = (PUNICODE_STRING)&v9;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 64;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    if ( NtOpenKey(&KeyHandle, 0xF003Fu, &ObjectAttributes) >= 0 )
      RegDeleteValueW((HKEY)KeyHandle, off_1800B8000[3 * v3 + 1]);
    if ( ++v3 == 2 )
      break;
    v2 = (HKEY)KeyHandle;
  }
  result = RegDeleteKeyW(hKey, L"HybridDrivePerformance");
  if ( KeyHandle )
    return RegCloseKey((HKEY)KeyHandle);
  return result;
}

```

## disassembly

```asm
0x1800569cc  mov     [rsp-28h+arg_0], rbx
0x1800569d1  mov     [rsp-28h+arg_10], rsi
0x1800569d6  push    rbp
0x1800569d7  push    rdi
0x1800569d8  push    r12
0x1800569da  push    r14
0x1800569dc  push    r15
0x1800569de  mov     rbp, rsp
0x1800569e1  sub     rsp, 60h
0x1800569e5  xorps   xmm0, xmm0
0x1800569e8  lea     r12, off_1800B8000; "\\Registry\\Machine\\System\\CurrentCon"...
0x1800569ef  xor     eax, eax
0x1800569f1  mov     rsi, rcx
0x1800569f4  xor     r14d, r14d
0x1800569f7  mov     ecx, r14d; hKey
0x1800569fa  mov     ebx, r14d
0x1800569fd  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x180056a01  mov     [rbp+KeyHandle], rcx
0x180056a05  lea     r15d, [rax+2]
0x180056a09  movups  [rbp+var_40], xmm0
0x180056a0d  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x180056a11  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x180056a15  test    rcx, rcx
0x180056a18  jz      short loc_180056A24
0x180056a1a  call    cs:__imp_RegCloseKey
0x180056a20  mov     [rbp+KeyHandle], r14
0x180056a24  lea     rdi, [rbx+rbx*2]
0x180056a28  xorps   xmm0, xmm0
0x180056a2b  mov     rdx, [r12+rdi*8]
0x180056a2f  movups  [rbp+var_40], xmm0
0x180056a33  test    rdx, rdx
0x180056a36  jz      short loc_180056A6C
0x180056a38  mov     ecx, 7FFFh
0x180056a3d  mov     rax, rdx
0x180056a40  cmp     [rax], r14w
0x180056a44  jz      short loc_180056A51
0x180056a46  add     rax, r15
0x180056a49  sub     rcx, 1
0x180056a4d  jnz     short loc_180056A40
0x180056a4f  jmp     short loc_180056A6C
0x180056a51  add     cx, cx
0x180056a54  mov     qword ptr [rbp+var_40+8], rdx
0x180056a58  mov     eax, 0FFFEh
0x180056a5d  sub     ax, cx
0x180056a60  mov     word ptr [rbp+var_40], ax
0x180056a64  add     ax, r15w
0x180056a68  mov     word ptr [rbp+var_40+2], ax
0x180056a6c  lea     rax, [rbp+var_40]
0x180056a70  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x180056a77  xorps   xmm0, xmm0
0x180056a7a  mov     [rbp+ObjectAttributes.ObjectName], rax
0x180056a7e  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x180056a82  mov     [rbp+ObjectAttributes.RootDirectory], r14
0x180056a86  mov     edx, 0F003Fh; DesiredAccess
0x180056a8b  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x180056a92  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x180056a96  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180056a9b  call    cs:__imp_NtOpenKey
0x180056aa1  test    eax, eax
0x180056aa3  js      short loc_180056AB4
0x180056aa5  mov     rdx, [r12+rdi*8+8]; lpValueName
0x180056aaa  mov     rcx, [rbp+KeyHandle]; hKey
0x180056aae  call    cs:__imp_RegDeleteValueW
0x180056ab4  inc     rbx
0x180056ab7  cmp     rbx, r15
0x180056aba  jz      short loc_180056AC5
0x180056abc  mov     rcx, [rbp+KeyHandle]
0x180056ac0  jmp     loc_180056A15
0x180056ac5  lea     rdx, aHybriddriveper; "HybridDrivePerformance"
0x180056acc  mov     rcx, rsi; hKey
0x180056acf  call    cs:__imp_RegDeleteKeyW
0x180056ad5  mov     rcx, [rbp+KeyHandle]; hKey
0x180056ad9  test    rcx, rcx
0x180056adc  jz      short loc_180056AE4
0x180056ade  call    cs:__imp_RegCloseKey
0x180056ae4  lea     r11, [rsp+60h+var_s0]
0x180056ae9  mov     rbx, [r11+30h]
0x180056aed  mov     rsi, [r11+40h]
0x180056af1  mov     rsp, r11
0x180056af4  pop     r15
0x180056af6  pop     r14
0x180056af8  pop     r12
0x180056afa  pop     rdi
0x180056afb  pop     rbp
0x180056afc  retn
```
