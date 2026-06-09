# CAutoRevertToSelf::~CAutoRevertToSelf(void)

- ea: `0x18001365c`
- end: `0x1800136d7`
- name: `??1CAutoRevertToSelf@@QEAA@XZ`
- size: `123`
- prototype: `void __fastcall(CAutoRevertToSelf *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x180015e24`

## callees

- `0x1800039f0`
- `0x18001365c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013683`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013683`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180013679`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180013679`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800136a1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800136c6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800136a1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800136c6`

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
0x18001365c  mov     [rsp+arg_8], rbx
0x180013661  push    rdi
0x180013662  sub     rsp, 20h
0x180013666  cmp     dword ptr [rcx], 0
0x180013669  mov     rdi, rcx
0x18001366c  jz      short loc_1800136BD
0x18001366e  mov     rdx, [rcx+8]; Token
0x180013672  test    rdx, rdx
0x180013675  jz      short loc_1800136BD
0x180013677  xor     ecx, ecx; Thread
0x180013679  call    cs:__imp_SetThreadToken
0x18001367f  test    eax, eax
0x180013681  jnz     short loc_1800136BD
0x180013683  call    cs:__imp_GetLastError
0x180013689  mov     ebx, eax
0x18001368b  test    eax, eax
0x18001368d  jle     short loc_180013698
0x18001368f  movzx   ebx, ax
0x180013692  or      ebx, 80070000h
0x180013698  mov     rcx, [rdi+8]; hObject
0x18001369c  test    rcx, rcx
0x18001369f  jz      short loc_1800136A7
0x1800136a1  call    cs:__imp_CloseHandle
0x1800136a7  lea     rdx, _TI1J; pThrowInfo
0x1800136ae  mov     [rsp+28h+pExceptionObject], ebx
0x1800136b2  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x1800136b7  call    _CxxThrowException_0
0x1800136bd  mov     rcx, [rdi+8]; hObject
0x1800136c1  test    rcx, rcx
0x1800136c4  jz      short loc_1800136CC
0x1800136c6  call    cs:__imp_CloseHandle
0x1800136cc  mov     rbx, [rsp+28h+arg_8]
0x1800136d1  add     rsp, 20h
0x1800136d5  pop     rdi
0x1800136d6  retn
```
