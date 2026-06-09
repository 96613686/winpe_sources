# MpObHandleOpenProcessCallback

- ea: `0x14002f510`
- end: `0x14002f9e2`
- name: `MpObHandleOpenProcessCallback`
- size: `1234`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation`

## callers

- `0x14002e380`

## callees

- `0x1400051bc`
- `0x14000dc18`
- `0x1400118d0`
- `0x14002f510`
- `0x140030060`
- `0x140033db0`
- `0x140037820`
- `0x140043520`
- `0x140056b50`
- `0x14006488c`
- `0x140065700`

## import_xrefs

- `ntoskrnl!PsGetProcessId` at `0x14002f60e`
- `ntoskrnl!PsGetProcessId` at `0x14002f6ca`
- `ntoskrnl!PsGetProcessId` at `0x14002f76f`
- `ntoskrnl!PsGetProcessId` at `0x14002f781`
- `ntoskrnl!PsGetProcessId` at `0x14002f60e`
- `ntoskrnl!PsGetProcessId` at `0x14002f6ca`
- `ntoskrnl!PsGetProcessId` at `0x14002f76f`
- `ntoskrnl!PsGetProcessId` at `0x14002f781`
- `ntoskrnl!PsGetProcessCreateTimeQuadPart` at `0x14002f5fc`
- `ntoskrnl!PsGetProcessCreateTimeQuadPart` at `0x14002f6b8`
- `ntoskrnl!PsGetProcessCreateTimeQuadPart` at `0x14002f5fc`
- `ntoskrnl!PsGetProcessCreateTimeQuadPart` at `0x14002f6b8`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14002f6a9`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14002f760`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14002f954`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14002f97c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14002f6a9`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14002f760`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14002f954`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14002f97c`
- `ntoskrnl!ExReleaseResourceLite` at `0x14002f69d`
- `ntoskrnl!ExReleaseResourceLite` at `0x14002f754`
- `ntoskrnl!ExReleaseResourceLite` at `0x14002f948`
- `ntoskrnl!ExReleaseResourceLite` at `0x14002f970`
- `ntoskrnl!ExReleaseResourceLite` at `0x14002f69d`
- `ntoskrnl!ExReleaseResourceLite` at `0x14002f754`
- `ntoskrnl!ExReleaseResourceLite` at `0x14002f948`
- `ntoskrnl!ExReleaseResourceLite` at `0x14002f970`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14002f641`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14002f6fb`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14002f641`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14002f6fb`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14002f62f`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14002f6e9`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14002f62f`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14002f6e9`
- `ntoskrnl!IoGetCurrentProcess` at `0x14002f547`
- `ntoskrnl!IoGetCurrentProcess` at `0x14002f547`
- `ntoskrnl!IoThreadToProcess` at `0x14002f585`
- `ntoskrnl!IoThreadToProcess` at `0x14002f5b1`
- `ntoskrnl!IoThreadToProcess` at `0x14002f585`
- `ntoskrnl!IoThreadToProcess` at `0x14002f5b1`

## pseudocode

