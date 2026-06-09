# CSgxAttestationHelper::GetQuote(unsigned __int64,IMemObj *,uchar const *,ulong,uchar * *,ulong *)

- ea: `0x10082c6c0`
- end: `0x10082ca09`
- name: `?GetQuote@CSgxAttestationHelper@@SAX_KPEAVIMemObj@@PEBEKPEAPEAEPEAK@Z`
- size: `841`
- prototype: `void __fastcall(unsigned __int64, struct IMemObj *, const unsigned __int8 *, unsigned int, unsigned __int8 **, unsigned int *)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, service_task`

## callers

- `0x10082e2c0`
- `0x100833a10`

## callees

- `0x100401170`
- `0x10045f130`
- `0x10082c6c0`
- `0x10082cad0`

## import_xrefs

- `sqldk!?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z` at `0x10082c791`
- `sqldk!?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z` at `0x10082c791`
- `sqldk!??_V@YAXPEAX@Z` at `0x10082c9c3`
- `sqldk!??_V@YAXPEAX@Z` at `0x10082c9c3`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10082c932`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10082c932`
- `sqldk!SystemThread_TlsIndex` at `0x10082c751`
- `sqldk!SystemThread_TlsIndex` at `0x10082c7a6`
- `sqldk!SystemThread_TlsOffset` at `0x10082c75a`
- `sqldk!SystemThread_TlsOffset` at `0x10082c7af`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10082c773`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10082c7ca`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10082c773`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10082c7ca`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10082c84a`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10082c8b3`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10082c8dc`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10082c913`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10082c969`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10082c9a6`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10082c84a`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10082c8b3`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10082c8dc`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10082c913`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10082c969`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10082c9a6`
- `sgx_urts!sgx_ecall` at `0x10082c887`
- `sgx_urts!sgx_ecall` at `0x10082c887`
- `sgx_dcap_ql!__imp_sgx_qe_get_target_info` at `0x10082c81e`
- `sgx_dcap_ql!__imp_sgx_qe_get_target_info` at `0x10082c81e`
- `sgx_dcap_ql!__imp_sgx_qe_get_quote_size` at `0x10082c8e7`
- `sgx_dcap_ql!__imp_sgx_qe_get_quote_size` at `0x10082c8e7`
- `sgx_dcap_ql!__imp_sgx_qe_get_quote` at `0x10082c97a`
- `sgx_dcap_ql!__imp_sgx_qe_get_quote` at `0x10082c97a`

## string_xrefs

