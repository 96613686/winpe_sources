# SdpSubstituteParamSet(ushort * *,ushort const *,_SDIAG_PARAMSET *)

- ea: `0x18000571c`
- end: `0x180005ac7`
- name: `?SdpSubstituteParamSet@@YAJPEAPEAGPEBGPEAU_SDIAG_PARAMSET@@@Z`
- size: `939`
- prototype: `__int64 __fastcall(unsigned __int16 **, const unsigned __int16 *, struct _SDIAG_PARAMSET *)`
- caller_count: `4`
- callee_count: `6`
- tags: `file_ops, loader_planting`

## callers

- `0x180002d20`
- `0x180018a9c`
- `0x18001cc2c`
- `0x180026500`

## callees

- `0x1800012a4`
- `0x1800012b0`
- `0x18000571c`
- `0x180026fa0`
- `0x180027aa0`
- `0x180029882`

## import_xrefs

- `ntdll!RtlCreateEnvironment` at `0x1800057bf`
- `ntdll!RtlCreateEnvironment` at `0x1800057bf`
- `ntdll!RtlDestroyEnvironment` at `0x180005a9a`
- `ntdll!RtlDestroyEnvironment` at `0x180005a9a`
- `ntdll!RtlExpandEnvironmentStrings` at `0x1800059b3`
- `ntdll!RtlExpandEnvironmentStrings` at `0x180005a39`
- `ntdll!RtlExpandEnvironmentStrings` at `0x1800059b3`
- `ntdll!RtlExpandEnvironmentStrings` at `0x180005a39`
- `ntdll!RtlSetEnvironmentVariable` at `0x1800058bb`
- `ntdll!RtlSetEnvironmentVariable` at `0x1800058bb`
- `ntdll!RtlInitUnicodeStringEx` at `0x18000583c`
- `ntdll!RtlInitUnicodeStringEx` at `0x180005881`
- `ntdll!RtlInitUnicodeStringEx` at `0x18000583c`
- `ntdll!RtlInitUnicodeStringEx` at `0x180005881`
- `ntdll!RtlNtStatusToDosError` at `0x1800057d0`
- `ntdll!RtlNtStatusToDosError` at `0x18000584c`
- `ntdll!RtlNtStatusToDosError` at `0x180005892`
- `ntdll!RtlNtStatusToDosError` at `0x1800058cc`
- `ntdll!RtlNtStatusToDosError` at `0x180005a4a`
- `ntdll!RtlNtStatusToDosError` at `0x1800057d0`
- `ntdll!RtlNtStatusToDosError` at `0x18000584c`
- `ntdll!RtlNtStatusToDosError` at `0x180005892`
- `ntdll!RtlNtStatusToDosError` at `0x1800058cc`
- `ntdll!RtlNtStatusToDosError` at `0x180005a4a`

## pseudocode

