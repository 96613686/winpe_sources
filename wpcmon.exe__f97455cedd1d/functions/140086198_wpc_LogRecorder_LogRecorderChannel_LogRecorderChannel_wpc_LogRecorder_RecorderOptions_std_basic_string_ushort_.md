# wpc::LogRecorder::LogRecorderChannel::LogRecorderChannel(wpc::LogRecorder::RecorderOptions,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>)

- ea: `0x140086198`
- end: `0x1400866d8`
- name: `??0LogRecorderChannel@LogRecorder@wpc@@QEAA@W4RecorderOptions@12@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `1344`
- prototype: `wpc::LogRecorder::LogRecorderChannel *__fastcall(wpc::LogRecorder::LogRecorderChannel *this, char, _QWORD *)`
- caller_count: `1`
- callee_count: `25`
- tags: `file_ops, authz_impersonation`

## callers

- `0x140086104`

## callees

- `0x140005530`
- `0x140008904`
- `0x140009858`
- `0x14000b744`
- `0x14000ccac`
- `0x140010e18`
- `0x14001c478`
- `0x1400231d4`
- `0x1400251c4`
- `0x14002c2e4`
- `0x140035800`
- `0x140067b84`
- `0x140068dbc`
- `0x14006ba34`
- `0x14006bbbc`
- `0x140081af0`
- `0x140081b44`
- `0x140082fe8`
- `0x140084688`
- `0x140085c50`
- `0x140085da8`
- `0x140086198`
- `0x140086cf4`
- `0x14008734c`
- `0x1400a8010`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x140086640`
- `KERNEL32!GetCurrentProcessId` at `0x140086640`
- `KERNEL32!GetFileTime` at `0x14008653f`
- `KERNEL32!GetFileTime` at `0x14008653f`
- `KERNEL32!GetFileAttributesW` at `0x140086500`
- `KERNEL32!GetFileAttributesW` at `0x140086500`
- `KERNEL32!CloseHandle` at `0x14008658d`
- `KERNEL32!CloseHandle` at `0x1400865a7`
- `KERNEL32!CloseHandle` at `0x14008658d`
- `KERNEL32!CloseHandle` at `0x1400865a7`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x140086285`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x140086285`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
wpc::LogRecorder::LogRecorderChannel *__fastcall wpc::LogRecorder::LogRecorderChannel::LogRecorderChannel(
        wpc::LogRecorder::LogRecorderChannel *this,
        char a2,
        _QWORD *a3)
{
  int v6; // esi
  __int64 v7; // rcx
  __int64 v8; // rax
  volatile signed __int32 *v9; // rbx
  __int64 v10; // rax
  volatile signed __int32 *v11; // rbx
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // rcx
  _QWORD *v15; // r9
  __int64 v16; // rax
  __int64 v17; // rdx
  __int64 v18; // r8
  __int64 v19; // rax
  _QWORD *v20; // r9
  __int64 v21; // rax
  const WCHAR *v22; // rcx
  char *v23; // rbx
  __int64 v24; // rax
  int v25; // esi
  __int64 Current; // rax
  Private::Format *v27; // rbx
  __int64 v28; // rax
  Private::Format *v29; // rbx
  __int64 v30; // rax
  _BYTE v32[4]; // [rsp+40h] [rbp-C0h] BYREF
  int v33; // [rsp+44h] [rbp-BCh]
  HANDLE hFile; // [rsp+48h] [rbp-B8h] BYREF
  struct _FILETIME CreationTime; // [rsp+50h] [rbp-B0h] BYREF
  wpc::LogRecorder::LogRecorderChannel *v36; // [rsp+58h] [rbp-A8h]
  _BYTE v37[16]; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD *v38; // [rsp+70h] [rbp-90h]
  __int128 v39; // [rsp+78h] [rbp-88h] BYREF
  char *v40; // [rsp+88h] [rbp-78h]
  __int64 v41; // [rsp+90h] [rbp-70h]
  _BYTE v42[8]; // [rsp+98h] [rbp-68h] BYREF
  volatile signed __int32 *v43; // [rsp+A0h] [rbp-60h]
  _BYTE v44[32]; // [rsp+B8h] [rbp-48h] BYREF
  _BYTE v45[32]; // [rsp+D8h] [rbp-28h] BYREF
  _BYTE v46[40]; // [rsp+F8h] [rbp-8h] BYREF
  _BYTE v47[72]; // [rsp+120h] [rbp+20h] BYREF
  _BYTE v48[40]; // [rsp+168h] [rbp+68h] BYREF

  v36 = this;
  v38 = a3;
  v33 = 0;
  v39 = 0;
  v40 = 0;
  v41 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v39, &SubKey, 0);
  IO::Path::Path(this, &v39);
  v39 = 0;
  v40 = 0;
  v41 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v39, &SubKey, 0);
  IO::Path::Path((char *)this + 32, &v39);
  DateTime::GetCurrent((char *)this + 64);
  DateTime::GetCurrent((char *)this + 76);
  *((_QWORD *)this + 11) = &LockBox<std::wstring,4294967295>::`vftable';
  *(_OWORD *)((char *)this + 104) = 0;
  *((_QWORD *)this + 15) = 0;
  v6 = 7;
  *((_QWORD *)this + 16) = 7;
  *((_WORD *)this + 52) = 0;
  InitializeSRWLock((PSRWLOCK)this + 12);
  *((_QWORD *)this + 17) = 0;
  *((_QWORD *)this + 18) = 0;
  *((_QWORD *)this + 19) = 0;
  *((_QWORD *)this + 20) = 0;
  if ( (a2 & 2) != 0 )
  {
    CreationTime = (struct _FILETIME)this;
    v8 = Threadpool::QueueTimerCallback__lambda_cbf5b5fb35637c87aa327395232b2d2a___(v7, v42, &CreationTime);
    std::shared_ptr<Signal<Optional<__int64> (unsigned __int64,__int64)>>::operator=((char *)this + 136, v8);
    v9 = v43;
    if ( v43 )
    {
      if ( _InterlockedExchangeAdd(v43 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v9)(v9);
        if ( _InterlockedExchangeAdd(v9 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v9 + 8LL))(v9);
      }
    }
  }
  if ( (a2 & 4) != 0 )
  {
    CreationTime = (struct _FILETIME)1200000000LL;
    hFile = this;
    v10 = Threadpool::QueueTimerCallback__lambda_3be6e2c04033393fb85ca8d5efb592b1___(v7, v42, &hFile, &CreationTime);
    std::shared_ptr<Signal<Optional<__int64> (unsigned __int64,__int64)>>::operator=((char *)this + 152, v10);
    v11 = v43;
    if ( v43 )
    {
      if ( _InterlockedExchangeAdd(v43 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v11)(v11);
        if ( !_InterlockedDecrement(v11 + 3) )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v11 + 8LL))(v11);
      }
    }
  }
  v32[0] = a2 & 1;
  lambda_6b4353445c5d79bdb48dad0cdc4514c8_::operator()(v32, v44);
  v33 = 1;
  if ( !IO::Directory::Exists((const struct Path *)v44) )
  {
    IO::Directory::Create(&v39, v44, 0);
    std::wstring::~wstring(&v39);
  }
  v14 = a3[2];
  if ( (unsigned __int64)(0x7FFFFFFFFFFFFFFELL - v14) < 8 )
    std::_Xlen_string();
  if ( a3[3] <= 7u )
    v15 = a3;
  else
    v15 = (_QWORD *)*a3;
  std::wstring::wstring(&v39, v12, v13, v15, v14, L"-old.log", 8);
  v33 = 3;
  IO::Path::Path(v42, &v39);
  v16 = IO::operator/(v45, v44, v42);
  std::wstring::operator=((char *)this + 32, v16);
  std::wstring::~wstring(v45);
  std::wstring::~wstring(v42);
  v19 = a3[2];
  if ( (unsigned __int64)(0x7FFFFFFFFFFFFFFELL - v19) < 4 )
    std::_Xlen_string();
  if ( a3[3] <= 7u )
    v20 = a3;
  else
    v20 = (_QWORD *)*a3;
  std::wstring::wstring(&v39, v17, v18, v20, v19, L".log", 4);
  v33 = 7;
  IO::Path::Path(v42, &v39);
  v21 = IO::operator/(v45, v44, v42);
  std::wstring::operator=(this, v21);
  std::wstring::~wstring(v45);
  std::wstring::~wstring(v42);
  if ( *((_QWORD *)this + 3) <= 7u )
    v22 = (const WCHAR *)this;
  else
    v22 = *(const WCHAR **)this;
  if ( (GetFileAttributesW(v22) & 0x10) != 0 )
    goto LABEL_32;
  IO::File::Open(&hFile, (const WCHAR *)this, 0);
  v6 = 23;
  v33 = 23;
  CreationTime = 0;
  v23 = (char *)hFile;
  if ( !GetFileTime(hFile, &CreationTime, 0, 0) )
  {
    if ( v23 && (unsigned __int64)(v23 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(v23);
LABEL_32:
    v40 = 0;
    v25 = v6 | 8;
    v33 = v25;
    goto LABEL_33;
  }
  v24 = DateTime::DateTime(v37, &CreationTime, 0);
  *(_QWORD *)((char *)&v39 + 4) = *(_QWORD *)v24;
  HIDWORD(v39) = *(_DWORD *)(v24 + 8);
  v40 = (char *)&v39 + 4;
  v25 = 31;
  v33 = 31;
  if ( v23 && (unsigned __int64)(v23 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v23);
LABEL_33:
  Current = DateTime::GetCurrent(v42);
  if ( v40 )
    Current = (__int64)v40;
  *(_QWORD *)((char *)this + 76) = *(_QWORD *)Current;
  *((_DWORD *)this + 21) = *(_DWORD *)(Current + 8);
  v39 = 0;
  v40 = 0;
  v41 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v39, L"Logging started for user:{0}, pid:{1}", 37);
  v27 = (Private::Format *)StringAlgo::FormatString(v46, &v39);
  v28 = Sid::GetCurrent(v47);
  std::wstring::wstring(v42, v28 + 72);
  v33 = v25 | 0x20;
  v29 = (Private::Format *)Private::Format::operator%<std::wstring>(v27);
  CreationTime.dwLowDateTime = GetCurrentProcessId();
  v30 = Private::Format::operator%<unsigned long>(v29);
  std::wstring::wstring(v45, v30);
  wpc::LogRecorder::LogRecorderChannel::AddLogEntry(this);
  std::wstring::~wstring(v42);
  std::wstring::~wstring(v48);
  std::wstring::~wstring(v46);
  std::wstring::~wstring(v44);
  std::wstring::~wstring(a3);
  return this;
}

```

