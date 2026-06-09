# RegistryFunctions::RegSetKeyValueW(HKEY__ *,ushort const *,ushort const *,ulong,void const *,ulong)

- ea: `0x180010380`
- end: `0x18001045f`
- name: `?RegSetKeyValueW@RegistryFunctions@@UEAAJPEAUHKEY__@@PEBG1KPEBXK@Z`
- size: `223`
- prototype: `__int64 __fastcall(RegistryFunctions *this, HKEY, const unsigned __int16 *, const unsigned __int16 *, DWORD dwType, BYTE *lpData, DWORD cbData)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x180010380`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180010424`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180010424`

## pseudocode

```c
__int64 __fastcall RegistryFunctions::RegSetKeyValueW(
        RegistryFunctions *this,
        HKEY a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        DWORD dwType,
        BYTE *lpData,
        DWORD cbData)
{
  unsigned int v10; // esi
  HKEY v11; // rcx
  HKEY v13; // [rsp+90h] [rbp+18h] BYREF

  v13 = 0;
  if ( a3 && *a3 )
  {
    v10 = (*(__int64 (__fastcall **)(RegistryFunctions *, HKEY, const unsigned __int16 *, _QWORD, _QWORD, _DWORD, int, _QWORD, HKEY *, _QWORD))(*(_QWORD *)this + 128LL))(
            this,
            a2,
            a3,
            0,
            0,
            0,
            2,
            0,
            &v13,
            0);
    if ( v10 )
      return v10;
    v11 = v13;
  }
  else
  {
    v11 = a2;
    v13 = a2;
  }
  v10 = RegSetValueExW(v11, a4, 0, dwType, lpData, cbData);
  if ( v13 != a2 )
    (*(void (__fastcall **)(RegistryFunctions *))(*(_QWORD *)this + 8LL))(this);
  return v10;
}

```

## disassembly

```asm
0x180010380  mov     r11, rsp
0x180010383  mov     [r11+8], rbx
0x180010387  mov     [r11+10h], rbp
0x18001038b  push    rsi
0x18001038c  push    rdi
0x18001038d  push    r14
0x18001038f  sub     rsp, 60h
0x180010393  xor     r14d, r14d
0x180010396  mov     rbp, r9
0x180010399  mov     [r11+18h], r14
0x18001039d  mov     rdi, rdx
0x1800103a0  mov     rbx, rcx
0x1800103a3  test    r8, r8
0x1800103a6  jz      short loc_1800103F3
0x1800103a8  cmp     [r8], r14w
0x1800103ac  jz      short loc_1800103F3
0x1800103ae  mov     rax, [rcx]
0x1800103b1  xor     r9d, r9d
0x1800103b4  mov     [r11-30h], r14
0x1800103b8  lea     rcx, [r11+18h]
0x1800103bc  mov     [r11-38h], rcx
0x1800103c0  mov     rcx, rbx
0x1800103c3  mov     [r11-40h], r14
0x1800103c7  mov     rax, [rax+80h]
0x1800103ce  mov     [rsp+78h+var_48], 2
0x1800103d6  mov     [r11-50h], r14d
0x1800103da  mov     [r11-58h], r14
0x1800103de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800103e3  mov     esi, eax
0x1800103e5  test    eax, eax
0x1800103e7  jnz     short loc_180010448
0x1800103e9  mov     rcx, [rsp+78h+arg_10]
0x1800103f1  jmp     short loc_1800103FE
0x1800103f3  mov     rcx, rdi; hKey
0x1800103f6  mov     [rsp+78h+arg_10], rcx
0x1800103fe  mov     eax, [rsp+78h+arg_30]
0x180010405  xor     r8d, r8d; Reserved
0x180010408  mov     r9d, [rsp+78h+dwType]; dwType
0x180010410  mov     rdx, rbp; lpValueName
0x180010413  mov     [rsp+78h+cbData], eax; cbData
0x180010417  mov     rax, [rsp+78h+arg_28]
0x18001041f  mov     [rsp+78h+lpData], rax; lpData
0x180010424  call    cs:__imp_RegSetValueExW
0x18001042a  mov     rdx, [rsp+78h+arg_10]
0x180010432  mov     esi, eax
0x180010434  cmp     rdx, rdi
0x180010437  jz      short loc_180010448
0x180010439  mov     rcx, [rbx]
0x18001043c  mov     rax, [rcx+8]
0x180010440  mov     rcx, rbx
0x180010443  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010448  lea     r11, [rsp+78h+var_18]
0x18001044d  mov     eax, esi
0x18001044f  mov     rbx, [r11+20h]
0x180010453  mov     rbp, [r11+28h]
0x180010457  mov     rsp, r11
0x18001045a  pop     r14
0x18001045c  pop     rdi
0x18001045d  pop     rsi
0x18001045e  retn
```
