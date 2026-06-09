# CBsString::_GetErrorText(long,ulong,___FORMAT_ERRORCODE_SEARCH_DLL_ENTRY const *,ulong,___FORMAT_ERRORCODE_ERROR_MAP_ENTRTY const *,long *,ushort * *,ushort * *)

- ea: `0x180020184`
- end: `0x18002047f`
- name: `?_GetErrorText@CBsString@@AEAAJJKPEBU___FORMAT_ERRORCODE_SEARCH_DLL_ENTRY@@KPEBU___FORMAT_ERRORCODE_ERROR_MAP_ENTRTY@@PEAJPEAPEAG3@Z`
- size: `763`
- prototype: `__int64 __fastcall(CBsString *this, __int64, unsigned int, const struct ___FORMAT_ERRORCODE_SEARCH_DLL_ENTRY *, unsigned int, const struct ___FORMAT_ERRORCODE_ERROR_MAP_ENTRTY *, int *, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18001f928`

## callees

- `0x1800076e4`
- `0x18001c28c`
- `0x180020184`

## import_xrefs

- `msvcrt!iswspace` at `0x1800203d6`
- `msvcrt!iswspace` at `0x180020430`
- `msvcrt!iswspace` at `0x1800203d6`
- `msvcrt!iswspace` at `0x180020430`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180020454`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180020454`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800201f7`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800201f7`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800203a8`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800203a8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002032f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002032f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020463`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020463`

## string_xrefs

- `0x1800201f0`: `ntdll.dll`
- `0x180020212`: `netmsg.dll`

## pseudocode

```c
__int64 __fastcall CBsString::_GetErrorText(
        CBsString *this,
        __int64 a2,
        unsigned int a3,
        const struct ___FORMAT_ERRORCODE_SEARCH_DLL_ENTRY *a4,
        unsigned int a5,
        const struct ___FORMAT_ERRORCODE_ERROR_MAP_ENTRTY *a6,
        int *a7,
        unsigned __int16 **a8,
        unsigned __int16 **a9)
{
  signed int v9; // edi
  HMODULE v10; // r15
  __int64 v11; // rbx
  HMODULE ModuleHandleW; // rax
  HINSTANCE System32Library; // rax
  unsigned int v14; // eax
  int v15; // edx
  unsigned int v16; // eax
  __int64 v17; // rcx
  int v18; // esi
  unsigned __int16 *v19; // rsi
  const unsigned __int16 *v20; // rbx
  __int64 v21; // rax
  __int64 v22; // rdi
  unsigned __int16 *v23; // rax
  int v24; // ebx
  unsigned __int16 *v25; // r11
  __int64 v26; // r14
  const unsigned __int16 *v27; // rcx
  int v28; // eax
  const unsigned __int16 *v29; // rcx
  wint_t v30; // ax
  WCHAR Buffer[4]; // [rsp+40h] [rbp-41h] BYREF
  int v33; // [rsp+48h] [rbp-39h]
  unsigned __int16 **v34; // [rsp+50h] [rbp-31h]
  LPCVOID lpSource[2]; // [rsp+58h] [rbp-29h]
  __int128 v36; // [rsp+68h] [rbp-19h]

  v9 = a2;
  v34 = a8;
  v10 = 0;
  *(_QWORD *)Buffer = 0;
  LODWORD(v11) = 0;
  *(_OWORD *)lpSource = 0;
  v36 = 0;
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
    System32Library = SxLoadSystem32LibraryEx(L"netmsg.dll", (void *)a2, a3);
    if ( System32Library )
      CBsString::s_hModuleNetMsg = System32Library;
  }
  v14 = 0;
  while ( *((_DWORD *)&g_rgStdMappedErrors + 2 * v14) != v9 )
  {
    if ( ++v14 >= 3 )
    {
      v33 = 0;
      goto LABEL_18;
    }
  }
  v33 = v9;
  v9 = dword_18002D7E4[2 * v14];
