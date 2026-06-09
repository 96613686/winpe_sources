# CUwfStaticConfiguration::get_StaticVolumeConfiguration(ushort const *,CUwfStaticVolumeConfiguration * *)

- ea: `0x18000b940`
- end: `0x18000bb2f`
- name: `?get_StaticVolumeConfiguration@CUwfStaticConfiguration@@QEAAJPEBGPEAPEAVCUwfStaticVolumeConfiguration@@@Z`
- size: `495`
- prototype: `__int64 __fastcall(CUwfStaticConfiguration *__hidden this, const unsigned __int16 *, struct CUwfStaticVolumeConfiguration **)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config`

## callers

- `0x180014d80`

## callees

- `0x180001390`
- `0x180008300`
- `0x180008cf0`
- `0x18000b940`
- `0x18000e0f0`
- `0x18000e320`
- `0x18001c010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000bab3`
- `msvcrt!_wcsicmp` at `0x18000bab3`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000bac0`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000bb06`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000bac0`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000bb06`

## pseudocode

```c
__int64 __fastcall CUwfStaticConfiguration::get_StaticVolumeConfiguration(
        CUwfStaticConfiguration *this,
        const unsigned __int16 *a2,
        struct CUwfStaticVolumeConfiguration **a3)
{
  wchar_t *v3; // rsi
  int v6; // ebx
  struct CUwfStaticVolumeConfiguration *v7; // r12
  unsigned int i; // r15d
  char *v9; // rdi
  char *v10; // rax
  void (__fastcall ***v11)(_QWORD, __int64); // rcx
  int v12; // eax
  unsigned int v15; // [rsp+80h] [rbp+18h] BYREF
  wchar_t *String1; // [rsp+88h] [rbp+20h] BYREF

  v3 = 0;
  v15 = 0;
  String1 = 0;
  if ( !a3 )
  {
    v6 = -2147467261;
    goto LABEL_30;
  }
  *a3 = 0;
  if ( *((_QWORD *)this + 5) )
  {
    v6 = -2147024891;
    goto LABEL_30;
  }
  v6 = CUwfRegKey::QueryDWORDValue((CUwfStaticConfiguration *)((char *)this + 24), L"NumVolumes", &v15);
  if ( v6 >= 0 )
  {
    v7 = 0;
    for ( i = 0; i < v15; ++i )
    {
      CUwfStaticConfiguration::ReleaseStaticVolumeConfiguration(this);
      v9 = (char *)*((_QWORD *)this + 5);
      v6 = 0;
      if ( v9 )
      {
        v11 = 0;
      }
      else
      {
        v10 = (char *)operator new(0x28u);
        v9 = v10;
        if ( !v10 )
        {
          v6 = -2147024882;
          goto LABEL_30;
        }
        *(_WORD *)(v10 + 9) = 1;
        *(_QWORD *)v10 = &CUwfStaticVolumeConfiguration::`vftable';
        *((_DWORD *)v10 + 3) = -1;
        *((_QWORD *)v10 + 2) = 0;
        *((_QWORD *)v10 + 3) = 0;
        *((_QWORD *)v10 + 4) = 0;
        v6 = CUwfStaticVolumeConfiguration::Initialize(
               (CUwfStaticVolumeConfiguration *)v10,
               *((HKEY *)this + 3),
               i,
               *((_BYTE *)this + 8),
               *((struct CUwfConfiguration **)this + 4),
               this);
        v11 = (void (__fastcall ***)(_QWORD, __int64))v9;
        if ( v6 < 0 )
          goto LABEL_15;
        *((_QWORD *)this + 5) = v9;
      }
      if ( *((_DWORD *)v9 + 3) == i )
      {
        v7 = (struct CUwfStaticVolumeConfiguration *)v9;
        goto LABEL_17;
      }
      v6 = -2147024891;
LABEL_15:
      if ( v11 )
        (**v11)(v11, 1);
LABEL_17:
      if ( v6 < 0 )
        goto LABEL_30;
      v12 = CUwfRegKey::QuerySzValue((CUwfRegKey *)(*((_QWORD *)this + 5) + 16LL), L"DriveLetter", &String1);
      v6 = v12;
      if ( v12 < 0 )
      {
        if ( v12 != -2147024894 )
        {
          v3 = String1;
          goto LABEL_30;
        }
        v6 = 0;
      }
      v3 = String1;
      if ( String1 && !_wcsicmp(String1, a2) )
      {
        *a3 = v7;
        break;
      }
      operator delete[](v3);
      v3 = 0;
      String1 = 0;
    }
    if ( !*a3 )
      v6 = -2147024894;
  }
