# SspGetTokenBufferByIndex

- ea: `0x18000d9d0`
- end: `0x18000dafa`
- name: `SspGetTokenBufferByIndex`
- size: `298`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x18001e4b0`
- `0x1800206d0`

## callees

- `0x18000d9d0`
- `0x180011fec`
- `0x1800185b8`
- `0x180038010`

## pseudocode

```c
char __fastcall SspGetTokenBufferByIndex(__int64 a1, unsigned int a2, __int64 *a3, char a4)
{
  __int64 v5; // rbx
  int v6; // eax
  _QWORD *v8; // rcx
  __int64 v9; // rdx

  if ( !a1 )
    return 0;
  if ( *(_DWORD *)a1 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return 0;
    v9 = 380;
LABEL_13:
    WPP_SF_(v8[2], v9, &WPP_0ed1b0878c133b2013fdb6f803dbb21a_Traceguids);
    return 0;
  }
  if ( a2 >= *(_DWORD *)(a1 + 4) )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return 0;
    v9 = 381;
    goto LABEL_13;
  }
  v5 = *(_QWORD *)(a1 + 8) + 16LL * a2;
  if ( !a4 && *(int *)(v5 + 4) < 0 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      return 0;
    v9 = 382;
    goto LABEL_13;
  }
  if ( !*(_DWORD *)v5
    || !*(_QWORD *)(v5 + 8)
    || (v6 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)&g_LsaFunctions + 152LL))(
               v5,
               *(_QWORD *)(a1 + 8) + 16LL * a2),
        v6 >= 0) )
  {
    *a3 = v5;
    return 1;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      383,
      &WPP_0ed1b0878c133b2013fdb6f803dbb21a_Traceguids,
      (unsigned int)v6);
  return 0;
}

```

## disassembly

```asm
0x18000d9d0  mov     [rsp+arg_0], rbx
0x18000d9d5  push    rdi
0x18000d9d6  sub     rsp, 20h
0x18000d9da  mov     rdi, r8
0x18000d9dd  test    rcx, rcx
0x18000d9e0  jz      loc_18000DAF3
0x18000d9e6  cmp     dword ptr [rcx], 0
0x18000d9e9  jnz     loc_18000DA82
0x18000d9ef  cmp     edx, [rcx+4]
0x18000d9f2  jnb     loc_18000DAA2
0x18000d9f8  mov     ebx, edx
0x18000d9fa  shl     rbx, 4
0x18000d9fe  add     rbx, [rcx+8]
0x18000da02  test    r9b, r9b
0x18000da05  jz      short loc_18000DA44
0x18000da07  cmp     dword ptr [rbx], 0
0x18000da0a  jz      short loc_18000DA34
0x18000da0c  cmp     qword ptr [rbx+8], 0
0x18000da11  jz      short loc_18000DA34
0x18000da13  mov     rax, cs:g_LsaFunctions
0x18000da1a  mov     rdx, rbx
0x18000da1d  mov     rcx, rbx
0x18000da20  mov     rax, [rax+98h]
0x18000da27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000da2c  test    eax, eax
0x18000da2e  js      loc_18000DAC2
0x18000da34  mov     [rdi], rbx
0x18000da37  mov     al, 1
0x18000da39  mov     rbx, [rsp+28h+arg_0]
0x18000da3e  add     rsp, 20h
0x18000da42  pop     rdi
0x18000da43  retn
0x18000da44  cmp     dword ptr [rbx+4], 0
0x18000da48  jge     short loc_18000DA07
0x18000da4a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000da51  lea     rdx, WPP_GLOBAL_Control
0x18000da58  cmp     rcx, rdx
0x18000da5b  jz      loc_18000DAF3
0x18000da61  test    byte ptr [rcx+1Ch], 4
0x18000da65  jz      loc_18000DAF3
0x18000da6b  mov     edx, 17Eh
0x18000da70  mov     rcx, [rcx+10h]
0x18000da74  lea     r8, WPP_0ed1b0878c133b2013fdb6f803dbb21a_Traceguids
0x18000da7b  call    WPP_SF_
0x18000da80  jmp     short loc_18000DAF3
0x18000da82  mov     rcx, cs:WPP_GLOBAL_Control
0x18000da89  lea     rdx, WPP_GLOBAL_Control
0x18000da90  cmp     rcx, rdx
0x18000da93  jz      short loc_18000DAF3
0x18000da95  test    byte ptr [rcx+1Ch], 1
0x18000da99  jz      short loc_18000DAF3
0x18000da9b  mov     edx, 17Ch
0x18000daa0  jmp     short loc_18000DA70
0x18000daa2  mov     rcx, cs:WPP_GLOBAL_Control
0x18000daa9  lea     rdx, WPP_GLOBAL_Control
0x18000dab0  cmp     rcx, rdx
0x18000dab3  jz      short loc_18000DAF3
0x18000dab5  test    byte ptr [rcx+1Ch], 1
0x18000dab9  jz      short loc_18000DAF3
0x18000dabb  mov     edx, 17Dh
0x18000dac0  jmp     short loc_18000DA70
0x18000dac2  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dac9  lea     rdx, WPP_GLOBAL_Control
0x18000dad0  cmp     rcx, rdx
0x18000dad3  jz      short loc_18000DAF3
0x18000dad5  test    byte ptr [rcx+1Ch], 1
0x18000dad9  jz      short loc_18000DAF3
0x18000dadb  mov     rcx, [rcx+10h]
0x18000dadf  lea     r8, WPP_0ed1b0878c133b2013fdb6f803dbb21a_Traceguids
0x18000dae6  mov     edx, 17Fh
0x18000daeb  mov     r9d, eax
0x18000daee  call    WPP_SF_d
0x18000daf3  xor     al, al
0x18000daf5  jmp     loc_18000DA39
```
