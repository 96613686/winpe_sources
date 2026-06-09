# ArgCheckFile(ushort const *,ulong)

- ea: `0x14003db38`
- end: `0x14003dd03`
- name: `?ArgCheckFile@@YAJPEBGK@Z`
- size: `459`
- prototype: `__int64 __fastcall(const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x14002ec00`

## callees

- `0x14003b908`
- `0x14003d4f0`
- `0x14003db38`
- `0x14003e014`

## import_xrefs

- `msvcrt!_wcslwr` at `0x14003dc98`
- `msvcrt!_wcslwr` at `0x14003dca1`
- `msvcrt!_wcslwr` at `0x14003dc98`
- `msvcrt!_wcslwr` at `0x14003dca1`
- `msvcrt!wcsstr` at `0x14003dcad`
- `msvcrt!wcsstr` at `0x14003dcad`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14003dcce`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14003dce7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14003dcce`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14003dce7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14003dc08`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14003dc36`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14003dcc0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14003dcd9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14003dc08`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14003dc36`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14003dcc0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14003dcd9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14003dc19`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14003dc45`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14003dc19`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14003dc45`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003db80`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003dbb8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003db80`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003dbb8`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14003db68`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14003db68`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003dcf0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003dcf0`

## pseudocode

```c
__int64 __fastcall ArgCheckFile(const unsigned __int16 *a1, int a2)
{
  signed int UserInput; // ebx
  HANDLE FileW; // rbp
  signed int LastError; // eax
  signed int v7; // eax
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v9; // rsi
  HANDLE v10; // rax
  WCHAR *v11; // rdi
  unsigned int v12; // edx
  int v13; // r8d
  int v14; // r9d
  HANDLE v15; // rax
  HANDLE v16; // rax
  int *dwCreationDisposition; // [rsp+20h] [rbp-48h]

  UserInput = 0;
  FileW = CreateFileW(a1, 0x80000000, 3u, 0, 3u, 0x80u, 0);
  if ( FileW == (HANDLE)-1LL )
  {
    if ( (a2 & 2) != 0 )
    {
      LastError = GetLastError();
      UserInput = LastError;
      if ( LastError )
      {
        if ( LastError > 0 )
          return (unsigned __int16)LastError | 0x80070000;
      }
      else
      {
        return (unsigned int)-2147467259;
      }
    }
    else if ( (a2 & 1) != 0 || !a2 )
    {
      v7 = GetLastError();
      UserInput = v7;
      if ( !v7 )
        return 0;
      if ( v7 > 0 )
        UserInput = (unsigned __int16)v7 | 0x80070000;
      if ( (_WORD)UserInput == 2 )
        return 0;
    }
  }
  else
  {
    if ( (a2 & 2) == 0 )
    {
      if ( a2 )
      {
        UserInput = (a2 & 1) != 0 ? 0x800700B7 : 0;
        if ( (a2 & 0x1000) != 0 )
        {
          ProcessHeap = GetProcessHeap();
          v9 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 0, 0x800u);
          if ( v9 )
          {
            *v9 = 0;
            v10 = GetProcessHeap();
            v11 = (WCHAR *)HeapAlloc(v10, 0, 0x20u);
            if ( v11 )
            {
              *v11 = 0;
              ArgPrintMessage(0, 0x3C8Cu, a1);
              UserInput = ArgGetUserInput(v9, v12, v13, v14, dwCreationDisposition);
              if ( UserInput >= 0 )
              {
                UserInput = ArgLoadString(0x3BC7u, v11, 0x10u);
                if ( UserInput >= 0 )
                {
                  _wcslwr(v9);
                  _wcslwr(v11);
                  UserInput = wcsstr(v9, v11) == 0 ? 0x800700B7 : 0;
                }
              }
            }
            else
            {
              UserInput = -2147024882;
            }
            v15 = GetProcessHeap();
            HeapFree(v15, 0, v9);
            if ( v11 )
            {
              v16 = GetProcessHeap();
              HeapFree(v16, 0, v11);
            }
          }
          else
          {
            UserInput = -2147024882;
          }
        }
      }
    }
    CloseHandle(FileW);
  }
  return (unsigned int)UserInput;
}

```

## disassembly

