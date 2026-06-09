# CWdsMetadata::ComputeMatch(CWdsMetadata const *,int,int *)

- ea: `0x18000d160`
- end: `0x18000d2e8`
- name: `?ComputeMatch@CWdsMetadata@@AEBAKPEBV1@HPEAH@Z`
- size: `392`
- prototype: `unsigned int __fastcall(CWdsMetadata *__hidden this, const struct CWdsMetadata *, int, int *)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000ec90`
- `0x18000ee00`

## callees

- `0x18000a7ec`
- `0x18000ce50`
- `0x18000d160`
- `0x180014d58`

## pseudocode

```c
__int64 __fastcall CWdsMetadata::ComputeMatch(CWdsMetadata *this, const struct CWdsMetadata *a2, int a3, int *a4)
{
  int v5; // edi
  int v6; // ecx
  unsigned int matched; // ebx
  __int64 v8; // rbp
  unsigned int v10; // eax
  struct CWdsMetadata::CEntryGroup *v12; // r14
  __int64 v13; // r15
  __int64 v14; // rcx
  int GroupIndex; // eax
  const char *v16; // rdx
  int v18; // [rsp+30h] [rbp-48h]
  int v19; // [rsp+80h] [rbp+8h] BYREF
  int v20; // [rsp+90h] [rbp+18h]

  v20 = a3;
  v5 = 0;
  v6 = 0;
  v19 = 0;
  matched = 0;
  v18 = 0;
  v8 = 0;
  v10 = *((_DWORD *)this + 3);
  if ( v10 )
  {
    while ( 1 )
    {
      v12 = 0;
      v13 = 0;
      matched = 0;
      if ( (unsigned int)v8 < v10 )
        v12 = *(struct CWdsMetadata::CEntryGroup **)(*(_QWORD *)this + 8 * v8);
      else
        matched = 1413;
      if ( ElValidateWin32(matched, (const char *)a2, "base\\eco\\wds\\lib\\metadata\\core\\metadata.cpp", 0x16C2u) )
        break;
      GroupIndex = CWdsMetadata::FindGroupIndex(v14, a2, *(_QWORD *)v12);
      if ( GroupIndex < 0 )
        goto LABEL_19;
      matched = 0;
      if ( (unsigned int)GroupIndex < *((_DWORD *)a2 + 3) )
      {
        _mm_lfence();
        v5 = v19;
        v13 = *(_QWORD *)(*(_QWORD *)a2 + 8LL * (unsigned int)GroupIndex);
      }
      else
      {
        matched = 1413;
      }
      if ( ElValidateWin32(matched, (const char *)a2, "base\\eco\\wds\\lib\\metadata\\core\\metadata.cpp", 0x16CBu) )
        return matched;
      if ( *((_DWORD *)v12 + 5) )
      {
        a3 = v20;
        if ( *(_DWORD *)(v13 + 20) )
        {
          v18 = 1;
          matched = CWdsMetadata::MatchTag(this, a2, v20, v12, (struct CWdsMetadata::CEntryGroup *)v13, &v19);
          if ( ElValidateWin32(matched, v16, "base\\eco\\wds\\lib\\metadata\\core\\metadata.cpp", 0x16D8u) )
            return matched;
          a3 = v20;
          v5 = v19;
          if ( v20 )
          {
            if ( !v19 )
            {
              *a4 = 0;
              return matched;
            }
          }
          else if ( v19 )
          {
            goto LABEL_25;
          }
        }
      }
      else
      {
LABEL_19:
        a3 = v20;
      }
      v10 = *((_DWORD *)this + 3);
      v8 = (unsigned int)(v8 + 1);
      if ( (unsigned int)v8 >= v10 )
      {
        v6 = v18;
        goto LABEL_22;
      }
    }
  }
  else
  {
LABEL_22:
    if ( a3 || !v6 )
      *a4 = 1;
    else
LABEL_25:
      *a4 = v5;
  }
  return matched;
}

```

## disassembly

