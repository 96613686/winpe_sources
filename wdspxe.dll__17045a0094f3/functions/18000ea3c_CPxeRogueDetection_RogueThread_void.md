# CPxeRogueDetection::RogueThread(void)

- ea: `0x18000ea3c`
- end: `0x18000ec8d`
- name: `?RogueThread@CPxeRogueDetection@@QEAAKXZ`
- size: `593`
- prototype: `unsigned int __fastcall(CPxeRogueDetection *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180010a90`

## callees

- `0x180002a30`
- `0x18000abe4`
- `0x18000adf8`
- `0x18000bdc0`
- `0x18000ea3c`
- `0x18000f8b8`
- `0x180011068`

## import_xrefs

- `KERNEL32!WaitForMultipleObjects` at `0x18000eb14`
- `KERNEL32!WaitForMultipleObjects` at `0x18000eb14`
- `KERNEL32!EnterCriticalSection` at `0x18000ea72`
- `KERNEL32!EnterCriticalSection` at `0x18000eaa4`
- `KERNEL32!EnterCriticalSection` at `0x18000eb68`
- `KERNEL32!EnterCriticalSection` at `0x18000eb8e`
- `KERNEL32!EnterCriticalSection` at `0x18000ea72`
- `KERNEL32!EnterCriticalSection` at `0x18000eaa4`
- `KERNEL32!EnterCriticalSection` at `0x18000eb68`
- `KERNEL32!EnterCriticalSection` at `0x18000eb8e`
- `KERNEL32!LeaveCriticalSection` at `0x18000eabd`
- `KERNEL32!LeaveCriticalSection` at `0x18000eadd`
- `KERNEL32!LeaveCriticalSection` at `0x18000eba7`
- `KERNEL32!LeaveCriticalSection` at `0x18000ec46`
- `KERNEL32!LeaveCriticalSection` at `0x18000eabd`
- `KERNEL32!LeaveCriticalSection` at `0x18000eadd`
- `KERNEL32!LeaveCriticalSection` at `0x18000eba7`
- `KERNEL32!LeaveCriticalSection` at `0x18000ec46`
- `WdsCommonLib!?Log@CEventLog@@QEAAKKHZZ` at `0x18000ec37`
- `WdsCommonLib!?Log@CEventLog@@QEAAKKHZZ` at `0x18000ec37`

## pseudocode

