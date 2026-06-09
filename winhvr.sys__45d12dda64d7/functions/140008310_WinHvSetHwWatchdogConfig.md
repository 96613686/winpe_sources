# WinHvSetHwWatchdogConfig

- ea: `0x140008310`
- end: `0x14000840e`
- name: `WinHvSetHwWatchdogConfig`
- size: `254`
- prototype: `__int64 __fastcall(void *Src, size_t Size)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, loader_planting, installer_update`

## callees

- `0x140002240`
- `0x140002358`
- `0x140004460`
- `0x140008310`
- `0x140009c90`
- `0x140009d40`
- `0x14000a040`

## pseudocode

```c
__int64 __fastcall WinHvSetHwWatchdogConfig(void *Src, size_t Size)
{
  unsigned int v2; // ebx
  unsigned int v4; // esi
  int v5; // edi
  size_t v6; // rbp
  int v7; // ebx
  _QWORD v9[8]; // [rsp+30h] [rbp-58h] BYREF
  void *v10; // [rsp+A0h] [rbp+18h] BYREF

  v2 = Size;
  memset(v9, 0, sizeof(v9));
  v4 = v2 - 1;
  v10 = 0;
  if ( v2 - 1 > 0xFFF )
    return 3221225485LL;
  v5 = 0;
  v6 = v2;
  while ( 1 )
  {
    WinHvpSetupHypercall((__int64 **)&v10, 0, (__int64)v9);
    memmove(v10, Src, v6);
    v7 = WinHvpVariableHeaderHypercall(246, v4, *(_QWORD *)(v9[5] + 24LL), *(_QWORD *)(v9[5] + 40LL));
    ((void (__fastcall *)(_QWORD))v9[7])(v9[0]);
    if ( v7 != -1070268299 && v7 != -1070268405 && (unsigned int)(v7 + 1070268287) > 1 )
      break;
    v7 = WinHvpLowMemoryHandler(-1, -2147418113, v7, 246, v5, 0);
    if ( v7 < 0 )
      break;
    ++v5;
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x140008310  mov     [rsp+arg_0], rbx
0x140008315  mov     [rsp+arg_8], rbp
0x14000831a  push    rsi
0x14000831b  push    rdi
0x14000831c  push    r14
0x14000831e  sub     rsp, 70h
0x140008322  mov     ebx, edx
0x140008324  mov     r14, rcx
0x140008327  xor     edx, edx; Val
0x140008329  lea     rcx, [rsp+88h+var_58]; void *
0x14000832e  lea     r8d, [rdx+40h]; Size
0x140008332  call    memset
0x140008337  lea     esi, [rbx-1]
0x14000833a  mov     [rsp+88h+arg_10], 0
0x140008346  cmp     esi, 0FFFh
0x14000834c  ja      loc_1400083F3
0x140008352  xor     edi, edi
0x140008354  mov     ebp, ebx
0x140008356  lea     r8, [rsp+88h+var_58]
0x14000835b  xor     edx, edx
0x14000835d  lea     rcx, [rsp+88h+arg_10]
0x140008365  call    WinHvpSetupHypercall
0x14000836a  mov     rcx, [rsp+88h+arg_10]; void *
0x140008372  mov     r8, rbp; Size
0x140008375  mov     rdx, r14; Src
0x140008378  call    memmove
0x14000837d  mov     r8, [rsp+88h+var_30]
0x140008382  mov     edx, esi
0x140008384  mov     ecx, 0F6h
0x140008389  mov     r9, [r8+28h]
0x14000838d  mov     r8, [r8+18h]
0x140008391  call    WinHvpVariableHeaderHypercall
0x140008396  mov     rcx, [rsp+88h+var_58]
0x14000839b  mov     ebx, eax
0x14000839d  mov     rax, [rsp+88h+var_20]
0x1400083a2  call    _guard_dispatch_icall
0x1400083a7  cmp     ebx, 0C0350075h
0x1400083ad  jz      short loc_1400083C2
0x1400083af  cmp     ebx, 0C035000Bh
0x1400083b5  jz      short loc_1400083C2
0x1400083b7  lea     ecx, [rbx+3FCAFF7Fh]
0x1400083bd  cmp     ecx, 1
0x1400083c0  ja      short loc_1400083EF
0x1400083c2  mov     [rsp+88h+var_60], 0
0x1400083c7  mov     r9d, 0F6h
0x1400083cd  mov     r8d, ebx
0x1400083d0  mov     [rsp+88h+var_68], edi
0x1400083d4  mov     edx, 8000FFFFh
0x1400083d9  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1400083dd  call    WinHvpLowMemoryHandler
0x1400083e2  mov     ebx, eax
0x1400083e4  test    eax, eax
0x1400083e6  js      short loc_1400083EF
0x1400083e8  inc     edi
0x1400083ea  jmp     loc_140008356
0x1400083ef  mov     eax, ebx
0x1400083f1  jmp     short loc_1400083F8
0x1400083f3  mov     eax, 0C000000Dh
0x1400083f8  lea     r11, [rsp+88h+var_18]
0x1400083fd  mov     rbx, [r11+20h]
0x140008401  mov     rbp, [r11+28h]
0x140008405  mov     rsp, r11
0x140008408  pop     r14
0x14000840a  pop     rdi
0x14000840b  pop     rsi
0x14000840c  retn
```
