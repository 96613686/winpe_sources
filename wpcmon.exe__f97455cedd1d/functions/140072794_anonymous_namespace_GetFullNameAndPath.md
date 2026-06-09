# _anonymous_namespace_::GetFullNameAndPath

- ea: `0x140072794`
- end: `0x140072aaa`
- name: `_anonymous_namespace_::GetFullNameAndPath`
- size: `790`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x140072ab0`
- `0x140073388`

## callees

- `0x140006338`
- `0x140009858`
- `0x14000b814`
- `0x14001f6b4`
- `0x140060f58`
- `0x140072794`
- `0x1400a8010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1400728b6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1400728fa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1400728b6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1400728fa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x140072863`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x140072872`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x140072863`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x140072872`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall anonymous_namespace_::GetFullNameAndPath(__int64 a1, __int64 a2)
{
  int v4; // eax
  int v5; // edi
  int v6; // eax
  int v7; // edi
  int v8; // eax
  int v9; // edi
  int v10; // eax
  int v11; // edi
  int v12; // eax
  int v13; // edi
  PCWSTR StringRawBuffer; // rdi
  PCWSTR v15; // rax
  unsigned __int64 v16; // r8
  __int64 v17; // rcx
  __int64 (__fastcall ***v18)(_QWORD, GUID *, _QWORD *); // rcx
  __int64 v19; // rcx
  HSTRING string; // [rsp+28h] [rbp-38h] BYREF
  HSTRING v22; // [rsp+30h] [rbp-30h] BYREF
  _BYTE pExceptionObject[40]; // [rsp+38h] [rbp-28h] BYREF
  __int64 v24; // [rsp+98h] [rbp+38h] BYREF
  __int64 (__fastcall ***v25)(_QWORD, GUID *, __int64 *); // [rsp+A0h] [rbp+40h] BYREF
  __int64 v26; // [rsp+A8h] [rbp+48h] BYREF

  v26 = 0;
  v4 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)a2 + 48LL))(a2, &v26);
  v5 = v4;
  if ( v4 < 0 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        12,
        WPP_0847ce96184e3f024f3fa6ccac8aefb7_Traceguids,
        (unsigned int)v4);
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, v5);
    throw (ErrorCodeException *)pExceptionObject;
  }
  v22 = 0;
  v6 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v26 + 96LL))(v26, &v22);
  v7 = v6;
  if ( v6 < 0 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        13,
        WPP_0847ce96184e3f024f3fa6ccac8aefb7_Traceguids,
        (unsigned int)v6);
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, v7);
    throw (ErrorCodeException *)pExceptionObject;
  }
  v25 = 0;
  v8 = (*(__int64 (__fastcall **)(__int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)))(*(_QWORD *)a2 + 56LL))(
         a2,
         &v25);
  v9 = v8;
  if ( v8 < 0 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        14,
        WPP_0847ce96184e3f024f3fa6ccac8aefb7_Traceguids,
        (unsigned int)v8);
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, v9);
    throw (ErrorCodeException *)pExceptionObject;
  }
  v24 = 0;
  v10 = (**v25)(v25, &GUID_4207a996_ca2f_42f7_bde8_8b10457a7f30, &v24);
  v11 = v10;
  if ( v10 < 0 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        15,
        WPP_0847ce96184e3f024f3fa6ccac8aefb7_Traceguids,
        (unsigned int)v10);
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, v11);
    throw (ErrorCodeException *)pExceptionObject;
  }
  string = 0;
  v12 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v24 + 96LL))(v24, &string);
  v13 = v12;
  if ( v12 < 0 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        16,
        WPP_0847ce96184e3f024f3fa6ccac8aefb7_Traceguids,
        (unsigned int)v12);
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, v13);
    throw (ErrorCodeException *)pExceptionObject;
  }
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  v15 = WindowsGetStringRawBuffer(v22, 0);
  *(_OWORD *)a1 = 0;
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 24) = 0;
  v16 = -1;
  do
    ++v16;
  while ( v15[v16] );
  std::wstring::_Construct<1,unsigned short const *>((char **)a1, v15, v16);
  std::wstring::wstring(a1 + 32, StringRawBuffer);
  if ( string )
    WindowsDeleteString(string);
  v17 = v24;
  if ( v24 )
  {
    v24 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
  }
  v18 = v25;
  if ( v25 )
  {
    v25 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v18)[2])(v18);
  }
  if ( v22 )
    WindowsDeleteString(v22);
  v19 = v26;
  if ( v26 )
  {
    v26 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
  }
  return a1;
}

