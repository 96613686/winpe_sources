# GetDateLimits(uint,_SYSTEMTIME *,_SYSTEMTIME *)

- ea: `0x180017c50`
- end: `0x180017ec2`
- name: `?GetDateLimits@@YAHIPEAU_SYSTEMTIME@@0@Z`
- size: `626`
- prototype: `__int64 __fastcall(unsigned int, struct _SYSTEMTIME *, struct _SYSTEMTIME *)`
- caller_count: `4`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x180009238`
- `0x18000c2b0`
- `0x180011e38`
- `0x18001b95c`

## callees

- `0x180017c50`
- `0x180028f60`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoW` at `0x180017cd8`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoW` at `0x180017cd8`
- `KERNEL32!ConvertCalDateTimeToSystemTime` at `0x180017e1f`
- `KERNEL32!ConvertCalDateTimeToSystemTime` at `0x180017e30`
- `KERNEL32!ConvertCalDateTimeToSystemTime` at `0x180017e1f`
- `KERNEL32!ConvertCalDateTimeToSystemTime` at `0x180017e30`
- `KERNEL32!UpdateCalendarDayOfWeek` at `0x180017e08`
- `KERNEL32!UpdateCalendarDayOfWeek` at `0x180017e12`
- `KERNEL32!UpdateCalendarDayOfWeek` at `0x180017e08`
- `KERNEL32!UpdateCalendarDayOfWeek` at `0x180017e12`

## pseudocode

```c
__int64 __fastcall GetDateLimits(unsigned int a1, struct _SYSTEMTIME *a2, struct _SYSTEMTIME *a3)
{
  __int64 result; // rax
  __int64 v4; // r15
  unsigned int v7; // ebx
  unsigned int v8; // edi
  unsigned int v9; // r8d
  __int64 v10; // rcx
  unsigned int v11; // ebx
  wchar_t LCData[4]; // [rsp+20h] [rbp-60h] BYREF
  __int128 v13; // [rsp+28h] [rbp-58h] BYREF
  __int128 v14; // [rsp+38h] [rbp-48h]
  __int64 v15; // [rsp+48h] [rbp-38h]
  _BYTE v16[40]; // [rsp+50h] [rbp-30h] BYREF

  result = 0;
  v4 = a1;
  *(_DWORD *)LCData = 0;
  v15 = 0;
  memset(v16, 0, sizeof(v16));
  v13 = 0;
  v14 = 0;
  if ( a2 && a3 && a1 <= 1 )
  {
    v7 = 0;
    v8 = 0;
    if ( GetLocaleInfoW(0x400u, 0x20001009u, LCData, 2) )
    {
      v9 = *(_DWORD *)LCData;
    }
    else
    {
      v9 = 1;
      wcscpy(LCData, L"\x01");
    }
    if ( v9 > 8 )
    {
      switch ( v9 )
      {
        case 9u:
        case 0xAu:
        case 0xBu:
        case 0xCu:
          goto LABEL_16;
        case 0x16u:
          v11 = 5;
          break;
        case 0x17u:
          v11 = 3;
          break;
        default:
          return v8;
      }
    }
    else
    {
      switch ( v9 )
      {
        case 8u:
          v11 = 2;
          break;
        case 1u:
        case 2u:
        case 3u:
          goto LABEL_16;
        case 4u:
          v7 = 4;
          goto LABEL_16;
        case 5u:
LABEL_16:
          v8 = 1;
          v10 = v7 + 6 * v4;
          a2->wDay = word_18002F820[6 * v10];
          a2->wMonth = word_18002F820[6 * v10 + 1];
          a2->wYear = word_18002F820[6 * v10 + 2];
          a3->wDay = word_18002F820[6 * v10 + 3];
          a3->wMonth = word_18002F820[6 * v10 + 4];
          a3->wYear = word_18002F820[6 * v10 + 5];
          return v8;
        case 6u:
          v11 = 1;
          break;
        case 7u:
          goto LABEL_16;
        default:
          return v8;
      }
    }
    *(_QWORD *)&v13 = v9 | 0x100000000LL;
    *(_QWORD *)v16 = v13;
    *((_QWORD *)&v14 + 1) = 0x3B00000017LL;
    *(_DWORD *)&v16[16] = word_18002F820[36 * v4 + 6 * v11];
    *(_DWORD *)&v16[12] = word_18002F820[36 * v4 + 1 + 6 * v11];
    *(_DWORD *)&v16[8] = word_18002F820[36 * v4 + 2 + 6 * v11];
    LODWORD(v14) = word_18002F820[36 * v4 + 3 + 6 * v11];
    HIDWORD(v13) = word_18002F820[36 * v4 + 4 + 6 * v11];
    DWORD2(v13) = word_18002F820[36 * v4 + 5 + 6 * v11];
    v15 = 0x98967F0000003BLL;
    *(_OWORD *)&v16[24] = 0;
    UpdateCalendarDayOfWeek(v16);
    UpdateCalendarDayOfWeek(&v13);
    return (unsigned int)ConvertCalDateTimeToSystemTime(v16, a2)
        && (unsigned int)ConvertCalDateTimeToSystemTime(&v13, a3);
  }
  return result;
}

