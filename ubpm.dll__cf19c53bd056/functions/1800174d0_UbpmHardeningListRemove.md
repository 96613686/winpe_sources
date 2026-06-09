# UbpmHardeningListRemove

- ea: `0x1800174d0`
- end: `0x180017608`
- name: `UbpmHardeningListRemove`
- size: `312`
- prototype: `__int64 __fastcall(wchar_t *String2)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, service_task, installer_update`

## callers

- `0x18000d5c0`
- `0x180016eb0`

## callees

- `0x1800174d0`
- `0x180017610`
- `0x180019d90`
- `0x180032dd8`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18001752a`
- `msvcrt!_wcsicmp` at `0x18001752a`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800174f5`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800174f5`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180017560`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800175a3`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180017560`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800175a3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800174fb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800174fb`

## pseudocode

```c
void __fastcall UbpmHardeningListRemove(wchar_t *String2, __int64 a2)
{
  DWORD CurrentThreadId; // eax
  struct _LIST_ENTRY *Flink; // rbx
  struct _LIST_ENTRY *v6; // r14
  unsigned __int8 v7; // si
  int v8; // eax
  struct _LIST_ENTRY *v9; // rcx
  struct _LIST_ENTRY *Blink; // rax

  if ( String2 && a2 )
  {
    RtlAcquireSRWLockExclusive(&g_TaskHostContextListLock);
    CurrentThreadId = GetCurrentThreadId();
    Flink = g_leTaskHostHardeningListHead.Flink;
    v6 = &g_leTaskHostHardeningListHead;
    dword_18004CF18 = CurrentThreadId;
    v7 = 0;
LABEL_4:
    if ( v7 >= 2u )
    {
      dword_18004CF18 = 0;
      RtlReleaseSRWLockExclusive(&g_TaskHostContextListLock);
    }
    else
    {
      while ( 1 )
      {
        if ( Flink == v6 )
        {
          Flink = g_leNonHostHardeningListHead.Flink;
          v6 = &g_leNonHostHardeningListHead;
          ++v7;
          goto LABEL_4;
        }
        v8 = _wcsicmp((const wchar_t *)Flink[1].Flink, String2);
        v9 = Flink->Flink;
        if ( !v8 )
          break;
        Flink = Flink->Flink;
      }
      if ( v9->Blink != Flink || (Blink = Flink->Blink, Blink->Flink != Flink) )
        __fastfail(3u);
      Blink->Flink = v9;
      v9->Blink = Blink;
      Flink->Blink = Flink;
      Flink->Flink = Flink;
      dword_18004CF18 = 0;
      RtlReleaseSRWLockExclusive(&g_TaskHostContextListLock);
      UBPM_MIDL_user_free(Flink);
      if ( *(_BYTE *)(a2 + 49) )
        UbpmUpdateConsumerSidCache(*(PCWSTR *)(a2 + 56), *(const WCHAR **)(a2 + 64), *(_DWORD *)(a2 + 72), 0);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 64, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids, String2);
    }
  }
}

```

## disassembly

```asm
0x1800174d0  test    rcx, rcx
0x1800174d3  jz      locret_180017570
0x1800174d9  push    rbx
0x1800174da  push    rbp
0x1800174db  push    rsi
0x1800174dc  push    rdi
0x1800174dd  push    r14
0x1800174df  sub     rsp, 20h
0x1800174e3  mov     rdi, rdx
0x1800174e6  mov     rbp, rcx
0x1800174e9  test    rdx, rdx
0x1800174ec  jz      short loc_180017566
0x1800174ee  lea     rcx, g_TaskHostContextListLock
0x1800174f5  call    cs:__imp_RtlAcquireSRWLockExclusive
0x1800174fb  call    cs:__imp_GetCurrentThreadId
0x180017501  mov     rbx, cs:?g_leTaskHostHardeningListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_leTaskHostHardeningListHead
0x180017508  lea     r14, ?g_leTaskHostHardeningListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_leTaskHostHardeningListHead
0x18001750f  mov     cs:dword_18004CF18, eax
0x180017515  xor     sil, sil
0x180017518  cmp     sil, 2
0x18001751c  jnb     short loc_18001754F
0x18001751e  cmp     rbx, r14
0x180017521  jz      short loc_18001753C
0x180017523  mov     rcx, [rbx+10h]; String1
0x180017527  mov     rdx, rbp; String2
0x18001752a  call    cs:__imp__wcsicmp
0x180017530  mov     rcx, [rbx]
0x180017533  test    eax, eax
0x180017535  jz      short loc_180017571
0x180017537  mov     rbx, rcx
0x18001753a  jmp     short loc_18001751E
0x18001753c  mov     rbx, cs:?g_leNonHostHardeningListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_leNonHostHardeningListHead
0x180017543  lea     r14, ?g_leNonHostHardeningListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_leNonHostHardeningListHead
0x18001754a  inc     sil
0x18001754d  jmp     short loc_180017518
0x18001754f  lea     rcx, g_TaskHostContextListLock
0x180017556  mov     cs:dword_18004CF18, 0
0x180017560  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180017566  add     rsp, 20h
0x18001756a  pop     r14
0x18001756c  pop     rdi
0x18001756d  pop     rsi
0x18001756e  pop     rbp
0x18001756f  pop     rbx
0x180017570  retn
0x180017571  cmp     [rcx+8], rbx
0x180017575  jnz     loc_180017601
0x18001757b  mov     rax, [rbx+8]
0x18001757f  cmp     [rax], rbx
0x180017582  jnz     short loc_180017601
0x180017584  mov     [rax], rcx
0x180017587  mov     [rcx+8], rax
0x18001758b  lea     rcx, g_TaskHostContextListLock
0x180017592  mov     [rbx+8], rbx
0x180017596  mov     [rbx], rbx
0x180017599  mov     cs:dword_18004CF18, 0
0x1800175a3  call    cs:__imp_RtlReleaseSRWLockExclusive
0x1800175a9  mov     rcx, rbx
0x1800175ac  call    UBPM_MIDL_user_free
0x1800175b1  cmp     byte ptr [rdi+31h], 0
0x1800175b5  jz      short loc_1800175CB
0x1800175b7  mov     r8d, [rdi+48h]
0x1800175bb  xor     r9d, r9d
0x1800175be  mov     rdx, [rdi+40h]
0x1800175c2  mov     rcx, [rdi+38h]; SourceString
0x1800175c6  call    UbpmUpdateConsumerSidCache
0x1800175cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800175d2  lea     rax, WPP_GLOBAL_Control
0x1800175d9  cmp     rcx, rax
0x1800175dc  jz      short loc_180017566
0x1800175de  test    byte ptr [rcx+1Ch], 80h
0x1800175e2  jz      short loc_180017566
0x1800175e4  mov     rcx, [rcx+10h]
0x1800175e8  lea     r8, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids
0x1800175ef  mov     edx, 40h ; '@'
0x1800175f4  mov     r9, rbp
0x1800175f7  call    WPP_SF_S
0x1800175fc  jmp     loc_180017566
0x180017601  mov     ecx, 3
0x180017606  int     29h; Win8: RtlFailFast(ecx)
```
