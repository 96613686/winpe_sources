# NsiNotifications::NotificationTracking::NeighborChangeCallback(void *,_NSI_KEYSTRUCT_DESC *,_NSI_SINGLE_PARAM_DESC *,_NSI_NOTIFICATION)

- ea: `0x18009da60`
- end: `0x18009dea4`
- name: `?NeighborChangeCallback@NotificationTracking@NsiNotifications@@CAXPEAXPEAU_NSI_KEYSTRUCT_DESC@@PEAU_NSI_SINGLE_PARAM_DESC@@W4_NSI_NOTIFICATION@@@Z`
- size: `1092`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `broker_com_uri`

## callees

- `0x180026e68`
- `0x180027630`
- `0x180084f50`
- `0x180099440`
- `0x1800994dc`
- `0x180099580`
- `0x18009961c`
- `0x1800996c0`
- `0x1800996fc`
- `0x1800997c4`
- `0x180099860`
- `0x18009da60`
- `0x1800a1850`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009dd04`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009dd36`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009ddef`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009de3a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009de68`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009dd04`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009dd36`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009ddef`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009de3a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009de68`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18009dd4b`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18009de7d`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18009dd4b`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18009de7d`
- `NSI!NsiFreeTable` at `0x18009dd77`
- `NSI!NsiFreeTable` at `0x18009dd77`
- `NSI!NsiAllocateAndGetTable` at `0x18009dbb8`
- `NSI!NsiAllocateAndGetTable` at `0x18009dbb8`

## pseudocode

