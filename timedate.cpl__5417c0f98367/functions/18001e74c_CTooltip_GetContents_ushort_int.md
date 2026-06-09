# CTooltip::GetContents(ushort *,int)

- ea: `0x18001e74c`
- end: `0x18001e8f3`
- name: `?GetContents@CTooltip@@QEAAHPEAGH@Z`
- size: `423`
- prototype: `__int64 __fastcall(CTooltip *__hidden this, unsigned __int16 *, int)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x18001f48c`
- `0x180020410`

## callees

- `0x18001e74c`
- `0x18001ec9c`

## string_xrefs

- `0x18001e823`: `ExtraClockName1`
- `0x18001e88e`: `ExtraClockName2`
- `0x18001e83d`: `ExtraClockDay1`
- `0x18001e8a8`: `ExtraClockDay2`

## pseudocode

```c
__int64 __fastcall CTooltip::GetContents(CTooltip *this, unsigned __int16 *a2, int a3)
{
  int v6; // r15d
  unsigned int v7; // r15d
  unsigned int v8; // r15d
  unsigned int v9; // r15d
  unsigned int v10; // r15d
  unsigned int v11; // r15d
  unsigned int v12; // r15d

  if ( a2 && a3 > 0 )
    *a2 = 0;
  v6 = CTooltip::_CheckAndGetContent(this, L"TodayStr", a2, a3, L" ");
  v7 = CTooltip::_CheckAndGetContent(this, L"TodaysDayName", a2, a3, L" ") + v6;
  if ( *((_QWORD *)this + 32) )
  {
    v8 = CTooltip::_CheckAndGetContent(this, L"MainClockName", a2, a3, L" ") + v7;
    v7 = CTooltip::_CheckAndGetContent(this, L"MainDigitalClock", a2, a3, L"\n") + v8;
  }
  if ( *((_DWORD *)this + 64) )
  {
    v9 = CTooltip::_CheckAndGetContent(this, L"ExtraClockName1", a2, a3, L"-") + v7;
    v10 = CTooltip::_CheckAndGetContent(this, L"ExtraClockDay1", a2, a3, L" ") + v9;
    v7 = CTooltip::_CheckAndGetContent(this, L"FirstClock", a2, a3, L"\n") + v10;
  }
  if ( *((_DWORD *)this + 65) )
  {
    v11 = CTooltip::_CheckAndGetContent(this, L"ExtraClockName2", a2, a3, L"-") + v7;
    v12 = CTooltip::_CheckAndGetContent(this, L"ExtraClockDay2", a2, a3, L" ") + v11;
    return CTooltip::_CheckAndGetContent(this, L"SecondClock", a2, a3, L"\n") + v12;
  }
  return v7;
}

```

## disassembly

