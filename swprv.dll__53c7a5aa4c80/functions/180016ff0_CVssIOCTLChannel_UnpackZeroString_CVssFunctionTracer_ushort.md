# CVssIOCTLChannel::UnpackZeroString(CVssFunctionTracer &,ushort * &)

- ea: `0x180016ff0`
- end: `0x1800171d5`
- name: `?UnpackZeroString@CVssIOCTLChannel@@QEAAPEBGAEAVCVssFunctionTracer@@AEAPEAG@Z`
- size: `485`
- prototype: `const unsigned __int16 *__fastcall(CVssIOCTLChannel *__hidden this, struct CVssFunctionTracer *, unsigned __int16 **)`
- caller_count: `8`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x180011178`
- `0x18001c5dc`
- `0x18001de8c`
- `0x18001e270`
- `0x18001fb80`
- `0x18002432c`
- `0x180024a6c`
- `0x180025228`

## callees

- `0x18000212c`
- `0x18000d6bc`
- `0x180016ff0`
- `0x1800171dc`
- `0x18003649c`
- `0x180037080`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001701c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017147`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001701c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017147`

## string_xrefs

- `0x180017098`: `Reading from NULL buffer`

## pseudocode

```c
const unsigned __int16 *__fastcall CVssIOCTLChannel::UnpackZeroString(
        CVssIOCTLChannel *this,
        struct CVssFunctionTracer *a2,
        LPVOID *a3)
{
  LPVOID *v3; // rbx
  CVssFunctionTracer *v4; // rsi
  __int64 v6; // r14
  unsigned __int16 *v7; // rax
  const unsigned __int16 *result; // rax
  int *v9; // r14
  unsigned int v10; // ebx
  unsigned int v11; // [rsp+40h] [rbp-F8h] BYREF
  int *v12; // [rsp+48h] [rbp-F0h]
  const unsigned __int16 *v13; // [rsp+50h] [rbp-E8h] BYREF
  const unsigned __int16 *v14; // [rsp+58h] [rbp-E0h]
  const unsigned __int16 *v15; // [rsp+60h] [rbp-D8h]
  int v16; // [rsp+68h] [rbp-D0h]
  int v17; // [rsp+6Ch] [rbp-CCh]
  int v18; // [rsp+70h] [rbp-C8h]
  _BYTE v19[120]; // [rsp+78h] [rbp-C0h] BYREF
  int v20; // [rsp+F0h] [rbp-48h]
  _com_error *v21; // [rsp+F8h] [rbp-40h] BYREF
  const std::exception *v22; // [rsp+100h] [rbp-38h] BYREF
  __int16 v23; // [rsp+140h] [rbp+8h] BYREF
  CVssFunctionTracer *v24; // [rsp+148h] [rbp+10h]
  LPVOID *v25; // [rsp+150h] [rbp+18h]
  LPVOID *v26; // [rsp+158h] [rbp+20h]

  v25 = a3;
  v24 = a2;
  v3 = a3;
  v4 = a2;
  v26 = a3;
  CoTaskMemFree(*a3);
  try
  {
    *v3 = 0;
    v12 = (int *)((char *)v4 + 8);
    *((_DWORD *)v4 + 2) = 0;
    if ( !*((_QWORD *)this + 10) )
    {
      *((_DWORD *)this + 11) = 0;
      *((_DWORD *)this + 16) = 0;
      v13 = L"base\\stor\\vss\\inc\\ichannel.hxx";
      v14 = L"CVssIOCTLChannel::UnpackZeroString";
      v15 = L"INCICHLH";
      v16 = 989;
      v17 = 10;
      v18 = 255;
      v20 = 0x1000000;
      memset_0(v19, 0, sizeof(v19));
      CVssFunctionTracer::TranslateGenericError(v4, &v13, 2147549183LL, L"Reading from NULL buffer");
    }
    v6 = -1;
    do
      ++v6;
    while ( *(_WORD *)(*((_QWORD *)this + 10) + *((unsigned int *)this + 16) + 2 * v6) );
    if ( (_DWORD)v6 )
    {
      v7 = VssAllocString(v4, (unsigned int)v6);
      *v3 = v7;
      CVssIOCTLChannel::Unpack<unsigned short>(this, v4, v7, v6 + 1);
    }
    else
    {
      v23 = 0;
      CVssIOCTLChannel::Unpack<unsigned short>(this, v4, &v23, 1u);
    }
  }
  catch ( long v11 )
  {
    CVssFunctionTracer::HandleHresultException(
      v24,
      v11,
      L"base\\stor\\vss\\inc\\ichannel.hxx",
      L"INCICHLH",
      L"CVssIOCTLChannel::UnpackZeroString",
      0x3F7u,
      *((_DWORD *)v24 + 9));
    v4 = v24;
    v3 = v25;
  }
  catch ( _com_error *v21 )
  {
    CVssFunctionTracer::HandleComException(
      v24,
      v21,
      L"base\\stor\\vss\\inc\\ichannel.hxx",
      L"INCICHLH",
      L"CVssIOCTLChannel::UnpackZeroString",
      0x3F7u,
      *((_DWORD *)v24 + 9));
  }
  catch ( std::bad_alloc )
  {
    CVssFunctionTracer::HandleStdBadAllocException(
      v24,
      L"base\\stor\\vss\\inc\\ichannel.hxx",
      L"INCICHLH",
      L"CVssIOCTLChannel::UnpackZeroString",
      0x3F7u,
      *((_DWORD *)v24 + 9));
    v4 = v24;
    v3 = v25;
  }
  catch ( const std::exception *v22 )
  {
    CVssFunctionTracer::HandleStdGenericException(
      v24,
      v22,
      L"base\\stor\\vss\\inc\\ichannel.hxx",
      L"INCICHLH",
      L"CVssIOCTLChannel::UnpackZeroString",
      0x3F7u,
      *((_DWORD *)v24 + 9));
  }
  result = (const unsigned __int16 *)*v26;
  v9 = v12;
  if ( *v12 < 0 )
  {
    CoTaskMemFree(*v26);
    *v3 = 0;
    v10 = *v9;
    v13 = L"base\\stor\\vss\\inc\\ichannel.hxx";
    v14 = L"CVssIOCTLChannel::UnpackZeroString";
    v15 = L"INCICHLH";
    v16 = 1019;
    v17 = 10;
    v18 = 255;
    v20 = 0x1000000;
    memset_0(v19, 0, sizeof(v19));
    CVssFunctionTracer::Throw(v4, &v13, v10, L"Exception re-thrown 0x%08lx", v10);
  }
  return result;
}

