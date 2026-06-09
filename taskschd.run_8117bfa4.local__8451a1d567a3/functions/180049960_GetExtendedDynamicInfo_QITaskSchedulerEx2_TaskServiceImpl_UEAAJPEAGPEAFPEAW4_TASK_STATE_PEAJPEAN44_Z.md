# ?GetExtendedDynamicInfo@?QITaskSchedulerEx2@@TaskServiceImpl@@UEAAJPEAGPEAFPEAW4_TASK_STATE@@PEAJPEAN44@Z

- ea: `0x180049960`
- end: `0x180049c9f`
- name: `?GetExtendedDynamicInfo@?QITaskSchedulerEx2@@TaskServiceImpl@@UEAAJPEAGPEAFPEAW4_TASK_STATE@@PEAJPEAN44@Z`
- size: `831`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000cd10`
- `0x18002e1a8`
- `0x180049960`
- `0x180051dc8`
- `0x180052640`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180049ae0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180049b69`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180049bf2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180049c38`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180049c59`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180049ae0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180049b69`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180049bf2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180049c38`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180049c59`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180049a16`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180049a16`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049ab9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049b42`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049bcb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049ab9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049b42`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049bcb`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180049aa9`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180049b32`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180049bbb`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180049aa9`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180049b32`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180049bbb`

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
0x180049960  mov     rax, rsp
0x180049963  push    rbx
0x180049964  push    rsi
0x180049965  push    rdi
0x180049966  push    r12
0x180049968  push    r13
0x18004996a  push    r14
0x18004996c  push    r15
0x18004996e  sub     rsp, 90h
0x180049975  movaps  xmmword ptr [rax-48h], xmm6
0x180049979  mov     rax, cs:__security_cookie
0x180049980  xor     rax, rsp
0x180049983  mov     [rsp+0C8h+var_50], rax
0x180049988  mov     r14, r9
0x18004998b  mov     r13, r8
0x18004998e  mov     rdi, rdx
0x180049991  mov     rbx, rcx
0x180049994  mov     r15, [rsp+0C8h+arg_20]
0x18004999c  mov     r12, [rsp+0C8h+arg_28]
0x1800499a4  mov     rcx, [rsp+0C8h+arg_30]
0x1800499ac  mov     [rsp+0C8h+var_78], rcx
0x1800499b1  mov     rdx, [rsp+0C8h+arg_38]
0x1800499b9  mov     [rsp+0C8h+var_70], rdx
0x1800499be  xor     r8d, r8d
0x1800499c1  mov     [rsp+0C8h+var_98], r8d
0x1800499c6  xorps   xmm0, xmm0
0x1800499c9  movups  xmmword ptr [rsp+0C8h+SystemTime.wYear], xmm0
0x1800499ce  test    r13, r13
0x1800499d1  jz      loc_180049C71
0x1800499d7  test    r9, r9
0x1800499da  jz      loc_180049C71
0x1800499e0  test    r15, r15
0x1800499e3  jz      loc_180049C71
0x1800499e9  test    r12, r12
0x1800499ec  jz      loc_180049C71
0x1800499f2  mov     [r13+0], r8w
0x1800499f7  mov     [r9], r8d
0x1800499fa  mov     [r15], r8d
0x1800499fd  mov     [r12], r8
0x180049a01  mov     [rcx], r8
0x180049a04  mov     [rdx], r8
0x180049a07  lea     rsi, [rbx+100h]
0x180049a0e  mov     [rsp+0C8h+var_68], rsi
0x180049a13  mov     rcx, rsi; lpCriticalSection
0x180049a16  call    cs:__imp_EnterCriticalSection
0x180049a1d  nop     dword ptr [rax+rax+00h]
0x180049a22  nop
0x180049a23  xor     ecx, ecx; void *
0x180049a25  mov     [rsp+0C8h+var_80], rcx
0x180049a2a  cmp     [rbx+128h], ecx
0x180049a30  jnz     short loc_180049A3C
0x180049a32  mov     edi, 800704E3h
0x180049a37  jmp     loc_180049C4C
0x180049a3c  mov     rax, [rbx+130h]
0x180049a43  test    rax, rax
0x180049a46  jz      loc_180049C47
0x180049a4c  lea     r8, [rsp+0C8h+var_80]
0x180049a51  mov     rdx, rdi
0x180049a54  mov     rcx, rax
0x180049a57  call    ?GetExtendedDynamicInfo@RpcSession@@QEBAJPEBGAEAV?$RpcStructPtr@U_SCHRPC_TASK_INFO_OUT_2@@@@@Z; RpcSession::GetExtendedDynamicInfo(ushort const *,RpcStructPtr<_SCHRPC_TASK_INFO_OUT_2> &)
0x180049a5c  mov     edi, eax
0x180049a5e  mov     [rsp+0C8h+var_98], eax
0x180049a62  test    eax, eax
0x180049a64  jns     short loc_180049A70
0x180049a66  mov     rcx, [rsp+0C8h+var_80]
0x180049a6b  jmp     loc_180049C50
0x180049a70  mov     rbx, [rsp+0C8h+var_80]
0x180049a75  mov     eax, [rbx]
0x180049a77  neg     eax
0x180049a79  sbb     cx, cx
0x180049a7c  mov     [r13+0], cx
0x180049a81  mov     eax, [rbx+4]
0x180049a84  mov     [r14], eax
0x180049a87  mov     eax, [rbx+8]
0x180049a8a  mov     [r15], eax
0x180049a8d  lea     rcx, [rbx+0Ch]; lpFileTime
0x180049a91  xor     r14d, r14d
0x180049a94  cmp     [rcx+4], r14d
0x180049a98  jnz     short loc_180049AA4
0x180049a9a  cmp     [rcx], r14d
0x180049a9d  jnz     short loc_180049AA4
0x180049a9f  xorps   xmm6, xmm6
0x180049aa2  jmp     short loc_180049B1D
0x180049aa4  lea     rdx, [rsp+0C8h+SystemTime]; lpSystemTime
0x180049aa9  call    cs:__imp_FileTimeToSystemTime
0x180049ab0  nop     dword ptr [rax+rax+00h]
0x180049ab5  test    eax, eax
0x180049ab7  jnz     short loc_180049AF3
0x180049ab9  call    cs:__imp_GetLastError
0x180049ac0  nop     dword ptr [rax+rax+00h]
0x180049ac5  mov     edi, eax
0x180049ac7  test    eax, eax
0x180049ac9  jle     short loc_180049AD4
0x180049acb  movzx   edi, ax
0x180049ace  or      edi, 80070000h
0x180049ad4  mov     rcx, rbx; void *
0x180049ad7  call    MIDL_user_free
0x180049adc  nop
0x180049add  mov     rcx, rsi; lpCriticalSection
0x180049ae0  call    cs:__imp_LeaveCriticalSection
0x180049ae7  nop     dword ptr [rax+rax+00h]
0x180049aec  mov     eax, edi
0x180049aee  jmp     loc_180049C76
0x180049af3  xorps   xmm6, xmm6
0x180049af6  movsd   [rsp+0C8h+var_90], xmm6
0x180049afc  mov     [rsp+0C8h+var_88], r14d
0x180049b01  lea     rdx, [rsp+0C8h+var_90]; double *
0x180049b06  lea     rcx, [rsp+0C8h+SystemTime]; struct _SYSTEMTIME *
0x180049b0b  call    ?AtlConvertSystemTimeToVariantTime@ATL@@YAHAEBU_SYSTEMTIME@@PEAN@Z; ATL::AtlConvertSystemTimeToVariantTime(_SYSTEMTIME const &,double *)
0x180049b10  nop
0x180049b11  movsd   xmm0, [rsp+0C8h+var_90]
0x180049b17  movsd   qword ptr [r12], xmm0
0x180049b1d  cmp     [rbx+18h], r14d
0x180049b21  jnz     short loc_180049B29
0x180049b23  cmp     [rbx+14h], r14d
0x180049b27  jz      short loc_180049BA6
0x180049b29  lea     rcx, [rbx+14h]; lpFileTime
0x180049b2d  lea     rdx, [rsp+0C8h+SystemTime]; lpSystemTime
0x180049b32  call    cs:__imp_FileTimeToSystemTime
0x180049b39  nop     dword ptr [rax+rax+00h]
0x180049b3e  test    eax, eax
0x180049b40  jnz     short loc_180049B7C
0x180049b42  call    cs:__imp_GetLastError
0x180049b49  nop     dword ptr [rax+rax+00h]
0x180049b4e  mov     edi, eax
0x180049b50  test    eax, eax
0x180049b52  jle     short loc_180049B5D
0x180049b54  movzx   edi, ax
0x180049b57  or      edi, 80070000h
0x180049b5d  mov     rcx, rbx; void *
0x180049b60  call    MIDL_user_free
0x180049b65  nop
0x180049b66  mov     rcx, rsi; lpCriticalSection
0x180049b69  call    cs:__imp_LeaveCriticalSection
0x180049b70  nop     dword ptr [rax+rax+00h]
0x180049b75  mov     eax, edi
0x180049b77  jmp     loc_180049C76
0x180049b7c  movsd   [rsp+0C8h+var_90], xmm6
0x180049b82  mov     [rsp+0C8h+var_88], r14d
0x180049b87  lea     rdx, [rsp+0C8h+var_90]; double *
0x180049b8c  lea     rcx, [rsp+0C8h+SystemTime]; struct _SYSTEMTIME *
0x180049b91  call    ?AtlConvertSystemTimeToVariantTime@ATL@@YAHAEBU_SYSTEMTIME@@PEAN@Z; ATL::AtlConvertSystemTimeToVariantTime(_SYSTEMTIME const &,double *)
0x180049b96  nop
0x180049b97  movsd   xmm0, [rsp+0C8h+var_90]
0x180049b9d  mov     rax, [rsp+0C8h+var_78]
0x180049ba2  movsd   qword ptr [rax], xmm0
0x180049ba6  cmp     [rbx+20h], r14d
0x180049baa  jnz     short loc_180049BB2
0x180049bac  cmp     [rbx+1Ch], r14d
0x180049bb0  jz      short loc_180049C2C
0x180049bb2  lea     rcx, [rbx+1Ch]; lpFileTime
0x180049bb6  lea     rdx, [rsp+0C8h+SystemTime]; lpSystemTime
0x180049bbb  call    cs:__imp_FileTimeToSystemTime
0x180049bc2  nop     dword ptr [rax+rax+00h]
0x180049bc7  test    eax, eax
0x180049bc9  jnz     short loc_180049C02
0x180049bcb  call    cs:__imp_GetLastError
0x180049bd2  nop     dword ptr [rax+rax+00h]
0x180049bd7  mov     edi, eax
0x180049bd9  test    eax, eax
0x180049bdb  jle     short loc_180049BE6
0x180049bdd  movzx   edi, ax
0x180049be0  or      edi, 80070000h
0x180049be6  mov     rcx, rbx; void *
0x180049be9  call    MIDL_user_free
0x180049bee  nop
0x180049bef  mov     rcx, rsi; lpCriticalSection
0x180049bf2  call    cs:__imp_LeaveCriticalSection
0x180049bf9  nop     dword ptr [rax+rax+00h]
0x180049bfe  mov     eax, edi
0x180049c00  jmp     short loc_180049C76
0x180049c02  movsd   [rsp+0C8h+var_90], xmm6
0x180049c08  mov     [rsp+0C8h+var_88], r14d
0x180049c0d  lea     rdx, [rsp+0C8h+var_90]; double *
0x180049c12  lea     rcx, [rsp+0C8h+SystemTime]; struct _SYSTEMTIME *
0x180049c17  call    ?AtlConvertSystemTimeToVariantTime@ATL@@YAHAEBU_SYSTEMTIME@@PEAN@Z; ATL::AtlConvertSystemTimeToVariantTime(_SYSTEMTIME const &,double *)
0x180049c1c  nop
0x180049c1d  movsd   xmm0, [rsp+0C8h+var_90]
0x180049c23  mov     rax, [rsp+0C8h+var_70]
0x180049c28  movsd   qword ptr [rax], xmm0
0x180049c2c  mov     rcx, rbx; void *
0x180049c2f  call    MIDL_user_free
0x180049c34  nop
0x180049c35  mov     rcx, rsi; lpCriticalSection
0x180049c38  call    cs:__imp_LeaveCriticalSection
0x180049c3f  nop     dword ptr [rax+rax+00h]
0x180049c44  nop
0x180049c45  jmp     short loc_180049C6D
0x180049c47  mov     edi, 80070032h
0x180049c4c  mov     [rsp+0C8h+var_98], edi
0x180049c50  call    MIDL_user_free
0x180049c55  nop
0x180049c56  mov     rcx, rsi; lpCriticalSection
0x180049c59  call    cs:__imp_LeaveCriticalSection
0x180049c60  nop     dword ptr [rax+rax+00h]
0x180049c65  mov     eax, edi
0x180049c67  jmp     short loc_180049C76
0x180049c69  mov     edi, [rsp+0C8h+var_98]
0x180049c6d  mov     eax, edi
0x180049c6f  jmp     short loc_180049C76
0x180049c71  mov     eax, 80004003h
0x180049c76  mov     rcx, [rsp+0C8h+var_50]
0x180049c7b  xor     rcx, rsp; StackCookie
0x180049c7e  call    __security_check_cookie
0x180049c83  movaps  xmm6, [rsp+0C8h+var_48]
0x180049c8b  add     rsp, 90h
0x180049c92  pop     r15
0x180049c94  pop     r14
0x180049c96  pop     r13
0x180049c98  pop     r12
0x180049c9a  pop     rdi
0x180049c9b  pop     rsi
0x180049c9c  pop     rbx
0x180049c9d  retn
```
