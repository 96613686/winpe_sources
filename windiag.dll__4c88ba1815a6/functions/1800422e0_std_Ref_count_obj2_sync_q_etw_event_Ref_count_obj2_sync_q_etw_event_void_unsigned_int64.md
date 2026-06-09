# std::_Ref_count_obj2<sync_q<etw_event>>::_Ref_count_obj2<sync_q<etw_event>>(void * &&,unsigned __int64 &)

- ea: `0x1800422e0`
- end: `0x180042499`
- name: `??$?0PEAXAEA_K@?$_Ref_count_obj2@U?$sync_q@Uetw_event@@@@@std@@QEAA@$$QEAPEAXAEA_K@Z`
- size: `441`
- prototype: `__int64 __fastcall(__int64, void **, __int64 *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18004d8e4`

## callees

- `0x180004510`
- `0x18000491c`
- `0x180005520`
- `0x18003af08`
- `0x1800422e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042415`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042415`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800423f0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18004242c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800423f0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18004242c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180042406`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180042406`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x1800423fd`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x1800423fd`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x1800423cf`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x1800423cf`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall std::_Ref_count_obj2<sync_q<etw_event>>::_Ref_count_obj2<sync_q<etw_event>>(
        __int64 a1,
        void **a2,
        __int64 *a3)
{
  __int64 v4; // rsi
  __int64 v5; // rdi
  void *v6; // rbp
  _QWORD *v7; // rbx
  _QWORD *v8; // rax
  PTP_WAIT ThreadpoolWait; // rax
  struct _TP_WAIT *v10; // rbx
  DWORD LastError; // eax
  _BYTE pExceptionObject[1072]; // [rsp+40h] [rbp-468h] BYREF

  *(_DWORD *)(a1 + 8) = 1;
  *(_DWORD *)(a1 + 12) = 1;
  *(_QWORD *)a1 = &std::_Ref_count_obj2<sync_q<etw_event>>::`vftable';
  v4 = a1 + 16;
  v5 = *a3;
  v6 = *a2;
  *(_QWORD *)(a1 + 16) = 2;
  *(_OWORD *)(a1 + 40) = 0;
  *(_OWORD *)(a1 + 56) = 0;
  *(_OWORD *)(a1 + 72) = 0;
  *(_QWORD *)(a1 + 24) = 0;
  *(_QWORD *)(a1 + 32) = 0;
  *(_DWORD *)(a1 + 88) = -1;
  *(_DWORD *)(a1 + 92) = 0;
  *(_QWORD *)(a1 + 96) = 0;
  *(_QWORD *)(a1 + 104) = 0;
  *(_OWORD *)(a1 + 112) = 0;
  *(_OWORD *)(a1 + 128) = 0;
  *(_OWORD *)(a1 + 144) = 0;
  *(_QWORD *)(a1 + 160) = 0;
  v7 = (_QWORD *)(a1 + 168);
  *(_QWORD *)(a1 + 168) = 0;
  *(_QWORD *)(a1 + 176) = 0;
  *(_QWORD *)(a1 + 184) = 0;
  *(_QWORD *)(a1 + 192) = 0;
  *(_QWORD *)(a1 + 200) = 0;
  v8 = operator new(0x10u);
  v8[1] = 0;
  *v7 = v8;
  *v8 = v7;
  *(_QWORD *)(v4 + 192) = v5;
  *(_QWORD *)(v4 + 200) = 0;
  *(_WORD *)(v4 + 208) = 0;
  if ( v6 )
  {
    ThreadpoolWait = CreateThreadpoolWait(
                       _lambda_d002aa1fe23be5b5afc0d1240c688f12_::_lambda_invoker_cdecl_<_TP_CALLBACK_INSTANCE *,void *,_TP_WAIT *,long>,
                       (PVOID)v4,
                       0);
    v10 = *(struct _TP_WAIT **)(v4 + 200);
    *(_QWORD *)(v4 + 200) = ThreadpoolWait;
    if ( v10 )
    {
      SetThreadpoolWait(v10, 0, 0);
      WaitForThreadpoolWaitCallbacks(v10, 1);
      CloseThreadpoolWait(v10);
    }
    if ( !*(_QWORD *)(v4 + 200) )
    {
      LastError = GetLastError();
      if ( LastError )
      {
        windiag::system_exception::system_exception(
          (windiag::system_exception *)pExceptionObject,
          LastError,
          0,
          "[%s:%d] failed; ",
          "sync_q",
          27);
        throw (windiag::system_exception *)pExceptionObject;
      }
    }
    SetThreadpoolWait(*(PTP_WAIT *)(v4 + 200), v6, 0);
  }
  return a1;
}

