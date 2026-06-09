# ConvertBlobToCMSketchAndSample(CXVariant *,uchar *)

- ea: `0x1008173d0`
- end: `0x100817642`
- name: `?ConvertBlobToCMSketchAndSample@@YAXPEAVCXVariant@@PEAE@Z`
- size: `626`
- prototype: `void __fastcall(struct CXVariant *, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x100401170`
- `0x1004024b0`
- `0x1008173d0`

## import_xrefs

- `sqldk!SystemThread_TlsIndex` at `0x100817512`
- `sqldk!SystemThread_TlsOffset` at `0x10081751b`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100817536`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100817536`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1008174fc`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1008174fc`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1008174c7`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1008174c7`

## string_xrefs

- `0x1008174f0`: `x_cbMaxCMSketchWithHeader == cBytesRead`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall ConvertBlobToCMSketchAndSample(struct CXVariant *a1, unsigned __int8 *a2)
{
  __int64 v3; // r15
  __int64 v4; // r14
  __int64 v5; // rdi
  __int64 v6; // rbx
  __int64 v7; // rax
  __int64 v8; // rax
  unsigned int v9; // [rsp+30h] [rbp-D0h] BYREF
  void **v10; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v11; // [rsp+40h] [rbp-C0h]
  __int64 v12; // [rsp+48h] [rbp-B8h]
  __int64 v13; // [rsp+50h] [rbp-B0h]
  int v14; // [rsp+58h] [rbp-A8h]
  __int64 v15; // [rsp+60h] [rbp-A0h]
  __int64 v16; // [rsp+68h] [rbp-98h]
  _QWORD v17[2]; // [rsp+70h] [rbp-90h] BYREF
  int v18; // [rsp+80h] [rbp-80h]
  __int64 v19; // [rsp+88h] [rbp-78h]
  _BYTE v20[8]; // [rsp+90h] [rbp-70h] BYREF
  __int64 v21; // [rsp+98h] [rbp-68h]
  __int64 v22; // [rsp+A0h] [rbp-60h]
  __int128 v23; // [rsp+A8h] [rbp-58h]
  void ***v24; // [rsp+B8h] [rbp-48h]
  __int64 v25; // [rsp+C0h] [rbp-40h]
  __int16 v26; // [rsp+2008h] [rbp+1F08h]
  int v27; // [rsp+2014h] [rbp+1F14h]
  void **v28; // [rsp+2018h] [rbp+1F18h]
  _BYTE v29[16]; // [rsp+2020h] [rbp+1F20h] BYREF
  __int64 v30; // [rsp+2030h] [rbp+1F30h]

  v16 = -2;
  v3 = *((_QWORD *)a2 + 3);
  v15 = 0;
  v4 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)a1 + 1) + 8LL))(*((_QWORD *)a1 + 1), 0);
  v15 = v4;
  v10 = &CByteLobReader::`vftable';
  v11 = 0;
  v12 = 0;
  v13 = 0;
  (*(void (__fastcall **)(__int64, _BYTE *, _QWORD))(*(_QWORD *)v4 + 72LL))(v4, v29, 0);
  v12 = v30;
  v11 = v4;
  v9 = 0;
  if ( (*(unsigned int (__fastcall **)(__int64, _QWORD, unsigned __int8 *, __int64, unsigned int *))(*(_QWORD *)v4 + 24LL))(
         v4,
         0,
         a2,
         3805624,
         &v9) )
  {
    ex_raise(71, 2, 20, 99);
  }
  v13 += v9;
  if ( v9 != 3805624 )
    utassert_fail(1u, "x_cbMaxCMSketchWithHeader == cBytesRead", "ApproxAggEsIntrinsic.cpp", 1867, 0);
  v5 = *(_QWORD *)a2 - *((_QWORD *)a2 + 1);
  v6 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v7 = *(_QWORD *)(v6 + 256);
  if ( !v7 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v7 = *(_QWORD *)(v6 + 256);
  }
  v8 = *(_QWORD *)(v7 + 1000);
  v17[0] = &CBlobSample::`vbtable';
  v28 = &CBlobSample::`vftable';
  v27 = 0;
  v17[1] = v5;
  v18 = 1;
  v19 = v8;
  v21 = 0;
  v22 = -1;
  v23 = 0u;
  v24 = &v10;
  v25 = 0;
  v14 = 0;
  ((void (__fastcall *)(void ***, _BYTE *, __int64))v10[5])(&v10, v20, 40);
  v26 = 0;
  *((_QWORD *)a2 + 3) = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v3 + 56LL))(
                          v3,
                          (char *)v17 + *(int *)(v17[0] + 4LL));
  v10 = &ILobReader::`vftable';
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
}

