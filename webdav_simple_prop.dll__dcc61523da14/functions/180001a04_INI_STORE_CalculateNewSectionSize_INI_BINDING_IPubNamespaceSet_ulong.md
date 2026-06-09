# INI_STORE::CalculateNewSectionSize(INI_BINDING *,IPubNamespaceSet *,ulong *)

- ea: `0x180001a04`
- end: `0x180001c04`
- name: `?CalculateNewSectionSize@INI_STORE@@AEAAJPEAUINI_BINDING@@PEAVIPubNamespaceSet@@PEAK@Z`
- size: `512`
- prototype: `__int64 __fastcall(INI_STORE *this, struct INI_BINDING *, struct IPubNamespaceSet *, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180002520`

## callees

- `0x180001a04`
- `0x180002b34`
- `0x180002c84`
- `0x1800031e4`
- `0x180003280`
- `0x180003490`
- `0x180004010`

## import_xrefs

- `iisutil!??0STRU@@QEAA@XZ` at `0x180001a4b`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180001a56`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180001a4b`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180001a56`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x180001bd5`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x180001bd5`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180001bc0`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180001bcb`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180001bc0`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180001bcb`
- `iisutil!??0MULTISZ@@QEAA@XZ` at `0x180001a40`
- `iisutil!??0MULTISZ@@QEAA@XZ` at `0x180001a40`

## pseudocode

```c
__int64 __fastcall INI_STORE::CalculateNewSectionSize(
        INI_STORE *this,
        struct INI_BINDING *a2,
        struct IPubNamespaceSet *a3,
        unsigned int *a4)
{
  unsigned int *v4; // r12
  int EntireSection; // ebx
  unsigned int v8; // r14d
  unsigned int v9; // esi
  __int64 v10; // rdi
  __int64 v11; // r12
  struct IPubProperty *i; // rax
  const unsigned __int16 *v13; // rax
  struct IPubProperty *v14; // rdi
  unsigned int v15; // eax
  int v16; // eax
  int v18; // [rsp+20h] [rbp-E0h]
  unsigned __int16 *v19; // [rsp+28h] [rbp-D8h]
  _BYTE v21[48]; // [rsp+38h] [rbp-C8h] BYREF
  int v22; // [rsp+68h] [rbp-98h]
  _BYTE v23[32]; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 *v24; // [rsp+90h] [rbp-70h]
  int v25; // [rsp+A0h] [rbp-60h]
  _BYTE v26[48]; // [rsp+A8h] [rbp-58h] BYREF
  int v27; // [rsp+D8h] [rbp-28h]
  int v28; // [rsp+DCh] [rbp-24h]
  _BYTE v29[64]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v30[64]; // [rsp+120h] [rbp+20h] BYREF

  v4 = a4;
  MULTISZ::MULTISZ((MULTISZ *)v26);
  STRU::STRU((STRU *)v23);
  STRU::STRU((STRU *)v21);
  EntireSection = ReadEntireSection(a2, (struct MULTISZ *)v26);
  if ( EntireSection >= 0 )
  {
    v18 = v27 + v28;
    v8 = 0;
    v9 = 0;
    v10 = (**(__int64 (__fastcall ***)(struct IPubNamespaceSet *, _BYTE *))a3)(a3, v30);
    if ( v10 )
    {
      do
      {
        v19 = (unsigned __int16 *)(**(__int64 (__fastcall ***)(__int64))v10)(v10);
        v11 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
        for ( i = (struct IPubProperty *)(**(__int64 (__fastcall ***)(__int64, _BYTE *))v11)(v11, v29);
              ;
              i = (struct IPubProperty *)(*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v11 + 8LL))(v11, v29) )
        {
          v14 = i;
          if ( !i )
            break;
          v13 = (const unsigned __int16 *)(**(__int64 (__fastcall ***)(struct IPubProperty *))i)(i);
          EntireSection = EncodeIniKeyName(v13, v19, (struct STRU *)v23);
          if ( EntireSection < 0 )
            goto LABEL_21;
          EntireSection = ReadValue(a2, v24, (struct STRU *)v21);
          if ( EntireSection < 0 )
            goto LABEL_21;
          if ( v22 )
            v9 += v25 + v22 + 4;
          if ( (*(__int64 (__fastcall **)(struct IPubProperty *))(*(_QWORD *)v14 + 8LL))(v14) )
          {
            EntireSection = EncodePropertyToString(v14, (struct STRU *)v21);
            if ( EntireSection < 0 )
              goto LABEL_21;
            v8 += v25 + v22 + 4;
          }
        }
        v10 = (*(__int64 (__fastcall **)(struct IPubNamespaceSet *, _BYTE *))(*(_QWORD *)a3 + 8LL))(a3, v30);
      }
      while ( v10 );
      v4 = a4;
    }
    v15 = v8 + v18;
    if ( v8 + v18 >= v8 )
    {
      if ( v9 > v15 )
        v16 = 0;
      else
        v16 = v15 - v9;
    }
    else
    {
      v16 = -1;
    }
    *v4 = v16;
  }
