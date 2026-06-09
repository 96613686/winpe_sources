# EmdpConvertToString(ulong,ushort,ushort,ushort,ushort,uchar const *,ushort *,EmdStringBuffer &)

- ea: `0x18000dcb0`
- end: `0x18000e7b8`
- name: `?EmdpConvertToString@@YAKKGGGGPEBEPEAGAEAVEmdStringBuffer@@@Z`
- size: `2824`
- prototype: `__int64 __fastcall(__int64, unsigned __int16, unsigned __int16, unsigned __int16, unsigned __int16, wchar_t *String, unsigned __int16 *, struct EmdStringBuffer *)`
- caller_count: `1`
- callee_count: `27`
- tags: `authz_impersonation, loader_planting, installer_update`

## callers

- `0x18000daf0`

## callees

- `0x18000dcb0`
- `0x18000e7c0`
- `0x18000e7f4`
- `0x18000e928`
- `0x18000ec34`
- `0x18000ed38`
- `0x18000ee28`
- `0x18000eed0`
- `0x18000ef7c`
- `0x18000f040`
- `0x18000f0e0`
- `0x18000f250`
- `0x18000f3f4`
- `0x180012d64`
- `0x180013bf8`
- `0x1800162e4`
- `0x18001cc90`
- `0x1800207c0`
- `0x180021296`
- `0x1800212a2`
- `0x180023b05`
- `0x18003e40c`
- `0x18003e4bc`
- `0x18003e57c`
- `0x18003e5e4`
- `0x18003e744`
- `0x18003e7c0`

## string_xrefs

