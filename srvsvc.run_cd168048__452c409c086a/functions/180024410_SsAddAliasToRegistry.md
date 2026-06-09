# SsAddAliasToRegistry

- ea: `0x180024410`
- end: `0x18002463d`
- name: `SsAddAliasToRegistry`
- size: `557`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180023a50`
- `0x18002be20`

## callees

- `0x180012ef0`
- `0x18001deb0`
- `0x18001e80c`
- `0x180024410`
- `0x180026838`
- `0x1800268d8`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002447d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002447d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024613`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024613`
- `ntdll!RtlWriteRegistryValue` at `0x1800245bd`
- `ntdll!RtlWriteRegistryValue` at `0x1800245bd`
- `ntdll!RtlSetEnvironmentVariable` at `0x1800244f5`
- `ntdll!RtlSetEnvironmentVariable` at `0x180024532`
- `ntdll!RtlSetEnvironmentVariable` at `0x18002458d`
- `ntdll!RtlSetEnvironmentVariable` at `0x1800244f5`
- `ntdll!RtlSetEnvironmentVariable` at `0x180024532`
- `ntdll!RtlSetEnvironmentVariable` at `0x18002458d`
- `ntdll!RtlCreateEnvironment` at `0x1800244bc`
- `ntdll!RtlCreateEnvironment` at `0x1800244bc`
- `ntdll!RtlIntegerToUnicodeString` at `0x180024573`
- `ntdll!RtlIntegerToUnicodeString` at `0x180024573`
- `ntdll!RtlDestroyEnvironment` at `0x18002460a`
- `ntdll!RtlDestroyEnvironment` at `0x18002460a`
- `ntdll!RtlInitUnicodeString` at `0x1800244d5`
- `ntdll!RtlInitUnicodeString` at `0x1800244e3`
- `ntdll!RtlInitUnicodeString` at `0x180024513`
- `ntdll!RtlInitUnicodeString` at `0x180024520`
- `ntdll!RtlInitUnicodeString` at `0x18002454b`
- `ntdll!RtlInitUnicodeString` at `0x1800244d5`
- `ntdll!RtlInitUnicodeString` at `0x1800244e3`
- `ntdll!RtlInitUnicodeString` at `0x180024513`
- `ntdll!RtlInitUnicodeString` at `0x180024520`
- `ntdll!RtlInitUnicodeString` at `0x18002454b`

## pseudocode

```c
int __fastcall SsAddAliasToRegistry(__int64 a1)
{
  PCWSTR v2; // rcx
  __int64 v3; // rax
  SIZE_T v4; // rsi
  wchar_t *v5; // rax
  wchar_t *v6; // rbx
  const wchar_t *v7; // r8
  bool v8; // zf
  ULONG ValueLength; // eax
  PVOID ValueData; // rcx
  NTSTATUS v11; // eax
  PWSTR Environment; // [rsp+30h] [rbp-49h] BYREF
  struct _UNICODE_STRING Value; // [rsp+38h] [rbp-41h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+48h] [rbp-31h] BYREF
  char v16; // [rsp+60h] [rbp-19h] BYREF

  v2 = *(PCWSTR *)a1;
  Environment = 0;
  DestinationString = 0;
  Value = 0;
  if ( v2 )
  {
    v3 = -1;
    do
      ++v3;
    while ( v2[v3] );
  }
  else
  {
    v3 = 1;
  }
  v4 = 2 * v3 + 2;
  v5 = (wchar_t *)LocalAlloc(0x40u, v4);
  v6 = v5;
  if ( v5 )
  {
    memset_0(v5, 0, v4);
    v7 = *(const wchar_t **)a1;
    if ( !*(_QWORD *)a1 )
      v7 = L"*";
    StringCbCopyW(v6, v4, v7);
    LODWORD(v5) = RtlCreateEnvironment(0, &Environment);
    if ( (int)v5 >= 0 )
    {
      RtlInitUnicodeString(&DestinationString, L"Target");
      RtlInitUnicodeString(&Value, *(PCWSTR *)(a1 + 8));
      if ( RtlSetEnvironmentVariable(&Environment, &DestinationString, &Value) >= 0 )
      {
        if ( !*(_QWORD *)a1
          || (RtlInitUnicodeString(&DestinationString, L"Alias"),
              RtlInitUnicodeString(&Value, *(PCWSTR *)a1),
              RtlSetEnvironmentVariable(&Environment, &DestinationString, &Value) >= 0) )
        {
          RtlInitUnicodeString(&DestinationString, L"Default");
          v8 = *(_BYTE *)(a1 + 16) == 0;
          Value.Buffer = (PWSTR)&v16;
          *(_DWORD *)&Value.Length = 4325442;
          if ( RtlIntegerToUnicodeString(!v8, 0xAu, &Value) >= 0
            && RtlSetEnvironmentVariable(&Environment, &DestinationString, &Value) >= 0 )
          {
            ValueLength = SsRtlQueryEnvironmentLength(Environment);
            v11 = RtlWriteRegistryValue(1u, L"LanmanServer\\Aliases", v6, 7u, ValueData, ValueLength);
            if ( v11 < 0
              && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) )
            {
              WPP_SF_dS(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                80,
                (unsigned int)WPP_6c51fa01af1134468f88fcdefbc326dc_Traceguids,
                v11,
                (__int64)v6);
            }
          }
        }
      }
      RtlDestroyEnvironment(Environment);
      LODWORD(v5) = (unsigned int)LocalFree(v6);
    }
  }
  return (int)v5;
}

