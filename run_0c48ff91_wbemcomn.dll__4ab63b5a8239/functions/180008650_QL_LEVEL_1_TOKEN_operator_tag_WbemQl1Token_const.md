# QL_LEVEL_1_TOKEN::operator=(_tag_WbemQl1Token const &)

- ea: `0x180008650`
- end: `0x180008729`
- name: `??4QL_LEVEL_1_TOKEN@@QEAAAEAU0@AEBU_tag_WbemQl1Token@@@Z`
- size: `217`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800370b0`

## callees

- `0x180008650`
- `0x180009c40`
- `0x180014120`
- `0x18002ca74`
- `0x18002ee7c`

## import_xrefs

- `OLEAUT32!__imp_VariantCopy` at `0x180008668`
- `OLEAUT32!__imp_VariantCopy` at `0x180008668`

## pseudocode

```c
__int64 __fastcall QL_LEVEL_1_TOKEN::operator=(__int64 a1, __int64 a2)
{
  char pExceptionObject; // [rsp+30h] [rbp+8h] BYREF

  if ( VariantCopy((VARIANTARG *)(a1 + 48), (const VARIANTARG *)(a2 + 48)) < 0 )
  {
    CMemoryLog::Write((CMemoryLog *)&unk_18006A9C0, 0xFFFFFFFE);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        28,
        &WPP_2122daa7e8023666a1921e333e1159b1_Traceguids,
        "CX_MemoryException()");
    }
    throw (CX_MemoryException *)&pExceptionObject;
  }
  *(_DWORD *)a1 = *(_DWORD *)a2;
  CPropertyName::operator=(a1 + 8, a2 + 8);
  if ( *(_DWORD *)(a2 + 84) )
    CPropertyName::operator=(a1 + 80, a2 + 24);
  *(_DWORD *)(a1 + 40) = *(_DWORD *)(a2 + 40);
  *(_DWORD *)(a1 + 116) = *(_DWORD *)(a2 + 72);
  *(_DWORD *)(a1 + 120) = *(_DWORD *)(a2 + 76);
  *(_DWORD *)(a1 + 72) = *(_DWORD *)(a2 + 80);
  *(_DWORD *)(a1 + 112) = *(_DWORD *)(a2 + 84);
  return a1;
}

```

## disassembly

```asm
0x180008650  mov     [rsp+arg_8], rbx
0x180008655  push    rdi
0x180008656  sub     rsp, 20h
0x18000865a  mov     rbx, rdx
0x18000865d  mov     rdi, rcx
0x180008660  add     rdx, 30h ; '0'; pvargSrc
0x180008664  add     rcx, 30h ; '0'; pvargDest
0x180008668  call    cs:__imp_VariantCopy
0x18000866e  test    eax, eax
0x180008670  js      short loc_1800086B9
0x180008672  mov     eax, [rbx]
0x180008674  lea     rdx, [rbx+8]
0x180008678  lea     rcx, [rdi+8]
0x18000867c  mov     [rdi], eax
0x18000867e  call    ??4CPropertyName@@QEAAXAEBU_tag_WbemPropertyName@@@Z; CPropertyName::operator=(_tag_WbemPropertyName const &)
0x180008683  cmp     dword ptr [rbx+54h], 0
0x180008687  jnz     loc_180008717
0x18000868d  mov     eax, [rbx+28h]
0x180008690  mov     [rdi+28h], eax
0x180008693  mov     eax, [rbx+48h]
0x180008696  mov     [rdi+74h], eax
0x180008699  mov     eax, [rbx+4Ch]
0x18000869c  mov     [rdi+78h], eax
0x18000869f  mov     eax, [rbx+50h]
0x1800086a2  mov     [rdi+48h], eax
0x1800086a5  mov     eax, [rbx+54h]
0x1800086a8  mov     rbx, [rsp+28h+arg_8]
0x1800086ad  mov     [rdi+70h], eax
0x1800086b0  mov     rax, rdi
0x1800086b3  add     rsp, 20h
0x1800086b7  pop     rdi
0x1800086b8  retn
0x1800086b9  mov     edx, 0FFFFFFFEh; int
0x1800086be  lea     rcx, unk_18006A9C0; this
0x1800086c5  call    ?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800086ca  mov     rcx, cs:WPP_GLOBAL_Control
0x1800086d1  lea     rax, WPP_GLOBAL_Control
0x1800086d8  cmp     rcx, rax
0x1800086db  jz      short loc_180008705
0x1800086dd  test    byte ptr [rcx+1Ch], 1
0x1800086e1  jz      short loc_180008705
0x1800086e3  cmp     byte ptr [rcx+19h], 2
0x1800086e7  jb      short loc_180008705
0x1800086e9  mov     rcx, [rcx+10h]
0x1800086ed  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x1800086f4  mov     edx, 1Ch
0x1800086f9  lea     r8, WPP_2122daa7e8023666a1921e333e1159b1_Traceguids
0x180008700  call    WPP_SF_s
0x180008705  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x18000870c  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x180008711  call    _CxxThrowException_0
0x180008717  lea     rdx, [rbx+18h]
0x18000871b  lea     rcx, [rdi+50h]
0x18000871f  call    ??4CPropertyName@@QEAAXAEBU_tag_WbemPropertyName@@@Z; CPropertyName::operator=(_tag_WbemPropertyName const &)
0x180008724  jmp     loc_18000868D
```
