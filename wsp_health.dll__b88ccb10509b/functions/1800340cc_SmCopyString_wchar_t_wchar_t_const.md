# SmCopyString(wchar_t * *,wchar_t const *)

- ea: `0x1800340cc`
- end: `0x1800341c5`
- name: `?SmCopyString@@YAJPEAPEA_WPEB_W@Z`
- size: `249`
- prototype: `int(wchar_t **, const wchar_t *)`
- caller_count: `3`
- callee_count: `11`
- tags: ``

## callers

- `0x180034224`
- `0x180079730`
- `0x1800797f0`

## callees

- `0x18000509c`
- `0x180009b10`
- `0x180033c20`
- `0x180033c6c`
- `0x180033cb0`
- `0x180033d0c`
- `0x180033dcc`
- `0x180033e24`
- `0x1800340cc`
- `0x1800344dc`
- `0x180034504`

## string_xrefs

- `0x1800340f5`: `SmCopyString`
- `0x18003416a`: `SmCopyString`
- `0x1800341a3`: `SmCopyString`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SmCopyString(wchar_t **a1, const wchar_t *a2)
{
  __int64 v4; // rcx
  int v5; // r8d
  int v6; // r9d
  int v7; // edx
  unsigned int v8; // ebx
  __int64 v9; // rbx
  unsigned __int64 v10; // rbx
  wchar_t *v11; // rax
  int v12; // eax
  LARGE_INTEGER v14[9]; // [rsp+20h] [rbp-48h] BYREF

  CSmTimer::CSmTimer((CSmTimer *)v14);
  CSmTimer::Start((CSmTimer *)v14);
  TraceEnterFunction<5,0,0>(L"SmCopyString", 75);
  if ( !a1 )
  {
    v7 = 77;
LABEL_3:
    v8 = -2147024809;
    TraceBadArgumentError<2,0,0>(v4, v7, v5, v6);
    goto LABEL_10;
  }
  if ( !a2 )
  {
    v7 = 78;
    goto LABEL_3;
  }
  v9 = -1;
  do
    ++v9;
  while ( a2[v9] );
  v10 = v9 + 1;
  v11 = (wchar_t *)operator new[](saturated_mul(v10, 2u));
  *a1 = v11;
  *v11 = 0;
  v12 = StringCchCopyW(*a1, v10, a2);
  v8 = v12;
  if ( v12 < 0 )
    TraceHRError<2,0,0>(L"SmCopyString", 83, (unsigned int)v12);
LABEL_10:
  CSmTimer::Stop(v14);
  TraceExitFunction<5,0,0>(
    L"SmCopyString",
    86,
    (unsigned __int64)(1000 * (v14[1].QuadPart - v14[0].QuadPart)) / v14[2].QuadPart,
    v8);
  CSmTimer::~CSmTimer((CSmTimer *)v14);
  return v8;
}

```

## disassembly

```asm
0x1800340cc  push    rbx
0x1800340ce  push    rbp
0x1800340cf  push    rsi
0x1800340d0  push    rdi
0x1800340d1  sub     rsp, 48h
0x1800340d5  mov     rdi, rdx
0x1800340d8  mov     rsi, rcx
0x1800340db  lea     rcx, [rsp+68h+var_48]; this
0x1800340e0  call    ??0CSmTimer@@QEAA@XZ; CSmTimer::CSmTimer(void)
0x1800340e5  nop
0x1800340e6  lea     rcx, [rsp+68h+var_48]; this
0x1800340eb  call    ?Start@CSmTimer@@QEAAXXZ; CSmTimer::Start(void)
0x1800340f0  mov     edx, 4Bh ; 'K'
0x1800340f5  lea     rcx, aSmcopystring; "SmCopyString"
0x1800340fc  call    ??$TraceEnterFunction@$04$0A@$0A@@@YAXPEB_WI@Z; TraceEnterFunction<5,0,0>(wchar_t const *,uint)
0x180034101  xor     ebp, ebp
0x180034103  test    rsi, rsi
0x180034106  jnz     short loc_180034117
0x180034108  lea     edx, [rbp+4Dh]
0x18003410b  mov     ebx, 80070057h
0x180034110  call    ??$TraceBadArgumentError@$01$0A@$0A@@@YAXPEB_WI@Z; TraceBadArgumentError<2,0,0>(wchar_t const *,uint)
0x180034115  jmp     short loc_180034176
0x180034117  test    rdi, rdi
0x18003411a  jnz     short loc_180034121
0x18003411c  lea     edx, [rdi+4Eh]
0x18003411f  jmp     short loc_18003410B
0x180034121  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180034125  mov     rbx, rcx
0x180034128  inc     rbx
0x18003412b  cmp     [rdi+rbx*2], bp
0x18003412f  jnz     short loc_180034128
0x180034131  inc     rbx
0x180034134  mov     eax, 2
0x180034139  mul     rbx
0x18003413c  cmovb   rax, rcx
0x180034140  mov     rcx, rax; unsigned __int64
0x180034143  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180034148  mov     [rsi], rax
0x18003414b  mov     [rax], bp
0x18003414e  mov     r8, rdi; wchar_t *
0x180034151  mov     rdx, rbx; unsigned __int64
0x180034154  mov     rcx, [rsi]; wchar_t *
0x180034157  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x18003415c  mov     ebx, eax
0x18003415e  test    eax, eax
0x180034160  jns     short loc_180034176
0x180034162  mov     r8d, eax
0x180034165  mov     edx, 53h ; 'S'
0x18003416a  lea     rcx, aSmcopystring; "SmCopyString"
0x180034171  call    ??$TraceHRError@$01$0A@$0A@@@YAXPEB_WII@Z; TraceHRError<2,0,0>(wchar_t const *,uint,uint)
0x180034176  lea     rcx, [rsp+68h+var_48]; this
0x18003417b  call    ?Stop@CSmTimer@@QEAAXXZ; CSmTimer::Stop(void)
0x180034180  mov     rdx, [rsp+68h+var_40]
0x180034185  sub     rdx, [rsp+68h+var_48]
0x18003418a  imul    rax, rdx, 3E8h
0x180034191  xor     edx, edx
0x180034193  div     [rsp+68h+var_38]
0x180034198  mov     r8, rax
0x18003419b  mov     r9d, ebx
0x18003419e  mov     edx, 56h ; 'V'
0x1800341a3  lea     rcx, aSmcopystring; "SmCopyString"
0x1800341aa  call    ??$TraceExitFunction@$04$0A@$0A@@@YAXPEB_WI_KJ@Z; TraceExitFunction<5,0,0>(wchar_t const *,uint,unsigned __int64,long)
0x1800341af  nop
0x1800341b0  lea     rcx, [rsp+68h+var_48]; this
0x1800341b5  call    ??1CSmTimer@@QEAA@XZ; CSmTimer::~CSmTimer(void)
0x1800341ba  mov     eax, ebx
0x1800341bc  add     rsp, 48h
0x1800341c0  pop     rdi
0x1800341c1  pop     rsi
0x1800341c2  pop     rbp
0x1800341c3  pop     rbx
0x1800341c4  retn
```
