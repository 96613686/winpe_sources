# VidHandlerpCpuidRegisterEntry

- ea: `0x140086120`
- end: `0x1400861dd`
- name: `VidHandlerpCpuidRegisterEntry`
- size: `189`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x1400857bc`

## callees

- `0x140021650`
- `0x140073e0c`
- `0x140086120`

## import_xrefs

- `ntoskrnl!RtlRbRemoveNode` at `0x1400861b4`
- `ntoskrnl!RtlRbRemoveNode` at `0x1400861b4`
- `winhvr!WinHvInstallIntercept` at `0x140086187`
- `winhvr!WinHvInstallIntercept` at `0x140086187`

## pseudocode

```c
__int64 __fastcall VidHandlerpCpuidRegisterEntry(__int64 a1, __int64 a2)
{
  int v2; // ebx
  __int64 v3; // rbp
  int v6; // ebx
  __int64 v7; // rcx
  __int64 v9; // [rsp+20h] [rbp-38h] BYREF
  int v10; // [rsp+28h] [rbp-30h]

  v2 = *(_DWORD *)(a2 + 116);
  v3 = a1 + 3456;
  v10 = 0;
  v9 = 0;
  if ( (unsigned __int8)VidHandlerTableInsert(a1 + 3456) )
  {
    v7 = *(_QWORD *)(a1 + 648);
    LODWORD(v9) = 2;
    v10 = v2;
    v6 = WinHvInstallIntercept(v7, 4, &v9);
    if ( v6 < 0 )
      RtlRbRemoveNode(v3, a2 + 160);
    else
      _InterlockedIncrement64((volatile signed __int64 *)(*(_QWORD *)(a1 + 1528) + 496LL));
  }
  else
  {
    return (unsigned int)-1070137343;
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140086120  mov     [rsp+arg_10], rbx
0x140086125  push    rbp
0x140086126  push    rsi
0x140086127  push    rdi
0x140086128  sub     rsp, 40h
0x14008612c  mov     rax, cs:__security_cookie
0x140086133  xor     rax, rsp
0x140086136  mov     [rsp+58h+var_28], rax
0x14008613b  mov     ebx, [rdx+74h]
0x14008613e  lea     rbp, [rcx+0D80h]
0x140086145  xor     eax, eax
0x140086147  mov     rdi, rcx
0x14008614a  mov     qword ptr [rsp+58h+var_34], rax
0x14008614f  mov     rcx, rbp
0x140086152  mov     [rsp+20h], rax
0x140086157  mov     rsi, rdx
0x14008615a  call    VidHandlerTableInsert
0x14008615f  test    al, al
0x140086161  jnz     short loc_14008616A
0x140086163  mov     ebx, 0C0370001h
0x140086168  jmp     short loc_1400861C0
0x14008616a  mov     rcx, [rdi+288h]
0x140086171  lea     r8, [rsp+58h+var_38]
0x140086176  mov     edx, 4
0x14008617b  mov     [rsp+58h+var_38], 2
0x140086183  mov     [rsp+58h+var_34+4], ebx
0x140086187  call    cs:__imp_WinHvInstallIntercept
0x14008618e  nop     dword ptr [rax+rax+00h]
0x140086193  mov     ebx, eax
0x140086195  test    eax, eax
0x140086197  js      short loc_1400861AA
0x140086199  mov     rcx, [rdi+5F8h]
0x1400861a0  lock inc qword ptr [rcx+1F0h]
0x1400861a8  jmp     short loc_1400861C0
0x1400861aa  lea     rdx, [rsi+0A0h]
0x1400861b1  mov     rcx, rbp
0x1400861b4  call    cs:__imp_RtlRbRemoveNode
0x1400861bb  nop     dword ptr [rax+rax+00h]
0x1400861c0  mov     eax, ebx
0x1400861c2  mov     rcx, [rsp+58h+var_28]
0x1400861c7  xor     rcx, rsp; StackCookie
0x1400861ca  call    __security_check_cookie
0x1400861cf  mov     rbx, [rsp+58h+arg_10]
0x1400861d4  add     rsp, 40h
0x1400861d8  pop     rdi
0x1400861d9  pop     rsi
0x1400861da  pop     rbp
0x1400861db  retn
```
