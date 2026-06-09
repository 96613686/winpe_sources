# Settings::_GetDeviceClassPropertySize(Autoplay::IDeviceProperties *,ushort const *,ulong *)

- ea: `0x180006578`
- end: `0x180006745`
- name: `?_GetDeviceClassPropertySize@Settings@@YAJPEAVIDeviceProperties@Autoplay@@PEBGPEAK@Z`
- size: `461`
- prototype: `__int64 __fastcall(Settings *this, struct Autoplay::IDeviceProperties *, unsigned int *, unsigned int *)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000541c`
- `0x1800055b4`
- `0x180005e80`

## callees

- `0x180006578`
- `0x1800329cc`
- `0x1800329f0`
- `0x180032c90`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800066d4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800066d4`

## pseudocode

```c
__int64 __fastcall Settings::_GetDeviceClassPropertySize(
        Settings *this,
        struct Autoplay::IDeviceProperties *a2,
        unsigned int *a3,
        unsigned int *a4)
{
  signed int Generic; // ebx
  __int64 v7; // r8
  const wchar_t *v8; // rcx
  __int64 v9; // rax
  WCHAR *v10; // r9
  __int64 v11; // rdx
  __int64 v12; // r10
  __int64 v13; // r11
  WCHAR *v14; // rcx
  WCHAR *v15; // rdx
  unsigned __int64 v16; // rdi
  WCHAR *v17; // rax
  WCHAR *v18; // rcx
  LSTATUS v19; // eax
  HKEY phkResult; // [rsp+30h] [rbp-468h] BYREF
  WCHAR SubKey[264]; // [rsp+40h] [rbp-458h] BYREF
  _BYTE v23[528]; // [rsp+250h] [rbp-248h] BYREF

  Generic = (*(__int64 (__fastcall **)(Settings *, const WCHAR *, _BYTE *, __int64))(*(_QWORD *)this + 24LL))(
              this,
              L"DeviceClass",
              v23,
              260);
  *a3 = 0;
  if ( Generic >= 0 )
  {
    v7 = 2147483646;
    v8 = L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\AutoplayHandlers\\DeviceClasses\\";
    v9 = 2147483646;
    v10 = SubKey;
    v11 = 260;
    v12 = 0;
    do
    {
      if ( !v9 )
        break;
      if ( !*v8 )
        break;
      *v10++ = *v8++;
      --v9;
      ++v12;
      --v11;
    }
    while ( v11 );
    v13 = v12 - 1;
    v14 = v10 - 1;
    if ( v11 )
      v13 = v12;
    Generic = v11 == 0 ? 0x8007007A : 0;
    if ( v11 )
      v14 = v10;
    *v14 = 0;
    if ( v11 )
    {
      v15 = &SubKey[v13];
      v16 = 260 - v13;
      if ( 260 == v13 )
      {
        return (unsigned int)-2147024809;
      }
      else if ( v16 <= 0x7FFFFFFF )
      {
        v17 = (WCHAR *)v23;
        do
        {
          if ( !v7 )
            break;
          if ( !*v17 )
            break;
          *v15++ = *v17++;
          --v7;
          --v16;
        }
        while ( v16 );
        v18 = v15 - 1;
        Generic = v16 == 0 ? 0x8007007A : 0;
        if ( v16 )
          v18 = v15;
        *v18 = 0;
        if ( v16 )
        {
          phkResult = 0;
          v19 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 1u, &phkResult);
          Generic = v19;
          if ( v19 > 0 )
            Generic = (unsigned __int16)v19 | 0x80070000;
          if ( Generic >= 0 )
          {
            Generic = _RegQueryGeneric(phkResult, 0, (const unsigned __int16 *)a2, 0, 0, a3);
            _RegCloseKey(phkResult);
          }
        }
      }
      else
      {
        Generic = -2147024809;
        *v15 = 0;
      }
    }
  }
  return (unsigned int)Generic;
}

