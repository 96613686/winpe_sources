# File::WriteCurrentChunk(bool,utl::unique_lock<utl::shared_mutex> &)

- ea: `0x180032dbc`
- end: `0x180033071`
- name: `?WriteCurrentChunk@File@@AEAAK_NAEAV?$unique_lock@Vshared_mutex@utl@@@utl@@@Z`
- size: `693`
- prototype: ``
- caller_count: `6`
- callee_count: `9`
- tags: `file_ops, installer_update`

## callers

- `0x180031cf4`
- `0x180031e60`
- `0x180031f14`
- `0x1800322f0`
- `0x180032704`
- `0x180032a7c`

## callees

- `0x18000a0d0`
- `0x180023548`
- `0x180032dbc`
- `0x1800337cc`
- `0x1800337fc`
- `0x180034fd8`
- `0x180034ffc`
- `0x180035290`
- `0x180035894`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180032fd2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180032fd2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180032fe5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180032fe5`
- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x180032e86`
- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x180032e86`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180033051`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180033051`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x180032fdb`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x180032fdb`

## pseudocode

```c
__int64 __fastcall File::WriteCurrentChunk(__int64 a1, char a2, __int64 a3)
{
  HANDLE *v3; // rbx
  HANDLE v7; // rdx
  unsigned int v8; // eax
  unsigned int v9; // edi
  void *v11; // rcx
  unsigned int v12; // ebp
  unsigned int v13; // r12d
  unsigned int v14; // r15d
  HANDLE v15; // rbx
  unsigned int v16; // r8d
  void *v17; // rdx
  FileView *v18; // rcx
  unsigned int v19; // r9d
  struct _TP_TIMER *v20; // rcx
  _BYTE v21[8]; // [rsp+20h] [rbp-78h] BYREF
  __int64 v22; // [rsp+28h] [rbp-70h]
  __int64 v23; // [rsp+30h] [rbp-68h]
  unsigned int v24; // [rsp+40h] [rbp-58h]
  char v25; // [rsp+49h] [rbp-4Fh]

  v3 = (HANDLE *)(a1 + 672);
  if ( *(_BYTE *)(a1 + 831) )
  {
    v23 = *(_QWORD *)(a1 + 144);
    v24 = 128;
    v22 = -1;
    v25 = 0;
    FileView::SetPointers((FileView *)v21);
    v7 = *v3;
    v22 = 0;
    v8 = FileView::ActualWrite((FileView *)v21, v7, 0, v24);
    v9 = v8;
    if ( v8 )
    {
      if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, &WPP_d3d936efbc913e3641017ad303784371_Traceguids, v8);
      }
      FileView::~FileView((FileView *)v21);
      return v9;
    }
    FlushFileBuffers(*v3);
    *(_BYTE *)(a1 + 831) = 0;
    v11 = *(void **)(a1 + 144);
    *(_QWORD *)(a1 + 144) = 0;
    if ( v11 )
      operator delete(v11, 0x80u);
    FileView::~FileView((FileView *)v21);
  }
  if ( !*(_BYTE *)(a1 + 827) )
  {
    *(_DWORD *)(a1 + 812) = 0;
    return 0;
  }
  if ( !*(_QWORD *)(a1 + 176) )
    return 0;
  WriteFileView::UpdateBothCRCValues((WriteFileView *)(a1 + 152));
  *(_BYTE *)(a1 + 838) = 1;
  if ( a2 )
  {
    if ( *(_BYTE *)(a1 + 829) )
      utl::unique_lock<utl::shared_mutex>::unlock(a3);
    v12 = FileView::ActualWrite((FileView *)(a1 + 160), *v3, 0, *(_DWORD *)(a1 + 192));
    if ( *(_BYTE *)(a1 + 829) )
      utl::unique_lock<utl::shared_mutex>::lock(a3);
    if ( !v12 )
    {
      *(_DWORD *)(a1 + 812) = 0;
      *(_BYTE *)(a1 + 827) = 0;
    }
    goto LABEL_32;
  }
  v13 = *(_DWORD *)(a1 + 812);
  v14 = *(_DWORD *)(*(_QWORD *)(a1 + 160) + 48LL);
  if ( *(_BYTE *)(a1 + 829) )
    utl::unique_lock<utl::shared_mutex>::unlock(a3);
  v15 = *v3;
  v16 = 0;
  v17 = v15;
  v18 = (FileView *)(a1 + 160);
  if ( !v13 )
  {
    v19 = v14;
LABEL_27:
    v12 = FileView::ActualWrite(v18, v17, v16, v19);
    goto LABEL_28;
  }
  v12 = FileView::ActualWrite((FileView *)(a1 + 160), v15, 0, 0x200u);
  if ( !v12 )
  {
    v16 = v13;
    v19 = v14 - v13;
    v17 = v15;
    v18 = (FileView *)(a1 + 160);
    goto LABEL_27;
  }