```

## disassembly

```asm
0x180016ff0  mov     [rsp+arg_10], r8
0x180016ff5  mov     [rsp+arg_8], rdx
0x180016ffa  push    rbx
0x180016ffb  push    rsi
0x180016ffc  push    rdi
0x180016ffd  push    r14
0x180016fff  push    r15
0x180017001  sub     rsp, 110h
0x180017008  mov     rbx, r8
0x18001700b  mov     rsi, rdx
0x18001700e  mov     r15, rcx
0x180017011  mov     [rsp+138h+arg_18], rbx
0x180017019  mov     rcx, [r8]; pv
0x18001701c  call    cs:__imp_CoTaskMemFree
0x180017022  xor     edi, edi
0x180017024  mov     [rbx], rdi
0x180017027  lea     r14, [rsi+8]
0x18001702b  mov     [rsp+138h+var_F0], r14
0x180017030  mov     [r14], edi
0x180017033  cmp     [r15+50h], rdi
0x180017037  jnz     short loc_1800170B2
0x180017039  mov     [r15+2Ch], edi
0x18001703d  mov     [r15+40h], edi
0x180017041  lea     rax, aBaseStorVssInc_4; "base\\stor\\vss\\inc\\ichannel.hxx"
0x180017048  mov     [rsp+138h+var_E8], rax
0x18001704d  lea     rax, aCvssioctlchann_3; "CVssIOCTLChannel::UnpackZeroString"
0x180017054  mov     [rsp+138h+var_E0], rax
0x180017059  lea     rax, aIncichlh; "INCICHLH"
0x180017060  mov     [rsp+138h+var_D8], rax
0x180017065  mov     [rsp+138h+var_D0], 3DDh
0x18001706d  mov     [rsp+138h+var_CC], 0Ah
0x180017075  mov     [rsp+138h+var_C8], 0FFh
0x18001707d  mov     [rsp+138h+var_48], 1000000h
0x180017088  xor     edx, edx; Val
0x18001708a  lea     r8d, [rdi+78h]; Size
0x18001708e  lea     rcx, [rsp+138h+var_C0]; void *
0x180017093  call    memset_0
0x180017098  lea     r9, aReadingFromNul; "Reading from NULL buffer"
0x18001709f  mov     r8d, 8000FFFFh
0x1800170a5  lea     rdx, [rsp+138h+var_E8]
0x1800170aa  mov     rcx, rsi
0x1800170ad  call    ?TranslateGenericError@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JPEBGZZ; CVssFunctionTracer::TranslateGenericError(CVssDebugInfo,long,ushort const *,...)
0x1800170b2  mov     eax, [r15+40h]
0x1800170b6  add     rax, [r15+50h]
0x1800170ba  or      r14, 0FFFFFFFFFFFFFFFFh
0x1800170be  inc     r14
0x1800170c1  cmp     [rax+r14*2], di
0x1800170c6  jnz     short loc_1800170BE
0x1800170c8  test    r14d, r14d
0x1800170cb  jz      short loc_1800170EF
0x1800170cd  mov     edx, r14d; unsigned __int64
0x1800170d0  mov     rcx, rsi; struct CVssFunctionTracer *
0x1800170d3  call    ?VssAllocString@@YAPEAGAEAVCVssFunctionTracer@@_K@Z; VssAllocString(CVssFunctionTracer &,unsigned __int64)
0x1800170d8  mov     [rbx], rax
0x1800170db  lea     r9d, [r14+1]
0x1800170df  mov     r8, rax; void *
0x1800170e2  mov     rdx, rsi; struct CVssFunctionTracer *
0x1800170e5  mov     rcx, r15; this
0x1800170e8  call    ??$Unpack@G@CVssIOCTLChannel@@QEAAXAEAVCVssFunctionTracer@@PEAGK_N@Z; CVssIOCTLChannel::Unpack<ushort>(CVssFunctionTracer &,ushort *,ulong,bool)
0x1800170ed  jmp     short loc_180017111
0x1800170ef  mov     [rsp+138h+arg_0], di
0x1800170f7  mov     r9d, 1
0x1800170fd  lea     r8, [rsp+138h+arg_0]; void *
0x180017105  mov     rdx, rsi; struct CVssFunctionTracer *
0x180017108  mov     rcx, r15; this
0x18001710b  call    ??$Unpack@G@CVssIOCTLChannel@@QEAAXAEAVCVssFunctionTracer@@PEAGK_N@Z; CVssIOCTLChannel::Unpack<ushort>(CVssFunctionTracer &,ushort *,ulong,bool)
0x180017110  nop
0x180017111  jmp     short loc_18001712B
0x180017113  jmp     short loc_180017119
0x180017115  jmp     short loc_180017119
0x180017117  jmp     short $+2
0x180017119  mov     rsi, [rsp+138h+arg_8]
0x180017121  mov     rbx, [rsp+138h+arg_10]
0x180017129  xor     edi, edi
0x18001712b  mov     rax, [rsp+138h+arg_18]
0x180017133  mov     rax, [rax]
0x180017136  mov     r14, [rsp+138h+var_F0]
0x18001713b  cmp     [r14], edi
0x18001713e  jge     loc_1800171C6
0x180017144  mov     rcx, rax; pv
0x180017147  call    cs:__imp_CoTaskMemFree
0x18001714d  mov     [rbx], rdi
0x180017150  mov     ebx, [r14]
0x180017153  lea     rax, aBaseStorVssInc_4; "base\\stor\\vss\\inc\\ichannel.hxx"
0x18001715a  mov     [rsp+138h+var_E8], rax
0x18001715f  lea     rax, aCvssioctlchann_3; "CVssIOCTLChannel::UnpackZeroString"
0x180017166  mov     [rsp+138h+var_E0], rax
0x18001716b  lea     rax, aIncichlh; "INCICHLH"
0x180017172  mov     [rsp+138h+var_D8], rax
0x180017177  mov     [rsp+138h+var_D0], 3FBh
0x18001717f  mov     [rsp+138h+var_CC], 0Ah
0x180017187  mov     [rsp+138h+var_C8], 0FFh
0x18001718f  mov     [rsp+138h+var_48], 1000000h
0x18001719a  xor     edx, edx; Val
0x18001719c  lea     r8d, [rdx+78h]; Size
0x1800171a0  lea     rcx, [rsp+138h+var_C0]; void *
0x1800171a5  call    memset_0
0x1800171aa  mov     [rsp+138h+var_118], ebx
0x1800171ae  lea     r9, aExceptionReThr; "Exception re-thrown 0x%08lx"
0x1800171b5  mov     r8d, ebx
0x1800171b8  lea     rdx, [rsp+138h+var_E8]
0x1800171bd  mov     rcx, rsi
0x1800171c0  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
0x1800171c6  add     rsp, 110h
0x1800171cd  pop     r15
0x1800171cf  pop     r14
0x1800171d1  pop     rdi
0x1800171d2  pop     rsi
0x1800171d3  pop     rbx
0x1800171d4  retn
```
