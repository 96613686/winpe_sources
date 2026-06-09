# CRegistryEventRequest::Execute(int)

- ea: `0x180008fe0`
- end: `0x1800090b7`
- name: `?Execute@CRegistryEventRequest@@UEAAJH@Z`
- size: `215`
- prototype: `__int64 __fastcall(CRegistryEventRequest *__hidden this, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180013ff0`

## callees

- `0x180008fe0`
- `0x180017010`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CRegistryEventRequest::Execute(CRegistryEventRequest *this, int a2)
{
  __int64 v3; // rax
  __int64 result; // rax
  __int64 v5; // rax
  __int64 v6; // rcx
  __int64 v7; // r9
  unsigned int v8; // eax
  unsigned int v9; // ebx
  __int64 v10; // rax
  int v11; // [rsp+38h] [rbp+10h] BYREF
  __int64 v12; // [rsp+40h] [rbp+18h] BYREF
  __int64 v13; // [rsp+48h] [rbp+20h] BYREF

  if ( a2 || !(*(unsigned int (__fastcall **)(CRegistryEventRequest *))(*(_QWORD *)this + 24LL))(this) )
  {
    v10 = *(_QWORD *)this;
    v11 = 0;
    result = (*(__int64 (__fastcall **)(CRegistryEventRequest *, int *))(v10 + 40))(this, &v11);
    if ( (int)result < 0 )
      return result;
    if ( v11 == *((_DWORD *)this + 40) )
      return 1;
    *((_DWORD *)this + 40) = v11;
  }
  v3 = *(_QWORD *)this;
  v12 = 0;
  result = (*(__int64 (__fastcall **)(CRegistryEventRequest *, __int64 *))(v3 + 32))(this, &v12);
  if ( (int)result >= 0 )
  {
    v5 = *((_QWORD *)this + 2);
    v6 = v12;
    v13 = v12;
    v7 = *(_QWORD *)(v5 + 80);
    if ( v7 )
    {
      v8 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64 *))(*(_QWORD *)v7 + 24LL))(*(_QWORD *)(v5 + 80), 1, &v13);
      v6 = v12;
      v9 = v8;
    }
    else
    {
      v9 = 0;
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    return v9;
  }
  return result;
}

```

## disassembly

```asm
0x180008fe0  mov     [rsp+arg_0], rbx
0x180008fe5  push    rdi
0x180008fe6  sub     rsp, 20h
0x180008fea  xor     edi, edi
0x180008fec  mov     rbx, rcx
0x180008fef  test    edx, edx
0x180008ff1  jnz     short loc_180009070
0x180008ff3  mov     rax, [rcx]
0x180008ff6  mov     rax, [rax+18h]
0x180008ffa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008fff  test    eax, eax
0x180009001  jz      short loc_180009070
0x180009003  mov     rax, [rbx]
0x180009006  lea     rdx, [rsp+28h+arg_10]
0x18000900b  mov     rcx, rbx
0x18000900e  mov     [rsp+28h+arg_10], rdi
0x180009013  mov     rax, [rax+20h]
0x180009017  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000901c  test    eax, eax
0x18000901e  js      short loc_180009065
0x180009020  mov     rax, [rbx+10h]
0x180009024  mov     rcx, [rsp+28h+arg_10]
0x180009029  mov     [rsp+28h+arg_18], rcx
0x18000902e  mov     r9, [rax+50h]
0x180009032  test    r9, r9
0x180009035  jz      short loc_1800090B3
0x180009037  mov     rax, [r9]
0x18000903a  lea     r8, [rsp+28h+arg_18]
0x18000903f  mov     edx, 1
0x180009044  mov     rcx, r9
0x180009047  mov     rax, [rax+18h]
0x18000904b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009050  mov     rcx, [rsp+28h+arg_10]
0x180009055  mov     ebx, eax
0x180009057  mov     rax, [rcx]
0x18000905a  mov     rax, [rax+10h]
0x18000905e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009063  mov     eax, ebx
0x180009065  mov     rbx, [rsp+28h+arg_0]
0x18000906a  add     rsp, 20h
0x18000906e  pop     rdi
0x18000906f  retn
0x180009070  mov     rax, [rbx]
0x180009073  lea     rdx, [rsp+28h+arg_8]
0x180009078  mov     rcx, rbx
0x18000907b  mov     [rsp+28h+arg_8], edi
0x18000907f  mov     rax, [rax+28h]
0x180009083  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009088  test    eax, eax
0x18000908a  js      short loc_180009065
0x18000908c  mov     eax, [rsp+28h+arg_8]
0x180009090  cmp     eax, [rbx+0A0h]
0x180009096  jnz     short loc_1800090A8
0x180009098  mov     rbx, [rsp+28h+arg_0]
0x18000909d  mov     eax, 1
0x1800090a2  add     rsp, 20h
0x1800090a6  pop     rdi
0x1800090a7  retn
0x1800090a8  mov     [rbx+0A0h], eax
0x1800090ae  jmp     loc_180009003
0x1800090b3  mov     ebx, edi
0x1800090b5  jmp     short loc_180009057
```
