# CBsString::_GetErrorText(long,ulong,___FORMAT_ERRORCODE_SEARCH_DLL_ENTRY const *,ulong,___FORMAT_ERRORCODE_ERROR_MAP_ENTRTY const *,long *,ushort * *,ushort * *)

- ea: `0x18009ab28`
- end: `0x18009ae2b`
- name: `?_GetErrorText@CBsString@@AEAAJJKPEBU___FORMAT_ERRORCODE_SEARCH_DLL_ENTRY@@KPEBU___FORMAT_ERRORCODE_ERROR_MAP_ENTRTY@@PEAJPEAPEAG3@Z`
- size: `771`
- prototype: `int(CBsString *__hidden this, int, unsigned int, const struct ___FORMAT_ERRORCODE_SEARCH_DLL_ENTRY *, unsigned int, const struct ___FORMAT_ERRORCODE_ERROR_MAP_ENTRTY *, int *, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, service_task`

## callers

- `0x180099d94`

## callees

- `0x180009ac8`
- `0x18008f3b0`
- `0x18009ab28`

## import_xrefs

- `msvcrt!iswspace` at `0x18009ad90`
- `msvcrt!iswspace` at `0x18009addc`
- `msvcrt!iswspace` at `0x18009ad90`
- `msvcrt!iswspace` at `0x18009addc`
- `KERNEL32!FreeLibrary` at `0x18009ae00`
- `KERNEL32!FreeLibrary` at `0x18009ae00`
- `KERNEL32!FormatMessageW` at `0x18009acf5`
- `KERNEL32!FormatMessageW` at `0x18009acf5`
- `KERNEL32!GetModuleHandleW` at `0x18009ab9f`
- `KERNEL32!GetModuleHandleW` at `0x18009ab9f`
- `ole32!CoTaskMemFree` at `0x18009ae0f`
- `ole32!CoTaskMemFree` at `0x18009ae0f`
- `ole32!CoTaskMemAlloc` at `0x18009ad28`
- `ole32!CoTaskMemAlloc` at `0x18009ad28`

## string_xrefs

- `0x18009ab98`: `ntdll.dll`
- `0x18009abc0`: `netmsg.dll`

## pseudocode

