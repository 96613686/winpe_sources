# p9fs::File::Open(p9fs::OpenFlags)

- ea: `0x1800200e0`
- end: `0x1800203c7`
- name: `?Open@File@p9fs@@UEAA?AV?$BasicExpected@UQid@p9fs@@J@util@@W4OpenFlags@2@@Z`
- size: `743`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x180004120`
- `0x1800074e0`
- `0x18001c9ec`
- `0x1800200e0`
- `0x1800204c8`
- `0x180028fdc`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180020373`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180020373`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002011a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002011a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002029f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180020321`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002029f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180020321`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002027f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002030e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002027f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002030e`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x180020297`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x1800202d1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x180020297`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x1800202d1`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolIoCallbacks` at `0x18002028d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolIoCallbacks` at `0x1800202c8`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolIoCallbacks` at `0x18002028d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolIoCallbacks` at `0x1800202c8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020319`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020364`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020319`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020364`
- `lxutil!LxUtilFsTruncate` at `0x18002021a`
- `lxutil!LxUtilFsTruncate` at `0x18002021a`

## string_xrefs

- `0x18002013b`: `onecore\vm\dv\storage\plan9\dll\windows\p9file.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall p9fs::File::Open(__int64 a1, __int64 a2, unsigned int a3)
{
  RTL_SRWLOCK *v6; // rsi
  int v7; // r10d
  __int64 v8; // r8
  __int64 v9; // rcx
  const char *v10; // r9
  char v11; // al
  int v12; // eax
  int v13; // eax
  __int64 v14; // rcx
  PTP_IO *v15; // rax
  const char *v16; // r9
  PTP_IO *v17; // r12
  PTP_IO *v18; // r13
  DWORD LastError; // ebx
  struct _TP_IO *v20; // rbx
  char v21; // dl
  void **v22; // r12
  void *v23; // r13
  DWORD v24; // ebx
  int v26; // [rsp+20h] [rbp-69h]
  struct _TP_IO *v27; // [rsp+60h] [rbp-29h]
  HANDLE v28; // [rsp+60h] [rbp-29h]
  int v29; // [rsp+68h] [rbp-21h]
  PTP_IO pio[2]; // [rsp+70h] [rbp-19h] BYREF
  PTP_IO pv[2]; // [rsp+80h] [rbp-9h] BYREF
  _BYTE v32[8]; // [rsp+90h] [rbp+7h] BYREF
  HANDLE hObject; // [rsp+98h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  v6 = (RTL_SRWLOCK *)(a1 + 8);
  AcquireSRWLockExclusive((PSRWLOCK)(a1 + 8));
  if ( (unsigned __int64)(*(_QWORD *)(a1 + 48) - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    wil::details::in1diag3::Log_Hr(
      retaddr,
      (void *)0x245,
      (unsigned int)"onecore\\vm\\dv\\storage\\plan9\\dll\\windows\\p9file.cpp",
      (const char *)0x8000FFFFLL,
      v26);
    *(_BYTE *)a2 = 0;
    *(_DWORD *)(a2 + 8) = -22;
    goto LABEL_29;
  }
  v7 = p9fs::OpenFlagsToAccessMask(a3);
  v29 = v7;
  if ( (v7 & 0xFFEDFF76) != 0 && (*(_BYTE *)(*(_QWORD *)(a1 + 72) + 48LL) & 1) != 0 )
  {
    *(_BYTE *)a2 = 0;
    *(_DWORD *)(a2 + 8) = -30;
    goto LABEL_29;
  }
  v8 = *(_QWORD *)(a1 + 72);
  v9 = *(_QWORD *)(v8 + 112);
  pio[0] = 0;
  pio[1] = 0;
  pv[0] = 0;
  pv[1] = 0;
  (*(void (__fastcall **)(__int64, _BYTE *, _QWORD, __int64, int, int, unsigned int, PTP_IO *, PTP_IO *, _QWORD))(*(_QWORD *)v9 + 8LL))(
    v9,
    v32,
    *(_QWORD *)(v8 + 24),
    a1 + 16,
    v7,
    1,
    (a3 & 0x10000 | 0x40000) >> 16,
    pv,
    pio,
    0);
  v11 = v32[0];
  if ( !v32[0] )
  {
    v12 = (int)hObject;
    *(_BYTE *)a2 = 0;
    *(_DWORD *)(a2 + 8) = v12;
    goto LABEL_29;
  }
  if ( (a3 & 0x200) != 0 )
  {
    v13 = LxUtilFsTruncate(hObject, 0);
    if ( v13 )
    {
      *(_BYTE *)a2 = 0;
      *(_DWORD *)(a2 + 8) = v13;
      if ( !v32[0] )
        goto LABEL_29;
      v14 = (__int64)hObject;
      goto LABEL_27;
    }
    v11 = v32[0];
  }
  if ( !v11 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x139,
      (unsigned int)"onecore\\vm\\inc\\expected.h",
      v10);
  v15 = p9fs::CoroutineIoIssuer::CoroutineIoIssuer(pv, (struct _TP_IO *)hObject);
  v17 = v15;
  v18 = (PTP_IO *)(a1 + 56);
  if ( (PTP_IO *)(a1 + 56) != v15 )
  {
    v27 = *v15;
    pio[0] = *v18;
    if ( pio[0] )
    {
      LastError = GetLastError();
      WaitForThreadpoolIoCallbacks(pio[0], 0);
      CloseThreadpoolIo(pio[0]);
      SetLastError(LastError);
    }
    *v18 = v27;
    *v17 = 0;
  }
  *(_QWORD *)(a1 + 64) = v17[1];
  v20 = pv[0];
  if ( pv[0] )
  {
    WaitForThreadpoolIoCallbacks(pv[0], 0);
    CloseThreadpoolIo(v20);
  }
  v21 = v32[0];
  if ( !v32[0] )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x139,
      (unsigned int)"onecore\\vm\\inc\\expected.h",
      v16);
  v22 = (void **)(a1 + 48);
  if ( (HANDLE *)(a1 + 48) == &hObject )
  {
    v14 = (__int64)hObject;
  }
  else
  {
    v28 = hObject;
    v23 = *v22;
    if ( (char *)*v22 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      v24 = GetLastError();
      CloseHandle(v23);
      SetLastError(v24);
      v21 = v32[0];
    }
    *v22 = v28;
    v14 = -1;
    hObject = (HANDLE)-1LL;
  }
  *(_DWORD *)(a1 + 88) = v29;
  *(_BYTE *)a2 = 1;
  *(_OWORD *)(a2 + 8) = *(_OWORD *)(a1 + 120);
  if ( v21 )
  {
LABEL_27:
    if ( (unsigned __int64)(v14 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle((HANDLE)v14);
  }
LABEL_29:
  if ( v6 )
    ReleaseSRWLockExclusive(v6);
  return a2;
}

```

