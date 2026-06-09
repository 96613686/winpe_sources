# CUwfStaticConfiguration::get_StaticVolumeConfiguration(ushort const *,ushort const *,CUwfStaticVolumeConfiguration * *)

- ea: `0x18000b6b0`
- end: `0x18000b92f`
- name: `?get_StaticVolumeConfiguration@CUwfStaticConfiguration@@QEAAJPEBG0PEAPEAVCUwfStaticVolumeConfiguration@@@Z`
- size: `639`
- prototype: `__int64 __fastcall(CUwfStaticConfiguration *__hidden this, const unsigned __int16 *, wchar_t *String2, struct CUwfStaticVolumeConfiguration **)`
- caller_count: `2`
- callee_count: `12`
- tags: `file_ops, registry_config`

## callers

- `0x1800151b0`
- `0x180016468`

## callees

- `0x180001390`
- `0x180002468`
- `0x180008300`
- `0x180008cf0`
- `0x18000b6b0`
- `0x18000e0f0`
- `0x18000e320`
- `0x180011870`
- `0x18001afe2`
- `0x18001afee`
- `0x18001b020`
- `0x18001c010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000b896`
- `msvcrt!_wcsicmp` at `0x18000b896`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000b8a3`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000b8d3`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000b8a3`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000b8d3`

## pseudocode

```c
__int64 __fastcall CUwfStaticConfiguration::get_StaticVolumeConfiguration(
        CUwfStaticConfiguration *this,
        const unsigned __int16 *a2,
        wchar_t *String2,
        struct CUwfStaticVolumeConfiguration **a4)
{
  unsigned int v8; // r12d
  wchar_t *v9; // rsi
  int VolumeGuid; // ebx
  __int64 v11; // rdi
  __int64 v12; // rax
  char *v13; // r13
  char *v14; // rdi
  char *v15; // rax
  void (__fastcall ***v16)(_QWORD, __int64); // rcx
  struct CUwfStaticVolumeConfiguration **v17; // rax
  unsigned int v19; // [rsp+30h] [rbp-89h] BYREF
  wchar_t *v20; // [rsp+38h] [rbp-81h] BYREF
  struct CUwfStaticVolumeConfiguration **v21; // [rsp+40h] [rbp-79h]
  wchar_t String1[4]; // [rsp+50h] [rbp-69h] BYREF
  char v23; // [rsp+58h] [rbp-61h] BYREF

  v21 = a4;
  memset_0(String1, 0, 0x64u);
  v8 = 0;
  *a4 = 0;
  v9 = 0;
  v19 = 0;
  v20 = 0;
  if ( *((_QWORD *)this + 5) )
  {
    VolumeGuid = -2147024891;
    goto LABEL_32;
  }
  v11 = -1;
  if ( !String2 )
    goto LABEL_7;
  v12 = -1;
  do
    ++v12;
  while ( String2[v12] );
  if ( !v12 )
  {
LABEL_7:
    VolumeGuid = VolumeGetVolumeGuid(a2, String1, 0x32u);
    if ( VolumeGuid < 0 )
      goto LABEL_32;
    do
      ++v11;
    while ( String1[v11] );
    if ( String1[(unsigned int)(v11 - 1)] == 92 )
    {
      if ( 2 * (unsigned __int64)(unsigned int)(v11 - 1) >= 0x64 )
        _report_rangecheckfailure();
      String1[(unsigned int)(v11 - 1)] = 0;
    }
    String2 = (wchar_t *)&v23;
    if ( wcsncmp_0(String1, L"\\\\?\\", 4u) )
      String2 = String1;
  }
  VolumeGuid = CUwfRegKey::QueryDWORDValue((CUwfStaticConfiguration *)((char *)this + 24), L"NumVolumes", &v19);
  if ( VolumeGuid >= 0 )
  {
    v13 = 0;
    if ( v19 )
    {
      do
      {
        CUwfStaticConfiguration::ReleaseStaticVolumeConfiguration(this);
        v14 = (char *)*((_QWORD *)this + 5);
        VolumeGuid = 0;
        if ( v14 )
        {
          v16 = 0;
        }
        else
        {
          v15 = (char *)operator new(0x28u);
          v14 = v15;
          if ( !v15 )
          {
            VolumeGuid = -2147024882;
            goto LABEL_32;
          }
          *(_WORD *)(v15 + 9) = 1;
          *(_QWORD *)v15 = &CUwfStaticVolumeConfiguration::`vftable';
          *((_DWORD *)v15 + 3) = -1;
          *((_QWORD *)v15 + 2) = 0;
          *((_QWORD *)v15 + 3) = 0;
          *((_QWORD *)v15 + 4) = 0;
          VolumeGuid = CUwfStaticVolumeConfiguration::Initialize(
                         (CUwfStaticVolumeConfiguration *)v15,
                         *((HKEY *)this + 3),
                         v8,
                         *((_BYTE *)this + 8),
                         *((struct CUwfConfiguration **)this + 4),
                         this);
          v16 = (void (__fastcall ***)(_QWORD, __int64))v14;
          if ( VolumeGuid < 0 )
          {
LABEL_37:
            (**v16)(v16, 1);
            goto LABEL_32;
          }
          *((_QWORD *)this + 5) = v14;
        }
        if ( *((_DWORD *)v14 + 3) == v8 )
        {
          v13 = v14;
        }
        else
        {
          VolumeGuid = -2147024891;
          if ( v16 )
            goto LABEL_37;
        }
        if ( VolumeGuid < 0 )
          goto LABEL_32;
        VolumeGuid = CUwfRegKey::QuerySzValue((CUwfRegKey *)(v13 + 16), L"VolumeName", &v20);
        v9 = v20;
        if ( VolumeGuid < 0 )
          goto LABEL_32;
        if ( v20 && !_wcsicmp(v20, String2) )
        {
          v17 = v21;
          *v21 = (struct CUwfStaticVolumeConfiguration *)v13;
          goto LABEL_30;
        }
        operator delete[](v9);
        v9 = 0;
        ++v8;
        v20 = 0;
      }
      while ( v8 < v19 );
    }
    v17 = v21;
