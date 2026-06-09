# CUserName::DuplicateTokenInPid(ulong,unsigned __int64 *)

- ea: `0x1800bea00`
- end: `0x1800beb38`
- name: `?DuplicateTokenInPid@CUserName@@UEAAJKPEA_K@Z`
- size: `312`
- prototype: `int(CUserName *__hidden this, unsigned int, unsigned __int64 *)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180009940`
- `0x180015020`
- `0x180015c44`
- `0x1800bea00`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bea75`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bea75`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800bead5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800bead5`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1800beb05`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1800beb05`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800bea52`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800bea52`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1800beac0`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1800beac0`

## string_xrefs

- `0x1800bea2f`: `No token`

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
0x1800bea00  mov     rax, rsp
0x1800bea03  mov     [rax+10h], rbx
0x1800bea07  mov     [rax+20h], rsi
0x1800bea0b  push    rdi
0x1800bea0c  sub     rsp, 40h
0x1800bea10  test    byte ptr [rcx+640h], 1
0x1800bea17  mov     rsi, r8
0x1800bea1a  mov     rdi, rcx
0x1800bea1d  mov     qword ptr [rax+18h], 0
0x1800bea25  mov     qword ptr [rax+8], 0
0x1800bea2d  jnz     short loc_1800BEA4A
0x1800bea2f  lea     rdx, aNoToken; "No token"
0x1800bea36  mov     ecx, 8; int
0x1800bea3b  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800bea40  mov     ebx, 800703F0h
0x1800bea45  jmp     loc_1800BEB1B
0x1800bea4a  mov     r8d, edx; dwProcessId
0x1800bea4d  xor     edx, edx; bInheritHandle
0x1800bea4f  lea     ecx, [rdx+40h]; dwDesiredAccess
0x1800bea52  call    cs:__imp_OpenProcess
0x1800bea59  nop     dword ptr [rax+rax+00h]
0x1800bea5e  mov     rdx, rax
0x1800bea61  lea     rcx, [rsp+48h+hTargetProcessHandle]
0x1800bea66  call    ??4SmartHANDLE@@QEAAXPEAX@Z; SmartHANDLE::operator=(void *)
0x1800bea6b  mov     rbx, [rsp+48h+hTargetProcessHandle]
0x1800bea70  test    rbx, rbx
0x1800bea73  jnz     short loc_1800BEA99
0x1800bea75  call    cs:__imp_GetLastError
0x1800bea7c  nop     dword ptr [rax+rax+00h]
0x1800bea81  mov     ebx, eax
0x1800bea83  test    eax, eax
0x1800bea85  jle     loc_1800BEB1B
0x1800bea8b  movzx   ebx, ax
0x1800bea8e  or      ebx, 80070000h
0x1800bea94  jmp     loc_1800BEB1B
0x1800bea99  mov     rcx, [rdi+638h]; hExistingToken
0x1800beaa0  lea     rax, [rsp+48h+hSourceHandle]
0x1800beaa5  mov     [rsp+48h+phNewToken], rax; phNewToken
0x1800beaaa  mov     r9d, 2; ImpersonationLevel
0x1800beab0  xor     r8d, r8d; lpTokenAttributes
0x1800beab3  mov     [rsp+48h+TokenType], 1; TokenType
0x1800beabb  mov     edx, 2000000h; dwDesiredAccess
0x1800beac0  call    cs:__imp_DuplicateTokenEx
0x1800beac7  nop     dword ptr [rax+rax+00h]
0x1800beacc  test    eax, eax
0x1800beace  jz      short loc_1800BEA75
0x1800bead0  mov     rdi, [rsp+48h+hSourceHandle]
0x1800bead5  call    cs:__imp_GetCurrentProcess
0x1800beadc  nop     dword ptr [rax+rax+00h]
0x1800beae1  mov     [rsp+48h+dwOptions], 3; dwOptions
0x1800beae9  mov     r9, rsi; lpTargetHandle
0x1800beaec  mov     rcx, rax; hSourceProcessHandle
0x1800beaef  mov     dword ptr [rsp+48h+phNewToken], 0; bInheritHandle
0x1800beaf7  mov     r8, rbx; hTargetProcessHandle
0x1800beafa  mov     [rsp+48h+TokenType], 0; dwDesiredAccess
0x1800beb02  mov     rdx, rdi; hSourceHandle
0x1800beb05  call    cs:__imp_DuplicateHandle
0x1800beb0c  nop     dword ptr [rax+rax+00h]
0x1800beb11  test    eax, eax
0x1800beb13  jz      loc_1800BEA75
0x1800beb19  xor     ebx, ebx
0x1800beb1b  lea     rcx, [rsp+48h+hTargetProcessHandle]; this
0x1800beb20  call    ??1SmartHANDLE@@QEAA@XZ; SmartHANDLE::~SmartHANDLE(void)
0x1800beb25  mov     rsi, [rsp+48h+arg_18]
0x1800beb2a  mov     eax, ebx
0x1800beb2c  mov     rbx, [rsp+48h+arg_8]
0x1800beb31  add     rsp, 40h
0x1800beb35  pop     rdi
0x1800beb36  retn
```
