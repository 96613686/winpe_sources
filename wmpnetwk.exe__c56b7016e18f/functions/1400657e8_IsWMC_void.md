# IsWMC(void)

- ea: `0x1400657e8`
- end: `0x140065a68`
- name: `?IsWMC@@YAHXZ`
- size: `640`
- prototype: `__int64(void)`
- caller_count: `6`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400413ec`
- `0x140064508`
- `0x140064618`
- `0x14006510c`
- `0x1400651a4`
- `0x140065384`

## callees

- `0x1400282b0`
- `0x14003f17c`
- `0x140045f20`
- `0x140047798`
- `0x140054534`
- `0x140064038`
- `0x140064158`
- `0x1400657e8`

## import_xrefs

- `KERNEL32!GetModuleFileNameW` at `0x14006596a`
- `KERNEL32!GetModuleFileNameW` at `0x14006596a`
- `KERNEL32!CompareStringW` at `0x140065a07`
- `KERNEL32!CompareStringW` at `0x140065a07`

## pseudocode

```c
_BOOL8 __fastcall IsWMC(__int64 a1, unsigned __int64 a2)
{
  const unsigned __int16 *v2; // rcx
  WCHAR *DllPath; // rax
  PVOID *v4; // rcx
  __int64 v5; // rdx
  int v6; // eax
  unsigned __int64 v7; // rdx
  const unsigned __int16 *v8; // r8
  int v9; // ebx
  int v10; // eax
  int v11; // ebx
  int v13; // eax
  BOOL v14; // ebx
  WCHAR String2[264]; // [rsp+30h] [rbp-448h] BYREF
  WCHAR Filename[272]; // [rsp+240h] [rbp-238h] BYREF

  v2 = (const unsigned __int16 *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_828385feb866308232dae4a9fce45b28_Traceguids);
  DllPath = GetDllPath(v2, a2);
  if ( !DllPath )
  {
    v4 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u )
    {
      return 0;
    }
    v5 = 11;
LABEL_32:
    WPP_SF_d(v4[2], v5, WPP_828385feb866308232dae4a9fce45b28_Traceguids, 0);
    return 0;
  }
  v6 = StringCchCopyW(String2, 0x104u, DllPath);
  v9 = v6;
  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    v7 = ((v6 >> 31) & 0xFFFFFFFD) + 5;
    if ( *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= (unsigned int)v7 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        12,
        WPP_828385feb866308232dae4a9fce45b28_Traceguids,
        (unsigned int)v6);
      v4 = (PVOID *)WPP_GLOBAL_Control;
    }
  }
  if ( v9 < 0 )
  {
    if ( v4 == &WPP_GLOBAL_Control || (*((_BYTE *)v4 + 28) & 1) == 0 || *((_BYTE *)v4 + 25) < 5u )
      return 0;
    v5 = 13;
    goto LABEL_32;
  }
  v10 = StringCchCatW(String2, v7, v8);
  v11 = v10;
  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((v10 >> 31) & 0xFFFFFFFD) + 5 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      14,
      WPP_828385feb866308232dae4a9fce45b28_Traceguids,
      (unsigned int)v10);
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v11 < 0 )
  {
    if ( v4 == &WPP_GLOBAL_Control || (*((_BYTE *)v4 + 28) & 1) == 0 || *((_BYTE *)v4 + 25) < 5u )
      return 0;
    v5 = 15;
    goto LABEL_32;
  }
  if ( GetModuleFileNameW(0, Filename, 0x10Eu) >= 0x10D )
  {
    v4 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u )
    {
      return 0;
    }
    v5 = 16;
    goto LABEL_32;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_SS(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)String2);
  }
  v13 = CompareStringW(0x7Fu, 1u, Filename, -1, String2, -1);
  v14 = v13 == 2;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_828385feb866308232dae4a9fce45b28_Traceguids, v13 == 2);
  }
  return v14;
}

