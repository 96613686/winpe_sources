# YReader::GetNextInfoItem(InfoSet *)

- ea: `0x100403820`
- end: `0x1004038a5`
- name: `?GetNextInfoItem@YReader@@UEAAJPEAW4InfoSet@@@Z`
- size: `133`
- prototype: `__int64 __fastcall(YReader *__hidden this, enum InfoSet *)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x100401780`
- `0x100402d90`
- `0x100403820`
- `0x100423dd0`
- `0x100439df0`

## pseudocode

```c
__int64 __fastcall YReader::GetNextInfoItem(YReader *this, enum InfoSet *a2)
{
  if ( *((int *)this + 70) > 0 && *((int *)this + 437) >= 0 )
  {
    MXRRaiseException(-1072894386);
    __debugbreak();
    JUMPOUT(0x1004038A5LL);
  }
  (*((void (__fastcall **)(char *))this + 184))((char *)this + *((int *)this + 370) - 32);
  *(_DWORD *)a2 = *((_DWORD *)this + 436);
  return *((unsigned int *)this + 437);
}

```

## disassembly

```asm
0x100403820  mov     [rsp+arg_10], rbx
0x100403825  mov     [rsp+arg_8], rdx
0x10040382a  mov     [rsp+arg_0], rcx
0x10040382f  push    rdi
0x100403830  sub     rsp, 40h
0x100403834  mov     rdi, rdx
0x100403837  mov     rbx, rcx
0x10040383a  cmp     dword ptr [rcx+118h], 0
0x100403841  jle     short loc_10040384C
0x100403843  cmp     dword ptr [rcx+6D4h], 0
0x10040384a  jge     short loc_100403899
0x10040384c  movsxd  rax, dword ptr [rcx+5C8h]
0x100403853  add     rcx, 0FFFFFFFFFFFFFFE0h
0x100403857  add     rcx, rax
0x10040385a  mov     rax, [rbx+5C0h]
0x100403861  call    cs:__guard_dispatch_icall_fptr
0x100403867  jmp     short loc_100403880
0x100403869  mov     rbx, [rsp+48h+arg_0]
0x10040386e  lea     rcx, [rbx-20h]; this
0x100403872  mov     edx, [rsp+48h+var_28]; int
0x100403876  call    ?HandleException@YReader@@AEAAXJ@Z; YReader::HandleException(long)
0x10040387b  mov     rdi, [rsp+48h+arg_8]
0x100403880  mov     eax, [rbx+6D0h]
0x100403886  mov     [rdi], eax
0x100403888  mov     eax, [rbx+6D4h]
0x10040388e  mov     rbx, [rsp+48h+arg_10]
0x100403893  add     rsp, 40h
0x100403897  pop     rdi
0x100403898  retn
0x100403899  mov     ecx, 0C00CEE4Eh; int
0x10040389e  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
0x1004038a3  nop
0x1004038a4  int     3; Trap to Debugger
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