```c
void __fastcall NsiNotifications::NotificationTracking::NeighborChangeCallback(__int64 **a1, __int64 a2)
{
  __int64 *v2; // rsi
  __int64 v3; // rbx
  __int64 **v4; // r8
  unsigned int v5; // r9d
  __int64 *v6; // r10
  int v7; // eax
  bool v8; // zf
  unsigned __int8 v9; // di
  const NPI_MODULEID *v10; // rdx
  LPCRITICAL_SECTION *v11; // r9
  unsigned int Table; // eax
  unsigned int v13; // r15d
  __int64 v14; // rdx
  LPCRITICAL_SECTION v15; // rcx
  __int64 v16; // rcx
  __int128 v17; // xmm0
  struct _TP_WORK *v18; // rcx
  __int64 v19; // rdi
  LPCRITICAL_SECTION lpCriticalSection[2]; // [rsp+70h] [rbp-90h] BYREF
  __int128 v21; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v22[80]; // [rsp+90h] [rbp-70h]
  int v23; // [rsp+E0h] [rbp-20h]
  LPCRITICAL_SECTION v24; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v25; // [rsp+F8h] [rbp-8h]
  __int64 v26; // [rsp+100h] [rbp+0h]
  __int64 v27; // [rsp+108h] [rbp+8h]
  struct _RTL_CRITICAL_SECTION *v28; // [rsp+110h] [rbp+10h] BYREF
  unsigned int v29; // [rsp+118h] [rbp+18h]
  wil::details::in1diag3 *retaddr; // [rsp+178h] [rbp+78h]

  v2 = *a1;
  v3 = **a1;
  if ( !(unsigned __int8)std::_Atomic_storage<bool,1>::load(v3, a2, a1) )
  {
    if ( v5 )
    {
      switch ( v5 )
      {
        case 1u:
          v7 = *((_DWORD *)v2 + 50) >> 1;
          break;
        case 2u:
          v7 = *((_DWORD *)v2 + 50) >> 2;
          break;
        case 3u:
          v7 = *((_DWORD *)v2 + 50) >> 3;
          break;
        default:
          return;
      }
      v8 = (v7 & 1) == 0;
    }
    else
    {
      v8 = (v2[25] & 1) == 0;
    }
    if ( !v8 )
    {
      if ( *((_DWORD *)v4 + 2) == 1 )
      {
        v9 = 1;
        v10 = &NPI_MS_IPV4_MODULEID;
      }
      else
      {
        v9 = 0;
        v10 = &NPI_MS_IPV6_MODULEID;
      }
      if ( v5 > 2 )
      {
        v28 = 0;
        v24 = 0;
        v27 = 0;
        v26 = 0;
        v25 = 0;
        v29 = 0;
        v11 = &v24;
        if ( v9 )
          v11 = &v28;
        Table = NsiAllocateAndGetTable(1, v10, 11, v11);
        if ( Table )
        {
          wil::details::in1diag3::_Log_Win32(
            retaddr,
            (void *)0x6E9,
            (unsigned int)"onecore\\private\\net\\inc\\nsinotificationtracking.h",
            (const char *)Table,
            8 * (v9 ^ 1) + 24);
LABEL_36:
          v15 = v28;
          if ( !v9 )
            v15 = v24;
          NsiFreeTable(v15, v27, v26, v25);
          return;
        }
        v13 = 0;
        if ( !v29 )
          goto LABEL_36;
        while ( 1 )
        {
          v14 = 32LL * v13;
          *(_QWORD *)&v21 = v3;
          *((_QWORD *)&v21 + 1) = v2;
          lpCriticalSection[0] = 0;
          if ( v9 )
          {
            *(_OWORD *)v22 = *(_OWORD *)(&v28->DebugInfo + 3 * v13);
            *(_QWORD *)&v22[16] = *((_QWORD *)&v28->OwningThread + 3 * v13);
            *(_OWORD *)&v22[24] = *(_OWORD *)(v14 + v27);
            *(_OWORD *)&v22[40] = *(_OWORD *)(v14 + v27 + 16);
            *(_OWORD *)&v22[56] = *(_OWORD *)(v26 + 16LL * v13);
            *(_DWORD *)&v22[72] = *(_DWORD *)(v25 + 4LL * v13);
            wil::EnterCriticalSection(lpCriticalSection, v3 + 1632);
            if ( *(_BYTE *)(v3 + 1896) )
              goto LABEL_27;
            if ( *(_DWORD *)(v3 + 1624) == 1 )
              ___emplace_back_V_lambda_2___BA___NeighborChangeCallback_NotificationTracking_NsiNotifications__CAXPEAXPEAU_NSI_KEYSTRUCT_DESC__PEAU_NSI_SINGLE_PARAM_DESC__W4_NSI_NOTIFICATION___Z____deque_V__function___A6AXXZ_std__V__allocator_V__function___A6AXXZ_std___2__std__QEAAAEAV__function___A6AXXZ_1___QEAV_lambda_2___BA___NeighborChangeCallback_NotificationTracking_NsiNotifications__CAXPEAXPEAU_NSI_KEYSTRUCT_DESC__PEAU_NSI_SINGLE_PARAM_DESC__W4_NSI_NOTIFICATION___Z__Z(
                v3 + 1776,
                &v21);
            else
              ___emplace_back_V_lambda_2___BA___NeighborChangeCallback_NotificationTracking_NsiNotifications__CAXPEAXPEAU_NSI_KEYSTRUCT_DESC__PEAU_NSI_SINGLE_PARAM_DESC__W4_NSI_NOTIFICATION___Z____deque_V__variant_V__function___A6AXXZ_std__V__shared_ptr_VBaseThreadPoolWaitableResult_WcmCommon___2__std__V__allocator_V__variant_V__function___A6AXXZ_std__V__shared_ptr_VBaseThreadPoolWaitableResult_WcmCommon___2__std___2__std__QEAAAEAV__variant_V__function___A6AXXZ_std__V__shared_ptr_VBaseThreadPoolWaitableResult_WcmCommon___2__1___QEAV_lambda_2___BA___NeighborChangeCallback_NotificationTracking_NsiNotifications__CAXPEAXPEAU_NSI_KEYSTRUCT_DESC__PEAU_NSI_SINGLE_PARAM_DESC__W4_NSI_NOTIFICATION___Z__Z(
                (_QWORD *)(v3 + 1856),
                (__int64)&v21);
          }
          else
          {
            *(_OWORD *)v22 = *(_OWORD *)((char *)&v24->DebugInfo + v14);
            *(_OWORD *)&v22[16] = *(_OWORD *)((char *)&v24->OwningThread + v14);
            *(_OWORD *)&v22[32] = *(_OWORD *)(v14 + v27);
            *(_OWORD *)&v22[48] = *(_OWORD *)(v14 + v27 + 16);
            *(_OWORD *)&v22[64] = *(_OWORD *)(v26 + 16LL * v13);
            v23 = *(_DWORD *)(v25 + 4LL * v13);
            wil::EnterCriticalSection(lpCriticalSection, v3 + 1632);
            if ( *(_BYTE *)(v3 + 1896) )
            {
LABEL_27:
              if ( lpCriticalSection[0] )
                LeaveCriticalSection(lpCriticalSection[0]);
              goto LABEL_35;
            }
            if ( *(_DWORD *)(v3 + 1624) == 1 )
              ___emplace_back_V_lambda_3___BC___NeighborChangeCallback_NotificationTracking_NsiNotifications__CAXPEAXPEAU_NSI_KEYSTRUCT_DESC__PEAU_NSI_SINGLE_PARAM_DESC__W4_NSI_NOTIFICATION___Z____deque_V__function___A6AXXZ_std__V__allocator_V__function___A6AXXZ_std___2__std__QEAAAEAV__function___A6AXXZ_1___QEAV_lambda_3___BC___NeighborChangeCallback_NotificationTracking_NsiNotifications__CAXPEAXPEAU_NSI_KEYSTRUCT_DESC__PEAU_NSI_SINGLE_PARAM_DESC__W4_NSI_NOTIFICATION___Z__Z(
                v3 + 1776,
                &v21);
            else
              ___emplace_back_V_lambda_3___BC___NeighborChangeCallback_NotificationTracking_NsiNotifications__CAXPEAXPEAU_NSI_KEYSTRUCT_DESC__PEAU_NSI_SINGLE_PARAM_DESC__W4_NSI_NOTIFICATION___Z____deque_V__variant_V__function___A6AXXZ_std__V__shared_ptr_VBaseThreadPoolWaitableResult_WcmCommon___2__std__V__allocator_V__variant_V__function___A6AXXZ_std__V__shared_ptr_VBaseThreadPoolWaitableResult_WcmCommon___2__std___2__std__QEAAAEAV__variant_V__function___A6AXXZ_std__V__shared_ptr_VBaseThreadPoolWaitableResult_WcmCommon___2__1___QEAV_lambda_3___BC___NeighborChangeCallback_NotificationTracking_NsiNotifications__CAXPEAXPEAU_NSI_KEYSTRUCT_DESC__PEAU_NSI_SINGLE_PARAM_DESC__W4_NSI_NOTIFICATION___Z__Z(
                (_QWORD *)(v3 + 1856),
                (__int64)&v21);
          }
          if ( lpCriticalSection[0] )
            LeaveCriticalSection(lpCriticalSection[0]);
          _InterlockedIncrement64((volatile signed __int64 *)(v3 + 1760));
          SubmitThreadpoolWork(*(PTP_WORK *)(v3 + 1752));
LABEL_35:
          if ( ++v13 >= v29 )
            goto LABEL_36;
        }
      }
      v16 = *v6;
      *(_QWORD *)&v21 = v3;
      *((_QWORD *)&v21 + 1) = v2;
      *(_DWORD *)v22 = v5;
      v17 = *(_OWORD *)(v16 + 8);
      v24 = 0;
      *(_OWORD *)&v22[8] = v17;
      if ( v9 )
      {
        *(_QWORD *)&v22[24] = *(_QWORD *)(v16 + 24);
        wil::EnterCriticalSection(&v24, v3 + 1632);
        if ( !*(_BYTE *)(v3 + 1896) )
        {
          if ( *(_DWORD *)(v3 + 1624) == 1 )
            ___emplace_back_V_lambda_4___BG___NeighborChangeCallback_NotificationTracking_NsiNotifications__CAXPEAXPEAU_NSI_KEYSTRUCT_DESC__PEAU_NSI_SINGLE_PARAM_DESC__W4_NSI_NOTIFICATION___Z____deque_V__function___A6AXXZ_std__V__allocator_V__function___A6AXXZ_std___2__std__QEAAAEAV__function___A6AXXZ_1___QEAV_lambda_4___BG___NeighborChangeCallback_NotificationTracking_NsiNotifications__CAXPEAXPEAU_NSI_KEYSTRUCT_DESC__PEAU_NSI_SINGLE_PARAM_DESC__W4_NSI_NOTIFICATION___Z__Z(
              v3 + 1776,
              &v21);
          else
            ___emplace_back_V_lambda_4___BG___NeighborChangeCallback_NotificationTracking_NsiNotifications__CAXPEAXPEAU_NSI_KEYSTRUCT_DESC__PEAU_NSI_SINGLE_PARAM_DESC__W4_NSI_NOTIFICATION___Z____deque_V__variant_V__function___A6AXXZ_std__V__shared_ptr_VBaseThreadPoolWaitableResult_WcmCommon___2__std__V__allocator_V__variant_V__function___A6AXXZ_std__V__shared_ptr_VBaseThreadPoolWaitableResult_WcmCommon___2__std___2__std__QEAAAEAV__variant_V__function___A6AXXZ_std__V__shared_ptr_VBaseThreadPoolWaitableResult_WcmCommon___2__1___QEAV_lambda_4___BG___NeighborChangeCallback_NotificationTracking_NsiNotifications__CAXPEAXPEAU_NSI_KEYSTRUCT_DESC__PEAU_NSI_SINGLE_PARAM_DESC__W4_NSI_NOTIFICATION___Z__Z(
              (_QWORD *)(v3 + 1856),
              &v21);
          if ( v24 )
            LeaveCriticalSection(v24);
          _InterlockedIncrement64((volatile signed __int64 *)(v3 + 1760));
          v18 = *(struct _TP_WORK **)(v3 + 1752);
LABEL_56:
          SubmitThreadpoolWork(v18);
          return;
        }
      }
      else
      {
        v19 = **v4;
        *(_OWORD *)&v22[24] = *(_OWORD *)(v16 + 24);
        wil::EnterCriticalSection(&v24, v19 + 1632);
        if ( !*(_BYTE *)(v19 + 1896) )
        {
          if ( *(_DWORD *)(v19 + 1624) == 1 )
            ___emplace_back_V_lambda_5___BI___NeighborChangeCallback_NotificationTracking_NsiNotifications__CAXPEAXPEAU_NSI_KEYSTRUCT_DESC__PEAU_NSI_SINGLE_PARAM_DESC__W4_NSI_NOTIFICATION___Z____deque_V__function___A6AXXZ_std__V__allocator_V__function___A6AXXZ_std___2__std__QEAAAEAV__function___A6AXXZ_1___QEAV_lambda_5___BI___NeighborChangeCallback_NotificationTracking_NsiNotifications__CAXPEAXPEAU_NSI_KEYSTRUCT_DESC__PEAU_NSI_SINGLE_PARAM_DESC__W4_NSI_NOTIFICATION___Z__Z(
              v19 + 1776,
              &v21);
          else
            ___emplace_back_V_lambda_5___BI___NeighborChangeCallback_NotificationTracking_NsiNotifications__CAXPEAXPEAU_NSI_KEYSTRUCT_DESC__PEAU_NSI_SINGLE_PARAM_DESC__W4_NSI_NOTIFICATION___Z____deque_V__variant_V__function___A6AXXZ_std__V__shared_ptr_VBaseThreadPoolWaitableResult_WcmCommon___2__std__V__allocator_V__variant_V__function___A6AXXZ_std__V__shared_ptr_VBaseThreadPoolWaitableResult_WcmCommon___2__std___2__std__QEAAAEAV__variant_V__function___A6AXXZ_std__V__shared_ptr_VBaseThreadPoolWaitableResult_WcmCommon___2__1___QEAV_lambda_5___BI___NeighborChangeCallback_NotificationTracking_NsiNotifications__CAXPEAXPEAU_NSI_KEYSTRUCT_DESC__PEAU_NSI_SINGLE_PARAM_DESC__W4_NSI_NOTIFICATION___Z__Z(
              (_QWORD *)(v19 + 1856),
              (__int64)&v21);
          if ( v24 )
            LeaveCriticalSection(v24);
          _InterlockedIncrement64((volatile signed __int64 *)(v19 + 1760));
          v18 = *(struct _TP_WORK **)(v19 + 1752);
          goto LABEL_56;
        }
      }
      if ( v24 )
        LeaveCriticalSection(v24);
    }
  }
}

```

