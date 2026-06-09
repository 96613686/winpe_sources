# CProfileNotifyHandler::OnCreate(wchar_t const *,wchar_t const *,ulong)

- ea: `0x180007fd0`
- end: `0x180008098`
- name: `?OnCreate@CProfileNotifyHandler@@UEAAJPEB_W0K@Z`
- size: `200`
- prototype: `int(CProfileNotifyHandler *__hidden this, const wchar_t *, const wchar_t *, unsigned int)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, service_task`

## callees

- `0x180001b78`
- `0x1800077f0`
- `0x180007fd0`
- `0x180008510`
- `0x18000f010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CProfileNotifyHandler::OnCreate(CProfileNotifyHandler *this, const wchar_t *a2, const wchar_t *a3)
{
  CProfileTask_OnCreate *v4; // rax
  CProfileTask_OnCreate *v5; // rbx
  signed int v6; // edi

  v4 = (CProfileTask_OnCreate *)operator new(0x10u, (const struct std::nothrow_t *)&std::nothrow);
  v5 = v4;
  if ( v4 )
  {
    *(_OWORD *)v4 = 0;
    *(_QWORD *)v4 = &CProfileTask_OnCreate::`vftable';
    *((_QWORD *)v4 + 1) = 0;
  }
  else
  {
    v5 = 0;
  }
  if ( !v5 )
  {
    v6 = -2147024882;
LABEL_6:
    Profile_LogCreateFailure(v6, a2);
    goto LABEL_7;
  }
  v6 = CProfileTask_OnCreate::Initialize(v5, a2);
  if ( v6 < 0 )
    goto LABEL_6;
  v6 = (*(__int64 (__fastcall **)(CProfileTask_OnCreate *))(*(_QWORD *)v5 + 8LL))(v5);
  if ( v6 < 0 )
    goto LABEL_6;
  (*(void (__fastcall **)(CProfileTask_OnCreate *))(*(_QWORD *)v5 + 16LL))(v5);
LABEL_7:
  if ( v5 )
    (**(void (__fastcall ***)(CProfileTask_OnCreate *, __int64))v5)(v5, 1);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180007fd0  mov     [rsp+arg_0], rbx
0x180007fd5  mov     [rsp+arg_8], rsi
0x180007fda  push    rdi
0x180007fdb  sub     rsp, 30h
0x180007fdf  mov     rsi, rdx
0x180007fe2  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180007fe9  mov     ecx, 10h; unsigned __int64
0x180007fee  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180007ff3  mov     rbx, rax
0x180007ff6  mov     [rsp+38h+var_18], rax
0x180007ffb  test    rax, rax
0x180007ffe  jz      short loc_18000801A
0x180008000  xorps   xmm0, xmm0
0x180008003  movups  xmmword ptr [rax], xmm0
0x180008006  lea     rax, ??_7CProfileTask_OnCreate@@6B@; const CProfileTask_OnCreate::`vftable'
0x18000800d  mov     [rbx], rax
0x180008010  mov     qword ptr [rbx+8], 0
0x180008018  jmp     short loc_18000801C
0x18000801a  xor     ebx, ebx
0x18000801c  mov     [rsp+38h+var_18], rbx
0x180008021  test    rbx, rbx
0x180008024  jnz     short loc_180008060
0x180008026  mov     edi, 8007000Eh
0x18000802b  mov     rdx, rsi; wchar_t *
0x18000802e  mov     ecx, edi; dwMessageId
0x180008030  call    ?Profile_LogCreateFailure@@YAXJPEB_W@Z; Profile_LogCreateFailure(long,wchar_t const *)
0x180008035  nop
0x180008036  test    rbx, rbx
0x180008039  jz      short loc_18000804E
0x18000803b  mov     rax, [rbx]
0x18000803e  mov     edx, 1
0x180008043  mov     rcx, rbx
0x180008046  mov     rax, [rax]
0x180008049  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000804e  mov     eax, edi
0x180008050  mov     rbx, [rsp+38h+arg_0]
0x180008055  mov     rsi, [rsp+38h+arg_8]
0x18000805a  add     rsp, 30h
0x18000805e  pop     rdi
0x18000805f  retn
0x180008060  mov     rdx, rsi; wchar_t *
0x180008063  mov     rcx, rbx; this
0x180008066  call    ?Initialize@CProfileTask_OnCreate@@QEAAJPEB_W@Z; CProfileTask_OnCreate::Initialize(wchar_t const *)
0x18000806b  mov     edi, eax
0x18000806d  test    eax, eax
0x18000806f  js      short loc_18000802B
0x180008071  mov     rax, [rbx]
0x180008074  mov     rcx, rbx
0x180008077  mov     rax, [rax+8]
0x18000807b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008080  mov     edi, eax
0x180008082  test    eax, eax
0x180008084  js      short loc_18000802B
0x180008086  mov     rax, [rbx]
0x180008089  mov     rcx, rbx
0x18000808c  mov     rax, [rax+10h]
0x180008090  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008095  jmp     short loc_180008036
```
