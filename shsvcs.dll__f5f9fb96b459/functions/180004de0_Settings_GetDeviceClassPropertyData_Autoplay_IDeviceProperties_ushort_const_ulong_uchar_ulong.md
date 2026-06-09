# Settings::_GetDeviceClassPropertyData(Autoplay::IDeviceProperties *,ushort const *,ulong,uchar *,ulong)

- ea: `0x180004de0`
- end: `0x180004ffb`
- name: `?_GetDeviceClassPropertyData@Settings@@YAJPEAVIDeviceProperties@Autoplay@@PEBGKPEAEK@Z`
- size: `539`
- prototype: `__int64 __fastcall(Settings *this, struct Autoplay::IDeviceProperties *, const unsigned __int16 *, unsigned __int8 *, unsigned __int8 *)`
- caller_count: `5`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800036e0`
- `0x180004b50`
- `0x180005010`
- `0x180006060`
- `0x180019280`

## callees

- `0x180004de0`
- `0x1800329cc`
- `0x1800329f0`
- `0x180032c90`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180004f67`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180004f67`

## pseudocode

```c
__int64 __fastcall Settings::_GetDeviceClassPropertyData(
        Settings *this,
        struct Autoplay::IDeviceProperties *a2,
        const unsigned __int16 *a3,
        unsigned __int8 *a4,
        unsigned __int8 *a5)
{
  int v6; // esi
  __int64 result; // rax
  const wchar_t *v9; // rdx
  int v10; // edi
  WCHAR *v11; // r8
  __int64 v12; // r11
  __int64 v13; // r10
  __int64 v14; // rcx
  __int64 v15; // r9
  unsigned int v16; // r9d
  WCHAR *v17; // rax
  unsigned __int64 v18; // rbx
  WCHAR *v19; // rcx
  WCHAR *v20; // rcx
  LSTATUS v21; // eax
  signed int v22; // ebx
  unsigned int v23; // [rsp+30h] [rbp-478h] BYREF
  unsigned int v24; // [rsp+38h] [rbp-470h] BYREF
  HKEY phkResult; // [rsp+40h] [rbp-468h] BYREF
  WCHAR SubKey[264]; // [rsp+50h] [rbp-458h] BYREF
  _BYTE v27[528]; // [rsp+260h] [rbp-248h] BYREF

  v6 = (int)a3;
  result = (*(__int64 (__fastcall **)(Settings *, const WCHAR *, _BYTE *, __int64))(*(_QWORD *)this + 24LL))(
             this,
             L"DeviceClass",
             v27,
             260);
  if ( (int)result < 0 )
    return result;
  v9 = L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\AutoplayHandlers\\DeviceClasses\\";
  v10 = 0;
  v11 = SubKey;
  v12 = 2147483646;
  v13 = 0;
  v14 = 2147483646;
  v15 = 260;
  while ( v14 && *v9 )
  {
    *v11++ = *v9++;
    --v14;
    ++v13;
    if ( !--v15 )
    {
      *(v11 - 1) = 0;
      v16 = -2147024774;
      v10 = -2147024774;
      v17 = &SubKey[v13 - 1];
      v18 = 260 - (v13 - 1);
      goto LABEL_8;
    }
  }
  v16 = -2147024774;
  *v11 = 0;
  v18 = 260 - v13;
  v17 = &SubKey[v13];
LABEL_8:
  if ( v10 < 0 )
    return (unsigned int)v10;
  if ( !v18 )
    return (unsigned int)-2147024809;
  if ( v18 > 0x7FFFFFFF )
  {
    v16 = -2147024809;
    *v17 = 0;
    return v16;
  }
  v19 = (WCHAR *)v27;
  do
  {
    if ( !v12 )
      break;
    if ( !*v19 )
      break;
    *v17++ = *v19++;
    --v12;
    --v18;
  }
  while ( v18 );
  v20 = v17 - 1;
  if ( v18 )
  {
    v20 = v17;
    v16 = 0;
  }
  *v20 = 0;
  if ( !v18 )
    return v16;
  phkResult = 0;
  v21 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 1u, &phkResult);
  v22 = v21;
  if ( v21 > 0 )
    v22 = (unsigned __int16)v21 | 0x80070000;
  if ( v22 >= 0 )
  {
    v24 = (unsigned int)a5;
    v23 = 0;
    v22 = _RegQueryGeneric(phkResult, 0, (const unsigned __int16 *)a2, &v23, a4, &v24);
    if ( v22 >= 0 && v23 != v6 )
      v22 = -2147467259;
    _RegCloseKey(phkResult);
  }
  return (unsigned int)v22;
}