LABEL_28:
  if ( *(_BYTE *)(a1 + 829) )
    utl::unique_lock<utl::shared_mutex>::lock(a3);
  if ( !v12 )
    *(_DWORD *)(a1 + 812) = v14;
LABEL_32:
  *(_BYTE *)(a1 + 838) = 0;
  AcquireSRWLockExclusive((PSRWLOCK)(a1 + 752));
  WakeAllConditionVariable((PCONDITION_VARIABLE)(a1 + 744));
  ReleaseSRWLockExclusive((PSRWLOCK)(a1 + 752));
  if ( !v12 )
  {
    v20 = *(struct _TP_TIMER **)(a1 + 656);
    if ( v20 && *(_BYTE *)(a1 + 837) )
    {
      *(_BYTE *)(a1 + 837) = 0;
      SetThreadpoolTimer(v20, 0, 0, 0);
    }
    *(_BYTE *)(a1 + 826) = 0;
    return 0;
  }
  if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, &WPP_d3d936efbc913e3641017ad303784371_Traceguids, v12);
  }
  return v12;
}

```

## disassembly

```asm
0x180032dbc  mov     r11, rsp
0x180032dbf  push    rbx
0x180032dc0  push    rbp
0x180032dc1  push    rsi
0x180032dc2  push    rdi
0x180032dc3  push    r12
0x180032dc5  push    r13
0x180032dc7  push    r14
0x180032dc9  push    r15
0x180032dcb  sub     rsp, 58h
0x180032dcf  xor     r13d, r13d
0x180032dd2  lea     rbx, [rcx+2A0h]
0x180032dd9  mov     r14, r8
0x180032ddc  mov     bpl, dl
0x180032ddf  mov     rsi, rcx
0x180032de2  cmp     [rcx+33Fh], r13b
0x180032de9  jz      loc_180032EB8
0x180032def  mov     rax, [rcx+90h]
0x180032df6  mov     r15d, 80h
0x180032dfc  lea     rcx, [r11-78h]; this
0x180032e00  mov     [r11-68h], rax
0x180032e04  mov     [r11-58h], r15d
0x180032e08  mov     qword ptr [r11-70h], 0FFFFFFFFFFFFFFFFh
0x180032e10  mov     [r11-4Fh], r13b
0x180032e14  call    ?SetPointers@FileView@@QEAAXXZ; FileView::SetPointers(void)
0x180032e19  mov     rdx, [rbx]; void *
0x180032e1c  lea     rcx, [rsp+98h+var_78]; this
0x180032e21  mov     r9d, [rsp+98h+var_58]; unsigned int
0x180032e26  xor     r8d, r8d; unsigned int
0x180032e29  mov     [rsp+98h+var_70], r13
0x180032e2e  call    ?ActualWrite@FileView@@AEAAKPEAXKK@Z; FileView::ActualWrite(void *,ulong,ulong)
0x180032e33  mov     edi, eax
0x180032e35  test    eax, eax
0x180032e37  jz      short loc_180032E83
0x180032e39  mov     rcx, cs:WPP_GLOBAL_Control
0x180032e40  lea     rdx, WPP_GLOBAL_Control
0x180032e47  cmp     rcx, rdx
0x180032e4a  jz      short loc_180032E72
0x180032e4c  test    dword ptr [rcx+1Ch], 8000h
0x180032e53  jz      short loc_180032E72
0x180032e55  cmp     byte ptr [rcx+19h], 2
0x180032e59  jb      short loc_180032E72
0x180032e5b  mov     rcx, [rcx+10h]
0x180032e5f  lea     edx, [r13+2Ah]
0x180032e63  mov     r9d, eax
0x180032e66  lea     r8, WPP_d3d936efbc913e3641017ad303784371_Traceguids
0x180032e6d  call    WPP_SF_D
0x180032e72  lea     rcx, [rsp+98h+var_78]; this
0x180032e77  call    ??1FileView@@QEAA@XZ; FileView::~FileView(void)
0x180032e7c  mov     eax, edi
0x180032e7e  jmp     loc_180033060
0x180032e83  mov     rcx, [rbx]; hFile
0x180032e86  call    cs:__imp_FlushFileBuffers
0x180032e8c  mov     [rsi+33Fh], r13b
0x180032e93  mov     rcx, [rsi+90h]; void *
0x180032e9a  mov     [rsi+90h], r13
0x180032ea1  test    rcx, rcx
0x180032ea4  jz      short loc_180032EAE
0x180032ea6  mov     rdx, r15; unsigned __int64
0x180032ea9  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180032eae  lea     rcx, [rsp+98h+var_78]; this
0x180032eb3  call    ??1FileView@@QEAA@XZ; FileView::~FileView(void)
0x180032eb8  cmp     [rsi+33Bh], r13b
0x180032ebf  jnz     short loc_180032ECD
0x180032ec1  mov     [rsi+32Ch], r13d
0x180032ec8  jmp     loc_18003305E
0x180032ecd  lea     rdi, [rsi+98h]
0x180032ed4  cmp     [rdi+18h], r13
0x180032ed8  jz      loc_18003305E
0x180032ede  mov     rcx, rdi; this
0x180032ee1  call    ?UpdateBothCRCValues@WriteFileView@@QEAAXXZ; WriteFileView::UpdateBothCRCValues(void)
0x180032ee6  add     rdi, 8
0x180032eea  mov     byte ptr [rsi+346h], 1
0x180032ef1  test    bpl, bpl
0x180032ef4  jz      short loc_180032F44
0x180032ef6  cmp     [rsi+33Dh], r13b
0x180032efd  jz      short loc_180032F07
0x180032eff  mov     rcx, r14
0x180032f02  call    ?unlock@?$unique_lock@Vshared_mutex@utl@@@utl@@QEAAXXZ; utl::unique_lock<utl::shared_mutex>::unlock(void)
0x180032f07  mov     r9d, [rdi+20h]; unsigned int
0x180032f0b  xor     r8d, r8d; unsigned int
0x180032f0e  mov     rdx, [rbx]; void *
0x180032f11  mov     rcx, rdi; this
0x180032f14  call    ?ActualWrite@FileView@@AEAAKPEAXKK@Z; FileView::ActualWrite(void *,ulong,ulong)
0x180032f19  mov     ebp, eax
0x180032f1b  cmp     [rsi+33Dh], r13b
0x180032f22  jz      short loc_180032F2C
0x180032f24  mov     rcx, r14
0x180032f27  call    ?lock@?$unique_lock@Vshared_mutex@utl@@@utl@@QEAAXXZ; utl::unique_lock<utl::shared_mutex>::lock(void)
0x180032f2c  test    ebp, ebp
0x180032f2e  jnz     loc_180032FC0
0x180032f34  mov     [rsi+32Ch], r13d
0x180032f3b  mov     [rsi+33Bh], r13b
0x180032f42  jmp     short loc_180032FC0
0x180032f44  mov     rax, [rsi+0A0h]
0x180032f4b  mov     r12d, [rsi+32Ch]
0x180032f52  mov     r15d, [rax+30h]
0x180032f56  cmp     [rsi+33Dh], r13b
0x180032f5d  jz      short loc_180032F67
0x180032f5f  mov     rcx, r14
0x180032f62  call    ?unlock@?$unique_lock@Vshared_mutex@utl@@@utl@@QEAAXXZ; utl::unique_lock<utl::shared_mutex>::unlock(void)
0x180032f67  mov     rbx, [rbx]
0x180032f6a  xor     r8d, r8d; unsigned int
0x180032f6d  mov     rdx, rbx; void *
0x180032f70  mov     rcx, rdi; this
0x180032f73  test    r12d, r12d
0x180032f76  jnz     short loc_180032F7D
0x180032f78  mov     r9d, r15d
0x180032f7b  jmp     short loc_180032F9D
0x180032f7d  mov     r9d, 200h; unsigned int
0x180032f83  call    ?ActualWrite@FileView@@AEAAKPEAXKK@Z; FileView::ActualWrite(void *,ulong,ulong)
0x180032f88  mov     ebp, eax
0x180032f8a  test    eax, eax
0x180032f8c  jnz     short loc_180032FA4
0x180032f8e  mov     r9d, r15d
0x180032f91  mov     r8d, r12d; unsigned int
0x180032f94  sub     r9d, r12d; unsigned int
0x180032f97  mov     rdx, rbx; void *
0x180032f9a  mov     rcx, rdi; this
0x180032f9d  call    ?ActualWrite@FileView@@AEAAKPEAXKK@Z; FileView::ActualWrite(void *,ulong,ulong)
0x180032fa2  mov     ebp, eax
0x180032fa4  cmp     [rsi+33Dh], r13b
0x180032fab  jz      short loc_180032FB5
0x180032fad  mov     rcx, r14
0x180032fb0  call    ?lock@?$unique_lock@Vshared_mutex@utl@@@utl@@QEAAXXZ; utl::unique_lock<utl::shared_mutex>::lock(void)
0x180032fb5  test    ebp, ebp
0x180032fb7  jnz     short loc_180032FC0
0x180032fb9  mov     [rsi+32Ch], r15d
0x180032fc0  lea     rbx, [rsi+2E8h]
0x180032fc7  mov     [rsi+346h], r13b
0x180032fce  lea     rcx, [rbx+8]; SRWLock
0x180032fd2  call    cs:__imp_AcquireSRWLockExclusive
0x180032fd8  mov     rcx, rbx; ConditionVariable
0x180032fdb  call    cs:__imp_WakeAllConditionVariable
0x180032fe1  lea     rcx, [rbx+8]; SRWLock
0x180032fe5  call    cs:__imp_ReleaseSRWLockExclusive
0x180032feb  test    ebp, ebp
0x180032fed  jz      short loc_18003302D
0x180032fef  mov     rcx, cs:WPP_GLOBAL_Control
0x180032ff6  lea     rdx, WPP_GLOBAL_Control
0x180032ffd  cmp     rcx, rdx
0x180033000  jz      short loc_180033029
0x180033002  test    dword ptr [rcx+1Ch], 8000h
0x180033009  jz      short loc_180033029
0x18003300b  cmp     byte ptr [rcx+19h], 2
0x18003300f  jb      short loc_180033029
0x180033011  mov     rcx, [rcx+10h]
0x180033015  lea     r8, WPP_d3d936efbc913e3641017ad303784371_Traceguids
0x18003301c  mov     edx, 2Bh ; '+'
0x180033021  mov     r9d, ebp
0x180033024  call    WPP_SF_D
0x180033029  mov     eax, ebp
0x18003302b  jmp     short loc_180033060
0x18003302d  mov     rcx, [rsi+290h]; pti
0x180033034  test    rcx, rcx
0x180033037  jz      short loc_180033057
0x180033039  cmp     [rsi+345h], r13b
0x180033040  jz      short loc_180033057
0x180033042  xor     r9d, r9d; msWindowLength
0x180033045  mov     [rsi+345h], r13b
0x18003304c  xor     r8d, r8d; msPeriod
0x18003304f  xor     edx, edx; pftDueTime
0x180033051  call    cs:__imp_SetThreadpoolTimer
0x180033057  mov     [rsi+33Ah], r13b
0x18003305e  xor     eax, eax
0x180033060  add     rsp, 58h
0x180033064  pop     r15
0x180033066  pop     r14
0x180033068  pop     r13
0x18003306a  pop     r12
0x18003306c  pop     rdi
0x18003306d  pop     rsi
0x18003306e  pop     rbp
0x18003306f  pop     rbx
0x180033070  retn
```