## disassembly

```asm
0x1800200e0  mov     [rsp-8+arg_18], rbx
0x1800200e5  push    rbp
0x1800200e6  push    rsi
0x1800200e7  push    rdi
0x1800200e8  push    r12
0x1800200ea  push    r13
0x1800200ec  push    r14
0x1800200ee  push    r15
0x1800200f0  lea     rbp, [rsp-27h]
0x1800200f5  sub     rsp, 0B0h
0x1800200fc  mov     rax, cs:__security_cookie
0x180020103  xor     rax, rsp
0x180020106  mov     [rbp+57h+var_40], rax
0x18002010a  mov     ebx, r8d
0x18002010d  mov     r14, rdx
0x180020110  mov     r15, rcx
0x180020113  lea     rsi, [rcx+8]
0x180020117  mov     rcx, rsi; SRWLock
0x18002011a  call    cs:__imp_AcquireSRWLockExclusive
0x180020120  mov     [rbp+57h+var_80], rsi
0x180020124  mov     rax, [r15+30h]
0x180020128  dec     rax
0x18002012b  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002012f  ja      short loc_18002015E
0x180020131  mov     rcx, [rbp+5Fh]; this
0x180020135  mov     r9d, 8000FFFFh; char *
0x18002013b  lea     r8, aOnecoreVmDvSto; "onecore\\vm\\dv\\storage\\plan9\\dll\\w"...
0x180020142  mov     edx, 245h; void *
0x180020147  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18002014c  xor     edi, edi
0x18002014e  mov     [r14], dil
0x180020151  mov     dword ptr [r14+8], 0FFFFFFEAh
0x180020159  jmp     loc_18002036B
0x18002015e  mov     ecx, ebx
0x180020160  call    ?OpenFlagsToAccessMask@p9fs@@YAKW4OpenFlags@1@@Z; p9fs::OpenFlagsToAccessMask(p9fs::OpenFlags)
0x180020165  mov     r10d, eax
0x180020168  mov     [rbp+57h+var_78], eax
0x18002016b  test    eax, 0FFEDFF76h
0x180020170  jz      short loc_18002018E
0x180020172  mov     rax, [r15+48h]
0x180020176  test    byte ptr [rax+30h], 1
0x18002017a  jz      short loc_18002018E
0x18002017c  xor     edi, edi
0x18002017e  mov     [r14], dil
0x180020181  mov     dword ptr [r14+8], 0FFFFFFE2h
0x180020189  jmp     loc_18002036B
0x18002018e  mov     r8, [r15+48h]
0x180020192  mov     rcx, [r8+70h]
0x180020196  xor     edi, edi
0x180020198  mov     [rbp+57h+pio], rdi
0x18002019c  mov     [rbp+57h+var_68], rdi
0x1800201a0  mov     [rbp+57h+pv], rdi
0x1800201a4  mov     [rbp+57h+var_58], rdi
0x1800201a8  mov     rax, [rcx]
0x1800201ab  mov     edx, ebx
0x1800201ad  and     edx, 10000h
0x1800201b3  bts     edx, 12h
0x1800201b7  shr     edx, 10h
0x1800201ba  lea     r9, [r15+10h]
0x1800201be  mov     [rsp+0E0h+var_98], rdi
0x1800201c3  lea     r11, [rbp+57h+pio]
0x1800201c7  mov     [rsp+0E0h+var_A0], r11
0x1800201cc  lea     r11, [rbp+57h+pv]
0x1800201d0  mov     [rsp+0E0h+var_A8], r11
0x1800201d5  mov     [rsp+0E0h+var_B0], edx
0x1800201d9  mov     [rsp+0E0h+var_B8], 1
0x1800201e1  mov     [rsp+0E0h+var_C0], r10d
0x1800201e6  mov     r8, [r8+18h]
0x1800201ea  lea     rdx, [rbp+57h+var_50]
0x1800201ee  mov     rax, [rax+8]
0x1800201f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800201f7  nop
0x1800201f8  mov     al, [rbp+57h+var_50]
0x1800201fb  test    al, al
0x1800201fd  jnz     short loc_18002020E
0x1800201ff  mov     eax, dword ptr [rbp+57h+hObject]
0x180020202  mov     [r14], dil
0x180020205  mov     [r14+8], eax
0x180020209  jmp     loc_18002036B
0x18002020e  bt      ebx, 9
0x180020212  jnb     short loc_180020241
0x180020214  xor     edx, edx
0x180020216  mov     rcx, [rbp+57h+hObject]
0x18002021a  call    cs:__imp_LxUtilFsTruncate
0x180020220  test    eax, eax
0x180020222  jz      short loc_18002023E
0x180020224  mov     [r14], dil
0x180020227  mov     [r14+8], eax
0x18002022b  cmp     [rbp+57h+var_50], dil
0x18002022f  jz      loc_18002036B
0x180020235  mov     rcx, [rbp+57h+hObject]
0x180020239  jmp     loc_18002035A
0x18002023e  mov     al, [rbp+57h+var_50]
0x180020241  test    al, al
0x180020243  setz    al
0x180020246  mov     rcx, [rbp+5Fh]; this
0x18002024a  test    al, al
0x18002024c  jnz     loc_1800203B5
0x180020252  mov     rdx, [rbp+57h+hObject]; FileHandle
0x180020256  lea     rcx, [rbp+57h+pv]; pv
0x18002025a  call    ??0CoroutineIoIssuer@p9fs@@QEAA@PEAX@Z; p9fs::CoroutineIoIssuer::CoroutineIoIssuer(void *)
0x18002025f  mov     r12, rax
0x180020262  lea     r13, [r15+38h]
0x180020266  cmp     r13, rax
0x180020269  jz      short loc_1800202B1
0x18002026b  mov     rax, [rax]
0x18002026e  mov     [rbp+57h+var_80], rax
0x180020272  mov     rax, [r13+0]
0x180020276  mov     [rbp+57h+pio], rax
0x18002027a  test    rax, rax
0x18002027d  jz      short loc_1800202A5
0x18002027f  call    cs:__imp_GetLastError
0x180020285  mov     ebx, eax
0x180020287  xor     edx, edx; fCancelPendingCallbacks
0x180020289  mov     rcx, [rbp+57h+pio]; pio
0x18002028d  call    cs:__imp_WaitForThreadpoolIoCallbacks
0x180020293  mov     rcx, [rbp+57h+pio]; pio
0x180020297  call    cs:__imp_CloseThreadpoolIo
0x18002029d  mov     ecx, ebx; dwErrCode
0x18002029f  call    cs:__imp_SetLastError
0x1800202a5  mov     rax, [rbp+57h+var_80]
0x1800202a9  mov     [r13+0], rax
0x1800202ad  mov     [r12], rdi
0x1800202b1  mov     rax, [r12+8]
0x1800202b6  mov     [r13+8], rax
0x1800202ba  mov     rbx, [rbp+57h+pv]
0x1800202be  test    rbx, rbx
0x1800202c1  jz      short loc_1800202D7
0x1800202c3  xor     edx, edx; fCancelPendingCallbacks
0x1800202c5  mov     rcx, rbx; pio
0x1800202c8  call    cs:__imp_WaitForThreadpoolIoCallbacks
0x1800202ce  mov     rcx, rbx; pio
0x1800202d1  call    cs:__imp_CloseThreadpoolIo
0x1800202d7  mov     dl, [rbp+57h+var_50]
0x1800202da  test    dl, dl
0x1800202dc  setz    al
0x1800202df  mov     rcx, [rbp+5Fh]; this
0x1800202e3  test    al, al
0x1800202e5  jnz     loc_1800203A3
0x1800202eb  lea     rax, [rbp+57h+hObject]
0x1800202ef  lea     r12, [r15+30h]
0x1800202f3  cmp     r12, rax
0x1800202f6  jz      short loc_18002033C
0x1800202f8  mov     rax, [rbp+57h+hObject]
0x1800202fc  mov     [rbp+57h+var_80], rax
0x180020300  mov     r13, [r12]
0x180020304  lea     rax, [r13-1]
0x180020308  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002030c  ja      short loc_18002032A
0x18002030e  call    cs:__imp_GetLastError
0x180020314  mov     ebx, eax
0x180020316  mov     rcx, r13; hObject
0x180020319  call    cs:__imp_CloseHandle
0x18002031f  mov     ecx, ebx; dwErrCode
0x180020321  call    cs:__imp_SetLastError
0x180020327  mov     dl, [rbp+57h+var_50]
0x18002032a  mov     rax, [rbp+57h+var_80]
0x18002032e  mov     [r12], rax
0x180020332  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180020336  mov     [rbp+57h+hObject], rcx
0x18002033a  jmp     short loc_180020340
0x18002033c  mov     rcx, [rbp+57h+hObject]; hObject
0x180020340  mov     eax, [rbp+57h+var_78]
0x180020343  mov     [r15+58h], eax
0x180020347  mov     byte ptr [r14], 1
0x18002034b  movups  xmm0, xmmword ptr [r15+78h]
0x180020350  movdqu  xmmword ptr [r14+8], xmm0
0x180020356  test    dl, dl
0x180020358  jz      short loc_18002036B
0x18002035a  lea     rax, [rcx-1]
0x18002035e  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180020362  ja      short loc_18002036B
0x180020364  call    cs:__imp_CloseHandle
0x18002036a  nop
0x18002036b  test    rsi, rsi
0x18002036e  jz      short loc_180020379
0x180020370  mov     rcx, rsi; SRWLock
0x180020373  call    cs:__imp_ReleaseSRWLockExclusive
0x180020379  mov     rax, r14
0x18002037c  mov     rcx, [rbp+57h+var_40]
0x180020380  xor     rcx, rsp; StackCookie
0x180020383  call    __security_check_cookie
0x180020388  mov     rbx, [rsp+0E0h+arg_18]
0x180020390  add     rsp, 0B0h
0x180020397  pop     r15
0x180020399  pop     r14
0x18002039b  pop     r13
0x18002039d  pop     r12
0x18002039f  pop     rdi
0x1800203a0  pop     rsi
0x1800203a1  pop     rbp
0x1800203a2  retn
0x1800203a3  lea     r8, aOnecoreVmIncEx; "onecore\\vm\\inc\\expected.h"
0x1800203aa  mov     edx, 139h; void *
0x1800203af  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800203b5  lea     r8, aOnecoreVmIncEx; "onecore\\vm\\inc\\expected.h"
0x1800203bc  mov     edx, 139h; void *
0x1800203c1  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