LABEL_21:
  STRU::~STRU((STRU *)v21);
  STRU::~STRU((STRU *)v23);
  MULTISZ::~MULTISZ((MULTISZ *)v26);
  return (unsigned int)EntireSection;
}

```

## disassembly

```asm
0x180001a04  mov     [rsp-8+arg_0], rbx
0x180001a09  push    rbp
0x180001a0a  push    rsi
0x180001a0b  push    rdi
0x180001a0c  push    r12
0x180001a0e  push    r13
0x180001a10  push    r14
0x180001a12  push    r15
0x180001a14  lea     rbp, [rsp-70h]
0x180001a19  sub     rsp, 170h
0x180001a20  mov     rax, cs:__security_cookie
0x180001a27  xor     rax, rsp
0x180001a2a  mov     [rbp+0A0h+var_40], rax
0x180001a2e  lea     rcx, [rbp+0A0h+var_F8]
0x180001a32  mov     [rsp+1A0h+var_170], r9
0x180001a37  mov     r12, r9
0x180001a3a  mov     r15, r8
0x180001a3d  mov     r13, rdx
0x180001a40  call    cs:__imp_??0MULTISZ@@QEAA@XZ; MULTISZ::MULTISZ(void)
0x180001a46  lea     rcx, [rsp+1A0h+var_130]
0x180001a4b  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180001a51  lea     rcx, [rsp+1A0h+var_168]
0x180001a56  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180001a5c  lea     rdx, [rbp+0A0h+var_F8]; struct MULTISZ *
0x180001a60  mov     rcx, r13; struct INI_BINDING *
0x180001a63  call    ?ReadEntireSection@@YAJPEAUINI_BINDING@@PEAVMULTISZ@@@Z; ReadEntireSection(INI_BINDING *,MULTISZ *)
0x180001a68  mov     ebx, eax
0x180001a6a  test    eax, eax
0x180001a6c  js      loc_180001BBB
0x180001a72  mov     eax, [rbp+0A0h+var_C4]
0x180001a75  lea     rdx, [rbp+0A0h+var_80]
0x180001a79  add     eax, [rbp+0A0h+var_C8]
0x180001a7c  mov     rcx, r15
0x180001a7f  mov     [rsp+1A0h+var_180], eax
0x180001a83  xor     r14d, r14d
0x180001a86  mov     rax, [r15]
0x180001a89  xor     esi, esi
0x180001a8b  mov     rax, [rax]
0x180001a8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001a93  mov     rdi, rax
0x180001a96  test    rax, rax
0x180001a99  jz      loc_180001B9C
0x180001a9f  mov     rcx, [rdi]
0x180001aa2  mov     rax, [rcx]
0x180001aa5  mov     rcx, rdi
0x180001aa8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001aad  mov     rcx, [rdi]
0x180001ab0  mov     [rsp+1A0h+var_178], rax
0x180001ab5  mov     rax, [rcx+10h]
0x180001ab9  mov     rcx, rdi
0x180001abc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001ac1  mov     r12, rax
0x180001ac4  mov     rcx, [rax]
0x180001ac7  mov     rax, [rcx]
0x180001aca  jmp     loc_180001B60
0x180001acf  mov     rcx, [rdi]
0x180001ad2  mov     rax, [rcx]
0x180001ad5  mov     rcx, rdi
0x180001ad8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001add  mov     rdx, [rsp+1A0h+var_178]; unsigned __int16 *
0x180001ae2  lea     r8, [rsp+1A0h+var_130]; struct STRU *
0x180001ae7  mov     rcx, rax; unsigned __int16 *
0x180001aea  call    ?EncodeIniKeyName@@YAJPEBG0PEAVSTRU@@@Z; EncodeIniKeyName(ushort const *,ushort const *,STRU *)
0x180001aef  mov     ebx, eax
0x180001af1  test    eax, eax
0x180001af3  js      loc_180001BBB
0x180001af9  mov     rdx, [rbp+0A0h+var_110]; unsigned __int16 *
0x180001afd  lea     r8, [rsp+1A0h+var_168]; struct STRU *
0x180001b02  mov     rcx, r13; struct INI_BINDING *
0x180001b05  call    ?ReadValue@@YAJPEAUINI_BINDING@@PEBGPEAVSTRU@@@Z; ReadValue(INI_BINDING *,ushort const *,STRU *)
0x180001b0a  mov     ebx, eax
0x180001b0c  test    eax, eax
0x180001b0e  js      loc_180001BBB
0x180001b14  mov     ecx, [rsp+1A0h+var_138]
0x180001b18  test    ecx, ecx
0x180001b1a  jz      short loc_180001B24
0x180001b1c  add     ecx, 4
0x180001b1f  add     ecx, [rbp+0A0h+var_100]
0x180001b22  add     esi, ecx
0x180001b24  mov     rax, [rdi]
0x180001b27  mov     rcx, rdi
0x180001b2a  mov     rax, [rax+8]
0x180001b2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001b33  test    rax, rax
0x180001b36  jz      short loc_180001B58
0x180001b38  lea     rdx, [rsp+1A0h+var_168]; struct STRU *
0x180001b3d  mov     rcx, rdi; struct IPubProperty *
0x180001b40  call    ?EncodePropertyToString@@YAJPEAVIPubProperty@@PEAVSTRU@@@Z; EncodePropertyToString(IPubProperty *,STRU *)
0x180001b45  mov     ebx, eax
0x180001b47  test    eax, eax
0x180001b49  js      short loc_180001BBB
0x180001b4b  mov     ecx, [rsp+1A0h+var_138]
0x180001b4f  add     ecx, 4
0x180001b52  add     ecx, [rbp+0A0h+var_100]
0x180001b55  add     r14d, ecx
0x180001b58  mov     rax, [r12]
0x180001b5c  mov     rax, [rax+8]
0x180001b60  lea     rdx, [rbp+0A0h+var_C0]
0x180001b64  mov     rcx, r12
0x180001b67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001b6c  mov     rdi, rax
0x180001b6f  test    rax, rax
0x180001b72  jnz     loc_180001ACF
0x180001b78  mov     rax, [r15]
0x180001b7b  lea     rdx, [rbp+0A0h+var_80]
0x180001b7f  mov     rcx, r15
0x180001b82  mov     rax, [rax+8]
0x180001b86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001b8b  mov     rdi, rax
0x180001b8e  test    rax, rax
0x180001b91  jnz     loc_180001A9F
0x180001b97  mov     r12, [rsp+1A0h+var_170]
0x180001b9c  mov     eax, [rsp+1A0h+var_180]
0x180001ba0  add     eax, r14d
0x180001ba3  cmp     eax, r14d
0x180001ba6  jnb     short loc_180001BAD
0x180001ba8  or      eax, 0FFFFFFFFh
0x180001bab  jmp     short loc_180001BB7
0x180001bad  cmp     esi, eax
0x180001baf  ja      short loc_180001BB5
0x180001bb1  sub     eax, esi
0x180001bb3  jmp     short loc_180001BB7
0x180001bb5  xor     eax, eax
0x180001bb7  mov     [r12], eax
0x180001bbb  lea     rcx, [rsp+1A0h+var_168]
0x180001bc0  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180001bc6  lea     rcx, [rsp+1A0h+var_130]
0x180001bcb  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180001bd1  lea     rcx, [rbp+0A0h+var_F8]
0x180001bd5  call    cs:__imp_??1MULTISZ@@QEAA@XZ; MULTISZ::~MULTISZ(void)
0x180001bdb  mov     eax, ebx
0x180001bdd  mov     rcx, [rbp+0A0h+var_40]
0x180001be1  xor     rcx, rsp; StackCookie
0x180001be4  call    __security_check_cookie
0x180001be9  mov     rbx, [rsp+1A0h+arg_0]
0x180001bf1  add     rsp, 170h
0x180001bf8  pop     r15
0x180001bfa  pop     r14
0x180001bfc  pop     r13
0x180001bfe  pop     r12
0x180001c00  pop     rdi
0x180001c01  pop     rsi
0x180001c02  pop     rbp
0x180001c03  retn
```
