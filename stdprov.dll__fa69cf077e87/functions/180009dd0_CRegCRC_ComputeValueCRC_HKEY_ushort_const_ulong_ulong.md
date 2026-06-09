# CRegCRC::ComputeValueCRC(HKEY__ *,ushort const *,ulong,ulong &)

- ea: `0x180009dd0`
- end: `0x180009edf`
- name: `?ComputeValueCRC@CRegCRC@@SAJPEAUHKEY__@@PEBGKAEAK@Z`
- size: `271`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpValueName, unsigned int, unsigned int *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180013a68`
- `0x180013ee0`

## callees

- `0x180009dd0`
- `0x180009ef0`
- `0x18000b91c`
- `0x18000ba94`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180009e07`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180009e68`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180009e07`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180009e68`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180009e1e`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180009e1e`

## pseudocode

```c
__int64 __fastcall CRegCRC::ComputeValueCRC(HKEY hKey, LPCWSTR lpValueName, unsigned int a3, unsigned int *a4)
{
  __int64 v8; // rdx
  unsigned int v9; // ebx
  LSTATUS v10; // eax
  unsigned int v11; // r8d
  __int64 i; // rdx
  DWORD cbData; // [rsp+30h] [rbp-38h] BYREF
  DWORD Type[3]; // [rsp+34h] [rbp-34h] BYREF
  LPBYTE lpData; // [rsp+40h] [rbp-28h] BYREF
  _BYTE v16[8]; // [rsp+48h] [rbp-20h] BYREF
  void (__fastcall *v17)(_QWORD); // [rsp+50h] [rbp-18h]
  _QWORD *v18; // [rsp+58h] [rbp-10h]

  *a4 = a3;
  cbData = 0;
  if ( RegQueryValueExW(hKey, lpValueName, 0, 0, 0, &cbData) )
    return 1;
  lpData = (LPBYTE)CWin32DefaultArena::WbemMemAlloc(cbData);
  MakeGuard<void (*)(unsigned short *),RefHolder<unsigned short *>>(v16, v8, &lpData);
  if ( !lpData )
  {
    v9 = -2147217402;
LABEL_6:
    ScopeGuardImpl1<void (*)(unsigned char *),RefHolder<unsigned char *>>::~ScopeGuardImpl1<void (*)(unsigned char *),RefHolder<unsigned char *>>((__int64)v16);
    return v9;
  }
  Type[0] = 0;
  v10 = RegQueryValueExW(hKey, lpValueName, 0, Type, lpData, &cbData);
  v9 = 1;
  if ( v10 )
    goto LABEL_6;
  v11 = *a4;
  for ( i = 0; i != 4; ++i )
    v11 = *((_DWORD *)qword_18001A550 + ((unsigned __int8)v11 ^ (unsigned __int64)*((unsigned __int8 *)Type + i)))
        ^ (v11 >> 8);
  *a4 = v11;
  *a4 = UpdateCRC32(lpData, cbData, v11);
  if ( !v16[0] )
    v17(*v18);
  return 0;
}