```

## disassembly

```asm
0x180004de0  push    rbx
0x180004de2  push    rbp
0x180004de3  push    rsi
0x180004de4  push    r14
0x180004de6  sub     rsp, 488h
0x180004ded  mov     rax, cs:__security_cookie
0x180004df4  xor     rax, rsp
0x180004df7  mov     [rsp+4A8h+var_38], rax
0x180004dff  mov     rax, [rcx]
0x180004e02  mov     r14, r9
0x180004e05  mov     esi, r8d
0x180004e08  mov     rbp, rdx
0x180004e0b  mov     ebx, 104h
0x180004e10  lea     r8, [rsp+4A8h+var_248]
0x180004e18  mov     r9d, ebx
0x180004e1b  lea     rdx, aDeviceclass; "DeviceClass"
0x180004e22  mov     rax, [rax+18h]
0x180004e26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e2b  test    eax, eax
0x180004e2d  js      loc_180004ECA
0x180004e33  mov     [rsp+4A8h+var_28], rdi
0x180004e3b  lea     rdx, aSoftwareMicros_5; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180004e42  xor     edi, edi
0x180004e44  lea     r8, [rsp+4A8h+SubKey]
0x180004e49  mov     r11d, 7FFFFFFEh
0x180004e4f  xor     r10d, r10d
0x180004e52  mov     ecx, r11d
0x180004e55  mov     r9d, ebx
0x180004e58  test    rcx, rcx
0x180004e5b  jz      short loc_180004EA4
0x180004e5d  movzx   eax, word ptr [rdx]
0x180004e60  test    ax, ax
0x180004e63  jz      short loc_180004E9F
0x180004e65  mov     [r8], ax
0x180004e69  add     rdx, 2
0x180004e6d  add     r8, 2
0x180004e71  dec     rcx
0x180004e74  inc     r10
0x180004e77  sub     r9, 1
0x180004e7b  jnz     short loc_180004E58
0x180004e7d  xor     eax, eax
0x180004e7f  lea     rcx, [r10-1]
0x180004e83  mov     [r8-2], ax
0x180004e88  mov     r9d, 8007007Ah
0x180004e8e  lea     rax, [rsp+4A8h+SubKey]
0x180004e93  mov     edi, r9d
0x180004e96  lea     rax, [rax+rcx*2]
0x180004e9a  sub     rbx, rcx
0x180004e9d  jmp     short loc_180004EBC
0x180004e9f  test    r9, r9
0x180004ea2  jz      short loc_180004E7D
0x180004ea4  xor     eax, eax
0x180004ea6  mov     r9d, 8007007Ah
0x180004eac  mov     [r8], ax
0x180004eb0  sub     rbx, r10
0x180004eb3  lea     rax, [rsp+4A8h+SubKey]
0x180004eb8  lea     rax, [rax+r10*2]
0x180004ebc  test    edi, edi
0x180004ebe  jns     short loc_180004EE7
0x180004ec0  mov     eax, edi
0x180004ec2  mov     rdi, [rsp+4A8h+var_28]
0x180004eca  mov     rcx, [rsp+4A8h+var_38]
0x180004ed2  xor     rcx, rsp; StackCookie
0x180004ed5  call    __security_check_cookie
0x180004eda  add     rsp, 488h
0x180004ee1  pop     r14
0x180004ee3  pop     rsi
0x180004ee4  pop     rbp
0x180004ee5  pop     rbx
0x180004ee6  retn
0x180004ee7  test    rbx, rbx
0x180004eea  jz      loc_180004FE3
0x180004ef0  cmp     rbx, 7FFFFFFFh
0x180004ef7  ja      loc_180004F87
0x180004efd  lea     rcx, [rsp+4A8h+var_248]
0x180004f05  test    r11, r11
0x180004f08  jz      short loc_180004F26
0x180004f0a  movzx   edx, word ptr [rcx]
0x180004f0d  test    dx, dx
0x180004f10  jz      short loc_180004F26
0x180004f12  mov     [rax], dx
0x180004f15  add     rcx, 2
0x180004f19  add     rax, 2
0x180004f1d  dec     r11
0x180004f20  sub     rbx, 1
0x180004f24  jnz     short loc_180004F05
0x180004f26  test    rbx, rbx
0x180004f29  lea     rcx, [rax-2]
0x180004f2d  cmovnz  rcx, rax
0x180004f31  xor     eax, eax
0x180004f33  test    rbx, rbx
0x180004f36  cmovnz  r9d, eax
0x180004f3a  mov     [rcx], ax
0x180004f3d  jz      loc_180004FF3
0x180004f43  mov     [rsp+4A8h+var_468], rax
0x180004f48  lea     rdx, [rsp+4A8h+SubKey]; lpSubKey
0x180004f4d  lea     rax, [rsp+4A8h+var_468]
0x180004f52  mov     r9d, 1; samDesired
0x180004f58  xor     r8d, r8d; ulOptions
0x180004f5b  mov     [rsp+4A8h+phkResult], rax; phkResult
0x180004f60  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180004f67  call    cs:__imp_RegOpenKeyExW
0x180004f6d  mov     ebx, eax
0x180004f6f  test    eax, eax
0x180004f71  jle     short loc_180004F7C
0x180004f73  movzx   ebx, ax
0x180004f76  or      ebx, 80070000h
0x180004f7c  test    ebx, ebx
0x180004f7e  jns     short loc_180004F8F
0x180004f80  mov     eax, ebx
0x180004f82  jmp     loc_180004EC2
0x180004f87  mov     r9d, 80070057h
0x180004f8d  jmp     short loc_180004FEE
0x180004f8f  mov     eax, dword ptr [rsp+4A8h+arg_20]
0x180004f96  lea     r9, [rsp+4A8h+var_478]; unsigned int *
0x180004f9b  mov     rcx, [rsp+4A8h+var_468]; HKEY
0x180004fa0  mov     r8, rbp; unsigned __int16 *
0x180004fa3  mov     [rsp+4A8h+var_470], eax
0x180004fa7  xor     edx, edx; unsigned __int16 *
0x180004fa9  lea     rax, [rsp+4A8h+var_470]
0x180004fae  mov     [rsp+4A8h+var_478], 0
0x180004fb6  mov     [rsp+4A8h+var_480], rax; unsigned int *
0x180004fbb  mov     [rsp+4A8h+phkResult], r14; unsigned __int8 *
0x180004fc0  call    ?_RegQueryGeneric@@YAJPEAUHKEY__@@PEBG1PEAKPEAE2@Z; _RegQueryGeneric(HKEY__ *,ushort const *,ushort const *,ulong *,uchar *,ulong *)
0x180004fc5  mov     ebx, eax
0x180004fc7  test    eax, eax
0x180004fc9  js      short loc_180004FD7
0x180004fcb  cmp     [rsp+4A8h+var_478], esi
0x180004fcf  mov     eax, 80004005h
0x180004fd4  cmovnz  ebx, eax
0x180004fd7  mov     rcx, [rsp+4A8h+var_468]; HKEY
0x180004fdc  call    ?_RegCloseKey@@YAJPEAUHKEY__@@@Z; _RegCloseKey(HKEY__ *)
0x180004fe1  jmp     short loc_180004F80
0x180004fe3  mov     r9d, 80070057h
0x180004fe9  test    rbx, rbx
0x180004fec  jz      short loc_180004FF3
0x180004fee  xor     ecx, ecx
0x180004ff0  mov     [rax], cx
0x180004ff3  mov     eax, r9d
0x180004ff6  jmp     loc_180004EC2
```
