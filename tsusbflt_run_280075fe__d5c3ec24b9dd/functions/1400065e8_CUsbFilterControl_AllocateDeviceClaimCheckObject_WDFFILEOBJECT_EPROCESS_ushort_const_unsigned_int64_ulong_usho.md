# CUsbFilterControl::AllocateDeviceClaimCheckObject(WDFFILEOBJECT__ *,_EPROCESS *,ushort const *,unsigned __int64,ulong,ushort const *,unsigned __int64,ulong,ushort const *,unsigned __int64,ulong,void * *)

- ea: `0x1400065e8`
- end: `0x1400068d4`
- name: `?AllocateDeviceClaimCheckObject@CUsbFilterControl@@AEAAJPEAUWDFFILEOBJECT__@@PEAU_EPROCESS@@PEBG_KK23K23KPEAPEAX@Z`
- size: `748`
- prototype: `int(CUsbFilterControl *__hidden this, struct WDFFILEOBJECT__ *, struct _EPROCESS *, const unsigned __int16 *, unsigned __int64, unsigned int, const unsigned __int16 *, unsigned __int64, unsigned int, const unsigned __int16 *, unsigned __int64, unsigned int, void **)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x140006278`
- `0x14000711c`

## callees

- `0x1400065e8`
- `0x14000a2e8`
- `0x14000aa30`
- `0x14000b140`

## import_xrefs

- `ntoskrnl!ObfReferenceObject` at `0x1400066b0`
- `ntoskrnl!ObfReferenceObject` at `0x1400066b0`

## pseudocode

