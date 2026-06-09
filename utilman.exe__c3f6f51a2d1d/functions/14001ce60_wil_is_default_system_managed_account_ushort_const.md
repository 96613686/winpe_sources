# wil::is_default_system_managed_account(ushort const *)

- ea: `0x14001ce60`
- end: `0x14001cf98`
- name: `?is_default_system_managed_account@wil@@YA_NPEBG@Z`
- size: `312`
- prototype: `bool __fastcall(wil *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14001ccb0`

## callees

- `0x140002480`
- `0x140002fa0`
- `0x14001ce60`

## import_xrefs

- `ADVAPI32!RegGetValueW` at `0x14001cf27`
- `ADVAPI32!RegGetValueW` at `0x14001cf27`
- `KERNEL32!CompareStringOrdinal` at `0x14001cf5f`
- `KERNEL32!CompareStringOrdinal` at `0x14001cf5f`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x14001cedf`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x14001cedf`
- `Secur32!GetUserNameExW` at `0x14001cec4`
- `Secur32!GetUserNameExW` at `0x14001cec4`

## pseudocode

```c
char __fastcall wil::is_default_system_managed_account(wil *this, const unsigned __int16 *a2)
{
  const WCHAR *v2; // rbx
  LSTATUS ValueW; // eax
  bool v4; // sf
  char v5; // di
  ULONG nSize; // [rsp+40h] [rbp-468h] BYREF
  DWORD pcbData[3]; // [rsp+44h] [rbp-464h] BYREF
  WCHAR String2[264]; // [rsp+50h] [rbp-458h] BYREF
  WCHAR NameBuffer[280]; // [rsp+260h] [rbp-248h] BYREF

  v2 = 0;
  memset_0(String2, 0, 0x202u);
  pcbData[0] = 514;
  memset_0(NameBuffer, 0, 0x222u);
  nSize = 273;
  if ( GetUserNameExW(NameSamCompatible, NameBuffer, &nSize) )
    v2 = wcschr(NameBuffer, 0x5Cu) + 1;
  ValueW = RegGetValueW(
             HKEY_LOCAL_MACHINE,
             L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\OOBE",
             L"DefaultAccountSAMName",
             2u,
             0,
             String2,
             pcbData);
  v4 = ValueW < 0;
  if ( ValueW > 0 )
    v4 = 1;
  if ( v4 )
    return 0;
  if ( !v2 )
    return 0;
  v5 = 1;
  if ( CompareStringOrdinal(v2, -1, String2, -1, 1) != 2 )
    return 0;
  return v5;
}

```

## disassembly

```asm
0x14001ce60  mov     [rsp+arg_0], rbx
0x14001ce65  push    rdi
0x14001ce66  sub     rsp, 4A0h
0x14001ce6d  mov     rax, cs:__security_cookie
0x14001ce74  xor     rax, rsp
0x14001ce77  mov     [rsp+4A8h+var_18], rax
0x14001ce7f  mov     edi, 202h
0x14001ce84  lea     rcx, [rsp+4A8h+String2]; void *
0x14001ce89  mov     r8d, edi; Size
0x14001ce8c  xor     edx, edx; Val
0x14001ce8e  xor     ebx, ebx
0x14001ce90  call    memset_0
0x14001ce95  xor     edx, edx; Val
0x14001ce97  mov     [rsp+4A8h+var_464], edi
0x14001ce9b  lea     r8d, [rdi+20h]; Size
0x14001ce9f  lea     rcx, [rsp+4A8h+NameBuffer]; void *
0x14001cea7  call    memset_0
0x14001ceac  lea     r8, [rsp+4A8h+nSize]; nSize
0x14001ceb1  mov     [rsp+4A8h+nSize], 111h
0x14001ceb9  lea     rdx, [rsp+4A8h+NameBuffer]; lpNameBuffer
0x14001cec1  lea     ecx, [rbx+2]; NameFormat
0x14001cec4  call    cs:__imp_GetUserNameExW
0x14001cecb  nop     dword ptr [rax+rax+00h]
0x14001ced0  test    al, al
0x14001ced2  jz      short loc_14001CEEF
0x14001ced4  lea     edx, [rbx+5Ch]; Ch
0x14001ced7  lea     rcx, [rsp+4A8h+NameBuffer]; Str
0x14001cedf  call    cs:__imp_wcschr
0x14001cee6  nop     dword ptr [rax+rax+00h]
0x14001ceeb  lea     rbx, [rax+2]
0x14001ceef  lea     rax, [rsp+4A8h+var_464]
0x14001cef4  mov     r9d, 2; dwFlags
0x14001cefa  mov     [rsp+4A8h+pcbData], rax; pcbData
0x14001ceff  lea     r8, Value; "DefaultAccountSAMName"
0x14001cf06  lea     rax, [rsp+4A8h+String2]
0x14001cf0b  mov     rcx, 0FFFFFFFF80000002h; hkey
0x14001cf12  mov     [rsp+4A8h+pvData], rax; pvData
0x14001cf17  lea     rdx, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x14001cf1e  mov     [rsp+4A8h+pdwType], 0; pdwType
0x14001cf27  call    cs:__imp_RegGetValueW
0x14001cf2e  nop     dword ptr [rax+rax+00h]
0x14001cf33  test    eax, eax
0x14001cf35  jle     short loc_14001CF41
0x14001cf37  movzx   eax, ax
0x14001cf3a  or      eax, 80070000h
0x14001cf3f  test    eax, eax
0x14001cf41  js      short loc_14001CF70
0x14001cf43  test    rbx, rbx
0x14001cf46  jz      short loc_14001CF70
0x14001cf48  or      edx, 0FFFFFFFFh; cchCount1
0x14001cf4b  lea     r8, [rsp+4A8h+String2]; lpString2
0x14001cf50  mov     edi, 1
0x14001cf55  mov     r9d, edx; cchCount2
0x14001cf58  mov     rcx, rbx; lpString1
0x14001cf5b  mov     dword ptr [rsp+4A8h+pdwType], edi; bIgnoreCase
0x14001cf5f  call    cs:__imp_CompareStringOrdinal
0x14001cf66  nop     dword ptr [rax+rax+00h]
0x14001cf6b  cmp     eax, 2
0x14001cf6e  jz      short loc_14001CF73
0x14001cf70  xor     dil, dil
0x14001cf73  mov     al, dil
0x14001cf76  mov     rcx, [rsp+4A8h+var_18]
0x14001cf7e  xor     rcx, rsp; StackCookie
0x14001cf81  call    __security_check_cookie
0x14001cf86  mov     rbx, [rsp+4A8h+arg_0]
0x14001cf8e  add     rsp, 4A0h
0x14001cf95  pop     rdi
0x14001cf96  retn
```
