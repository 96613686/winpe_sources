# RealSystemParametersInfoW(uint,uint,void *,uint)

- ea: `0x180048ca0`
- end: `0x18004912a`
- name: `?RealSystemParametersInfoW@@YAHIIPEAXI@Z`
- size: `1162`
- prototype: `int(unsigned int, unsigned int, void *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180048ca0`
- `0x1800945d0`

## import_xrefs

- `win32u!NtUserSystemParametersInfo` at `0x180048cfb`
- `win32u!NtUserSystemParametersInfo` at `0x180048d79`
- `win32u!NtUserSystemParametersInfo` at `0x180048dc3`
- `win32u!NtUserSystemParametersInfo` at `0x180048df5`
- `win32u!NtUserSystemParametersInfo` at `0x180048e58`
- `win32u!NtUserSystemParametersInfo` at `0x180048eb6`
- `win32u!NtUserSystemParametersInfo` at `0x180048f1c`
- `win32u!NtUserSystemParametersInfo` at `0x180048fe7`
- `win32u!NtUserSystemParametersInfo` at `0x180048ffc`
- `win32u!NtUserSystemParametersInfo` at `0x18009e0d7`
- `win32u!NtUserSystemParametersInfo` at `0x18009e13d`
- `win32u!NtUserSystemParametersInfo` at `0x180048cfb`
- `win32u!NtUserSystemParametersInfo` at `0x180048d79`
- `win32u!NtUserSystemParametersInfo` at `0x180048dc3`
- `win32u!NtUserSystemParametersInfo` at `0x180048df5`
- `win32u!NtUserSystemParametersInfo` at `0x180048e58`
- `win32u!NtUserSystemParametersInfo` at `0x180048eb6`
- `win32u!NtUserSystemParametersInfo` at `0x180048f1c`
- `win32u!NtUserSystemParametersInfo` at `0x180048fe7`
- `win32u!NtUserSystemParametersInfo` at `0x180048ffc`
- `win32u!NtUserSystemParametersInfo` at `0x18009e0d7`
- `win32u!NtUserSystemParametersInfo` at `0x18009e13d`
- `ntdll!RtlInitUnicodeString` at `0x180048f6d`
- `ntdll!RtlInitUnicodeString` at `0x180048f8f`
- `ntdll!RtlInitUnicodeString` at `0x18009e120`
- `ntdll!RtlInitUnicodeString` at `0x180048f6d`
- `ntdll!RtlInitUnicodeString` at `0x180048f8f`
- `ntdll!RtlInitUnicodeString` at `0x18009e120`
- `ntdll!RtlAllocateHeap` at `0x180048d3e`
- `ntdll!RtlAllocateHeap` at `0x180048d3e`

## pseudocode

