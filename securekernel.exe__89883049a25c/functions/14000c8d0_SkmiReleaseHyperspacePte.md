# SkmiReleaseHyperspacePte

- ea: `0x14000c8d0`
- end: `0x14000cca2`
- name: `SkmiReleaseHyperspacePte`
- size: `978`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `56`
- callee_count: `5`
- tags: ``

## callers

- `0x140003860`
- `0x14000821c`
- `0x140008500`
- `0x14000a320`
- `0x14000b2c0`
- `0x14000bab0`
- `0x14000d060`
- `0x14000db40`
- `0x140010c00`
- `0x140012750`
- `0x14001b0c0`
- `0x1400273c8`
- `0x1400276d8`
- `0x1400280b0`
- `0x1400290f8`
- `0x14002f42c`
- `0x140031148`
- `0x140032fb0`
- `0x140039f74`
- `0x14003afa4`
- `0x14003b9dc`
- `0x1400507c4`
- `0x140051d48`
- `0x140052318`
- `0x140052970`
- `0x140053778`
- `0x140054118`
- `0x1400541cc`
- `0x140054660`
- `0x140054acc`
- `0x140055000`
- `0x14005549c`
- `0x140055ca8`
- `0x14005b200`
- `0x14005bd70`
- `0x14005c1e0`
- `0x14005d674`
- `0x14005e098`
- `0x14005fc00`
- `0x1400671bc`
- `0x14006977c`
- `0x14006cfe0`
- `0x14006f704`
- `0x14006fcdc`
- `0x14006ffbc`
- `0x140071704`
- `0x14007357c`
- `0x140073890`
- `0x140074c10`
- `0x1400764dc`

## callees

- `0x14000c8d0`
- `0x14002b534`
- `0x14002e70c`
- `0x140081290`
- `0x1400f9a80`

## pseudocode

