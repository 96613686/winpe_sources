# RtlWriteDataIntoSmartLBlobWritingContext

- ea: `0x1800377a0`
- end: `0x180037aad`
- name: `RtlWriteDataIntoSmartLBlobWritingContext`
- size: `781`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18004d310`

## callees

- `0x1800370f4`
- `0x1800371a4`
- `0x1800376bc`
- `0x1800377a0`
- `0x180037ab4`
- `0x1800607b0`
- `0x180060e70`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1800379c6`
- `msvcrt!memcpy_s` at `0x180037a26`
- `msvcrt!memcpy_s` at `0x1800379c6`
- `msvcrt!memcpy_s` at `0x180037a26`

## string_xrefs

- `0x1800377e4`: `RtlWriteDataIntoSmartLBlobWritingContext`
- `0x18003782e`: `RtlWriteDataIntoSmartLBlobWritingContext`
- `0x180037859`: `RtlWriteDataIntoSmartLBlobWritingContext`
- `0x1800378d3`: `RtlWriteDataIntoSmartLBlobWritingContext`
- `0x180037935`: `RtlWriteDataIntoSmartLBlobWritingContext`
- `0x180037a83`: `RtlWriteDataIntoSmartLBlobWritingContext`
- `0x180037a94`: `BUCL::Rtl::Add<SIZE_T>(DataLength, OldLength, TempSize)`

## pseudocode

```c
__int64 __fastcall RtlWriteDataIntoSmartLBlobWritingContext(__int64 a1, char **a2)
{
  const char *v4; // rax
  rsize_t *v6; // rcx
  char *v7; // rsi
  char *v8; // rdi
  rsize_t v9; // r14
  unsigned __int64 v10; // rcx
  unsigned __int64 v11; // rsi
  unsigned __int64 v12; // r8
  int v13; // edi
  char *v14; // rax
  int v15; // eax
  char *v16; // r8
  char *v17; // rcx
  char *v18; // rcx
  char *v19; // rax
  char *v20; // rdx
  char *v21; // rdi
  const char *v22; // [rsp+20h] [rbp-50h] BYREF
  const char *v23; // [rsp+28h] [rbp-48h]
  int v24; // [rsp+30h] [rbp-40h]
  const char *v25; // [rsp+38h] [rbp-38h]
  const char *v26; // [rsp+40h] [rbp-30h] BYREF
  const char *v27; // [rsp+48h] [rbp-28h]
  int v28; // [rsp+50h] [rbp-20h]
  const char *v29; // [rsp+58h] [rbp-18h]
  unsigned __int64 v30; // [rsp+60h] [rbp-10h] BYREF

  if ( !a1 )
  {
    v24 = 1770;
    v22 = "onecore\\base\\lstring\\lblob.cpp";
    v23 = "RtlWriteDataIntoSmartLBlobWritingContext";
    v4 = "Not-null check failed: Data";
LABEL_3:
    v25 = v4;
    RtlReportErrorOrigination(&v22, a2, 3221225485LL);
    return 3221225485LL;
  }
  if ( !(unsigned __int8)RtlIsLBlobValid() )
  {
    v24 = 1771;
    v22 = "onecore\\base\\lstring\\lblob.cpp";
    v23 = "RtlWriteDataIntoSmartLBlobWritingContext";
    v4 = "::RtlIsLBlobValid(Data)";
    goto LABEL_3;
  }
  if ( !a2 )
  {
    v24 = 1772;
    v22 = "onecore\\base\\lstring\\lblob.cpp";
    v23 = "RtlWriteDataIntoSmartLBlobWritingContext";
    v4 = "Not-null check failed: Context";
    goto LABEL_3;
  }
  v7 = a2[1];
  v8 = *a2;
  v9 = *v6;
  if ( *v6 > v7 - *a2 )
  {
    if ( !a2[6] )
      return 3221225507LL;
    v10 = *(_QWORD *)a2[4];
    v11 = v10 + v9;
    if ( v10 + v9 < v9 || v11 < v10 )
    {
      v28 = 1790;
      v26 = "onecore\\base\\lstring\\lblob.cpp";
      v27 = "RtlWriteDataIntoSmartLBlobWritingContext";
      v29 = "BUCL::Rtl::Add<SIZE_T>(DataLength, OldLength, TempSize)";
      RtlReportErrorOrigination(&v26, a2, 3221225621LL);
      return (unsigned int)-1073741675;
    }
    v12 = (unsigned __int64)a2[3];
    if ( v11 > v12 )
    {
      v29 = 0;
      v26 = "onecore\\base\\lstring\\lblob.cpp";
      v28 = 1793;
      v27 = "RtlWriteDataIntoSmartLBlobWritingContext";
      RtlReportErrorOrigination(&v26, a2, 3221226539LL);
      return (unsigned int)-1073740757;
    }
    v14 = a2[8];
    if ( v14 )
      v15 = ((__int64 (__fastcall *)(char **, unsigned __int64, unsigned __int64 *))v14)(a2, v11, &v30);
    else
      v15 = RtlpSmartLBlobWritingContextResizePolicy(v10, v11, v12, &v30);
    v13 = v15;
    if ( v15 < 0 )
      return (unsigned int)v13;
    if ( v30 < v11 )
    {
      v29 = 0;
      v26 = "onecore\\base\\lstring\\lblob.cpp";
      v28 = 1809;
      v27 = "RtlWriteDataIntoSmartLBlobWritingContext";
      RtlReportErrorOrigination(&v26, v30, 3221225507LL);
      return (unsigned int)-1073741789;
    }
    v16 = a2[4];
    v17 = a2[6];
    if ( v16 == v17 )
    {
      if ( *((_QWORD *)v16 + 1) < v30 )
      {
        v13 = RtlReallocateLBlob(v17, v30, a2[6]);
        if ( v13 < 0 )
          return (unsigned int)v13;
      }
    }
    else if ( v16 == a2[5] )
    {
      if ( *((_QWORD *)v17 + 1) < v30 )
      {
        v13 = RtlReallocateLBlob(v17, v30, a2[6]);
        if ( v13 < 0 )
          return (unsigned int)v13;
        v16 = a2[4];
        v17 = a2[6];
      }
      memcpy_s(*((void *const *)v17 + 2), *((_QWORD *)v17 + 1), *((const void *const *)v16 + 2), *(_QWORD *)v16);
      *(_QWORD *)a2[6] = *(_QWORD *)a2[4];
      v18 = a2[7];
      v19 = a2[6];
      a2[4] = v19;
      if ( v18 )
        *(_QWORD *)v18 = v19;
    }
    else
    {
      __debugbreak();
    }
    v20 = a2[4];
    v8 = (char *)(*(_QWORD *)v20 + *((_QWORD *)v20 + 2));
    *a2 = v8;
    v7 = (char *)(*((_QWORD *)v20 + 2) + *((_QWORD *)v20 + 1));
    a2[1] = v7;
  }
  if ( v9 )
  {
    memcpy_s(v8, v7 - v8, *(const void *const *)(a1 + 16), v9);
    v21 = &v8[v9];
    *(_QWORD *)a2[4] = &v21[-*((_QWORD *)a2[4] + 2)];
    *a2 = v21;
  }
  return 0;
}

```