```c
__int64 __fastcall RealSystemParametersInfoW(unsigned int a1, DWORD a2, const WCHAR *a3, __int64 a4)
{
  unsigned int v4; // esi
  const WCHAR *v5; // rdi
  DWORD v6; // ebp
  unsigned int v8; // eax
  unsigned int v9; // edx
  unsigned int v10; // ebx
  unsigned int v11; // ebx
  const WCHAR *Heap; // rax
  bool v14; // zf
  unsigned int v15; // eax
  unsigned int v16; // r14d
  const WCHAR *v17; // rdx
  _DWORD v18[2]; // [rsp+20h] [rbp-68h] BYREF
  __int128 v19; // [rsp+28h] [rbp-60h]
  struct _UNICODE_STRING DestinationString[5]; // [rsp+38h] [rbp-50h] BYREF

  memset(DestinationString, 0, 32);
  v4 = a4;
  v5 = a3;
  v6 = a2;
  LODWORD(DestinationString[1].Buffer) = 0;
  v19 = 0;
  if ( a1 == 97 )
    return 0;
  if ( a1 == 66 )
  {
    if ( a3 )
    {
      if ( *(_DWORD *)a3 == 16 )
      {
        Heap = pwcHighContrastScheme;
        if ( pwcHighContrastScheme
          || (Heap = (const WCHAR *)RtlAllocateHeap(pUserHeap, 8u, 0x100u), (pwcHighContrastScheme = Heap) != 0) )
        {
          *((_QWORD *)v5 + 1) = Heap;
          return (unsigned int)NtUserSystemParametersInfo(a1, v6, v5, v4);
        }
      }
    }
    return 0;
  }
  if ( a1 <= 0x2017 )
  {
    if ( a1 != 8215 )
    {
      switch ( a1 )
      {
        case 0x14u:
          if ( (unsigned __int64)a3 - 1 <= 0xFFFFFFFFFFFFFFFCuLL )
          {
            *(_QWORD *)&DestinationString[1].Length = DestinationString;
            RtlInitUnicodeString(DestinationString, a3);
            v5 = *(const WCHAR **)&DestinationString[1].Length;
            v15 = 0;
          }
          else
          {
            v15 = -1;
          }
          a4 = v4;
          a3 = v5;
          return (unsigned int)NtUserSystemParametersInfo(a1, v15, a3, a4);
        case 0x15u:
          v15 = -1;
          v16 = -1;
          if ( a2 != 0xFFFF )
            v16 = a2;
          if ( v16 == -1 )
            return (unsigned int)NtUserSystemParametersInfo(a1, v15, a3, a4);
          if ( (unsigned __int64)a3 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
          {
            *(_QWORD *)&DestinationString[1].Length = DestinationString;
            RtlInitUnicodeString(DestinationString, a3);
            v5 = *(const WCHAR **)&DestinationString[1].Length;
          }
          v9 = NtUserSystemParametersInfo(a1, v16, v5, v4);
          break;
        case 0x22u:
          return (unsigned int)NtUserSystemParametersInfo(a1, 92, a3, a4);
        case 0x29u:
          if ( !a3 || ((*(_DWORD *)a3 - 500) & 0xFFFFFFFB) != 0 )
            return 0;
          return (unsigned int)NtUserSystemParametersInfo(a1, *(unsigned int *)a3, a3, a4);
        case 0x2Au:
          if ( !a3 || ((*(_DWORD *)a3 - 500) & 0xFFFFFFFB) != 0 )
            return 0;
          if ( *((int *)a3 + 4) > 256 )
            *((_DWORD *)a3 + 4) = 256;
          if ( *((int *)a3 + 5) > 256 )
            *((_DWORD *)a3 + 5) = 256;
          return (unsigned int)NtUserSystemParametersInfo(a1, *(unsigned int *)a3, a3, a4);
        case 0x2Bu:
          if ( !a3 )
            return 0;
          v14 = *(_DWORD *)a3 == 20;
          goto LABEL_34;
        case 0x2Cu:
          if ( !a3 || *(_DWORD *)a3 != 20 )
            return 0;
          return (unsigned int)NtUserSystemParametersInfo(a1, 20, a3, a4);
        case 0x2Du:
          if ( !a3 || *(_DWORD *)a3 != 108 )
            return 0;
          goto LABEL_6;
        case 0x2Eu:
          if ( !a3 || *(_DWORD *)a3 != 108 )
            return 0;
          return (unsigned int)NtUserSystemParametersInfo(a1, 108, a3, a4);
        case 0x32u:
          if ( (unsigned int)(*(_DWORD *)a3 - 1) > 0x17 )
            return 0;
          goto LABEL_6;
        case 0x34u:
        case 0x3Au:
          if ( (unsigned int)(*(_DWORD *)a3 - 1) > 7 )
            return 0;
          goto LABEL_6;
        case 0x36u:
          if ( (unsigned int)(*(_DWORD *)a3 - 1) > 0x1B )
            return 0;
          goto LABEL_6;
        case 0x3Cu:
          if ( (unsigned int)(*(_DWORD *)a3 - 1) > 0xB )
            return 0;
          goto LABEL_6;
        case 0x40u:
          if ( (unsigned int)(*(_DWORD *)a3 - 1) > 0x37 )
            return 0;
          goto LABEL_6;
        case 0x43u:
          v18[0] = 16;
          if ( !a3 || *(_DWORD *)a3 != 16 )
            return 0;
          v17 = (const WCHAR *)*((_QWORD *)a3 + 1);
          v18[1] = *((_DWORD *)a3 + 1);
          *(_QWORD *)&DestinationString[1].Length = DestinationString;
          RtlInitUnicodeString(DestinationString, v17);
          v19 = **(_OWORD **)&DestinationString[1].Length;
          return (unsigned int)NtUserSystemParametersInfo(a1, v6, v18, v4);
        case 0x48u:
        case 0x49u:
          if ( !a3 )
            return 0;
          v14 = *(_DWORD *)a3 == 8;
LABEL_34:
          if ( !v14 )
            return 0;
          goto LABEL_6;
        case 0x73u:
          if ( !a3 || !a2 )
            return 0;
          v6 = a2 - 1;
          v9 = NtUserSystemParametersInfo(a1, a2 - 1, a3, a4);
          goto LABEL_23;
        case 0x74u:
        case 0x75u:
          if ( !a3 || *(_DWORD *)a3 != 12 )
            return 0;
          goto LABEL_6;
        default:
          goto LABEL_6;
      }
      return v9;
    }
    if ( (unsigned int)((_DWORD)a3 - 1) <= 3 )
      return 0;
  }
LABEL_6:
  v8 = NtUserSystemParametersInfo(a1, a2, a3, a4);
  v9 = v8;
  v10 = a1 - 81;
  if ( !v10 || (v11 = v10 - 1) == 0 )
  {
    if ( v8 && (v4 & 1) != 0 )
      return (unsigned int)SetVideoTimeout(v6);
    return v9;
  }
  if ( v11 != 33 )
    return v9;
LABEL_23:
  v5[v6] = 0;
  return v9;
}

```

