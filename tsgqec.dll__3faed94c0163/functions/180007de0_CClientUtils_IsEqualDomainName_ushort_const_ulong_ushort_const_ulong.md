# CClientUtils::IsEqualDomainName(ushort const *,ulong,ushort const *,ulong)

- ea: `0x180007de0`
- end: `0x180007f41`
- name: `?IsEqualDomainName@CClientUtils@@UEAAHPEBGK0K@Z`
- size: `353`
- prototype: `int(CClientUtils *__hidden this, const unsigned __int16 *, unsigned int, const unsigned __int16 *, unsigned int)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180003970`
- `0x1800053ac`
- `0x180007de0`
- `0x18000ae79`
- `0x18000aea0`

## import_xrefs

- `KERNEL32!CompareStringOrdinal` at `0x180007f0f`
- `KERNEL32!CompareStringOrdinal` at `0x180007f0f`
- `Normaliz!IdnToAscii` at `0x180007e4b`
- `Normaliz!IdnToAscii` at `0x180007ec0`
- `Normaliz!IdnToAscii` at `0x180007e4b`
- `Normaliz!IdnToAscii` at `0x180007ec0`

## pseudocode

```c
__int64 __fastcall CClientUtils::IsEqualDomainName(
        CClientUtils *this,
        const unsigned __int16 *a2,
        int a3,
        const unsigned __int16 *a4,
        int cchUnicodeChar)
{
  unsigned int v8; // esi
  int v9; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  __int64 v11; // rdx
  int v12; // eax
  WCHAR String2[256]; // [rsp+30h] [rbp-428h] BYREF
  WCHAR ASCIICharStr[256]; // [rsp+230h] [rbp-228h] BYREF

  v8 = 0;
  memset_0(ASCIICharStr, 0, sizeof(ASCIICharStr));
  memset_0(String2, 0, sizeof(String2));
  v9 = IdnToAscii(0, a2, a3, ASCIICharStr, 256);
  if ( v9 > 0 )
  {
    v12 = IdnToAscii(0, a4, cchUnicodeChar, String2, 256);
    if ( v12 > 0 )
    {
      LOBYTE(v8) = CompareStringOrdinal(ASCIICharStr, v9, String2, v12, 1) == 2;
      return v8;
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v11 = 50;
      goto LABEL_6;
    }
  }
  else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v11 = 49;
LABEL_6:
    WPP_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v11,
      &WPP_72aaf7d92de938e37e89151f64d0d640_Traceguids,
      CurrentThreadActivityIdPrefix);
  }
  return v8;
}

```

## disassembly

```asm
0x180007de0  mov     [rsp+arg_0], rbx
0x180007de5  push    rbp
0x180007de6  push    rsi
0x180007de7  push    rdi
0x180007de8  sub     rsp, 440h
0x180007def  mov     rax, cs:__security_cookie
0x180007df6  xor     rax, rsp
0x180007df9  mov     [rsp+458h+var_28], rax
0x180007e01  mov     edi, r8d
0x180007e04  lea     rcx, [rsp+458h+ASCIICharStr]; void *
0x180007e0c  mov     rbx, rdx
0x180007e0f  mov     r8d, 200h; Size
0x180007e15  xor     edx, edx; Val
0x180007e17  mov     rbp, r9
0x180007e1a  xor     esi, esi
0x180007e1c  call    memset_0
0x180007e21  xor     edx, edx; Val
0x180007e23  lea     rcx, [rsp+458h+String2]; void *
0x180007e28  mov     r8d, 200h; Size
0x180007e2e  call    memset_0
0x180007e33  lea     r9, [rsp+458h+ASCIICharStr]; lpASCIICharStr
0x180007e3b  mov     [rsp+458h+cchASCIIChar], 100h; cchASCIIChar
0x180007e43  mov     r8d, edi; cchUnicodeChar
0x180007e46  mov     rdx, rbx; lpUnicodeCharStr
0x180007e49  xor     ecx, ecx; dwFlags
0x180007e4b  call    cs:__imp_IdnToAscii
0x180007e51  mov     ebx, eax
0x180007e53  test    eax, eax
0x180007e55  jg      short loc_180007EA6
0x180007e57  mov     rax, cs:WPP_GLOBAL_Control
0x180007e5e  lea     rcx, WPP_GLOBAL_Control
0x180007e65  cmp     rax, rcx
0x180007e68  jz      loc_180007F1C
0x180007e6e  test    byte ptr [rax+1Ch], 8
0x180007e72  jz      loc_180007F1C
0x180007e78  cmp     byte ptr [rax+19h], 2
0x180007e7c  jb      loc_180007F1C
0x180007e82  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180007e87  lea     edx, [rsi+31h]
0x180007e8a  mov     rcx, cs:WPP_GLOBAL_Control
0x180007e91  lea     r8, WPP_72aaf7d92de938e37e89151f64d0d640_Traceguids
0x180007e98  mov     r9d, eax
0x180007e9b  mov     rcx, [rcx+10h]
0x180007e9f  call    WPP_SF_D
0x180007ea4  jmp     short loc_180007F1C
0x180007ea6  mov     r8d, [rsp+458h+cchUnicodeChar]; cchUnicodeChar
0x180007eae  lea     r9, [rsp+458h+String2]; lpASCIICharStr
0x180007eb3  mov     rdx, rbp; lpUnicodeCharStr
0x180007eb6  mov     [rsp+458h+cchASCIIChar], 100h; cchASCIIChar
0x180007ebe  xor     ecx, ecx; dwFlags
0x180007ec0  call    cs:__imp_IdnToAscii
0x180007ec6  test    eax, eax
0x180007ec8  jg      short loc_180007EF5
0x180007eca  mov     rax, cs:WPP_GLOBAL_Control
0x180007ed1  lea     rcx, WPP_GLOBAL_Control
0x180007ed8  cmp     rax, rcx
0x180007edb  jz      short loc_180007F1C
0x180007edd  test    byte ptr [rax+1Ch], 8
0x180007ee1  jz      short loc_180007F1C
0x180007ee3  cmp     byte ptr [rax+19h], 2
0x180007ee7  jb      short loc_180007F1C
0x180007ee9  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180007eee  mov     edx, 32h ; '2'
0x180007ef3  jmp     short loc_180007E8A
0x180007ef5  mov     r9d, eax; cchCount2
0x180007ef8  mov     [rsp+458h+cchASCIIChar], 1; bIgnoreCase
0x180007f00  lea     r8, [rsp+458h+String2]; lpString2
0x180007f05  mov     edx, ebx; cchCount1
0x180007f07  lea     rcx, [rsp+458h+ASCIICharStr]; lpString1
0x180007f0f  call    cs:__imp_CompareStringOrdinal
0x180007f15  cmp     eax, 2
0x180007f18  setz    sil
0x180007f1c  mov     eax, esi
0x180007f1e  mov     rcx, [rsp+458h+var_28]
0x180007f26  xor     rcx, rsp; StackCookie
0x180007f29  call    __security_check_cookie
0x180007f2e  mov     rbx, [rsp+458h+arg_0]
0x180007f36  add     rsp, 440h
0x180007f3d  pop     rdi
0x180007f3e  pop     rsi
0x180007f3f  pop     rbp
0x180007f40  retn
```
