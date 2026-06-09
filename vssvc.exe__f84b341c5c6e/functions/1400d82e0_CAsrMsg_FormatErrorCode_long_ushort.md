# CAsrMsg::FormatErrorCode(long,ushort * *)

- ea: `0x1400d82e0`
- end: `0x1400d8598`
- name: `?FormatErrorCode@CAsrMsg@@QEAAJJPEAPEAG@Z`
- size: `696`
- prototype: `int(CAsrMsg *__hidden this, int, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140061e80`

## callees

- `0x1400d829c`
- `0x1400d82e0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x1400d8511`
- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x1400d855d`
- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x1400d8511`
- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x1400d855d`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1400d8494`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1400d8494`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400d8340`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400d8362`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400d8340`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400d8362`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1400d84db`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1400d84db`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1400d838a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1400d83f6`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1400d838a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1400d83f6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400d84ee`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400d84ee`

## string_xrefs

- `0x1400d8339`: `ntdll.dll`
- `0x1400d837f`: `netmsg.dll`
- `0x1400d835b`: `kernel32.dll`

## pseudocode

```c
__int64 __fastcall CAsrMsg::FormatErrorCode(CAsrMsg *this, int a2, unsigned __int16 **a3)
{
  int v3; // r14d
  bool v6; // zf
  HMODULE v7; // r12
  unsigned int v8; // ebx
  int v9; // edi
  HMODULE ModuleHandleW; // rax
  HMODULE v11; // rax
  HMODULE Library; // rax
  DWORD v13; // r15d
  int i; // eax
  HMODULE v15; // rax
  __int64 v16; // rcx
  __int64 v17; // rbx
  unsigned int v18; // eax
  __int64 v19; // rdx
  __int64 v20; // rdi
  __int64 v21; // r8
  const wchar_t *v22; // r15
  const unsigned __int16 *v23; // rbx
  unsigned int v24; // ebx
  const unsigned __int16 *v25; // rcx
  int v26; // eax
  const unsigned __int16 *v27; // rcx
  unsigned __int16 v28; // ax
  __int64 nSize; // [rsp+28h] [rbp-58h]
  WCHAR Buffer[4]; // [rsp+40h] [rbp-40h] BYREF
  CAsrMsg *v32; // [rsp+48h] [rbp-38h]
  LPCVOID lpSource[2]; // [rsp+50h] [rbp-30h]
  __int128 v34; // [rsp+60h] [rbp-20h]
  __int64 v35; // [rsp+70h] [rbp-10h]

  v3 = 0;
  v32 = this;
  *(_QWORD *)Buffer = 0;
  v35 = 0;
  *(_OWORD *)lpSource = 0;
  v34 = 0;
  if ( a3 )
  {
    v6 = CAsrMsg::s_hModuleNTDLL == 0;
    v7 = 0;
    *a3 = 0;
    v8 = 0;
    v9 = 0;
    if ( v6 )
    {
      ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
      if ( ModuleHandleW )
        CAsrMsg::s_hModuleNTDLL = ModuleHandleW;
    }
    if ( !CAsrMsg::s_hModuleKernel32 )
    {
      v11 = GetModuleHandleW(L"kernel32.dll");
      if ( v11 )
        CAsrMsg::s_hModuleKernel32 = v11;
    }
    if ( !CAsrMsg::s_hModuleNetMsg )
    {
      Library = LoadLibraryExW(L"netmsg.dll", 0, 2u);
      if ( Library )
        CAsrMsg::s_hModuleNetMsg = Library;
    }
    if ( (a2 & 0xFFFF0000) == 0x80070000 )
    {
      v13 = (unsigned __int16)a2;
    }
    else if ( (a2 & 0x10000000) != 0 || (a2 & 0xC0000000) == 0xC0000000 )
    {
      v8 = 1;
      lpSource[0] = CAsrMsg::s_hModuleNTDLL;
      v9 = 1;
      v13 = a2 & 0xEFFFFFFF;
    }
    else
    {
      v13 = a2;
      for ( i = 0; !i; i = 1 )
      {
        if ( a2 <= -2147212033 && a2 >= -2147212543 )
        {
          v7 = LoadLibraryExW(g_rgErrorCodeSearchTable, 0, 2u);
          v15 = (HMODULE)lpSource[0];
          if ( v7 )
            v15 = v7;
          LOBYTE(v8) = v7 != 0;
          lpSource[0] = v15;
          if ( v7 )
            goto LABEL_27;
          break;
        }
      }
    }
    v16 = v8;
    v17 = v8 + 1;
    lpSource[v16] = CAsrMsg::s_hModuleKernel32;
    lpSource[v17] = CAsrMsg::s_hModuleNetMsg;
    v8 = v17 + 1;
    v18 = v8;
    if ( !v9 )
    {
      ++v8;
      lpSource[v18] = CAsrMsg::s_hModuleNTDLL;
    }
LABEL_27:
    if ( v8 )
    {
      while ( 1 )
      {
        LODWORD(v20) = FormatMessageW(0xBFFu, lpSource[v3], v13, 0, Buffer, 1u, 0);
        if ( (_DWORD)v20 )
          break;
        if ( ++v3 >= v8 )
          goto LABEL_30;
      }
      v25 = *(const unsigned __int16 **)Buffer;
      v22 = L" ";
      v23 = *(const unsigned __int16 **)Buffer;
      while ( 1 )
      {
        if ( !(_DWORD)v20 )
          goto LABEL_31;
        v20 = (unsigned int)(v20 - 1);
        v26 = _o_iswspace(v25[(unsigned int)v20], v19, v21);
        v27 = *(const unsigned __int16 **)Buffer;
        if ( !v26 )
        {
          v19 = 32;
          if ( *(_WORD *)(*(_QWORD *)Buffer + 2LL * (unsigned int)v20) >= 0x20u )
            break;
        }
        *(_WORD *)(*(_QWORD *)Buffer + 2LL * (unsigned int)v20) = 0;
        v25 = *(const unsigned __int16 **)Buffer;
      }
      v23 = (const unsigned __int16 *)(*(_QWORD *)Buffer + 2 * v20);
      while ( 1 )
      {
        if ( !(_DWORD)v20 )
          goto LABEL_31;
        v20 = (unsigned int)(v20 - 1);
        v28 = v27[v20];
        if ( v28 < 0x20u )
          break;
        if ( (unsigned int)_o_iswspace(v28, 32, v21) )
        {
LABEL_43:
          v27 = *(const unsigned __int16 **)Buffer;
        }
        else
        {
          v27 = *(const unsigned __int16 **)Buffer;
          v23 = (const unsigned __int16 *)(*(_QWORD *)Buffer + 2 * v20);
        }
      }
      v27[v20] = 32;
      goto LABEL_43;
    }
LABEL_30:
    v22 = &byte_1400F9C88;
    v23 = &byte_1400F9C88;
LABEL_31:
    LODWORD(nSize) = a2;
    v24 = CAsrMsg::Format(v32, a3, L"%s%s(0x%08X)", v23, v22, nSize);
    if ( v7 )
      FreeLibrary(v7);
    if ( *(_QWORD *)Buffer )
      LocalFree(*(HLOCAL *)Buffer);
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v24;
}

```

