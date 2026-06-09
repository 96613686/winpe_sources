# INI_STORE::GetProperties(IPubResource *,IPubNamespaceSet *)

- ea: `0x180002220`
- end: `0x1800023f3`
- name: `?GetProperties@INI_STORE@@UEAAJPEAVIPubResource@@PEAVIPubNamespaceSet@@@Z`
- size: `467`
- prototype: `__int64 __fastcall(INI_STORE *this, struct IPubResource *, struct IPubNamespaceSet *)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x180002220`
- `0x180002974`
- `0x180002b34`
- `0x180002fd0`
- `0x180003280`
- `0x180003490`
- `0x180004010`

## import_xrefs

- `iisutil!??0STRU@@QEAA@XZ` at `0x180002259`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180002263`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000226e`
- `iisutil!??0STRU@@QEAA@XZ` at `0x1800022f0`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180002259`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180002263`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000226e`
- `iisutil!??0STRU@@QEAA@XZ` at `0x1800022f0`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180002326`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800023b1`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800023bb`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800023c5`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180002326`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800023b1`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800023bb`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800023c5`

## pseudocode

```c
__int64 __fastcall INI_STORE::GetProperties(INI_STORE *this, struct IPubResource *a2, struct IPubNamespaceSet *a3)
{
  int IniBinding; // ebx
  __int64 (__fastcall ***i)(_QWORD); // rax
  const unsigned __int16 *v8; // r15
  __int64 v9; // r14
  struct IPubProperty *j; // rax
  const unsigned __int16 *v11; // rbx
  __int64 v12; // rax
  struct IPubProperty *v13; // rdi
  __int64 (__fastcall ***v14)(_QWORD); // rdi
  _BYTE v16[32]; // [rsp+20h] [rbp-E0h] BYREF
  unsigned __int16 *v17; // [rsp+40h] [rbp-C0h]
  int v18; // [rsp+50h] [rbp-B0h]
  _BYTE v19[32]; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 *v20; // [rsp+78h] [rbp-88h]
  LPCWSTR v21[7]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v22[56]; // [rsp+C8h] [rbp-38h] BYREF
  _BYTE v23[64]; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v24[64]; // [rsp+140h] [rbp+40h] BYREF

  STRU::STRU((STRU *)v21);
  STRU::STRU((STRU *)v22);
  STRU::STRU((STRU *)v16);
  IniBinding = MakeIniBinding(a2, (INI_STORE *)((char *)this + 12), (struct INI_BINDING *)v21, 0);
  if ( IniBinding >= 0 )
  {
    for ( i = (__int64 (__fastcall ***)(_QWORD))(**(__int64 (__fastcall ***)(struct IPubNamespaceSet *, _BYTE *))a3)(
                                                  a3,
                                                  v24);
          ;
          i = (__int64 (__fastcall ***)(_QWORD))(*(__int64 (__fastcall **)(struct IPubNamespaceSet *, _BYTE *))(*(_QWORD *)a3 + 8LL))(
                                                  a3,
                                                  v24) )
    {
      v14 = i;
      if ( !i || IniBinding < 0 )
        break;
      v8 = (const unsigned __int16 *)(**i)(i);
      v9 = (*v14)[2](v14);
      for ( j = (struct IPubProperty *)(**(__int64 (__fastcall ***)(__int64, _BYTE *))v9)(v9, v23);
            ;
            j = (struct IPubProperty *)(*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v9 + 8LL))(v9, v23) )
      {
        v13 = j;
        if ( !j || IniBinding < 0 )
          break;
        v11 = (const unsigned __int16 *)(**(__int64 (__fastcall ***)(struct IPubProperty *))j)(j);
        STRU::STRU((STRU *)v19);
        IniBinding = EncodeIniKeyName(v11, v8, (struct STRU *)v19);
        if ( IniBinding >= 0 )
          IniBinding = ReadValue(v21, v20, (struct STRU *)v16);
        STRU::~STRU((STRU *)v19);
        if ( IniBinding >= 0 && v18 )
        {
          IniBinding = DecodePropertyFromString(v17, v13);
          v12 = *(_QWORD *)v13;
          if ( IniBinding < 0 )
            (*(void (__fastcall **)(struct IPubProperty *, _QWORD))(v12 + 56))(v13, (unsigned int)IniBinding);
          else
            (*(void (__fastcall **)(struct IPubProperty *, __int64, _QWORD))(v12 + 48))(v13, 200, 0);
        }
      }
    }
  }
  STRU::~STRU((STRU *)v16);
  STRU::~STRU((STRU *)v22);
  STRU::~STRU((STRU *)v21);
  return (unsigned int)IniBinding;
}

