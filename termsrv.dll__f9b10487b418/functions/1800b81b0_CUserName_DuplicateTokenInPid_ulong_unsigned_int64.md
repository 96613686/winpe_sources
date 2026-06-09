# CUserName::DuplicateTokenInPid(ulong,unsigned __int64 *)

- ea: `0x1800b81b0`
- end: `0x1800b82c2`
- name: `?DuplicateTokenInPid@CUserName@@UEAAJKPEA_K@Z`
- size: `274`
- prototype: `int(CUserName *__hidden this, unsigned int, unsigned __int64 *)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18000a210`
- `0x1800148d0`
- `0x1800152a4`
- `0x1800b81b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b821f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b821f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800b826c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800b826c`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1800b8296`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1800b8296`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800b8202`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800b8202`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1800b825d`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1800b825d`

## string_xrefs

- `0x1800b81df`: `No token`

## pseudocode

```c
__int64 __fastcall CUserName::DuplicateTokenInPid(CUserName *this, DWORD a2, HANDLE *a3)
{
  bool v3; // zf
  unsigned int v6; // ebx
  HANDLE v7; // rax
  HANDLE v8; // rbx
  signed int LastError; // eax
  HANDLE v10; // rdi
  HANDLE CurrentProcess; // rax
  HANDLE hTargetProcessHandle; // [rsp+50h] [rbp+8h] BYREF
  HANDLE hSourceHandle; // [rsp+60h] [rbp+18h] BYREF

  v3 = (*((_BYTE *)this + 1600) & 1) == 0;
  hSourceHandle = 0;
  hTargetProcessHandle = 0;
  if ( v3 )
  {
    _DbgPrintMessage(8, "No token");
    v6 = -2147023888;
  }
  else
  {
    v7 = OpenProcess(0x40u, 0, a2);
    SmartHANDLE::operator=(&hTargetProcessHandle, v7);
    v8 = hTargetProcessHandle;
    if ( hTargetProcessHandle
      && DuplicateTokenEx(*((HANDLE *)this + 199), 0x2000000u, 0, SecurityImpersonation, TokenPrimary, &hSourceHandle)
      && (v10 = hSourceHandle,
          CurrentProcess = GetCurrentProcess(),
          DuplicateHandle(CurrentProcess, v10, v8, a3, 0, 0, 3u)) )
    {
      v6 = 0;
    }
    else
    {
      LastError = GetLastError();
      v6 = LastError;
      if ( LastError > 0 )
        v6 = (unsigned __int16)LastError | 0x80070000;
    }
  }
  SmartHANDLE::~SmartHANDLE((SmartHANDLE *)&hTargetProcessHandle);
  return v6;
}

```

## disassembly

```asm
0x1800b81b0  mov     rax, rsp
0x1800b81b3  mov     [rax+10h], rbx
0x1800b81b7  mov     [rax+20h], rsi
0x1800b81bb  push    rdi
0x1800b81bc  sub     rsp, 40h
0x1800b81c0  test    byte ptr [rcx+640h], 1
0x1800b81c7  mov     rsi, r8
0x1800b81ca  mov     rdi, rcx
0x1800b81cd  mov     qword ptr [rax+18h], 0
0x1800b81d5  mov     qword ptr [rax+8], 0
0x1800b81dd  jnz     short loc_1800B81FA
0x1800b81df  lea     rdx, aNoToken; "No token"
0x1800b81e6  mov     ecx, 8; int
0x1800b81eb  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800b81f0  mov     ebx, 800703F0h
0x1800b81f5  jmp     loc_1800B82A6
0x1800b81fa  mov     r8d, edx; dwProcessId
0x1800b81fd  xor     edx, edx; bInheritHandle
0x1800b81ff  lea     ecx, [rdx+40h]; dwDesiredAccess
0x1800b8202  call    cs:__imp_OpenProcess
0x1800b8208  mov     rdx, rax
0x1800b820b  lea     rcx, [rsp+48h+hTargetProcessHandle]
0x1800b8210  call    ??4SmartHANDLE@@QEAAXPEAX@Z; SmartHANDLE::operator=(void *)
0x1800b8215  mov     rbx, [rsp+48h+hTargetProcessHandle]
0x1800b821a  test    rbx, rbx
0x1800b821d  jnz     short loc_1800B8236
0x1800b821f  call    cs:__imp_GetLastError
0x1800b8225  mov     ebx, eax
0x1800b8227  test    eax, eax
0x1800b8229  jle     short loc_1800B82A6
0x1800b822b  movzx   ebx, ax
0x1800b822e  or      ebx, 80070000h
0x1800b8234  jmp     short loc_1800B82A6
0x1800b8236  mov     rcx, [rdi+638h]; hExistingToken
0x1800b823d  lea     rax, [rsp+48h+hSourceHandle]
0x1800b8242  mov     [rsp+48h+phNewToken], rax; phNewToken
0x1800b8247  mov     r9d, 2; ImpersonationLevel
0x1800b824d  xor     r8d, r8d; lpTokenAttributes
0x1800b8250  mov     [rsp+48h+TokenType], 1; TokenType
0x1800b8258  mov     edx, 2000000h; dwDesiredAccess
0x1800b825d  call    cs:__imp_DuplicateTokenEx
0x1800b8263  test    eax, eax
0x1800b8265  jz      short loc_1800B821F
0x1800b8267  mov     rdi, [rsp+48h+hSourceHandle]
0x1800b826c  call    cs:__imp_GetCurrentProcess
0x1800b8272  mov     [rsp+48h+dwOptions], 3; dwOptions
0x1800b827a  mov     r9, rsi; lpTargetHandle
0x1800b827d  mov     rcx, rax; hSourceProcessHandle
0x1800b8280  mov     dword ptr [rsp+48h+phNewToken], 0; bInheritHandle
0x1800b8288  mov     r8, rbx; hTargetProcessHandle
0x1800b828b  mov     [rsp+48h+TokenType], 0; dwDesiredAccess
0x1800b8293  mov     rdx, rdi; hSourceHandle
0x1800b8296  call    cs:__imp_DuplicateHandle
0x1800b829c  test    eax, eax
0x1800b829e  jz      loc_1800B821F
0x1800b82a4  xor     ebx, ebx
0x1800b82a6  lea     rcx, [rsp+48h+hTargetProcessHandle]; this
0x1800b82ab  call    ??1SmartHANDLE@@QEAA@XZ; SmartHANDLE::~SmartHANDLE(void)
0x1800b82b0  mov     rsi, [rsp+48h+arg_18]
0x1800b82b5  mov     eax, ebx
0x1800b82b7  mov     rbx, [rsp+48h+arg_8]
0x1800b82bc  add     rsp, 40h
0x1800b82c0  pop     rdi
0x1800b82c1  retn
```