- `0x18000e105`: `ntdll.dll`
- `0x18000e3fd`: `ntdll.dll`
- `0x18000e6d4`: `ntdll.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall EmdpConvertToString(
        __int64 a1,
        unsigned __int16 a2,
        unsigned __int16 a3,
        unsigned __int16 a4,
        unsigned __int16 a5,
        wchar_t *String,
        unsigned __int16 *a7,
        struct EmdStringBuffer *a8)
{
  unsigned __int16 v9; // ax
  __int64 result; // rax
  DWORD v11; // r10d
  __int64 v12; // r9
  __int64 v13; // rax
  __int64 v14; // r9
  __int64 v15; // rcx
  __int64 v16; // rcx
  unsigned __int16 v17; // bx
  unsigned __int16 v18; // ax
  unsigned __int16 v19; // dx
  __int64 v20; // r9
  unsigned int v21; // ecx
  unsigned __int16 v22; // dx
  wchar_t v23; // dx
  __int64 v24; // rcx
  struct EmdStringBuffer *v25; // rdx
  __int128 v26; // xmm0
  unsigned __int64 v27; // rdx
  char *v28; // rcx
  unsigned __int64 v29; // rdx
  unsigned __int64 v30; // r8
  unsigned __int64 v31; // rcx
  unsigned __int16 v32; // ax
  int v33; // r8d
  unsigned __int8 *v34; // rcx
  unsigned __int16 v35; // ax
  wchar_t v36[8]; // [rsp+20h] [rbp-50h] BYREF
  _OWORD v37[3]; // [rsp+30h] [rbp-40h] BYREF

  if ( a2 != 8 )
  {
    switch ( a2 )
    {
      case 0x134u:
LABEL_20:
        if ( a4 == (_DWORD)a1 )
        {
          if ( (_DWORD)a1 == 4 )
          {
            if ( a5 >= 4u )
            {
              *a7 = 4;
              v24 = *(unsigned int *)String;
              if ( a3 == 9 )
                return DecimalToBuffer_int_(v24, a8);
              v25 = a8;
              if ( a3 == 10 )
                return DecimalToBuffer_unsigned_int_(v24, v25);
              else
                return HexIntToBuffer_unsigned_int_(v24, v25);
            }
            return 111;
          }
          if ( a5 < 8u )
            return 111;
          *a7 = 8;
          if ( a3 == 9 )
            return DecimalToBuffer___int64_(*(_QWORD *)String, a8);
          if ( a3 != 10 )
            return HexIntToBuffer_unsigned___int64_(*(_QWORD *)String, a8);
          EmdStringBuffer::AppendInteger<10,unsigned __int64>(a8, *(_QWORD *)String);
          goto LABEL_17;
        }
        break;
      case 0xAu:
        if ( a4 == 8 )
        {
          if ( a5 >= 8u )
          {
            *a7 = 8;
            v16 = *(_QWORD *)String;
            if ( a3 == 19 || a3 == 37 )
              return HexIntToBuffer_unsigned___int64_(v16, a8);
            else
              return DecimalToBuffer_unsigned___int64_(v16, a8);
          }
          return 111;
        }
        break;
      case 1u:
LABEL_31:
        v17 = a5 >> 1;
        if ( a4 )
        {
          if ( a4 > v17 )
            return 111;
          v19 = a4;
          goto LABEL_34;
        }
        v18 = wcsnlen_0(String, v17);
        v19 = v18;
        if ( v18 < v17 )
        {
          a4 = v18 + 1;
LABEL_34:
          *a7 = 2 * a4;
          v20 = *((unsigned int *)a8 + 3);
          v21 = v20 + v19;
          *((_DWORD *)a8 + 3) = v21;
          if ( v21 <= *((_DWORD *)a8 + 2) )
            memcpy_0((void *)(*(_QWORD *)a8 + 2 * v20), String, 2LL * v19);
          goto LABEL_17;
        }
        break;
      default:
        if ( a2 <= 0x12Cu )
        {
          if ( a2 != 300 )
          {
            switch ( a2 )
            {
              case 0u:
                return 15005;
              case 2u:
                goto LABEL_8;
              case 3u:
                if ( a4 != 1 )
                  return 15005;
                if ( !a5 )
                  return 111;
                *a7 = 1;
                v23 = *(unsigned __int8 *)String;
                if ( a3 == 1 )
                  goto LABEL_76;
                v24 = (unsigned int)(char)v23;
                return DecimalToBuffer_int_(v24, a8);
              case 4u:
                if ( a4 != 1 )
                  return 15005;
                if ( !a5 )
                  return 111;
                *a7 = 1;
                v23 = *(unsigned __int8 *)String;
                if ( a3 == 1 )
                {
LABEL_76:
                  v36[0] = v23;
                  goto LABEL_77;
                }
                v24 = *(unsigned __int8 *)String;
                v25 = a8;
                if ( a3 != 16 )
                  return DecimalToBuffer_unsigned_int_(v24, v25);
                return HexIntToBuffer_unsigned_int_(v24, v25);
              case 5u:
                if ( a4 != 2 )
                  return 15005;
                if ( a5 < 2u )
                  return 111;
                *a7 = 2;
                return DecimalToBuffer_int_((unsigned int)(__int16)*String, a8);
              case 6u:
                if ( a4 != 2 )
                  return 15005;
                if ( a5 < 2u )
                  return 111;
                *a7 = 2;
                v24 = *String;
                if ( a3 == 17 )
                  goto LABEL_48;
                if ( a3 == 1 )
                {
                  v36[0] = *String;
                  goto LABEL_88;
                }
                v25 = a8;
                if ( a3 != 22 )
                  return DecimalToBuffer_unsigned_int_(v24, v25);
                return DecimalToBuffer_unsigned_int_((unsigned __int16)__ROR2__(v24, 8), a8);
              case 7u:
                if ( a4 != 4 )
                  return 15005;
                if ( a5 < 4u )
                  return 111;
                *a7 = 4;
                v24 = *(unsigned int *)String;
                if ( a3 != 32 )
                  return DecimalToBuffer_int_(v24, a8);
                if ( (v24 & 0x10000000) != 0 )
                  return FormatMessageToBuffer(
                           (unsigned int)v24 & 0xEFFFFFFF,
                           (wchar_t *)L"Unknown HResult Error code: 0x",
                           L"ntdll.dll",
                           a8);
                else
                  return FormatMessageToBuffer(v24, (wchar_t *)L"Unknown HResult Error code: 0x", 0, a8);
              case 9u:
                if ( a4 != 8 )
                  return 15005;
                if ( a5 < 8u )
                  return 111;
                *a7 = 8;
                return DecimalToBuffer___int64_(*(_QWORD *)String, a8);
              case 0xBu:
                if ( a4 != 4 )
                  return 15005;
                if ( a5 < 4u )
                  return 111;
                *a7 = 4;
                return FloatToBuffer(a1, a8);
              case 0xCu:
                if ( a4 != 8 )
                  return 15005;
                if ( a5 < 8u )
                  return 111;
                *a7 = 8;
                return FloatToBuffer(a1, a8);
              case 0xDu:
                if ( a5 < 4u )
                  return 111;
                *a7 = 4;
                LOBYTE(a1) = *(_DWORD *)String != 0;
                return BooleanToBuffer(a1, a8);
              case 0xEu:
                *a7 = a4;
                switch ( a3 )
                {
                  case 0xFu:
                    goto LABEL_110;
                  case 0x18u:
                    if ( !a4 )
                      return WideToBuffer((void *)&pszFormat);
                    if ( a5 < 0x10u )
                    {
                      *a7 = a5;
                      return HexBinaryToBuffer(String, a5, a8);
                    }
                    *a7 = 16;
                    v26 = *(_OWORD *)String;
                    goto LABEL_109;
                  case 0x19u:
                    if ( a5 < a4 )
                      return 111;
                    return SockAddrToBuffer(String);
                  default:
LABEL_110:
                    if ( a5 < a4 )
                      return 111;
                    return HexBinaryToBuffer(String, a4, a8);
                }
              case 0xFu:
                if ( a4 != 16 )
                  return 15005;
                if ( a5 < 0x10u )
                  return 111;
                *a7 = 16;
                v37[0] = *(_OWORD *)String;
                return GuidToBuffer(v37, a8);
              case 0x10u:
                goto LABEL_20;
              case 0x11u:
                if ( a5 < 8u )
                  return 111;
                *a7 = 8;
                return FileTimeToBuffer(a3, *(_QWORD *)String, a8);
              case 0x12u:
                if ( a5 < 0x10u )
                  return 111;
                *a7 = 16;
                v37[0] = *(_OWORD *)String;
                return SystemTimeToBuffer(a3, v37, a8);
              case 0x13u:
                if ( a5 < 8u )
                  return 111;
                v22 = 4 * (*((unsigned __int8 *)String + 1) + 2);
                if ( a5 < v22 )
                  return 111;
                *a7 = v22;
                return SidToBuffer(String);
              case 0x14u:
                if ( a4 != 4 )
                  return 15005;
                if ( a5 < 4u )
                  return 111;
                *a7 = 4;
                v24 = *(unsigned int *)String;
                if ( a3 == 30 )
                  return FormatMessageToBuffer(v24, (wchar_t *)L"Unknown Win32 Error code: 0x", 0, a8);
                if ( a3 != 31 )
                {
LABEL_48:
                  v25 = a8;
                  return HexIntToBuffer_unsigned_int_(v24, v25);
                }
                return FormatMessageToBuffer(v24, (wchar_t *)L"Unknown NTSTATUS Error code: 0x", L"ntdll.dll", a8);
              case 0x15u:
                if ( a5 < 8u )
                  return 111;
                *a7 = 8;
                return HexIntToBuffer_unsigned___int64_(*(_QWORD *)String, a8);
              case 0x16u:
                goto LABEL_128;
              case 0x17u:
                goto LABEL_133;
              case 0x19u:
                if ( a5 < 2u )
                  return 111;
                v27 = *String;
                if ( (unsigned __int64)a5 - 2 < v27 )
                  return 111;
                *a7 = v27 + 2;
                v28 = (char *)(String + 1);
                switch ( a3 )
                {
                  case 0xFu:
                    return HexBinaryToBuffer(v28, v27, a8);
                  case 0x18u:
                    if ( (_DWORD)v27 != 16 )
                      return HexBinaryToBuffer(v28, v27, a8);
                    v26 = *(_OWORD *)v28;
LABEL_109:
                    v37[0] = v26;
                    result = IPV6ToBuffer(v37, a8);
                    break;
                  case 0x19u:
                    result = SockAddrToBuffer(v28);
                    break;
                  default:
                    return HexBinaryToBuffer(v28, v27, a8);
                }
                break;
              default:
                return 50;
            }
            return result;
          }
LABEL_128:
          if ( a5 >= 2u )
          {
            v29 = *String;
            if ( (unsigned __int64)a5 - 2 >= v29 )
            {
              *a7 = v29 + 2;
              return WideToBuffer(String + 1);
            }
          }
          return 111;
        }
        switch ( a2 )
        {
          case 0x12Du:
LABEL_133:
            if ( a5 < 2u )
              return 111;
            v30 = *String;
            if ( (unsigned __int64)a5 - 2 < v30 )
              return 111;
            *a7 = v30 + 2;
            return MbcsToBuffer(a3, String + 1, v30, a8);
          case 0x12Eu:
          case 0x12Fu:
            if ( a5 < 2u )
              return 111;
            v31 = (unsigned __int16)__ROR2__(*String, 8);
            if ( (unsigned __int64)a5 - 2 < v31 )
              return 111;
            *a7 = v31 + 2;
            if ( a2 == 303 )
              return MbcsToBuffer(a3, String + 1, (unsigned __int16)v31, a8);
            else
              return WideToBuffer(String + 1);
          case 0x130u:
            *a7 = a5;
            return WideToBuffer(String);
          case 0x131u:
            *a7 = a5;
            return MbcsToBuffer(a3, String, a5, a8);
          case 0x132u:
            if ( a3 == 1 )
              goto LABEL_31;
            if ( a5 < 2u )
              return 111;
            *a7 = 2;
            v36[0] = *String;
LABEL_88:
            v36[1] = 0;
            EmdStringBuffer::AppendWide(a8, v36, 2u);
            return 0;
          case 0x133u:
            if ( a3 == 1 )
            {
LABEL_8:
              if ( a4 )
              {
                if ( a4 > a5 )
                  return 111;
                v9 = a4;
              }
              else
              {
                v9 = strnlen_0((const char *)String, a5);
                if ( v9 >= a5 )
                  return 15005;
                a4 = v9 + 1;
              }
              *a7 = a4;
              return MbcsToBuffer(a3, String, v9, a8);
            }
            if ( !a5 )
              return 111;
            *a7 = 1;
            v36[0] = *(unsigned __int8 *)String;
LABEL_77:
            v36[1] = 0;
LABEL_79:
            EmdStringBuffer::AppendWide(a8, v36, 2u);
            break;
          case 0x135u:
            if ( a5 < 4u )
              return 111;
            v27 = *(unsigned int *)String;
            if ( (unsigned int)v27 >= 0x10000 )
              return 15005;
            if ( (unsigned __int64)a5 - 4 < v27 )
              return 111;
            *a7 = v27 + 4;
            v28 = (char *)(String + 2);
            return HexBinaryToBuffer(v28, v27, a8);
          case 0x136u:
            if ( a5 < 4u )
              return 111;
            if ( !*(_DWORD *)String )
            {
              *a7 = 4;
              wcscpy(v36, L"0");
              goto LABEL_79;
            }
            v32 = 4;
            if ( (_DWORD)a1 != 4 )
              v32 = 8;
            v33 = v32 * 2;
            if ( a5 < (unsigned int)(v32 * 2) + 8 )
              return 111;
            v34 = (unsigned __int8 *)&String[v32];
            v35 = 4 * (v34[1] + 2);
            if ( a5 - v33 < v35 )
              return 111;
            *a7 = v33 + v35;
            return WbemSidToBuffer(v34);
          default:
            return 50;
        }
        return 0;
    }
    return 15005;
  }
  if ( a4 != 4 )
    return 15005;
  if ( a5 < 4u )
    return 111;
  *a7 = 4;
  v11 = *(_DWORD *)String;
  if ( a3 == 37 )
  {
LABEL_14:
    LODWORD(v12) = 18;
    do
    {
      v12 = (unsigned int)(v12 - 1);
      v13 = v11 & 0xF;
      v11 >>= 4;
      *((_WORD *)&v37[1] + v12) = a0123456789abcd_0[v13];
    }
    while ( v11 );
    v14 = (unsigned int)(v12 - 2);
    *((_WORD *)&v37[1] + v14) = 48;
    *((_WORD *)&v37[1] + (unsigned int)(v14 + 1)) = 120;
    EmdStringBuffer::AppendWide(a8, (const wchar_t *)&v37[1] + v14, 18 - v14);
LABEL_17:
    v15 = *((unsigned int *)a8 + 3);
    *((_DWORD *)a8 + 3) = v15 + 1;
    if ( (unsigned int)(v15 + 1) <= *((_DWORD *)a8 + 2) )
      *(_WORD *)(*(_QWORD *)a8 + 2 * v15) = 0;
    return 0;
  }
  switch ( a3 )
  {
    case 0x12u:
    case 0x1Du:
      goto LABEL_14;
    case 0x17u:
      result = IPV4ToBuffer(v11, a8, &_ImageBase);
      break;
    case 0x1Eu:
      result = FormatMessageToBuffer(v11, (wchar_t *)L"Unknown Win32 Error code: 0x", 0, a8);
      break;
    case 0x1Fu:
      result = FormatMessageToBuffer(v11, (wchar_t *)L"Unknown NTSTATUS Error code: 0x", L"ntdll.dll", a8);
      break;
    default:
      result = DecimalToBuffer_unsigned_int_(v11, a8);
      break;
  }
  return result;
}

```

