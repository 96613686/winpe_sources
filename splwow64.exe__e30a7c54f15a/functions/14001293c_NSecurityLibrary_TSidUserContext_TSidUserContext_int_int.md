# NSecurityLibrary::TSidUserContext::TSidUserContext(int,int)

- ea: `0x14001293c`
- end: `0x140012a18`
- name: `??0TSidUserContext@NSecurityLibrary@@QEAA@HH@Z`
- size: `220`
- prototype: `__int64 __fastcall(NSecurityLibrary::TSidUserContext *__hidden this, int, int)`
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140006f98`
- `0x14000805c`
- `0x14000fae0`

## callees

- `0x14001293c`
- `0x140012bd4`
- `0x140012c80`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1400129a2`
- `KERNEL32!GetLastError` at `0x1400129a2`
- `KERNEL32!GetCurrentProcess` at `0x1400129af`
- `KERNEL32!GetCurrentProcess` at `0x1400129af`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x14001297b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x14001297b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x140012990`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x140012990`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1400129c0`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1400129c0`

## pseudocode

```c
NSecurityLibrary::TSidUserContext *__fastcall NSecurityLibrary::TSidUserContext::TSidUserContext(
        NSecurityLibrary::TSidUserContext *this)
{
  void **v2; // rdi
  HANDLE CurrentThread; // rax
  BOOL v4; // eax
  NCoreLibrary *v5; // rcx
  HANDLE CurrentProcess; // rax
  int LastErrorAsHResult; // eax

  *(_QWORD *)this = &NSecurityLibrary::TUserContext::`vftable';
  v2 = (void **)((char *)this + 16);
  *((_DWORD *)this + 2) = 1685222261;
  *((_QWORD *)this + 2) = 0;
  *((_DWORD *)this + 6) = -2147467259;
  *(_QWORD *)((char *)this + 28) = 4;
  *((_DWORD *)this + 9) = 0;
  CurrentThread = GetCurrentThread();
  v4 = OpenThreadToken(CurrentThread, 8u, 1, v2);
  v5 = (NCoreLibrary *)*((unsigned int *)this + 7);
  if ( v4 )
  {
    *((_DWORD *)this + 7) = (unsigned int)v5 & 0xFFFFFFFB;
  }
  else if ( ((unsigned __int8)v5 & 4) == 0
         || GetLastError() != 1008
         || (CurrentProcess = GetCurrentProcess(), !OpenProcessToken(CurrentProcess, 8u, v2)) )
  {
    LastErrorAsHResult = NCoreLibrary::GetLastErrorAsHResult(v5);
    goto LABEL_8;
  }
  LastErrorAsHResult = 0;
LABEL_8:
  *((_DWORD *)this + 10) = 1684302195;
  *(_QWORD *)this = &NSecurityLibrary::TSidUserContext::`vftable';
  *((_QWORD *)this + 6) = 0;
  *((_DWORD *)this + 6) = LastErrorAsHResult;
  *((_DWORD *)this + 14) = LastErrorAsHResult;
  if ( LastErrorAsHResult >= 0 )
    *((_DWORD *)this + 14) = NSecurityLibrary::TSidUserContext::Initialize(*v2, (struct _TOKEN_USER **)this + 6);
  return this;
}

```

## disassembly

```asm
0x14001293c  mov     [rsp+arg_0], rbx
0x140012941  push    rdi
0x140012942  sub     rsp, 20h
0x140012946  lea     rax, ??_7TUserContext@NSecurityLibrary@@6B@; const NSecurityLibrary::TUserContext::`vftable'
0x14001294d  mov     rbx, rcx
0x140012950  mov     [rcx], rax
0x140012953  lea     rdi, [rcx+10h]
0x140012957  mov     dword ptr [rcx+8], 64727375h
0x14001295e  mov     qword ptr [rdi], 0
0x140012965  mov     dword ptr [rcx+18h], 80004005h
0x14001296c  mov     qword ptr [rcx+1Ch], 4
0x140012974  mov     dword ptr [rcx+24h], 0
0x14001297b  call    cs:__imp_GetCurrentThread
0x140012981  mov     edx, 8; DesiredAccess
0x140012986  mov     r9, rdi; TokenHandle
0x140012989  mov     rcx, rax; ThreadHandle
0x14001298c  lea     r8d, [rdx-7]; OpenAsSelf
0x140012990  call    cs:__imp_OpenThreadToken
0x140012996  mov     ecx, [rbx+1Ch]
0x140012999  test    eax, eax
0x14001299b  jnz     short loc_1400129D1
0x14001299d  test    cl, 4
0x1400129a0  jz      short loc_1400129CA
0x1400129a2  call    cs:__imp_GetLastError
0x1400129a8  cmp     eax, 3F0h
0x1400129ad  jnz     short loc_1400129CA
0x1400129af  call    cs:__imp_GetCurrentProcess
0x1400129b5  mov     r8, rdi; TokenHandle
0x1400129b8  mov     edx, 8; DesiredAccess
0x1400129bd  mov     rcx, rax; ProcessHandle
0x1400129c0  call    cs:__imp_OpenProcessToken
0x1400129c6  test    eax, eax
0x1400129c8  jnz     short loc_1400129D7
0x1400129ca  call    ?GetLastErrorAsHResult@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsHResult(void)
0x1400129cf  jmp     short loc_1400129D9
0x1400129d1  and     ecx, 0FFFFFFFBh
0x1400129d4  mov     [rbx+1Ch], ecx
0x1400129d7  xor     eax, eax
0x1400129d9  mov     dword ptr [rbx+28h], 64646973h
0x1400129e0  lea     rcx, ??_7TSidUserContext@NSecurityLibrary@@6B@; const NSecurityLibrary::TSidUserContext::`vftable'
0x1400129e7  mov     [rbx], rcx
0x1400129ea  lea     rdx, [rbx+30h]; struct _TOKEN_USER **
0x1400129ee  mov     qword ptr [rdx], 0
0x1400129f5  mov     [rbx+18h], eax
0x1400129f8  mov     [rbx+38h], eax
0x1400129fb  test    eax, eax
0x1400129fd  js      short loc_140012A0A
0x1400129ff  mov     rcx, [rdi]; TokenHandle
0x140012a02  call    ?Initialize@TSidUserContext@NSecurityLibrary@@CAJPEAXPEAPEAU_TOKEN_USER@@@Z; NSecurityLibrary::TSidUserContext::Initialize(void *,_TOKEN_USER * *)
0x140012a07  mov     [rbx+38h], eax
0x140012a0a  mov     rax, rbx
0x140012a0d  mov     rbx, [rsp+28h+arg_0]
0x140012a12  add     rsp, 20h
0x140012a16  pop     rdi
0x140012a17  retn
```