LABEL_18:
  if ( (v9 & 0xFFFF0000) == 0x80070000 )
  {
    v15 = 0;
  }
  else
  {
    if ( (v9 & 0x10000000) == 0 && (a2 = 3221225472LL, (v9 & 0xC0000000) != 0xC0000000)
      || (LODWORD(v11) = 1, lpSource[0] = CBsString::s_hModuleNTDLL, (v9 & 0x10000000) == 0) )
    {
      v16 = 0;
      while ( v9 > dword_1800236CC[4 * v16] || v9 < dword_1800236C8[4 * v16] )
      {
        if ( ++v16 >= 4 )
          goto LABEL_27;
      }
      v10 = SxLoadSystem32LibraryEx((&off_1800236C0)[2 * v16], (void *)a2, (unsigned int)&_ImageBase);
      if ( !v10 )
      {
LABEL_27:
        v15 = v11;
        goto LABEL_31;
      }
      lpSource[(unsigned int)v11] = v10;
      goto LABEL_33;
    }
    v9 &= ~0x10000000u;
    v15 = 1;
  }
LABEL_31:
  v17 = (unsigned int)v11;
  v11 = (unsigned int)(v11 + 1);
  lpSource[v17] = CBsString::s_hModuleNetMsg;
  if ( v15 )
    goto LABEL_34;
  lpSource[v11] = CBsString::s_hModuleNTDLL;
LABEL_33:
  LODWORD(v11) = v11 + 1;
LABEL_34:
  v18 = 0;
  if ( (_DWORD)v11 )
  {
    while ( 1 )
    {
      LODWORD(v26) = FormatMessageW(0x1BFFu, lpSource[v18], v9, 0, Buffer, 1u, 0);
      if ( (_DWORD)v26 )
        break;
      if ( ++v18 >= (unsigned int)v11 )
        goto LABEL_35;
    }
    v27 = *(const unsigned __int16 **)Buffer;
    v19 = L" ";
    v20 = *(const unsigned __int16 **)Buffer;
    while ( 1 )
    {
      v26 = (unsigned int)(v26 - 1);
      v28 = iswspace(v27[(unsigned int)v26]);
      v29 = *(const unsigned __int16 **)Buffer;
      if ( !v28 && *(_WORD *)(*(_QWORD *)Buffer + 2LL * (unsigned int)v26) >= 0x20u )
        break;
      *(_WORD *)(*(_QWORD *)Buffer + 2LL * (unsigned int)v26) = 0;
      if ( !(_DWORD)v26 )
        goto LABEL_36;
      v27 = *(const unsigned __int16 **)Buffer;
    }
    v20 = (const unsigned __int16 *)(*(_QWORD *)Buffer + 2 * v26);
    while ( 1 )
    {
      if ( !(_DWORD)v26 )
        goto LABEL_36;
      v26 = (unsigned int)(v26 - 1);
      v30 = v29[v26];
      if ( v30 < 0x20u )
        break;
      if ( iswspace(v30) )
      {
LABEL_55:
        v29 = *(const unsigned __int16 **)Buffer;
      }
      else
      {
        v29 = *(const unsigned __int16 **)Buffer;
        v20 = (const unsigned __int16 *)(*(_QWORD *)Buffer + 2 * v26);
      }
    }
    v29[v26] = 32;
    goto LABEL_55;
  }
LABEL_35:
  v19 = (unsigned __int16 *)&qword_180025E20;
  v20 = &qword_180025E20;
LABEL_36:
  v21 = -1;
  do
    ++v21;
  while ( v20[v21] );
  v22 = (unsigned int)(v21 + 1);
  v23 = (unsigned __int16 *)CoTaskMemAlloc(2 * v22);
  if ( v23 )
  {
    v24 = StringCchCopyW(v23, (unsigned int)v22, v20);
    if ( v24 >= 0 )
    {
      *v34 = v25;
      if ( a9 )
        *a9 = v19;
      if ( a7 )
        *a7 = v33;
    }
  }
  else
  {
    v24 = 0;
  }
  if ( v10 )
    FreeLibrary(v10);
  if ( *(_QWORD *)Buffer )
    CoTaskMemFree(*(LPVOID *)Buffer);
  return (unsigned int)v24;
}

