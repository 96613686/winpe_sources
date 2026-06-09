# LogServiceError(uint,ulong,uint)

- ea: `0x18002c33c`
- end: `0x18002c493`
- name: `?LogServiceError@@YAXIKI@Z`
- size: `343`
- prototype: `void __fastcall(unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001452c`

## callees

- `0x180003ef0`
- `0x180029464`
- `0x18002c28c`
- `0x18002c33c`
- `0x18002cd24`
- `0x18002e572`
- `0x18002e5b0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002c462`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002c46d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002c462`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002c46d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18002c389`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18002c389`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18002c446`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18002c446`

## string_xrefs

- `0x18002c393`: `"Task Scheduler Service" ** FATAL ERROR **\n`

## pseudocode

```c
void __fastcall LogServiceError()
{
  unsigned __int16 *v0; // rax
  unsigned __int16 *v1; // rbx
  unsigned __int16 *v2; // rcx
  WCHAR lpBuffer[4]; // [rsp+40h] [rbp-C0h] BYREF
  va_list Arguments[3]; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR Buffer[64]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR DateStr[64]; // [rsp+E0h] [rbp-20h] BYREF
  WCHAR TimeStr[64]; // [rsp+160h] [rbp+60h] BYREF

  if ( ghLog )
  {
    if ( LoadStringW(g_hInstance, 0x46Eu, Buffer, 64) )
    {
      memset_0(DateStr, 0, sizeof(DateStr));
      memset_0(TimeStr, 0, sizeof(TimeStr));
      if ( (unsigned int)GetDateTime(0, DateStr, TimeStr) )
      {
        v0 = ComposeErrorMsg();
        v1 = v0;
        if ( v0 )
        {
          Arguments[2] = (va_list)v0;
          Arguments[0] = (va_list)DateStr;
          *(_QWORD *)lpBuffer = 0;
          Arguments[1] = (va_list)TimeStr;
          if ( FormatMessageW(0x2500u, Buffer, 0, 0, lpBuffer, 1u, Arguments) )
          {
            WriteLog(*(_WORD **)lpBuffer);
            LocalFree(v1);
            v2 = *(unsigned __int16 **)lpBuffer;
          }
          else
          {
            v2 = v1;
          }
          LocalFree(v2);
        }
      }
    }
    else
    {
      StringCchCopyW(Buffer, 0x40u, L"\"Task Scheduler Service\" ** FATAL ERROR **\n");
      WriteLog(Buffer);
    }
  }
}

```

## disassembly

```asm
0x18002c33c  mov     [rsp-8+arg_0], rbx
0x18002c341  push    rbp
0x18002c342  lea     rbp, [rsp-0F0h]
0x18002c34a  sub     rsp, 1F0h
0x18002c351  mov     rax, cs:__security_cookie
0x18002c358  xor     rax, rsp
0x18002c35b  mov     [rbp+0F0h+var_10], rax
0x18002c362  cmp     cs:?ghLog@@3PEAXEA, 0; void * ghLog
0x18002c36a  jz      loc_18002C473
0x18002c370  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x18002c377  lea     r8, [rsp+1F0h+Buffer]; lpBuffer
0x18002c37c  mov     ebx, 40h ; '@'
0x18002c381  mov     edx, 46Eh; uID
0x18002c386  mov     r9d, ebx; cchBufferMax
0x18002c389  call    cs:__imp_LoadStringW
0x18002c38f  test    eax, eax
0x18002c391  jnz     short loc_18002C3B5
0x18002c393  lea     r8, aTaskSchedulerS; "\"Task Scheduler Service\" ** FATAL ERR"...
0x18002c39a  mov     edx, ebx; unsigned __int64
0x18002c39c  lea     rcx, [rsp+1F0h+Buffer]; unsigned __int16 *
0x18002c3a1  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002c3a6  lea     rcx, [rsp+1F0h+Buffer]; lpBuffer
0x18002c3ab  call    ?WriteLog@@YAXPEAG@Z; WriteLog(ushort *)
0x18002c3b0  jmp     loc_18002C473
0x18002c3b5  mov     ebx, 80h
0x18002c3ba  lea     rcx, [rbp+0F0h+DateStr]; void *
0x18002c3be  mov     r8d, ebx; Size
0x18002c3c1  xor     edx, edx; Val
0x18002c3c3  call    memset_0
0x18002c3c8  mov     r8d, ebx; Size
0x18002c3cb  lea     rcx, [rbp+0F0h+TimeStr]; void *
0x18002c3cf  xor     edx, edx; Val
0x18002c3d1  call    memset_0
0x18002c3d6  lea     r8, [rbp+0F0h+TimeStr]; lpTimeStr
0x18002c3da  xor     ecx, ecx; lpTime
0x18002c3dc  lea     rdx, [rbp+0F0h+DateStr]; lpDateStr
0x18002c3e0  call    ?GetDateTime@@YAHPEBU_SYSTEMTIME@@PEAG1@Z; GetDateTime(_SYSTEMTIME const *,ushort *,ushort *)
0x18002c3e5  test    eax, eax
0x18002c3e7  jz      loc_18002C473
0x18002c3ed  call    ?ComposeErrorMsg@@YAPEAGIKIH@Z; ComposeErrorMsg(uint,ulong,uint,int)
0x18002c3f2  mov     rbx, rax
0x18002c3f5  test    rax, rax
0x18002c3f8  jz      short loc_18002C473
0x18002c3fa  lea     rax, [rbp+0F0h+DateStr]
0x18002c3fe  mov     [rsp+1F0h+var_198], rbx
0x18002c403  mov     [rsp+1F0h+var_1A8], rax
0x18002c408  lea     rdx, [rsp+1F0h+Buffer]; lpSource
0x18002c40d  lea     rax, [rbp+0F0h+TimeStr]
0x18002c411  mov     qword ptr [rsp+1F0h+var_1B0], 0
0x18002c41a  mov     [rsp+1F0h+var_1A0], rax
0x18002c41f  xor     r9d, r9d; dwLanguageId
0x18002c422  lea     rax, [rsp+1F0h+var_1A8]
0x18002c427  xor     r8d, r8d; dwMessageId
0x18002c42a  mov     [rsp+1F0h+Arguments], rax; Arguments
0x18002c42f  mov     ecx, 2500h; dwFlags
0x18002c434  lea     rax, [rsp+1F0h+var_1B0]
0x18002c439  mov     [rsp+1F0h+nSize], 1; nSize
0x18002c441  mov     [rsp+1F0h+lpBuffer], rax; lpBuffer
0x18002c446  call    cs:__imp_FormatMessageW
0x18002c44c  test    eax, eax
0x18002c44e  jnz     short loc_18002C455
0x18002c450  mov     rcx, rbx
0x18002c453  jmp     short loc_18002C46D
0x18002c455  mov     rcx, qword ptr [rsp+1F0h+var_1B0]; lpBuffer
0x18002c45a  call    ?WriteLog@@YAXPEAG@Z; WriteLog(ushort *)
0x18002c45f  mov     rcx, rbx; hMem
0x18002c462  call    cs:__imp_LocalFree
0x18002c468  mov     rcx, qword ptr [rsp+1F0h+var_1B0]; hMem
0x18002c46d  call    cs:__imp_LocalFree
0x18002c473  mov     rcx, [rbp+0F0h+var_10]
0x18002c47a  xor     rcx, rsp; StackCookie
0x18002c47d  call    __security_check_cookie
0x18002c482  mov     rbx, [rsp+1F0h+arg_0]
0x18002c48a  add     rsp, 1F0h
0x18002c491  pop     rbp
0x18002c492  retn
```
