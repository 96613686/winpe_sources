# SAL2::CSALFileIoMgr::AsyncIo::IssueIo(void)

- ea: `0x180088f60`
- end: `0x180089262`
- name: `?IssueIo@AsyncIo@CSALFileIoMgr@SAL2@@QEAAXXZ`
- size: `770`
- prototype: `void __fastcall(SAL2::CSALFileIoMgr::AsyncIo *__hidden this)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800892b0`
- `0x180089cc8`

## callees

- `0x1800017ec`
- `0x180001c00`
- `0x180062710`
- `0x1800627f0`
- `0x180087acc`
- `0x18008848c`
- `0x180088f60`
- `0x180089ffc`
- `0x1800b6010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800891c8`
- `KERNEL32!GetLastError` at `0x1800891c8`
- `KERNEL32!ReadFileScatter` at `0x18008916b`
- `KERNEL32!ReadFileScatter` at `0x18008916b`
- `KERNEL32!WriteFileGather` at `0x180089151`
- `KERNEL32!WriteFileGather` at `0x180089151`
- `KERNEL32!ReadFile` at `0x18008912d`
- `KERNEL32!ReadFile` at `0x18008912d`
- `KERNEL32!WriteFile` at `0x180089112`
- `KERNEL32!WriteFile` at `0x180089112`

## pseudocode

