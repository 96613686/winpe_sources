# LogServiceError(uint,ulong,uint)

- ea: `0x18002e0f8`
- end: `0x18002e26c`
- name: `?LogServiceError@@YAXIKI@Z`
- size: `372`
- prototype: `void __fastcall(unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800151b8`

## callees

- `0x1800040c0`
- `0x18002ae14`
- `0x18002e034`
- `0x18002e0f8`
- `0x18002ebd4`
- `0x1800306c2`
- `0x180030700`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002e22e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002e23f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002e22e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002e23f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18002e145`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18002e145`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18002e20c`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18002e20c`

## string_xrefs

- `0x18002e155`: `"Task Scheduler Service" ** FATAL ERROR **\n`

## pseudocode

```c
void __fastcall LogServiceError()
{
  unsigned int v0; // edx
  unsigned int v1; // ecx
  unsigned int v2; // r8d
  int v3; // r9d
  unsigned __int16 *v4; // rax
  unsigned __int16 *v5; // rbx
  unsigned __int16 *v6; // rcx
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
        v4 = ComposeErrorMsg(v1, v0, v2, v3);
        v5 = v4;
        if ( v4 )
        {
          Arguments[2] = (va_list)v4;
          Arguments[0] = (va_list)DateStr;
          *(_QWORD *)lpBuffer = 0;
          Arguments[1] = (va_list)TimeStr;
          if ( FormatMessageW(0x2500u, Buffer, 0, 0, lpBuffer, 1u, Arguments) )
          {
            WriteLog(*(_WORD **)lpBuffer);
            LocalFree(v5);
            v6 = *(unsigned __int16 **)lpBuffer;
          }
          else
          {
            v6 = v5;
          }
          LocalFree(v6);
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
0x18002e0f8  mov     [rsp-8+arg_0], rbx
0x18002e0fd  push    rbp
0x18002e0fe  lea     rbp, [rsp-0F0h]
0x18002e106  sub     rsp, 1F0h
0x18002e10d  mov     rax, cs:__security_cookie
0x18002e114  xor     rax, rsp
0x18002e117  mov     [rbp+0F0h+var_10], rax
0x18002e11e  cmp     cs:?ghLog@@3PEAXEA, 0; void * ghLog
0x18002e126  jz      loc_18002E24B
0x18002e12c  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x18002e133  lea     r8, [rsp+1F0h+Buffer]; lpBuffer
0x18002e138  mov     ebx, 40h ; '@'
0x18002e13d  mov     edx, 46Eh; uID
0x18002e142  mov     r9d, ebx; cchBufferMax
0x18002e145  call    cs:__imp_LoadStringW
0x18002e14c  nop     dword ptr [rax+rax+00h]
0x18002e151  test    eax, eax
0x18002e153  jnz     short loc_18002E177
0x18002e155  lea     r8, aTaskSchedulerS; "\"Task Scheduler Service\" ** FATAL ERR"...
0x18002e15c  mov     edx, ebx; unsigned __int64
0x18002e15e  lea     rcx, [rsp+1F0h+Buffer]; unsigned __int16 *
0x18002e163  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002e168  lea     rcx, [rsp+1F0h+Buffer]; lpBuffer
0x18002e16d  call    ?WriteLog@@YAXPEAG@Z; WriteLog(ushort *)
0x18002e172  jmp     loc_18002E24B
0x18002e177  mov     ebx, 80h
0x18002e17c  lea     rcx, [rbp+0F0h+DateStr]; void *
0x18002e180  mov     r8d, ebx; Size
0x18002e183  xor     edx, edx; Val
0x18002e185  call    memset_0
0x18002e18a  mov     r8d, ebx; Size
0x18002e18d  lea     rcx, [rbp+0F0h+TimeStr]; void *
0x18002e191  xor     edx, edx; Val
0x18002e193  call    memset_0
0x18002e198  lea     r8, [rbp+0F0h+TimeStr]; lpTimeStr
0x18002e19c  xor     ecx, ecx; lpTime
0x18002e19e  lea     rdx, [rbp+0F0h+DateStr]; lpDateStr
0x18002e1a2  call    ?GetDateTime@@YAHPEBU_SYSTEMTIME@@PEAG1@Z; GetDateTime(_SYSTEMTIME const *,ushort *,ushort *)
0x18002e1a7  test    eax, eax
0x18002e1a9  jz      loc_18002E24B
0x18002e1af  call    ?ComposeErrorMsg@@YAPEAGIKIH@Z; ComposeErrorMsg(uint,ulong,uint,int)
0x18002e1b4  mov     rbx, rax
0x18002e1b7  test    rax, rax
0x18002e1ba  jz      loc_18002E24B
0x18002e1c0  lea     rax, [rbp+0F0h+DateStr]
0x18002e1c4  mov     [rsp+1F0h+var_198], rbx
0x18002e1c9  mov     [rsp+1F0h+var_1A8], rax
0x18002e1ce  lea     rdx, [rsp+1F0h+Buffer]; lpSource
0x18002e1d3  lea     rax, [rbp+0F0h+TimeStr]
0x18002e1d7  mov     qword ptr [rsp+1F0h+var_1B0], 0
0x18002e1e0  mov     [rsp+1F0h+var_1A0], rax
0x18002e1e5  xor     r9d, r9d; dwLanguageId
0x18002e1e8  lea     rax, [rsp+1F0h+var_1A8]
0x18002e1ed  xor     r8d, r8d; dwMessageId
0x18002e1f0  mov     [rsp+1F0h+Arguments], rax; Arguments
0x18002e1f5  mov     ecx, 2500h; dwFlags
0x18002e1fa  lea     rax, [rsp+1F0h+var_1B0]
0x18002e1ff  mov     [rsp+1F0h+nSize], 1; nSize
0x18002e207  mov     [rsp+1F0h+lpBuffer], rax; lpBuffer
0x18002e20c  call    cs:__imp_FormatMessageW
0x18002e213  nop     dword ptr [rax+rax+00h]
0x18002e218  test    eax, eax
0x18002e21a  jnz     short loc_18002E221
0x18002e21c  mov     rcx, rbx
0x18002e21f  jmp     short loc_18002E23F
0x18002e221  mov     rcx, qword ptr [rsp+1F0h+var_1B0]; lpBuffer
0x18002e226  call    ?WriteLog@@YAXPEAG@Z; WriteLog(ushort *)
0x18002e22b  mov     rcx, rbx; hMem
0x18002e22e  call    cs:__imp_LocalFree
0x18002e235  nop     dword ptr [rax+rax+00h]
0x18002e23a  mov     rcx, qword ptr [rsp+1F0h+var_1B0]; hMem
0x18002e23f  call    cs:__imp_LocalFree
0x18002e246  nop     dword ptr [rax+rax+00h]
0x18002e24b  mov     rcx, [rbp+0F0h+var_10]
0x18002e252  xor     rcx, rsp; StackCookie
0x18002e255  call    __security_check_cookie
0x18002e25a  mov     rbx, [rsp+1F0h+arg_0]
0x18002e262  add     rsp, 1F0h
0x18002e269  pop     rbp
0x18002e26a  retn
```