```c
__int64 __fastcall SkmiReleaseHyperspacePte(unsigned __int64 a1)
{
  struct _EXCEPTION_REGISTRATION_RECORD *ExceptionList; // rdi
  struct _EXCEPTION_REGISTRATION_RECORD *Next; // rax
  __int64 v4; // rbp
  _BYTE *v5; // rax
  unsigned __int64 v6; // r8
  __int64 v7; // rdx
  bool v8; // zf
  unsigned __int64 *v9; // r12
  __int64 result; // rax
  _BYTE *StackBase; // rax
  unsigned __int64 v12; // r8
  __int64 v13; // rdx
  unsigned __int64 *v14; // r15
  _QWORD *v15; // rax
  __int64 v16; // rcx
  __int64 v17; // rdx
  _QWORD *v18; // rax
  __int64 v19; // rcx
  __int64 v20; // rdx
  ULONG v21; // ecx
  __int64 v22; // rdx
  __int64 v23; // rcx
  ULONG v24; // ecx
  __int64 v25; // rdx
  __int64 v26; // rcx
  unsigned __int64 retaddr; // [rsp+48h] [rbp+0h]
  ULONG BackTraceHash; // [rsp+58h] [rbp+10h] BYREF

  ExceptionList = KeGetPcr()->NtTib.ExceptionList;
  Next = ExceptionList[5].Next;
  if ( Next )
  {
    v4 = (__int64)(a1 - (_QWORD)Next) >> 3;
    if ( SkmiDataTraces )
    {
      if ( (StackBase = KeGetPcr()->NtTib.StackBase, v12 = *(_QWORD *)a1, StackBase) && StackBase[344]
        || (a1 < 0xFFFFF68000000000uLL || a1 > 0xFFFFF6FFFFFFFFFFuLL)
        && (a1 < 0xFFFFF60000000000uLL || a1 > 0xFFFFF67FFFFFFFFFuLL)
        && (v12 & 0x10000000000000LL) != 0 )
      {
        v13 = _InterlockedExchangeAdd(&SkmiDataTraceIndex, 1u) & (unsigned int)(SkmiDataTraceSize - 1);
        v8 = SkmiDataTraces + 96 * v13 == 0;
        v14 = (unsigned __int64 *)(SkmiDataTraces + 96 * v13);
        *v14 = 0;
        v14[1] = 0;
        if ( !v8 )
        {
          v14[2] = v12;
          *v14 = a1;
          v14[3] = 0;
          *((_BYTE *)v14 + 8) = 1;
          memset_0(v14 + 4, 0, 0x40u);
          if ( (SkmiFlags & 0x400000) != 0
            && KeGetPcr()->NtTib.StackBase
            && !RtlCaptureStackBackTrace(v24, 8u, (PVOID *)v14 + 4, &BackTraceHash) )
          {
            v14[5] = retaddr;
            v14[4] = SkmiGetInstructionPointer(v26, v25);
          }
        }
      }
    }
    if ( a1 >= 0xFFFFF6FB7DBED000uLL && a1 < 0xFFFFF6FB7DBED800uLL )
    {
      v18 = KeGetPcr()->NtTib.StackBase;
      v19 = v18 ? v18[10] : 0LL;
      v20 = *(_QWORD *)(v19 + 232);
      if ( v20 )
        *(_QWORD *)(v20 + 8 * (((__int64)a1 >> 3) & 0x1FF)) = 0;
    }
    *(_QWORD *)a1 = 0;
    result = 96;
  }
  else
  {
    v4 = (__int64)(a1 - (((unsigned __int64)qword_140156C20 >> 9) & 0x7FFFFFFFF8LL) + 0x98000000000LL) >> 3;
    if ( SkmiDataTraces )
    {
      if ( (v5 = KeGetPcr()->NtTib.StackBase, v6 = *(_QWORD *)a1, v5) && v5[344]
        || (a1 < 0xFFFFF68000000000uLL || a1 > 0xFFFFF6FFFFFFFFFFuLL)
        && (a1 < 0xFFFFF60000000000uLL || a1 > 0xFFFFF67FFFFFFFFFuLL)
        && (v6 & 0x10000000000000LL) != 0 )
      {
        v7 = _InterlockedExchangeAdd(&SkmiDataTraceIndex, 1u) & (unsigned int)(SkmiDataTraceSize - 1);
        v8 = SkmiDataTraces + 96 * v7 == 0;
        v9 = (unsigned __int64 *)(SkmiDataTraces + 96 * v7);
        *v9 = 0;
        v9[1] = 0;
        if ( !v8 )
        {
          v9[2] = v6;
          *v9 = a1;
          v9[3] = 0;
          *((_BYTE *)v9 + 8) = 1;
          memset_0(v9 + 4, 0, 0x40u);
          if ( (SkmiFlags & 0x400000) != 0
            && KeGetPcr()->NtTib.StackBase
            && !RtlCaptureStackBackTrace(v21, 8u, (PVOID *)v9 + 4, &BackTraceHash) )
          {
            v9[5] = retaddr;
            v9[4] = SkmiGetInstructionPointer(v23, v22);
          }
        }
      }
    }
    if ( a1 >= 0xFFFFF6FB7DBED000uLL && a1 < 0xFFFFF6FB7DBED800uLL )
    {
      v15 = KeGetPcr()->NtTib.StackBase;
      if ( v15 )
        v16 = v15[10];
      else
        v16 = 0;
      v17 = *(_QWORD *)(v16 + 232);
      if ( v17 )
        *(_QWORD *)(v17 + 8 * (((__int64)a1 >> 3) & 0x1FF)) = 0;
    }
    *(_QWORD *)a1 = 0;
    SkeFlushSingleCurrentTb((__int64)(a1 << 25) >> 16);
    result = 88;
  }
  _InterlockedOr64((volatile signed __int64 *)((char *)ExceptionList + result), 1LL << v4);
  return result;
}

```

## disassembly