```asm
0x18001e74c  push    rbx
0x18001e74e  push    rbp
0x18001e74f  push    rsi
0x18001e750  push    rdi
0x18001e751  push    r13
0x18001e753  push    r14
0x18001e755  push    r15
0x18001e757  sub     rsp, 30h
0x18001e75b  mov     ebp, r8d
0x18001e75e  mov     rsi, rdx
0x18001e761  mov     rdi, rcx
0x18001e764  test    rdx, rdx
0x18001e767  jz      short loc_18001E773
0x18001e769  test    r8d, r8d
0x18001e76c  jle     short loc_18001E773
0x18001e76e  xor     eax, eax
0x18001e770  mov     [rdx], ax
0x18001e773  lea     r13, asc_18002F1D4; " "
0x18001e77a  mov     r9d, ebp; int
0x18001e77d  mov     r8, rsi; unsigned __int16 *
0x18001e780  mov     [rsp+68h+var_48], r13; unsigned __int16 *
0x18001e785  lea     rdx, aTodaystr; "TodayStr"
0x18001e78c  call    ?_CheckAndGetContent@CTooltip@@AEAAHPEBGPEAGH0@Z; CTooltip::_CheckAndGetContent(ushort const *,ushort *,int,ushort const *)
0x18001e791  mov     r9d, ebp; int
0x18001e794  mov     [rsp+68h+var_48], r13; unsigned __int16 *
0x18001e799  mov     r8, rsi; unsigned __int16 *
0x18001e79c  lea     rdx, aTodaysdayname; "TodaysDayName"
0x18001e7a3  mov     rcx, rdi; this
0x18001e7a6  mov     r15d, eax
0x18001e7a9  call    ?_CheckAndGetContent@CTooltip@@AEAAHPEBGPEAGH0@Z; CTooltip::_CheckAndGetContent(ushort const *,ushort *,int,ushort const *)
0x18001e7ae  add     r15d, eax
0x18001e7b1  lea     r14, [rdi+104h]
0x18001e7b8  cmp     dword ptr [rdi+100h], 0
0x18001e7bf  jnz     short loc_18001E7C7
0x18001e7c1  cmp     dword ptr [r14], 0
0x18001e7c5  jz      short loc_18001E808
0x18001e7c7  mov     r9d, ebp; int
0x18001e7ca  mov     [rsp+68h+var_48], r13; unsigned __int16 *
0x18001e7cf  mov     r8, rsi; unsigned __int16 *
0x18001e7d2  lea     rdx, aMainclockname; "MainClockName"
0x18001e7d9  mov     rcx, rdi; this
0x18001e7dc  call    ?_CheckAndGetContent@CTooltip@@AEAAHPEBGPEAGH0@Z; CTooltip::_CheckAndGetContent(ushort const *,ushort *,int,ushort const *)
0x18001e7e1  add     r15d, eax
0x18001e7e4  lea     rdx, aMaindigitalclo; "MainDigitalClock"
0x18001e7eb  lea     rax, asc_18002E648; "\n"
0x18001e7f2  mov     r9d, ebp; int
0x18001e7f5  mov     r8, rsi; unsigned __int16 *
0x18001e7f8  mov     [rsp+68h+var_48], rax; unsigned __int16 *
0x18001e7fd  mov     rcx, rdi; this
0x18001e800  call    ?_CheckAndGetContent@CTooltip@@AEAAHPEBGPEAGH0@Z; CTooltip::_CheckAndGetContent(ushort const *,ushort *,int,ushort const *)
0x18001e805  add     r15d, eax
0x18001e808  cmp     dword ptr [rdi+100h], 0
0x18001e80f  lea     rax, asc_18002FE4C; "-"
0x18001e816  jz      short loc_18001E87D
0x18001e818  mov     r9d, ebp; int
0x18001e81b  mov     [rsp+68h+var_48], rax; unsigned __int16 *
0x18001e820  mov     r8, rsi; unsigned __int16 *
0x18001e823  lea     rdx, aExtraclockname; "ExtraClockName1"
0x18001e82a  mov     rcx, rdi; this
0x18001e82d  call    ?_CheckAndGetContent@CTooltip@@AEAAHPEBGPEAGH0@Z; CTooltip::_CheckAndGetContent(ushort const *,ushort *,int,ushort const *)
0x18001e832  mov     r9d, ebp; int
0x18001e835  mov     [rsp+68h+var_48], r13; unsigned __int16 *
0x18001e83a  mov     r8, rsi; unsigned __int16 *
0x18001e83d  lea     rdx, aExtraclockday1; "ExtraClockDay1"
0x18001e844  mov     rcx, rdi; this
0x18001e847  add     r15d, eax
0x18001e84a  call    ?_CheckAndGetContent@CTooltip@@AEAAHPEBGPEAGH0@Z; CTooltip::_CheckAndGetContent(ushort const *,ushort *,int,ushort const *)
0x18001e84f  add     r15d, eax
0x18001e852  lea     rdx, aFirstclock; "FirstClock"
0x18001e859  lea     rax, asc_18002E648; "\n"
0x18001e860  mov     r9d, ebp; int
0x18001e863  mov     r8, rsi; unsigned __int16 *
0x18001e866  mov     [rsp+68h+var_48], rax; unsigned __int16 *
0x18001e86b  mov     rcx, rdi; this
0x18001e86e  call    ?_CheckAndGetContent@CTooltip@@AEAAHPEBGPEAGH0@Z; CTooltip::_CheckAndGetContent(ushort const *,ushort *,int,ushort const *)
0x18001e873  add     r15d, eax
0x18001e876  lea     rax, asc_18002FE4C; "-"
0x18001e87d  cmp     dword ptr [r14], 0
0x18001e881  jz      short loc_18001E8E1
0x18001e883  mov     r9d, ebp; int
0x18001e886  mov     [rsp+68h+var_48], rax; unsigned __int16 *
0x18001e88b  mov     r8, rsi; unsigned __int16 *
0x18001e88e  lea     rdx, aExtraclockname_0; "ExtraClockName2"
0x18001e895  mov     rcx, rdi; this
0x18001e898  call    ?_CheckAndGetContent@CTooltip@@AEAAHPEBGPEAGH0@Z; CTooltip::_CheckAndGetContent(ushort const *,ushort *,int,ushort const *)
0x18001e89d  mov     r9d, ebp; int
0x18001e8a0  mov     [rsp+68h+var_48], r13; unsigned __int16 *
0x18001e8a5  mov     r8, rsi; unsigned __int16 *
0x18001e8a8  lea     rdx, aExtraclockday2; "ExtraClockDay2"
0x18001e8af  mov     rcx, rdi; this
0x18001e8b2  add     r15d, eax
0x18001e8b5  call    ?_CheckAndGetContent@CTooltip@@AEAAHPEBGPEAGH0@Z; CTooltip::_CheckAndGetContent(ushort const *,ushort *,int,ushort const *)
0x18001e8ba  add     r15d, eax
0x18001e8bd  lea     rdx, aSecondclock; "SecondClock"
0x18001e8c4  lea     rax, asc_18002E648; "\n"
0x18001e8cb  mov     r9d, ebp; int
0x18001e8ce  mov     r8, rsi; unsigned __int16 *
0x18001e8d1  mov     [rsp+68h+var_48], rax; unsigned __int16 *
0x18001e8d6  mov     rcx, rdi; this
0x18001e8d9  call    ?_CheckAndGetContent@CTooltip@@AEAAHPEBGPEAGH0@Z; CTooltip::_CheckAndGetContent(ushort const *,ushort *,int,ushort const *)
0x18001e8de  add     r15d, eax
0x18001e8e1  mov     eax, r15d
0x18001e8e4  add     rsp, 30h
0x18001e8e8  pop     r15
0x18001e8ea  pop     r14
0x18001e8ec  pop     r13
0x18001e8ee  pop     rdi
0x18001e8ef  pop     rsi
0x18001e8f0  pop     rbp
0x18001e8f1  pop     rbx
0x18001e8f2  retn
```
