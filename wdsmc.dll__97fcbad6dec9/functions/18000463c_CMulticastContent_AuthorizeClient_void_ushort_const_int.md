# CMulticastContent::AuthorizeClient(void *,ushort const *,int *)

- ea: `0x18000463c`
- end: `0x180004805`
- name: `?AuthorizeClient@CMulticastContent@@AEAAKPEAXPEBGPEAH@Z`
- size: `457`
- prototype: `unsigned int __fastcall(LPCRITICAL_SECTION lpCriticalSection, void *, const unsigned __int16 *, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x180004c60`

## callees

- `0x18000463c`
- `0x180025850`
- `0x180026d70`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800046c9`
- `KERNEL32!GetLastError` at `0x1800046c9`
- `KERNEL32!GetCurrentThread` at `0x1800046a6`
- `KERNEL32!GetCurrentThread` at `0x1800046a6`
- `KERNEL32!LeaveCriticalSection` at `0x180004723`
- `KERNEL32!LeaveCriticalSection` at `0x18000472f`
- `KERNEL32!LeaveCriticalSection` at `0x1800047e4`
- `KERNEL32!LeaveCriticalSection` at `0x180004723`
- `KERNEL32!LeaveCriticalSection` at `0x18000472f`
- `KERNEL32!LeaveCriticalSection` at `0x1800047e4`
- `KERNEL32!EnterCriticalSection` at `0x180004668`
- `KERNEL32!EnterCriticalSection` at `0x18000470f`
- `KERNEL32!EnterCriticalSection` at `0x180004668`
- `KERNEL32!EnterCriticalSection` at `0x18000470f`
- `ADVAPI32!OpenThreadToken` at `0x1800046bf`
- `ADVAPI32!OpenThreadToken` at `0x1800046bf`
- `WDSSRV!WdsImpersonateClient` at `0x180004671`
- `WDSSRV!WdsImpersonateClient` at `0x180004671`
- `WDSSRV!WdsRevertToSelf` at `0x1800046e8`
- `WDSSRV!WdsRevertToSelf` at `0x1800046f6`
- `WDSSRV!WdsRevertToSelf` at `0x1800046e8`
- `WDSSRV!WdsRevertToSelf` at `0x1800046f6`

## pseudocode

```c
__int64 __fastcall CMulticastContent::AuthorizeClient(
        LPCRITICAL_SECTION lpCriticalSection,
        void *a2,
        const unsigned __int16 *a3,
        int *a4)
{
  unsigned int v8; // eax
  const char *v9; // rdx
  unsigned int v10; // ebx
  HANDLE CurrentThread; // rax
  DWORD LastError; // eax
  const char *v13; // rdx
  struct _RTL_CRITICAL_SECTION *OwningThread; // rdi
  HANDLE v15; // rbp
  __int64 v16; // r14
  const char *v17; // rdx
  __int64 (__fastcall *SpinCount)(__int64, HANDLE, int *); // rbx
  int v19; // eax
  const char *v20; // rdx
  const wchar_t *v21; // rcx
  HANDLE TokenHandle; // [rsp+40h] [rbp-38h] BYREF
  int v24; // [rsp+80h] [rbp+8h] BYREF

  v24 = 0;
  TokenHandle = 0;
  EnterCriticalSection(lpCriticalSection);
  v8 = WdsImpersonateClient(a2);
  v10 = v8;
  if ( v8 )
  {
    if ( v8 != 1244
      && v8 != 50
      && ElValidateWin32(v8, v9, "base\\eco\\wds\\transport\\server\\mc\\mccontent.cpp", 0x201u) )
    {
      goto LABEL_21;
    }
  }
  else
  {
    CurrentThread = GetCurrentThread();
    if ( !OpenThreadToken(CurrentThread, 0xF01FFu, 1, &TokenHandle) )
    {
      LastError = GetLastError();
      v10 = ElValidateWin32(LastError, v13, "base\\eco\\wds\\transport\\server\\mc\\mccontent.cpp", 0x20Bu);
      WdsRevertToSelf(a2);
      goto LABEL_21;
    }
    WdsRevertToSelf(a2);
  }
  OwningThread = (struct _RTL_CRITICAL_SECTION *)lpCriticalSection[1].OwningThread;
  v15 = TokenHandle;
  v16 = *(_QWORD *)&lpCriticalSection[6].LockCount;
  EnterCriticalSection(OwningThread);
  if ( OwningThread[1].LockCount )
  {
    SpinCount = (__int64 (__fastcall *)(__int64, HANDLE, int *))OwningThread[2].SpinCount;
    LeaveCriticalSection(OwningThread);
    v19 = SpinCount(v16, v15, &v24);
    v10 = v19;
    if ( v19 < 0 && (v19 & 0x1FFF0000) == 0x70000 )
      v10 = (unsigned __int16)v19;
    ElValidateWin32(v10, v20, "base\\eco\\wds\\transport\\server\\mc\\contentprovider.cpp", 0x3D7u);
  }
  else
  {
    v10 = 21;
    LeaveCriticalSection(OwningThread);
  }
  if ( !ElValidateWin32(v10, v17, "base\\eco\\wds\\transport\\server\\mc\\mccontent.cpp", 0x21Au) )
  {
    if ( g_ErrLibTraceFunction )
    {
      v21 = L"No";
      if ( v24 )
        v21 = L"Yes";
      g_ErrLibTraceFunction(
        L"WDSMCSE[%u:%s] Client=`%s', Content='%s', Authorized=%s",
        LODWORD(lpCriticalSection[1].DebugInfo),
        lpCriticalSection[5].SpinCount,
        a3,
        lpCriticalSection[5].SpinCount,
        v21);
    }
    *a4 = v24;
  }
LABEL_21:
  LeaveCriticalSection(lpCriticalSection);
  return v10;
}

