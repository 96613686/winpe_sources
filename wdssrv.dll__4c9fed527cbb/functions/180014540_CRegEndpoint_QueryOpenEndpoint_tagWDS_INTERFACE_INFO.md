# CRegEndpoint::QueryOpenEndpoint(tagWDS_INTERFACE_INFO *)

- ea: `0x180014540`
- end: `0x180014608`
- name: `?QueryOpenEndpoint@CRegEndpoint@@UEAAKPEAUtagWDS_INTERFACE_INFO@@@Z`
- size: `200`
- prototype: `unsigned int __fastcall(CRegEndpoint *__hidden this, struct tagWDS_INTERFACE_INFO *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180014540`
- `0x18001d010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18001459e`
- `KERNEL32!LeaveCriticalSection` at `0x1800145c1`
- `KERNEL32!LeaveCriticalSection` at `0x18001459e`
- `KERNEL32!LeaveCriticalSection` at `0x1800145c1`
- `KERNEL32!EnterCriticalSection` at `0x180014581`
- `KERNEL32!EnterCriticalSection` at `0x180014581`

## pseudocode

```c
__int64 __fastcall CRegEndpoint::QueryOpenEndpoint(CRegEndpoint *this, struct tagWDS_INTERFACE_INFO *a2)
{
  __int64 v2; // rsi
  unsigned int (__fastcall *v4)(__int64, char *, struct tagWDS_INTERFACE_INFO *); // rdi
  unsigned int v5; // ebx
  __int64 v6; // r15

  v2 = *((_QWORD *)this + 8);
  v4 = (unsigned int (__fastcall *)(__int64, char *, struct tagWDS_INTERFACE_INFO *))*((_QWORD *)this + 147);
  v5 = 0;
  v6 = *((_QWORD *)this + 148);
  EnterCriticalSection((LPCRITICAL_SECTION)(v2 + 200));
  if ( (unsigned int)(_InterlockedExchangeAdd((volatile signed __int32 *)(v2 + 32), 0) - 1) <= 1 )
  {
    if ( !v4 )
    {
      v4 = *(unsigned int (__fastcall **)(__int64, char *, struct tagWDS_INTERFACE_INFO *))(v2 + 88);
      v6 = *(_QWORD *)(v2 + 96);
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)(v2 + 200));
    if ( v4 )
      return v4(v6, (char *)this + 72, a2);
  }
  else
  {
    LeaveCriticalSection((LPCRITICAL_SECTION)(v2 + 200));
    return 5023;
  }
  return v5;
}

```

## disassembly

```asm
0x180014540  mov     rax, rsp
0x180014543  mov     [rax+8], rbx
0x180014547  mov     [rax+10h], rbp
0x18001454b  mov     [rax+18h], rsi
0x18001454f  mov     [rax+20h], rdi
0x180014553  push    r12
0x180014555  push    r14
0x180014557  push    r15
0x180014559  sub     rsp, 20h
0x18001455d  mov     rsi, [rcx+40h]
0x180014561  mov     r14, rcx
0x180014564  mov     rdi, [rcx+498h]
0x18001456b  xor     ebx, ebx
0x18001456d  mov     r15, [rcx+4A0h]
0x180014574  mov     r12, rdx
0x180014577  lea     rbp, [rsi+0C8h]
0x18001457e  mov     rcx, rbp; lpCriticalSection
0x180014581  call    cs:__imp_EnterCriticalSection
0x180014588  nop     dword ptr [rax+rax+00h]
0x18001458d  mov     eax, ebx
0x18001458f  lock xadd [rsi+20h], eax
0x180014594  dec     eax
0x180014596  cmp     eax, 1
0x180014599  jbe     short loc_1800145B1
0x18001459b  mov     rcx, rbp; lpCriticalSection
0x18001459e  call    cs:__imp_LeaveCriticalSection
0x1800145a5  nop     dword ptr [rax+rax+00h]
0x1800145aa  mov     ebx, 139Fh
0x1800145af  jmp     short loc_1800145E6
0x1800145b1  test    rdi, rdi
0x1800145b4  jnz     short loc_1800145BE
0x1800145b6  mov     rdi, [rsi+58h]
0x1800145ba  mov     r15, [rsi+60h]
0x1800145be  mov     rcx, rbp; lpCriticalSection
0x1800145c1  call    cs:__imp_LeaveCriticalSection
0x1800145c8  nop     dword ptr [rax+rax+00h]
0x1800145cd  test    rdi, rdi
0x1800145d0  jz      short loc_1800145E6
0x1800145d2  lea     rdx, [r14+48h]
0x1800145d6  mov     r8, r12
0x1800145d9  mov     rcx, r15
0x1800145dc  mov     rax, rdi
0x1800145df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800145e4  mov     ebx, eax
0x1800145e6  mov     rbp, [rsp+38h+arg_8]
0x1800145eb  mov     eax, ebx
0x1800145ed  mov     rbx, [rsp+38h+arg_0]
0x1800145f2  mov     rsi, [rsp+38h+arg_10]
0x1800145f7  mov     rdi, [rsp+38h+arg_18]
0x1800145fc  add     rsp, 20h
0x180014600  pop     r15
0x180014602  pop     r14
0x180014604  pop     r12
0x180014606  retn
```