```c
void __fastcall MpObHandleOpenProcessCallback(__int64 a1)
{
  __int64 v1; // rbp
  PEPROCESS CurrentProcess; // rax
  struct _KPROCESS *v4; // r13
  struct _KPROCESS *v5; // r12
  struct _KPROCESS *v6; // rbx
  struct _KPROCESS *v7; // rbx
  LONGLONG TimeQuadPart; // r14
  __int64 v9; // rdi
  unsigned __int64 ProcessId; // rsi
  char *v11; // rbx
  _QWORD *v12; // r8
  _QWORD *i; // rax
  LONGLONG v14; // r14
  unsigned __int64 v15; // rsi
  char *v16; // rbx
  _QWORD *v17; // r8
  _QWORD *j; // rax
  __int64 v19; // rbx
  HANDLE v20; // r14
  unsigned int v21; // esi
  int v22; // r8d
  int v23; // r9d
  int v24; // [rsp+40h] [rbp-98h]
  int *v25; // [rsp+48h] [rbp-90h] BYREF
  int v26; // [rsp+50h] [rbp-88h]
  __int128 v27; // [rsp+58h] [rbp-80h] BYREF
  char v28; // [rsp+68h] [rbp-70h] BYREF
  char v29[7]; // [rsp+69h] [rbp-6Fh] BYREF
  _OWORD v30[2]; // [rsp+70h] [rbp-68h] BYREF
  __int64 v31; // [rsp+90h] [rbp-48h]
  int v32; // [rsp+98h] [rbp-40h]

  v1 = 0;
  if ( (*(_DWORD *)(a1 + 4) & 1) == 0 )
  {
    CurrentProcess = IoGetCurrentProcess();
    v4 = *(struct _KPROCESS **)(a1 + 8);
    v5 = CurrentProcess;
    if ( v4 != CurrentProcess )
    {
      v6 = *(struct _KPROCESS **)(MpData + 232);
      if ( IoThreadToProcess(KeGetCurrentThread()) != v6 )
      {
        v7 = *(struct _KPROCESS **)(MpData + 256);
        if ( IoThreadToProcess(KeGetCurrentThread()) != v7 && (*(_DWORD *)a1 == 1 || *(_DWORD *)a1 == 2) )
        {
          v25 = *(int **)(a1 + 32);
          v24 = *v25;
          TimeQuadPart = PsGetProcessCreateTimeQuadPart(v5);
          v9 = 0;
          ProcessId = (unsigned __int64)PsGetProcessId(v5);
          if ( ProcessId )
          {
            v11 = (char *)MpProcessTable;
            KeEnterCriticalRegion();
            ExAcquireResourceSharedLite((PERESOURCE)(v11 + 8), 1u);
            v12 = (_QWORD *)(*((_QWORD *)MpProcessTable + 48) + 16 * ((ProcessId >> 2) & 0x7F));
            for ( i = (_QWORD *)*v12; ; i = (_QWORD *)*i )
            {
              if ( i == v12 )
              {
                ExReleaseResourceLite((PERESOURCE)((char *)MpProcessTable + 8));
                KeLeaveCriticalRegion();
                v9 = 0;
                goto LABEL_33;
              }
              v9 = (__int64)(i - 1);
              if ( ProcessId == i[2] && TimeQuadPart == *(_QWORD *)(v9 + 32) )
                break;
            }
            _InterlockedIncrement((volatile signed __int32 *)(v9 + 48));
            ExReleaseResourceLite((PERESOURCE)((char *)MpProcessTable + 8));
            KeLeaveCriticalRegion();
            v14 = PsGetProcessCreateTimeQuadPart(v4);
            v15 = (unsigned __int64)PsGetProcessId(v4);
            if ( v15 )
            {
              v16 = (char *)MpProcessTable;
              KeEnterCriticalRegion();
              ExAcquireResourceSharedLite((PERESOURCE)(v16 + 8), 1u);
              v17 = (_QWORD *)(*((_QWORD *)MpProcessTable + 48) + 16 * ((v15 >> 2) & 0x7F));
              for ( j = (_QWORD *)*v17; ; j = (_QWORD *)*j )
              {
                if ( j == v17 )
                {
                  ExReleaseResourceLite((PERESOURCE)((char *)MpProcessTable + 8));
                  KeLeaveCriticalRegion();
                  goto LABEL_26;
                }
                v19 = (__int64)(j - 1);
                if ( v15 == j[2] && v14 == *(_QWORD *)(v19 + 32) )
                  break;
              }
              _InterlockedIncrement((volatile signed __int32 *)(v19 + 48));
              ExReleaseResourceLite((PERESOURCE)((char *)MpProcessTable + 8));
              KeLeaveCriticalRegion();
              v20 = PsGetProcessId(v5);
              v29[0] = 0;
              v21 = (unsigned int)PsGetProcessId(v4);
              v28 = 0;
              MpObHipsCallback(a1, (_DWORD)v25, (_DWORD)v20, v21, v9, v19, (__int64)v29, (__int64)&v28);
              MpObSendOpenProcessBMNotification(v20, v24, *v25, v29[0], v28);
              MpObDoHardening(v25, v9, v19);
              v1 = v19;
              if ( (_DWORD)v20 )
              {
                if ( v21 )
                {
                  if ( !v9 )
                    goto LABEL_28;
                  if ( v19 && (*(_DWORD *)(v9 + 60) & 4) != 0 )
                  {
                    v31 = 0;
                    v32 = 0;
                    memset(v30, 0, sizeof(v30));
                    MpObOperationFillSyncData(a1, v9, v22, v23, v19, (__int64)v30);
                    v27 = 0;
                    MpGetPriorityInfo(0, 0, &v27);
                    v25 = 0;
                    v26 = 0;
                    GetMpUniquePidFromProcessId(v20, &v25);
                    MpSendSyncMonitorNotification(8, (unsigned int)&v25, (unsigned int)v30, (unsigned int)&v27, v9 + 56);
                  }
LABEL_27:
                  MpReleaseProcessContext(v9);
LABEL_28:
                  if ( v1 )
                    MpReleaseProcessContext(v1);
                  return;
                }
              }
            }
          }
          else
          {
LABEL_33:
            if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
              return;
            if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
            {
              _mm_lfence();
              WPP_SF_qD(
                WPP_GLOBAL_Control->AttachedDevice,
                22,
                WPP_987d9fc7520d333ff9fdca1fa9c66d57_Traceguids,
                KeGetCurrentThread(),
                -1073741275);
            }
          }
LABEL_26:
          if ( !v9 )
            goto LABEL_28;
          goto LABEL_27;
        }
      }
    }
  }
}

```

