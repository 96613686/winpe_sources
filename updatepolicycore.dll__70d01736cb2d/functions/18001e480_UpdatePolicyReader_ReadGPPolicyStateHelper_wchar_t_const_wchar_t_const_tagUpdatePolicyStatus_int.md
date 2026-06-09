# UpdatePolicyReader::ReadGPPolicyStateHelper(wchar_t const *,wchar_t const *,tagUpdatePolicyStatus *,int *)

- ea: `0x18001e480`
- end: `0x18001e524`
- name: `?ReadGPPolicyStateHelper@UpdatePolicyReader@@CAJPEB_W0PEAW4tagUpdatePolicyStatus@@PEAH@Z`
- size: `164`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey, LPCWSTR lpValue, enum tagUpdatePolicyStatus *, int *)`
- caller_count: `5`
- callee_count: `2`
- tags: `registry_config, installer_update`

## callers

- `0x18001bf44`
- `0x18001e52c`
- `0x18001e5f4`
- `0x18001e704`
- `0x18001ec08`

## callees

- `0x18001e480`
- `0x18002ffd0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001e4d2`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001e4d2`

## pseudocode

```c
__int64 __fastcall UpdatePolicyReader::ReadGPPolicyStateHelper(
        LPCWSTR lpSubKey,
        LPCWSTR lpValue,
        enum tagUpdatePolicyStatus *a3,
        int *a4)
{
  unsigned int v4; // ebx
  LSTATUS ValueW; // ecx
  bool v8; // zf
  int v10; // [rsp+40h] [rbp-28h] BYREF
  DWORD v11; // [rsp+44h] [rbp-24h] BYREF

  v4 = 0;
  v11 = 4;
  v10 = 0;
  ValueW = RegGetValueW(HKEY_LOCAL_MACHINE, lpSubKey, lpValue, 0x10u, 0, &v10, &v11);
  if ( (unsigned int)(ValueW - 2) <= 1 )
  {
    *(_DWORD *)a3 = 0;
    *a4 = 0;
  }
  else if ( ValueW )
  {
    v4 = (unsigned __int16)ValueW | 0x80070000;
    if ( ValueW <= 0 )
      return (unsigned int)ValueW;
  }
  else
  {
    v8 = v10 == 0;
    *(_DWORD *)a3 = 1;
    *a4 = !v8;
  }
  return v4;
}

```

## disassembly

```asm
0x18001e480  mov     r11, rsp
0x18001e483  push    rbx
0x18001e484  push    rsi
0x18001e485  push    rdi
0x18001e486  sub     rsp, 50h
0x18001e48a  mov     rax, cs:__security_cookie
0x18001e491  xor     rax, rsp
0x18001e494  mov     [rsp+68h+var_20], rax
0x18001e499  xor     ebx, ebx
0x18001e49b  mov     [rsp+68h+var_24], 4
0x18001e4a3  lea     rax, [r11-24h]
0x18001e4a7  mov     [rsp+68h+var_28], ebx
0x18001e4ab  mov     [r11-38h], rax
0x18001e4af  mov     rdi, r8
0x18001e4b2  lea     rax, [r11-28h]
0x18001e4b6  mov     r8, rdx; lpValue
0x18001e4b9  mov     rsi, r9
0x18001e4bc  mov     [r11-40h], rax
0x18001e4c0  mov     rdx, rcx; lpSubKey
0x18001e4c3  mov     [r11-48h], rbx
0x18001e4c7  lea     r9d, [rbx+10h]; dwFlags
0x18001e4cb  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18001e4d2  call    cs:__imp_RegGetValueW
0x18001e4d8  mov     ecx, eax
0x18001e4da  add     eax, 0FFFFFFFEh
0x18001e4dd  cmp     eax, 1
0x18001e4e0  jbe     short loc_18001E509
0x18001e4e2  test    ecx, ecx
0x18001e4e4  jz      short loc_18001E4F6
0x18001e4e6  movzx   ebx, cx
0x18001e4e9  or      ebx, 80070000h
0x18001e4ef  test    ecx, ecx
0x18001e4f1  cmovle  ebx, ecx
0x18001e4f4  jmp     short loc_18001E50D
0x18001e4f6  cmp     [rsp+68h+var_28], ebx
0x18001e4fa  mov     eax, ebx
0x18001e4fc  mov     dword ptr [rdi], 1
0x18001e502  setnz   al
0x18001e505  mov     [rsi], eax
0x18001e507  jmp     short loc_18001E50D
0x18001e509  mov     [rdi], ebx
0x18001e50b  mov     [rsi], ebx
0x18001e50d  mov     eax, ebx
0x18001e50f  mov     rcx, [rsp+68h+var_20]
0x18001e514  xor     rcx, rsp; StackCookie
0x18001e517  call    __security_check_cookie
0x18001e51c  add     rsp, 50h
0x18001e520  pop     rdi
0x18001e521  pop     rsi
0x18001e522  pop     rbx
0x18001e523  retn
```