```c
__int64 __fastcall CUsbFilterControl::AllocateDeviceClaimCheckObject(
        CUsbFilterControl *this,
        struct WDFFILEOBJECT__ *a2,
        struct _EPROCESS *a3,
        unsigned __int16 *a4,
        size_t Size,
        unsigned int a6,
        const unsigned __int16 *a7,
        size_t a8,
        unsigned int a9,
        const unsigned __int16 *a10,
        size_t pcchLength,
        unsigned int a12,
        void **a13)
{
  __int64 v13; // r15
  size_t v14; // r12
  size_t v16; // r14
  size_t v17; // r13
  NTSTATUS v19; // ebx
  __int64 v20; // rax
  void *v21; // rdx
  __int64 v22; // rsi
  size_t v23; // rbx
  size_t v24; // rdi
  void *v25; // rbx
  void *v26; // rdi
  int v27; // r14d
  __int64 v28; // r15
  const wchar_t *v29; // r11
  unsigned __int64 v30; // rdi
  unsigned int v31; // r12d
  __int64 v32; // r11
  unsigned __int64 v33; // rcx
  void *v34; // rcx
  void *v36; // [rsp+30h] [rbp-48h]
  _QWORD v37[3]; // [rsp+38h] [rbp-40h] BYREF
  int v38; // [rsp+50h] [rbp-28h]
  int v39; // [rsp+54h] [rbp-24h]
  struct WDFFILEOBJECT__ *v40; // [rsp+58h] [rbp-20h]
  size_t v41; // [rsp+60h] [rbp-18h]
  __int64 *v42; // [rsp+68h] [rbp-10h]
  void *v43; // [rsp+C0h] [rbp+48h] BYREF
  void *v44; // [rsp+C8h] [rbp+50h]
  struct _EPROCESS *v45; // [rsp+D0h] [rbp+58h]
  void *Src; // [rsp+D8h] [rbp+60h]

  Src = a4;
  v45 = a3;
  v13 = a6;
  v14 = Size;
  v16 = a8;
  v17 = pcchLength;
  v43 = 0;
  v37[2] = 0;
  v38 = 1;
  v39 = 1;
  v42 = off_14000F0B8;
  v40 = a2;
  v37[0] = 56;
  v37[1] = CcEvtObjectContextCleanup;
  v41 = pcchLength + a8 + Size + 8 * (a9 + 11LL + a6 + (unsigned __int64)a12);
  v19 = ((__int64 (__fastcall *)(struct _LIST_ENTRY *, _QWORD *, void **))WPP_MAIN_CB.Queue.ListEntry.Flink[103].Blink)(
          WPP_MAIN_CB.Queue.ListEntry.Blink,
          v37,
          &v43);
  if ( v19 >= 0 )
  {
    ObfReferenceObject(a3);
    ((void (__fastcall *)(struct _LIST_ENTRY *, struct WDFFILEOBJECT__ *, _QWORD, __int64, const char *))WPP_MAIN_CB.Queue.ListEntry.Flink[102].Blink)(
      WPP_MAIN_CB.Queue.ListEntry.Blink,
      a2,
      0,
      1977,
      "clientcore\\termsrv\\devices\\urbdr\\busfilter\\control.cpp");
    v20 = ((__int64 (__fastcall *)(struct _LIST_ENTRY *, void *, __int64 *))WPP_MAIN_CB.Queue.ListEntry.Flink[101].Flink)(
            WPP_MAIN_CB.Queue.ListEntry.Blink,
            v43,
            off_14000F0B8);
    v21 = Src;
    v22 = v20;
    *(_QWORD *)v20 = a2;
    v23 = v20 + v14;
    *(_QWORD *)(v20 + 8) = v45;
    v24 = v20 + v14 + v16;
    *(_DWORD *)(v20 + 16) = a6;
    *(_DWORD *)(v20 + 40) = a9;
    *(_DWORD *)(v20 + 64) = a12;
    *(_QWORD *)(v20 + 32) = v14;
    *(_QWORD *)(v20 + 24) = v24 + v17 + 88;
    *(_QWORD *)(v20 + 56) = v16;
    *(_QWORD *)(v20 + 80) = v17;
    *(_QWORD *)(v20 + 48) = v17 + v24 + 8 * (v13 + 11);
    *(_QWORD *)(v20 + 72) = v17 + v24 + 8 * (v13 + a9 + 11LL);
    memmove((void *)(v20 + 88), v21, v14);
    v25 = (void *)(v23 + 88);
    v36 = v25;
    memmove(v25, a7, v16);
    v26 = (void *)(v24 + 88);
    v44 = v26;
    memmove(v26, a10, v17);
    v27 = 0;
    while ( 1 )
    {
      if ( v27 )
      {
        if ( v27 == 1 )
        {
          if ( !*(_DWORD *)(v22 + 40) )
            goto LABEL_17;
          v28 = *(_QWORD *)(v22 + 48);
          v29 = (const wchar_t *)v25;
          v30 = a8;
        }
        else
        {
          if ( !*(_DWORD *)(v22 + 64) )
            goto LABEL_17;
          v28 = *(_QWORD *)(v22 + 72);
          v29 = (const wchar_t *)v26;
          v30 = v17;
        }
      }
      else
      {
        if ( !*(_DWORD *)(v22 + 16) )
          goto LABEL_17;
        v28 = *(_QWORD *)(v22 + 24);
        v29 = (const wchar_t *)(v22 + 88);
        v30 = v14;
      }
      v31 = 0;
      if ( *v29 )
      {
        while ( 1 )
        {
          pcchLength = 0;
          *(_QWORD *)(v28 + 8LL * v31) = v29;
          if ( v30 >> 1 > 0x7FFFFFFF )
            break;
          v19 = RtlStringLengthWorkerW(v29, v30 >> 1, &pcchLength);
          if ( v19 < 0 )
            goto LABEL_20;
          ++v31;
          v33 = 2 * pcchLength + 2;
          v30 -= v33;
          v29 = (const wchar_t *)(v32 + 2 * (v33 >> 1));
          if ( !*v29 )
          {
            v25 = v36;
            goto LABEL_16;
          }
        }
        v19 = -1073741811;
        break;
      }
LABEL_16:
      v26 = v44;
      v14 = Size;
LABEL_17:
      if ( (unsigned int)++v27 >= 3 )
      {
        v19 = 0;
        v34 = v43;
        goto LABEL_21;
      }
    }
  }
LABEL_20:
  ((void (__fastcall *)(struct _LIST_ENTRY *, void *))WPP_MAIN_CB.Queue.ListEntry.Flink[104].Flink)(
    WPP_MAIN_CB.Queue.ListEntry.Blink,
    v43);
  v34 = 0;
LABEL_21:
  *a13 = v34;
  return (unsigned int)v19;
}

```

## disassembly

