# GetOldSidString(void *,ushort const *,ushort * *)

- ea: `0x18001c00c`
- end: `0x18001c166`
- name: `?GetOldSidString@@YAJPEAXPEBGPEAPEAG@Z`
- size: `346`
- prototype: `__int64 __fastcall(void *, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180002a40`

## callees

- `0x1800040b0`
- `0x180007e00`
- `0x180008a58`
- `0x18000db08`
- `0x18001ad58`
- `0x18001c00c`
- `0x18001c16c`

## string_xrefs

- `0x18001c05a`: `onecore\ds\security\gina\profile\proflib\sid.cpp`
- `0x18001c0b7`: `onecore\ds\security\gina\profile\proflib\sid.cpp`
- `0x18001c11e`: `onecore\ds\security\gina\profile\proflib\sid.cpp`
- `0x18001c0da`: `SidString`

## pseudocode

```c
__int64 __fastcall GetOldSidString(void *a1, const unsigned __int16 *a2, unsigned __int16 **a3)
{
  int UserGuid; // eax
  unsigned int v6; // ebx
  int v7; // eax
  __int64 v8; // rdx
  int v9; // eax
  unsigned __int16 *v11; // [rsp+20h] [rbp-58h] BYREF
  __int64 v12; // [rsp+28h] [rbp-50h]
  __int64 v13; // [rsp+30h] [rbp-48h]
  _QWORD v14[3]; // [rsp+38h] [rbp-40h] BYREF
  const WCHAR *v15[5]; // [rsp+50h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+20h]

  *a3 = 0;
  v11 = 0;
  v12 = 0;
  v13 = 0;
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&v11);
  v12 = -1;
  v13 = -1;
  UserGuid = GetUserGuid(a1, &v11);
  v6 = UserGuid;
  if ( UserGuid >= 0 )
  {
    if ( v11 && *v11 )
    {
      memset(v15, 0, 24);
      v7 = Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::InitializeFormat(
             v15,
             L"%s\\%s",
             L"Software\\Microsoft\\Windows NT\\CurrentVersion\\ProfileGuid");
      v6 = v7;
      if ( v7 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xD2,
          (unsigned int)"onecore\\ds\\security\\gina\\profile\\proflib\\sid.cpp",
          (const char *)(unsigned int)v7,
          (int)v11);
LABEL_7:
        Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(v15);
        goto LABEL_15;
      }
      memset(v14, 0, sizeof(v14));
      if ( (int)Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::Initialize(
                  (__int64)v14,
                  v8,
                  v15[0],
                  (__int64)L"SidString") >= 0 )
      {
        if ( v14[0] )
        {
          if ( *(_WORD *)v14[0] )
          {
            v9 = Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::CopyTo(
                   v14,
                   a3);
            v6 = v9;
            if ( v9 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0xD7,
                (unsigned int)"onecore\\ds\\security\\gina\\profile\\proflib\\sid.cpp",
                (const char *)(unsigned int)v9,
                (int)v11);
              Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(v14);
              goto LABEL_7;
            }
          }
        }
      }
      Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(v14);
      Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(v15);
    }
    v6 = 0;
    goto LABEL_15;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xCC,
    (unsigned int)"onecore\\ds\\security\\gina\\profile\\proflib\\sid.cpp",
    (const char *)(unsigned int)UserGuid,
    (int)v11);
LABEL_15:
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&v11);
  return v6;
}

```

## disassembly

