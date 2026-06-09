# WPP_RECORDER_SF_qd

- ea: `0x1400014bc`
- end: `0x1400015d0`
- name: `WPP_RECORDER_SF_qd`
- size: `276`
- prototype: ``
- caller_count: `12`
- callee_count: `2`
- tags: ``

## callers

- `0x1400026d0`
- `0x14000be88`
- `0x14000c500`
- `0x14000e19c`
- `0x14000ea0c`
- `0x14000eff0`
- `0x1400190b0`
- `0x14001ab90`
- `0x14001c734`
- `0x14001cb74`
- `0x14001cf28`
- `0x14001d590`

## callees

- `0x1400014bc`
- `0x140010700`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x1400015b6`
- `WppRecorder!WppAutoLogTrace` at `0x1400015b6`

## pseudocode

```c
__int64 WPP_RECORDER_SF_qd(__int64 a1, unsigned __int8 a2, unsigned int a3, unsigned __int16 a4, __int64 a5, ...)
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
  return WppAutoLogTrace(a1, v8, a3, a5, v12, (__int64 *)va);
}

```

## disassembly

```asm
0x1400014bc  push    rbx
0x1400014be  push    rbp
0x1400014bf  push    rsi
0x1400014c0  push    rdi
0x1400014c1  push    r14
0x1400014c3  push    r15
0x1400014c5  sub     rsp, 58h
0x1400014c9  mov     r14d, r8d
0x1400014cc  mov     r15, rcx
0x1400014cf  mov     edi, r8d
0x1400014d2  shr     rdi, 10h
0x1400014d6  movzx   esi, dl
0x1400014d9  lea     ebx, [r14-1]
0x1400014dd  movzx   ebp, r9w
0x1400014e1  mov     r10d, ebx
0x1400014e4  and     ebx, 1Fh
0x1400014e7  shr     r10, 5
0x1400014eb  lea     rax, [rdi+rdi*4]
0x1400014ef  and     r10d, 7FFh
0x1400014f6  mov     edx, ebx
0x1400014f8  mov     ebx, 4
0x1400014fd  lea     r11, [r10+rax*4]
0x140001501  mov     r10, cs:WPP_GLOBAL_Control
0x140001508  mov     eax, [r10+r11*4+2Ch]
0x14000150d  bt      eax, edx
0x140001510  jnb     short loc_140001570
0x140001512  lea     rcx, [rdi+rdi*4]
0x140001516  add     rcx, rcx
0x140001519  cmp     [r10+rcx*8+29h], sil
0x14000151e  jb      short loc_140001570
0x140001520  mov     rax, cs:pfnWppTraceMessage
0x140001527  lea     rdx, [rsp+88h+arg_30]
0x14000152f  mov     r8, [rsp+88h+arg_20]
0x140001537  mov     r9d, ebp
0x14000153a  mov     rcx, [r10+rcx*8+18h]
0x14000153f  mov     [rsp+88h+var_48], 0
0x140001548  mov     [rsp+88h+var_50], rbx
0x14000154d  mov     [rsp+88h+var_58], rdx
0x140001552  lea     rdx, [rsp+88h+arg_28]
0x14000155a  mov     [rsp+88h+var_60], 8
0x140001563  mov     [rsp+88h+var_68], rdx
0x140001568  lea     edx, [rbx+27h]
0x14000156b  call    _guard_dispatch_icall
0x140001570  mov     r9, [rsp+88h+arg_20]
0x140001578  lea     rax, [rsp+88h+arg_30]
0x140001580  mov     [rsp+88h+var_40], 0
0x140001589  mov     r8d, r14d
0x14000158c  mov     [rsp+88h+var_48], rbx
0x140001591  mov     edx, esi
0x140001593  mov     [rsp+88h+var_50], rax
0x140001598  mov     rcx, r15
0x14000159b  lea     rax, [rsp+88h+arg_28]
0x1400015a3  mov     [rsp+88h+var_58], 8
0x1400015ac  mov     [rsp+88h+var_60], rax
0x1400015b1  mov     word ptr [rsp+88h+var_68], bp
0x1400015b6  call    cs:__imp_WppAutoLogTrace
0x1400015bd  nop     dword ptr [rax+rax+00h]
0x1400015c2  add     rsp, 58h
0x1400015c6  pop     r15
0x1400015c8  pop     r14
0x1400015ca  pop     rdi
0x1400015cb  pop     rsi
0x1400015cc  pop     rbp
0x1400015cd  pop     rbx
0x1400015ce  retn
```
