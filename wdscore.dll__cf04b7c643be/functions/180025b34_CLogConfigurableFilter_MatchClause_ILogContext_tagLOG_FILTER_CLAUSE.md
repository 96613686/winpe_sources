# CLogConfigurableFilter::MatchClause(ILogContext *,tagLOG_FILTER_CLAUSE *)

- ea: `0x180025b34`
- end: `0x180025bd3`
- name: `?MatchClause@CLogConfigurableFilter@@IEAAHPEAVILogContext@@PEAUtagLOG_FILTER_CLAUSE@@@Z`
- size: `159`
- prototype: `__int64 __fastcall(CLogConfigurableFilter *__hidden this, struct ILogContext *, struct tagLOG_FILTER_CLAUSE *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800260a0`

## callees

- `0x180022680`
- `0x180025828`
- `0x180025894`
- `0x180025b34`
- `0x18002a010`

## pseudocode

```c
char __fastcall CLogConfigurableFilter::MatchClause(
        CLogConfigurableFilter *this,
        struct ILogContext *a2,
        struct tagLOG_FILTER_CLAUSE *a3)
{
  __int64 v4; // rax
  __int64 v5; // rcx
  int v6; // edx
  __int64 v7; // rdx
  int v8; // eax
  int v9; // edi
  int v10; // edx

  v4 = (*(__int64 (__fastcall **)(struct ILogContext *, _QWORD))(*(_QWORD *)a2 + 48LL))(a2, *(unsigned int *)a3);
  if ( !v4 )
    goto LABEL_11;
  v6 = *(_DWORD *)(v4 + 520);
  if ( v6 != *((_DWORD *)a3 + 2) )
    goto LABEL_11;
  if ( v6 )
  {
    v7 = (unsigned int)(v6 - 1);
    if ( !(_DWORD)v7 )
    {
      LOBYTE(v8) = CLogConfigurableFilter::CompareDword(
                     v5,
                     *(unsigned int *)(v4 + 528),
                     *((unsigned int *)a3 + 1),
                     *((unsigned int *)a3 + 4));
      return v8;
    }
    if ( (_DWORD)v7 == 2 )
    {
      LOBYTE(v8) = CLogConfigurableFilter::CompareDate(v5, v7, *((unsigned int *)a3 + 1));
      return v8;
    }
LABEL_11:
    LOBYTE(v8) = 0;
    return v8;
  }
  v9 = *((_DWORD *)a3 + 1);
  v8 = TestParsedPatternW(*((_QWORD *)a3 + 2), *(_QWORD *)(v4 + 528));
  v10 = v8;
  if ( v9 )
  {
    LOBYTE(v8) = 0;
    if ( v9 == 1 )
      LOBYTE(v8) = v10 == 0;
  }
  return v8;
}

```

## disassembly

```asm
0x180025b34  mov     [rsp+arg_0], rbx
0x180025b39  push    rdi
0x180025b3a  sub     rsp, 20h
0x180025b3e  mov     rax, [rdx]
0x180025b41  mov     rcx, rdx
0x180025b44  mov     edx, [r8]
0x180025b47  mov     rbx, r8
0x180025b4a  mov     rax, [rax+30h]
0x180025b4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025b53  test    rax, rax
0x180025b56  jz      short loc_180025BC5
0x180025b58  mov     edx, [rax+208h]
0x180025b5e  cmp     edx, [rbx+8]
0x180025b61  jnz     short loc_180025BC5
0x180025b63  test    edx, edx
0x180025b65  jz      short loc_180025B9E
0x180025b67  sub     edx, 1
0x180025b6a  jz      short loc_180025B89
0x180025b6c  cmp     edx, 2
0x180025b6f  jnz     short loc_180025BC5
0x180025b71  movsd   xmm3, qword ptr [rbx+10h]
0x180025b76  mov     r8d, [rbx+4]
0x180025b7a  movsd   xmm1, qword ptr [rax+210h]
0x180025b82  call    ?CompareDate@CLogConfigurableFilter@@IEAAHNW4tagLOG_FILTER_COMPAREOP@@N@Z; CLogConfigurableFilter::CompareDate(double,tagLOG_FILTER_COMPAREOP,double)
0x180025b87  jmp     short loc_180025BC7
0x180025b89  mov     r8d, [rbx+4]
0x180025b8d  mov     r9d, [rbx+10h]
0x180025b91  mov     edx, [rax+210h]
0x180025b97  call    ?CompareDword@CLogConfigurableFilter@@IEAAHKW4tagLOG_FILTER_COMPAREOP@@K@Z; CLogConfigurableFilter::CompareDword(ulong,tagLOG_FILTER_COMPAREOP,ulong)
0x180025b9c  jmp     short loc_180025BC7
0x180025b9e  mov     rdx, [rax+210h]
0x180025ba5  mov     rcx, [rbx+10h]
0x180025ba9  mov     edi, [rbx+4]
0x180025bac  call    TestParsedPatternW
0x180025bb1  mov     edx, eax
0x180025bb3  test    edi, edi
0x180025bb5  jz      short loc_180025BC7
0x180025bb7  xor     eax, eax
0x180025bb9  cmp     edi, 1
0x180025bbc  jnz     short loc_180025BC7
0x180025bbe  test    edx, edx
0x180025bc0  setz    al
0x180025bc3  jmp     short loc_180025BC7
0x180025bc5  xor     eax, eax
0x180025bc7  mov     rbx, [rsp+28h+arg_0]
0x180025bcc  add     rsp, 20h
0x180025bd0  pop     rdi
0x180025bd1  retn
```
