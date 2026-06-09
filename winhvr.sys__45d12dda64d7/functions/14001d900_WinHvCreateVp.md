# WinHvCreateVp

- ea: `0x14001d900`
- end: `0x14001d9c2`
- name: `WinHvCreateVp`
- size: `194`
- prototype: `__int64 __usercall@<rax>(int@<ecx>, int@<edx>, __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x140001ef0`
- `0x140004408`
- `0x14001d900`
- `0x14001d9e0`
- `0x1400226bc`

## pseudocode

```c
__int64 __fastcall WinHvCreateVp(__int64 a1, __int64 a2, __int64 *a3, int a4, __int64 a5)
{
  unsigned int v7; // ebp
  __int64 v8; // rax
  int VpObject; // ebx
  __int64 Src; // [rsp+40h] [rbp-58h] BYREF
  int v12; // [rsp+48h] [rbp-50h]
  __int16 v13; // [rsp+4Ch] [rbp-4Ch]
  char v14; // [rsp+4Eh] [rbp-4Ah]
  char v15; // [rsp+4Fh] [rbp-49h]
  __int64 v16; // [rsp+50h] [rbp-48h]
  __int64 v17; // [rsp+58h] [rbp-40h] BYREF
  __int64 v18; // [rsp+60h] [rbp-38h]

  v13 = 0;
  v14 = 0;
  v7 = a2;
  v17 = 0;
  v18 = 0;
  v8 = *a3;
  Src = a1;
  v12 = a4;
  v16 = v8;
  v15 = *((_BYTE *)a3 + 8);
  WinHvpSetProximityDomain(&v17, a2);
  v18 = a5;
  VpObject = WinHvpAllocatingHypercall(a1, v7, 78, 0, &Src, 0x28u, 0, 0);
  if ( VpObject >= 0 )
  {
    if ( WinHvpRootSchedulerActive )
    {
      VpObject = WinHvpCreateVpObject(a1, a4, v7);
      if ( VpObject < 0 )
        WinHvDeleteVp(a1, a4);
    }
  }
  return (unsigned int)VpObject;
}

```

## disassembly

```asm
0x14001d900  mov     r11, rsp
0x14001d903  push    rbx
0x14001d904  push    rbp
0x14001d905  push    rsi
0x14001d906  push    rdi
0x14001d907  sub     rsp, 78h
0x14001d90b  xor     eax, eax
0x14001d90d  mov     rdi, rcx
0x14001d910  mov     [rsp+98h+var_4C], ax
0x14001d915  mov     esi, r9d
0x14001d918  mov     [rsp+98h+var_4A], al
0x14001d91c  mov     ebp, edx
0x14001d91e  mov     [r11-40h], rax
0x14001d922  mov     [r11-38h], rax
0x14001d926  mov     rax, [r8]
0x14001d929  mov     [r11-58h], rcx
0x14001d92d  lea     rcx, [r11-40h]
0x14001d931  mov     [rsp+98h+var_50], r9d
0x14001d936  mov     [r11-48h], rax
0x14001d93a  mov     al, [r8+8]
0x14001d93e  mov     [rsp+98h+var_49], al
0x14001d942  call    WinHvpSetProximityDomain
0x14001d947  mov     rcx, [rsp+98h+arg_20]
0x14001d94f  lea     rax, [rsp+98h+var_58]
0x14001d954  mov     [rsp+98h+var_60], 0; size_t
0x14001d95d  xor     r9d, r9d; int
0x14001d960  mov     [rsp+98h+var_38], rcx
0x14001d965  mov     edx, ebp; int
0x14001d967  mov     [rsp+98h+var_68], 0; void *
0x14001d970  mov     rcx, rdi; int
0x14001d973  mov     [rsp+98h+Size], 28h ; '('; Size
0x14001d97c  lea     r8d, [r9+4Eh]; int
0x14001d980  mov     [rsp+98h+Src], rax; Src
0x14001d985  call    WinHvpAllocatingHypercall
0x14001d98a  mov     ebx, eax
0x14001d98c  test    eax, eax
0x14001d98e  js      short loc_14001D9B6
0x14001d990  cmp     cs:WinHvpRootSchedulerActive, 0
0x14001d997  jz      short loc_14001D9B6
0x14001d999  mov     r8d, ebp
0x14001d99c  mov     edx, esi
0x14001d99e  mov     rcx, rdi
0x14001d9a1  call    WinHvpCreateVpObject
0x14001d9a6  mov     ebx, eax
0x14001d9a8  test    eax, eax
0x14001d9aa  jns     short loc_14001D9B6
0x14001d9ac  mov     edx, esi
0x14001d9ae  mov     rcx, rdi
0x14001d9b1  call    WinHvDeleteVp
0x14001d9b6  mov     eax, ebx
0x14001d9b8  add     rsp, 78h
0x14001d9bc  pop     rdi
0x14001d9bd  pop     rsi
0x14001d9be  pop     rbp
0x14001d9bf  pop     rbx
0x14001d9c0  retn
```