```

## disassembly

```asm
0x180006578  push    rbx
0x18000657a  push    rbp
0x18000657b  push    rsi
0x18000657c  push    rdi
0x18000657d  push    r14
0x18000657f  sub     rsp, 470h
0x180006586  mov     rax, cs:__security_cookie
0x18000658d  xor     rax, rsp
0x180006590  mov     [rsp+498h+var_38], rax
0x180006598  mov     rax, [rcx]
0x18000659b  mov     rsi, r8
0x18000659e  mov     rbp, rdx
0x1800065a1  lea     r8, [rsp+498h+var_248]
0x1800065a9  mov     edi, 104h
0x1800065ae  lea     rdx, aDeviceclass; "DeviceClass"
0x1800065b5  mov     r9d, edi
0x1800065b8  mov     rax, [rax+18h]
0x1800065bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800065c1  xor     r14d, r14d
0x1800065c4  mov     ebx, eax
0x1800065c6  mov     [rsi], r14d
0x1800065c9  test    eax, eax
0x1800065cb  js      loc_180006725
0x1800065d1  mov     r8d, 7FFFFFFEh
0x1800065d7  lea     rcx, aSoftwareMicros_5; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800065de  mov     eax, r8d
0x1800065e1  lea     r9, [rsp+498h+SubKey]
0x1800065e6  mov     edx, edi
0x1800065e8  mov     r10d, r14d
0x1800065eb  test    rax, rax
0x1800065ee  jz      short loc_180006612
0x1800065f0  movzx   r11d, word ptr [rcx]
0x1800065f4  test    r11w, r11w
0x1800065f8  jz      short loc_180006612
0x1800065fa  mov     [r9], r11w
0x1800065fe  add     rcx, 2
0x180006602  add     r9, 2
0x180006606  dec     rax
0x180006609  inc     r10
0x18000660c  sub     rdx, 1
0x180006610  jnz     short loc_1800065EB
0x180006612  test    rdx, rdx
0x180006615  lea     r11, [r10-1]
0x180006619  mov     rax, rdx
0x18000661c  lea     rcx, [r9-2]
0x180006620  cmovnz  r11, r10
0x180006624  neg     rax
0x180006627  mov     r10d, 8007007Ah
0x18000662d  sbb     ebx, ebx
0x18000662f  not     ebx
0x180006631  and     ebx, r10d
0x180006634  test    rdx, rdx
0x180006637  cmovnz  rcx, r9
0x18000663b  mov     [rcx], r14w
0x18000663f  jz      loc_180006725
0x180006645  lea     rdx, [rsp+498h+SubKey]
0x18000664a  lea     rdx, [rdx+r11*2]
0x18000664e  sub     rdi, r11
0x180006651  jz      loc_180006717
0x180006657  cmp     rdi, 7FFFFFFFh
0x18000665e  jbe     short loc_180006669
0x180006660  lea     ebx, [r10-23h]
0x180006664  jmp     loc_180006721
0x180006669  lea     rax, [rsp+498h+var_248]
0x180006671  test    r8, r8
0x180006674  jz      short loc_180006692
0x180006676  movzx   ecx, word ptr [rax]
0x180006679  test    cx, cx
0x18000667c  jz      short loc_180006692
0x18000667e  mov     [rdx], cx
0x180006681  add     rax, 2
0x180006685  add     rdx, 2
0x180006689  dec     r8
0x18000668c  sub     rdi, 1
0x180006690  jnz     short loc_180006671
0x180006692  mov     rax, rdi
0x180006695  lea     rcx, [rdx-2]
0x180006699  neg     rax
0x18000669c  sbb     ebx, ebx
0x18000669e  not     ebx
0x1800066a0  and     ebx, r10d
0x1800066a3  test    rdi, rdi
0x1800066a6  cmovnz  rcx, rdx
0x1800066aa  mov     [rcx], r14w
0x1800066ae  jz      short loc_180006725
0x1800066b0  lea     rax, [rsp+498h+var_468]
0x1800066b5  mov     [rsp+498h+var_468], r14
0x1800066ba  mov     r9d, 1; samDesired
0x1800066c0  mov     [rsp+498h+phkResult], rax; phkResult
0x1800066c5  xor     r8d, r8d; ulOptions
0x1800066c8  lea     rdx, [rsp+498h+SubKey]; lpSubKey
0x1800066cd  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800066d4  call    cs:__imp_RegOpenKeyExW
0x1800066da  mov     ebx, eax
0x1800066dc  test    eax, eax
0x1800066de  jle     short loc_1800066E9
0x1800066e0  movzx   ebx, ax
0x1800066e3  or      ebx, 80070000h
0x1800066e9  test    ebx, ebx
0x1800066eb  js      short loc_180006725
0x1800066ed  mov     rcx, [rsp+498h+var_468]; HKEY
0x1800066f2  xor     r9d, r9d; unsigned int *
0x1800066f5  mov     [rsp+498h+var_470], rsi; unsigned int *
0x1800066fa  mov     r8, rbp; unsigned __int16 *
0x1800066fd  xor     edx, edx; unsigned __int16 *
0x1800066ff  mov     [rsp+498h+phkResult], r14; unsigned __int8 *
0x180006704  call    ?_RegQueryGeneric@@YAJPEAUHKEY__@@PEBG1PEAKPEAE2@Z; _RegQueryGeneric(HKEY__ *,ushort const *,ushort const *,ulong *,uchar *,ulong *)
0x180006709  mov     rcx, [rsp+498h+var_468]; HKEY
0x18000670e  mov     ebx, eax
0x180006710  call    ?_RegCloseKey@@YAJPEAUHKEY__@@@Z; _RegCloseKey(HKEY__ *)
0x180006715  jmp     short loc_180006725
0x180006717  mov     ebx, 80070057h
0x18000671c  test    rdi, rdi
0x18000671f  jz      short loc_180006725
0x180006721  mov     [rdx], r14w
0x180006725  mov     eax, ebx
0x180006727  mov     rcx, [rsp+498h+var_38]
0x18000672f  xor     rcx, rsp; StackCookie
0x180006732  call    __security_check_cookie
0x180006737  add     rsp, 470h
0x18000673e  pop     r14
0x180006740  pop     rdi
0x180006741  pop     rsi
0x180006742  pop     rbp
0x180006743  pop     rbx
0x180006744  retn
```
