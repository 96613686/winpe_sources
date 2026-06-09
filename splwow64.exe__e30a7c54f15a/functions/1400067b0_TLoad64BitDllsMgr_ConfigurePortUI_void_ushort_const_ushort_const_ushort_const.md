# TLoad64BitDllsMgr::ConfigurePortUI(void *,ushort const *,ushort const *,ushort const *)

- ea: `0x1400067b0`
- end: `0x14000688d`
- name: `?ConfigurePortUI@TLoad64BitDllsMgr@@KAKPEAXPEBG11@Z`
- size: `221`
- prototype: `unsigned int __fastcall(void *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callees

- `0x1400067b0`
- `0x140006894`
- `0x140007298`
- `0x140007548`
- `0x140007d54`
- `0x140016010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140006826`
- `KERNEL32!GetLastError` at `0x140006854`
- `KERNEL32!GetLastError` at `0x140006826`
- `KERNEL32!GetLastError` at `0x140006854`

## pseudocode

```c
__int64 __fastcall TLoad64BitDllsMgr::ConfigurePortUI(
        void *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  DWORD LastError; // ebx
  TLoad64BitDllsMgr *v8; // rcx
  int v10; // [rsp+40h] [rbp-30h] BYREF
  unsigned int (__fastcall *v11)(const unsigned __int16 *, void *, const unsigned __int16 *); // [rsp+48h] [rbp-28h] BYREF
  unsigned __int64 v12; // [rsp+50h] [rbp-20h] BYREF
  void *v13; // [rsp+58h] [rbp-18h] BYREF
  void *v14[2]; // [rsp+60h] [rbp-10h] BYREF

  v14[0] = 0;
  v13 = 0;
  v12 = 0;
  v10 = 0;
  v11 = 0;
  if ( (unsigned int)TLoad64BitDllsMgr::LoadMonitorUIDll(
                       (__int64)v14,
                       a3,
                       0,
                       &v11,
                       (HMODULE *)v14,
                       (__int64 *)&v13,
                       &v12,
                       &v10) )
  {
    return GetLastError();
  }
  else
  {
    LastError = 0;
    TLoad64BitDllsMgr::IncUIRefCnt(pGLdrObj);
    if ( !v11(a2, a1, a4) )
      LastError = GetLastError();
    TLoad64BitDllsMgr::DecUIRefCnt(pGLdrObj);
    TLoad64BitDllsMgr::ReleaseMonitorActivationContext(v8, v14[0], v13, v12, v10);
  }
  return LastError;
}

```

## disassembly

```asm
0x1400067b0  mov     r11, rsp
0x1400067b3  push    rbp
0x1400067b4  push    rbx
0x1400067b5  push    rsi
0x1400067b6  push    rdi
0x1400067b7  push    r14
0x1400067b9  mov     rbp, rsp
0x1400067bc  sub     rsp, 70h
0x1400067c0  mov     r14, rcx
0x1400067c3  mov     [rbp+var_10], 0
0x1400067cb  mov     rax, r8
0x1400067ce  mov     [rbp+var_18], 0
0x1400067d6  lea     rcx, [rbp+var_30]
0x1400067da  mov     [rbp+var_20], 0
0x1400067e2  mov     [r11-60h], rcx
0x1400067e6  mov     rdi, r9
0x1400067e9  lea     rcx, [rbp+var_20]
0x1400067ed  mov     [rbp+var_30], 0
0x1400067f4  mov     [r11-68h], rcx
0x1400067f8  lea     r9, [rbp+var_28]
0x1400067fc  lea     rcx, [rbp+var_18]
0x140006800  mov     [rbp+var_28], 0
0x140006808  mov     [r11-70h], rcx
0x14000680c  mov     rsi, rdx
0x14000680f  lea     rcx, [rbp+var_10]
0x140006813  xor     r8d, r8d
0x140006816  mov     rdx, rax
0x140006819  mov     [r11-78h], rcx
0x14000681d  call    ?LoadMonitorUIDll@TLoad64BitDllsMgr@@IEBAKPEBGW4EPortOp@@PEAPEAX22PEA_KPEAH@Z; TLoad64BitDllsMgr::LoadMonitorUIDll(ushort const *,EPortOp,void * *,void * *,void * *,unsigned __int64 *,int *)
0x140006822  test    eax, eax
0x140006824  jz      short loc_140006830
0x140006826  call    cs:__imp_GetLastError
0x14000682c  mov     ebx, eax
0x14000682e  jmp     short loc_140006880
0x140006830  mov     rcx, cs:?pGLdrObj@@3PEAVTLoad64BitDllsMgr@@EA; this
0x140006837  xor     ebx, ebx
0x140006839  call    ?IncUIRefCnt@TLoad64BitDllsMgr@@QEAAXXZ; TLoad64BitDllsMgr::IncUIRefCnt(void)
0x14000683e  mov     rax, [rbp+var_28]
0x140006842  mov     r8, rdi
0x140006845  mov     rdx, r14
0x140006848  mov     rcx, rsi
0x14000684b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006850  test    eax, eax
0x140006852  jnz     short loc_14000685C
0x140006854  call    cs:__imp_GetLastError
0x14000685a  mov     ebx, eax
0x14000685c  mov     rcx, cs:?pGLdrObj@@3PEAVTLoad64BitDllsMgr@@EA; this
0x140006863  call    ?DecUIRefCnt@TLoad64BitDllsMgr@@QEAAXXZ; TLoad64BitDllsMgr::DecUIRefCnt(void)
0x140006868  mov     eax, [rbp+var_30]
0x14000686b  mov     r9, [rbp+var_20]; unsigned __int64
0x14000686f  mov     r8, [rbp+var_18]; void *
0x140006873  mov     rdx, [rbp+var_10]; void *
0x140006877  mov     [rsp+70h+var_50], eax; int
0x14000687b  call    ?ReleaseMonitorActivationContext@TLoad64BitDllsMgr@@IEBAXPEAX0_KH@Z; TLoad64BitDllsMgr::ReleaseMonitorActivationContext(void *,void *,unsigned __int64,int)
0x140006880  mov     eax, ebx
0x140006882  add     rsp, 70h
0x140006886  pop     r14
0x140006888  pop     rdi
0x140006889  pop     rsi
0x14000688a  pop     rbx
0x14000688b  pop     rbp
0x14000688c  retn
```
