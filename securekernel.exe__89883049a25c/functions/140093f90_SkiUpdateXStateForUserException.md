# SkiUpdateXStateForUserException

- ea: `0x140093f90`
- end: `0x140094071`
- name: `SkiUpdateXStateForUserException`
- size: `225`
- prototype: `__int64 __fastcall(ULONG_PTR BugCheckParameter3)`
- caller_count: `4`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x140092f74`
- `0x140093844`
- `0x140095dcc`
- `0x140096770`

## callees

- `0x1400119c4`
- `0x140093f90`
- `0x14009419c`
- `0x1400d68a0`
- `0x1400d6d4c`
- `0x1400f2f80`

## pseudocode

```c
void __fastcall SkiUpdateXStateForUserException(ULONG_PTR BugCheckParameter3, __int64 a2, char a3, unsigned __int64 a4)
{
  unsigned __int64 v4; // rbx
  int v8; // ebp
  struct _EXCEPTION_REGISTRATION_RECORD *ExceptionList; // rax
  int Handler_high; // eax
  __int64 v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // r8

  v4 = a4;
  _RDI = a2;
  if ( !a4 )
    v4 = SkeEnabledXStateFeatures & 0xFFFFFFFFFFFFFFFCuLL;
  v8 = SkeDisableInterrupts();
  ExceptionList = KeGetPcr()->NtTib.ExceptionList;
  if ( (*(_DWORD *)(BugCheckParameter3 + 328) & 2) != 0 )
    SkeBugCheckEx(0x131u, 0xBu, (ULONG_PTR)ExceptionList, BugCheckParameter3, 0);
  Handler_high = HIDWORD(ExceptionList[12].Handler);
  if ( a3 )
  {
    if ( (Handler_high & 4) != 0 )
    {
      if ( (MEMORY[0xFFFFF780000003EC] & 2) != 0 )
        __asm { xrstors byte ptr [rdi] }
      else
        RtlXRestore(_RDI, v4);
      goto LABEL_15;
    }
    v11 = *(_QWORD *)(BugCheckParameter3 + 320);
    v13 = _RDI;
    v12 = v4;
  }
  else
  {
    v11 = _RDI;
    v12 = v4;
    if ( (Handler_high & 2) != 0 )
    {
      SkiXSaveS(_RDI, v4);
      goto LABEL_15;
    }
    v13 = *(_QWORD *)(BugCheckParameter3 + 320);
  }
  RtlCopyXStateArea(v11, v12, v13);
LABEL_15:
  if ( v8 )
    _enable();
}

```

## disassembly

```asm
0x140093f90  push    rbx
0x140093f92  push    rbp
0x140093f93  push    rsi
0x140093f94  push    rdi
0x140093f95  push    r14
0x140093f97  sub     rsp, 30h
0x140093f9b  mov     rbx, r9
0x140093f9e  mov     r14b, r8b
0x140093fa1  mov     rdi, rdx
0x140093fa4  mov     rsi, rcx
0x140093fa7  test    r9, r9
0x140093faa  jnz     short loc_140093FB7
0x140093fac  mov     rbx, cs:SkeEnabledXStateFeatures
0x140093fb3  and     rbx, 0FFFFFFFFFFFFFFFCh
0x140093fb7  call    SkeDisableInterrupts
0x140093fbc  mov     ebp, eax
0x140093fbe  mov     dl, 2
0x140093fc0  mov     rax, gs:0
0x140093fc9  mov     ecx, [rsi+148h]
0x140093fcf  test    dl, cl
0x140093fd1  jz      short loc_140093FF2
0x140093fd3  mov     r9, rsi; BugCheckParameter3
0x140093fd6  mov     [rsp+58h+BugCheckParameter4], 0; BugCheckParameter4
0x140093fdf  mov     r8, rax; BugCheckParameter2
0x140093fe2  mov     edx, 0Bh; BugCheckParameter1
0x140093fe7  mov     ecx, 131h; BugCheckCode
0x140093fec  call    SkeBugCheckEx
0x140093ff2  mov     eax, [rax+0CCh]
0x140093ff8  test    r14b, r14b
0x140093ffb  jnz     short loc_140094017
0x140093ffd  test    dl, al
0x140093fff  mov     rcx, rdi
0x140094002  mov     rdx, rbx
0x140094005  jnz     short loc_140094010
0x140094007  mov     r8, [rsi+140h]
0x14009400e  jmp     short loc_140094028
0x140094010  call    SkiXSaveS
0x140094015  jmp     short loc_140094060
0x140094017  test    al, 4
0x140094019  jnz     short loc_14009402F
0x14009401b  mov     rcx, [rsi+140h]
0x140094022  mov     r8, rdi
0x140094025  mov     rdx, rbx
0x140094028  call    RtlCopyXStateArea
0x14009402d  jmp     short loc_140094060
0x14009402f  mov     rax, 0FFFFF780000003ECh
0x140094039  mov     eax, [rax]
0x14009403b  test    dl, al
0x14009403d  jnz     short loc_14009404C
0x14009403f  mov     rdx, rbx
0x140094042  mov     rcx, rdi
0x140094045  call    RtlXRestore
0x14009404a  jmp     short loc_140094060
0x14009404c  mov     rdx, [rdi+208h]
0x140094053  and     rdx, rbx
0x140094056  mov     rax, rdx
0x140094059  shr     rdx, 20h
0x14009405d  xrstors byte ptr [rdi]
0x140094060  test    ebp, ebp
0x140094062  jz      short loc_140094065
0x140094064  sti
0x140094065  add     rsp, 30h
0x140094069  pop     r14
0x14009406b  pop     rdi
0x14009406c  pop     rsi
0x14009406d  pop     rbp
0x14009406e  pop     rbx
0x14009406f  retn
```
