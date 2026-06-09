# SxspDoesFileOrDirectoryExist(ulong,ushort const *,ulong &)

- ea: `0x180068838`
- end: `0x180068975`
- name: `?SxspDoesFileOrDirectoryExist@@YAHKPEBGAEAK@Z`
- size: `317`
- prototype: `int(unsigned int, const unsigned __int16 *, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x180068724`

## callees

- `0x18000a804`
- `0x18000df40`
- `0x18001c270`
- `0x18005d2b0`
- `0x18005d38c`
- `0x180068838`
- `0x18006a110`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800688f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800688f7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800688ba`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800688ba`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800688e6`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800688e6`

## pseudocode

```c
__int64 __fastcall SxspDoesFileOrDirectoryExist(int a1, const unsigned __int16 *a2, unsigned int *a3)
{
  const char *v6; // rcx
  DWORD FileAttributesW; // eax
  DWORD LastError; // eax
  unsigned int v9; // ebx
  int v11; // [rsp+20h] [rbp-40h] BYREF
  int v12; // [rsp+28h] [rbp-38h] BYREF
  __int64 v13; // [rsp+30h] [rbp-30h]
  __int64 *v14; // [rsp+38h] [rbp-28h]
  __int64 v15; // [rsp+40h] [rbp-20h]
  int v16; // [rsp+48h] [rbp-18h]
  int *v17; // [rsp+50h] [rbp-10h]

  v11 = 0;
  v14 = &qword_18007CAE0;
  v12 = 1;
  v17 = &v11;
  v13 = 0;
  v15 = 544438355;
  v16 = 64;
  CFrame::BaseEnter((CFrame *)&v12);
  *a3 = 3;
  if ( a2 )
  {
    if ( (a1 & 0xFFFFFFFD) == 0 )
    {
      FileAttributesW = GetFileAttributesW(a2);
      if ( FileAttributesW == -1 )
      {
        LastError = GetLastError();
        if ( ((LastError & 0xFFFFFFFC) != 0 || LastError == 1) && ((a1 & 2) == 0 || LastError != 53 && LastError != 67) )
        {
          CFnTracerWin32::MarkWin32Failure((CFnTracerWin32 *)&v12, LastError);
          FusionpTraceWin32LastErrorFailureOrigination((const struct _CALL_SITE_INFO *)off_18007CB60);
          goto LABEL_15;
        }
      }
      else
      {
        *a3 = ((FileAttributesW & 0x10) != 0) + 1;
      }
      v11 = 1;
      goto LABEL_15;
    }
    v16 = 72;
  }
  else
  {
    v16 = 71;
  }
  FusionpTraceParameterCheck(v6);
  SetLastError(0x57u);
  *v17 = 0;
LABEL_15:
  v9 = v11;
  CFnTracerWin32::~CFnTracerWin32((CFnTracerWin32 *)&v12);
  return v9;
}

```

## disassembly

```asm
0x180068838  mov     [rsp-18h+arg_0], rbx
0x18006883d  push    rbp
0x18006883e  push    rsi
0x18006883f  push    rdi
0x180068840  mov     rbp, rsp
0x180068843  sub     rsp, 60h
0x180068847  mov     rax, cs:__security_cookie
0x18006884e  xor     rax, rsp
0x180068851  mov     [rbp+var_8], rax
0x180068855  lea     rax, qword_18007CAE0
0x18006885c  mov     [rbp+var_40], 0
0x180068863  mov     [rbp+var_28], rax
0x180068867  mov     ebx, ecx
0x180068869  lea     rax, [rbp+var_40]
0x18006886d  mov     [rbp+var_38], 1
0x180068874  lea     rcx, [rbp+var_38]; this
0x180068878  mov     [rbp+var_10], rax
0x18006887c  mov     rdi, r8
0x18006887f  mov     [rbp+var_30], 0
0x180068887  mov     rsi, rdx
0x18006888a  mov     [rbp+var_20], 20737853h
0x180068892  mov     [rbp+var_18], 40h ; '@'
0x180068899  call    ?BaseEnter@CFrame@@QEAAXXZ; CFrame::BaseEnter(void)
0x18006889e  mov     dword ptr [rdi], 3
0x1800688a4  test    rsi, rsi
0x1800688a7  jnz     short loc_1800688D2
0x1800688a9  mov     [rbp+var_18], 47h ; 'G'
0x1800688b0  call    ?FusionpTraceParameterCheck@@YAXPEBD@Z; FusionpTraceParameterCheck(char const *)
0x1800688b5  mov     ecx, 57h ; 'W'; dwErrCode
0x1800688ba  call    cs:__imp_SetLastError
0x1800688c1  nop     dword ptr [rax+rax+00h]
0x1800688c6  mov     rax, [rbp+var_10]
0x1800688ca  mov     dword ptr [rax], 0
0x1800688d0  jmp     short loc_18006894A
0x1800688d2  test    ebx, 0FFFFFFFDh
0x1800688d8  jz      short loc_1800688E3
0x1800688da  mov     [rbp+var_18], 48h ; 'H'
0x1800688e1  jmp     short loc_1800688B0
0x1800688e3  mov     rcx, rsi; lpFileName
0x1800688e6  call    cs:__imp_GetFileAttributesW
0x1800688ed  nop     dword ptr [rax+rax+00h]
0x1800688f2  cmp     eax, 0FFFFFFFFh
0x1800688f5  jnz     short loc_180068937
0x1800688f7  call    cs:__imp_GetLastError
0x1800688fe  nop     dword ptr [rax+rax+00h]
0x180068903  test    eax, 0FFFFFFFCh
0x180068908  jnz     short loc_18006890F
0x18006890a  cmp     eax, 1
0x18006890d  jnz     short loc_180068943
0x18006890f  test    bl, 2
0x180068912  jz      short loc_18006891E
0x180068914  cmp     eax, 35h ; '5'
0x180068917  jz      short loc_180068943
0x180068919  cmp     eax, 43h ; 'C'
0x18006891c  jz      short loc_180068943
0x18006891e  mov     edx, eax; unsigned int
0x180068920  lea     rcx, [rbp+var_38]; this
0x180068924  call    ?MarkWin32Failure@CFnTracerWin32@@QEAAXK@Z; CFnTracerWin32::MarkWin32Failure(ulong)
0x180068929  lea     rcx, off_18007CB60; struct _CALL_SITE_INFO *
0x180068930  call    ?FusionpTraceWin32LastErrorFailureOrigination@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailureOrigination(_CALL_SITE_INFO const &)
0x180068935  jmp     short loc_18006894A
0x180068937  and     al, 10h
0x180068939  neg     al
0x18006893b  sbb     eax, eax
0x18006893d  neg     eax
0x18006893f  inc     eax
0x180068941  mov     [rdi], eax
0x180068943  mov     [rbp+var_40], 1
0x18006894a  mov     ebx, [rbp+var_40]
0x18006894d  lea     rcx, [rbp+var_38]; this
0x180068951  call    ??1CFnTracerWin32@@QEAA@XZ; CFnTracerWin32::~CFnTracerWin32(void)
0x180068956  mov     eax, ebx
0x180068958  mov     rcx, [rbp+var_8]
0x18006895c  xor     rcx, rsp; StackCookie
0x18006895f  call    __security_check_cookie
0x180068964  mov     rbx, [rsp+60h+arg_0]
0x18006896c  add     rsp, 60h
0x180068970  pop     rdi
0x180068971  pop     rsi
0x180068972  pop     rbp
0x180068973  retn
```