```asm
0x18001c00c  push    rbp
0x18001c00e  push    rbx
0x18001c00f  push    rsi
0x18001c010  push    rdi
0x18001c011  mov     rbp, rsp
0x18001c014  sub     rsp, 78h
0x18001c018  xor     esi, esi
0x18001c01a  mov     rbx, rcx
0x18001c01d  lea     rcx, [rbp+var_58]
0x18001c021  mov     [r8], rsi
0x18001c024  mov     [rbp+var_58], rsi
0x18001c028  mov     rdi, r8
0x18001c02b  mov     [rbp+var_50], rsi
0x18001c02f  mov     [rbp+var_48], rsi
0x18001c033  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18001c038  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001c03c  lea     rdx, [rbp+var_58]; unsigned __int16 **
0x18001c040  mov     rcx, rbx; TokenHandle
0x18001c043  mov     [rbp+var_50], rax
0x18001c047  mov     [rbp+var_48], rax
0x18001c04b  call    ?GetUserGuid@@YAJPEAXPEAPEAG@Z; GetUserGuid(void *,ushort * *)
0x18001c050  mov     ebx, eax
0x18001c052  test    eax, eax
0x18001c054  jns     short loc_18001C073
0x18001c056  mov     rcx, [rbp+20h]; this
0x18001c05a  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001c061  mov     r9d, eax; char *
0x18001c064  mov     edx, 0CCh; void *
0x18001c069  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c06e  jmp     loc_18001C151
0x18001c073  mov     r9, [rbp+var_58]
0x18001c077  test    r9, r9
0x18001c07a  jz      loc_18001C14F
0x18001c080  cmp     [r9], si
0x18001c084  jz      loc_18001C14F
0x18001c08a  lea     r8, aSoftwareMicros; "Software\\Microsoft\\Windows NT\\Curren"...
0x18001c091  mov     [rbp+var_28], rsi
0x18001c095  lea     rdx, aSS; "%s\\%s"
0x18001c09c  mov     [rbp+var_20], rsi
0x18001c0a0  lea     rcx, [rbp+var_28]
0x18001c0a4  mov     [rbp+var_18], rsi
0x18001c0a8  call    ?InitializeFormat@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x18001c0ad  mov     ebx, eax
0x18001c0af  test    eax, eax
0x18001c0b1  jns     short loc_18001C0D6
0x18001c0b3  mov     rcx, [rbp+20h]; this
0x18001c0b7  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001c0be  mov     r9d, eax; char *
0x18001c0c1  mov     edx, 0D2h; void *
0x18001c0c6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c0cb  lea     rcx, [rbp+var_28]
0x18001c0cf  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18001c0d4  jmp     short loc_18001C151
0x18001c0d6  mov     r8, [rbp+var_28]
0x18001c0da  lea     r9, aSidstring; "SidString"
0x18001c0e1  lea     rcx, [rbp+var_40]
0x18001c0e5  mov     [rbp+var_40], rsi
0x18001c0e9  mov     [rbp+var_38], rsi
0x18001c0ed  mov     [rbp+var_30], rsi
0x18001c0f1  call    ?Initialize@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEAUHKEY__@@PEBG1@Z; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::Initialize(HKEY__ *,ushort const *,ushort const *)
0x18001c0f6  test    eax, eax
0x18001c0f8  js      short loc_18001C13D
0x18001c0fa  mov     rax, [rbp+var_40]
0x18001c0fe  test    rax, rax
0x18001c101  jz      short loc_18001C13D
0x18001c103  cmp     [rax], si
0x18001c106  jz      short loc_18001C13D
0x18001c108  mov     rdx, rdi
0x18001c10b  lea     rcx, [rbp+var_40]
0x18001c10f  call    ?CopyTo@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEBAJPEAPEAG@Z; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::CopyTo(ushort * *)
0x18001c114  mov     ebx, eax
0x18001c116  test    eax, eax
0x18001c118  jns     short loc_18001C13D
0x18001c11a  mov     rcx, [rbp+20h]; this
0x18001c11e  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001c125  mov     r9d, eax; char *
0x18001c128  mov     edx, 0D7h; void *
0x18001c12d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c132  lea     rcx, [rbp+var_40]
0x18001c136  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18001c13b  jmp     short loc_18001C0CB
0x18001c13d  lea     rcx, [rbp+var_40]
0x18001c141  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18001c146  lea     rcx, [rbp+var_28]
0x18001c14a  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18001c14f  mov     ebx, esi
0x18001c151  lea     rcx, [rbp+var_58]
0x18001c155  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18001c15a  mov     eax, ebx
0x18001c15c  add     rsp, 78h
0x18001c160  pop     rdi
0x18001c161  pop     rsi
0x18001c162  pop     rbx
0x18001c163  pop     rbp
0x18001c164  retn
```
