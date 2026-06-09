# CThreadContext::RevertPrivileges(void)

- ea: `0x180005a48`
- end: `0x180005aee`
- name: `?RevertPrivileges@CThreadContext@@QEAAJXZ`
- size: `166`
- prototype: `__int64 __fastcall(CThreadContext *__hidden this)`
- caller_count: `5`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180004f48`
- `0x180005b78`
- `0x180006160`
- `0x1800065d8`
- `0x180006ce0`

## callees

- `0x180005a48`
- `0x180005af4`
- `0x180005b30`
- `0x180006138`

## import_xrefs

- `ntdll!RtlAdjustPrivilege` at `0x180005aa4`
- `ntdll!RtlAdjustPrivilege` at `0x180005aa4`

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
0x180005a48  mov     [rsp+arg_8], rbx
0x180005a4d  mov     [rsp+arg_10], rsi
0x180005a52  push    rdi
0x180005a53  sub     rsp, 20h
0x180005a57  mov     eax, [rcx+18h]
0x180005a5a  xor     esi, esi
0x180005a5c  mov     [rsp+28h+OldValue], 0
0x180005a61  mov     rbx, rcx
0x180005a64  test    eax, eax
0x180005a66  jnz     short loc_180005A83
0x180005a68  mov     rcx, rbx; this
0x180005a6b  call    ?RevertToSelf@CThreadContext@@QEAAXXZ; CThreadContext::RevertToSelf(void)
0x180005a70  mov     rbx, [rsp+28h+arg_8]
0x180005a75  mov     eax, esi
0x180005a77  mov     rsi, [rsp+28h+arg_10]
0x180005a7c  add     rsp, 20h
0x180005a80  pop     rdi
0x180005a81  retn
0x180005a83  xor     edi, edi
0x180005a85  test    eax, eax
0x180005a87  jz      short loc_180005AC0
0x180005a89  mov     rax, [rbx+28h]
0x180005a8d  cmp     dword ptr [rax+rdi*4], 0
0x180005a91  jz      short loc_180005AB9
0x180005a93  mov     rcx, [rbx+20h]
0x180005a97  lea     r9, [rsp+28h+OldValue]; OldValue
0x180005a9c  mov     r8b, 1; ForThread
0x180005a9f  xor     edx, edx; NewValue
0x180005aa1  mov     ecx, [rcx+rdi*4]; Privilege
0x180005aa4  call    cs:__imp_RtlAdjustPrivilege
0x180005aab  nop     dword ptr [rax+rax+00h]
0x180005ab0  mov     ecx, eax; int
0x180005ab2  call    ?ResultFromWin32FromStatus@@YAJJ@Z; ResultFromWin32FromStatus(long)
0x180005ab7  mov     esi, eax
0x180005ab9  inc     edi
0x180005abb  cmp     edi, [rbx+18h]
0x180005abe  jb      short loc_180005A89
0x180005ac0  mov     rcx, [rbx+20h]; lpMem
0x180005ac4  call    ?ResultFromHeapFree@@YAJPEAX@Z; ResultFromHeapFree(void *)
0x180005ac9  mov     rcx, [rbx+28h]; lpMem
0x180005acd  mov     qword ptr [rbx+20h], 0
0x180005ad5  call    ?ResultFromHeapFree@@YAJPEAX@Z; ResultFromHeapFree(void *)
0x180005ada  mov     qword ptr [rbx+28h], 0
0x180005ae2  mov     dword ptr [rbx+18h], 0
0x180005ae9  jmp     loc_180005A68
```
