# ConnectionProviderImpl::RenewSecondaryChannel(unsigned __int64,ushort const *,ushort const *,ushort const *,ushort const *,ulong,ulong,long)

- ea: `0x180012810`
- end: `0x180012b06`
- name: `?RenewSecondaryChannel@ConnectionProviderImpl@@UEAAJ_KPEBG111KKJ@Z`
- size: `758`
- prototype: `int(ConnectionProviderImpl *__hidden this, unsigned __int64, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned int, unsigned int, int)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting`

## callees

- `0x18000fddc`
- `0x18000fe54`
- `0x180012810`
- `0x1800133b0`
- `0x180013728`
- `0x180096010`

## string_xrefs

- `0x180012882`: `onecoreuap\base\diagnosis\platform\notifications\prov\dll\connectionproviderimpl.cpp`
- `0x1800128d1`: `onecoreuap\base\diagnosis\platform\notifications\prov\dll\connectionproviderimpl.cpp`
- `0x18001291f`: `onecoreuap\base\diagnosis\platform\notifications\prov\dll\connectionproviderimpl.cpp`
- `0x180012972`: `onecoreuap\base\diagnosis\platform\notifications\prov\dll\connectionproviderimpl.cpp`
- `0x180012a7f`: `onecoreuap\base\diagnosis\platform\notifications\prov\dll\connectionproviderimpl.cpp`

## pseudocode

```c
__int64 __fastcall ConnectionProviderImpl::RenewSecondaryChannel(
        ConnectionProviderImpl *this,
        __int64 a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        const unsigned __int16 *a5,
        const unsigned __int16 *a6,
        unsigned int a7,
        unsigned int a8,
        int a9)
{
  PVOID *v12; // rcx
  unsigned int v13; // ebx
  PVOID *v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // r9
  int v17; // eax
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  v12 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_I(*((_QWORD *)WPP_GLOBAL_Control + 2), 75, &WPP_a895bbf08a1439ace591c2d232a3486a_Traceguids, a2);
    v12 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !a3 )
  {
    v13 = -2147467261;
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x168,
      (int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\dll\\connectionproviderimpl.cpp",
      (const char *)0x80004003LL);
    v14 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return v13;
    if ( *((char *)WPP_GLOBAL_Control + 28) >= 0 )
      goto LABEL_36;
    v15 = 76;
LABEL_9:
    v16 = 2147500035LL;
LABEL_34:
    WPP_SF_d(v14[2], v15, &WPP_a895bbf08a1439ace591c2d232a3486a_Traceguids, v16);
LABEL_35:
    v14 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_36;
  }
  if ( !a4 )
  {
    v13 = -2147467261;
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x169,
      (int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\dll\\connectionproviderimpl.cpp",
      (const char *)0x80004003LL);
    v14 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return v13;
    if ( *((char *)WPP_GLOBAL_Control + 28) >= 0 )
      goto LABEL_36;
    v15 = 77;
    goto LABEL_9;
  }
  if ( !a5 )
  {
    v13 = -2147467261;
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x16A,
      (int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\dll\\connectionproviderimpl.cpp",
      (const char *)0x80004003LL);
    v14 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return v13;
    if ( *((char *)WPP_GLOBAL_Control + 28) >= 0 )
      goto LABEL_36;
    v15 = 78;
    goto LABEL_9;
  }
  if ( !a6 )
  {
    v13 = -2147467261;
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x16B,
      (int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\dll\\connectionproviderimpl.cpp",
      (const char *)0x80004003LL);
    v14 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return v13;
    if ( *((char *)WPP_GLOBAL_Control + 28) >= 0 )
      goto LABEL_36;
    v15 = 79;
    goto LABEL_9;
  }
  if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 1) != 0 && *((_BYTE *)v12 + 25) >= 5u )
    WPP_SF_SSSDdd((TRACEHANDLE)v12[2], (__int64)a4, (__int64)a5, a7, a8, a9);
  v17 = (*(__int64 (__fastcall **)(_QWORD, __int64, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned int, unsigned int, int))(**((_QWORD **)this + 2) + 192LL))(
          *((_QWORD *)this + 2),
          a2,
          a3,
          a4,
          a5,
          a6,
          a7,
          a8,
          a9);
  v13 = v17;
  if ( v17 >= 0 )
    goto LABEL_35;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      81,
      &WPP_a895bbf08a1439ace591c2d232a3486a_Traceguids,
      (unsigned int)v17);
  }
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)0x170,
    (int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\dll\\connectionproviderimpl.cpp",
    (const char *)v13);
  v14 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( *((char *)WPP_GLOBAL_Control + 28) >= 0 )
    {
LABEL_36:
      if ( v14 != &WPP_GLOBAL_Control && (*((_BYTE *)v14 + 28) & 1) != 0 && *((_BYTE *)v14 + 25) >= 6u )
        WPP_SF_d(v14[2], 83, &WPP_a895bbf08a1439ace591c2d232a3486a_Traceguids, v13);
      return v13;
    }
    v15 = 82;
    v16 = v13;
    goto LABEL_34;
  }
  return v13;
}

```

