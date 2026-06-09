# ?GetExtendedDynamicInfo@?QITaskSchedulerEx2@@TaskServiceImpl@@UEAAJPEAGPEAFPEAW4_TASK_STATE@@PEAJPEAN44@Z

- ea: `0x180046150`
- end: `0x180046447`
- name: `?GetExtendedDynamicInfo@?QITaskSchedulerEx2@@TaskServiceImpl@@UEAAJPEAGPEAFPEAW4_TASK_STATE@@PEAJPEAN44@Z`
- size: `759`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000c750`
- `0x18002c214`
- `0x180046150`
- `0x18004e150`
- `0x18004e950`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800462be`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180046335`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800463ac`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800463ec`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180046407`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800462be`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180046335`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800463ac`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800463ec`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180046407`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180046206`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180046206`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004629d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046314`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004638b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004629d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046314`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004638b`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180046293`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18004630a`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180046381`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180046293`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18004630a`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180046381`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall _GetExtendedDynamicInfo__QITaskSchedulerEx2__TaskServiceImpl__UEAAJPEAGPEAFPEAW4_TASK_STATE__PEAJPEAN44_Z(
        __int64 a1,
        __int64 a2,
        _WORD *a3,
        _DWORD *a4,
        _DWORD *a5,
        _QWORD *a6,
        double *a7,
        double *a8)
{
  struct _RTL_CRITICAL_SECTION *v12; // rsi
  void *v13; // rcx
  unsigned int ExtendedDynamicInfo; // edi
  char *v15; // rbx
  signed int v16; // eax
  unsigned int v17; // edi
  signed int LastError; // eax
  signed int v20; // eax
  double v21; // [rsp+38h] [rbp-90h] BYREF
  int v22; // [rsp+40h] [rbp-88h]
  void *v23; // [rsp+48h] [rbp-80h] BYREF
  double *v24; // [rsp+50h] [rbp-78h]
  double *v25; // [rsp+58h] [rbp-70h]
  __int64 v26; // [rsp+60h] [rbp-68h]
  struct _SYSTEMTIME SystemTime; // [rsp+68h] [rbp-60h] BYREF

  v24 = a7;
  v25 = a8;
  SystemTime = 0;
  if ( !a3 || !a4 || !a5 || !a6 )
    return 2147500035LL;
  *a3 = 0;
  *a4 = 0;
  *a5 = 0;
  *a6 = 0;
  *a7 = 0.0;
  *a8 = 0.0;
  v12 = (struct _RTL_CRITICAL_SECTION *)(a1 + 256);
  v26 = a1 + 256;
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 256));
  v13 = 0;
  v23 = 0;
  if ( !*(_DWORD *)(a1 + 296) )
  {
    ExtendedDynamicInfo = -2147023645;
LABEL_32:
    MIDL_user_free(v13);
    LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 256));
    return ExtendedDynamicInfo;
  }
  if ( !*(_QWORD *)(a1 + 304) )
  {
    ExtendedDynamicInfo = -2147024846;
    goto LABEL_32;
  }
  ExtendedDynamicInfo = RpcSession::GetExtendedDynamicInfo(*(_QWORD *)(a1 + 304), a2, &v23);
  if ( (ExtendedDynamicInfo & 0x80000000) != 0 )
  {
    v13 = v23;
    goto LABEL_32;
  }
  v15 = (char *)v23;
  *a3 = -(*(_DWORD *)v23 != 0);
  *a4 = *((_DWORD *)v15 + 1);
  *a5 = *((_DWORD *)v15 + 2);
  if ( !*(_QWORD *)(v15 + 12) )
  {
LABEL_16:
    if ( *((_DWORD *)v15 + 6) || *((_DWORD *)v15 + 5) )
    {
      if ( !FileTimeToSystemTime((const FILETIME *)(v15 + 20), &SystemTime) )
      {
        LastError = GetLastError();
        ExtendedDynamicInfo = LastError;
        if ( LastError > 0 )
          ExtendedDynamicInfo = (unsigned __int16)LastError | 0x80070000;
LABEL_30:
        MIDL_user_free(v15);
        LeaveCriticalSection(v12);
        return ExtendedDynamicInfo;
      }
      v21 = 0.0;
      v22 = 0;
      ATL::AtlConvertSystemTimeToVariantTime(&SystemTime, &v21);
      *v24 = v21;
    }
    if ( *((_DWORD *)v15 + 8) || *((_DWORD *)v15 + 7) )
    {
      if ( FileTimeToSystemTime((const FILETIME *)(v15 + 28), &SystemTime) )
      {
        v21 = 0.0;
        v22 = 0;
        ATL::AtlConvertSystemTimeToVariantTime(&SystemTime, &v21);
        *v25 = v21;
      }
      else
      {
        v20 = GetLastError();
        ExtendedDynamicInfo = v20;
        if ( v20 > 0 )
          ExtendedDynamicInfo = (unsigned __int16)v20 | 0x80070000;
      }
    }
    goto LABEL_30;
  }
  if ( FileTimeToSystemTime((const FILETIME *)(v15 + 12), &SystemTime) )
  {
    v21 = 0.0;
    v22 = 0;
    ATL::AtlConvertSystemTimeToVariantTime(&SystemTime, &v21);
    *a6 = *(_QWORD *)&v21;
    goto LABEL_16;
  }
  v16 = GetLastError();
  v17 = v16;
  if ( v16 > 0 )
    v17 = (unsigned __int16)v16 | 0x80070000;
  MIDL_user_free(v15);
  LeaveCriticalSection(v12);
  return v17;
}

