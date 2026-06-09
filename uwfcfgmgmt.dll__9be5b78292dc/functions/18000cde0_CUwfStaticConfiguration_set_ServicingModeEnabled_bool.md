# CUwfStaticConfiguration::set_ServicingModeEnabled(bool)

- ea: `0x18000cde0`
- end: `0x18000cee2`
- name: `?set_ServicingModeEnabled@CUwfStaticConfiguration@@QEAAJ_N@Z`
- size: `258`
- prototype: `__int64 __fastcall(CUwfStaticConfiguration *this, unsigned __int8)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x18001a2d0`

## callees

- `0x180006144`
- `0x180009688`
- `0x18000a150`
- `0x18000cde0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000ce6c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000ce6c`

## pseudocode

```c
__int64 __fastcall CUwfStaticConfiguration::set_ServicingModeEnabled(CUwfStaticConfiguration *this, unsigned __int8 a2)
{
  CUwfConfiguration **v2; // rbx
  unsigned __int64 v4; // rcx
  HKEY *v6; // rsi
  HKEY v7; // rcx
  LSTATUS v8; // eax
  HKEY v9; // r8
  int v10; // eax
  DWORD Type; // [rsp+50h] [rbp+8h] BYREF
  DWORD cbData; // [rsp+60h] [rbp+18h] BYREF
  int Data; // [rsp+68h] [rbp+20h] BYREF

  v2 = (CUwfConfiguration **)((char *)this + 32);
  if ( *((_BYTE *)this + 9) )
  {
    LODWORD(v4) = -2147024891;
  }
  else
  {
    v6 = (HKEY *)((char *)this + 16);
    LODWORD(v4) = CUwfConfiguration::UpdateDWORDValue(
                    *v2,
                    (CUwfStaticConfiguration *)((char *)this + 16),
                    L"ServicingModeEnabled",
                    a2,
                    1);
    if ( (v4 & 0x80000000) == 0LL )
    {
      v7 = *v6;
      Data = 0;
      Type = 0;
      cbData = 4;
      v8 = RegQueryValueExW(v7, L"UWFEnabled", 0, &Type, (LPBYTE)&Data, &cbData);
      v4 = (unsigned int)v8;
      if ( v8 )
      {
        if ( v8 > 0 )
          v4 = (unsigned __int16)v8 | 0x80070000;
        if ( (v4 & 0x80000000) != 0LL )
          goto LABEL_3;
      }
      else
      {
        if ( Type != 4 )
        {
          LODWORD(v4) = -2147023267;
          goto LABEL_3;
        }
        if ( cbData != 4 )
        {
          LODWORD(v4) = -2147024883;
          goto LABEL_3;
        }
      }
      if ( Data == 0
        || (!a2
          ? (v10 = CUwfStaticConfiguration::SetBackgroundTasksDisabled((CUwfStaticConfiguration *)v4, 0))
          : (v10 = CUwfStaticConfiguration::ClearBackgroundTasksDisabled((CUwfStaticConfiguration *)v4, 2u, v9)),
            LODWORD(v4) = v10,
            v10 >= 0) )
      {
        LODWORD(v4) = 0;
        return (unsigned int)v4;
      }
    }
  }
LABEL_3:
  *((_DWORD *)*v2 + 4) = v4;
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000cde0  push    rbx
0x18000cde2  push    rsi
0x18000cde3  push    rdi
0x18000cde4  sub     rsp, 30h
0x18000cde8  cmp     byte ptr [rcx+9], 0
0x18000cdec  lea     rbx, [rcx+20h]
0x18000cdf0  movzx   edi, dl
0x18000cdf3  jz      short loc_18000CE0A
0x18000cdf5  mov     ecx, 80070005h
0x18000cdfa  mov     rax, [rbx]
0x18000cdfd  mov     [rax+10h], ecx
0x18000ce00  mov     eax, ecx
0x18000ce02  add     rsp, 30h
0x18000ce06  pop     rdi
0x18000ce07  pop     rsi
0x18000ce08  pop     rbx
0x18000ce09  retn
0x18000ce0a  lea     rsi, [rcx+10h]
0x18000ce0e  mov     byte ptr [rsp+48h+lpData], 1; bool
0x18000ce13  mov     rcx, [rbx]; this
0x18000ce16  lea     r8, aServicingmodee; "ServicingModeEnabled"
0x18000ce1d  mov     rdx, rsi; struct CUwfRegKey *
0x18000ce20  mov     r9d, edi; unsigned int
0x18000ce23  call    ?UpdateDWORDValue@CUwfConfiguration@@QEAAJAEAVCUwfRegKey@@PEBGK_N@Z; CUwfConfiguration::UpdateDWORDValue(CUwfRegKey &,ushort const *,ulong,bool)
0x18000ce28  mov     ecx, eax
0x18000ce2a  test    eax, eax
0x18000ce2c  js      short loc_18000CDFA
0x18000ce2e  mov     rcx, [rsi]; hKey
0x18000ce31  lea     rax, [rsp+48h+cbData]
0x18000ce36  mov     [rsp+48h+lpcbData], rax; lpcbData
0x18000ce3b  lea     r9, [rsp+48h+Type]; lpType
0x18000ce40  lea     rax, [rsp+48h+Data]
0x18000ce45  mov     [rsp+48h+Data], 0
0x18000ce4d  xor     r8d, r8d; lpReserved
0x18000ce50  mov     [rsp+48h+lpData], rax; lpData
0x18000ce55  lea     rdx, aUwfenabled; "UWFEnabled"
0x18000ce5c  mov     [rsp+48h+Type], 0
0x18000ce64  mov     [rsp+48h+cbData], 4
0x18000ce6c  call    cs:__imp_RegQueryValueExW
0x18000ce72  mov     ecx, eax
0x18000ce74  test    eax, eax
0x18000ce76  jz      short loc_18000CEB7
0x18000ce78  jle     short loc_18000CE83
0x18000ce7a  movzx   ecx, ax
0x18000ce7d  or      ecx, 80070000h; this
0x18000ce83  test    ecx, ecx
0x18000ce85  js      loc_18000CDFA
0x18000ce8b  cmp     [rsp+48h+Data], 0
0x18000ce90  setnz   al
0x18000ce93  cmp     al, 1
0x18000ce95  jnz     short loc_18000CEB0
0x18000ce97  test    dil, dil
0x18000ce9a  jz      short loc_18000CED9
0x18000ce9c  mov     edx, 2; unsigned int
0x18000cea1  call    ?ClearBackgroundTasksDisabled@CUwfStaticConfiguration@@AEAAJK@Z; CUwfStaticConfiguration::ClearBackgroundTasksDisabled(ulong)
0x18000cea6  mov     ecx, eax
0x18000cea8  test    eax, eax
0x18000ceaa  js      loc_18000CDFA
0x18000ceb0  xor     ecx, ecx
0x18000ceb2  jmp     loc_18000CE00
0x18000ceb7  cmp     [rsp+48h+Type], 4
0x18000cebc  jz      short loc_18000CEC8
0x18000cebe  mov     ecx, 8007065Dh
0x18000cec3  jmp     loc_18000CDFA
0x18000cec8  cmp     [rsp+48h+cbData], 4
0x18000cecd  jz      short loc_18000CE8B
0x18000cecf  mov     ecx, 8007000Dh
0x18000ced4  jmp     loc_18000CDFA
0x18000ced9  xor     edx, edx; unsigned int
0x18000cedb  call    ?SetBackgroundTasksDisabled@CUwfStaticConfiguration@@AEAAJK@Z; CUwfStaticConfiguration::SetBackgroundTasksDisabled(ulong)
0x18000cee0  jmp     short loc_18000CEA6
```