## disassembly

```asm
0x180012810  mov     [rsp+arg_0], rcx
0x180012815  push    rbx
0x180012816  push    rbp
0x180012817  push    rsi
0x180012818  push    rdi
0x180012819  push    r12
0x18001281b  push    r13
0x18001281d  push    r14
0x18001281f  push    r15
0x180012821  sub     rsp, 58h
0x180012825  mov     rdi, r9
0x180012828  mov     rsi, r8
0x18001282b  mov     r13, rdx
0x18001282e  lea     r14, WPP_GLOBAL_Control
0x180012835  mov     rcx, cs:WPP_GLOBAL_Control
0x18001283c  cmp     rcx, r14
0x18001283f  jz      short loc_18001286C
0x180012841  test    byte ptr [rcx+1Ch], 1
0x180012845  jz      short loc_18001286C
0x180012847  cmp     byte ptr [rcx+19h], 6
0x18001284b  jb      short loc_18001286C
0x18001284d  mov     edx, 4Bh ; 'K'
0x180012852  mov     r9, r13
0x180012855  lea     r8, WPP_a895bbf08a1439ace591c2d232a3486a_Traceguids
0x18001285c  mov     rcx, [rcx+10h]
0x180012860  call    WPP_SF_I
0x180012865  mov     rcx, cs:WPP_GLOBAL_Control
0x18001286c  test    rsi, rsi
0x18001286f  jnz     short loc_1800128BB
0x180012871  mov     r9d, 80004003h; char *
0x180012877  mov     ebx, r9d
0x18001287a  mov     rcx, [rsp+98h]; this
0x180012882  lea     r8, aOnecoreuapBase_33; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180012889  mov     edx, 168h; void *
0x18001288e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180012893  mov     rcx, cs:WPP_GLOBAL_Control
0x18001289a  cmp     rcx, r14
0x18001289d  jz      loc_180012AF3
0x1800128a3  test    byte ptr [rcx+1Ch], 80h
0x1800128a7  jz      loc_180012ACA
0x1800128ad  lea     edx, [rsi+4Ch]
0x1800128b0  mov     r9d, 80004003h
0x1800128b6  jmp     loc_180012AAA
0x1800128bb  test    rdi, rdi
0x1800128be  jnz     short loc_180012901
0x1800128c0  mov     r9d, 80004003h; char *
0x1800128c6  mov     ebx, r9d
0x1800128c9  mov     rcx, [rsp+98h]; this
0x1800128d1  lea     r8, aOnecoreuapBase_33; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800128d8  mov     edx, 169h; void *
0x1800128dd  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800128e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800128e9  cmp     rcx, r14
0x1800128ec  jz      loc_180012AF3
0x1800128f2  test    byte ptr [rcx+1Ch], 80h
0x1800128f6  jz      loc_180012ACA
0x1800128fc  lea     edx, [rdi+4Dh]
0x1800128ff  jmp     short loc_1800128B0
0x180012901  mov     rbx, [rsp+98h+arg_20]
0x180012909  test    rbx, rbx
0x18001290c  jnz     short loc_180012954
0x18001290e  mov     r9d, 80004003h; char *
0x180012914  mov     ebx, r9d
0x180012917  mov     rcx, [rsp+98h]; this
0x18001291f  lea     r8, aOnecoreuapBase_33; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180012926  mov     edx, 16Ah; void *
0x18001292b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180012930  mov     rcx, cs:WPP_GLOBAL_Control
0x180012937  cmp     rcx, r14
0x18001293a  jz      loc_180012AF3
0x180012940  test    byte ptr [rcx+1Ch], 80h
0x180012944  jz      loc_180012ACA
0x18001294a  mov     edx, 4Eh ; 'N'
0x18001294f  jmp     loc_1800128B0
0x180012954  mov     rbp, [rsp+98h+arg_28]
0x18001295c  test    rbp, rbp
0x18001295f  jnz     short loc_1800129A5
0x180012961  mov     r9d, 80004003h; char *
0x180012967  mov     ebx, r9d
0x18001296a  mov     rcx, [rsp+98h]; this
0x180012972  lea     r8, aOnecoreuapBase_33; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180012979  mov     edx, 16Bh; void *
0x18001297e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180012983  mov     rcx, cs:WPP_GLOBAL_Control
0x18001298a  cmp     rcx, r14
0x18001298d  jz      loc_180012AF3
0x180012993  test    byte ptr [rcx+1Ch], 80h
0x180012997  jz      loc_180012ACA
0x18001299d  lea     edx, [rbp+4Fh]
0x1800129a0  jmp     loc_1800128B0
0x1800129a5  mov     r14d, dword ptr [rsp+98h+arg_40]
0x1800129ad  mov     r15d, dword ptr [rsp+98h+arg_38]
0x1800129b5  mov     r12d, dword ptr [rsp+98h+arg_30]
0x1800129bd  lea     rax, WPP_GLOBAL_Control
0x1800129c4  cmp     rcx, rax
0x1800129c7  jz      short loc_1800129FA
0x1800129c9  test    byte ptr [rcx+1Ch], 1
0x1800129cd  jz      short loc_1800129FA
0x1800129cf  cmp     byte ptr [rcx+19h], 5
0x1800129d3  jb      short loc_1800129FA
0x1800129d5  mov     dword ptr [rsp+98h+var_58], r14d; char
0x1800129da  mov     dword ptr [rsp+98h+var_60], r15d; char
0x1800129df  mov     dword ptr [rsp+98h+var_68], r12d; char
0x1800129e4  mov     [rsp+98h+var_70], rbx; __int64
0x1800129e9  mov     [rsp+98h+var_78], rdi; __int64
0x1800129ee  mov     r9, rsi
0x1800129f1  mov     rcx, [rcx+10h]; LoggerHandle
0x1800129f5  call    WPP_SF_SSSDdd
0x1800129fa  mov     rcx, [rsp+98h+arg_0]
0x180012a02  mov     rcx, [rcx+10h]
0x180012a06  mov     rax, [rcx]
0x180012a09  mov     dword ptr [rsp+98h+var_58], r14d
0x180012a0e  mov     dword ptr [rsp+98h+var_60], r15d
0x180012a13  mov     dword ptr [rsp+98h+var_68], r12d
0x180012a18  mov     [rsp+98h+var_70], rbp
0x180012a1d  mov     [rsp+98h+var_78], rbx; int
0x180012a22  mov     r9, rdi
0x180012a25  mov     r8, rsi
0x180012a28  mov     rdx, r13
0x180012a2b  mov     rax, [rax+0C0h]
0x180012a32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012a37  mov     ebx, eax
0x180012a39  test    eax, eax
0x180012a3b  jns     short loc_180012ABC
0x180012a3d  mov     rcx, cs:WPP_GLOBAL_Control
0x180012a44  lea     r14, WPP_GLOBAL_Control
0x180012a4b  cmp     rcx, r14
0x180012a4e  jz      short loc_180012A74
0x180012a50  test    byte ptr [rcx+1Ch], 1
0x180012a54  jz      short loc_180012A74
0x180012a56  cmp     byte ptr [rcx+19h], 2
0x180012a5a  jb      short loc_180012A74
0x180012a5c  mov     edx, 51h ; 'Q'
0x180012a61  mov     r9d, eax
0x180012a64  lea     r8, WPP_a895bbf08a1439ace591c2d232a3486a_Traceguids
0x180012a6b  mov     rcx, [rcx+10h]
0x180012a6f  call    WPP_SF_d
0x180012a74  mov     rcx, [rsp+98h]; this
0x180012a7c  mov     r9d, ebx; char *
0x180012a7f  lea     r8, aOnecoreuapBase_33; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180012a86  mov     edx, 170h; void *
0x180012a8b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180012a90  mov     rcx, cs:WPP_GLOBAL_Control
0x180012a97  cmp     rcx, r14
0x180012a9a  jz      short loc_180012AF3
0x180012a9c  test    byte ptr [rcx+1Ch], 80h
0x180012aa0  jz      short loc_180012ACA
0x180012aa2  mov     edx, 52h ; 'R'
0x180012aa7  mov     r9d, ebx
0x180012aaa  lea     r8, WPP_a895bbf08a1439ace591c2d232a3486a_Traceguids
0x180012ab1  mov     rcx, [rcx+10h]
0x180012ab5  call    WPP_SF_d
0x180012aba  jmp     short loc_180012AC3
0x180012abc  lea     r14, WPP_GLOBAL_Control
0x180012ac3  mov     rcx, cs:WPP_GLOBAL_Control
0x180012aca  cmp     rcx, r14
0x180012acd  jz      short loc_180012AF3
0x180012acf  test    byte ptr [rcx+1Ch], 1
0x180012ad3  jz      short loc_180012AF3
0x180012ad5  cmp     byte ptr [rcx+19h], 6
0x180012ad9  jb      short loc_180012AF3
0x180012adb  mov     edx, 53h ; 'S'
0x180012ae0  mov     r9d, ebx
0x180012ae3  lea     r8, WPP_a895bbf08a1439ace591c2d232a3486a_Traceguids
0x180012aea  mov     rcx, [rcx+10h]
0x180012aee  call    WPP_SF_d
0x180012af3  mov     eax, ebx
0x180012af5  add     rsp, 58h
0x180012af9  pop     r15
0x180012afb  pop     r14
0x180012afd  pop     r13
0x180012aff  pop     r12
0x180012b01  pop     rdi
0x180012b02  pop     rsi
0x180012b03  pop     rbp
0x180012b04  pop     rbx
0x180012b05  retn
```
