# WPP_RECORDER_SF_dD

- ea: `0x14000193c`
- end: `0x140001a46`
- name: `WPP_RECORDER_SF_dD`
- size: `266`
- prototype: ``
- caller_count: `27`
- callee_count: `2`
- tags: ``

## callers

- `0x140001e04`
- `0x1400024d0`
- `0x1400026d0`
- `0x1400034cc`
- `0x140003a20`
- `0x140003e7c`
- `0x140004130`
- `0x140004740`
- `0x140004908`
- `0x140004ea4`
- `0x1400055fc`
- `0x140005838`
- `0x140005fe8`
- `0x140006dec`
- `0x140008df0`
- `0x140009634`
- `0x1400099d0`
- `0x14000a450`
- `0x14000af00`
- `0x14000b3fc`
- `0x14000b670`
- `0x14000ca60`
- `0x14000d3ac`
- `0x14000e19c`
- `0x14000eff0`
- `0x14001c2f0`
- `0x14001c940`

## callees

- `0x14000193c`
- `0x140010700`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x140001a2c`
- `WppRecorder!WppAutoLogTrace` at `0x140001a2c`

## pseudocode

```c
__int64 WPP_RECORDER_SF_dD(__int64 a1, unsigned __int8 a2, unsigned int a3, unsigned __int16 a4, __int64 a5, ...)
{
  unsigned __int64 v7; // rbx
  unsigned int v9; // edi
  int v10; // eax
  int v12; // [rsp+20h] [rbp-68h]
  __int64 v13; // [rsp+B8h] [rbp+30h] BYREF
  va_list va; // [rsp+B8h] [rbp+30h]
  va_list va1; // [rsp+C0h] [rbp+38h] BYREF

  va_start(va1, a5);
  va_start(va, a5);
  v13 = va_arg(va1, _QWORD);
  v7 = (unsigned __int64)a3 >> 16;
  v9 = a2;
  v10 = *((_DWORD *)&WPP_GLOBAL_Control->Timer + 20 * v7 + (((a3 - 1) >> 5) & 0x7FF) + 1);
  if ( _bittest(&v10, a3 - 1) && *((_BYTE *)&WPP_GLOBAL_Control->Timer + 80 * v7 + 1) >= a2 )
    ((void (__fastcall *)(_QWORD, __int64, __int64, _QWORD, __int64 *, __int64, char *, __int64, _QWORD))pfnWppTraceMessage)(
      *((_QWORD *)&WPP_GLOBAL_Control->AttachedDevice + 10 * v7),
      43,
      a5,
      a4,
      (__int64 *)va,
      4,
      va1,
      4,
      0);
  LOWORD(v12) = a4;
  return WppAutoLogTrace(a1, v9, a3, a5, v12, (__int64 *)va, 4, va1, 4, 0);
}

```

## disassembly

```asm
0x14000193c  push    rbx
0x14000193e  push    rbp
0x14000193f  push    rsi
0x140001940  push    rdi
0x140001941  push    r14
0x140001943  push    r15
0x140001945  sub     rsp, 58h
0x140001949  mov     ebp, r8d
0x14000194c  mov     r14, rcx
0x14000194f  mov     ebx, r8d
0x140001952  mov     r15d, 4
0x140001958  shr     rbx, 10h
0x14000195c  movzx   esi, r9w
0x140001960  lea     r11d, [rbp-1]
0x140001964  movzx   edi, dl
0x140001967  mov     r10d, r11d
0x14000196a  shr     r10, 5
0x14000196e  lea     rax, [rbx+rbx*4]
0x140001972  and     r10d, 7FFh
0x140001979  lea     rax, [r10+rax*4]
0x14000197d  mov     r10, cs:WPP_GLOBAL_Control
0x140001984  mov     eax, [r10+rax*4+2Ch]
0x140001989  bt      eax, r11d
0x14000198d  jnb     short loc_1400019EA
0x14000198f  lea     rcx, [rbx+rbx*4]
0x140001993  add     rcx, rcx
0x140001996  cmp     [r10+rcx*8+29h], dil
0x14000199b  jb      short loc_1400019EA
0x14000199d  mov     rax, cs:pfnWppTraceMessage
0x1400019a4  lea     rdx, [rsp+88h+arg_30]
0x1400019ac  mov     r8, [rsp+88h+arg_20]
0x1400019b4  mov     r9d, esi
0x1400019b7  mov     rcx, [r10+rcx*8+18h]
0x1400019bc  mov     [rsp+88h+var_48], 0
0x1400019c5  mov     [rsp+88h+var_50], r15
0x1400019ca  mov     [rsp+88h+var_58], rdx
0x1400019cf  lea     rdx, [rsp+88h+arg_28]
0x1400019d7  mov     [rsp+88h+var_60], r15
0x1400019dc  mov     [rsp+88h+var_68], rdx
0x1400019e1  lea     edx, [r15+27h]
0x1400019e5  call    _guard_dispatch_icall
0x1400019ea  mov     r9, [rsp+88h+arg_20]
0x1400019f2  lea     rax, [rsp+88h+arg_30]
0x1400019fa  mov     [rsp+88h+var_40], 0
0x140001a03  mov     r8d, ebp
0x140001a06  mov     [rsp+88h+var_48], r15
0x140001a0b  mov     edx, edi
0x140001a0d  mov     [rsp+88h+var_50], rax
0x140001a12  mov     rcx, r14
0x140001a15  lea     rax, [rsp+88h+arg_28]
0x140001a1d  mov     [rsp+88h+var_58], r15
0x140001a22  mov     [rsp+88h+var_60], rax
0x140001a27  mov     word ptr [rsp+88h+var_68], si
0x140001a2c  call    cs:__imp_WppAutoLogTrace
0x140001a33  nop     dword ptr [rax+rax+00h]
0x140001a38  add     rsp, 58h
0x140001a3c  pop     r15
0x140001a3e  pop     r14
0x140001a40  pop     rdi
0x140001a41  pop     rsi
0x140001a42  pop     rbp
0x140001a43  pop     rbx
0x140001a44  retn
```
