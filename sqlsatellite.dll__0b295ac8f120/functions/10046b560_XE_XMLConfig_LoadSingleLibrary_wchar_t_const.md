# XE_XMLConfig::LoadSingleLibrary(wchar_t const *)

- ea: `0x10046b560`
- end: `0x10046b824`
- name: `?LoadSingleLibrary@XE_XMLConfig@@QEAAHPEB_W@Z`
- size: `708`
- prototype: `int(XE_XMLConfig *__hidden this, const wchar_t *)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x10046d020`

## callees

- `0x10046b560`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x10046b7c4`
- `KERNEL32!FreeLibrary` at `0x10046b7c4`
- `KERNEL32!LoadLibraryW` at `0x10046b71b`
- `KERNEL32!LoadLibraryW` at `0x10046b71b`
- `KERNEL32!GetProcAddress` at `0x10046b734`
- `KERNEL32!GetProcAddress` at `0x10046b734`
- `KERNEL32!GetLastError` at `0x10046b797`
- `KERNEL32!GetLastError` at `0x10046b797`
- `sqldk!??_V@YAXPEAX@Z` at `0x10046b7f8`
- `sqldk!??_V@YAXPEAX@Z` at `0x10046b7f8`

## string_xrefs

- `0x10046b7a3`: `XE_XML LoadLibraryW %s Failed with Error: %u`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall XE_XMLConfig::LoadSingleLibrary(XE_XMLConfig *this, const wchar_t *a2)
{
  __int64 result; // rax
  unsigned int v5; // r15d
  _QWORD *v6; // r9
  char *v7; // rax
  char *v8; // r8
  int v9; // ecx
  int v10; // edx
  _QWORD *v11; // rax
  _QWORD *v12; // rsi
  _QWORD *v13; // rbx
  __int64 v14; // rax
  unsigned __int64 v15; // rbp
  unsigned int v16; // eax
  char *v17; // rdi
  char *v18; // rcx
  unsigned __int64 v19; // rcx
  signed __int64 v20; // rdx
  __int16 v21; // ax
  char *v22; // rax
  HMODULE LibraryW; // rax
  __int64 v24; // rcx
  FARPROC ProcAddress; // rax
  _QWORD *v26; // rdx
  _WORD *v27; // rax
  DWORD LastError; // eax
  HMODULE v29; // rcx
  void **v30; // rdi

  result = *((_QWORD *)this + 137);
  if ( result
    || ((result = qword_1005170E8(0, 8)) == 0 ? (result = 0) : (*(_QWORD *)result = 0),
        (*((_QWORD *)this + 137) = result) != 0) )
  {
    v5 = 0;
    v6 = *(_QWORD **)result;
    if ( *(_QWORD *)result )
    {
      do
      {
        v7 = (char *)v6[3];
        v8 = (char *)((char *)a2 - v7);
        do
        {
          v9 = *(unsigned __int16 *)&v8[(_QWORD)v7];
          v10 = *(unsigned __int16 *)v7 - v9;
          if ( v10 )
            break;
          v7 += 2;
        }
        while ( v9 );
        if ( !v10 )
          return 1;
        v6 = (_QWORD *)*v6;
      }
      while ( v6 );
    }
    v11 = (_QWORD *)qword_1005170E8(0, 32);
    v12 = v11;
    if ( v11 )
    {
      *v11 = 0;
      v11[1] = 0;
      v11[2] = 0;
      v11[3] = 0;
    }
    else
    {
      v12 = 0;
    }
    v13 = v12;
    if ( v12 )
    {
      v14 = -1;
      do
        ++v14;
      while ( a2[v14] );
      v15 = (unsigned int)(v14 + 1);
      v16 = 2 * (v14 + 1);
      if ( !is_mul_ok(v15, 2u) )
        v16 = -1;
      v17 = (char *)qword_1005170E8(0, v16);
      v18 = (char *)v12[3];
      if ( v18 != v17 && v18 )
        qword_1005170F0(v18);
      v12[3] = v17;
      if ( v17 )
      {
        if ( v15 - 1 > 0x7FFFFFFE )
        {
          if ( v15 )
            *(_WORD *)v17 = 0;
        }
        else
        {
          v19 = 2147483646 - v15;
          v20 = (char *)a2 - v17;
          do
          {
            if ( !(v19 + v15) )
              break;
            v21 = *(_WORD *)&v17[v20];
            if ( !v21 )
              break;
            *(_WORD *)v17 = v21;
            v17 += 2;
            --v15;
          }
          while ( v15 );
          v22 = v17 - 2;
          if ( v15 )
            v22 = v17;
          *(_WORD *)v22 = 0;
          if ( v15 )
          {
            LibraryW = LoadLibraryW(a2);
            v12[1] = LibraryW;
            if ( LibraryW )
            {
              ProcAddress = GetProcAddress(LibraryW, "LifetimeControl");
              v12[2] = ProcAddress;
              if ( ProcAddress )
              {
                v5 = ((__int64 (__fastcall *)(__int64))ProcAddress)(1);
                if ( v5 )
                {
                  v13 = 0;
                  v26 = (_QWORD *)*((_QWORD *)this + 137);
                  *v12 = *v26;
                  *v26 = v12;
                  goto LABEL_46;
                }
              }
            }
            else
            {
              v27 = (_WORD *)qword_100516FE0(v24);
              if ( !v27[1] && !v27[2] && !v27[3] )
                qword_1005170D0(10, 11, 0);
              LastError = GetLastError();
              qword_100517290(L"XE_XML LoadLibraryW %s Failed with Error: %u", a2, LastError);
            }
          }
        }
      }
      v29 = (HMODULE)v12[1];
      if ( v29 )
        FreeLibrary(v29);
    }
LABEL_46:
    if ( v13 )
    {
      v30 = (void **)(v13 + 3);
      if ( v13[3] )
        qword_1005170F0(v13[3]);
      *v30 = 0;
      operator delete[](*v30);
      qword_1005170F0(v13);
    }
    return v5;
  }
  return result;
}

```

