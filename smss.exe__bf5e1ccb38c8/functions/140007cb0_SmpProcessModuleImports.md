# SmpProcessModuleImports

- ea: `0x140007cb0`
- end: `0x140007e45`
- name: `SmpProcessModuleImports`
- size: `405`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x140007cb0`
- `0x140007e50`
- `0x1400080c0`
- `0x14001cc40`

## import_xrefs

- `ntdll!_stricmp` at `0x140007d05`
- `ntdll!_stricmp` at `0x140007d1d`
- `ntdll!_stricmp` at `0x140007d05`
- `ntdll!_stricmp` at `0x140007d1d`
- `ntdll!RtlInitAnsiString` at `0x140007d33`
- `ntdll!RtlInitAnsiString` at `0x140007d33`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x140007d62`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x140007d62`

## string_xrefs

- `0x140007ce6`: `ntdll.dll`
- `0x140007d13`: `ntdll32.dll`

## pseudocode

```c
int __fastcall SmpProcessModuleImports(__int64 a1, const char *a2)
{
  int result; // eax
  WCHAR *v5; // rax
  __int64 v6; // rax
  struct _UNICODE_STRING *v7; // rdx
  char v8; // [rsp+30h] [rbp-D0h] BYREF
  struct _UNICODE_STRING v9; // [rsp+40h] [rbp-C0h] BYREF
  struct _UNICODE_STRING v10; // [rsp+50h] [rbp-B0h] BYREF
  _STRING DestinationString; // [rsp+60h] [rbp-A0h] BYREF
  char v12; // [rsp+70h] [rbp-90h] BYREF

  v8 = 0;
  v9 = 0;
  DestinationString = 0;
  v10 = 0;
  result = _stricmp(a2, "ntdll.dll");
  if ( result )
  {
    result = _stricmp(a2, "ntdll32.dll");
    if ( result )
    {
      RtlInitAnsiString(&DestinationString, a2);
      *(_QWORD *)&v9.Length = 34209792;
      v9.Buffer = (PWSTR)&v12;
      result = RtlAnsiStringToUnicodeString(&v9, &DestinationString, 0);
      if ( result >= 0 )
      {
        result = ApiSetResolveToHost(
                   *(_QWORD *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 104LL),
                   (unsigned int)&v9,
                   *(_QWORD *)a1,
                   (unsigned int)&v8,
                   (__int64)&v10);
        if ( result >= 0 )
        {
          if ( v8 )
          {
            if ( !v10.Length )
              return result;
            v9 = v10;
          }
          v5 = (PWSTR)((char *)v9.Buffer + v9.Length - 2);
          if ( v5 < v9.Buffer )
          {
LABEL_14:
            v7 = &v9;
          }
          else
          {
            while ( *v5 != 46 )
            {
              if ( --v5 < v9.Buffer )
                goto LABEL_14;
            }
            *(&v10.MaximumLength + 2) = 0;
            v6 = v5 - v9.Buffer;
            v7 = &v10;
            v10.Buffer = v9.Buffer;
            *(_DWORD *)&v10.MaximumLength = (unsigned __int16)(2 * v6);
            v10.Length = 2 * v6;
          }
          return SmpSaveRegistryValue_U(*(struct _UNICODE_STRING ***)(a1 + 8), v7, &v9, 1, 0);
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x140007cb0  mov     [rsp-8+arg_10], rbx
0x140007cb5  mov     [rsp-8+arg_18], rdi
0x140007cba  push    rbp
0x140007cbb  lea     rbp, [rsp-190h]
0x140007cc3  sub     rsp, 290h
0x140007cca  mov     rax, cs:__security_cookie
0x140007cd1  xor     rax, rsp
0x140007cd4  mov     [rbp+190h+var_10], rax
0x140007cdb  mov     rdi, rdx
0x140007cde  mov     [rsp+290h+var_260], 0
0x140007ce3  xorps   xmm0, xmm0
0x140007ce6  lea     rdx, Str2; "ntdll.dll"
0x140007ced  mov     rbx, rcx
0x140007cf0  xorps   xmm1, xmm1
0x140007cf3  mov     rcx, rdi; Str1
0x140007cf6  movups  xmmword ptr [rsp+290h+var_250.Length], xmm0
0x140007cfb  movups  xmmword ptr [rsp+290h+DestinationString.Length], xmm1
0x140007d00  movups  [rsp+290h+var_240], xmm0
0x140007d05  call    cs:__imp__stricmp
0x140007d0b  test    eax, eax
0x140007d0d  jz      loc_140007E11
0x140007d13  lea     rdx, aNtdll32Dll; "ntdll32.dll"
0x140007d1a  mov     rcx, rdi; Str1
0x140007d1d  call    cs:__imp__stricmp
0x140007d23  test    eax, eax
0x140007d25  jz      loc_140007E11
0x140007d2b  mov     rdx, rdi; SourceString
0x140007d2e  lea     rcx, [rsp+290h+DestinationString]; DestinationString
0x140007d33  call    cs:__imp_RtlInitAnsiString
0x140007d39  xorps   xmm0, xmm0
0x140007d3c  lea     rdx, [rsp+290h+DestinationString]; SourceString
0x140007d41  movups  xmmword ptr [rsp+290h+var_250.Length], xmm0
0x140007d46  mov     eax, 20Ah
0x140007d4b  lea     rcx, [rsp+290h+var_250]; DestinationString
0x140007d50  mov     [rsp+290h+var_250.MaximumLength], ax
0x140007d55  xor     r8d, r8d; AllocateDestinationString
0x140007d58  lea     rax, [rsp+290h+var_220]
0x140007d5d  mov     [rsp+290h+var_250.Buffer], rax
0x140007d62  call    cs:__imp_RtlAnsiStringToUnicodeString
0x140007d68  test    eax, eax
0x140007d6a  js      loc_140007E11
0x140007d70  mov     rcx, gs:60h
0x140007d79  lea     rax, [rsp+290h+var_240]
0x140007d7e  mov     r8, [rbx]
0x140007d81  lea     r9, [rsp+290h+var_260]
0x140007d86  lea     rdx, [rsp+290h+var_250]
0x140007d8b  mov     [rsp+290h+var_270], rax
0x140007d90  mov     rcx, [rcx+68h]
0x140007d94  call    ApiSetResolveToHost
0x140007d99  test    eax, eax
0x140007d9b  js      short loc_140007E11
0x140007d9d  cmp     [rsp+290h+var_260], 0
0x140007da2  jz      short loc_140007DB7
0x140007da4  cmp     word ptr [rsp+290h+var_240], 0
0x140007daa  jz      short loc_140007E11
0x140007dac  movaps  xmm0, [rsp+290h+var_240]
0x140007db1  movdqa  xmmword ptr [rsp+290h+var_250.Length], xmm0
0x140007db7  mov     rcx, [rsp+290h+var_250.Buffer]
0x140007dbc  xor     r8d, r8d
0x140007dbf  movzx   eax, [rsp+290h+var_250.Length]
0x140007dc4  add     rax, 0FFFFFFFFFFFFFFFEh
0x140007dc8  add     rax, rcx
0x140007dcb  cmp     rax, rcx
0x140007dce  jb      short loc_140007E3E
0x140007dd0  cmp     word ptr [rax], 2Eh ; '.'
0x140007dd4  jnz     short loc_140007E35
0x140007dd6  sub     rax, rcx
0x140007dd9  mov     dword ptr [rsp+290h+var_240+4], r8d
0x140007dde  sar     rax, 1
0x140007de1  lea     rdx, [rsp+290h+var_240]
0x140007de6  add     ax, ax
0x140007de9  mov     qword ptr [rsp+290h+var_240+8], rcx
0x140007dee  mov     word ptr [rsp+290h+var_240+2], ax
0x140007df3  mov     word ptr [rsp+290h+var_240], ax
0x140007df8  mov     rcx, [rbx+8]
0x140007dfc  mov     r9d, 1
0x140007e02  mov     [rsp+290h+var_270], r8
0x140007e07  lea     r8, [rsp+290h+var_250]
0x140007e0c  call    SmpSaveRegistryValue_U
0x140007e11  mov     rcx, [rbp+190h+var_10]
0x140007e18  xor     rcx, rsp; StackCookie
0x140007e1b  call    __security_check_cookie
0x140007e20  lea     r11, [rsp+290h+var_s0]
0x140007e28  mov     rbx, [r11+20h]
0x140007e2c  mov     rdi, [r11+28h]
0x140007e30  mov     rsp, r11
0x140007e33  pop     rbp
0x140007e34  retn
0x140007e35  sub     rax, 2
0x140007e39  cmp     rax, rcx
0x140007e3c  jnb     short loc_140007DD0
0x140007e3e  lea     rdx, [rsp+290h+var_250]
0x140007e43  jmp     short loc_140007DF8
```