```c
__int64 __fastcall CBsString::_GetErrorText(
        CBsString *this,
        void *a2,
        __int64 a3,
        const struct ___FORMAT_ERRORCODE_SEARCH_DLL_ENTRY *a4,
        unsigned int a5,
        const struct ___FORMAT_ERRORCODE_ERROR_MAP_ENTRTY *a6,
        int *a7,
        unsigned __int16 **a8,
        unsigned __int16 **a9)
{
  int v9; // esi
  int v10; // edi
  HINSTANCE v11; // r15
  __int64 v12; // rbx
  HMODULE ModuleHandleW; // rax
  HINSTANCE System32Library; // rax
  unsigned int i; // eax
  int v16; // edx
  DWORD v17; // r14d
  unsigned int j; // eax
  __int64 v19; // rcx
  __int64 v20; // rdi
  unsigned __int16 *v21; // r14
  const unsigned __int16 *v22; // rbx
  __int64 v23; // rax
  __int64 v24; // rdi
  unsigned __int16 *v25; // rax
  int v26; // ebx
  unsigned __int16 *v27; // r11
  const unsigned __int16 *v28; // rcx
  int v29; // eax
  const unsigned __int16 *v30; // rcx
  wint_t v31; // ax
  WCHAR Buffer[4]; // [rsp+40h] [rbp-41h] BYREF
  int v34; // [rsp+48h] [rbp-39h]
  int v35; // [rsp+4Ch] [rbp-35h]
  unsigned __int16 **v36; // [rsp+50h] [rbp-31h]
  LPCVOID lpSource[2]; // [rsp+58h] [rbp-29h]
  __int128 v38; // [rsp+68h] [rbp-19h]

  v9 = 0;
  v10 = (int)a2;
  v36 = a8;
  v11 = 0;
  v35 = 0;
  LODWORD(v12) = 0;
  *(_QWORD *)Buffer = 0;
  v34 = 0;
  *(_OWORD *)lpSource = 0;
  v38 = 0;
  if ( a7 )
    *a7 = 0;
  if ( a8 )
    *a8 = 0;
  if ( a9 )
    *a9 = 0;
  if ( !CBsString::s_hModuleNTDLL )
  {
    ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
    if ( ModuleHandleW )
      CBsString::s_hModuleNTDLL = ModuleHandleW;
  }
  if ( !CBsString::s_hModuleNetMsg )
  {
    System32Library = SxLoadSystem32LibraryEx(L"netmsg.dll", a2, 2u);
    if ( System32Library )
      CBsString::s_hModuleNetMsg = System32Library;
  }
  for ( i = 0; i < 3; ++i )
  {
    if ( *((_DWORD *)&g_rgStdMappedErrors + 2 * i) == v10 )
    {
      _mm_lfence();
      v34 = v10;
      v10 = dword_1800FCE64[2 * i];
      break;
    }
  }
  if ( (v10 & 0xFFFF0000) == 0x80070000 )
  {
    v16 = 0;
    v17 = v10;
  }
  else
  {
    if ( (v10 & 0x10000000) != 0 || (v10 & 0xC0000000) == 0xC0000000 )
    {
      lpSource[0] = CBsString::s_hModuleNTDLL;
      v17 = v10 & 0xEFFFFFFF;
      LODWORD(v12) = 1;
    }
    else
    {
      v17 = 0;
    }
    if ( (v10 & 0x10000000) != 0 )
    {
LABEL_32:
      v16 = v12;
    }
    else
    {
      v17 = v10;
      for ( j = 0; ; ++j )
      {
        v16 = v12;
        if ( j >= 4 )
          break;
        if ( v10 <= dword_1800D5A0C[4 * j] && v10 >= dword_1800D5A08[4 * j] )
        {
          v11 = SxLoadSystem32LibraryEx((&off_1800D5A00)[2 * j], (void *)(unsigned int)v12, 2u);
          if ( !v11 )
            goto LABEL_32;
          lpSource[(unsigned int)v12] = v11;
          goto LABEL_35;
        }
      }
    }
  }
  v19 = (unsigned int)v12;
  v12 = (unsigned int)(v12 + 1);
  lpSource[v19] = CBsString::s_hModuleNetMsg;
  if ( !v16 )
  {
    lpSource[v12] = CBsString::s_hModuleNTDLL;
LABEL_35:
    LODWORD(v12) = v12 + 1;
  }
  if ( (_DWORD)v12 )
  {
    while ( 1 )
    {
      LODWORD(v20) = FormatMessageW(0x1BFFu, lpSource[v9], v17, 0, Buffer, 1u, 0);
      if ( (_DWORD)v20 )
        break;
      if ( ++v9 >= (unsigned int)v12 )
        goto LABEL_39;
    }
    v28 = *(const unsigned __int16 **)Buffer;
    v21 = L" ";
    v22 = *(const unsigned __int16 **)Buffer;
    while ( 1 )
    {
      if ( !(_DWORD)v20 )
        goto LABEL_40;
      v20 = (unsigned int)(v20 - 1);
      v29 = iswspace(v28[(unsigned int)v20]);
      v30 = *(const unsigned __int16 **)Buffer;
      if ( !v29 && *(_WORD *)(*(_QWORD *)Buffer + 2LL * (unsigned int)v20) >= 0x20u )
        break;
      *(_WORD *)(*(_QWORD *)Buffer + 2LL * (unsigned int)v20) = 0;
      v28 = *(const unsigned __int16 **)Buffer;
    }
    v22 = (const unsigned __int16 *)(*(_QWORD *)Buffer + 2 * v20);
    while ( 1 )
    {
      if ( !(_DWORD)v20 )
        goto LABEL_40;
      v20 = (unsigned int)(v20 - 1);
      v31 = v30[v20];
      if ( v31 < 0x20u )
        break;
      if ( iswspace(v31) )
      {
LABEL_56:
        v30 = *(const unsigned __int16 **)Buffer;
      }
      else
      {
        v30 = *(const unsigned __int16 **)Buffer;
        v22 = (const unsigned __int16 *)(*(_QWORD *)Buffer + 2 * v20);
      }
    }
    v30[v20] = 32;
    goto LABEL_56;
  }
LABEL_39:
  v21 = (unsigned __int16 *)&Data;
  v22 = (const unsigned __int16 *)&Data;
LABEL_40:
  v23 = -1;
  do
    ++v23;
  while ( v22[v23] );
  v24 = (unsigned int)(v23 + 1);
  v25 = (unsigned __int16 *)CoTaskMemAlloc(2 * v24);
  if ( v25 )
  {
    v26 = StringCchCopyW(v25, (unsigned int)v24, v22);
    if ( v26 >= 0 )
    {
      *v36 = v27;
      if ( a9 )
        *a9 = v21;
      if ( a7 )
        *a7 = v34;
    }
  }
  else
  {
    v26 = v35;
  }
  if ( v11 )
    FreeLibrary(v11);
  if ( *(_QWORD *)Buffer )
    CoTaskMemFree(*(LPVOID *)Buffer);
  return (unsigned int)v26;
}

```