```

## disassembly

```asm
0x180020184  push    rbp
0x180020186  push    rbx
0x180020187  push    rsi
0x180020188  push    rdi
0x180020189  push    r12
0x18002018b  push    r13
0x18002018d  push    r14
0x18002018f  push    r15
0x180020191  lea     rbp, [rsp-7]
0x180020196  sub     rsp, 88h
0x18002019d  mov     r13, [rbp+3Fh+arg_30]
0x1800201a1  xor     r14d, r14d
0x1800201a4  mov     rax, [rbp+3Fh+arg_38]
0x1800201ab  xorps   xmm0, xmm0
0x1800201ae  mov     r12, [rbp+3Fh+arg_40]
0x1800201b5  mov     edi, edx
0x1800201b7  mov     [rbp+3Fh+var_70], rax
0x1800201bb  mov     r15d, r14d
0x1800201be  mov     qword ptr [rbp+3Fh+Buffer], r14
0x1800201c2  mov     ebx, r14d
0x1800201c5  movups  xmmword ptr [rbp+3Fh+lpSource], xmm0
0x1800201c9  movups  [rbp+3Fh+var_58], xmm0
0x1800201cd  test    r13, r13
0x1800201d0  jz      short loc_1800201D6
0x1800201d2  mov     [r13+0], r14d
0x1800201d6  test    rax, rax
0x1800201d9  jz      short loc_1800201DE
0x1800201db  mov     [rax], r14
0x1800201de  test    r12, r12
0x1800201e1  jz      short loc_1800201E7
0x1800201e3  mov     [r12], r14
0x1800201e7  cmp     cs:?s_hModuleNTDLL@CBsString@@0PEAUHINSTANCE__@@EA, r14; HINSTANCE__ * CBsString::s_hModuleNTDLL
0x1800201ee  jnz     short loc_180020209
0x1800201f0  lea     rcx, ModuleName; "ntdll.dll"
0x1800201f7  call    cs:__imp_GetModuleHandleW
0x1800201fd  test    rax, rax
0x180020200  jz      short loc_180020209
0x180020202  mov     cs:?s_hModuleNTDLL@CBsString@@0PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * CBsString::s_hModuleNTDLL
0x180020209  cmp     cs:?s_hModuleNetMsg@CBsString@@0PEAUHINSTANCE__@@EA, r14; HINSTANCE__ * CBsString::s_hModuleNetMsg
0x180020210  jnz     short loc_18002022A
0x180020212  lea     rcx, aNetmsgDll; "netmsg.dll"
0x180020219  call    ?SxLoadSystem32LibraryEx@@YAPEAUHINSTANCE__@@PEBGPEAXK@Z; SxLoadSystem32LibraryEx(ushort const *,void *,ulong)
0x18002021e  test    rax, rax
0x180020221  jz      short loc_18002022A
0x180020223  mov     cs:?s_hModuleNetMsg@CBsString@@0PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * CBsString::s_hModuleNetMsg
0x18002022a  mov     eax, r14d
0x18002022d  lea     r8, __ImageBase; unsigned int
0x180020234  mov     esi, 1
0x180020239  mov     ecx, eax
0x18002023b  cmp     rva ?g_rgStdMappedErrors@@3PAU___FORMAT_ERRORCODE_ERROR_MAP_ENTRTY@@A[r8+rcx*8], edi; ___FORMAT_ERRORCODE_ERROR_MAP_ENTRTY near * g_rgStdMappedErrors ...
0x180020243  jz      short loc_180020252
0x180020245  add     eax, esi
0x180020247  cmp     eax, 3
0x18002024a  jb      short loc_180020239
0x18002024c  mov     [rbp+3Fh+var_78], r14d
0x180020250  jmp     short loc_18002025D
0x180020252  mov     [rbp+3Fh+var_78], edi
0x180020255  mov     edi, rva dword_18002D7E4[r8+rcx*8]
0x18002025d  mov     eax, edi
0x18002025f  and     eax, 0FFFF0000h
0x180020264  cmp     eax, 80070000h
0x180020269  jnz     short loc_180020270
0x18002026b  mov     edx, r14d
0x18002026e  jmp     short loc_1800202E3
0x180020270  mov     ecx, edi
0x180020272  and     ecx, 10000000h
0x180020278  jnz     short loc_180020287
0x18002027a  mov     edx, 0C0000000h; void *
0x18002027f  mov     eax, edi
0x180020281  and     eax, edx
0x180020283  cmp     eax, edx
0x180020285  jnz     short loc_180020298
0x180020287  mov     rax, cs:?s_hModuleNTDLL@CBsString@@0PEAUHINSTANCE__@@EA; HINSTANCE__ * CBsString::s_hModuleNTDLL
0x18002028e  mov     ebx, esi
0x180020290  mov     [rbp+3Fh+lpSource], rax
0x180020294  test    ecx, ecx
0x180020296  jnz     short loc_1800202DD
0x180020298  mov     eax, r14d
0x18002029b  mov     ecx, eax
0x18002029d  add     rcx, rcx
0x1800202a0  cmp     edi, ds:rva dword_1800236CC[r8+rcx*8]
0x1800202a8  jg      short loc_1800202B4
0x1800202aa  cmp     edi, ds:rva dword_1800236C8[r8+rcx*8]
0x1800202b2  jge     short loc_1800202BF
0x1800202b4  add     eax, esi
0x1800202b6  cmp     eax, 4
0x1800202b9  jb      short loc_18002029B
0x1800202bb  mov     edx, ebx
0x1800202bd  jmp     short loc_1800202E3
0x1800202bf  mov     rcx, ds:rva off_1800236C0[r8+rcx*8]; unsigned __int16 *
0x1800202c7  call    ?SxLoadSystem32LibraryEx@@YAPEAUHINSTANCE__@@PEBGPEAXK@Z; SxLoadSystem32LibraryEx(ushort const *,void *,ulong)
0x1800202cc  mov     r15, rax
0x1800202cf  test    rax, rax
0x1800202d2  jz      short loc_1800202BB
0x1800202d4  mov     eax, ebx
0x1800202d6  mov     [rbp+rax*8+3Fh+lpSource], r15
0x1800202db  jmp     short loc_180020303
0x1800202dd  btr     edi, 1Ch
0x1800202e1  mov     edx, esi
0x1800202e3  mov     rax, cs:?s_hModuleNetMsg@CBsString@@0PEAUHINSTANCE__@@EA; HINSTANCE__ * CBsString::s_hModuleNetMsg
0x1800202ea  mov     ecx, ebx
0x1800202ec  add     ebx, esi
0x1800202ee  mov     [rbp+rcx*8+3Fh+lpSource], rax
0x1800202f3  test    edx, edx
0x1800202f5  jnz     short loc_180020305
0x1800202f7  mov     rax, cs:?s_hModuleNTDLL@CBsString@@0PEAUHINSTANCE__@@EA; HINSTANCE__ * CBsString::s_hModuleNTDLL
0x1800202fe  mov     [rbp+rbx*8+3Fh+lpSource], rax
0x180020303  add     ebx, esi
0x180020305  mov     esi, r14d
0x180020308  test    ebx, ebx
0x18002030a  jnz     short loc_180020380
0x18002030c  lea     rsi, qword_180025E20
0x180020313  mov     rbx, rsi
0x180020316  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002031a  xor     r14d, r14d
0x18002031d  inc     rax
0x180020320  cmp     [rbx+rax*2], r14w
0x180020325  jnz     short loc_18002031D
0x180020327  inc     eax
0x180020329  mov     edi, eax
0x18002032b  lea     rcx, [rax+rax]; cb
0x18002032f  call    cs:__imp_CoTaskMemAlloc
0x180020335  mov     r11, rax
0x180020338  test    rax, rax
0x18002033b  jz      loc_180020449
0x180020341  mov     r8, rbx; unsigned __int16 *
0x180020344  mov     edx, edi; unsigned __int64
0x180020346  mov     rcx, rax; unsigned __int16 *
0x180020349  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002034e  mov     ebx, eax
0x180020350  test    eax, eax
0x180020352  js      loc_18002044C
0x180020358  mov     rcx, [rbp+3Fh+var_70]
0x18002035c  mov     [rcx], r11
0x18002035f  test    r12, r12
0x180020362  jz      short loc_180020368
0x180020364  mov     [r12], rsi
0x180020368  test    r13, r13
0x18002036b  jz      loc_18002044C
0x180020371  mov     ecx, [rbp+3Fh+var_78]
0x180020374  mov     [r13+0], ecx
0x180020378  jmp     loc_18002044C
0x18002037d  xor     r14d, r14d
0x180020380  mov     [rsp+0C0h+Arguments], r14; Arguments
0x180020385  lea     rax, [rbp+3Fh+Buffer]
0x180020389  mov     edx, esi
0x18002038b  xor     r9d, r9d; dwLanguageId
0x18002038e  mov     [rsp+0C0h+nSize], 1; nSize
0x180020396  mov     r8d, edi; dwMessageId
0x180020399  mov     ecx, 1BFFh; dwFlags
0x18002039e  mov     [rsp+0C0h+lpBuffer], rax; lpBuffer
0x1800203a3  mov     rdx, [rbp+rdx*8+3Fh+lpSource]; lpSource
0x1800203a8  call    cs:__imp_FormatMessageW
0x1800203ae  mov     r14d, eax
0x1800203b1  test    eax, eax
0x1800203b3  jnz     short loc_1800203C0
0x1800203b5  inc     esi
0x1800203b7  cmp     esi, ebx
0x1800203b9  jb      short loc_18002037D
0x1800203bb  jmp     loc_18002030C
0x1800203c0  mov     rcx, qword ptr [rbp+3Fh+Buffer]
0x1800203c4  lea     rsi, asc_180027FD4; " "
0x1800203cb  mov     rbx, rcx
0x1800203ce  dec     r14d
0x1800203d1  movzx   ecx, word ptr [rcx+r14*2]; C
0x1800203d6  call    cs:__imp_iswspace
0x1800203dc  mov     rcx, qword ptr [rbp+3Fh+Buffer]
0x1800203e0  test    eax, eax
0x1800203e2  jnz     short loc_1800203F2
0x1800203e4  lea     rax, [rcx+r14*2]
0x1800203e8  mov     edx, 20h ; ' '
0x1800203ed  cmp     [rax], dx
0x1800203f0  jnb     short loc_180020408
0x1800203f2  xor     eax, eax
0x1800203f4  mov     [rcx+r14*2], ax
0x1800203f9  test    r14d, r14d
0x1800203fc  jz      loc_180020316
0x180020402  mov     rcx, qword ptr [rbp+3Fh+Buffer]
0x180020406  jmp     short loc_1800203CE
0x180020408  mov     rbx, rax
0x18002040b  jmp     short loc_180020423
0x18002040d  dec     r14d
0x180020410  movzx   eax, word ptr [rcx+r14*2]
0x180020415  cmp     ax, dx
0x180020418  jnb     short loc_18002042D
0x18002041a  mov     [rcx+r14*2], dx
0x18002041f  mov     rcx, qword ptr [rbp+3Fh+Buffer]
0x180020423  test    r14d, r14d
0x180020426  jnz     short loc_18002040D
0x180020428  jmp     loc_180020316
0x18002042d  movzx   ecx, ax; C
0x180020430  call    cs:__imp_iswspace
0x180020436  mov     edx, 20h ; ' '
0x18002043b  test    eax, eax
0x18002043d  jnz     short loc_18002041F
0x18002043f  mov     rcx, qword ptr [rbp+3Fh+Buffer]
0x180020443  lea     rbx, [rcx+r14*2]
0x180020447  jmp     short loc_180020423
0x180020449  mov     ebx, r14d
0x18002044c  test    r15, r15
0x18002044f  jz      short loc_18002045A
0x180020451  mov     rcx, r15; hLibModule
0x180020454  call    cs:__imp_FreeLibrary
0x18002045a  mov     rcx, qword ptr [rbp+3Fh+Buffer]; pv
0x18002045e  test    rcx, rcx
0x180020461  jz      short loc_180020469
0x180020463  call    cs:__imp_CoTaskMemFree
0x180020469  mov     eax, ebx
0x18002046b  add     rsp, 88h
0x180020472  pop     r15
0x180020474  pop     r14
0x180020476  pop     r13
0x180020478  pop     r12
0x18002047a  pop     rdi
0x18002047b  pop     rsi
0x18002047c  pop     rbx
0x18002047d  pop     rbp
0x18002047e  retn
```
