# WPP_RECORDER_SF_sDZ

- ea: `0x140002294`
- end: `0x1400024cd`
- name: `WPP_RECORDER_SF_sDZ`
- size: `569`
- prototype: ``
- caller_count: `8`
- callee_count: `2`
- tags: ``

## callers

- `0x140003930`
- `0x140017f64`
- `0x140024f60`
- `0x140025220`
- `0x140026210`
- `0x140026de0`
- `0x140029608`
- `0x140030d54`

## callees

- `0x140002294`
- `0x140007d40`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x1400024af`
- `WppRecorder!WppAutoLogTrace` at `0x1400024af`

## pseudocode

```c
__int64 __fastcall WPP_RECORDER_SF_sDZ(
        __int64 a1,
        unsigned __int8 a2,
        unsigned int a3,
        unsigned __int16 a4,
        __int64 a5,
        const char *a6,
        char a7,
        unsigned __int16 *a8)
{
  const wchar_t *v8; // r13
  const char *v9; // rdi
  __int64 v10; // r14
  __int16 v11; // ax
  __int64 v12; // rbp
  unsigned __int64 v13; // rsi
  unsigned __int64 v15; // rsi
  __int64 v16; // r15
  unsigned int v17; // edx
  const wchar_t *v18; // rbx
  int v19; // eax
  __int64 v20; // rdx
  const wchar_t *v21; // r11
  const wchar_t *v22; // r9
  __int64 v23; // rax
  __int64 v24; // r8
  const char *v25; // rcx
  bool v26; // zf
  bool v27; // zf
  int v29; // [rsp+20h] [rbp-98h]
  __int64 v30; // [rsp+70h] [rbp-48h]
  __int64 v31; // [rsp+78h] [rbp-40h]
  __int64 v32; // [rsp+80h] [rbp-38h]
  __int64 v33; // [rsp+88h] [rbp-30h]
  __int64 v34; // [rsp+90h] [rbp-28h]
  __int64 v35; // [rsp+98h] [rbp-20h]
  __int64 v36; // [rsp+A0h] [rbp-18h]
  __int64 v37; // [rsp+C0h] [rbp+8h]
  unsigned __int16 v40; // [rsp+D8h] [rbp+20h]

  v40 = a4;
  v37 = a1;
  v8 = L"NULL";
  v9 = a6;
  v10 = 8;
  v11 = a3;
  v12 = -1;
  v13 = a3;
  v15 = v13 >> 16;
  v16 = 5;
  v17 = ((_BYTE)v11 - 1) & 0x1F;
  v18 = a8;
  v19 = *((_DWORD *)&WPP_GLOBAL_Control->Timer + 20 * v15 + ((unsigned __int16)(v11 - 1) >> 5) + 1);
  if ( !_bittest(&v19, v17) || *((_BYTE *)&WPP_GLOBAL_Control->Timer + 80 * v15 + 1) < a2 )
    goto LABEL_18;
  if ( !a8 )
  {
    v20 = 8;
    goto LABEL_7;
  }
  v20 = *a8;
  if ( !*a8 )
  {
LABEL_7:
    v21 = L"NULL";
    goto LABEL_8;
  }
  v21 = (const wchar_t *)*((_QWORD *)a8 + 1);
LABEL_8:
  v22 = a8;
  if ( !a8 )
    v22 = L"\b";
  if ( a6 )
  {
    v23 = -1;
    do
      ++v23;
    while ( a6[v23] );
    v24 = v23 + 1;
  }
  else
  {
    v24 = 5;
  }
  v25 = a6;
  if ( !a6 )
    v25 = "NULL";
  ((void (__fastcall *)(_QWORD, __int64, __int64, _QWORD, const char *, __int64, char *, __int64, const wchar_t *, __int64, const wchar_t *, __int64, _QWORD))pfnWppTraceMessage)(
    *((_QWORD *)&WPP_GLOBAL_Control->AttachedDevice + 10 * v15),
    43,
    a5,
    v40,
    v25,
    v24,
    &a7,
    4,
    v22,
    2,
    v21,
    v20,
    0);
  a4 = v40;
  a1 = v37;
LABEL_18:
  v26 = v18 == 0;
  if ( v18 )
  {
    v10 = *v18;
    if ( *v18 )
      v8 = (const wchar_t *)*((_QWORD *)v18 + 1);
    v26 = v18 == 0;
  }
  if ( v26 )
    v18 = L"\b";
  v27 = a6 == 0;
  if ( a6 )
  {
    do
      ++v12;
    while ( a6[v12] );
    v16 = v12 + 1;
    v27 = a6 == 0;
  }
  if ( v27 )
    v9 = "NULL";
  LOWORD(v29) = a4;
  return WppAutoLogTrace(a1, a2, a3, a5, v29, v9, v16, &a7, 4, v18, 2, v8, v10, 0, v30, v31, v32, v33, v34, v35, v36);
}