```asm
0x14000c8d0  mov     [rsp+arg_10], rbx
0x14000c8d5  mov     [rsp+arg_18], rbp
0x14000c8da  push    rsi
0x14000c8db  push    rdi
0x14000c8dc  push    r12
0x14000c8de  push    r14
0x14000c8e0  push    r15
0x14000c8e2  sub     rsp, 20h
0x14000c8e6  mov     rdi, gs:0
0x14000c8ef  mov     rbx, rcx
0x14000c8f2  mov     rbp, rcx
0x14000c8f5  mov     rax, [rdi+50h]
0x14000c8f9  test    rax, rax
0x14000c8fc  jnz     loc_14000CA32
0x14000c902  mov     rax, cs:qword_140156C20
0x14000c909  mov     rcx, 7FFFFFFFF8h
0x14000c913  shr     rax, 9
0x14000c917  and     rax, rcx
0x14000c91a  mov     r15, 0FFFFF68000000000h
0x14000c924  sub     rbp, rax
0x14000c927  mov     rax, r15
0x14000c92a  sub     rbp, rax
0x14000c92d  xor     r14d, r14d
0x14000c930  sar     rbp, 3
0x14000c934  mov     esi, 1
0x14000c939  cmp     cs:SkmiDataTraces, r14
0x14000c940  jz      loc_14000C9D8
0x14000c946  mov     rax, gs:8
0x14000c94f  mov     r8, [rbx]
0x14000c952  test    rax, rax
0x14000c955  jz      short loc_14000C960
0x14000c957  cmp     [rax+158h], r14b
0x14000c95e  jnz     short loc_14000C9A5
0x14000c960  mov     rax, r15
0x14000c963  cmp     rbx, rax
0x14000c966  jb      short loc_14000C97A
0x14000c968  mov     rax, 0FFFFF6FFFFFFFFFFh
0x14000c972  mov     rax, rax
0x14000c975  cmp     rbx, rax
0x14000c978  jbe     short loc_14000C9D8
0x14000c97a  mov     rax, 0FFFFF60000000000h
0x14000c984  mov     rax, rax
0x14000c987  cmp     rbx, rax
0x14000c98a  jb      short loc_14000C99E
0x14000c98c  mov     rax, 0FFFFF67FFFFFFFFFh
0x14000c996  mov     rax, rax
0x14000c999  cmp     rbx, rax
0x14000c99c  jbe     short loc_14000C9D8
0x14000c99e  bt      r8, 34h ; '4'
0x14000c9a3  jnb     short loc_14000C9D8
0x14000c9a5  mov     eax, esi
0x14000c9a7  lock xadd cs:SkmiDataTraceIndex, eax
0x14000c9af  mov     edx, cs:SkmiDataTraceSize
0x14000c9b5  dec     edx
0x14000c9b7  and     rdx, rax
0x14000c9ba  lea     r12, [rdx+rdx*2]
0x14000c9be  shl     r12, 5
0x14000c9c2  add     r12, cs:SkmiDataTraces
0x14000c9c9  mov     [r12], r14
0x14000c9cd  mov     [r12+8], r14
0x14000c9d2  jnz     loc_14000CB7C
0x14000c9d8  mov     rax, 0FFFFF6FB7DBED000h
0x14000c9e2  mov     rax, rax
0x14000c9e5  cmp     rbx, rax
0x14000c9e8  jnb     loc_14000CBF7
0x14000c9ee  mov     [rbx], r14
0x14000c9f1  mov     rax, r15
0x14000c9f4  shl     rbx, 19h
0x14000c9f8  shl     rax, 19h
0x14000c9fc  sub     rbx, rax
0x14000c9ff  sar     rbx, 10h
0x14000ca03  mov     rcx, rbx
0x14000ca06  call    SkeFlushSingleCurrentTb
0x14000ca0b  mov     eax, 58h ; 'X'
0x14000ca10  mov     ecx, ebp
0x14000ca12  shl     rsi, cl
0x14000ca15  lock or [rax+rdi], rsi
0x14000ca1a  mov     rbx, [rsp+48h+arg_10]
0x14000ca1f  mov     rbp, [rsp+48h+arg_18]
0x14000ca24  add     rsp, 20h
0x14000ca28  pop     r15
0x14000ca2a  pop     r14
0x14000ca2c  pop     r12
0x14000ca2e  pop     rdi
0x14000ca2f  pop     rsi
0x14000ca30  retn
0x14000ca32  sub     rbp, rax
0x14000ca35  xor     r14d, r14d
0x14000ca38  sar     rbp, 3
0x14000ca3c  mov     esi, 1
0x14000ca41  cmp     cs:SkmiDataTraces, r14
0x14000ca48  jz      loc_14000CAE8
0x14000ca4e  mov     rax, gs:8
0x14000ca57  mov     r8, [rcx]
0x14000ca5a  test    rax, rax
0x14000ca5d  jz      short loc_14000CA68
0x14000ca5f  cmp     [rax+158h], r14b
0x14000ca66  jnz     short loc_14000CAB7
0x14000ca68  mov     r15, 0FFFFF68000000000h
0x14000ca72  mov     rax, r15
0x14000ca75  cmp     rbx, rax
0x14000ca78  jb      short loc_14000CA8C
0x14000ca7a  mov     rax, 0FFFFF6FFFFFFFFFFh
0x14000ca84  mov     rax, rax
0x14000ca87  cmp     rbx, rax
0x14000ca8a  jbe     short loc_14000CAE8
0x14000ca8c  mov     rax, 0FFFFF60000000000h
0x14000ca96  mov     rax, rax
0x14000ca99  cmp     rbx, rax
0x14000ca9c  jb      short loc_14000CAB0
0x14000ca9e  mov     rax, 0FFFFF67FFFFFFFFFh
0x14000caa8  mov     rax, rax
0x14000caab  cmp     rbx, rax
0x14000caae  jbe     short loc_14000CAE8
0x14000cab0  bt      r8, 34h ; '4'
0x14000cab5  jnb     short loc_14000CAE8
0x14000cab7  mov     eax, esi
0x14000cab9  lock xadd cs:SkmiDataTraceIndex, eax
0x14000cac1  mov     edx, cs:SkmiDataTraceSize
0x14000cac7  dec     edx
0x14000cac9  and     rdx, rax
0x14000cacc  lea     r15, [rdx+rdx*2]
0x14000cad0  shl     r15, 5
0x14000cad4  add     r15, cs:SkmiDataTraces
0x14000cadb  mov     [r15], r14
0x14000cade  mov     [r15+8], r14
0x14000cae2  jnz     loc_14000CC12
0x14000cae8  mov     rax, 0FFFFF6FB7DBED000h
0x14000caf2  mov     rax, rax
0x14000caf5  cmp     rbx, rax
0x14000caf8  jnb     loc_14000CC87
0x14000cafe  mov     [rbx], r14
0x14000cb01  mov     eax, 60h ; '`'
0x14000cb06  jmp     loc_14000CA10
0x14000cb0b  mov     rax, gs:8
0x14000cb14  test    rax, rax
0x14000cb17  jz      short loc_14000CB42
0x14000cb19  mov     rcx, [rax+50h]
0x14000cb1d  mov     rdx, [rcx+0E8h]
0x14000cb24  test    rdx, rdx
0x14000cb27  jz      loc_14000C9EE
0x14000cb2d  mov     rax, rbx
0x14000cb30  sar     rax, 3
0x14000cb34  and     eax, 1FFh
0x14000cb39  mov     [rdx+rax*8], r14
0x14000cb3d  jmp     loc_14000C9EE
0x14000cb42  mov     rcx, r14
0x14000cb45  jmp     short loc_14000CB1D
0x14000cb47  mov     rax, gs:8
0x14000cb50  test    rax, rax
0x14000cb53  jz      short loc_14000CB77
0x14000cb55  mov     rcx, [rax+50h]
0x14000cb59  mov     rdx, [rcx+0E8h]
0x14000cb60  test    rdx, rdx
0x14000cb63  jz      short loc_14000CAFE
0x14000cb65  mov     rax, rbx
0x14000cb68  sar     rax, 3
0x14000cb6c  and     eax, 1FFh
0x14000cb71  mov     [rdx+rax*8], r14
0x14000cb75  jmp     short loc_14000CAFE
0x14000cb77  mov     rcx, r14
0x14000cb7a  jmp     short loc_14000CB59
0x14000cb7c  mov     [r12+10h], r8
0x14000cb81  lea     rcx, [r12+20h]; void *
0x14000cb86  mov     r8d, 40h ; '@'; Size
0x14000cb8c  mov     [rsp+48h+arg_0], r13
0x14000cb91  xor     edx, edx; Val
0x14000cb93  mov     [r12], rbx
0x14000cb97  mov     [r12+18h], r14
0x14000cb9c  mov     [r12+8], sil
0x14000cba1  call    memset_0
0x14000cba6  test    cs:SkmiFlags, 400000h
0x14000cbb0  jz      short loc_14000CBED
0x14000cbb2  mov     rax, gs:8
0x14000cbbb  test    rax, rax
0x14000cbbe  jz      short loc_14000CBED
0x14000cbc0  lea     r9, [rsp+48h+BackTraceHash]; BackTraceHash
0x14000cbc5  mov     edx, 8; FramesToCapture
0x14000cbca  lea     r8, [r12+20h]; BackTrace
0x14000cbcf  call    RtlCaptureStackBackTrace
0x14000cbd4  test    ax, ax
0x14000cbd7  jnz     short loc_14000CBED
0x14000cbd9  mov     rax, [rsp+48h]
0x14000cbde  mov     [r12+28h], rax
0x14000cbe3  call    SkmiGetInstructionPointer
0x14000cbe8  mov     [r12+20h], rax
0x14000cbed  mov     r13, [rsp+48h+arg_0]
0x14000cbf2  jmp     loc_14000C9D8
0x14000cbf7  mov     rax, 0FFFFF6FB7DBED800h
0x14000cc01  mov     rax, rax
0x14000cc04  cmp     rbx, rax
0x14000cc07  jnb     loc_14000C9EE
0x14000cc0d  jmp     loc_14000CB0B
0x14000cc12  mov     [r15+10h], r8
0x14000cc16  lea     rcx, [r15+20h]; void *
0x14000cc1a  mov     r8d, 40h ; '@'; Size
0x14000cc20  mov     [r15], rbx
0x14000cc23  xor     edx, edx; Val
0x14000cc25  mov     [r15+18h], r14
0x14000cc29  mov     [r15+8], sil
0x14000cc2d  call    memset_0
0x14000cc32  test    cs:SkmiFlags, 400000h
0x14000cc3c  jz      loc_14000CAE8
0x14000cc42  mov     rax, gs:8
0x14000cc4b  test    rax, rax
0x14000cc4e  jz      loc_14000CAE8
0x14000cc54  lea     r9, [rsp+48h+BackTraceHash]; BackTraceHash
0x14000cc59  mov     edx, 8; FramesToCapture
0x14000cc5e  lea     r8, [r15+20h]; BackTrace
0x14000cc62  call    RtlCaptureStackBackTrace
0x14000cc67  test    ax, ax
0x14000cc6a  jnz     loc_14000CAE8
0x14000cc70  mov     rax, [rsp+48h]
0x14000cc75  mov     [r15+28h], rax
0x14000cc79  call    SkmiGetInstructionPointer
0x14000cc7e  mov     [r15+20h], rax
0x14000cc82  jmp     loc_14000CAE8
0x14000cc87  mov     rax, 0FFFFF6FB7DBED800h
0x14000cc91  mov     rax, rax
0x14000cc94  cmp     rbx, rax
0x14000cc97  jnb     loc_14000CAFE
0x14000cc9d  jmp     loc_14000CB47
```
