# CBsString::_GetErrorText(long,ulong,___FORMAT_ERRORCODE_SEARCH_DLL_ENTRY const *,ulong,___FORMAT_ERRORCODE_ERROR_MAP_ENTRTY const *,long *,ushort * *,ushort * *)

- ea: `0x180035818`
- end: `0x180035af8`
- name: `?_GetErrorText@CBsString@@AEAAJJKPEBU___FORMAT_ERRORCODE_SEARCH_DLL_ENTRY@@KPEBU___FORMAT_ERRORCODE_ERROR_MAP_ENTRTY@@PEAJPEAPEAG3@Z`
- size: `736`
- prototype: `__int64 __fastcall(CBsString *this, void *, unsigned int, const unsigned __int16 **, unsigned int, const struct ___FORMAT_ERRORCODE_ERROR_MAP_ENTRTY *, int *, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800350b8`

## callees

- `0x180026cf4`
- `0x18002d240`
- `0x180035818`

## import_xrefs

- `msvcrt!iswspace` at `0x180035a58`
- `msvcrt!iswspace` at `0x180035aa4`
- `msvcrt!iswspace` at `0x180035a58`
- `msvcrt!iswspace` at `0x180035aa4`
- `KERNEL32!FreeLibrary` at `0x180035ac6`
- `KERNEL32!FreeLibrary` at `0x180035ac6`
- `KERNEL32!GetModuleHandleW` at `0x180035896`
- `KERNEL32!GetModuleHandleW` at `0x180035896`
- `KERNEL32!FormatMessageW` at `0x1800359b4`
- `KERNEL32!FormatMessageW` at `0x1800359b4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035ad5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035ad5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800359e9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800359e9`

## string_xrefs

- `0x18003588f`: `ntdll.dll`
- `0x1800358b4`: `netmsg.dll`

## pseudocode