```c
void __fastcall SAL2::CSALFileIoMgr::AsyncIo::IssueIo(SAL2::CSALFileIoMgr::AsyncIo *this)
{
  void *v2; // r15
  __int64 v3; // r13
  __int64 v4; // r12
  FILE_SEGMENT_ELEMENT *__attribute__((__org_arrdim(0,0))) *v5; // r14
  __int64 v6; // rcx
  __int64 v7; // rdi
  FILE_SEGMENT_ELEMENT *v8; // rax
  ULONGLONG *v9; // r8
  signed int v10; // edi
  __int64 **v11; // rsi
  __int64 i; // rax
  int v13; // r9d
  ULONGLONG v14; // rdx
  __int64 v15; // rcx
  BOOL v16; // edi
  int v17; // ecx
  int v18; // ecx
  BOOL FileScatter; // eax
  int v20; // ecx
  bool v21; // zf
  __int64 v22; // xmm1_8
  __int64 *v23; // rcx
  __int64 v24; // rax
  signed int LastError; // eax
  __int64 v26; // xmm1_8
  GUID v27; // [rsp+30h] [rbp-78h] BYREF
  __int128 v28; // [rsp+40h] [rbp-68h] BYREF
  __int64 v29; // [rsp+50h] [rbp-58h]

  v2 = *(void **)(*((_QWORD *)this + 2) + 304LL);
  v3 = *(_QWORD *)(*((_QWORD *)this + 6) + 16LL);
  v4 = *(_QWORD *)(*(_QWORD *)(v3 + 96) + 16LL);
  (*(void (__fastcall **)(SAL2::CSALFileIoMgr::AsyncIo *))(*(_QWORD *)this + 8LL))(this);
  (*(void (__fastcall **)(SAL2::CSALFileIoMgr::AsyncIo *))(*(_QWORD *)this + 8LL))(this);
  v5 = (FILE_SEGMENT_ELEMENT *__attribute__((__org_arrdim(0,0))) *)((char *)this + 72);
  *((_DWORD *)this + 32) = *((_DWORD *)this + 6);
  *((_QWORD *)this + 17) = *((_QWORD *)this + 4);
  *((_DWORD *)this + 36) = *((_DWORD *)this + 10);
  if ( v4 )
  {
    if ( *v5 )
      SBEBasicTracers::EtwTraceAssert(
        (struct CEhEventTracer *)(*((_QWORD *)this + 2) + 96LL),
        "multimedia\\dshow\\filters\\sbe\\sal\\salfileio.cpp",
        0x430u);
    v6 = *((_QWORD *)this + 2);
    if ( *((_DWORD *)this + 10) % *(_DWORD *)(v6 + 300) )
      SBEBasicTracers::EtwTraceAssert(
        (struct CEhEventTracer *)(v6 + 96),
        "multimedia\\dshow\\filters\\sbe\\sal\\salfileio.cpp",
        0x431u);
    v7 = *(unsigned int *)(*((_QWORD *)this + 2) + 300LL);
    v8 = (FILE_SEGMENT_ELEMENT *)operator new[](saturated_mul(*((_DWORD *)this + 10) / (unsigned int)v7 + 1, 8u));
    *v5 = v8;
    v9 = (ULONGLONG *)v8;
    if ( !v8 )
    {
      v10 = -2147024882;
      SBEBasicTracers::EtwTraceError(
        (struct CEhEventTracer *)(*((_QWORD *)this + 2) + 96LL),
        "multimedia\\dshow\\filters\\sbe\\sal\\salfileio.cpp",
        0x438u,
        0x8007000E);
      v11 = (__int64 **)((char *)this + 112);
LABEL_34:
      v26 = *((_QWORD *)this + 18);
      v28 = *((_OWORD *)this + 8);
      v29 = v26;
      CEhSpanTracer::InstanceEx::trace_end<SbeSal_IoComplete>(v11, &v28);
      SAL2::CSALFileIoMgr::AbortRequests((char *)this + 48, (unsigned int)v10);
      (*(void (__fastcall **)(SAL2::CSALFileIoMgr::AsyncIo *))(*(_QWORD *)this + 16LL))(this);
      goto LABEL_35;
    }
    for ( i = *((_QWORD *)this + 6); ; i = *(_QWORD *)(v15 + 96) )
    {
      v15 = *(_QWORD *)(i + 16);
      if ( !v15 )
        break;
      v13 = *(_DWORD *)(v15 + 48);
      v14 = *(_QWORD *)(v15 + 56);
      ++*((_DWORD *)this + 33);
      for ( ; v13; v13 -= v7 )
      {
        *v9++ = v14;
        v14 += v7;
      }
    }
    *v9 = 0;
  }
  *((_DWORD *)this + 24) = *((_DWORD *)this + 8);
  v11 = (__int64 **)((char *)this + 112);
  v16 = 0;
  *((_DWORD *)this + 25) = HIDWORD(*((_QWORD *)this + 4));
  CEhSpanTracer::InstanceEx::trace_begin((SAL2::CSALFileIoMgr::AsyncIo *)((char *)this + 112));
  v17 = *((_DWORD *)this + 6);
  if ( v4 )
  {
    v20 = v17 - 1;
    if ( v20 )
    {
      if ( v20 != 1 )
        goto LABEL_24;
      FileScatter = WriteFileGather(v2, *v5, *((_DWORD *)this + 10), 0, (LPOVERLAPPED)((char *)this + 80));
    }
    else
    {
      FileScatter = ReadFileScatter(v2, *v5, *((_DWORD *)this + 10), 0, (LPOVERLAPPED)((char *)this + 80));
    }
  }
  else
  {
    v18 = v17 - 1;
    if ( v18 )
    {
      if ( v18 != 1 )
        goto LABEL_24;
      FileScatter = WriteFile(v2, *(LPCVOID *)(v3 + 56), *((_DWORD *)this + 10), 0, (LPOVERLAPPED)((char *)this + 80));
    }
    else
    {
      FileScatter = ReadFile(v2, *(LPVOID *)(v3 + 56), *((_DWORD *)this + 10), 0, (LPOVERLAPPED)((char *)this + 80));
    }
  }
  v16 = FileScatter;
LABEL_24:
  v21 = *((_DWORD *)this + 30) == 0;
  v22 = *((_QWORD *)this + 18);
  v28 = *((_OWORD *)this + 8);
  v29 = v22;
  if ( !v21 )
  {
    v23 = *v11;
    v24 = **v11;
    v27 = GUID_6fcf792f_1f85_4a41_b1e6_cba95bb402ee;
    (*(void (__fastcall **)(__int64 *, GUID *, char *, __int128 *, int))(v24 + 40))(
      v23,
      &v27,
      (char *)this + 112,
      &v28,
      24);
  }
  if ( v16 )
  {
    v10 = 0;
  }
  else
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      v10 = (unsigned __int16)LastError | 0x80070000;
    else
      v10 = LastError;
    *((_DWORD *)this + 37) = v10;
    if ( LastError == 997 )
      goto LABEL_35;
  }
  if ( v10 < 0 )
    goto LABEL_34;
LABEL_35:
  (*(void (__fastcall **)(SAL2::CSALFileIoMgr::AsyncIo *))(*(_QWORD *)this + 16LL))(this);
}

```