## disassembly

```asm
0x180048ca0  push    rbx
0x180048ca2  push    rbp
0x180048ca3  push    rsi
0x180048ca4  push    rdi
0x180048ca5  push    r14
0x180048ca7  sub     rsp, 60h
0x180048cab  xorps   xmm0, xmm0
0x180048cae  xor     eax, eax
0x180048cb0  mov     [rsp+88h+DestinationString.Length], ax
0x180048cb5  mov     esi, r9d
0x180048cb8  mov     rdi, r8
0x180048cbb  mov     ebp, edx
0x180048cbd  mov     ebx, ecx
0x180048cbf  movups  xmmword ptr [rsp+88h+DestinationString.MaximumLength], xmm0
0x180048cc4  movups  xmmword ptr [rsp+48h], xmm0
0x180048cc9  mov     [rsp+88h+var_38], eax
0x180048ccd  movdqu  [rsp+88h+var_60], xmm0
0x180048cd3  cmp     ecx, 61h ; 'a'
0x180048cd6  jz      short loc_180048D50
0x180048cd8  cmp     ecx, 42h ; 'B'
0x180048cdb  jz      short loc_180048D54
0x180048cdd  cmp     ecx, 2017h
0x180048ce3  ja      short def_180048DA8; jumptable 0000000180048DA8 default case, cases 22-33,35-40,47-49,51,53,55-57,59,61-63,65,66,68-71,74-114
0x180048ce5  jz      loc_180049048
0x180048ceb  lea     eax, [rcx-14h]; switch 98 cases
0x180048cee  cmp     eax, 61h
0x180048cf1  jbe     loc_180048D8F
0x180048cf7  mov     edx, ebp; jumptable 0000000180048DA8 default case, cases 22-33,35-40,47-49,51,53,55-57,59,61-63,65,66,68-71,74-114
0x180048cf9  mov     ecx, ebx
0x180048cfb  call    cs:__imp_NtUserSystemParametersInfo
0x180048d01  movsxd  rdx, eax
0x180048d04  sub     ebx, 51h ; 'Q'
0x180048d07  jz      loc_18004905A
0x180048d0d  sub     ebx, 1
0x180048d10  jz      loc_18004905A
0x180048d16  cmp     ebx, 21h ; '!'
0x180048d19  jz      loc_180048DFE
0x180048d1f  mov     eax, edx
0x180048d21  add     rsp, 60h
0x180048d25  pop     r14
0x180048d27  pop     rdi
0x180048d28  pop     rsi
0x180048d29  pop     rbp
0x180048d2a  pop     rbx
0x180048d2b  retn
0x180048d2c  mov     rcx, cs:pUserHeap; HeapHandle
0x180048d33  mov     edx, 8; Flags
0x180048d38  mov     r8d, 100h; Size
0x180048d3e  call    cs:__imp_RtlAllocateHeap
0x180048d44  mov     cs:?pwcHighContrastScheme@@3PEAGEA, rax; ushort * pwcHighContrastScheme
0x180048d4b  test    rax, rax
0x180048d4e  jnz     short loc_180048D6B
0x180048d50  xor     edx, edx
0x180048d52  jmp     short loc_180048D1F
0x180048d54  test    rdi, rdi
0x180048d57  jz      short loc_180048D50
0x180048d59  cmp     dword ptr [r8], 10h
0x180048d5d  jnz     short loc_180048D50
0x180048d5f  mov     rax, cs:?pwcHighContrastScheme@@3PEAGEA; ushort * pwcHighContrastScheme
0x180048d66  test    rax, rax
0x180048d69  jz      short loc_180048D2C
0x180048d6b  mov     r9d, esi
0x180048d6e  mov     [rdi+8], rax
0x180048d72  mov     r8, rdi
0x180048d75  mov     edx, ebp
0x180048d77  mov     ecx, ebx
0x180048d79  call    cs:__imp_NtUserSystemParametersInfo
0x180048d7f  movsxd  rdx, eax
0x180048d82  mov     eax, edx
0x180048d84  add     rsp, 60h
0x180048d88  pop     r14
0x180048d8a  pop     rdi
0x180048d8b  pop     rsi
0x180048d8c  pop     rbp
0x180048d8d  pop     rbx
0x180048d8e  retn
0x180048d8f  lea     rdx, __ImageBase
0x180048d96  movzx   eax, ds:(byte_1800490C8 - 180000000h)[rdx+rax]
0x180048d9e  mov     ecx, ds:(jpt_180048DA8 - 180000000h)[rdx+rax*4]
0x180048da5  add     rcx, rdx
0x180048da8  jmp     rcx; switch jump
0x180048daa  test    rdi, rdi; jumptable 0000000180048DA8 case 41
0x180048dad  jz      short loc_180048D50
0x180048daf  mov     eax, [r8]
0x180048db2  sub     eax, 1F4h
0x180048db7  test    eax, 0FFFFFFFBh
0x180048dbc  jnz     short loc_180048D50
0x180048dbe  mov     edx, [r8]
0x180048dc1  mov     ecx, ebx
0x180048dc3  call    cs:__imp_NtUserSystemParametersInfo
0x180048dc9  movsxd  rdx, eax
0x180048dcc  mov     eax, edx
0x180048dce  add     rsp, 60h
0x180048dd2  pop     r14
0x180048dd4  pop     rdi
0x180048dd5  pop     rsi
0x180048dd6  pop     rbp
0x180048dd7  pop     rbx
0x180048dd8  retn
0x180048dd9  test    rdi, rdi; jumptable 0000000180048DA8 case 115
0x180048ddc  jz      loc_180048D50
0x180048de2  test    ebp, ebp
0x180048de4  jz      loc_180048D50
0x180048dea  mov     eax, 0FFFFFFFFh
0x180048def  mov     ecx, ebx
0x180048df1  add     ebp, eax
0x180048df3  mov     edx, ebp
0x180048df5  call    cs:__imp_NtUserSystemParametersInfo
0x180048dfb  movsxd  rdx, eax
0x180048dfe  xor     eax, eax
0x180048e00  mov     ecx, ebp
0x180048e02  mov     [rdi+rcx*2], ax
0x180048e06  mov     eax, edx
0x180048e08  add     rsp, 60h
0x180048e0c  pop     r14
0x180048e0e  pop     rdi
0x180048e0f  pop     rsi
0x180048e10  pop     rbp
0x180048e11  pop     rbx
0x180048e12  retn
0x180048e13  test    rdi, rdi; jumptable 0000000180048DA8 case 45
0x180048e16  jz      loc_180048D50
0x180048e1c  cmp     dword ptr [r8], 6Ch ; 'l'
0x180048e20  jz      def_180048DA8; jumptable 0000000180048DA8 default case, cases 22-33,35-40,47-49,51,53,55-57,59,61-63,65,66,68-71,74-114
0x180048e26  jmp     loc_180048D50
0x180048e2b  mov     eax, [r8]; jumptable 0000000180048DA8 case 64
0x180048e2e  dec     eax
0x180048e30  cmp     eax, 37h ; '7'
0x180048e33  jbe     def_180048DA8; jumptable 0000000180048DA8 default case, cases 22-33,35-40,47-49,51,53,55-57,59,61-63,65,66,68-71,74-114
0x180048e39  jmp     loc_180048D50
0x180048e3e  test    rdi, rdi; jumptable 0000000180048DA8 case 44
0x180048e41  jz      loc_180048D50
0x180048e47  cmp     dword ptr [r8], 14h
0x180048e4b  jnz     loc_180048D50
0x180048e51  mov     edx, 14h
0x180048e56  mov     ecx, ebx
0x180048e58  call    cs:__imp_NtUserSystemParametersInfo
0x180048e5e  movsxd  rdx, eax
0x180048e61  mov     eax, edx
0x180048e63  add     rsp, 60h
0x180048e67  pop     r14
0x180048e69  pop     rdi
0x180048e6a  pop     rsi
0x180048e6b  pop     rbp
0x180048e6c  pop     rbx
0x180048e6d  retn
0x180048e6e  test    rdi, rdi; jumptable 0000000180048DA8 case 43
0x180048e71  jz      loc_180048D50
0x180048e77  cmp     dword ptr [r8], 14h
0x180048e7b  jz      def_180048DA8; jumptable 0000000180048DA8 default case, cases 22-33,35-40,47-49,51,53,55-57,59,61-63,65,66,68-71,74-114
0x180048e81  jmp     loc_180048D50
0x180048e86  mov     eax, [r8]; jumptable 0000000180048DA8 case 54
0x180048e89  dec     eax
0x180048e8b  cmp     eax, 1Bh
0x180048e8e  jbe     def_180048DA8; jumptable 0000000180048DA8 default case, cases 22-33,35-40,47-49,51,53,55-57,59,61-63,65,66,68-71,74-114
0x180048e94  jmp     loc_180048D50
0x180048e99  lea     rax, [r8-1]; jumptable 0000000180048DA8 case 20
0x180048e9d  cmp     rax, 0FFFFFFFFFFFFFFFCh
0x180048ea1  jbe     loc_180048F7D
0x180048ea7  mov     eax, 0FFFFFFFFh
0x180048eac  mov     r9d, esi
0x180048eaf  mov     r8, rdi
0x180048eb2  mov     edx, eax
0x180048eb4  mov     ecx, ebx
0x180048eb6  call    cs:__imp_NtUserSystemParametersInfo
0x180048ebc  movsxd  rdx, eax
0x180048ebf  mov     eax, edx
0x180048ec1  add     rsp, 60h
0x180048ec5  pop     r14
0x180048ec7  pop     rdi
0x180048ec8  pop     rsi
0x180048ec9  pop     rbp
0x180048eca  pop     rbx
0x180048ecb  retn
0x180048ecc  mov     eax, [r8]; jumptable 0000000180048DA8 case 50
0x180048ecf  dec     eax
0x180048ed1  cmp     eax, 17h
0x180048ed4  jbe     def_180048DA8; jumptable 0000000180048DA8 default case, cases 22-33,35-40,47-49,51,53,55-57,59,61-63,65,66,68-71,74-114
0x180048eda  jmp     loc_180048D50
0x180048edf  test    rdi, rdi; jumptable 0000000180048DA8 case 42
0x180048ee2  jz      loc_180048D50
0x180048ee8  mov     eax, [r8]
0x180048eeb  sub     eax, 1F4h
0x180048ef0  test    eax, 0FFFFFFFBh
0x180048ef5  jnz     loc_180048D50
0x180048efb  cmp     dword ptr [r8+10h], 100h
0x180048f03  jg      loc_180048FB3
0x180048f09  cmp     dword ptr [r8+14h], 100h
0x180048f11  jg      loc_180048FC0
0x180048f17  mov     edx, [r8]
0x180048f1a  mov     ecx, ebx
0x180048f1c  call    cs:__imp_NtUserSystemParametersInfo
0x180048f22  movsxd  rdx, eax
0x180048f25  mov     eax, edx
0x180048f27  add     rsp, 60h
0x180048f2b  pop     r14
0x180048f2d  pop     rdi
0x180048f2e  pop     rsi
0x180048f2f  pop     rbp
0x180048f30  pop     rbx
0x180048f31  retn
0x180048f32  mov     eax, 0FFFFFFFFh; jumptable 0000000180048DA8 case 21
0x180048f37  cmp     ebp, 0FFFFh
0x180048f3d  mov     r14d, eax
0x180048f40  cmovnz  r14d, ebp
0x180048f44  cmp     r14d, eax
0x180048f47  jz      loc_180048EB2
0x180048f4d  lea     rax, [r8-1]
0x180048f51  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180048f55  ja      loc_18009E0CC
0x180048f5b  lea     rax, [rsp+88h+DestinationString]
0x180048f60  mov     rdx, rdi; SourceString
0x180048f63  lea     rcx, [rsp+88h+DestinationString]; DestinationString
0x180048f68  mov     [rsp+48h], rax
0x180048f6d  call    cs:__imp_RtlInitUnicodeString
0x180048f73  mov     rdi, [rsp+48h]
0x180048f78  jmp     loc_18009E0CC
0x180048f7d  lea     rax, [rsp+88h+DestinationString]
0x180048f82  mov     rdx, rdi; SourceString
0x180048f85  lea     rcx, [rsp+88h+DestinationString]; DestinationString
0x180048f8a  mov     [rsp+48h], rax
0x180048f8f  call    cs:__imp_RtlInitUnicodeString
0x180048f95  mov     rdi, [rsp+48h]
0x180048f9a  xor     eax, eax
0x180048f9c  jmp     loc_180048EAC
0x180048fa1  test    rdi, rdi; jumptable 0000000180048DA8 cases 72,73
0x180048fa4  jz      loc_180048D50
0x180048faa  cmp     dword ptr [r8], 8
0x180048fae  jmp     loc_180048E7B
0x180048fb3  mov     dword ptr [r8+10h], 100h
0x180048fbb  jmp     loc_180048F09
0x180048fc0  mov     dword ptr [r8+14h], 100h
0x180048fc8  jmp     loc_180048F17
0x180048fcd  test    rdi, rdi; jumptable 0000000180048DA8 case 46
0x180048fd0  jz      loc_180048D50
0x180048fd6  cmp     dword ptr [r8], 6Ch ; 'l'
0x180048fda  jnz     loc_180048D50
0x180048fe0  mov     edx, 6Ch ; 'l'
0x180048fe5  mov     ecx, ebx
0x180048fe7  call    cs:__imp_NtUserSystemParametersInfo
0x180048fed  movsxd  rdx, eax
0x180048ff0  jmp     loc_180048D1F
0x180048ff5  mov     edx, 5Ch ; '\'; jumptable 0000000180048DA8 case 34
0x180048ffa  mov     ecx, ebx
0x180048ffc  call    cs:__imp_NtUserSystemParametersInfo
0x180049002  movsxd  rdx, eax
0x180049005  jmp     loc_180048D1F
0x18004900a  mov     eax, [r8]; jumptable 0000000180048DA8 cases 52,58
0x18004900d  dec     eax
0x18004900f  cmp     eax, 7
0x180049012  jbe     def_180048DA8; jumptable 0000000180048DA8 default case, cases 22-33,35-40,47-49,51,53,55-57,59,61-63,65,66,68-71,74-114
0x180049018  jmp     loc_180048D50
0x18004901d  mov     eax, [r8]; jumptable 0000000180048DA8 case 60
0x180049020  dec     eax
0x180049022  cmp     eax, 0Bh
0x180049025  jbe     def_180048DA8; jumptable 0000000180048DA8 default case, cases 22-33,35-40,47-49,51,53,55-57,59,61-63,65,66,68-71,74-114
0x18004902b  jmp     loc_180048D50
0x180049030  test    rdi, rdi; jumptable 0000000180048DA8 cases 116,117
0x180049033  jz      loc_180048D50
0x180049039  cmp     dword ptr [r8], 0Ch
0x18004903d  jz      def_180048DA8; jumptable 0000000180048DA8 default case, cases 22-33,35-40,47-49,51,53,55-57,59,61-63,65,66,68-71,74-114
0x180049043  jmp     loc_180048D50
0x180049048  lea     eax, [r8-1]
0x18004904c  cmp     eax, 3
0x18004904f  jbe     loc_180048D50
0x180049055  jmp     def_180048DA8; jumptable 0000000180048DA8 default case, cases 22-33,35-40,47-49,51,53,55-57,59,61-63,65,66,68-71,74-114
0x18004905a  test    eax, eax
0x18004905c  jz      loc_180048D1F
0x180049062  test    sil, 1
0x180049066  jz      loc_180048D1F
0x18004906c  mov     ecx, ebp; DcValueIndex
0x18004906e  call    ?SetVideoTimeout@@YAHK@Z; SetVideoTimeout(ulong)
0x180049073  movsxd  rdx, eax
0x180049076  jmp     loc_180048D1F
0x18009e0cc  mov     r9d, esi
0x18009e0cf  mov     r8, rdi
0x18009e0d2  mov     edx, r14d
0x18009e0d5  mov     ecx, ebx
0x18009e0d7  call    cs:__imp_NtUserSystemParametersInfo
0x18009e0dd  movsxd  rdx, eax
0x18009e0e0  jmp     loc_180048D1F
0x18009e0e5  mov     [rsp+88h+var_68], 10h; jumptable 0000000180048DA8 case 67
0x18009e0ed  test    rdi, rdi
0x18009e0f0  jz      loc_180048D50
0x18009e0f6  cmp     dword ptr [r8], 10h
0x18009e0fa  jnz     loc_180048D50
0x18009e100  mov     eax, [r8+4]
0x18009e104  lea     rcx, [rsp+88h+DestinationString]; DestinationString
0x18009e109  mov     rdx, [r8+8]; SourceString
0x18009e10d  lea     r14, [rsp+88h+var_68]
0x18009e112  mov     [rsp+88h+var_64], eax
0x18009e116  lea     rax, [rsp+88h+DestinationString]
0x18009e11b  mov     [rsp+48h], rax
0x18009e120  call    cs:__imp_RtlInitUnicodeString
0x18009e126  mov     rax, [rsp+48h]
0x18009e12b  mov     r9d, esi
0x18009e12e  mov     r8, r14
0x18009e131  mov     edx, ebp
0x18009e133  mov     ecx, ebx
0x18009e135  movups  xmm0, xmmword ptr [rax]
  ... truncated ...
```
