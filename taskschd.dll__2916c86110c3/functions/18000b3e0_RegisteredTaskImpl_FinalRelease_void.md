# RegisteredTaskImpl::FinalRelease(void)

- ea: `0x18000b3e0`
- end: `0x18000b52d`
- name: `?FinalRelease@RegisteredTaskImpl@@QEAAXXZ`
- size: `333`
- prototype: `void __fastcall(RegisteredTaskImpl *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18000acd0`

## callees

- `0x18000b3e0`
- `0x180054010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b4c2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b4c2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b40f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b40f`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18000b525`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18000b525`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b455`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b463`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b455`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b463`

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
0x18000b3e0  mov     [rsp+arg_8], rbx
0x18000b3e5  mov     [rsp+arg_10], rbp
0x18000b3ea  push    rsi
0x18000b3eb  push    rdi
0x18000b3ec  push    r14
0x18000b3ee  sub     rsp, 20h
0x18000b3f2  mov     rbx, rcx
0x18000b3f5  xor     r14d, r14d
0x18000b3f8  mov     ebp, r14d
0x18000b3fb  lea     rdi, [rcx+10h]
0x18000b3ff  test    rcx, rcx
0x18000b402  cmovz   rdi, r14
0x18000b406  test    rdi, rdi
0x18000b409  jz      short loc_18000B415
0x18000b40b  lea     rcx, [rdi+8]; lpCriticalSection
0x18000b40f  call    cs:__imp_EnterCriticalSection
0x18000b415  mov     [rsp+38h+arg_0], rdi
0x18000b41a  mov     rax, [rbx+0A0h]
0x18000b421  test    rax, rax
0x18000b424  jnz     loc_18000B4F2
0x18000b42a  mov     rcx, [rbx+98h]
0x18000b431  test    rcx, rcx
0x18000b434  jnz     loc_18000B501
0x18000b43a  cmp     qword ptr [rbx+68h], 8
0x18000b43f  jb      loc_18000B519
0x18000b445  mov     rcx, [rbx+50h]
0x18000b449  mov     [rbx+60h], r14
0x18000b44d  mov     [rcx], r14w
0x18000b451  mov     rcx, [rbx+70h]; bstrString
0x18000b455  call    cs:__imp_SysFreeString
0x18000b45b  mov     [rbx+70h], r14
0x18000b45f  mov     rcx, [rbx+78h]; bstrString
0x18000b463  call    cs:__imp_SysFreeString
0x18000b469  mov     [rbx+78h], r14
0x18000b46d  lea     rsi, [rbx+90h]
0x18000b474  mov     rcx, [rsi]
0x18000b477  test    rcx, rcx
0x18000b47a  jz      short loc_18000B490
0x18000b47c  test    rsi, rsi
0x18000b47f  jz      short loc_18000B490
0x18000b481  mov     rax, [rcx]
0x18000b484  mov     rax, [rax+10h]
0x18000b488  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b48d  mov     [rsi], r14
0x18000b490  mov     rcx, [rbx+88h]
0x18000b497  test    rcx, rcx
0x18000b49a  jz      short loc_18000B4AB
0x18000b49c  mov     eax, 0FFFFFFFFh
0x18000b4a1  lock xadd [rcx+8], eax
0x18000b4a6  cmp     eax, 1
0x18000b4a9  jz      short loc_18000B4E0
0x18000b4ab  mov     [rbx+88h], r14
0x18000b4b2  mov     [rbx+80h], r14
0x18000b4b9  test    rdi, rdi
0x18000b4bc  jz      short loc_18000B4C8
0x18000b4be  lea     rcx, [rdi+8]; lpCriticalSection
0x18000b4c2  call    cs:__imp_LeaveCriticalSection
0x18000b4c8  test    rbp, rbp
0x18000b4cb  jnz     short loc_18000B522
0x18000b4cd  mov     rbx, [rsp+38h+arg_8]
0x18000b4d2  mov     rbp, [rsp+38h+arg_10]
0x18000b4d7  add     rsp, 20h
0x18000b4db  pop     r14
0x18000b4dd  pop     rdi
0x18000b4de  pop     rsi
0x18000b4df  retn
0x18000b4e0  mov     rax, [rcx]
0x18000b4e3  mov     edx, 1
0x18000b4e8  mov     rax, [rax]
0x18000b4eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b4f0  jmp     short loc_18000B4AB
0x18000b4f2  mov     rbp, rax
0x18000b4f5  mov     [rbx+0A0h], r14
0x18000b4fc  jmp     loc_18000B42A
0x18000b501  mov     rax, [rcx]
0x18000b504  mov     rax, [rax+10h]
0x18000b508  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b50d  mov     [rbx+98h], r14
0x18000b514  jmp     loc_18000B43A
0x18000b519  lea     rcx, [rbx+50h]
0x18000b51d  jmp     loc_18000B449
0x18000b522  mov     rcx, rbp
0x18000b525  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x18000b52b  jmp     short loc_18000B4CD
```