## disassembly

```asm
0x1800377a0  mov     [rsp-28h+arg_10], rbx
0x1800377a5  mov     [rsp-28h+arg_18], rsi
0x1800377aa  push    rbp
0x1800377ab  push    rdi
0x1800377ac  push    r13
0x1800377ae  push    r14
0x1800377b0  push    r15
0x1800377b2  mov     rbp, rsp
0x1800377b5  sub     rsp, 70h
0x1800377b9  mov     rax, cs:__security_cookie
0x1800377c0  xor     rax, rsp
0x1800377c3  mov     [rbp+var_8], rax
0x1800377c7  mov     rbx, rdx
0x1800377ca  mov     r15, rcx
0x1800377cd  test    rcx, rcx
0x1800377d0  jnz     short loc_180037813
0x1800377d2  lea     rax, aOnecoreBaseLst_0; "onecore\\base\\lstring\\lblob.cpp"
0x1800377d9  mov     [rbp+var_40], 6EAh
0x1800377e0  mov     [rbp+var_50], rax
0x1800377e4  lea     rax, aRtlwritedatain; "RtlWriteDataIntoSmartLBlobWritingContex"...
0x1800377eb  mov     [rbp+var_48], rax
0x1800377ef  lea     rax, aNotNullCheckFa_4; "Not-null check failed: Data"
0x1800377f6  mov     r8d, 0C000000Dh
0x1800377fc  mov     [rbp+var_38], rax
0x180037800  lea     rcx, [rbp+var_50]
0x180037804  call    RtlReportErrorOrigination
0x180037809  mov     eax, 0C000000Dh
0x18003780e  jmp     loc_180037A48
0x180037813  call    RtlIsLBlobValid
0x180037818  test    al, al
0x18003781a  jnz     short loc_180037842
0x18003781c  lea     rax, aOnecoreBaseLst_0; "onecore\\base\\lstring\\lblob.cpp"
0x180037823  mov     [rbp+var_40], 6EBh
0x18003782a  mov     [rbp+var_50], rax
0x18003782e  lea     rax, aRtlwritedatain; "RtlWriteDataIntoSmartLBlobWritingContex"...
0x180037835  mov     [rbp+var_48], rax
0x180037839  lea     rax, aRtlislblobvali_0; "::RtlIsLBlobValid(Data)"
0x180037840  jmp     short loc_1800377F6
0x180037842  test    rbx, rbx
0x180037845  jnz     short loc_18003786D
0x180037847  lea     rax, aOnecoreBaseLst_0; "onecore\\base\\lstring\\lblob.cpp"
0x18003784e  mov     [rbp+var_40], 6ECh
0x180037855  mov     [rbp+var_50], rax
0x180037859  lea     rax, aRtlwritedatain; "RtlWriteDataIntoSmartLBlobWritingContex"...
0x180037860  mov     [rbp+var_48], rax
0x180037864  lea     rax, aNotNullCheckFa_1; "Not-null check failed: Context"
0x18003786b  jmp     short loc_1800377F6
0x18003786d  mov     rsi, [rdx+8]
0x180037871  mov     rdi, [rdx]
0x180037874  mov     rax, rsi
0x180037877  mov     r14, [rcx]
0x18003787a  sub     rax, rdi
0x18003787d  cmp     r14, rax
0x180037880  jbe     loc_180037A11
0x180037886  cmp     qword ptr [rdx+30h], 0
0x18003788b  jnz     short loc_180037897
0x18003788d  mov     eax, 0C0000023h
0x180037892  jmp     loc_180037A48
0x180037897  mov     rax, [rdx+20h]
0x18003789b  xor     r13d, r13d
0x18003789e  mov     rcx, [rax]; unsigned __int64
0x1800378a1  lea     rsi, [rcx+r14]
0x1800378a5  cmp     rsi, r14
0x1800378a8  jb      loc_180037A6D
0x1800378ae  cmp     rsi, rcx
0x1800378b1  jb      loc_180037A6D
0x1800378b7  mov     r8, [rdx+18h]; unsigned __int64
0x1800378bb  cmp     rsi, r8
0x1800378be  jbe     short loc_1800378FA
0x1800378c0  and     [rbp+var_18], r13
0x1800378c4  lea     rax, aOnecoreBaseLst_0; "onecore\\base\\lstring\\lblob.cpp"
0x1800378cb  mov     [rbp+var_30], rax
0x1800378cf  lea     rcx, [rbp+var_30]
0x1800378d3  lea     rax, aRtlwritedatain; "RtlWriteDataIntoSmartLBlobWritingContex"...
0x1800378da  mov     [rbp+var_20], 701h
0x1800378e1  mov     r8d, 0C000042Bh
0x1800378e7  mov     [rbp+var_28], rax
0x1800378eb  call    RtlReportErrorOrigination
0x1800378f0  mov     edi, 0C000042Bh
0x1800378f5  jmp     loc_180037AA9
0x1800378fa  mov     rax, [rdx+40h]
0x1800378fe  mov     rdx, rsi; unsigned __int64
0x180037901  test    rax, rax
0x180037904  jnz     short loc_18003795C
0x180037906  lea     r9, [rbp+var_10]; unsigned __int64 *
0x18003790a  call    ?RtlpSmartLBlobWritingContextResizePolicy@@YAJ_K00PEA_K@Z; RtlpSmartLBlobWritingContextResizePolicy(unsigned __int64,unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18003790f  mov     edi, eax
0x180037911  test    eax, eax
0x180037913  js      loc_180037AA9
0x180037919  mov     rdx, [rbp+var_10]
0x18003791d  cmp     rdx, rsi
0x180037920  jnb     short loc_18003796B
0x180037922  and     [rbp+var_18], r13
0x180037926  lea     rax, aOnecoreBaseLst_0; "onecore\\base\\lstring\\lblob.cpp"
0x18003792d  mov     [rbp+var_30], rax
0x180037931  lea     rcx, [rbp+var_30]
0x180037935  lea     rax, aRtlwritedatain; "RtlWriteDataIntoSmartLBlobWritingContex"...
0x18003793c  mov     [rbp+var_20], 711h
0x180037943  mov     r8d, 0C0000023h
0x180037949  mov     [rbp+var_28], rax
0x18003794d  call    RtlReportErrorOrigination
0x180037952  mov     edi, 0C0000023h
0x180037957  jmp     loc_180037AA9
0x18003795c  lea     r8, [rbp+var_10]
0x180037960  mov     rcx, rbx
0x180037963  call    cs:__guard_dispatch_icall_fptr
0x180037969  jmp     short loc_18003790F
0x18003796b  mov     r8, [rbx+20h]
0x18003796f  mov     rcx, [rbx+30h]
0x180037973  cmp     r8, rcx
0x180037976  jnz     short loc_180037991
0x180037978  cmp     [r8+8], rdx
0x18003797c  jnb     short loc_1800379F7
0x18003797e  mov     r8, rcx
0x180037981  call    RtlReallocateLBlob
0x180037986  mov     edi, eax
0x180037988  test    eax, eax
0x18003798a  jns     short loc_1800379F7
0x18003798c  jmp     loc_180037AA9
0x180037991  cmp     r8, [rbx+28h]
0x180037995  jnz     short loc_1800379F6
0x180037997  cmp     [rcx+8], rdx
0x18003799b  jnb     short loc_1800379B7
0x18003799d  mov     r8, rcx
0x1800379a0  call    RtlReallocateLBlob
0x1800379a5  mov     edi, eax
0x1800379a7  test    eax, eax
0x1800379a9  js      loc_180037AA9
0x1800379af  mov     r8, [rbx+20h]
0x1800379b3  mov     rcx, [rbx+30h]
0x1800379b7  mov     r9, [r8]; SourceSize
0x1800379ba  mov     rdx, [rcx+8]; DestinationSize
0x1800379be  mov     r8, [r8+10h]; Source
0x1800379c2  mov     rcx, [rcx+10h]; Destination
0x1800379c6  call    cs:__imp_memcpy_s
0x1800379cd  nop     dword ptr [rax+rax+00h]
0x1800379d2  mov     rax, [rbx+20h]
0x1800379d6  mov     rcx, [rbx+30h]
0x1800379da  mov     rax, [rax]
0x1800379dd  mov     [rcx], rax
0x1800379e0  mov     rcx, [rbx+38h]
0x1800379e4  mov     rax, [rbx+30h]
0x1800379e8  mov     [rbx+20h], rax
0x1800379ec  test    rcx, rcx
0x1800379ef  jz      short loc_1800379F7
0x1800379f1  mov     [rcx], rax
0x1800379f4  jmp     short loc_1800379F7
0x1800379f6  int     3; Trap to Debugger
0x1800379f7  mov     rdx, [rbx+20h]
0x1800379fb  mov     rdi, [rdx+10h]
0x1800379ff  add     rdi, [rdx]
0x180037a02  mov     [rbx], rdi
0x180037a05  mov     rsi, [rdx+8]
0x180037a09  add     rsi, [rdx+10h]
0x180037a0d  mov     [rbx+8], rsi
0x180037a11  test    r14, r14
0x180037a14  jz      short loc_180037A46
0x180037a16  mov     r8, [r15+10h]; Source
0x180037a1a  sub     rsi, rdi
0x180037a1d  mov     rdx, rsi; DestinationSize
0x180037a20  mov     r9, r14; SourceSize
0x180037a23  mov     rcx, rdi; Destination
0x180037a26  call    cs:__imp_memcpy_s
0x180037a2d  nop     dword ptr [rax+rax+00h]
0x180037a32  mov     rdx, [rbx+20h]
0x180037a36  add     rdi, r14
0x180037a39  mov     rcx, rdi
0x180037a3c  sub     rcx, [rdx+10h]
0x180037a40  mov     [rdx], rcx
0x180037a43  mov     [rbx], rdi
0x180037a46  xor     eax, eax
0x180037a48  mov     rcx, [rbp+var_8]
0x180037a4c  xor     rcx, rsp; StackCookie
0x180037a4f  call    __security_check_cookie
0x180037a54  lea     r11, [rsp+70h+var_s0]
0x180037a59  mov     rbx, [r11+40h]
0x180037a5d  mov     rsi, [r11+48h]
0x180037a61  mov     rsp, r11
0x180037a64  pop     r15
0x180037a66  pop     r14
0x180037a68  pop     r13
0x180037a6a  pop     rdi
0x180037a6b  pop     rbp
0x180037a6c  retn
0x180037a6d  lea     rax, aOnecoreBaseLst_0; "onecore\\base\\lstring\\lblob.cpp"
0x180037a74  mov     [rbp+var_20], 6FEh
0x180037a7b  mov     [rbp+var_30], rax
0x180037a7f  lea     rcx, [rbp+var_30]
0x180037a83  lea     rax, aRtlwritedatain; "RtlWriteDataIntoSmartLBlobWritingContex"...
0x180037a8a  mov     r8d, 0C0000095h
0x180037a90  mov     [rbp+var_28], rax
0x180037a94  lea     rax, aBuclRtlAddSize_0; "BUCL::Rtl::Add<SIZE_T>(DataLength, OldL"...
0x180037a9b  mov     [rbp+var_18], rax
0x180037a9f  call    RtlReportErrorOrigination
0x180037aa4  mov     edi, 0C0000095h
0x180037aa9  mov     eax, edi
0x180037aab  jmp     short loc_180037A48
```