## disassembly

```asm
0x18009ab28  push    rbp
0x18009ab2a  push    rbx
0x18009ab2b  push    rsi
0x18009ab2c  push    rdi
0x18009ab2d  push    r12
0x18009ab2f  push    r13
0x18009ab31  push    r14
0x18009ab33  push    r15
0x18009ab35  lea     rbp, [rsp-7]
0x18009ab3a  sub     rsp, 88h
0x18009ab41  mov     r13, [rbp+3Fh+arg_30]
0x18009ab45  xor     esi, esi
0x18009ab47  mov     rax, [rbp+3Fh+arg_38]
0x18009ab4e  xorps   xmm0, xmm0
0x18009ab51  mov     r12, [rbp+3Fh+arg_40]
0x18009ab58  mov     edi, edx
0x18009ab5a  mov     [rbp+3Fh+var_70], rax
0x18009ab5e  mov     r15d, esi
0x18009ab61  mov     [rbp+3Fh+var_74], esi
0x18009ab64  mov     ebx, esi
0x18009ab66  mov     qword ptr [rbp+3Fh+Buffer], rsi
0x18009ab6a  mov     [rbp+3Fh+var_78], esi
0x18009ab6d  movups  xmmword ptr [rbp+3Fh+lpSource], xmm0
0x18009ab71  movups  [rbp+3Fh+var_58], xmm0
0x18009ab75  test    r13, r13
0x18009ab78  jz      short loc_18009AB7E
0x18009ab7a  mov     [r13+0], esi
0x18009ab7e  test    rax, rax
0x18009ab81  jz      short loc_18009AB86
0x18009ab83  mov     [rax], rsi
0x18009ab86  test    r12, r12
0x18009ab89  jz      short loc_18009AB8F
0x18009ab8b  mov     [r12], rsi
0x18009ab8f  cmp     cs:?s_hModuleNTDLL@CBsString@@0PEAUHINSTANCE__@@EA, rsi; HINSTANCE__ * CBsString::s_hModuleNTDLL
0x18009ab96  jnz     short loc_18009ABB1
0x18009ab98  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18009ab9f  call    cs:__imp_GetModuleHandleW
0x18009aba5  test    rax, rax
0x18009aba8  jz      short loc_18009ABB1
0x18009abaa  mov     cs:?s_hModuleNTDLL@CBsString@@0PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * CBsString::s_hModuleNTDLL
0x18009abb1  cmp     cs:?s_hModuleNetMsg@CBsString@@0PEAUHINSTANCE__@@EA, rsi; HINSTANCE__ * CBsString::s_hModuleNetMsg
0x18009abb8  jnz     short loc_18009ABD8
0x18009abba  mov     r8d, 2; unsigned int
0x18009abc0  lea     rcx, aNetmsgDll; "netmsg.dll"
0x18009abc7  call    ?SxLoadSystem32LibraryEx@@YAPEAUHINSTANCE__@@PEBGPEAXK@Z; SxLoadSystem32LibraryEx(ushort const *,void *,ulong)
0x18009abcc  test    rax, rax
0x18009abcf  jz      short loc_18009ABD8
0x18009abd1  mov     cs:?s_hModuleNetMsg@CBsString@@0PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * CBsString::s_hModuleNetMsg
0x18009abd8  mov     eax, esi
0x18009abda  lea     r9, __ImageBase
0x18009abe1  cmp     eax, 3
0x18009abe4  jnb     short loc_18009AC04
0x18009abe6  mov     ecx, eax
0x18009abe8  cmp     rva ?g_rgStdMappedErrors@@3PAU___FORMAT_ERRORCODE_ERROR_MAP_ENTRTY@@A[r9+rcx*8], edi; ___FORMAT_ERRORCODE_ERROR_MAP_ENTRTY near * g_rgStdMappedErrors ...
0x18009abf0  jz      short loc_18009ABF6
0x18009abf2  inc     eax
0x18009abf4  jmp     short loc_18009ABE1
0x18009abf6  lfence
0x18009abf9  mov     [rbp+3Fh+var_78], edi
0x18009abfc  mov     edi, rva dword_1800FCE64[r9+rcx*8]
0x18009ac04  mov     eax, edi
0x18009ac06  and     eax, 0FFFF0000h
0x18009ac0b  cmp     eax, 80070000h
0x18009ac10  jnz     short loc_18009AC1C
0x18009ac12  mov     edx, esi
0x18009ac14  mov     r14d, edi
0x18009ac17  jmp     loc_18009ACA3
0x18009ac1c  mov     ecx, edi
0x18009ac1e  and     ecx, 10000000h
0x18009ac24  jnz     short loc_18009AC38
0x18009ac26  mov     edx, 0C0000000h
0x18009ac2b  mov     eax, edi
0x18009ac2d  and     eax, edx
0x18009ac2f  cmp     eax, edx
0x18009ac31  jz      short loc_18009AC38
0x18009ac33  mov     r14d, esi
0x18009ac36  jmp     short loc_18009AC50
0x18009ac38  mov     rax, cs:?s_hModuleNTDLL@CBsString@@0PEAUHINSTANCE__@@EA; HINSTANCE__ * CBsString::s_hModuleNTDLL
0x18009ac3f  mov     r14d, edi
0x18009ac42  mov     [rbp+3Fh+lpSource], rax
0x18009ac46  btr     r14d, 1Ch
0x18009ac4b  mov     ebx, 1
0x18009ac50  test    ecx, ecx
0x18009ac52  jnz     short loc_18009ACA1
0x18009ac54  mov     r14d, edi
0x18009ac57  mov     eax, esi
0x18009ac59  mov     edx, ebx; void *
0x18009ac5b  cmp     eax, 4
0x18009ac5e  jnb     short loc_18009ACA3
0x18009ac60  mov     ecx, eax
0x18009ac62  add     rcx, rcx
0x18009ac65  cmp     edi, ds:rva dword_1800D5A0C[r9+rcx*8]
0x18009ac6d  jg      short loc_18009AC79
0x18009ac6f  cmp     edi, ds:rva dword_1800D5A08[r9+rcx*8]
0x18009ac77  jge     short loc_18009AC7D
0x18009ac79  inc     eax
0x18009ac7b  jmp     short loc_18009AC59
0x18009ac7d  mov     rcx, ds:rva off_1800D5A00[r9+rcx*8]; unsigned __int16 *
0x18009ac85  mov     r8d, 2; unsigned int
0x18009ac8b  call    ?SxLoadSystem32LibraryEx@@YAPEAUHINSTANCE__@@PEBGPEAXK@Z; SxLoadSystem32LibraryEx(ushort const *,void *,ulong)
0x18009ac90  mov     r15, rax
0x18009ac93  test    rax, rax
0x18009ac96  jz      short loc_18009ACA1
0x18009ac98  mov     eax, ebx
0x18009ac9a  mov     [rbp+rax*8+3Fh+lpSource], r15
0x18009ac9f  jmp     short loc_18009ACC3
0x18009aca1  mov     edx, ebx
0x18009aca3  mov     rax, cs:?s_hModuleNetMsg@CBsString@@0PEAUHINSTANCE__@@EA; HINSTANCE__ * CBsString::s_hModuleNetMsg
0x18009acaa  mov     ecx, ebx
0x18009acac  inc     ebx
0x18009acae  mov     [rbp+rcx*8+3Fh+lpSource], rax
0x18009acb3  test    edx, edx
0x18009acb5  jnz     short loc_18009ACC5
0x18009acb7  mov     rax, cs:?s_hModuleNTDLL@CBsString@@0PEAUHINSTANCE__@@EA; HINSTANCE__ * CBsString::s_hModuleNTDLL
0x18009acbe  mov     [rbp+rbx*8+3Fh+lpSource], rax
0x18009acc3  inc     ebx
0x18009acc5  test    ebx, ebx
0x18009acc7  jz      short loc_18009AD07
0x18009acc9  mov     [rsp+0C0h+Arguments], 0; Arguments
0x18009acd2  lea     rax, [rbp+3Fh+Buffer]
0x18009acd6  mov     edx, esi
0x18009acd8  xor     r9d, r9d; dwLanguageId
0x18009acdb  mov     [rsp+0C0h+nSize], 1; nSize
0x18009ace3  mov     r8d, r14d; dwMessageId
0x18009ace6  mov     ecx, 1BFFh; dwFlags
0x18009aceb  mov     [rsp+0C0h+lpBuffer], rax; lpBuffer
0x18009acf0  mov     rdx, [rbp+rdx*8+3Fh+lpSource]; lpSource
0x18009acf5  call    cs:__imp_FormatMessageW
0x18009acfb  mov     edi, eax
0x18009acfd  test    eax, eax
0x18009acff  jnz     short loc_18009AD76
0x18009ad01  inc     esi
0x18009ad03  cmp     esi, ebx
0x18009ad05  jb      short loc_18009ACC9
0x18009ad07  lea     r14, Data
0x18009ad0e  xor     esi, esi
0x18009ad10  mov     rbx, r14
0x18009ad13  or      rax, 0FFFFFFFFFFFFFFFFh
0x18009ad17  inc     rax
0x18009ad1a  cmp     [rbx+rax*2], si
0x18009ad1e  jnz     short loc_18009AD17
0x18009ad20  inc     eax
0x18009ad22  mov     edi, eax
0x18009ad24  lea     rcx, [rax+rax]; cb
0x18009ad28  call    cs:__imp_CoTaskMemAlloc
0x18009ad2e  mov     r11, rax
0x18009ad31  test    rax, rax
0x18009ad34  jz      loc_18009ADF5
0x18009ad3a  mov     r8, rbx; unsigned __int16 *
0x18009ad3d  mov     edx, edi; unsigned __int64
0x18009ad3f  mov     rcx, rax; unsigned __int16 *
0x18009ad42  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18009ad47  mov     ebx, eax
0x18009ad49  test    eax, eax
0x18009ad4b  js      loc_18009ADF8
0x18009ad51  mov     rcx, [rbp+3Fh+var_70]
0x18009ad55  mov     [rcx], r11
0x18009ad58  test    r12, r12
0x18009ad5b  jz      short loc_18009AD61
0x18009ad5d  mov     [r12], r14
0x18009ad61  test    r13, r13
0x18009ad64  jz      loc_18009ADF8
0x18009ad6a  mov     eax, [rbp+3Fh+var_78]
0x18009ad6d  mov     [r13+0], eax
0x18009ad71  jmp     loc_18009ADF8
0x18009ad76  mov     rcx, qword ptr [rbp+3Fh+Buffer]
0x18009ad7a  lea     r14, asc_1800E3F2C; " "
0x18009ad81  mov     rbx, rcx
0x18009ad84  xor     esi, esi
0x18009ad86  test    edi, edi
0x18009ad88  jz      short loc_18009AD13
0x18009ad8a  dec     edi
0x18009ad8c  movzx   ecx, word ptr [rcx+rdi*2]; C
0x18009ad90  call    cs:__imp_iswspace
0x18009ad96  mov     rcx, qword ptr [rbp+3Fh+Buffer]
0x18009ad9a  test    eax, eax
0x18009ad9c  jnz     short loc_18009ADAA
0x18009ad9e  lea     rax, [rcx+rdi*2]
0x18009ada2  lea     edx, [rsi+20h]
0x18009ada5  cmp     [rax], dx
0x18009ada8  jnb     short loc_18009ADB6
0x18009adaa  xor     eax, eax
0x18009adac  mov     [rcx+rdi*2], ax
0x18009adb0  mov     rcx, qword ptr [rbp+3Fh+Buffer]
0x18009adb4  jmp     short loc_18009AD84
0x18009adb6  mov     rbx, rax
0x18009adb9  jmp     short loc_18009ADD0
0x18009adbb  dec     edi
0x18009adbd  movzx   eax, word ptr [rcx+rdi*2]
0x18009adc1  cmp     ax, dx
0x18009adc4  jnb     short loc_18009ADD9
0x18009adc6  mov     [rcx+rdi*2], dx
0x18009adca  mov     rcx, qword ptr [rbp+3Fh+Buffer]
0x18009adce  xor     esi, esi
0x18009add0  test    edi, edi
0x18009add2  jnz     short loc_18009ADBB
0x18009add4  jmp     loc_18009AD13
0x18009add9  movzx   ecx, ax; C
0x18009addc  call    cs:__imp_iswspace
0x18009ade2  mov     edx, 20h ; ' '
0x18009ade7  test    eax, eax
0x18009ade9  jnz     short loc_18009ADCA
0x18009adeb  mov     rcx, qword ptr [rbp+3Fh+Buffer]
0x18009adef  lea     rbx, [rcx+rdi*2]
0x18009adf3  jmp     short loc_18009ADCE
0x18009adf5  mov     ebx, [rbp+3Fh+var_74]
0x18009adf8  test    r15, r15
0x18009adfb  jz      short loc_18009AE06
0x18009adfd  mov     rcx, r15; hLibModule
0x18009ae00  call    cs:__imp_FreeLibrary
0x18009ae06  mov     rcx, qword ptr [rbp+3Fh+Buffer]; pv
0x18009ae0a  test    rcx, rcx
0x18009ae0d  jz      short loc_18009AE15
0x18009ae0f  call    cs:__imp_CoTaskMemFree
0x18009ae15  mov     eax, ebx
0x18009ae17  add     rsp, 88h
0x18009ae1e  pop     r15
0x18009ae20  pop     r14
0x18009ae22  pop     r13
0x18009ae24  pop     r12
0x18009ae26  pop     rdi
0x18009ae27  pop     rsi
0x18009ae28  pop     rbx
0x18009ae29  pop     rbp
0x18009ae2a  retn
```
