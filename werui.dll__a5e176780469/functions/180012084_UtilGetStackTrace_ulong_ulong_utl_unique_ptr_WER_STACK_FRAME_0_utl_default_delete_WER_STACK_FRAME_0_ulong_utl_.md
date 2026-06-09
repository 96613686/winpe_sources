# UtilGetStackTrace(ulong,ulong,utl::unique_ptr<_WER_STACK_FRAME [0],utl::default_delete<_WER_STACK_FRAME [0]>> *,ulong *,utl::unique_ptr<ushort [0],utl::default_delete<ushort [0]>> *,void * *,void * *)

- ea: `0x180012084`
- end: `0x180012590`
- name: `?UtilGetStackTrace@@YAJKKPEAV?$unique_ptr@$$BY0A@U_WER_STACK_FRAME@@U?$default_delete@$$BY0A@U_WER_STACK_FRAME@@@utl@@@utl@@PEAKPEAV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@utl@@@2@PEAPEAX3@Z`
- size: `1292`
- prototype: `__int64 __fastcall(DWORD dwProcessId, DWORD dwThreadId, __int64, unsigned int *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18000ff3c`

## callees

- `0x18000322c`
- `0x180005ddc`
- `0x18000983c`
- `0x18000f6b0`
- `0x18000f800`
- `0x1800113fc`
- `0x180012084`
- `0x180016c1e`
- `0x180016c50`

## import_xrefs

- `KERNEL32!OpenThread` at `0x180012117`
- `KERNEL32!OpenThread` at `0x180012117`
- `KERNEL32!GetThreadContext` at `0x1800121e1`
- `KERNEL32!GetThreadContext` at `0x1800121e1`
- `KERNEL32!OpenProcess` at `0x1800122c3`
- `KERNEL32!OpenProcess` at `0x1800122c3`
- `KERNEL32!GetLastError` at `0x180012527`
- `KERNEL32!GetLastError` at `0x180012527`
- `imagehlp!SymSetExtendedOption` at `0x1800122f0`
- `imagehlp!SymSetExtendedOption` at `0x1800122f0`
- `imagehlp!SymFunctionTableAccess64` at `0x18001237d`
- `imagehlp!StackWalk64` at `0x18001239f`
- `imagehlp!StackWalk64` at `0x18001239f`
- `imagehlp!SymGetModuleBase64` at `0x18001235f`
- `imagehlp!SymCleanup` at `0x18001251f`
- `imagehlp!SymCleanup` at `0x18001251f`
- `imagehlp!SymInitialize` at `0x180012304`
- `imagehlp!SymInitialize` at `0x180012304`

## pseudocode

