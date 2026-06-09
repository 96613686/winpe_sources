# CAutoRevertToSelf::~CAutoRevertToSelf(void)

- ea: `0x180009e00`
- end: `0x180009e7b`
- name: `??1CAutoRevertToSelf@@QEAA@XZ`
- size: `123`
- prototype: `void __fastcall(CAutoRevertToSelf *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x18000a998`

## callees

- `0x1800033c0`
- `0x180009e00`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009e27`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009e27`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180009e1d`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180009e1d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009e45`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009e6a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009e45`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009e6a`

## pseudocode

```c
void __fastcall CAutoRevertToSelf::~CAutoRevertToSelf(CAutoRevertToSelf *this)
{
  void *v2; // rdx
  signed int LastError; // eax
  unsigned int v4; // ebx
  void *v5; // rcx
  void *v6; // rcx
  unsigned int pExceptionObject; // [rsp+30h] [rbp+8h] BYREF

  if ( *(_DWORD *)this )
  {
    v2 = (void *)*((_QWORD *)this + 1);
    if ( v2 )
    {
      if ( !SetThreadToken(0, v2) )
      {
        LastError = GetLastError();
        v4 = LastError;
        if ( LastError > 0 )
          v4 = (unsigned __int16)LastError | 0x80070000;
        v5 = (void *)*((_QWORD *)this + 1);
        if ( v5 )
          CloseHandle(v5);
        pExceptionObject = v4;
        throw (long *)&pExceptionObject;
      }
    }
  }
  v6 = (void *)*((_QWORD *)this + 1);
  if ( v6 )
    CloseHandle(v6);
}

```

## disassembly

```asm
0x180009e00  mov     [rsp+arg_8], rbx
0x180009e05  push    rdi
0x180009e06  sub     rsp, 20h
0x180009e0a  cmp     dword ptr [rcx], 0
0x180009e0d  mov     rdi, rcx
0x180009e10  jz      short loc_180009E61
0x180009e12  mov     rdx, [rcx+8]; Token
0x180009e16  test    rdx, rdx
0x180009e19  jz      short loc_180009E61
0x180009e1b  xor     ecx, ecx; Thread
0x180009e1d  call    cs:__imp_SetThreadToken
0x180009e23  test    eax, eax
0x180009e25  jnz     short loc_180009E61
0x180009e27  call    cs:__imp_GetLastError
0x180009e2d  mov     ebx, eax
0x180009e2f  test    eax, eax
0x180009e31  jle     short loc_180009E3C
0x180009e33  movzx   ebx, ax
0x180009e36  or      ebx, 80070000h
0x180009e3c  mov     rcx, [rdi+8]; hObject
0x180009e40  test    rcx, rcx
0x180009e43  jz      short loc_180009E4B
0x180009e45  call    cs:__imp_CloseHandle
0x180009e4b  lea     rdx, _TI1J; pThrowInfo
0x180009e52  mov     [rsp+28h+pExceptionObject], ebx
0x180009e56  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x180009e5b  call    _CxxThrowException_0
0x180009e61  mov     rcx, [rdi+8]; hObject
0x180009e65  test    rcx, rcx
0x180009e68  jz      short loc_180009E70
0x180009e6a  call    cs:__imp_CloseHandle
0x180009e70  mov     rbx, [rsp+28h+arg_8]
0x180009e75  add     rsp, 20h
0x180009e79  pop     rdi
0x180009e7a  retn
```
