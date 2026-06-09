# WcMungeDirectoryEntry

- ea: `0x140029060`
- end: `0x1400294fb`
- name: `WcMungeDirectoryEntry`
- size: `1179`
- prototype: `__int64 __fastcall(int, __int64, char, __int64, int, int, unsigned int, __int64, unsigned int, __int64, char, __int64, __int64)`
- caller_count: `2`
- callee_count: `9`
- tags: `reparse_path`

## callers

- `0x140028f74`
- `0x14002fed4`

## callees

- `0x140015a70`
- `0x140015dc4`
- `0x140016734`
- `0x140016aa8`
- `0x140016d68`
- `0x14001771c`
- `0x1400179f4`
- `0x140017ad0`
- `0x140029060`

## pseudocode

```c
__int64 __fastcall WcMungeDirectoryEntry(
        int a1,
        __int64 a2,
        char a3,
        __int64 a4,
        int a5,
        int a6,
        unsigned int a7,
        __int64 a8,
        unsigned int a9,
        __int64 a10,
        char a11,
        __int64 a12,
        __int64 a13)
{
  unsigned int v13; // r10d
  int v14; // ecx
  int v15; // ecx
  int v16; // ecx
  int v17; // ecx
  int v18; // ecx
  int v19; // ecx
  int v20; // ecx

  v13 = a2;
  v14 = a1 - 12;
  if ( v14 )
  {
    v15 = v14 - 21;
    if ( v15 )
    {
      v16 = v15 - 27;
      if ( v16 )
      {
        v17 = v16 - 3;
        if ( v17 )
        {
          v18 = v17 - 15;
          if ( v18 )
          {
            v19 = v18 - 1;
            if ( v19 )
            {
              v20 = v19 - 1;
              if ( v20 )
              {
                if ( v20 != 1 )
                  return 3221225485LL;
                if ( a7 >= 0x7A && *(_DWORD *)(a8 + 60) < 0xFFFFFF86 && a7 >= *(_DWORD *)(a8 + 60) + 122 )
                {
                  LOBYTE(a2) = a3;
                  return WcMungeDirectoryEnumerateWithShortnameFileIdAll(v13, a2);
                }
              }
              else if ( a7 >= 0x60 && *(_DWORD *)(a8 + 60) < 0xFFFFFFA0 && a7 >= *(_DWORD *)(a8 + 60) + 96 )
              {
                LOBYTE(a2) = a3;
                return WcMungeDirectoryEnumerateWithoutShortnameFileIdAll(v13, a2);
              }
            }
            else if ( a7 >= 0x6A && *(_DWORD *)(a8 + 60) < 0xFFFFFF96 && a7 >= *(_DWORD *)(a8 + 60) + 106 )
            {
              LOBYTE(a2) = a3;
              return WcMungeDirectoryEnumerateWithShortnameFileId64(v13, a2);
            }
          }
          else if ( a7 >= 0x50 && *(_DWORD *)(a8 + 60) < 0xFFFFFFB0 && a7 >= *(_DWORD *)(a8 + 60) + 80 )
          {
            LOBYTE(a2) = a3;
            return WcMungeDirectoryEnumerateWithoutShortnameFileId64(v13, a2);
          }
        }
        else if ( a7 >= 0x72 && *(_DWORD *)(a8 + 60) < 0xFFFFFF8E && a7 >= *(_DWORD *)(a8 + 60) + 114 )
        {
          LOBYTE(a2) = a3;
          return WcMungeDirectoryEnumerateWithShortname(v13, a2);
        }
      }
      else if ( a7 >= 0x58 && *(_DWORD *)(a8 + 60) < 0xFFFFFFA8 && a7 >= *(_DWORD *)(a8 + 60) + 88 )
      {
        LOBYTE(a2) = a3;
        return WcMungeDirectoryEnumerateWithoutShortname(v13, a2);
      }
    }
    else if ( a7 >= 0x10 )
    {
      return WcMungeReparseEnumerate((unsigned int)a2, a8, a10, a9, a11, a13);
    }
  }
  else if ( a7 >= 0xC && *(_DWORD *)(a8 + 8) < 0xFFFFFFF4 && a7 >= *(_DWORD *)(a8 + 8) + 12 )
  {
    LOBYTE(a2) = a3;
    return WcMungeNamesEnumerate(v13, a2, a8, a10, a9, a11, a12, a13);
  }
  return 2147483653LL;
}

```

## disassembly