- `0x10082c88d`: `SgxCreateReport`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall CSgxAttestationHelper::GetQuote(
        __int64 a1,
        struct IMemObj *a2,
        const unsigned __int8 *a3,
        unsigned int a4,
        unsigned __int8 **a5,
        unsigned int *a6)
{
  __int64 v6; // r14
  __int64 v10; // rbx
  __int64 v11; // rcx
  __int64 v12; // rcx
  __int64 v13; // rbx
  __int64 v14; // rdx
  int target_info; // eax
  int v16; // eax
  int quote_size; // eax
  unsigned __int8 *v18; // rbx
  int quote; // eax
  __int64 v20; // [rsp+28h] [rbp-D8h]
  unsigned int v21; // [rsp+30h] [rbp-D0h] BYREF
  int v22; // [rsp+34h] [rbp-CCh] BYREF
  unsigned __int8 *v23; // [rsp+38h] [rbp-C8h]
  int v24; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v25; // [rsp+48h] [rbp-B8h]
  int v26; // [rsp+50h] [rbp-B0h] BYREF
  int v27; // [rsp+54h] [rbp-ACh]
  __int64 v28; // [rsp+58h] [rbp-A8h]
  int v29; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v30; // [rsp+68h] [rbp-98h]
  __int64 v31; // [rsp+70h] [rbp-90h]
  __int64 v32; // [rsp+78h] [rbp-88h]
  __int64 v33; // [rsp+80h] [rbp-80h]
  bool v34; // [rsp+90h] [rbp-70h]
  _QWORD v35[8]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v36[432]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v37[512]; // [rsp+290h] [rbp+190h] BYREF

  v35[5] = -2;
  v6 = a4;
  Worker::TaskAutoOnFlags::TaskAutoOnFlags(&v24, 1);
  v35[6] = &v26;
  v29 = 536872438;
  v30 = 0;
  v32 = 0;
  v31 = 0;
  v33 = 0;
  v34 = 0;
  v10 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v11 = *(_QWORD *)(v10 + 256);
  if ( !v11 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v11 = *(_QWORD *)(v10 + 256);
  }
  v12 = *(_QWORD *)(v11 + 600);
  if ( v12 )
    v34 = (unsigned int)SOS_Task::PushWait(v12, &v29) == 0;
  v13 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v14 = *(_QWORD *)(v13 + 256);
  if ( !v14 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v14 = *(_QWORD *)(v13 + 256);
  }
  v28 = v14;
  v27 = (*(_DWORD *)(v14 + 800) >> 11) & 1;
  if ( v27 || (*(_BYTE *)(v14 + 800) & 4) == 0 )
  {
    v26 = 1;
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v14 + 608) + 8LL))(*(_QWORD *)(v14 + 608));
  }
  else
  {
    v26 = 0;
  }
  target_info = sgx_qe_get_target_info(v37);
  if ( target_info )
    ex_raise(373, 9, 16, 61, L"sgx_qe_get_target_info", target_info);
  v35[0] = v37;
  v35[1] = a3;
  v35[2] = v6;
  v35[3] = v36;
  v35[4] = &v22;
  v16 = sgx_ecall(a1, 1, &qword_10089E878, v35);
  if ( v16 )
  {
    LODWORD(v20) = v16;
    ex_raise(373, 9, 16, 62, L"SgxCreateReport", v20);
  }
  if ( v22 )
  {
    LODWORD(v20) = v22;
    ex_raise(373, 9, 16, 62, L"SgxCreateReport", v20);
  }
  quote_size = sgx_qe_get_quote_size(&v21);
  if ( quote_size )
  {
    LODWORD(v20) = quote_size;
    ex_raise(373, 9, 16, 63, L"sgx_qe_get_quote_size", v20);
  }
  v18 = (unsigned __int8 *)operator new[](v21, a2, "Sql\\Ntdbms\\aetmhost\\SgxAttestationHelper.cpp", 108, 6u);
  v23 = v18;
  if ( !v18 )
  {
    LODWORD(v20) = -2147024882;
    ex_raise(373, 9, 16, 64, L"quoteBuffer", v20);
  }
  quote = sgx_qe_get_quote(v36, v21, v18);
  if ( quote )
  {
    LODWORD(v20) = quote;
    ex_raise(373, 9, 16, 65, L"sgx_qe_get_quote", v20);
  }
  v23 = 0;
  *a5 = v18;
  *a6 = v21;
  operator delete[](0);
  AutoSwitchPreemptive::~AutoSwitchPreemptive((AutoSwitchPreemptive *)&v26);
  *(_DWORD *)(v25 + 616) &= ~v24;
}

