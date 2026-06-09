# RegistryHelper::ReadBufferFromRegistry(HKEY__ *,ushort const *,ushort const *,ulong,uchar * *,ulong *)

- ea: `0x1800050f8`
- end: `0x180005354`
- name: `?ReadBufferFromRegistry@RegistryHelper@@QEAAJPEAUHKEY__@@PEBG1KPEAPEAEPEAK@Z`
- size: `604`
- prototype: `__int64 __fastcall(RegistryHelper *__hidden this, HKEY, const unsigned __int16 *, const unsigned __int16 *, unsigned int, unsigned __int8 **, unsigned int *)`
- caller_count: `8`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180013ddc`
- `0x180014004`
- `0x18003b6e4`
- `0x18003c9cc`
- `0x18003d0d0`
- `0x18003d848`
- `0x18003dd2c`
- `0x18003dfd4`

## callees

- `0x1800050f8`
- `0x18000535c`
- `0x180013434`
- `0x180015abc`
- `0x180016758`
- `0x180058010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180005307`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180005307`

## string_xrefs

- `0x1800051b5`: `onecoreuap\ds\ext\live\identity\lib\utilitieslite\registryhelper.cpp`
- `0x18000526c`: `onecoreuap\ds\ext\live\identity\lib\utilitieslite\registryhelper.cpp`
- `0x180005334`: `onecoreuap\ds\ext\live\identity\lib\utilitieslite\registryhelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall RegistryHelper::ReadBufferFromRegistry(
        RegistryHelper *this,
        HKEY a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned int a5,
        unsigned __int8 **a6,
        unsigned int *a7)
{
  const unsigned __int16 *v7; // rdi
  __int64 v9; // r15
  int v10; // esi
  unsigned __int8 *v11; // rbx
  char v12; // al
  char v13; // r12
  HKEY v14; // r14
  unsigned int v15; // eax
  unsigned int v16; // edi
  HKEY v17; // rdx
  int v18; // eax
  __int64 v20; // rdx
  unsigned int v21; // [rsp+20h] [rbp-61h]
  int v22; // [rsp+20h] [rbp-61h]
  unsigned int v23; // [rsp+20h] [rbp-61h]
  HKEY v24; // [rsp+50h] [rbp-31h] BYREF
  __int64 v25; // [rsp+58h] [rbp-29h]
  __int64 v26; // [rsp+60h] [rbp-21h]
  _QWORD v27[11]; // [rsp+68h] [rbp-19h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+47h]
  unsigned __int8 *v29; // [rsp+D8h] [rbp+57h] BYREF
  const unsigned __int16 *v30; // [rsp+E0h] [rbp+5Fh]
  const unsigned __int16 *v31; // [rsp+E8h] [rbp+67h]

  v31 = a4;
  v30 = a3;
  v7 = a4;
  v9 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)this + 8LL))(*(_QWORD *)this);
  v27[2] = v9;
  v10 = 0;
  v27[1] = 0;
  v11 = 0;
  v29 = 0;
  *a6 = 0;
  *a7 = 0;
  if ( !a2 || (v12 = 0, a2 == HKEY_CURRENT_USER) )
    v12 = 1;
  v13 = 0;
  v14 = 0;
  v27[0] = 0;
  if ( v12 )
  {
    v24 = 0;
    v26 = v9;
    v25 = 0;
    v15 = (*(__int64 (__fastcall **)(__int64, __int64, HKEY *))(*(_QWORD *)v9 + 72LL))(v9, 2, &v24);
    if ( !v15 )
    {
      v14 = v24;
      v24 = 0;
      v25 = 0;
      v27[0] = v14;
      v13 = 1;
      Auto<HKEY__ *,RegistryFunctor,IRegistryFunctions>::~Auto<HKEY__ *,RegistryFunctor,IRegistryFunctions>(&v24);
      goto LABEL_8;
    }
    v16 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x103,
            (unsigned int)"onecoreuap\\ds\\ext\\live\\identity\\lib\\utilitieslite\\registryhelper.cpp",
            (const char *)v15,
            v21);
    Auto<HKEY__ *,RegistryFunctor,IRegistryFunctions>::~Auto<HKEY__ *,RegistryFunctor,IRegistryFunctions>(&v24);
    v13 = 0;
    if ( (v16 & 0x80000000) == 0 )
    {
      v7 = v31;
      goto LABEL_8;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3D,
      (unsigned int)"onecoreuap\\ds\\ext\\live\\identity\\lib\\utilitieslite\\registryhelper.cpp",
      (const char *)v16,
      v22);
    goto LABEL_17;
  }
  while ( 1 )
  {
LABEL_8:
    v17 = a2;
    if ( v13 )
      v17 = v14;
    v23 = a5;
    v18 = (*(__int64 (__fastcall **)(__int64, HKEY, const unsigned __int16 *, const unsigned __int16 *))(*(_QWORD *)v9 + 56LL))(
            v9,
            v17,
            v30,
            v7);
    if ( !v18 )
    {
      if ( v11 )
      {
LABEL_18:
        *a6 = v11;
        *a7 = 0;
        Auto<HKEY__ *,RegistryFunctor,IRegistryFunctions>::~Auto<HKEY__ *,RegistryFunctor,IRegistryFunctions>(v27);
        return 0;
      }
      goto LABEL_27;
    }
    if ( v18 != 234 )
      break;
    if ( v10 >= 5 )
      goto LABEL_13;
LABEL_27:
    CMIDLPtr<unsigned short *>::Clear(&v29);
    v11 = (unsigned __int8 *)malloc(0);
    CMIDLPtr<unsigned short *>::Clear(&v29);
    v29 = v11;
    if ( !v11 )
    {
      v16 = -2147024882;
      v20 = 90;
      goto LABEL_30;
    }
    if ( v10 >= 5 )
      goto LABEL_18;
    ++v10;
  }
  if ( v18 > 0 )
  {
LABEL_13:
    v16 = (unsigned __int16)v18 | 0x80070000;
    goto LABEL_14;
  }
  v16 = v18;
LABEL_14:
  if ( v16 == -2147024894 )
  {
    CMIDLPtr<unsigned short *>::Clear(&v29);
    v16 = -2147024894;
    goto LABEL_17;
  }
  v20 = 96;
LABEL_30:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v20,
    (unsigned int)"onecoreuap\\ds\\ext\\live\\identity\\lib\\utilitieslite\\registryhelper.cpp",
    (const char *)v16,
    v23);
  CMIDLPtr<unsigned short *>::Clear(&v29);
LABEL_17:
  Auto<HKEY__ *,RegistryFunctor,IRegistryFunctions>::~Auto<HKEY__ *,RegistryFunctor,IRegistryFunctions>(v27);
  return v16;
}

```

