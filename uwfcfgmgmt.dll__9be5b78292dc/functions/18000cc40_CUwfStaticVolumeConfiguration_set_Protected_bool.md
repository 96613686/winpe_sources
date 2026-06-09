# CUwfStaticVolumeConfiguration::set_Protected(bool)

- ea: `0x18000cc40`
- end: `0x18000cd1c`
- name: `?set_Protected@CUwfStaticVolumeConfiguration@@QEAAJ_N@Z`
- size: `220`
- prototype: `int __fastcall(CUwfStaticVolumeConfiguration *this, unsigned __int8)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, installer_update`

## callers

- `0x18001a580`

## callees

- `0x18000a150`
- `0x18000cc40`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000cc9d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000cc9d`

## pseudocode

```c
int __fastcall CUwfStaticVolumeConfiguration::set_Protected(CUwfStaticVolumeConfiguration *this, unsigned __int8 a2)
{
  unsigned int v3; // edi
  int result; // eax
  HKEY v5; // rcx
  int Data; // [rsp+50h] [rbp+8h] BYREF
  DWORD Type; // [rsp+60h] [rbp+18h] BYREF
  DWORD cbData; // [rsp+68h] [rbp+20h] BYREF

  v3 = a2;
  if ( *((_BYTE *)this + 9) )
  {
    result = -2147024891;
LABEL_16:
    *(_DWORD *)(*((_QWORD *)this + 3) + 16LL) = result;
    return result;
  }
  v5 = (HKEY)*((_QWORD *)this + 2);
  Data = 0;
  Type = 0;
  cbData = 4;
  result = RegQueryValueExW(v5, L"VolumeEnabled", 0, &Type, (LPBYTE)&Data, &cbData);
  if ( result )
  {
    if ( result > 0 )
      result = (unsigned __int16)result | 0x80070000;
    if ( result == -2147024894 )
    {
      Data = 0;
      goto LABEL_13;
    }
  }
  else
  {
    if ( Type != 4 )
    {
      result = -2147023267;
      goto LABEL_16;
    }
    result = 0;
    if ( cbData != 4 )
    {
      result = -2147024883;
      goto LABEL_16;
    }
  }
  if ( result < 0 )
    goto LABEL_16;
LABEL_13:
  result = CUwfConfiguration::UpdateDWORDValue(
             *((CUwfConfiguration **)this + 3),
             (CUwfStaticVolumeConfiguration *)((char *)this + 16),
             L"VolumeEnabled",
             v3,
             1);
  if ( result == 1 )
    return 0;
  if ( result < 0 )
    goto LABEL_16;
  return result;
}

```

## disassembly

```asm
0x18000cc40  push    rbx
0x18000cc42  push    rsi
0x18000cc43  push    rdi
0x18000cc44  sub     rsp, 30h
0x18000cc48  cmp     byte ptr [rcx+9], 0
0x18000cc4c  mov     rbx, rcx
0x18000cc4f  movzx   edi, dl
0x18000cc52  jz      short loc_18000CC5E
0x18000cc54  mov     eax, 80070005h
0x18000cc59  jmp     loc_18000CD0D
0x18000cc5e  mov     rcx, [rcx+10h]; hKey
0x18000cc62  lea     rax, [rsp+48h+cbData]
0x18000cc67  mov     [rsp+48h+lpcbData], rax; lpcbData
0x18000cc6c  lea     r9, [rsp+48h+Type]; lpType
0x18000cc71  lea     rax, [rsp+48h+Data]
0x18000cc76  mov     [rsp+48h+Data], 0
0x18000cc7e  xor     r8d, r8d; lpReserved
0x18000cc81  mov     [rsp+48h+lpData], rax; lpData
0x18000cc86  lea     rdx, ValueName; "VolumeEnabled"
0x18000cc8d  mov     [rsp+48h+Type], 0
0x18000cc95  mov     [rsp+48h+cbData], 4
0x18000cc9d  call    cs:__imp_RegQueryValueExW
0x18000cca3  test    eax, eax
0x18000cca5  jz      short loc_18000CCC2
0x18000cca7  jle     short loc_18000CCB1
0x18000cca9  movzx   eax, ax
0x18000ccac  or      eax, 80070000h
0x18000ccb1  cmp     eax, 80070002h
0x18000ccb6  jnz     short loc_18000CCE0
0x18000ccb8  mov     [rsp+48h+Data], 0
0x18000ccc0  jmp     short loc_18000CCE4
0x18000ccc2  cmp     [rsp+48h+Type], 4
0x18000ccc7  jz      short loc_18000CCD0
0x18000ccc9  mov     eax, 8007065Dh
0x18000ccce  jmp     short loc_18000CD0D
0x18000ccd0  xor     eax, eax
0x18000ccd2  cmp     [rsp+48h+cbData], 4
0x18000ccd7  jz      short loc_18000CCE0
0x18000ccd9  mov     eax, 8007000Dh
0x18000ccde  jmp     short loc_18000CD0D
0x18000cce0  test    eax, eax
0x18000cce2  js      short loc_18000CD0D
0x18000cce4  mov     rcx, [rbx+18h]; this
0x18000cce8  lea     r8, ValueName; "VolumeEnabled"
0x18000ccef  mov     r9d, edi; unsigned int
0x18000ccf2  mov     byte ptr [rsp+48h+lpData], 1; bool
0x18000ccf7  lea     rdx, [rbx+10h]; struct CUwfRegKey *
0x18000ccfb  call    ?UpdateDWORDValue@CUwfConfiguration@@QEAAJAEAVCUwfRegKey@@PEBGK_N@Z; CUwfConfiguration::UpdateDWORDValue(CUwfRegKey &,ushort const *,ulong,bool)
0x18000cd00  cmp     eax, 1
0x18000cd03  jnz     short loc_18000CD09
0x18000cd05  xor     eax, eax
0x18000cd07  jmp     short loc_18000CD14
0x18000cd09  test    eax, eax
0x18000cd0b  jns     short loc_18000CD14
0x18000cd0d  mov     rcx, [rbx+18h]
0x18000cd11  mov     [rcx+10h], eax
0x18000cd14  add     rsp, 30h
0x18000cd18  pop     rdi
0x18000cd19  pop     rsi
0x18000cd1a  pop     rbx
0x18000cd1b  retn
```