## disassembly

```asm
0x18000dcb0  mov     [rsp-28h+arg_0], rbx
0x18000dcb5  push    rbp
0x18000dcb6  push    rsi
0x18000dcb7  push    rdi
0x18000dcb8  push    r14
0x18000dcba  push    r15
0x18000dcbc  mov     rbp, rsp
0x18000dcbf  sub     rsp, 70h
0x18000dcc3  mov     rax, cs:__security_cookie
0x18000dcca  xor     rax, rsp
0x18000dccd  mov     [rbp+var_8], rax
0x18000dcd1  mov     rdi, [rbp+arg_38]
0x18000dcd5  mov     rsi, [rbp+String]
0x18000dcd9  mov     r15, [rbp+arg_30]
0x18000dcdd  movzx   eax, dx
0x18000dce0  movzx   r14d, r8w
0x18000dce4  cmp     eax, 8
0x18000dce7  jz      short loc_18000DD5F
0x18000dce9  cmp     eax, 134h
0x18000dcee  jz      loc_18000DE22; jumptable 000000018000DD32 case 16
0x18000dcf4  cmp     eax, 0Ah
0x18000dcf7  jz      loc_18000DE6D
0x18000dcfd  cmp     eax, 1
0x18000dd00  jz      loc_18000DEAB
0x18000dd06  cmp     eax, 12Ch
0x18000dd0b  ja      loc_18000E464
0x18000dd11  jz      loc_18000E42C; jumptable 000000018000DD32 case 22
0x18000dd17  cmp     eax, 19h; switch 26 cases
0x18000dd1a  ja      def_18000DD32; jumptable 000000018000DD32 default case, cases 1,8,10,24
0x18000dd20  lea     r8, __ImageBase
0x18000dd27  mov     eax, ds:(jpt_18000DD32 - 180000000h)[r8+rax*4]
0x18000dd2f  add     rax, r8
0x18000dd32  jmp     rax; switch jump
0x18000dd34  test    r9w, r9w; jumptable 000000018000DD32 case 2
0x18000dd38  jnz     loc_18000E0D1
0x18000dd3e  movzx   ebx, [rbp+arg_20]
0x18000dd42  mov     rcx, rsi; String
0x18000dd45  mov     edx, ebx; MaxCount
0x18000dd47  call    strnlen_0
0x18000dd4c  cmp     ax, bx
0x18000dd4f  jb      loc_18000DFFC
0x18000dd55  mov     eax, 3A9Dh; jumptable 000000018000DD32 case 0
0x18000dd5a  jmp     loc_18000DE02
0x18000dd5f  cmp     r9w, 4
0x18000dd64  jnz     short loc_18000DD55; jumptable 000000018000DD32 case 0
0x18000dd66  cmp     [rbp+arg_20], r9w
0x18000dd6b  jb      loc_18000DF1A
0x18000dd71  mov     [r15], r9w
0x18000dd75  mov     eax, r14d
0x18000dd78  mov     r10d, [rsi]
0x18000dd7b  lea     r8, __ImageBase
0x18000dd82  cmp     r14d, 25h ; '%'
0x18000dd86  jnz     loc_18000E0E5
0x18000dd8c  mov     r11d, 12h; jumptable 000000018000E6A5 cases 18,29
0x18000dd92  mov     r9d, r11d
0x18000dd95  movzx   eax, r10b
0x18000dd99  dec     r9d
0x18000dd9c  and     eax, 0Fh
0x18000dd9f  shr     r10d, 4
0x18000dda3  movsx   ecx, byte ptr [rax+r8+57250h]
0x18000ddac  mov     [rbp+r9*2+var_30], cx
0x18000ddb2  mov     eax, r9d
0x18000ddb5  test    r10d, r10d
0x18000ddb8  jnz     short loc_18000DD95
0x18000ddba  add     r9d, 0FFFFFFFEh
0x18000ddbe  lea     rdx, [rbp+var_30]
0x18000ddc2  mov     eax, 78h ; 'x'
0x18000ddc7  mov     word ptr [rdx+r9*2], 30h ; '0'
0x18000ddce  sub     r11d, r9d
0x18000ddd1  lea     rdx, [rdx+r9*2]; wchar_t *
0x18000ddd5  mov     r8d, r11d; unsigned int
0x18000ddd8  lea     ecx, [r9+1]
0x18000dddc  mov     [rbp+rcx*2+var_30], ax
0x18000dde1  mov     rcx, rdi; this
0x18000dde4  call    ?AppendWide@EmdStringBuffer@@QEAAXPEB_WK@Z; EmdStringBuffer::AppendWide(wchar_t const *,ulong)
0x18000dde9  mov     ecx, [rdi+0Ch]
0x18000ddec  lea     eax, [rcx+1]
0x18000ddef  mov     [rdi+0Ch], eax
0x18000ddf2  cmp     eax, [rdi+8]
0x18000ddf5  ja      short loc_18000DE00
0x18000ddf7  mov     rax, [rdi]
0x18000ddfa  xor     edx, edx
0x18000ddfc  mov     [rax+rcx*2], dx
0x18000de00  xor     eax, eax
0x18000de02  mov     rcx, [rbp+var_8]
0x18000de06  xor     rcx, rsp; StackCookie
0x18000de09  call    __security_check_cookie
0x18000de0e  mov     rbx, [rsp+70h+arg_0]
0x18000de16  add     rsp, 70h
0x18000de1a  pop     r15
0x18000de1c  pop     r14
0x18000de1e  pop     rdi
0x18000de1f  pop     rsi
0x18000de20  pop     rbp
0x18000de21  retn
0x18000de22  movzx   eax, r9w; jumptable 000000018000DD32 case 16
0x18000de26  cmp     eax, ecx
0x18000de28  jnz     loc_18000DD55; jumptable 000000018000DD32 case 0
0x18000de2e  cmp     ecx, 4
0x18000de31  jz      loc_18000E663
0x18000de37  cmp     [rbp+arg_20], 8
0x18000de3c  jb      loc_18000DF1A
0x18000de42  mov     edx, r14d
0x18000de45  mov     word ptr [r15], 8
0x18000de4b  sub     edx, 9
0x18000de4e  jz      loc_18000E222
0x18000de54  cmp     edx, 1
0x18000de57  jnz     loc_18000DFEC
0x18000de5d  mov     rdx, [rsi]
0x18000de60  mov     rcx, rdi
0x18000de63  call    ??$AppendInteger@$09_K@EmdStringBuffer@@AEAAX_K@Z; EmdStringBuffer::AppendInteger<10,unsigned __int64>(unsigned __int64)
0x18000de68  jmp     loc_18000DDE9
0x18000de6d  cmp     r9w, 8
0x18000de72  jnz     loc_18000DD55; jumptable 000000018000DD32 case 0
0x18000de78  cmp     [rbp+arg_20], r9w
0x18000de7d  jb      loc_18000DF1A
0x18000de83  mov     [r15], r9w
0x18000de87  mov     rcx, [rsi]
0x18000de8a  cmp     r14d, 13h
0x18000de8e  jz      loc_18000E06D
0x18000de94  cmp     r14d, 25h ; '%'
0x18000de98  jz      loc_18000E063
0x18000de9e  mov     rdx, rdi
0x18000dea1  call    DecimalToBuffer_unsigned___int64_
0x18000dea6  jmp     loc_18000DE02
0x18000deab  movzx   ebx, [rbp+arg_20]
0x18000deaf  shr     bx, 1
0x18000deb2  test    r9w, r9w
0x18000deb6  jnz     loc_18000E650
0x18000debc  movzx   edx, bx; MaxCount
0x18000debf  mov     rcx, rsi; Source
0x18000dec2  call    wcsnlen_0
0x18000dec7  mov     rdx, rax
0x18000deca  cmp     ax, bx
0x18000decd  jnb     loc_18000DD55; jumptable 000000018000DD32 case 0
0x18000ded3  lea     r9d, [rax+1]
0x18000ded7  add     r9w, r9w
0x18000dedb  movzx   ecx, dx
0x18000dede  mov     [r15], r9w
0x18000dee2  mov     r9d, [rdi+0Ch]
0x18000dee6  add     ecx, r9d
0x18000dee9  mov     [rdi+0Ch], ecx
0x18000deec  cmp     ecx, [rdi+8]
0x18000deef  ja      loc_18000DDE9
0x18000def5  mov     rax, [rdi]
0x18000def8  movzx   r8d, dx
0x18000defc  mov     rdx, rsi; Src
0x18000deff  add     r8, r8; Size
0x18000df02  lea     rcx, [rax+r9*2]; void *
0x18000df06  call    memcpy_0
0x18000df0b  jmp     loc_18000DDE9
0x18000df10  movzx   eax, [rbp+arg_20]; jumptable 000000018000DD32 case 19
0x18000df14  cmp     ax, 8
0x18000df18  jnb     short loc_18000DF24
0x18000df1a  mov     eax, 6Fh ; 'o'
0x18000df1f  jmp     loc_18000DE02
0x18000df24  movzx   edx, byte ptr [rsi+1]
0x18000df28  add     dx, 2
0x18000df2c  shl     dx, 2
0x18000df30  cmp     ax, dx
0x18000df33  jb      short loc_18000DF1A
0x18000df35  mov     r8, rdi
0x18000df38  mov     [r15], dx
0x18000df3c  mov     rcx, rsi; Src
0x18000df3f  call    SidToBuffer
0x18000df44  jmp     loc_18000DE02
0x18000df49  cmp     r9w, 1; jumptable 000000018000DD32 case 4
0x18000df4e  jnz     loc_18000DD55; jumptable 000000018000DD32 case 0
0x18000df54  cmp     [rbp+arg_20], r9w
0x18000df59  jb      short loc_18000DF1A
0x18000df5b  mov     ecx, r14d
0x18000df5e  mov     [r15], r9w
0x18000df62  movzx   edx, byte ptr [rsi]
0x18000df65  sub     ecx, 1
0x18000df68  jz      loc_18000E149
0x18000df6e  cmp     ecx, 0Fh
0x18000df71  mov     ecx, edx
0x18000df73  mov     rdx, rdi
0x18000df76  jnz     loc_18000E188
0x18000df7c  call    HexIntToBuffer_unsigned_int_
0x18000df81  jmp     loc_18000DE02
0x18000df86  cmp     r9w, 2; jumptable 000000018000DD32 case 6
0x18000df8b  jnz     loc_18000DD55; jumptable 000000018000DD32 case 0
0x18000df91  cmp     [rbp+arg_20], r9w
0x18000df96  jb      short loc_18000DF1A
0x18000df98  mov     r8d, 2
0x18000df9e  mov     edx, r14d
0x18000dfa1  mov     [r15], r8w
0x18000dfa5  movzx   ecx, word ptr [rsi]
0x18000dfa8  cmp     r14d, 11h
0x18000dfac  jnz     loc_18000E1BC
0x18000dfb2  mov     rdx, rdi
0x18000dfb5  jmp     short loc_18000DF7C
0x18000dfb7  cmp     [rbp+arg_20], 4; jumptable 000000018000DD32 case 13
0x18000dfbc  jb      loc_18000DF1A
0x18000dfc2  mov     word ptr [r15], 4
0x18000dfc8  mov     rdx, rdi
0x18000dfcb  cmp     dword ptr [rsi], 0
0x18000dfce  setnz   cl
0x18000dfd1  call    BooleanToBuffer
0x18000dfd6  jmp     loc_18000DE02
0x18000dfdb  cmp     [rbp+arg_20], 8; jumptable 000000018000DD32 case 21
0x18000dfe0  jb      loc_18000DF1A
0x18000dfe6  mov     word ptr [r15], 8
0x18000dfec  mov     rcx, [rsi]
0x18000dfef  mov     rdx, rdi
0x18000dff2  call    HexIntToBuffer_unsigned___int64_
0x18000dff7  jmp     loc_18000DE02
0x18000dffc  lea     r9d, [rax+1]
0x18000e000  mov     [r15], r9w
0x18000e004  movzx   r8d, ax
0x18000e008  mov     r9, rdi
0x18000e00b  mov     rdx, rsi
0x18000e00e  movzx   ecx, r14w
0x18000e012  call    MbcsToBuffer
0x18000e017  jmp     loc_18000DE02
0x18000e01c  cmp     r9w, 4; jumptable 000000018000DD32 case 7
0x18000e021  jnz     loc_18000DD55; jumptable 000000018000DD32 case 0
0x18000e027  cmp     [rbp+arg_20], r9w
0x18000e02c  jb      loc_18000DF1A
0x18000e032  mov     [r15], r9w
0x18000e036  mov     ecx, [rsi]; dwMessageId
0x18000e038  cmp     r14d, 20h ; ' '
0x18000e03c  jnz     loc_18000E13C
0x18000e042  lea     rdx, aUnknownHresult; "Unknown HResult Error code: 0x"
0x18000e049  mov     r9, rdi; this
0x18000e04c  bt      ecx, 1Ch
0x18000e050  jb      loc_18000E101
0x18000e056  xor     r8d, r8d; lpLibFileName
0x18000e059  call    FormatMessageToBuffer
0x18000e05e  jmp     loc_18000DE02
0x18000e063  cmp     r14d, 1Bh
0x18000e067  jz      loc_18000DE9E
0x18000e06d  mov     rdx, rdi
0x18000e070  call    HexIntToBuffer_unsigned___int64_
0x18000e075  jmp     loc_18000DE02
0x18000e07a  cmp     [rbp+arg_20], 8; jumptable 000000018000DD32 case 17
0x18000e07f  jb      loc_18000DF1A
0x18000e085  mov     word ptr [r15], 8
0x18000e08b  mov     r8, rdi
0x18000e08e  mov     rdx, [rsi]
0x18000e091  movzx   ecx, r14w
0x18000e095  call    FileTimeToBuffer
0x18000e09a  jmp     loc_18000DE02
0x18000e09f  cmp     r9w, 10h; jumptable 000000018000DD32 case 15
0x18000e0a4  jnz     loc_18000DD55; jumptable 000000018000DD32 case 0
0x18000e0aa  cmp     [rbp+arg_20], r9w
0x18000e0af  jb      loc_18000DF1A
0x18000e0b5  mov     [r15], r9w
0x18000e0b9  lea     rcx, [rbp+var_40]
0x18000e0bd  movups  xmm0, xmmword ptr [rsi]
0x18000e0c0  mov     rdx, rdi
0x18000e0c3  movaps  [rbp+var_40], xmm0
0x18000e0c7  call    GuidToBuffer
0x18000e0cc  jmp     loc_18000DE02
0x18000e0d1  cmp     r9w, [rbp+arg_20]
0x18000e0d6  ja      loc_18000DF1A
0x18000e0dc  movzx   eax, r9w
0x18000e0e0  jmp     loc_18000E000
0x18000e0e5  add     eax, 0FFFFFFEEh; switch 14 cases
0x18000e0e8  cmp     eax, 0Dh
0x18000e0eb  jbe     loc_18000E698
0x18000e0f1  mov     rdx, rdi; jumptable 000000018000E6A5 default case, cases 19-22,24-28
0x18000e0f4  mov     ecx, r10d
0x18000e0f7  call    DecimalToBuffer_unsigned_int_
0x18000e0fc  jmp     loc_18000DE02
0x18000e101  btr     ecx, 1Ch; dwMessageId
0x18000e105  lea     r8, aNtdllDll_0; "ntdll.dll"
0x18000e10c  call    FormatMessageToBuffer
0x18000e111  jmp     loc_18000DE02
0x18000e116  cmp     r9w, 1; jumptable 000000018000DD32 case 3
0x18000e11b  jnz     loc_18000DD55; jumptable 000000018000DD32 case 0
0x18000e121  cmp     [rbp+arg_20], r9w
0x18000e126  jb      loc_18000DF1A
0x18000e12c  mov     [r15], r9w
0x18000e130  movzx   edx, byte ptr [rsi]
0x18000e133  cmp     r14d, 1
0x18000e137  jz      short loc_18000E149
0x18000e139  movsx   ecx, dl
0x18000e13c  mov     rdx, rdi
0x18000e13f  call    DecimalToBuffer_int_
0x18000e144  jmp     loc_18000DE02
0x18000e149  mov     [rbp+var_50], dx
0x18000e14d  jmp     short loc_18000E15C
0x18000e14f  mov     word ptr [r15], 1
0x18000e155  movzx   eax, byte ptr [rsi]
0x18000e158  mov     [rbp+var_50], ax
0x18000e15c  xor     edx, edx
0x18000e15e  mov     [rbp+var_50+2], dx
0x18000e162  jmp     short loc_18000E171
0x18000e164  mov     word ptr [r15], 4
0x18000e16a  mov     dword ptr [rbp+var_50], 30h ; '0'
0x18000e171  mov     r8d, 2; unsigned int
0x18000e177  lea     rdx, [rbp+var_50]; wchar_t *
0x18000e17b  mov     rcx, rdi; this
0x18000e17e  call    ?AppendWide@EmdStringBuffer@@QEAAXPEB_WK@Z; EmdStringBuffer::AppendWide(wchar_t const *,ulong)
0x18000e183  jmp     loc_18000DE00
0x18000e188  call    DecimalToBuffer_unsigned_int_
0x18000e18d  jmp     loc_18000DE02
0x18000e192  cmp     r9w, 2; jumptable 000000018000DD32 case 5
  ... truncated ...
```
