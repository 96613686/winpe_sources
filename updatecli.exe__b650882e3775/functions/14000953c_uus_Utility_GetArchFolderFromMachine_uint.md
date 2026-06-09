# uus::Utility::GetArchFolderFromMachine(uint)

- ea: `0x14000953c`
- end: `0x140009602`
- name: `?GetArchFolderFromMachine@Utility@uus@@SA?AVpath@filesystem@std@@I@Z`
- size: `198`
- prototype: `_QWORD *__fastcall(_QWORD *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x14000969c`

## callees

- `0x140002c68`
- `0x140007168`
- `0x1400085bc`
- `0x14000953c`

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
0x14000953c  mov     [rsp-8+arg_0], rbx
0x140009541  push    rbp
0x140009542  mov     rbp, rsp
0x140009545  sub     rsp, 50h
0x140009549  xor     r8d, r8d
0x14000954c  mov     rbx, rcx
0x14000954f  sub     edx, 14Ch
0x140009555  jz      short loc_1400095B1
0x140009557  sub     edx, 74h ; 't'
0x14000955a  jz      short loc_14000959A
0x14000955c  sub     edx, 84A4h; char *
0x140009562  jz      short loc_140009583
0x140009564  cmp     edx, 2400h
0x14000956a  jnz     short loc_1400095E8
0x14000956c  mov     rcx, cs:?archArm64@Const@uus@@2PEBGEB; ushort const * const uus::Const::archArm64
0x140009573  or      rax, 0FFFFFFFFFFFFFFFFh
0x140009577  inc     rax
0x14000957a  cmp     [rcx+rax*2], r8w
0x14000957f  jnz     short loc_140009577
0x140009581  jmp     short loc_1400095C6
0x140009583  mov     rcx, cs:?archX64@Const@uus@@2PEBGEB; ushort const * const uus::Const::archX64
0x14000958a  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000958e  inc     rax
0x140009591  cmp     [rcx+rax*2], r8w
0x140009596  jnz     short loc_14000958E
0x140009598  jmp     short loc_1400095C6
0x14000959a  mov     rcx, cs:?archArm@Const@uus@@2PEBGEB; ushort const * const uus::Const::archArm
0x1400095a1  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400095a5  inc     rax
0x1400095a8  cmp     [rcx+rax*2], r8w
0x1400095ad  jnz     short loc_1400095A5
0x1400095af  jmp     short loc_1400095C6
0x1400095b1  mov     rcx, cs:?archX86@Const@uus@@2PEBGEB; ushort const * const uus::Const::archX86
0x1400095b8  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400095bc  inc     rax
0x1400095bf  cmp     [rcx+rax*2], r8w
0x1400095c4  jnz     short loc_1400095BC
0x1400095c6  mov     [rbp+pExceptionObject], rcx
0x1400095ca  lea     rdx, [rbp+pExceptionObject]
0x1400095ce  mov     rcx, rbx; void *
0x1400095d1  mov     [rbp+var_18], rax
0x1400095d5  call    ??$_Convert_stringoid_to_wide@U_Normal_conversion@filesystem@std@@@filesystem@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@V?$basic_string_view@GU?$char_traits@G@std@@@1@U_Normal_conversion@01@@Z; std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(std::basic_string_view<ushort>,std::filesystem::_Normal_conversion)
0x1400095da  mov     rax, rbx
0x1400095dd  mov     rbx, [rsp+50h+arg_0]
0x1400095e2  add     rsp, 50h
0x1400095e6  pop     rbp
0x1400095e7  retn
0x1400095e8  lea     rcx, [rbp+pExceptionObject]; this
0x1400095ec  call    ??0runtime_error@std@@QEAA@PEBD@Z; std::runtime_error::runtime_error(char const *)
0x1400095f1  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x1400095f8  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1400095fc  call    _CxxThrowException_0
```
