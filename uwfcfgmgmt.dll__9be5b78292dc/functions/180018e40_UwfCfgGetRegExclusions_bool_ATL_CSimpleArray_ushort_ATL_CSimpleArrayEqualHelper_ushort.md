# UwfCfgGetRegExclusions(bool,ATL::CSimpleArray<ushort *,ATL::CSimpleArrayEqualHelper<ushort *>> *)

- ea: `0x180018e40`
- end: `0x180018f46`
- name: `?UwfCfgGetRegExclusions@@YAJ_NPEAV?$CSimpleArray@PEAGV?$CSimpleArrayEqualHelper@PEAG@ATL@@@ATL@@@Z`
- size: `262`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, registry_config`

## callees

- `0x18000e170`
- `0x18000f364`
- `0x180017cc4`
- `0x180018e40`
- `0x18001aa08`
- `0x18001aa94`
- `0x18001aad4`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x180018f21`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180018f21`
- `OLEAUT32!__imp_SysAllocString` at `0x180018ee3`
- `OLEAUT32!__imp_SysAllocString` at `0x180018ee3`

## string_xrefs

- `0x180018eb0`: `RegistryExceptionsUserDefined`

## pseudocode

```c
__int64 __fastcall UwfCfgGetRegExclusions(char a1, __int64 a2)
{
  BSTR v4; // rsi
  int v5; // ebx
  __int64 v6; // rdx
  int v7; // eax
  struct _MULTISZ *v8; // rdi
  __int64 v9; // r14
  BSTR v11; // [rsp+68h] [rbp+38h] BYREF
  struct _MULTISZ *v12; // [rsp+70h] [rbp+40h] BYREF
  __int64 v13; // [rsp+78h] [rbp+48h] BYREF

  anonymous_namespace_::uwfCfgApiBreakpoint();
  v4 = 0;
  v13 = 0;
  v11 = 0;
  v12 = 0;
  if ( a2 )
  {
    EnsureUwfFeatureState();
    LOBYTE(v6) = a1;
    v7 = anonymous_namespace_::uwfCfgInitialize(0, v6, &v13, &v11, 0, 0);
    v4 = v11;
    v5 = v7;
    if ( v7 >= 0 )
    {
      v5 = CUwfRegKey::QueryMultiSzValue((HKEY *)v11 + 2, L"RegistryExceptionsUserDefined", &v12);
      v8 = v12;
      if ( v5 >= 0 )
      {
        if ( !v12 )
        {
          v5 = -2147467259;
          goto LABEL_16;
        }
        v9 = 0;
        if ( *((_DWORD *)v12 + 6) )
        {
          while ( 1 )
          {
            v11 = SysAllocString(*(const OLECHAR **)(*((_QWORD *)v8 + 2) + 8 * v9));
            if ( !v11 )
              break;
            if ( !(unsigned int)ATL::CSimpleArray<unsigned short *,ATL::CSimpleArrayEqualHelper<unsigned short *>>::Add(
                                  a2,
                                  &v11) )
            {
              v5 = -2147467259;
              goto LABEL_14;
            }
            v9 = (unsigned int)(v9 + 1);
            if ( (unsigned int)v9 >= *((_DWORD *)v8 + 6) )
              goto LABEL_14;
          }
          v5 = -2147024882;
        }
      }
LABEL_14:
      if ( v8 )
        operator delete[](v8);
    }
  }
  else
  {
    v5 = -2147024809;
  }
LABEL_16:
  anonymous_namespace_::uwfCfgFinalize(v13, v4);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180018e40  mov     [rsp-28h+arg_0], rbx
0x180018e45  push    rbp
0x180018e46  push    rsi
0x180018e47  push    rdi
0x180018e48  push    r14
0x180018e4a  push    r15
0x180018e4c  mov     rbp, rsp
0x180018e4f  sub     rsp, 30h
0x180018e53  mov     r15, rdx
0x180018e56  mov     bl, cl
0x180018e58  call    _anonymous_namespace___uwfCfgApiBreakpoint
0x180018e5d  xor     esi, esi
0x180018e5f  mov     [rbp+arg_18], 0
0x180018e67  mov     [rbp+arg_8], rsi
0x180018e6b  mov     [rbp+arg_10], rsi
0x180018e6f  test    r15, r15
0x180018e72  jnz     short loc_180018E7E
0x180018e74  mov     ebx, 80070057h
0x180018e79  jmp     loc_180018F27
0x180018e7e  call    ?EnsureUwfFeatureState@@YAJ_N@Z; EnsureUwfFeatureState(bool)
0x180018e83  lea     r9, [rbp+arg_8]
0x180018e87  mov     [rsp+30h+var_8], rsi
0x180018e8c  lea     r8, [rbp+arg_18]
0x180018e90  mov     [rsp+30h+var_10], rsi
0x180018e95  mov     dl, bl
0x180018e97  xor     ecx, ecx
0x180018e99  call    _anonymous_namespace___uwfCfgInitialize
0x180018e9e  mov     rsi, [rbp+arg_8]
0x180018ea2  mov     ebx, eax
0x180018ea4  test    eax, eax
0x180018ea6  js      short loc_180018F27
0x180018ea8  lea     rcx, [rsi+10h]; this
0x180018eac  lea     r8, [rbp+arg_10]; struct _MULTISZ **
0x180018eb0  lea     rdx, aRegistryexcept_0; "RegistryExceptionsUserDefined"
0x180018eb7  call    ?QueryMultiSzValue@CUwfRegKey@@QEAAJPEBGPEAPEAU_MULTISZ@@@Z; CUwfRegKey::QueryMultiSzValue(ushort const *,_MULTISZ * *)
0x180018ebc  mov     ebx, eax
0x180018ebe  mov     rdi, [rbp+arg_10]
0x180018ec2  test    eax, eax
0x180018ec4  js      short loc_180018F19
0x180018ec6  test    rdi, rdi
0x180018ec9  jnz     short loc_180018ED2
0x180018ecb  mov     ebx, 80004005h
0x180018ed0  jmp     short loc_180018F27
0x180018ed2  xor     r14d, r14d
0x180018ed5  cmp     [rdi+18h], r14d
0x180018ed9  jbe     short loc_180018F19
0x180018edb  mov     rcx, [rdi+10h]
0x180018edf  mov     rcx, [rcx+r14*8]; psz
0x180018ee3  call    cs:__imp_SysAllocString
0x180018ee9  mov     [rbp+arg_8], rax
0x180018eed  test    rax, rax
0x180018ef0  jz      short loc_180018F14
0x180018ef2  lea     rdx, [rbp+arg_8]
0x180018ef6  mov     rcx, r15
0x180018ef9  call    ?Add@?$CSimpleArray@PEAGV?$CSimpleArrayEqualHelper@PEAG@ATL@@@ATL@@QEAAHAEBQEAG@Z; ATL::CSimpleArray<ushort *,ATL::CSimpleArrayEqualHelper<ushort *>>::Add(ushort * const &)
0x180018efe  test    eax, eax
0x180018f00  jz      short loc_180018F0D
0x180018f02  inc     r14d
0x180018f05  cmp     r14d, [rdi+18h]
0x180018f09  jb      short loc_180018EDB
0x180018f0b  jmp     short loc_180018F19
0x180018f0d  mov     ebx, 80004005h
0x180018f12  jmp     short loc_180018F19
0x180018f14  mov     ebx, 8007000Eh
0x180018f19  test    rdi, rdi
0x180018f1c  jz      short loc_180018F27
0x180018f1e  mov     rcx, rdi
0x180018f21  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180018f27  mov     rcx, [rbp+arg_18]
0x180018f2b  mov     rdx, rsi
0x180018f2e  call    _anonymous_namespace___uwfCfgFinalize
0x180018f33  mov     eax, ebx
0x180018f35  mov     rbx, [rsp+30h+arg_0]
0x180018f3a  add     rsp, 30h
0x180018f3e  pop     r15
0x180018f40  pop     r14
0x180018f42  pop     rdi
0x180018f43  pop     rsi
0x180018f44  pop     rbp
0x180018f45  retn
```