```

## disassembly

```asm
0x140072794  mov     [rsp-28h+arg_0], rcx
0x140072799  push    rbp
0x14007279a  push    rbx
0x14007279b  push    rsi
0x14007279c  push    rdi
0x14007279d  push    r14
0x14007279f  mov     rbp, rsp
0x1400727a2  sub     rsp, 60h
0x1400727a6  mov     rsi, rdx
0x1400727a9  mov     rbx, rcx
0x1400727ac  xor     r14d, r14d
0x1400727af  mov     [rbp+arg_18], r14
0x1400727b3  mov     rax, [rdx]
0x1400727b6  lea     rdx, [rbp+arg_18]
0x1400727ba  mov     rcx, rsi
0x1400727bd  mov     rax, [rax+30h]
0x1400727c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400727c6  mov     edi, eax
0x1400727c8  test    eax, eax
0x1400727ca  js      loc_140072976
0x1400727d0  mov     [rbp+var_30], r14
0x1400727d4  mov     rcx, [rbp+arg_18]
0x1400727d8  mov     rax, [rcx]
0x1400727db  lea     rdx, [rbp+var_30]
0x1400727df  mov     rax, [rax+60h]
0x1400727e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400727e8  mov     edi, eax
0x1400727ea  test    eax, eax
0x1400727ec  js      loc_1400729C3
0x1400727f2  mov     [rbp+arg_10], r14
0x1400727f6  mov     rax, [rsi]
0x1400727f9  lea     rdx, [rbp+arg_10]
0x1400727fd  mov     rcx, rsi
0x140072800  mov     rax, [rax+38h]
0x140072804  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140072809  mov     edi, eax
0x14007280b  test    eax, eax
0x14007280d  js      loc_140072A10
0x140072813  mov     [rbp+arg_8], r14
0x140072817  mov     rcx, [rbp+arg_10]
0x14007281b  mov     rax, [rcx]
0x14007281e  lea     r8, [rbp+arg_8]
0x140072822  lea     rdx, _GUID_4207a996_ca2f_42f7_bde8_8b10457a7f30
0x140072829  mov     rax, [rax]
0x14007282c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140072831  mov     edi, eax
0x140072833  test    eax, eax
0x140072835  js      loc_140072A5D
0x14007283b  mov     [rbp+string], r14
0x14007283f  mov     rcx, [rbp+arg_8]
0x140072843  mov     rax, [rcx]
0x140072846  lea     rdx, [rbp+string]
0x14007284a  mov     rax, [rax+60h]
0x14007284e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140072853  mov     edi, eax
0x140072855  test    eax, eax
0x140072857  js      loc_140072929
0x14007285d  xor     edx, edx; length
0x14007285f  mov     rcx, [rbp+string]; string
0x140072863  call    cs:__imp_WindowsGetStringRawBuffer
0x140072869  mov     rdi, rax
0x14007286c  xor     edx, edx; length
0x14007286e  mov     rcx, [rbp+var_30]; string
0x140072872  call    cs:__imp_WindowsGetStringRawBuffer
0x140072878  xorps   xmm0, xmm0
0x14007287b  movups  xmmword ptr [rbx], xmm0
0x14007287e  mov     [rbx+10h], r14
0x140072882  mov     [rbx+18h], r14
0x140072886  or      r8, 0FFFFFFFFFFFFFFFFh
0x14007288a  inc     r8
0x14007288d  cmp     [rax+r8*2], r14w
0x140072892  jnz     short loc_14007288A
0x140072894  mov     rdx, rax
0x140072897  mov     rcx, rbx
0x14007289a  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x14007289f  nop
0x1400728a0  lea     rcx, [rbx+20h]
0x1400728a4  mov     rdx, rdi
0x1400728a7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1400728ac  nop
0x1400728ad  mov     rcx, [rbp+string]; string
0x1400728b1  test    rcx, rcx
0x1400728b4  jz      short loc_1400728BD
0x1400728b6  call    cs:__imp_WindowsDeleteString
0x1400728bc  nop
0x1400728bd  mov     rcx, [rbp+arg_8]
0x1400728c1  test    rcx, rcx
0x1400728c4  jz      short loc_1400728D7
0x1400728c6  mov     [rbp+arg_8], r14
0x1400728ca  mov     rax, [rcx]
0x1400728cd  mov     rax, [rax+10h]
0x1400728d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400728d6  nop
0x1400728d7  mov     rcx, [rbp+arg_10]
0x1400728db  test    rcx, rcx
0x1400728de  jz      short loc_1400728F1
0x1400728e0  mov     [rbp+arg_10], r14
0x1400728e4  mov     rax, [rcx]
0x1400728e7  mov     rax, [rax+10h]
0x1400728eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400728f0  nop
0x1400728f1  mov     rcx, [rbp+var_30]; string
0x1400728f5  test    rcx, rcx
0x1400728f8  jz      short loc_140072901
0x1400728fa  call    cs:__imp_WindowsDeleteString
0x140072900  nop
0x140072901  mov     rcx, [rbp+arg_18]
0x140072905  test    rcx, rcx
0x140072908  jz      short loc_14007291B
0x14007290a  mov     [rbp+arg_18], r14
0x14007290e  mov     rax, [rcx]
0x140072911  mov     rax, [rax+10h]
0x140072915  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007291a  nop
0x14007291b  mov     rax, rbx
0x14007291e  add     rsp, 60h
0x140072922  pop     r14
0x140072924  pop     rdi
0x140072925  pop     rsi
0x140072926  pop     rbx
0x140072927  pop     rbp
0x140072928  retn
0x140072929  lea     rdx, WPP_GLOBAL_Control
0x140072930  mov     rcx, cs:WPP_GLOBAL_Control
0x140072937  cmp     rcx, rdx
0x14007293a  jz      short loc_14007295A
0x14007293c  test    byte ptr [rcx+1Ch], 1
0x140072940  jz      short loc_14007295A
0x140072942  mov     edx, 10h
0x140072947  mov     r9d, edi
0x14007294a  lea     r8, WPP_0847ce96184e3f024f3fa6ccac8aefb7_Traceguids
0x140072951  mov     rcx, [rcx+10h]
0x140072955  call    WPP_SF_d
0x14007295a  mov     edx, edi; int
0x14007295c  lea     rcx, [rbp+pExceptionObject]; this
0x140072960  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x140072965  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x14007296c  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x140072970  call    _CxxThrowException_0
0x140072976  lea     rdx, WPP_GLOBAL_Control
0x14007297d  mov     rcx, cs:WPP_GLOBAL_Control
0x140072984  cmp     rcx, rdx
0x140072987  jz      short loc_1400729A7
0x140072989  test    byte ptr [rcx+1Ch], 1
0x14007298d  jz      short loc_1400729A7
0x14007298f  mov     edx, 0Ch
0x140072994  mov     r9d, edi
0x140072997  lea     r8, WPP_0847ce96184e3f024f3fa6ccac8aefb7_Traceguids
0x14007299e  mov     rcx, [rcx+10h]
0x1400729a2  call    WPP_SF_d
0x1400729a7  mov     edx, edi; int
0x1400729a9  lea     rcx, [rbp+pExceptionObject]; this
0x1400729ad  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x1400729b2  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x1400729b9  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1400729bd  call    _CxxThrowException_0
0x1400729c3  lea     rdx, WPP_GLOBAL_Control
0x1400729ca  mov     rcx, cs:WPP_GLOBAL_Control
0x1400729d1  cmp     rcx, rdx
0x1400729d4  jz      short loc_1400729F4
0x1400729d6  test    byte ptr [rcx+1Ch], 1
0x1400729da  jz      short loc_1400729F4
0x1400729dc  mov     edx, 0Dh
0x1400729e1  mov     r9d, edi
0x1400729e4  lea     r8, WPP_0847ce96184e3f024f3fa6ccac8aefb7_Traceguids
0x1400729eb  mov     rcx, [rcx+10h]
0x1400729ef  call    WPP_SF_d
0x1400729f4  mov     edx, edi; int
0x1400729f6  lea     rcx, [rbp+pExceptionObject]; this
0x1400729fa  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x1400729ff  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x140072a06  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x140072a0a  call    _CxxThrowException_0
0x140072a10  lea     rdx, WPP_GLOBAL_Control
0x140072a17  mov     rcx, cs:WPP_GLOBAL_Control
0x140072a1e  cmp     rcx, rdx
0x140072a21  jz      short loc_140072A41
0x140072a23  test    byte ptr [rcx+1Ch], 1
0x140072a27  jz      short loc_140072A41
0x140072a29  mov     edx, 0Eh
0x140072a2e  mov     r9d, edi
0x140072a31  lea     r8, WPP_0847ce96184e3f024f3fa6ccac8aefb7_Traceguids
0x140072a38  mov     rcx, [rcx+10h]
0x140072a3c  call    WPP_SF_d
0x140072a41  mov     edx, edi; int
0x140072a43  lea     rcx, [rbp+pExceptionObject]; this
0x140072a47  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x140072a4c  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x140072a53  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x140072a57  call    _CxxThrowException_0
0x140072a5d  lea     rdx, WPP_GLOBAL_Control
0x140072a64  mov     rcx, cs:WPP_GLOBAL_Control
0x140072a6b  cmp     rcx, rdx
0x140072a6e  jz      short loc_140072A8E
0x140072a70  test    byte ptr [rcx+1Ch], 1
0x140072a74  jz      short loc_140072A8E
0x140072a76  mov     edx, 0Fh
0x140072a7b  mov     r9d, edi
0x140072a7e  lea     r8, WPP_0847ce96184e3f024f3fa6ccac8aefb7_Traceguids
0x140072a85  mov     rcx, [rcx+10h]
0x140072a89  call    WPP_SF_d
0x140072a8e  mov     edx, edi; int
0x140072a90  lea     rcx, [rbp+pExceptionObject]; this
0x140072a94  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x140072a99  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x140072aa0  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x140072aa4  call    _CxxThrowException_0
```
