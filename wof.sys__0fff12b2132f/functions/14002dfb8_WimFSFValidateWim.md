# WimFSFValidateWim

- ea: `0x14002dfb8`
- end: `0x14002e1ee`
- name: `WimFSFValidateWim`
- size: `566`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14002da2c`

## callees

- `0x14000d3b8`
- `0x14000fb60`
- `0x140010320`
- `0x1400105e8`
- `0x140011560`
- `0x14002dfb8`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x14002e029`
- `ntoskrnl!RtlCompareMemory` at `0x14002e029`
- `FLTMGR!FltQueryInformationFile` at `0x14002e009`
- `FLTMGR!FltQueryInformationFile` at `0x14002e009`

## pseudocode

```c
NTSTATUS __fastcall WimFSFValidateWim(struct _FLT_INSTANCE *a1, struct _FILE_OBJECT *a2, __int64 a3, _QWORD *a4)
{
  int v6; // ebx
  NTSTATUS result; // eax
  int v8; // edx
  int v9; // r8d
  __int64 v10; // r9
  PDEVICE_OBJECT v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // rcx
  __int128 v15; // [rsp+30h] [rbp-48h] BYREF
  __int64 v16; // [rsp+40h] [rbp-38h]
  __int64 Source2; // [rsp+48h] [rbp-30h] BYREF

  Source2 = 0x4D4957534DLL;
  v15 = 0;
  v6 = 0;
  v16 = 0;
  result = FltQueryInformationFile(a1, a2, &v15, 0x18u, FileStandardInformation, 0);
  if ( result >= 0 )
  {
    if ( RtlCompareMemory((const void *)a3, &Source2, 8u) != 8 )
    {
      v6 = -1073700187;
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        WPP_SF_s(WPP_GLOBAL_Control->AttachedDevice, 16, WPP_58aa16c06f40368a72f8e1151ea34c8a_Traceguids, a3);
      return v6;
    }
    v10 = *(unsigned int *)(a3 + 8);
    if ( (_DWORD)v10 == 208 )
    {
      v10 = *(unsigned int *)(a3 + 12);
      if ( (_DWORD)v10 == 68864 )
      {
        if ( (*(_BYTE *)(a3 + 16) & 0x38) != 0 )
        {
          if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 19, WPP_58aa16c06f40368a72f8e1151ea34c8a_Traceguids);
          return -1073741637;
        }
        else
        {
          if ( !a4 )
            goto LABEL_23;
          v13 = *(_QWORD *)(a3 + 24) - *a4;
          if ( !v13 )
            v13 = *(_QWORD *)(a3 + 32) - a4[1];
          if ( v13 )
          {
            v6 = -1073700187;
            if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
              WPP_SF__guid__guid_(WPP_GLOBAL_Control->AttachedDevice, v8, v9, a3 + 24, (__int64)a4);
          }
          else
          {
LABEL_23:
            v14 = *(_QWORD *)(a3 + 56);
            if ( v14 > *((__int64 *)&v15 + 1)
              || v14 + (*(_QWORD *)(a3 + 48) & 0xFFFFFFFFFFFFFFLL) > *((__int64 *)&v15 + 1) )
            {
              v6 = -1073700186;
              if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
                WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 21, WPP_58aa16c06f40368a72f8e1151ea34c8a_Traceguids);
            }
          }
        }
        return v6;
      }
      v6 = -1073700187;
      v11 = WPP_GLOBAL_Control;
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0 || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        return v6;
      v12 = 18;
    }
    else
    {
      v6 = -1073700187;
      v11 = WPP_GLOBAL_Control;
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0 || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        return v6;
      v12 = 17;
    }
    WPP_SF_d(v11->AttachedDevice, v12, WPP_58aa16c06f40368a72f8e1151ea34c8a_Traceguids, v10);
    return v6;
  }
  return result;
}

```

## disassembly

