# PacWorkerClient::FinalConstruct(void)

- ea: `0x1800c4830`
- end: `0x1800c495e`
- name: `?FinalConstruct@PacWorkerClient@@QEAAJXZ`
- size: `302`
- prototype: `__int64 __fastcall(PacWorkerClient *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800c3118`

## callees

- `0x18009136c`
- `0x1800c4830`
- `0x1800db6b0`
- `0x1800db704`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x1800c4873`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x1800c48c9`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x1800c4873`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x1800c48c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c4894`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c48ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c4894`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c48ea`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c4885`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c48db`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c4885`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c48db`

## pseudocode

```c
__int64 __fastcall PacWorkerClient::FinalConstruct(PacWorkerClient *this)
{
  HANDLE EventA; // rax
  void *v3; // rcx
  HANDLE v4; // rbx
  signed int v5; // eax
  signed int v6; // ebx
  HANDLE v7; // rax
  void *v8; // rcx
  HANDLE v9; // rbx
  signed int LastError; // eax
  __int64 v12; // [rsp+20h] [rbp-18h]

  HIDWORD(v12) = 0;
  if ( (xmmword_180107A60 & 0x20) != 0 )
    WPP_SF_q(1029, 17, WPP_7537b208fef33d19ae8f417444b45cbe_Traceguids);
  EventA = CreateEventA(0, 1, 0, 0);
  v3 = (void *)*((_QWORD *)this + 8);
  v4 = EventA;
  if ( v3 )
    CloseHandle(v3);
  *((_QWORD *)this + 8) = v4;
  if ( v4 )
  {
    v7 = CreateEventA(0, 1, 0, 0);
    v8 = (void *)*((_QWORD *)this + 9);
    v9 = v7;
    if ( v8 )
      CloseHandle(v8);
    *((_QWORD *)this + 9) = v9;
    if ( v9 )
    {
      v6 = PacWorkerClient::WorkerRegisterCallbacksServer();
      if ( v6 >= 0 )
        *((_DWORD *)this + 1) = 1;
      else
        HIDWORD(v12) = 254;
    }
    else
    {
      LastError = GetLastError();
      v6 = LastError;
      if ( LastError > 0 )
        v6 = (unsigned __int16)LastError | 0x80070000;
      HIDWORD(v12) = 248;
      if ( v6 >= 0 )
        v6 = -2147418113;
    }
  }
  else
  {
    v5 = GetLastError();
    v6 = v5;
    if ( v5 > 0 )
      v6 = (unsigned __int16)v5 | 0x80070000;
    HIDWORD(v12) = 242;
    if ( v6 >= 0 )
      v6 = -2147418113;
  }
  if ( (xmmword_180107A60 & 0x20) != 0 )
    WPP_SF_d(1029, 18, WPP_7537b208fef33d19ae8f417444b45cbe_Traceguids, (unsigned int)v6, v12);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800c4830  mov     [rsp+arg_8], rbx
0x1800c4835  push    rdi
0x1800c4836  sub     rsp, 30h
0x1800c483a  mov     rdi, rcx
0x1800c483d  mov     [rsp+38h+var_14], 0
0x1800c4845  test    byte ptr cs:xmmword_180107A60, 20h
0x1800c484c  jz      short loc_1800C4867
0x1800c484e  mov     edx, 11h
0x1800c4853  lea     r8, WPP_7537b208fef33d19ae8f417444b45cbe_Traceguids
0x1800c485a  mov     ecx, 405h
0x1800c485f  mov     r9, rdi
0x1800c4862  call    WPP_SF_q
0x1800c4867  xor     r9d, r9d; lpName
0x1800c486a  xor     r8d, r8d; bInitialState
0x1800c486d  xor     ecx, ecx; lpEventAttributes
0x1800c486f  lea     edx, [r9+1]; bManualReset
0x1800c4873  call    cs:__imp_CreateEventA
0x1800c4879  mov     rcx, [rdi+40h]; hObject
0x1800c487d  mov     rbx, rax
0x1800c4880  test    rcx, rcx
0x1800c4883  jz      short loc_1800C488B
0x1800c4885  call    cs:__imp_CloseHandle
0x1800c488b  mov     [rdi+40h], rbx
0x1800c488f  test    rbx, rbx
0x1800c4892  jnz     short loc_1800C48BD
0x1800c4894  call    cs:__imp_GetLastError
0x1800c489a  mov     ebx, eax
0x1800c489c  test    eax, eax
0x1800c489e  jle     short loc_1800C48A9
0x1800c48a0  movzx   ebx, ax
0x1800c48a3  or      ebx, 80070000h
0x1800c48a9  test    ebx, ebx
0x1800c48ab  mov     [rsp+38h+var_14], 0F2h
0x1800c48b3  mov     eax, 8000FFFFh
0x1800c48b8  cmovns  ebx, eax
0x1800c48bb  jmp     short loc_1800C492F
0x1800c48bd  xor     r9d, r9d; lpName
0x1800c48c0  xor     r8d, r8d; bInitialState
0x1800c48c3  xor     ecx, ecx; lpEventAttributes
0x1800c48c5  lea     edx, [r9+1]; bManualReset
0x1800c48c9  call    cs:__imp_CreateEventA
0x1800c48cf  mov     rcx, [rdi+48h]; hObject
0x1800c48d3  mov     rbx, rax
0x1800c48d6  test    rcx, rcx
0x1800c48d9  jz      short loc_1800C48E1
0x1800c48db  call    cs:__imp_CloseHandle
0x1800c48e1  mov     [rdi+48h], rbx
0x1800c48e5  test    rbx, rbx
0x1800c48e8  jnz     short loc_1800C4913
0x1800c48ea  call    cs:__imp_GetLastError
0x1800c48f0  mov     ebx, eax
0x1800c48f2  test    eax, eax
0x1800c48f4  jle     short loc_1800C48FF
0x1800c48f6  movzx   ebx, ax
0x1800c48f9  or      ebx, 80070000h
0x1800c48ff  test    ebx, ebx
0x1800c4901  mov     [rsp+38h+var_14], 0F8h
0x1800c4909  mov     eax, 8000FFFFh
0x1800c490e  cmovns  ebx, eax
0x1800c4911  jmp     short loc_1800C492F
0x1800c4913  call    ?WorkerRegisterCallbacksServer@PacWorkerClient@@SAJXZ; PacWorkerClient::WorkerRegisterCallbacksServer(void)
0x1800c4918  mov     ebx, eax
0x1800c491a  test    eax, eax
0x1800c491c  jns     short loc_1800C4928
0x1800c491e  mov     [rsp+38h+var_14], 0FEh
0x1800c4926  jmp     short loc_1800C492F
0x1800c4928  mov     dword ptr [rdi+4], 1
0x1800c492f  test    byte ptr cs:xmmword_180107A60, 20h
0x1800c4936  jz      short loc_1800C4951
0x1800c4938  mov     edx, 12h
0x1800c493d  lea     r8, WPP_7537b208fef33d19ae8f417444b45cbe_Traceguids
0x1800c4944  mov     ecx, 405h
0x1800c4949  mov     r9d, ebx
0x1800c494c  call    WPP_SF_d
0x1800c4951  mov     eax, ebx
0x1800c4953  mov     rbx, [rsp+38h+arg_8]
0x1800c4958  add     rsp, 30h
0x1800c495c  pop     rdi
0x1800c495d  retn
```
