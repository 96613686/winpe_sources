# GetSessionValue(ushort *,uint,ATL::CRegKey &)

- ea: `0x14000dea0`
- end: `0x14000dfb5`
- name: `?GetSessionValue@@YAXPEAGIAEAVCRegKey@ATL@@@Z`
- size: `277`
- prototype: `void __fastcall(unsigned __int16 *, unsigned int, struct ATL::CRegKey *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140012f54`

## callees

- `0x140002480`
- `0x14000d604`
- `0x14000dea0`
- `0x14000ea8c`
- `0x14000ecdc`

## string_xrefs

- `0x14000df7b`: `Configuration`
- `0x14000deda`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\Accessibility\Session`

## pseudocode

```c
void __fastcall GetSessionValue(unsigned __int16 *a1, __int64 a2, struct ATL::CRegKey *a3)
{
  unsigned int v5[4]; // [rsp+20h] [rbp-E0h] BYREF
  unsigned __int16 v6[8]; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v7; // [rsp+40h] [rbp-C0h]
  __int128 v8; // [rsp+50h] [rbp-B0h]
  __int128 v9; // [rsp+60h] [rbp-A0h]
  __int128 v10; // [rsp+70h] [rbp-90h]
  __int128 v11; // [rsp+80h] [rbp-80h]
  __int128 v12; // [rsp+90h] [rbp-70h]
  _OWORD v13[2]; // [rsp+A0h] [rbp-60h]
  WCHAR SubKey[80]; // [rsp+C0h] [rbp-40h] BYREF

  v7 = *(_OWORD *)L"\\Microsoft\\Windows NT\\CurrentVersion\\Accessibility\\Session";
  *(_OWORD *)v6 = *(_OWORD *)L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Accessibility\\Session";
  v9 = *(_OWORD *)L"ws NT\\CurrentVersion\\Accessibility\\Session";
  v8 = *(_OWORD *)L"ft\\Windows NT\\CurrentVersion\\Accessibility\\Session";
  v11 = *(_OWORD *)L"sion\\Accessibility\\Session";
  v13[0] = *(_OWORD *)L"ty\\Session";
  *(_QWORD *)((char *)v13 + 14) = *(_QWORD *)L"ion";
  v10 = *(_OWORD *)L"rrentVersion\\Accessibility\\Session";
  SubKey[0] = 0;
  v12 = *(_OWORD *)L"essibility\\Session";
  if ( (int)AppendSessionIDToKey(v6, 0x4Du, SubKey) >= 0
    && !(unsigned int)ATL::CRegKey::Open(a3, HKEY_LOCAL_MACHINE, SubKey, 0x2001Fu) )
  {
    v5[0] = 1024;
    if ( (unsigned int)ATL::CRegKey::QueryStringValue(a3, L"Configuration", a1, v5) )
      *a1 = 0;
  }
}

```

## disassembly

```asm
0x14000dea0  mov     [rsp-8+arg_8], rbx
0x14000dea5  mov     [rsp-8+arg_18], rdi
0x14000deaa  push    rbp
0x14000deab  lea     rbp, [rsp-70h]
0x14000deb0  sub     rsp, 170h
0x14000deb7  mov     rax, cs:__security_cookie
0x14000debe  xor     rax, rsp
0x14000dec1  mov     [rbp+70h+var_10], rax
0x14000dec5  mov     rax, qword ptr cs:aSoftwareMicros_0+7Eh; "ion"
0x14000decc  mov     rdi, r8
0x14000decf  movaps  xmm1, xmmword ptr cs:aSoftwareMicros_0+10h; "\\Microsoft\\Windows NT\\CurrentVersion"...
0x14000ded6  lea     r8, [rbp+70h+SubKey]; unsigned __int16 *
0x14000deda  movaps  xmm0, xmmword ptr cs:aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x14000dee1  mov     rbx, rcx
0x14000dee4  movups  [rsp+170h+var_130], xmm1
0x14000dee9  lea     rcx, [rsp+170h+var_140]; unsigned __int16 *
0x14000deee  movaps  xmm1, xmmword ptr cs:aSoftwareMicros_0+30h; "ws NT\\CurrentVersion\\Accessibility\\S"...
0x14000def5  movups  xmmword ptr [rsp+170h+var_140], xmm0
0x14000defa  movaps  xmm0, xmmword ptr cs:aSoftwareMicros_0+20h; "ft\\Windows NT\\CurrentVersion\\Accessi"...
0x14000df01  movups  [rsp+170h+var_110], xmm1
0x14000df06  movaps  xmm1, xmmword ptr cs:aSoftwareMicros_0+50h; "sion\\Accessibility\\Session"
0x14000df0d  movups  [rsp+170h+var_120], xmm0
0x14000df12  movaps  xmm0, xmmword ptr cs:aSoftwareMicros_0+40h; "rrentVersion\\Accessibility\\Session"
0x14000df19  movups  [rbp+70h+var_F0], xmm1
0x14000df1d  movaps  xmm1, xmmword ptr cs:aSoftwareMicros_0+70h; "ty\\Session"
0x14000df24  movups  xmmword ptr [rbp+70h+var_D0], xmm1
0x14000df28  mov     qword ptr [rbp+70h+var_D0+0Eh], rax
0x14000df2c  xor     eax, eax
0x14000df2e  movups  [rsp+170h+var_100], xmm0
0x14000df33  mov     [rbp+70h+SubKey], ax
0x14000df37  movaps  xmm0, xmmword ptr cs:aSoftwareMicros_0+60h; "essibility\\Session"
0x14000df3e  lea     edx, [rax+4Dh]; unsigned int
0x14000df41  movups  [rbp+70h+var_E0], xmm0
0x14000df45  call    ?AppendSessionIDToKey@@YAJPEBGIPEAG@Z; AppendSessionIDToKey(ushort const *,uint,ushort *)
0x14000df4a  test    eax, eax
0x14000df4c  js      short loc_14000DF93
0x14000df4e  mov     r9d, 2001Fh; unsigned int
0x14000df54  lea     r8, [rbp+70h+SubKey]; lpSubKey
0x14000df58  mov     rdx, 0FFFFFFFF80000002h; hKey
0x14000df5f  mov     rcx, rdi; this
0x14000df62  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x14000df67  test    eax, eax
0x14000df69  jnz     short loc_14000DF93
0x14000df6b  lea     r9, [rsp+170h+var_150]; unsigned int *
0x14000df70  mov     [rsp+170h+var_150], 400h
0x14000df78  mov     r8, rbx; unsigned __int16 *
0x14000df7b  lea     rdx, aConfiguration; "Configuration"
0x14000df82  mov     rcx, rdi; this
0x14000df85  call    ?QueryStringValue@CRegKey@ATL@@QEAAJPEBGPEAGPEAK@Z; ATL::CRegKey::QueryStringValue(ushort const *,ushort *,ulong *)
0x14000df8a  test    eax, eax
0x14000df8c  jz      short loc_14000DF93
0x14000df8e  xor     eax, eax
0x14000df90  mov     [rbx], ax
0x14000df93  mov     rcx, [rbp+70h+var_10]
0x14000df97  xor     rcx, rsp; StackCookie
0x14000df9a  call    __security_check_cookie
0x14000df9f  lea     r11, [rsp+170h+var_s0]
0x14000dfa7  mov     rbx, [r11+18h]
0x14000dfab  mov     rdi, [r11+28h]
0x14000dfaf  mov     rsp, r11
0x14000dfb2  pop     rbp
0x14000dfb3  retn
```
