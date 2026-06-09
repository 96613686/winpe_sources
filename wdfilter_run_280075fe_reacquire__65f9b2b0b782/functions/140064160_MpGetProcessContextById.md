# MpGetProcessContextById

- ea: `0x140064160`
- end: `0x140064369`
- name: `MpGetProcessContextById`
- size: `521`
- prototype: ``
- caller_count: `10`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x14000b998`
- `0x140036780`
- `0x1400387f0`
- `0x140062588`
- `0x140063a70`
- `0x14006436c`
- `0x140080e40`
- `0x140081bd0`
- `0x140081da0`
- `0x140082380`

## callees

- `0x1400051bc`
- `0x1400118d0`
- `0x140064160`

## import_xrefs

- `ntoskrnl!PsGetProcessId` at `0x1400641dc`
- `ntoskrnl!PsGetProcessId` at `0x1400641dc`
- `ntoskrnl!PsLookupProcessByProcessId` at `0x14006419a`
- `ntoskrnl!PsLookupProcessByProcessId` at `0x14006419a`
- `ntoskrnl!PsGetProcessCreateTimeQuadPart` at `0x1400641ca`
- `ntoskrnl!PsGetProcessCreateTimeQuadPart` at `0x1400641ca`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006427c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006427c`
- `ntoskrnl!ExReleaseResourceLite` at `0x140064270`
- `ntoskrnl!ExReleaseResourceLite` at `0x140064270`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140064215`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140064215`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140064203`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140064203`
- `ntoskrnl!KdRefreshDebuggerNotPresent` at `0x1400642f1`
- `ntoskrnl!KdRefreshDebuggerNotPresent` at `0x1400642f1`
- `ntoskrnl!KeBugCheck` at `0x140064309`
- `ntoskrnl!KeBugCheck` at `0x140064309`
- `ntoskrnl!ObfDereferenceObject` at `0x14006429c`
- `ntoskrnl!ObfDereferenceObject` at `0x14006429c`

## pseudocode

```c
__int64 __fastcall MpGetProcessContextById(void *a1, volatile signed __int32 **a2)
{
  NTSTATUS v3; // ebx
  struct _KPROCESS *v4; // rbx
  LONGLONG TimeQuadPart; // rbp
  HANDLE ProcessId; // rax
  unsigned int v7; // esi
  unsigned __int64 v8; // rdi
  char *v9; // rbx
  _QWORD *v10; // r8
  _QWORD *i; // rax
  volatile signed __int32 *v12; // rcx
  PEPROCESS Process; // [rsp+30h] [rbp-38h] BYREF

  Process = 0;
  if ( !a1 )
    return 3221226021LL;
  v3 = PsLookupProcessByProcessId(a1, &Process);
  if ( v3 < 0 )
  {
    _mm_lfence();
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_qD(
        WPP_GLOBAL_Control->AttachedDevice,
        40,
        WPP_9c9a40995a6d306ff00b675dc6e33d78_Traceguids,
        KeGetCurrentThread(),
        v3);
    return (unsigned int)v3;
  }
  else
  {
    _InterlockedIncrement64(&ObTotalReferences);
    v4 = Process;
    TimeQuadPart = PsGetProcessCreateTimeQuadPart(Process);
    ProcessId = PsGetProcessId(v4);
    v7 = -1073741275;
    *a2 = 0;
    v8 = (unsigned __int64)ProcessId;
    if ( ProcessId )
    {
      v9 = (char *)MpProcessTable;
      KeEnterCriticalRegion();
      ExAcquireResourceSharedLite((PERESOURCE)(v9 + 8), 1u);
      v10 = (_QWORD *)(*((_QWORD *)MpProcessTable + 48) + 16 * ((v8 >> 2) & 0x7F));
      for ( i = (_QWORD *)*v10; i != v10; i = (_QWORD *)*i )
      {
        v12 = (volatile signed __int32 *)(i - 1);
        if ( v8 == i[2] && TimeQuadPart == *((_QWORD *)v12 + 4) )
        {
          _InterlockedIncrement(v12 + 12);
          *a2 = v12;
          v7 = 0;
          break;
        }
      }
      ExReleaseResourceLite((PERESOURCE)((char *)MpProcessTable + 8));
      KeLeaveCriticalRegion();
    }
    if ( Process )
    {
      ObfDereferenceObject(Process);
      if ( _InterlockedDecrement64(&ObTotalReferences) < 0 && *(int *)(MpData + 868) < 0 )
      {
        if ( KdRefreshDebuggerNotPresent() )
          KeBugCheck(1u);
        __debugbreak();
      }
    }
    return v7;
  }
}

```

## disassembly

