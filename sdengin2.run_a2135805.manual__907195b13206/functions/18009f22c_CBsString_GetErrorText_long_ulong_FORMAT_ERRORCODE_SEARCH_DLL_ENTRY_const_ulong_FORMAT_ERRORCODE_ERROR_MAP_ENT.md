# CBsString::_GetErrorText(long,ulong,___FORMAT_ERRORCODE_SEARCH_DLL_ENTRY const *,ulong,___FORMAT_ERRORCODE_ERROR_MAP_ENTRTY const *,long *,ushort * *,ushort * *)

- ea: `0x18009f22c`
- end: `0x18009f55a`
- name: `?_GetErrorText@CBsString@@AEAAJJKPEBU___FORMAT_ERRORCODE_SEARCH_DLL_ENTRY@@KPEBU___FORMAT_ERRORCODE_ERROR_MAP_ENTRTY@@PEAJPEAPEAG3@Z`
- size: `814`
- prototype: `int(CBsString *__hidden this, int, unsigned int, const struct ___FORMAT_ERRORCODE_SEARCH_DLL_ENTRY *, unsigned int, const struct ___FORMAT_ERRORCODE_ERROR_MAP_ENTRTY *, int *, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, service_task`

## callers

- `0x18009e404`

## callees

- `0x180009d44`
- `0x1800933b4`
- `0x18009f22c`

## import_xrefs

- `msvcrt!iswspace` at `0x18009f4a6`
- `msvcrt!iswspace` at `0x18009f4f8`
- `msvcrt!iswspace` at `0x18009f4a6`
- `msvcrt!iswspace` at `0x18009f4f8`
- `KERNEL32!FreeLibrary` at `0x18009f522`
- `KERNEL32!FreeLibrary` at `0x18009f522`
- `KERNEL32!FormatMessageW` at `0x18009f3ff`
- `KERNEL32!FormatMessageW` at `0x18009f3ff`
- `KERNEL32!GetModuleHandleW` at `0x18009f2a3`
- `KERNEL32!GetModuleHandleW` at `0x18009f2a3`
- `ole32!CoTaskMemFree` at `0x18009f537`
- `ole32!CoTaskMemFree` at `0x18009f537`
- `ole32!CoTaskMemAlloc` at `0x18009f438`
- `ole32!CoTaskMemAlloc` at `0x18009f438`

## string_xrefs

