# WcMungeDirectoryEntry

- ea: `0x140029010`
- end: `0x1400294ab`
- name: `WcMungeDirectoryEntry`
- size: `1179`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `reparse_path`

## callers

- `0x140028f24`
- `0x14002fe84`

## callees

- `0x140015a70`
- `0x140015dc4`
- `0x140016734`
- `0x140016aa8`
- `0x140016d68`
- `0x14001771c`
- `0x1400179f4`
- `0x140017ad0`
- `0x140029010`

## pseudocode

```c
__int64 __fastcall WcMungeDirectoryEntry(
        int a1,
        __int64 a2,
        char a3,
        char a4,
        int a5,
        unsigned int a6,
        unsigned int a7,
        __int64 a8,
        unsigned int a9,
        _DWORD *a10,
        char a11,
        _QWORD *a12,
        unsigned int *a13)
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
              return WcMungeDirectoryEnumerateWithShortnameFileId64(a2, a3, a8, a4, a5, a6, a10, a9, a11, a12, a13);
            }
          }
          else if ( a7 >= 0x50 && *(_DWORD *)(a8 + 60) < 0xFFFFFFB0 && a7 >= *(_DWORD *)(a8 + 60) + 80 )
          {
            return WcMungeDirectoryEnumerateWithoutShortnameFileId64(a2, a3, a8, a4, a5, a6, a10, a9, a11, a12, a13);
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
0x140029010  sub     rsp, 68h
0x140029014  mov     r11b, r8b
0x140029017  mov     r10d, edx
0x14002901a  sub     ecx, 0Ch
0x14002901d  jz      loc_140029434
0x140029023  sub     ecx, 15h
0x140029026  jz      loc_1400293EC
0x14002902c  sub     ecx, 1Bh
0x14002902f  jz      loc_140029356
0x140029035  sub     ecx, 3
0x140029038  jz      loc_1400292C0
0x14002903e  sub     ecx, 0Fh
0x140029041  jz      loc_14002922A
0x140029047  sub     ecx, 1
0x14002904a  jz      loc_140029194
0x140029050  sub     ecx, 1
0x140029053  jz      loc_1400290FE
0x140029059  cmp     ecx, 1
0x14002905c  jz      short loc_140029068
0x14002905e  mov     eax, 0C000000Dh
0x140029063  jmp     loc_1400294A5
0x140029068  cmp     [rsp+68h+arg_30], 7Ah ; 'z'
0x140029070  jb      loc_1400294A0
0x140029076  mov     r8, [rsp+68h+arg_38]
0x14002907e  mov     eax, [r8+3Ch]
0x140029082  add     eax, 7Ah ; 'z'
0x140029085  cmp     eax, 7Ah ; 'z'
0x140029088  jb      loc_1400294A0
0x14002908e  cmp     [rsp+68h+arg_30], eax
0x140029095  jb      loc_1400294A0
0x14002909b  mov     rax, [rsp+68h+arg_60]
0x1400290a3  mov     dl, r11b
0x1400290a6  mov     [rsp+68h+var_18], rax
0x1400290ab  mov     ecx, r10d
0x1400290ae  mov     rax, [rsp+68h+arg_58]
0x1400290b6  mov     [rsp+68h+var_20], rax
0x1400290bb  mov     al, [rsp+68h+arg_50]
0x1400290c2  mov     [rsp+68h+var_28], al
0x1400290c6  mov     eax, [rsp+68h+arg_40]
0x1400290cd  mov     dword ptr [rsp+68h+var_30], eax
0x1400290d1  mov     rax, [rsp+68h+arg_48]
0x1400290d9  mov     [rsp+68h+var_38], rax
0x1400290de  mov     eax, [rsp+68h+arg_28]
0x1400290e5  mov     dword ptr [rsp+68h+var_40], eax
0x1400290e9  mov     eax, [rsp+68h+arg_20]
0x1400290f0  mov     [rsp+68h+var_48], eax
0x1400290f4  call    WcMungeDirectoryEnumerateWithShortnameFileIdAll
0x1400290f9  jmp     loc_1400294A5
0x1400290fe  cmp     [rsp+68h+arg_30], 60h ; '`'
0x140029106  jb      loc_1400294A0
0x14002910c  mov     r8, [rsp+68h+arg_38]
0x140029114  mov     eax, [r8+3Ch]
0x140029118  add     eax, 60h ; '`'
0x14002911b  cmp     eax, 60h ; '`'
0x14002911e  jb      loc_1400294A0
0x140029124  cmp     [rsp+68h+arg_30], eax
0x14002912b  jb      loc_1400294A0
0x140029131  mov     rax, [rsp+68h+arg_60]
0x140029139  mov     dl, r11b
0x14002913c  mov     [rsp+68h+var_18], rax
0x140029141  mov     ecx, r10d
0x140029144  mov     rax, [rsp+68h+arg_58]
0x14002914c  mov     [rsp+68h+var_20], rax
0x140029151  mov     al, [rsp+68h+arg_50]
0x140029158  mov     [rsp+68h+var_28], al
0x14002915c  mov     eax, [rsp+68h+arg_40]
0x140029163  mov     dword ptr [rsp+68h+var_30], eax
0x140029167  mov     rax, [rsp+68h+arg_48]
0x14002916f  mov     [rsp+68h+var_38], rax
0x140029174  mov     eax, [rsp+68h+arg_28]
0x14002917b  mov     dword ptr [rsp+68h+var_40], eax
0x14002917f  mov     eax, [rsp+68h+arg_20]
0x140029186  mov     [rsp+68h+var_48], eax
0x14002918a  call    WcMungeDirectoryEnumerateWithoutShortnameFileIdAll
0x14002918f  jmp     loc_1400294A5
0x140029194  cmp     [rsp+68h+arg_30], 6Ah ; 'j'
0x14002919c  jb      loc_1400294A0
0x1400291a2  mov     r8, [rsp+68h+arg_38]
0x1400291aa  mov     eax, [r8+3Ch]
0x1400291ae  add     eax, 6Ah ; 'j'
0x1400291b1  cmp     eax, 6Ah ; 'j'
0x1400291b4  jb      loc_1400294A0
0x1400291ba  cmp     [rsp+68h+arg_30], eax
0x1400291c1  jb      loc_1400294A0
0x1400291c7  mov     rax, [rsp+68h+arg_60]
0x1400291cf  mov     dl, r11b
0x1400291d2  mov     [rsp+68h+var_18], rax
0x1400291d7  mov     ecx, r10d
0x1400291da  mov     rax, [rsp+68h+arg_58]
0x1400291e2  mov     [rsp+68h+var_20], rax
0x1400291e7  mov     al, [rsp+68h+arg_50]
0x1400291ee  mov     [rsp+68h+var_28], al
0x1400291f2  mov     eax, [rsp+68h+arg_40]
0x1400291f9  mov     dword ptr [rsp+68h+var_30], eax
0x1400291fd  mov     rax, [rsp+68h+arg_48]
0x140029205  mov     [rsp+68h+var_38], rax
0x14002920a  mov     eax, [rsp+68h+arg_28]
0x140029211  mov     dword ptr [rsp+68h+var_40], eax
0x140029215  mov     eax, [rsp+68h+arg_20]
0x14002921c  mov     [rsp+68h+var_48], eax
0x140029220  call    WcMungeDirectoryEnumerateWithShortnameFileId64
0x140029225  jmp     loc_1400294A5
0x14002922a  cmp     [rsp+68h+arg_30], 50h ; 'P'
0x140029232  jb      loc_1400294A0
0x140029238  mov     r8, [rsp+68h+arg_38]
0x140029240  mov     eax, [r8+3Ch]
0x140029244  add     eax, 50h ; 'P'
0x140029247  cmp     eax, 50h ; 'P'
0x14002924a  jb      loc_1400294A0
0x140029250  cmp     [rsp+68h+arg_30], eax
0x140029257  jb      loc_1400294A0
0x14002925d  mov     rax, [rsp+68h+arg_60]
0x140029265  mov     dl, r11b
0x140029268  mov     [rsp+68h+var_18], rax
0x14002926d  mov     ecx, r10d
0x140029270  mov     rax, [rsp+68h+arg_58]
0x140029278  mov     [rsp+68h+var_20], rax
0x14002927d  mov     al, [rsp+68h+arg_50]
0x140029284  mov     [rsp+68h+var_28], al
0x140029288  mov     eax, [rsp+68h+arg_40]
0x14002928f  mov     dword ptr [rsp+68h+var_30], eax
0x140029293  mov     rax, [rsp+68h+arg_48]
0x14002929b  mov     [rsp+68h+var_38], rax
0x1400292a0  mov     eax, [rsp+68h+arg_28]
0x1400292a7  mov     dword ptr [rsp+68h+var_40], eax
0x1400292ab  mov     eax, [rsp+68h+arg_20]
0x1400292b2  mov     [rsp+68h+var_48], eax
0x1400292b6  call    WcMungeDirectoryEnumerateWithoutShortnameFileId64
0x1400292bb  jmp     loc_1400294A5
0x1400292c0  cmp     [rsp+68h+arg_30], 72h ; 'r'
0x1400292c8  jb      loc_1400294A0
0x1400292ce  mov     r8, [rsp+68h+arg_38]
0x1400292d6  mov     eax, [r8+3Ch]
0x1400292da  add     eax, 72h ; 'r'
0x1400292dd  cmp     eax, 72h ; 'r'
0x1400292e0  jb      loc_1400294A0
0x1400292e6  cmp     [rsp+68h+arg_30], eax
0x1400292ed  jb      loc_1400294A0
0x1400292f3  mov     rax, [rsp+68h+arg_60]
0x1400292fb  mov     dl, r11b
0x1400292fe  mov     [rsp+68h+var_18], rax
0x140029303  mov     ecx, r10d
0x140029306  mov     rax, [rsp+68h+arg_58]
0x14002930e  mov     [rsp+68h+var_20], rax
0x140029313  mov     al, [rsp+68h+arg_50]
0x14002931a  mov     [rsp+68h+var_28], al
0x14002931e  mov     eax, [rsp+68h+arg_40]
0x140029325  mov     dword ptr [rsp+68h+var_30], eax
0x140029329  mov     rax, [rsp+68h+arg_48]
0x140029331  mov     [rsp+68h+var_38], rax
0x140029336  mov     eax, [rsp+68h+arg_28]
0x14002933d  mov     dword ptr [rsp+68h+var_40], eax
0x140029341  mov     eax, [rsp+68h+arg_20]
0x140029348  mov     [rsp+68h+var_48], eax
0x14002934c  call    WcMungeDirectoryEnumerateWithShortname
0x140029351  jmp     loc_1400294A5
0x140029356  cmp     [rsp+68h+arg_30], 58h ; 'X'
0x14002935e  jb      loc_1400294A0
0x140029364  mov     r8, [rsp+68h+arg_38]
0x14002936c  mov     eax, [r8+3Ch]
0x140029370  add     eax, 58h ; 'X'
0x140029373  cmp     eax, 58h ; 'X'
0x140029376  jb      loc_1400294A0
0x14002937c  cmp     [rsp+68h+arg_30], eax
0x140029383  jb      loc_1400294A0
0x140029389  mov     rax, [rsp+68h+arg_60]
0x140029391  mov     dl, r11b
0x140029394  mov     [rsp+68h+var_18], rax
0x140029399  mov     ecx, r10d
0x14002939c  mov     rax, [rsp+68h+arg_58]
0x1400293a4  mov     [rsp+68h+var_20], rax
0x1400293a9  mov     al, [rsp+68h+arg_50]
0x1400293b0  mov     [rsp+68h+var_28], al
0x1400293b4  mov     eax, [rsp+68h+arg_40]
0x1400293bb  mov     dword ptr [rsp+68h+var_30], eax
0x1400293bf  mov     rax, [rsp+68h+arg_48]
0x1400293c7  mov     [rsp+68h+var_38], rax
0x1400293cc  mov     eax, [rsp+68h+arg_28]
0x1400293d3  mov     dword ptr [rsp+68h+var_40], eax
0x1400293d7  mov     eax, [rsp+68h+arg_20]
0x1400293de  mov     [rsp+68h+var_48], eax
0x1400293e2  call    WcMungeDirectoryEnumerateWithoutShortname
0x1400293e7  jmp     loc_1400294A5
0x1400293ec  cmp     [rsp+68h+arg_30], 10h
0x1400293f4  jb      loc_1400294A0
0x1400293fa  mov     rax, [rsp+68h+arg_60]
0x140029402  mov     ecx, r10d
0x140029405  mov     r9d, [rsp+68h+arg_40]
0x14002940d  mov     r8, [rsp+68h+arg_48]
0x140029415  mov     rdx, [rsp+68h+arg_38]
0x14002941d  mov     [rsp+68h+var_40], rax
0x140029422  mov     al, [rsp+68h+arg_50]
0x140029429  mov     byte ptr [rsp+68h+var_48], al
0x14002942d  call    WcMungeReparseEnumerate
0x140029432  jmp     short loc_1400294A5
0x140029434  cmp     [rsp+68h+arg_30], 0Ch
0x14002943c  jb      short loc_1400294A0
0x14002943e  mov     r8, [rsp+68h+arg_38]
0x140029446  mov     eax, [r8+8]
0x14002944a  add     eax, 0Ch
0x14002944d  cmp     eax, 0Ch
0x140029450  jb      short loc_1400294A0
0x140029452  cmp     [rsp+68h+arg_30], eax
0x140029459  jb      short loc_1400294A0
0x14002945b  mov     rax, [rsp+68h+arg_60]
0x140029463  mov     dl, r11b
0x140029466  mov     r9, [rsp+68h+arg_48]
0x14002946e  mov     ecx, r10d
0x140029471  mov     [rsp+68h+var_30], rax
0x140029476  mov     rax, [rsp+68h+arg_58]
0x14002947e  mov     [rsp+68h+var_38], rax
0x140029483  mov     al, [rsp+68h+arg_50]
0x14002948a  mov     byte ptr [rsp+68h+var_40], al
0x14002948e  mov     eax, [rsp+68h+arg_40]
0x140029495  mov     [rsp+68h+var_48], eax
0x140029499  call    WcMungeNamesEnumerate
0x14002949e  jmp     short loc_1400294A5
0x1400294a0  mov     eax, 80000005h
0x1400294a5  add     rsp, 68h
0x1400294a9  retn
```
