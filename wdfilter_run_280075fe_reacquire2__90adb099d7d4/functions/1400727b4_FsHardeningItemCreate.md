# FsHardeningItemCreate

- ea: `0x1400727b4`
- end: `0x140072a4b`
- name: `FsHardeningItemCreate`
- size: `663`
- prototype: `__int64 __usercall@<rax>(PCUNICODE_STRING SourceString@<rcx>, int, int, __int64)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x140072464`
- `0x14008a1a4`

## callees

- `0x1400051bc`
- `0x140005f04`
- `0x14000b704`
- `0x140011890`
- `0x1400727b4`
- `0x140072a4c`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x140072919`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140072919`
- `ntoskrnl!RtlUpcaseUnicodeString` at `0x14007292e`
- `ntoskrnl!RtlUpcaseUnicodeString` at `0x14007292e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140072a12`
- `ntoskrnl!ExFreePoolWithTag` at `0x140072a12`
- `ntoskrnl!ExQueryDepthSList` at `0x1400729cd`
- `ntoskrnl!ExQueryDepthSList` at `0x1400729cd`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1400729fc`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1400729fc`

## pseudocode

```c
__int64 __fastcall FsHardeningItemCreate(
        PCUNICODE_STRING SourceString,
        __int64 a2,
        int a3,
        int a4,
        int a5,
        int a6,
        PSLIST_ENTRY *a7)
{
  int v11; // eax
  PSLIST_ENTRY v13; // rsi
  __int16 v14; // ax
  int v15; // eax
  unsigned int v16; // ebp
  char *v17; // rdi
  USHORT v18; // bx
  USHORT DepthSList; // ax
  PSLIST_ENTRY ListEntry[2]; // [rsp+30h] [rbp-38h] BYREF

  ListEntry[0] = 0;
  if ( !MpFsHardeningData
    || !SourceString
    || !a7
    || (unsigned int)(a3 - 1) > 2
    || (unsigned int)(a4 - 1) > 3
    || (a5 & 0xFFFFFFE0) != 0
    || (unsigned int)(a6 - 1) > 5
    || *(int *)(MpData + 868) >= 0 && a6 == 6 )
  {
    return 3221225485LL;
  }
  *a7 = 0;
  v11 = FsHardeningItemAllocate(SourceString, ListEntry);
  if ( v11 >= 0 )
  {
    _mm_lfence();
    v13 = ListEntry[0];
    *(&ListEntry[0]->Next + 1) = ListEntry[0];
    v13->Next = v13;
    LOBYTE(v13[1].Next) = 0;
    HIDWORD(v13[1].Next) = a3;
    *((_DWORD *)&v13[1].Next + 2) = a4;
    *((_DWORD *)&v13[1].Next + 3) = a5;
    LODWORD(v13[2].Next) = a6;
    v14 = SourceString->Length + 2;
    *((_WORD *)&v13[10].Next + 6) = v14;
    *(struct _SLIST_ENTRY *)((char *)&v13[2] + 8) = 0;
    *((_WORD *)&v13[2].Next + 5) = v14;
    v13[3].Next = (PSLIST_ENTRY)((char *)v13 + 174);
    RtlCopyUnicodeString((PUNICODE_STRING)(&v13[2].Next + 1), SourceString);
    RtlUpcaseUnicodeString((PUNICODE_STRING)(&v13[2].Next + 1), (PCUNICODE_STRING)(&v13[2].Next + 1), 0);
    v15 = MpParseFileNameEx(&v13[2].Next + 1, 0, 0, a2, &v13[3].Next + 1);
    v16 = v15;
    if ( v15 >= 0 )
    {
      *a7 = v13;
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      {
        _mm_lfence();
        WPP_SF_qZd(
          WPP_GLOBAL_Control->AttachedDevice,
          15,
          (unsigned int)WPP_f33b5dcbe4b13cb98fb01cab96d1311e_Traceguids,
          (unsigned int)KeGetCurrentThread(),
          (__int64)SourceString,
          v15);
      }
      if ( v13 )
      {
        if ( (*(_DWORD *)(&v13[10].Next + 1) & 1) != 0 )
        {
          v17 = (char *)MpFsHardeningData + 32;
          ++*((_DWORD *)MpFsHardeningData + 15);
          v18 = *((_WORD *)v17 + 8);
          DepthSList = ExQueryDepthSList((PSLIST_HEADER)v17);
          _mm_lfence();
          if ( DepthSList < v18 )
          {
            ExpInterlockedPushEntrySList((PSLIST_HEADER)v17, v13);
          }
          else
          {
            ++*((_DWORD *)v17 + 8);
            (*((void (__fastcall **)(PSLIST_ENTRY, char *))v17 + 7))(v13, v17);
          }
        }
        else
        {
          ExFreePoolWithTag(v13, 0x6968504Du);
        }
      }
    }
    return v16;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    {
      _mm_lfence();
      WPP_SF_qD(
        WPP_GLOBAL_Control->AttachedDevice,
        14,
        WPP_f33b5dcbe4b13cb98fb01cab96d1311e_Traceguids,
        KeGetCurrentThread(),
        v11);
    }
    return 3221225626LL;
  }
}

```