```c
__int64 __fastcall CPxeRogueDetection::RogueThread(struct _RTL_CRITICAL_SECTION *this)
{
  HANDLE OwningThread; // rax
  int v2; // ebp
  HANDLE *p_LockSemaphore; // rsi
  int v5; // ebx
  DWORD v6; // eax
  unsigned int ServerRole; // eax
  __int64 v8; // rdx
  __int64 v9; // r8
  int v10; // ebx
  int LockSemaphore_high; // ecx
  int v12; // ecx
  unsigned int v13; // eax
  __int64 v14; // rdx
  __int64 v15; // r8
  __int64 v16; // r9
  unsigned int OwningThread_high; // eax
  HANDLE Handles[3]; // [rsp+30h] [rbp-18h] BYREF
  unsigned int v20; // [rsp+50h] [rbp+8h] BYREF

  OwningThread = this[6].OwningThread;
  v2 = 0;
  v20 = 0;
  Handles[0] = OwningThread;
  Handles[1] = this[6].LockSemaphore;
  while ( 1 )
  {
    EnterCriticalSection(this);
    if ( this[1].LockCount )
    {
      CPxeRogueDetection::SetAuthState((CPxeRogueDetection *)this, 0);
      p_LockSemaphore = &this[1].LockSemaphore;
    }
    else
    {
      p_LockSemaphore = &this[1].LockSemaphore;
      if ( LODWORD(this[1].LockSemaphore)
        || (EnterCriticalSection(&CriticalSection), v5 = dword_18001CD08, LeaveCriticalSection(&CriticalSection), !v5) )
      {
        CPxeRogueDetection::SetAuthState((CPxeRogueDetection *)this, 1);
      }
    }
    LeaveCriticalSection(this);
    Trace(0x20000u, L"Rogue Detection: Wait=%u", v20);
    v6 = WaitForMultipleObjects(2u, Handles, 0, 1000 * v20);
    if ( !v6 )
      return 0;
    if ( v6 != 258 && v6 != 1 )
    {
      CPxeRogueDetection::SetAuthState((CPxeRogueDetection *)this, 0);
      return 0;
    }
    if ( HIDWORD(this[5].LockSemaphore) == 4 )
    {
      ServerRole = CPxeRogueDetection::GetServerRole((CPxeRogueDetection *)this, &v20);
      v2 = ElValidateWin32_4(ServerRole, v8, v9, 1993);
      if ( v2 )
        continue;
    }
    EnterCriticalSection(this);
    if ( this[1].LockCount )
      goto LABEL_26;
    if ( *(_DWORD *)p_LockSemaphore
      || (EnterCriticalSection(&CriticalSection), v10 = dword_18001CD08, LeaveCriticalSection(&CriticalSection), !v10) )
    {
      if ( this[1].LockCount )
LABEL_26:
        OwningThread_high = HIDWORD(this[1].OwningThread);
      else
        OwningThread_high = (unsigned int)this[1].OwningThread;
      v20 = OwningThread_high;
      goto LABEL_24;
    }
    LockSemaphore_high = HIDWORD(this[5].LockSemaphore);
    if ( LockSemaphore_high )
    {
      v12 = LockSemaphore_high - 1;
      if ( !v12 )
      {
        CPxeRogueDetection::SetAuthState((CPxeRogueDetection *)this, 1);
        v20 = -1;
        goto LABEL_22;
      }
      if ( (unsigned int)(v12 - 1) > 1 )
        goto LABEL_22;
      v13 = CPxeRogueDetection::DoNetworkAuthorization((CPxeRogueDetection *)this, &v20);
      v16 = 2044;
    }
    else
    {
      v13 = CPxeRogueDetection::DoNT5Authorization((const unsigned __int16 **)this, &v20);
      v16 = 2039;
    }
    v2 = ElValidateWin32_4(v13, v14, v15, v16);
LABEL_22:
    if ( v2 )
      CEventLog::Log((CEventLog *)qword_18001CC40, 0xC1070305, 1);
LABEL_24:
    LeaveCriticalSection(this);
  }
}

```

## disassembly

