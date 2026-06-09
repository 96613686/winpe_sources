# SclFindAndReplaceChars

- ea: `0x1800126d8`
- end: `0x18001298f`
- name: `SclFindAndReplaceChars`
- size: `695`
- prototype: `__int64 __fastcall(char *Src, unsigned __int64, unsigned __int64 *, unsigned __int64 *, __int64, __int64, const void *, unsigned __int64, bool *)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18000d220`
- `0x180012434`

## callees

- `0x1800126d8`
- `0x1800155c4`
- `0x1800179ad`
- `0x1800179e0`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x180012842`
- `ntdll!RtlAllocateHeap` at `0x180012842`
- `ntdll!RtlFreeHeap` at `0x18001295b`
- `ntdll!RtlFreeHeap` at `0x18001295b`

## pseudocode

```c
__int64 __fastcall SclFindAndReplaceChars(
        char *Src,
        unsigned __int64 a2,
        unsigned __int64 *a3,
        unsigned __int64 *a4,
        __int64 a5,
        __int64 a6,
        const void *a7,
        unsigned __int64 a8,
        bool *a9)
{
  char *v9; // r13
  unsigned __int64 *v11; // rbx
  unsigned __int64 v13; // r12
  __int64 v14; // rdi
  __int64 v15; // rax
  unsigned __int64 v17; // rdi
  unsigned __int64 v18; // rsi
  char *Heap; // rbp
  char *v20; // r12
  char *v21; // r14
  __int64 v22; // rax
  char *v23; // r13
  unsigned __int64 v24; // r14
  char *v26; // [rsp+20h] [rbp-4A8h]
  __int64 v29; // [rsp+50h] [rbp-478h]
  _BYTE P[1040]; // [rsp+60h] [rbp-468h] BYREF

  v9 = Src;
  v11 = a3;
  if ( !Src || !a4 || !a5 || !a6 || !a7 || !a9 )
    return 3221225485LL;
  v13 = *a4;
  v14 = 0;
  v15 = StrStrNIC(Src, a2, a5, a6);
  if ( v15 )
  {
    do
    {
      v14 = (unsigned int)(v14 + 1);
      v15 = StrStrNIC(v15 + 2 * a6, a2 - (unsigned int)((v15 + 2 * a6 - (__int64)v9) >> 1), a5, a6);
    }
    while ( v15 );
    v11 = a3;
  }
  *a9 = (_DWORD)v14 != 0;
  if ( !(_DWORD)v14 )
  {
    if ( v11 )
      *v11 = a2;
    return 0;
  }
  v17 = a2 + (a8 - a6) * v14;
  if ( v11 )
    *v11 = v17;
  if ( v13 < v17 )
  {
LABEL_17:
    *a4 = v17;
    return 3221225507LL;
  }
  v18 = 520;
  if ( v17 <= 0x208 )
  {
    Heap = P;
    goto LABEL_23;
  }
  Heap = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 2 * v17);
  if ( Heap )
  {
    v18 = v17;
LABEL_23:
    v20 = v9;
    v21 = Heap;
    while ( 1 )
    {
      v26 = v21;
      v22 = StrStrNIC(v20, a2 - (unsigned int)((v20 - v9) >> 1), a5, a6);
      v29 = v22;
      v23 = &v9[2 * a2];
      if ( v22 )
        v23 = (char *)v22;
      if ( v23 != v20 )
      {
        v24 = (v23 - v20) >> 1;
        if ( v18 < v24 )
          goto LABEL_17;
        memcpy_0(v26, v20, 2 * v24);
        v22 = v29;
        v18 -= v24;
        v21 = &v26[2 * v24];
      }
      if ( !v22 )
        break;
      if ( v18 < a8 )
        goto LABEL_17;
      memcpy_0(v21, a7, 2 * a8);
      v21 += 2 * a8;
      v20 = &v23[2 * a6];
      v9 = Src;
      v18 -= a8;
    }
    *a4 = v17;
    memcpy_0(Src, Heap, 2 * v17);
    if ( Heap != P )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
    return 0;
  }
  return 3221225495LL;
}