LABEL_30:
    if ( !*v17 )
      VolumeGuid = -2147024894;
  }
LABEL_32:
  operator delete[](v9);
  if ( VolumeGuid < 0 )
    CUwfStaticConfiguration::ReleaseStaticVolumeConfiguration(this);
  return (unsigned int)VolumeGuid;
}

```

## disassembly

```asm
0x18000b6b0  push    rbp
0x18000b6b2  push    rbx
0x18000b6b3  push    rsi
0x18000b6b4  push    rdi
0x18000b6b5  push    r12
0x18000b6b7  push    r13
0x18000b6b9  push    r14
0x18000b6bb  push    r15
0x18000b6bd  lea     rbp, [rsp-1Fh]
0x18000b6c2  sub     rsp, 0D8h
0x18000b6c9  mov     rax, cs:__security_cookie
0x18000b6d0  xor     rax, rsp
0x18000b6d3  mov     [rbp+57h+var_50], rax
0x18000b6d7  mov     rbx, rdx
0x18000b6da  mov     [rbp+57h+var_D0], r9
0x18000b6de  xor     edx, edx; Val
0x18000b6e0  mov     r14, r8
0x18000b6e3  mov     r15, rcx
0x18000b6e6  mov     rdi, r9
0x18000b6e9  lea     rcx, [rbp+57h+String1]; void *
0x18000b6ed  lea     r8d, [rdx+64h]; Size
0x18000b6f1  call    memset_0
0x18000b6f6  xor     r12d, r12d
0x18000b6f9  mov     [rdi], r12
0x18000b6fc  mov     esi, r12d
0x18000b6ff  mov     [rsp+110h+var_E0], r12d
0x18000b704  mov     [rsp+110h+var_D8], r12
0x18000b709  cmp     [r15+28h], r12
0x18000b70d  jz      short loc_18000B719
0x18000b70f  mov     ebx, 80070005h
0x18000b714  jmp     loc_18000B8D0
0x18000b719  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18000b71d  test    r14, r14
0x18000b720  jz      short loc_18000B734
0x18000b722  mov     rax, rdi
0x18000b725  inc     rax
0x18000b728  cmp     [r14+rax*2], r12w
0x18000b72d  jnz     short loc_18000B725
0x18000b72f  test    rax, rax
0x18000b732  jnz     short loc_18000B7A0
0x18000b734  mov     r8d, 32h ; '2'; unsigned int
0x18000b73a  lea     rdx, [rbp+57h+String1]; unsigned __int16 *
0x18000b73e  mov     rcx, rbx; unsigned __int16 *
0x18000b741  call    ?VolumeGetVolumeGuid@@YAJPEBGPEAGK@Z; VolumeGetVolumeGuid(ushort const *,ushort *,ulong)
0x18000b746  mov     ebx, eax
0x18000b748  test    eax, eax
0x18000b74a  js      loc_18000B8D0
0x18000b750  lea     rax, [rbp+57h+String1]
0x18000b754  inc     rdi
0x18000b757  cmp     [rax+rdi*2], r12w
0x18000b75c  jnz     short loc_18000B754
0x18000b75e  lea     ecx, [rdi-1]
0x18000b761  add     rcx, rcx
0x18000b764  cmp     [rbp+rcx+57h+String1], 5Ch ; '\'
0x18000b76a  jnz     short loc_18000B77C
0x18000b76c  cmp     rcx, 64h ; 'd'
0x18000b770  jnb     loc_18000B929
0x18000b776  mov     [rbp+rcx+57h+String1], r12w
0x18000b77c  mov     r8d, 4; MaxCount
0x18000b782  lea     rdx, String2; "\\\\?\\"
0x18000b789  lea     rcx, [rbp+57h+String1]; String1
0x18000b78d  call    wcsncmp_0
0x18000b792  test    eax, eax
0x18000b794  lea     r14, [rbp+57h+var_B8]
0x18000b798  lea     rcx, [rbp+57h+String1]
0x18000b79c  cmovnz  r14, rcx
0x18000b7a0  lea     rcx, [r15+18h]; this
0x18000b7a4  lea     r8, [rsp+110h+var_E0]; unsigned int *
0x18000b7a9  lea     rdx, aNumvolumes; "NumVolumes"
0x18000b7b0  call    ?QueryDWORDValue@CUwfRegKey@@QEAAJPEBGPEAK@Z; CUwfRegKey::QueryDWORDValue(ushort const *,ulong *)
0x18000b7b5  mov     ebx, eax
0x18000b7b7  test    eax, eax
0x18000b7b9  js      loc_18000B8D0
0x18000b7bf  mov     r13, r12
0x18000b7c2  cmp     [rsp+110h+var_E0], r12d
0x18000b7c7  jbe     loc_18000B8BE
0x18000b7cd  mov     rcx, r15; this
0x18000b7d0  call    ?ReleaseStaticVolumeConfiguration@CUwfStaticConfiguration@@QEAAXXZ; CUwfStaticConfiguration::ReleaseStaticVolumeConfiguration(void)
0x18000b7d5  mov     rdi, [r15+28h]
0x18000b7d9  xor     ebx, ebx
0x18000b7db  test    rdi, rdi
0x18000b7de  jnz     short loc_18000B84B
0x18000b7e0  lea     ecx, [rdi+28h]; Size
0x18000b7e3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000b7e8  mov     rdi, rax
0x18000b7eb  test    rax, rax
0x18000b7ee  jz      loc_18000B907
0x18000b7f4  mov     word ptr [rdi+9], 1
0x18000b7fa  lea     rax, ??_7CUwfStaticVolumeConfiguration@@6B@; const CUwfStaticVolumeConfiguration::`vftable'
0x18000b801  mov     [rdi], rax
0x18000b804  mov     r8d, r12d; unsigned int
0x18000b807  mov     dword ptr [rdi+0Ch], 0FFFFFFFFh
0x18000b80e  mov     [rdi+10h], rbx
0x18000b812  mov     [rdi+18h], rbx
0x18000b816  mov     [rdi+20h], rbx
0x18000b81a  mov     rcx, [r15+20h]
0x18000b81e  mov     r9b, [r15+8]; bool
0x18000b822  mov     rdx, [r15+18h]; HKEY
0x18000b826  mov     [rsp+110h+var_E8], r15; struct CUwfStaticConfiguration *
0x18000b82b  mov     [rsp+110h+var_F0], rcx; struct CUwfConfiguration *
0x18000b830  mov     rcx, rdi; this
0x18000b833  call    ?Initialize@CUwfStaticVolumeConfiguration@@QEAAJPEAUHKEY__@@K_NPEAVCUwfConfiguration@@PEAVCUwfStaticConfiguration@@@Z; CUwfStaticVolumeConfiguration::Initialize(HKEY__ *,ulong,bool,CUwfConfiguration *,CUwfStaticConfiguration *)
0x18000b838  mov     ebx, eax
0x18000b83a  mov     rcx, rdi
0x18000b83d  test    eax, eax
0x18000b83f  js      loc_18000B917
0x18000b845  mov     [r15+28h], rdi
0x18000b849  jmp     short loc_18000B84E
0x18000b84b  mov     rcx, rbx
0x18000b84e  cmp     [rdi+0Ch], r12d
0x18000b852  jnz     short loc_18000B859
0x18000b854  mov     r13, rdi
0x18000b857  jmp     short loc_18000B867
0x18000b859  mov     ebx, 80070005h
0x18000b85e  test    rcx, rcx
0x18000b861  jnz     loc_18000B917
0x18000b867  test    ebx, ebx
0x18000b869  js      short loc_18000B8D0
0x18000b86b  lea     rcx, [r13+10h]; this
0x18000b86f  lea     r8, [rsp+110h+var_D8]; unsigned __int16 **
0x18000b874  lea     rdx, aVolumename; "VolumeName"
0x18000b87b  call    ?QuerySzValue@CUwfRegKey@@QEAAJPEBGPEAPEAG@Z; CUwfRegKey::QuerySzValue(ushort const *,ushort * *)
0x18000b880  mov     ebx, eax
0x18000b882  mov     rsi, [rsp+110h+var_D8]
0x18000b887  test    eax, eax
0x18000b889  js      short loc_18000B8D0
0x18000b88b  test    rsi, rsi
0x18000b88e  jz      short loc_18000B8A0
0x18000b890  mov     rdx, r14; String2
0x18000b893  mov     rcx, rsi; String1
0x18000b896  call    cs:__imp__wcsicmp
0x18000b89c  test    eax, eax
0x18000b89e  jz      short loc_18000B90E
0x18000b8a0  mov     rcx, rsi
0x18000b8a3  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18000b8a9  xor     esi, esi
0x18000b8ab  inc     r12d
0x18000b8ae  mov     [rsp+110h+var_D8], rsi
0x18000b8b3  cmp     r12d, [rsp+110h+var_E0]
0x18000b8b8  jb      loc_18000B7CD
0x18000b8be  mov     rax, [rbp+57h+var_D0]
0x18000b8c2  xor     r12d, r12d
0x18000b8c5  mov     ecx, 80070002h
0x18000b8ca  cmp     [rax], r12
0x18000b8cd  cmovz   ebx, ecx
0x18000b8d0  mov     rcx, rsi
0x18000b8d3  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18000b8d9  test    ebx, ebx
0x18000b8db  jns     short loc_18000B8E5
0x18000b8dd  mov     rcx, r15; this
0x18000b8e0  call    ?ReleaseStaticVolumeConfiguration@CUwfStaticConfiguration@@QEAAXXZ; CUwfStaticConfiguration::ReleaseStaticVolumeConfiguration(void)
0x18000b8e5  mov     eax, ebx
0x18000b8e7  mov     rcx, [rbp+57h+var_50]
0x18000b8eb  xor     rcx, rsp; StackCookie
0x18000b8ee  call    __security_check_cookie
0x18000b8f3  add     rsp, 0D8h
0x18000b8fa  pop     r15
0x18000b8fc  pop     r14
0x18000b8fe  pop     r13
0x18000b900  pop     r12
0x18000b902  pop     rdi
0x18000b903  pop     rsi
0x18000b904  pop     rbx
0x18000b905  pop     rbp
0x18000b906  retn
0x18000b907  mov     ebx, 8007000Eh
0x18000b90c  jmp     short loc_18000B8D0
0x18000b90e  mov     rax, [rbp+57h+var_D0]
0x18000b912  mov     [rax], r13
0x18000b915  jmp     short loc_18000B8C2
0x18000b917  mov     rax, [rcx]
0x18000b91a  mov     edx, 1
0x18000b91f  mov     rax, [rax]
0x18000b922  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b927  jmp     short loc_18000B8D0
0x18000b929  call    __report_rangecheckfailure
```