## disassembly

```asm
0x1400727b4  mov     rax, rsp
0x1400727b7  mov     [rax+8], rbx
0x1400727bb  mov     [rax+10h], rbp
0x1400727bf  mov     [rax+18h], rsi
0x1400727c3  push    rdi
0x1400727c4  push    r12
0x1400727c6  push    r13
0x1400727c8  push    r14
0x1400727ca  push    r15
0x1400727cc  sub     rsp, 40h
0x1400727d0  xor     esi, esi
0x1400727d2  mov     r15d, r9d
0x1400727d5  cmp     cs:MpFsHardeningData, rsi
0x1400727dc  mov     r13d, r8d
0x1400727df  mov     r12, rdx
0x1400727e2  mov     [rax-38h], rsi
0x1400727e6  mov     r14, rcx
0x1400727e9  jz      loc_140072A27
0x1400727ef  test    rcx, rcx
0x1400727f2  jz      loc_140072A27
0x1400727f8  mov     rdi, [rsp+68h+arg_30]
0x140072800  test    rdi, rdi
0x140072803  jz      loc_140072A27
0x140072809  lea     eax, [r8-1]
0x14007280d  lea     ecx, [rsi+2]
0x140072810  cmp     eax, ecx
0x140072812  ja      loc_140072A27
0x140072818  lea     eax, [r9-1]
0x14007281c  cmp     eax, 3
0x14007281f  ja      loc_140072A27
0x140072825  mov     ebp, [rsp+68h+arg_20]
0x14007282c  test    ebp, 0FFFFFFE0h
0x140072832  jnz     loc_140072A27
0x140072838  mov     ebx, [rsp+68h+arg_28]
0x14007283f  lea     eax, [rbx-1]
0x140072842  cmp     eax, 5
0x140072845  ja      loc_140072A27
0x14007284b  mov     rax, cs:MpData
0x140072852  mov     ecx, [rax+364h]
0x140072858  test    ecx, ecx
0x14007285a  js      short loc_140072865
0x14007285c  cmp     ebx, 6
0x14007285f  jz      loc_140072A27
0x140072865  lea     rdx, [rsp+68h+ListEntry]
0x14007286a  mov     [rdi], rsi
0x14007286d  mov     rcx, r14
0x140072870  call    FsHardeningItemAllocate
0x140072875  test    eax, eax
0x140072877  jns     short loc_1400728CA
0x140072879  mov     rdx, cs:WPP_GLOBAL_Control
0x140072880  lea     rcx, WPP_GLOBAL_Control
0x140072887  cmp     rdx, rcx
0x14007288a  jz      short loc_1400728C0
0x14007288c  mov     ecx, [rdx+2Ch]
0x14007288f  test    cl, 1
0x140072892  jz      short loc_1400728C0
0x140072894  lfence
0x140072897  mov     r9, gs:188h
0x1400728a0  lea     r8, WPP_f33b5dcbe4b13cb98fb01cab96d1311e_Traceguids
0x1400728a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400728ae  mov     edx, 0Eh
0x1400728b3  mov     dword ptr [rsp+68h+var_48], eax
0x1400728b7  mov     rcx, [rcx+18h]
0x1400728bb  call    WPP_SF_qD
0x1400728c0  mov     eax, 0C000009Ah
0x1400728c5  jmp     loc_140072A2C
0x1400728ca  lfence
0x1400728cd  mov     rsi, [rsp+68h+ListEntry]
0x1400728d2  xorps   xmm0, xmm0
0x1400728d5  mov     rdx, r14; SourceString
0x1400728d8  mov     [rsi+8], rsi
0x1400728dc  mov     [rsi], rsi
0x1400728df  mov     byte ptr [rsi+10h], 0
0x1400728e3  mov     [rsi+14h], r13d
0x1400728e7  mov     [rsi+18h], r15d
0x1400728eb  mov     [rsi+1Ch], ebp
0x1400728ee  mov     [rsi+20h], ebx
0x1400728f1  lea     rbx, [rsi+28h]
0x1400728f5  movzx   eax, word ptr [r14]
0x1400728f9  mov     rcx, rbx; DestinationString
0x1400728fc  add     ax, 2
0x140072900  mov     [rsi+0ACh], ax
0x140072907  movups  xmmword ptr [rbx], xmm0
0x14007290a  mov     [rbx+2], ax
0x14007290e  lea     rax, [rsi+0AEh]
0x140072915  mov     [rbx+8], rax
0x140072919  call    cs:__imp_RtlCopyUnicodeString
0x140072920  nop     dword ptr [rax+rax+00h]
0x140072925  xor     r8d, r8d; AllocateDestinationString
0x140072928  mov     rdx, rbx; SourceString
0x14007292b  mov     rcx, rbx; DestinationString
0x14007292e  call    cs:__imp_RtlUpcaseUnicodeString
0x140072935  nop     dword ptr [rax+rax+00h]
0x14007293a  lea     rax, [rsi+38h]
0x14007293e  mov     r9, r12
0x140072941  xor     r8d, r8d
0x140072944  mov     [rsp+68h+var_48], rax
0x140072949  xor     edx, edx
0x14007294b  mov     rcx, rbx
0x14007294e  call    MpParseFileNameEx
0x140072953  mov     ebp, eax
0x140072955  test    eax, eax
0x140072957  jns     loc_140072A20
0x14007295d  mov     rdx, cs:WPP_GLOBAL_Control
0x140072964  lea     rcx, WPP_GLOBAL_Control
0x14007296b  cmp     rdx, rcx
0x14007296e  jz      short loc_1400729A9
0x140072970  mov     ecx, [rdx+2Ch]
0x140072973  test    cl, 1
0x140072976  jz      short loc_1400729A9
0x140072978  lfence
0x14007297b  mov     r9, gs:188h
0x140072984  lea     r8, WPP_f33b5dcbe4b13cb98fb01cab96d1311e_Traceguids
0x14007298b  mov     rcx, cs:WPP_GLOBAL_Control
0x140072992  mov     edx, 0Fh
0x140072997  mov     [rsp+68h+var_40], eax
0x14007299b  mov     [rsp+68h+var_48], r14
0x1400729a0  mov     rcx, [rcx+18h]
0x1400729a4  call    WPP_SF_qZd
0x1400729a9  test    rsi, rsi
0x1400729ac  jz      short loc_140072A23
0x1400729ae  mov     eax, [rsi+0A8h]
0x1400729b4  test    al, 1
0x1400729b6  jz      short loc_140072A0A
0x1400729b8  mov     rdi, cs:MpFsHardeningData
0x1400729bf  add     rdi, 20h ; ' '
0x1400729c3  mov     rcx, rdi; SListHead
0x1400729c6  inc     dword ptr [rdi+1Ch]
0x1400729c9  movzx   ebx, word ptr [rdi+10h]
0x1400729cd  call    cs:__imp_ExQueryDepthSList
0x1400729d4  nop     dword ptr [rax+rax+00h]
0x1400729d9  lfence
0x1400729dc  cmp     ax, bx
0x1400729df  jb      short loc_1400729F6
0x1400729e1  inc     dword ptr [rdi+20h]
0x1400729e4  mov     rdx, rdi
0x1400729e7  mov     rax, [rdi+38h]
0x1400729eb  mov     rcx, rsi
0x1400729ee  call    cs:__guard_dispatch_icall_fptr
0x1400729f4  jmp     short loc_140072A23
0x1400729f6  mov     rdx, rsi; ListEntry
0x1400729f9  mov     rcx, rdi; ListHead
0x1400729fc  call    cs:__imp_ExpInterlockedPushEntrySList
0x140072a03  nop     dword ptr [rax+rax+00h]
0x140072a08  jmp     short loc_140072A23
0x140072a0a  mov     edx, 6968504Dh; Tag
0x140072a0f  mov     rcx, rsi; P
0x140072a12  call    cs:__imp_ExFreePoolWithTag
0x140072a19  nop     dword ptr [rax+rax+00h]
0x140072a1e  jmp     short loc_140072A23
0x140072a20  mov     [rdi], rsi
0x140072a23  mov     eax, ebp
0x140072a25  jmp     short loc_140072A2C
0x140072a27  mov     eax, 0C000000Dh
0x140072a2c  lea     r11, [rsp+68h+var_28]
0x140072a31  mov     rbx, [r11+30h]
0x140072a35  mov     rbp, [r11+38h]
0x140072a39  mov     rsi, [r11+40h]
0x140072a3d  mov     rsp, r11
0x140072a40  pop     r15
0x140072a42  pop     r14
0x140072a44  pop     r13
0x140072a46  pop     r12
0x140072a48  pop     rdi
0x140072a49  retn
```