```c
__int64 __fastcall UtilGetStackTrace(DWORD dwProcessId, DWORD dwThreadId, __int64 a3, unsigned int *a4)
{
  unsigned int v7; // r15d
  HANDLE v9; // rax
  HANDLE v10; // rdi
  __int64 v11; // rdx
  CONTEXT *p_Context; // rax
  _OWORD *v13; // rcx
  __int128 v14; // xmm1
  __int128 v15; // xmm0
  __int128 v16; // xmm1
  __int128 v17; // xmm0
  __int128 v18; // xmm1
  __int128 v19; // xmm0
  __int128 v20; // xmm1
  __int128 v21; // xmm1
  __int128 v22; // xmm0
  __int128 v23; // xmm1
  __int128 v24; // xmm0
  _tagSTACKFRAME64 *p_StackFrame; // rcx
  __int64 v26; // rdx
  ADDRESS64 *v27; // rax
  ADDRESS64 v28; // xmm1
  ADDRESS64 v29; // xmm0
  ADDRESS64 v30; // xmm1
  ADDRESS64 v31; // xmm0
  ADDRESS64 v32; // xmm1
  ADDRESS64 v33; // xmm0
  ADDRESS64 v34; // xmm1
  HANDLE v35; // rax
  HANDLE v36; // rbx
  char *v37; // rax
  char *v38; // r14
  unsigned int i; // esi
  ADDRESS64 *v40; // rcx
  _tagSTACKFRAME64 *v41; // rax
  __int64 v42; // rdx
  ADDRESS64 AddrReturn; // xmm1
  ADDRESS64 AddrFrame; // xmm0
  ADDRESS64 AddrStack; // xmm1
  ADDRESS64 AddrBStore; // xmm0
  ADDRESS64 v47; // xmm1
  ADDRESS64 v48; // xmm0
  ADDRESS64 v49; // xmm1
  __int64 v50; // rcx
  _OWORD *v51; // rax
  char *v52; // r8
  __int128 v53; // xmm1
  __int128 v54; // xmm0
  __int128 v55; // xmm1
  __int128 v56; // xmm0
  __int128 v57; // xmm1
  __int128 v58; // xmm0
  __int128 v59; // xmm1
  unsigned __int64 v60; // rax
  struct _WER_STACK_FRAME *v61; // r9
  __int64 v62; // rdi
  unsigned int v63; // edi
  signed int LastError; // eax
  __int64 v66; // [rsp+50h] [rbp-B0h] BYREF
  void *v67; // [rsp+58h] [rbp-A8h] BYREF
  HANDLE hThread; // [rsp+60h] [rbp-A0h] BYREF
  HANDLE hProcess; // [rsp+68h] [rbp-98h] BYREF
  char *v70; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v71[1232]; // [rsp+80h] [rbp-80h] BYREF
  _tagSTACKFRAME64 StackFrame; // [rsp+550h] [rbp+450h] BYREF
  CONTEXT Context; // [rsp+660h] [rbp+560h] BYREF

  v7 = 0;
  hProcess = 0;
  hThread = 0;
  memset_0(&StackFrame, 0, sizeof(StackFrame));
  v70 = 0;
  v66 = 0;
  memset_0(&Context, 0, sizeof(Context));
  if ( a3 && a4 )
  {
    v9 = OpenThread(0x48u, 0, dwThreadId);
    tlx::unique_any<tlx::file_handle_traits>::reset(&hThread, v9);
    v10 = hThread;
    if ( (unsigned __int64)hThread + 1 <= 1 )
      goto LABEL_30;
    memset_0(v71, 0, sizeof(v71));
    v11 = 9;
    p_Context = &Context;
    v13 = v71;
    do
    {
      v14 = v13[1];
      *(_OWORD *)&p_Context->P1Home = *v13;
      v15 = v13[2];
      *(_OWORD *)&p_Context->P3Home = v14;
      v16 = v13[3];
      *(_OWORD *)&p_Context->P5Home = v15;
      v17 = v13[4];
      *(_OWORD *)&p_Context->ContextFlags = v16;
      v18 = v13[5];
      *(_OWORD *)&p_Context->SegGs = v17;
      v19 = v13[6];
      *(_OWORD *)&p_Context->Dr1 = v18;
      v20 = v13[7];
      v13 += 8;
      *(_OWORD *)&p_Context->Dr3 = v19;
      *(_OWORD *)&p_Context->Dr7 = v20;
      p_Context = (CONTEXT *)((char *)p_Context + 128);
      --v11;
    }
    while ( v11 );
    v21 = v13[1];
    *(_OWORD *)&p_Context->P1Home = *v13;
    v22 = v13[2];
    *(_OWORD *)&p_Context->P3Home = v21;
    v23 = v13[3];
    *(_OWORD *)&p_Context->P5Home = v22;
    v24 = v13[4];
    *(_OWORD *)&p_Context->ContextFlags = v23;
    *(_OWORD *)&p_Context->SegGs = v24;
    Context.ContextFlags = 1048607;
    if ( !GetThreadContext(v10, &Context) )
      goto LABEL_30;
    memset_0(v71, 0, 0x108u);
    p_StackFrame = &StackFrame;
    v26 = 2;
    v27 = (ADDRESS64 *)v71;
    do
    {
      v28 = v27[1];
      p_StackFrame->AddrPC = *v27;
      v29 = v27[2];
      p_StackFrame->AddrReturn = v28;
      v30 = v27[3];
      p_StackFrame->AddrFrame = v29;
      v31 = v27[4];
      p_StackFrame->AddrStack = v30;
      v32 = v27[5];
      p_StackFrame->AddrBStore = v31;
      v33 = v27[6];
      *(ADDRESS64 *)&p_StackFrame->FuncTableEntry = v32;
      v34 = v27[7];
      v27 += 8;
      *(ADDRESS64 *)&p_StackFrame->Params[1] = v33;
      *(ADDRESS64 *)&p_StackFrame->Params[3] = v34;
      p_StackFrame = (_tagSTACKFRAME64 *)((char *)p_StackFrame + 128);
      --v26;
    }
    while ( v26 );
    p_StackFrame->AddrPC.Offset = v27->Offset;
    StackFrame.AddrPC.Offset = Context.Rip;
    StackFrame.AddrStack.Offset = Context.Rsp;
    StackFrame.AddrFrame.Offset = Context.Rbp;
    StackFrame.AddrPC.Segment = 0;
    StackFrame.AddrStack.Segment = 0;
    StackFrame.AddrFrame.Segment = 0;
    StackFrame.AddrPC.Mode = AddrModeFlat;
    StackFrame.AddrStack.Mode = AddrModeFlat;
    StackFrame.AddrFrame.Mode = AddrModeFlat;
    v35 = OpenProcess(0x410u, 0, dwProcessId);
    tlx::unique_any<tlx::file_handle_traits>::reset(&hProcess, v35);
    v36 = hProcess;
    if ( (unsigned __int64)hProcess + 1 <= 1 )
      goto LABEL_30;
    SymSetExtendedOption((IMAGEHLP_EXTENDED_OPTIONS)3, 1);
    if ( SymInitialize(v36, UserSearchPath, 1) )
    {
      v37 = (char *)operator new[](0x8400u, (const struct std::nothrow_t *)std::nothrow);
      v38 = v37;
      if ( v37 )
        memset_0(v37, 0, 0x8400u);
      else
        v38 = 0;
      v67 = 0;
      v70 = v38;
      utl::unique_ptr<unsigned short [0],utl::default_delete<unsigned short [0]>>::~unique_ptr<unsigned short [0],utl::default_delete<unsigned short [0]>>(&v67);
      if ( !v38 )
        goto LABEL_28;
      for ( i = 0; i < 0x80; ++i )
      {
        if ( !StackWalk64(0x8664u, v36, v10, &StackFrame, &Context, 0, SymFunctionTableAccess64, SymGetModuleBase64, 0) )
          break;
        v40 = (ADDRESS64 *)v71;
        v41 = &StackFrame;
        v42 = 2;
        do
        {
          AddrReturn = v41->AddrReturn;
          *v40 = v41->AddrPC;
          AddrFrame = v41->AddrFrame;
          v40[1] = AddrReturn;
          AddrStack = v41->AddrStack;
          v40[2] = AddrFrame;
          AddrBStore = v41->AddrBStore;
          v40[3] = AddrStack;
          v47 = *(ADDRESS64 *)&v41->FuncTableEntry;
          v40[4] = AddrBStore;
          v48 = *(ADDRESS64 *)&v41->Params[1];
          v40[5] = v47;
          v49 = *(ADDRESS64 *)&v41->Params[3];
          v41 = (_tagSTACKFRAME64 *)((char *)v41 + 128);
          v40[6] = v48;
          v40[7] = v49;
          v40 += 8;
          --v42;
        }
        while ( v42 );
        v40->Offset = v41->AddrPC.Offset;
        v50 = 2;
        v51 = v71;
        v52 = &v38[264 * i];
        do
        {
          v53 = v51[1];
          *(_OWORD *)v52 = *v51;
          v54 = v51[2];
          *((_OWORD *)v52 + 1) = v53;
          v55 = v51[3];
          *((_OWORD *)v52 + 2) = v54;
          v56 = v51[4];
          *((_OWORD *)v52 + 3) = v55;
          v57 = v51[5];
          *((_OWORD *)v52 + 4) = v56;
          v58 = v51[6];
          *((_OWORD *)v52 + 5) = v57;
          v59 = v51[7];
          v51 += 8;
          *((_OWORD *)v52 + 6) = v58;
          *((_OWORD *)v52 + 7) = v59;
          v52 += 128;
          --v50;
        }
        while ( v50 );
        *(_QWORD *)v52 = *(_QWORD *)v51;
      }
      v60 = 1048LL * i;
      if ( !is_mul_ok(i, 0x418u) )
        v60 = -1;
      v67 = operator new[](v60, (const struct std::nothrow_t *)std::nothrow);
      utl::unique_ptr<_WER_STACK_FRAME [0],utl::default_delete<_WER_STACK_FRAME [0]>>::operator=(&v66, &v67);
      utl::unique_ptr<unsigned short [0],utl::default_delete<unsigned short [0]>>::~unique_ptr<unsigned short [0],utl::default_delete<unsigned short [0]>>(&v67);
      v62 = v66;
      if ( v66 )
      {
        if ( i )
        {
          do
          {
            _werDetail::UtilConvertDbgFrameToWerFrame(
              (_werDetail *)v36,
              &v38[264 * v7],
              (void *)(v62 + 1048LL * v7),
              v61);
            ++v7;
          }
          while ( v7 < i );
        }
        utl::unique_ptr<_WER_STACK_FRAME [0],utl::default_delete<_WER_STACK_FRAME [0]>>::operator=(a3, &v66);
        v63 = 0;
        *a4 = i;
      }
      else
      {
LABEL_28:
        v63 = -2147024882;
      }
      SymCleanup(v36);
    }
    else
    {
LABEL_30:
      LastError = GetLastError();
      v63 = LastError;
      if ( LastError > 0 )
        v63 = (unsigned __int16)LastError | 0x80070000;
    }
  }
  else
  {
    v63 = -2147024809;
  }
  utl::unique_ptr<unsigned short [0],utl::default_delete<unsigned short [0]>>::~unique_ptr<unsigned short [0],utl::default_delete<unsigned short [0]>>(&v66);
  utl::unique_ptr<unsigned short [0],utl::default_delete<unsigned short [0]>>::~unique_ptr<unsigned short [0],utl::default_delete<unsigned short [0]>>(&v70);
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&hThread);
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&hProcess);
  return v63;
}

```

