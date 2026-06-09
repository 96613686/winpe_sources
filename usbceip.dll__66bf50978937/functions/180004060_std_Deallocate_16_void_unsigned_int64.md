# std::_Deallocate<16>(void *,unsigned __int64)

- ea: `0x180004060`
- end: `0x18000408d`
- name: `??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z`
- size: `45`
- prototype: `void __fastcall(_QWORD *, unsigned __int64)`
- caller_count: `42`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180004124`
- `0x180004164`
- `0x1800041b4`
- `0x180004240`
- `0x180004388`
- `0x180004e88`
- `0x180005170`
- `0x180005194`
- `0x180005c5c`
- `0x180005ce4`
- `0x180006544`
- `0x1800065a0`
- `0x180006808`
- `0x180006bc8`
- `0x180006d2c`
- `0x1800072b4`
- `0x1800080c8`
- `0x180008218`
- `0x180008290`
- `0x180008730`
- `0x1800089bc`
- `0x180009260`
- `0x1800097ec`
- `0x180009b24`
- `0x180009fe0`
- `0x18000a130`
- `0x18000a294`
- `0x18000a40c`
- `0x18000a464`
- `0x18000a48c`
- `0x18000a698`
- `0x18000aacc`
- `0x18000ab28`
- `0x18000ad38`
- `0x18000ad94`
- `0x18000adec`
- `0x18000ae48`
- `0x18000af94`
- `0x18000b140`
- `0x18000b5c8`
- `0x18000bcd0`
- `0x18000bd24`

## callees

- `0x180002434`
- `0x180004060`

## pseudocode

```c
void __fastcall std::_Deallocate<16>(_QWORD *a1, unsigned __int64 a2)
{
  if ( a2 >= 0x1000 )
  {
    if ( (unsigned __int64)a1 - *(a1 - 1) - 8 > 0x1F )
      __fastfail(5u);
    a1 = (_QWORD *)*(a1 - 1);
  }
  operator delete(a1);
}

```

## disassembly

```asm
0x180004060  cmp     rdx, 1000h
0x180004067  jb      short loc_180004081
0x180004069  mov     rax, [rcx-8]
0x18000406d  sub     rcx, rax
0x180004070  sub     rcx, 8
0x180004074  cmp     rcx, 1Fh
0x180004078  ja      short loc_180004086
0x18000407a  add     rdx, 27h ; '''
0x18000407e  mov     rcx, rax; Block
0x180004081  jmp     ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180004086  mov     ecx, 5
0x18000408b  int     29h; Win8: RtlFailFast(ecx)
```