```asm
0x18000d160  mov     rax, rsp
0x18000d163  mov     [rax+10h], rbx
0x18000d167  mov     [rax+18h], r8d
0x18000d16b  push    rbp
0x18000d16c  push    rsi
0x18000d16d  push    rdi
0x18000d16e  push    r12
0x18000d170  push    r13
0x18000d172  push    r14
0x18000d174  push    r15
0x18000d176  sub     rsp, 40h
0x18000d17a  mov     r12, rcx
0x18000d17d  xor     edi, edi
0x18000d17f  xor     ecx, ecx
0x18000d181  mov     [rax+8], edi
0x18000d184  xor     ebx, ebx
0x18000d186  mov     [rsp+78h+var_48], ecx
0x18000d18a  xor     ebp, ebp
0x18000d18c  mov     rsi, r9
0x18000d18f  mov     eax, [r12+0Ch]
0x18000d194  mov     r13, rdx
0x18000d197  test    eax, eax
0x18000d199  jz      loc_18000D2BB
0x18000d19f  xor     r14d, r14d
0x18000d1a2  xor     r15d, r15d
0x18000d1a5  xor     ebx, ebx
0x18000d1a7  cmp     ebp, eax
0x18000d1a9  jb      short loc_18000D1B2
0x18000d1ab  mov     ebx, 585h
0x18000d1b0  jmp     short loc_18000D1BA
0x18000d1b2  mov     rax, [r12]
0x18000d1b6  mov     r14, [rax+rbp*8]
0x18000d1ba  mov     r9d, 16C2h; unsigned int
0x18000d1c0  lea     r8, aBaseEcoWdsLibM; "base\\eco\\wds\\lib\\metadata\\core\\me"...
0x18000d1c7  mov     ecx, ebx; unsigned int
0x18000d1c9  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000d1ce  test    eax, eax
0x18000d1d0  jnz     loc_18000D2CE
0x18000d1d6  mov     r8, [r14]
0x18000d1d9  mov     rdx, r13
0x18000d1dc  call    ?FindGroupIndex@CWdsMetadata@@AEBAHPEAV?$CDynArray@PEAUCEntryGroup@CWdsMetadata@@VCDeallocatePointer@@@@PEBG@Z; CWdsMetadata::FindGroupIndex(CDynArray<CWdsMetadata::CEntryGroup *,CDeallocatePointer> *,ushort const *)
0x18000d1e1  test    eax, eax
0x18000d1e3  js      loc_18000D2A0
0x18000d1e9  xor     ebx, ebx
0x18000d1eb  cmp     eax, [r13+0Ch]
0x18000d1ef  jb      short loc_18000D1F8
0x18000d1f1  mov     ebx, 585h
0x18000d1f6  jmp     short loc_18000D20C
0x18000d1f8  lfence
0x18000d1fb  mov     edi, [rsp+78h+arg_0]
0x18000d202  mov     ecx, eax
0x18000d204  mov     rax, [r13+0]
0x18000d208  mov     r15, [rax+rcx*8]
0x18000d20c  mov     r9d, 16CBh; unsigned int
0x18000d212  lea     r8, aBaseEcoWdsLibM; "base\\eco\\wds\\lib\\metadata\\core\\me"...
0x18000d219  mov     ecx, ebx; unsigned int
0x18000d21b  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000d220  test    eax, eax
0x18000d222  jnz     loc_18000D2CE
0x18000d228  cmp     [r14+14h], eax
0x18000d22c  jz      short loc_18000D2A0
0x18000d22e  mov     r8d, [rsp+78h+arg_10]; int
0x18000d236  cmp     [r15+14h], eax
0x18000d23a  jz      short loc_18000D2A8
0x18000d23c  lea     rax, [rsp+78h+arg_0]
0x18000d244  mov     [rsp+78h+var_48], 1
0x18000d24c  mov     [rsp+78h+var_50], rax; int *
0x18000d251  mov     r9, r14; struct CWdsMetadata::CEntryGroup *
0x18000d254  mov     rdx, r13; struct CWdsMetadata *
0x18000d257  mov     [rsp+78h+var_58], r15; struct CWdsMetadata::CEntryGroup *
0x18000d25c  mov     rcx, r12; this
0x18000d25f  call    ?MatchTag@CWdsMetadata@@AEBAKPEBV1@HPEAUCEntryGroup@1@1PEAH@Z; CWdsMetadata::MatchTag(CWdsMetadata const *,int,CWdsMetadata::CEntryGroup *,CWdsMetadata::CEntryGroup *,int *)
0x18000d264  mov     r9d, 16D8h; unsigned int
0x18000d26a  lea     r8, aBaseEcoWdsLibM; "base\\eco\\wds\\lib\\metadata\\core\\me"...
0x18000d271  mov     ecx, eax; unsigned int
0x18000d273  mov     ebx, eax
0x18000d275  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000d27a  test    eax, eax
0x18000d27c  jnz     short loc_18000D2CE
0x18000d27e  mov     r8d, [rsp+78h+arg_10]
0x18000d286  mov     edi, [rsp+78h+arg_0]
0x18000d28d  test    r8d, r8d
0x18000d290  jz      short loc_18000D29A
0x18000d292  test    edi, edi
0x18000d294  jnz     short loc_18000D2A8
0x18000d296  and     [rsi], edi
0x18000d298  jmp     short loc_18000D2CE
0x18000d29a  test    edi, edi
0x18000d29c  jnz     short loc_18000D2CC
0x18000d29e  jmp     short loc_18000D2A8
0x18000d2a0  mov     r8d, [rsp+78h+arg_10]
0x18000d2a8  mov     eax, [r12+0Ch]
0x18000d2ad  inc     ebp
0x18000d2af  cmp     ebp, eax
0x18000d2b1  jb      loc_18000D19F
0x18000d2b7  mov     ecx, [rsp+78h+var_48]
0x18000d2bb  test    r8d, r8d
0x18000d2be  jz      short loc_18000D2C8
0x18000d2c0  mov     dword ptr [rsi], 1
0x18000d2c6  jmp     short loc_18000D2CE
0x18000d2c8  test    ecx, ecx
0x18000d2ca  jz      short loc_18000D2C0
0x18000d2cc  mov     [rsi], edi
0x18000d2ce  mov     eax, ebx
0x18000d2d0  mov     rbx, [rsp+78h+arg_8]
0x18000d2d8  add     rsp, 40h
0x18000d2dc  pop     r15
0x18000d2de  pop     r14
0x18000d2e0  pop     r13
0x18000d2e2  pop     r12
0x18000d2e4  pop     rdi
0x18000d2e5  pop     rsi
0x18000d2e6  pop     rbp
0x18000d2e7  retn
```