```

## disassembly

```asm
0x140002294  mov     rax, rsp
0x140002297  mov     [rax+20h], r9w
0x14000229c  mov     [rax+18h], r8d
0x1400022a0  mov     [rax+10h], dl
0x1400022a3  mov     [rax+8], rcx
0x1400022a7  push    rbx
0x1400022a8  push    rbp
0x1400022a9  push    rsi
0x1400022aa  push    rdi
0x1400022ab  push    r12
0x1400022ad  push    r13
0x1400022af  push    r14
0x1400022b1  push    r15
0x1400022b3  sub     rsp, 78h
0x1400022b7  mov     r12, cs:WPP_GLOBAL_Control
0x1400022be  lea     r13, aNull_0; "NULL"
0x1400022c5  mov     rdi, [rsp+0B8h+arg_28]
0x1400022cd  mov     r14d, 8
0x1400022d3  mov     eax, r8d
0x1400022d6  or      rbp, 0FFFFFFFFFFFFFFFFh
0x1400022da  mov     esi, eax
0x1400022dc  mov     r8b, dl
0x1400022df  shr     rsi, 10h
0x1400022e3  lea     r15d, [r14-3]
0x1400022e7  lea     ebx, [rax-1]
0x1400022ea  mov     r10d, ebx
0x1400022ed  and     ebx, 1Fh
0x1400022f0  shr     r10, 5
0x1400022f4  lea     rax, [rsi+rsi*4]
0x1400022f8  and     r10d, 7FFh
0x1400022ff  mov     edx, ebx
0x140002301  mov     rbx, [rsp+0B8h+arg_38]
0x140002309  lea     r11, [r10+rax*4]
0x14000230d  mov     eax, [r12+r11*4+2Ch]
0x140002312  lea     r10, asc_14000A7D0; "\b"
0x140002319  bt      eax, edx
0x14000231c  lea     r11, aNull; "NULL"
0x140002323  jnb     loc_140002420
0x140002329  lea     r10, [rsi+rsi*4]
0x14000232d  xor     esi, esi
0x14000232f  add     r10, r10
0x140002332  cmp     [r12+r10*8+29h], r8b
0x140002337  jb      loc_140002417
0x14000233d  test    rbx, rbx
0x140002340  jz      short loc_140002350
0x140002342  movzx   edx, word ptr [rbx]
0x140002345  cmp     [rbx], si
0x140002348  jz      short loc_140002353
0x14000234a  mov     r11, [rbx+8]
0x14000234e  jmp     short loc_140002356
0x140002350  mov     rdx, r14
0x140002353  mov     r11, r13
0x140002356  test    rbx, rbx
0x140002359  lea     rax, asc_14000A7D0; "\b"
0x140002360  mov     r9, rbx
0x140002363  cmovz   r9, rax
0x140002367  test    rdi, rdi
0x14000236a  jz      short loc_14000237E
0x14000236c  mov     rax, rbp
0x14000236f  inc     rax
0x140002372  cmp     [rdi+rax], sil
0x140002376  jnz     short loc_14000236F
0x140002378  lea     r8, [rax+1]
0x14000237c  jmp     short loc_140002381
0x14000237e  mov     r8, r15
0x140002381  mov     [rsp+0B8h+var_58], rsi
0x140002386  lea     rax, aNull; "NULL"
0x14000238d  mov     [rsp+0B8h+var_60], rdx
0x140002392  test    rdi, rdi
0x140002395  mov     [rsp+0B8h+var_68], r11
0x14000239a  lea     rdx, [rsp+0B8h+arg_30]
0x1400023a2  mov     [rsp+0B8h+var_70], 2
0x1400023ab  mov     rcx, rdi
0x1400023ae  mov     [rsp+0B8h+var_78], r9
0x1400023b3  cmovz   rcx, rax
0x1400023b7  mov     rax, cs:pfnWppTraceMessage
0x1400023be  movzx   r9d, [rsp+0B8h+arg_18]
0x1400023c7  mov     [rsp+0B8h+var_80], 4
0x1400023d0  mov     [rsp+0B8h+var_88], rdx
0x1400023d5  mov     edx, 2Bh ; '+'
0x1400023da  mov     [rsp+0B8h+var_90], r8
0x1400023df  mov     r8, [rsp+0B8h+arg_20]
0x1400023e7  mov     [rsp+0B8h+var_98], rcx
0x1400023ec  mov     rcx, [r12+r10*8+18h]
0x1400023f1  call    _guard_dispatch_icall
0x1400023f6  movzx   r9d, [rsp+0B8h+arg_18]
0x1400023ff  lea     r10, asc_14000A7D0; "\b"
0x140002406  mov     rcx, [rsp+0B8h+arg_0]
0x14000240e  lea     r11, aNull; "NULL"
0x140002415  jmp     short loc_140002422
0x140002417  lea     r10, asc_14000A7D0; "\b"
0x14000241e  jmp     short loc_140002422
0x140002420  xor     esi, esi
0x140002422  test    rbx, rbx
0x140002425  jz      short loc_140002437
0x140002427  movzx   r14d, word ptr [rbx]
0x14000242b  cmp     [rbx], si
0x14000242e  jz      short loc_140002434
0x140002430  mov     r13, [rbx+8]
0x140002434  test    rbx, rbx
0x140002437  cmovz   rbx, r10
0x14000243b  test    rdi, rdi
0x14000243e  jz      short loc_140002450
0x140002440  inc     rbp
0x140002443  cmp     [rdi+rbp], sil
0x140002447  jnz     short loc_140002440
0x140002449  lea     r15, [rbp+1]
0x14000244d  test    rdi, rdi
0x140002450  mov     r8d, [rsp+0B8h+arg_10]
0x140002458  lea     rax, [rsp+0B8h+arg_30]
0x140002460  movzx   edx, [rsp+0B8h+arg_8]
0x140002468  cmovz   rdi, r11
0x14000246c  mov     [rsp+0B8h+var_50], rsi
0x140002471  mov     [rsp+0B8h+var_58], r14
0x140002476  mov     [rsp+0B8h+var_60], r13
0x14000247b  mov     [rsp+0B8h+var_68], 2
0x140002484  mov     [rsp+0B8h+var_70], rbx
0x140002489  mov     [rsp+0B8h+var_78], 4
0x140002492  mov     [rsp+0B8h+var_80], rax
0x140002497  mov     [rsp+0B8h+var_88], r15
0x14000249c  mov     [rsp+0B8h+var_90], rdi
0x1400024a1  mov     word ptr [rsp+0B8h+var_98], r9w
0x1400024a7  mov     r9, [rsp+0B8h+arg_20]
0x1400024af  call    cs:__imp_WppAutoLogTrace
0x1400024b6  nop     dword ptr [rax+rax+00h]
0x1400024bb  add     rsp, 78h
0x1400024bf  pop     r15
0x1400024c1  pop     r14
0x1400024c3  pop     r13
0x1400024c5  pop     r12
0x1400024c7  pop     rdi
0x1400024c8  pop     rsi
0x1400024c9  pop     rbp
0x1400024ca  pop     rbx
0x1400024cb  retn
```
