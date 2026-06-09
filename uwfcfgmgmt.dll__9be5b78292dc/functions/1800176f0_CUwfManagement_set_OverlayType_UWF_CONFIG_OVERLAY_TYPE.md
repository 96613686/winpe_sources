# CUwfManagement::set_OverlayType(_UWF_CONFIG_OVERLAY_TYPE)

- ea: `0x1800176f0`
- end: `0x18001783a`
- name: `?set_OverlayType@CUwfManagement@@QEAAJW4_UWF_CONFIG_OVERLAY_TYPE@@@Z`
- size: `330`
- prototype: `int __fastcall(__int64, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18001a010`

## callees

- `0x18000c300`
- `0x1800176f0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180017744`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800177dc`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180017744`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800177dc`

## pseudocode

```c
int __fastcall CUwfManagement::set_OverlayType(__int64 a1, unsigned int a2)
{
  __int64 v3; // rsi
  HKEY v5; // rcx
  int result; // eax
  bool v7; // sf
  int v8; // ecx
  HKEY v9; // rcx
  bool v10; // sf
  DWORD Type; // [rsp+50h] [rbp+20h] BYREF
  DWORD cbData; // [rsp+60h] [rbp+30h] BYREF
  int Data; // [rsp+68h] [rbp+38h] BYREF

  v3 = a1 + 168;
  v5 = *(HKEY *)(a1 + 184);
  Data = 0;
  Type = 0;
  cbData = 4;
  result = RegQueryValueExW(v5, L"OverlayType", 0, &Type, (LPBYTE)&Data, &cbData);
  v7 = result < 0;
  if ( result )
  {
    if ( result > 0 )
    {
      result = (unsigned __int16)result | 0x80070000;
      v7 = result < 0;
    }
    if ( v7 )
      goto LABEL_26;
  }
  else
  {
    if ( Type != 4 )
      goto LABEL_7;
    result = 0;
    if ( cbData != 4 )
    {
LABEL_11:
      result = -2147024883;
      goto LABEL_26;
    }
  }
  if ( Data )
  {
    if ( Data != 1 )
      goto LABEL_11;
    v8 = 1;
  }
  else
  {
    v8 = 0;
  }
  if ( a2 == v8 )
    return result;
  v9 = *(HKEY *)(a1 + 136);
  Data = 0;
  Type = 0;
  cbData = 4;
  result = RegQueryValueExW(v9, L"UWFEnabled", 0, &Type, (LPBYTE)&Data, &cbData);
  v10 = result < 0;
  if ( result )
  {
    if ( result > 0 )
    {
      result = (unsigned __int16)result | 0x80070000;
      v10 = result < 0;
    }
    if ( v10 )
      goto LABEL_26;
    goto LABEL_22;
  }
  if ( Type != 4 )
  {
LABEL_7:
    result = -2147023267;
    goto LABEL_26;
  }
  if ( cbData != 4 )
    goto LABEL_11;
LABEL_22:
  if ( Data )
  {
    result = -2147024891;
    goto LABEL_26;
  }
  result = CUwfStaticConfiguration::set_OverlayType(v3, a2);
  if ( result < 0 )
LABEL_26:
    *(_DWORD *)(a1 + 12) = result;
  return result;
}

