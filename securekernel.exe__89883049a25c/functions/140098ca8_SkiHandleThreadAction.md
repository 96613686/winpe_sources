# SkiHandleThreadAction

- ea: `0x140098ca8`
- end: `0x140098d52`
- name: `SkiHandleThreadAction`
- size: `170`
- prototype: `__int64(void)`
- caller_count: `16`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x1400eef20`
- `0x1400f0850`
- `0x1400f0b40`
- `0x1400f0f70`
- `0x1400f1420`
- `0x1400f1a50`
- `0x1400f1f30`
- `0x1400f2410`
- `0x1400f28f0`
- `0x1400f30c0`
- `0x1400f3c20`
- `0x1400f5440`
- `0x1400f6b00`
- `0x1400f89c0`
- `0x1400f9040`
- `0x1400f9340`

## callees

- `0x140098ca8`
- `0x140099358`
- `0x1400b1190`
- `0x1400f9a80`

## pseudocode

```c
__int64 __fastcall SkiHandleThreadAction(__int64 a1)
{
  __int64 v2; // rbx
  __int64 result; // rax
  _DWORD v4[4]; // [rsp+20h] [rbp-A8h] BYREF
  __int64 v5; // [rsp+30h] [rbp-98h]

  if ( (*(_DWORD *)(a1 + 172) & 0x1000) != 0 )
  {
    v2 = *(_QWORD *)(a1 + 112);
    memset_0(v4, 0, 0x98u);
    v5 = *(_QWORD *)(v2 - 40);
    v4[0] = -1073740523;
    SkpsDispatchBasicEnclaveException(a1, v4, v2 - 400);
    _InterlockedAnd((volatile signed __int32 *)(a1 + 172), 0xFFFFEFFF);
  }
  if ( (*(_DWORD *)(a1 + 172) & 0x4000) != 0 )
  {
    *(_QWORD *)(a1 + 312) = 0;
    _InterlockedAnd((volatile signed __int32 *)(a1 + 172), 0xFFFFBFFF);
  }
  result = *(unsigned int *)(a1 + 172);
  if ( (result & 2) != 0 )
  {
    SkiTerminateThread(0, 0);
    JUMPOUT(0x140098D51LL);
  }
  return result;
}

```

## disassembly

```asm
0x140098ca8  mov     [rsp+arg_0], rbx
0x140098cad  push    rdi
0x140098cae  sub     rsp, 0C0h
0x140098cb5  mov     eax, [rcx+0ACh]
0x140098cbb  mov     rdi, rcx
0x140098cbe  bt      eax, 0Ch
0x140098cc2  jnb     short loc_140098D0A
0x140098cc4  mov     rbx, [rcx+70h]
0x140098cc8  xor     edx, edx; Val
0x140098cca  lea     rcx, [rsp+0C8h+var_A8]; void *
0x140098ccf  mov     r8d, 98h; Size
0x140098cd5  call    memset_0
0x140098cda  mov     rax, [rbx-28h]
0x140098cde  lea     r8, [rbx-190h]
0x140098ce5  lea     rdx, [rsp+0C8h+var_A8]
0x140098cea  mov     [rsp+0C8h+var_98], rax
0x140098cef  mov     rcx, rdi
0x140098cf2  mov     [rsp+0C8h+var_A8], 0C0000515h
0x140098cfa  call    SkpsDispatchBasicEnclaveException
0x140098cff  lock and dword ptr [rdi+0ACh], 0FFFFEFFFh
0x140098d0a  mov     eax, [rdi+0ACh]
0x140098d10  bt      eax, 0Eh
0x140098d14  jnb     short loc_140098D2C
0x140098d16  mov     qword ptr [rdi+138h], 0
0x140098d21  lock and dword ptr [rdi+0ACh], 0FFFFBFFFh
0x140098d2c  mov     eax, [rdi+0ACh]
0x140098d32  test    al, 2
0x140098d34  jnz     short loc_140098D48
0x140098d36  mov     rbx, [rsp+0C8h+arg_0]
0x140098d3e  add     rsp, 0C0h
0x140098d45  pop     rdi
0x140098d46  retn
0x140098d48  xor     edx, edx
0x140098d4a  xor     ecx, ecx
0x140098d4c  call    SkiTerminateThread
```