## disassembly

```asm
0x1800050f8  mov     [rsp-8+arg_18], r9
0x1800050fd  mov     [rsp-8+arg_10], r8
0x180005102  push    rbp
0x180005103  push    rbx
0x180005104  push    rsi
0x180005105  push    rdi
0x180005106  push    r12
0x180005108  push    r13
0x18000510a  push    r14
0x18000510c  push    r15
0x18000510e  lea     rbp, [rsp-7]
0x180005113  sub     rsp, 88h
0x18000511a  mov     rdi, r9
0x18000511d  mov     r13, rdx
0x180005120  mov     rcx, [rcx]
0x180005123  mov     rax, [rcx]
0x180005126  mov     rax, [rax+8]
0x18000512a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000512f  mov     r15, rax
0x180005132  mov     [rbp+3Fh+var_48], rax
0x180005136  xor     esi, esi
0x180005138  mov     [rbp+3Fh+var_50], rsi
0x18000513c  mov     ebx, esi
0x18000513e  mov     [rbp+3Fh+arg_8], rbx
0x180005142  mov     rax, [rbp+3Fh+arg_28]
0x180005146  mov     [rax], rsi
0x180005149  mov     rax, [rbp+3Fh+arg_30]
0x18000514d  mov     [rax], esi
0x18000514f  test    r13, r13
0x180005152  jnz     loc_1800052D5
0x180005158  mov     al, 1
0x18000515a  mov     r12b, sil
0x18000515d  mov     r14, rsi
0x180005160  mov     [rbp+3Fh+var_58], rsi
0x180005164  test    al, al
0x180005166  jz      short loc_1800051E0
0x180005168  mov     [rbp+3Fh+var_70], rsi
0x18000516c  mov     [rbp+3Fh+var_60], r15
0x180005170  mov     [rbp+3Fh+var_68], rsi
0x180005174  mov     rax, [r15]
0x180005177  lea     r8, [rbp+3Fh+var_70]
0x18000517b  mov     edx, 2
0x180005180  mov     rcx, r15
0x180005183  mov     rax, [rax+48h]
0x180005187  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000518c  test    eax, eax
0x18000518e  jnz     short loc_1800051AE
0x180005190  mov     r14, [rbp+3Fh+var_70]
0x180005194  mov     [rbp+3Fh+var_70], rsi
0x180005198  mov     [rbp+3Fh+var_68], rsi
0x18000519c  mov     [rbp+3Fh+var_58], r14
0x1800051a0  mov     r12b, 1
0x1800051a3  lea     rcx, [rbp+3Fh+var_70]
0x1800051a7  call    ??1?$Auto@PEAUHKEY__@@VRegistryFunctor@@VIRegistryFunctions@@@@QEAA@XZ; Auto<HKEY__ *,RegistryFunctor,IRegistryFunctions>::~Auto<HKEY__ *,RegistryFunctor,IRegistryFunctions>(void)
0x1800051ac  jmp     short loc_1800051E0
0x1800051ae  mov     rcx, [rbp+47h]; this
0x1800051b2  mov     r9d, eax; char *
0x1800051b5  lea     r8, aOnecoreuapDsEx_13; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x1800051bc  mov     edx, 103h; void *
0x1800051c1  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800051c6  mov     edi, eax
0x1800051c8  lea     rcx, [rbp+3Fh+var_70]
0x1800051cc  call    ??1?$Auto@PEAUHKEY__@@VRegistryFunctor@@VIRegistryFunctions@@@@QEAA@XZ; Auto<HKEY__ *,RegistryFunctor,IRegistryFunctions>::~Auto<HKEY__ *,RegistryFunctor,IRegistryFunctions>(void)
0x1800051d1  mov     r12b, sil
0x1800051d4  test    edi, edi
0x1800051d6  js      loc_180005265
0x1800051dc  mov     rdi, [rbp+3Fh+arg_18]
0x1800051e0  mov     [rbp+3Fh+arg_0], esi
0x1800051e3  mov     rax, [r15]
0x1800051e6  mov     rdx, r13
0x1800051e9  test    r12b, r12b
0x1800051ec  cmovnz  rdx, r14
0x1800051f0  lea     rcx, [rbp+3Fh+arg_0]
0x1800051f4  mov     [rsp+0C0h+var_88], rcx
0x1800051f9  mov     [rsp+0C0h+var_90], rbx
0x1800051fe  mov     [rsp+0C0h+var_98], 0
0x180005207  mov     ecx, [rbp+3Fh+arg_20]
0x18000520a  mov     [rsp+0C0h+var_A0], ecx; int
0x18000520e  mov     r9, rdi
0x180005211  mov     r8, [rbp+3Fh+arg_10]
0x180005215  mov     rcx, r15
0x180005218  mov     rax, [rax+38h]
0x18000521c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005221  test    eax, eax
0x180005223  jz      loc_1800052EA
0x180005229  mov     ecx, 0EAh
0x18000522e  cmp     eax, ecx
0x180005230  jz      loc_1800052F1
0x180005236  test    eax, eax
0x180005238  jle     loc_1800052CE
0x18000523e  movzx   edi, ax
0x180005241  or      edi, 80070000h
0x180005247  test    edi, edi
0x180005249  jns     short loc_18000528B
0x18000524b  mov     ebx, 80070002h
0x180005250  cmp     edi, ebx
0x180005252  jnz     loc_18000532C
0x180005258  lea     rcx, [rbp+3Fh+arg_8]
0x18000525c  call    ?Clear@?$CMIDLPtr@PEAG@@QEAAXXZ; CMIDLPtr<ushort *>::Clear(void)
0x180005261  mov     edi, ebx
0x180005263  jmp     short loc_18000527E
0x180005265  mov     rcx, [rbp+47h]; this
0x180005269  mov     r9d, edi; char *
0x18000526c  lea     r8, aOnecoreuapDsEx_13; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180005273  mov     edx, 3Dh ; '='; void *
0x180005278  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000527d  nop
0x18000527e  lea     rcx, [rbp+3Fh+var_58]
0x180005282  call    ??1?$Auto@PEAUHKEY__@@VRegistryFunctor@@VIRegistryFunctions@@@@QEAA@XZ; Auto<HKEY__ *,RegistryFunctor,IRegistryFunctions>::~Auto<HKEY__ *,RegistryFunctor,IRegistryFunctions>(void)
0x180005287  mov     eax, edi
0x180005289  jmp     short loc_1800052AA
0x18000528b  cmp     eax, ecx
0x18000528d  jz      short loc_1800052BE
0x18000528f  mov     rax, [rbp+3Fh+arg_28]
0x180005293  mov     [rax], rbx
0x180005296  mov     eax, [rbp+3Fh+arg_0]
0x180005299  mov     rcx, [rbp+3Fh+arg_30]
0x18000529d  mov     [rcx], eax
0x18000529f  lea     rcx, [rbp+3Fh+var_58]
0x1800052a3  call    ??1?$Auto@PEAUHKEY__@@VRegistryFunctor@@VIRegistryFunctions@@@@QEAA@XZ; Auto<HKEY__ *,RegistryFunctor,IRegistryFunctions>::~Auto<HKEY__ *,RegistryFunctor,IRegistryFunctions>(void)
0x1800052a8  xor     eax, eax
0x1800052aa  add     rsp, 88h
0x1800052b1  pop     r15
0x1800052b3  pop     r14
0x1800052b5  pop     r13
0x1800052b7  pop     r12
0x1800052b9  pop     rdi
0x1800052ba  pop     rsi
0x1800052bb  pop     rbx
0x1800052bc  pop     rbp
0x1800052bd  retn
0x1800052be  mov     rdi, [rbp+3Fh+arg_18]
0x1800052c2  cmp     esi, 5
0x1800052c5  jge     short loc_18000528F
0x1800052c7  inc     esi
0x1800052c9  jmp     loc_1800051E3
0x1800052ce  mov     edi, eax
0x1800052d0  jmp     loc_180005247
0x1800052d5  cmp     r13, 0FFFFFFFF80000001h
0x1800052dc  mov     al, sil
0x1800052df  jnz     loc_18000515A
0x1800052e5  jmp     loc_180005158
0x1800052ea  test    rbx, rbx
0x1800052ed  jnz     short loc_18000528F
0x1800052ef  jmp     short loc_1800052FA
0x1800052f1  cmp     esi, 5
0x1800052f4  jge     loc_18000523E
0x1800052fa  lea     rcx, [rbp+3Fh+arg_8]
0x1800052fe  call    ?Clear@?$CMIDLPtr@PEAG@@QEAAXXZ; CMIDLPtr<ushort *>::Clear(void)
0x180005303  movsxd  rcx, [rbp+3Fh+arg_0]; Size
0x180005307  call    cs:__imp_malloc
0x18000530d  mov     rbx, rax
0x180005310  lea     rcx, [rbp+3Fh+arg_8]
0x180005314  call    ?Clear@?$CMIDLPtr@PEAG@@QEAAXXZ; CMIDLPtr<ushort *>::Clear(void)
0x180005319  mov     [rbp+3Fh+arg_8], rbx
0x18000531d  test    rbx, rbx
0x180005320  jnz     short loc_1800052C2
0x180005322  mov     edi, 8007000Eh
0x180005327  lea     edx, [rbx+5Ah]
0x18000532a  jmp     short loc_180005331
0x18000532c  mov     edx, 60h ; '`'; void *
0x180005331  mov     r9d, edi; char *
0x180005334  lea     r8, aOnecoreuapDsEx_13; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18000533b  mov     rcx, [rbp+47h]; this
0x18000533f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005344  nop
0x180005345  lea     rcx, [rbp+3Fh+arg_8]
0x180005349  call    ?Clear@?$CMIDLPtr@PEAG@@QEAAXXZ; CMIDLPtr<ushort *>::Clear(void)
0x18000534e  jmp     loc_18000527E
```