## disassembly

```asm
0x14002f510  mov     r11, rsp
0x14002f513  push    rbp
0x14002f514  push    r15
0x14002f516  sub     rsp, 0C8h
0x14002f51d  mov     rax, cs:__security_cookie
0x14002f524  xor     rax, rsp
0x14002f527  mov     [rsp+0D8h+var_38], rax
0x14002f52f  mov     eax, [rcx+4]
0x14002f532  xor     ebp, ebp
0x14002f534  mov     r15, rcx
0x14002f537  test    al, 1
0x14002f539  jnz     loc_14002F921
0x14002f53f  mov     [r11-18h], r12
0x14002f543  mov     [r11-20h], r13
0x14002f547  call    cs:__imp_IoGetCurrentProcess
0x14002f54e  nop     dword ptr [rax+rax+00h]
0x14002f553  mov     r13, [r15+8]
0x14002f557  mov     r12, rax
0x14002f55a  cmp     r13, rax
0x14002f55d  jz      loc_14002F911
0x14002f563  mov     rdx, gs:188h
0x14002f56c  mov     rcx, cs:MpData
0x14002f573  mov     [rsp+0D8h+arg_8], rbx
0x14002f57b  mov     rbx, [rcx+0E8h]
0x14002f582  mov     rcx, rdx; Thread
0x14002f585  call    cs:__imp_IoThreadToProcess
0x14002f58c  nop     dword ptr [rax+rax+00h]
0x14002f591  cmp     rax, rbx
0x14002f594  jz      loc_14002F909
0x14002f59a  mov     rcx, gs:188h; Thread
0x14002f5a3  mov     rax, cs:MpData
0x14002f5aa  mov     rbx, [rax+100h]
0x14002f5b1  call    cs:__imp_IoThreadToProcess
0x14002f5b8  nop     dword ptr [rax+rax+00h]
0x14002f5bd  cmp     rax, rbx
0x14002f5c0  jz      loc_14002F909
0x14002f5c6  mov     eax, [r15]
0x14002f5c9  cmp     eax, 1
0x14002f5cc  jnz     loc_14002F8CC
0x14002f5d2  mov     [rsp+0D8h+arg_10], rsi
0x14002f5da  mov     rcx, r12; Process
0x14002f5dd  mov     [rsp+0D8h+arg_18], rdi
0x14002f5e5  mov     [rsp+0D8h+var_28], r14
0x14002f5ed  mov     rax, [r15+20h]
0x14002f5f1  mov     [rsp+0D8h+var_90], rax
0x14002f5f6  mov     eax, [rax]
0x14002f5f8  mov     [rsp+0D8h+var_98], eax
0x14002f5fc  call    cs:__imp_PsGetProcessCreateTimeQuadPart
0x14002f603  nop     dword ptr [rax+rax+00h]
0x14002f608  mov     rcx, r12; Process
0x14002f60b  mov     r14, rax
0x14002f60e  call    cs:__imp_PsGetProcessId
0x14002f615  nop     dword ptr [rax+rax+00h]
0x14002f61a  xor     edi, edi
0x14002f61c  mov     rsi, rax
0x14002f61f  test    rax, rax
0x14002f622  jz      loc_14002F98A
0x14002f628  mov     rbx, cs:MpProcessTable
0x14002f62f  call    cs:__imp_KeEnterCriticalRegion
0x14002f636  nop     dword ptr [rax+rax+00h]
0x14002f63b  mov     dl, 1; Wait
0x14002f63d  lea     rcx, [rbx+8]; Resource
0x14002f641  call    cs:__imp_ExAcquireResourceSharedLite
0x14002f648  nop     dword ptr [rax+rax+00h]
0x14002f64d  mov     rax, cs:MpProcessTable
0x14002f654  mov     r8, rsi
0x14002f657  shr     r8, 2
0x14002f65b  and     r8d, 7Fh
0x14002f65f  shl     r8, 4
0x14002f663  add     r8, [rax+180h]
0x14002f66a  mov     rax, [r8]
0x14002f66d  nop     dword ptr [rax]
0x14002f670  cmp     rax, r8
0x14002f673  jz      loc_14002F965
0x14002f679  cmp     rsi, [rax+10h]
0x14002f67d  lea     rdi, [rax-8]
0x14002f681  jz      short loc_14002F688
0x14002f683  mov     rax, [rax]
0x14002f686  jmp     short loc_14002F670
0x14002f688  cmp     r14, [rdi+20h]
0x14002f68c  jnz     short loc_14002F683
0x14002f68e  lock inc dword ptr [rdi+30h]
0x14002f692  mov     rcx, cs:MpProcessTable
0x14002f699  add     rcx, 8; Resource
0x14002f69d  call    cs:__imp_ExReleaseResourceLite
0x14002f6a4  nop     dword ptr [rax+rax+00h]
0x14002f6a9  call    cs:__imp_KeLeaveCriticalRegion
0x14002f6b0  nop     dword ptr [rax+rax+00h]
0x14002f6b5  mov     rcx, r13; Process
0x14002f6b8  call    cs:__imp_PsGetProcessCreateTimeQuadPart
0x14002f6bf  nop     dword ptr [rax+rax+00h]
0x14002f6c4  mov     rcx, r13; Process
0x14002f6c7  mov     r14, rax
0x14002f6ca  call    cs:__imp_PsGetProcessId
0x14002f6d1  nop     dword ptr [rax+rax+00h]
0x14002f6d6  mov     rsi, rax
0x14002f6d9  test    rax, rax
0x14002f6dc  jz      loc_14002F8D7
0x14002f6e2  mov     rbx, cs:MpProcessTable
0x14002f6e9  call    cs:__imp_KeEnterCriticalRegion
0x14002f6f0  nop     dword ptr [rax+rax+00h]
0x14002f6f5  mov     dl, 1; Wait
0x14002f6f7  lea     rcx, [rbx+8]; Resource
0x14002f6fb  call    cs:__imp_ExAcquireResourceSharedLite
0x14002f702  nop     dword ptr [rax+rax+00h]
0x14002f707  mov     rax, cs:MpProcessTable
0x14002f70e  mov     r8, rsi
0x14002f711  shr     r8, 2
0x14002f715  and     r8d, 7Fh
0x14002f719  shl     r8, 4
0x14002f71d  add     r8, [rax+180h]
0x14002f724  mov     rax, [r8]
0x14002f727  cmp     rax, r8
0x14002f72a  jz      loc_14002F93D
0x14002f730  cmp     rsi, [rax+10h]
0x14002f734  lea     rbx, [rax-8]
0x14002f738  jz      short loc_14002F73F
0x14002f73a  mov     rax, [rax]
0x14002f73d  jmp     short loc_14002F727
0x14002f73f  cmp     r14, [rbx+20h]
0x14002f743  jnz     short loc_14002F73A
0x14002f745  lock inc dword ptr [rbx+30h]
0x14002f749  mov     rcx, cs:MpProcessTable
0x14002f750  add     rcx, 8; Resource
0x14002f754  call    cs:__imp_ExReleaseResourceLite
0x14002f75b  nop     dword ptr [rax+rax+00h]
0x14002f760  call    cs:__imp_KeLeaveCriticalRegion
0x14002f767  nop     dword ptr [rax+rax+00h]
0x14002f76c  mov     rcx, r12; Process
0x14002f76f  call    cs:__imp_PsGetProcessId
0x14002f776  nop     dword ptr [rax+rax+00h]
0x14002f77b  mov     rcx, r13; Process
0x14002f77e  mov     r14, rax
0x14002f781  call    cs:__imp_PsGetProcessId
0x14002f788  nop     dword ptr [rax+rax+00h]
0x14002f78d  mov     [rsp+0D8h+var_6F], bpl
0x14002f792  mov     r8, r14
0x14002f795  mov     rsi, rax
0x14002f798  mov     [rsp+0D8h+var_70], bpl
0x14002f79d  mov     rbp, [rsp+0D8h+var_90]
0x14002f7a2  lea     rax, [rsp+0D8h+var_70]
0x14002f7a7  mov     qword ptr [rsp+0D8h+var_A0], rax
0x14002f7ac  mov     r9, rsi
0x14002f7af  lea     rax, [rsp+0D8h+var_6F]
0x14002f7b4  mov     rdx, rbp
0x14002f7b7  mov     qword ptr [rsp+0D8h+var_A8], rax
0x14002f7bc  mov     rcx, r15
0x14002f7bf  mov     qword ptr [rsp+0D8h+var_B0], rbx
0x14002f7c4  mov     qword ptr [rsp+0D8h+var_B8], rdi
0x14002f7c9  call    MpObHipsCallback
0x14002f7ce  movzx   ecx, [rsp+0D8h+var_70]
0x14002f7d3  mov     r9, rbx
0x14002f7d6  movzx   eax, [rsp+0D8h+var_6F]
0x14002f7db  mov     r8, rdi
0x14002f7de  mov     [rsp+0D8h+var_A0], cl; char
0x14002f7e2  mov     rdx, rsi
0x14002f7e5  mov     [rsp+0D8h+var_A8], al; char
0x14002f7e9  mov     rcx, r14; ProcessId
0x14002f7ec  mov     eax, [rbp+0]
0x14002f7ef  mov     [rsp+0D8h+var_B0], eax; int
0x14002f7f3  mov     eax, [rsp+0D8h+var_98]
0x14002f7f7  mov     [rsp+0D8h+var_B8], eax; int
0x14002f7fb  call    MpObSendOpenProcessBMNotification
0x14002f800  mov     r8, rbx
0x14002f803  mov     rdx, rdi
0x14002f806  mov     rcx, rbp
0x14002f809  call    MpObDoHardening
0x14002f80e  mov     rbp, rbx
0x14002f811  test    r14d, r14d
0x14002f814  jz      loc_14002F8D7
0x14002f81a  test    esi, esi
0x14002f81c  jz      loc_14002F8D7
0x14002f822  test    rdi, rdi
0x14002f825  jz      loc_14002F8E4
0x14002f82b  test    rbx, rbx
0x14002f82e  jz      loc_14002F8DC
0x14002f834  mov     eax, [rdi+3Ch]
0x14002f837  test    al, 4
0x14002f839  jz      loc_14002F8DC
0x14002f83f  xor     eax, eax
0x14002f841  xorps   xmm0, xmm0
0x14002f844  mov     [rsp+0D8h+var_48], rax
0x14002f84c  mov     rdx, rdi
0x14002f84f  mov     [rsp+0D8h+var_40], eax
0x14002f856  mov     rcx, r15
0x14002f859  lea     rax, [rsp+0D8h+var_68]
0x14002f85e  mov     qword ptr [rsp+0D8h+var_B0], rax
0x14002f863  mov     qword ptr [rsp+0D8h+var_B8], rbx
0x14002f868  movups  [rsp+0D8h+var_68], xmm0
0x14002f86d  movups  [rsp+0D8h+var_58], xmm0
0x14002f875  call    MpObOperationFillSyncData
0x14002f87a  xorps   xmm0, xmm0
0x14002f87d  lea     r8, [rsp+0D8h+var_80]
0x14002f882  xor     edx, edx
0x14002f884  xor     ecx, ecx
0x14002f886  movups  [rsp+0D8h+var_80], xmm0
0x14002f88b  call    MpGetPriorityInfo
0x14002f890  xor     eax, eax
0x14002f892  lea     rdx, [rsp+0D8h+var_90]
0x14002f897  mov     rcx, r14
0x14002f89a  mov     [rsp+0D8h+var_90], rax
0x14002f89f  mov     [rsp+0D8h+var_88], eax
0x14002f8a3  call    GetMpUniquePidFromProcessId
0x14002f8a8  lea     rax, [rdi+38h]
0x14002f8ac  mov     ecx, 8
0x14002f8b1  lea     r9, [rsp+0D8h+var_80]
0x14002f8b6  mov     qword ptr [rsp+0D8h+var_B8], rax
0x14002f8bb  lea     r8, [rsp+0D8h+var_68]
0x14002f8c0  lea     rdx, [rsp+0D8h+var_90]
0x14002f8c5  call    MpSendSyncMonitorNotification
0x14002f8ca  jmp     short loc_14002F8DC
0x14002f8cc  cmp     eax, 2
0x14002f8cf  jz      loc_14002F5D2
0x14002f8d5  jmp     short loc_14002F909
0x14002f8d7  test    rdi, rdi
0x14002f8da  jz      short loc_14002F8E4
0x14002f8dc  mov     rcx, rdi
0x14002f8df  call    MpReleaseProcessContext
0x14002f8e4  test    rbp, rbp
0x14002f8e7  jz      short loc_14002F8F1
0x14002f8e9  mov     rcx, rbp
0x14002f8ec  call    MpReleaseProcessContext
0x14002f8f1  mov     rdi, [rsp+0D8h+arg_18]
0x14002f8f9  mov     rsi, [rsp+0D8h+arg_10]
0x14002f901  mov     r14, [rsp+0D8h+var_28]
0x14002f909  mov     rbx, [rsp+0D8h+arg_8]
0x14002f911  mov     r12, [rsp+0D8h+var_18]
0x14002f919  mov     r13, [rsp+0D8h+var_20]
0x14002f921  mov     rcx, [rsp+0D8h+var_38]
0x14002f929  xor     rcx, rsp; StackCookie
0x14002f92c  call    __security_check_cookie
0x14002f931  add     rsp, 0C8h
0x14002f938  pop     r15
0x14002f93a  pop     rbp
0x14002f93b  retn
0x14002f93d  mov     rcx, cs:MpProcessTable
0x14002f944  add     rcx, 8; Resource
0x14002f948  call    cs:__imp_ExReleaseResourceLite
0x14002f94f  nop     dword ptr [rax+rax+00h]
0x14002f954  call    cs:__imp_KeLeaveCriticalRegion
0x14002f95b  nop     dword ptr [rax+rax+00h]
0x14002f960  jmp     loc_14002F8D7
0x14002f965  mov     rcx, cs:MpProcessTable
0x14002f96c  add     rcx, 8; Resource
0x14002f970  call    cs:__imp_ExReleaseResourceLite
0x14002f977  nop     dword ptr [rax+rax+00h]
0x14002f97c  call    cs:__imp_KeLeaveCriticalRegion
0x14002f983  nop     dword ptr [rax+rax+00h]
0x14002f988  xor     edi, edi
0x14002f98a  mov     ecx, 0C0000225h
0x14002f98f  mov     rax, cs:WPP_GLOBAL_Control
0x14002f996  lea     rdx, WPP_GLOBAL_Control
0x14002f99d  cmp     rax, rdx
0x14002f9a0  jz      loc_14002F8F1
0x14002f9a6  mov     eax, [rax+2Ch]
0x14002f9a9  test    al, 1
0x14002f9ab  jz      loc_14002F8D7
0x14002f9b1  lfence
0x14002f9b4  mov     r9, gs:188h
0x14002f9bd  lea     r8, WPP_987d9fc7520d333ff9fdca1fa9c66d57_Traceguids
0x14002f9c4  mov     [rsp+0D8h+var_B8], ecx
0x14002f9c8  mov     edx, 16h
0x14002f9cd  mov     rcx, cs:WPP_GLOBAL_Control
0x14002f9d4  mov     rcx, [rcx+18h]
0x14002f9d8  call    WPP_SF_qD
0x14002f9dd  jmp     loc_14002F8D7
```