```

## disassembly

```asm
0x1800126d8  push    rbx
0x1800126da  push    rbp
0x1800126db  push    rsi
0x1800126dc  push    rdi
0x1800126dd  push    r12
0x1800126df  push    r13
0x1800126e1  push    r14
0x1800126e3  push    r15
0x1800126e5  sub     rsp, 488h
0x1800126ec  mov     rax, cs:__security_cookie
0x1800126f3  xor     rax, rsp
0x1800126f6  mov     [rsp+4C8h+var_58], rax
0x1800126fe  mov     rbp, [rsp+4C8h+arg_28]
0x180012706  mov     r13, rcx
0x180012709  mov     rax, [rsp+4C8h+arg_38]
0x180012711  mov     rsi, rdx
0x180012714  mov     r14, [rsp+4C8h+arg_40]
0x18001271c  mov     rbx, r8
0x18001271f  mov     [rsp+4C8h+var_480], rdx
0x180012724  mov     r15, r9
0x180012727  mov     rdx, [rsp+4C8h+arg_30]
0x18001272f  mov     [rsp+4C8h+var_488], rcx
0x180012734  mov     rcx, [rsp+4C8h+arg_20]
0x18001273c  mov     [rsp+4C8h+var_498], rcx
0x180012741  mov     [rsp+4C8h+Src], rdx
0x180012746  mov     [rsp+4C8h+var_4A8], rbx
0x18001274b  mov     [rsp+4C8h+var_490], rbp
0x180012750  mov     [rsp+4C8h+var_4A0], rax
0x180012755  test    r13, r13
0x180012758  jz      loc_180012966
0x18001275e  test    r9, r9
0x180012761  jz      loc_180012966
0x180012767  test    rcx, rcx
0x18001276a  jz      loc_180012966
0x180012770  test    rbp, rbp
0x180012773  jz      loc_180012966
0x180012779  test    rdx, rdx
0x18001277c  jz      loc_180012966
0x180012782  test    r14, r14
0x180012785  jz      loc_180012966
0x18001278b  mov     r12, [r9]
0x18001278e  mov     r8, rcx
0x180012791  mov     r9, rbp
0x180012794  mov     rcx, r13
0x180012797  mov     rdx, rsi
0x18001279a  xor     edi, edi
0x18001279c  call    StrStrNIC
0x1800127a1  test    rax, rax
0x1800127a4  jz      short loc_1800127D7
0x1800127a6  mov     rbx, [rsp+4C8h+var_498]
0x1800127ab  lea     rcx, [rax+rbp*2]
0x1800127af  mov     rdx, rsi
0x1800127b2  mov     rax, rcx
0x1800127b5  mov     r9, rbp
0x1800127b8  sub     rax, r13
0x1800127bb  mov     r8, rbx
0x1800127be  sar     rax, 1
0x1800127c1  inc     edi
0x1800127c3  mov     eax, eax
0x1800127c5  sub     rdx, rax
0x1800127c8  call    StrStrNIC
0x1800127cd  test    rax, rax
0x1800127d0  jnz     short loc_1800127AB
0x1800127d2  mov     rbx, [rsp+4C8h+var_4A8]
0x1800127d7  test    edi, edi
0x1800127d9  setnz   al
0x1800127dc  mov     [r14], al
0x1800127df  test    edi, edi
0x1800127e1  jnz     short loc_1800127F2
0x1800127e3  test    rbx, rbx
0x1800127e6  jz      short loc_1800127EB
0x1800127e8  mov     [rbx], rsi
0x1800127eb  xor     eax, eax
0x1800127ed  jmp     loc_18001296B
0x1800127f2  mov     rcx, [rsp+4C8h+var_4A0]
0x1800127f7  sub     rcx, rbp
0x1800127fa  imul    rdi, rcx
0x1800127fe  add     rdi, rsi
0x180012801  test    rbx, rbx
0x180012804  jz      short loc_180012809
0x180012806  mov     [rbx], rdi
0x180012809  cmp     r12, rdi
0x18001280c  jnb     short loc_18001281B
0x18001280e  mov     [r15], rdi
0x180012811  mov     eax, 0C0000023h
0x180012816  jmp     loc_18001296B
0x18001281b  mov     esi, 208h
0x180012820  cmp     rdi, rsi
0x180012823  ja      short loc_18001282C
0x180012825  lea     rbp, [rsp+4C8h+P]
0x18001282a  jmp     short loc_18001285D
0x18001282c  mov     rcx, gs:60h
0x180012835  lea     r8, [rdi+rdi]; Size
0x180012839  mov     edx, 8; Flags
0x18001283e  mov     rcx, [rcx+30h]; HeapHandle
0x180012842  call    cs:__imp_RtlAllocateHeap
0x180012848  mov     rbp, rax
0x18001284b  test    rax, rax
0x18001284e  jnz     short loc_18001285A
0x180012850  mov     eax, 0C0000017h
0x180012855  jmp     loc_18001296B
0x18001285a  mov     rsi, rdi
0x18001285d  mov     r12, r13
0x180012860  mov     r14, rbp
0x180012863  mov     rbx, [rsp+4C8h+var_480]
0x180012868  mov     rax, r12
0x18001286b  mov     r9, [rsp+4C8h+var_490]
0x180012870  sub     rax, r13
0x180012873  mov     r8, [rsp+4C8h+var_498]
0x180012878  mov     rdx, rbx
0x18001287b  sar     rax, 1
0x18001287e  mov     rcx, r12
0x180012881  mov     eax, eax
0x180012883  sub     rdx, rax
0x180012886  mov     [rsp+4C8h+var_4A8], r14
0x18001288b  call    StrStrNIC
0x180012890  mov     [rsp+4C8h+var_478], rax
0x180012895  lea     r13, [r13+rbx*2+0]
0x18001289a  test    rax, rax
0x18001289d  jz      short loc_1800128A2
0x18001289f  mov     r13, rax
0x1800128a2  cmp     r13, r12
0x1800128a5  jz      short loc_1800128DE
0x1800128a7  mov     r14, r13
0x1800128aa  sub     r14, r12
0x1800128ad  sar     r14, 1
0x1800128b0  cmp     rsi, r14
0x1800128b3  jb      loc_18001280E
0x1800128b9  mov     rdx, r12; Src
0x1800128bc  lea     rbx, [r14+r14]
0x1800128c0  mov     r12, [rsp+4C8h+var_4A8]
0x1800128c5  mov     r8, rbx; Size
0x1800128c8  mov     rcx, r12; void *
0x1800128cb  call    memcpy_0
0x1800128d0  mov     rax, [rsp+4C8h+var_478]
0x1800128d5  add     r12, rbx
0x1800128d8  sub     rsi, r14
0x1800128db  mov     r14, r12
0x1800128de  test    rax, rax
0x1800128e1  jz      short loc_180012927
0x1800128e3  mov     rax, [rsp+4C8h+var_4A0]
0x1800128e8  cmp     rsi, rax
0x1800128eb  jb      loc_18001280E
0x1800128f1  mov     rdx, [rsp+4C8h+Src]; Src
0x1800128f6  lea     rbx, [rax+rax]
0x1800128fa  mov     r8, rbx; Size
0x1800128fd  mov     rcx, r14; void *
0x180012900  call    memcpy_0
0x180012905  mov     rax, [rsp+4C8h+var_490]
0x18001290a  add     r14, rbx
0x18001290d  lea     r12, ds:0[rax*2]
0x180012915  add     r12, r13
0x180012918  mov     r13, [rsp+4C8h+var_488]
0x18001291d  sub     rsi, [rsp+4C8h+var_4A0]
0x180012922  jmp     loc_180012863
0x180012927  mov     rcx, [rsp+4C8h+var_488]; void *
0x18001292c  lea     r8, [rdi+rdi]; Size
0x180012930  mov     rdx, rbp; Src
0x180012933  mov     [r15], rdi
0x180012936  call    memcpy_0
0x18001293b  lea     rax, [rsp+4C8h+P]
0x180012940  cmp     rbp, rax
0x180012943  jz      loc_1800127EB
0x180012949  mov     rcx, gs:60h
0x180012952  mov     r8, rbp; P
0x180012955  xor     edx, edx; Flags
0x180012957  mov     rcx, [rcx+30h]; HeapHandle
0x18001295b  call    cs:__imp_RtlFreeHeap
0x180012961  jmp     loc_1800127EB
0x180012966  mov     eax, 0C000000Dh
0x18001296b  mov     rcx, [rsp+4C8h+var_58]
0x180012973  xor     rcx, rsp; StackCookie
0x180012976  call    __security_check_cookie
0x18001297b  add     rsp, 488h
0x180012982  pop     r15
0x180012984  pop     r14
0x180012986  pop     r13
0x180012988  pop     r12
0x18001298a  pop     rdi
0x18001298b  pop     rsi
0x18001298c  pop     rbp
0x18001298d  pop     rbx
0x18001298e  retn
```
