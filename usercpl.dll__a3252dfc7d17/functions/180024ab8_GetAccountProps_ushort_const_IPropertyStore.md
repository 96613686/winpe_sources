# _GetAccountProps(ushort const *,IPropertyStore * *)

- ea: `0x180024ab8`
- end: `0x180024c36`
- name: `?_GetAccountProps@@YAJPEBGPEAPEAUIPropertyStore@@@Z`
- size: `382`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct IPropertyStore **)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180024e34`
- `0x180024f04`

## callees

- `0x180006eb8`
- `0x180024a34`
- `0x180024ab8`
- `0x1800772c0`
- `0x180078010`

## import_xrefs

- `SHLWAPI!StrChrW` at `0x180024b04`
- `SHLWAPI!StrChrW` at `0x180024b04`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180024bd3`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180024bd3`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180024b6c`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180024b6c`
- `KERNEL32!lstrcmpiW` at `0x180024b81`
- `KERNEL32!lstrcmpiW` at `0x180024b81`

## pseudocode

```c
__int64 __fastcall _GetAccountProps(const unsigned __int16 *a1, struct IPropertyStore **a2)
{
  HRESULT Instance; // ebx
  PWSTR v5; // rax
  __int64 v6; // r11
  DWORD nSize[2]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Buffer[20]; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR String2[256]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 v11[264]; // [rsp+260h] [rbp+160h] BYREF

  *a2 = 0;
  Instance = -2147467259;
  if ( !a1 )
    return (unsigned int)Instance;
  v5 = StrChrW(a1, 0x5Cu);
  if ( v5 )
  {
    Instance = StringCchCopyW(v11, 0x101u, v5 + 1);
    if ( Instance < 0 )
      return (unsigned int)Instance;
    Instance = StringCchCopyNW(String2, 0x100u, a1, (v6 - (__int64)a1) >> 1);
    if ( Instance < 0 )
      return (unsigned int)Instance;
    nSize[0] = 16;
    if ( !GetComputerNameExW(ComputerNamePhysicalNetBIOS, Buffer, nSize) || lstrcmpiW(Buffer, String2) )
      goto LABEL_10;
  }
  else
  {
    Instance = StringCchCopyW(v11, 0x101u, a1);
    if ( Instance < 0 )
      return (unsigned int)Instance;
  }
  String2[0] = 0;
LABEL_10:
  if ( String2[0] )
  {
    return (unsigned int)-2147024894;
  }
  else
  {
    *(_QWORD *)nSize = 0;
    Instance = CoCreateInstance(
                 &CLSID_LocalUserAccounts,
                 0,
                 1u,
                 &GUID_3c708557_c99d_4fa3_9231_56518418b4e4,
                 (LPVOID *)nSize);
    if ( Instance >= 0 )
    {
      Instance = (*(__int64 (__fastcall **)(_QWORD, unsigned __int16 *, struct IPropertyStore **))(**(_QWORD **)nSize
                                                                                                 + 72LL))(
                   *(_QWORD *)nSize,
                   v11,
                   a2);
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)nSize + 16LL))(*(_QWORD *)nSize);
    }
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180024ab8  mov     [rsp-8+arg_10], rbx
0x180024abd  mov     [rsp-8+arg_18], rsi
0x180024ac2  push    rbp
0x180024ac3  push    rdi
0x180024ac4  push    r14
0x180024ac6  lea     rbp, [rsp-380h]
0x180024ace  sub     rsp, 480h
0x180024ad5  mov     rax, cs:__security_cookie
0x180024adc  xor     rax, rsp
0x180024adf  mov     [rbp+390h+var_20], rax
0x180024ae6  xor     r14d, r14d
0x180024ae9  mov     rsi, rdx
0x180024aec  mov     [rdx], r14
0x180024aef  mov     rdi, rcx
0x180024af2  mov     ebx, 80004005h
0x180024af7  test    rcx, rcx
0x180024afa  jz      loc_180024C0D
0x180024b00  lea     edx, [r14+5Ch]; wMatch
0x180024b04  call    cs:__imp_StrChrW
0x180024b0a  mov     edx, 101h; unsigned __int64
0x180024b0f  lea     rcx, [rbp+390h+var_230]; unsigned __int16 *
0x180024b16  mov     r11, rax
0x180024b19  test    rax, rax
0x180024b1c  jz      short loc_180024B8D
0x180024b1e  lea     r8, [rax+2]; unsigned __int16 *
0x180024b22  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180024b27  mov     ebx, eax
0x180024b29  test    eax, eax
0x180024b2b  js      loc_180024C0D
0x180024b31  sub     r11, rdi
0x180024b34  lea     rcx, [rsp+490h+String2]; unsigned __int16 *
0x180024b39  sar     r11, 1
0x180024b3c  mov     r8, rdi; unsigned __int16 *
0x180024b3f  mov     r9, r11; unsigned __int64
0x180024b42  mov     edx, 100h; unsigned __int64
0x180024b47  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x180024b4c  mov     ebx, eax
0x180024b4e  test    eax, eax
0x180024b50  js      loc_180024C0D
0x180024b56  lea     r8, [rsp+490h+nSize]; nSize
0x180024b5b  mov     [rsp+490h+nSize], 10h
0x180024b63  lea     rdx, [rsp+490h+Buffer]; lpBuffer
0x180024b68  lea     ecx, [r14+4]; NameType
0x180024b6c  call    cs:__imp_GetComputerNameExW
0x180024b72  cmp     eax, 1
0x180024b75  jnz     short loc_180024BA1
0x180024b77  lea     rdx, [rsp+490h+String2]; lpString2
0x180024b7c  lea     rcx, [rsp+490h+Buffer]; lpString1
0x180024b81  call    cs:__imp_lstrcmpiW
0x180024b87  test    eax, eax
0x180024b89  jz      short loc_180024B9B
0x180024b8b  jmp     short loc_180024BA1
0x180024b8d  mov     r8, rdi; unsigned __int16 *
0x180024b90  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180024b95  mov     ebx, eax
0x180024b97  test    eax, eax
0x180024b99  js      short loc_180024C0D
0x180024b9b  mov     [rsp+490h+String2], r14w
0x180024ba1  cmp     [rsp+490h+String2], r14w
0x180024ba7  jz      short loc_180024BB0
0x180024ba9  mov     ebx, 80070002h
0x180024bae  jmp     short loc_180024C0D
0x180024bb0  xor     edx, edx; pUnkOuter
0x180024bb2  mov     qword ptr [rsp+490h+nSize], r14
0x180024bb7  lea     rax, [rsp+490h+nSize]
0x180024bbc  lea     r9, _GUID_3c708557_c99d_4fa3_9231_56518418b4e4; riid
0x180024bc3  mov     [rsp+490h+ppv], rax; ppv
0x180024bc8  lea     rcx, CLSID_LocalUserAccounts; rclsid
0x180024bcf  lea     r8d, [rdx+1]; dwClsContext
0x180024bd3  call    cs:__imp_CoCreateInstance
0x180024bd9  mov     ebx, eax
0x180024bdb  test    eax, eax
0x180024bdd  js      short loc_180024C0D
0x180024bdf  mov     rcx, qword ptr [rsp+490h+nSize]
0x180024be4  lea     rdx, [rbp+390h+var_230]
0x180024beb  mov     r8, rsi
0x180024bee  mov     rax, [rcx]
0x180024bf1  mov     rax, [rax+48h]
0x180024bf5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024bfa  mov     rcx, qword ptr [rsp+490h+nSize]
0x180024bff  mov     ebx, eax
0x180024c01  mov     rax, [rcx]
0x180024c04  mov     rax, [rax+10h]
0x180024c08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024c0d  mov     eax, ebx
0x180024c0f  mov     rcx, [rbp+390h+var_20]
0x180024c16  xor     rcx, rsp; StackCookie
0x180024c19  call    __security_check_cookie
0x180024c1e  lea     r11, [rsp+490h+var_10]
0x180024c26  mov     rbx, [r11+30h]
0x180024c2a  mov     rsi, [r11+38h]
0x180024c2e  mov     rsp, r11
0x180024c31  pop     r14
0x180024c33  pop     rdi
0x180024c34  pop     rbp
0x180024c35  retn
```