```

## disassembly

```asm
0x180002220  mov     [rsp-8+arg_18], rbx
0x180002225  push    rbp
0x180002226  push    rsi
0x180002227  push    rdi
0x180002228  push    r14
0x18000222a  push    r15
0x18000222c  lea     rbp, [rsp-90h]
0x180002234  sub     rsp, 190h
0x18000223b  mov     rax, cs:__security_cookie
0x180002242  xor     rax, rsp
0x180002245  mov     [rbp+0B0h+var_30], rax
0x18000224c  mov     rbx, rcx
0x18000224f  mov     rsi, r8
0x180002252  lea     rcx, [rbp+0B0h+var_120]
0x180002256  mov     rdi, rdx
0x180002259  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18000225f  lea     rcx, [rbp+0B0h+var_E8]
0x180002263  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180002269  lea     rcx, [rsp+1B0h+var_190]
0x18000226e  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180002274  lea     rdx, [rbx+0Ch]; struct INI_OPTIONS *
0x180002278  xor     r9d, r9d; int
0x18000227b  lea     r8, [rbp+0B0h+var_120]; struct INI_BINDING *
0x18000227f  mov     rcx, rdi; struct IPubResource *
0x180002282  call    ?MakeIniBinding@@YAJPEAVIPubResource@@PEAUINI_OPTIONS@@PEAUINI_BINDING@@H@Z; MakeIniBinding(IPubResource *,INI_OPTIONS *,INI_BINDING *,int)
0x180002287  mov     ebx, eax
0x180002289  test    eax, eax
0x18000228b  js      loc_1800023AC
0x180002291  mov     rax, [rsi]
0x180002294  mov     rax, [rax]
0x180002297  jmp     loc_180002394
0x18000229c  test    ebx, ebx
0x18000229e  js      loc_1800023AC
0x1800022a4  mov     rcx, [rdi]
0x1800022a7  mov     rax, [rcx]
0x1800022aa  mov     rcx, rdi
0x1800022ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800022b2  mov     rcx, [rdi]
0x1800022b5  mov     r15, rax
0x1800022b8  mov     rax, [rcx+10h]
0x1800022bc  mov     rcx, rdi
0x1800022bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800022c4  mov     r14, rax
0x1800022c7  mov     rcx, [rax]
0x1800022ca  mov     rax, [rcx]
0x1800022cd  jmp     loc_180002375
0x1800022d2  test    ebx, ebx
0x1800022d4  js      loc_18000238D
0x1800022da  mov     rcx, [rdi]
0x1800022dd  mov     rax, [rcx]
0x1800022e0  mov     rcx, rdi
0x1800022e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800022e8  lea     rcx, [rsp+1B0h+var_158]
0x1800022ed  mov     rbx, rax
0x1800022f0  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x1800022f6  lea     r8, [rsp+1B0h+var_158]; struct STRU *
0x1800022fb  mov     rdx, r15; unsigned __int16 *
0x1800022fe  mov     rcx, rbx; unsigned __int16 *
0x180002301  call    ?EncodeIniKeyName@@YAJPEBG0PEAVSTRU@@@Z; EncodeIniKeyName(ushort const *,ushort const *,STRU *)
0x180002306  mov     ebx, eax
0x180002308  test    eax, eax
0x18000230a  js      short loc_180002321
0x18000230c  mov     rdx, [rsp+1B0h+var_138]; unsigned __int16 *
0x180002311  lea     r8, [rsp+1B0h+var_190]; struct STRU *
0x180002316  lea     rcx, [rbp+0B0h+var_120]; struct INI_BINDING *
0x18000231a  call    ?ReadValue@@YAJPEAUINI_BINDING@@PEBGPEAVSTRU@@@Z; ReadValue(INI_BINDING *,ushort const *,STRU *)
0x18000231f  mov     ebx, eax
0x180002321  lea     rcx, [rsp+1B0h+var_158]
0x180002326  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000232c  test    ebx, ebx
0x18000232e  js      short loc_18000236E
0x180002330  cmp     [rsp+1B0h+var_160], 0
0x180002335  jbe     short loc_18000236E
0x180002337  mov     rcx, [rsp+1B0h+var_170]; unsigned __int16 *
0x18000233c  mov     rdx, rdi; struct IPubProperty *
0x18000233f  call    ?DecodePropertyFromString@@YAJPEBGPEAVIPubProperty@@@Z; DecodePropertyFromString(ushort const *,IPubProperty *)
0x180002344  mov     ebx, eax
0x180002346  mov     rcx, rdi
0x180002349  mov     rax, [rdi]
0x18000234c  test    ebx, ebx
0x18000234e  js      short loc_180002363
0x180002350  mov     rax, [rax+30h]
0x180002354  xor     r8d, r8d
0x180002357  mov     edx, 0C8h
0x18000235c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002361  jmp     short loc_18000236E
0x180002363  mov     rax, [rax+38h]
0x180002367  mov     edx, ebx
0x180002369  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000236e  mov     rax, [r14]
0x180002371  mov     rax, [rax+8]
0x180002375  lea     rdx, [rbp+0B0h+var_B0]
0x180002379  mov     rcx, r14
0x18000237c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002381  mov     rdi, rax
0x180002384  test    rax, rax
0x180002387  jnz     loc_1800022D2
0x18000238d  mov     rax, [rsi]
0x180002390  mov     rax, [rax+8]
0x180002394  lea     rdx, [rbp+0B0h+var_70]
0x180002398  mov     rcx, rsi
0x18000239b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800023a0  mov     rdi, rax
0x1800023a3  test    rax, rax
0x1800023a6  jnz     loc_18000229C
0x1800023ac  lea     rcx, [rsp+1B0h+var_190]
0x1800023b1  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1800023b7  lea     rcx, [rbp+0B0h+var_E8]
0x1800023bb  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1800023c1  lea     rcx, [rbp+0B0h+var_120]
0x1800023c5  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1800023cb  mov     eax, ebx
0x1800023cd  mov     rcx, [rbp+0B0h+var_30]
0x1800023d4  xor     rcx, rsp; StackCookie
0x1800023d7  call    __security_check_cookie
0x1800023dc  mov     rbx, [rsp+1B0h+arg_18]
0x1800023e4  add     rsp, 190h
0x1800023eb  pop     r15
0x1800023ed  pop     r14
0x1800023ef  pop     rdi
0x1800023f0  pop     rsi
0x1800023f1  pop     rbp
0x1800023f2  retn
```