## disassembly

```asm
0x1400d82e0  mov     [rsp-38h+arg_0], rbx
0x1400d82e5  push    rbp
0x1400d82e6  push    rsi
0x1400d82e7  push    rdi
0x1400d82e8  push    r12
0x1400d82ea  push    r13
0x1400d82ec  push    r14
0x1400d82ee  push    r15
0x1400d82f0  mov     rbp, rsp
0x1400d82f3  sub     rsp, 80h
0x1400d82fa  xor     r14d, r14d
0x1400d82fd  mov     [rbp+var_38], rcx
0x1400d8301  xor     eax, eax
0x1400d8303  mov     qword ptr [rbp+Buffer], r14
0x1400d8307  mov     [rbp+var_10], rax
0x1400d830b  xorps   xmm0, xmm0
0x1400d830e  mov     r13, r8
0x1400d8311  mov     esi, edx
0x1400d8313  movups  xmmword ptr [rbp+lpSource], xmm0
0x1400d8317  movups  [rbp+var_20], xmm0
0x1400d831b  test    r8, r8
0x1400d831e  jz      loc_1400D8576
0x1400d8324  cmp     cs:?s_hModuleNTDLL@CAsrMsg@@0PEAUHINSTANCE__@@EA, r14; HINSTANCE__ * CAsrMsg::s_hModuleNTDLL
0x1400d832b  mov     r12d, r14d
0x1400d832e  mov     [r8], r14
0x1400d8331  mov     ebx, r14d
0x1400d8334  mov     edi, r14d
0x1400d8337  jnz     short loc_1400D8352
0x1400d8339  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x1400d8340  call    cs:__imp_GetModuleHandleW
0x1400d8346  test    rax, rax
0x1400d8349  jz      short loc_1400D8352
0x1400d834b  mov     cs:?s_hModuleNTDLL@CAsrMsg@@0PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * CAsrMsg::s_hModuleNTDLL
0x1400d8352  cmp     cs:?s_hModuleKernel32@CAsrMsg@@0PEAUHINSTANCE__@@EA, r14; HINSTANCE__ * CAsrMsg::s_hModuleKernel32
0x1400d8359  jnz     short loc_1400D8374
0x1400d835b  lea     rcx, aKernel32Dll; "kernel32.dll"
0x1400d8362  call    cs:__imp_GetModuleHandleW
0x1400d8368  test    rax, rax
0x1400d836b  jz      short loc_1400D8374
0x1400d836d  mov     cs:?s_hModuleKernel32@CAsrMsg@@0PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * CAsrMsg::s_hModuleKernel32
0x1400d8374  cmp     cs:?s_hModuleNetMsg@CAsrMsg@@0PEAUHINSTANCE__@@EA, r14; HINSTANCE__ * CAsrMsg::s_hModuleNetMsg
0x1400d837b  jnz     short loc_1400D839C
0x1400d837d  xor     edx, edx; hFile
0x1400d837f  lea     rcx, aNetmsgDll; "netmsg.dll"
0x1400d8386  lea     r8d, [rdx+2]; dwFlags
0x1400d838a  call    cs:__imp_LoadLibraryExW
0x1400d8390  test    rax, rax
0x1400d8393  jz      short loc_1400D839C
0x1400d8395  mov     cs:?s_hModuleNetMsg@CAsrMsg@@0PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * CAsrMsg::s_hModuleNetMsg
0x1400d839c  mov     eax, esi
0x1400d839e  and     eax, 0FFFF0000h
0x1400d83a3  cmp     eax, 80070000h
0x1400d83a8  jnz     short loc_1400D83B0
0x1400d83aa  movzx   r15d, si
0x1400d83ae  jmp     short loc_1400D842F
0x1400d83b0  bt      esi, 1Ch
0x1400d83b4  jb      short loc_1400D8415
0x1400d83b6  mov     ecx, 0C0000000h
0x1400d83bb  mov     eax, esi
0x1400d83bd  and     eax, ecx
0x1400d83bf  cmp     eax, ecx
0x1400d83c1  jz      short loc_1400D8415
0x1400d83c3  mov     r15d, esi
0x1400d83c6  lea     r9, g_rgErrorCodeSearchTable
0x1400d83cd  mov     eax, r14d
0x1400d83d0  cmp     eax, 1
0x1400d83d3  jnb     short loc_1400D842F
0x1400d83d5  mov     ecx, eax
0x1400d83d7  add     rcx, rcx
0x1400d83da  cmp     esi, [r9+rcx*8+0Ch]
0x1400d83df  jg      short loc_1400D83E8
0x1400d83e1  cmp     esi, [r9+rcx*8+8]
0x1400d83e6  jge     short loc_1400D83EC
0x1400d83e8  inc     eax
0x1400d83ea  jmp     short loc_1400D83D0
0x1400d83ec  mov     rcx, [r9+rcx*8]; lpLibFileName
0x1400d83f0  xor     edx, edx; hFile
0x1400d83f2  lea     r8d, [rdx+2]; dwFlags
0x1400d83f6  call    cs:__imp_LoadLibraryExW
0x1400d83fc  mov     r12, rax
0x1400d83ff  mov     rax, [rbp+lpSource]
0x1400d8403  test    r12, r12
0x1400d8406  cmovnz  rax, r12
0x1400d840a  setnz   bl
0x1400d840d  mov     [rbp+lpSource], rax
0x1400d8411  jnz     short loc_1400D8463
0x1400d8413  jmp     short loc_1400D842F
0x1400d8415  mov     rax, cs:?s_hModuleNTDLL@CAsrMsg@@0PEAUHINSTANCE__@@EA; HINSTANCE__ * CAsrMsg::s_hModuleNTDLL
0x1400d841c  mov     ebx, 1
0x1400d8421  mov     r15d, esi
0x1400d8424  mov     [rbp+lpSource], rax
0x1400d8428  mov     edi, ebx
0x1400d842a  btr     r15d, 1Ch
0x1400d842f  mov     rax, cs:?s_hModuleKernel32@CAsrMsg@@0PEAUHINSTANCE__@@EA; HINSTANCE__ * CAsrMsg::s_hModuleKernel32
0x1400d8436  mov     ecx, ebx
0x1400d8438  inc     ebx
0x1400d843a  mov     [rbp+rcx*8+lpSource], rax
0x1400d843f  mov     rax, cs:?s_hModuleNetMsg@CAsrMsg@@0PEAUHINSTANCE__@@EA; HINSTANCE__ * CAsrMsg::s_hModuleNetMsg
0x1400d8446  mov     [rbp+rbx*8+lpSource], rax
0x1400d844b  inc     ebx
0x1400d844d  mov     eax, ebx
0x1400d844f  test    edi, edi
0x1400d8451  jnz     short loc_1400D8463
0x1400d8453  mov     ecx, eax
0x1400d8455  inc     ebx
0x1400d8457  mov     rax, cs:?s_hModuleNTDLL@CAsrMsg@@0PEAUHINSTANCE__@@EA; HINSTANCE__ * CAsrMsg::s_hModuleNTDLL
0x1400d845e  mov     [rbp+rcx*8+lpSource], rax
0x1400d8463  test    ebx, ebx
0x1400d8465  jz      short loc_1400D84A8
0x1400d8467  mov     [rsp+80h+Arguments], 0; Arguments
0x1400d8470  lea     rax, [rbp+Buffer]
0x1400d8474  mov     edx, r14d
0x1400d8477  xor     r9d, r9d; dwLanguageId
0x1400d847a  mov     dword ptr [rsp+80h+nSize], 1; nSize
0x1400d8482  mov     r8d, r15d; dwMessageId
0x1400d8485  mov     ecx, 0BFFh; dwFlags
0x1400d848a  mov     [rsp+80h+lpBuffer], rax; lpBuffer
0x1400d848f  mov     rdx, [rbp+rdx*8+lpSource]; lpSource
0x1400d8494  call    cs:__imp_FormatMessageW
0x1400d849a  mov     edi, eax
0x1400d849c  test    eax, eax
0x1400d849e  jnz     short loc_1400D84F9
0x1400d84a0  inc     r14d
0x1400d84a3  cmp     r14d, ebx
0x1400d84a6  jb      short loc_1400D8467
0x1400d84a8  lea     r15, byte_1400F9C88
0x1400d84af  mov     rbx, r15
0x1400d84b2  mov     rcx, [rbp+var_38]; this
0x1400d84b6  lea     r8, aSS0x08x; "%s%s(0x%08X)"
0x1400d84bd  mov     dword ptr [rsp+80h+nSize], esi
0x1400d84c1  mov     r9, rbx
0x1400d84c4  mov     rdx, r13; unsigned __int16 **
0x1400d84c7  mov     [rsp+80h+lpBuffer], r15
0x1400d84cc  call    ?Format@CAsrMsg@@QEAAJPEAPEAGPEBGZZ; CAsrMsg::Format(ushort * *,ushort const *,...)
0x1400d84d1  mov     ebx, eax
0x1400d84d3  test    r12, r12
0x1400d84d6  jz      short loc_1400D84E1
0x1400d84d8  mov     rcx, r12; hLibModule
0x1400d84db  call    cs:__imp_FreeLibrary
0x1400d84e1  mov     rcx, qword ptr [rbp+Buffer]; hMem
0x1400d84e5  test    rcx, rcx
0x1400d84e8  jz      loc_1400D857B
0x1400d84ee  call    cs:__imp_LocalFree
0x1400d84f4  jmp     loc_1400D857B
0x1400d84f9  mov     rcx, qword ptr [rbp+Buffer]
0x1400d84fd  lea     r15, asc_140138880; " "
0x1400d8504  mov     rbx, rcx
0x1400d8507  test    edi, edi
0x1400d8509  jz      short loc_1400D84B2
0x1400d850b  dec     edi
0x1400d850d  movzx   ecx, word ptr [rcx+rdi*2]
0x1400d8511  call    cs:__imp__o_iswspace
0x1400d8517  mov     rcx, qword ptr [rbp+Buffer]
0x1400d851b  test    eax, eax
0x1400d851d  jnz     short loc_1400D852D
0x1400d851f  lea     rax, [rcx+rdi*2]
0x1400d8523  mov     edx, 20h ; ' '
0x1400d8528  cmp     [rax], dx
0x1400d852b  jnb     short loc_1400D8539
0x1400d852d  xor     eax, eax
0x1400d852f  mov     [rcx+rdi*2], ax
0x1400d8533  mov     rcx, qword ptr [rbp+Buffer]
0x1400d8537  jmp     short loc_1400D8507
0x1400d8539  mov     rbx, rax
0x1400d853c  jmp     short loc_1400D8551
0x1400d853e  dec     edi
0x1400d8540  movzx   eax, word ptr [rcx+rdi*2]
0x1400d8544  cmp     ax, dx
0x1400d8547  jnb     short loc_1400D855A
0x1400d8549  mov     [rcx+rdi*2], dx
0x1400d854d  mov     rcx, qword ptr [rbp+Buffer]
0x1400d8551  test    edi, edi
0x1400d8553  jnz     short loc_1400D853E
0x1400d8555  jmp     loc_1400D84B2
0x1400d855a  movzx   ecx, ax
0x1400d855d  call    cs:__imp__o_iswspace
0x1400d8563  mov     edx, 20h ; ' '
0x1400d8568  test    eax, eax
0x1400d856a  jnz     short loc_1400D854D
0x1400d856c  mov     rcx, qword ptr [rbp+Buffer]
0x1400d8570  lea     rbx, [rcx+rdi*2]
0x1400d8574  jmp     short loc_1400D8551
0x1400d8576  mov     ebx, 80070057h
0x1400d857b  mov     eax, ebx
0x1400d857d  mov     rbx, [rsp+80h+arg_0]
0x1400d8585  add     rsp, 80h
0x1400d858c  pop     r15
0x1400d858e  pop     r14
0x1400d8590  pop     r13
0x1400d8592  pop     r12
0x1400d8594  pop     rdi
0x1400d8595  pop     rsi
0x1400d8596  pop     rbp
0x1400d8597  retn
```