```

## disassembly

```asm
0x18000463c  mov     rax, rsp
0x18000463f  mov     [rax+10h], rbx
0x180004643  mov     [rax+18h], rbp
0x180004647  push    rsi
0x180004648  push    rdi
0x180004649  push    r12
0x18000464b  push    r14
0x18000464d  push    r15
0x18000464f  sub     rsp, 50h
0x180004653  and     dword ptr [rax+8], 0
0x180004657  mov     r15, r9
0x18000465a  and     qword ptr [rax-38h], 0
0x18000465f  mov     r12, r8
0x180004662  mov     rdi, rdx
0x180004665  mov     rsi, rcx
0x180004668  call    cs:__imp_EnterCriticalSection
0x18000466e  mov     rcx, rdi
0x180004671  call    cs:__imp_WdsImpersonateClient
0x180004677  mov     ebx, eax
0x180004679  test    eax, eax
0x18000467b  jz      short loc_1800046A6
0x18000467d  cmp     eax, 4DCh
0x180004682  jz      short loc_1800046FC
0x180004684  cmp     eax, 32h ; '2'
0x180004687  jz      short loc_1800046FC
0x180004689  mov     r9d, 201h; unsigned int
0x18000468f  lea     r8, aBaseEcoWdsTran_6; "base\\eco\\wds\\transport\\server\\mc\\"...
0x180004696  mov     ecx, eax; unsigned int
0x180004698  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000469d  test    eax, eax
0x18000469f  jz      short loc_1800046FC
0x1800046a1  jmp     loc_1800047E1
0x1800046a6  call    cs:__imp_GetCurrentThread
0x1800046ac  lea     r9, [rsp+78h+TokenHandle]; TokenHandle
0x1800046b1  mov     edx, 0F01FFh; DesiredAccess
0x1800046b6  mov     rcx, rax; ThreadHandle
0x1800046b9  mov     r8d, 1; OpenAsSelf
0x1800046bf  call    cs:__imp_OpenThreadToken
0x1800046c5  test    eax, eax
0x1800046c7  jnz     short loc_1800046F3
0x1800046c9  call    cs:__imp_GetLastError
0x1800046cf  mov     r9d, 20Bh; unsigned int
0x1800046d5  lea     r8, aBaseEcoWdsTran_6; "base\\eco\\wds\\transport\\server\\mc\\"...
0x1800046dc  mov     ecx, eax; unsigned int
0x1800046de  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x1800046e3  mov     rcx, rdi
0x1800046e6  mov     ebx, eax
0x1800046e8  call    cs:__imp_WdsRevertToSelf
0x1800046ee  jmp     loc_1800047E1
0x1800046f3  mov     rcx, rdi
0x1800046f6  call    cs:__imp_WdsRevertToSelf
0x1800046fc  mov     rdi, [rsi+38h]
0x180004700  mov     rbp, [rsp+78h+TokenHandle]
0x180004705  mov     rcx, rdi; lpCriticalSection
0x180004708  mov     r14, [rsi+0F8h]
0x18000470f  call    cs:__imp_EnterCriticalSection
0x180004715  cmp     dword ptr [rdi+30h], 0
0x180004719  mov     rcx, rdi; lpCriticalSection
0x18000471c  jnz     short loc_18000472B
0x18000471e  mov     ebx, 15h
0x180004723  call    cs:__imp_LeaveCriticalSection
0x180004729  jmp     short loc_180004775
0x18000472b  mov     rbx, [rdi+70h]
0x18000472f  call    cs:__imp_LeaveCriticalSection
0x180004735  lea     r8, [rsp+78h+arg_0]
0x18000473d  mov     rdx, rbp
0x180004740  mov     rcx, r14
0x180004743  mov     rax, rbx
0x180004746  call    cs:__guard_dispatch_icall_fptr
0x18000474c  mov     ebx, eax
0x18000474e  test    eax, eax
0x180004750  jns     short loc_180004761
0x180004752  and     eax, 1FFF0000h
0x180004757  cmp     eax, 70000h
0x18000475c  jnz     short loc_180004761
0x18000475e  movzx   ebx, bx
0x180004761  mov     r9d, 3D7h; unsigned int
0x180004767  lea     r8, aBaseEcoWdsTran_3; "base\\eco\\wds\\transport\\server\\mc\\"...
0x18000476e  mov     ecx, ebx; unsigned int
0x180004770  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180004775  mov     r9d, 21Ah; unsigned int
0x18000477b  lea     r8, aBaseEcoWdsTran_6; "base\\eco\\wds\\transport\\server\\mc\\"...
0x180004782  mov     ecx, ebx; unsigned int
0x180004784  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180004789  test    eax, eax
0x18000478b  jnz     short loc_1800047E1
0x18000478d  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180004794  test    rax, rax
0x180004797  jz      short loc_1800047D7
0x180004799  cmp     [rsp+78h+arg_0], 0
0x1800047a1  lea     rdx, aYes; "Yes"
0x1800047a8  mov     r8, [rsi+0E8h]
0x1800047af  lea     rcx, aNo; "No"
0x1800047b6  cmovnz  rcx, rdx
0x1800047ba  mov     r9, r12
0x1800047bd  mov     edx, [rsi+28h]
0x1800047c0  mov     [rsp+78h+var_50], rcx
0x1800047c5  lea     rcx, aWdsmcseUSClien; "WDSMCSE[%u:%s] Client=`%s', Content='%s"...
0x1800047cc  mov     [rsp+78h+var_58], r8
0x1800047d1  call    cs:__guard_dispatch_icall_fptr
0x1800047d7  mov     eax, [rsp+78h+arg_0]
0x1800047de  mov     [r15], eax
0x1800047e1  mov     rcx, rsi; lpCriticalSection
0x1800047e4  call    cs:__imp_LeaveCriticalSection
0x1800047ea  lea     r11, [rsp+78h+var_28]
0x1800047ef  mov     eax, ebx
0x1800047f1  mov     rbx, [r11+38h]
0x1800047f5  mov     rbp, [r11+40h]
0x1800047f9  mov     rsp, r11
0x1800047fc  pop     r15
0x1800047fe  pop     r14
0x180004800  pop     r12
0x180004802  pop     rdi
0x180004803  pop     rsi
0x180004804  retn
```