```

## disassembly

```asm
0x1400657e8  mov     [rsp+arg_0], rbx
0x1400657ed  mov     [rsp+arg_8], rsi
0x1400657f2  push    rdi
0x1400657f3  sub     rsp, 470h
0x1400657fa  mov     rax, cs:__security_cookie
0x140065801  xor     rax, rsp
0x140065804  mov     [rsp+478h+var_18], rax
0x14006580c  mov     rcx, cs:WPP_GLOBAL_Control
0x140065813  lea     rdi, WPP_GLOBAL_Control
0x14006581a  lea     rsi, WPP_828385feb866308232dae4a9fce45b28_Traceguids
0x140065821  cmp     rcx, rdi
0x140065824  jz      short loc_14006583D
0x140065826  test    byte ptr [rcx+1Ch], 1
0x14006582a  jz      short loc_14006583D
0x14006582c  mov     rcx, [rcx+10h]
0x140065830  mov     edx, 0Ah
0x140065835  mov     r8, rsi
0x140065838  call    WPP_SF_
0x14006583d  call    ?GetDllPath@@YAPEBGXZ; GetDllPath(void)
0x140065842  test    rax, rax
0x140065845  jnz     short loc_140065873
0x140065847  mov     rcx, cs:WPP_GLOBAL_Control
0x14006584e  cmp     rcx, rdi
0x140065851  jz      loc_1400659A3
0x140065857  test    byte ptr [rcx+1Ch], 1
0x14006585b  jz      loc_1400659A3
0x140065861  cmp     byte ptr [rcx+19h], 5
0x140065865  jb      loc_1400659A3
0x14006586b  lea     edx, [rax+0Bh]
0x14006586e  jmp     loc_140065994
0x140065873  mov     r8, rax; unsigned __int16 *
0x140065876  lea     rcx, [rsp+478h+String2]; unsigned __int16 *
0x14006587b  mov     edx, 104h; unsigned __int64
0x140065880  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140065885  mov     ebx, eax
0x140065887  mov     rcx, cs:WPP_GLOBAL_Control
0x14006588e  cmp     rcx, rdi
0x140065891  jz      short loc_1400658C7
0x140065893  test    byte ptr [rcx+1Ch], 2
0x140065897  jz      short loc_1400658C7
0x140065899  mov     edx, eax
0x14006589b  movzx   eax, byte ptr [rcx+19h]
0x14006589f  sar     edx, 1Fh
0x1400658a2  and     edx, 0FFFFFFFDh
0x1400658a5  add     edx, 5
0x1400658a8  cmp     eax, edx
0x1400658aa  jb      short loc_1400658C7
0x1400658ac  mov     rcx, [rcx+10h]
0x1400658b0  mov     edx, 0Ch
0x1400658b5  mov     r9d, ebx
0x1400658b8  mov     r8, rsi
0x1400658bb  call    WPP_SF_d
0x1400658c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400658c7  test    ebx, ebx
0x1400658c9  jns     short loc_1400658F2
0x1400658cb  cmp     rcx, rdi
0x1400658ce  jz      loc_1400659A3
0x1400658d4  test    byte ptr [rcx+1Ch], 1
0x1400658d8  jz      loc_1400659A3
0x1400658de  cmp     byte ptr [rcx+19h], 5
0x1400658e2  jb      loc_1400659A3
0x1400658e8  mov     edx, 0Dh
0x1400658ed  jmp     loc_140065994
0x1400658f2  lea     rcx, [rsp+478h+String2]; unsigned __int16 *
0x1400658f7  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1400658fc  mov     ebx, eax
0x1400658fe  mov     rcx, cs:WPP_GLOBAL_Control
0x140065905  cmp     rcx, rdi
0x140065908  jz      short loc_14006593E
0x14006590a  test    byte ptr [rcx+1Ch], 2
0x14006590e  jz      short loc_14006593E
0x140065910  mov     edx, eax
0x140065912  movzx   eax, byte ptr [rcx+19h]
0x140065916  sar     edx, 1Fh
0x140065919  and     edx, 0FFFFFFFDh
0x14006591c  add     edx, 5
0x14006591f  cmp     eax, edx
0x140065921  jb      short loc_14006593E
0x140065923  mov     rcx, [rcx+10h]
0x140065927  mov     edx, 0Eh
0x14006592c  mov     r9d, ebx
0x14006592f  mov     r8, rsi
0x140065932  call    WPP_SF_d
0x140065937  mov     rcx, cs:WPP_GLOBAL_Control
0x14006593e  test    ebx, ebx
0x140065940  jns     short loc_14006595A
0x140065942  cmp     rcx, rdi
0x140065945  jz      short loc_1400659A3
0x140065947  test    byte ptr [rcx+1Ch], 1
0x14006594b  jz      short loc_1400659A3
0x14006594d  cmp     byte ptr [rcx+19h], 5
0x140065951  jb      short loc_1400659A3
0x140065953  mov     edx, 0Fh
0x140065958  jmp     short loc_140065994
0x14006595a  mov     r8d, 10Eh; nSize
0x140065960  lea     rdx, [rsp+478h+Filename]; lpFilename
0x140065968  xor     ecx, ecx; hModule
0x14006596a  call    cs:__imp_GetModuleFileNameW
0x140065970  cmp     eax, 10Dh
0x140065975  jb      short loc_1400659AA
0x140065977  mov     rcx, cs:WPP_GLOBAL_Control
0x14006597e  cmp     rcx, rdi
0x140065981  jz      short loc_1400659A3
0x140065983  test    byte ptr [rcx+1Ch], 1
0x140065987  jz      short loc_1400659A3
0x140065989  cmp     byte ptr [rcx+19h], 5
0x14006598d  jb      short loc_1400659A3
0x14006598f  mov     edx, 10h
0x140065994  mov     rcx, [rcx+10h]
0x140065998  xor     r9d, r9d
0x14006599b  mov     r8, rsi
0x14006599e  call    WPP_SF_d
0x1400659a3  xor     eax, eax
0x1400659a5  jmp     loc_140065A43
0x1400659aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1400659b1  cmp     rcx, rdi
0x1400659b4  jz      short loc_1400659E5
0x1400659b6  test    byte ptr [rcx+1Ch], 2
0x1400659ba  jz      short loc_1400659E5
0x1400659bc  cmp     byte ptr [rcx+19h], 5
0x1400659c0  jb      short loc_1400659E5
0x1400659c2  mov     rcx, [rcx+10h]; LoggerHandle
0x1400659c6  lea     rax, [rsp+478h+String2]
0x1400659cb  mov     edx, 11h
0x1400659d0  mov     [rsp+478h+lpString2], rax; __int64
0x1400659d5  lea     r9, [rsp+478h+Filename]
0x1400659dd  mov     r8, rsi
0x1400659e0  call    WPP_SF_SS
0x1400659e5  or      r9d, 0FFFFFFFFh; cchCount1
0x1400659e9  lea     rax, [rsp+478h+String2]
0x1400659ee  mov     [rsp+478h+cchCount2], r9d; cchCount2
0x1400659f3  lea     r8, [rsp+478h+Filename]; lpString1
0x1400659fb  mov     [rsp+478h+lpString2], rax; lpString2
0x140065a00  lea     edx, [r9+2]; dwCmpFlags
0x140065a04  lea     ecx, [rdx+7Eh]; Locale
0x140065a07  call    cs:__imp_CompareStringW
0x140065a0d  mov     rcx, cs:WPP_GLOBAL_Control
0x140065a14  xor     ebx, ebx
0x140065a16  cmp     eax, 2
0x140065a19  setz    bl
0x140065a1c  cmp     rcx, rdi
0x140065a1f  jz      short loc_140065A41
0x140065a21  test    byte ptr [rcx+1Ch], 1
0x140065a25  jz      short loc_140065A41
0x140065a27  cmp     byte ptr [rcx+19h], 5
0x140065a2b  jb      short loc_140065A41
0x140065a2d  mov     rcx, [rcx+10h]
0x140065a31  mov     edx, 12h
0x140065a36  mov     r9d, ebx
0x140065a39  mov     r8, rsi
0x140065a3c  call    WPP_SF_d
0x140065a41  mov     eax, ebx
0x140065a43  mov     rcx, [rsp+478h+var_18]
0x140065a4b  xor     rcx, rsp; StackCookie
0x140065a4e  call    __security_check_cookie
0x140065a53  lea     r11, [rsp+478h+var_8]
0x140065a5b  mov     rbx, [r11+10h]
0x140065a5f  mov     rsi, [r11+18h]
0x140065a63  mov     rsp, r11
0x140065a66  pop     rdi
0x140065a67  retn
```