```c
__int64 __fastcall CBsString::_GetErrorText(
        CBsString *this,
        void *a2,
        unsigned int a3,
        const unsigned __int16 **a4,
        unsigned int a5,
        const struct ___FORMAT_ERRORCODE_ERROR_MAP_ENTRTY *a6,
        int *a7,
        unsigned __int16 **a8,
        unsigned __int16 **a9)
{
  signed int v11; // edi
  HINSTANCE v12; // r15
  __int64 v13; // rbx
  HMODULE ModuleHandleW; // rax
  HINSTANCE System32Library; // rax
  int v16; // edx
  DWORD v17; // r14d
  unsigned int i; // eax
  __int64 v19; // rcx
  int v20; // esi
  __int64 v21; // rdi
  unsigned __int16 *v22; // r14
  const unsigned __int16 *v23; // rbx
  __int64 v24; // rax
  __int64 v25; // rdi
  unsigned __int16 *v26; // rax
  int v27; // ebx
  unsigned __int16 *v28; // r11
  const unsigned __int16 *v29; // rcx
  int v30; // eax
  const unsigned __int16 *v31; // rcx
  wint_t v32; // ax
  WCHAR Buffer[4]; // [rsp+40h] [rbp-40h] BYREF
  int v35; // [rsp+48h] [rbp-38h]
  unsigned __int16 **v36; // [rsp+50h] [rbp-30h]
  int *v37; // [rsp+58h] [rbp-28h]
  LPCVOID lpSource[2]; // [rsp+60h] [rbp-20h]
  __int128 v39; // [rsp+70h] [rbp-10h]

  v37 = a7;
  v36 = a8;
  v11 = (int)a2;
  v35 = 0;
  v12 = 0;
  *(_QWORD *)Buffer = 0;
  LODWORD(v13) = 0;
  *(_OWORD *)lpSource = 0;
  v39 = 0;
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
    System32Library = SxLoadSystem32LibraryEx(L"netmsg.dll", a2);
    if ( System32Library )
      CBsString::s_hModuleNetMsg = System32Library;
  }
  if ( (v11 & 0xFFFF0000) == 0x80070000 )
  {
    v16 = 0;
    v17 = v11;
  }
  else
  {
    if ( (v11 & 0x10000000) != 0 || (v11 & 0xC0000000) == 0xC0000000 )
    {
      lpSource[0] = CBsString::s_hModuleNTDLL;
      v17 = v11 & 0xEFFFFFFF;
      LODWORD(v13) = 1;
    }
    else
    {
      v17 = 0;
    }
    if ( (v11 & 0x10000000) != 0 || (v17 = v11, !a4) )
    {
LABEL_28:
      v16 = v13;
    }
    else
    {
      for ( i = 0; ; ++i )
      {
        v16 = v13;
        if ( i >= a3 )
          break;
        if ( v11 <= SHIDWORD(a4[2 * i + 1]) && v11 >= SLODWORD(a4[2 * i + 1]) )
        {
          v12 = SxLoadSystem32LibraryEx(a4[2 * i], (void *)(unsigned int)v13);
          if ( !v12 )
            goto LABEL_28;
          lpSource[(unsigned int)v13] = v12;
          goto LABEL_31;
        }
      }
    }
  }
  v19 = (unsigned int)v13;
  v13 = (unsigned int)(v13 + 1);
  lpSource[v19] = CBsString::s_hModuleNetMsg;
  if ( !v16 )
  {
    lpSource[v13] = CBsString::s_hModuleNTDLL;
LABEL_31:
    LODWORD(v13) = v13 + 1;
  }
  v20 = 0;
  if ( (_DWORD)v13 )
  {
    while ( 1 )
    {
      LODWORD(v21) = FormatMessageW(0x1BFFu, lpSource[v20], v17, 0, Buffer, 1u, 0);
      if ( (_DWORD)v21 )
        break;
      if ( ++v20 >= (unsigned int)v13 )
        goto LABEL_35;
    }
    v29 = *(const unsigned __int16 **)Buffer;
    v22 = L" ";
    v23 = *(const unsigned __int16 **)Buffer;
    while ( 1 )
    {
      if ( !(_DWORD)v21 )
        goto LABEL_36;
      v21 = (unsigned int)(v21 - 1);
      v30 = iswspace(v29[(unsigned int)v21]);
      v31 = *(const unsigned __int16 **)Buffer;
      if ( !v30 && *(_WORD *)(*(_QWORD *)Buffer + 2LL * (unsigned int)v21) >= 0x20u )
        break;
      *(_WORD *)(*(_QWORD *)Buffer + 2LL * (unsigned int)v21) = 0;
      v29 = *(const unsigned __int16 **)Buffer;
    }
    v23 = (const unsigned __int16 *)(*(_QWORD *)Buffer + 2 * v21);
    while ( 1 )
    {
      if ( !(_DWORD)v21 )
        goto LABEL_36;
      v21 = (unsigned int)(v21 - 1);
      v32 = v31[v21];
      if ( v32 < 0x20u )
        break;
      if ( iswspace(v32) )
      {
LABEL_52:
        v31 = *(const unsigned __int16 **)Buffer;
      }
      else
      {
        v31 = *(const unsigned __int16 **)Buffer;
        v23 = (const unsigned __int16 *)(*(_QWORD *)Buffer + 2 * v21);
      }
    }
    v31[v21] = 32;
    goto LABEL_52;
  }
LABEL_35:
  v22 = (unsigned __int16 *)&word_18003B6A0;
  v23 = &word_18003B6A0;
LABEL_36:
  v24 = -1;
  do
    ++v24;
  while ( v23[v24] );
  v25 = (unsigned int)(v24 + 1);
  v26 = (unsigned __int16 *)CoTaskMemAlloc(2 * v25);
  if ( v26 )
  {
    v27 = StringCchCopyW(v26, (unsigned int)v25, v23);
    if ( v27 >= 0 )
    {
      *v36 = v28;
      if ( a9 )
        *a9 = v22;
      if ( v37 )
        *v37 = 0;
    }
  }
  else
  {
    v27 = v35;
  }
  if ( v12 )
    FreeLibrary(v12);
  if ( *(_QWORD *)Buffer )
    CoTaskMemFree(*(LPVOID *)Buffer);
  return (unsigned int)v27;
}

```

