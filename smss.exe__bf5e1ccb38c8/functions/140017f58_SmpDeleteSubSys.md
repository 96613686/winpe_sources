# SmpDeleteSubSys

- ea: `0x140017f58`
- end: `0x140017fe7`
- name: `SmpDeleteSubSys`
- size: `143`
- prototype: `__int64 __fastcall(PVOID BaseAddress)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140001f60`
- `0x1400151e0`

## callees

- `0x140001e40`
- `0x1400030f0`
- `0x140008cd0`
- `0x14000b8f0`
- `0x140017f58`

## pseudocode

```c
__int64 __fastcall SmpDeleteSubSys(unsigned int *BaseAddress)
{
  __int64 result; // rax
  bool v3; // zf
  unsigned int **v4; // rdx
  PVOID *v5; // rcx
  int v6; // edi
  __int64 v7; // [rsp+20h] [rbp-18h] BYREF
  int v8; // [rsp+28h] [rbp-10h]

  result = 0;
  v3 = (BaseAddress[2] & 4) == 0;
  v8 = 0;
  v7 = 0;
  if ( v3 )
  {
    SmpLockKnownSubSysList(BaseAddress[16], 0, &v7);
    if ( (BaseAddress[2] & 4) != 0 )
    {
      v6 = 0;
    }
    else
    {
      _InterlockedOr((volatile signed __int32 *)BaseAddress + 2, 4u);
      v4 = (unsigned int **)*((_QWORD *)BaseAddress + 9);
      if ( v4[1] != BaseAddress + 18 || (v5 = (PVOID *)*((_QWORD *)BaseAddress + 10), *v5 != BaseAddress + 18) )
        __fastfail(3u);
      *v5 = v4;
      v6 = 1;
      v4[1] = (unsigned int *)v5;
    }
    result = SmpUnlockKnownSubSysList(&v7);
    if ( v6 == 1 )
    {
      SmpCompleteSubSysStatusChange(BaseAddress);
      return SmpDereferenceKnownSubSys(BaseAddress);
    }
  }
  return result;
}

```

## disassembly

```asm
0x140017f58  mov     r11, rsp
0x140017f5b  mov     [r11+8], rbx
0x140017f5f  push    rdi
0x140017f60  sub     rsp, 30h
0x140017f64  xor     eax, eax
0x140017f66  mov     rbx, rcx
0x140017f69  test    byte ptr [rcx+8], 4
0x140017f6d  mov     [r11-14h], rax
0x140017f71  mov     [r11-18h], rax
0x140017f75  jnz     short loc_140017FDC
0x140017f77  mov     ecx, [rcx+40h]
0x140017f7a  lea     r8, [r11-18h]
0x140017f7e  xor     edx, edx
0x140017f80  call    SmpLockKnownSubSysList
0x140017f85  test    byte ptr [rbx+8], 4
0x140017f89  jnz     short loc_140017FBB
0x140017f8b  lock or dword ptr [rbx+8], 4
0x140017f90  lea     rax, [rbx+48h]
0x140017f94  mov     rdx, [rax]
0x140017f97  cmp     [rdx+8], rax
0x140017f9b  jnz     short loc_140017FB4
0x140017f9d  mov     rcx, [rax+8]
0x140017fa1  cmp     [rcx], rax
0x140017fa4  jnz     short loc_140017FB4
0x140017fa6  mov     [rcx], rdx
0x140017fa9  mov     edi, 1
0x140017fae  mov     [rdx+8], rcx
0x140017fb2  jmp     short loc_140017FBD
0x140017fb4  mov     ecx, 3
0x140017fb9  int     29h; Win8: RtlFailFast(ecx)
0x140017fbb  xor     edi, edi
0x140017fbd  lea     rcx, [rsp+38h+var_18]
0x140017fc2  call    SmpUnlockKnownSubSysList
0x140017fc7  cmp     edi, 1
0x140017fca  jnz     short loc_140017FDC
0x140017fcc  mov     rcx, rbx
0x140017fcf  call    SmpCompleteSubSysStatusChange
0x140017fd4  mov     rcx, rbx; BaseAddress
0x140017fd7  call    SmpDereferenceKnownSubSys
0x140017fdc  mov     rbx, [rsp+38h+arg_0]
0x140017fe1  add     rsp, 30h
0x140017fe5  pop     rdi
0x140017fe6  retn
```