```c
__int64 __fastcall SdpSubstituteParamSet(unsigned __int16 **a1, const unsigned __int16 *a2, struct _SDIAG_PARAMSET *a3)
{
  unsigned __int16 *v6; // rsi
  unsigned int v7; // r8d
  int v8; // eax
  signed int v9; // ebx
  int v10; // r9d
  int v11; // eax
  signed int v12; // eax
  PWSTR v13; // r10
  unsigned int v14; // r14d
  const WCHAR *v15; // rdx
  int inited; // eax
  signed int v17; // eax
  const WCHAR *v18; // rdx
  int v19; // eax
  signed int v20; // eax
  int v21; // eax
  signed int v22; // eax
  const unsigned __int16 *v23; // rax
  __int64 v24; // rdx
  __int64 v25; // rdi
  NTSTATUS v26; // eax
  unsigned __int16 *v27; // rax
  unsigned __int64 v28; // rbx
  signed int v29; // eax
  struct _UNICODE_STRING Value; // [rsp+30h] [rbp-20h] BYREF
  _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-10h] BYREF
  PWSTR Environment; // [rsp+90h] [rbp+40h] BYREF
  unsigned __int64 v34; // [rsp+A8h] [rbp+58h] BYREF

  Environment = 0;
  v34 = 0;
  v6 = 0;
  DestinationString = 0;
  Value = 0;
  if ( !a1 )
  {
    v7 = 344;
LABEL_3:
    v8 = -2147024809;
    v9 = -2147024809;
LABEL_4:
    v10 = v8;
LABEL_5:
    SdpDebugTrace(1u, L"SdpSubstituteParamSet", v7, v10);
    goto LABEL_66;
  }
  if ( !a2 )
  {
    v7 = 345;
    goto LABEL_3;
  }
  if ( !a3 )
  {
    v7 = 346;
    goto LABEL_3;
  }
  if ( *(_QWORD *)a3 )
  {
    v11 = RtlCreateEnvironment(0, &Environment);
    if ( v11 < 0 )
    {
      v12 = RtlNtStatusToDosError(v11);
      v9 = v12;
      if ( v12 > 0 )
        v9 = (unsigned __int16)v12 | 0x80070000;
    }
    else
    {
      v9 = 0;
    }
    if ( v9 < 0 )
    {
      v10 = v9;
      v7 = 361;
      goto LABEL_5;
    }
    v13 = Environment;
    if ( !Environment )
    {
      v10 = -2147467261;
      v7 = 362;
      v9 = -2147467261;
      goto LABEL_5;
    }
    v14 = 0;
    if ( *((_DWORD *)a3 + 2) )
    {
      while ( 1 )
      {
        v15 = *(const WCHAR **)(*(_QWORD *)a3 + 24LL * v14);
        if ( !v15 )
          break;
        inited = RtlInitUnicodeStringEx(&DestinationString, v15);
        if ( inited < 0 )
        {
          v17 = RtlNtStatusToDosError(inited);
          v9 = v17;
          if ( v17 > 0 )
            v9 = (unsigned __int16)v17 | 0x80070000;
        }
        else
        {
          v9 = 0;
        }
        if ( v9 < 0 )
        {
          v10 = v9;
          v7 = 368;
          goto LABEL_5;
        }
        v18 = *(const WCHAR **)(*(_QWORD *)a3 + 24LL * v14 + 8);
        if ( !v18 )
        {
          v10 = -2147467261;
          v7 = 370;
          v9 = -2147467261;
          goto LABEL_5;
        }
        v19 = RtlInitUnicodeStringEx(&Value, v18);
        if ( v19 < 0 )
        {
          v20 = RtlNtStatusToDosError(v19);
          v9 = v20;
          if ( v20 > 0 )
            v9 = (unsigned __int16)v20 | 0x80070000;
        }
        else
        {
          v9 = 0;
        }
        if ( v9 < 0 )
        {
          v10 = v9;
          v7 = 373;
          goto LABEL_5;
        }
        v21 = RtlSetEnvironmentVariable(&Environment, &DestinationString, &Value);
        if ( v21 < 0 )
        {
          v22 = RtlNtStatusToDosError(v21);
          v9 = v22;
          if ( v22 > 0 )
            v9 = (unsigned __int16)v22 | 0x80070000;
        }
        else
        {
          v9 = 0;
        }
        if ( v9 < 0 )
        {
          v10 = v9;
          v7 = 376;
          goto LABEL_5;
        }
        if ( ++v14 >= *((_DWORD *)a3 + 2) )
        {
          v13 = Environment;
          goto LABEL_41;
        }
      }
      v10 = -2147467261;
      v7 = 365;
      v9 = -2147467261;
      goto LABEL_5;
    }
LABEL_41:
    v23 = a2;
    v24 = 1024;
    do
    {
      if ( !*v23 )
        break;
      ++v23;
      --v24;
    }
    while ( v24 );
    v9 = v24 == 0 ? 0x80070057 : 0;
    v25 = (1024 - v24) & -(__int64)(v24 != 0);
    if ( !v24 )
    {
      v10 = -2147024809;
      v7 = 380;
      goto LABEL_5;
    }
    v26 = RtlExpandEnvironmentStrings(
            v13,
            a2,
            (1024 - v24) & -(__int64)(v24 != 0),
            0,
            0,
            &v34,
            *(_QWORD *)&Value.Length,
            Value.Buffer,
            *(_QWORD *)&DestinationString.Length,
            DestinationString.Buffer);
    if ( v26 == -1073741789 )
    {
      if ( v34 > 0x400 )
      {
        v9 = -2147024785;
        v7 = 392;
        v10 = -2147024785;
        goto LABEL_5;
      }
      v27 = (unsigned __int16 *)operator new[](saturated_mul(v34, 2u));
      v6 = v27;
      if ( !v27 )
      {
        v9 = -2147024882;
        v7 = 396;
        v10 = -2147024882;
        goto LABEL_5;
      }
      v28 = v34;
      memset_0(v27, 0, 2 * v34);
      v26 = RtlExpandEnvironmentStrings(
              Environment,
              a2,
              v25,
              v6,
              v28,
              0,
              *(_QWORD *)&Value.Length,
              Value.Buffer,
              *(_QWORD *)&DestinationString.Length,
              DestinationString.Buffer);
    }
    if ( v26 < 0 )
    {
      v29 = RtlNtStatusToDosError(v26);
      v9 = v29;
      if ( v29 > 0 )
        v9 = (unsigned __int16)v29 | 0x80070000;
    }
    else
    {
      v9 = 0;
    }
    if ( v9 < 0 )
    {
      v10 = v9;
      v7 = 408;
      goto LABEL_5;
    }
    if ( !v6 )
    {
      v10 = -2147467261;
      v7 = 409;
      v9 = -2147467261;
      goto LABEL_5;
    }
    *a1 = v6;
    v6 = 0;
  }
  else
  {
    v8 = SdpStrCpy(a1, a2);
    v9 = v8;
    if ( v8 < 0 )
    {
      v7 = 355;
      goto LABEL_4;
    }
  }
LABEL_66:
  if ( Environment )
    RtlDestroyEnvironment(Environment);
  if ( v6 )
    operator delete(v6);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18000571c  mov     [rsp-38h+arg_8], rbx
0x180005721  push    rbp
0x180005722  push    rsi
0x180005723  push    rdi
0x180005724  push    r12
0x180005726  push    r13
0x180005728  push    r14
0x18000572a  push    r15
0x18000572c  mov     rbp, rsp
0x18000572f  sub     rsp, 50h
0x180005733  xor     r15d, r15d
0x180005736  xorps   xmm0, xmm0
0x180005739  mov     [rbp+Environment], r15
0x18000573d  xorps   xmm1, xmm1
0x180005740  mov     [rbp+arg_18], r15
0x180005744  mov     rdi, r8
0x180005747  mov     r12, rdx
0x18000574a  mov     r13, rcx
0x18000574d  mov     esi, r15d
0x180005750  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x180005754  movups  xmmword ptr [rbp+Value.Length], xmm1
0x180005758  test    rcx, rcx
0x18000575b  jnz     short loc_180005783
0x18000575d  mov     r8d, 158h; int
0x180005763  mov     eax, 80070057h
0x180005768  mov     ebx, eax
0x18000576a  mov     r9d, eax; int
0x18000576d  lea     rdx, aSdpsubstitutep; "SdpSubstituteParamSet"
0x180005774  mov     ecx, 1; Level
0x180005779  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18000577e  jmp     loc_180005A91
0x180005783  test    r12, r12
0x180005786  jnz     short loc_180005790
0x180005788  mov     r8d, 159h
0x18000578e  jmp     short loc_180005763
0x180005790  test    rdi, rdi
0x180005793  jnz     short loc_18000579D
0x180005795  mov     r8d, 15Ah
0x18000579b  jmp     short loc_180005763
0x18000579d  cmp     [r8], r15
0x1800057a0  jnz     short loc_1800057B9
0x1800057a2  call    ?SdpStrCpy@@YAJPEAPEAGPEBG@Z; SdpStrCpy(ushort * *,ushort const *)
0x1800057a7  mov     ebx, eax
0x1800057a9  test    eax, eax
0x1800057ab  jns     loc_180005A91
0x1800057b1  mov     r8d, 163h
0x1800057b7  jmp     short loc_18000576A
0x1800057b9  lea     rdx, [rbp+Environment]; Environment
0x1800057bd  xor     ecx, ecx; Inherit
0x1800057bf  call    cs:__imp_RtlCreateEnvironment
0x1800057c5  test    eax, eax
0x1800057c7  js      short loc_1800057CE
0x1800057c9  mov     ebx, r15d
0x1800057cc  jmp     short loc_1800057E5
0x1800057ce  mov     ecx, eax; Status
0x1800057d0  call    cs:__imp_RtlNtStatusToDosError
0x1800057d6  mov     ebx, eax
0x1800057d8  test    eax, eax
0x1800057da  jle     short loc_1800057E5
0x1800057dc  movzx   ebx, ax
0x1800057df  or      ebx, 80070000h
0x1800057e5  test    ebx, ebx
0x1800057e7  jns     short loc_1800057F7
0x1800057e9  mov     r9d, ebx
0x1800057ec  mov     r8d, 169h
0x1800057f2  jmp     loc_18000576D
0x1800057f7  mov     r10, [rbp+Environment]
0x1800057fb  test    r10, r10
0x1800057fe  jnz     short loc_180005814
0x180005800  mov     r9d, 80004003h
0x180005806  mov     r8d, 16Ah
0x18000580c  mov     ebx, r9d
0x18000580f  jmp     loc_18000576D
0x180005814  mov     r14d, r15d
0x180005817  cmp     [rdi+8], r15d
0x18000581b  jbe     loc_1800058F6
0x180005821  mov     eax, r14d
0x180005824  lea     r15, [rax+rax*2]
0x180005828  mov     rax, [rdi]
0x18000582b  mov     rdx, [rax+r15*8]; SourceString
0x18000582f  test    rdx, rdx
0x180005832  jz      loc_180005985
0x180005838  lea     rcx, [rbp+DestinationString]; DestinationString
0x18000583c  call    cs:__imp_RtlInitUnicodeStringEx
0x180005842  test    eax, eax
0x180005844  js      short loc_18000584A
0x180005846  xor     ebx, ebx
0x180005848  jmp     short loc_180005861
0x18000584a  mov     ecx, eax; Status
0x18000584c  call    cs:__imp_RtlNtStatusToDosError
0x180005852  mov     ebx, eax
0x180005854  test    eax, eax
0x180005856  jle     short loc_180005861
0x180005858  movzx   ebx, ax
0x18000585b  or      ebx, 80070000h
0x180005861  test    ebx, ebx
0x180005863  js      loc_180005977
0x180005869  mov     rax, [rdi]
0x18000586c  mov     rdx, [rax+r15*8+8]; SourceString
0x180005871  xor     r15d, r15d
0x180005874  test    rdx, rdx
0x180005877  jz      loc_180005963
0x18000587d  lea     rcx, [rbp+Value]; DestinationString
0x180005881  call    cs:__imp_RtlInitUnicodeStringEx
0x180005887  test    eax, eax
0x180005889  js      short loc_180005890
0x18000588b  mov     ebx, r15d
0x18000588e  jmp     short loc_1800058A7
0x180005890  mov     ecx, eax; Status
0x180005892  call    cs:__imp_RtlNtStatusToDosError
0x180005898  mov     ebx, eax
0x18000589a  test    eax, eax
0x18000589c  jle     short loc_1800058A7
0x18000589e  movzx   ebx, ax
0x1800058a1  or      ebx, 80070000h
0x1800058a7  test    ebx, ebx
0x1800058a9  js      loc_180005955
0x1800058af  lea     r8, [rbp+Value]; Value
0x1800058b3  lea     rdx, [rbp+DestinationString]; Name
0x1800058b7  lea     rcx, [rbp+Environment]; Environment
0x1800058bb  call    cs:__imp_RtlSetEnvironmentVariable
0x1800058c1  test    eax, eax
0x1800058c3  js      short loc_1800058CA
0x1800058c5  mov     ebx, r15d
0x1800058c8  jmp     short loc_1800058E1
0x1800058ca  mov     ecx, eax; Status
0x1800058cc  call    cs:__imp_RtlNtStatusToDosError
0x1800058d2  mov     ebx, eax
0x1800058d4  test    eax, eax
0x1800058d6  jle     short loc_1800058E1
0x1800058d8  movzx   ebx, ax
0x1800058db  or      ebx, 80070000h
0x1800058e1  test    ebx, ebx
0x1800058e3  js      short loc_180005947
0x1800058e5  inc     r14d
0x1800058e8  cmp     r14d, [rdi+8]
0x1800058ec  jb      loc_180005821
0x1800058f2  mov     r10, [rbp+Environment]
0x1800058f6  mov     r14d, 400h
0x1800058fc  mov     rax, r12
0x1800058ff  mov     edx, r14d
0x180005902  cmp     [rax], r15w
0x180005906  jz      short loc_180005912
0x180005908  add     rax, 2
0x18000590c  sub     rdx, 1
0x180005910  jnz     short loc_180005902
0x180005912  mov     rax, rdx
0x180005915  mov     rcx, r14
0x180005918  neg     rax
0x18000591b  mov     rax, rdx
0x18000591e  sbb     ebx, ebx
0x180005920  sub     rcx, rdx
0x180005923  not     ebx
0x180005925  and     ebx, 80070057h
0x18000592b  neg     rax
0x18000592e  sbb     rdi, rdi
0x180005931  and     rdi, rcx
0x180005934  test    rdx, rdx
0x180005937  jnz     short loc_180005999
0x180005939  mov     r9d, ebx
0x18000593c  mov     r8d, 17Ch
0x180005942  jmp     loc_18000576D
0x180005947  mov     r9d, ebx
0x18000594a  mov     r8d, 178h
0x180005950  jmp     loc_18000576D
0x180005955  mov     r9d, ebx
0x180005958  mov     r8d, 175h
0x18000595e  jmp     loc_18000576D
0x180005963  mov     r9d, 80004003h
0x180005969  mov     r8d, 172h
0x18000596f  mov     ebx, r9d
0x180005972  jmp     loc_18000576D
0x180005977  mov     r9d, ebx
0x18000597a  mov     r8d, 170h
0x180005980  jmp     loc_18000576D
0x180005985  mov     r9d, 80004003h
0x18000598b  mov     r8d, 16Dh
0x180005991  mov     ebx, r9d
0x180005994  jmp     loc_18000576D
0x180005999  lea     rax, [rbp+arg_18]
0x18000599d  xor     r9d, r9d
0x1800059a0  mov     [rsp+50h+var_28], rax
0x1800059a5  mov     r8, rdi
0x1800059a8  mov     rdx, r12
0x1800059ab  mov     [rsp+50h+var_30], r15
0x1800059b0  mov     rcx, r10
0x1800059b3  call    cs:__imp_RtlExpandEnvironmentStrings
0x1800059b9  cmp     eax, 0C0000023h
0x1800059be  jnz     short loc_180005A3F
0x1800059c0  cmp     [rbp+arg_18], r14
0x1800059c4  jbe     short loc_1800059D9
0x1800059c6  mov     ebx, 8007006Fh
0x1800059cb  mov     r8d, 188h
0x1800059d1  mov     r9d, ebx
0x1800059d4  jmp     loc_18000576D
0x1800059d9  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800059e0  mov     eax, 2
0x1800059e5  mul     [rbp+arg_18]
0x1800059e9  cmovb   rax, rcx
0x1800059ed  mov     rcx, rax; unsigned __int64
0x1800059f0  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800059f5  mov     rsi, rax
0x1800059f8  test    rax, rax
0x1800059fb  jnz     short loc_180005A10
0x1800059fd  mov     ebx, 8007000Eh
0x180005a02  mov     r8d, 18Ch
0x180005a08  mov     r9d, ebx
0x180005a0b  jmp     loc_18000576D
0x180005a10  mov     rbx, [rbp+arg_18]
0x180005a14  xor     edx, edx; Val
0x180005a16  mov     rcx, rsi; void *
0x180005a19  lea     r8, [rbx+rbx]; Size
0x180005a1d  call    memset_0
0x180005a22  mov     rcx, [rbp+Environment]
0x180005a26  mov     r9, rsi
0x180005a29  mov     r8, rdi
0x180005a2c  mov     [rsp+50h+var_28], r15
0x180005a31  mov     rdx, r12
0x180005a34  mov     [rsp+50h+var_30], rbx
0x180005a39  call    cs:__imp_RtlExpandEnvironmentStrings
0x180005a3f  test    eax, eax
0x180005a41  js      short loc_180005A48
0x180005a43  mov     ebx, r15d
0x180005a46  jmp     short loc_180005A5F
0x180005a48  mov     ecx, eax; Status
0x180005a4a  call    cs:__imp_RtlNtStatusToDosError
0x180005a50  mov     ebx, eax
0x180005a52  test    eax, eax
0x180005a54  jle     short loc_180005A5F
0x180005a56  movzx   ebx, ax
0x180005a59  or      ebx, 80070000h
0x180005a5f  test    ebx, ebx
0x180005a61  jns     short loc_180005A71
0x180005a63  mov     r9d, ebx
0x180005a66  mov     r8d, 198h
0x180005a6c  jmp     loc_18000576D
0x180005a71  test    rsi, rsi
0x180005a74  jnz     short loc_180005A8A
0x180005a76  mov     r9d, 80004003h
0x180005a7c  mov     r8d, 199h
0x180005a82  mov     ebx, r9d
0x180005a85  jmp     loc_18000576D
0x180005a8a  mov     [r13+0], rsi
0x180005a8e  mov     rsi, r15
0x180005a91  mov     rcx, [rbp+Environment]; Environment
0x180005a95  test    rcx, rcx
0x180005a98  jz      short loc_180005AA0
0x180005a9a  call    cs:__imp_RtlDestroyEnvironment
0x180005aa0  test    rsi, rsi
0x180005aa3  jz      short loc_180005AAD
0x180005aa5  mov     rcx, rsi; Block
0x180005aa8  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180005aad  mov     eax, ebx
0x180005aaf  mov     rbx, [rsp+50h+arg_8]
0x180005ab7  add     rsp, 50h
0x180005abb  pop     r15
0x180005abd  pop     r14
0x180005abf  pop     r13
0x180005ac1  pop     r12
0x180005ac3  pop     rdi
0x180005ac4  pop     rsi
0x180005ac5  pop     rbp
0x180005ac6  retn
```