## disassembly

```asm
0x140086198  mov     [rsp-8+arg_8], rbx
0x14008619d  push    rbp
0x14008619e  push    rsi
0x14008619f  push    rdi
0x1400861a0  push    r12
0x1400861a2  push    r13
0x1400861a4  push    r14
0x1400861a6  push    r15
0x1400861a8  lea     rbp, [rsp-0A0h]
0x1400861b0  sub     rsp, 1A0h
0x1400861b7  mov     rax, cs:__security_cookie
0x1400861be  xor     rax, rsp
0x1400861c1  mov     [rbp+0D0h+var_40], rax
0x1400861c8  mov     r14, r8
0x1400861cb  mov     r15d, edx
0x1400861ce  mov     rdi, rcx
0x1400861d1  mov     [rsp+1D0h+var_178], rcx
0x1400861d6  mov     [rsp+1D0h+var_160], r8
0x1400861db  xor     r12d, r12d
0x1400861de  mov     [rsp+1D0h+var_18C], r12d
0x1400861e3  xorps   xmm0, xmm0
0x1400861e6  movups  [rsp+1D0h+var_158], xmm0
0x1400861eb  mov     [rbp+0D0h+var_148], r12
0x1400861ef  mov     [rbp+0D0h+var_140], r12
0x1400861f3  xor     r8d, r8d
0x1400861f6  lea     rdx, SubKey
0x1400861fd  lea     rcx, [rsp+1D0h+var_158]
0x140086202  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x140086207  lea     rdx, [rsp+1D0h+var_158]
0x14008620c  mov     rcx, rdi
0x14008620f  call    ??0Path@IO@@QEAA@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; IO::Path::Path(std::wstring)
0x140086214  nop
0x140086215  xorps   xmm0, xmm0
0x140086218  movups  [rsp+1D0h+var_158], xmm0
0x14008621d  mov     [rbp+0D0h+var_148], r12
0x140086221  mov     [rbp+0D0h+var_140], r12
0x140086225  xor     r8d, r8d
0x140086228  lea     rdx, SubKey
0x14008622f  lea     rcx, [rsp+1D0h+var_158]
0x140086234  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x140086239  lea     rdx, [rsp+1D0h+var_158]
0x14008623e  lea     rcx, [rdi+20h]
0x140086242  call    ??0Path@IO@@QEAA@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; IO::Path::Path(std::wstring)
0x140086247  nop
0x140086248  lea     rcx, [rdi+40h]
0x14008624c  call    ?GetCurrent@DateTime@@SA?AV1@XZ; DateTime::GetCurrent(void)
0x140086251  lea     rcx, [rdi+4Ch]
0x140086255  call    ?GetCurrent@DateTime@@SA?AV1@XZ; DateTime::GetCurrent(void)
0x14008625a  lea     rax, ??_7?$LockBox@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$0PPPPPPPP@@@6B@; const LockBox<std::wstring,4294967295>::`vftable'
0x140086261  mov     [rdi+58h], rax
0x140086265  xorps   xmm0, xmm0
0x140086268  movups  xmmword ptr [rdi+68h], xmm0
0x14008626c  mov     [rdi+78h], r12
0x140086270  lea     esi, [r12+7]
0x140086275  mov     [rdi+80h], rsi
0x14008627c  mov     [rdi+68h], r12w
0x140086281  lea     rcx, [rdi+60h]; SRWLock
0x140086285  call    cs:__imp_InitializeSRWLock
0x14008628b  nop
0x14008628c  lea     rbx, [rdi+88h]
0x140086293  mov     [rbx], r12
0x140086296  mov     [rbx+8], r12
0x14008629a  lea     r12, [rdi+98h]
0x1400862a1  mov     qword ptr [r12], 0
0x1400862a9  mov     qword ptr [r12+8], 0
0x1400862b2  test    r15b, 2
0x1400862b6  jz      short loc_140086316
0x1400862b8  mov     qword ptr [rsp+1D0h+CreationTime.dwLowDateTime], rdi
0x1400862bd  lea     r8, [rsp+1D0h+CreationTime]
0x1400862c2  lea     rdx, [rbp+0D0h+var_138]
0x1400862c6  call    Threadpool__QueueTimerCallback__lambda_cbf5b5fb35637c87aa327395232b2d2a___
0x1400862cb  mov     rdx, rax
0x1400862ce  mov     rcx, rbx
0x1400862d1  call    ??4?$shared_ptr@V?$Signal@$$A6A?AV?$Optional@_J@@_K_J@Z@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<Signal<Optional<__int64> (unsigned __int64,__int64)>>::operator=(std::shared_ptr<Signal<Optional<__int64> (unsigned __int64,__int64)>> &&)
0x1400862d6  mov     rbx, [rbp+0D0h+var_130]
0x1400862da  test    rbx, rbx
0x1400862dd  jz      short loc_140086316
0x1400862df  or      eax, 0FFFFFFFFh
0x1400862e2  lock xadd [rbx+8], eax
0x1400862e7  cmp     eax, 1
0x1400862ea  jnz     short loc_140086316
0x1400862ec  mov     rax, [rbx]
0x1400862ef  mov     rcx, rbx
0x1400862f2  mov     rax, [rax]
0x1400862f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400862fa  or      eax, 0FFFFFFFFh
0x1400862fd  lock xadd [rbx+0Ch], eax
0x140086302  cmp     eax, 1
0x140086305  jnz     short loc_140086316
0x140086307  mov     rax, [rbx]
0x14008630a  mov     rcx, rbx
0x14008630d  mov     rax, [rax+8]
0x140086311  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140086316  test    r15b, 4
0x14008631a  jz      short loc_14008638C
0x14008631c  mov     qword ptr [rsp+1D0h+CreationTime.dwLowDateTime], 47868C00h
0x140086325  mov     [rsp+1D0h+hFile], rdi
0x14008632a  lea     r9, [rsp+1D0h+CreationTime]
0x14008632f  lea     r8, [rsp+1D0h+hFile]
0x140086334  lea     rdx, [rbp+0D0h+var_138]
0x140086338  call    Threadpool__QueueTimerCallback__lambda_3be6e2c04033393fb85ca8d5efb592b1___
0x14008633d  mov     rdx, rax
0x140086340  mov     rcx, r12
0x140086343  call    ??4?$shared_ptr@V?$Signal@$$A6A?AV?$Optional@_J@@_K_J@Z@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<Signal<Optional<__int64> (unsigned __int64,__int64)>>::operator=(std::shared_ptr<Signal<Optional<__int64> (unsigned __int64,__int64)>> &&)
0x140086348  mov     rbx, [rbp+0D0h+var_130]
0x14008634c  test    rbx, rbx
0x14008634f  jz      short loc_14008638C
0x140086351  or      r12d, 0FFFFFFFFh
0x140086355  mov     eax, r12d
0x140086358  lock xadd [rbx+8], eax
0x14008635d  add     eax, r12d
0x140086360  jnz     short loc_14008638C
0x140086362  mov     rax, [rbx]
0x140086365  mov     rcx, rbx
0x140086368  mov     rax, [rax]
0x14008636b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140086370  mov     eax, r12d
0x140086373  lock xadd [rbx+0Ch], eax
0x140086378  add     eax, r12d
0x14008637b  jnz     short loc_14008638C
0x14008637d  mov     rax, [rbx]
0x140086380  mov     rcx, rbx
0x140086383  mov     rax, [rax+8]
0x140086387  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008638c  and     r15d, 1
0x140086390  mov     [rsp+1D0h+var_190], r15b
0x140086395  lea     rdx, [rbp+0D0h+var_118]
0x140086399  lea     rcx, [rsp+1D0h+var_190]
0x14008639e  call    _lambda_6b4353445c5d79bdb48dad0cdc4514c8___operator__
0x1400863a3  mov     [rsp+1D0h+var_18C], 1
0x1400863ab  lea     rcx, [rbp+0D0h+var_118]; struct Path *
0x1400863af  call    ?Exists@Directory@IO@@SA_NAEBVPath@2@@Z; IO::Directory::Exists(IO::Path const &)
0x1400863b4  xor     r15d, r15d
0x1400863b7  test    al, al
0x1400863b9  jnz     short loc_1400863D6
0x1400863bb  xor     r8d, r8d
0x1400863be  lea     rdx, [rbp+0D0h+var_118]
0x1400863c2  lea     rcx, [rsp+1D0h+var_158]
0x1400863c7  call    ?Create@Directory@IO@@SA?AV12@AEBVPath@2@PEBVSecurityDescriptor@@@Z; IO::Directory::Create(IO::Path const &,SecurityDescriptor const *)
0x1400863cc  lea     rcx, [rsp+1D0h+var_158]
0x1400863d1  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400863d6  mov     rcx, [r14+10h]
0x1400863da  mov     rbx, 7FFFFFFFFFFFFFFEh
0x1400863e4  mov     rax, rbx
0x1400863e7  sub     rax, rcx
0x1400863ea  cmp     rax, 8
0x1400863ee  jb      loc_1400866D2
0x1400863f4  cmp     [r14+18h], rsi
0x1400863f8  jbe     short loc_1400863FF
0x1400863fa  mov     r9, [r14]
0x1400863fd  jmp     short loc_140086402
0x1400863ff  mov     r9, r14
0x140086402  mov     [rsp+1D0h+var_1A0], 8
0x14008640b  lea     rax, aOldLog; "-old.log"
0x140086412  mov     [rsp+1D0h+var_1A8], rax
0x140086417  mov     [rsp+1D0h+var_1B0], rcx
0x14008641c  lea     rcx, [rsp+1D0h+var_158]
0x140086421  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBG_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x140086426  mov     [rsp+1D0h+var_18C], 3
0x14008642e  lea     rdx, [rsp+1D0h+var_158]
0x140086433  lea     rcx, [rbp+0D0h+var_138]
0x140086437  call    ??0Path@IO@@QEAA@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; IO::Path::Path(std::wstring)
0x14008643c  nop
0x14008643d  lea     r8, [rbp+0D0h+var_138]
0x140086441  lea     rdx, [rbp+0D0h+var_118]
0x140086445  lea     rcx, [rbp+0D0h+var_F8]
0x140086449  call    ??KIO@@YA?AVPath@0@AEBV10@0@Z; IO::operator/(IO::Path const &,IO::Path const &)
0x14008644e  mov     rdx, rax
0x140086451  lea     rcx, [rdi+20h]
0x140086455  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x14008645a  lea     rcx, [rbp+0D0h+var_F8]
0x14008645e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140086463  nop
0x140086464  lea     rcx, [rbp+0D0h+var_138]
0x140086468  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14008646d  mov     rax, [r14+10h]
0x140086471  sub     rbx, rax
0x140086474  cmp     rbx, 4
0x140086478  jb      loc_1400866CC
0x14008647e  cmp     [r14+18h], rsi
0x140086482  jbe     short loc_140086489
0x140086484  mov     r9, [r14]
0x140086487  jmp     short loc_14008648C
0x140086489  mov     r9, r14
0x14008648c  mov     [rsp+1D0h+var_1A0], 4
0x140086495  lea     rcx, aLog; ".log"
0x14008649c  mov     [rsp+1D0h+var_1A8], rcx
0x1400864a1  mov     [rsp+1D0h+var_1B0], rax
0x1400864a6  lea     rcx, [rsp+1D0h+var_158]
0x1400864ab  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBG_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x1400864b0  mov     [rsp+1D0h+var_18C], esi
0x1400864b4  lea     rdx, [rsp+1D0h+var_158]
0x1400864b9  lea     rcx, [rbp+0D0h+var_138]
0x1400864bd  call    ??0Path@IO@@QEAA@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; IO::Path::Path(std::wstring)
0x1400864c2  nop
0x1400864c3  lea     r8, [rbp+0D0h+var_138]
0x1400864c7  lea     rdx, [rbp+0D0h+var_118]
0x1400864cb  lea     rcx, [rbp+0D0h+var_F8]
0x1400864cf  call    ??KIO@@YA?AVPath@0@AEBV10@0@Z; IO::operator/(IO::Path const &,IO::Path const &)
0x1400864d4  mov     rdx, rax
0x1400864d7  mov     rcx, rdi
0x1400864da  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1400864df  lea     rcx, [rbp+0D0h+var_F8]
0x1400864e3  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400864e8  nop
0x1400864e9  lea     rcx, [rbp+0D0h+var_138]
0x1400864ed  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400864f2  cmp     [rdi+18h], rsi
0x1400864f6  jbe     short loc_1400864FD
0x1400864f8  mov     rcx, [rdi]
0x1400864fb  jmp     short loc_140086500
0x1400864fd  mov     rcx, rdi; lpFileName
0x140086500  call    cs:__imp_GetFileAttributesW
0x140086506  test    al, 10h
0x140086508  jnz     loc_1400865AD
0x14008650e  xor     r8d, r8d
0x140086511  mov     rdx, rdi
0x140086514  lea     rcx, [rsp+1D0h+hFile]
0x140086519  call    ?Open@File@IO@@YA?AV?$unique_ptr@XUHandleClose@Private@@@std@@AEBVPath@2@W4Access@12@UAssumeDirectoryExists@2@@Z; IO::File::Open(IO::Path const &,IO::File::Access,IO::AssumeDirectoryExists)
0x14008651e  mov     esi, 17h
0x140086523  mov     [rsp+1D0h+var_18C], esi
0x140086527  mov     qword ptr [rsp+1D0h+CreationTime.dwLowDateTime], r15
0x14008652c  xor     r9d, r9d; lpLastWriteTime
0x14008652f  xor     r8d, r8d; lpLastAccessTime
0x140086532  lea     rdx, [rsp+1D0h+CreationTime]; lpCreationTime
0x140086537  mov     rbx, [rsp+1D0h+hFile]
0x14008653c  mov     rcx, rbx; hFile
0x14008653f  call    cs:__imp_GetFileTime
0x140086545  test    eax, eax
0x140086547  jz      short loc_140086595
0x140086549  xor     r8d, r8d
0x14008654c  lea     rdx, [rsp+1D0h+CreationTime]
0x140086551  lea     rcx, [rsp+1D0h+var_170]
0x140086556  call    ??0DateTime@@QEAA@AEBU_FILETIME@@W4TimeType@@@Z; DateTime::DateTime(_FILETIME const &,TimeType)
0x14008655b  mov     rcx, [rax]
0x14008655e  mov     qword ptr [rsp+1D0h+var_158+4], rcx
0x140086563  mov     eax, [rax+8]
0x140086566  mov     dword ptr [rbp+0D0h+var_158+0Ch], eax
0x140086569  lea     rax, [rsp+1D0h+var_158+4]
0x14008656e  mov     [rbp+0D0h+var_148], rax
0x140086572  mov     esi, 1Fh
0x140086577  mov     [rsp+1D0h+var_18C], esi
0x14008657b  test    rbx, rbx
0x14008657e  jz      short loc_1400865B8
0x140086580  lea     rax, [rbx-1]
0x140086584  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140086588  ja      short loc_1400865B8
0x14008658a  mov     rcx, rbx; hObject
0x14008658d  call    cs:__imp_CloseHandle
0x140086593  jmp     short loc_1400865B8
0x140086595  test    rbx, rbx
0x140086598  jz      short loc_1400865AD
0x14008659a  lea     rax, [rbx-1]
0x14008659e  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400865a2  ja      short loc_1400865AD
0x1400865a4  mov     rcx, rbx; hObject
0x1400865a7  call    cs:__imp_CloseHandle
0x1400865ad  mov     [rbp+0D0h+var_148], r15
0x1400865b1  or      esi, 8
0x1400865b4  mov     [rsp+1D0h+var_18C], esi
0x1400865b8  lea     rcx, [rbp+0D0h+var_138]
0x1400865bc  call    ?GetCurrent@DateTime@@SA?AV1@XZ; DateTime::GetCurrent(void)
0x1400865c1  mov     rcx, [rbp+0D0h+var_148]
0x1400865c5  test    rcx, rcx
0x1400865c8  cmovnz  rax, rcx
0x1400865cc  movsd   xmm0, qword ptr [rax]
0x1400865d0  movsd   qword ptr [rdi+4Ch], xmm0
0x1400865d5  mov     eax, [rax+8]
0x1400865d8  mov     [rdi+54h], eax
0x1400865db  xorps   xmm0, xmm0
0x1400865de  movups  [rsp+1D0h+var_158], xmm0
0x1400865e3  mov     [rbp+0D0h+var_148], r15
0x1400865e7  mov     [rbp+0D0h+var_140], r15
0x1400865eb  mov     r8d, 25h ; '%'
0x1400865f1  lea     rdx, aLoggingStarted; "Logging started for user:{0}, pid:{1}"
0x1400865f8  lea     rcx, [rsp+1D0h+var_158]
0x1400865fd  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x140086602  lea     rdx, [rsp+1D0h+var_158]
0x140086607  lea     rcx, [rbp+0D0h+var_D8]
0x14008660b  call    ?FormatString@StringAlgo@@YA?AVFormat@Private@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; StringAlgo::FormatString(std::wstring)
0x140086610  mov     rbx, rax
0x140086613  lea     rcx, [rbp+0D0h+var_B0]
0x140086617  call    ?GetCurrent@Sid@@SA?AV1@XZ; Sid::GetCurrent(void)
0x14008661c  nop
0x14008661d  lea     rdx, [rax+48h]
0x140086621  lea     rcx, [rbp+0D0h+var_138]
0x140086625  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x14008662a  or      esi, 20h
0x14008662d  mov     [rsp+1D0h+var_18C], esi
0x140086631  lea     rdx, [rbp+0D0h+var_138]
0x140086635  mov     rcx, rbx; this
0x140086638  call    ??$?LV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Format@Private@@QEAAAEAV01@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Private::Format::operator%<std::wstring>(std::wstring const &)
0x14008663d  mov     rbx, rax
0x140086640  call    cs:__imp_GetCurrentProcessId
0x140086646  mov     [rsp+1D0h+CreationTime.dwLowDateTime], eax
0x14008664a  lea     rdx, [rsp+1D0h+CreationTime]
0x14008664f  mov     rcx, rbx; this
0x140086652  call    ??$?LK@Format@Private@@QEAAAEAV01@AEBK@Z; Private::Format::operator%<ulong>(ulong const &)
0x140086657  mov     rdx, rax
0x14008665a  lea     rcx, [rbp+0D0h+var_F8]
  ... truncated ...
```
