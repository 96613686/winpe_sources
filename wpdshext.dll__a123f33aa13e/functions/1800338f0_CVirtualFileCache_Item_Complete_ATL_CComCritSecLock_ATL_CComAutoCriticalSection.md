# CVirtualFileCache::Item::Complete(ATL::CComCritSecLock<ATL::CComAutoCriticalSection> *)

- ea: `0x1800338f0`
- end: `0x1800339c6`
- name: `?Complete@Item@CVirtualFileCache@@QEAAXPEAV?$CComCritSecLock@VCComAutoCriticalSection@ATL@@@ATL@@@Z`
- size: `214`
- prototype: `__int64 __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180028664`

## callees

- `0x1800338f0`
- `0x1800339cc`
- `0x18006a5d0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18003394e`
- `KERNEL32!GetLastError` at `0x18003397f`
- `KERNEL32!GetLastError` at `0x18003394e`
- `KERNEL32!GetLastError` at `0x18003397f`
- `KERNEL32!CreateThreadpoolWork` at `0x180033921`
- `KERNEL32!CreateThreadpoolWork` at `0x180033921`
- `KERNEL32!SubmitThreadpoolWork` at `0x180033932`
- `KERNEL32!SubmitThreadpoolWork` at `0x180033932`
- `KERNEL32!WaitForThreadpoolWorkCallbacks` at `0x18003393d`
- `KERNEL32!WaitForThreadpoolWorkCallbacks` at `0x18003393d`
- `KERNEL32!CloseThreadpoolWork` at `0x180033946`
- `KERNEL32!CloseThreadpoolWork` at `0x180033946`

## pseudocode

```c
void __fastcall CVirtualFileCache::Item::Complete(__int64 *pv, __int64 a2)
{
  struct _TP_WORK *ThreadpoolWork; // rax
  struct _TP_WORK *v4; // rbx
  signed int LastError; // eax
  bool v6; // sf
  char v7; // al

  if ( !(unsigned int)CVirtualFileCache::Item::WaitForTimer(a2, pv[5]) )
  {
    ThreadpoolWork = CreateThreadpoolWork(CVirtualFileCache::Item::TimerCallback, pv, 0);
    v4 = ThreadpoolWork;
    if ( ThreadpoolWork )
    {
      SubmitThreadpoolWork(ThreadpoolWork);
      WaitForThreadpoolWorkCallbacks(v4, 0);
      CloseThreadpoolWork(v4);
    }
    else
    {
      LastError = GetLastError();
      v6 = LastError < 0;
      if ( LastError > 0 )
        v6 = 1;
      if ( v6 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        v7 = GetLastError();
        WPP_SF_SSd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          17,
          (unsigned int)WPP_d08d68109c073cdceb0fe354085e5f25_Traceguids,
          pv[4],
          pv[3],
          v7);
      }
    }
  }
}

```

## disassembly

```asm
0x1800338f0  mov     [rsp+arg_0], rbx
0x1800338f5  push    rdi
0x1800338f6  sub     rsp, 30h
0x1800338fa  mov     rax, rdx
0x1800338fd  mov     rdi, rcx
0x180033900  mov     rdx, [rcx+28h]
0x180033904  mov     rcx, rax
0x180033907  call    ?WaitForTimer@Item@CVirtualFileCache@@KAHPEAV?$CComCritSecLock@VCComAutoCriticalSection@ATL@@@ATL@@PEAU_TP_TIMER@@@Z; CVirtualFileCache::Item::WaitForTimer(ATL::CComCritSecLock<ATL::CComAutoCriticalSection> *,_TP_TIMER *)
0x18003390c  test    eax, eax
0x18003390e  jnz     loc_1800339BB
0x180033914  xor     r8d, r8d; pcbe
0x180033917  lea     rcx, ?TimerCallback@Item@CVirtualFileCache@@KAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnwk
0x18003391e  mov     rdx, rdi; pv
0x180033921  call    cs:__imp_CreateThreadpoolWork
0x180033927  mov     rbx, rax
0x18003392a  test    rax, rax
0x18003392d  jz      short loc_18003394E
0x18003392f  mov     rcx, rax; pwk
0x180033932  call    cs:__imp_SubmitThreadpoolWork
0x180033938  xor     edx, edx; fCancelPendingCallbacks
0x18003393a  mov     rcx, rbx; pwk
0x18003393d  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x180033943  mov     rcx, rbx; pwk
0x180033946  call    cs:__imp_CloseThreadpoolWork
0x18003394c  jmp     short loc_1800339BB
0x18003394e  call    cs:__imp_GetLastError
0x180033954  mov     ebx, 80070000h
0x180033959  test    eax, eax
0x18003395b  jle     short loc_180033964
0x18003395d  movzx   eax, ax
0x180033960  or      eax, ebx
0x180033962  test    eax, eax
0x180033964  jns     short loc_1800339BB
0x180033966  mov     rax, cs:WPP_GLOBAL_Control
0x18003396d  lea     rcx, WPP_GLOBAL_Control
0x180033974  cmp     rax, rcx
0x180033977  jz      short loc_1800339BB
0x180033979  test    byte ptr [rax+1Ch], 4
0x18003397d  jz      short loc_1800339BB
0x18003397f  call    cs:__imp_GetLastError
0x180033985  test    eax, eax
0x180033987  jle     short loc_18003398E
0x180033989  movzx   eax, ax
0x18003398c  or      eax, ebx
0x18003398e  mov     rcx, cs:WPP_GLOBAL_Control
0x180033995  lea     r8, WPP_d08d68109c073cdceb0fe354085e5f25_Traceguids
0x18003399c  mov     r9, [rdi+20h]
0x1800339a0  mov     edx, 11h
0x1800339a5  mov     [rsp+38h+var_10], eax
0x1800339a9  mov     rax, [rdi+18h]
0x1800339ad  mov     rcx, [rcx+10h]
0x1800339b1  mov     [rsp+38h+var_18], rax
0x1800339b6  call    WPP_SF_SSd
0x1800339bb  mov     rbx, [rsp+38h+arg_0]
0x1800339c0  add     rsp, 30h
0x1800339c4  pop     rdi
0x1800339c5  retn
```
