# HTTP_LOG_PIPE_CLIENT::ConnectToPipe(void)

- ea: `0x180009148`
- end: `0x180009214`
- name: `?ConnectToPipe@HTTP_LOG_PIPE_CLIENT@@QEAAJXZ`
- size: `204`
- prototype: `__int64 __fastcall(HTTP_LOG_PIPE_CLIENT *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000b964`

## callees

- `0x180009148`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800091c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800091c6`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800091bb`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800091bb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800091fc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800091fc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180009164`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180009164`
- `iisutil!?CreateIpmMessagePipe@IPM2_MESSAGE_PIPE@@SAJPEAVIPM2_MESSAGE_ACCEPTOR@@PEBGHPEAU_SECURITY_ATTRIBUTES@@PEAPEAV1@@Z` at `0x1800091a3`
- `iisutil!?CreateIpmMessagePipe@IPM2_MESSAGE_PIPE@@SAJPEAVIPM2_MESSAGE_ACCEPTOR@@PEBGHPEAU_SECURITY_ATTRIBUTES@@PEAPEAV1@@Z` at `0x1800091a3`

## pseudocode

```c
__int64 __fastcall HTTP_LOG_PIPE_CLIENT::ConnectToPipe(HTTP_LOG_PIPE_CLIENT *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rsi
  signed int IpmMessagePipe; // ebx
  DWORD v4; // eax
  signed int LastError; // eax

  v1 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 80352);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 80352));
  if ( *((_QWORD *)this + 42) )
  {
    IpmMessagePipe = -2147418113;
  }
  else
  {
    IpmMessagePipe = IPM2_MESSAGE_PIPE::CreateIpmMessagePipe(
                       (struct IPM2_MESSAGE_ACCEPTOR *)(((unsigned __int64)this + 128) & -(__int64)(this != 0)),
                       *((const unsigned __int16 **)this + 39),
                       0,
                       0,
                       (struct IPM2_MESSAGE_PIPE **)this + 42);
    if ( IpmMessagePipe >= 0 )
    {
      v4 = WaitForSingleObject(*((HANDLE *)this + 24), 0xC350u);
      if ( v4 == -1 )
      {
        LastError = GetLastError();
        IpmMessagePipe = LastError;
        if ( LastError > 0 )
          IpmMessagePipe = (unsigned __int16)LastError | 0x80070000;
      }
      else if ( v4 == 258 )
      {
        IpmMessagePipe = -2147024638;
      }
      else if ( *((_DWORD *)this + 40) > 1u )
      {
        IpmMessagePipe = 1;
      }
    }
  }
  LeaveCriticalSection(v1);
  return (unsigned int)IpmMessagePipe;
}

```

## disassembly

```asm
0x180009148  mov     [rsp+arg_0], rbx
0x18000914d  mov     [rsp+arg_8], rsi
0x180009152  push    rdi
0x180009153  sub     rsp, 30h
0x180009157  lea     rsi, [rcx+139E0h]
0x18000915e  mov     rdi, rcx
0x180009161  mov     rcx, rsi; lpCriticalSection
0x180009164  call    cs:__imp_EnterCriticalSection
0x18000916a  lea     r8, [rdi+150h]
0x180009171  cmp     qword ptr [r8], 0
0x180009175  jz      short loc_18000917E
0x180009177  mov     ebx, 8000FFFFh
0x18000917c  jmp     short loc_1800091F9
0x18000917e  lea     rdx, [rdi+80h]
0x180009185  mov     [rsp+38h+var_18], r8
0x18000918a  mov     rax, rdi
0x18000918d  neg     rax
0x180009190  sbb     rcx, rcx
0x180009193  xor     r9d, r9d
0x180009196  and     rcx, rdx
0x180009199  xor     r8d, r8d
0x18000919c  mov     rdx, [rdi+138h]
0x1800091a3  call    cs:__imp_?CreateIpmMessagePipe@IPM2_MESSAGE_PIPE@@SAJPEAVIPM2_MESSAGE_ACCEPTOR@@PEBGHPEAU_SECURITY_ATTRIBUTES@@PEAPEAV1@@Z; IPM2_MESSAGE_PIPE::CreateIpmMessagePipe(IPM2_MESSAGE_ACCEPTOR *,ushort const *,int,_SECURITY_ATTRIBUTES *,IPM2_MESSAGE_PIPE * *)
0x1800091a9  mov     ebx, eax
0x1800091ab  test    eax, eax
0x1800091ad  js      short loc_1800091F9
0x1800091af  mov     rcx, [rdi+0C0h]; hHandle
0x1800091b6  mov     edx, 0C350h; dwMilliseconds
0x1800091bb  call    cs:__imp_WaitForSingleObject
0x1800091c1  cmp     eax, 0FFFFFFFFh
0x1800091c4  jnz     short loc_1800091DD
0x1800091c6  call    cs:__imp_GetLastError
0x1800091cc  mov     ebx, eax
0x1800091ce  test    eax, eax
0x1800091d0  jle     short loc_1800091F9
0x1800091d2  movzx   ebx, ax
0x1800091d5  or      ebx, 80070000h
0x1800091db  jmp     short loc_1800091F9
0x1800091dd  cmp     eax, 102h
0x1800091e2  jnz     short loc_1800091EB
0x1800091e4  mov     ebx, 80070102h
0x1800091e9  jmp     short loc_1800091F9
0x1800091eb  mov     eax, 1
0x1800091f0  cmp     [rdi+0A0h], eax
0x1800091f6  cmova   ebx, eax
0x1800091f9  mov     rcx, rsi; lpCriticalSection
0x1800091fc  call    cs:__imp_LeaveCriticalSection
0x180009202  mov     rsi, [rsp+38h+arg_8]
0x180009207  mov     eax, ebx
0x180009209  mov     rbx, [rsp+38h+arg_0]
0x18000920e  add     rsp, 30h
0x180009212  pop     rdi
0x180009213  retn
```