```

## disassembly

```asm
0x180017c50  push    rbp
0x180017c52  push    rbx
0x180017c53  push    rsi
0x180017c54  push    rdi
0x180017c55  push    r12
0x180017c57  push    r14
0x180017c59  push    r15
0x180017c5b  mov     rbp, rsp
0x180017c5e  sub     rsp, 80h
0x180017c65  mov     rax, cs:__security_cookie
0x180017c6c  xor     rax, rsp
0x180017c6f  mov     [rbp+var_8], rax
0x180017c73  xor     eax, eax
0x180017c75  mov     r15d, ecx
0x180017c78  mov     dword ptr [rbp+LCData], 0
0x180017c7f  xorps   xmm0, xmm0
0x180017c82  mov     [rbp+var_10], rax
0x180017c86  xorps   xmm1, xmm1
0x180017c89  mov     [rbp+var_38], rax
0x180017c8d  mov     rsi, r8
0x180017c90  mov     r14, rdx
0x180017c93  movups  [rbp+var_30], xmm0
0x180017c97  movups  [rbp+var_20], xmm0
0x180017c9b  movups  [rbp+var_58], xmm1
0x180017c9f  movups  [rbp+var_48], xmm1
0x180017ca3  test    rdx, rdx
0x180017ca6  jz      loc_180017EA4
0x180017cac  test    r8, r8
0x180017caf  jz      loc_180017EA4
0x180017cb5  lea     r12d, [rax+1]
0x180017cb9  cmp     r15d, r12d
0x180017cbc  ja      loc_180017EA4
0x180017cc2  lea     r9d, [rax+2]; cchData
0x180017cc6  mov     edx, 20001009h; LCType
0x180017ccb  lea     r8, [rbp+LCData]; lpLCData
0x180017ccf  mov     ecx, 400h; Locale
0x180017cd4  xor     ebx, ebx
0x180017cd6  xor     edi, edi
0x180017cd8  call    cs:__imp_GetLocaleInfoW
0x180017cde  test    eax, eax
0x180017ce0  jnz     short loc_180017CEB
0x180017ce2  mov     r8d, r12d
0x180017ce5  mov     dword ptr [rbp+LCData], r12d
0x180017ce9  jmp     short loc_180017CEF
0x180017ceb  mov     r8d, dword ptr [rbp+LCData]
0x180017cef  lea     r9, word_18002F820
0x180017cf6  cmp     r8d, 8
0x180017cfa  ja      loc_180017E5B
0x180017d00  jz      loc_180017E51
0x180017d06  mov     eax, r8d
0x180017d09  sub     eax, r12d
0x180017d0c  jz      short loc_180017D38
0x180017d0e  sub     eax, r12d
0x180017d11  jz      short loc_180017D38
0x180017d13  sub     eax, r12d
0x180017d16  jz      short loc_180017D38
0x180017d18  sub     eax, r12d
0x180017d1b  jz      loc_180017E47
0x180017d21  sub     eax, r12d
0x180017d24  jz      short loc_180017D38
0x180017d26  sub     eax, r12d
0x180017d29  jz      loc_180017E3F
0x180017d2f  cmp     eax, r12d
0x180017d32  jnz     loc_180017EA2
0x180017d38  mov     eax, ebx
0x180017d3a  lea     rcx, [r15+r15*2]
0x180017d3e  mov     edi, r12d
0x180017d41  lea     rcx, [rax+rcx*2]
0x180017d45  lea     rdx, [rcx+rcx*2]
0x180017d49  movzx   eax, word ptr [r9+rdx*4]
0x180017d4e  mov     [r14+6], ax
0x180017d53  movzx   eax, word ptr [r9+rdx*4+2]
0x180017d59  mov     [r14+2], ax
0x180017d5e  movzx   eax, word ptr [r9+rdx*4+4]
0x180017d64  mov     [r14], ax
0x180017d68  movzx   eax, word ptr [r9+rdx*4+6]
0x180017d6e  mov     [rsi+6], ax
0x180017d72  movzx   eax, word ptr [r9+rdx*4+8]
0x180017d78  mov     [rsi+2], ax
0x180017d7c  movzx   eax, word ptr [r9+rdx*4+0Ah]
0x180017d82  mov     [rsi], ax
0x180017d85  test    ebx, 0FFFFFFFBh
0x180017d8b  jz      loc_180017EA2
0x180017d91  mov     eax, ebx
0x180017d93  lea     rcx, [r15+r15*2]
0x180017d97  mov     dword ptr [rbp+var_58], r8d
0x180017d9b  xorps   xmm0, xmm0
0x180017d9e  mov     dword ptr [rbp+var_30], r8d
0x180017da2  mov     dword ptr [rbp+var_58+4], r12d
0x180017da6  lea     rcx, [rax+rcx*2]
0x180017daa  mov     dword ptr [rbp+var_30+4], r12d
0x180017dae  lea     r8, [rcx+rcx*2]
0x180017db2  mov     dword ptr [rbp+var_48+8], 17h
0x180017db9  movzx   eax, word ptr [r9+r8*4]
0x180017dbe  lea     rcx, [rbp+var_30]
0x180017dc2  mov     dword ptr [rbp+var_20], eax
0x180017dc5  movzx   eax, word ptr [r9+r8*4+2]
0x180017dcb  mov     dword ptr [rbp+var_30+0Ch], eax
0x180017dce  movzx   eax, word ptr [r9+r8*4+4]
0x180017dd4  mov     dword ptr [rbp+var_30+8], eax
0x180017dd7  movzx   eax, word ptr [r9+r8*4+6]
0x180017ddd  mov     dword ptr [rbp+var_48], eax
0x180017de0  movzx   eax, word ptr [r9+r8*4+8]
0x180017de6  mov     dword ptr [rbp+var_58+0Ch], eax
0x180017de9  movzx   eax, word ptr [r9+r8*4+0Ah]
0x180017def  mov     dword ptr [rbp+var_58+8], eax
0x180017df2  mov     eax, 3Bh ; ';'
0x180017df7  mov     dword ptr [rbp+var_48+0Ch], eax
0x180017dfa  mov     dword ptr [rbp+var_38], eax
0x180017dfd  movups  [rbp+var_20+8], xmm0
0x180017e01  mov     dword ptr [rbp+var_38+4], 98967Fh
0x180017e08  call    cs:__imp_UpdateCalendarDayOfWeek
0x180017e0e  lea     rcx, [rbp+var_58]
0x180017e12  call    cs:__imp_UpdateCalendarDayOfWeek
0x180017e18  mov     rdx, r14
0x180017e1b  lea     rcx, [rbp+var_30]
0x180017e1f  call    cs:__imp_ConvertCalDateTimeToSystemTime
0x180017e25  test    eax, eax
0x180017e27  jz      short loc_180017EA0
0x180017e29  mov     rdx, rsi
0x180017e2c  lea     rcx, [rbp+var_58]
0x180017e30  call    cs:__imp_ConvertCalDateTimeToSystemTime
0x180017e36  test    eax, eax
0x180017e38  jz      short loc_180017EA0
0x180017e3a  mov     edi, r12d
0x180017e3d  jmp     short loc_180017EA2
0x180017e3f  mov     ebx, r12d
0x180017e42  jmp     loc_180017D91
0x180017e47  mov     ebx, 4
0x180017e4c  jmp     loc_180017D38
0x180017e51  mov     ebx, 2
0x180017e56  jmp     loc_180017D91
0x180017e5b  mov     eax, r8d
0x180017e5e  sub     eax, 9
0x180017e61  jz      loc_180017D38
0x180017e67  sub     eax, r12d
0x180017e6a  jz      loc_180017D38
0x180017e70  sub     eax, r12d
0x180017e73  jz      loc_180017D38
0x180017e79  sub     eax, r12d
0x180017e7c  jz      loc_180017D38
0x180017e82  sub     eax, 0Ah
0x180017e85  jz      short loc_180017E96
0x180017e87  cmp     eax, r12d
0x180017e8a  jnz     short loc_180017EA2
0x180017e8c  mov     ebx, 3
0x180017e91  jmp     loc_180017D91
0x180017e96  mov     ebx, 5
0x180017e9b  jmp     loc_180017D91
0x180017ea0  xor     edi, edi
0x180017ea2  mov     eax, edi
0x180017ea4  mov     rcx, [rbp+var_8]
0x180017ea8  xor     rcx, rsp; StackCookie
0x180017eab  call    __security_check_cookie
0x180017eb0  add     rsp, 80h
0x180017eb7  pop     r15
0x180017eb9  pop     r14
0x180017ebb  pop     r12
0x180017ebd  pop     rdi
0x180017ebe  pop     rsi
0x180017ebf  pop     rbx
0x180017ec0  pop     rbp
0x180017ec1  retn
```