```

## disassembly

```asm
0x1008173d0  push    rbp
0x1008173d2  push    rsi
0x1008173d3  push    rdi
0x1008173d4  push    r12
0x1008173d6  push    r13
0x1008173d8  push    r14
0x1008173da  push    r15
0x1008173dc  lea     rbp, [rsp-1F80h]
0x1008173e4  mov     eax, 2080h
0x1008173e9  call    _alloca_probe
0x1008173ee  sub     rsp, rax
0x1008173f1  mov     [rsp+20B0h+var_2048], 0FFFFFFFFFFFFFFFEh
0x1008173fa  mov     [rsp+20B0h+arg_10], rbx
0x100817402  mov     rax, cs:__security_cookie
0x100817409  xor     rax, rsp
0x10081740c  mov     [rbp+1FB0h+var_40], rax
0x100817413  mov     rsi, rdx
0x100817416  mov     r15, [rdx+18h]
0x10081741a  xor     r12d, r12d
0x10081741d  mov     [rsp+20B0h+var_2050], r12
0x100817422  mov     rcx, [rcx+8]
0x100817426  mov     rax, [rcx]
0x100817429  xor     edx, edx
0x10081742b  call    qword ptr [rax+8]
0x10081742e  mov     r14, rax
0x100817431  mov     [rsp+20B0h+var_2050], rax
0x100817436  lea     r13, ??_7ILobReader@@6B@; const ILobReader::`vftable'
0x10081743d  mov     [rsp+20B0h+var_2078], r13
0x100817442  lea     rax, ??_7CByteLobReader@@6B@; const CByteLobReader::`vftable'
0x100817449  mov     [rsp+20B0h+var_2078], rax
0x10081744e  mov     [rsp+20B0h+var_2070], r12
0x100817453  mov     [rsp+20B0h+var_2068], r12
0x100817458  mov     [rsp+20B0h+var_2060], r12
0x10081745d  mov     [rsp+20B0h+var_2068], r12
0x100817462  mov     [rsp+20B0h+var_2060], r12
0x100817467  mov     rax, [r14]
0x10081746a  xor     r8d, r8d
0x10081746d  lea     rdx, [rbp+1FB0h+var_90]
0x100817474  mov     rcx, r14
0x100817477  call    qword ptr [rax+48h]
0x10081747a  mov     rax, [rbp+1FB0h+var_80]
0x100817481  mov     [rsp+20B0h+var_2068], rax
0x100817486  mov     [rsp+20B0h+var_2070], r14
0x10081748b  mov     [rsp+20B0h+var_2080], r12d
0x100817490  mov     rax, [r14]
0x100817493  lea     rcx, [rsp+20B0h+var_2080]
0x100817498  mov     [rsp+20B0h+var_2090], rcx
0x10081749d  mov     r9d, 3A11B8h
0x1008174a3  mov     r8, rsi
0x1008174a6  mov     rdx, [rsp+20B0h+var_2060]
0x1008174ab  mov     rcx, r14
0x1008174ae  call    qword ptr [rax+18h]
0x1008174b1  test    eax, eax
0x1008174b3  jz      short loc_1008174CD
0x1008174b5  lea     edx, [r12+2]
0x1008174ba  lea     ecx, [rdx+45h]
0x1008174bd  lea     r9d, [r12+63h]
0x1008174c2  lea     r8d, [r12+14h]
0x1008174c7  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x1008174cd  mov     ecx, [rsp+20B0h+var_2080]
0x1008174d1  add     [rsp+20B0h+var_2060], rcx
0x1008174d6  cmp     ecx, 3A11B8h
0x1008174dc  jz      short loc_100817502
0x1008174de  mov     [rsp+20B0h+var_2090], r12
0x1008174e3  mov     r9d, 74Bh
0x1008174e9  lea     r8, aApproxaggesint; "ApproxAggEsIntrinsic.cpp"
0x1008174f0  lea     rdx, aXCbmaxcmsketch; "x_cbMaxCMSketchWithHeader == cBytesRead"
0x1008174f7  mov     ecx, 1
0x1008174fc  call    cs:__imp_?utassert_fail@@YAXIPEBD0H0ZZ; utassert_fail(uint,char const *,char const *,int,char const *,...)
0x100817502  mov     rdi, [rsi]
0x100817505  sub     rdi, [rsi+8]
0x100817509  mov     rdx, gs:58h
0x100817512  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100817519  mov     ecx, [rax]
0x10081751b  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100817522  mov     ebx, [rax]
0x100817524  add     rbx, [rdx+rcx*8]
0x100817528  mov     rax, [rbx+100h]
0x10081752f  test    rax, rax
0x100817532  jnz     short loc_100817543
0x100817534  xor     ecx, ecx
0x100817536  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10081753c  mov     rax, [rbx+100h]
0x100817543  mov     rax, [rax+3E8h]
0x10081754a  lea     rcx, ??_8CBlobSample@@7B@; const CBlobSample::`vbtable'
0x100817551  mov     [rsp+20B0h+var_2040], rcx
0x100817556  lea     rcx, ??_7CBlobSample@@6B@; const CBlobSample::`vftable'
0x10081755d  mov     [rbp+1FB0h+var_98], rcx
0x100817564  mov     [rbp+1FB0h+var_9C], r12d
0x10081756b  mov     [rsp+20B0h+var_2038], rdi
0x100817570  mov     [rbp+1FB0h+var_2030], 1
0x100817577  mov     [rbp+1FB0h+var_2028], rax
0x10081757b  xorps   xmm0, xmm0
0x10081757e  movups  [rbp+1FB0h+var_2018], xmm0
0x100817582  movups  [rbp+1FB0h+var_2008], xmm0
0x100817586  mov     byte ptr [rbp+1FB0h+var_2018], 0
0x10081758a  mov     dword ptr [rbp+1FB0h+var_2018+4], r12d
0x10081758e  mov     qword ptr [rbp+1FB0h+var_2018+8], 0FFFFFFFFFFFFFFFFh
0x100817596  mov     dword ptr [rbp+1FB0h+var_2008], r12d
0x10081759a  mov     qword ptr [rbp+1FB0h+var_2008+8], 0
0x1008175a2  lea     rax, [rsp+20B0h+var_2078]
0x1008175a7  mov     [rbp+1FB0h+var_1FF8], rax
0x1008175ab  mov     [rbp+1FB0h+var_1FF0], r12
0x1008175af  mov     [rsp+20B0h+var_2058], r12d
0x1008175b4  lea     rax, [rsp+20B0h+var_2058]
0x1008175b9  mov     [rsp+20B0h+var_2090], rax
0x1008175be  mov     r9d, 28h ; '('
0x1008175c4  mov     r8d, r9d
0x1008175c7  lea     rdx, [rbp+1FB0h+var_2020]
0x1008175cb  lea     rcx, [rsp+20B0h+var_2078]
0x1008175d0  mov     rax, [rsp+20B0h+var_2078]
0x1008175d5  call    qword ptr [rax+28h]
0x1008175d8  mov     [rbp+1FB0h+var_A8], r12w
0x1008175e0  mov     rax, [rsp+20B0h+var_2040]
0x1008175e5  movsxd  rdx, dword ptr [rax+4]
0x1008175e9  lea     rax, [rsp+20B0h+var_2040]
0x1008175ee  add     rdx, rax
0x1008175f1  mov     rax, [r15]
0x1008175f4  mov     rcx, r15
0x1008175f7  call    qword ptr [rax+38h]
0x1008175fa  mov     [rsi+18h], rax
0x1008175fe  lea     rax, ??_7CByteLobReader@@6B@; const CByteLobReader::`vftable'
0x100817605  mov     [rsp+20B0h+var_2078], rax
0x10081760a  mov     [rsp+20B0h+var_2078], r13
0x10081760f  mov     rax, [r14]
0x100817612  mov     rcx, r14
0x100817615  call    qword ptr [rax+10h]
0x100817618  mov     rcx, [rbp+1FB0h+var_40]
0x10081761f  xor     rcx, rsp; StackCookie
0x100817622  call    __security_check_cookie
0x100817627  mov     rbx, [rsp+20B0h+arg_10]
0x10081762f  add     rsp, 2080h
0x100817636  pop     r15
0x100817638  pop     r14
0x10081763a  pop     r13
0x10081763c  pop     r12
0x10081763e  pop     rdi
0x10081763f  pop     rsi
0x100817640  pop     rbp
0x100817641  retn
```