## disassembly

```asm
0x180035818  mov     [rsp-38h+arg_0], rbx
0x18003581d  push    rbp
0x18003581e  push    rsi
0x18003581f  push    rdi
0x180035820  push    r12
0x180035822  push    r13
0x180035824  push    r14
0x180035826  push    r15
0x180035828  mov     rbp, rsp
0x18003582b  sub     rsp, 80h
0x180035832  mov     rax, [rbp+arg_30]
0x180035836  xorps   xmm0, xmm0
0x180035839  mov     rcx, [rbp+arg_38]
0x18003583d  mov     r12d, r8d
0x180035840  mov     r13, [rbp+arg_40]
0x180035847  xor     r8d, r8d
0x18003584a  mov     [rbp+var_28], rax
0x18003584e  mov     rsi, r9
0x180035851  mov     [rbp+var_30], rcx
0x180035855  mov     edi, edx
0x180035857  mov     [rbp+var_38], r8d
0x18003585b  mov     r15d, r8d
0x18003585e  mov     qword ptr [rbp+Buffer], r8
0x180035862  mov     ebx, r8d
0x180035865  movups  xmmword ptr [rbp+lpSource], xmm0
0x180035869  movups  [rbp+var_10], xmm0
0x18003586d  test    rax, rax
0x180035870  jz      short loc_180035875
0x180035872  mov     [rax], r8d
0x180035875  test    rcx, rcx
0x180035878  jz      short loc_18003587D
0x18003587a  mov     [rcx], r8
0x18003587d  test    r13, r13
0x180035880  jz      short loc_180035886
0x180035882  mov     [r13+0], r8
0x180035886  cmp     cs:?s_hModuleNTDLL@CBsString@@0PEAUHINSTANCE__@@EA, r8; HINSTANCE__ * CBsString::s_hModuleNTDLL
0x18003588d  jnz     short loc_1800358AB
0x18003588f  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x180035896  call    cs:__imp_GetModuleHandleW
0x18003589c  xor     r8d, r8d; unsigned int
0x18003589f  test    rax, rax
0x1800358a2  jz      short loc_1800358AB
0x1800358a4  mov     cs:?s_hModuleNTDLL@CBsString@@0PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * CBsString::s_hModuleNTDLL
0x1800358ab  cmp     cs:?s_hModuleNetMsg@CBsString@@0PEAUHINSTANCE__@@EA, r8; HINSTANCE__ * CBsString::s_hModuleNetMsg
0x1800358b2  jnz     short loc_1800358CF
0x1800358b4  lea     rcx, aNetmsgDll; "netmsg.dll"
0x1800358bb  call    ?SxLoadSystem32LibraryEx@@YAPEAUHINSTANCE__@@PEBGPEAXK@Z; SxLoadSystem32LibraryEx(ushort const *,void *,ulong)
0x1800358c0  xor     r8d, r8d; unsigned int
0x1800358c3  test    rax, rax
0x1800358c6  jz      short loc_1800358CF
0x1800358c8  mov     cs:?s_hModuleNetMsg@CBsString@@0PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * CBsString::s_hModuleNetMsg
0x1800358cf  mov     eax, edi
0x1800358d1  and     eax, 0FFFF0000h
0x1800358d6  cmp     eax, 80070000h
0x1800358db  jnz     short loc_1800358E5
0x1800358dd  mov     edx, r8d
0x1800358e0  mov     r14d, edi
0x1800358e3  jmp     short loc_180035963
0x1800358e5  mov     ecx, edi
0x1800358e7  and     ecx, 10000000h
0x1800358ed  jnz     short loc_180035901
0x1800358ef  mov     edx, 0C0000000h
0x1800358f4  mov     eax, edi
0x1800358f6  and     eax, edx
0x1800358f8  cmp     eax, edx
0x1800358fa  jz      short loc_180035901
0x1800358fc  mov     r14d, r8d
0x1800358ff  jmp     short loc_180035919
0x180035901  mov     rax, cs:?s_hModuleNTDLL@CBsString@@0PEAUHINSTANCE__@@EA; HINSTANCE__ * CBsString::s_hModuleNTDLL
0x180035908  mov     r14d, edi
0x18003590b  mov     [rbp+lpSource], rax
0x18003590f  btr     r14d, 1Ch
0x180035914  mov     ebx, 1
0x180035919  test    ecx, ecx
0x18003591b  jnz     short loc_180035961
0x18003591d  mov     r14d, edi
0x180035920  test    rsi, rsi
0x180035923  jz      short loc_180035961
0x180035925  mov     eax, r8d
0x180035928  mov     edx, ebx; void *
0x18003592a  cmp     eax, r12d
0x18003592d  jnb     short loc_180035963
0x18003592f  mov     ecx, eax
0x180035931  add     rcx, rcx
0x180035934  cmp     edi, [rsi+rcx*8+0Ch]
0x180035938  jg      short loc_180035940
0x18003593a  cmp     edi, [rsi+rcx*8+8]
0x18003593e  jge     short loc_180035944
0x180035940  inc     eax
0x180035942  jmp     short loc_180035928
0x180035944  mov     rcx, [rsi+rcx*8]; unsigned __int16 *
0x180035948  call    ?SxLoadSystem32LibraryEx@@YAPEAUHINSTANCE__@@PEBGPEAXK@Z; SxLoadSystem32LibraryEx(ushort const *,void *,ulong)
0x18003594d  xor     r8d, r8d
0x180035950  mov     r15, rax
0x180035953  test    rax, rax
0x180035956  jz      short loc_180035961
0x180035958  mov     eax, ebx
0x18003595a  mov     [rbp+rax*8+lpSource], r15
0x18003595f  jmp     short loc_180035983
0x180035961  mov     edx, ebx
0x180035963  mov     rax, cs:?s_hModuleNetMsg@CBsString@@0PEAUHINSTANCE__@@EA; HINSTANCE__ * CBsString::s_hModuleNetMsg
0x18003596a  mov     ecx, ebx
0x18003596c  inc     ebx
0x18003596e  mov     [rbp+rcx*8+lpSource], rax
0x180035973  test    edx, edx
0x180035975  jnz     short loc_180035985
0x180035977  mov     rax, cs:?s_hModuleNTDLL@CBsString@@0PEAUHINSTANCE__@@EA; HINSTANCE__ * CBsString::s_hModuleNTDLL
0x18003597e  mov     [rbp+rbx*8+lpSource], rax
0x180035983  inc     ebx
0x180035985  mov     esi, r8d
0x180035988  test    ebx, ebx
0x18003598a  jz      short loc_1800359C9
0x18003598c  mov     [rsp+80h+Arguments], r8; Arguments
0x180035991  lea     rax, [rbp+Buffer]
0x180035995  mov     edx, esi
0x180035997  xor     r9d, r9d; dwLanguageId
0x18003599a  mov     [rsp+80h+nSize], 1; nSize
0x1800359a2  mov     r8d, r14d; dwMessageId
0x1800359a5  mov     ecx, 1BFFh; dwFlags
0x1800359aa  mov     [rsp+80h+lpBuffer], rax; lpBuffer
0x1800359af  mov     rdx, [rbp+rdx*8+lpSource]; lpSource
0x1800359b4  call    cs:__imp_FormatMessageW
0x1800359ba  xor     r8d, r8d
0x1800359bd  mov     edi, eax
0x1800359bf  test    eax, eax
0x1800359c1  jnz     short loc_180035A3A
0x1800359c3  inc     esi
0x1800359c5  cmp     esi, ebx
0x1800359c7  jb      short loc_18003598C
0x1800359c9  lea     r14, word_18003B6A0
0x1800359d0  mov     rbx, r14
0x1800359d3  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800359d7  inc     rax
0x1800359da  cmp     [rbx+rax*2], r8w
0x1800359df  jnz     short loc_1800359D7
0x1800359e1  inc     eax
0x1800359e3  mov     edi, eax
0x1800359e5  lea     rcx, [rax+rax]; cb
0x1800359e9  call    cs:__imp_CoTaskMemAlloc
0x1800359ef  mov     r11, rax
0x1800359f2  test    rax, rax
0x1800359f5  jz      loc_180035ABB
0x1800359fb  mov     r8, rbx; unsigned __int16 *
0x1800359fe  mov     edx, edi; unsigned __int64
0x180035a00  mov     rcx, rax; unsigned __int16 *
0x180035a03  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180035a08  mov     ebx, eax
0x180035a0a  test    eax, eax
0x180035a0c  js      loc_180035ABE
0x180035a12  mov     rcx, [rbp+var_30]
0x180035a16  mov     [rcx], r11
0x180035a19  test    r13, r13
0x180035a1c  jz      short loc_180035A22
0x180035a1e  mov     [r13+0], r14
0x180035a22  mov     rcx, [rbp+var_28]
0x180035a26  test    rcx, rcx
0x180035a29  jz      loc_180035ABE
0x180035a2f  mov     dword ptr [rcx], 0
0x180035a35  jmp     loc_180035ABE
0x180035a3a  mov     rcx, qword ptr [rbp+Buffer]
0x180035a3e  lea     r14, asc_18003A418; " "
0x180035a45  mov     rbx, rcx
0x180035a48  mov     r12d, 20h ; ' '
0x180035a4e  test    edi, edi
0x180035a50  jz      short loc_1800359D3
0x180035a52  dec     edi
0x180035a54  movzx   ecx, word ptr [rcx+rdi*2]; C
0x180035a58  call    cs:__imp_iswspace
0x180035a5e  mov     rcx, qword ptr [rbp+Buffer]
0x180035a62  xor     r8d, r8d
0x180035a65  test    eax, eax
0x180035a67  jnz     short loc_180035A73
0x180035a69  lea     rax, [rcx+rdi*2]
0x180035a6d  cmp     [rax], r12w
0x180035a71  jnb     short loc_180035A7E
0x180035a73  mov     [rcx+rdi*2], r8w
0x180035a78  mov     rcx, qword ptr [rbp+Buffer]
0x180035a7c  jmp     short loc_180035A4E
0x180035a7e  mov     rbx, rax
0x180035a81  jmp     short loc_180035A98
0x180035a83  dec     edi
0x180035a85  movzx   eax, word ptr [rcx+rdi*2]
0x180035a89  cmp     ax, r12w
0x180035a8d  jnb     short loc_180035AA1
0x180035a8f  mov     [rcx+rdi*2], r12w
0x180035a94  mov     rcx, qword ptr [rbp+Buffer]
0x180035a98  test    edi, edi
0x180035a9a  jnz     short loc_180035A83
0x180035a9c  jmp     loc_1800359D3
0x180035aa1  movzx   ecx, ax; C
0x180035aa4  call    cs:__imp_iswspace
0x180035aaa  xor     r8d, r8d
0x180035aad  test    eax, eax
0x180035aaf  jnz     short loc_180035A94
0x180035ab1  mov     rcx, qword ptr [rbp+Buffer]
0x180035ab5  lea     rbx, [rcx+rdi*2]
0x180035ab9  jmp     short loc_180035A98
0x180035abb  mov     ebx, [rbp+var_38]
0x180035abe  test    r15, r15
0x180035ac1  jz      short loc_180035ACC
0x180035ac3  mov     rcx, r15; hLibModule
0x180035ac6  call    cs:__imp_FreeLibrary
0x180035acc  mov     rcx, qword ptr [rbp+Buffer]; pv
0x180035ad0  test    rcx, rcx
0x180035ad3  jz      short loc_180035ADB
0x180035ad5  call    cs:__imp_CoTaskMemFree
0x180035adb  mov     eax, ebx
0x180035add  mov     rbx, [rsp+80h+arg_0]
0x180035ae5  add     rsp, 80h
0x180035aec  pop     r15
0x180035aee  pop     r14
0x180035af0  pop     r13
0x180035af2  pop     r12
0x180035af4  pop     rdi
0x180035af5  pop     rsi
0x180035af6  pop     rbp
0x180035af7  retn
```
