# SkpWriteDumpData

- ea: `0x1400be4f8`
- end: `0x1400be636`
- name: `SkpWriteDumpData`
- size: `318`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1400bd2a0`

## callees

- `0x1400be3dc`
- `0x1400be4f8`
- `0x1400be63c`
- `0x1400be870`
- `0x1400be910`
- `0x1400bee00`
- `0x1400bef5c`
- `0x1400f3620`
- `0x1400f38f0`

## pseudocode

```c
__int64 __fastcall SkpWriteDumpData(char *a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5, _QWORD *a6)
{
  int v10; // eax
  __int64 result; // rax
  __int64 v12; // rcx
  int v13; // [rsp+30h] [rbp-68h] BYREF
  _DWORD Src[3]; // [rsp+38h] [rbp-60h] BYREF
  __int64 v15; // [rsp+44h] [rbp-54h]
  int v16; // [rsp+4Ch] [rbp-4Ch]
  __int64 v17; // [rsp+50h] [rbp-48h]

  v16 = 0;
  if ( *(_QWORD *)(a2 + 160) >= 0x20u )
  {
    v10 = *(_DWORD *)a2;
    Src[0] = 1347241037;
    Src[1] = -1600149613;
    Src[2] = v10;
    v15 = 32;
    v17 = 0;
    RtlCopyVolatileMemory(a1, Src, 0x20u);
  }
  result = SkpWriteSystemInfo(a1, a2);
  if ( (int)result >= 0 )
  {
    SkpWriteMiscInfo(a1, a2, a3);
    if ( !a4 || (result = SkpWriteException(a1, a2, a4, a5), (int)result >= 0) )
    {
      v12 = *(unsigned int *)(a2 + 112);
      if ( *(_QWORD *)(a2 + 160) >= (unsigned __int64)(v12 + 4) )
      {
        v13 = *(_DWORD *)(a2 + 216);
        RtlCopyVolatileMemory(&a1[v12], &v13, 4u);
        *(_DWORD *)(a2 + 112) += 4;
      }
      result = SkpWriteThreadList((__int64)a1, a2, a3);
      if ( (int)result >= 0 )
      {
        result = SkpWriteModuleList((__int64)a1, a2, a3, a4, a6);
        if ( (int)result >= 0 )
          return SkpWriteDirectoryTable(a1, *(unsigned int *)(a2 + 12), a2);
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x1400be4f8  push    rbx
0x1400be4fa  push    rbp
0x1400be4fb  push    rsi
0x1400be4fc  push    rdi
0x1400be4fd  push    r14
0x1400be4ff  push    r15
0x1400be501  sub     rsp, 68h
0x1400be505  mov     rax, cs:__security_cookie
0x1400be50c  xor     rax, rsp
0x1400be50f  mov     [rsp+98h+var_40], rax
0x1400be514  mov     r14, [rsp+98h+arg_20]
0x1400be51c  mov     rsi, r8
0x1400be51f  mov     r15, [rsp+98h+arg_28]
0x1400be527  mov     r8d, 20h ; ' '; Size
0x1400be52d  mov     rbp, r9
0x1400be530  mov     rbx, rdx
0x1400be533  mov     rdi, rcx
0x1400be536  mov     [rsp+98h+var_4C], 0
0x1400be53e  cmp     [rdx+0A0h], r8
0x1400be545  jb      short loc_1400BE575
0x1400be547  mov     eax, [rdx]
0x1400be549  lea     rdx, [rsp+98h+Src]; Src
0x1400be54e  mov     [rsp+98h+Src], 504D444Dh
0x1400be556  mov     [rsp+98h+var_5C], 0A09FA793h
0x1400be55e  mov     [rsp+98h+var_58], eax
0x1400be562  mov     [rsp+98h+var_54], r8
0x1400be567  mov     [rsp+98h+var_48], 0
0x1400be570  call    RtlCopyVolatileMemory
0x1400be575  mov     rdx, rbx
0x1400be578  mov     rcx, rdi
0x1400be57b  call    SkpWriteSystemInfo
0x1400be580  test    eax, eax
0x1400be582  js      loc_1400BE61B
0x1400be588  mov     r8, rsi
0x1400be58b  mov     rdx, rbx
0x1400be58e  mov     rcx, rdi
0x1400be591  call    SkpWriteMiscInfo
0x1400be596  test    rbp, rbp
0x1400be599  jz      short loc_1400BE5B0
0x1400be59b  mov     r9, r14
0x1400be59e  mov     r8, rbp
0x1400be5a1  mov     rdx, rbx
0x1400be5a4  mov     rcx, rdi
0x1400be5a7  call    SkpWriteException
0x1400be5ac  test    eax, eax
0x1400be5ae  js      short loc_1400BE61B
0x1400be5b0  mov     ecx, [rbx+70h]
0x1400be5b3  lea     rax, [rcx+4]
0x1400be5b7  cmp     [rbx+0A0h], rax
0x1400be5be  jb      short loc_1400BE5E1
0x1400be5c0  mov     eax, [rbx+0D8h]
0x1400be5c6  lea     rdx, [rsp+98h+var_68]; Src
0x1400be5cb  add     rcx, rdi; void *
0x1400be5ce  mov     [rsp+98h+var_68], eax
0x1400be5d2  mov     r8d, 4; Size
0x1400be5d8  call    RtlCopyVolatileMemory
0x1400be5dd  add     dword ptr [rbx+70h], 4
0x1400be5e1  mov     r8, rsi
0x1400be5e4  mov     rdx, rbx
0x1400be5e7  mov     rcx, rdi
0x1400be5ea  call    SkpWriteThreadList
0x1400be5ef  test    eax, eax
0x1400be5f1  js      short loc_1400BE61B
0x1400be5f3  mov     r9, rbp
0x1400be5f6  mov     [rsp+98h+var_78], r15
0x1400be5fb  mov     r8, rsi
0x1400be5fe  mov     rdx, rbx
0x1400be601  mov     rcx, rdi
0x1400be604  call    SkpWriteModuleList
0x1400be609  test    eax, eax
0x1400be60b  js      short loc_1400BE61B
0x1400be60d  mov     edx, [rbx+0Ch]
0x1400be610  mov     r8, rbx
0x1400be613  mov     rcx, rdi
0x1400be616  call    SkpWriteDirectoryTable
0x1400be61b  mov     rcx, [rsp+98h+var_40]
0x1400be620  xor     rcx, rsp; StackCookie
0x1400be623  call    __security_check_cookie
0x1400be628  add     rsp, 68h
0x1400be62c  pop     r15
0x1400be62e  pop     r14
0x1400be630  pop     rdi
0x1400be631  pop     rsi
0x1400be632  pop     rbp
0x1400be633  pop     rbx
0x1400be634  retn
```