```asm
0x14002dfb8  mov     r11, rsp
0x14002dfbb  push    rbx
0x14002dfbc  push    rsi
0x14002dfbd  push    rdi
0x14002dfbe  sub     rsp, 60h
0x14002dfc2  mov     rax, cs:__security_cookie
0x14002dfc9  xor     rax, rsp
0x14002dfcc  mov     [rsp+78h+var_28], rax
0x14002dfd1  mov     rax, 4D4957534Dh
0x14002dfdb  xorps   xmm0, xmm0
0x14002dfde  mov     [r11-30h], rax
0x14002dfe2  mov     rsi, r9
0x14002dfe5  xor     eax, eax
0x14002dfe7  mov     rdi, r8
0x14002dfea  movups  [rsp+78h+var_48], xmm0
0x14002dfef  xor     ebx, ebx
0x14002dff1  mov     [r11-38h], rax
0x14002dff5  mov     [r11-50h], rbx
0x14002dff9  lea     r8, [r11-48h]; FileInformation
0x14002dffd  lea     r9d, [rax+18h]; Length
0x14002e001  mov     [rsp+78h+FileInformationClass], 5; FileInformationClass
0x14002e009  call    cs:__imp_FltQueryInformationFile
0x14002e010  nop     dword ptr [rax+rax+00h]
0x14002e015  test    eax, eax
0x14002e017  js      loc_14002E1D8
0x14002e01d  lea     r8d, [rbx+8]; Length
0x14002e021  mov     rcx, rdi; Source1
0x14002e024  lea     rdx, [rsp+78h+Source2]; Source2
0x14002e029  call    cs:__imp_RtlCompareMemory
0x14002e030  nop     dword ptr [rax+rax+00h]
0x14002e035  cmp     rax, 8
0x14002e039  jz      short loc_14002E079
0x14002e03b  mov     ebx, 0C000A2A5h
0x14002e040  mov     rcx, cs:WPP_GLOBAL_Control
0x14002e047  mov     eax, [rcx+2Ch]
0x14002e04a  test    al, 8
0x14002e04c  jz      loc_14002E1D6
0x14002e052  cmp     byte ptr [rcx+29h], 2
0x14002e056  jb      loc_14002E1D6
0x14002e05c  mov     rcx, [rcx+18h]
0x14002e060  lea     r8, WPP_58aa16c06f40368a72f8e1151ea34c8a_Traceguids
0x14002e067  mov     edx, 10h
0x14002e06c  mov     r9, rdi
0x14002e06f  call    WPP_SF_s
0x14002e074  jmp     loc_14002E1D6
0x14002e079  mov     r9d, [rdi+8]
0x14002e07d  cmp     r9d, 0D0h
0x14002e084  jz      short loc_14002E0AE
0x14002e086  mov     ebx, 0C000A2A5h
0x14002e08b  mov     rcx, cs:WPP_GLOBAL_Control
0x14002e092  mov     eax, [rcx+2Ch]
0x14002e095  test    al, 8
0x14002e097  jz      loc_14002E1D6
0x14002e09d  cmp     byte ptr [rcx+29h], 2
0x14002e0a1  jb      loc_14002E1D6
0x14002e0a7  mov     edx, 11h
0x14002e0ac  jmp     short loc_14002E0E1
0x14002e0ae  mov     r9d, [rdi+0Ch]
0x14002e0b2  cmp     r9d, 10D00h
0x14002e0b9  jz      short loc_14002E0F6
0x14002e0bb  mov     ebx, 0C000A2A5h
0x14002e0c0  mov     rcx, cs:WPP_GLOBAL_Control
0x14002e0c7  mov     eax, [rcx+2Ch]
0x14002e0ca  test    al, 8
0x14002e0cc  jz      loc_14002E1D6
0x14002e0d2  cmp     byte ptr [rcx+29h], 2
0x14002e0d6  jb      loc_14002E1D6
0x14002e0dc  mov     edx, 12h
0x14002e0e1  mov     rcx, [rcx+18h]
0x14002e0e5  lea     r8, WPP_58aa16c06f40368a72f8e1151ea34c8a_Traceguids
0x14002e0ec  call    WPP_SF_d
0x14002e0f1  jmp     loc_14002E1D6
0x14002e0f6  test    byte ptr [rdi+10h], 38h
0x14002e0fa  jnz     loc_14002E1A8
0x14002e100  test    rsi, rsi
0x14002e103  jz      short loc_14002E152
0x14002e105  lea     r9, [rdi+18h]
0x14002e109  mov     rcx, [r9]
0x14002e10c  sub     rcx, [rsi]
0x14002e10f  jnz     short loc_14002E119
0x14002e111  mov     rcx, [r9+8]
0x14002e115  sub     rcx, [rsi+8]
0x14002e119  test    rcx, rcx
0x14002e11c  jz      short loc_14002E152
0x14002e11e  mov     ebx, 0C000A2A5h
0x14002e123  mov     rcx, cs:WPP_GLOBAL_Control
0x14002e12a  mov     eax, [rcx+2Ch]
0x14002e12d  test    al, 8
0x14002e12f  jz      loc_14002E1D6
0x14002e135  cmp     byte ptr [rcx+29h], 2
0x14002e139  jb      loc_14002E1D6
0x14002e13f  mov     rcx, [rcx+18h]
0x14002e143  mov     qword ptr [rsp+78h+FileInformationClass], rsi
0x14002e148  call    WPP_SF__guid__guid_
0x14002e14d  jmp     loc_14002E1D6
0x14002e152  mov     rcx, [rdi+38h]
0x14002e156  cmp     rcx, qword ptr [rsp+78h+var_48+8]
0x14002e15b  jg      short loc_14002E178
0x14002e15d  mov     rax, [rdi+30h]
0x14002e161  mov     rdx, 0FFFFFFFFFFFFFFh
0x14002e16b  and     rax, rdx
0x14002e16e  add     rax, rcx
0x14002e171  cmp     rax, qword ptr [rsp+78h+var_48+8]
0x14002e176  jle     short loc_14002E1D6
0x14002e178  mov     ebx, 0C000A2A6h
0x14002e17d  mov     rcx, cs:WPP_GLOBAL_Control
0x14002e184  mov     eax, [rcx+2Ch]
0x14002e187  test    al, 8
0x14002e189  jz      short loc_14002E1D6
0x14002e18b  cmp     byte ptr [rcx+29h], 2
0x14002e18f  jb      short loc_14002E1D6
0x14002e191  mov     rcx, [rcx+18h]
0x14002e195  lea     r8, WPP_58aa16c06f40368a72f8e1151ea34c8a_Traceguids
0x14002e19c  mov     edx, 15h
0x14002e1a1  call    WPP_SF_
0x14002e1a6  jmp     short loc_14002E1D6
0x14002e1a8  mov     rcx, cs:WPP_GLOBAL_Control
0x14002e1af  mov     eax, [rcx+2Ch]
0x14002e1b2  test    al, 8
0x14002e1b4  jz      short loc_14002E1D1
0x14002e1b6  cmp     byte ptr [rcx+29h], 2
0x14002e1ba  jb      short loc_14002E1D1
0x14002e1bc  mov     rcx, [rcx+18h]
0x14002e1c0  lea     r8, WPP_58aa16c06f40368a72f8e1151ea34c8a_Traceguids
0x14002e1c7  mov     edx, 13h
0x14002e1cc  call    WPP_SF_
0x14002e1d1  mov     ebx, 0C00000BBh
0x14002e1d6  mov     eax, ebx
0x14002e1d8  mov     rcx, [rsp+78h+var_28]
0x14002e1dd  xor     rcx, rsp; StackCookie
0x14002e1e0  call    __security_check_cookie
0x14002e1e5  add     rsp, 60h
0x14002e1e9  pop     rdi
0x14002e1ea  pop     rsi
0x14002e1eb  pop     rbx
0x14002e1ec  retn
```