```asm
0x1400065e8  mov     [rsp-40h+Src], r9
0x1400065ed  mov     [rsp-40h+arg_10], r8
0x1400065f2  mov     [rsp-40h+arg_0], rcx
0x1400065f7  push    rbp
0x1400065f8  push    rbx
0x1400065f9  push    rsi
0x1400065fa  push    rdi
0x1400065fb  push    r12
0x1400065fd  push    r13
0x1400065ff  push    r14
0x140006601  push    r15
0x140006603  mov     rbp, rsp
0x140006606  sub     rsp, 78h
0x14000660a  mov     ecx, [rbp+arg_40]
0x140006610  xor     eax, eax
0x140006612  mov     r15d, [rbp+arg_28]
0x140006616  add     rcx, 0Bh
0x14000661a  mov     r12, [rbp+Size]
0x14000661e  mov     rsi, r8
0x140006621  mov     r14, [rbp+arg_38]
0x140006628  lea     r8, [rbp+arg_0]
0x14000662c  mov     r13, [rbp+pcchLength]
0x140006633  mov     rdi, rdx
0x140006636  mov     [rbp+arg_0], rax
0x14000663a  mov     [rbp+var_30], rax
0x14000663e  mov     eax, 1
0x140006643  mov     [rbp+var_28], eax
0x140006646  mov     [rbp+var_24], eax
0x140006649  mov     rax, cs:off_14000F0B8
0x140006650  mov     [rbp+var_10], rax
0x140006654  mov     eax, [rbp+arg_58]
0x14000665a  add     rax, r15
0x14000665d  mov     [rbp+var_20], rdx
0x140006661  add     rax, rcx
0x140006664  mov     [rbp+var_40], 38h ; '8'
0x14000666c  lea     rdx, [rbp+var_40]
0x140006670  lea     rcx, [r12+rax*8]
0x140006674  add     rcx, r14
0x140006677  lea     rax, CcEvtObjectContextCleanup
0x14000667e  mov     [rbp+var_38], rax
0x140006682  add     rcx, r13
0x140006685  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x14000668c  mov     [rbp+var_18], rcx
0x140006690  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140006697  mov     rax, [rax+678h]
0x14000669e  call    _guard_dispatch_icall
0x1400066a3  mov     ebx, eax
0x1400066a5  test    eax, eax
0x1400066a7  js      loc_140006896
0x1400066ad  mov     rcx, rsi; Object
0x1400066b0  call    cs:__imp_ObfReferenceObject
0x1400066b7  nop     dword ptr [rax+rax+00h]
0x1400066bc  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x1400066c3  lea     rcx, aClientcoreTerm_0; "clientcore\\termsrv\\devices\\urbdr\\bu"...
0x1400066ca  mov     [rsp+78h+var_58], rcx
0x1400066cf  mov     r9d, 7B9h
0x1400066d5  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x1400066dc  xor     r8d, r8d
0x1400066df  mov     rdx, rdi
0x1400066e2  mov     rax, [rax+668h]
0x1400066e9  call    _guard_dispatch_icall
0x1400066ee  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x1400066f5  mov     r8, cs:off_14000F0B8
0x1400066fc  mov     rdx, [rbp+arg_0]
0x140006700  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140006707  mov     rax, [rax+650h]
0x14000670e  call    _guard_dispatch_icall
0x140006713  mov     rdx, [rbp+Src]; Src
0x140006717  mov     rsi, rax
0x14000671a  mov     r8, r12; Size
0x14000671d  mov     [rax], rdi
0x140006720  mov     rax, [rbp+arg_10]
0x140006724  lea     rbx, [rsi+r12]
0x140006728  mov     [rsi+8], rax
0x14000672c  lea     rdi, [rbx+r14]
0x140006730  mov     eax, [rbp+arg_28]
0x140006733  mov     [rsi+10h], eax
0x140006736  mov     eax, [rbp+arg_40]
0x14000673c  mov     [rsi+28h], eax
0x14000673f  mov     eax, [rbp+arg_58]
0x140006745  mov     [rsi+40h], eax
0x140006748  lea     rax, [r13+58h]
0x14000674c  add     rax, rdi
0x14000674f  mov     [rsi+20h], r12
0x140006753  mov     [rsi+18h], rax
0x140006757  lea     rax, [r15+0Bh]
0x14000675b  lea     rax, [rdi+rax*8]
0x14000675f  mov     [rsi+38h], r14
0x140006763  add     rax, r13
0x140006766  mov     [rsi+50h], r13
0x14000676a  mov     [rsi+30h], rax
0x14000676e  mov     eax, [rbp+arg_40]
0x140006774  add     rax, 0Bh
0x140006778  add     rax, r15
0x14000677b  lea     rcx, [rdi+rax*8]
0x14000677f  add     rcx, r13
0x140006782  mov     [rsi+48h], rcx
0x140006786  lea     rcx, [rsi+58h]; void *
0x14000678a  call    memmove
0x14000678f  mov     rdx, [rbp+arg_30]; Src
0x140006793  add     rbx, 58h ; 'X'
0x140006797  mov     rcx, rbx; void *
0x14000679a  mov     [rbp+var_48], rbx
0x14000679e  mov     r8, r14; Size
0x1400067a1  call    memmove
0x1400067a6  mov     rdx, [rbp+arg_48]; Src
0x1400067ad  add     rdi, 58h ; 'X'
0x1400067b1  mov     rcx, rdi; void *
0x1400067b4  mov     [rbp+arg_8], rdi
0x1400067b8  mov     r8, r13; Size
0x1400067bb  call    memmove
0x1400067c0  xor     edx, edx
0x1400067c2  mov     r14d, edx
0x1400067c5  test    r14d, r14d
0x1400067c8  jnz     short loc_1400067E0
0x1400067ca  cmp     [rsi+10h], edx
0x1400067cd  jz      loc_14000687C
0x1400067d3  mov     r15, [rsi+18h]
0x1400067d7  lea     r11, [rsi+58h]
0x1400067db  mov     rdi, r12
0x1400067de  jmp     short loc_14000680E
0x1400067e0  cmp     r14d, 1
0x1400067e4  jnz     short loc_1400067FF
0x1400067e6  cmp     [rsi+28h], edx
0x1400067e9  jz      loc_14000687C
0x1400067ef  mov     r15, [rsi+30h]
0x1400067f3  mov     r11, rbx
0x1400067f6  mov     rdi, [rbp+arg_38]
0x1400067fd  jmp     short loc_14000680E
0x1400067ff  cmp     [rsi+40h], edx
0x140006802  jz      short loc_14000687C
0x140006804  mov     r15, [rsi+48h]
0x140006808  mov     r11, rdi
0x14000680b  mov     rdi, r13
0x14000680e  mov     r12d, edx
0x140006811  cmp     [r11], dx
0x140006815  jz      short loc_140006874
0x140006817  mov     [rbp+pcchLength], rdx
0x14000681e  mov     rdx, rdi
0x140006821  mov     eax, r12d
0x140006824  shr     rdx, 1; cchMax
0x140006827  mov     [r15+rax*8], r11
0x14000682b  cmp     rdx, 7FFFFFFFh
0x140006832  ja      short loc_140006891
0x140006834  lea     r8, [rbp+pcchLength]; pcchLength
0x14000683b  mov     rcx, r11; psz
0x14000683e  call    RtlStringLengthWorkerW
0x140006843  xor     edx, edx
0x140006845  mov     ebx, eax
0x140006847  test    eax, eax
0x140006849  js      short loc_140006896
0x14000684b  mov     rax, [rbp+pcchLength]
0x140006852  inc     r12d
0x140006855  lea     rcx, ds:2[rax*2]
0x14000685d  mov     rax, rcx
0x140006860  sub     rdi, rcx
0x140006863  shr     rax, 1
0x140006866  lea     r11, [r11+rax*2]
0x14000686a  cmp     [r11], dx
0x14000686e  jnz     short loc_140006817
0x140006870  mov     rbx, [rbp+var_48]
0x140006874  mov     rdi, [rbp+arg_8]
0x140006878  mov     r12, [rbp+Size]
0x14000687c  inc     r14d
0x14000687f  cmp     r14d, 3
0x140006883  jb      loc_1400067C5
0x140006889  mov     ebx, edx
0x14000688b  mov     rcx, [rbp+arg_0]
0x14000688f  jmp     short loc_1400068B6
0x140006891  mov     ebx, 0C000000Dh
0x140006896  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x14000689d  mov     rdx, [rbp+arg_0]
0x1400068a1  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x1400068a8  mov     rax, [rax+680h]
0x1400068af  call    _guard_dispatch_icall
0x1400068b4  xor     ecx, ecx
0x1400068b6  mov     rax, [rbp+arg_60]
0x1400068bd  mov     [rax], rcx
0x1400068c0  mov     eax, ebx
0x1400068c2  add     rsp, 78h
0x1400068c6  pop     r15
0x1400068c8  pop     r14
0x1400068ca  pop     r13
0x1400068cc  pop     r12
0x1400068ce  pop     rdi
0x1400068cf  pop     rsi
0x1400068d0  pop     rbx
0x1400068d1  pop     rbp
0x1400068d2  retn
```
