# VolumeGetConfig(CUwfStaticConfiguration *,ushort const *,ushort const *,CUwfStaticVolumeConfiguration * *)

- ea: `0x180011130`
- end: `0x18001148a`
- name: `?VolumeGetConfig@@YAJPEAVCUwfStaticConfiguration@@PEBG1PEAPEAVCUwfStaticVolumeConfiguration@@@Z`
- size: `858`
- prototype: `__int64 __fastcall(struct CUwfStaticConfiguration *this, const unsigned __int16 *, const unsigned __int16 *, struct CUwfStaticVolumeConfiguration **)`
- caller_count: `3`
- callee_count: `11`
- tags: `file_ops, registry_config`

## callers

- `0x180017e90`
- `0x1800197d0`
- `0x18001aad4`

## callees

- `0x180001390`
- `0x180002468`
- `0x180008300`
- `0x180008cf0`
- `0x18000e0f0`
- `0x18000e320`
- `0x180011130`
- `0x180011870`
- `0x18001afe2`
- `0x18001b020`
- `0x18001c010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180011398`
- `msvcrt!_wcsicmp` at `0x1800113f0`
- `msvcrt!_wcsicmp` at `0x180011398`
- `msvcrt!_wcsicmp` at `0x1800113f0`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001135a`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800113b6`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180011451`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001145c`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001135a`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800113b6`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180011451`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001145c`

## pseudocode

```c
__int64 __fastcall VolumeGetConfig(
        struct CUwfStaticConfiguration *this,
        wchar_t *a2,
        wchar_t *a3,
        struct CUwfStaticVolumeConfiguration **a4)
{
  int v8; // ebx
  __int64 v9; // rsi
  char v10; // r14
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // rcx
  int DWORDValue; // edi
  unsigned __int64 v15; // rsi
  HKEY *v16; // r13
  unsigned int v17; // r12d
  HKEY *v18; // rsi
  char *v19; // rax
  HKEY *v20; // rax
  bool v21; // sf
  wchar_t *String1; // [rsp+38h] [rbp-A1h] BYREF
  wchar_t *v24; // [rsp+40h] [rbp-99h]
  unsigned int v25; // [rsp+48h] [rbp-91h] BYREF
  wchar_t *String2; // [rsp+50h] [rbp-89h]
  wchar_t *v27; // [rsp+58h] [rbp-81h]
  struct CUwfStaticVolumeConfiguration **v28; // [rsp+60h] [rbp-79h]
  unsigned __int16 v29[4]; // [rsp+70h] [rbp-69h] BYREF
  char v30; // [rsp+78h] [rbp-61h] BYREF

  v27 = a3;
  String2 = a2;
  v28 = a4;
  v25 = 0;
  v8 = -2147023728;
  memset_0(v29, 0, 0x66u);
  v9 = -1;
  String1 = 0;
  v24 = 0;
  v10 = 0;
  if ( a2 )
  {
    v11 = -1;
    do
      ++v11;
    while ( a2[v11] );
    if ( v11 )
      v10 = 1;
  }
  if ( !a3 )
    goto LABEL_22;
  v12 = -1;
  do
    ++v12;
  while ( a3[v12] );
  if ( !v12 )
  {
LABEL_22:
    if ( !v10 )
    {
LABEL_23:
      v8 = -2147024809;
LABEL_42:
      if ( this )
        CUwfStaticConfiguration::ReleaseStaticVolumeConfiguration(this);
      goto LABEL_44;
    }
LABEL_15:
    if ( a4 )
    {
      DWORDValue = CUwfRegKey::QueryDWORDValue((HKEY *)this + 3, L"NumVolumes", (BYTE *)&v25);
      if ( DWORDValue < 0 )
        goto LABEL_38;
      v16 = 0;
      v17 = 0;
      if ( !v25 )
        goto LABEL_38;
      while ( 1 )
      {
        CUwfStaticConfiguration::ReleaseStaticVolumeConfiguration(this);
        v18 = (HKEY *)*((_QWORD *)this + 5);
        if ( v18 )
        {
          v20 = 0;
          DWORDValue = 0;
        }
        else
        {
          v19 = (char *)operator new(0x28u);
          v18 = (HKEY *)v19;
          if ( !v19 )
          {
            v8 = -2147024882;
            goto LABEL_42;
          }
          *(_WORD *)(v19 + 9) = 1;
          *(_QWORD *)v19 = &CUwfStaticVolumeConfiguration::`vftable';
          *((_DWORD *)v19 + 3) = -1;
          *((_QWORD *)v19 + 2) = 0;
          *((_QWORD *)v19 + 3) = 0;
          *((_QWORD *)v19 + 4) = 0;
          DWORDValue = CUwfStaticVolumeConfiguration::Initialize(
                         (CUwfStaticVolumeConfiguration *)v19,
                         *((HKEY *)this + 3),
                         v17,
                         *((_BYTE *)this + 8),
                         *((struct CUwfConfiguration **)this + 4),
                         this);
          if ( DWORDValue < 0 )
            goto LABEL_28;
          *((_QWORD *)this + 5) = v18;
          v20 = v18;
        }
        if ( *((_DWORD *)v18 + 3) == v17 )
        {
          v16 = v18;
          goto LABEL_29;
        }
        v18 = v20;
        DWORDValue = -2147024891;
        if ( !v20 )
          goto LABEL_31;