## disassembly

```asm
0x180088f60  push    rbx
0x180088f62  push    rbp
0x180088f63  push    rsi
0x180088f64  push    rdi
0x180088f65  push    r12
0x180088f67  push    r13
0x180088f69  push    r14
0x180088f6b  push    r15
0x180088f6d  sub     rsp, 68h
0x180088f71  mov     rax, cs:__security_cookie
0x180088f78  xor     rax, rsp
0x180088f7b  mov     [rsp+0A8h+var_50], rax
0x180088f80  mov     rax, [rcx+10h]
0x180088f84  mov     rbx, rcx
0x180088f87  mov     r15, [rax+130h]
0x180088f8e  mov     rax, [rcx+30h]
0x180088f92  mov     r13, [rax+10h]
0x180088f96  mov     rax, [r13+60h]
0x180088f9a  mov     r12, [rax+10h]
0x180088f9e  mov     rax, [rcx]
0x180088fa1  mov     rax, [rax+8]
0x180088fa5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180088faa  mov     rax, [rbx]
0x180088fad  mov     rcx, rbx
0x180088fb0  mov     rax, [rax+8]
0x180088fb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180088fb9  mov     eax, [rbx+18h]
0x180088fbc  lea     r14, [rbx+48h]
0x180088fc0  mov     [rbx+80h], eax
0x180088fc6  mov     rax, [rbx+20h]
0x180088fca  mov     [rbx+88h], rax
0x180088fd1  mov     eax, [rbx+28h]
0x180088fd4  mov     [rbx+90h], eax
0x180088fda  test    r12, r12
0x180088fdd  jz      loc_1800890CA
0x180088fe3  cmp     qword ptr [r14], 0
0x180088fe7  lea     rbp, aMultimediaDsho_11; "multimedia\\dshow\\filters\\sbe\\sal\\s"...
0x180088fee  jz      short loc_180089006
0x180088ff0  mov     rcx, [rbx+10h]
0x180088ff4  mov     r8d, 430h; unsigned int
0x180088ffa  add     rcx, 60h ; '`'; struct CEhEventTracer *
0x180088ffe  mov     rdx, rbp; char *
0x180089001  call    ?EtwTraceAssert@SBEBasicTracers@@SAXAEAVCEhEventTracer@@PEBDK@Z; SBEBasicTracers::EtwTraceAssert(CEhEventTracer &,char const *,ulong)
0x180089006  mov     rcx, [rbx+10h]
0x18008900a  xor     edx, edx
0x18008900c  mov     eax, [rbx+28h]
0x18008900f  div     dword ptr [rcx+12Ch]
0x180089015  test    edx, edx
0x180089017  jz      short loc_18008902B
0x180089019  add     rcx, 60h ; '`'; struct CEhEventTracer *
0x18008901d  mov     r8d, 431h; unsigned int
0x180089023  mov     rdx, rbp; char *
0x180089026  call    ?EtwTraceAssert@SBEBasicTracers@@SAXAEAVCEhEventTracer@@PEBDK@Z; SBEBasicTracers::EtwTraceAssert(CEhEventTracer &,char const *,ulong)
0x18008902b  mov     rax, [rbx+10h]
0x18008902f  xor     edx, edx
0x180089031  mov     edi, [rax+12Ch]
0x180089037  mov     eax, [rbx+28h]
0x18008903a  div     edi
0x18008903c  lea     ecx, [rax+1]
0x18008903f  mov     eax, 8
0x180089044  mul     rcx
0x180089047  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18008904e  cmovb   rax, rcx
0x180089052  mov     rcx, rax; unsigned __int64
0x180089055  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18008905a  mov     [r14], rax
0x18008905d  mov     r8, rax
0x180089060  test    rax, rax
0x180089063  jnz     short loc_18008908F
0x180089065  mov     rcx, [rbx+10h]
0x180089069  mov     r9d, 8007000Eh; unsigned int
0x18008906f  add     rcx, 60h ; '`'; struct CEhEventTracer *
0x180089073  mov     r8d, 438h; unsigned int
0x180089079  mov     rdx, rbp; char *
0x18008907c  mov     edi, 8007000Eh
0x180089081  call    ?EtwTraceError@SBEBasicTracers@@SAXAEAVCEhEventTracer@@PEBDKK@Z; SBEBasicTracers::EtwTraceError(CEhEventTracer &,char const *,ulong,ulong)
0x180089086  lea     rsi, [rbx+70h]
0x18008908a  jmp     loc_1800891F4
0x18008908f  mov     rax, [rbx+30h]
0x180089093  jmp     short loc_1800890BE
0x180089095  mov     r9d, [rcx+30h]
0x180089099  mov     rdx, [rcx+38h]
0x18008909d  inc     dword ptr [rbx+84h]
0x1800890a3  test    r9d, r9d
0x1800890a6  jz      short loc_1800890BA
0x1800890a8  mov     rax, rdi
0x1800890ab  mov     [r8], rdx
0x1800890ae  add     r8, 8
0x1800890b2  add     rdx, rax
0x1800890b5  sub     r9d, edi
0x1800890b8  jnz     short loc_1800890AB
0x1800890ba  mov     rax, [rcx+60h]
0x1800890be  mov     rcx, [rax+10h]
0x1800890c2  test    rcx, rcx
0x1800890c5  jnz     short loc_180089095
0x1800890c7  mov     [r8], rcx
0x1800890ca  mov     eax, [rbx+20h]
0x1800890cd  lea     rbp, [rbx+50h]
0x1800890d1  mov     [rbp+10h], eax
0x1800890d4  lea     rsi, [rbx+70h]
0x1800890d8  mov     rax, [rbx+20h]
0x1800890dc  mov     rcx, rsi; this
0x1800890df  shr     rax, 20h
0x1800890e3  xor     edi, edi
0x1800890e5  mov     [rbx+64h], eax
0x1800890e8  call    ?trace_begin@InstanceEx@CEhSpanTracer@@QEAAJXZ; CEhSpanTracer::InstanceEx::trace_begin(void)
0x1800890ed  mov     ecx, [rbx+18h]
0x1800890f0  test    r12, r12
0x1800890f3  jnz     short loc_180089135
0x1800890f5  sub     ecx, 1
0x1800890f8  jz      short loc_18008911A
0x1800890fa  cmp     ecx, 1
0x1800890fd  jnz     short loc_180089173
0x1800890ff  mov     r8d, [rbx+28h]; nNumberOfBytesToWrite
0x180089103  xor     r9d, r9d; lpNumberOfBytesWritten
0x180089106  mov     rdx, [r13+38h]; lpBuffer
0x18008910a  mov     rcx, r15; hFile
0x18008910d  mov     [rsp+0A8h+lpOverlapped], rbp; lpOverlapped
0x180089112  call    cs:__imp_WriteFile
0x180089118  jmp     short loc_180089171
0x18008911a  mov     r8d, [rbx+28h]; nNumberOfBytesToRead
0x18008911e  xor     r9d, r9d; lpNumberOfBytesRead
0x180089121  mov     rdx, [r13+38h]; lpBuffer
0x180089125  mov     rcx, r15; hFile
0x180089128  mov     [rsp+0A8h+lpOverlapped], rbp; lpOverlapped
0x18008912d  call    cs:__imp_ReadFile
0x180089133  jmp     short loc_180089171
0x180089135  sub     ecx, 1
0x180089138  jz      short loc_180089159
0x18008913a  cmp     ecx, 1
0x18008913d  jnz     short loc_180089173
0x18008913f  mov     r8d, [rbx+28h]; nNumberOfBytesToWrite
0x180089143  xor     r9d, r9d; lpReserved
0x180089146  mov     rdx, [r14]; aSegmentArray
0x180089149  mov     rcx, r15; hFile
0x18008914c  mov     [rsp+0A8h+lpOverlapped], rbp; lpOverlapped
0x180089151  call    cs:__imp_WriteFileGather
0x180089157  jmp     short loc_180089171
0x180089159  mov     r8d, [rbx+28h]; nNumberOfBytesToRead
0x18008915d  xor     r9d, r9d; lpReserved
0x180089160  mov     rdx, [r14]; aSegmentArray
0x180089163  mov     rcx, r15; hFile
0x180089166  mov     [rsp+0A8h+lpOverlapped], rbp; lpOverlapped
0x18008916b  call    cs:__imp_ReadFileScatter
0x180089171  mov     edi, eax
0x180089173  cmp     dword ptr [rsi+8], 0
0x180089177  movups  xmm0, xmmword ptr [rbx+80h]
0x18008917e  movsd   xmm1, qword ptr [rbx+90h]
0x180089186  movups  [rsp+0A8h+var_68], xmm0
0x18008918b  movsd   [rsp+0A8h+var_58], xmm1
0x180089191  jz      short loc_1800891C4
0x180089193  mov     rcx, [rsi]
0x180089196  lea     r9, [rsp+0A8h+var_68]
0x18008919b  movups  xmm0, xmmword ptr cs:_GUID_6fcf792f_1f85_4a41_b1e6_cba95bb402ee.Data1
0x1800891a2  mov     r8, rsi
0x1800891a5  mov     dword ptr [rsp+0A8h+lpOverlapped], 18h
0x1800891ad  lea     rdx, [rsp+0A8h+var_78]
0x1800891b2  mov     rax, [rcx]
0x1800891b5  movdqu  [rsp+0A8h+var_78], xmm0
0x1800891bb  mov     rax, [rax+28h]
0x1800891bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800891c4  test    edi, edi
0x1800891c6  jnz     short loc_1800891EE
0x1800891c8  call    cs:__imp_GetLastError
0x1800891ce  test    eax, eax
0x1800891d0  jg      short loc_1800891D6
0x1800891d2  mov     edi, eax
0x1800891d4  jmp     short loc_1800891DF
0x1800891d6  movzx   edi, ax
0x1800891d9  or      edi, 80070000h
0x1800891df  mov     [rbx+94h], edi
0x1800891e5  cmp     eax, 3E5h
0x1800891ea  jz      short loc_180089235
0x1800891ec  jmp     short loc_1800891F0
0x1800891ee  xor     edi, edi
0x1800891f0  test    edi, edi
0x1800891f2  jns     short loc_180089235
0x1800891f4  movups  xmm0, xmmword ptr [rbx+80h]
0x1800891fb  lea     rdx, [rsp+0A8h+var_68]
0x180089200  mov     rcx, rsi
0x180089203  movsd   xmm1, qword ptr [rbx+90h]
0x18008920b  movups  [rsp+0A8h+var_68], xmm0
0x180089210  movsd   [rsp+0A8h+var_58], xmm1
0x180089216  call    ??$trace_end@USbeSal_IoComplete@@@InstanceEx@CEhSpanTracer@@QEAAJAEBUSbeSal_IoComplete@@@Z; CEhSpanTracer::InstanceEx::trace_end<SbeSal_IoComplete>(SbeSal_IoComplete const &)
0x18008921b  mov     edx, edi
0x18008921d  lea     rcx, [rbx+30h]
0x180089221  call    ?AbortRequests@CSALFileIoMgr@SAL2@@CAXAEAV?$TList@PEAVIoRequest@CSALFileIoMgr@SAL2@@@@J@Z; SAL2::CSALFileIoMgr::AbortRequests(TList<SAL2::CSALFileIoMgr::IoRequest *> &,long)
0x180089226  mov     rax, [rbx]
0x180089229  mov     rcx, rbx
0x18008922c  mov     rax, [rax+10h]
0x180089230  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089235  mov     rax, [rbx]
0x180089238  mov     rcx, rbx
0x18008923b  mov     rax, [rax+10h]
0x18008923f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089244  mov     rcx, [rsp+0A8h+var_50]
0x180089249  xor     rcx, rsp; StackCookie
0x18008924c  call    __security_check_cookie
0x180089251  add     rsp, 68h
0x180089255  pop     r15
0x180089257  pop     r14
0x180089259  pop     r13
0x18008925b  pop     r12
0x18008925d  pop     rdi
0x18008925e  pop     rsi
0x18008925f  pop     rbp
0x180089260  pop     rbx
0x180089261  retn
```