```asm
0x140064160  push    rsi
0x140064162  push    r14
0x140064164  push    r15
0x140064166  sub     rsp, 50h
0x14006416a  mov     rax, cs:__security_cookie
0x140064171  xor     rax, rsp
0x140064174  mov     [rsp+68h+var_30], rax
0x140064179  xor     r15d, r15d
0x14006417c  mov     r14, rdx
0x14006417f  mov     [rsp+68h+Process], r15
0x140064184  test    rcx, rcx
0x140064187  jz      loc_140064316
0x14006418d  lea     rdx, [rsp+68h+Process]; Process
0x140064192  mov     [rsp+68h+arg_10], rbx
0x14006419a  call    cs:__imp_PsLookupProcessByProcessId
0x1400641a1  nop     dword ptr [rax+rax+00h]
0x1400641a6  mov     ebx, eax
0x1400641a8  test    eax, eax
0x1400641aa  js      loc_14006431D
0x1400641b0  mov     [rsp+68h+var_20], rbp
0x1400641b5  mov     [rsp+68h+var_28], rdi
0x1400641ba  lock inc cs:ObTotalReferences
0x1400641c2  mov     rbx, [rsp+68h+Process]
0x1400641c7  mov     rcx, rbx; Process
0x1400641ca  call    cs:__imp_PsGetProcessCreateTimeQuadPart
0x1400641d1  nop     dword ptr [rax+rax+00h]
0x1400641d6  mov     rcx, rbx; Process
0x1400641d9  mov     rbp, rax
0x1400641dc  call    cs:__imp_PsGetProcessId
0x1400641e3  nop     dword ptr [rax+rax+00h]
0x1400641e8  mov     esi, 0C0000225h
0x1400641ed  mov     [r14], r15
0x1400641f0  mov     rdi, rax
0x1400641f3  test    rax, rax
0x1400641f6  jz      loc_140064288
0x1400641fc  mov     rbx, cs:MpProcessTable
0x140064203  call    cs:__imp_KeEnterCriticalRegion
0x14006420a  nop     dword ptr [rax+rax+00h]
0x14006420f  mov     dl, 1; Wait
0x140064211  lea     rcx, [rbx+8]; Resource
0x140064215  call    cs:__imp_ExAcquireResourceSharedLite
0x14006421c  nop     dword ptr [rax+rax+00h]
0x140064221  mov     rax, cs:MpProcessTable
0x140064228  mov     r8, rdi
0x14006422b  shr     r8, 2
0x14006422f  and     r8d, 7Fh
0x140064233  shl     r8, 4
0x140064237  add     r8, [rax+180h]
0x14006423e  mov     rax, [r8]
0x140064241  cmp     rax, r8
0x140064244  jz      short loc_140064265
0x140064246  cmp     rdi, [rax+10h]
0x14006424a  lea     rcx, [rax-8]
0x14006424e  jz      short loc_140064255
0x140064250  mov     rax, [rax]
0x140064253  jmp     short loc_140064241
0x140064255  cmp     rbp, [rcx+20h]
0x140064259  jnz     short loc_140064250
0x14006425b  lock inc dword ptr [rcx+30h]
0x14006425f  mov     [r14], rcx
0x140064262  mov     esi, r15d
0x140064265  mov     rcx, cs:MpProcessTable
0x14006426c  add     rcx, 8; Resource
0x140064270  call    cs:__imp_ExReleaseResourceLite
0x140064277  nop     dword ptr [rax+rax+00h]
0x14006427c  call    cs:__imp_KeLeaveCriticalRegion
0x140064283  nop     dword ptr [rax+rax+00h]
0x140064288  mov     rcx, [rsp+68h+Process]; Object
0x14006428d  mov     rdi, [rsp+68h+var_28]
0x140064292  mov     rbp, [rsp+68h+var_20]
0x140064297  test    rcx, rcx
0x14006429a  jz      short loc_1400642BE
0x14006429c  call    cs:__imp_ObfDereferenceObject
0x1400642a3  nop     dword ptr [rax+rax+00h]
0x1400642a8  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1400642af  lock xadd cs:ObTotalReferences, rax
0x1400642b8  cmp     rax, 1
0x1400642bc  js      short loc_1400642E0
0x1400642be  mov     eax, esi
0x1400642c0  mov     rbx, [rsp+68h+arg_10]
0x1400642c8  mov     rcx, [rsp+68h+var_30]
0x1400642cd  xor     rcx, rsp; StackCookie
0x1400642d0  call    __security_check_cookie
0x1400642d5  add     rsp, 50h
0x1400642d9  pop     r15
0x1400642db  pop     r14
0x1400642dd  pop     rsi
0x1400642de  retn
0x1400642e0  mov     rax, cs:MpData
0x1400642e7  mov     ecx, [rax+364h]
0x1400642ed  test    ecx, ecx
0x1400642ef  jns     short loc_1400642BE
0x1400642f1  call    cs:__imp_KdRefreshDebuggerNotPresent
0x1400642f8  nop     dword ptr [rax+rax+00h]
0x1400642fd  test    al, al
0x1400642ff  jnz     short loc_140064304
0x140064301  int     3; Trap to Debugger
0x140064302  jmp     short loc_1400642BE
0x140064304  mov     ecx, 1; BugCheckCode
0x140064309  call    cs:__imp_KeBugCheck
0x140064316  mov     eax, 0C0000225h
0x14006431b  jmp     short loc_1400642C8
0x14006431d  lfence
0x140064320  mov     rax, cs:WPP_GLOBAL_Control
0x140064327  lea     rcx, WPP_GLOBAL_Control
0x14006432e  cmp     rax, rcx
0x140064331  jnz     short loc_140064337
0x140064333  mov     eax, ebx
0x140064335  jmp     short loc_1400642C0
0x140064337  mov     eax, [rax+2Ch]
0x14006433a  test    al, 1
0x14006433c  jz      short loc_140064333
0x14006433e  mov     r9, gs:188h
0x140064347  lea     r8, WPP_9c9a40995a6d306ff00b675dc6e33d78_Traceguids
0x14006434e  mov     rcx, cs:WPP_GLOBAL_Control
0x140064355  mov     edx, 28h ; '('
0x14006435a  mov     [rsp+68h+var_48], ebx
0x14006435e  mov     rcx, [rcx+18h]
0x140064362  call    WPP_SF_qD
0x140064367  jmp     short loc_140064333
```