```

## disassembly

```asm
0x180046150  mov     rax, rsp
0x180046153  push    rbx
0x180046154  push    rsi
0x180046155  push    rdi
0x180046156  push    r12
0x180046158  push    r13
0x18004615a  push    r14
0x18004615c  push    r15
0x18004615e  sub     rsp, 90h
0x180046165  movaps  xmmword ptr [rax-48h], xmm6
0x180046169  mov     rax, cs:__security_cookie
0x180046170  xor     rax, rsp
0x180046173  mov     [rsp+0C8h+var_50], rax
0x180046178  mov     r14, r9
0x18004617b  mov     r13, r8
0x18004617e  mov     rdi, rdx
0x180046181  mov     rbx, rcx
0x180046184  mov     r15, [rsp+0C8h+arg_20]
0x18004618c  mov     r12, [rsp+0C8h+arg_28]
0x180046194  mov     rcx, [rsp+0C8h+arg_30]
0x18004619c  mov     [rsp+0C8h+var_78], rcx
0x1800461a1  mov     rdx, [rsp+0C8h+arg_38]
0x1800461a9  mov     [rsp+0C8h+var_70], rdx
0x1800461ae  xor     r8d, r8d
0x1800461b1  mov     [rsp+0C8h+var_98], r8d
0x1800461b6  xorps   xmm0, xmm0
0x1800461b9  movups  xmmword ptr [rsp+0C8h+SystemTime.wYear], xmm0
0x1800461be  test    r13, r13
0x1800461c1  jz      loc_180046419
0x1800461c7  test    r9, r9
0x1800461ca  jz      loc_180046419
0x1800461d0  test    r15, r15
0x1800461d3  jz      loc_180046419
0x1800461d9  test    r12, r12
0x1800461dc  jz      loc_180046419
0x1800461e2  mov     [r13+0], r8w
0x1800461e7  mov     [r9], r8d
0x1800461ea  mov     [r15], r8d
0x1800461ed  mov     [r12], r8
0x1800461f1  mov     [rcx], r8
0x1800461f4  mov     [rdx], r8
0x1800461f7  lea     rsi, [rbx+100h]
0x1800461fe  mov     [rsp+0C8h+var_68], rsi
0x180046203  mov     rcx, rsi; lpCriticalSection
0x180046206  call    cs:__imp_EnterCriticalSection
0x18004620c  nop
0x18004620d  xor     ecx, ecx; void *
0x18004620f  mov     [rsp+0C8h+var_80], rcx
0x180046214  cmp     [rbx+128h], ecx
0x18004621a  jnz     short loc_180046226
0x18004621c  mov     edi, 800704E3h
0x180046221  jmp     loc_1800463FA
0x180046226  mov     rax, [rbx+130h]
0x18004622d  test    rax, rax
0x180046230  jz      loc_1800463F5
0x180046236  lea     r8, [rsp+0C8h+var_80]
0x18004623b  mov     rdx, rdi
0x18004623e  mov     rcx, rax
0x180046241  call    ?GetExtendedDynamicInfo@RpcSession@@QEBAJPEBGAEAV?$RpcStructPtr@U_SCHRPC_TASK_INFO_OUT_2@@@@@Z; RpcSession::GetExtendedDynamicInfo(ushort const *,RpcStructPtr<_SCHRPC_TASK_INFO_OUT_2> &)
0x180046246  mov     edi, eax
0x180046248  mov     [rsp+0C8h+var_98], eax
0x18004624c  test    eax, eax
0x18004624e  jns     short loc_18004625A
0x180046250  mov     rcx, [rsp+0C8h+var_80]
0x180046255  jmp     loc_1800463FE
0x18004625a  mov     rbx, [rsp+0C8h+var_80]
0x18004625f  mov     eax, [rbx]
0x180046261  neg     eax
0x180046263  sbb     cx, cx
0x180046266  mov     [r13+0], cx
0x18004626b  mov     eax, [rbx+4]
0x18004626e  mov     [r14], eax
0x180046271  mov     eax, [rbx+8]
0x180046274  mov     [r15], eax
0x180046277  lea     rcx, [rbx+0Ch]; lpFileTime
0x18004627b  xor     r14d, r14d
0x18004627e  cmp     [rcx+4], r14d
0x180046282  jnz     short loc_18004628E
0x180046284  cmp     [rcx], r14d
0x180046287  jnz     short loc_18004628E
0x180046289  xorps   xmm6, xmm6
0x18004628c  jmp     short loc_1800462F5
0x18004628e  lea     rdx, [rsp+0C8h+SystemTime]; lpSystemTime
0x180046293  call    cs:__imp_FileTimeToSystemTime
0x180046299  test    eax, eax
0x18004629b  jnz     short loc_1800462CB
0x18004629d  call    cs:__imp_GetLastError
0x1800462a3  mov     edi, eax
0x1800462a5  test    eax, eax
0x1800462a7  jle     short loc_1800462B2
0x1800462a9  movzx   edi, ax
0x1800462ac  or      edi, 80070000h
0x1800462b2  mov     rcx, rbx; void *
0x1800462b5  call    MIDL_user_free
0x1800462ba  nop
0x1800462bb  mov     rcx, rsi; lpCriticalSection
0x1800462be  call    cs:__imp_LeaveCriticalSection
0x1800462c4  mov     eax, edi
0x1800462c6  jmp     loc_18004641E
0x1800462cb  xorps   xmm6, xmm6
0x1800462ce  movsd   [rsp+0C8h+var_90], xmm6
0x1800462d4  mov     [rsp+0C8h+var_88], r14d
0x1800462d9  lea     rdx, [rsp+0C8h+var_90]; double *
0x1800462de  lea     rcx, [rsp+0C8h+SystemTime]; struct _SYSTEMTIME *
0x1800462e3  call    ?AtlConvertSystemTimeToVariantTime@ATL@@YAHAEBU_SYSTEMTIME@@PEAN@Z; ATL::AtlConvertSystemTimeToVariantTime(_SYSTEMTIME const &,double *)
0x1800462e8  nop
0x1800462e9  movsd   xmm0, [rsp+0C8h+var_90]
0x1800462ef  movsd   qword ptr [r12], xmm0
0x1800462f5  cmp     [rbx+18h], r14d
0x1800462f9  jnz     short loc_180046301
0x1800462fb  cmp     [rbx+14h], r14d
0x1800462ff  jz      short loc_18004636C
0x180046301  lea     rcx, [rbx+14h]; lpFileTime
0x180046305  lea     rdx, [rsp+0C8h+SystemTime]; lpSystemTime
0x18004630a  call    cs:__imp_FileTimeToSystemTime
0x180046310  test    eax, eax
0x180046312  jnz     short loc_180046342
0x180046314  call    cs:__imp_GetLastError
0x18004631a  mov     edi, eax
0x18004631c  test    eax, eax
0x18004631e  jle     short loc_180046329
0x180046320  movzx   edi, ax
0x180046323  or      edi, 80070000h
0x180046329  mov     rcx, rbx; void *
0x18004632c  call    MIDL_user_free
0x180046331  nop
0x180046332  mov     rcx, rsi; lpCriticalSection
0x180046335  call    cs:__imp_LeaveCriticalSection
0x18004633b  mov     eax, edi
0x18004633d  jmp     loc_18004641E
0x180046342  movsd   [rsp+0C8h+var_90], xmm6
0x180046348  mov     [rsp+0C8h+var_88], r14d
0x18004634d  lea     rdx, [rsp+0C8h+var_90]; double *
0x180046352  lea     rcx, [rsp+0C8h+SystemTime]; struct _SYSTEMTIME *
0x180046357  call    ?AtlConvertSystemTimeToVariantTime@ATL@@YAHAEBU_SYSTEMTIME@@PEAN@Z; ATL::AtlConvertSystemTimeToVariantTime(_SYSTEMTIME const &,double *)
0x18004635c  nop
0x18004635d  movsd   xmm0, [rsp+0C8h+var_90]
0x180046363  mov     rax, [rsp+0C8h+var_78]
0x180046368  movsd   qword ptr [rax], xmm0
0x18004636c  cmp     [rbx+20h], r14d
0x180046370  jnz     short loc_180046378
0x180046372  cmp     [rbx+1Ch], r14d
0x180046376  jz      short loc_1800463E0
0x180046378  lea     rcx, [rbx+1Ch]; lpFileTime
0x18004637c  lea     rdx, [rsp+0C8h+SystemTime]; lpSystemTime
0x180046381  call    cs:__imp_FileTimeToSystemTime
0x180046387  test    eax, eax
0x180046389  jnz     short loc_1800463B6
0x18004638b  call    cs:__imp_GetLastError
0x180046391  mov     edi, eax
0x180046393  test    eax, eax
0x180046395  jle     short loc_1800463A0
0x180046397  movzx   edi, ax
0x18004639a  or      edi, 80070000h
0x1800463a0  mov     rcx, rbx; void *
0x1800463a3  call    MIDL_user_free
0x1800463a8  nop
0x1800463a9  mov     rcx, rsi; lpCriticalSection
0x1800463ac  call    cs:__imp_LeaveCriticalSection
0x1800463b2  mov     eax, edi
0x1800463b4  jmp     short loc_18004641E
0x1800463b6  movsd   [rsp+0C8h+var_90], xmm6
0x1800463bc  mov     [rsp+0C8h+var_88], r14d
0x1800463c1  lea     rdx, [rsp+0C8h+var_90]; double *
0x1800463c6  lea     rcx, [rsp+0C8h+SystemTime]; struct _SYSTEMTIME *
0x1800463cb  call    ?AtlConvertSystemTimeToVariantTime@ATL@@YAHAEBU_SYSTEMTIME@@PEAN@Z; ATL::AtlConvertSystemTimeToVariantTime(_SYSTEMTIME const &,double *)
0x1800463d0  nop
0x1800463d1  movsd   xmm0, [rsp+0C8h+var_90]
0x1800463d7  mov     rax, [rsp+0C8h+var_70]
0x1800463dc  movsd   qword ptr [rax], xmm0
0x1800463e0  mov     rcx, rbx; void *
0x1800463e3  call    MIDL_user_free
0x1800463e8  nop
0x1800463e9  mov     rcx, rsi; lpCriticalSection
0x1800463ec  call    cs:__imp_LeaveCriticalSection
0x1800463f2  nop
0x1800463f3  jmp     short loc_180046415
0x1800463f5  mov     edi, 80070032h
0x1800463fa  mov     [rsp+0C8h+var_98], edi
0x1800463fe  call    MIDL_user_free
0x180046403  nop
0x180046404  mov     rcx, rsi; lpCriticalSection
0x180046407  call    cs:__imp_LeaveCriticalSection
0x18004640d  mov     eax, edi
0x18004640f  jmp     short loc_18004641E
0x180046411  mov     edi, [rsp+0C8h+var_98]
0x180046415  mov     eax, edi
0x180046417  jmp     short loc_18004641E
0x180046419  mov     eax, 80004003h
0x18004641e  mov     rcx, [rsp+0C8h+var_50]
0x180046423  xor     rcx, rsp; StackCookie
0x180046426  call    __security_check_cookie
0x18004642b  movaps  xmm6, [rsp+0C8h+var_48]
0x180046433  add     rsp, 90h
0x18004643a  pop     r15
0x18004643c  pop     r14
0x18004643e  pop     r13
0x180046440  pop     r12
0x180046442  pop     rdi
0x180046443  pop     rsi
0x180046444  pop     rbx
0x180046445  retn
```
