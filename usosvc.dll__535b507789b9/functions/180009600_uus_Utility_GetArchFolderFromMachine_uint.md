# uus::Utility::GetArchFolderFromMachine(uint)

- ea: `0x180009600`
- end: `0x1800096c6`
- name: `?GetArchFolderFromMachine@Utility@uus@@SA?AVpath@filesystem@std@@I@Z`
- size: `198`
- prototype: `_QWORD *__fastcall(_QWORD *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180009890`

## callees

- `0x1800031b0`
- `0x1800074ac`
- `0x180008900`
- `0x180009600`

## pseudocode

```c
_QWORD *__fastcall uus::Utility::GetArchFolderFromMachine(_QWORD *a1, int a2)
{
  int v3; // edx
  int v4; // edx
  const char *v5; // rdx
  const unsigned __int16 *v6; // rcx
  __int64 v7; // rax
  _QWORD pExceptionObject[4]; // [rsp+30h] [rbp-20h] BYREF

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
  pExceptionObject[0] = v6;
  pExceptionObject[1] = v7;
  std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(a1, (__int64)pExceptionObject);
  return a1;
}

```

## disassembly

```asm
0x180009600  mov     [rsp-8+arg_0], rbx
0x180009605  push    rbp
0x180009606  mov     rbp, rsp
0x180009609  sub     rsp, 50h
0x18000960d  xor     r8d, r8d
0x180009610  mov     rbx, rcx
0x180009613  sub     edx, 14Ch
0x180009619  jz      short loc_180009675
0x18000961b  sub     edx, 74h ; 't'
0x18000961e  jz      short loc_18000965E
0x180009620  sub     edx, 84A4h; char *
0x180009626  jz      short loc_180009647
0x180009628  cmp     edx, 2400h
0x18000962e  jnz     short loc_1800096AC
0x180009630  mov     rcx, cs:?archArm64@Const@uus@@2PEBGEB; ushort const * const uus::Const::archArm64
0x180009637  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000963b  inc     rax
0x18000963e  cmp     [rcx+rax*2], r8w
0x180009643  jnz     short loc_18000963B
0x180009645  jmp     short loc_18000968A
0x180009647  mov     rcx, cs:?archX64@Const@uus@@2PEBGEB; ushort const * const uus::Const::archX64
0x18000964e  or      rax, 0FFFFFFFFFFFFFFFFh
0x180009652  inc     rax
0x180009655  cmp     [rcx+rax*2], r8w
0x18000965a  jnz     short loc_180009652
0x18000965c  jmp     short loc_18000968A
0x18000965e  mov     rcx, cs:?archArm@Const@uus@@2PEBGEB; ushort const * const uus::Const::archArm
0x180009665  or      rax, 0FFFFFFFFFFFFFFFFh
0x180009669  inc     rax
0x18000966c  cmp     [rcx+rax*2], r8w
0x180009671  jnz     short loc_180009669
0x180009673  jmp     short loc_18000968A
0x180009675  mov     rcx, cs:?archX86@Const@uus@@2PEBGEB; ushort const * const uus::Const::archX86
0x18000967c  or      rax, 0FFFFFFFFFFFFFFFFh
0x180009680  inc     rax
0x180009683  cmp     [rcx+rax*2], r8w
0x180009688  jnz     short loc_180009680
0x18000968a  mov     [rbp+pExceptionObject], rcx
0x18000968e  lea     rdx, [rbp+pExceptionObject]
0x180009692  mov     rcx, rbx; void *
0x180009695  mov     [rbp+var_18], rax
0x180009699  call    ??$_Convert_stringoid_to_wide@U_Normal_conversion@filesystem@std@@@filesystem@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@V?$basic_string_view@GU?$char_traits@G@std@@@1@U_Normal_conversion@01@@Z; std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(std::basic_string_view<ushort>,std::filesystem::_Normal_conversion)
0x18000969e  mov     rax, rbx
0x1800096a1  mov     rbx, [rsp+50h+arg_0]
0x1800096a6  add     rsp, 50h
0x1800096aa  pop     rbp
0x1800096ab  retn
0x1800096ac  lea     rcx, [rbp+pExceptionObject]; this
0x1800096b0  call    ??0runtime_error@std@@QEAA@PEBD@Z; std::runtime_error::runtime_error(char const *)
0x1800096b5  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x1800096bc  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800096c0  call    _CxxThrowException_0
```
