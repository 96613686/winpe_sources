# HaveCapturedUwfSettings(bool *)

- ea: `0x180010040`
- end: `0x180010108`
- name: `?HaveCapturedUwfSettings@@YAJPEA_N@Z`
- size: `200`
- prototype: `__int64 __fastcall(bool *)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x180008160`
- `0x18000f258`
- `0x1800166c0`

## callees

- `0x18000d5f0`
- `0x18000de30`
- `0x180010040`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800100b5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800100b5`

## string_xrefs

- `0x180010063`: `SYSTEM\CurrentControlSet\Services\UWFVOL\Parameters.Default`

## pseudocode

```c
__int64 __fastcall HaveCapturedUwfSettings(bool *a1)
{
  signed int v2; // ebx
  LSTATUS v3; // eax
  DWORD Type; // [rsp+50h] [rbp+20h] BYREF
  DWORD cbData; // [rsp+58h] [rbp+28h] BYREF
  int Data; // [rsp+60h] [rbp+30h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+38h] BYREF

  *a1 = 0;
  hKey = 0;
  v2 = CUwfRegKey::Open(
         &hKey,
         HKEY_LOCAL_MACHINE,
         L"SYSTEM\\CurrentControlSet\\Services\\UWFVOL\\Parameters.Default",
         0x20019u);
  if ( v2 >= 0 )
  {
    Data = 0;
    Type = 0;
    cbData = 4;
    v3 = RegQueryValueExW(hKey, L"CapturedUwfSettings", 0, &Type, (LPBYTE)&Data, &cbData);
    v2 = v3;
    if ( v3 )
    {
      if ( v3 > 0 )
        v2 = (unsigned __int16)v3 | 0x80070000;
    }
    else
    {
      if ( Type != 4 )
      {
        v2 = -2147023267;
        goto LABEL_7;
      }
      v2 = 0;
      if ( cbData != 4 )
      {
        v2 = -2147024883;
        goto LABEL_7;
      }
    }
    if ( v2 >= 0 )
      *a1 = Data == 1;
  }
LABEL_7:
  CUwfRegKey::Close(&hKey);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180010040  push    rbp
0x180010042  push    rbx
0x180010043  push    rdi
0x180010044  mov     rbp, rsp
0x180010047  sub     rsp, 30h
0x18001004b  mov     rdi, rcx
0x18001004e  mov     byte ptr [rcx], 0
0x180010051  lea     rcx, [rbp+hKey]; phkResult
0x180010055  mov     [rbp+hKey], 0
0x18001005d  mov     r9d, 20019h; samDesired
0x180010063  lea     r8, aSystemCurrentc_10; "SYSTEM\\CurrentControlSet\\Services\\UW"...
0x18001006a  mov     rdx, 0FFFFFFFF80000002h; hKey
0x180010071  call    ?Open@CUwfRegKey@@QEAAJPEAUHKEY__@@PEBGK@Z; CUwfRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180010076  mov     ebx, eax
0x180010078  test    eax, eax
0x18001007a  js      short loc_1800100D9
0x18001007c  mov     rcx, [rbp+hKey]; hKey
0x180010080  lea     rax, [rbp+cbData]
0x180010084  mov     [rsp+30h+lpcbData], rax; lpcbData
0x180010089  lea     r9, [rbp+Type]; lpType
0x18001008d  lea     rax, [rbp+Data]
0x180010091  mov     [rbp+Data], 0
0x180010098  xor     r8d, r8d; lpReserved
0x18001009b  mov     [rsp+30h+lpData], rax; lpData
0x1800100a0  lea     rdx, aCaptureduwfset; "CapturedUwfSettings"
0x1800100a7  mov     [rbp+Type], 0
0x1800100ae  mov     [rbp+cbData], 4
0x1800100b5  call    cs:__imp_RegQueryValueExW
0x1800100bb  mov     ebx, eax
0x1800100bd  test    eax, eax
0x1800100bf  jz      short loc_1800100EC
0x1800100c1  jle     short loc_1800100CC
0x1800100c3  movzx   ebx, ax
0x1800100c6  or      ebx, 80070000h
0x1800100cc  test    ebx, ebx
0x1800100ce  js      short loc_1800100D9
0x1800100d0  cmp     [rbp+Data], 1
0x1800100d4  setz    al
0x1800100d7  mov     [rdi], al
0x1800100d9  lea     rcx, [rbp+hKey]; this
0x1800100dd  call    ?Close@CUwfRegKey@@QEAAJXZ; CUwfRegKey::Close(void)
0x1800100e2  mov     eax, ebx
0x1800100e4  add     rsp, 30h
0x1800100e8  pop     rdi
0x1800100e9  pop     rbx
0x1800100ea  pop     rbp
0x1800100eb  retn
0x1800100ec  cmp     [rbp+Type], 4
0x1800100f0  jz      short loc_1800100F9
0x1800100f2  mov     ebx, 8007065Dh
0x1800100f7  jmp     short loc_1800100D9
0x1800100f9  xor     ebx, ebx
0x1800100fb  cmp     [rbp+cbData], 4
0x1800100ff  jz      short loc_1800100CC
0x180010101  mov     ebx, 8007000Dh
0x180010106  jmp     short loc_1800100D9
```