```

## disassembly

```asm
0x10082c6c0  push    rbp
0x10082c6c2  push    rbx
0x10082c6c3  push    rsi
0x10082c6c4  push    rdi
0x10082c6c5  push    r12
0x10082c6c7  push    r13
0x10082c6c9  push    r14
0x10082c6cb  push    r15
0x10082c6cd  lea     rbp, [rsp-3A8h]
0x10082c6d5  sub     rsp, 4A8h
0x10082c6dc  mov     [rbp+3E0h+var_418], 0FFFFFFFFFFFFFFFEh
0x10082c6e4  mov     rax, cs:__security_cookie
0x10082c6eb  xor     rax, rsp
0x10082c6ee  mov     [rbp+3E0h+var_50], rax
0x10082c6f5  mov     r14d, r9d
0x10082c6f8  mov     rsi, r8
0x10082c6fb  mov     r15, rdx
0x10082c6fe  mov     rdi, rcx
0x10082c701  mov     r12, [rbp+3E0h+arg_20]
0x10082c708  mov     r13, [rbp+3E0h+arg_28]
0x10082c70f  mov     edx, 1
0x10082c714  lea     rcx, [rsp+4E0h+var_4A0]
0x10082c719  call    ??0TaskAutoOnFlags@Worker@@QEAA@W4TASK_FLAGS@@@Z; Worker::TaskAutoOnFlags::TaskAutoOnFlags(TASK_FLAGS)
0x10082c71e  nop
0x10082c71f  lea     rax, [rsp+4E0h+var_490]
0x10082c724  mov     [rbp+3E0h+var_410], rax
0x10082c728  mov     [rsp+4E0h+var_480], 200005F6h
0x10082c730  xor     eax, eax
0x10082c732  mov     [rsp+4E0h+var_478], rax
0x10082c737  mov     [rsp+4E0h+var_468], rax
0x10082c73c  mov     [rsp+4E0h+var_470], rax
0x10082c741  mov     [rbp+3E0h+var_460], rax
0x10082c745  mov     [rbp+3E0h+var_450], al
0x10082c748  mov     rdx, gs:58h
0x10082c751  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10082c758  mov     ecx, [rax]
0x10082c75a  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10082c761  mov     ebx, [rax]
0x10082c763  add     rbx, [rdx+rcx*8]
0x10082c767  mov     rcx, [rbx+100h]
0x10082c76e  test    rcx, rcx
0x10082c771  jnz     short loc_10082C780
0x10082c773  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10082c779  mov     rcx, [rbx+100h]
0x10082c780  mov     rcx, [rcx+258h]
0x10082c787  test    rcx, rcx
0x10082c78a  jz      short loc_10082C79D
0x10082c78c  lea     rdx, [rsp+4E0h+var_480]
0x10082c791  call    cs:__imp_?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z; SOS_Task::PushWait(SOS_ExternalAutoWait *)
0x10082c797  test    eax, eax
0x10082c799  setz    [rbp+3E0h+var_450]
0x10082c79d  mov     rdx, gs:58h
0x10082c7a6  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10082c7ad  mov     ecx, [rax]
0x10082c7af  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10082c7b6  mov     ebx, [rax]
0x10082c7b8  add     rbx, [rdx+rcx*8]
0x10082c7bc  mov     rdx, [rbx+100h]
0x10082c7c3  test    rdx, rdx
0x10082c7c6  jnz     short loc_10082C7D7
0x10082c7c8  xor     ecx, ecx
0x10082c7ca  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10082c7d0  mov     rdx, [rbx+100h]
0x10082c7d7  mov     [rsp+4E0h+var_488], rdx
0x10082c7dc  mov     eax, [rdx+320h]
0x10082c7e2  shr     eax, 0Bh
0x10082c7e5  and     eax, 1
0x10082c7e8  mov     [rsp+4E0h+var_48C], eax
0x10082c7ec  jnz     short loc_10082C801
0x10082c7ee  test    byte ptr [rdx+320h], 4
0x10082c7f5  jz      short loc_10082C801
0x10082c7f7  mov     [rsp+4E0h+var_490], 0
0x10082c7ff  jmp     short loc_10082C817
0x10082c801  mov     [rsp+4E0h+var_490], 1
0x10082c809  mov     rcx, [rdx+260h]
0x10082c810  mov     rax, [rcx]
0x10082c813  call    qword ptr [rax+8]
0x10082c816  nop
0x10082c817  lea     rcx, [rbp+3E0h+var_250]
0x10082c81e  call    cs:__imp_sgx_qe_get_target_info
0x10082c824  test    eax, eax
0x10082c826  jz      short loc_10082C850
0x10082c828  mov     dword ptr [rsp+4E0h+var_4B8], eax
0x10082c82c  lea     rax, aSgxQeGetTarget; "sgx_qe_get_target_info"
0x10082c833  mov     [rsp+4E0h+var_4C0], rax
0x10082c838  mov     edx, 9
0x10082c83d  mov     ecx, 175h
0x10082c842  lea     r9d, [rdx+34h]
0x10082c846  lea     r8d, [rdx+7]
0x10082c84a  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x10082c850  lea     rax, [rbp+3E0h+var_250]
0x10082c857  mov     [rbp+3E0h+var_440], rax
0x10082c85b  mov     [rbp+3E0h+var_438], rsi
0x10082c85f  mov     [rbp+3E0h+var_430], r14
0x10082c863  lea     rax, [rbp+3E0h+var_400]
0x10082c867  mov     [rbp+3E0h+var_428], rax
0x10082c86b  lea     rax, [rsp+4E0h+var_4AC]
0x10082c870  mov     [rbp+3E0h+var_420], rax
0x10082c874  lea     r9, [rbp+3E0h+var_440]
0x10082c878  lea     r8, qword_10089E878
0x10082c87f  mov     edx, 1
0x10082c884  mov     rcx, rdi
0x10082c887  call    cs:__imp_sgx_ecall
0x10082c88d  lea     rbx, aSgxcreaterepor; "SgxCreateReport"
0x10082c894  test    eax, eax
0x10082c896  jz      short loc_10082C8B9
0x10082c898  mov     dword ptr [rsp+4E0h+var_4B8], eax
0x10082c89c  mov     [rsp+4E0h+var_4C0], rbx
0x10082c8a1  mov     edx, 9
0x10082c8a6  mov     ecx, 175h
0x10082c8ab  lea     r9d, [rdx+35h]
0x10082c8af  lea     r8d, [rdx+7]
0x10082c8b3  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x10082c8b9  mov     eax, [rsp+4E0h+var_4AC]
0x10082c8bd  test    eax, eax
0x10082c8bf  jz      short loc_10082C8E2
0x10082c8c1  mov     dword ptr [rsp+4E0h+var_4B8], eax
0x10082c8c5  mov     [rsp+4E0h+var_4C0], rbx
0x10082c8ca  mov     edx, 9
0x10082c8cf  mov     ecx, 175h
0x10082c8d4  lea     r9d, [rdx+35h]
0x10082c8d8  lea     r8d, [rdx+7]
0x10082c8dc  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x10082c8e2  lea     rcx, [rsp+4E0h+var_4B0]
0x10082c8e7  call    cs:__imp_sgx_qe_get_quote_size
0x10082c8ed  test    eax, eax
0x10082c8ef  jz      short loc_10082C919
0x10082c8f1  mov     dword ptr [rsp+4E0h+var_4B8], eax
0x10082c8f5  lea     rax, aSgxQeGetQuoteS; "sgx_qe_get_quote_size"
0x10082c8fc  mov     [rsp+4E0h+var_4C0], rax
0x10082c901  mov     edx, 9
0x10082c906  mov     ecx, 175h
0x10082c90b  lea     r9d, [rdx+36h]
0x10082c90f  lea     r8d, [rdx+7]
0x10082c913  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x10082c919  mov     ecx, [rsp+4E0h+var_4B0]
0x10082c91d  mov     byte ptr [rsp+4E0h+var_4C0], 6
0x10082c922  mov     r9d, 6Ch ; 'l'
0x10082c928  lea     r8, aSqlNtdbmsAetmh_1; "Sql\\Ntdbms\\aetmhost\\SgxAttestationHe"...
0x10082c92f  mov     rdx, r15
0x10082c932  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new[](unsigned __int64,IMemObj *,char const *,int,uchar)
0x10082c938  mov     rbx, rax
0x10082c93b  mov     [rsp+4E0h+var_4A8], rax
0x10082c940  test    rax, rax
0x10082c943  jnz     short loc_10082C96F
0x10082c945  mov     dword ptr [rsp+4E0h+var_4B8], 8007000Eh
0x10082c94d  lea     rax, aQuotebuffer; "quoteBuffer"
0x10082c954  mov     [rsp+4E0h+var_4C0], rax
0x10082c959  lea     edx, [rbx+9]
0x10082c95c  mov     ecx, 175h
0x10082c961  lea     r9d, [rbx+40h]
0x10082c965  lea     r8d, [rbx+10h]
0x10082c969  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x10082c96f  mov     r8, rbx
0x10082c972  mov     edx, [rsp+4E0h+var_4B0]
0x10082c976  lea     rcx, [rbp+3E0h+var_400]
0x10082c97a  call    cs:__imp_sgx_qe_get_quote
0x10082c980  test    eax, eax
0x10082c982  jz      short loc_10082C9AC
0x10082c984  mov     dword ptr [rsp+4E0h+var_4B8], eax
0x10082c988  lea     rax, aSgxQeGetQuote; "sgx_qe_get_quote"
0x10082c98f  mov     [rsp+4E0h+var_4C0], rax
0x10082c994  mov     edx, 9
0x10082c999  mov     ecx, 175h
0x10082c99e  lea     r9d, [rdx+38h]
0x10082c9a2  lea     r8d, [rdx+7]
0x10082c9a6  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x10082c9ac  mov     [rsp+4E0h+var_4A8], 0
0x10082c9b5  mov     [r12], rbx
0x10082c9b9  mov     eax, [rsp+4E0h+var_4B0]
0x10082c9bd  mov     [r13+0], eax
0x10082c9c1  xor     ecx, ecx
0x10082c9c3  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x10082c9c9  nop
0x10082c9ca  lea     rcx, [rsp+4E0h+var_490]; this
0x10082c9cf  call    ??1AutoSwitchPreemptive@@IEAA@XZ; AutoSwitchPreemptive::~AutoSwitchPreemptive(void)
0x10082c9d4  nop
0x10082c9d5  mov     rcx, [rsp+4E0h+var_498]
0x10082c9da  mov     eax, [rsp+4E0h+var_4A0]
0x10082c9de  not     eax
0x10082c9e0  and     [rcx+268h], eax
0x10082c9e6  mov     rcx, [rbp+3E0h+var_50]
0x10082c9ed  xor     rcx, rsp; StackCookie
0x10082c9f0  call    __security_check_cookie
0x10082c9f5  add     rsp, 4A8h
0x10082c9fc  pop     r15
0x10082c9fe  pop     r14
0x10082ca00  pop     r13
0x10082ca02  pop     r12
0x10082ca04  pop     rdi
0x10082ca05  pop     rsi
0x10082ca06  pop     rbx
0x10082ca07  pop     rbp
0x10082ca08  retn
```