```asm
0x140029060  sub     rsp, 68h
0x140029064  mov     r11b, r8b
0x140029067  mov     r10d, edx
0x14002906a  sub     ecx, 0Ch
0x14002906d  jz      loc_140029484
0x140029073  sub     ecx, 15h
0x140029076  jz      loc_14002943C
0x14002907c  sub     ecx, 1Bh
0x14002907f  jz      loc_1400293A6
0x140029085  sub     ecx, 3
0x140029088  jz      loc_140029310
0x14002908e  sub     ecx, 0Fh
0x140029091  jz      loc_14002927A
0x140029097  sub     ecx, 1
0x14002909a  jz      loc_1400291E4
0x1400290a0  sub     ecx, 1
0x1400290a3  jz      loc_14002914E
0x1400290a9  cmp     ecx, 1
0x1400290ac  jz      short loc_1400290B8
0x1400290ae  mov     eax, 0C000000Dh
0x1400290b3  jmp     loc_1400294F5
0x1400290b8  cmp     [rsp+68h+arg_30], 7Ah ; 'z'
0x1400290c0  jb      loc_1400294F0
0x1400290c6  mov     r8, [rsp+68h+arg_38]
0x1400290ce  mov     eax, [r8+3Ch]
0x1400290d2  add     eax, 7Ah ; 'z'
0x1400290d5  cmp     eax, 7Ah ; 'z'
0x1400290d8  jb      loc_1400294F0
0x1400290de  cmp     [rsp+68h+arg_30], eax
0x1400290e5  jb      loc_1400294F0
0x1400290eb  mov     rax, [rsp+68h+arg_60]
0x1400290f3  mov     dl, r11b
0x1400290f6  mov     [rsp+68h+var_18], rax
0x1400290fb  mov     ecx, r10d
0x1400290fe  mov     rax, [rsp+68h+arg_58]
0x140029106  mov     [rsp+68h+var_20], rax
0x14002910b  mov     al, [rsp+68h+arg_50]
0x140029112  mov     [rsp+68h+var_28], al
0x140029116  mov     eax, [rsp+68h+arg_40]
0x14002911d  mov     dword ptr [rsp+68h+var_30], eax
0x140029121  mov     rax, [rsp+68h+arg_48]
0x140029129  mov     [rsp+68h+var_38], rax
0x14002912e  mov     eax, [rsp+68h+arg_28]
0x140029135  mov     dword ptr [rsp+68h+var_40], eax
0x140029139  mov     eax, [rsp+68h+arg_20]
0x140029140  mov     [rsp+68h+var_48], eax
0x140029144  call    WcMungeDirectoryEnumerateWithShortnameFileIdAll
0x140029149  jmp     loc_1400294F5
0x14002914e  cmp     [rsp+68h+arg_30], 60h ; '`'
0x140029156  jb      loc_1400294F0
0x14002915c  mov     r8, [rsp+68h+arg_38]
0x140029164  mov     eax, [r8+3Ch]
0x140029168  add     eax, 60h ; '`'
0x14002916b  cmp     eax, 60h ; '`'
0x14002916e  jb      loc_1400294F0
0x140029174  cmp     [rsp+68h+arg_30], eax
0x14002917b  jb      loc_1400294F0
0x140029181  mov     rax, [rsp+68h+arg_60]
0x140029189  mov     dl, r11b
0x14002918c  mov     [rsp+68h+var_18], rax
0x140029191  mov     ecx, r10d
0x140029194  mov     rax, [rsp+68h+arg_58]
0x14002919c  mov     [rsp+68h+var_20], rax
0x1400291a1  mov     al, [rsp+68h+arg_50]
0x1400291a8  mov     [rsp+68h+var_28], al
0x1400291ac  mov     eax, [rsp+68h+arg_40]
0x1400291b3  mov     dword ptr [rsp+68h+var_30], eax
0x1400291b7  mov     rax, [rsp+68h+arg_48]
0x1400291bf  mov     [rsp+68h+var_38], rax
0x1400291c4  mov     eax, [rsp+68h+arg_28]
0x1400291cb  mov     dword ptr [rsp+68h+var_40], eax
0x1400291cf  mov     eax, [rsp+68h+arg_20]
0x1400291d6  mov     [rsp+68h+var_48], eax
0x1400291da  call    WcMungeDirectoryEnumerateWithoutShortnameFileIdAll
0x1400291df  jmp     loc_1400294F5
0x1400291e4  cmp     [rsp+68h+arg_30], 6Ah ; 'j'
0x1400291ec  jb      loc_1400294F0
0x1400291f2  mov     r8, [rsp+68h+arg_38]
0x1400291fa  mov     eax, [r8+3Ch]
0x1400291fe  add     eax, 6Ah ; 'j'
0x140029201  cmp     eax, 6Ah ; 'j'
0x140029204  jb      loc_1400294F0
0x14002920a  cmp     [rsp+68h+arg_30], eax
0x140029211  jb      loc_1400294F0
0x140029217  mov     rax, [rsp+68h+arg_60]
0x14002921f  mov     dl, r11b
0x140029222  mov     [rsp+68h+var_18], rax
0x140029227  mov     ecx, r10d
0x14002922a  mov     rax, [rsp+68h+arg_58]
0x140029232  mov     [rsp+68h+var_20], rax
0x140029237  mov     al, [rsp+68h+arg_50]
0x14002923e  mov     [rsp+68h+var_28], al
0x140029242  mov     eax, [rsp+68h+arg_40]
0x140029249  mov     dword ptr [rsp+68h+var_30], eax
0x14002924d  mov     rax, [rsp+68h+arg_48]
0x140029255  mov     [rsp+68h+var_38], rax
0x14002925a  mov     eax, [rsp+68h+arg_28]
0x140029261  mov     dword ptr [rsp+68h+var_40], eax
0x140029265  mov     eax, [rsp+68h+arg_20]
0x14002926c  mov     [rsp+68h+var_48], eax
0x140029270  call    WcMungeDirectoryEnumerateWithShortnameFileId64
0x140029275  jmp     loc_1400294F5
0x14002927a  cmp     [rsp+68h+arg_30], 50h ; 'P'
0x140029282  jb      loc_1400294F0
0x140029288  mov     r8, [rsp+68h+arg_38]
0x140029290  mov     eax, [r8+3Ch]
0x140029294  add     eax, 50h ; 'P'
0x140029297  cmp     eax, 50h ; 'P'
0x14002929a  jb      loc_1400294F0
0x1400292a0  cmp     [rsp+68h+arg_30], eax
0x1400292a7  jb      loc_1400294F0
0x1400292ad  mov     rax, [rsp+68h+arg_60]
0x1400292b5  mov     dl, r11b
0x1400292b8  mov     [rsp+68h+var_18], rax
0x1400292bd  mov     ecx, r10d
0x1400292c0  mov     rax, [rsp+68h+arg_58]
0x1400292c8  mov     [rsp+68h+var_20], rax
0x1400292cd  mov     al, [rsp+68h+arg_50]
0x1400292d4  mov     [rsp+68h+var_28], al
0x1400292d8  mov     eax, [rsp+68h+arg_40]
0x1400292df  mov     dword ptr [rsp+68h+var_30], eax
0x1400292e3  mov     rax, [rsp+68h+arg_48]
0x1400292eb  mov     [rsp+68h+var_38], rax
0x1400292f0  mov     eax, [rsp+68h+arg_28]
0x1400292f7  mov     dword ptr [rsp+68h+var_40], eax
0x1400292fb  mov     eax, [rsp+68h+arg_20]
0x140029302  mov     [rsp+68h+var_48], eax
0x140029306  call    WcMungeDirectoryEnumerateWithoutShortnameFileId64
0x14002930b  jmp     loc_1400294F5
0x140029310  cmp     [rsp+68h+arg_30], 72h ; 'r'
0x140029318  jb      loc_1400294F0
0x14002931e  mov     r8, [rsp+68h+arg_38]
0x140029326  mov     eax, [r8+3Ch]
0x14002932a  add     eax, 72h ; 'r'
0x14002932d  cmp     eax, 72h ; 'r'
0x140029330  jb      loc_1400294F0
0x140029336  cmp     [rsp+68h+arg_30], eax
0x14002933d  jb      loc_1400294F0
0x140029343  mov     rax, [rsp+68h+arg_60]
0x14002934b  mov     dl, r11b
0x14002934e  mov     [rsp+68h+var_18], rax
0x140029353  mov     ecx, r10d
0x140029356  mov     rax, [rsp+68h+arg_58]
0x14002935e  mov     [rsp+68h+var_20], rax
0x140029363  mov     al, [rsp+68h+arg_50]
0x14002936a  mov     [rsp+68h+var_28], al
0x14002936e  mov     eax, [rsp+68h+arg_40]
0x140029375  mov     dword ptr [rsp+68h+var_30], eax
0x140029379  mov     rax, [rsp+68h+arg_48]
0x140029381  mov     [rsp+68h+var_38], rax
0x140029386  mov     eax, [rsp+68h+arg_28]
0x14002938d  mov     dword ptr [rsp+68h+var_40], eax
0x140029391  mov     eax, [rsp+68h+arg_20]
0x140029398  mov     [rsp+68h+var_48], eax
0x14002939c  call    WcMungeDirectoryEnumerateWithShortname
0x1400293a1  jmp     loc_1400294F5
0x1400293a6  cmp     [rsp+68h+arg_30], 58h ; 'X'
0x1400293ae  jb      loc_1400294F0
0x1400293b4  mov     r8, [rsp+68h+arg_38]
0x1400293bc  mov     eax, [r8+3Ch]
0x1400293c0  add     eax, 58h ; 'X'
0x1400293c3  cmp     eax, 58h ; 'X'
0x1400293c6  jb      loc_1400294F0
0x1400293cc  cmp     [rsp+68h+arg_30], eax
0x1400293d3  jb      loc_1400294F0
0x1400293d9  mov     rax, [rsp+68h+arg_60]
0x1400293e1  mov     dl, r11b
0x1400293e4  mov     [rsp+68h+var_18], rax
0x1400293e9  mov     ecx, r10d
0x1400293ec  mov     rax, [rsp+68h+arg_58]
0x1400293f4  mov     [rsp+68h+var_20], rax
0x1400293f9  mov     al, [rsp+68h+arg_50]
0x140029400  mov     [rsp+68h+var_28], al
0x140029404  mov     eax, [rsp+68h+arg_40]
0x14002940b  mov     dword ptr [rsp+68h+var_30], eax
0x14002940f  mov     rax, [rsp+68h+arg_48]
0x140029417  mov     [rsp+68h+var_38], rax
0x14002941c  mov     eax, [rsp+68h+arg_28]
0x140029423  mov     dword ptr [rsp+68h+var_40], eax
0x140029427  mov     eax, [rsp+68h+arg_20]
0x14002942e  mov     [rsp+68h+var_48], eax
0x140029432  call    WcMungeDirectoryEnumerateWithoutShortname
0x140029437  jmp     loc_1400294F5
0x14002943c  cmp     [rsp+68h+arg_30], 10h
0x140029444  jb      loc_1400294F0
0x14002944a  mov     rax, [rsp+68h+arg_60]
0x140029452  mov     ecx, r10d
0x140029455  mov     r9d, [rsp+68h+arg_40]
0x14002945d  mov     r8, [rsp+68h+arg_48]
0x140029465  mov     rdx, [rsp+68h+arg_38]
0x14002946d  mov     [rsp+68h+var_40], rax
0x140029472  mov     al, [rsp+68h+arg_50]
0x140029479  mov     byte ptr [rsp+68h+var_48], al
0x14002947d  call    WcMungeReparseEnumerate
0x140029482  jmp     short loc_1400294F5
0x140029484  cmp     [rsp+68h+arg_30], 0Ch
0x14002948c  jb      short loc_1400294F0
0x14002948e  mov     r8, [rsp+68h+arg_38]
0x140029496  mov     eax, [r8+8]
0x14002949a  add     eax, 0Ch
0x14002949d  cmp     eax, 0Ch
0x1400294a0  jb      short loc_1400294F0
0x1400294a2  cmp     [rsp+68h+arg_30], eax
0x1400294a9  jb      short loc_1400294F0
0x1400294ab  mov     rax, [rsp+68h+arg_60]
0x1400294b3  mov     dl, r11b
0x1400294b6  mov     r9, [rsp+68h+arg_48]
0x1400294be  mov     ecx, r10d
0x1400294c1  mov     [rsp+68h+var_30], rax
0x1400294c6  mov     rax, [rsp+68h+arg_58]
0x1400294ce  mov     [rsp+68h+var_38], rax
0x1400294d3  mov     al, [rsp+68h+arg_50]
0x1400294da  mov     byte ptr [rsp+68h+var_40], al
0x1400294de  mov     eax, [rsp+68h+arg_40]
0x1400294e5  mov     [rsp+68h+var_48], eax
0x1400294e9  call    WcMungeNamesEnumerate
0x1400294ee  jmp     short loc_1400294F5
0x1400294f0  mov     eax, 80000005h
0x1400294f5  add     rsp, 68h
0x1400294f9  retn
```
