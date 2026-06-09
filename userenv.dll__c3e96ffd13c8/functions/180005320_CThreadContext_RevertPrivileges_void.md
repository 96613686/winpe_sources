# CThreadContext::RevertPrivileges(void)

- ea: `0x180005320`
- end: `0x1800053bc`
- name: `?RevertPrivileges@CThreadContext@@QEAAJXZ`
- size: `156`
- prototype: `__int64 __fastcall(CThreadContext *__hidden this)`
- caller_count: `5`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180004938`
- `0x18000542c`
- `0x1800059a4`
- `0x180005de0`
- `0x1800067b0`

## callees

- `0x180005320`
- `0x1800053c4`
- `0x1800053f0`
- `0x180005980`

## import_xrefs

- `ntdll!RtlAdjustPrivilege` at `0x18000537b`
- `ntdll!RtlAdjustPrivilege` at `0x18000537b`

## pseudocode

```c
__int64 __fastcall CThreadContext::RevertPrivileges(CThreadContext *this)
{
  int v1; // eax
  unsigned int v2; // esi
  __int64 v5; // rdi
  NTSTATUS v6; // eax
  void *v7; // rcx
  unsigned __int8 OldValue; // [rsp+30h] [rbp+8h] BYREF

  v1 = *((_DWORD *)this + 6);
  v2 = 0;
  OldValue = 0;
  if ( v1 )
  {
    v5 = 0;
    do
    {
      if ( *(_DWORD *)(*((_QWORD *)this + 5) + 4 * v5) )
      {
        v6 = RtlAdjustPrivilege(*(_DWORD *)(*((_QWORD *)this + 4) + 4 * v5), 0, 1u, &OldValue);
        v2 = ResultFromWin32FromStatus(v6);
      }
      v5 = (unsigned int)(v5 + 1);
    }
    while ( (unsigned int)v5 < *((_DWORD *)this + 6) );
    ResultFromHeapFree(*((void **)this + 4));
    v7 = (void *)*((_QWORD *)this + 5);
    *((_QWORD *)this + 4) = 0;
    ResultFromHeapFree(v7);
    *((_QWORD *)this + 5) = 0;
    *((_DWORD *)this + 6) = 0;
  }
  CThreadContext::RevertToSelf(this);
  return v2;
}

```

## disassembly

```asm
0x180005320  mov     [rsp+arg_8], rbx
0x180005325  mov     [rsp+arg_10], rsi
0x18000532a  push    rdi
0x18000532b  sub     rsp, 20h
0x18000532f  mov     eax, [rcx+18h]
0x180005332  xor     esi, esi
0x180005334  mov     [rsp+28h+OldValue], 0
0x180005339  mov     rbx, rcx
0x18000533c  test    eax, eax
0x18000533e  jnz     short loc_18000535A
0x180005340  mov     rcx, rbx; this
0x180005343  call    ?RevertToSelf@CThreadContext@@QEAAXXZ; CThreadContext::RevertToSelf(void)
0x180005348  mov     rbx, [rsp+28h+arg_8]
0x18000534d  mov     eax, esi
0x18000534f  mov     rsi, [rsp+28h+arg_10]
0x180005354  add     rsp, 20h
0x180005358  pop     rdi
0x180005359  retn
0x18000535a  xor     edi, edi
0x18000535c  test    eax, eax
0x18000535e  jz      short loc_180005391
0x180005360  mov     rax, [rbx+28h]
0x180005364  cmp     dword ptr [rax+rdi*4], 0
0x180005368  jz      short loc_18000538A
0x18000536a  mov     rcx, [rbx+20h]
0x18000536e  lea     r9, [rsp+28h+OldValue]; OldValue
0x180005373  mov     r8b, 1; ForThread
0x180005376  xor     edx, edx; NewValue
0x180005378  mov     ecx, [rcx+rdi*4]; Privilege
0x18000537b  call    cs:__imp_RtlAdjustPrivilege
0x180005381  mov     ecx, eax; int
0x180005383  call    ?ResultFromWin32FromStatus@@YAJJ@Z; ResultFromWin32FromStatus(long)
0x180005388  mov     esi, eax
0x18000538a  inc     edi
0x18000538c  cmp     edi, [rbx+18h]
0x18000538f  jb      short loc_180005360
0x180005391  mov     rcx, [rbx+20h]; lpMem
0x180005395  call    ?ResultFromHeapFree@@YAJPEAX@Z; ResultFromHeapFree(void *)
0x18000539a  mov     rcx, [rbx+28h]; lpMem
0x18000539e  mov     qword ptr [rbx+20h], 0
0x1800053a6  call    ?ResultFromHeapFree@@YAJPEAX@Z; ResultFromHeapFree(void *)
0x1800053ab  mov     qword ptr [rbx+28h], 0
0x1800053b3  mov     dword ptr [rbx+18h], 0
0x1800053ba  jmp     short loc_180005340
```
