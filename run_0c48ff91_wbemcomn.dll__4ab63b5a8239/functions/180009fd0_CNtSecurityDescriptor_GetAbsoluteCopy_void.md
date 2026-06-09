# CNtSecurityDescriptor::GetAbsoluteCopy(void)

- ea: `0x180009fd0`
- end: `0x18000a28a`
- name: `?GetAbsoluteCopy@CNtSecurityDescriptor@@QEAAPEAUSNtAbsoluteSD@@XZ`
- size: `698`
- prototype: `struct SNtAbsoluteSD *__fastcall(CNtSecurityDescriptor *__hidden this)`
- caller_count: `5`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18001a730`
- `0x180023800`
- `0x180023a60`
- `0x18003c7b0`
- `0x18003f9b0`

## callees

- `0x180009fd0`
- `0x18000a290`
- `0x18001d19c`
- `0x1800238d0`
- `0x180023b18`
- `0x1800442d3`
- `0x180047010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a0bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a0bb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a21a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a259`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a21a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a259`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a233`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a26f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a233`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a26f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
struct SNtAbsoluteSD *__fastcall CNtSecurityDescriptor::GetAbsoluteCopy(CNtSecurityDescriptor *this)
{
  SNtAbsoluteSD *v2; // rax
  SNtAbsoluteSD *v3; // rbx
  __int64 v4; // rsi
  __int64 v5; // r14
  __int64 v6; // r15
  __int64 v7; // r12
  __int64 v8; // r13
  FARPROC ProcAddress; // rax
  unsigned int v10; // edx
  void *v11; // rax
  void *v12; // rax
  void *v13; // rax
  void *v14; // rax
  void *v15; // rax
  __int64 v16; // rsi
  __int64 v17; // r14
  __int64 v18; // r15
  __int64 v19; // r12
  __int64 v20; // r13
  __int64 v21; // rdi
  FARPROC v22; // rax
  DWORD SecurityDll; // eax
  DWORD v25; // eax
  size_t Size; // [rsp+60h] [rbp-18h] BYREF
  SNtAbsoluteSD *v27; // [rsp+68h] [rbp-10h]
  size_t v28; // [rsp+C0h] [rbp+48h] BYREF
  size_t v29; // [rsp+C8h] [rbp+50h] BYREF
  size_t v30; // [rsp+D0h] [rbp+58h] BYREF
  size_t v31; // [rsp+D8h] [rbp+60h] BYREF

