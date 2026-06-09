# CreateJobObjectContext

- ea: `0x1800204cc`
- end: `0x1800205fc`
- name: `CreateJobObjectContext`
- size: `304`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x18001fa6c`
- `0x180021060`

## callees

- `0x18000f9a0`
- `0x18002046c`
- `0x1800204cc`
- `0x18003d7de`
- `0x18003d810`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800205dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800205dc`
- `api-ms-win-core-job-l2-1-0!CreateJobObjectW` at `0x180020531`
- `api-ms-win-core-job-l2-1-0!CreateJobObjectW` at `0x180020531`
- `api-ms-win-core-job-l2-1-0!SetInformationJobObject` at `0x18002057f`
- `api-ms-win-core-job-l2-1-0!SetInformationJobObject` at `0x18002057f`

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
      v10 = off_18004C170;
      if ( off_18004C170->Flink != &g_leJobObjectContextsHead )
        __fastfail(3u);
      v8->Flink = &g_leJobObjectContextsHead;
      LastError = 0;
      v8->Blink = v10;
      v10->Flink = v8;
      off_18004C170 = v8;
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
0x1800204cc  mov     [rsp+arg_0], rbx
0x1800204d1  mov     [rsp+arg_8], rbp
0x1800204d6  push    rsi
0x1800204d7  push    rdi
0x1800204d8  push    r14
0x1800204da  sub     rsp, 0C0h
0x1800204e1  mov     rax, cs:__security_cookie
0x1800204e8  xor     rax, rsp
0x1800204eb  mov     [rsp+0D8h+var_28], rax
0x1800204f3  mov     r14, r8
0x1800204f6  mov     ebx, edx
0x1800204f8  mov     ebp, ecx
0x1800204fa  xor     edx, edx; Val
0x1800204fc  mov     r8d, 90h; Size
0x180020502  lea     rcx, [rsp+0D8h+JobObjectInformation]; void *
0x180020507  call    memset_0
0x18002050c  mov     ecx, 28h ; '('; Size
0x180020511  call    ?UbpmAlloc@@YAPEAXK@Z; UbpmAlloc(ulong)
0x180020516  mov     rdi, rax
0x180020519  test    rax, rax
0x18002051c  jz      loc_1800205F5
0x180020522  lea     rsi, [rax+8]
0x180020526  xor     edx, edx; lpName
0x180020528  xor     ecx, ecx; lpJobAttributes
0x18002052a  mov     [rsi+8], rsi
0x18002052e  mov     [rsi], rsi
0x180020531  call    cs:__imp_CreateJobObjectW
0x180020537  mov     [rdi+18h], rax
0x18002053b  test    rax, rax
0x18002053e  jz      loc_1800205DC
0x180020544  mov     [rdi+20h], ebx
0x180020547  mov     [rdi+24h], ebp
0x18002054a  cmp     ebp, 1
0x18002054d  jz      short loc_180020589
0x18002054f  test    ebx, ebx
0x180020551  jnz     short loc_180020589
0x180020553  xor     edx, edx; Val
0x180020555  lea     rcx, [rsp+0D8h+JobObjectInformation]; void *
0x18002055a  mov     r8d, 90h; Size
0x180020560  call    memset_0
0x180020565  mov     [rsp+0D8h+var_A8], 1000h
0x18002056d  lea     r8, [rsp+0D8h+JobObjectInformation]; lpJobObjectInformation
0x180020572  mov     rcx, [rdi+18h]; hJob
0x180020576  lea     edx, [rbx+9]; JobObjectInformationClass
0x180020579  mov     r9d, 90h; cbJobObjectInformationLength
0x18002057f  call    cs:__imp_SetInformationJobObject
0x180020585  test    eax, eax
0x180020587  jz      short loc_1800205DC
0x180020589  mov     rax, cs:off_18004C170
0x180020590  lea     rcx, ?g_leJobObjectContextsHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_leJobObjectContextsHead
0x180020597  cmp     [rax], rcx
0x18002059a  jnz     short loc_1800205EE
0x18002059c  mov     [rsi], rcx
0x18002059f  xor     ebx, ebx
0x1800205a1  mov     [rsi+8], rax
0x1800205a5  mov     [rax], rsi
0x1800205a8  mov     cs:off_18004C170, rsi
0x1800205af  mov     [r14], rdi
0x1800205b2  mov     eax, ebx
0x1800205b4  mov     rcx, [rsp+0D8h+var_28]
0x1800205bc  xor     rcx, rsp; StackCookie
0x1800205bf  call    __security_check_cookie
0x1800205c4  lea     r11, [rsp+0D8h+var_18]
0x1800205cc  mov     rbx, [r11+20h]
0x1800205d0  mov     rbp, [r11+28h]
0x1800205d4  mov     rsp, r11
0x1800205d7  pop     r14
0x1800205d9  pop     rdi
0x1800205da  pop     rsi
0x1800205db  retn
0x1800205dc  call    cs:__imp_GetLastError
0x1800205e2  mov     rcx, rdi
0x1800205e5  mov     ebx, eax
0x1800205e7  call    DestroyJobObjectContext
0x1800205ec  jmp     short loc_1800205B2
0x1800205ee  mov     ecx, 3
0x1800205f3  int     29h; Win8: RtlFailFast(ecx)
0x1800205f5  mov     ebx, 0Eh
0x1800205fa  jmp     short loc_1800205B2
```
