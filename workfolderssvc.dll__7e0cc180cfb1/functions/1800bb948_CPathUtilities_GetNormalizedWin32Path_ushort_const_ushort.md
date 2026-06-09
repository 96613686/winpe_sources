# CPathUtilities::GetNormalizedWin32Path(ushort const *,ushort * *)

- ea: `0x1800bb948`
- end: `0x1800bbb88`
- name: `?GetNormalizedWin32Path@CPathUtilities@@SAJPEBGPEAPEAG@Z`
- size: `576`
- prototype: `__int64 __fastcall(PWSTR FileName, unsigned __int16 **)`
- caller_count: `19`
- callee_count: `7`
- tags: `reparse_path, loader_planting`

## callers

- `0x18008ac38`
- `0x18008bb6c`
- `0x180090c88`
- `0x1800950b4`
- `0x18009ff30`
- `0x1800be950`
- `0x1800beee0`
- `0x1800bf9d0`
- `0x1800c01f0`
- `0x1800c0570`
- `0x1800c0760`
- `0x1800c096c`
- `0x1800c0e30`
- `0x1800c2d2c`
- `0x1800c47f0`
- `0x18010afdc`
- `0x18010b520`
- `0x18010e248`
- `0x18010fd2c`

## callees

- `0x180006f5c`
- `0x180007e10`
- `0x180008080`
- `0x180011314`
- `0x180058d88`
- `0x18008b634`
- `0x1800bb948`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800bba17`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800bba35`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800bba8b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800bba17`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800bba35`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800bba8b`
- `ntdll!RtlGetFullPathName_UEx` at `0x1800bbae7`
- `ntdll!RtlGetFullPathName_UEx` at `0x1800bbae7`

## string_xrefs

- `0x1800bb9c4`: `CPathUtilities::GetNormalizedWin32Path`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CPathUtilities::GetNormalizedWin32Path(PWSTR FileName, unsigned __int16 **a2)
{
  _BYTE *v4; // rax
  char v5; // cl
  __int16 v6; // ax
  __int64 v7; // rdi
  __int64 v8; // r14
  unsigned __int64 v9; // r14
  int v10; // ebx
  unsigned __int16 *v11; // r8
  unsigned int FullPathName_UEx; // eax
  unsigned __int16 *v13; // rcx
  int v15; // [rsp+30h] [rbp-20h] BYREF
  int v16; // [rsp+34h] [rbp-1Ch]
  char v17; // [rsp+38h] [rbp-18h]
  const char *v18; // [rsp+40h] [rbp-10h]
  __int64 v19; // [rsp+48h] [rbp-8h]
  RTL_PATH_TYPE InputPathType; // [rsp+80h] [rbp+30h] BYREF
  unsigned __int16 *v21; // [rsp+88h] [rbp+38h] BYREF

  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x20) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 14, WPP_0e035964b16e3dba2f65f7eff446a590_Traceguids);
    v4 = WPP_GLOBAL_Control;
  }
  if ( (v4[68] & 0x20) == 0 || (v5 = 1, v4[65] < 6u) )
    v5 = 0;
  v15 = 0;
  v16 = 329;
  v17 = v5;
  v18 = "CPathUtilities::GetNormalizedWin32Path";
  v19 = 0;
  v21 = 0;
  if ( a2 )
    *a2 = 0;
  v6 = 340;
  if ( !FileName )
    goto LABEL_30;
  LOWORD(v16) = 340;
  v6 = 341;
  if ( !a2 )
    goto LABEL_30;
  v15 = 0;
  LOWORD(v16) = 341;
  if ( !(unsigned int)_o__wcsnicmp(FileName, L"\\??\\", 4) || !(unsigned int)_o__wcsnicmp(FileName, L"\\device\\", 8) )
  {
    v6 = 347;
LABEL_30:
    v10 = -2147024809;
    goto LABEL_31;
  }
  v7 = -1;
  v8 = -1;
  do
    ++v8;
  while ( FileName[v8] );
  v9 = v8 + 5;
  v10 = CEcsMemPtr<unsigned short,0>::AllocBytes((void **)&v21, 2 * v9);
  v15 = v10;
  v6 = 356;
  if ( v10 < 0 )
    goto LABEL_32;
  LOWORD(v16) = 356;
  if ( (unsigned int)_o__wcsnicmp(FileName, L"\\\\?\\", 4) )
  {
    v10 = StringCchCopyW(v21, v9, L"\\\\?\\");
    v15 = v10;
    v6 = 369;
    if ( v10 < 0 )
    {
LABEL_32:
      HIWORD(v16) = v6;
      goto LABEL_33;
    }
    LOWORD(v16) = 369;
    v11 = v21 + 4;
    v9 -= 4LL;
  }
  else
  {
    v11 = v21;
  }
  InputPathType = RtlPathTypeUnknown;
  FullPathName_UEx = RtlGetFullPathName_UEx(FileName, 2 * v9, v11, 0, &InputPathType);
  v10 = HRESULTFromNTSTATUS(FullPathName_UEx);
  v15 = v10;
  v6 = 381;
  if ( v10 < 0 )
    goto LABEL_32;
  LOWORD(v16) = 381;
  if ( (unsigned int)InputPathType > 2 * v9 )
  {
    v10 = -2147024774;
    v6 = 386;
LABEL_31:
    v15 = v10;
    goto LABEL_32;
  }
  v13 = v21;
  do
    ++v7;
  while ( v21[v7] );
  if ( v21[v7 - 1] == 92 )
  {
    v21[v7 - 1] = 0;
    v10 = v15;
    v13 = v21;
  }
  v21 = 0;
  *a2 = v13;
LABEL_33:
  CEcsMemPtr<unsigned short,0>::~CEcsMemPtr<unsigned short,0>(&v21);
  CEcsFunctionTracer::~CEcsFunctionTracer((CEcsFunctionTracer *)&v15);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800bb948  mov     [rsp-28h+arg_10], rbx
0x1800bb94d  mov     [rsp-28h+arg_18], rsi
0x1800bb952  push    rbp
0x1800bb953  push    rdi
0x1800bb954  push    r12
0x1800bb956  push    r14
0x1800bb958  push    r15
0x1800bb95a  mov     rbp, rsp
0x1800bb95d  sub     rsp, 50h
0x1800bb961  mov     r15, rdx
0x1800bb964  mov     rsi, rcx
0x1800bb967  lea     rcx, WPP_GLOBAL_Control
0x1800bb96e  mov     rax, cs:WPP_GLOBAL_Control
0x1800bb975  cmp     rax, rcx
0x1800bb978  jz      short loc_1800BB9A2
0x1800bb97a  test    byte ptr [rax+44h], 20h
0x1800bb97e  jz      short loc_1800BB9A2
0x1800bb980  cmp     byte ptr [rax+41h], 6
0x1800bb984  jb      short loc_1800BB9A2
0x1800bb986  mov     edx, 0Eh
0x1800bb98b  lea     r8, WPP_0e035964b16e3dba2f65f7eff446a590_Traceguids
0x1800bb992  mov     rcx, [rax+38h]
0x1800bb996  call    WPP_SF_
0x1800bb99b  mov     rax, cs:WPP_GLOBAL_Control
0x1800bb9a2  xor     r12d, r12d
0x1800bb9a5  test    byte ptr [rax+44h], 20h
0x1800bb9a9  jz      short loc_1800BB9B3
0x1800bb9ab  cmp     byte ptr [rax+41h], 6
0x1800bb9af  mov     cl, 1
0x1800bb9b1  jnb     short loc_1800BB9B6
0x1800bb9b3  mov     cl, r12b
0x1800bb9b6  mov     [rbp+var_20], r12d
0x1800bb9ba  mov     [rbp+var_1C], 149h
0x1800bb9c1  mov     [rbp+var_18], cl
0x1800bb9c4  lea     rax, aCpathutilities_3; "CPathUtilities::GetNormalizedWin32Path"
0x1800bb9cb  mov     [rbp+var_10], rax
0x1800bb9cf  mov     [rbp+var_8], r12
0x1800bb9d3  mov     [rbp+arg_8], r12
0x1800bb9d7  test    r15, r15
0x1800bb9da  jz      short loc_1800BB9DF
0x1800bb9dc  mov     [r15], r12
0x1800bb9df  mov     eax, 154h
0x1800bb9e4  test    rsi, rsi
0x1800bb9e7  jz      loc_1800BBB4F
0x1800bb9ed  mov     word ptr [rbp+var_1C], ax
0x1800bb9f1  mov     eax, 155h
0x1800bb9f6  test    r15, r15
0x1800bb9f9  jz      loc_1800BBB4F
0x1800bb9ff  mov     [rbp+var_20], r12d
0x1800bba03  mov     word ptr [rbp+var_1C], ax
0x1800bba07  mov     r8d, 4
0x1800bba0d  lea     rdx, asc_18015D9C0; "\\??\\"
0x1800bba14  mov     rcx, rsi
0x1800bba17  call    cs:__imp__o__wcsnicmp
0x1800bba1d  test    eax, eax
0x1800bba1f  jz      loc_1800BBB4A
0x1800bba25  mov     r8d, 8
0x1800bba2b  lea     rdx, aDevice; "\\device\\"
0x1800bba32  mov     rcx, rsi
0x1800bba35  call    cs:__imp__o__wcsnicmp
0x1800bba3b  test    eax, eax
0x1800bba3d  jz      loc_1800BBB4A
0x1800bba43  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800bba47  mov     r14, rdi
0x1800bba4a  inc     r14
0x1800bba4d  cmp     [rsi+r14*2], r12w
0x1800bba52  jnz     short loc_1800BBA4A
0x1800bba54  add     r14, 5
0x1800bba58  lea     rdx, [r14+r14]; unsigned __int64
0x1800bba5c  lea     rcx, [rbp+arg_8]; void **
0x1800bba60  call    ?AllocBytes@?$CEcsMemPtr@G$0A@@@QEAAJ_K@Z; CEcsMemPtr<ushort,0>::AllocBytes(unsigned __int64)
0x1800bba65  mov     ebx, eax
0x1800bba67  mov     [rbp+var_20], eax
0x1800bba6a  test    eax, eax
0x1800bba6c  mov     eax, 164h
0x1800bba71  js      loc_1800BBB57
0x1800bba77  mov     word ptr [rbp+var_1C], ax
0x1800bba7b  mov     r8d, 4
0x1800bba81  lea     rdx, asc_18015D9A0; "\\\\?\\"
0x1800bba88  mov     rcx, rsi
0x1800bba8b  call    cs:__imp__o__wcsnicmp
0x1800bba91  test    eax, eax
0x1800bba93  jnz     short loc_1800BBA9B
0x1800bba95  mov     r8, [rbp+arg_8]
0x1800bba99  jmp     short loc_1800BBAD0
0x1800bba9b  lea     r8, asc_18015D9A0; "\\\\?\\"
0x1800bbaa2  mov     rdx, r14; unsigned __int64
0x1800bbaa5  mov     rcx, [rbp+arg_8]; unsigned __int16 *
0x1800bbaa9  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800bbaae  mov     ebx, eax
0x1800bbab0  mov     [rbp+var_20], eax
0x1800bbab3  test    eax, eax
0x1800bbab5  mov     eax, 171h
0x1800bbaba  js      loc_1800BBB57
0x1800bbac0  mov     word ptr [rbp+var_1C], ax
0x1800bbac4  mov     r8, [rbp+arg_8]
0x1800bbac8  add     r8, 8; Buffer
0x1800bbacc  add     r14, 0FFFFFFFFFFFFFFFCh
0x1800bbad0  mov     [rbp+arg_0], r12d
0x1800bbad4  lea     edx, [r14+r14]; BufferLength
0x1800bbad8  lea     rax, [rbp+arg_0]
0x1800bbadc  mov     [rsp+50h+InputPathType], rax; InputPathType
0x1800bbae1  xor     r9d, r9d; FilePart
0x1800bbae4  mov     rcx, rsi; FileName
0x1800bbae7  call    cs:__imp_RtlGetFullPathName_UEx
0x1800bbaed  mov     ecx, eax
0x1800bbaef  call    HRESULTFromNTSTATUS
0x1800bbaf4  mov     ebx, eax
0x1800bbaf6  mov     [rbp+var_20], eax
0x1800bbaf9  test    eax, eax
0x1800bbafb  mov     eax, 17Dh
0x1800bbb00  js      short loc_1800BBB57
0x1800bbb02  mov     word ptr [rbp+var_1C], ax
0x1800bbb06  lea     rcx, [r14+r14]
0x1800bbb0a  mov     eax, [rbp+arg_0]
0x1800bbb0d  cmp     rax, rcx
0x1800bbb10  jbe     short loc_1800BBB1E
0x1800bbb12  mov     ebx, 8007007Ah
0x1800bbb17  mov     eax, 182h
0x1800bbb1c  jmp     short loc_1800BBB54
0x1800bbb1e  mov     rcx, [rbp+arg_8]
0x1800bbb22  inc     rdi
0x1800bbb25  cmp     [rcx+rdi*2], r12w
0x1800bbb2a  jnz     short loc_1800BBB22
0x1800bbb2c  cmp     word ptr [rcx+rdi*2-2], 5Ch ; '\'
0x1800bbb32  jnz     short loc_1800BBB41
0x1800bbb34  mov     [rcx+rdi*2-2], r12w
0x1800bbb3a  mov     ebx, [rbp+var_20]
0x1800bbb3d  mov     rcx, [rbp+arg_8]
0x1800bbb41  mov     [rbp+arg_8], r12
0x1800bbb45  mov     [r15], rcx
0x1800bbb48  jmp     short loc_1800BBB5B
0x1800bbb4a  mov     eax, 15Bh
0x1800bbb4f  mov     ebx, 80070057h
0x1800bbb54  mov     [rbp+var_20], ebx
0x1800bbb57  mov     word ptr [rbp+var_1C+2], ax
0x1800bbb5b  lea     rcx, [rbp+arg_8]
0x1800bbb5f  call    ??1?$CEcsMemPtr@G$0A@@@QEAA@XZ; CEcsMemPtr<ushort,0>::~CEcsMemPtr<ushort,0>(void)
0x1800bbb64  lea     rcx, [rbp+var_20]; this
0x1800bbb68  call    ??1CEcsFunctionTracer@@QEAA@XZ; CEcsFunctionTracer::~CEcsFunctionTracer(void)
0x1800bbb6d  mov     eax, ebx
0x1800bbb6f  lea     r11, [rsp+50h+var_s0]
0x1800bbb74  mov     rbx, [r11+40h]
0x1800bbb78  mov     rsi, [r11+48h]
0x1800bbb7c  mov     rsp, r11
0x1800bbb7f  pop     r15
0x1800bbb81  pop     r14
0x1800bbb83  pop     r12
0x1800bbb85  pop     rdi
0x1800bbb86  pop     rbp
0x1800bbb87  retn
```