```

## disassembly

```asm
0x180009dd0  push    rbp
0x180009dd2  push    rbx
0x180009dd3  push    rsi
0x180009dd4  push    rdi
0x180009dd5  mov     rbp, rsp
0x180009dd8  sub     rsp, 68h
0x180009ddc  mov     rdi, r9
0x180009ddf  mov     rbx, rdx
0x180009de2  mov     rsi, rcx
0x180009de5  mov     [r9], r8d
0x180009de8  mov     [rbp+cbData], 0
0x180009def  lea     rax, [rbp+cbData]
0x180009df3  mov     [rsp+68h+lpcbData], rax; lpcbData
0x180009df8  mov     [rsp+68h+lpData], 0; lpData
0x180009e01  xor     r9d, r9d; lpType
0x180009e04  xor     r8d, r8d; lpReserved
0x180009e07  call    cs:__imp_RegQueryValueExW
0x180009e0d  test    eax, eax
0x180009e0f  jz      short loc_180009E1B
0x180009e11  mov     eax, 1
0x180009e16  jmp     loc_180009ED6
0x180009e1b  mov     ecx, [rbp+cbData]
0x180009e1e  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180009e24  mov     [rbp+var_28], rax
0x180009e28  lea     r8, [rbp+var_28]
0x180009e2c  lea     rcx, [rbp+var_20]
0x180009e30  call    ??$MakeGuard@P6AXPEAG@ZV?$RefHolder@PEAG@@@@YA?AV?$ScopeGuardImpl1@P6AXPEAG@ZV?$RefHolder@PEAG@@@@P6AXPEAG@ZV?$RefHolder@PEAG@@@Z; MakeGuard<void (*)(ushort *),RefHolder<ushort *>>(void (*)(ushort *),RefHolder<ushort *>)
0x180009e35  nop
0x180009e36  mov     rax, [rbp+var_28]
0x180009e3a  test    rax, rax
0x180009e3d  jnz     short loc_180009E46
0x180009e3f  mov     ebx, 80041006h
0x180009e44  jmp     short loc_180009E77
0x180009e46  mov     [rbp+Type], 0
0x180009e4d  lea     rcx, [rbp+cbData]
0x180009e51  mov     [rsp+68h+lpcbData], rcx; lpcbData
0x180009e56  mov     [rsp+68h+lpData], rax; lpData
0x180009e5b  lea     r9, [rbp+Type]; lpType
0x180009e5f  xor     r8d, r8d; lpReserved
0x180009e62  mov     rdx, rbx; lpValueName
0x180009e65  mov     rcx, rsi; hKey
0x180009e68  call    cs:__imp_RegQueryValueExW
0x180009e6e  mov     ebx, 1
0x180009e73  test    eax, eax
0x180009e75  jz      short loc_180009E84
0x180009e77  lea     rcx, [rbp+var_20]
0x180009e7b  call    ??1?$ScopeGuardImpl1@P6AXPEAE@ZV?$RefHolder@PEAE@@@@QEAA@XZ; ScopeGuardImpl1<void (*)(uchar *),RefHolder<uchar *>>::~ScopeGuardImpl1<void (*)(uchar *),RefHolder<uchar *>>(void)
0x180009e80  mov     eax, ebx
0x180009e82  jmp     short loc_180009ED6
0x180009e84  mov     r8d, [rdi]
0x180009e87  xor     edx, edx
0x180009e89  movzx   ecx, byte ptr [rbp+rdx+Type]
0x180009e8e  movzx   eax, r8b
0x180009e92  xor     rcx, rax
0x180009e95  lea     rax, qword_18001A550
0x180009e9c  shr     r8d, 8
0x180009ea0  xor     r8d, [rax+rcx*4]; unsigned int
0x180009ea4  add     rdx, rbx
0x180009ea7  cmp     rdx, 4
0x180009eab  jnz     short loc_180009E89
0x180009ead  mov     [rdi], r8d
0x180009eb0  mov     edx, [rbp+cbData]; int
0x180009eb3  mov     rcx, [rbp+var_28]; unsigned __int8 *
0x180009eb7  call    ?UpdateCRC32@@YAKPEAEHK@Z; UpdateCRC32(uchar *,int,ulong)
0x180009ebc  mov     [rdi], eax
0x180009ebe  cmp     [rbp+var_20], 0
0x180009ec2  jnz     short loc_180009ED4
0x180009ec4  mov     rcx, [rbp+var_10]
0x180009ec8  mov     rcx, [rcx]
0x180009ecb  mov     rax, [rbp+var_18]
0x180009ecf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009ed4  xor     eax, eax
0x180009ed6  add     rsp, 68h
0x180009eda  pop     rdi
0x180009edb  pop     rsi
0x180009edc  pop     rbx
0x180009edd  pop     rbp
0x180009ede  retn
```
