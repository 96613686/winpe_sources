# CmdLineParamProcessDash_jobobject(DkParameter &)

- ea: `0x100411500`
- end: `0x1004115e2`
- name: `?CmdLineParamProcessDash_jobobject@@YAXAEAVDkParameter@@@Z`
- size: `226`
- prototype: `void __fastcall(struct DkParameter *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x100411500`

## import_xrefs

- `KERNEL32!CreateJobObjectW` at `0x100411516`
- `KERNEL32!CreateJobObjectW` at `0x100411516`
- `KERNEL32!AssignProcessToJobObject` at `0x100411554`
- `KERNEL32!AssignProcessToJobObject` at `0x100411554`
- `KERNEL32!GetCurrentProcess` at `0x100411548`
- `KERNEL32!GetCurrentProcess` at `0x100411548`
- `sqlmin!?SetJobObjectLimits@@YAXPEAXPEB_W@Z` at `0x1004115db`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x100411542`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10041157a`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x100411542`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10041157a`
- `sqldk!?SOS_OS_NtJobObjectHandle@@3PEAXEA` at `0x100411580`

## pseudocode

```c
// write access to const memory has been detected, the output may be wrong!
void __fastcall CmdLineParamProcessDash_jobobject(struct DkParameter *a1)
{
  __int64 v2; // rbx
  HANDLE JobObjectW; // rsi
  HANDLE CurrentProcess; // rax
  const wchar_t *v5; // rdx
  wchar_t v6; // ax
  wchar_t *v7; // rcx

  v2 = 0;
  JobObjectW = CreateJobObjectW(0, 0);
  if ( !JobObjectW )
    utassert_fail(1u, "nullptr != job", "\"sql\\\\ntdbms\\\\ksource\\\\serverma.cpp\"", 3494, 0);
  CurrentProcess = GetCurrentProcess();
  if ( !AssignProcessToJobObject(JobObjectW, CurrentProcess) )
    utassert_fail(1u, "winResult", "\"sql\\\\ntdbms\\\\ksource\\\\serverma.cpp\"", 3497, 0);
  SOS_OS_NtJobObjectHandle = JobObjectW;
  v5 = (const wchar_t *)*((_QWORD *)a1 + 5);
  v6 = *v5;
  if ( *v5 )
  {
    v7 = (wchar_t *)*((_QWORD *)a1 + 5);
    do
    {
      if ( v6 == 91 )
      {
        *v7 = 60;
      }
      else if ( v6 == 93 )
      {
        *v7 = 62;
      }
      v6 = v5[++v2];
      v7 = (wchar_t *)&v5[v2];
    }
    while ( v6 );
  }
  SetJobObjectLimits(JobObjectW, v5);
}

```

## disassembly

```asm
0x100411500  mov     [rsp+arg_0], rbx
0x100411505  mov     [rsp+arg_8], rsi
0x10041150a  push    rdi
0x10041150b  sub     rsp, 30h
0x10041150f  mov     rdi, rcx
0x100411512  xor     edx, edx; lpName
0x100411514  xor     ecx, ecx; lpJobAttributes
0x100411516  call    cs:__imp_CreateJobObjectW
0x10041151c  xor     ebx, ebx
0x10041151e  mov     rsi, rax
0x100411521  test    rax, rax
0x100411524  jnz     short loc_100411548
0x100411526  mov     r9d, 0DA6h
0x10041152c  mov     [rsp+38h+var_18], rbx
0x100411531  lea     r8, aSqlNtdbmsKsour_3; "\"sql\\\\ntdbms\\\\ksource\\\\serverma."...
0x100411538  lea     rdx, aNullptrJob; "nullptr != job"
0x10041153f  lea     ecx, [rax+1]
0x100411542  call    cs:__imp_?utassert_fail@@YAXIPEBD0H0ZZ; utassert_fail(uint,char const *,char const *,int,char const *,...)
0x100411548  call    cs:__imp_GetCurrentProcess
0x10041154e  mov     rdx, rax; hProcess
0x100411551  mov     rcx, rsi; hJob
0x100411554  call    cs:__imp_AssignProcessToJobObject
0x10041155a  test    eax, eax
0x10041155c  jnz     short loc_100411580
0x10041155e  mov     r9d, 0DA9h
0x100411564  mov     [rsp+38h+var_18], rbx
0x100411569  lea     r8, aSqlNtdbmsKsour_3; "\"sql\\\\ntdbms\\\\ksource\\\\serverma."...
0x100411570  lea     rdx, aWinresult; "winResult"
0x100411577  lea     ecx, [rax+1]
0x10041157a  call    cs:__imp_?utassert_fail@@YAXIPEBD0H0ZZ; utassert_fail(uint,char const *,char const *,int,char const *,...)
0x100411580  mov     rax, cs:__imp_?SOS_OS_NtJobObjectHandle@@3PEAXEA; void * SOS_OS_NtJobObjectHandle
0x100411587  mov     [rax], rsi
0x10041158a  mov     rdx, [rdi+28h]
0x10041158e  movzx   eax, word ptr [rdx]
0x100411591  test    ax, ax
0x100411594  jz      short loc_1004115C9
0x100411596  mov     r8d, 3Ch ; '<'
0x10041159c  mov     rcx, rdx
0x10041159f  lea     r9d, [r8+2]
0x1004115a3  cmp     ax, 5Bh ; '['
0x1004115a7  jnz     short loc_1004115AF
0x1004115a9  mov     [rcx], r8w
0x1004115ad  jmp     short loc_1004115B9
0x1004115af  cmp     ax, 5Dh ; ']'
0x1004115b3  jnz     short loc_1004115B9
0x1004115b5  mov     [rcx], r9w
0x1004115b9  inc     rbx
0x1004115bc  movzx   eax, word ptr [rdx+rbx*2]
0x1004115c0  lea     rcx, [rdx+rbx*2]
0x1004115c4  test    ax, ax
0x1004115c7  jnz     short loc_1004115A3
0x1004115c9  mov     rcx, rsi
0x1004115cc  mov     rbx, [rsp+38h+arg_0]
0x1004115d1  mov     rsi, [rsp+38h+arg_8]
0x1004115d6  add     rsp, 30h
0x1004115da  pop     rdi
0x1004115db  jmp     cs:__imp_?SetJobObjectLimits@@YAXPEAXPEB_W@Z; SetJobObjectLimits(void *,wchar_t const *)
```
