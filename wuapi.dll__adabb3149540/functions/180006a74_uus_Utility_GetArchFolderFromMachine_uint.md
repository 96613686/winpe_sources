# uus::Utility::GetArchFolderFromMachine(uint)

- ea: `0x180006a74`
- end: `0x180006b33`
- name: `?GetArchFolderFromMachine@Utility@uus@@SA?AVpath@filesystem@std@@I@Z`
- size: `191`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180006bd4`

## callees

- `0x1800055e4`
- `0x180006a74`
- `0x180008868`
- `0x180011eb8`

## pseudocode

```c
__int64 __fastcall uus::Utility::GetArchFolderFromMachine(__int64 a1, int a2)
{
  int v3; // edx
  int v4; // edx
  const char *v5; // rdx
  const wchar_t *v6; // rdx
  __int64 v7; // r8
  _BYTE pExceptionObject[40]; // [rsp+30h] [rbp-28h] BYREF

  v3 = a2 - 332;
  if ( v3 )
  {
    v4 = v3 - 116;
    if ( v4 )
    {
      v5 = (const char *)(unsigned int)(v4 - 33956);
      if ( (_DWORD)v5 )
      {
        if ( (_DWORD)v5 != 9216 )
        {
          std::runtime_error::runtime_error((std::runtime_error *)pExceptionObject, v5);
          throw (std::runtime_error *)pExceptionObject;
        }
        v6 = uus::Const::archArm64;
        v7 = -1;
        do
          ++v7;
        while ( uus::Const::archArm64[v7] );
      }
      else
      {
        v6 = uus::Const::archX64;
        v7 = -1;
        do
          ++v7;
        while ( uus::Const::archX64[v7] );
      }
    }
    else
    {
      v6 = uus::Const::archArm;
      v7 = -1;
      do
        ++v7;
      while ( uus::Const::archArm[v7] );
    }
  }
  else
  {
    v6 = uus::Const::archX86;
    v7 = -1;
    do
      ++v7;
    while ( uus::Const::archX86[v7] );
  }
  *(_OWORD *)a1 = 0;
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 24) = 0;
  std::wstring::_Construct<1,wchar_t const *>(a1, v6, v7);
  return a1;
}

```

## disassembly

```asm
0x180006a74  push    rbx
0x180006a76  sub     rsp, 50h
0x180006a7a  xor     eax, eax
0x180006a7c  mov     [rsp+58h+var_38], rcx
0x180006a81  mov     rbx, rcx
0x180006a84  sub     edx, 14Ch
0x180006a8a  jz      short loc_180006AE6
0x180006a8c  sub     edx, 74h ; 't'
0x180006a8f  jz      short loc_180006ACF
0x180006a91  sub     edx, 84A4h; char *
0x180006a97  jz      short loc_180006AB8
0x180006a99  cmp     edx, 2400h
0x180006a9f  jnz     short loc_180006B17
0x180006aa1  mov     rdx, cs:?archArm64@Const@uus@@2PEB_WEB; wchar_t const * const uus::Const::archArm64
0x180006aa8  or      r8, 0FFFFFFFFFFFFFFFFh
0x180006aac  inc     r8
0x180006aaf  cmp     [rdx+r8*2], ax
0x180006ab4  jnz     short loc_180006AAC
0x180006ab6  jmp     short loc_180006AFB
0x180006ab8  mov     rdx, cs:?archX64@Const@uus@@2PEB_WEB; wchar_t const * const uus::Const::archX64
0x180006abf  or      r8, 0FFFFFFFFFFFFFFFFh
0x180006ac3  inc     r8
0x180006ac6  cmp     [rdx+r8*2], ax
0x180006acb  jnz     short loc_180006AC3
0x180006acd  jmp     short loc_180006AFB
0x180006acf  mov     rdx, cs:?archArm@Const@uus@@2PEB_WEB; wchar_t const * const uus::Const::archArm
0x180006ad6  or      r8, 0FFFFFFFFFFFFFFFFh
0x180006ada  inc     r8
0x180006add  cmp     [rdx+r8*2], ax
0x180006ae2  jnz     short loc_180006ADA
0x180006ae4  jmp     short loc_180006AFB
0x180006ae6  mov     rdx, cs:?archX86@Const@uus@@2PEB_WEB; wchar_t const * const uus::Const::archX86
0x180006aed  or      r8, 0FFFFFFFFFFFFFFFFh
0x180006af1  inc     r8
0x180006af4  cmp     [rdx+r8*2], ax
0x180006af9  jnz     short loc_180006AF1
0x180006afb  xorps   xmm0, xmm0
0x180006afe  movups  xmmword ptr [rcx], xmm0
0x180006b01  mov     [rcx+10h], rax
0x180006b05  mov     [rcx+18h], rax
0x180006b09  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180006b0e  mov     rax, rbx
0x180006b11  add     rsp, 50h
0x180006b15  pop     rbx
0x180006b16  retn
0x180006b17  lea     rcx, [rsp+58h+pExceptionObject]; this
0x180006b1c  call    ??0runtime_error@std@@QEAA@PEBD@Z; std::runtime_error::runtime_error(char const *)
0x180006b21  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x180006b28  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x180006b2d  call    _CxxThrowException
```