- `0x18009f29c`: `ntdll.dll`
- `0x18009f2ca`: `netmsg.dll`

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
      v10 = dword_180102F64[2 * i];
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
        if ( v10 <= dword_1800DB9FC[4 * j] && v10 >= dword_1800DB9F8[4 * j] )
        {
          v11 = SxLoadSystem32LibraryEx((&off_1800DB9F0)[2 * j], (void *)(unsigned int)v12, 2u);
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
0x18009f22c  push    rbp
0x18009f22e  push    rbx
0x18009f22f  push    rsi
0x18009f230  push    rdi
0x18009f231  push    r12
0x18009f233  push    r13
0x18009f235  push    r14
0x18009f237  push    r15
0x18009f239  lea     rbp, [rsp-7]
0x18009f23e  sub     rsp, 88h
0x18009f245  mov     r13, [rbp+3Fh+arg_30]
0x18009f249  xor     esi, esi
0x18009f24b  mov     rax, [rbp+3Fh+arg_38]
0x18009f252  xorps   xmm0, xmm0
0x18009f255  mov     r12, [rbp+3Fh+arg_40]
0x18009f25c  mov     edi, edx
0x18009f25e  mov     [rbp+3Fh+var_70], rax
0x18009f262  mov     r15d, esi
0x18009f265  mov     [rbp+3Fh+var_74], esi
0x18009f268  mov     ebx, esi
0x18009f26a  mov     qword ptr [rbp+3Fh+Buffer], rsi
0x18009f26e  mov     [rbp+3Fh+var_78], esi
0x18009f271  movups  xmmword ptr [rbp+3Fh+lpSource], xmm0
0x18009f275  movups  [rbp+3Fh+var_58], xmm0
0x18009f279  test    r13, r13
0x18009f27c  jz      short loc_18009F282
0x18009f27e  mov     [r13+0], esi
0x18009f282  test    rax, rax
0x18009f285  jz      short loc_18009F28A
0x18009f287  mov     [rax], rsi
0x18009f28a  test    r12, r12
0x18009f28d  jz      short loc_18009F293
0x18009f28f  mov     [r12], rsi
0x18009f293  cmp     cs:?s_hModuleNTDLL@CBsString@@0PEAUHINSTANCE__@@EA, rsi; HINSTANCE__ * CBsString::s_hModuleNTDLL
0x18009f29a  jnz     short loc_18009F2BB
0x18009f29c  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18009f2a3  call    cs:__imp_GetModuleHandleW
0x18009f2aa  nop     dword ptr [rax+rax+00h]
0x18009f2af  test    rax, rax
0x18009f2b2  jz      short loc_18009F2BB
0x18009f2b4  mov     cs:?s_hModuleNTDLL@CBsString@@0PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * CBsString::s_hModuleNTDLL
0x18009f2bb  cmp     cs:?s_hModuleNetMsg@CBsString@@0PEAUHINSTANCE__@@EA, rsi; HINSTANCE__ * CBsString::s_hModuleNetMsg
0x18009f2c2  jnz     short loc_18009F2E2
0x18009f2c4  mov     r8d, 2; unsigned int
0x18009f2ca  lea     rcx, aNetmsgDll; "netmsg.dll"
0x18009f2d1  call    ?SxLoadSystem32LibraryEx@@YAPEAUHINSTANCE__@@PEBGPEAXK@Z; SxLoadSystem32LibraryEx(ushort const *,void *,ulong)
0x18009f2d6  test    rax, rax
0x18009f2d9  jz      short loc_18009F2E2
0x18009f2db  mov     cs:?s_hModuleNetMsg@CBsString@@0PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * CBsString::s_hModuleNetMsg
0x18009f2e2  mov     eax, esi
0x18009f2e4  lea     r9, __ImageBase
0x18009f2eb  cmp     eax, 3
0x18009f2ee  jnb     short loc_18009F30E
0x18009f2f0  mov     ecx, eax
0x18009f2f2  cmp     rva ?g_rgStdMappedErrors@@3PAU___FORMAT_ERRORCODE_ERROR_MAP_ENTRTY@@A[r9+rcx*8], edi; ___FORMAT_ERRORCODE_ERROR_MAP_ENTRTY near * g_rgStdMappedErrors ...
0x18009f2fa  jz      short loc_18009F300
0x18009f2fc  inc     eax
0x18009f2fe  jmp     short loc_18009F2EB
0x18009f300  lfence
0x18009f303  mov     [rbp+3Fh+var_78], edi
0x18009f306  mov     edi, rva dword_180102F64[r9+rcx*8]
0x18009f30e  mov     eax, edi
0x18009f310  and     eax, 0FFFF0000h
0x18009f315  cmp     eax, 80070000h
0x18009f31a  jnz     short loc_18009F326
0x18009f31c  mov     edx, esi
0x18009f31e  mov     r14d, edi
0x18009f321  jmp     loc_18009F3AD
0x18009f326  mov     ecx, edi
0x18009f328  and     ecx, 10000000h
0x18009f32e  jnz     short loc_18009F342
0x18009f330  mov     edx, 0C0000000h
0x18009f335  mov     eax, edi
0x18009f337  and     eax, edx
0x18009f339  cmp     eax, edx
0x18009f33b  jz      short loc_18009F342
0x18009f33d  mov     r14d, esi
0x18009f340  jmp     short loc_18009F35A
0x18009f342  mov     rax, cs:?s_hModuleNTDLL@CBsString@@0PEAUHINSTANCE__@@EA; HINSTANCE__ * CBsString::s_hModuleNTDLL
0x18009f349  mov     r14d, edi
0x18009f34c  mov     [rbp+3Fh+lpSource], rax
0x18009f350  btr     r14d, 1Ch
0x18009f355  mov     ebx, 1
0x18009f35a  test    ecx, ecx
0x18009f35c  jnz     short loc_18009F3AB
0x18009f35e  mov     r14d, edi
0x18009f361  mov     eax, esi
0x18009f363  mov     edx, ebx; void *
0x18009f365  cmp     eax, 4
0x18009f368  jnb     short loc_18009F3AD
0x18009f36a  mov     ecx, eax
0x18009f36c  add     rcx, rcx
0x18009f36f  cmp     edi, ds:rva dword_1800DB9FC[r9+rcx*8]
0x18009f377  jg      short loc_18009F383
0x18009f379  cmp     edi, ds:rva dword_1800DB9F8[r9+rcx*8]
0x18009f381  jge     short loc_18009F387
0x18009f383  inc     eax
0x18009f385  jmp     short loc_18009F363
0x18009f387  mov     rcx, ds:rva off_1800DB9F0[r9+rcx*8]; unsigned __int16 *
0x18009f38f  mov     r8d, 2; unsigned int
0x18009f395  call    ?SxLoadSystem32LibraryEx@@YAPEAUHINSTANCE__@@PEBGPEAXK@Z; SxLoadSystem32LibraryEx(ushort const *,void *,ulong)
0x18009f39a  mov     r15, rax
0x18009f39d  test    rax, rax
0x18009f3a0  jz      short loc_18009F3AB
0x18009f3a2  mov     eax, ebx
0x18009f3a4  mov     [rbp+rax*8+3Fh+lpSource], r15
0x18009f3a9  jmp     short loc_18009F3CD
0x18009f3ab  mov     edx, ebx
0x18009f3ad  mov     rax, cs:?s_hModuleNetMsg@CBsString@@0PEAUHINSTANCE__@@EA; HINSTANCE__ * CBsString::s_hModuleNetMsg
0x18009f3b4  mov     ecx, ebx
0x18009f3b6  inc     ebx
0x18009f3b8  mov     [rbp+rcx*8+3Fh+lpSource], rax
0x18009f3bd  test    edx, edx
0x18009f3bf  jnz     short loc_18009F3CF
0x18009f3c1  mov     rax, cs:?s_hModuleNTDLL@CBsString@@0PEAUHINSTANCE__@@EA; HINSTANCE__ * CBsString::s_hModuleNTDLL
0x18009f3c8  mov     [rbp+rbx*8+3Fh+lpSource], rax
0x18009f3cd  inc     ebx
0x18009f3cf  test    ebx, ebx
0x18009f3d1  jz      short loc_18009F417
0x18009f3d3  mov     [rsp+0C0h+Arguments], 0; Arguments
0x18009f3dc  lea     rax, [rbp+3Fh+Buffer]
0x18009f3e0  mov     edx, esi
0x18009f3e2  xor     r9d, r9d; dwLanguageId
0x18009f3e5  mov     [rsp+0C0h+nSize], 1; nSize
0x18009f3ed  mov     r8d, r14d; dwMessageId
0x18009f3f0  mov     ecx, 1BFFh; dwFlags
0x18009f3f5  mov     [rsp+0C0h+lpBuffer], rax; lpBuffer
0x18009f3fa  mov     rdx, [rbp+rdx*8+3Fh+lpSource]; lpSource
0x18009f3ff  call    cs:__imp_FormatMessageW
0x18009f406  nop     dword ptr [rax+rax+00h]
0x18009f40b  mov     edi, eax
0x18009f40d  test    eax, eax
0x18009f40f  jnz     short loc_18009F48C
0x18009f411  inc     esi
0x18009f413  cmp     esi, ebx
0x18009f415  jb      short loc_18009F3D3
0x18009f417  lea     r14, Data
0x18009f41e  xor     esi, esi
0x18009f420  mov     rbx, r14
0x18009f423  or      rax, 0FFFFFFFFFFFFFFFFh
0x18009f427  inc     rax
0x18009f42a  cmp     [rbx+rax*2], si
0x18009f42e  jnz     short loc_18009F427
0x18009f430  inc     eax
0x18009f432  mov     edi, eax
0x18009f434  lea     rcx, [rax+rax]; cb
0x18009f438  call    cs:__imp_CoTaskMemAlloc
0x18009f43f  nop     dword ptr [rax+rax+00h]
0x18009f444  mov     r11, rax
0x18009f447  test    rax, rax
0x18009f44a  jz      loc_18009F517
0x18009f450  mov     r8, rbx; unsigned __int16 *
0x18009f453  mov     edx, edi; unsigned __int64
0x18009f455  mov     rcx, rax; unsigned __int16 *
0x18009f458  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18009f45d  mov     ebx, eax
0x18009f45f  test    eax, eax
0x18009f461  js      loc_18009F51A
0x18009f467  mov     rcx, [rbp+3Fh+var_70]
0x18009f46b  mov     [rcx], r11
0x18009f46e  test    r12, r12
0x18009f471  jz      short loc_18009F477
0x18009f473  mov     [r12], r14
0x18009f477  test    r13, r13
0x18009f47a  jz      loc_18009F51A
0x18009f480  mov     eax, [rbp+3Fh+var_78]
0x18009f483  mov     [r13+0], eax
0x18009f487  jmp     loc_18009F51A
0x18009f48c  mov     rcx, qword ptr [rbp+3Fh+Buffer]
0x18009f490  lea     r14, asc_1800E9F0C; " "
0x18009f497  mov     rbx, rcx
0x18009f49a  xor     esi, esi
0x18009f49c  test    edi, edi
0x18009f49e  jz      short loc_18009F423
0x18009f4a0  dec     edi
0x18009f4a2  movzx   ecx, word ptr [rcx+rdi*2]; C
0x18009f4a6  call    cs:__imp_iswspace
0x18009f4ad  nop     dword ptr [rax+rax+00h]
0x18009f4b2  mov     rcx, qword ptr [rbp+3Fh+Buffer]
0x18009f4b6  test    eax, eax
0x18009f4b8  jnz     short loc_18009F4C6
0x18009f4ba  lea     rax, [rcx+rdi*2]
0x18009f4be  lea     edx, [rsi+20h]
0x18009f4c1  cmp     [rax], dx
0x18009f4c4  jnb     short loc_18009F4D2
0x18009f4c6  xor     eax, eax
0x18009f4c8  mov     [rcx+rdi*2], ax
0x18009f4cc  mov     rcx, qword ptr [rbp+3Fh+Buffer]
0x18009f4d0  jmp     short loc_18009F49A
0x18009f4d2  mov     rbx, rax
0x18009f4d5  jmp     short loc_18009F4EC
0x18009f4d7  dec     edi
0x18009f4d9  movzx   eax, word ptr [rcx+rdi*2]
0x18009f4dd  cmp     ax, dx
0x18009f4e0  jnb     short loc_18009F4F5
0x18009f4e2  mov     [rcx+rdi*2], dx
0x18009f4e6  mov     rcx, qword ptr [rbp+3Fh+Buffer]
0x18009f4ea  xor     esi, esi
0x18009f4ec  test    edi, edi
0x18009f4ee  jnz     short loc_18009F4D7
0x18009f4f0  jmp     loc_18009F423
0x18009f4f5  movzx   ecx, ax; C
0x18009f4f8  call    cs:__imp_iswspace
0x18009f4ff  nop     dword ptr [rax+rax+00h]
0x18009f504  mov     edx, 20h ; ' '
0x18009f509  test    eax, eax
0x18009f50b  jnz     short loc_18009F4E6
0x18009f50d  mov     rcx, qword ptr [rbp+3Fh+Buffer]
0x18009f511  lea     rbx, [rcx+rdi*2]
0x18009f515  jmp     short loc_18009F4EA
0x18009f517  mov     ebx, [rbp+3Fh+var_74]
0x18009f51a  test    r15, r15
0x18009f51d  jz      short loc_18009F52E
0x18009f51f  mov     rcx, r15; hLibModule
0x18009f522  call    cs:__imp_FreeLibrary
0x18009f529  nop     dword ptr [rax+rax+00h]
0x18009f52e  mov     rcx, qword ptr [rbp+3Fh+Buffer]; pv
0x18009f532  test    rcx, rcx
0x18009f535  jz      short loc_18009F543
0x18009f537  call    cs:__imp_CoTaskMemFree
0x18009f53e  nop     dword ptr [rax+rax+00h]
0x18009f543  mov     eax, ebx
0x18009f545  add     rsp, 88h
0x18009f54c  pop     r15
0x18009f54e  pop     r14
0x18009f550  pop     r13
0x18009f552  pop     r12
0x18009f554  pop     rdi
0x18009f555  pop     rsi
0x18009f556  pop     rbx
0x18009f557  pop     rbp
0x18009f558  retn
```
