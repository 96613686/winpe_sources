# WPP_RECORDER_SF_qD

- ea: `0x14000b4bc`
- end: `0x14000b5d0`
- name: `WPP_RECORDER_SF_qD`
- size: `276`
- prototype: ``
- caller_count: `30`
- callee_count: `2`
- tags: ``

## callers

- `0x140001314`
- `0x1400018b0`
- `0x140001bc8`
- `0x140002ad0`
- `0x140003470`
- `0x140003d08`
- `0x140003e88`
- `0x1400047d0`
- `0x140005350`
- `0x140005fc4`
- `0x140006d40`
- `0x140006f58`
- `0x140007c38`
- `0x140008230`
- `0x1400084c0`
- `0x140009d20`
- `0x14000e360`
- `0x14000eb6c`
- `0x140013314`
- `0x1400142fc`
- `0x1400145e0`
- `0x140023938`
- `0x1400242a4`
- `0x140025bd0`
- `0x140028440`
- `0x140029dac`
- `0x14002a2e0`
- `0x14002a82c`
- `0x14002ab6c`
- `0x14002e27c`

## callees

- `0x14000b4bc`
- `0x140014d50`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x14000b5b6`
- `WppRecorder!WppAutoLogTrace` at `0x14000b5b6`

## pseudocode

```c
__int64 WPP_RECORDER_SF_qD(__int64 a1, unsigned __int8 a2, unsigned int a3, unsigned __int16 a4, __int64 a5, ...)
{
  unsigned __int64 v7; // rdi
  unsigned int v8; // esi
  int v10; // eax
  int v12; // [rsp+20h] [rbp-68h]
  __int64 v13; // [rsp+B8h] [rbp+30h] BYREF
  va_list va; // [rsp+B8h] [rbp+30h]
  va_list va1; // [rsp+C0h] [rbp+38h] BYREF

  va_start(va1, a5);
  va_start(va, a5);
  v13 = va_arg(va1, _QWORD);
  v7 = (unsigned __int64)a3 >> 16;
  v8 = a2;
  v10 = *((_DWORD *)&WPP_GLOBAL_Control->Timer + 20 * v7 + (((a3 - 1) >> 5) & 0x7FF) + 1);
  if ( _bittest(&v10, ((_BYTE)a3 - 1) & 0x1F) && *((_BYTE *)&WPP_GLOBAL_Control->Timer + 80 * v7 + 1) >= a2 )
    ((void (__fastcall *)(_QWORD, __int64, __int64, _QWORD, __int64 *, __int64, char *, __int64, _QWORD))pfnWppTraceMessage)(
      *((_QWORD *)&WPP_GLOBAL_Control->AttachedDevice + 10 * v7),
      43,
      a5,
      a4,
      (__int64 *)va,
      8,
      va1,
      4,
      0);
  LOWORD(v12) = a4;
  return WppAutoLogTrace(a1, v8, a3, a5, v12, (__int64 *)va, 8, va1, 4, 0);
}

```

## disassembly

```asm
0x14000b4bc  push    rbx
0x14000b4be  push    rbp
0x14000b4bf  push    rsi
0x14000b4c0  push    rdi
0x14000b4c1  push    r14
0x14000b4c3  push    r15
0x14000b4c5  sub     rsp, 58h
0x14000b4c9  mov     r14d, r8d
0x14000b4cc  mov     r15, rcx
0x14000b4cf  mov     edi, r8d
0x14000b4d2  shr     rdi, 10h
0x14000b4d6  movzx   esi, dl
0x14000b4d9  lea     ebx, [r14-1]
0x14000b4dd  movzx   ebp, r9w
0x14000b4e1  mov     r10d, ebx
0x14000b4e4  and     ebx, 1Fh
0x14000b4e7  shr     r10, 5
0x14000b4eb  lea     rax, [rdi+rdi*4]
0x14000b4ef  and     r10d, 7FFh
0x14000b4f6  mov     edx, ebx
0x14000b4f8  mov     ebx, 4
0x14000b4fd  lea     r11, [r10+rax*4]
0x14000b501  mov     r10, cs:WPP_GLOBAL_Control
0x14000b508  mov     eax, [r10+r11*4+2Ch]
0x14000b50d  bt      eax, edx
0x14000b510  jnb     short loc_14000B570
0x14000b512  lea     rcx, [rdi+rdi*4]
0x14000b516  add     rcx, rcx
0x14000b519  cmp     [r10+rcx*8+29h], sil
0x14000b51e  jb      short loc_14000B570
0x14000b520  mov     rax, cs:pfnWppTraceMessage
0x14000b527  lea     rdx, [rsp+88h+arg_30]
0x14000b52f  mov     r8, [rsp+88h+arg_20]
0x14000b537  mov     r9d, ebp
0x14000b53a  mov     rcx, [r10+rcx*8+18h]
0x14000b53f  mov     [rsp+88h+var_48], 0
0x14000b548  mov     [rsp+88h+var_50], rbx
0x14000b54d  mov     [rsp+88h+var_58], rdx
0x14000b552  lea     rdx, [rsp+88h+arg_28]
0x14000b55a  mov     [rsp+88h+var_60], 8
0x14000b563  mov     [rsp+88h+var_68], rdx
0x14000b568  lea     edx, [rbx+27h]
0x14000b56b  call    _guard_dispatch_icall
0x14000b570  mov     r9, [rsp+88h+arg_20]
0x14000b578  lea     rax, [rsp+88h+arg_30]
0x14000b580  mov     [rsp+88h+var_40], 0
0x14000b589  mov     r8d, r14d
0x14000b58c  mov     [rsp+88h+var_48], rbx
0x14000b591  mov     edx, esi
0x14000b593  mov     [rsp+88h+var_50], rax
0x14000b598  mov     rcx, r15
0x14000b59b  lea     rax, [rsp+88h+arg_28]
0x14000b5a3  mov     [rsp+88h+var_58], 8
0x14000b5ac  mov     [rsp+88h+var_60], rax
0x14000b5b1  mov     word ptr [rsp+88h+var_68], bp
0x14000b5b6  call    cs:__imp_WppAutoLogTrace
0x14000b5bd  nop     dword ptr [rax+rax+00h]
0x14000b5c2  add     rsp, 58h
0x14000b5c6  pop     r15
0x14000b5c8  pop     r14
0x14000b5ca  pop     rdi
0x14000b5cb  pop     rsi
0x14000b5cc  pop     rbp
0x14000b5cd  pop     rbx
0x14000b5ce  retn
```
