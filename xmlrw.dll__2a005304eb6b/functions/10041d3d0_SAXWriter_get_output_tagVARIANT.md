# SAXWriter::get_output(tagVARIANT *)

- ea: `0x10041d3d0`
- end: `0x10041d44d`
- name: `?get_output@SAXWriter@@UEAAJPEAUtagVARIANT@@@Z`
- size: `125`
- prototype: `__int64 __fastcall(SAXWriter *__hidden this, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x100401780`
- `0x10041d3d0`
- `0x100423dd0`
- `0x100439df0`

## pseudocode

```c
__int64 __fastcall SAXWriter::get_output(LONGLONG *this, struct tagVARIANT *a2)
{
  if ( !a2 )
  {
    MXRRaiseException(-2147467261);
    __debugbreak();
    JUMPOUT(0x10041D44DLL);
  }
  (*(void (__fastcall **)(LONGLONG *))(*this + 184))(this);
  if ( this[10] )
  {
    a2->vt = 13;
    a2->llVal = this[10];
    (*(void (__fastcall **)(LONGLONG))(*(_QWORD *)this[10] + 8LL))(this[10]);
  }
  else
  {
    a2->vt = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x10041d3d0  mov     [rsp+arg_0], rbx
0x10041d3d5  mov     [rsp+arg_8], rsi
0x10041d3da  push    rdi
0x10041d3db  sub     rsp, 40h
0x10041d3df  mov     rdi, rdx
0x10041d3e2  mov     rsi, rcx
0x10041d3e5  xor     ebx, ebx
0x10041d3e7  test    rdx, rdx
0x10041d3ea  jz      short loc_10041D441
0x10041d3ec  mov     rax, [rcx]
0x10041d3ef  mov     rax, [rax+0B8h]
0x10041d3f6  call    cs:__guard_dispatch_icall_fptr
0x10041d3fc  cmp     qword ptr [rsi+50h], 0
0x10041d401  jz      short loc_10041D426
0x10041d403  mov     eax, 0Dh
0x10041d408  mov     [rdi], ax
0x10041d40b  mov     rax, [rsi+50h]
0x10041d40f  mov     [rdi+8], rax
0x10041d413  mov     rcx, [rsi+50h]
0x10041d417  mov     rax, [rcx]
0x10041d41a  mov     rax, [rax+8]
0x10041d41e  call    cs:__guard_dispatch_icall_fptr
0x10041d424  jmp     short loc_10041D429
0x10041d426  mov     [rdi], bx
0x10041d429  jmp     short loc_10041D42F
0x10041d42b  mov     ebx, [rsp+48h+var_28]
0x10041d42f  mov     eax, ebx
0x10041d431  mov     rbx, [rsp+48h+arg_0]
0x10041d436  mov     rsi, [rsp+48h+arg_8]
0x10041d43b  add     rsp, 40h
0x10041d43f  pop     rdi
0x10041d440  retn
0x10041d441  mov     ecx, 80004003h; int
0x10041d446  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
0x10041d44b  nop
0x10041d44c  int     3; Trap to Debugger
0x100439f20  push    rbp
0x100439f22  sub     rsp, 20h
0x100439f26  mov     rbp, rdx
0x100439f29  mov     [rbp+38h], rcx
0x100439f2d  mov     [rbp+30h], rcx
0x100439f31  mov     rax, [rbp+30h]
0x100439f35  mov     rcx, [rax]
0x100439f38  mov     [rbp+28h], rcx
0x100439f3c  mov     rax, [rbp+28h]
0x100439f40  mov     eax, [rax]
0x100439f42  cmp     eax, 0C0000005h
0x100439f47  jz      short loc_100439F79
0x100439f49  add     eax, 1FFFFFFFh
0x100439f4e  cmp     eax, 1
0x100439f51  ja      short loc_100439F69
0x100439f53  mov     rax, [rbp+28h]
0x100439f57  cmp     dword ptr [rax+18h], 1
0x100439f5b  jnz     short loc_100439F69
0x100439f5d  mov     rax, [rbp+28h]
0x100439f61  mov     ecx, [rax+20h]
0x100439f64  mov     [rbp+20h], ecx
0x100439f67  jmp     short loc_100439F70
0x100439f69  mov     dword ptr [rbp+20h], 8000FFFFh
0x100439f70  mov     dword ptr [rbp+24h], 1
0x100439f77  jmp     short loc_100439F80
0x100439f79  mov     dword ptr [rbp+24h], 0
0x100439f80  mov     eax, [rbp+24h]
0x100439f83  add     rsp, 20h
0x100439f87  pop     rbp
0x100439f88  retn
```