  if ( *((_DWORD *)this + 2) || !*(_QWORD *)this || !(unsigned int)CNtSecurityDescriptor::IsValid(this) )
    return 0;
  LODWORD(Size) = 0;
  LODWORD(v31) = 0;
  LODWORD(v30) = 0;
  LODWORD(v29) = 0;
  LODWORD(v28) = 0;
  v2 = (SNtAbsoluteSD *)CWin32DefaultArena::WbemMemAlloc(0x28u);
  v3 = v2;
  v27 = v2;
  if ( v2 )
  {
    *(_QWORD *)v2 = 0;
    *((_QWORD *)v2 + 1) = 0;
    *((_QWORD *)v2 + 2) = 0;
    *((_QWORD *)v2 + 3) = 0;
    *((_QWORD *)v2 + 4) = 0;
  }
  else
  {
    v3 = 0;
  }
  if ( !v3 )
    return 0;
  v4 = *((_QWORD *)v3 + 4);
  v5 = *((_QWORD *)v3 + 3);
  v6 = *((_QWORD *)v3 + 2);
  v7 = *((_QWORD *)v3 + 1);
  v8 = *(_QWORD *)v3;
  v27 = *(SNtAbsoluteSD **)this;
  ProcAddress = (FARPROC)qword_180070368;
  if ( !qword_180070368 )
  {
    SecurityDll = DLpLoadSecurityDll();
    if ( SecurityDll )
    {
      SetLastError(SecurityDll);
      goto LABEL_9;
    }
    ProcAddress = GetProcAddress(g_hInstSecurityDLL, "MakeAbsoluteSD");
    qword_180070368 = (__int64)ProcAddress;
    if ( !ProcAddress )
      goto LABEL_9;
  }
  ((void (__fastcall *)(SNtAbsoluteSD *, __int64, size_t *, __int64, size_t *, __int64, size_t *, __int64, size_t *, __int64, size_t *))ProcAddress)(
    v27,
    v8,
    &Size,
    v7,
    &v31,
    v6,
    &v30,
    v5,
    &v29,
    v4,
    &v28);
LABEL_9:
  if ( GetLastError() == 122 )
  {
    v11 = CWin32DefaultArena::WbemMemAlloc((unsigned int)Size);
    *(_QWORD *)v3 = v11;
    if ( v11 )
    {
      memset_0(v11, 0, (unsigned int)Size);
      v12 = CWin32DefaultArena::WbemMemAlloc((unsigned int)v31);
      *((_QWORD *)v3 + 1) = v12;
      if ( v12 )
      {
        memset_0(v12, 0, (unsigned int)v31);
        v13 = CWin32DefaultArena::WbemMemAlloc((unsigned int)v30);
        *((_QWORD *)v3 + 2) = v13;
        if ( v13 )
        {
          memset_0(v13, 0, (unsigned int)v30);
          v14 = CWin32DefaultArena::WbemMemAlloc((unsigned int)v29);
          *((_QWORD *)v3 + 3) = v14;
          if ( v14 )
          {
            memset_0(v14, 0, (unsigned int)v29);
            v15 = CWin32DefaultArena::WbemMemAlloc((unsigned int)v28);
            *((_QWORD *)v3 + 4) = v15;
            if ( v15 )
            {
              memset_0(v15, 0, (unsigned int)v28);
              v16 = *((_QWORD *)v3 + 4);
              v17 = *((_QWORD *)v3 + 3);
              v18 = *((_QWORD *)v3 + 2);
              v19 = *((_QWORD *)v3 + 1);
              v20 = *(_QWORD *)v3;
              v21 = *(_QWORD *)this;
              v22 = (FARPROC)qword_180070368;
              if ( qword_180070368 )
                goto LABEL_16;
              v25 = DLpLoadSecurityDll();
              if ( v25 )
              {
                SetLastError(v25);
              }
              else
              {
                v22 = GetProcAddress(g_hInstSecurityDLL, "MakeAbsoluteSD");
                qword_180070368 = (__int64)v22;
                if ( v22 )
                {
LABEL_16:
                  if ( ((unsigned int (__fastcall *)(__int64, __int64, size_t *, __int64, size_t *, __int64, size_t *, __int64, size_t *, __int64, size_t *))v22)(
                         v21,
                         v20,
                         &Size,
                         v19,
                         &v31,
                         v18,
                         &v30,
                         v17,
                         &v29,
                         v16,
                         &v28) )
                  {
                    return v3;
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  SNtAbsoluteSD::`scalar deleting destructor'(v3, v10);
  return 0;
}

```

## disassembly

```asm
0x180009fd0  push    rbp
0x180009fd2  push    rbx
0x180009fd3  push    rsi
0x180009fd4  push    rdi
0x180009fd5  push    r12
0x180009fd7  push    r13
0x180009fd9  push    r14
0x180009fdb  push    r15
0x180009fdd  mov     rbp, rsp
0x180009fe0  sub     rsp, 78h
0x180009fe4  mov     rdi, rcx
0x180009fe7  xor     esi, esi
0x180009fe9  cmp     [rcx+8], esi
0x180009fec  jnz     loc_18000A203
0x180009ff2  cmp     [rcx], rsi
0x180009ff5  jz      loc_18000A203
0x180009ffb  call    ?IsValid@CNtSecurityDescriptor@@QEAAHXZ; CNtSecurityDescriptor::IsValid(void)
0x18000a000  test    eax, eax
0x18000a002  jz      loc_18000A203
0x18000a008  mov     dword ptr [rbp+Size], esi
0x18000a00b  mov     dword ptr [rbp+arg_18], esi
0x18000a00e  mov     dword ptr [rbp+arg_10], esi
0x18000a011  mov     dword ptr [rbp+arg_8], esi
0x18000a014  mov     dword ptr [rbp+arg_0], esi
0x18000a017  lea     ecx, [rsi+28h]; unsigned __int64
0x18000a01a  call    ?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18000a01f  mov     rbx, rax
0x18000a022  mov     [rbp+var_10], rax
0x18000a026  test    rax, rax
0x18000a029  jz      loc_18000A207
0x18000a02f  mov     [rax], rsi
0x18000a032  mov     [rax+8], rsi
0x18000a036  mov     [rax+10h], rsi
0x18000a03a  mov     [rax+18h], rsi
0x18000a03e  mov     [rax+20h], rsi
0x18000a042  test    rbx, rbx
0x18000a045  jz      loc_18000A203
0x18000a04b  mov     rsi, [rbx+20h]
0x18000a04f  mov     r14, [rbx+18h]
0x18000a053  mov     r15, [rbx+10h]
0x18000a057  mov     r12, [rbx+8]
0x18000a05b  mov     r13, [rbx]
0x18000a05e  mov     rax, [rdi]
0x18000a061  mov     [rbp+var_10], rax
0x18000a065  mov     rax, cs:qword_180070368
0x18000a06c  test    rax, rax
0x18000a06f  jz      loc_18000A20F
0x18000a075  lea     rcx, [rbp+arg_0]
0x18000a079  mov     [rsp+78h+var_28], rcx
0x18000a07e  mov     [rsp+78h+var_30], rsi
0x18000a083  lea     rcx, [rbp+arg_8]
0x18000a087  mov     [rsp+78h+var_38], rcx
0x18000a08c  mov     [rsp+78h+var_40], r14
0x18000a091  lea     rcx, [rbp+arg_10]
0x18000a095  mov     [rsp+78h+var_48], rcx
0x18000a09a  mov     [rsp+78h+var_50], r15
0x18000a09f  lea     rcx, [rbp+arg_18]
0x18000a0a3  mov     [rsp+78h+var_58], rcx
0x18000a0a8  mov     r9, r12
0x18000a0ab  lea     r8, [rbp+Size]
0x18000a0af  mov     rdx, r13
0x18000a0b2  mov     rcx, [rbp+var_10]
0x18000a0b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a0bb  call    cs:__imp_GetLastError
0x18000a0c1  cmp     eax, 7Ah ; 'z'
0x18000a0c4  jnz     loc_18000A1FB
0x18000a0ca  mov     ecx, dword ptr [rbp+Size]; unsigned __int64
0x18000a0cd  call    ?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18000a0d2  mov     [rbx], rax
0x18000a0d5  test    rax, rax
0x18000a0d8  jz      loc_18000A1FB
0x18000a0de  mov     r8d, dword ptr [rbp+Size]; Size
0x18000a0e2  xor     edx, edx; Val
0x18000a0e4  mov     rcx, rax; void *
0x18000a0e7  call    memset_0
0x18000a0ec  mov     ecx, dword ptr [rbp+arg_18]; unsigned __int64
0x18000a0ef  call    ?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18000a0f4  mov     [rbx+8], rax
0x18000a0f8  test    rax, rax
0x18000a0fb  jz      loc_18000A1FB
0x18000a101  mov     r8d, dword ptr [rbp+arg_18]; Size
0x18000a105  xor     edx, edx; Val
0x18000a107  mov     rcx, rax; void *
0x18000a10a  call    memset_0
0x18000a10f  mov     ecx, dword ptr [rbp+arg_10]; unsigned __int64
0x18000a112  call    ?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18000a117  mov     [rbx+10h], rax
0x18000a11b  test    rax, rax
0x18000a11e  jz      loc_18000A1FB
0x18000a124  mov     r8d, dword ptr [rbp+arg_10]; Size
0x18000a128  xor     edx, edx; Val
0x18000a12a  mov     rcx, rax; void *
0x18000a12d  call    memset_0
0x18000a132  mov     ecx, dword ptr [rbp+arg_8]; unsigned __int64
0x18000a135  call    ?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18000a13a  mov     [rbx+18h], rax
0x18000a13e  test    rax, rax
0x18000a141  jz      loc_18000A1FB
0x18000a147  mov     r8d, dword ptr [rbp+arg_8]; Size
0x18000a14b  xor     edx, edx; Val
0x18000a14d  mov     rcx, rax; void *
0x18000a150  call    memset_0
0x18000a155  mov     ecx, dword ptr [rbp+arg_0]; unsigned __int64
0x18000a158  call    ?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18000a15d  mov     [rbx+20h], rax
0x18000a161  test    rax, rax
0x18000a164  jz      loc_18000A1FB
0x18000a16a  mov     r8d, dword ptr [rbp+arg_0]; Size
0x18000a16e  xor     edx, edx; Val
0x18000a170  mov     rcx, rax; void *
0x18000a173  call    memset_0
0x18000a178  mov     rsi, [rbx+20h]
0x18000a17c  mov     r14, [rbx+18h]
0x18000a180  mov     r15, [rbx+10h]
0x18000a184  mov     r12, [rbx+8]
0x18000a188  mov     r13, [rbx]
0x18000a18b  mov     rdi, [rdi]
0x18000a18e  mov     rax, cs:qword_180070368
0x18000a195  test    rax, rax
0x18000a198  jz      loc_18000A24E
0x18000a19e  lea     rcx, [rbp+arg_0]
0x18000a1a2  mov     [rsp+78h+var_28], rcx
0x18000a1a7  mov     [rsp+78h+var_30], rsi
0x18000a1ac  lea     rcx, [rbp+arg_8]
0x18000a1b0  mov     [rsp+78h+var_38], rcx
0x18000a1b5  mov     [rsp+78h+var_40], r14
0x18000a1ba  lea     rcx, [rbp+arg_10]
0x18000a1be  mov     [rsp+78h+var_48], rcx
0x18000a1c3  mov     [rsp+78h+var_50], r15
0x18000a1c8  lea     rcx, [rbp+arg_18]
0x18000a1cc  mov     [rsp+78h+var_58], rcx
0x18000a1d1  mov     r9, r12
0x18000a1d4  lea     r8, [rbp+Size]
0x18000a1d8  mov     rdx, r13
0x18000a1db  mov     rcx, rdi
0x18000a1de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a1e3  test    eax, eax
0x18000a1e5  jz      short loc_18000A1FB
0x18000a1e7  mov     rax, rbx
0x18000a1ea  add     rsp, 78h
0x18000a1ee  pop     r15
0x18000a1f0  pop     r14
0x18000a1f2  pop     r13
0x18000a1f4  pop     r12
0x18000a1f6  pop     rdi
0x18000a1f7  pop     rsi
0x18000a1f8  pop     rbx
0x18000a1f9  pop     rbp
0x18000a1fa  retn
0x18000a1fb  mov     rcx, rbx; this
0x18000a1fe  call    ??_GSNtAbsoluteSD@@QEAAPEAXI@Z; SNtAbsoluteSD::`scalar deleting destructor'(uint)
0x18000a203  xor     eax, eax
0x18000a205  jmp     short loc_18000A1EA
0x18000a207  mov     rbx, rsi
0x18000a20a  jmp     loc_18000A042
0x18000a20f  call    ?DLpLoadSecurityDll@@YAKXZ; DLpLoadSecurityDll(void)
0x18000a214  test    eax, eax
0x18000a216  jz      short loc_18000A225
0x18000a218  mov     ecx, eax; dwErrCode
0x18000a21a  call    cs:__imp_SetLastError
0x18000a220  jmp     loc_18000A0BB
0x18000a225  lea     rdx, ProcName; "MakeAbsoluteSD"
0x18000a22c  mov     rcx, cs:?g_hInstSecurityDLL@@3PEAUHINSTANCE__@@EA; hModule
0x18000a233  call    cs:__imp_GetProcAddress
0x18000a239  mov     cs:qword_180070368, rax
0x18000a240  test    rax, rax
0x18000a243  jz      loc_18000A0BB
0x18000a249  jmp     loc_18000A075
0x18000a24e  call    ?DLpLoadSecurityDll@@YAKXZ; DLpLoadSecurityDll(void)
0x18000a253  test    eax, eax
0x18000a255  jz      short loc_18000A261
0x18000a257  mov     ecx, eax; dwErrCode
0x18000a259  call    cs:__imp_SetLastError
0x18000a25f  jmp     short loc_18000A1FB
0x18000a261  lea     rdx, ProcName; "MakeAbsoluteSD"
0x18000a268  mov     rcx, cs:?g_hInstSecurityDLL@@3PEAUHINSTANCE__@@EA; hModule
0x18000a26f  call    cs:__imp_GetProcAddress
0x18000a275  mov     cs:qword_180070368, rax
0x18000a27c  test    rax, rax
0x18000a27f  jz      loc_18000A1FB
0x18000a285  jmp     loc_18000A19E
```
