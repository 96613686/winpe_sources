# RegisteredTaskImpl::FinalRelease(void)

- ea: `0x18000b7c0`
- end: `0x18000b92c`
- name: `?FinalRelease@RegisteredTaskImpl@@QEAAXXZ`
- size: `364`
- prototype: `void __fastcall(RegisteredTaskImpl *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18000afe0`

## callees

- `0x18000b7c0`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b8b4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b8b4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b7ef`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b7ef`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18000b91e`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18000b91e`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b83b`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b84f`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b83b`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b84f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall RegisteredTaskImpl::FinalRelease(RegisteredTaskImpl *this)
{
  __int64 v2; // rbp
  char *v3; // rdi
  __int64 v4; // rcx
  _WORD *v5; // rcx
  __int64 v6; // rcx
  __int64 v7; // rcx

  v2 = 0;
  v3 = (char *)this + 16;
  if ( !this )
    v3 = 0;
  if ( v3 )
    EnterCriticalSection((LPCRITICAL_SECTION)(v3 + 8));
  if ( *((_QWORD *)this + 20) )
  {
    v2 = *((_QWORD *)this + 20);
    *((_QWORD *)this + 20) = 0;
  }
  v4 = *((_QWORD *)this + 19);
  if ( v4 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
    *((_QWORD *)this + 19) = 0;
  }
  if ( *((_QWORD *)this + 13) < 8u )
    v5 = (_WORD *)((char *)this + 80);
  else
    v5 = (_WORD *)*((_QWORD *)this + 10);
  *((_QWORD *)this + 12) = 0;
  *v5 = 0;
  SysFreeString(*((BSTR *)this + 14));
  *((_QWORD *)this + 14) = 0;
  SysFreeString(*((BSTR *)this + 15));
  *((_QWORD *)this + 15) = 0;
  v6 = *((_QWORD *)this + 18);
  if ( v6 && this != (RegisteredTaskImpl *)-144LL )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    *((_QWORD *)this + 18) = 0;
  }
  v7 = *((_QWORD *)this + 17);
  if ( v7 && _InterlockedExchangeAdd((volatile signed __int32 *)(v7 + 8), 0xFFFFFFFF) == 1 )
    (**(void (__fastcall ***)(__int64, __int64))v7)(v7, 1);
  *((_QWORD *)this + 17) = 0;
  *((_QWORD *)this + 16) = 0;
  if ( v3 )
    LeaveCriticalSection((LPCRITICAL_SECTION)(v3 + 8));
  if ( v2 )
    RtlUnsubscribeWnfNotificationWaitForCompletion(v2);
}

```

## disassembly

```asm
0x18000b7c0  mov     [rsp+arg_8], rbx
0x18000b7c5  mov     [rsp+arg_10], rbp
0x18000b7ca  push    rsi
0x18000b7cb  push    rdi
0x18000b7cc  push    r14
0x18000b7ce  sub     rsp, 20h
0x18000b7d2  mov     rbx, rcx
0x18000b7d5  xor     r14d, r14d
0x18000b7d8  mov     ebp, r14d
0x18000b7db  lea     rdi, [rcx+10h]
0x18000b7df  test    rcx, rcx
0x18000b7e2  cmovz   rdi, r14
0x18000b7e6  test    rdi, rdi
0x18000b7e9  jz      short loc_18000B7FB
0x18000b7eb  lea     rcx, [rdi+8]; lpCriticalSection
0x18000b7ef  call    cs:__imp_EnterCriticalSection
0x18000b7f6  nop     dword ptr [rax+rax+00h]
0x18000b7fb  mov     [rsp+38h+arg_0], rdi
0x18000b800  mov     rax, [rbx+0A0h]
0x18000b807  test    rax, rax
0x18000b80a  jnz     loc_18000B8EB
0x18000b810  mov     rcx, [rbx+98h]
0x18000b817  test    rcx, rcx
0x18000b81a  jnz     loc_18000B8FA
0x18000b820  cmp     qword ptr [rbx+68h], 8
0x18000b825  jb      loc_18000B912
0x18000b82b  mov     rcx, [rbx+50h]
0x18000b82f  mov     [rbx+60h], r14
0x18000b833  mov     [rcx], r14w
0x18000b837  mov     rcx, [rbx+70h]; bstrString
0x18000b83b  call    cs:__imp_SysFreeString
0x18000b842  nop     dword ptr [rax+rax+00h]
0x18000b847  mov     [rbx+70h], r14
0x18000b84b  mov     rcx, [rbx+78h]; bstrString
0x18000b84f  call    cs:__imp_SysFreeString
0x18000b856  nop     dword ptr [rax+rax+00h]
0x18000b85b  mov     [rbx+78h], r14
0x18000b85f  lea     rsi, [rbx+90h]
0x18000b866  mov     rcx, [rsi]
0x18000b869  test    rcx, rcx
0x18000b86c  jz      short loc_18000B882
0x18000b86e  test    rsi, rsi
0x18000b871  jz      short loc_18000B882
0x18000b873  mov     rax, [rcx]
0x18000b876  mov     rax, [rax+10h]
0x18000b87a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b87f  mov     [rsi], r14
0x18000b882  mov     rcx, [rbx+88h]
0x18000b889  test    rcx, rcx
0x18000b88c  jz      short loc_18000B89D
0x18000b88e  mov     eax, 0FFFFFFFFh
0x18000b893  lock xadd [rcx+8], eax
0x18000b898  cmp     eax, 1
0x18000b89b  jz      short loc_18000B8D9
0x18000b89d  mov     [rbx+88h], r14
0x18000b8a4  mov     [rbx+80h], r14
0x18000b8ab  test    rdi, rdi
0x18000b8ae  jz      short loc_18000B8C0
0x18000b8b0  lea     rcx, [rdi+8]; lpCriticalSection
0x18000b8b4  call    cs:__imp_LeaveCriticalSection
0x18000b8bb  nop     dword ptr [rax+rax+00h]
0x18000b8c0  test    rbp, rbp
0x18000b8c3  jnz     short loc_18000B91B
0x18000b8c5  mov     rbx, [rsp+38h+arg_8]
0x18000b8ca  mov     rbp, [rsp+38h+arg_10]
0x18000b8cf  add     rsp, 20h
0x18000b8d3  pop     r14
0x18000b8d5  pop     rdi
0x18000b8d6  pop     rsi
0x18000b8d7  retn
0x18000b8d9  mov     rax, [rcx]
0x18000b8dc  mov     edx, 1
0x18000b8e1  mov     rax, [rax]
0x18000b8e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b8e9  jmp     short loc_18000B89D
0x18000b8eb  mov     rbp, rax
0x18000b8ee  mov     [rbx+0A0h], r14
0x18000b8f5  jmp     loc_18000B810
0x18000b8fa  mov     rax, [rcx]
0x18000b8fd  mov     rax, [rax+10h]
0x18000b901  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b906  mov     [rbx+98h], r14
0x18000b90d  jmp     loc_18000B820
0x18000b912  lea     rcx, [rbx+50h]
0x18000b916  jmp     loc_18000B82F
0x18000b91b  mov     rcx, rbp
0x18000b91e  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x18000b925  nop     dword ptr [rax+rax+00h]
0x18000b92a  jmp     short loc_18000B8C5
```
