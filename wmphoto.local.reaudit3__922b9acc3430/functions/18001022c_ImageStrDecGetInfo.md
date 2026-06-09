# ImageStrDecGetInfo

- ea: `0x18001022c`
- end: `0x1800102d9`
- name: `ImageStrDecGetInfo`
- size: `173`
- prototype: `__int64 __fastcall(__int64 *, __int64)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x18000ef30`
- `0x18000ffc0`
- `0x180010e08`
- `0x18002b180`

## callees

- `0x18001022c`
- `0x1800108a8`
- `0x180036420`
- `0x180037174`
- `0x180045010`

## pseudocode

```c
__int64 __fastcall ImageStrDecGetInfo(__int64 *a1, __int64 a2)
{
  __int64 v5; // [rsp+20h] [rbp-B8h] BYREF
  _BYTE v6[144]; // [rsp+30h] [rbp-A8h] BYREF

  v5 = 0;
  memset_0(v6, 0, 0x88u);
  if ( (*(int (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)(a2 + 64) + 96LL))(*(_QWORD *)(a2 + 64), &v5) < 0
    || (int)ReadWMIHeader(a1, a2, (__int64)v6) < 0 )
  {
    return 0xFFFFFFFFLL;
  }
  else
  {
    return (unsigned int)((*(int (__fastcall **)(_QWORD, __int64))(*(_QWORD *)(a2 + 64) + 88LL))(
                            *(_QWORD *)(a2 + 64),
                            v5) >= 0)
         - 1;
  }
}

```

## disassembly

```asm
0x18001022c  mov     [rsp+arg_10], rbx
0x180010231  push    rdi
0x180010232  sub     rsp, 0D0h
0x180010239  mov     rax, cs:__security_cookie
0x180010240  xor     rax, rsp
0x180010243  mov     [rsp+0D8h+var_18], rax
0x18001024b  mov     rbx, rdx
0x18001024e  mov     [rsp+0D8h+var_B8], 0
0x180010257  mov     rdi, rcx
0x18001025a  xor     edx, edx; Val
0x18001025c  lea     rcx, [rsp+0D8h+var_A8]; void *
0x180010261  mov     r8d, 88h; Size
0x180010267  call    memset_0
0x18001026c  mov     rcx, [rbx+40h]
0x180010270  lea     rdx, [rsp+0D8h+var_B8]
0x180010275  mov     rax, [rcx+60h]
0x180010279  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001027e  test    eax, eax
0x180010280  js      short loc_1800102D4
0x180010282  lea     r8, [rsp+0D8h+var_A8]
0x180010287  mov     rdx, rbx
0x18001028a  mov     rcx, rdi
0x18001028d  call    ReadWMIHeader
0x180010292  test    eax, eax
0x180010294  js      short loc_1800102D4
0x180010296  mov     rcx, [rbx+40h]
0x18001029a  mov     rdx, [rsp+0D8h+var_B8]
0x18001029f  mov     rax, [rcx+58h]
0x1800102a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800102a8  xor     ecx, ecx
0x1800102aa  test    eax, eax
0x1800102ac  setns   cl
0x1800102af  lea     eax, [rcx-1]
0x1800102b2  mov     rcx, [rsp+0D8h+var_18]
0x1800102ba  xor     rcx, rsp; StackCookie
0x1800102bd  call    __security_check_cookie
0x1800102c2  mov     rbx, [rsp+0D8h+arg_10]
0x1800102ca  add     rsp, 0D0h
0x1800102d1  pop     rdi
0x1800102d2  retn
0x1800102d4  or      eax, 0FFFFFFFFh
0x1800102d7  jmp     short loc_1800102B2
```
