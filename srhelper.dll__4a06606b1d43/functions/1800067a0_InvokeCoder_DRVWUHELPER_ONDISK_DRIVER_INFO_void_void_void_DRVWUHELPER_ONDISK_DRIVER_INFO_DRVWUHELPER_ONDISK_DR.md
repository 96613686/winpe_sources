# InvokeCoder<_DRVWUHELPER_ONDISK_DRIVER_INFO>(void *,void (*)(void *,_DRVWUHELPER_ONDISK_DRIVER_INFO *),_DRVWUHELPER_ONDISK_DRIVER_INFO *)

- ea: `0x1800067a0`
- end: `0x180006838`
- name: `??$InvokeCoder@U_DRVWUHELPER_ONDISK_DRIVER_INFO@@@@YAJPEAXP6AX0PEAU_DRVWUHELPER_ONDISK_DRIVER_INFO@@@Z1@Z`
- size: `152`
- prototype: `__int64 __fastcall(__int64, void (__fastcall *)(__int64, __int64), __int64)`
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x180005e30`
- `0x1800062e8`
- `0x180006840`
- `0x180006b50`

## callees

- `0x180003ce0`
- `0x180005df0`
- `0x1800067a0`
- `0x180016010`

## import_xrefs

- `RPCRT4!I_RpcExceptionFilter` at `0x180015be4`
- `RPCRT4!I_RpcExceptionFilter` at `0x180015be4`

## pseudocode

```c
__int64 __fastcall InvokeCoder<_DRVWUHELPER_ONDISK_DRIVER_INFO>(
        __int64 a1,
        void (__fastcall *a2)(__int64, __int64),
        __int64 a3)
{
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_2c5669c0156b363454a636adea0dbbf0_Traceguids);
  a2(a1, a3);
  return 0;
}

```

## disassembly

```asm
0x1800067a0  push    rbx
0x1800067a2  push    rsi
0x1800067a3  push    rdi
0x1800067a4  push    r14
0x1800067a6  sub     rsp, 28h
0x1800067aa  mov     rdi, r8
0x1800067ad  mov     rsi, rdx
0x1800067b0  mov     r14, rcx
0x1800067b3  xor     ebx, ebx
0x1800067b5  lea     rax, WPP_GLOBAL_Control
0x1800067bc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800067c3  cmp     rcx, rax
0x1800067c6  jz      short loc_1800067E5
0x1800067c8  test    dword ptr [rcx+1Ch], 20000000h
0x1800067cf  jz      short loc_1800067E5
0x1800067d1  lea     edx, [rbx+0Ah]
0x1800067d4  lea     r8, WPP_2c5669c0156b363454a636adea0dbbf0_Traceguids
0x1800067db  mov     rcx, [rcx+10h]
0x1800067df  call    WPP_SF_
0x1800067e4  nop
0x1800067e5  mov     rdx, rdi
0x1800067e8  mov     rcx, r14
0x1800067eb  mov     rax, rsi
0x1800067ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800067f3  jmp     short loc_18000682C
0x1800067f5  mov     ebx, eax
0x1800067f7  lea     rax, WPP_GLOBAL_Control
0x1800067fe  mov     rcx, cs:WPP_GLOBAL_Control
0x180006805  cmp     rcx, rax
0x180006808  jz      short loc_18000682C
0x18000680a  test    dword ptr [rcx+1Ch], 2000000h
0x180006811  jz      short loc_18000682C
0x180006813  mov     edx, 0Bh
0x180006818  mov     r9d, ebx
0x18000681b  lea     r8, WPP_2c5669c0156b363454a636adea0dbbf0_Traceguids
0x180006822  mov     rcx, [rcx+10h]
0x180006826  call    WPP_SF_D
0x18000682b  nop
0x18000682c  mov     eax, ebx
0x18000682e  add     rsp, 28h
0x180006832  pop     r14
0x180006834  pop     rdi
0x180006835  pop     rsi
0x180006836  pop     rbx
0x180006837  retn
0x180015bd6  push    rbp
0x180015bd8  sub     rsp, 20h
0x180015bdc  mov     rbp, rdx
0x180015bdf  mov     rcx, [rcx]
0x180015be2  mov     ecx, [rcx]; ExceptionCode
0x180015be4  call    cs:__imp_I_RpcExceptionFilter
0x180015bea  nop
0x180015beb  add     rsp, 20h
0x180015bef  pop     rbp
0x180015bf0  retn
```
