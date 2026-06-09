# CreateJobObjectContext

- ea: `0x18001cd98`
- end: `0x18001cedb`
- name: `CreateJobObjectContext`
- size: `323`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x18001c160`
- `0x18001da20`

## callees

- `0x18000467c`
- `0x1800150c0`
- `0x18001cd98`
- `0x18004022e`
- `0x180040260`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ceb5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ceb5`
- `api-ms-win-core-job-l2-1-0!CreateJobObjectW` at `0x18001cdfd`
- `api-ms-win-core-job-l2-1-0!CreateJobObjectW` at `0x18001cdfd`
- `api-ms-win-core-job-l2-1-0!SetInformationJobObject` at `0x18001ce51`
- `api-ms-win-core-job-l2-1-0!SetInformationJobObject` at `0x18001ce51`

## pseudocode

```c
__int64 __fastcall CreateJobObjectContext(int a1, int a2, _QWORD *a3)
{
  char *v6; // rax
  char *v7; // rdi
  struct _LIST_ENTRY *v8; // rsi
  HANDLE JobObjectW; // rax
  struct _LIST_ENTRY *v10; // rax
  DWORD LastError; // ebx
  _BYTE JobObjectInformation[16]; // [rsp+20h] [rbp-B8h] BYREF
  int v14; // [rsp+30h] [rbp-A8h]

  memset_0(JobObjectInformation, 0, 0x90u);
  v6 = (char *)UbpmAlloc(0x28u);
  v7 = v6;
  if ( v6 )
  {
    v8 = (struct _LIST_ENTRY *)(v6 + 8);
    *((_QWORD *)v6 + 2) = v6 + 8;
    *((_QWORD *)v6 + 1) = v6 + 8;
    JobObjectW = CreateJobObjectW(0, 0);
    *((_QWORD *)v7 + 3) = JobObjectW;
    if ( JobObjectW
      && ((*((_DWORD *)v7 + 8) = a2, *((_DWORD *)v7 + 9) = a1, a1 == 1)
       || a2
       || (memset_0(JobObjectInformation, 0, 0x90u),
           v14 = 4096,
           SetInformationJobObject(*((HANDLE *)v7 + 3), JobObjectExtendedLimitInformation, JobObjectInformation, 0x90u))) )
    {
      v10 = off_18004F170;
      if ( off_18004F170->Flink != &g_leJobObjectContextsHead )
        __fastfail(3u);
      v8->Flink = &g_leJobObjectContextsHead;
      LastError = 0;
      v8->Blink = v10;
      v10->Flink = v8;
      off_18004F170 = v8;
      *a3 = v7;
    }
    else
    {
      LastError = GetLastError();
      DestroyJobObjectContext(v7);
    }
  }
  else
  {
    return 14;
  }
  return LastError;
}

```

## disassembly

```asm
0x18001cd98  mov     [rsp+arg_0], rbx
0x18001cd9d  mov     [rsp+arg_8], rbp
0x18001cda2  push    rsi
0x18001cda3  push    rdi
0x18001cda4  push    r14
0x18001cda6  sub     rsp, 0C0h
0x18001cdad  mov     rax, cs:__security_cookie
0x18001cdb4  xor     rax, rsp
0x18001cdb7  mov     [rsp+0D8h+var_28], rax
0x18001cdbf  mov     r14, r8
0x18001cdc2  mov     ebx, edx
0x18001cdc4  mov     ebp, ecx
0x18001cdc6  xor     edx, edx; Val
0x18001cdc8  mov     r8d, 90h; Size
0x18001cdce  lea     rcx, [rsp+0D8h+JobObjectInformation]; void *
0x18001cdd3  call    memset_0
0x18001cdd8  mov     ecx, 28h ; '('; Size
0x18001cddd  call    ?UbpmAlloc@@YAPEAXK@Z; UbpmAlloc(ulong)
0x18001cde2  mov     rdi, rax
0x18001cde5  test    rax, rax
0x18001cde8  jz      loc_18001CED4
0x18001cdee  lea     rsi, [rax+8]
0x18001cdf2  xor     edx, edx; lpName
0x18001cdf4  xor     ecx, ecx; lpJobAttributes
0x18001cdf6  mov     [rsi+8], rsi
0x18001cdfa  mov     [rsi], rsi
0x18001cdfd  call    cs:__imp_CreateJobObjectW
0x18001ce04  nop     dword ptr [rax+rax+00h]
0x18001ce09  mov     [rdi+18h], rax
0x18001ce0d  test    rax, rax
0x18001ce10  jz      loc_18001CEB5
0x18001ce16  mov     [rdi+20h], ebx
0x18001ce19  mov     [rdi+24h], ebp
0x18001ce1c  cmp     ebp, 1
0x18001ce1f  jz      short loc_18001CE61
0x18001ce21  test    ebx, ebx
0x18001ce23  jnz     short loc_18001CE61
0x18001ce25  xor     edx, edx; Val
0x18001ce27  lea     rcx, [rsp+0D8h+JobObjectInformation]; void *
0x18001ce2c  mov     r8d, 90h; Size
0x18001ce32  call    memset_0
0x18001ce37  mov     [rsp+0D8h+var_A8], 1000h
0x18001ce3f  lea     r8, [rsp+0D8h+JobObjectInformation]; lpJobObjectInformation
0x18001ce44  mov     rcx, [rdi+18h]; hJob
0x18001ce48  lea     edx, [rbx+9]; JobObjectInformationClass
0x18001ce4b  mov     r9d, 90h; cbJobObjectInformationLength
0x18001ce51  call    cs:__imp_SetInformationJobObject
0x18001ce58  nop     dword ptr [rax+rax+00h]
0x18001ce5d  test    eax, eax
0x18001ce5f  jz      short loc_18001CEB5
0x18001ce61  mov     rax, cs:off_18004F170
0x18001ce68  lea     rcx, ?g_leJobObjectContextsHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_leJobObjectContextsHead
0x18001ce6f  cmp     [rax], rcx
0x18001ce72  jnz     short loc_18001CECD
0x18001ce74  mov     [rsi], rcx
0x18001ce77  xor     ebx, ebx
0x18001ce79  mov     [rsi+8], rax
0x18001ce7d  mov     [rax], rsi
0x18001ce80  mov     cs:off_18004F170, rsi
0x18001ce87  mov     [r14], rdi
0x18001ce8a  mov     eax, ebx
0x18001ce8c  mov     rcx, [rsp+0D8h+var_28]
0x18001ce94  xor     rcx, rsp; StackCookie
0x18001ce97  call    __security_check_cookie
0x18001ce9c  lea     r11, [rsp+0D8h+var_18]
0x18001cea4  mov     rbx, [r11+20h]
0x18001cea8  mov     rbp, [r11+28h]
0x18001ceac  mov     rsp, r11
0x18001ceaf  pop     r14
0x18001ceb1  pop     rdi
0x18001ceb2  pop     rsi
0x18001ceb3  retn
0x18001ceb5  call    cs:__imp_GetLastError
0x18001cebc  nop     dword ptr [rax+rax+00h]
0x18001cec1  mov     rcx, rdi
0x18001cec4  mov     ebx, eax
0x18001cec6  call    DestroyJobObjectContext
0x18001cecb  jmp     short loc_18001CE8A
0x18001cecd  mov     ecx, 3
0x18001ced2  int     29h; Win8: RtlFailFast(ecx)
0x18001ced4  mov     ebx, 0Eh
0x18001ced9  jmp     short loc_18001CE8A
```
