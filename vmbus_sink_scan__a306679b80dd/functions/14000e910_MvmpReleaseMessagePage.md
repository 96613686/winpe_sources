# MvmpReleaseMessagePage

- ea: `0x14000e910`
- end: `0x14000e9ed`
- name: `MvmpReleaseMessagePage`
- size: `221`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `6`
- callee_count: `3`
- tags: ``

## callers

- `0x14000d300`
- `0x14000d410`
- `0x14000d620`
- `0x14000d704`
- `0x14000d910`
- `0x14000da50`

## callees

- `0x14000b42c`
- `0x14000e910`
- `0x14000eaa8`

## pseudocode

```c
__int64 __fastcall MvmpReleaseMessagePage(__int64 a1, int a2)
{
  __int64 v4; // rcx
  __int64 v5; // rdx
  __int64 result; // rax
  int v7; // esi
  bool v8; // zf

  v4 = *(_QWORD *)(a1 + 32);
  if ( v4 == *(_QWORD *)(a1 + 40) )
  {
    MvmpSetVpRegister(a1, a2, 1073741955, *(_QWORD *)(a1 + 200), 2);
  }
  else
  {
    if ( *(_BYTE *)(a1 + 189) )
      v5 = *(_QWORD *)(a1 + 80);
    else
      v5 = 0;
    MvmUnmapPage(v4, v5);
  }
  result = *(unsigned int *)(a1 + 92);
  *(_QWORD *)(a1 + 32) = 0;
  if ( (_DWORD)result )
  {
    v7 = result + 1073741968;
    result = MvmpSetVpRegister(a1, 0, (int)result + 1073741968, *(_DWORD *)(a1 + 96) | 0x10000u, 1);
    v8 = *(_DWORD *)(a1 + 216) == 2;
    *(_QWORD *)(a1 + 96) = 0;
    if ( v8 )
    {
      result = MvmpSetVpRegister(a1, a2, v7, (unsigned int)*(_QWORD *)(a1 + 192) | 0x10000, 0);
      *(_QWORD *)(a1 + 192) = 0;
    }
    *(_DWORD *)(a1 + 92) = 0;
  }
  return result;
}

```

## disassembly

```asm
0x14000e910  mov     [rsp+arg_0], rbx
0x14000e915  mov     [rsp+arg_8], rsi
0x14000e91a  push    rdi
0x14000e91b  sub     rsp, 30h
0x14000e91f  mov     rbx, rcx
0x14000e922  mov     rdi, rdx
0x14000e925  mov     rcx, [rcx+20h]
0x14000e929  cmp     rcx, [rbx+28h]
0x14000e92d  jnz     short loc_14000E94E
0x14000e92f  mov     r9, [rbx+0C8h]
0x14000e936  mov     r8d, 40000083h
0x14000e93c  mov     rcx, rbx
0x14000e93f  mov     [rsp+38h+var_18], 2
0x14000e947  call    MvmpSetVpRegister
0x14000e94c  jmp     short loc_14000E964
0x14000e94e  cmp     byte ptr [rbx+0BDh], 0
0x14000e955  jz      short loc_14000E95D
0x14000e957  mov     rdx, [rbx+50h]
0x14000e95b  jmp     short loc_14000E95F
0x14000e95d  xor     edx, edx
0x14000e95f  call    MvmUnmapPage
0x14000e964  mov     eax, [rbx+5Ch]
0x14000e967  mov     qword ptr [rbx+20h], 0
0x14000e96f  test    eax, eax
0x14000e971  jz      short loc_14000E9DC
0x14000e973  mov     r9, [rbx+60h]
0x14000e977  lea     esi, [rax+40000090h]
0x14000e97d  bts     r9, 10h
0x14000e982  mov     [rsp+38h+var_18], 1
0x14000e98a  mov     r8d, esi
0x14000e98d  xor     edx, edx
0x14000e98f  mov     rcx, rbx
0x14000e992  call    MvmpSetVpRegister
0x14000e997  cmp     dword ptr [rbx+0D8h], 2
0x14000e99e  mov     qword ptr [rbx+60h], 0
0x14000e9a6  jnz     short loc_14000E9D5
0x14000e9a8  mov     r9, [rbx+0C0h]
0x14000e9af  mov     r8d, esi
0x14000e9b2  bts     r9, 10h
0x14000e9b7  mov     [rsp+38h+var_18], 0
0x14000e9bf  mov     rdx, rdi
0x14000e9c2  mov     rcx, rbx
0x14000e9c5  call    MvmpSetVpRegister
0x14000e9ca  mov     qword ptr [rbx+0C0h], 0
0x14000e9d5  mov     dword ptr [rbx+5Ch], 0
0x14000e9dc  mov     rbx, [rsp+38h+arg_0]
0x14000e9e1  mov     rsi, [rsp+38h+arg_8]
0x14000e9e6  add     rsp, 30h
0x14000e9ea  pop     rdi
0x14000e9eb  retn
```