```

## disassembly

```asm
0x1800422e0  mov     [rsp+arg_10], rbx
0x1800422e5  push    rbp
0x1800422e6  push    rsi
0x1800422e7  push    rdi
0x1800422e8  push    r14
0x1800422ea  push    r15
0x1800422ec  sub     rsp, 480h
0x1800422f3  mov     rax, cs:__security_cookie
0x1800422fa  xor     rax, rsp
0x1800422fd  mov     [rsp+4A8h+var_38], rax
0x180042305  mov     r14, rcx
0x180042308  mov     dword ptr [rcx+8], 1
0x18004230f  mov     dword ptr [rcx+0Ch], 1
0x180042316  lea     rax, ??_7?$_Ref_count_obj2@U?$sync_q@Uetw_event@@@@@std@@6B@; const std::_Ref_count_obj2<sync_q<etw_event>>::`vftable'
0x18004231d  mov     [rcx], rax
0x180042320  lea     rsi, [rcx+10h]
0x180042324  mov     [rsp+4A8h+var_478], rsi
0x180042329  mov     rdi, [r8]
0x18004232c  mov     rbp, [rdx]
0x18004232f  mov     qword ptr [rsi], 2
0x180042336  xorps   xmm0, xmm0
0x180042339  movups  xmmword ptr [rsi+18h], xmm0
0x18004233d  movups  xmmword ptr [rsi+28h], xmm0
0x180042341  movups  xmmword ptr [rsi+38h], xmm0
0x180042345  xor     r15d, r15d
0x180042348  mov     [rsi+8], r15
0x18004234c  mov     [rsi+10h], r15
0x180042350  mov     dword ptr [rsi+48h], 0FFFFFFFFh
0x180042357  mov     [rsi+4Ch], r15d
0x18004235b  mov     [rsi+50h], r15
0x18004235f  mov     [rsi+58h], r15
0x180042363  xor     eax, eax
0x180042365  movups  xmmword ptr [rsi+60h], xmm0
0x180042369  movups  xmmword ptr [rsi+70h], xmm0
0x18004236d  movups  xmmword ptr [rsi+80h], xmm0
0x180042374  mov     [rsi+90h], rax
0x18004237b  lea     rbx, [rsi+98h]
0x180042382  mov     [rbx], r15
0x180042385  mov     [rbx+8], r15
0x180042389  mov     [rbx+10h], r15
0x18004238d  mov     [rbx+18h], r15
0x180042391  mov     [rbx+20h], r15
0x180042395  lea     ecx, [rax+10h]; Size
0x180042398  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004239d  mov     [rax+8], r15
0x1800423a1  mov     [rbx], rax
0x1800423a4  mov     [rax], rbx
0x1800423a7  mov     [rsi+0C0h], rdi
0x1800423ae  mov     [rsi+0C8h], r15
0x1800423b5  mov     [rsi+0D0h], r15w
0x1800423bd  test    rbp, rbp
0x1800423c0  jz      short loc_180042433
0x1800423c2  xor     r8d, r8d; pcbe
0x1800423c5  mov     rdx, rsi; pv
0x1800423c8  lea     rcx, ??$_lambda_invoker_cdecl_@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@_lambda_d002aa1fe23be5b5afc0d1240c688f12_@@CA?A_PPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x1800423cf  call    cs:__imp_CreateThreadpoolWait
0x1800423d5  mov     rbx, [rsi+0C8h]
0x1800423dc  mov     [rsi+0C8h], rax
0x1800423e3  test    rbx, rbx
0x1800423e6  jz      short loc_18004240C
0x1800423e8  xor     r8d, r8d; pftTimeout
0x1800423eb  xor     edx, edx; h
0x1800423ed  mov     rcx, rbx; pwa
0x1800423f0  call    cs:__imp_SetThreadpoolWait
0x1800423f6  lea     edx, [r15+1]; fCancelPendingCallbacks
0x1800423fa  mov     rcx, rbx; pwa
0x1800423fd  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x180042403  mov     rcx, rbx; pwa
0x180042406  call    cs:__imp_CloseThreadpoolWait
0x18004240c  cmp     [rsi+0C8h], r15
0x180042413  jnz     short loc_18004241F
0x180042415  call    cs:__imp_GetLastError
0x18004241b  test    eax, eax
0x18004241d  jnz     short loc_18004245D
0x18004241f  xor     r8d, r8d; pftTimeout
0x180042422  mov     rdx, rbp; h
0x180042425  mov     rcx, [rsi+0C8h]; pwa
0x18004242c  call    cs:__imp_SetThreadpoolWait
0x180042432  nop
0x180042433  mov     rax, r14
0x180042436  mov     rcx, [rsp+4A8h+var_38]
0x18004243e  xor     rcx, rsp; StackCookie
0x180042441  call    __security_check_cookie
0x180042446  mov     rbx, [rsp+4A8h+arg_10]
0x18004244e  add     rsp, 480h
0x180042455  pop     r15
0x180042457  pop     r14
0x180042459  pop     rdi
0x18004245a  pop     rsi
0x18004245b  pop     rbp
0x18004245c  retn
0x18004245d  mov     edx, eax; __int64
0x18004245f  mov     [rsp+4A8h+var_480], 1Bh
0x180042467  lea     rax, aSyncQ; "sync_q"
0x18004246e  mov     [rsp+4A8h+var_488], rax
0x180042473  lea     r9, aSDFailed; "[%s:%d] failed; "
0x18004247a  xor     r8d, r8d; void *
0x18004247d  lea     rcx, [rsp+4A8h+pExceptionObject]; this
0x180042482  call    ??0system_exception@windiag@@QEAA@_JPEBXPEBDZZ; windiag::system_exception::system_exception(__int64,void const *,char const *,...)
0x180042487  lea     rdx, _TI2?AUsystem_exception@windiag@@; pThrowInfo
0x18004248e  lea     rcx, [rsp+4A8h+pExceptionObject]; pExceptionObject
0x180042493  call    _CxxThrowException_0
```