## disassembly

```asm
0x180012084  push    rbp
0x180012086  push    rbx
0x180012087  push    rsi
0x180012088  push    rdi
0x180012089  push    r12
0x18001208b  push    r13
0x18001208d  push    r14
0x18001208f  push    r15
0x180012091  lea     rbp, [rsp-0A48h]
0x180012099  sub     rsp, 0B48h
0x1800120a0  mov     rax, cs:__security_cookie
0x1800120a7  xor     rax, rsp
0x1800120aa  mov     [rbp+0A80h+var_50], rax
0x1800120b1  mov     r13, r8
0x1800120b4  mov     ebx, edx
0x1800120b6  mov     esi, ecx
0x1800120b8  xor     r15d, r15d
0x1800120bb  xor     edx, edx; Val
0x1800120bd  mov     [rsp+0B80h+hProcess], r15
0x1800120c2  mov     r8d, 108h; Size
0x1800120c8  mov     [rsp+0B80h+hThread], r15
0x1800120cd  lea     rcx, [rbp+0A80h+StackFrame]; void *
0x1800120d4  mov     r12, r9
0x1800120d7  call    memset_0
0x1800120dc  mov     r14d, 4D0h
0x1800120e2  mov     [rsp+0B80h+var_B10], r15
0x1800120e7  mov     r8d, r14d; Size
0x1800120ea  mov     [rsp+0B80h+var_B30], r15
0x1800120ef  xor     edx, edx; Val
0x1800120f1  lea     rcx, [rbp+0A80h+Context]; void *
0x1800120f8  call    memset_0
0x1800120fd  test    r13, r13
0x180012100  jz      loc_18001253E
0x180012106  test    r12, r12
0x180012109  jz      loc_18001253E
0x18001210f  xor     edx, edx; bInheritHandle
0x180012111  mov     r8d, ebx; dwThreadId
0x180012114  lea     ecx, [rdx+48h]; dwDesiredAccess
0x180012117  call    cs:__imp_OpenThread
0x18001211d  mov     rdx, rax
0x180012120  lea     rcx, [rsp+0B80h+hThread]
0x180012125  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x18001212a  mov     rdi, [rsp+0B80h+hThread]
0x18001212f  lea     rax, [rdi+1]
0x180012133  cmp     rax, 1
0x180012137  jbe     loc_180012527
0x18001213d  mov     r8d, r14d; Size
0x180012140  lea     rcx, [rbp+0A80h+var_B00]; void *
0x180012144  xor     edx, edx; Val
0x180012146  call    memset_0
0x18001214b  lea     edx, [r15+9]
0x18001214f  lea     rax, [rbp+0A80h+Context]
0x180012156  lea     rcx, [rbp+0A80h+var_B00]
0x18001215a  lea     ebx, [rdx+77h]
0x18001215d  movups  xmm0, xmmword ptr [rcx]
0x180012160  movups  xmm1, xmmword ptr [rcx+10h]
0x180012164  movups  xmmword ptr [rax], xmm0
0x180012167  movups  xmm0, xmmword ptr [rcx+20h]
0x18001216b  movups  xmmword ptr [rax+10h], xmm1
0x18001216f  movups  xmm1, xmmword ptr [rcx+30h]
0x180012173  movups  xmmword ptr [rax+20h], xmm0
0x180012177  movups  xmm0, xmmword ptr [rcx+40h]
0x18001217b  movups  xmmword ptr [rax+30h], xmm1
0x18001217f  movups  xmm1, xmmword ptr [rcx+50h]
0x180012183  movups  xmmword ptr [rax+40h], xmm0
0x180012187  movups  xmm0, xmmword ptr [rcx+60h]
0x18001218b  movups  xmmword ptr [rax+50h], xmm1
0x18001218f  movups  xmm1, xmmword ptr [rcx+70h]
0x180012193  add     rcx, rbx
0x180012196  movups  xmmword ptr [rax+60h], xmm0
0x18001219a  movups  xmmword ptr [rax+70h], xmm1
0x18001219e  add     rax, rbx
0x1800121a1  sub     rdx, 1
0x1800121a5  jnz     short loc_18001215D
0x1800121a7  movups  xmm0, xmmword ptr [rcx]
0x1800121aa  lea     rdx, [rbp+0A80h+Context]; lpContext
0x1800121b1  movups  xmm1, xmmword ptr [rcx+10h]
0x1800121b5  movups  xmmword ptr [rax], xmm0
0x1800121b8  movups  xmm0, xmmword ptr [rcx+20h]
0x1800121bc  movups  xmmword ptr [rax+10h], xmm1
0x1800121c0  movups  xmm1, xmmword ptr [rcx+30h]
0x1800121c4  movups  xmmword ptr [rax+20h], xmm0
0x1800121c8  movups  xmm0, xmmword ptr [rcx+40h]
0x1800121cc  mov     rcx, rdi; hThread
0x1800121cf  movups  xmmword ptr [rax+30h], xmm1
0x1800121d3  movups  xmmword ptr [rax+40h], xmm0
0x1800121d7  mov     [rbp+0A80h+Context.ContextFlags], 10001Fh
0x1800121e1  call    cs:__imp_GetThreadContext
0x1800121e7  test    eax, eax
0x1800121e9  jz      loc_180012527
0x1800121ef  xor     edx, edx; Val
0x1800121f1  lea     rcx, [rbp+0A80h+var_B00]; void *
0x1800121f5  mov     r8d, 108h; Size
0x1800121fb  call    memset_0
0x180012200  lea     rcx, [rbp+0A80h+StackFrame]
0x180012207  mov     edx, 2
0x18001220c  lea     rax, [rbp+0A80h+var_B00]
0x180012210  movups  xmm0, xmmword ptr [rax]
0x180012213  movups  xmm1, xmmword ptr [rax+10h]
0x180012217  movups  xmmword ptr [rcx], xmm0
0x18001221a  movups  xmm0, xmmword ptr [rax+20h]
0x18001221e  movups  xmmword ptr [rcx+10h], xmm1
0x180012222  movups  xmm1, xmmword ptr [rax+30h]
0x180012226  movups  xmmword ptr [rcx+20h], xmm0
0x18001222a  movups  xmm0, xmmword ptr [rax+40h]
0x18001222e  movups  xmmword ptr [rcx+30h], xmm1
0x180012232  movups  xmm1, xmmword ptr [rax+50h]
0x180012236  movups  xmmword ptr [rcx+40h], xmm0
0x18001223a  movups  xmm0, xmmword ptr [rax+60h]
0x18001223e  movups  xmmword ptr [rcx+50h], xmm1
0x180012242  movups  xmm1, xmmword ptr [rax+70h]
0x180012246  add     rax, rbx
0x180012249  movups  xmmword ptr [rcx+60h], xmm0
0x18001224d  movups  xmmword ptr [rcx+70h], xmm1
0x180012251  add     rcx, rbx
0x180012254  sub     rdx, 1; bInheritHandle
0x180012258  jnz     short loc_180012210
0x18001225a  mov     rax, [rax]
0x18001225d  lea     r14d, [rdx+3]
0x180012261  mov     [rcx], rax
0x180012264  mov     r8d, esi; dwProcessId
0x180012267  mov     rax, [rbp+0A80h+Context.Rip]
0x18001226e  mov     ecx, 410h; dwDesiredAccess
0x180012273  mov     [rbp+0A80h+StackFrame.AddrPC.Offset], rax
0x18001227a  mov     rax, [rbp+0A80h+Context.Rsp]
0x180012281  mov     [rbp+0A80h+StackFrame.AddrStack.Offset], rax
0x180012288  mov     rax, [rbp+0A80h+Context.Rbp]
0x18001228f  mov     [rbp+0A80h+StackFrame.AddrFrame.Offset], rax
0x180012296  mov     [rbp+0A80h+StackFrame.AddrPC.Segment], r15w
0x18001229e  mov     [rbp+0A80h+StackFrame.AddrStack.Segment], r15w
0x1800122a6  mov     [rbp+0A80h+StackFrame.AddrFrame.Segment], r15w
0x1800122ae  mov     [rbp+0A80h+StackFrame.AddrPC.Mode], r14d
0x1800122b5  mov     [rbp+0A80h+StackFrame.AddrStack.Mode], r14d
0x1800122bc  mov     [rbp+0A80h+StackFrame.AddrFrame.Mode], r14d
0x1800122c3  call    cs:__imp_OpenProcess
0x1800122c9  mov     rdx, rax
0x1800122cc  lea     rcx, [rsp+0B80h+hProcess]
0x1800122d1  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x1800122d6  mov     rbx, [rsp+0B80h+hProcess]
0x1800122db  lea     rax, [rbx+1]
0x1800122df  cmp     rax, 1
0x1800122e3  jbe     loc_180012527
0x1800122e9  lea     edx, [r14-2]; value
0x1800122ed  mov     ecx, r14d; option
0x1800122f0  call    cs:__imp_SymSetExtendedOption
0x1800122f6  lea     r8d, [r14-2]; fInvadeProcess
0x1800122fa  mov     rcx, rbx; hProcess
0x1800122fd  lea     rdx, UserSearchPath; UserSearchPath
0x180012304  call    cs:__imp_SymInitialize
0x18001230a  test    eax, eax
0x18001230c  jz      loc_180012527
0x180012312  mov     esi, 8400h
0x180012317  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001231e  mov     ecx, esi; unsigned __int64
0x180012320  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180012325  mov     r14, rax
0x180012328  test    rax, rax
0x18001232b  jz      short loc_18001233C
0x18001232d  mov     r8d, esi; Size
0x180012330  xor     edx, edx; Val
0x180012332  mov     rcx, rax; void *
0x180012335  call    memset_0
0x18001233a  jmp     short loc_18001233F
0x18001233c  mov     r14, r15
0x18001233f  lea     rcx, [rsp+0B80h+var_B28]
0x180012344  mov     [rsp+0B80h+var_B28], r15
0x180012349  mov     [rsp+0B80h+var_B10], r14
0x18001234e  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@utl@@@utl@@QEAA@XZ; utl::unique_ptr<ushort [0],utl::default_delete<ushort [0]>>::~unique_ptr<ushort [0],utl::default_delete<ushort [0]>>(void)
0x180012353  test    r14, r14
0x180012356  jz      loc_180012517
0x18001235c  mov     esi, r15d
0x18001235f  mov     rax, cs:__imp_SymGetModuleBase64
0x180012366  lea     r9, [rbp+0A80h+StackFrame]; StackFrame
0x18001236d  mov     [rsp+0B80h+TranslateAddress], r15; TranslateAddress
0x180012372  mov     r8, rdi; hThread
0x180012375  mov     [rsp+0B80h+GetModuleBaseRoutine], rax; GetModuleBaseRoutine
0x18001237a  mov     rdx, rbx; hProcess
0x18001237d  mov     rax, cs:__imp_SymFunctionTableAccess64
0x180012384  mov     ecx, 8664h; MachineType
0x180012389  mov     [rsp+0B80h+FunctionTableAccessRoutine], rax; FunctionTableAccessRoutine
0x18001238e  lea     rax, [rbp+0A80h+Context]
0x180012395  mov     [rsp+0B80h+ReadMemoryRoutine], r15; ReadMemoryRoutine
0x18001239a  mov     [rsp+0B80h+ContextRecord], rax; ContextRecord
0x18001239f  call    cs:__imp_StackWalk64
0x1800123a5  test    eax, eax
0x1800123a7  jz      loc_18001248B
0x1800123ad  mov     r10d, 2
0x1800123b3  lea     rcx, [rbp+0A80h+var_B00]
0x1800123b7  lea     rax, [rbp+0A80h+StackFrame]
0x1800123be  mov     edx, r10d
0x1800123c1  lea     r9d, [r10+7Eh]
0x1800123c5  movups  xmm0, xmmword ptr [rax]
0x1800123c8  movups  xmm1, xmmword ptr [rax+10h]
0x1800123cc  movups  xmmword ptr [rcx], xmm0
0x1800123cf  movups  xmm0, xmmword ptr [rax+20h]
0x1800123d3  movups  xmmword ptr [rcx+10h], xmm1
0x1800123d7  movups  xmm1, xmmword ptr [rax+30h]
0x1800123db  movups  xmmword ptr [rcx+20h], xmm0
0x1800123df  movups  xmm0, xmmword ptr [rax+40h]
0x1800123e3  movups  xmmword ptr [rcx+30h], xmm1
0x1800123e7  movups  xmm1, xmmword ptr [rax+50h]
0x1800123eb  movups  xmmword ptr [rcx+40h], xmm0
0x1800123ef  movups  xmm0, xmmword ptr [rax+60h]
0x1800123f3  movups  xmmword ptr [rcx+50h], xmm1
0x1800123f7  movups  xmm1, xmmword ptr [rax+70h]
0x1800123fb  add     rax, r9
0x1800123fe  movups  xmmword ptr [rcx+60h], xmm0
0x180012402  movups  xmmword ptr [rcx+70h], xmm1
0x180012406  add     rcx, r9
0x180012409  sub     rdx, 1
0x18001240d  jnz     short loc_1800123C5
0x18001240f  mov     rax, [rax]
0x180012412  mov     [rcx], rax
0x180012415  mov     rcx, r10
0x180012418  mov     eax, esi
0x18001241a  imul    r8, rax, 108h
0x180012421  lea     rax, [rbp+0A80h+var_B00]
0x180012425  add     r8, r14
0x180012428  movups  xmm0, xmmword ptr [rax]
0x18001242b  movups  xmm1, xmmword ptr [rax+10h]
0x18001242f  movups  xmmword ptr [r8], xmm0
0x180012433  movups  xmm0, xmmword ptr [rax+20h]
0x180012437  movups  xmmword ptr [r8+10h], xmm1
0x18001243c  movups  xmm1, xmmword ptr [rax+30h]
0x180012440  movups  xmmword ptr [r8+20h], xmm0
0x180012445  movups  xmm0, xmmword ptr [rax+40h]
0x180012449  movups  xmmword ptr [r8+30h], xmm1
0x18001244e  movups  xmm1, xmmword ptr [rax+50h]
0x180012452  movups  xmmword ptr [r8+40h], xmm0
0x180012457  movups  xmm0, xmmword ptr [rax+60h]
0x18001245b  movups  xmmword ptr [r8+50h], xmm1
0x180012460  movups  xmm1, xmmword ptr [rax+70h]
0x180012464  add     rax, r9
0x180012467  movups  xmmword ptr [r8+60h], xmm0
0x18001246c  movups  xmmword ptr [r8+70h], xmm1
0x180012471  add     r8, r9
0x180012474  sub     rcx, 1
0x180012478  jnz     short loc_180012428
0x18001247a  mov     rax, [rax]
0x18001247d  inc     esi
0x18001247f  mov     [r8], rax
0x180012482  cmp     esi, r9d
0x180012485  jb      loc_18001235F
0x18001248b  mov     ecx, esi
0x18001248d  mov     eax, 418h
0x180012492  mul     rcx
0x180012495  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18001249c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800124a3  cmovb   rax, rcx
0x1800124a7  mov     rcx, rax; unsigned __int64
0x1800124aa  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800124af  lea     rdx, [rsp+0B80h+var_B28]
0x1800124b4  mov     [rsp+0B80h+var_B28], rax
0x1800124b9  lea     rcx, [rsp+0B80h+var_B30]
0x1800124be  call    ??4?$unique_ptr@$$BY0A@U_WER_STACK_FRAME@@U?$default_delete@$$BY0A@U_WER_STACK_FRAME@@@utl@@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::unique_ptr<_WER_STACK_FRAME [0],utl::default_delete<_WER_STACK_FRAME [0]>>::operator=(utl::unique_ptr<_WER_STACK_FRAME [0],utl::default_delete<_WER_STACK_FRAME [0]>> &&)
0x1800124c3  lea     rcx, [rsp+0B80h+var_B28]
0x1800124c8  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@utl@@@utl@@QEAA@XZ; utl::unique_ptr<ushort [0],utl::default_delete<ushort [0]>>::~unique_ptr<ushort [0],utl::default_delete<ushort [0]>>(void)
0x1800124cd  mov     rdi, [rsp+0B80h+var_B30]
0x1800124d2  test    rdi, rdi
0x1800124d5  jz      short loc_180012517
0x1800124d7  test    esi, esi
0x1800124d9  jz      short loc_180012502
0x1800124db  mov     eax, r15d
0x1800124de  mov     rcx, rbx; this
0x1800124e1  imul    r8, rax, 418h
0x1800124e8  imul    rdx, rax, 108h
0x1800124ef  add     r8, rdi; void *
0x1800124f2  add     rdx, r14; void *
0x1800124f5  call    ?UtilConvertDbgFrameToWerFrame@_werDetail@@YAJPEAX0PEAU_WER_STACK_FRAME@@@Z; _werDetail::UtilConvertDbgFrameToWerFrame(void *,void *,_WER_STACK_FRAME *)
0x1800124fa  inc     r15d
0x1800124fd  cmp     r15d, esi
0x180012500  jb      short loc_1800124DB
0x180012502  lea     rdx, [rsp+0B80h+var_B30]
0x180012507  mov     rcx, r13
0x18001250a  call    ??4?$unique_ptr@$$BY0A@U_WER_STACK_FRAME@@U?$default_delete@$$BY0A@U_WER_STACK_FRAME@@@utl@@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::unique_ptr<_WER_STACK_FRAME [0],utl::default_delete<_WER_STACK_FRAME [0]>>::operator=(utl::unique_ptr<_WER_STACK_FRAME [0],utl::default_delete<_WER_STACK_FRAME [0]>> &&)
0x18001250f  xor     edi, edi
0x180012511  mov     [r12], esi
0x180012515  jmp     short loc_18001251C
0x180012517  mov     edi, 8007000Eh
0x18001251c  mov     rcx, rbx; hProcess
0x18001251f  call    cs:__imp_SymCleanup
0x180012525  jmp     short loc_180012543
0x180012527  call    cs:__imp_GetLastError
0x18001252d  mov     edi, eax
0x18001252f  test    eax, eax
0x180012531  jle     short loc_180012543
0x180012533  movzx   edi, ax
0x180012536  or      edi, 80070000h
0x18001253c  jmp     short loc_180012543
0x18001253e  mov     edi, 80070057h
0x180012543  lea     rcx, [rsp+0B80h+var_B30]
0x180012548  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@utl@@@utl@@QEAA@XZ; utl::unique_ptr<ushort [0],utl::default_delete<ushort [0]>>::~unique_ptr<ushort [0],utl::default_delete<ushort [0]>>(void)
0x18001254d  lea     rcx, [rsp+0B80h+var_B10]
0x180012552  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@utl@@@utl@@QEAA@XZ; utl::unique_ptr<ushort [0],utl::default_delete<ushort [0]>>::~unique_ptr<ushort [0],utl::default_delete<ushort [0]>>(void)
0x180012557  lea     rcx, [rsp+0B80h+hThread]
0x18001255c  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x180012561  lea     rcx, [rsp+0B80h+hProcess]
0x180012566  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x18001256b  mov     eax, edi
0x18001256d  mov     rcx, [rbp+0A80h+var_50]
  ... truncated ...
```
