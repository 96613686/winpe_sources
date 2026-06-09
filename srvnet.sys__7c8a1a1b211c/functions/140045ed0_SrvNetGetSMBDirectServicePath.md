# SrvNetGetSMBDirectServicePath

- ea: `0x140045ed0`
- end: `0x14004603e`
- name: `SrvNetGetSMBDirectServicePath`
- size: `366`
- prototype: `__int64 __fastcall(PUNICODE_STRING Destination)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task`

## callers

- `0x140046680`

## callees

- `0x140016384`
- `0x140019d64`
- `0x14001f8a4`
- `0x14002a3e0`
- `0x140045ed0`
- `0x14004a868`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x140045f87`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140045f87`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140045f9a`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140045f9a`

## string_xrefs

- `0x140045f10`: `\Registry\Machine\System\CurrentControlSet\Services\LanmanServer\Parameters`
- `0x140045f1c`: `SMBDirectServiceName`

## pseudocode

```c
__int64 __fastcall SrvNetGetSMBDirectServicePath(PUNICODE_STRING Destination)
{
  unsigned int v2; // r11d
  int v4; // [rsp+30h] [rbp-59h] BYREF
  UNICODE_STRING Source; // [rsp+38h] [rbp-51h] BYREF
  unsigned __int16 *v6; // [rsp+48h] [rbp-41h] BYREF
  wchar_t pszDest[64]; // [rsp+50h] [rbp-39h] BYREF

  v6 = 0;
  Destination->Length = 0;
  v4 = 128;
  Source = 0;
  if ( (int)RfsRegGetString(
              L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\LanmanServer\\Parameters",
              L"SMBDirectServiceName",
              pszDest,
              &v4) >= 0 )
  {
    v2 = v4;
  }
  else
  {
    RtlStringCbCopyW(pszDest, 0x80u, L"SMBDirect");
    v2 = 18;
  }
  if ( v2 >= 0xFFFE )
    return 3221225734LL;
  Source.Length = v2;
  Source.Buffer = pszDest;
  Source.MaximumLength = v2 + 2;
  if ( (unsigned __int16)(v2 + 2) > 0x80u )
    return 3221225734LL;
  RtlCopyUnicodeString(Destination, &stru_14002EBD0);
  if ( RtlAppendUnicodeStringToString(Destination, &Source) < 0 )
    return 3221225734LL;
  if ( (unsigned __int8)RfsRegIsValidSubkeyName(Source.Buffer, Source.Length >> 1, &v6) )
    return 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_Dd(
      WPP_GLOBAL_Control->AttachedDevice,
      19,
      WPP_c4c5c2b3626832d86a1d2b192965291e_Traceguids,
      *v6,
      (_DWORD)v6 - LODWORD(Source.Buffer));
  }
  return 3221225523LL;
}

```

## disassembly

