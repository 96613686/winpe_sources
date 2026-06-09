# SBECoreUtil::GetRegStringValW(HKEY__ *,ushort const *,ushort const *,ulong *,uchar *)

- ea: `0x18005f880`
- end: `0x18005f954`
- name: `?GetRegStringValW@SBECoreUtil@@YAHPEAUHKEY__@@PEBG1PEAKPEAE@Z`
- size: `212`
- prototype: `int(SBECoreUtil *__hidden this, HKEY, const unsigned __int16 *, const unsigned __int16 *, unsigned int *, unsigned __int8 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800561a0`
- `0x1800567b0`

## callees

- `0x180001c00`
- `0x18005f880`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x18005f91b`
- `ADVAPI32!RegQueryValueExW` at `0x18005f91b`
- `ADVAPI32!RegCloseKey` at `0x18005f92d`
- `ADVAPI32!RegCloseKey` at `0x18005f92d`
- `ADVAPI32!RegCreateKeyExW` at `0x18005f8eb`
- `ADVAPI32!RegCreateKeyExW` at `0x18005f8eb`

## string_xrefs

- `0x18005f8ab`: `IO\Writer`
- `0x18005f904`: `DVRDirectory`

## pseudocode

```c
_BOOL8 __fastcall SBECoreUtil::GetRegStringValW(
        SBECoreUtil *this,
        HKEY a2,
        const unsigned __int16 *a3,
        DWORD *a4,
        BYTE *lpData)
{
  BOOL v6; // ebx
  HKEY hKey; // [rsp+50h] [rbp-28h] BYREF
  DWORD v9; // [rsp+58h] [rbp-20h] BYREF
  DWORD Type; // [rsp+5Ch] [rbp-1Ch] BYREF

  hKey = 0;
  v9 = 0;
  if ( RegCreateKeyExW((HKEY)this, L"IO\\Writer", 0, 0, 0, 0x2001Fu, 0, &hKey, &v9) )
  {
    return 0;
  }
  else
  {
    Type = 1;
    v6 = RegQueryValueExW(hKey, L"DVRDirectory", 0, &Type, lpData, a4) == 0;
    RegCloseKey(hKey);
  }
  return v6;
}

```

## disassembly

```asm
0x18005f880  mov     r11, rsp
0x18005f883  mov     [r11+10h], rbx
0x18005f887  push    rdi
0x18005f888  sub     rsp, 70h
0x18005f88c  mov     rax, cs:__security_cookie
0x18005f893  xor     rax, rsp
0x18005f896  mov     [rsp+78h+var_18], rax
0x18005f89b  mov     rdi, [rsp+78h+lpData]
0x18005f8a3  lea     rax, [r11-20h]
0x18005f8a7  mov     [r11-38h], rax
0x18005f8ab  lea     rdx, aIoWriter; "IO\\Writer"
0x18005f8b2  lea     rax, [r11-28h]
0x18005f8b6  mov     qword ptr [r11-28h], 0
0x18005f8be  mov     [r11-40h], rax
0x18005f8c2  mov     rbx, r9
0x18005f8c5  mov     qword ptr [r11-48h], 0
0x18005f8cd  xor     r9d, r9d; lpClass
0x18005f8d0  mov     [rsp+78h+samDesired], 2001Fh; samDesired
0x18005f8d8  xor     r8d, r8d; Reserved
0x18005f8db  mov     [rsp+78h+dwOptions], 0; dwOptions
0x18005f8e3  mov     [rsp+78h+var_20], 0
0x18005f8eb  call    cs:__imp_RegCreateKeyExW
0x18005f8f1  test    eax, eax
0x18005f8f3  jnz     short loc_18005F935
0x18005f8f5  mov     rcx, [rsp+78h+hKey]; hKey
0x18005f8fa  lea     r9, [rsp+78h+Type]; lpType
0x18005f8ff  mov     qword ptr [rsp+78h+samDesired], rbx; lpcbData
0x18005f904  lea     rdx, aDvrdirectory; "DVRDirectory"
0x18005f90b  xor     r8d, r8d; lpReserved
0x18005f90e  mov     qword ptr [rsp+78h+dwOptions], rdi; lpData
0x18005f913  mov     [rsp+78h+Type], 1
0x18005f91b  call    cs:__imp_RegQueryValueExW
0x18005f921  mov     rcx, [rsp+78h+hKey]; hKey
0x18005f926  xor     ebx, ebx
0x18005f928  test    eax, eax
0x18005f92a  setz    bl
0x18005f92d  call    cs:__imp_RegCloseKey
0x18005f933  jmp     short loc_18005F937
0x18005f935  xor     ebx, ebx
0x18005f937  mov     eax, ebx
0x18005f939  mov     rcx, [rsp+78h+var_18]
0x18005f93e  xor     rcx, rsp; StackCookie
0x18005f941  call    __security_check_cookie
0x18005f946  mov     rbx, [rsp+78h+arg_8]
0x18005f94e  add     rsp, 70h
0x18005f952  pop     rdi
0x18005f953  retn
```