LABEL_28:
        (*(void (__fastcall **)(HKEY *, __int64))*v18)(v18, 1);
LABEL_29:
        if ( DWORDValue == -2147024893 )
        {
          DWORDValue = 0;
          goto LABEL_34;
        }
LABEL_31:
        v21 = DWORDValue < 0;
        if ( DWORDValue < 0 )
          goto LABEL_39;
        operator delete[](String1);
        String1 = 0;
        DWORDValue = CUwfRegKey::QuerySzValue(v16 + 2, L"VolumeName", &String1);
        if ( DWORDValue >= 0 && !_wcsicmp(String1, String2) )
        {
          v8 = 0;
          *v28 = (struct CUwfStaticVolumeConfiguration *)v16;
          goto LABEL_38;
        }
LABEL_34:
        if ( ++v17 >= v25 )
          goto LABEL_38;
      }
    }
    goto LABEL_23;
  }
  if ( v10 )
    goto LABEL_15;
  DWORDValue = VolumeGetVolumeGuid(a3, v29, 0x33u);
  if ( DWORDValue >= 0 )
  {
    do
      ++v9;
    while ( v29[v9] );
    v15 = 2 * v9 - 2;
    if ( v15 >= 0x66 )
      _report_rangecheckfailure(v13, 0);
    *(unsigned __int16 *)((char *)v29 + v15) = 0;
    String2 = (wchar_t *)&v30;
    goto LABEL_15;
  }
LABEL_38:
  v21 = DWORDValue < 0;
LABEL_39:
  if ( v21 )
    v8 = DWORDValue;
  if ( v8 < 0 )
    goto LABEL_42;
LABEL_44:
  operator delete[](String1);
  operator delete[](v24);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180011130  push    rbp