```asm
0x14003db38  push    rbx
0x14003db3a  push    rbp
0x14003db3b  push    rsi
0x14003db3c  push    rdi
0x14003db3d  push    r14
0x14003db3f  sub     rsp, 40h
0x14003db43  xor     ebx, ebx
0x14003db45  mov     edi, edx
0x14003db47  mov     [rsp+68h+hTemplateFile], rbx; hTemplateFile
0x14003db4c  xor     r9d, r9d; lpSecurityAttributes
0x14003db4f  mov     [rsp+68h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x14003db57  mov     edx, 80000000h; dwDesiredAccess
0x14003db5c  mov     r14, rcx
0x14003db5f  lea     r8d, [rbx+3]; dwShareMode
0x14003db63  mov     dword ptr [rsp+68h+dwCreationDisposition], r8d; int *
0x14003db68  call    cs:__imp_CreateFileW
0x14003db6e  mov     rbp, rax
0x14003db71  mov     eax, edi
0x14003db73  and     eax, 2
0x14003db76  cmp     rbp, 0FFFFFFFFFFFFFFFFh
0x14003db7a  jnz     short loc_14003DBE0
0x14003db7c  test    eax, eax
0x14003db7e  jz      short loc_14003DBAA
0x14003db80  call    cs:__imp_GetLastError
0x14003db86  mov     ebx, eax
0x14003db88  test    eax, eax
0x14003db8a  jz      short loc_14003DBA0
0x14003db8c  jle     loc_14003DCF6
0x14003db92  movzx   ebx, ax
0x14003db95  or      ebx, 80070000h
0x14003db9b  jmp     loc_14003DCF6
0x14003dba0  mov     ebx, 80004005h
0x14003dba5  jmp     loc_14003DCF6
0x14003dbaa  test    dil, 1
0x14003dbae  jnz     short loc_14003DBB8
0x14003dbb0  test    edi, edi
0x14003dbb2  jnz     loc_14003DCF6
0x14003dbb8  call    cs:__imp_GetLastError
0x14003dbbe  mov     ebx, eax
0x14003dbc0  test    eax, eax
0x14003dbc2  jz      short loc_14003DBD9
0x14003dbc4  jle     short loc_14003DBCF
0x14003dbc6  movzx   ebx, ax
0x14003dbc9  or      ebx, 80070000h
0x14003dbcf  cmp     bx, 2
0x14003dbd3  jnz     loc_14003DCF6
0x14003dbd9  xor     ebx, ebx
0x14003dbdb  jmp     loc_14003DCF6
0x14003dbe0  test    eax, eax
0x14003dbe2  jnz     loc_14003DCED
0x14003dbe8  test    edi, edi
0x14003dbea  jz      loc_14003DCED
0x14003dbf0  mov     eax, edi
0x14003dbf2  and     al, 1
0x14003dbf4  neg     al
0x14003dbf6  sbb     ebx, ebx
0x14003dbf8  and     ebx, 800700B7h
0x14003dbfe  bt      edi, 0Ch
0x14003dc02  jnb     loc_14003DCED
0x14003dc08  call    cs:__imp_GetProcessHeap
0x14003dc0e  xor     edx, edx; dwFlags
0x14003dc10  mov     r8d, 800h; dwBytes
0x14003dc16  mov     rcx, rax; hHeap
0x14003dc19  call    cs:__imp_HeapAlloc
0x14003dc1f  mov     rsi, rax
0x14003dc22  test    rax, rax
0x14003dc25  jnz     short loc_14003DC31
0x14003dc27  mov     ebx, 8007000Eh
0x14003dc2c  jmp     loc_14003DCED
0x14003dc31  xor     eax, eax
0x14003dc33  mov     [rsi], ax
0x14003dc36  call    cs:__imp_GetProcessHeap
0x14003dc3c  xor     edx, edx; dwFlags
0x14003dc3e  mov     rcx, rax; hHeap
0x14003dc41  lea     r8d, [rdx+20h]; dwBytes
0x14003dc45  call    cs:__imp_HeapAlloc
0x14003dc4b  mov     rdi, rax
0x14003dc4e  test    rax, rax
0x14003dc51  jnz     short loc_14003DC5A
0x14003dc53  mov     ebx, 8007000Eh
0x14003dc58  jmp     short loc_14003DCC0
0x14003dc5a  xor     eax, eax
0x14003dc5c  mov     r8, r14
0x14003dc5f  mov     edx, 3C8Ch; uID
0x14003dc64  mov     [rdi], ax
0x14003dc67  xor     ecx, ecx; unsigned int *
0x14003dc69  call    ?ArgPrintMessage@@YAJPEAKIZZ; ArgPrintMessage(ulong *,uint,...)
0x14003dc6e  mov     rcx, rsi; unsigned __int16 *
0x14003dc71  call    ?ArgGetUserInput@@YAJPEAGKHHPEAH@Z; ArgGetUserInput(ushort *,ulong,int,int,int *)
0x14003dc76  mov     ebx, eax
0x14003dc78  test    eax, eax
0x14003dc7a  js      short loc_14003DCC0
0x14003dc7c  mov     r8d, 10h; cchBufferMax
0x14003dc82  mov     rdx, rdi; lpBuffer
0x14003dc85  mov     ecx, 3BC7h; uID
0x14003dc8a  call    ?ArgLoadString@@YAJKPEAG_K@Z; ArgLoadString(ulong,ushort *,unsigned __int64)
0x14003dc8f  mov     ebx, eax
0x14003dc91  test    eax, eax
0x14003dc93  js      short loc_14003DCC0
0x14003dc95  mov     rcx, rsi; String
0x14003dc98  call    cs:__imp__wcslwr
0x14003dc9e  mov     rcx, rdi; String
0x14003dca1  call    cs:__imp__wcslwr
0x14003dca7  mov     rdx, rdi; SubStr
0x14003dcaa  mov     rcx, rsi; Str
0x14003dcad  call    cs:__imp_wcsstr
0x14003dcb3  neg     rax
0x14003dcb6  sbb     ebx, ebx
0x14003dcb8  not     ebx
0x14003dcba  and     ebx, 800700B7h
0x14003dcc0  call    cs:__imp_GetProcessHeap
0x14003dcc6  mov     r8, rsi; lpMem
0x14003dcc9  xor     edx, edx; dwFlags
0x14003dccb  mov     rcx, rax; hHeap
0x14003dcce  call    cs:__imp_HeapFree
0x14003dcd4  test    rdi, rdi
0x14003dcd7  jz      short loc_14003DCED
0x14003dcd9  call    cs:__imp_GetProcessHeap
0x14003dcdf  mov     r8, rdi; lpMem
0x14003dce2  xor     edx, edx; dwFlags
0x14003dce4  mov     rcx, rax; hHeap
0x14003dce7  call    cs:__imp_HeapFree
0x14003dced  mov     rcx, rbp; hObject
0x14003dcf0  call    cs:__imp_CloseHandle
0x14003dcf6  mov     eax, ebx
0x14003dcf8  add     rsp, 40h
0x14003dcfc  pop     r14
0x14003dcfe  pop     rdi
0x14003dcff  pop     rsi
0x14003dd00  pop     rbp
0x14003dd01  pop     rbx
0x14003dd02  retn
```
