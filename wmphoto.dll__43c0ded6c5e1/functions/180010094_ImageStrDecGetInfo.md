# ImageStrDecGetInfo

- ea: `0x180010094`
- end: `0x180010140`
- name: `ImageStrDecGetInfo`
- size: `172`
- prototype: `__int64 __fastcall(__int64 *, __int64)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x18000ee00`
- `0x18000fe30`
- `0x180010c4c`
- `0x18002af00`

## callees

- `0x180010094`
- `0x1800106f0`
- `0x180035e50`
- `0x180036ba4`
- `0x180044010`

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
0x180010094  mov     [rsp+arg_10], rbx
0x180010099  push    rdi
0x18001009a  sub     rsp, 0D0h
0x1800100a1  mov     rax, cs:__security_cookie
0x1800100a8  xor     rax, rsp
0x1800100ab  mov     [rsp+0D8h+var_18], rax
0x1800100b3  mov     rbx, rdx
0x1800100b6  mov     [rsp+0D8h+var_B8], 0
0x1800100bf  mov     rdi, rcx
0x1800100c2  xor     edx, edx; Val
0x1800100c4  lea     rcx, [rsp+0D8h+var_A8]; void *
0x1800100c9  mov     r8d, 88h; Size
0x1800100cf  call    memset_0
0x1800100d4  mov     rcx, [rbx+40h]
0x1800100d8  lea     rdx, [rsp+0D8h+var_B8]
0x1800100dd  mov     rax, [rcx+60h]
0x1800100e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800100e6  test    eax, eax
0x1800100e8  js      short loc_18001013B
0x1800100ea  lea     r8, [rsp+0D8h+var_A8]
0x1800100ef  mov     rdx, rbx
0x1800100f2  mov     rcx, rdi
0x1800100f5  call    ReadWMIHeader
0x1800100fa  test    eax, eax
0x1800100fc  js      short loc_18001013B
0x1800100fe  mov     rcx, [rbx+40h]
0x180010102  mov     rdx, [rsp+0D8h+var_B8]
0x180010107  mov     rax, [rcx+58h]
0x18001010b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010110  xor     ecx, ecx
0x180010112  test    eax, eax
0x180010114  setns   cl
0x180010117  lea     eax, [rcx-1]
0x18001011a  mov     rcx, [rsp+0D8h+var_18]
0x180010122  xor     rcx, rsp; StackCookie
0x180010125  call    __security_check_cookie
0x18001012a  mov     rbx, [rsp+0D8h+arg_10]
0x180010132  add     rsp, 0D0h
0x180010139  pop     rdi
0x18001013a  retn
0x18001013b  or      eax, 0FFFFFFFFh
0x18001013e  jmp     short loc_18001011A
```
