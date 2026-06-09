# SmCopyString(wchar_t * *,wchar_t const *)

- ea: `0x1800351fc`
- end: `0x1800352f6`
- name: `?SmCopyString@@YAJPEAPEA_WPEB_W@Z`
- size: `250`
- prototype: `int(wchar_t **, const wchar_t *)`
- caller_count: `3`
- callee_count: `11`
- tags: ``

## callers

- `0x180035354`
- `0x18007b7e0`
- `0x18007b8b0`

## callees

- `0x18000513c`
- `0x180009e80`
- `0x180034d3c`
- `0x180034d8c`
- `0x180034dd0`
- `0x180034e2c`
- `0x180034eec`
- `0x180034f4c`
- `0x1800351fc`
- `0x180035620`
- `0x180035650`

## string_xrefs

- `0x180035225`: `SmCopyString`
- `0x18003529a`: `SmCopyString`
- `0x1800352d3`: `SmCopyString`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SmCopyString(wchar_t **a1, const wchar_t *a2)
{
  __int64 v4; // rcx
  __int64 v5; // rdx
  unsigned int v6; // ebx
  __int64 v7; // rbx
  unsigned __int64 v8; // rbx
  wchar_t *v9; // rax
  int v10; // eax
  LARGE_INTEGER v12[9]; // [rsp+20h] [rbp-48h] BYREF

  CSmTimer::CSmTimer((CSmTimer *)v12);
  CSmTimer::Start((CSmTimer *)v12);
  TraceEnterFunction<5,0,0>(L"SmCopyString", 75);
  if ( !a1 )
  {
    v5 = 77;
LABEL_3:
    v6 = -2147024809;
    TraceBadArgumentError<2,0,0>(v4, v5);
    goto LABEL_10;
  }
  if ( !a2 )
  {
    v5 = 78;
    goto LABEL_3;
  }
  v7 = -1;
  do
    ++v7;
  while ( a2[v7] );
  v8 = v7 + 1;
  v9 = (wchar_t *)operator new[](saturated_mul(v8, 2u));
  *a1 = v9;
  *v9 = 0;
  v10 = StringCchCopyW(*a1, v8, a2);
  v6 = v10;
  if ( v10 < 0 )
    TraceHRError<2,0,0>(L"SmCopyString", 83, (unsigned int)v10);
LABEL_10:
  CSmTimer::Stop(v12);
  TraceExitFunction<5,0,0>(
    L"SmCopyString",
    86,
    (unsigned __int64)(1000 * (v12[1].QuadPart - v12[0].QuadPart)) / v12[2].QuadPart,
    v6);
  CSmTimer::~CSmTimer((CSmTimer *)v12);
  return v6;
}

```

## disassembly

```asm
0x1800351fc  push    rbx
0x1800351fe  push    rbp
0x1800351ff  push    rsi
0x180035200  push    rdi
0x180035201  sub     rsp, 48h
0x180035205  mov     rdi, rdx
0x180035208  mov     rsi, rcx
0x18003520b  lea     rcx, [rsp+68h+var_48]; this
0x180035210  call    ??0CSmTimer@@QEAA@XZ; CSmTimer::CSmTimer(void)
0x180035215  nop
0x180035216  lea     rcx, [rsp+68h+var_48]; this
0x18003521b  call    ?Start@CSmTimer@@QEAAXXZ; CSmTimer::Start(void)
0x180035220  mov     edx, 4Bh ; 'K'
0x180035225  lea     rcx, aSmcopystring; "SmCopyString"
0x18003522c  call    ??$TraceEnterFunction@$04$0A@$0A@@@YAXPEB_WI@Z; TraceEnterFunction<5,0,0>(wchar_t const *,uint)
0x180035231  xor     ebp, ebp
0x180035233  test    rsi, rsi
0x180035236  jnz     short loc_180035247
0x180035238  lea     edx, [rbp+4Dh]
0x18003523b  mov     ebx, 80070057h
0x180035240  call    ??$TraceBadArgumentError@$01$0A@$0A@@@YAXPEB_WI@Z; TraceBadArgumentError<2,0,0>(wchar_t const *,uint)
0x180035245  jmp     short loc_1800352A6
0x180035247  test    rdi, rdi
0x18003524a  jnz     short loc_180035251
0x18003524c  lea     edx, [rdi+4Eh]
0x18003524f  jmp     short loc_18003523B
0x180035251  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180035255  mov     rbx, rcx
0x180035258  inc     rbx
0x18003525b  cmp     [rdi+rbx*2], bp
0x18003525f  jnz     short loc_180035258
0x180035261  inc     rbx
0x180035264  mov     eax, 2
0x180035269  mul     rbx
0x18003526c  cmovb   rax, rcx
0x180035270  mov     rcx, rax; unsigned __int64
0x180035273  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180035278  mov     [rsi], rax
0x18003527b  mov     [rax], bp
0x18003527e  mov     r8, rdi; wchar_t *
0x180035281  mov     rdx, rbx; unsigned __int64
0x180035284  mov     rcx, [rsi]; wchar_t *
0x180035287  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x18003528c  mov     ebx, eax
0x18003528e  test    eax, eax
0x180035290  jns     short loc_1800352A6
0x180035292  mov     r8d, eax
0x180035295  mov     edx, 53h ; 'S'
0x18003529a  lea     rcx, aSmcopystring; "SmCopyString"
0x1800352a1  call    ??$TraceHRError@$01$0A@$0A@@@YAXPEB_WII@Z; TraceHRError<2,0,0>(wchar_t const *,uint,uint)
0x1800352a6  lea     rcx, [rsp+68h+var_48]; this
0x1800352ab  call    ?Stop@CSmTimer@@QEAAXXZ; CSmTimer::Stop(void)
0x1800352b0  mov     rdx, [rsp+68h+var_40]
0x1800352b5  sub     rdx, [rsp+68h+var_48]
0x1800352ba  imul    rax, rdx, 3E8h
0x1800352c1  xor     edx, edx
0x1800352c3  div     [rsp+68h+var_38]
0x1800352c8  mov     r8, rax
0x1800352cb  mov     r9d, ebx
0x1800352ce  mov     edx, 56h ; 'V'
0x1800352d3  lea     rcx, aSmcopystring; "SmCopyString"
0x1800352da  call    ??$TraceExitFunction@$04$0A@$0A@@@YAXPEB_WI_KJ@Z; TraceExitFunction<5,0,0>(wchar_t const *,uint,unsigned __int64,long)
0x1800352df  nop
0x1800352e0  lea     rcx, [rsp+68h+var_48]; this
0x1800352e5  call    ??1CSmTimer@@QEAA@XZ; CSmTimer::~CSmTimer(void)
0x1800352ea  mov     eax, ebx
0x1800352ec  add     rsp, 48h
0x1800352f0  pop     rdi
0x1800352f1  pop     rsi
0x1800352f2  pop     rbp
0x1800352f3  pop     rbx
0x1800352f4  retn
```
