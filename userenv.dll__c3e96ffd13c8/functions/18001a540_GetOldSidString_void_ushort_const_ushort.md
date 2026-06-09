# GetOldSidString(void *,ushort const *,ushort * *)

- ea: `0x18001a540`
- end: `0x18001a699`
- name: `?GetOldSidString@@YAJPEAXPEBGPEAPEAG@Z`
- size: `345`
- prototype: `__int64 __fastcall(void *, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180002ad0`

## callees

- `0x180003f60`
- `0x180007130`
- `0x180007988`
- `0x18000cea0`
- `0x180019290`
- `0x18001a540`
- `0x18001a6a0`

## string_xrefs

- `0x18001a58e`: `onecore\ds\security\gina\profile\proflib\sid.cpp`
- `0x18001a5eb`: `onecore\ds\security\gina\profile\proflib\sid.cpp`
- `0x18001a652`: `onecore\ds\security\gina\profile\proflib\sid.cpp`
- `0x18001a60e`: `SidString`

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
  _QWORD v15[5]; // [rsp+50h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+20h]

  *a3 = 0;
  v11 = 0;
  v12 = 0;
  v13 = 0;
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)&v11);
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
        Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)v15);
        goto LABEL_15;
      }
      memset(v14, 0, sizeof(v14));
      if ( (int)Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::Initialize(
                  v14,
                  v8,
                  v15[0],
                  L"SidString") >= 0 )
      {
        if ( v14[0] )
        {
          if ( *(_WORD *)v14[0] )
          {
            v9 = Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::CopyTo(
                   (__int64)v14,
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
              Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)v14);
              goto LABEL_7;
            }
          }
        }
      }
      Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)v14);
      Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)v15);
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
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)&v11);
  return v6;
}

```

## disassembly

```asm
0x18001a540  push    rbp
0x18001a542  push    rbx
0x18001a543  push    rsi
0x18001a544  push    rdi
0x18001a545  mov     rbp, rsp
0x18001a548  sub     rsp, 78h
0x18001a54c  xor     esi, esi
0x18001a54e  mov     rbx, rcx
0x18001a551  lea     rcx, [rbp+var_58]
0x18001a555  mov     [r8], rsi
0x18001a558  mov     [rbp+var_58], rsi
0x18001a55c  mov     rdi, r8
0x18001a55f  mov     [rbp+var_50], rsi
0x18001a563  mov     [rbp+var_48], rsi
0x18001a567  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18001a56c  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001a570  lea     rdx, [rbp+var_58]; unsigned __int16 **
0x18001a574  mov     rcx, rbx; TokenHandle
0x18001a577  mov     [rbp+var_50], rax
0x18001a57b  mov     [rbp+var_48], rax
0x18001a57f  call    ?GetUserGuid@@YAJPEAXPEAPEAG@Z; GetUserGuid(void *,ushort * *)
0x18001a584  mov     ebx, eax
0x18001a586  test    eax, eax
0x18001a588  jns     short loc_18001A5A7
0x18001a58a  mov     rcx, [rbp+20h]; this
0x18001a58e  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001a595  mov     r9d, eax; char *
0x18001a598  mov     edx, 0CCh; void *
0x18001a59d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a5a2  jmp     loc_18001A685
0x18001a5a7  mov     r9, [rbp+var_58]
0x18001a5ab  test    r9, r9
0x18001a5ae  jz      loc_18001A683
0x18001a5b4  cmp     [r9], si
0x18001a5b8  jz      loc_18001A683
0x18001a5be  lea     r8, aSoftwareMicros; "Software\\Microsoft\\Windows NT\\Curren"...
0x18001a5c5  mov     [rbp+var_28], rsi
0x18001a5c9  lea     rdx, aSS; "%s\\%s"
0x18001a5d0  mov     [rbp+var_20], rsi
0x18001a5d4  lea     rcx, [rbp+var_28]
0x18001a5d8  mov     [rbp+var_18], rsi
0x18001a5dc  call    ?InitializeFormat@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x18001a5e1  mov     ebx, eax
0x18001a5e3  test    eax, eax
0x18001a5e5  jns     short loc_18001A60A
0x18001a5e7  mov     rcx, [rbp+20h]; this
0x18001a5eb  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001a5f2  mov     r9d, eax; char *
0x18001a5f5  mov     edx, 0D2h; void *
0x18001a5fa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a5ff  lea     rcx, [rbp+var_28]
0x18001a603  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18001a608  jmp     short loc_18001A685
0x18001a60a  mov     r8, [rbp+var_28]
0x18001a60e  lea     r9, aSidstring; "SidString"
0x18001a615  lea     rcx, [rbp+var_40]
0x18001a619  mov     [rbp+var_40], rsi
0x18001a61d  mov     [rbp+var_38], rsi
0x18001a621  mov     [rbp+var_30], rsi
0x18001a625  call    ?Initialize@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEAUHKEY__@@PEBG1@Z; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::Initialize(HKEY__ *,ushort const *,ushort const *)
0x18001a62a  test    eax, eax
0x18001a62c  js      short loc_18001A671
0x18001a62e  mov     rax, [rbp+var_40]
0x18001a632  test    rax, rax
0x18001a635  jz      short loc_18001A671
0x18001a637  cmp     [rax], si
0x18001a63a  jz      short loc_18001A671
0x18001a63c  mov     rdx, rdi
0x18001a63f  lea     rcx, [rbp+var_40]
0x18001a643  call    ?CopyTo@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEBAJPEAPEAG@Z; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::CopyTo(ushort * *)
0x18001a648  mov     ebx, eax
0x18001a64a  test    eax, eax
0x18001a64c  jns     short loc_18001A671
0x18001a64e  mov     rcx, [rbp+20h]; this
0x18001a652  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001a659  mov     r9d, eax; char *
0x18001a65c  mov     edx, 0D7h; void *
0x18001a661  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a666  lea     rcx, [rbp+var_40]
0x18001a66a  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18001a66f  jmp     short loc_18001A5FF
0x18001a671  lea     rcx, [rbp+var_40]
0x18001a675  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18001a67a  lea     rcx, [rbp+var_28]
0x18001a67e  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18001a683  mov     ebx, esi
0x18001a685  lea     rcx, [rbp+var_58]
0x18001a689  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18001a68e  mov     eax, ebx
0x18001a690  add     rsp, 78h
0x18001a694  pop     rdi
0x18001a695  pop     rsi
0x18001a696  pop     rbx
0x18001a697  pop     rbp
0x18001a698  retn
```
