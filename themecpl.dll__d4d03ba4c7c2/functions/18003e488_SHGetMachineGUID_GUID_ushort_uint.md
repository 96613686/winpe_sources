# SHGetMachineGUID(_GUID *,ushort *,uint)

- ea: `0x18003e488`
- end: `0x18003e65a`
- name: `?SHGetMachineGUID@@YAJPEAU_GUID@@PEAGI@Z`
- size: `466`
- prototype: `__int64 __fastcall(struct _GUID *, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003bff8`

## callees

- `0x180002280`
- `0x180007fd8`
- `0x18003e488`

## import_xrefs

- `SHELL32!__imp_GUIDFromStringW` at `0x18003e617`
- `SHELL32!__imp_GUIDFromStringW` at `0x18003e617`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003e5fa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003e5fa`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003e54d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003e54d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003e5b7`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003e5b7`

## pseudocode

```c
__int64 __fastcall SHGetMachineGUID(struct _GUID *a1, unsigned __int16 *a2)
{
  _WORD *v2; // r8
  __int64 v4; // rdx
  const wchar_t *v5; // rcx
  __int64 v6; // r9
  __int64 v7; // rax
  __int64 v8; // rsi
  _WORD *v9; // rcx
  signed int v10; // ebx
  LSTATUS v11; // eax
  unsigned __int64 v12; // rdi
  _WORD *pvData; // rsi
  LSTATUS ValueW; // eax
  DWORD pcbData; // [rsp+40h] [rbp-88h] BYREF
  HKEY hkey; // [rsp+48h] [rbp-80h] BYREF
  _WORD v18[40]; // [rsp+50h] [rbp-78h] BYREF

  v2 = v18;
  v4 = 39;
  v5 = L"{";
  v6 = 0;
  v7 = 2147483646;
  do
  {
    if ( !v7 )
      break;
    if ( !*v5 )
      break;
    *v2++ = *v5++;
    --v7;
    ++v6;
    --v4;
  }
  while ( v4 );
  v8 = v6 - 1;
  v9 = v2 - 1;
  if ( v4 )
    v8 = v6;
  v10 = v4 == 0 ? 0x8007007A : 0;
  if ( v4 )
    v9 = v2;
  *v9 = 0;
  if ( v4 )
  {
    hkey = 0;
    v11 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Cryptography", 0, 0x101u, &hkey);
    v10 = v11;
    if ( v11 > 0 )
      v10 = (unsigned __int16)v11 | 0x80070000;
    if ( v10 >= 0 )
    {
      v12 = 39 - v8;
      if ( 2 * (unsigned __int64)(unsigned int)(39 - v8) > 0xFFFFFFFF )
      {
        pcbData = -1;
        v10 = -2147024362;
      }
      else
      {
        pcbData = 2 * (39 - v8);
        pvData = &v18[v8];
        ValueW = RegGetValueW(hkey, 0, L"MachineGuid", 2u, 0, pvData, &pcbData);
        v10 = ValueW;
        if ( ValueW > 0 )
          v10 = (unsigned __int16)ValueW | 0x80070000;
        if ( v10 >= 0 )
          v10 = StringCchCatW(pvData, v12, L"}");
      }
      RegCloseKey(hkey);
      if ( v10 >= 0 && a1 )
        return (unsigned int)GUIDFromStringW(v18, a1) == 0 ? 0x80004005 : 0;
    }
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18003e488  mov     [rsp+arg_8], rbx
0x18003e48d  mov     [rsp+arg_10], rbp
0x18003e492  push    rsi
0x18003e493  push    rdi
0x18003e494  push    r14
0x18003e496  sub     rsp, 0B0h
0x18003e49d  mov     rax, cs:__security_cookie
0x18003e4a4  xor     rax, rsp
0x18003e4a7  mov     [rsp+0C8h+var_28], rax
0x18003e4af  mov     edi, 27h ; '''
0x18003e4b4  lea     r8, [rsp+0C8h+var_78]
0x18003e4b9  xor     r14d, r14d
0x18003e4bc  mov     rbp, rcx
0x18003e4bf  mov     edx, edi
0x18003e4c1  lea     rcx, asc_18005FD94; "{"
0x18003e4c8  mov     r9d, r14d
0x18003e4cb  mov     eax, 7FFFFFFEh
0x18003e4d0  test    rax, rax
0x18003e4d3  jz      short loc_18003E4F7
0x18003e4d5  movzx   r10d, word ptr [rcx]
0x18003e4d9  test    r10w, r10w
0x18003e4dd  jz      short loc_18003E4F7
0x18003e4df  mov     [r8], r10w
0x18003e4e3  add     rcx, 2
0x18003e4e7  add     r8, 2
0x18003e4eb  dec     rax
0x18003e4ee  inc     r9
0x18003e4f1  sub     rdx, 1
0x18003e4f5  jnz     short loc_18003E4D0
0x18003e4f7  test    rdx, rdx
0x18003e4fa  lea     rsi, [r9-1]
0x18003e4fe  mov     rax, rdx
0x18003e501  lea     rcx, [r8-2]
0x18003e505  cmovnz  rsi, r9
0x18003e509  neg     rax
0x18003e50c  sbb     ebx, ebx
0x18003e50e  not     ebx
0x18003e510  and     ebx, 8007007Ah
0x18003e516  test    rdx, rdx
0x18003e519  cmovnz  rcx, r8
0x18003e51d  mov     [rcx], r14w
0x18003e521  jz      loc_18003E62F
0x18003e527  lea     rax, [rsp+0C8h+hkey]
0x18003e52c  mov     [rsp+0C8h+hkey], r14
0x18003e531  mov     r9d, 101h; samDesired
0x18003e537  mov     [rsp+0C8h+phkResult], rax; phkResult
0x18003e53c  xor     r8d, r8d; ulOptions
0x18003e53f  lea     rdx, aSoftwareMicros_6; "SOFTWARE\\Microsoft\\Cryptography"
0x18003e546  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003e54d  call    cs:__imp_RegOpenKeyExW
0x18003e554  nop     dword ptr [rax+rax+00h]
0x18003e559  mov     ebx, eax
0x18003e55b  test    eax, eax
0x18003e55d  jle     short loc_18003E568
0x18003e55f  movzx   ebx, ax
0x18003e562  or      ebx, 80070000h
0x18003e568  test    ebx, ebx
0x18003e56a  js      loc_18003E62F
0x18003e570  sub     rdi, rsi
0x18003e573  mov     ecx, 0FFFFFFFFh
0x18003e578  mov     eax, edi
0x18003e57a  add     rax, rax
0x18003e57d  cmp     rax, rcx
0x18003e580  ja      short loc_18003E5EC
0x18003e582  lea     rcx, [rsp+0C8h+var_78]
0x18003e587  mov     [rsp+0C8h+var_88], eax
0x18003e58b  lea     rsi, [rcx+rsi*2]
0x18003e58f  mov     r9d, 2; dwFlags
0x18003e595  mov     rcx, [rsp+0C8h+hkey]; hkey
0x18003e59a  lea     rax, [rsp+0C8h+var_88]
0x18003e59f  mov     [rsp+0C8h+pcbData], rax; pcbData
0x18003e5a4  lea     r8, aMachineguid; "MachineGuid"
0x18003e5ab  mov     [rsp+0C8h+pvData], rsi; pvData
0x18003e5b0  xor     edx, edx; lpSubKey
0x18003e5b2  mov     [rsp+0C8h+phkResult], r14; pdwType
0x18003e5b7  call    cs:__imp_RegGetValueW
0x18003e5be  nop     dword ptr [rax+rax+00h]
0x18003e5c3  mov     ebx, eax
0x18003e5c5  test    eax, eax
0x18003e5c7  jle     short loc_18003E5D2
0x18003e5c9  movzx   ebx, ax
0x18003e5cc  or      ebx, 80070000h
0x18003e5d2  test    ebx, ebx
0x18003e5d4  js      short loc_18003E5F5
0x18003e5d6  lea     r8, asc_18005FE18; "}"
0x18003e5dd  mov     rdx, rdi; unsigned __int64
0x18003e5e0  mov     rcx, rsi; unsigned __int16 *
0x18003e5e3  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18003e5e8  mov     ebx, eax
0x18003e5ea  jmp     short loc_18003E5F5
0x18003e5ec  mov     [rsp+0C8h+var_88], ecx
0x18003e5f0  mov     ebx, 80070216h
0x18003e5f5  mov     rcx, [rsp+0C8h+hkey]; hKey
0x18003e5fa  call    cs:__imp_RegCloseKey
0x18003e601  nop     dword ptr [rax+rax+00h]
0x18003e606  test    ebx, ebx
0x18003e608  js      short loc_18003E62F
0x18003e60a  test    rbp, rbp
0x18003e60d  jz      short loc_18003E62F
0x18003e60f  mov     rdx, rbp
0x18003e612  lea     rcx, [rsp+0C8h+var_78]
0x18003e617  call    cs:__imp_GUIDFromStringW
0x18003e61e  nop     dword ptr [rax+rax+00h]
0x18003e623  neg     eax
0x18003e625  sbb     ebx, ebx
0x18003e627  not     ebx
0x18003e629  and     ebx, 80004005h
0x18003e62f  mov     eax, ebx
0x18003e631  mov     rcx, [rsp+0C8h+var_28]
0x18003e639  xor     rcx, rsp; StackCookie
0x18003e63c  call    __security_check_cookie
0x18003e641  lea     r11, [rsp+0C8h+var_18]
0x18003e649  mov     rbx, [r11+28h]
0x18003e64d  mov     rbp, [r11+30h]
0x18003e651  mov     rsp, r11
0x18003e654  pop     r14
0x18003e656  pop     rdi
0x18003e657  pop     rsi
0x18003e658  retn
```
