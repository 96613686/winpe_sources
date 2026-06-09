# IsWorkQueueAccessible

- ea: `0x18000bca4`
- end: `0x18000bd4c`
- name: `IsWorkQueueAccessible`
- size: `168`
- prototype: ``
- caller_count: `19`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x1800027dc`
- `0x180002c4c`
- `0x180002f5c`
- `0x180003680`
- `0x180003804`
- `0x1800039dc`
- `0x180003bbc`
- `0x180003d18`
- `0x180004164`
- `0x1800044f0`
- `0x180004e6c`
- `0x1800051d4`
- `0x18000525c`
- `0x180005760`
- `0x1800058ec`
- `0x180005950`
- `0x180005ff0`
- `0x18000859c`
- `0x18000d1c0`

## callees

- `0x180002250`
- `0x18000bca4`
- `0x18001dc70`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bcbb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bcbb`

## string_xrefs

- `0x18000bd0b`: `IsWorkQueueAccessible`

## pseudocode

```c
_BOOL8 __fastcall IsWorkQueueAccessible(const char *a1)
{
  int v1; // edx
  DWORD LastError; // ebx
  int *v4; // rax
  LPCWSTR lpModuleName; // [rsp+68h] [rbp+0h]

  v1 = g_WorkQueue;
  if ( !g_WorkQueue )
  {
    LastError = GetLastError();
    v4 = (int *)ConstructPartialMsgW(
                  0x3000020u,
                  "Function %s was called, but the panther work queue is not running!",
                  a1);
    WdsSetupLogMessageW(
      v4,
      589824,
      (__int64)L"D",
      0,
      0x4D5u,
      L"onecore\\base\\ntsetup\\panther\\engine\\engine.cpp",
      L"IsWorkQueueAccessible",
      lpModuleName,
      LastError,
      0,
      0);
    v1 = g_WorkQueue;
  }
  return v1 != 0;
}

```

## disassembly

```asm
0x18000bca4  mov     [rsp+arg_0], rbx
0x18000bca9  push    rdi
0x18000bcaa  sub     rsp, 60h
0x18000bcae  mov     edx, cs:?g_WorkQueue@@3UWORK_QUEUE@@A; WORK_QUEUE g_WorkQueue
0x18000bcb4  mov     rdi, rcx
0x18000bcb7  test    edx, edx
0x18000bcb9  jnz     short loc_18000BD39
0x18000bcbb  call    cs:__imp_GetLastError
0x18000bcc2  nop     dword ptr [rax+rax+00h]
0x18000bcc7  mov     r8, rdi
0x18000bcca  lea     rdx, aFunctionSWasCa; "Function %s was called, but the panther"...
0x18000bcd1  mov     ecx, 3000020h; unsigned int
0x18000bcd6  mov     ebx, eax
0x18000bcd8  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000bcdd  mov     rcx, [rsp+68h]
0x18000bce2  lea     r8, aD_1; "D"
0x18000bce9  mov     [rsp+68h+var_18], 0; int
0x18000bcf1  xor     r9d, r9d; int
0x18000bcf4  mov     [rsp+68h+var_20], 0; __int64
0x18000bcfd  mov     edx, 90000h; int
0x18000bd02  mov     [rsp+68h+var_28], ebx; int
0x18000bd06  mov     [rsp+68h+lpModuleName], rcx; lpModuleName
0x18000bd0b  lea     rcx, aIsworkqueueacc; "IsWorkQueueAccessible"
0x18000bd12  mov     [rsp+68h+var_38], rcx; __int64
0x18000bd17  lea     rcx, aOnecoreBaseNts_1; "onecore\\base\\ntsetup\\panther\\engine"...
0x18000bd1e  mov     [rsp+68h+var_40], rcx; unsigned __int16 *
0x18000bd23  mov     rcx, rax; int
0x18000bd26  mov     [rsp+68h+var_48], 4D5h; int
0x18000bd2e  call    WdsSetupLogMessageW
0x18000bd33  mov     edx, cs:?g_WorkQueue@@3UWORK_QUEUE@@A; WORK_QUEUE g_WorkQueue
0x18000bd39  mov     rbx, [rsp+68h+arg_0]
0x18000bd3e  xor     eax, eax
0x18000bd40  test    edx, edx
0x18000bd42  setnz   al
0x18000bd45  add     rsp, 60h
0x18000bd49  pop     rdi
0x18000bd4a  retn
```
