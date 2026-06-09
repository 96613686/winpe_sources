# CUwfStaticConfiguration::AddRegKeyExclusion(ushort const *)

- ea: `0x180005f00`
- end: `0x18000613b`
- name: `?AddRegKeyExclusion@CUwfStaticConfiguration@@QEAAJPEBG@Z`
- size: `571`
- prototype: `__int64 __fastcall(CUwfStaticConfiguration *this, wchar_t *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x180017df0`

## callees

- `0x180001384`
- `0x180005f00`
- `0x1800079a0`
- `0x18000e4d0`
- `0x18001065c`
- `0x180011a30`
- `0x180011b90`
- `0x180011c40`
- `0x180012930`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180005fae`
- `msvcrt!_wcsicmp` at `0x180005fae`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800060a2`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180006110`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800060a2`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180006110`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180006000`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180006079`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180006000`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180006079`

## string_xrefs

- `0x180005fe8`: `RegistryExceptionsUserDefined`
- `0x18000605c`: `RegistryExceptionsUserDefined`
- `0x1800060ec`: `RegistryExceptionsUserDefined`

## pseudocode

```c
__int64 __fastcall CUwfStaticConfiguration::AddRegKeyExclusion(CUwfStaticConfiguration *this, wchar_t *a2)
{
  void *pvData; // r15
  struct _MULTISZ *v5; // r14
  int v6; // ebx
  wchar_t *v7; // rdi
  unsigned int i; // ebx
  HKEY v9; // rcx
  LSTATUS ValueW; // eax
  signed int v11; // edi
  bool v12; // cc
  __int64 v13; // rax
  HKEY pcbData; // [rsp+88h] [rbp+48h] BYREF
  wchar_t *String1; // [rsp+90h] [rbp+50h] BYREF

  pvData = 0;
  v5 = 0;
  if ( !a2 )
  {
    v6 = -2147467261;
    goto LABEL_29;
  }
  if ( *((_BYTE *)this + 9) )
  {
    v6 = -2147024891;
    goto LABEL_29;
  }
  if ( IsValidRegKeyName(a2) )
  {
    pcbData = 0;
    String1 = 0;
    if ( ParsePredefinedKey(a2, (const unsigned __int16 **)&String1, &pcbData) && pcbData == HKEY_LOCAL_MACHINE )
    {
      v7 = String1;
      if ( *String1 )
      {
        for ( i = 0; i < 6; ++i )
        {
          if ( qword_18002A0D0[2 * i] == -2147483646 && !_wcsicmp(v7, (const wchar_t *)qword_18002A0D0[2 * i + 1]) )
            goto LABEL_28;
        }
        LODWORD(String1) = 0;
        v9 = (HKEY)*((_QWORD *)this + 2);
        LODWORD(pcbData) = 0;
        ValueW = RegGetValueW(v9, 0, L"RegistryExceptionsUserDefined", 0x20u, (LPDWORD)&String1, 0, (LPDWORD)&pcbData);
        v11 = ValueW;
        v6 = -2147024882;
        v12 = ValueW <= 0;
        if ( !ValueW )
        {
          pvData = operator new[](saturated_mul((unsigned __int64)(unsigned int)pcbData >> 1, 2u));
          if ( !pvData )
          {
            v11 = -2147024882;
LABEL_21:
            operator delete[](pvData);
            if ( v11 < 0 )
            {
              v6 = v11;
            }
            else if ( (int)MultiSzFind(a2) >= 0 )
            {
              v6 = 0;
            }
            else
            {
              v13 = MultiSzReAlloc(v5, a2);
              if ( v13 )
              {
                v5 = (struct _MULTISZ *)v13;
                v6 = CUwfConfiguration::FixupUpdatedSettings(*((CUwfConfiguration **)this + 4));
                if ( v6 >= 0 )
                  v6 = CUwfRegKey::SetMultiSzValue(
                         (CUwfStaticConfiguration *)((char *)this + 16),
                         L"RegistryExceptionsUserDefined",
                         v5);
              }
            }
            goto LABEL_29;
          }
          ValueW = RegGetValueW(
                     *((HKEY *)this + 2),
                     0,
                     L"RegistryExceptionsUserDefined",
                     0x20u,
                     (LPDWORD)&String1,
                     pvData,
                     (LPDWORD)&pcbData);
          v11 = ValueW;
          v12 = ValueW <= 0;
          if ( !ValueW )
          {
            v5 = (struct _MULTISZ *)MultiSzAlloc(pvData);
            v11 = -2147024882;
            if ( v5 )
              v11 = 0;
            goto LABEL_21;
          }
        }
        if ( !v12 )
          v11 = (unsigned __int16)ValueW | 0x80070000;
        goto LABEL_21;
      }
    }
  }
LABEL_28:
  v6 = -2147024809;
LABEL_29:
  operator delete[](v5);
  if ( v6 < 0 )
    *(_DWORD *)(*((_QWORD *)this + 4) + 16LL) = v6;
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180005f00  mov     [rsp-38h+arg_0], rbx
0x180005f05  push    rbp
0x180005f06  push    rsi
0x180005f07  push    rdi
0x180005f08  push    r12
0x180005f0a  push    r13
0x180005f0c  push    r14
0x180005f0e  push    r15
0x180005f10  mov     rbp, rsp
0x180005f13  sub     rsp, 40h
0x180005f17  xor     r15d, r15d
0x180005f1a  mov     rsi, rdx
0x180005f1d  mov     r13, rcx
0x180005f20  mov     r14d, r15d
0x180005f23  test    rdx, rdx
0x180005f26  jnz     short loc_180005F32
0x180005f28  mov     ebx, 80004003h
0x180005f2d  jmp     loc_18000610D
0x180005f32  cmp     [rcx+9], r15b
0x180005f36  jz      short loc_180005F42
0x180005f38  mov     ebx, 80070005h
0x180005f3d  jmp     loc_18000610D
0x180005f42  mov     rcx, rsi; unsigned __int16 *
0x180005f45  call    ?IsValidRegKeyName@@YA_NPEBG@Z; IsValidRegKeyName(ushort const *)
0x180005f4a  test    al, al
0x180005f4c  jz      loc_180006108
0x180005f52  lea     r8, [rbp+arg_8]; HKEY *
0x180005f56  mov     [rbp+arg_8], r15
0x180005f5a  lea     rdx, [rbp+String1]; unsigned __int16 **
0x180005f5e  mov     [rbp+String1], r15
0x180005f62  mov     rcx, rsi; String2
0x180005f65  call    ?ParsePredefinedKey@@YA_NPEBGPEAPEBGPEAPEAUHKEY__@@@Z; ParsePredefinedKey(ushort const *,ushort const * *,HKEY__ * *)
0x180005f6a  test    al, al
0x180005f6c  jz      loc_180006108
0x180005f72  mov     r12, 0FFFFFFFF80000002h
0x180005f79  cmp     [rbp+arg_8], r12
0x180005f7d  jnz     loc_180006108
0x180005f83  mov     rdi, [rbp+String1]
0x180005f87  cmp     [rdi], r15w
0x180005f8b  jz      loc_180006108
0x180005f91  mov     ebx, r15d
0x180005f94  lea     rax, qword_18002A0D0
0x180005f9b  mov     edx, ebx
0x180005f9d  add     rdx, rdx
0x180005fa0  cmp     [rax+rdx*8], r12
0x180005fa4  jnz     short loc_180005FC3
0x180005fa6  mov     rdx, [rax+rdx*8+8]; String2
0x180005fab  mov     rcx, rdi; String1
0x180005fae  call    cs:__imp__wcsicmp
0x180005fb4  test    eax, eax
0x180005fb6  jz      loc_180006108
0x180005fbc  lea     rax, qword_18002A0D0
0x180005fc3  inc     ebx
0x180005fc5  cmp     ebx, 6
0x180005fc8  jb      short loc_180005F9B
0x180005fca  lea     rax, [rbp+arg_8]
0x180005fce  mov     dword ptr [rbp+String1], r15d
0x180005fd2  mov     [rsp+40h+pcbData], rax; pcbData
0x180005fd7  lea     r12, [r13+10h]
0x180005fdb  mov     rcx, [r12]; hkey
0x180005fdf  lea     rax, [rbp+String1]
0x180005fe3  mov     [rsp+40h+pvData], r15; pvData
0x180005fe8  lea     r8, aRegistryexcept_0; "RegistryExceptionsUserDefined"
0x180005fef  mov     r9d, 20h ; ' '; dwFlags
0x180005ff5  mov     [rsp+40h+pdwType], rax; pdwType
0x180005ffa  xor     edx, edx; lpSubKey
0x180005ffc  mov     dword ptr [rbp+arg_8], r15d
0x180006000  call    cs:__imp_RegGetValueW
0x180006006  mov     edi, eax
0x180006008  mov     ebx, 8007000Eh
0x18000600d  test    eax, eax
0x18000600f  jz      short loc_180006022
0x180006011  jle     loc_18000609F
0x180006017  movzx   edi, ax
0x18000601a  or      edi, 80070000h
0x180006020  jmp     short loc_18000609F
0x180006022  mov     ecx, dword ptr [rbp+arg_8]
0x180006025  mov     eax, 2
0x18000602a  shr     rcx, 1
0x18000602d  mul     rcx
0x180006030  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180006037  cmovb   rax, rcx
0x18000603b  mov     rcx, rax; unsigned __int64
0x18000603e  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180006043  mov     r15, rax
0x180006046  test    rax, rax
0x180006049  jnz     short loc_18000604F
0x18000604b  mov     edi, ebx
0x18000604d  jmp     short loc_18000609F
0x18000604f  mov     rcx, [r12]; hkey
0x180006053  lea     rax, [rbp+arg_8]
0x180006057  mov     [rsp+40h+pcbData], rax; pcbData
0x18000605c  lea     r8, aRegistryexcept_0; "RegistryExceptionsUserDefined"
0x180006063  lea     rax, [rbp+String1]
0x180006067  mov     [rsp+40h+pvData], r15; pvData
0x18000606c  mov     r9d, 20h ; ' '; dwFlags
0x180006072  mov     [rsp+40h+pdwType], rax; pdwType
0x180006077  xor     edx, edx; lpSubKey
0x180006079  call    cs:__imp_RegGetValueW
0x18000607f  mov     edi, eax
0x180006081  test    eax, eax
0x180006083  jnz     short loc_180006011
0x180006085  mov     edx, dword ptr [rbp+arg_8]
0x180006088  mov     rcx, r15; Src
0x18000608b  shr     edx, 1
0x18000608d  call    MultiSzAlloc
0x180006092  mov     r14, rax
0x180006095  mov     edi, ebx
0x180006097  xor     eax, eax
0x180006099  test    r14, r14
0x18000609c  cmovnz  edi, eax
0x18000609f  mov     rcx, r15
0x1800060a2  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1800060a8  xor     r15d, r15d
0x1800060ab  test    edi, edi
0x1800060ad  js      short loc_180006104
0x1800060af  xor     r9d, r9d
0x1800060b2  xor     r8d, r8d
0x1800060b5  mov     rdx, r14
0x1800060b8  mov     rcx, rsi; String2
0x1800060bb  call    MultiSzFind
0x1800060c0  test    eax, eax
0x1800060c2  jns     short loc_1800060FF
0x1800060c4  mov     rdx, rsi
0x1800060c7  mov     rcx, r14
0x1800060ca  call    MultiSzReAlloc
0x1800060cf  mov     rdi, rax
0x1800060d2  test    rax, rax
0x1800060d5  jz      short loc_18000610D
0x1800060d7  mov     r14, rax
0x1800060da  mov     rcx, [r13+20h]; this
0x1800060de  call    ?FixupUpdatedSettings@CUwfConfiguration@@QEAAJXZ; CUwfConfiguration::FixupUpdatedSettings(void)
0x1800060e3  mov     ebx, eax
0x1800060e5  test    eax, eax
0x1800060e7  js      short loc_18000610D
0x1800060e9  mov     r8, r14; struct _MULTISZ *
0x1800060ec  lea     rdx, aRegistryexcept_0; "RegistryExceptionsUserDefined"
0x1800060f3  mov     rcx, r12; this
0x1800060f6  call    ?SetMultiSzValue@CUwfRegKey@@QEAAJPEBGQEAU_MULTISZ@@@Z; CUwfRegKey::SetMultiSzValue(ushort const *,_MULTISZ * const)
0x1800060fb  mov     ebx, eax
0x1800060fd  jmp     short loc_18000610D
0x1800060ff  mov     ebx, r15d
0x180006102  jmp     short loc_18000610D
0x180006104  mov     ebx, edi
0x180006106  jmp     short loc_18000610D
0x180006108  mov     ebx, 80070057h
0x18000610d  mov     rcx, r14
0x180006110  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180006116  test    ebx, ebx
0x180006118  jns     short loc_180006121
0x18000611a  mov     rax, [r13+20h]
0x18000611e  mov     [rax+10h], ebx
0x180006121  mov     eax, ebx
0x180006123  mov     rbx, [rsp+40h+arg_0]
0x18000612b  add     rsp, 40h
0x18000612f  pop     r15
0x180006131  pop     r14
0x180006133  pop     r13
0x180006135  pop     r12
0x180006137  pop     rdi
0x180006138  pop     rsi
0x180006139  pop     rbp
0x18000613a  retn
```