```asm
0x18000ea3c  mov     r11, rsp
0x18000ea3f  mov     [r11+10h], rbx
0x18000ea43  mov     [r11+18h], rbp
0x18000ea47  mov     [r11+20h], rsi
0x18000ea4b  push    rdi
0x18000ea4c  sub     rsp, 40h
0x18000ea50  mov     rax, [rcx+100h]
0x18000ea57  xor     ebp, ebp
0x18000ea59  and     [rsp+48h+arg_0], ebp
0x18000ea5d  mov     rdi, rcx
0x18000ea60  mov     [r11-18h], rax
0x18000ea64  mov     rax, [rcx+108h]
0x18000ea6b  mov     [r11-10h], rax
0x18000ea6f  mov     rcx, rdi; lpCriticalSection
0x18000ea72  call    cs:__imp_EnterCriticalSection
0x18000ea79  nop     dword ptr [rax+rax+00h]
0x18000ea7e  cmp     dword ptr [rdi+30h], 0
0x18000ea82  jz      short loc_18000EA94
0x18000ea84  xor     edx, edx; int
0x18000ea86  mov     rcx, rdi; this
0x18000ea89  call    ?SetAuthState@CPxeRogueDetection@@AEAAXH@Z; CPxeRogueDetection::SetAuthState(int)
0x18000ea8e  lea     rsi, [rdi+40h]
0x18000ea92  jmp     short loc_18000EADA
0x18000ea94  lea     rsi, [rdi+40h]
0x18000ea98  cmp     dword ptr [rsi], 0
0x18000ea9b  jnz     short loc_18000EACD
0x18000ea9d  lea     rcx, CriticalSection; lpCriticalSection
0x18000eaa4  call    cs:__imp_EnterCriticalSection
0x18000eaab  nop     dword ptr [rax+rax+00h]
0x18000eab0  mov     ebx, cs:dword_18001CD08
0x18000eab6  lea     rcx, CriticalSection; lpCriticalSection
0x18000eabd  call    cs:__imp_LeaveCriticalSection
0x18000eac4  nop     dword ptr [rax+rax+00h]
0x18000eac9  test    ebx, ebx
0x18000eacb  jnz     short loc_18000EADA
0x18000eacd  mov     edx, 1; int
0x18000ead2  mov     rcx, rdi; this
0x18000ead5  call    ?SetAuthState@CPxeRogueDetection@@AEAAXH@Z; CPxeRogueDetection::SetAuthState(int)
0x18000eada  mov     rcx, rdi; lpCriticalSection
0x18000eadd  call    cs:__imp_LeaveCriticalSection
0x18000eae4  nop     dword ptr [rax+rax+00h]
0x18000eae9  mov     r8d, [rsp+48h+arg_0]
0x18000eaee  lea     rdx, aRogueDetection_5; "Rogue Detection: Wait=%u"
0x18000eaf5  mov     ecx, 20000h; unsigned int
0x18000eafa  call    ?Trace@@YAXKPEBGZZ; Trace(ulong,ushort const *,...)
0x18000eaff  imul    r9d, [rsp+48h+arg_0], 3E8h; dwMilliseconds
0x18000eb08  lea     rdx, [rsp+48h+Handles]; lpHandles
0x18000eb0d  xor     r8d, r8d; bWaitAll
0x18000eb10  lea     ecx, [r8+2]; nCount
0x18000eb14  call    cs:__imp_WaitForMultipleObjects
0x18000eb1b  nop     dword ptr [rax+rax+00h]
0x18000eb20  test    eax, eax
0x18000eb22  jz      loc_18000EC75
0x18000eb28  cmp     eax, 102h
0x18000eb2d  jz      short loc_18000EB38
0x18000eb2f  cmp     eax, 1
0x18000eb32  jnz     loc_18000EC6B
0x18000eb38  cmp     dword ptr [rdi+0E4h], 4
0x18000eb3f  jnz     short loc_18000EB65
0x18000eb41  lea     rdx, [rsp+48h+arg_0]; unsigned int *
0x18000eb46  mov     rcx, rdi; this
0x18000eb49  call    ?GetServerRole@CPxeRogueDetection@@AEAAKPEAK@Z; CPxeRogueDetection::GetServerRole(ulong *)
0x18000eb4e  mov     ecx, eax
0x18000eb50  mov     r9d, 7C9h
0x18000eb56  call    ElValidateWin32_4
0x18000eb5b  mov     ebp, eax
0x18000eb5d  test    eax, eax
0x18000eb5f  jnz     loc_18000EA6F
0x18000eb65  mov     rcx, rdi; lpCriticalSection
0x18000eb68  call    cs:__imp_EnterCriticalSection
0x18000eb6f  nop     dword ptr [rax+rax+00h]
0x18000eb74  cmp     dword ptr [rdi+30h], 0
0x18000eb78  jnz     loc_18000EC5D
0x18000eb7e  cmp     dword ptr [rsi], 0
0x18000eb81  jnz     loc_18000EC57
0x18000eb87  lea     rcx, CriticalSection; lpCriticalSection
0x18000eb8e  call    cs:__imp_EnterCriticalSection
0x18000eb95  nop     dword ptr [rax+rax+00h]
0x18000eb9a  mov     ebx, cs:dword_18001CD08
0x18000eba0  lea     rcx, CriticalSection; lpCriticalSection
0x18000eba7  call    cs:__imp_LeaveCriticalSection
0x18000ebae  nop     dword ptr [rax+rax+00h]
0x18000ebb3  test    ebx, ebx
0x18000ebb5  jz      loc_18000EC57
0x18000ebbb  mov     ecx, [rdi+0E4h]
0x18000ebc1  test    ecx, ecx
0x18000ebc3  jz      short loc_18000EBFD
0x18000ebc5  sub     ecx, 1
0x18000ebc8  jz      short loc_18000EBE9
0x18000ebca  sub     ecx, 1
0x18000ebcd  jz      short loc_18000EBD4
0x18000ebcf  cmp     ecx, 1
0x18000ebd2  jnz     short loc_18000EC19
0x18000ebd4  lea     rdx, [rsp+48h+arg_0]; unsigned int *
0x18000ebd9  mov     rcx, rdi; this
0x18000ebdc  call    ?DoNetworkAuthorization@CPxeRogueDetection@@AEAAKPEAK@Z; CPxeRogueDetection::DoNetworkAuthorization(ulong *)
0x18000ebe1  mov     r9d, 7FCh
0x18000ebe7  jmp     short loc_18000EC10
0x18000ebe9  mov     edx, 1; int
0x18000ebee  mov     rcx, rdi; this
0x18000ebf1  call    ?SetAuthState@CPxeRogueDetection@@AEAAXH@Z; CPxeRogueDetection::SetAuthState(int)
0x18000ebf6  or      [rsp+48h+arg_0], 0FFFFFFFFh
0x18000ebfb  jmp     short loc_18000EC19
0x18000ebfd  lea     rdx, [rsp+48h+arg_0]; unsigned int *
0x18000ec02  mov     rcx, rdi; this
0x18000ec05  call    ?DoNT5Authorization@CPxeRogueDetection@@AEAAKPEAK@Z; CPxeRogueDetection::DoNT5Authorization(ulong *)
0x18000ec0a  mov     r9d, 7F7h
0x18000ec10  mov     ecx, eax
0x18000ec12  call    ElValidateWin32_4
0x18000ec17  mov     ebp, eax
0x18000ec19  test    ebp, ebp
0x18000ec1b  jz      short loc_18000EC43
0x18000ec1d  mov     r9d, 5
0x18000ec23  mov     [rsp+48h+var_28], ebp
0x18000ec27  mov     edx, 0C1070305h
0x18000ec2c  lea     rcx, qword_18001CC40
0x18000ec33  lea     r8d, [r9-4]
0x18000ec37  call    cs:__imp_?Log@CEventLog@@QEAAKKHZZ; CEventLog::Log(ulong,int,...)
0x18000ec3e  nop     dword ptr [rax+rax+00h]
0x18000ec43  mov     rcx, rdi; lpCriticalSection
0x18000ec46  call    cs:__imp_LeaveCriticalSection
0x18000ec4d  nop     dword ptr [rax+rax+00h]
0x18000ec52  jmp     loc_18000EA6F
0x18000ec57  cmp     dword ptr [rdi+30h], 0
0x18000ec5b  jz      short loc_18000EC62
0x18000ec5d  mov     eax, [rdi+3Ch]
0x18000ec60  jmp     short loc_18000EC65
0x18000ec62  mov     eax, [rdi+38h]
0x18000ec65  mov     [rsp+48h+arg_0], eax
0x18000ec69  jmp     short loc_18000EC43
0x18000ec6b  xor     edx, edx; int
0x18000ec6d  mov     rcx, rdi; this
0x18000ec70  call    ?SetAuthState@CPxeRogueDetection@@AEAAXH@Z; CPxeRogueDetection::SetAuthState(int)
0x18000ec75  mov     rbx, [rsp+48h+arg_8]
0x18000ec7a  xor     eax, eax
0x18000ec7c  mov     rbp, [rsp+48h+arg_10]
0x18000ec81  mov     rsi, [rsp+48h+arg_18]
0x18000ec86  add     rsp, 40h
0x18000ec8a  pop     rdi
0x18000ec8b  retn
```