```

## disassembly

```asm
0x1800176f0  mov     [rsp-18h+arg_8], rbx
0x1800176f5  push    rbp
0x1800176f6  push    rsi
0x1800176f7  push    rdi
0x1800176f8  mov     rbp, rsp
0x1800176fb  sub     rsp, 30h
0x1800176ff  mov     ebx, edx
0x180017701  lea     rsi, [rcx+0A8h]
0x180017708  mov     rdi, rcx
0x18001770b  mov     rcx, [rsi+10h]; hKey
0x18001770f  lea     rax, [rbp+cbData]
0x180017713  mov     [rsp+30h+lpcbData], rax; lpcbData
0x180017718  lea     r9, [rbp+Type]; lpType
0x18001771c  lea     rax, [rbp+Data]
0x180017720  mov     [rbp+Data], 0
0x180017727  xor     r8d, r8d; lpReserved
0x18001772a  mov     [rsp+30h+lpData], rax; lpData
0x18001772f  lea     rdx, aOverlaytype; "OverlayType"
0x180017736  mov     [rbp+Type], 0
0x18001773d  mov     [rbp+cbData], 4
0x180017744  call    cs:__imp_RegQueryValueExW
0x18001774a  test    eax, eax
0x18001774c  jz      short loc_180017761
0x18001774e  jle     short loc_18001775A
0x180017750  movzx   eax, ax
0x180017753  or      eax, 80070000h
0x180017758  test    eax, eax
0x18001775a  jns     short loc_180017779
0x18001775c  jmp     loc_18001782A
0x180017761  cmp     [rbp+Type], 4
0x180017765  jz      short loc_180017771
0x180017767  mov     eax, 8007065Dh
0x18001776c  jmp     loc_18001782A
0x180017771  xor     eax, eax
0x180017773  cmp     [rbp+cbData], 4
0x180017777  jnz     short loc_180017785
0x180017779  mov     ecx, [rbp+Data]
0x18001777c  test    ecx, ecx
0x18001777e  jz      short loc_180017796
0x180017780  cmp     ecx, 1
0x180017783  jz      short loc_18001778F
0x180017785  mov     eax, 8007000Dh
0x18001778a  jmp     loc_18001782A
0x18001778f  mov     ecx, 1
0x180017794  jmp     short loc_180017798
0x180017796  xor     ecx, ecx
0x180017798  cmp     ebx, ecx
0x18001779a  jz      loc_18001782D
0x1800177a0  mov     rcx, [rdi+88h]; hKey
0x1800177a7  lea     rax, [rbp+cbData]
0x1800177ab  mov     [rsp+30h+lpcbData], rax; lpcbData
0x1800177b0  lea     r9, [rbp+Type]; lpType
0x1800177b4  lea     rax, [rbp+Data]
0x1800177b8  mov     [rbp+Data], 0
0x1800177bf  xor     r8d, r8d; lpReserved
0x1800177c2  mov     [rsp+30h+lpData], rax; lpData
0x1800177c7  lea     rdx, aUwfenabled; "UWFEnabled"
0x1800177ce  mov     [rbp+Type], 0
0x1800177d5  mov     [rbp+cbData], 4
0x1800177dc  call    cs:__imp_RegQueryValueExW
0x1800177e2  test    eax, eax
0x1800177e4  jz      short loc_1800177F6
0x1800177e6  jle     short loc_1800177F2
0x1800177e8  movzx   eax, ax
0x1800177eb  or      eax, 80070000h
0x1800177f0  test    eax, eax
0x1800177f2  jns     short loc_18001780A
0x1800177f4  jmp     short loc_18001782A
0x1800177f6  cmp     [rbp+Type], 4
0x1800177fa  jnz     loc_180017767
0x180017800  cmp     [rbp+cbData], 4
0x180017804  jnz     loc_180017785
0x18001780a  cmp     [rbp+Data], 0
0x18001780e  setnz   al
0x180017811  test    al, al
0x180017813  jnz     short loc_180017825
0x180017815  mov     edx, ebx
0x180017817  mov     rcx, rsi
0x18001781a  call    ?set_OverlayType@CUwfStaticConfiguration@@QEAAJW4_UWF_CONFIG_OVERLAY_TYPE@@@Z; CUwfStaticConfiguration::set_OverlayType(_UWF_CONFIG_OVERLAY_TYPE)
0x18001781f  test    eax, eax
0x180017821  js      short loc_18001782A
0x180017823  jmp     short loc_18001782D
0x180017825  mov     eax, 80070005h
0x18001782a  mov     [rdi+0Ch], eax
0x18001782d  mov     rbx, [rsp+30h+arg_8]
0x180017832  add     rsp, 30h
0x180017836  pop     rdi
0x180017837  pop     rsi
0x180017838  pop     rbp
0x180017839  retn
```
