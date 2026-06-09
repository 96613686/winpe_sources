# SspirCallRpc

- ea: `0x1800012b0`
- end: `0x1800013c4`
- name: `SspirCallRpc`
- size: `276`
- prototype: `__int64 __fastcall(__int64, unsigned int, const void *, _DWORD *, __int16 **, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180002a70`

## callees

- `0x1800012b0`
- `0x1800013d0`
- `0x1800032b8`
- `0x1800032c4`
- `0x180004010`

## pseudocode

```c
__int64 __fastcall SspirCallRpc(__int64 a1, unsigned int a2, const void *a3, _DWORD *a4, __int16 **a5, __int64 a6)
{
  __int16 *v10; // rax
  __int16 *v11; // rbx
  int v12; // edi

  if ( !gLsapSspiExtension || !*(_QWORD *)(gLsapSspiExtension + 32) )
    return 3221225659LL;
  if ( a2 > 0x1F8 )
    return 3221225485LL;
  if ( *(_QWORD *)gLsapSspiExtension )
  {
    v10 = (__int16 *)(*(__int64 (__fastcall **)(__int64))gLsapSspiExtension)(504);
    v11 = v10;
    if ( v10 )
    {
      memset_0(v10, 0, 0x1F8u);
      memcpy_0(v11, a3, a2);
      if ( v11[1] == a2 )
      {
        v12 = (*(__int64 (__fastcall **)(__int64, __int16 *, __int64))(gLsapSspiExtension + 32))(a1, v11, a6);
        if ( v12 >= 0 )
        {
          *a5 = v11;
          *a4 = v11[1];
          return (unsigned int)v12;
        }
      }
      else
      {
        v12 = -1073741584;
      }
      MIDL_user_free(v11);
      return (unsigned int)v12;
    }
  }
  return 3221225626LL;
}

```

## disassembly

```asm
0x1800012b0  push    rbp
0x1800012b2  push    rsi
0x1800012b3  push    rdi
0x1800012b4  push    r14
0x1800012b6  sub     rsp, 28h
0x1800012ba  mov     rax, cs:gLsapSspiExtension
0x1800012c1  mov     rsi, r9
0x1800012c4  mov     edi, edx
0x1800012c6  mov     rbp, r8
0x1800012c9  mov     r14, rcx
0x1800012cc  test    rax, rax
0x1800012cf  jz      loc_18000137E
0x1800012d5  cmp     qword ptr [rax+20h], 0
0x1800012da  jz      loc_18000137E
0x1800012e0  cmp     edi, 1F8h
0x1800012e6  ja      loc_18000138E
0x1800012ec  mov     rax, [rax]
0x1800012ef  mov     [rsp+48h+arg_0], rbx
0x1800012f4  test    rax, rax
0x1800012f7  jz      loc_18000139E
0x1800012fd  mov     ecx, 1F8h
0x180001302  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001307  mov     rbx, rax
0x18000130a  test    rax, rax
0x18000130d  jz      loc_18000139E
0x180001313  xor     edx, edx; Val
0x180001315  mov     r8d, 1F8h; Size
0x18000131b  mov     rcx, rax; void *
0x18000131e  call    memset_0
0x180001323  mov     r8d, edi; Size
0x180001326  mov     rdx, rbp; Src
0x180001329  mov     rcx, rbx; void *
0x18000132c  call    memcpy_0
0x180001331  movsx   ecx, word ptr [rbx+2]
0x180001335  cmp     ecx, edi
0x180001337  jnz     loc_1800013BD
0x18000133d  mov     rax, cs:gLsapSspiExtension
0x180001344  mov     rdx, rbx
0x180001347  mov     r8, [rsp+48h+arg_28]
0x18000134c  mov     rcx, r14
0x18000134f  mov     rax, [rax+20h]
0x180001353  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001358  mov     edi, eax
0x18000135a  test    eax, eax
0x18000135c  js      short loc_1800013B3
0x18000135e  mov     rcx, [rsp+48h+arg_20]
0x180001363  mov     [rcx], rbx
0x180001366  movsx   ecx, word ptr [rbx+2]
0x18000136a  mov     [rsi], ecx
0x18000136c  mov     rbx, [rsp+48h+arg_0]
0x180001371  mov     eax, edi
0x180001373  add     rsp, 28h
0x180001377  pop     r14
0x180001379  pop     rdi
0x18000137a  pop     rsi
0x18000137b  pop     rbp
0x18000137c  retn
0x18000137e  mov     eax, 0C00000BBh
0x180001383  add     rsp, 28h
0x180001387  pop     r14
0x180001389  pop     rdi
0x18000138a  pop     rsi
0x18000138b  pop     rbp
0x18000138c  retn
0x18000138e  mov     eax, 0C000000Dh
0x180001393  add     rsp, 28h
0x180001397  pop     r14
0x180001399  pop     rdi
0x18000139a  pop     rsi
0x18000139b  pop     rbp
0x18000139c  retn
0x18000139e  mov     rbx, [rsp+48h+arg_0]
0x1800013a3  mov     eax, 0C000009Ah
0x1800013a8  add     rsp, 28h
0x1800013ac  pop     r14
0x1800013ae  pop     rdi
0x1800013af  pop     rsi
0x1800013b0  pop     rbp
0x1800013b1  retn
0x1800013b3  mov     rcx, rbx; void *
0x1800013b6  call    MIDL_user_free
0x1800013bb  jmp     short loc_18000136C
0x1800013bd  mov     edi, 0C00000F0h
0x1800013c2  jmp     short loc_1800013B3
```