```

## disassembly

```asm
0x180024410  mov     [rsp-8+arg_8], rbx
0x180024415  mov     [rsp-8+arg_10], rsi
0x18002441a  push    rbp
0x18002441b  push    rdi
0x18002441c  push    r14
0x18002441e  lea     rbp, [rsp-47h]
0x180024423  sub     rsp, 0C0h
0x18002442a  mov     rax, cs:__security_cookie
0x180024431  xor     rax, rsp
0x180024434  mov     [rbp+57h+var_20], rax
0x180024438  xor     r14d, r14d
0x18002443b  mov     rdi, rcx
0x18002443e  mov     rcx, [rcx]
0x180024441  xorps   xmm0, xmm0
0x180024444  mov     [rbp+57h+Environment], r14
0x180024448  xorps   xmm1, xmm1
0x18002444b  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x18002444f  movups  xmmword ptr [rbp+57h+Value.Length], xmm1
0x180024453  test    rcx, rcx
0x180024456  jz      short loc_180024468
0x180024458  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002445c  inc     rax
0x18002445f  cmp     [rcx+rax*2], r14w
0x180024464  jnz     short loc_18002445C
0x180024466  jmp     short loc_18002446D
0x180024468  mov     eax, 1
0x18002446d  lea     rsi, ds:2[rax*2]
0x180024475  mov     ecx, 40h ; '@'; uFlags
0x18002447a  mov     rdx, rsi; uBytes
0x18002447d  call    cs:__imp_LocalAlloc
0x180024483  mov     rbx, rax
0x180024486  test    rax, rax
0x180024489  jz      loc_180024619
0x18002448f  mov     r8, rsi; Size
0x180024492  xor     edx, edx; Val
0x180024494  mov     rcx, rax; void *
0x180024497  call    memset_0
0x18002449c  mov     r8, [rdi]
0x18002449f  mov     rdx, rsi; cbDest
0x1800244a2  mov     rcx, rbx; pszDest
0x1800244a5  test    r8, r8
0x1800244a8  jnz     short loc_1800244B1
0x1800244aa  lea     r8, pszSrc; "*"
0x1800244b1  call    StringCbCopyW
0x1800244b6  lea     rdx, [rbp+57h+Environment]; Environment
0x1800244ba  xor     ecx, ecx; Inherit
0x1800244bc  call    cs:__imp_RtlCreateEnvironment
0x1800244c2  test    eax, eax
0x1800244c4  js      loc_180024619
0x1800244ca  lea     rdx, aTarget; "Target"
0x1800244d1  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1800244d5  call    cs:__imp_RtlInitUnicodeString
0x1800244db  mov     rdx, [rdi+8]; SourceString
0x1800244df  lea     rcx, [rbp+57h+Value]; DestinationString
0x1800244e3  call    cs:__imp_RtlInitUnicodeString
0x1800244e9  lea     r8, [rbp+57h+Value]; Value
0x1800244ed  lea     rdx, [rbp+57h+DestinationString]; Name
0x1800244f1  lea     rcx, [rbp+57h+Environment]; Environment
0x1800244f5  call    cs:__imp_RtlSetEnvironmentVariable
0x1800244fb  test    eax, eax
0x1800244fd  js      loc_180024606
0x180024503  cmp     [rdi], r14
0x180024506  jz      short loc_180024540
0x180024508  lea     rdx, aAlias; "Alias"
0x18002450f  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x180024513  call    cs:__imp_RtlInitUnicodeString
0x180024519  mov     rdx, [rdi]; SourceString
0x18002451c  lea     rcx, [rbp+57h+Value]; DestinationString
0x180024520  call    cs:__imp_RtlInitUnicodeString
0x180024526  lea     r8, [rbp+57h+Value]; Value
0x18002452a  lea     rdx, [rbp+57h+DestinationString]; Name
0x18002452e  lea     rcx, [rbp+57h+Environment]; Environment
0x180024532  call    cs:__imp_RtlSetEnvironmentVariable
0x180024538  test    eax, eax
0x18002453a  js      loc_180024606
0x180024540  lea     rdx, aDefault; "Default"
0x180024547  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18002454b  call    cs:__imp_RtlInitUnicodeString
0x180024551  cmp     [rdi+10h], r14b
0x180024555  lea     rax, [rbp+57h+var_70]
0x180024559  mov     ecx, r14d
0x18002455c  mov     [rbp+57h+Value.Buffer], rax
0x180024560  setnz   cl; Value
0x180024563  mov     dword ptr [rbp+57h+Value.Length], 420042h
0x18002456a  lea     r8, [rbp+57h+Value]; String
0x18002456e  mov     edx, 0Ah; Base
0x180024573  call    cs:__imp_RtlIntegerToUnicodeString
0x180024579  test    eax, eax
0x18002457b  js      loc_180024606
0x180024581  lea     r8, [rbp+57h+Value]; Value
0x180024585  lea     rdx, [rbp+57h+DestinationString]; Name
0x180024589  lea     rcx, [rbp+57h+Environment]; Environment
0x18002458d  call    cs:__imp_RtlSetEnvironmentVariable
0x180024593  test    eax, eax
0x180024595  js      short loc_180024606
0x180024597  mov     rcx, [rbp+57h+Environment]
0x18002459b  call    SsRtlQueryEnvironmentLength
0x1800245a0  mov     r9d, 7; ValueType
0x1800245a6  mov     [rsp+0D0h+ValueLength], eax; ValueLength
0x1800245aa  mov     [rsp+0D0h+ValueData], rcx; ValueData
0x1800245af  lea     rdx, aLanmanserverAl; "LanmanServer\\Aliases"
0x1800245b6  mov     r8, rbx; ValueName
0x1800245b9  lea     ecx, [r9-6]; RelativeTo
0x1800245bd  call    cs:__imp_RtlWriteRegistryValue
0x1800245c3  test    eax, eax
0x1800245c5  jns     short loc_180024606
0x1800245c7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800245ce  lea     rdx, WPP_GLOBAL_Control
0x1800245d5  cmp     rcx, rdx
0x1800245d8  jz      short loc_180024606
0x1800245da  test    dword ptr [rcx+1Ch], 100h
0x1800245e1  jz      short loc_180024606
0x1800245e3  cmp     byte ptr [rcx+19h], 1
0x1800245e7  jb      short loc_180024606
0x1800245e9  mov     rcx, [rcx+10h]
0x1800245ed  lea     r8, WPP_6c51fa01af1134468f88fcdefbc326dc_Traceguids
0x1800245f4  mov     edx, 50h ; 'P'
0x1800245f9  mov     [rsp+0D0h+ValueData], rbx
0x1800245fe  mov     r9d, eax
0x180024601  call    WPP_SF_dS
0x180024606  mov     rcx, [rbp+57h+Environment]; Environment
0x18002460a  call    cs:__imp_RtlDestroyEnvironment
0x180024610  mov     rcx, rbx; hMem
0x180024613  call    cs:__imp_LocalFree
0x180024619  mov     rcx, [rbp+57h+var_20]
0x18002461d  xor     rcx, rsp; StackCookie
0x180024620  call    __security_check_cookie
0x180024625  lea     r11, [rsp+0D0h+var_10]
0x18002462d  mov     rbx, [r11+28h]
0x180024631  mov     rsi, [r11+30h]
0x180024635  mov     rsp, r11
0x180024638  pop     r14
0x18002463a  pop     rdi
0x18002463b  pop     rbp
0x18002463c  retn
```