## disassembly

```asm
0x10046b560  push    rbp
0x10046b562  push    rsi
0x10046b563  push    rdi
0x10046b564  push    r12
0x10046b566  push    r13
0x10046b568  push    r14
0x10046b56a  push    r15
0x10046b56c  sub     rsp, 30h
0x10046b570  mov     [rsp+68h+var_48], 0FFFFFFFFFFFFFFFEh
0x10046b579  mov     [rsp+68h+arg_8], rbx
0x10046b57e  mov     r14, rdx
0x10046b581  mov     r13, rcx
0x10046b584  mov     rax, [rcx+448h]
0x10046b58b  lea     rbx, ?sm_ServiceAPI@XE_API@@2UXEEngineServicesAPI@@A; XEEngineServicesAPI XE_API::sm_ServiceAPI
0x10046b592  xor     r12d, r12d
0x10046b595  test    rax, rax
0x10046b598  jnz     short loc_10046B5CF
0x10046b59a  mov     [rsp+68h+arg_0], rbx
0x10046b59f  lea     edx, [rax+8]
0x10046b5a2  xor     ecx, ecx
0x10046b5a4  call    cs:qword_1005170E8
0x10046b5aa  mov     [rsp+68h+arg_10], rax
0x10046b5b2  test    rax, rax
0x10046b5b5  jz      short loc_10046B5BC
0x10046b5b7  mov     [rax], r12
0x10046b5ba  jmp     short loc_10046B5BF
0x10046b5bc  mov     rax, r12
0x10046b5bf  mov     [r13+448h], rax
0x10046b5c6  test    rax, rax
0x10046b5c9  jz      loc_10046B80F
0x10046b5cf  mov     r15d, r12d
0x10046b5d2  mov     r9, [rax]
0x10046b5d5  test    r9, r9
0x10046b5d8  jz      short loc_10046B610
0x10046b5da  nop     word ptr [rax+rax+00h]
0x10046b5e0  mov     rax, [r9+18h]
0x10046b5e4  mov     r8, r14
0x10046b5e7  sub     r8, rax
0x10046b5ea  nop     word ptr [rax+rax+00h]
0x10046b5f0  movzx   edx, word ptr [rax]
0x10046b5f3  movzx   ecx, word ptr [rax+r8]
0x10046b5f8  sub     edx, ecx
0x10046b5fa  jnz     short loc_10046B604
0x10046b5fc  add     rax, 2
0x10046b600  test    ecx, ecx
0x10046b602  jnz     short loc_10046B5F0
0x10046b604  test    edx, edx
0x10046b606  jz      short loc_10046B64E
0x10046b608  mov     r9, [r9]
0x10046b60b  test    r9, r9
0x10046b60e  jnz     short loc_10046B5E0
0x10046b610  mov     [rsp+68h+arg_0], rbx
0x10046b615  mov     edx, 20h ; ' '
0x10046b61a  xor     ecx, ecx
0x10046b61c  call    cs:qword_1005170E8
0x10046b622  mov     rsi, rax
0x10046b625  mov     [rsp+68h+arg_10], rax
0x10046b62d  test    rax, rax
0x10046b630  jz      short loc_10046B659
0x10046b632  mov     [rax], r12
0x10046b635  mov     [rax+8], r12
0x10046b639  mov     [rax+10h], r12
0x10046b63d  lea     rcx, [rax+18h]
0x10046b641  mov     [rsp+68h+arg_18], rcx
0x10046b649  mov     [rcx], r12
0x10046b64c  jmp     short loc_10046B65C
0x10046b64e  mov     r15d, 1
0x10046b654  jmp     loc_10046B80C
0x10046b659  mov     rsi, r12
0x10046b65c  mov     rbx, rsi
0x10046b65f  mov     [rsp+68h+arg_0], rbx
0x10046b664  test    rsi, rsi
0x10046b667  jz      loc_10046B7CB
0x10046b66d  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x10046b674  mov     rax, rcx
0x10046b677  nop     word ptr [rax+rax+00000000h]
0x10046b680  lea     rax, [rax+1]
0x10046b684  cmp     word ptr [r14+rax*2], 0
0x10046b68a  jnz     short loc_10046B680
0x10046b68c  lea     ebp, [rax+1]
0x10046b68f  mov     eax, 2
0x10046b694  mul     rbp
0x10046b697  cmovo   rax, rcx
0x10046b69b  mov     edx, eax
0x10046b69d  xor     ecx, ecx
0x10046b69f  call    cs:qword_1005170E8
0x10046b6a5  mov     rdi, rax
0x10046b6a8  mov     rcx, [rsi+18h]
0x10046b6ac  cmp     rcx, rax
0x10046b6af  jz      short loc_10046B6BC
0x10046b6b1  test    rcx, rcx
0x10046b6b4  jz      short loc_10046B6BC
0x10046b6b6  call    cs:qword_1005170F0
0x10046b6bc  mov     [rsi+18h], rdi
0x10046b6c0  test    rdi, rdi
0x10046b6c3  jz      loc_10046B7BB
0x10046b6c9  lea     rax, [rbp-1]
0x10046b6cd  mov     ecx, 7FFFFFFEh
0x10046b6d2  cmp     rax, rcx
0x10046b6d5  ja      loc_10046B7B2
0x10046b6db  sub     rcx, rbp
0x10046b6de  mov     rdx, r14
0x10046b6e1  sub     rdx, rdi
0x10046b6e4  lea     rax, [rcx+rbp]
0x10046b6e8  test    rax, rax
0x10046b6eb  jz      short loc_10046B703
0x10046b6ed  movzx   eax, word ptr [rdx+rdi]
0x10046b6f1  test    ax, ax
0x10046b6f4  jz      short loc_10046B703
0x10046b6f6  mov     [rdi], ax
0x10046b6f9  add     rdi, 2
0x10046b6fd  sub     rbp, 1
0x10046b701  jnz     short loc_10046B6E4
0x10046b703  lea     rax, [rdi-2]
0x10046b707  test    rbp, rbp
0x10046b70a  cmovnz  rax, rdi
0x10046b70e  mov     [rax], r12w
0x10046b712  jz      loc_10046B7BB
0x10046b718  mov     rcx, r14; lpLibFileName
0x10046b71b  call    cs:__imp_LoadLibraryW
0x10046b721  mov     [rsi+8], rax
0x10046b725  test    rax, rax
0x10046b728  jz      short loc_10046B76B
0x10046b72a  lea     rdx, aLifetimecontro; "LifetimeControl"
0x10046b731  mov     rcx, rax; hModule
0x10046b734  call    cs:__imp_GetProcAddress
0x10046b73a  mov     [rsi+10h], rax
0x10046b73e  test    rax, rax
0x10046b741  jz      short loc_10046B7BB
0x10046b743  mov     ecx, 1
0x10046b748  call    rax
0x10046b74a  mov     r15d, eax
0x10046b74d  test    eax, eax
0x10046b74f  jz      short loc_10046B7BB
0x10046b751  mov     rbx, r12
0x10046b754  mov     [rsp+68h+arg_0], rbx
0x10046b759  mov     rdx, [r13+448h]
0x10046b760  mov     rcx, [rdx]
0x10046b763  mov     [rsi], rcx
0x10046b766  mov     [rdx], rsi
0x10046b769  jmp     short loc_10046B7CB
0x10046b76b  call    cs:qword_100516FE0
0x10046b771  cmp     word ptr [rax+2], 0
0x10046b776  jnz     short loc_10046B797
0x10046b778  cmp     word ptr [rax+4], 0
0x10046b77d  jnz     short loc_10046B797
0x10046b77f  cmp     word ptr [rax+6], 0
0x10046b784  jnz     short loc_10046B797
0x10046b786  mov     edx, 0Bh
0x10046b78b  lea     ecx, [rdx-1]
0x10046b78e  xor     r8d, r8d
0x10046b791  call    cs:qword_1005170D0
0x10046b797  call    cs:__imp_GetLastError
0x10046b79d  mov     r8d, eax
0x10046b7a0  mov     rdx, r14
0x10046b7a3  lea     rcx, aXeXmlLoadlibra_0; "XE_XML LoadLibraryW %s Failed with Erro"...
0x10046b7aa  call    cs:qword_100517290
0x10046b7b0  jmp     short loc_10046B7BB
0x10046b7b2  test    rbp, rbp
0x10046b7b5  jz      short loc_10046B7BB
0x10046b7b7  mov     [rdi], r12w
0x10046b7bb  mov     rcx, [rsi+8]; hLibModule
0x10046b7bf  test    rcx, rcx
0x10046b7c2  jz      short loc_10046B7CB
0x10046b7c4  call    cs:__imp_FreeLibrary
0x10046b7ca  nop
0x10046b7cb  mov     [rsp+68h+arg_10], rbx
0x10046b7d3  test    rbx, rbx
0x10046b7d6  jz      short loc_10046B807
0x10046b7d8  lea     rdi, [rbx+18h]
0x10046b7dc  mov     [rsp+68h+arg_10], rdi
0x10046b7e4  mov     rcx, [rdi]
0x10046b7e7  test    rcx, rcx
0x10046b7ea  jz      short loc_10046B7F2
0x10046b7ec  call    cs:qword_1005170F0
0x10046b7f2  mov     [rdi], r12
0x10046b7f5  mov     rcx, [rdi]
0x10046b7f8  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x10046b7fe  mov     rcx, rbx
0x10046b801  call    cs:qword_1005170F0
0x10046b807  mov     [rsp+68h+arg_0], r12
0x10046b80c  mov     eax, r15d
0x10046b80f  mov     rbx, [rsp+68h+arg_8]
0x10046b814  add     rsp, 30h
0x10046b818  pop     r15
0x10046b81a  pop     r14
0x10046b81c  pop     r13
0x10046b81e  pop     r12
0x10046b820  pop     rdi
0x10046b821  pop     rsi
0x10046b822  pop     rbp
0x10046b823  retn
```
