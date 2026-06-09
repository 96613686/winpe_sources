# CheckCrashDumpSettings(ushort const *)

- ea: `0x180019ee8`
- end: `0x18001a0b2`
- name: `?CheckCrashDumpSettings@@YAJPEBG@Z`
- size: `458`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180026bfc`

## callees

- `0x18000d030`
- `0x180019234`
- `0x180019ee8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18001a033`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18001a033`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180019f71`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180019fb2`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001a004`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180019f71`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180019fb2`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001a004`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18001a06f`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18001a06f`

## pseudocode

```c
__int64 __fastcall CheckCrashDumpSettings(const unsigned __int16 *a1)
{
  int v1; // ebx
  unsigned __int64 v3; // rdx
  LSTATUS v4; // eax
  DWORD pcbData; // [rsp+40h] [rbp-C0h] BYREF
  int Data; // [rsp+44h] [rbp-BCh] BYREF
  int pvData; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int64 v9; // [rsp+50h] [rbp-B0h] BYREF
  _WORD v10[264]; // [rsp+60h] [rbp-A0h] BYREF

  pvData = 0;
  v10[0] = 0;
  v1 = 0;
  Data = 0;
  pcbData = 4;
  if ( !RegGetValueW(
          HKEY_LOCAL_MACHINE,
          L"System\\ControlSet001\\Control\\CrashControl",
          L"ExpectedCrashDumpEnabled",
          0x10u,
          0,
          &pvData,
          &pcbData) )
  {
    pcbData = 4;
    if ( !RegGetValueW(
            HKEY_LOCAL_MACHINE,
            L"System\\ControlSet001\\Control\\CrashControl",
            L"CrashDumpEnabled",
            0x10u,
            0,
            &Data,
            &pcbData)
      && pvData != Data )
    {
      pcbData = 520;
      if ( !RegGetValueW(
              HKEY_LOCAL_MACHINE,
              L"System\\ControlSet001\\Control\\CrashControl",
              L"DedicatedDumpFile",
              2u,
              0,
              v10,
              &pcbData) )
      {
        v9 = 0;
        v1 = StringCchLengthW(a1, v3, &v9);
        if ( v1 >= 0 && !(unsigned int)_o__wcsnicmp(a1, v10, v9) )
        {
          pcbData = 4;
          Data = pvData;
          v4 = RegSetKeyValueW(
                 HKEY_LOCAL_MACHINE,
                 L"System\\ControlSet001\\Control\\CrashControl",
                 L"CrashDumpEnabled",
                 4u,
                 &Data,
                 4u);
          if ( v4 )
          {
            if ( v4 > 0 )
              return (unsigned __int16)v4 | 0x80070000;
            else
              return (unsigned int)v4;
          }
        }
      }
    }
  }
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x180019ee8  mov     [rsp-8+arg_8], rbx
0x180019eed  mov     [rsp-8+arg_10], rdi
0x180019ef2  push    rbp
0x180019ef3  push    r12
0x180019ef5  push    r14
0x180019ef7  lea     rbp, [rsp-180h]
0x180019eff  sub     rsp, 280h
0x180019f06  mov     rax, cs:__security_cookie
0x180019f0d  xor     rax, rsp
0x180019f10  mov     [rbp+190h+var_20], rax
0x180019f17  xor     eax, eax
0x180019f19  mov     [rsp+290h+var_248], 0
0x180019f21  mov     [rsp+290h+var_230], ax
0x180019f26  lea     r8, Value; "ExpectedCrashDumpEnabled"
0x180019f2d  xor     ebx, ebx
0x180019f2f  mov     [rsp+290h+Data], 0
0x180019f37  lea     rax, [rsp+290h+var_250]
0x180019f3c  mov     rdi, rcx
0x180019f3f  mov     [rsp+290h+pcbData], rax; pcbData
0x180019f44  lea     rdx, SubKey; "System\\ControlSet001\\Control\\CrashCo"...
0x180019f4b  lea     rax, [rsp+290h+var_248]
0x180019f50  mov     r12, 0FFFFFFFF80000002h
0x180019f57  mov     [rsp+290h+pvData], rax; pvData
0x180019f5c  lea     r14d, [rbx+4]
0x180019f60  lea     r9d, [rbx+10h]; dwFlags
0x180019f64  mov     [rsp+290h+pdwType], rbx; pdwType
0x180019f69  mov     rcx, r12; hkey
0x180019f6c  mov     [rsp+290h+var_250], r14d
0x180019f71  call    cs:__imp_RegGetValueW
0x180019f77  test    eax, eax
0x180019f79  jnz     loc_18001A088
0x180019f7f  lea     rax, [rsp+290h+var_250]
0x180019f84  mov     [rsp+290h+var_250], r14d
0x180019f89  mov     [rsp+290h+pcbData], rax; pcbData
0x180019f8e  lea     r9d, [rbx+10h]; dwFlags
0x180019f92  lea     rax, [rsp+290h+Data]
0x180019f97  mov     rcx, r12; hkey
0x180019f9a  mov     [rsp+290h+pvData], rax; pvData
0x180019f9f  lea     r8, ValueName; "CrashDumpEnabled"
0x180019fa6  lea     rdx, SubKey; "System\\ControlSet001\\Control\\CrashCo"...
0x180019fad  mov     [rsp+290h+pdwType], rbx; pdwType
0x180019fb2  call    cs:__imp_RegGetValueW
0x180019fb8  test    eax, eax
0x180019fba  jnz     loc_18001A088
0x180019fc0  mov     eax, [rsp+290h+Data]
0x180019fc4  cmp     [rsp+290h+var_248], eax
0x180019fc8  jz      loc_18001A088
0x180019fce  lea     rax, [rsp+290h+var_250]
0x180019fd3  mov     [rsp+290h+var_250], 208h
0x180019fdb  mov     [rsp+290h+pcbData], rax; pcbData
0x180019fe0  lea     r9d, [rbx+2]; dwFlags
0x180019fe4  lea     rax, [rsp+290h+var_230]
0x180019fe9  mov     rcx, r12; hkey
0x180019fec  mov     [rsp+290h+pvData], rax; pvData
0x180019ff1  lea     r8, aDedicateddumpf; "DedicatedDumpFile"
0x180019ff8  lea     rdx, SubKey; "System\\ControlSet001\\Control\\CrashCo"...
0x180019fff  mov     [rsp+290h+pdwType], rbx; pdwType
0x18001a004  call    cs:__imp_RegGetValueW
0x18001a00a  test    eax, eax
0x18001a00c  jnz     short loc_18001A088
0x18001a00e  lea     r8, [rsp+290h+var_240]; unsigned __int64 *
0x18001a013  mov     [rsp+290h+var_240], rbx
0x18001a018  mov     rcx, rdi; unsigned __int16 *
0x18001a01b  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18001a020  mov     ebx, eax
0x18001a022  test    eax, eax
0x18001a024  js      short loc_18001A088
0x18001a026  mov     r8, [rsp+290h+var_240]
0x18001a02b  lea     rdx, [rsp+290h+var_230]
0x18001a030  mov     rcx, rdi
0x18001a033  call    cs:__imp__o__wcsnicmp
0x18001a039  test    eax, eax
0x18001a03b  jnz     short loc_18001A088
0x18001a03d  mov     r10d, [rsp+290h+var_248]
0x18001a042  lea     rax, [rsp+290h+Data]
0x18001a047  mov     dword ptr [rsp+290h+pvData], r14d; cbData
0x18001a04c  lea     r8, ValueName; "CrashDumpEnabled"
0x18001a053  mov     r9d, r14d; dwType
0x18001a056  mov     [rsp+290h+pdwType], rax; lpData
0x18001a05b  lea     rdx, SubKey; "System\\ControlSet001\\Control\\CrashCo"...
0x18001a062  mov     [rsp+290h+var_250], r14d
0x18001a067  mov     rcx, r12; hKey
0x18001a06a  mov     [rsp+290h+Data], r10d
0x18001a06f  call    cs:__imp_RegSetKeyValueW
0x18001a075  test    eax, eax
0x18001a077  jz      short loc_18001A088
0x18001a079  jg      short loc_18001A07F
0x18001a07b  mov     ebx, eax
0x18001a07d  jmp     short loc_18001A088
0x18001a07f  movzx   ebx, ax
0x18001a082  or      ebx, 80070000h
0x18001a088  mov     eax, ebx
0x18001a08a  mov     rcx, [rbp+190h+var_20]
0x18001a091  xor     rcx, rsp; StackCookie
0x18001a094  call    __security_check_cookie
0x18001a099  lea     r11, [rsp+290h+var_10]
0x18001a0a1  mov     rbx, [r11+28h]
0x18001a0a5  mov     rdi, [r11+30h]
0x18001a0a9  mov     rsp, r11
0x18001a0ac  pop     r14
0x18001a0ae  pop     r12
0x18001a0b0  pop     rbp
0x18001a0b1  retn
```
