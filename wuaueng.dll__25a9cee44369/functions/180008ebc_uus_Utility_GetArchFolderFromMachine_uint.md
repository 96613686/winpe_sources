# uus::Utility::GetArchFolderFromMachine(uint)

- ea: `0x180008ebc`
- end: `0x180008f7b`
- name: `?GetArchFolderFromMachine@Utility@uus@@SA?AVpath@filesystem@std@@I@Z`
- size: `191`
- prototype: `__int64 __fastcall(__int64, int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180008388`

## callees

- `0x180008dfc`
- `0x180008ebc`
- `0x18000a620`
- `0x180011e68`

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
0x180008ebc  push    rbx
0x180008ebe  sub     rsp, 50h
0x180008ec2  xor     eax, eax
0x180008ec4  mov     [rsp+58h+var_38], rcx
0x180008ec9  mov     rbx, rcx
0x180008ecc  sub     edx, 14Ch
0x180008ed2  jz      short loc_180008F2E
0x180008ed4  sub     edx, 74h ; 't'
0x180008ed7  jz      short loc_180008F17
0x180008ed9  sub     edx, 84A4h; char *
0x180008edf  jz      short loc_180008F00
0x180008ee1  cmp     edx, 2400h
0x180008ee7  jnz     short loc_180008F5F
0x180008ee9  mov     rdx, cs:?archArm64@Const@uus@@2PEB_WEB; wchar_t const * const uus::Const::archArm64
0x180008ef0  or      r8, 0FFFFFFFFFFFFFFFFh
0x180008ef4  inc     r8
0x180008ef7  cmp     [rdx+r8*2], ax
0x180008efc  jnz     short loc_180008EF4
0x180008efe  jmp     short loc_180008F43
0x180008f00  mov     rdx, cs:?archX64@Const@uus@@2PEB_WEB; wchar_t const * const uus::Const::archX64
0x180008f07  or      r8, 0FFFFFFFFFFFFFFFFh
0x180008f0b  inc     r8
0x180008f0e  cmp     [rdx+r8*2], ax
0x180008f13  jnz     short loc_180008F0B
0x180008f15  jmp     short loc_180008F43
0x180008f17  mov     rdx, cs:?archArm@Const@uus@@2PEB_WEB; wchar_t const * const uus::Const::archArm
0x180008f1e  or      r8, 0FFFFFFFFFFFFFFFFh
0x180008f22  inc     r8
0x180008f25  cmp     [rdx+r8*2], ax
0x180008f2a  jnz     short loc_180008F22
0x180008f2c  jmp     short loc_180008F43
0x180008f2e  mov     rdx, cs:?archX86@Const@uus@@2PEB_WEB; wchar_t const * const uus::Const::archX86
0x180008f35  or      r8, 0FFFFFFFFFFFFFFFFh
0x180008f39  inc     r8
0x180008f3c  cmp     [rdx+r8*2], ax
0x180008f41  jnz     short loc_180008F39
0x180008f43  xorps   xmm0, xmm0
0x180008f46  movups  xmmword ptr [rcx], xmm0
0x180008f49  mov     [rcx+10h], rax
0x180008f4d  mov     [rcx+18h], rax
0x180008f51  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180008f56  mov     rax, rbx
0x180008f59  add     rsp, 50h
0x180008f5d  pop     rbx
0x180008f5e  retn
0x180008f5f  lea     rcx, [rsp+58h+pExceptionObject]; this
0x180008f64  call    ??0runtime_error@std@@QEAA@PEBD@Z; std::runtime_error::runtime_error(char const *)
0x180008f69  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x180008f70  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x180008f75  call    _CxxThrowException
```