```asm
0x140045ed0  mov     [rsp-8+arg_8], rbx
0x140045ed5  mov     [rsp-8+arg_10], rdi
0x140045eda  push    rbp
0x140045edb  lea     rbp, [rsp-57h]
0x140045ee0  sub     rsp, 0E0h
0x140045ee7  mov     rax, cs:__security_cookie
0x140045eee  xor     rax, rsp
0x140045ef1  mov     [rbp+57h+var_10], rax
0x140045ef5  xor     eax, eax
0x140045ef7  mov     [rbp+57h+var_98], 0
0x140045eff  mov     [rcx], ax
0x140045f02  lea     r9, [rbp+57h+var_B0]
0x140045f06  mov     rbx, rcx
0x140045f09  lea     r8, [rbp+57h+pszDest]
0x140045f0d  xorps   xmm0, xmm0
0x140045f10  lea     rcx, aRegistryMachin_5; "\\Registry\\Machine\\System\\CurrentCon"...
0x140045f17  mov     edi, 80h
0x140045f1c  lea     rdx, aSmbdirectservi; "SMBDirectServiceName"
0x140045f23  mov     [rbp+57h+var_B0], edi
0x140045f26  movups  xmmword ptr [rbp+57h+Source.Length], xmm0
0x140045f2a  call    RfsRegGetString
0x140045f2f  test    eax, eax
0x140045f31  jns     short loc_140045F4B
0x140045f33  lea     r8, aSmbdirect; "SMBDirect"
0x140045f3a  mov     edx, edi; cbDest
0x140045f3c  lea     rcx, [rbp+57h+pszDest]; pszDest
0x140045f40  call    RtlStringCbCopyW
0x140045f45  lea     r11d, [rdi-6Eh]
0x140045f49  jmp     short loc_140045F4F
0x140045f4b  mov     r11d, [rbp+57h+var_B0]
0x140045f4f  cmp     r11d, 0FFFEh
0x140045f56  jnb     loc_140046017
0x140045f5c  mov     [rbp+57h+Source.Length], r11w
0x140045f61  lea     rax, [rbp+57h+pszDest]
0x140045f65  add     r11w, 2
0x140045f6a  mov     [rbp+57h+Source.Buffer], rax
0x140045f6e  mov     [rbp+57h+Source.MaximumLength], r11w
0x140045f73  cmp     r11w, di
0x140045f77  ja      loc_140046017
0x140045f7d  lea     rdx, stru_14002EBD0; SourceString
0x140045f84  mov     rcx, rbx; DestinationString
0x140045f87  call    cs:__imp_RtlCopyUnicodeString
0x140045f8e  nop     dword ptr [rax+rax+00h]
0x140045f93  lea     rdx, [rbp+57h+Source]; Source
0x140045f97  mov     rcx, rbx; Destination
0x140045f9a  call    cs:__imp_RtlAppendUnicodeStringToString
0x140045fa1  nop     dword ptr [rax+rax+00h]
0x140045fa6  test    eax, eax
0x140045fa8  js      short loc_140046017
0x140045faa  movzx   edx, [rbp+57h+Source.Length]
0x140045fae  lea     r8, [rbp+57h+var_98]
0x140045fb2  mov     rcx, [rbp+57h+Source.Buffer]
0x140045fb6  shr     edx, 1
0x140045fb8  call    RfsRegIsValidSubkeyName
0x140045fbd  test    al, al
0x140045fbf  jnz     short loc_140046013
0x140045fc1  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140045fc8  lea     rax, WPP_GLOBAL_Control
0x140045fcf  cmp     rcx, rax
0x140045fd2  jz      short loc_14004600C
0x140045fd4  test    dword ptr [rcx+2Ch], 80000h
0x140045fdb  jz      short loc_14004600C
0x140045fdd  cmp     byte ptr [rcx+29h], 4
0x140045fe1  jb      short loc_14004600C
0x140045fe3  mov     rax, [rbp+57h+var_98]
0x140045fe7  mov     edx, 13h
0x140045fec  mov     rcx, [rcx+18h]
0x140045ff0  mov     r8d, eax
0x140045ff3  sub     r8d, dword ptr [rbp+57h+Source.Buffer]
0x140045ff7  mov     [rsp+0E0h+var_C0], r8d
0x140045ffc  lea     r8, WPP_c4c5c2b3626832d86a1d2b192965291e_Traceguids
0x140046003  movzx   r9d, word ptr [rax]
0x140046007  call    WPP_SF_Dd
0x14004600c  mov     eax, 0C0000033h
0x140046011  jmp     short loc_14004601C
0x140046013  xor     eax, eax
0x140046015  jmp     short loc_14004601C
0x140046017  mov     eax, 0C0000106h
0x14004601c  mov     rcx, [rbp+57h+var_10]
0x140046020  xor     rcx, rsp; StackCookie
0x140046023  call    __security_check_cookie
0x140046028  lea     r11, [rsp+0E0h+var_s0]
0x140046030  mov     rbx, [r11+18h]
0x140046034  mov     rdi, [r11+20h]
0x140046038  mov     rsp, r11
0x14004603b  pop     rbp
0x14004603c  retn
```