LABEL_30:
  operator delete[](v3);
  if ( v6 < 0 )
    CUwfStaticConfiguration::ReleaseStaticVolumeConfiguration(this);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18000b940  mov     rax, rsp
0x18000b943  mov     [rax+8], rbx
0x18000b947  mov     [rax+10h], rdx
0x18000b94b  push    rbp
0x18000b94c  push    rsi
0x18000b94d  push    rdi
0x18000b94e  push    r12
0x18000b950  push    r13
0x18000b952  push    r14
0x18000b954  push    r15
0x18000b956  sub     rsp, 30h
0x18000b95a  xor     esi, esi
0x18000b95c  mov     dword ptr [rax+18h], 0
0x18000b963  mov     [rax+20h], rsi
0x18000b967  mov     r14, r8
0x18000b96a  mov     rbp, rcx
0x18000b96d  test    r8, r8
0x18000b970  jnz     short loc_18000B97C
0x18000b972  mov     ebx, 80004003h
0x18000b977  jmp     loc_18000BB03
0x18000b97c  mov     [r8], rsi
0x18000b97f  cmp     [rcx+28h], rsi
0x18000b983  jz      short loc_18000B98F
0x18000b985  mov     ebx, 80070005h
0x18000b98a  jmp     loc_18000BB03
0x18000b98f  lea     r8, [rsp+68h+arg_10]; unsigned int *
0x18000b997  add     rcx, 18h; this
0x18000b99b  lea     rdx, aNumvolumes; "NumVolumes"
0x18000b9a2  call    ?QueryDWORDValue@CUwfRegKey@@QEAAJPEBGPEAK@Z; CUwfRegKey::QueryDWORDValue(ushort const *,ulong *)
0x18000b9a7  mov     ebx, eax
0x18000b9a9  test    eax, eax
0x18000b9ab  js      loc_18000BB03
0x18000b9b1  xor     r12d, r12d
0x18000b9b4  xor     r15d, r15d
0x18000b9b7  mov     eax, 80070002h
0x18000b9bc  cmp     [rsp+68h+arg_10], esi
0x18000b9c3  jbe     loc_18000BAFC
0x18000b9c9  mov     rcx, rbp; this
0x18000b9cc  call    ?ReleaseStaticVolumeConfiguration@CUwfStaticConfiguration@@QEAAXXZ; CUwfStaticConfiguration::ReleaseStaticVolumeConfiguration(void)
0x18000b9d1  mov     rdi, [rbp+28h]
0x18000b9d5  xor     ebx, ebx
0x18000b9d7  test    rdi, rdi
0x18000b9da  jnz     short loc_18000BA43
0x18000b9dc  lea     ecx, [rdi+28h]; Size
0x18000b9df  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000b9e4  mov     rdi, rax
0x18000b9e7  test    rax, rax
0x18000b9ea  jz      loc_18000BAE3
0x18000b9f0  mov     word ptr [rdi+9], 1
0x18000b9f6  lea     rax, ??_7CUwfStaticVolumeConfiguration@@6B@; const CUwfStaticVolumeConfiguration::`vftable'
0x18000b9fd  mov     [rdi], rax
0x18000ba00  mov     r8d, r15d; unsigned int
0x18000ba03  mov     dword ptr [rdi+0Ch], 0FFFFFFFFh
0x18000ba0a  mov     rcx, rdi; this
0x18000ba0d  mov     [rdi+10h], rbx
0x18000ba11  mov     [rdi+18h], rbx
0x18000ba15  mov     [rdi+20h], rbx
0x18000ba19  mov     rax, [rbp+20h]
0x18000ba1d  mov     r9b, [rbp+8]; bool
0x18000ba21  mov     rdx, [rbp+18h]; HKEY
0x18000ba25  mov     [rsp+68h+var_40], rbp; struct CUwfStaticConfiguration *
0x18000ba2a  mov     [rsp+68h+var_48], rax; struct CUwfConfiguration *
0x18000ba2f  call    ?Initialize@CUwfStaticVolumeConfiguration@@QEAAJPEAUHKEY__@@K_NPEAVCUwfConfiguration@@PEAVCUwfStaticConfiguration@@@Z; CUwfStaticVolumeConfiguration::Initialize(HKEY__ *,ulong,bool,CUwfConfiguration *,CUwfStaticConfiguration *)
0x18000ba34  mov     ebx, eax
0x18000ba36  mov     rcx, rdi
0x18000ba39  test    eax, eax
0x18000ba3b  js      short loc_18000BA56
0x18000ba3d  mov     [rbp+28h], rdi
0x18000ba41  jmp     short loc_18000BA46
0x18000ba43  mov     rcx, rbx
0x18000ba46  cmp     [rdi+0Ch], r15d
0x18000ba4a  jnz     short loc_18000BA51
0x18000ba4c  mov     r12, rdi
0x18000ba4f  jmp     short loc_18000BA6B
0x18000ba51  mov     ebx, 80070005h
0x18000ba56  test    rcx, rcx
0x18000ba59  jz      short loc_18000BA6B
0x18000ba5b  mov     rax, [rcx]
0x18000ba5e  mov     edx, 1
0x18000ba63  mov     rax, [rax]
0x18000ba66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ba6b  test    ebx, ebx
0x18000ba6d  js      loc_18000BB03
0x18000ba73  mov     rcx, [rbp+28h]
0x18000ba77  lea     r8, [rsp+68h+String1]; unsigned __int16 **
0x18000ba7f  add     rcx, 10h; this
0x18000ba83  lea     rdx, aDriveletter; "DriveLetter"
0x18000ba8a  call    ?QuerySzValue@CUwfRegKey@@QEAAJPEBGPEAPEAG@Z; CUwfRegKey::QuerySzValue(ushort const *,ushort * *)
0x18000ba8f  mov     ebx, eax
0x18000ba91  test    eax, eax
0x18000ba93  jns     short loc_18000BA9E
0x18000ba95  cmp     eax, 80070002h
0x18000ba9a  jnz     short loc_18000BAEA
0x18000ba9c  xor     ebx, ebx
0x18000ba9e  mov     rsi, [rsp+68h+String1]
0x18000baa6  test    rsi, rsi
0x18000baa9  jz      short loc_18000BABD
0x18000baab  mov     rdx, [rsp+68h+String2]; String2
0x18000bab0  mov     rcx, rsi; String1
0x18000bab3  call    cs:__imp__wcsicmp
0x18000bab9  test    eax, eax
0x18000babb  jz      short loc_18000BAF4
0x18000babd  mov     rcx, rsi
0x18000bac0  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18000bac6  xor     esi, esi
0x18000bac8  inc     r15d
0x18000bacb  mov     [rsp+68h+String1], rsi
0x18000bad3  cmp     r15d, [rsp+68h+arg_10]
0x18000badb  jb      loc_18000B9C9
0x18000bae1  jmp     short loc_18000BAF7
0x18000bae3  mov     ebx, 8007000Eh
0x18000bae8  jmp     short loc_18000BB03
0x18000baea  mov     rsi, [rsp+68h+String1]
0x18000baf2  jmp     short loc_18000BB03
0x18000baf4  mov     [r14], r12
0x18000baf7  mov     eax, 80070002h
0x18000bafc  cmp     qword ptr [r14], 0
0x18000bb00  cmovz   ebx, eax
0x18000bb03  mov     rcx, rsi
0x18000bb06  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18000bb0c  test    ebx, ebx
0x18000bb0e  jns     short loc_18000BB18
0x18000bb10  mov     rcx, rbp; this
0x18000bb13  call    ?ReleaseStaticVolumeConfiguration@CUwfStaticConfiguration@@QEAAXXZ; CUwfStaticConfiguration::ReleaseStaticVolumeConfiguration(void)
0x18000bb18  mov     eax, ebx
0x18000bb1a  mov     rbx, [rsp+68h+arg_0]
0x18000bb1f  add     rsp, 30h
0x18000bb23  pop     r15
0x18000bb25  pop     r14
0x18000bb27  pop     r13
0x18000bb29  pop     r12
0x18000bb2b  pop     rdi
0x18000bb2c  pop     rsi
0x18000bb2d  pop     rbp
0x18000bb2e  retn
```