## disassembly

```asm
0x18009da60  push    rbp
0x18009da62  push    rbx
0x18009da63  push    rsi
0x18009da64  push    rdi
0x18009da65  push    r12
0x18009da67  push    r13
0x18009da69  push    r14
0x18009da6b  push    r15
0x18009da6d  lea     rbp, [rsp-38h]
0x18009da72  sub     rsp, 138h
0x18009da79  mov     rax, cs:__security_cookie
0x18009da80  xor     rax, rsp
0x18009da83  mov     [rbp+70h+var_50], rax
0x18009da87  mov     r10, rdx
0x18009da8a  mov     r8, rcx
0x18009da8d  mov     rsi, [rcx]
0x18009da90  mov     rbx, [rsi]
0x18009da93  mov     rcx, rbx
0x18009da96  call    ?load@?$_Atomic_storage@_N$00@std@@QEBA_NW4memory_order@2@@Z; std::_Atomic_storage<bool,1>::load(std::memory_order)
0x18009da9b  xor     r13d, r13d
0x18009da9e  test    al, al
0x18009daa0  jnz     loc_18009DE84
0x18009daa6  mov     ecx, r9d
0x18009daa9  test    r9d, r9d
0x18009daac  jz      short loc_18009DAE5
0x18009daae  sub     ecx, 1
0x18009dab1  jz      short loc_18009DAD7
0x18009dab3  sub     ecx, 1
0x18009dab6  jz      short loc_18009DACC
0x18009dab8  cmp     ecx, 1
0x18009dabb  jnz     loc_18009DE84
0x18009dac1  mov     eax, [rsi+0C8h]
0x18009dac7  shr     eax, 3
0x18009daca  jmp     short loc_18009DADF
0x18009dacc  mov     eax, [rsi+0C8h]
0x18009dad2  shr     eax, 2
0x18009dad5  jmp     short loc_18009DADF
0x18009dad7  mov     eax, [rsi+0C8h]
0x18009dadd  shr     eax, 1
0x18009dadf  and     al, 1
0x18009dae1  test    al, al
0x18009dae3  jmp     short loc_18009DAEC
0x18009dae5  test    byte ptr [rsi+0C8h], 1
0x18009daec  jz      loc_18009DE84
0x18009daf2  cmp     dword ptr [r8+8], 1
0x18009daf7  jnz     short loc_18009DB05
0x18009daf9  mov     dil, 1
0x18009dafc  lea     rdx, NPI_MS_IPV4_MODULEID
0x18009db03  jmp     short loc_18009DB0F
0x18009db05  mov     dil, r13b
0x18009db08  lea     rdx, NPI_MS_IPV6_MODULEID
0x18009db0f  mov     ecx, r9d
0x18009db12  test    r9d, r9d
0x18009db15  jz      loc_18009DD82
0x18009db1b  sub     ecx, 1
0x18009db1e  jz      loc_18009DD82
0x18009db24  sub     ecx, 1
0x18009db27  jz      loc_18009DD82
0x18009db2d  cmp     ecx, 1
0x18009db30  jnz     loc_18009DE84
0x18009db36  mov     [rbp+70h+var_60], r13
0x18009db3a  mov     [rbp+70h+var_80], r13
0x18009db3e  mov     [rbp+70h+var_68], r13
0x18009db42  mov     [rbp+70h+var_70], r13
0x18009db46  mov     [rbp+70h+var_78], r13
0x18009db4a  mov     [rbp+70h+var_58], r13d
0x18009db4e  movzx   eax, dil
0x18009db52  xor     eax, ecx
0x18009db54  lea     eax, ds:18h[rax*8]
0x18009db5b  lea     r9, [rbp+70h+var_80]
0x18009db5f  lea     rcx, [rbp+70h+var_60]
0x18009db63  test    dil, dil
0x18009db66  cmovnz  r9, rcx
0x18009db6a  mov     [rsp+170h+var_110], 1
0x18009db6f  lea     rcx, [rbp+70h+var_58]
0x18009db73  mov     [rsp+170h+var_118], rcx
0x18009db78  mov     [rsp+170h+var_120], 4
0x18009db80  lea     rcx, [rbp+70h+var_78]
0x18009db84  mov     [rsp+170h+var_128], rcx
0x18009db89  mov     [rsp+170h+var_130], 10h
0x18009db91  lea     rcx, [rbp+70h+var_70]
0x18009db95  mov     [rsp+170h+var_138], rcx
0x18009db9a  mov     [rsp+170h+var_140], 20h ; ' '
0x18009dba2  lea     rcx, [rbp+70h+var_68]
0x18009dba6  mov     [rsp+170h+var_148], rcx
0x18009dbab  mov     [rsp+170h+var_150], eax; unsigned int
0x18009dbaf  mov     ecx, 1
0x18009dbb4  lea     r8d, [rcx+0Ah]
0x18009dbb8  call    cs:__imp_NsiAllocateAndGetTable
0x18009dbbe  test    eax, eax
0x18009dbc0  jz      short loc_18009DBDF
0x18009dbc2  mov     rcx, [rbp+78h]; this
0x18009dbc6  mov     r9d, eax; char *
0x18009dbc9  lea     r8, aOnecorePrivate_0; "onecore\\private\\net\\inc\\nsinotifica"...
0x18009dbd0  mov     edx, 6E9h; void *
0x18009dbd5  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x18009dbda  jmp     loc_18009DD5E
0x18009dbdf  mov     r15d, r13d
0x18009dbe2  cmp     [rbp+70h+var_58], r13d
0x18009dbe6  jbe     loc_18009DD5E
0x18009dbec  lea     r12, [rbx+660h]
0x18009dbf3  lea     r14, [rbx+6F0h]
0x18009dbfa  mov     r8d, r15d
0x18009dbfd  mov     edx, r15d
0x18009dc00  shl     rdx, 5
0x18009dc04  mov     r9d, r15d
0x18009dc07  add     r9, r9
0x18009dc0a  mov     [rbp+70h+var_F0], rbx
0x18009dc0e  mov     [rbp+70h+var_E8], rsi
0x18009dc12  mov     [rsp+170h+lpCriticalSection], r13
0x18009dc17  test    dil, dil
0x18009dc1a  jz      loc_18009DCA4
0x18009dc20  lea     rcx, [r8+r8*2]
0x18009dc24  mov     rax, [rbp+70h+var_60]
0x18009dc28  movups  xmm0, xmmword ptr [rax+rcx*8]
0x18009dc2c  movaps  [rbp+70h+var_E0], xmm0
0x18009dc30  movsd   xmm1, qword ptr [rax+rcx*8+10h]
0x18009dc36  movsd   qword ptr [rbp+70h+var_D0], xmm1
0x18009dc3b  mov     rax, [rbp+70h+var_68]
0x18009dc3f  movups  xmm0, xmmword ptr [rdx+rax]
0x18009dc43  movups  [rbp+70h+var_D0+8], xmm0
0x18009dc47  movups  xmm1, xmmword ptr [rdx+rax+10h]
0x18009dc4c  movups  [rbp+70h+var_B8], xmm1
0x18009dc50  mov     rax, [rbp+70h+var_70]
0x18009dc54  movups  xmm0, xmmword ptr [rax+r9*8]
0x18009dc59  movdqu  [rbp+70h+var_A8], xmm0
0x18009dc5e  mov     rax, [rbp+70h+var_78]
0x18009dc62  mov     ecx, [rax+r8*4]
0x18009dc66  mov     [rbp+70h+var_98], ecx
0x18009dc69  mov     rdx, r12
0x18009dc6c  lea     rcx, [rsp+170h+lpCriticalSection]
0x18009dc71  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x18009dc76  cmp     [r14+78h], r13b
0x18009dc7a  jnz     short loc_18009DCFA
0x18009dc7c  lea     rdx, [rbp+70h+var_F0]
0x18009dc80  cmp     dword ptr [rbx+658h], 1
0x18009dc87  jnz     short loc_18009DC96
0x18009dc89  mov     rcx, r14
0x18009dc8c  call    ??$emplace_back@V_lambda_2_@?BA@??NeighborChangeCallback@NotificationTracking@NsiNotifications@@CAXPEAXPEAU_NSI_KEYSTRUCT_DESC@@PEAU_NSI_SINGLE_PARAM_DESC@@W4_NSI_NOTIFICATION@@@Z@@?$deque@V?$function@$$A6AXXZ@std@@V?$allocator@V?$function@$$A6AXXZ@std@@@2@@std@@QEAAAEAV?$function@$$A6AXXZ@1@$$QEAV_lambda_2_@?BA@??NeighborChangeCallback@NotificationTracking@NsiNotifications@@CAXPEAXPEAU_NSI_KEYSTRUCT_DESC@@PEAU_NSI_SINGLE_PARAM_DESC@@W4_NSI_NOTIFICATION@@@Z@@Z; std::deque<std::function<void (void)>>::emplace_back<`NsiNotifications::NotificationTracking::NeighborChangeCallback(void *,_NSI_KEYSTRUCT_DESC *,_NSI_SINGLE_PARAM_DESC *,_NSI_NOTIFICATION)'::`16'::_lambda_2_>(`NsiNotifications::NotificationTracking::NeighborChangeCallback(void *,_NSI_KEYSTRUCT_DESC *,_NSI_SINGLE_PARAM_DESC *,_NSI_NOTIFICATION)'::`16'::_lambda_2_ &&)
0x18009dc91  jmp     loc_18009DD2C
0x18009dc96  lea     rcx, [r14+50h]
0x18009dc9a  call    ??$emplace_back@V_lambda_2_@?BA@??NeighborChangeCallback@NotificationTracking@NsiNotifications@@CAXPEAXPEAU_NSI_KEYSTRUCT_DESC@@PEAU_NSI_SINGLE_PARAM_DESC@@W4_NSI_NOTIFICATION@@@Z@@?$deque@V?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@V?$allocator@V?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@@2@@std@@QEAAAEAV?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@1@$$QEAV_lambda_2_@?BA@??NeighborChangeCallback@NotificationTracking@NsiNotifications@@CAXPEAXPEAU_NSI_KEYSTRUCT_DESC@@PEAU_NSI_SINGLE_PARAM_DESC@@W4_NSI_NOTIFICATION@@@Z@@Z; std::deque<std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>>::emplace_back<`NsiNotifications::NotificationTracking::NeighborChangeCallback(void *,_NSI_KEYSTRUCT_DESC *,_NSI_SINGLE_PARAM_DESC *,_NSI_NOTIFICATION)'::`16'::_lambda_2_>(`NsiNotifications::NotificationTracking::NeighborChangeCallback(void *,_NSI_KEYSTRUCT_DESC *,_NSI_SINGLE_PARAM_DESC *,_NSI_NOTIFICATION)'::`16'::_lambda_2_ &&)
0x18009dc9f  jmp     loc_18009DD2C
0x18009dca4  mov     rax, [rbp+70h+var_80]
0x18009dca8  movups  xmm0, xmmword ptr [rdx+rax]
0x18009dcac  movaps  [rbp+70h+var_E0], xmm0
0x18009dcb0  movups  xmm1, xmmword ptr [rdx+rax+10h]
0x18009dcb5  movaps  [rbp+70h+var_D0], xmm1
0x18009dcb9  mov     rax, [rbp+70h+var_68]
0x18009dcbd  movups  xmm0, xmmword ptr [rdx+rax]
0x18009dcc1  movaps  xmmword ptr [rbp-50h], xmm0
0x18009dcc5  movups  xmm1, xmmword ptr [rdx+rax+10h]
0x18009dcca  movaps  [rbp+70h+var_B8+8], xmm1
0x18009dcce  mov     rax, [rbp+70h+var_70]
0x18009dcd2  movups  xmm0, xmmword ptr [rax+r9*8]
0x18009dcd7  movdqu  [rbp+70h+var_A8+8], xmm0
0x18009dcdc  mov     rax, [rbp+70h+var_78]
0x18009dce0  mov     ecx, [rax+r8*4]
0x18009dce4  mov     [rbp+70h+var_90], ecx
0x18009dce7  mov     rdx, r12
0x18009dcea  lea     rcx, [rsp+170h+lpCriticalSection]
0x18009dcef  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x18009dcf4  cmp     [r14+78h], r13b
0x18009dcf8  jz      short loc_18009DD0C
0x18009dcfa  mov     rcx, [rsp+170h+lpCriticalSection]; lpCriticalSection
0x18009dcff  test    rcx, rcx
0x18009dd02  jz      short loc_18009DD51
0x18009dd04  call    cs:__imp_LeaveCriticalSection
0x18009dd0a  jmp     short loc_18009DD51
0x18009dd0c  lea     rdx, [rbp+70h+var_F0]
0x18009dd10  cmp     dword ptr [rbx+658h], 1
0x18009dd17  jnz     short loc_18009DD23
0x18009dd19  mov     rcx, r14
0x18009dd1c  call    ??$emplace_back@V_lambda_3_@?BC@??NeighborChangeCallback@NotificationTracking@NsiNotifications@@CAXPEAXPEAU_NSI_KEYSTRUCT_DESC@@PEAU_NSI_SINGLE_PARAM_DESC@@W4_NSI_NOTIFICATION@@@Z@@?$deque@V?$function@$$A6AXXZ@std@@V?$allocator@V?$function@$$A6AXXZ@std@@@2@@std@@QEAAAEAV?$function@$$A6AXXZ@1@$$QEAV_lambda_3_@?BC@??NeighborChangeCallback@NotificationTracking@NsiNotifications@@CAXPEAXPEAU_NSI_KEYSTRUCT_DESC@@PEAU_NSI_SINGLE_PARAM_DESC@@W4_NSI_NOTIFICATION@@@Z@@Z; std::deque<std::function<void (void)>>::emplace_back<`NsiNotifications::NotificationTracking::NeighborChangeCallback(void *,_NSI_KEYSTRUCT_DESC *,_NSI_SINGLE_PARAM_DESC *,_NSI_NOTIFICATION)'::`18'::_lambda_3_>(`NsiNotifications::NotificationTracking::NeighborChangeCallback(void *,_NSI_KEYSTRUCT_DESC *,_NSI_SINGLE_PARAM_DESC *,_NSI_NOTIFICATION)'::`18'::_lambda_3_ &&)
0x18009dd21  jmp     short loc_18009DD2C
0x18009dd23  lea     rcx, [r14+50h]
0x18009dd27  call    ??$emplace_back@V_lambda_3_@?BC@??NeighborChangeCallback@NotificationTracking@NsiNotifications@@CAXPEAXPEAU_NSI_KEYSTRUCT_DESC@@PEAU_NSI_SINGLE_PARAM_DESC@@W4_NSI_NOTIFICATION@@@Z@@?$deque@V?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@V?$allocator@V?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@@2@@std@@QEAAAEAV?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@1@$$QEAV_lambda_3_@?BC@??NeighborChangeCallback@NotificationTracking@NsiNotifications@@CAXPEAXPEAU_NSI_KEYSTRUCT_DESC@@PEAU_NSI_SINGLE_PARAM_DESC@@W4_NSI_NOTIFICATION@@@Z@@Z; std::deque<std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>>::emplace_back<`NsiNotifications::NotificationTracking::NeighborChangeCallback(void *,_NSI_KEYSTRUCT_DESC *,_NSI_SINGLE_PARAM_DESC *,_NSI_NOTIFICATION)'::`18'::_lambda_3_>(`NsiNotifications::NotificationTracking::NeighborChangeCallback(void *,_NSI_KEYSTRUCT_DESC *,_NSI_SINGLE_PARAM_DESC *,_NSI_NOTIFICATION)'::`18'::_lambda_3_ &&)
0x18009dd2c  mov     rcx, [rsp+170h+lpCriticalSection]; lpCriticalSection
0x18009dd31  test    rcx, rcx
0x18009dd34  jz      short loc_18009DD3C
0x18009dd36  call    cs:__imp_LeaveCriticalSection
0x18009dd3c  lock inc qword ptr [rbx+6E0h]
0x18009dd44  mov     rcx, [rbx+6D8h]; pwk
0x18009dd4b  call    cs:__imp_SubmitThreadpoolWork
0x18009dd51  inc     r15d
0x18009dd54  cmp     r15d, [rbp+70h+var_58]
0x18009dd58  jb      loc_18009DBFA
0x18009dd5e  mov     r9, [rbp+70h+var_78]
0x18009dd62  mov     r8, [rbp+70h+var_70]
0x18009dd66  mov     rdx, [rbp+70h+var_68]
0x18009dd6a  test    dil, dil
0x18009dd6d  mov     rcx, [rbp+70h+var_60]
0x18009dd71  jnz     short loc_18009DD77
0x18009dd73  mov     rcx, [rbp+70h+var_80]
0x18009dd77  call    cs:__imp_NsiFreeTable
0x18009dd7d  jmp     loc_18009DE84
0x18009dd82  mov     rcx, [r10]
0x18009dd85  mov     [rbp+70h+var_F0], rbx
0x18009dd89  mov     [rbp+70h+var_E8], rsi
0x18009dd8d  mov     dword ptr [rbp+70h+var_E0], r9d
0x18009dd91  movups  xmm0, xmmword ptr [rcx+8]
0x18009dd95  mov     [rbp+70h+var_80], r13
0x18009dd99  movups  [rbp+70h+var_E0+8], xmm0
0x18009dd9d  test    dil, dil
0x18009dda0  jz      short loc_18009DE06
0x18009dda2  movsd   xmm1, qword ptr [rcx+18h]
0x18009dda7  movsd   qword ptr [rbp+70h+var_D0+8], xmm1
0x18009ddac  lea     rdx, [rbx+660h]
0x18009ddb3  lea     rcx, [rbp+70h+var_80]
0x18009ddb7  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x18009ddbc  lea     rcx, [rbx+6F0h]
0x18009ddc3  cmp     [rcx+78h], r13b
0x18009ddc7  jnz     short loc_18009DE31
0x18009ddc9  lea     rdx, [rbp+70h+var_F0]
0x18009ddcd  cmp     dword ptr [rbx+658h], 1
0x18009ddd4  jnz     short loc_18009DDDD
0x18009ddd6  call    ??$emplace_back@V_lambda_4_@?BG@??NeighborChangeCallback@NotificationTracking@NsiNotifications@@CAXPEAXPEAU_NSI_KEYSTRUCT_DESC@@PEAU_NSI_SINGLE_PARAM_DESC@@W4_NSI_NOTIFICATION@@@Z@@?$deque@V?$function@$$A6AXXZ@std@@V?$allocator@V?$function@$$A6AXXZ@std@@@2@@std@@QEAAAEAV?$function@$$A6AXXZ@1@$$QEAV_lambda_4_@?BG@??NeighborChangeCallback@NotificationTracking@NsiNotifications@@CAXPEAXPEAU_NSI_KEYSTRUCT_DESC@@PEAU_NSI_SINGLE_PARAM_DESC@@W4_NSI_NOTIFICATION@@@Z@@Z; std::deque<std::function<void (void)>>::emplace_back<`NsiNotifications::NotificationTracking::NeighborChangeCallback(void *,_NSI_KEYSTRUCT_DESC *,_NSI_SINGLE_PARAM_DESC *,_NSI_NOTIFICATION)'::`22'::_lambda_4_>(`NsiNotifications::NotificationTracking::NeighborChangeCallback(void *,_NSI_KEYSTRUCT_DESC *,_NSI_SINGLE_PARAM_DESC *,_NSI_NOTIFICATION)'::`22'::_lambda_4_ &&)
0x18009dddb  jmp     short loc_18009DDE6
0x18009dddd  add     rcx, 50h ; 'P'
0x18009dde1  call    ??$emplace_back@V_lambda_4_@?BG@??NeighborChangeCallback@NotificationTracking@NsiNotifications@@CAXPEAXPEAU_NSI_KEYSTRUCT_DESC@@PEAU_NSI_SINGLE_PARAM_DESC@@W4_NSI_NOTIFICATION@@@Z@@?$deque@V?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@V?$allocator@V?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@@2@@std@@QEAAAEAV?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@1@$$QEAV_lambda_4_@?BG@??NeighborChangeCallback@NotificationTracking@NsiNotifications@@CAXPEAXPEAU_NSI_KEYSTRUCT_DESC@@PEAU_NSI_SINGLE_PARAM_DESC@@W4_NSI_NOTIFICATION@@@Z@@Z; std::deque<std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>>::emplace_back<`NsiNotifications::NotificationTracking::NeighborChangeCallback(void *,_NSI_KEYSTRUCT_DESC *,_NSI_SINGLE_PARAM_DESC *,_NSI_NOTIFICATION)'::`22'::_lambda_4_>(`NsiNotifications::NotificationTracking::NeighborChangeCallback(void *,_NSI_KEYSTRUCT_DESC *,_NSI_SINGLE_PARAM_DESC *,_NSI_NOTIFICATION)'::`22'::_lambda_4_ &&)
0x18009dde6  mov     rcx, [rbp+70h+var_80]; lpCriticalSection
0x18009ddea  test    rcx, rcx
0x18009dded  jz      short loc_18009DDF5
0x18009ddef  call    cs:__imp_LeaveCriticalSection
0x18009ddf5  lock inc qword ptr [rbx+6E0h]
0x18009ddfd  mov     rcx, [rbx+6D8h]
0x18009de04  jmp     short loc_18009DE7D
0x18009de06  mov     rax, [r8]
0x18009de09  mov     rdi, [rax]
0x18009de0c  movups  xmm1, xmmword ptr [rcx+18h]
0x18009de10  movups  [rbp+70h+var_D0+8], xmm1
0x18009de14  lea     rdx, [rdi+660h]
0x18009de1b  lea     rcx, [rbp+70h+var_80]
0x18009de1f  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x18009de24  lea     rcx, [rdi+6F0h]
0x18009de2b  cmp     [rcx+78h], r13b
0x18009de2f  jz      short loc_18009DE42
0x18009de31  mov     rcx, [rbp+70h+var_80]; lpCriticalSection
0x18009de35  test    rcx, rcx
0x18009de38  jz      short loc_18009DE84
0x18009de3a  call    cs:__imp_LeaveCriticalSection
0x18009de40  jmp     short loc_18009DE84
0x18009de42  lea     rdx, [rbp+70h+var_F0]
0x18009de46  cmp     dword ptr [rdi+658h], 1
0x18009de4d  jnz     short loc_18009DE56
0x18009de4f  call    ??$emplace_back@V_lambda_5_@?BI@??NeighborChangeCallback@NotificationTracking@NsiNotifications@@CAXPEAXPEAU_NSI_KEYSTRUCT_DESC@@PEAU_NSI_SINGLE_PARAM_DESC@@W4_NSI_NOTIFICATION@@@Z@@?$deque@V?$function@$$A6AXXZ@std@@V?$allocator@V?$function@$$A6AXXZ@std@@@2@@std@@QEAAAEAV?$function@$$A6AXXZ@1@$$QEAV_lambda_5_@?BI@??NeighborChangeCallback@NotificationTracking@NsiNotifications@@CAXPEAXPEAU_NSI_KEYSTRUCT_DESC@@PEAU_NSI_SINGLE_PARAM_DESC@@W4_NSI_NOTIFICATION@@@Z@@Z; std::deque<std::function<void (void)>>::emplace_back<`NsiNotifications::NotificationTracking::NeighborChangeCallback(void *,_NSI_KEYSTRUCT_DESC *,_NSI_SINGLE_PARAM_DESC *,_NSI_NOTIFICATION)'::`24'::_lambda_5_>(`NsiNotifications::NotificationTracking::NeighborChangeCallback(void *,_NSI_KEYSTRUCT_DESC *,_NSI_SINGLE_PARAM_DESC *,_NSI_NOTIFICATION)'::`24'::_lambda_5_ &&)
0x18009de54  jmp     short loc_18009DE5F
0x18009de56  add     rcx, 50h ; 'P'
0x18009de5a  call    ??$emplace_back@V_lambda_5_@?BI@??NeighborChangeCallback@NotificationTracking@NsiNotifications@@CAXPEAXPEAU_NSI_KEYSTRUCT_DESC@@PEAU_NSI_SINGLE_PARAM_DESC@@W4_NSI_NOTIFICATION@@@Z@@?$deque@V?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@V?$allocator@V?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@@2@@std@@QEAAAEAV?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@1@$$QEAV_lambda_5_@?BI@??NeighborChangeCallback@NotificationTracking@NsiNotifications@@CAXPEAXPEAU_NSI_KEYSTRUCT_DESC@@PEAU_NSI_SINGLE_PARAM_DESC@@W4_NSI_NOTIFICATION@@@Z@@Z; std::deque<std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>>::emplace_back<`NsiNotifications::NotificationTracking::NeighborChangeCallback(void *,_NSI_KEYSTRUCT_DESC *,_NSI_SINGLE_PARAM_DESC *,_NSI_NOTIFICATION)'::`24'::_lambda_5_>(`NsiNotifications::NotificationTracking::NeighborChangeCallback(void *,_NSI_KEYSTRUCT_DESC *,_NSI_SINGLE_PARAM_DESC *,_NSI_NOTIFICATION)'::`24'::_lambda_5_ &&)
0x18009de5f  mov     rcx, [rbp+70h+var_80]; lpCriticalSection
0x18009de63  test    rcx, rcx
0x18009de66  jz      short loc_18009DE6E
0x18009de68  call    cs:__imp_LeaveCriticalSection
0x18009de6e  lock inc qword ptr [rdi+6E0h]
0x18009de76  mov     rcx, [rdi+6D8h]; pwk
0x18009de7d  call    cs:__imp_SubmitThreadpoolWork
0x18009de83  nop
0x18009de84  mov     rcx, [rbp+70h+var_50]
0x18009de88  xor     rcx, rsp; StackCookie
0x18009de8b  call    __security_check_cookie
0x18009de90  add     rsp, 138h
0x18009de97  pop     r15
0x18009de99  pop     r14
0x18009de9b  pop     r13
0x18009de9d  pop     r12
0x18009de9f  pop     rdi
0x18009dea0  pop     rsi
0x18009dea1  pop     rbx
0x18009dea2  pop     rbp
0x18009dea3  retn
```
