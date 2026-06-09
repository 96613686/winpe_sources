# CClientUtils::IsEqualDomainName(ushort const *,ulong,ushort const *,ulong)

- ea: `0x180082310`
- end: `0x180082471`
- name: `?IsEqualDomainName@CClientUtils@@UEAAHPEBGK0K@Z`
- size: `353`
- prototype: `int(CClientUtils *__hidden this, const unsigned __int16 *, unsigned int, const unsigned __int16 *, unsigned int)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x1800044bf`
- `0x18000b1d8`
- `0x18000ec54`
- `0x180082310`
- `0x18009a520`

## import_xrefs

- `KERNEL32!CompareStringOrdinal` at `0x18008243f`
- `KERNEL32!CompareStringOrdinal` at `0x18008243f`
- `Normaliz!IdnToAscii` at `0x18008237b`
- `Normaliz!IdnToAscii` at `0x1800823f0`
- `Normaliz!IdnToAscii` at `0x18008237b`
- `Normaliz!IdnToAscii` at `0x1800823f0`

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
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v11 = 50;
      goto LABEL_6;
    }
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
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
0x180082310  mov     [rsp+arg_0], rbx
0x180082315  push    rbp
0x180082316  push    rsi
0x180082317  push    rdi
0x180082318  sub     rsp, 440h
0x18008231f  mov     rax, cs:__security_cookie
0x180082326  xor     rax, rsp
0x180082329  mov     [rsp+458h+var_28], rax
0x180082331  mov     edi, r8d
0x180082334  lea     rcx, [rsp+458h+ASCIICharStr]; void *
0x18008233c  mov     rbx, rdx
0x18008233f  mov     r8d, 200h; Size
0x180082345  xor     edx, edx; Val
0x180082347  mov     rbp, r9
0x18008234a  xor     esi, esi
0x18008234c  call    memset_0
0x180082351  xor     edx, edx; Val
0x180082353  lea     rcx, [rsp+458h+String2]; void *
0x180082358  mov     r8d, 200h; Size
0x18008235e  call    memset_0
0x180082363  lea     r9, [rsp+458h+ASCIICharStr]; lpASCIICharStr
0x18008236b  mov     [rsp+458h+cchASCIIChar], 100h; cchASCIIChar
0x180082373  mov     r8d, edi; cchUnicodeChar
0x180082376  mov     rdx, rbx; lpUnicodeCharStr
0x180082379  xor     ecx, ecx; dwFlags
0x18008237b  call    cs:__imp_IdnToAscii
0x180082381  mov     ebx, eax
0x180082383  test    eax, eax
0x180082385  jg      short loc_1800823D6
0x180082387  mov     rax, cs:WPP_GLOBAL_Control
0x18008238e  lea     rcx, WPP_GLOBAL_Control
0x180082395  cmp     rax, rcx
0x180082398  jz      loc_18008244C
0x18008239e  test    byte ptr [rax+1Ch], 8
0x1800823a2  jz      loc_18008244C
0x1800823a8  cmp     byte ptr [rax+19h], 2
0x1800823ac  jb      loc_18008244C
0x1800823b2  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800823b7  lea     edx, [rsi+31h]
0x1800823ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1800823c1  lea     r8, WPP_72aaf7d92de938e37e89151f64d0d640_Traceguids
0x1800823c8  mov     r9d, eax
0x1800823cb  mov     rcx, [rcx+10h]
0x1800823cf  call    WPP_SF_D
0x1800823d4  jmp     short loc_18008244C
0x1800823d6  mov     r8d, [rsp+458h+cchUnicodeChar]; cchUnicodeChar
0x1800823de  lea     r9, [rsp+458h+String2]; lpASCIICharStr
0x1800823e3  mov     rdx, rbp; lpUnicodeCharStr
0x1800823e6  mov     [rsp+458h+cchASCIIChar], 100h; cchASCIIChar
0x1800823ee  xor     ecx, ecx; dwFlags
0x1800823f0  call    cs:__imp_IdnToAscii
0x1800823f6  test    eax, eax
0x1800823f8  jg      short loc_180082425
0x1800823fa  mov     rax, cs:WPP_GLOBAL_Control
0x180082401  lea     rcx, WPP_GLOBAL_Control
0x180082408  cmp     rax, rcx
0x18008240b  jz      short loc_18008244C
0x18008240d  test    byte ptr [rax+1Ch], 8
0x180082411  jz      short loc_18008244C
0x180082413  cmp     byte ptr [rax+19h], 2
0x180082417  jb      short loc_18008244C
0x180082419  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18008241e  mov     edx, 32h ; '2'
0x180082423  jmp     short loc_1800823BA
0x180082425  mov     r9d, eax; cchCount2
0x180082428  mov     [rsp+458h+cchASCIIChar], 1; bIgnoreCase
0x180082430  lea     r8, [rsp+458h+String2]; lpString2
0x180082435  mov     edx, ebx; cchCount1
0x180082437  lea     rcx, [rsp+458h+ASCIICharStr]; lpString1
0x18008243f  call    cs:__imp_CompareStringOrdinal
0x180082445  cmp     eax, 2
0x180082448  setz    sil
0x18008244c  mov     eax, esi
0x18008244e  mov     rcx, [rsp+458h+var_28]
0x180082456  xor     rcx, rsp; StackCookie
0x180082459  call    __security_check_cookie
0x18008245e  mov     rbx, [rsp+458h+arg_0]
0x180082466  add     rsp, 440h
0x18008246d  pop     rdi
0x18008246e  pop     rsi
0x18008246f  pop     rbp
0x180082470  retn
```