0x180011132  push    rbx
0x180011133  push    rsi
0x180011134  push    rdi
0x180011135  push    r12
0x180011137  push    r13
0x180011139  push    r14
0x18001113b  push    r15
0x18001113d  lea     rbp, [rsp-1Fh]
0x180011142  sub     rsp, 0F8h
0x180011149  mov     rax, cs:__security_cookie
0x180011150  xor     rax, rsp
0x180011153  mov     [rbp+57h+var_50], rax
0x180011157  xor     eax, eax
0x180011159  mov     [rsp+130h+var_D8], r8
0x18001115e  mov     r12, r8
0x180011161  mov     [rsp+130h+String2], rdx
0x180011166  mov     rdi, rdx
0x180011169  mov     [rbp+57h+var_D0], r9
0x18001116d  mov     r15, rcx
0x180011170  mov     [rsp+130h+var_E8], eax
0x180011174  lea     r8d, [rax+66h]; Size
0x180011178  xor     edx, edx; Val
0x18001117a  lea     rcx, [rbp+57h+var_C0]; void *
0x18001117e  mov     r13, r9
0x180011181  mov     ebx, 80070490h
0x180011186  call    memset_0
0x18001118b  xor     edx, edx
0x18001118d  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180011191  mov     [rsp+130h+String1], rdx
0x180011196  mov     [rsp+130h+var_F0], rdx
0x18001119b  movzx   r14d, dl
0x18001119f  lea     ecx, [rdx+1]
0x1800111a2  test    rdi, rdi
0x1800111a5  jz      short loc_1800111BA
0x1800111a7  mov     rax, rsi
0x1800111aa  inc     rax
0x1800111ad  cmp     [rdi+rax*2], dx
0x1800111b1  jnz     short loc_1800111AA
0x1800111b3  test    rax, rax
0x1800111b6  cmovnz  r14d, ecx
0x1800111ba  test    r12, r12
0x1800111bd  jz      loc_1800112F0
0x1800111c3  mov     rax, rsi
0x1800111c6  inc     rax
0x1800111c9  cmp     [r12+rax*2], dx
0x1800111ce  jnz     short loc_1800111C6
0x1800111d0  test    rax, rax
0x1800111d3  jz      loc_1800112F0
0x1800111d9  mov     [rsp+130h+var_FF], cl
0x1800111dd  test    r14b, r14b
0x1800111e0  jnz     short loc_180011230
0x1800111e2  mov     r8d, 33h ; '3'; unsigned int
0x1800111e8  lea     rdx, [rbp+57h+var_C0]; unsigned __int16 *
0x1800111ec  mov     rcx, r12; unsigned __int16 *
0x1800111ef  call    ?VolumeGetVolumeGuid@@YAJPEBGPEAGK@Z; VolumeGetVolumeGuid(ushort const *,ushort *,ulong)
0x1800111f4  xor     edx, edx
0x1800111f6  mov     edi, eax
0x1800111f8  test    eax, eax
0x1800111fa  js      loc_180011436
0x180011200  lea     rax, [rbp+57h+var_C0]
0x180011204  inc     rsi
0x180011207  cmp     [rax+rsi*2], dx
0x18001120b  jnz     short loc_180011204
0x18001120d  lea     rsi, ds:0FFFFFFFFFFFFFFFEh[rsi*2]
0x180011215  cmp     rsi, 66h ; 'f'
0x180011219  jnb     loc_180011484
0x18001121f  lea     rax, [rbp+57h+var_B8]
0x180011223  mov     [rbp+rsi+57h+var_C0], dx
0x180011228  mov     [rsp+130h+String2], rax
0x18001122d  mov     r14b, 1
0x180011230  test    r13, r13
0x180011233  jz      loc_1800112FD
0x180011239  lea     rcx, [r15+18h]; this
0x18001123d  lea     r8, [rsp+130h+var_E8]; unsigned int *
0x180011242  lea     rdx, aNumvolumes; "NumVolumes"
0x180011249  call    ?QueryDWORDValue@CUwfRegKey@@QEAAJPEBGPEAK@Z; CUwfRegKey::QueryDWORDValue(ushort const *,ulong *)
0x18001124e  mov     edi, eax
0x180011250  xor     edx, edx
0x180011252  test    eax, eax
0x180011254  js      loc_180011436
0x18001125a  mov     r13d, edx
0x18001125d  mov     [rsp+130h+var_100], dl
0x180011261  mov     r12d, edx
0x180011264  cmp     [rsp+130h+var_E8], edx
0x180011268  jbe     loc_180011436
0x18001126e  mov     rcx, r15; this
0x180011271  call    ?ReleaseStaticVolumeConfiguration@CUwfStaticConfiguration@@QEAAXXZ; CUwfStaticConfiguration::ReleaseStaticVolumeConfiguration(void)
0x180011276  mov     rsi, [r15+28h]
0x18001127a  xor     edx, edx
0x18001127c  test    rsi, rsi
0x18001127f  jnz     loc_180011307
0x180011285  lea     ecx, [rsi+28h]; Size
0x180011288  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001128d  xor     edx, edx
0x18001128f  mov     rsi, rax
0x180011292  test    rax, rax
0x180011295  jz      loc_180011426
0x18001129b  mov     word ptr [rsi+9], 1
0x1800112a1  lea     rax, ??_7CUwfStaticVolumeConfiguration@@6B@; const CUwfStaticVolumeConfiguration::`vftable'
0x1800112a8  mov     [rsi], rax
0x1800112ab  mov     r8d, r12d; unsigned int
0x1800112ae  mov     dword ptr [rsi+0Ch], 0FFFFFFFFh
0x1800112b5  mov     rcx, rsi; this
0x1800112b8  mov     [rsi+10h], rdx
0x1800112bc  mov     [rsi+18h], rdx
0x1800112c0  mov     [rsi+20h], rdx
0x1800112c4  mov     rax, [r15+20h]
0x1800112c8  mov     r9b, [r15+8]; bool
0x1800112cc  mov     rdx, [r15+18h]; HKEY
0x1800112d0  mov     [rsp+130h+var_108], r15; struct CUwfStaticConfiguration *
0x1800112d5  mov     [rsp+130h+var_110], rax; struct CUwfConfiguration *
0x1800112da  call    ?Initialize@CUwfStaticVolumeConfiguration@@QEAAJPEAUHKEY__@@K_NPEAVCUwfConfiguration@@PEAVCUwfStaticConfiguration@@@Z; CUwfStaticVolumeConfiguration::Initialize(HKEY__ *,ulong,bool,CUwfConfiguration *,CUwfStaticConfiguration *)
0x1800112df  xor     edx, edx
0x1800112e1  mov     edi, eax
0x1800112e3  test    eax, eax
0x1800112e5  js      short loc_180011324
0x1800112e7  mov     [r15+28h], rsi
0x1800112eb  mov     rax, rsi
0x1800112ee  jmp     short loc_18001130C
0x1800112f0  mov     [rsp+130h+var_FF], dl
0x1800112f4  test    r14b, r14b
0x1800112f7  jnz     loc_180011230
0x1800112fd  mov     ebx, 80070057h
0x180011302  jmp     loc_18001143F
0x180011307  mov     rax, rdx
0x18001130a  mov     edi, edx
0x18001130c  cmp     [rsi+0Ch], r12d
0x180011310  jnz     short loc_180011317
0x180011312  mov     r13, rsi
0x180011315  jmp     short loc_180011337
0x180011317  mov     rsi, rax
0x18001131a  mov     edi, 80070005h
0x18001131f  test    rax, rax
0x180011322  jz      short loc_180011348
0x180011324  mov     rax, [rsi]
0x180011327  mov     edx, 1
0x18001132c  mov     rcx, rsi
0x18001132f  mov     rax, [rax]
0x180011332  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011337  xor     edx, edx
0x180011339  cmp     edi, 80070003h
0x18001133f  jnz     short loc_180011348
0x180011341  mov     edi, edx
0x180011343  jmp     loc_180011416
0x180011348  test    edi, edi
0x18001134a  js      loc_180011438
0x180011350  test    r14b, r14b
0x180011353  jz      short loc_1800113AB
0x180011355  mov     rcx, [rsp+130h+String1]
0x18001135a  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180011360  xor     eax, eax
0x180011362  lea     rcx, [r13+10h]; this
0x180011366  lea     r8, [rsp+130h+String1]; unsigned __int16 **
0x18001136b  mov     [rsp+130h+String1], rax
0x180011370  lea     rdx, aVolumename; "VolumeName"
0x180011377  call    ?QuerySzValue@CUwfRegKey@@QEAAJPEBGPEAPEAG@Z; CUwfRegKey::QuerySzValue(ushort const *,ushort * *)
0x18001137c  mov     edi, eax
0x18001137e  test    eax, eax
0x180011380  mov     rax, [rsp+130h+String1]
0x180011385  mov     [rsp+130h+String1], rax
0x18001138a  js      loc_180011416
0x180011390  mov     rdx, [rsp+130h+String2]; String2
0x180011395  mov     rcx, rax; String1
0x180011398  call    cs:__imp__wcsicmp
0x18001139e  xor     edx, edx
0x1800113a0  test    eax, eax
0x1800113a2  setz    al
0x1800113a5  mov     [rsp+130h+var_100], al
0x1800113a9  jmp     short loc_180011412
0x1800113ab  cmp     [rsp+130h+var_FF], dl
0x1800113af  jz      short loc_18001140E
0x1800113b1  mov     rcx, [rsp+130h+var_F0]
0x1800113b6  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1800113bc  xor     eax, eax
0x1800113be  lea     rcx, [r13+10h]; this
0x1800113c2  lea     r8, [rsp+130h+var_F0]; unsigned __int16 **
0x1800113c7  mov     [rsp+130h+var_F0], rax
0x1800113cc  lea     rdx, aDriveletter; "DriveLetter"
0x1800113d3  call    ?QuerySzValue@CUwfRegKey@@QEAAJPEBGPEAPEAG@Z; CUwfRegKey::QuerySzValue(ushort const *,ushort * *)
0x1800113d8  mov     edi, eax
0x1800113da  test    eax, eax
0x1800113dc  js      short loc_180011402
0x1800113de  mov     rsi, [rsp+130h+var_F0]
0x1800113e3  mov     rdx, [rsp+130h+var_D8]; String2
0x1800113e8  mov     rcx, rsi; String1
0x1800113eb  mov     [rsp+130h+var_F0], rsi
0x1800113f0  call    cs:__imp__wcsicmp
0x1800113f6  xor     edx, edx
0x1800113f8  test    eax, eax
0x1800113fa  jz      short loc_18001142D
0x1800113fc  mov     [rsp+130h+var_100], dl
0x180011400  jmp     short loc_180011416
0x180011402  mov     rax, [rsp+130h+var_F0]
0x180011407  mov     [rsp+130h+var_F0], rax
0x18001140c  jmp     short loc_180011416
0x18001140e  mov     al, [rsp+130h+var_100]
0x180011412  test    al, al
0x180011414  jnz     short loc_18001142D
0x180011416  inc     r12d
0x180011419  cmp     r12d, [rsp+130h+var_E8]
0x18001141e  jb      loc_18001126E
0x180011424  jmp     short loc_180011436
0x180011426  mov     ebx, 8007000Eh
0x18001142b  jmp     short loc_18001143F
0x18001142d  mov     rax, [rbp+57h+var_D0]
0x180011431  mov     ebx, edx
0x180011433  mov     [rax], r13
0x180011436  test    edi, edi
0x180011438  cmovs   ebx, edi
0x18001143b  test    ebx, ebx
0x18001143d  jns     short loc_18001144C
0x18001143f  test    r15, r15
0x180011442  jz      short loc_18001144C
0x180011444  mov     rcx, r15; this
0x180011447  call    ?ReleaseStaticVolumeConfiguration@CUwfStaticConfiguration@@QEAAXXZ; CUwfStaticConfiguration::ReleaseStaticVolumeConfiguration(void)
0x18001144c  mov     rcx, [rsp+130h+String1]
0x180011451  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180011457  mov     rcx, [rsp+130h+var_F0]
0x18001145c  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180011462  mov     eax, ebx
0x180011464  mov     rcx, [rbp+57h+var_50]
0x180011468  xor     rcx, rsp; StackCookie
0x18001146b  call    __security_check_cookie
0x180011470  add     rsp, 0F8h
0x180011477  pop     r15
0x180011479  pop     r14
0x18001147b  pop     r13
0x18001147d  pop     r12
0x18001147f  pop     rdi
0x180011480  pop     rsi
0x180011481  pop     rbx
0x180011482  pop     rbp
0x180011483  retn
0x180011484  call    __report_rangecheckfailure
```
